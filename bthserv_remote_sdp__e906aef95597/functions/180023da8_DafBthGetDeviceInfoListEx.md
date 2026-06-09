# DafBthGetDeviceInfoListEx

- ea: `0x180023da8`
- end: `0x18002400c`
- name: `DafBthGetDeviceInfoListEx`
- size: `612`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180022a74`

## callees

- `0x1800017a0`
- `0x1800026d0`
- `0x1800026dc`
- `0x18000270c`
- `0x180023da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180023e0c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180023e0c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180023f1f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180023f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023fd5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023e7a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023f57`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023e7a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023f57`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180023eab`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180023f8b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180023eab`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180023f8b`

## pseudocode

```c
__int64 __fastcall DafBthGetDeviceInfoListEx(HANDLE hFile, __int64 a2, _QWORD *a3)
{
  unsigned int v3; // ebx
  signed int LastError; // eax
  DWORD nOutBufferSize; // esi
  _DWORD *v8; // rax
  _DWORD *lpOutBuffer; // rdi
  HANDLE hEvent; // rcx
  signed int v11; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-19h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-11h] BYREF
  _DWORD OutBuffer[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v16; // [rsp+70h] [rbp+17h]

  v3 = 0;
  BytesReturned = 0;
  memset(&Overlapped, 0, 24);
  OutBuffer[1] = 3;
  OutBuffer[0] = 3;
  v16 = 0;
  Overlapped.hEvent = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Overlapped.hEvent )
  {
LABEL_2:
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError <= 0 )
      goto LABEL_22;
    goto LABEL_3;
  }
  if ( !DeviceIoControl(hFile, 0x411058u, OutBuffer, 0x18u, OutBuffer, 0x18u, &BytesReturned, &Overlapped) )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( LastError > 0 )
      {
LABEL_3:
        v3 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_22;
      }
      v3 = LastError;
      goto LABEL_22;
    }
    if ( !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
      goto LABEL_2;
  }
  if ( !DWORD2(v16) )
  {
    v3 = -2147023728;
    goto LABEL_22;
  }
  nOutBufferSize = 832 * DWORD2(v16) + 24;
  v8 = o_malloc_0(nOutBufferSize);
  lpOutBuffer = v8;
  if ( !v8 )
  {
    v3 = -2147024882;
    goto LABEL_22;
  }
  memset_0(v8, 0, nOutBufferSize);
  hEvent = Overlapped.hEvent;
  lpOutBuffer[1] = 3;
  *lpOutBuffer = 3;
  ResetEvent(hEvent);
  if ( !DeviceIoControl(hFile, 0x411058u, lpOutBuffer, 0x18u, lpOutBuffer, nOutBufferSize, &BytesReturned, &Overlapped) )
  {
    v11 = GetLastError();
    if ( v11 != 997 )
    {
      if ( v11 <= 0 )
      {
        v3 = v11;
        goto LABEL_18;
      }
      goto LABEL_17;
    }
    if ( !GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
    {
      v11 = GetLastError();
      v3 = v11;
      if ( v11 <= 0 )
      {
LABEL_18:
        free(lpOutBuffer);
        goto LABEL_22;
      }
LABEL_17:
      v3 = (unsigned __int16)v11 | 0x80070000;
      goto LABEL_18;
    }
  }
  *a3 = lpOutBuffer;
LABEL_22:
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  return v3;
}

