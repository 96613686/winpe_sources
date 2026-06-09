# Resources::classInit(bool)

- ea: `0x1800777bc`
- end: `0x1800778f8`
- name: `?classInit@Resources@@SAX_N@Z`
- size: `316`
- prototype: `void __fastcall(bool fLoadResDLL)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800776b0`

## callees

- `0x1800777bc`
- `0x180077900`
- `0x1800bb5e0`
- `0x1800bfc70`
- `0x1800cada0`
- `0x1800d82e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007787b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007787b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800778bd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800778bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800777e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800777e9`

## string_xrefs

- `0x18007782f`: `msxml6r.dll`

## pseudocode

```c
void __fastcall Resources::classInit(bool fLoadResDLL)
{
  wchar_t v1; // dx
  wchar_t *v2; // rcx
  const wchar_t *v3; // rdx
  int v4; // r9d
  unsigned __int64 i; // rax
  HMODULE Library; // rax
  int verDll[4]; // [rsp+20h] [rbp-248h] BYREF
  int verRes[4]; // [rsp+30h] [rbp-238h] BYREF
  wchar_t szModulePath[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( GetModuleFileNameW(g_hInstance, szModulePath, 0x104u) )
  {
    szModulePath[260] = 0;
    if ( !Resources::GetVersion(g_hInstance, (int (*)[4])verDll) )
      goto LABEL_15;
    v2 = wcsrchr(szModulePath, v1) + 1;
    v3 = L"msxml6r.dll";
    v4 = 261 - (v2 - szModulePath);
    for ( i = 0; i < 0x7FFFFFFF; ++i )
    {
      if ( !*v3 )
        break;
      ++v3;
    }
    if ( (int)i >= v4 )
    {
      Library = (HMODULE)Resources::s_hInstance;
    }
    else
    {
      if ( StringCchCopyW(v2, v4, L"msxml6r.dll") < 0 )
        goto LABEL_15;
      Library = LoadLibraryExW(szModulePath, 0, 2u);
      Resources::s_hInstance = Library;
    }
    if ( !Resources::GetVersion(Library, (int (*)[4])verRes) || verRes[0] != verDll[0] || verRes[1] > verDll[1] )
    {
      FreeLibrary((HMODULE)Resources::s_hInstance);
      Resources::s_hInstance = 0;
      Exception::throw_E_FAIL();
    }
  }
  if ( !Resources::s_hInstance )
LABEL_15:
    Exception::throw_E_FAIL();
}

```

## disassembly

```asm
0x1800777bc  push    rbx
0x1800777be  sub     rsp, 260h
0x1800777c5  mov     rax, cs:__security_cookie
0x1800777cc  xor     rax, rsp
0x1800777cf  mov     [rsp+268h+var_18], rax
0x1800777d7  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800777de  lea     rdx, [rsp+268h+szModulePath]; lpFilename
0x1800777e3  mov     r8d, 104h; nSize
0x1800777e9  call    cs:__imp_GetModuleFileNameW
0x1800777ef  xor     ebx, ebx
0x1800777f1  test    eax, eax
0x1800777f3  jz      loc_1800778D0
0x1800777f9  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hmod
0x180077800  lea     rdx, [rsp+268h+verDll]; auiVersion
0x180077805  mov     [rsp+268h+szModulePath+208h], bx
0x18007780d  call    ?GetVersion@Resources@@SA_NPEAUHINSTANCE__@@AEAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x180077812  test    al, al
0x180077814  jz      loc_1800778D9
0x18007781a  lea     rcx, [rsp+268h+szModulePath]; _String
0x18007781f  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x180077824  lea     rdx, [rsp+268h+szModulePath]
0x180077829  mov     r9d, 105h
0x18007782f  lea     r8, aMsxml6rDll; "msxml6r.dll"
0x180077836  lea     rcx, [rax+2]; pszDest
0x18007783a  mov     rax, rcx
0x18007783d  sub     rax, rdx
0x180077840  mov     rdx, r8
0x180077843  sar     rax, 1
0x180077846  sub     r9d, eax
0x180077849  mov     eax, ebx
0x18007784b  cmp     [rdx], bx
0x18007784e  jz      short loc_18007785F
0x180077850  add     rdx, 2
0x180077854  inc     rax
0x180077857  cmp     rax, 7FFFFFFFh
0x18007785d  jb      short loc_18007784B
0x18007785f  cmp     eax, r9d
0x180077862  jge     short loc_18007788A
0x180077864  movsxd  rdx, r9d; cchDest
0x180077867  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007786c  test    eax, eax
0x18007786e  js      short loc_1800778D9
0x180077870  xor     edx, edx; hFile
0x180077872  lea     rcx, [rsp+268h+szModulePath]; lpLibFileName
0x180077877  lea     r8d, [rdx+2]; dwFlags
0x18007787b  call    cs:__imp_LoadLibraryExW
0x180077881  mov     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Resources::s_hInstance
0x180077888  jmp     short loc_180077891
0x18007788a  mov     rax, cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Resources::s_hInstance
0x180077891  lea     rdx, [rsp+268h+verRes]; auiVersion
0x180077896  mov     rcx, rax; hmod
0x180077899  call    ?GetVersion@Resources@@SA_NPEAUHINSTANCE__@@AEAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x18007789e  test    al, al
0x1800778a0  jz      short loc_1800778B6
0x1800778a2  mov     eax, [rsp+268h+verDll]
0x1800778a6  cmp     [rsp+268h+verRes], eax
0x1800778aa  jnz     short loc_1800778B6
0x1800778ac  mov     eax, [rsp+268h+verDll+4]
0x1800778b0  cmp     [rsp+268h+verRes+4], eax
0x1800778b4  jle     short loc_1800778D0
0x1800778b6  mov     rcx, cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA; hLibModule
0x1800778bd  call    cs:__imp_FreeLibrary
0x1800778c3  mov     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * Resources::s_hInstance
0x1800778ca  call    ?throw_E_FAIL@Exception@@SAXXZ; Exception::throw_E_FAIL(void)
0x1800778d0  cmp     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * Resources::s_hInstance
0x1800778d7  jnz     short loc_1800778DF
0x1800778d9  call    ?throw_E_FAIL@Exception@@SAXXZ; Exception::throw_E_FAIL(void)
0x1800778df  mov     rcx, [rsp+268h+var_18]
0x1800778e7  xor     rcx, rsp; StackCookie
0x1800778ea  call    __security_check_cookie
0x1800778ef  add     rsp, 260h
0x1800778f6  pop     rbx
0x1800778f7  retn
```
