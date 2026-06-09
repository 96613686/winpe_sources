# GetLibraryReference

- ea: `0x18001a3b0`
- end: `0x18001a496`
- name: `GetLibraryReference`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001a49c`

## callees

- `0x1800022d6`
- `0x1800093d0`
- `0x180013d20`
- `0x18001a3b0`
- `0x180023ca0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18001a3e7`
- `KERNEL32!GetModuleFileNameW` at `0x18001a3e7`
- `KERNEL32!LoadLibraryW` at `0x18001a434`
- `KERNEL32!LoadLibraryW` at `0x18001a434`
- `KERNEL32!GetLastError` at `0x18001a3f1`
- `KERNEL32!GetLastError` at `0x18001a43f`
- `KERNEL32!GetLastError` at `0x18001a3f1`
- `KERNEL32!GetLastError` at `0x18001a43f`

## pseudocode

```c
HMODULE GetLibraryReference()
{
  DWORD LastError; // eax
  unsigned int v1; // ebx
  HMODULE result; // rax
  DWORD v3; // eax
  unsigned int v4; // ebx
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF

  Filename[259] = 0;
  if ( !GetModuleFileNameW(g_hInstance, Filename, 0x103u) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"rt/CRtReceive", 0x4B1u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v1);
    throw (bad_win32_error *)pExceptionObject;
  }
  result = LoadLibraryW(Filename);
  if ( !result )
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 )
      LogMsgNTStatus(v3, (wchar_t *)L"rt/CRtReceive", 0x4B2u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v4);
    throw (bad_win32_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18001a3b0  push    rbx
0x18001a3b2  sub     rsp, 260h
0x18001a3b9  mov     rax, cs:__security_cookie
0x18001a3c0  xor     rax, rsp
0x18001a3c3  mov     [rsp+268h+var_18], rax
0x18001a3cb  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18001a3d2  lea     rdx, [rsp+268h+Filename]; lpFilename
0x18001a3d7  xor     eax, eax
0x18001a3d9  mov     r8d, 103h; nSize
0x18001a3df  mov     [rsp+268h+var_22], ax
0x18001a3e7  call    cs:__imp_GetModuleFileNameW
0x18001a3ed  test    eax, eax
0x18001a3ef  jnz     short loc_18001A42F
0x18001a3f1  call    cs:__imp_GetLastError
0x18001a3f7  mov     ebx, eax
0x18001a3f9  test    eax, eax
0x18001a3fb  jz      short loc_18001A411
0x18001a3fd  mov     r8d, 4B1h; unsigned __int16
0x18001a403  lea     rdx, aRtCrtreceive; "rt/CRtReceive"
0x18001a40a  mov     ecx, eax; int
0x18001a40c  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001a411  mov     edx, ebx; unsigned int
0x18001a413  lea     rcx, [rsp+268h+pExceptionObject]; this
0x18001a418  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18001a41d  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18001a424  lea     rcx, [rsp+268h+pExceptionObject]; pExceptionObject
0x18001a429  call    _CxxThrowException_0
0x18001a42f  lea     rcx, [rsp+268h+Filename]; lpLibFileName
0x18001a434  call    cs:__imp_LoadLibraryW
0x18001a43a  test    rax, rax
0x18001a43d  jnz     short loc_18001A47D
0x18001a43f  call    cs:__imp_GetLastError
0x18001a445  mov     ebx, eax
0x18001a447  test    eax, eax
0x18001a449  jz      short loc_18001A45F
0x18001a44b  mov     r8d, 4B2h; unsigned __int16
0x18001a451  lea     rdx, aRtCrtreceive; "rt/CRtReceive"
0x18001a458  mov     ecx, eax; int
0x18001a45a  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18001a45f  mov     edx, ebx; unsigned int
0x18001a461  lea     rcx, [rsp+268h+pExceptionObject]; this
0x18001a466  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18001a46b  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18001a472  lea     rcx, [rsp+268h+pExceptionObject]; pExceptionObject
0x18001a477  call    _CxxThrowException_0
0x18001a47d  mov     rcx, [rsp+268h+var_18]
0x18001a485  xor     rcx, rsp; StackCookie
0x18001a488  call    __security_check_cookie
0x18001a48d  add     rsp, 260h
0x18001a494  pop     rbx
0x18001a495  retn
```
