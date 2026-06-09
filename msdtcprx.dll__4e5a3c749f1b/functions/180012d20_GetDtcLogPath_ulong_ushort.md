# GetDtcLogPath(ulong,ushort *)

- ea: `0x180012d20`
- end: `0x180012e3d`
- name: `?GetDtcLogPath@@YAHKPEAG@Z`
- size: `285`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180012d20`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180012d40`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180012d40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012da8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012da8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012e20`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012db3`

## string_xrefs

- `0x180012d7b`: `GetDtcLogPath`
- `0x180012e09`: `GetDtcLogPath`
- `0x180012d74`: `com\complus\dtc\dtc\msdtcprx\src\dtcinit.cpp`
- `0x180012df9`: `com\complus\dtc\dtc\msdtcprx\src\dtcinit.cpp`
- `0x180012d68`: `GetDtcLogPath, MtxCluGetDefaultClusterResource failed`
- `0x180012dc8`: `GetDtcLogPath, GetProcAddress(hMtxcluDll, MtxCluGetDtcLogPathW) failed`
- `0x180012d36`: `mtxclu.dll`
- `0x180012d9e`: `MtxCluGetDtcLogPathW`
- `0x180012de7`: `GetDtcLogPath, pfnMtxCluGetDtcLogPathW failed`

## pseudocode

```c
_BOOL8 __fastcall GetDtcLogPath(unsigned int a1, unsigned __int16 *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rdi
  signed int v6; // eax
  signed int v7; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  const wchar_t *v10; // rax
  __int64 v11; // r9
  __int64 v13; // [rsp+28h] [rbp-20h]

  Library = LoadLibraryExA("mtxclu.dll", 0, 0);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "MtxCluGetDtcLogPathW");
    if ( ProcAddress )
    {
      v7 = ((__int64 (__fastcall *)(_QWORD, unsigned __int16 *))ProcAddress)(a1, a2);
      if ( v7 >= 0 )
      {
LABEL_12:
        FreeLibrary(v5);
        return v7 >= 0;
      }
      v10 = L"GetDtcLogPath, pfnMtxCluGetDtcLogPathW failed";
      v11 = 309;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v10 = L"GetDtcLogPath, GetProcAddress(hMtxcluDll, MtxCluGetDtcLogPathW) failed";
      v11 = 303;
    }
    LODWORD(v13) = v7;
    TraceStringInline(7, 1, L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinit.cpp", v11, L"GetDtcLogPath", v13, v10);
    goto LABEL_12;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  LODWORD(v13) = v7;
  TraceStringInline(
    7,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcinit.cpp",
    296,
    L"GetDtcLogPath",
    v13,
    L"GetDtcLogPath, MtxCluGetDefaultClusterResource failed");
  return v7 >= 0;
}

```

## disassembly

```asm
0x180012d20  mov     [rsp+arg_0], rbx
0x180012d25  mov     [rsp+arg_8], rsi
0x180012d2a  push    rdi
0x180012d2b  sub     rsp, 40h
0x180012d2f  mov     rbx, rdx
0x180012d32  mov     esi, ecx
0x180012d34  xor     edx, edx; hFile
0x180012d36  lea     rcx, aMtxcluDll_0; "mtxclu.dll"
0x180012d3d  xor     r8d, r8d; dwFlags
0x180012d40  call    cs:__imp_LoadLibraryExA
0x180012d46  mov     rdi, rax
0x180012d49  test    rax, rax
0x180012d4c  jnz     short loc_180012D9E
0x180012d4e  call    cs:__imp_GetLastError
0x180012d54  mov     ebx, eax
0x180012d56  test    eax, eax
0x180012d58  jle     short loc_180012D63
0x180012d5a  movzx   ebx, ax
0x180012d5d  or      ebx, 80070000h
0x180012d63  mov     edx, 1
0x180012d68  lea     rax, aGetdtclogpathM; "GetDtcLogPath, MtxCluGetDefaultClusterR"...
0x180012d6f  mov     [rsp+48h+var_18], rax
0x180012d74  lea     r8, aComComplusDtcD_25; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180012d7b  lea     rax, aGetdtclogpath_0; "GetDtcLogPath"
0x180012d82  mov     dword ptr [rsp+48h+var_20], ebx
0x180012d86  mov     r9d, 128h
0x180012d8c  mov     [rsp+48h+var_28], rax
0x180012d91  lea     ecx, [rdx+6]
0x180012d94  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180012d99  jmp     loc_180012E26
0x180012d9e  lea     rdx, aMtxclugetdtclo; "MtxCluGetDtcLogPathW"
0x180012da5  mov     rcx, rdi; hModule
0x180012da8  call    cs:__imp_GetProcAddress
0x180012dae  test    rax, rax
0x180012db1  jnz     short loc_180012DD7
0x180012db3  call    cs:__imp_GetLastError
0x180012db9  mov     ebx, eax
0x180012dbb  test    eax, eax
0x180012dbd  jle     short loc_180012DC8
0x180012dbf  movzx   ebx, ax
0x180012dc2  or      ebx, 80070000h
0x180012dc8  lea     rax, aGetdtclogpathG; "GetDtcLogPath, GetProcAddress(hMtxcluDl"...
0x180012dcf  mov     r9d, 12Fh
0x180012dd5  jmp     short loc_180012DF4
0x180012dd7  mov     rdx, rbx
0x180012dda  mov     ecx, esi
0x180012ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012de1  mov     ebx, eax
0x180012de3  test    eax, eax
0x180012de5  jns     short loc_180012E1D
0x180012de7  lea     rax, aGetdtclogpathP; "GetDtcLogPath, pfnMtxCluGetDtcLogPathW "...
0x180012dee  mov     r9d, 135h
0x180012df4  mov     [rsp+48h+var_18], rax
0x180012df9  lea     r8, aComComplusDtcD_25; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180012e00  mov     edx, 1
0x180012e05  mov     dword ptr [rsp+48h+var_20], ebx
0x180012e09  lea     rax, aGetdtclogpath_0; "GetDtcLogPath"
0x180012e10  mov     [rsp+48h+var_28], rax
0x180012e15  lea     ecx, [rdx+6]
0x180012e18  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180012e1d  mov     rcx, rdi; hLibModule
0x180012e20  call    cs:__imp_FreeLibrary
0x180012e26  mov     rsi, [rsp+48h+arg_8]
0x180012e2b  xor     eax, eax
0x180012e2d  test    ebx, ebx
0x180012e2f  mov     rbx, [rsp+48h+arg_0]
0x180012e34  setns   al
0x180012e37  add     rsp, 40h
0x180012e3b  pop     rdi
0x180012e3c  retn
```
