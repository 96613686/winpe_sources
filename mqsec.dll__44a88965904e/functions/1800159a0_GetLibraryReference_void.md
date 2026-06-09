# GetLibraryReference(void)

- ea: `0x1800159a0`
- end: `0x180015ac4`
- name: `?GetLibraryReference@@YAPEAUHINSTANCE__@@XZ`
- size: `292`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180015ad0`

## callees

- `0x180003426`
- `0x1800049ac`
- `0x18000ca5c`
- `0x1800159a0`
- `0x18002f0e0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1800159d7`
- `KERNEL32!GetModuleFileNameW` at `0x1800159d7`
- `KERNEL32!LoadLibraryW` at `0x180015a43`
- `KERNEL32!LoadLibraryW` at `0x180015a43`
- `KERNEL32!GetLastError` at `0x1800159e1`
- `KERNEL32!GetLastError` at `0x180015a4e`
- `KERNEL32!GetLastError` at `0x1800159e1`
- `KERNEL32!GetLastError` at `0x180015a4e`

## pseudocode

```c
HINSTANCE GetLibraryReference(void)
{
  DWORD LastError; // eax
  unsigned int v1; // ebx
  HINSTANCE result; // rax
  DWORD v3; // eax
  unsigned int v4; // ebx
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF

  Filename[259] = 0;
  if ( !GetModuleFileNameW(g_hInstance, Filename, 0x103u) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 10, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids, LastError);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v1);
    throw (bad_win32_error *)pExceptionObject;
  }
  result = LoadLibraryW(Filename);
  if ( !result )
  {
    v3 = GetLastError();
    v4 = v3;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 11, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids, v3);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v4);
    throw (bad_win32_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800159a0  push    rbx
0x1800159a2  sub     rsp, 260h
0x1800159a9  mov     rax, cs:__security_cookie
0x1800159b0  xor     rax, rsp
0x1800159b3  mov     [rsp+268h+var_18], rax
0x1800159bb  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800159c2  lea     rdx, [rsp+268h+Filename]; lpFilename
0x1800159c7  xor     eax, eax
0x1800159c9  mov     r8d, 103h; nSize
0x1800159cf  mov     [rsp+268h+var_22], ax
0x1800159d7  call    cs:__imp_GetModuleFileNameW
0x1800159dd  test    eax, eax
0x1800159df  jnz     short loc_180015A3E
0x1800159e1  call    cs:__imp_GetLastError
0x1800159e7  mov     ebx, eax
0x1800159e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159f0  lea     rdx, WPP_GLOBAL_Control
0x1800159f7  cmp     rcx, rdx
0x1800159fa  jz      short loc_180015A20
0x1800159fc  test    byte ptr [rcx+0BCh], 1
0x180015a03  jz      short loc_180015A20
0x180015a05  mov     rcx, [rcx+0B0h]
0x180015a0c  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015a13  mov     edx, 0Ah
0x180015a18  mov     r9d, eax
0x180015a1b  call    WPP_SF_d
0x180015a20  mov     edx, ebx; unsigned int
0x180015a22  lea     rcx, [rsp+268h+pExceptionObject]; this
0x180015a27  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015a2c  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180015a33  lea     rcx, [rsp+268h+pExceptionObject]; pExceptionObject
0x180015a38  call    _CxxThrowException_0
0x180015a3e  lea     rcx, [rsp+268h+Filename]; lpLibFileName
0x180015a43  call    cs:__imp_LoadLibraryW
0x180015a49  test    rax, rax
0x180015a4c  jnz     short loc_180015AAB
0x180015a4e  call    cs:__imp_GetLastError
0x180015a54  mov     ebx, eax
0x180015a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a5d  lea     rdx, WPP_GLOBAL_Control
0x180015a64  cmp     rcx, rdx
0x180015a67  jz      short loc_180015A8D
0x180015a69  test    byte ptr [rcx+0BCh], 1
0x180015a70  jz      short loc_180015A8D
0x180015a72  mov     rcx, [rcx+0B0h]
0x180015a79  lea     r8, WPP_dc0bbe74ca103883720d3da5dcd49021_Traceguids
0x180015a80  mov     edx, 0Bh
0x180015a85  mov     r9d, eax
0x180015a88  call    WPP_SF_d
0x180015a8d  mov     edx, ebx; unsigned int
0x180015a8f  lea     rcx, [rsp+268h+pExceptionObject]; this
0x180015a94  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015a99  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180015aa0  lea     rcx, [rsp+268h+pExceptionObject]; pExceptionObject
0x180015aa5  call    _CxxThrowException_0
0x180015aab  mov     rcx, [rsp+268h+var_18]
0x180015ab3  xor     rcx, rsp; StackCookie
0x180015ab6  call    __security_check_cookie
0x180015abb  add     rsp, 260h
0x180015ac2  pop     rbx
0x180015ac3  retn
```