```

## disassembly

```asm
0x180023da8  mov     [rsp-8+arg_8], rbx
0x180023dad  mov     [rsp-8+arg_18], rsi
0x180023db2  push    rbp
0x180023db3  push    rdi
0x180023db4  push    r12
0x180023db6  push    r14
0x180023db8  push    r15
0x180023dba  lea     rbp, [rsp-37h]
0x180023dbf  sub     rsp, 90h
0x180023dc6  mov     rax, cs:__security_cookie
0x180023dcd  xor     rax, rsp
0x180023dd0  mov     [rbp+57h+var_30], rax
0x180023dd4  xor     ebx, ebx
0x180023dd6  mov     r12, r8
0x180023dd9  and     [rbp+57h+BytesReturned], ebx
0x180023ddc  mov     r14, rcx
0x180023ddf  and     [rbp+57h+Overlapped.Internal], rbx
0x180023de3  xorps   xmm0, xmm0
0x180023de6  xorps   xmm1, xmm1
0x180023de9  mov     r9d, 1F0003h; dwDesiredAccess
0x180023def  lea     eax, [rbx+3]
0x180023df2  xor     edx, edx; lpName
0x180023df4  lea     edi, [rbx+1]
0x180023df7  mov     [rbp+57h+var_44], eax
0x180023dfa  mov     r8d, edi; dwFlags
0x180023dfd  mov     [rbp+57h+OutBuffer], eax
0x180023e00  xor     ecx, ecx; lpEventAttributes
0x180023e02  movdqu  xmmword ptr [rbp+57h+Overlapped.InternalHigh], xmm0
0x180023e07  movdqu  [rbp+57h+var_40], xmm1
0x180023e0c  call    cs:__imp_CreateEventExW
0x180023e13  nop     dword ptr [rax+rax+00h]
0x180023e18  mov     [rbp+57h+Overlapped.hEvent], rax
0x180023e1c  test    rax, rax
0x180023e1f  jnz     short loc_180023E45
0x180023e21  call    cs:__imp_GetLastError
0x180023e28  nop     dword ptr [rax+rax+00h]
0x180023e2d  mov     ebx, eax
0x180023e2f  test    eax, eax
0x180023e31  jle     loc_180023FCC
0x180023e37  movzx   ebx, ax
0x180023e3a  or      ebx, 80070000h
0x180023e40  jmp     loc_180023FCC
0x180023e45  lea     rax, [rbp+57h+Overlapped]
0x180023e49  mov     r9d, 18h; nInBufferSize
0x180023e4f  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x180023e54  lea     r8, [rbp+57h+OutBuffer]; lpInBuffer
0x180023e58  lea     rax, [rbp+57h+BytesReturned]
0x180023e5c  mov     edx, 411058h; dwIoControlCode
0x180023e61  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x180023e66  mov     rcx, r14; hDevice
0x180023e69  lea     rax, [rbp+57h+OutBuffer]
0x180023e6d  mov     [rsp+0B0h+nOutBufferSize], 18h; nOutBufferSize
0x180023e75  mov     [rsp+0B0h+lpOutBuffer], rax; lpOutBuffer
0x180023e7a  call    cs:__imp_DeviceIoControl
0x180023e81  nop     dword ptr [rax+rax+00h]
0x180023e86  test    eax, eax
0x180023e88  jnz     short loc_180023EBF
0x180023e8a  call    cs:__imp_GetLastError
0x180023e91  nop     dword ptr [rax+rax+00h]
0x180023e96  cmp     eax, 3E5h
0x180023e9b  jnz     short loc_180023ED0
0x180023e9d  mov     r9d, edi; bWait
0x180023ea0  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x180023ea4  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x180023ea8  mov     rcx, r14; hFile
0x180023eab  call    cs:__imp_GetOverlappedResult
0x180023eb2  nop     dword ptr [rax+rax+00h]
0x180023eb7  test    eax, eax
0x180023eb9  jz      loc_180023E21
0x180023ebf  mov     eax, dword ptr [rbp+57h+var_40+8]
0x180023ec2  test    eax, eax
0x180023ec4  jnz     short loc_180023EDF
0x180023ec6  mov     ebx, 80070490h
0x180023ecb  jmp     loc_180023FCC
0x180023ed0  test    eax, eax
0x180023ed2  jg      loc_180023E37
0x180023ed8  mov     ebx, eax
0x180023eda  jmp     loc_180023FCC
0x180023edf  imul    esi, eax, 340h
0x180023ee5  add     esi, 18h
0x180023ee8  mov     ecx, esi; Size
0x180023eea  mov     r15d, esi
0x180023eed  call    _o_malloc_0
0x180023ef2  mov     rdi, rax
0x180023ef5  test    rax, rax
0x180023ef8  jnz     short loc_180023F04
0x180023efa  mov     ebx, 8007000Eh
0x180023eff  jmp     loc_180023FCC
0x180023f04  mov     r8, r15; Size
0x180023f07  xor     edx, edx; Val
0x180023f09  mov     rcx, rdi; void *
0x180023f0c  call    memset_0
0x180023f11  mov     rcx, [rbp+57h+Overlapped.hEvent]; hEvent
0x180023f15  mov     eax, 3
0x180023f1a  mov     [rdi+4], eax
0x180023f1d  mov     [rdi], eax
0x180023f1f  call    cs:__imp_ResetEvent
0x180023f26  nop     dword ptr [rax+rax+00h]
0x180023f2b  lea     rax, [rbp+57h+Overlapped]
0x180023f2f  mov     r9d, 18h; nInBufferSize
0x180023f35  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x180023f3a  mov     r8, rdi; lpInBuffer
0x180023f3d  lea     rax, [rbp+57h+BytesReturned]
0x180023f41  mov     edx, 411058h; dwIoControlCode
0x180023f46  mov     [rsp+0B0h+lpBytesReturned], rax; lpBytesReturned
0x180023f4b  mov     rcx, r14; hDevice
0x180023f4e  mov     [rsp+0B0h+nOutBufferSize], esi; nOutBufferSize
0x180023f52  mov     [rsp+0B0h+lpOutBuffer], rdi; lpOutBuffer
0x180023f57  call    cs:__imp_DeviceIoControl
0x180023f5e  nop     dword ptr [rax+rax+00h]
0x180023f63  test    eax, eax
0x180023f65  jnz     short loc_180023FC8
0x180023f67  call    cs:__imp_GetLastError
0x180023f6e  nop     dword ptr [rax+rax+00h]
0x180023f73  cmp     eax, 3E5h
0x180023f78  jnz     short loc_180023FC0
0x180023f7a  mov     r9d, 1; bWait
0x180023f80  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x180023f84  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x180023f88  mov     rcx, r14; hFile
0x180023f8b  call    cs:__imp_GetOverlappedResult
0x180023f92  nop     dword ptr [rax+rax+00h]
0x180023f97  test    eax, eax
0x180023f99  jnz     short loc_180023FC8
0x180023f9b  call    cs:__imp_GetLastError
0x180023fa2  nop     dword ptr [rax+rax+00h]
0x180023fa7  mov     ebx, eax
0x180023fa9  test    eax, eax
0x180023fab  jle     short loc_180023FB6
0x180023fad  movzx   ebx, ax
0x180023fb0  or      ebx, 80070000h
0x180023fb6  mov     rcx, rdi; Block
0x180023fb9  call    free
0x180023fbe  jmp     short loc_180023FCC
0x180023fc0  test    eax, eax
0x180023fc2  jg      short loc_180023FAD
0x180023fc4  mov     ebx, eax
0x180023fc6  jmp     short loc_180023FB6
0x180023fc8  mov     [r12], rdi
0x180023fcc  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x180023fd0  test    rcx, rcx
0x180023fd3  jz      short loc_180023FE1
0x180023fd5  call    cs:__imp_CloseHandle
0x180023fdc  nop     dword ptr [rax+rax+00h]
0x180023fe1  mov     eax, ebx
0x180023fe3  mov     rcx, [rbp+57h+var_30]
0x180023fe7  xor     rcx, rsp; StackCookie
0x180023fea  call    __security_check_cookie
0x180023fef  lea     r11, [rsp+0B0h+var_20]
0x180023ff7  mov     rbx, [r11+38h]
0x180023ffb  mov     rsi, [r11+48h]
0x180023fff  mov     rsp, r11
0x180024002  pop     r15
0x180024004  pop     r14
0x180024006  pop     r12
0x180024008  pop     rdi
0x180024009  pop     rbp
0x18002400a  retn
```
