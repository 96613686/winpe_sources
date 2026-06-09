# Resources::classInit(bool)

- ea: `0x180038288`
- end: `0x1800383c8`
- name: `?classInit@Resources@@SAX_N@Z`
- size: `320`
- prototype: `void __fastcall(bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180037ec4`

## callees

- `0x180038288`
- `0x1800386a8`
- `0x180042064`
- `0x18004a960`
- `0x180102d20`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800382ee`
- `msvcrt!wcsrchr` at `0x1800382ee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003834b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003834b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003838d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003838d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800382b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800382b5`

## string_xrefs

- `0x1800382ff`: `msxml3r.dll`

## pseudocode

```c
void __fastcall Resources::classInit()
{
  unsigned __int16 *v0; // rcx
  const unsigned __int16 *v1; // rdx
  int v2; // r9d
  unsigned __int64 i; // rax
  HMODULE Library; // rax
  int v5[4]; // [rsp+20h] [rbp-248h] BYREF
  int v6[4]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( GetModuleFileNameW(g_hInstance, Filename, 0x104u) )
  {
    Filename[260] = 0;
    if ( !Resources::GetVersion(g_hInstance, (int (*)[4])v5) )
      goto LABEL_15;
    v0 = wcsrchr(Filename, 0x5Cu) + 1;
    v1 = L"msxml3r.dll";
    v2 = 261 - (v0 - Filename);
    for ( i = 0; i < 0x7FFFFFFF; ++i )
    {
      if ( !*v1 )
        break;
      ++v1;
    }
    if ( (int)i >= v2 )
    {
      Library = Resources::s_hInstance;
    }
    else
    {
      if ( StringCchCopyW(v0, v2, L"msxml3r.dll") < 0 )
        goto LABEL_15;
      Library = LoadLibraryExW(Filename, 0, 2u);
      Resources::s_hInstance = Library;
    }
    if ( !Resources::GetVersion(Library, (int (*)[4])v6) || v6[0] != v5[0] || v6[1] > v5[1] )
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
0x180038288  push    rbx
0x18003828a  sub     rsp, 260h
0x180038291  mov     rax, cs:__security_cookie
0x180038298  xor     rax, rsp
0x18003829b  mov     [rsp+268h+var_18], rax
0x1800382a3  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800382aa  lea     rdx, [rsp+268h+Filename]; lpFilename
0x1800382af  mov     r8d, 104h; nSize
0x1800382b5  call    cs:__imp_GetModuleFileNameW
0x1800382bb  xor     ebx, ebx
0x1800382bd  test    eax, eax
0x1800382bf  jz      loc_1800383A0
0x1800382c5  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800382cc  lea     rdx, [rsp+268h+var_248]; int (*)[4]
0x1800382d1  mov     [rsp+268h+var_20], bx
0x1800382d9  call    ?GetVersion@Resources@@SA_NPEAUHINSTANCE__@@AEAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x1800382de  test    al, al
0x1800382e0  jz      loc_1800383A9
0x1800382e6  lea     edx, [rbx+5Ch]; Ch
0x1800382e9  lea     rcx, [rsp+268h+Filename]; Str
0x1800382ee  call    cs:__imp_wcsrchr
0x1800382f4  lea     rdx, [rsp+268h+Filename]
0x1800382f9  mov     r9d, 105h
0x1800382ff  lea     r8, aMsxml3rDll; "msxml3r.dll"
0x180038306  lea     rcx, [rax+2]; unsigned __int16 *
0x18003830a  mov     rax, rcx
0x18003830d  sub     rax, rdx
0x180038310  mov     rdx, r8
0x180038313  sar     rax, 1
0x180038316  sub     r9d, eax
0x180038319  mov     eax, ebx
0x18003831b  cmp     [rdx], bx
0x18003831e  jz      short loc_18003832F
0x180038320  add     rdx, 2
0x180038324  inc     rax
0x180038327  cmp     rax, 7FFFFFFFh
0x18003832d  jb      short loc_18003831B
0x18003832f  cmp     eax, r9d
0x180038332  jge     short loc_18003835A
0x180038334  movsxd  rdx, r9d; unsigned __int64
0x180038337  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003833c  test    eax, eax
0x18003833e  js      short loc_1800383A9
0x180038340  xor     edx, edx; hFile
0x180038342  lea     rcx, [rsp+268h+Filename]; lpLibFileName
0x180038347  lea     r8d, [rdx+2]; dwFlags
0x18003834b  call    cs:__imp_LoadLibraryExW
0x180038351  mov     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Resources::s_hInstance
0x180038358  jmp     short loc_180038361
0x18003835a  mov     rax, cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Resources::s_hInstance
0x180038361  lea     rdx, [rsp+268h+var_238]; int (*)[4]
0x180038366  mov     rcx, rax; hModule
0x180038369  call    ?GetVersion@Resources@@SA_NPEAUHINSTANCE__@@AEAY03H@Z; Resources::GetVersion(HINSTANCE__ *,int (&)[4])
0x18003836e  test    al, al
0x180038370  jz      short loc_180038386
0x180038372  mov     eax, [rsp+268h+var_248]
0x180038376  cmp     [rsp+268h+var_238], eax
0x18003837a  jnz     short loc_180038386
0x18003837c  mov     eax, [rsp+268h+var_248+4]
0x180038380  cmp     [rsp+268h+var_238+4], eax
0x180038384  jle     short loc_1800383A0
0x180038386  mov     rcx, cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA; hLibModule
0x18003838d  call    cs:__imp_FreeLibrary
0x180038393  mov     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * Resources::s_hInstance
0x18003839a  call    ?throw_E_FAIL@Exception@@SAXXZ; Exception::throw_E_FAIL(void)
0x1800383a0  cmp     cs:?s_hInstance@Resources@@2PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * Resources::s_hInstance
0x1800383a7  jnz     short loc_1800383AF
0x1800383a9  call    ?throw_E_FAIL@Exception@@SAXXZ; Exception::throw_E_FAIL(void)
0x1800383af  mov     rcx, [rsp+268h+var_18]
0x1800383b7  xor     rcx, rsp; StackCookie
0x1800383ba  call    __security_check_cookie
0x1800383bf  add     rsp, 260h
0x1800383c6  pop     rbx
0x1800383c7  retn
```
