# CFileByteStreamSimple::HrSetFileCompression(int)

- ea: `0x1800352b0`
- end: `0x1800354bc`
- name: `?HrSetFileCompression@CFileByteStreamSimple@@UEAAJH@Z`
- size: `524`
- prototype: `__int64 __fastcall(CFileByteStreamSimple *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180011618`
- `0x1800264b4`
- `0x1800352b0`
- `0x18003bec8`
- `0x180053f1c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003539e`
- `KERNEL32!GetLastError` at `0x1800353dd`
- `KERNEL32!GetLastError` at `0x180035430`
- `KERNEL32!GetLastError` at `0x18003543d`
- `KERNEL32!GetLastError` at `0x18003546f`
- `KERNEL32!GetLastError` at `0x18003539e`
- `KERNEL32!GetLastError` at `0x1800353dd`
- `KERNEL32!GetLastError` at `0x180035430`
- `KERNEL32!GetLastError` at `0x18003543d`
- `KERNEL32!GetLastError` at `0x18003546f`
- `KERNEL32!CloseHandle` at `0x1800354a0`
- `KERNEL32!CloseHandle` at `0x1800354a0`
- `KERNEL32!DeviceIoControl` at `0x180035390`
- `KERNEL32!DeviceIoControl` at `0x180035426`
- `KERNEL32!DeviceIoControl` at `0x180035390`
- `KERNEL32!DeviceIoControl` at `0x180035426`
- `KERNEL32!CreateEventW` at `0x1800353c8`
- `KERNEL32!CreateEventW` at `0x1800353c8`
- `KERNEL32!GetCurrentThreadId` at `0x180035311`
- `KERNEL32!GetCurrentThreadId` at `0x180035311`
- `KERNEL32!GetOverlappedResult` at `0x180035465`
- `KERNEL32!GetOverlappedResult` at `0x180035465`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileByteStreamSimple::HrSetFileCompression(CFileByteStreamSimple *this, int a2)
{
  unsigned int v4; // ebx
  std::_Mutex_base *v5; // rax
  signed int v6; // eax
  signed int LastError; // eax
  signed int v8; // eax
  signed int v9; // eax
  struct _Mtx_internal_imp_t *v10; // rax
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  __int16 InBuffer; // [rsp+A0h] [rbp+40h] BYREF
  DWORD BytesReturned; // [rsp+A8h] [rbp+48h] BYREF

  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 312LL) )
  {
    return (unsigned int)-2134044667;
  }
  else
  {
    v4 = 0;
    if ( !*((_DWORD *)this + 56) || *((_DWORD *)this + 56) == GetCurrentThreadId() )
    {
      if ( *((_BYTE *)this + 128) )
      {
        v5 = (std::_Mutex_base *)std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*((char *)this + 48);
        std::_Mutex_base::lock(v5);
      }
      BytesReturned = 0;
      InBuffer = a2 != 0;
      if ( *((_DWORD *)this + 9) )
      {
        Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
        if ( Overlapped.hEvent )
          goto LABEL_20;
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( !v4 )
        {
LABEL_20:
          if ( DeviceIoControl(*((HANDLE *)this + 3), 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, &Overlapped)
            || GetLastError() == 997 )
          {
            goto LABEL_31;
          }
          v8 = GetLastError();
          v4 = v8;
          if ( v8 > 0 )
            v4 = (unsigned __int16)v8 | 0x80070000;
          if ( !v4 )
          {
LABEL_31:
            if ( !GetOverlappedResult(*((HANDLE *)this + 3), &Overlapped, &BytesReturned, 1) )
            {
              v9 = GetLastError();
              v4 = v9;
              if ( v9 > 0 )
                v4 = (unsigned __int16)v9 | 0x80070000;
            }
          }
        }
      }
      else if ( !DeviceIoControl(*((HANDLE *)this + 3), 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
      {
        v6 = GetLastError();
        v4 = v6;
        if ( v6 > 0 )
          v4 = (unsigned __int16)v6 | 0x80070000;
      }
      if ( *((_BYTE *)this + 128) )
      {
        v10 = (struct _Mtx_internal_imp_t *)std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*((char *)this + 48);
        Mtx_unlock(v10);
      }
    }
    else
    {
      MsoShipAssertTagProc(7118878);
      v4 = -2147467259;
    }
    if ( Overlapped.hEvent )
      CloseHandle(Overlapped.hEvent);
  }
  return v4;
}

```

## disassembly

```asm
0x1800352b0  mov     [rsp-28h+arg_0], rbx
0x1800352b5  push    rbp
0x1800352b6  push    rsi
0x1800352b7  push    rdi
0x1800352b8  push    r14
0x1800352ba  push    r15
0x1800352bc  mov     rbp, rsp
0x1800352bf  sub     rsp, 60h
0x1800352c3  mov     r14d, edx
0x1800352c6  mov     rsi, rcx
0x1800352c9  xor     r15d, r15d
0x1800352cc  mov     [rbp+Overlapped.Internal], r15
0x1800352d0  xorps   xmm0, xmm0
0x1800352d3  movdqu  xmmword ptr [rbp+Overlapped.InternalHigh], xmm0
0x1800352d8  mov     [rbp+Overlapped.hEvent], r15
0x1800352dc  mov     r8d, cs:_tls_index
0x1800352e3  mov     rax, gs:58h
0x1800352ec  mov     ecx, 138h
0x1800352f1  mov     rax, [rax+r8*8]
0x1800352f5  cmp     [rcx+rax], r15d
0x1800352f9  jbe     short loc_180035305
0x1800352fb  mov     ebx, 80CD1005h
0x180035300  jmp     loc_1800354A6
0x180035305  mov     ebx, r15d
0x180035308  cmp     [rsi+0E0h], r15d
0x18003530f  jz      short loc_180035333
0x180035311  call    cs:__imp_GetCurrentThreadId
0x180035317  cmp     [rsi+0E0h], eax
0x18003531d  jz      short loc_180035333
0x18003531f  mov     ecx, 6CA01Eh
0x180035324  call    MsoShipAssertTagProc
0x180035329  mov     ebx, 80004005h
0x18003532e  jmp     loc_180035497
0x180035333  lea     rdi, [rsi+30h]
0x180035337  cmp     [rdi+50h], r15b
0x18003533b  jz      short loc_18003534E
0x18003533d  mov     rcx, rdi
0x180035340  call    ??D?$_Optional_construct_base@U?$DataField@_N@Telemetry@Mso@@@std@@QEGBAAEBU?$DataField@_N@Telemetry@Mso@@XZ; std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*(void)
0x180035345  mov     rcx, rax; this
0x180035348  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18003534d  nop
0x18003534e  mov     [rbp+BytesReturned], r15d
0x180035352  mov     eax, r15d
0x180035355  test    r14d, r14d
0x180035358  setnz   al
0x18003535b  mov     [rbp+InBuffer], ax
0x18003535f  cmp     [rsi+24h], r15d
0x180035363  jnz     short loc_1800353BC
0x180035365  mov     [rsp+60h+lpOverlapped], r15; lpOverlapped
0x18003536a  lea     rax, [rbp+BytesReturned]
0x18003536e  mov     [rsp+60h+lpBytesReturned], rax; lpBytesReturned
0x180035373  mov     [rsp+60h+nOutBufferSize], r15d; nOutBufferSize
0x180035378  mov     [rsp+60h+lpOutBuffer], r15; lpOutBuffer
0x18003537d  mov     r9d, 2; nInBufferSize
0x180035383  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180035387  mov     edx, 9C040h; dwIoControlCode
0x18003538c  mov     rcx, [rsi+18h]; hDevice
0x180035390  call    cs:__imp_DeviceIoControl
0x180035396  test    eax, eax
0x180035398  jnz     loc_180035481
0x18003539e  call    cs:__imp_GetLastError
0x1800353a4  mov     ebx, eax
0x1800353a6  test    eax, eax
0x1800353a8  jle     loc_180035481
0x1800353ae  movzx   ebx, ax
0x1800353b1  or      ebx, 80070000h
0x1800353b7  jmp     loc_180035481
0x1800353bc  xor     r9d, r9d; lpName
0x1800353bf  xor     r8d, r8d; bInitialState
0x1800353c2  lea     edx, [r9+1]; bManualReset
0x1800353c6  xor     ecx, ecx; lpEventAttributes
0x1800353c8  call    cs:__imp_CreateEventW
0x1800353ce  mov     [rbp+Overlapped.hEvent], rax
0x1800353d2  mov     r14d, 80070000h
0x1800353d8  test    rax, rax
0x1800353db  jnz     short loc_1800353F7
0x1800353dd  call    cs:__imp_GetLastError
0x1800353e3  mov     ebx, eax
0x1800353e5  test    eax, eax
0x1800353e7  jle     short loc_1800353EF
0x1800353e9  movzx   ebx, ax
0x1800353ec  or      ebx, r14d
0x1800353ef  test    ebx, ebx
0x1800353f1  jnz     loc_180035481
0x1800353f7  lea     rax, [rbp+Overlapped]
0x1800353fb  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x180035400  lea     rax, [rbp+BytesReturned]
0x180035404  mov     [rsp+60h+lpBytesReturned], rax; lpBytesReturned
0x180035409  mov     [rsp+60h+nOutBufferSize], r15d; nOutBufferSize
0x18003540e  mov     [rsp+60h+lpOutBuffer], r15; lpOutBuffer
0x180035413  mov     r9d, 2; nInBufferSize
0x180035419  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18003541d  mov     edx, 9C040h; dwIoControlCode
0x180035422  mov     rcx, [rsi+18h]; hDevice
0x180035426  call    cs:__imp_DeviceIoControl
0x18003542c  test    eax, eax
0x18003542e  jnz     short loc_180035453
0x180035430  call    cs:__imp_GetLastError
0x180035436  cmp     eax, 3E5h
0x18003543b  jz      short loc_180035453
0x18003543d  call    cs:__imp_GetLastError
0x180035443  mov     ebx, eax
0x180035445  test    eax, eax
0x180035447  jle     short loc_18003544F
0x180035449  movzx   ebx, ax
0x18003544c  or      ebx, r14d
0x18003544f  test    ebx, ebx
0x180035451  jnz     short loc_180035481
0x180035453  mov     r9d, 1; bWait
0x180035459  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x18003545d  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180035461  mov     rcx, [rsi+18h]; hFile
0x180035465  call    cs:__imp_GetOverlappedResult
0x18003546b  test    eax, eax
0x18003546d  jnz     short loc_180035481
0x18003546f  call    cs:__imp_GetLastError
0x180035475  mov     ebx, eax
0x180035477  test    eax, eax
0x180035479  jle     short loc_180035481
0x18003547b  movzx   ebx, ax
0x18003547e  or      ebx, r14d
0x180035481  cmp     [rdi+50h], r15b
0x180035485  jz      short loc_180035497
0x180035487  mov     rcx, rdi
0x18003548a  call    ??D?$_Optional_construct_base@U?$DataField@_N@Telemetry@Mso@@@std@@QEGBAAEBU?$DataField@_N@Telemetry@Mso@@XZ; std::_Optional_construct_base<Mso::Telemetry::DataField<bool>>::operator*(void)
0x18003548f  mov     rcx, rax; _Mtx_t
0x180035492  call    _Mtx_unlock
0x180035497  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x18003549b  test    rcx, rcx
0x18003549e  jz      short loc_1800354A6
0x1800354a0  call    cs:__imp_CloseHandle
0x1800354a6  mov     eax, ebx
0x1800354a8  mov     rbx, [rsp+60h+arg_0]
0x1800354b0  add     rsp, 60h
0x1800354b4  pop     r15
0x1800354b6  pop     r14
0x1800354b8  pop     rdi
0x1800354b9  pop     rsi
0x1800354ba  pop     rbp
0x1800354bb  retn
```
