# CKsProxy::QueryTopologyItems(ulong,KSMULTIPLE_ITEM * *)

- ea: `0x18000c6f0`
- end: `0x18000c933`
- name: `?QueryTopologyItems@CKsProxy@@QEAAJKPEAPEAUKSMULTIPLE_ITEM@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(CKsProxy *this, int, struct KSMULTIPLE_ITEM **)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c1f4`
- `0x18000cc78`
- `0x1800196f0`
- `0x1800218a4`
- `0x180021a94`

## callees

- `0x18000bde0`
- `0x18000c6f0`
- `0x18001f1c4`
- `0x18001f210`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c7b6`
- `KERNEL32!GetLastError` at `0x18000c891`
- `KERNEL32!GetLastError` at `0x18000c8da`
- `KERNEL32!GetLastError` at `0x18000c7b6`
- `KERNEL32!GetLastError` at `0x18000c891`
- `KERNEL32!GetLastError` at `0x18000c8da`
- `KERNEL32!CreateEventW` at `0x18000c758`
- `KERNEL32!CreateEventW` at `0x18000c758`
- `KERNEL32!CloseHandle` at `0x18000c7e1`
- `KERNEL32!CloseHandle` at `0x18000c7e1`
- `KERNEL32!GetOverlappedResult` at `0x18000c8c6`
- `KERNEL32!GetOverlappedResult` at `0x18000c8c6`
- `KERNEL32!DeviceIoControl` at `0x18000c7a6`
- `KERNEL32!DeviceIoControl` at `0x18000c7a6`

## pseudocode

```c
__int64 __fastcall CKsProxy::QueryTopologyItems(CKsProxy *this, int a2, struct KSMULTIPLE_ITEM **a3)
{
  char *m_FilterHandle; // rsi
  signed int LastError; // eax
  int v7; // ebx
  struct KSMULTIPLE_ITEM *lpOutBuffer; // rax
  unsigned __int64 v10; // rdx
  signed int v11; // eax
  signed int v12; // eax
  GUID InBuffer; // [rsp+40h] [rbp-40h] BYREF
  int v14; // [rsp+50h] [rbp-30h]
  int v15; // [rsp+54h] [rbp-2Ch]
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-28h] BYREF
  DWORD BytesReturned; // [rsp+A8h] [rbp+28h] BYREF

  m_FilterHandle = (char *)this->m_FilterHandle;
  BytesReturned = 0;
  v14 = a2;
  v15 = 1;
  InBuffer = GUID_720d4ac0_7533_11d0_a5d6_28db04c10000;
  if ( (unsigned __int64)(m_FilterHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return (unsigned int)-2147024890;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(m_FilterHandle, 0x2F0003u, &InBuffer, 0x18u, 0, 0, &BytesReturned, &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101uLL:
          v7 = -2147024875;
          goto LABEL_7;
        case 0x105uLL:
          v7 = -2147024662;
          goto LABEL_7;
        case 0x107uLL:
          v7 = -2147023595;
          goto LABEL_7;
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 != -2147023899 )
        goto LABEL_7;
      if ( !GetOverlappedResult(m_FilterHandle, &Overlapped, &BytesReturned, 1) )
      {
        v12 = GetLastError();
        v7 = v12;
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
        goto LABEL_7;
      }
    }
    v7 = 0;
LABEL_7:
    CloseHandle(Overlapped.hEvent);
    goto LABEL_8;
  }
  v11 = GetLastError();
  v7 = v11;
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
LABEL_8:
  if ( v7 == -2147024662 )
  {
    lpOutBuffer = (struct KSMULTIPLE_ITEM *)operator new[](BytesReturned);
    *a3 = lpOutBuffer;
    if ( !lpOutBuffer )
      return 2147942414LL;
    v7 = KsSynchronousDeviceControl(
           (char *)this->m_FilterHandle,
           0x2F0003u,
           &InBuffer,
           0x18u,
           lpOutBuffer,
           BytesReturned,
           &BytesReturned);
    if ( v7 < 0 )
      operator delete(*a3, v10);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c6f0  mov     [rsp-18h+arg_0], rbx
0x18000c6f5  mov     [rsp-18h+arg_10], rsi
0x18000c6fa  push    rbp
0x18000c6fb  push    r14
0x18000c6fd  push    r15
0x18000c6ff  mov     rbp, rsp
0x18000c702  sub     rsp, 80h
0x18000c709  mov     rsi, [rcx+170h]
0x18000c710  mov     r14, r8
0x18000c713  movups  xmm0, xmmword ptr cs:_GUID_720d4ac0_7533_11d0_a5d6_28db04c10000.Data1
0x18000c71a  mov     r15, rcx
0x18000c71d  mov     [rbp+BytesReturned], 0
0x18000c724  mov     [rbp+var_30], edx
0x18000c727  lea     rax, [rsi-1]
0x18000c72b  mov     [rbp+var_2C], 1
0x18000c732  movdqu  [rbp+InBuffer], xmm0
0x18000c737  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c73b  ja      loc_18000C929
0x18000c741  xorps   xmm0, xmm0
0x18000c744  xor     r9d, r9d; lpName
0x18000c747  xor     r8d, r8d; bInitialState
0x18000c74a  xor     ecx, ecx; lpEventAttributes
0x18000c74c  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000c750  lea     edx, [r9+1]; bManualReset
0x18000c754  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000c758  call    cs:__imp_CreateEventW
0x18000c75f  nop     dword ptr [rax+rax+00h]
0x18000c764  mov     [rbp+Overlapped.hEvent], rax
0x18000c768  test    rax, rax
0x18000c76b  jz      loc_18000C891
0x18000c771  lea     rax, [rbp+Overlapped]
0x18000c775  mov     r9d, 18h; nInBufferSize
0x18000c77b  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x18000c780  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000c784  lea     rax, [rbp+BytesReturned]
0x18000c788  mov     edx, 2F0003h; dwIoControlCode
0x18000c78d  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x18000c792  mov     rcx, rsi; hDevice
0x18000c795  mov     [rsp+80h+nOutBufferSize], 0; nOutBufferSize
0x18000c79d  mov     [rsp+80h+lpOutBuffer], 0; lpOutBuffer
0x18000c7a6  call    cs:__imp_DeviceIoControl
0x18000c7ad  nop     dword ptr [rax+rax+00h]
0x18000c7b2  test    eax, eax
0x18000c7b4  jnz     short loc_18000C82B
0x18000c7b6  call    cs:__imp_GetLastError
0x18000c7bd  nop     dword ptr [rax+rax+00h]
0x18000c7c2  mov     ebx, eax
0x18000c7c4  test    eax, eax
0x18000c7c6  jle     short loc_18000C7D1
0x18000c7c8  movzx   ebx, ax
0x18000c7cb  or      ebx, 80070000h
0x18000c7d1  cmp     ebx, 800703E5h
0x18000c7d7  jz      loc_18000C8B5
0x18000c7dd  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x18000c7e1  call    cs:__imp_CloseHandle
0x18000c7e8  nop     dword ptr [rax+rax+00h]
0x18000c7ed  cmp     ebx, 800700EAh
0x18000c7f3  jnz     loc_18000C88D
0x18000c7f9  mov     ecx, [rbp+BytesReturned]; unsigned __int64
0x18000c7fc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c801  mov     [r14], rax
0x18000c804  mov     rcx, rax
0x18000c807  test    rax, rax
0x18000c80a  jnz     short loc_18000C853
0x18000c80c  mov     eax, 8007000Eh
0x18000c811  lea     r11, [rsp+80h+var_s0]
0x18000c819  mov     rbx, [r11+20h]
0x18000c81d  mov     rsi, [r11+30h]
0x18000c821  mov     rsp, r11
0x18000c824  pop     r15
0x18000c826  pop     r14
0x18000c828  pop     rbp
0x18000c829  retn
0x18000c82b  mov     rax, [rbp+Overlapped.Internal]
0x18000c82f  sub     rax, 101h
0x18000c835  jz      loc_18000C912
0x18000c83b  sub     rax, 4
0x18000c83f  jz      loc_18000C908
0x18000c845  cmp     rax, 2
0x18000c849  jz      loc_18000C8FE
0x18000c84f  xor     ebx, ebx
0x18000c851  jmp     short loc_18000C7DD
0x18000c853  lea     rax, [rbp+BytesReturned]
0x18000c857  mov     r9d, 18h; nInBufferSize
0x18000c85d  mov     [rsp+80h+lpBytesReturned], rax; lpNumberOfBytesTransferred
0x18000c862  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000c866  mov     eax, [rbp+BytesReturned]
0x18000c869  mov     edx, 2F0003h; dwIoControlCode
0x18000c86e  mov     [rsp+80h+nOutBufferSize], eax; DWORD
0x18000c872  mov     [rsp+80h+lpOutBuffer], rcx; LPVOID
0x18000c877  mov     rcx, [r15+170h]; hFile
0x18000c87e  call    KsSynchronousDeviceControl
0x18000c883  mov     ebx, eax
0x18000c885  test    eax, eax
0x18000c887  js      loc_18000C91C
0x18000c88d  mov     eax, ebx
0x18000c88f  jmp     short loc_18000C811
0x18000c891  call    cs:__imp_GetLastError
0x18000c898  nop     dword ptr [rax+rax+00h]
0x18000c89d  mov     ebx, eax
0x18000c89f  test    eax, eax
0x18000c8a1  jle     loc_18000C7ED
0x18000c8a7  movzx   ebx, ax
0x18000c8aa  or      ebx, 80070000h
0x18000c8b0  jmp     loc_18000C7ED
0x18000c8b5  mov     r9d, 1; bWait
0x18000c8bb  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x18000c8bf  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000c8c3  mov     rcx, rsi; hFile
0x18000c8c6  call    cs:__imp_GetOverlappedResult
0x18000c8cd  nop     dword ptr [rax+rax+00h]
0x18000c8d2  test    eax, eax
0x18000c8d4  jnz     loc_18000C84F
0x18000c8da  call    cs:__imp_GetLastError
0x18000c8e1  nop     dword ptr [rax+rax+00h]
0x18000c8e6  mov     ebx, eax
0x18000c8e8  test    eax, eax
0x18000c8ea  jle     loc_18000C7DD
0x18000c8f0  movzx   ebx, ax
0x18000c8f3  or      ebx, 80070000h
0x18000c8f9  jmp     loc_18000C7DD
0x18000c8fe  mov     ebx, 80070515h
0x18000c903  jmp     loc_18000C7DD
0x18000c908  mov     ebx, 800700EAh
0x18000c90d  jmp     loc_18000C7DD
0x18000c912  mov     ebx, 80070015h
0x18000c917  jmp     loc_18000C7DD
0x18000c91c  mov     rcx, [r14]; void *
0x18000c91f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c924  jmp     loc_18000C88D
0x18000c929  mov     ebx, 80070006h
0x18000c92e  jmp     loc_18000C88D
```
