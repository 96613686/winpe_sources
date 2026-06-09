# _PictLoadLibraries

- ea: `0x180031350`
- end: `0x180031511`
- name: `_PictLoadLibraries`
- size: `449`
- prototype: `HRESULT __fastcall(unsigned int p_dwFlags)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fab4`
- `0x180031184`
- `0x1800bce4c`

## callees

- `0x18001fe14`
- `0x180031350`
- `0x180052390`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x180031384`
- `ntdll!RtlGetNtSystemRoot` at `0x180031441`
- `ntdll!RtlGetNtSystemRoot` at `0x180031384`
- `ntdll!RtlGetNtSystemRoot` at `0x180031441`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031402`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003141d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003148d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800313e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031402`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003141d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003148d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800313b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003146d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800313b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003146d`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800314a6`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800314ba`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800314ce`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800314e2`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800314a6`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800314ba`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800314ce`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800314e2`

## string_xrefs

- `0x18003138a`: `%s\system32\urlmon.dll`
- `0x1800313c2`: `CreateURLMoniker`
- `0x1800313d9`: `CreateAsyncBindCtx`
- `0x180031447`: `%s\system32\asycfilt.dll`
- `0x180031483`: `FilterCreateInstance`

## pseudocode

```c
__int64 __fastcall PictLoadLibraries(char p_dwFlags)
{
  __int64 NtSystemRoot; // rax
  HMODULE Library; // rax
  __int64 v4; // rax
  HMODULE v5; // rax
  wchar_t rcDll[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( (p_dwFlags & 2) != 0 && !g_hURLMonDLL )
  {
    NtSystemRoot = RtlGetNtSystemRoot();
    StringCbPrintfW(rcDll, 0x208u, L"%s\\system32\\urlmon.dll", NtSystemRoot);
    Library = LoadLibraryExW(rcDll, 0, 0x800u);
    g_hURLMonDLL = Library;
    if ( Library )
    {
      g_fnCreateURLMoniker = (HRESULT (__fastcall *)(IMoniker *, const wchar_t *, IMoniker **))GetProcAddress(
                                                                                                 Library,
                                                                                                 "CreateURLMoniker");
      g_fnCreateAsyncBindCtx = (HRESULT (__fastcall *)(unsigned int, IBindStatusCallback *, IEnumFORMATETC *, IBindCtx **))GetProcAddress(g_hURLMonDLL, "CreateAsyncBindCtx");
      g_fnRegisterBindStatusCallback = (HRESULT (__fastcall *)(IBindCtx *, IBindStatusCallback *, IBindStatusCallback **, unsigned int))GetProcAddress(g_hURLMonDLL, "RegisterBindStatusCallback");
      g_fnRevokeBindStatusCallback = (HRESULT (__fastcall *)(IBindCtx *, IBindStatusCallback *))GetProcAddress(
                                                                                                  g_hURLMonDLL,
                                                                                                  "RevokeBindStatusCallback");
    }
  }
  if ( (p_dwFlags & 1) == 0 || g_hFilterDLL )
    return 0;
  v4 = RtlGetNtSystemRoot();
  StringCbPrintfW(rcDll, 0x208u, L"%s\\system32\\asycfilt.dll", v4);
  v5 = LoadLibraryExW(rcDll, 0, 0x800u);
  g_hFilterDLL = v5;
  if ( v5 )
  {
    g_fnFilterCreateInstance = (HRESULT (__fastcall *)(const _GUID *, IUnknown *, unsigned int, const _GUID *, void **))GetProcAddress(v5, "FilterCreateInstance");
    if ( g_fnFilterCreateInstance )
    {
      ITA_DCWAIT = GlobalAddAtomW(L"MS_AsyncImage_DCWait");
      ITA_DISPLAY = GlobalAddAtomW(L"MS_AsyncImage_Display");
      ITA_ABNORMAL = GlobalAddAtomW(L"MS_AsyncImage_Abnormal");
      ITA_FINISHED = GlobalAddAtomW(L"MS_AsyncImage_Finished");
      return 0;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180031350  push    rbx
0x180031352  sub     rsp, 240h
0x180031359  mov     rax, cs:__security_cookie
0x180031360  xor     rax, rsp
0x180031363  mov     [rsp+248h+var_18], rax
0x18003136b  mov     ebx, p_dwFlags
0x18003136d  test    cl, 2
0x180031370  jz      loc_18003142A
0x180031376  cmp     cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hURLMonDLL
0x18003137e  jnz     loc_18003142A
0x180031384  call    cs:__imp_RtlGetNtSystemRoot
0x18003138a  lea     r8, aSSystem32Urlmo; "%s\\system32\\urlmon.dll"
0x180031391  mov     edx, 208h; cbDest
0x180031396  mov     r9, rax
0x180031399  lea     rcx, [rsp+248h+rcDll]; pszDest
0x18003139e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800313a3  xor     edx, edx; hFile
0x1800313a5  lea     rcx, [rsp+248h+rcDll]; lpLibFileName
0x1800313aa  mov     r8d, 800h; dwFlags
0x1800313b0  call    cs:__imp_LoadLibraryExW
0x1800313b6  mov     cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hURLMonDLL
0x1800313bd  test    rax, rax
0x1800313c0  jz      short loc_18003142A
0x1800313c2  lea     rdx, ProcName; "CreateURLMoniker"
0x1800313c9  mov     rcx, rax; hModule
0x1800313cc  call    cs:__imp_GetProcAddress
0x1800313d2  mov     rcx, cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800313d9  lea     rdx, aCreateasyncbin; "CreateAsyncBindCtx"
0x1800313e0  mov     cs:?g_fnCreateURLMoniker@@3P6AJPEAUIMoniker@@PEBGPEAPEAU1@@ZEA, rax; long (*g_fnCreateURLMoniker)(IMoniker *,ushort const *,IMoniker * *)
0x1800313e7  call    cs:__imp_GetProcAddress
0x1800313ed  mov     rcx, cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800313f4  lea     rdx, aRegisterbindst; "RegisterBindStatusCallback"
0x1800313fb  mov     cs:?g_fnCreateAsyncBindCtx@@3P6AJKPEAUIBindStatusCallback@@PEAUIEnumFORMATETC@@PEAPEAUIBindCtx@@@ZEA, rax; long (*g_fnCreateAsyncBindCtx)(ulong,IBindStatusCallback *,IEnumFORMATETC *,IBindCtx * *)
0x180031402  call    cs:__imp_GetProcAddress
0x180031408  mov     rcx, cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18003140f  lea     rdx, aRevokebindstat; "RevokeBindStatusCallback"
0x180031416  mov     cs:?g_fnRegisterBindStatusCallback@@3P6AJPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAPEAU2@K@ZEA, rax; long (*g_fnRegisterBindStatusCallback)(IBindCtx *,IBindStatusCallback *,IBindStatusCallback * *,ulong)
0x18003141d  call    cs:__imp_GetProcAddress
0x180031423  mov     cs:?g_fnRevokeBindStatusCallback@@3P6AJPEAUIBindCtx@@PEAUIBindStatusCallback@@@ZEA, rax; long (*g_fnRevokeBindStatusCallback)(IBindCtx *,IBindStatusCallback *)
0x18003142a  test    bl, 1
0x18003142d  jz      loc_1800314EF
0x180031433  cmp     cs:?g_hFilterDLL@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hFilterDLL
0x18003143b  jnz     loc_1800314EF
0x180031441  call    cs:__imp_RtlGetNtSystemRoot
0x180031447  lea     r8, aSSystem32Asycf; "%s\\system32\\asycfilt.dll"
0x18003144e  mov     edx, 208h; cbDest
0x180031453  mov     r9, rax
0x180031456  lea     rcx, [rsp+248h+rcDll]; pszDest
0x18003145b  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180031460  xor     edx, edx; hFile
0x180031462  lea     rcx, [rsp+248h+rcDll]; lpLibFileName
0x180031467  mov     r8d, 800h; dwFlags
0x18003146d  call    cs:__imp_LoadLibraryExW
0x180031473  mov     cs:?g_hFilterDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hFilterDLL
0x18003147a  test    rax, rax
0x18003147d  jz      loc_18003150A
0x180031483  lea     rdx, aFiltercreatein; "FilterCreateInstance"
0x18003148a  mov     rcx, rax; hModule
0x18003148d  call    cs:__imp_GetProcAddress
0x180031493  mov     cs:?g_fnFilterCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA, rax; long (*g_fnFilterCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18003149a  test    rax, rax
0x18003149d  jz      short loc_18003150A
0x18003149f  lea     rcx, aMsAsyncimageDc; "MS_AsyncImage_DCWait"
0x1800314a6  call    cs:__imp_GlobalAddAtomW
0x1800314ac  lea     rcx, aMsAsyncimageDi; "MS_AsyncImage_Display"
0x1800314b3  mov     cs:?ITA_DCWAIT@@3GA, ax; ushort ITA_DCWAIT
0x1800314ba  call    cs:__imp_GlobalAddAtomW
0x1800314c0  lea     rcx, aMsAsyncimageAb; "MS_AsyncImage_Abnormal"
0x1800314c7  mov     cs:?ITA_DISPLAY@@3GA, ax; ushort ITA_DISPLAY
0x1800314ce  call    cs:__imp_GlobalAddAtomW
0x1800314d4  lea     rcx, aMsAsyncimageFi; "MS_AsyncImage_Finished"
0x1800314db  mov     cs:?ITA_ABNORMAL@@3GA, ax; ushort ITA_ABNORMAL
0x1800314e2  call    cs:__imp_GlobalAddAtomW
0x1800314e8  mov     cs:?ITA_FINISHED@@3GA, ax; ushort ITA_FINISHED
0x1800314ef  xor     eax, eax
0x1800314f1  mov     rcx, [rsp+248h+var_18]
0x1800314f9  xor     rcx, rsp; StackCookie
0x1800314fc  call    __security_check_cookie
0x180031501  add     rsp, 240h
0x180031508  pop     rbx
0x180031509  retn
0x18003150a  mov     eax, 80004005h
0x18003150f  jmp     short loc_1800314F1
```
