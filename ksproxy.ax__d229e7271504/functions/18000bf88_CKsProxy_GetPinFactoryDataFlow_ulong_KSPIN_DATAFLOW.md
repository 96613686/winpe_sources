# CKsProxy::GetPinFactoryDataFlow(ulong,KSPIN_DATAFLOW *)

- ea: `0x18000bf88`
- end: `0x18000c146`
- name: `?GetPinFactoryDataFlow@CKsProxy@@QEAAJKPEAW4KSPIN_DATAFLOW@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(CKsProxy *this, int, enum KSPIN_DATAFLOW *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b6fc`

## callees

- `0x18000bf88`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c051`
- `KERNEL32!GetLastError` at `0x18000c0bc`
- `KERNEL32!GetLastError` at `0x18000c0fa`
- `KERNEL32!GetLastError` at `0x18000c051`
- `KERNEL32!GetLastError` at `0x18000c0bc`
- `KERNEL32!GetLastError` at `0x18000c0fa`
- `KERNEL32!CreateEventW` at `0x18000bff7`
- `KERNEL32!CreateEventW` at `0x18000bff7`
- `KERNEL32!CloseHandle` at `0x18000c078`
- `KERNEL32!CloseHandle` at `0x18000c078`
- `KERNEL32!GetOverlappedResult` at `0x18000c0ea`
- `KERNEL32!GetOverlappedResult` at `0x18000c0ea`
- `KERNEL32!DeviceIoControl` at `0x18000c041`
- `KERNEL32!DeviceIoControl` at `0x18000c041`

## pseudocode

```c
__int64 __fastcall CKsProxy::GetPinFactoryDataFlow(CKsProxy *this, int a2, enum KSPIN_DATAFLOW *a3)
{
  char *m_FilterHandle; // rsi
  signed int LastError; // eax
  unsigned int v6; // ebx
  signed int v8; // eax
  signed int v9; // eax
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-40h] BYREF
  GUID InBuffer; // [rsp+60h] [rbp-20h] BYREF
  int v12; // [rsp+70h] [rbp-10h]
  int v13; // [rsp+74h] [rbp-Ch]
  int v14; // [rsp+78h] [rbp-8h]
  int v15; // [rsp+7Ch] [rbp-4h]
  DWORD BytesReturned; // [rsp+98h] [rbp+18h] BYREF

  m_FilterHandle = (char *)this->m_FilterHandle;
  BytesReturned = 0;
  v12 = 2;
  v13 = 1;
  v14 = a2;
  v15 = 0;
  InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  if ( (unsigned __int64)(m_FilterHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return (unsigned int)-2147024890;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(m_FilterHandle, 0x2F0003u, &InBuffer, 0x20u, a3, 4u, &BytesReturned, &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101uLL:
          v6 = -2147024875;
          goto LABEL_7;
        case 0x105uLL:
          v6 = -2147024662;
          goto LABEL_7;
        case 0x107uLL:
          v6 = -2147023595;
          goto LABEL_7;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 != -2147023899 )
        goto LABEL_7;
      if ( !GetOverlappedResult(m_FilterHandle, &Overlapped, &BytesReturned, 1) )
      {
        v9 = GetLastError();
        v6 = v9;
        if ( v9 > 0 )
          v6 = (unsigned __int16)v9 | 0x80070000;
        goto LABEL_7;
      }
    }
    v6 = 0;
LABEL_7:
    CloseHandle(Overlapped.hEvent);
    return v6;
  }
  v8 = GetLastError();
  v6 = v8;
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x18000bf88  mov     [rsp-8+arg_0], rbx
0x18000bf8d  mov     [rsp-8+arg_10], rsi
0x18000bf92  push    rbp
0x18000bf93  mov     rbp, rsp
0x18000bf96  sub     rsp, 80h
0x18000bf9d  mov     rsi, [rcx+170h]
0x18000bfa4  mov     rbx, r8
0x18000bfa7  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x18000bfae  mov     [rbp+BytesReturned], 0
0x18000bfb5  mov     [rbp+var_10], 2
0x18000bfbc  lea     rax, [rsi-1]
0x18000bfc0  mov     [rbp+var_C], 1
0x18000bfc7  mov     [rbp+var_8], edx
0x18000bfca  mov     [rbp+var_4], 0
0x18000bfd1  movdqu  [rbp+InBuffer], xmm0
0x18000bfd6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000bfda  ja      loc_18000C13C
0x18000bfe0  xorps   xmm0, xmm0
0x18000bfe3  xor     r9d, r9d; lpName
0x18000bfe6  xor     r8d, r8d; bInitialState
0x18000bfe9  xor     ecx, ecx; lpEventAttributes
0x18000bfeb  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000bfef  lea     edx, [r9+1]; bManualReset
0x18000bff3  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000bff7  call    cs:__imp_CreateEventW
0x18000bffe  nop     dword ptr [rax+rax+00h]
0x18000c003  mov     [rbp+Overlapped.hEvent], rax
0x18000c007  test    rax, rax
0x18000c00a  jz      loc_18000C0BC
0x18000c010  lea     rax, [rbp+Overlapped]
0x18000c014  mov     r9d, 20h ; ' '; nInBufferSize
0x18000c01a  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x18000c01f  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000c023  lea     rax, [rbp+BytesReturned]
0x18000c027  mov     edx, 2F0003h; dwIoControlCode
0x18000c02c  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x18000c031  mov     rcx, rsi; hDevice
0x18000c034  mov     [rsp+80h+nOutBufferSize], 4; nOutBufferSize
0x18000c03c  mov     [rsp+80h+lpOutBuffer], rbx; lpOutBuffer
0x18000c041  call    cs:__imp_DeviceIoControl
0x18000c048  nop     dword ptr [rax+rax+00h]
0x18000c04d  test    eax, eax
0x18000c04f  jnz     short loc_18000C09C
0x18000c051  call    cs:__imp_GetLastError
0x18000c058  nop     dword ptr [rax+rax+00h]
0x18000c05d  mov     ebx, eax
0x18000c05f  test    eax, eax
0x18000c061  jle     short loc_18000C06C
0x18000c063  movzx   ebx, ax
0x18000c066  or      ebx, 80070000h
0x18000c06c  cmp     ebx, 800703E5h
0x18000c072  jz      short loc_18000C0D9
0x18000c074  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x18000c078  call    cs:__imp_CloseHandle
0x18000c07f  nop     dword ptr [rax+rax+00h]
0x18000c084  lea     r11, [rsp+80h+var_s0]
0x18000c08c  mov     eax, ebx
0x18000c08e  mov     rbx, [r11+10h]
0x18000c092  mov     rsi, [r11+20h]
0x18000c096  mov     rsp, r11
0x18000c099  pop     rbp
0x18000c09a  retn
0x18000c09c  mov     rax, [rbp+Overlapped.Internal]
0x18000c0a0  sub     rax, 101h
0x18000c0a6  jz      loc_18000C132
0x18000c0ac  sub     rax, 4
0x18000c0b0  jz      short loc_18000C128
0x18000c0b2  cmp     rax, 2
0x18000c0b6  jz      short loc_18000C11E
0x18000c0b8  xor     ebx, ebx
0x18000c0ba  jmp     short loc_18000C074
0x18000c0bc  call    cs:__imp_GetLastError
0x18000c0c3  nop     dword ptr [rax+rax+00h]
0x18000c0c8  mov     ebx, eax
0x18000c0ca  test    eax, eax
0x18000c0cc  jle     short loc_18000C084
0x18000c0ce  movzx   ebx, ax
0x18000c0d1  or      ebx, 80070000h
0x18000c0d7  jmp     short loc_18000C084
0x18000c0d9  mov     r9d, 1; bWait
0x18000c0df  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x18000c0e3  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000c0e7  mov     rcx, rsi; hFile
0x18000c0ea  call    cs:__imp_GetOverlappedResult
0x18000c0f1  nop     dword ptr [rax+rax+00h]
0x18000c0f6  test    eax, eax
0x18000c0f8  jnz     short loc_18000C0B8
0x18000c0fa  call    cs:__imp_GetLastError
0x18000c101  nop     dword ptr [rax+rax+00h]
0x18000c106  mov     ebx, eax
0x18000c108  test    eax, eax
0x18000c10a  jle     loc_18000C074
0x18000c110  movzx   ebx, ax
0x18000c113  or      ebx, 80070000h
0x18000c119  jmp     loc_18000C074
0x18000c11e  mov     ebx, 80070515h
0x18000c123  jmp     loc_18000C074
0x18000c128  mov     ebx, 800700EAh
0x18000c12d  jmp     loc_18000C074
0x18000c132  mov     ebx, 80070015h
0x18000c137  jmp     loc_18000C074
0x18000c13c  mov     ebx, 80070006h
0x18000c141  jmp     loc_18000C084
```
