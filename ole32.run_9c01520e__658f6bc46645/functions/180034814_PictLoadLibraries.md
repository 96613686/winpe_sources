# _PictLoadLibraries

- ea: `0x180034814`
- end: `0x180034a2c`
- name: `_PictLoadLibraries`
- size: `536`
- prototype: `HRESULT __fastcall(unsigned int p_dwFlags)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002503c`
- `0x18003464c`
- `0x1800c5a68`

## callees

- `0x1800253cc`
- `0x180034814`
- `0x180046460`

## import_xrefs

- `ntdll!RtlGetNtSystemRoot` at `0x180034848`
- `ntdll!RtlGetNtSystemRoot` at `0x18003492d`
- `ntdll!RtlGetNtSystemRoot` at `0x180034848`
- `ntdll!RtlGetNtSystemRoot` at `0x18003492d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003487a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003495f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003487a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003495f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034903`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034985`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800348e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034903`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034985`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800349a8`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800349c2`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800349dc`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800349f6`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800349a8`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800349c2`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800349dc`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x1800349f6`

## string_xrefs

- `0x1800348b3`: `CreateAsyncBindCtx`
- `0x180034939`: `%s\system32\asycfilt.dll`
- `0x180034854`: `%s\system32\urlmon.dll`
- `0x180034896`: `CreateURLMoniker`
- `0x18003497b`: `FilterCreateInstance`

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
0x180034814  push    rbx
0x180034816  sub     rsp, 240h
0x18003481d  mov     rax, cs:__security_cookie
0x180034824  xor     rax, rsp
0x180034827  mov     [rsp+248h+var_18], rax
0x18003482f  mov     ebx, p_dwFlags
0x180034831  test    cl, 2
0x180034834  jz      loc_180034916
0x18003483a  cmp     cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hURLMonDLL
0x180034842  jnz     loc_180034916
0x180034848  call    cs:__imp_RtlGetNtSystemRoot
0x18003484f  nop     dword ptr [rax+rax+00h]
0x180034854  lea     r8, aSSystem32Urlmo; "%s\\system32\\urlmon.dll"
0x18003485b  mov     edx, 208h; cbDest
0x180034860  mov     r9, rax
0x180034863  lea     rcx, [rsp+248h+rcDll]; pszDest
0x180034868  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003486d  xor     edx, edx; hFile
0x18003486f  lea     rcx, [rsp+248h+rcDll]; lpLibFileName
0x180034874  mov     r8d, 800h; dwFlags
0x18003487a  call    cs:__imp_LoadLibraryExW
0x180034881  nop     dword ptr [rax+rax+00h]
0x180034886  mov     cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hURLMonDLL
0x18003488d  test    rax, rax
0x180034890  jz      loc_180034916
0x180034896  lea     rdx, aCreateurlmonik; "CreateURLMoniker"
0x18003489d  mov     rcx, rax; hModule
0x1800348a0  call    cs:__imp_GetProcAddress
0x1800348a7  nop     dword ptr [rax+rax+00h]
0x1800348ac  mov     rcx, cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800348b3  lea     rdx, aCreateasyncbin; "CreateAsyncBindCtx"
0x1800348ba  mov     cs:?g_fnCreateURLMoniker@@3P6AJPEAUIMoniker@@PEBGPEAPEAU1@@ZEA, rax; long (*g_fnCreateURLMoniker)(IMoniker *,ushort const *,IMoniker * *)
0x1800348c1  call    cs:__imp_GetProcAddress
0x1800348c8  nop     dword ptr [rax+rax+00h]
0x1800348cd  mov     rcx, cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800348d4  lea     rdx, aRegisterbindst; "RegisterBindStatusCallback"
0x1800348db  mov     cs:?g_fnCreateAsyncBindCtx@@3P6AJKPEAUIBindStatusCallback@@PEAUIEnumFORMATETC@@PEAPEAUIBindCtx@@@ZEA, rax; long (*g_fnCreateAsyncBindCtx)(ulong,IBindStatusCallback *,IEnumFORMATETC *,IBindCtx * *)
0x1800348e2  call    cs:__imp_GetProcAddress
0x1800348e9  nop     dword ptr [rax+rax+00h]
0x1800348ee  mov     rcx, cs:?g_hURLMonDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800348f5  lea     rdx, aRevokebindstat; "RevokeBindStatusCallback"
0x1800348fc  mov     cs:?g_fnRegisterBindStatusCallback@@3P6AJPEAUIBindCtx@@PEAUIBindStatusCallback@@PEAPEAU2@K@ZEA, rax; long (*g_fnRegisterBindStatusCallback)(IBindCtx *,IBindStatusCallback *,IBindStatusCallback * *,ulong)
0x180034903  call    cs:__imp_GetProcAddress
0x18003490a  nop     dword ptr [rax+rax+00h]
0x18003490f  mov     cs:?g_fnRevokeBindStatusCallback@@3P6AJPEAUIBindCtx@@PEAUIBindStatusCallback@@@ZEA, rax; long (*g_fnRevokeBindStatusCallback)(IBindCtx *,IBindStatusCallback *)
0x180034916  test    bl, 1
0x180034919  jz      loc_180034A09
0x18003491f  cmp     cs:?g_hFilterDLL@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hFilterDLL
0x180034927  jnz     loc_180034A09
0x18003492d  call    cs:__imp_RtlGetNtSystemRoot
0x180034934  nop     dword ptr [rax+rax+00h]
0x180034939  lea     r8, aSSystem32Asycf; "%s\\system32\\asycfilt.dll"
0x180034940  mov     edx, 208h; cbDest
0x180034945  mov     r9, rax
0x180034948  lea     rcx, [rsp+248h+rcDll]; pszDest
0x18003494d  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034952  xor     edx, edx; hFile
0x180034954  lea     rcx, [rsp+248h+rcDll]; lpLibFileName
0x180034959  mov     r8d, 800h; dwFlags
0x18003495f  call    cs:__imp_LoadLibraryExW
0x180034966  nop     dword ptr [rax+rax+00h]
0x18003496b  mov     cs:?g_hFilterDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hFilterDLL
0x180034972  test    rax, rax
0x180034975  jz      loc_180034A25
0x18003497b  lea     rdx, aFiltercreatein; "FilterCreateInstance"
0x180034982  mov     rcx, rax; hModule
0x180034985  call    cs:__imp_GetProcAddress
0x18003498c  nop     dword ptr [rax+rax+00h]
0x180034991  mov     cs:?g_fnFilterCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA, rax; long (*g_fnFilterCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180034998  test    rax, rax
0x18003499b  jz      loc_180034A25
0x1800349a1  lea     rcx, aMsAsyncimageDc; "MS_AsyncImage_DCWait"
0x1800349a8  call    cs:__imp_GlobalAddAtomW
0x1800349af  nop     dword ptr [rax+rax+00h]
0x1800349b4  lea     rcx, aMsAsyncimageDi; "MS_AsyncImage_Display"
0x1800349bb  mov     cs:?ITA_DCWAIT@@3GA, ax; ushort ITA_DCWAIT
0x1800349c2  call    cs:__imp_GlobalAddAtomW
0x1800349c9  nop     dword ptr [rax+rax+00h]
0x1800349ce  lea     rcx, aMsAsyncimageAb; "MS_AsyncImage_Abnormal"
0x1800349d5  mov     cs:?ITA_DISPLAY@@3GA, ax; ushort ITA_DISPLAY
0x1800349dc  call    cs:__imp_GlobalAddAtomW
0x1800349e3  nop     dword ptr [rax+rax+00h]
0x1800349e8  lea     rcx, aMsAsyncimageFi; "MS_AsyncImage_Finished"
0x1800349ef  mov     cs:?ITA_ABNORMAL@@3GA, ax; ushort ITA_ABNORMAL
0x1800349f6  call    cs:__imp_GlobalAddAtomW
0x1800349fd  nop     dword ptr [rax+rax+00h]
0x180034a02  mov     cs:?ITA_FINISHED@@3GA, ax; ushort ITA_FINISHED
0x180034a09  xor     eax, eax
0x180034a0b  mov     rcx, [rsp+248h+var_18]
0x180034a13  xor     rcx, rsp; StackCookie
0x180034a16  call    __security_check_cookie
0x180034a1b  add     rsp, 240h
0x180034a22  pop     rbx
0x180034a23  retn
0x180034a25  mov     eax, 80004005h
0x180034a2a  jmp     short loc_180034A0B
```
