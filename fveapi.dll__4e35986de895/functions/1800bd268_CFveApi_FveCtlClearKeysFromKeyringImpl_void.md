# CFveApi::FveCtlClearKeysFromKeyringImpl(void)

- ea: `0x1800bd268`
- end: `0x1800bd3b2`
- name: `?FveCtlClearKeysFromKeyringImpl@CFveApi@@SAJXZ`
- size: `330`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800bd044`

## callees

- `0x180005410`
- `0x180008d70`
- `0x1800090c0`
- `0x1800bd268`
- `0x1800bd3b8`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd35b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd35b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bd2ef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800bd2ef`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800bd33b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800bd33b`

## pseudocode

```c
__int64 CFveApi::FveCtlClearKeysFromKeyringImpl(void)
{
  unsigned int LastHresultError; // ebx
  HANDLE FileW; // rdi
  DWORD BytesReturned; // [rsp+48h] [rbp-20h] BYREF

  LastHresultError = 0;
  BytesReturned = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 364, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
  FileW = CreateFileW(L"\\\\.\\BitLocker", 0x80u, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL || !DeviceIoControl(FileW, 0x4C4210D4u, 0, 0, 0, 0, &BytesReturned, 0) )
    LastHresultError = GetLastHresultError();
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      365,
      &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
      LastHresultError);
  return LastHresultError;
}

```

## disassembly

```asm
0x1800bd268  mov     [rsp+arg_0], rbx
0x1800bd26d  mov     [rsp+arg_8], rdi
0x1800bd272  push    r14
0x1800bd274  sub     rsp, 60h
0x1800bd278  mov     rax, cs:__security_cookie
0x1800bd27f  xor     rax, rsp
0x1800bd282  mov     [rsp+68h+var_18], rax
0x1800bd287  xor     ebx, ebx
0x1800bd289  mov     [rsp+68h+var_28], 0FFFFFFFFFFFFFFFFh
0x1800bd292  mov     [rsp+68h+BytesReturned], ebx
0x1800bd296  lea     r14, WPP_GLOBAL_Control
0x1800bd29d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd2a4  cmp     rcx, r14
0x1800bd2a7  jz      short loc_1800BD2C5
0x1800bd2a9  test    byte ptr [rcx+1Ch], 20h
0x1800bd2ad  jz      short loc_1800BD2C5
0x1800bd2af  mov     edx, 16Ch
0x1800bd2b4  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800bd2bb  mov     rcx, [rcx+10h]
0x1800bd2bf  call    WPP_SF_
0x1800bd2c4  nop
0x1800bd2c5  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800bd2ce  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800bd2d6  mov     r8d, 3; dwShareMode
0x1800bd2dc  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800bd2e1  xor     r9d, r9d; lpSecurityAttributes
0x1800bd2e4  lea     edx, [r8+7Dh]; dwDesiredAccess
0x1800bd2e8  lea     rcx, FileName; "\\\\.\\BitLocker"
0x1800bd2ef  call    cs:__imp_CreateFileW
0x1800bd2f6  nop     dword ptr [rax+rax+00h]
0x1800bd2fb  mov     rdi, rax
0x1800bd2fe  mov     [rsp+68h+var_28], rax
0x1800bd303  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bd307  jz      short loc_1800BD34B
0x1800bd309  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800bd312  lea     rax, [rsp+68h+BytesReturned]
0x1800bd317  mov     [rsp+68h+hTemplateFile], rax; lpBytesReturned
0x1800bd31c  mov     [rsp+68h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1800bd324  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOutBuffer
0x1800bd32d  xor     r9d, r9d; nInBufferSize
0x1800bd330  xor     r8d, r8d; lpInBuffer
0x1800bd333  mov     edx, 4C4210D4h; dwIoControlCode
0x1800bd338  mov     rcx, rdi; hDevice
0x1800bd33b  call    cs:__imp_DeviceIoControl
0x1800bd342  nop     dword ptr [rax+rax+00h]
0x1800bd347  test    eax, eax
0x1800bd349  jnz     short loc_1800BD352
0x1800bd34b  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x1800bd350  mov     ebx, eax
0x1800bd352  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800bd356  jz      short loc_1800BD367
0x1800bd358  mov     rcx, rdi; hObject
0x1800bd35b  call    cs:__imp_CloseHandle
0x1800bd362  nop     dword ptr [rax+rax+00h]
0x1800bd367  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd36e  cmp     rcx, r14
0x1800bd371  jz      short loc_1800BD391
0x1800bd373  test    byte ptr [rcx+1Ch], 20h
0x1800bd377  jz      short loc_1800BD391
0x1800bd379  mov     edx, 16Dh
0x1800bd37e  mov     r9d, ebx
0x1800bd381  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800bd388  mov     rcx, [rcx+10h]
0x1800bd38c  call    WPP_SF_d
0x1800bd391  mov     eax, ebx
0x1800bd393  mov     rcx, [rsp+68h+var_18]
0x1800bd398  xor     rcx, rsp; StackCookie
0x1800bd39b  call    __security_check_cookie
0x1800bd3a0  mov     rbx, [rsp+68h+arg_0]
0x1800bd3a5  mov     rdi, [rsp+68h+arg_8]
0x1800bd3aa  add     rsp, 60h
0x1800bd3ae  pop     r14
0x1800bd3b0  retn
0x180126d30  push    rbp
0x180126d32  sub     rsp, 40h
0x180126d36  mov     rbp, rdx
0x180126d39  mov     rcx, [rbp+40h]; hObject
0x180126d3d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180126d41  jz      short loc_180126D57
0x180126d43  call    cs:__imp_CloseHandle
0x180126d4a  nop     dword ptr [rax+rax+00h]
0x180126d4f  mov     qword ptr [rbp+40h], 0FFFFFFFFFFFFFFFFh
0x180126d57  add     rsp, 40h
0x180126d5b  pop     rbp
0x180126d5c  retn
```
