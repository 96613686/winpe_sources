# Resources::classInit(bool)

- ea: `0x180076afc`
- end: `0x180076c4b`
- name: `?classInit@Resources@@SAX_N@Z`
- size: `335`
- prototype: `void __fastcall(bool fLoadResDLL)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800769ec`

## callees

- `0x180076afc`
- `0x180076c54`
- `0x1800bcb90`
- `0x1800c12f4`
- `0x1800cc6c0`
- `0x1800da0a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180076bc1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180076bc1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180076c09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180076c09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180076b29`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180076b29`

## string_xrefs

- `0x180076b75`: `msxml6r.dll`

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
      Library = Resources::s_hInstance;
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
      FreeLibrary(Resources::s_hInstance);
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
0x180076afc  push    rbx
0x180076afe  sub     rsp, 260h
0x180076b05  mov     rax, cs:__security_cookie
0x180076b0c  xor     rax, rsp
0x180076b0f  mov     [rsp+268h+var_18], rax
0x180076b17  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180076b1e  lea     rdx, [rsp+268h+szModulePath]; lpFilename
0x180076b23  mov     r8d, 104h; nSize
0x180076b29  call    cs:__imp_GetModuleFileNameW
0x180076b30  nop     dword ptr [rax+rax+00h]
0x180076b35  xor     ebx, ebx
0x180076b37  test    eax, eax
0x180076b39  jz      loc_180076C22
0x180076b3f  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hmod
0x180076b46  lea     rdx, [rsp+268h+verDll]; auiVersion
0x180076b4b  mov     [rsp+268h+szModulePath+208h], bx
0x180076b53  call    ?GetVersion@Resources@@SA_NPEAUHINSTANCE__@@AEAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x180076b58  test    al, al
0x180076b5a  jz      loc_180076C2B
0x180076b60  lea     rcx, [rsp+268h+szModulePath]; _String
0x180076b65  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x180076b6a  lea     rdx, [rsp+268h+szModulePath]
0x180076b6f  mov     r9d, 105h
0x180076b75  lea     r8, aMsxml6rDll; "msxml6r.dll"
0x180076b7c  lea     rcx, [rax+2]; pszDest
0x180076b80  mov     rax, rcx
0x180076b83  sub     rax, rdx
0x180076b86  mov     rdx, r8
0x180076b89  sar     rax, 1
0x180076b8c  sub     r9d, eax
0x180076b8f  mov     eax, ebx
0x180076b91  cmp     [rdx], bx
0x180076b94  jz      short loc_180076BA5
0x180076b96  add     rdx, 2
0x180076b9a  inc     rax
0x180076b9d  cmp     rax, 7FFFFFFFh
0x180076ba3  jb      short loc_180076B91
0x180076ba5  cmp     eax, r9d
0x180076ba8  jge     short loc_180076BD6
0x180076baa  movsxd  rdx, r9d; cchDest
0x180076bad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180076bb2  test    eax, eax
0x180076bb4  js      short loc_180076C2B
0x180076bb6  xor     edx, edx; hFile
0x180076bb8  lea     rcx, [rsp+268h+szModulePath]; lpLibFileName
0x180076bbd  lea     r8d, [rdx+2]; dwFlags
0x180076bc1  call    cs:__imp_LoadLibraryExW
0x180076bc8  nop     dword ptr [rax+rax+00h]
0x180076bcd  mov     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Resources::s_hInstance
0x180076bd4  jmp     short loc_180076BDD
0x180076bd6  mov     rax, cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Resources::s_hInstance
0x180076bdd  lea     rdx, [rsp+268h+verRes]; auiVersion
0x180076be2  mov     rcx, rax; hmod
0x180076be5  call    ?GetVersion@Resources@@SA_NPEAUHINSTANCE__@@AEAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x180076bea  test    al, al
0x180076bec  jz      short loc_180076C02
0x180076bee  mov     eax, [rsp+268h+verDll]
0x180076bf2  cmp     [rsp+268h+verRes], eax
0x180076bf6  jnz     short loc_180076C02
0x180076bf8  mov     eax, [rsp+268h+verDll+4]
0x180076bfc  cmp     [rsp+268h+verRes+4], eax
0x180076c00  jle     short loc_180076C22
0x180076c02  mov     rcx, cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA; hLibModule
0x180076c09  call    cs:__imp_FreeLibrary
0x180076c10  nop     dword ptr [rax+rax+00h]
0x180076c15  mov     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * Resources::s_hInstance
0x180076c1c  call    ?throw_E_FAIL@Exception@@SAXXZ; Exception::throw_E_FAIL(void)
0x180076c22  cmp     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * Resources::s_hInstance
0x180076c29  jnz     short loc_180076C31
0x180076c2b  call    ?throw_E_FAIL@Exception@@SAXXZ; Exception::throw_E_FAIL(void)
0x180076c31  mov     rcx, [rsp+268h+var_18]
0x180076c39  xor     rcx, rsp; StackCookie
0x180076c3c  call    __security_check_cookie
0x180076c41  add     rsp, 260h
0x180076c48  pop     rbx
0x180076c49  retn
```
