# CKsProxy::GetPinFactoryCommunication(ulong,KSPIN_COMMUNICATION *)

- ea: `0x18000cab4`
- end: `0x18000cc72`
- name: `?GetPinFactoryCommunication@CKsProxy@@QEAAJKPEAW4KSPIN_COMMUNICATION@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(CKsProxy *this, int, enum KSPIN_COMMUNICATION *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c14c`
- `0x18000d88c`
- `0x1800189b0`
- `0x180024d10`
- `0x180025480`

## callees

- `0x18000cab4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000cb7d`
- `KERNEL32!GetLastError` at `0x18000cbe8`
- `KERNEL32!GetLastError` at `0x18000cc26`
- `KERNEL32!GetLastError` at `0x18000cb7d`
- `KERNEL32!GetLastError` at `0x18000cbe8`
- `KERNEL32!GetLastError` at `0x18000cc26`
- `KERNEL32!CreateEventW` at `0x18000cb23`
- `KERNEL32!CreateEventW` at `0x18000cb23`
- `KERNEL32!CloseHandle` at `0x18000cba4`
- `KERNEL32!CloseHandle` at `0x18000cba4`
- `KERNEL32!GetOverlappedResult` at `0x18000cc16`
- `KERNEL32!GetOverlappedResult` at `0x18000cc16`
- `KERNEL32!DeviceIoControl` at `0x18000cb6d`
- `KERNEL32!DeviceIoControl` at `0x18000cb6d`

## pseudocode

```c
__int64 __fastcall CKsProxy::GetPinFactoryCommunication(CKsProxy *this, int a2, enum KSPIN_COMMUNICATION *a3)
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
  v12 = 7;
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
0x18000cab4  mov     [rsp-8+arg_0], rbx
0x18000cab9  mov     [rsp-8+arg_10], rsi
0x18000cabe  push    rbp
0x18000cabf  mov     rbp, rsp
0x18000cac2  sub     rsp, 80h
0x18000cac9  mov     rsi, [rcx+170h]
0x18000cad0  mov     rbx, r8
0x18000cad3  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x18000cada  mov     [rbp+BytesReturned], 0
0x18000cae1  mov     [rbp+var_10], 7
0x18000cae8  lea     rax, [rsi-1]
0x18000caec  mov     [rbp+var_C], 1
0x18000caf3  mov     [rbp+var_8], edx
0x18000caf6  mov     [rbp+var_4], 0
0x18000cafd  movdqu  [rbp+InBuffer], xmm0
0x18000cb02  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cb06  ja      loc_18000CC68
0x18000cb0c  xorps   xmm0, xmm0
0x18000cb0f  xor     r9d, r9d; lpName
0x18000cb12  xor     r8d, r8d; bInitialState
0x18000cb15  xor     ecx, ecx; lpEventAttributes
0x18000cb17  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000cb1b  lea     edx, [r9+1]; bManualReset
0x18000cb1f  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18000cb23  call    cs:__imp_CreateEventW
0x18000cb2a  nop     dword ptr [rax+rax+00h]
0x18000cb2f  mov     [rbp+Overlapped.hEvent], rax
0x18000cb33  test    rax, rax
0x18000cb36  jz      loc_18000CBE8
0x18000cb3c  lea     rax, [rbp+Overlapped]
0x18000cb40  mov     r9d, 20h ; ' '; nInBufferSize
0x18000cb46  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x18000cb4b  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000cb4f  lea     rax, [rbp+BytesReturned]
0x18000cb53  mov     edx, 2F0003h; dwIoControlCode
0x18000cb58  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x18000cb5d  mov     rcx, rsi; hDevice
0x18000cb60  mov     [rsp+80h+nOutBufferSize], 4; nOutBufferSize
0x18000cb68  mov     [rsp+80h+lpOutBuffer], rbx; lpOutBuffer
0x18000cb6d  call    cs:__imp_DeviceIoControl
0x18000cb74  nop     dword ptr [rax+rax+00h]
0x18000cb79  test    eax, eax
0x18000cb7b  jnz     short loc_18000CBC8
0x18000cb7d  call    cs:__imp_GetLastError
0x18000cb84  nop     dword ptr [rax+rax+00h]
0x18000cb89  mov     ebx, eax
0x18000cb8b  test    eax, eax
0x18000cb8d  jle     short loc_18000CB98
0x18000cb8f  movzx   ebx, ax
0x18000cb92  or      ebx, 80070000h
0x18000cb98  cmp     ebx, 800703E5h
0x18000cb9e  jz      short loc_18000CC05
0x18000cba0  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x18000cba4  call    cs:__imp_CloseHandle
0x18000cbab  nop     dword ptr [rax+rax+00h]
0x18000cbb0  lea     r11, [rsp+80h+var_s0]
0x18000cbb8  mov     eax, ebx
0x18000cbba  mov     rbx, [r11+10h]
0x18000cbbe  mov     rsi, [r11+20h]
0x18000cbc2  mov     rsp, r11
0x18000cbc5  pop     rbp
0x18000cbc6  retn
0x18000cbc8  mov     rax, [rbp+Overlapped.Internal]
0x18000cbcc  sub     rax, 101h
0x18000cbd2  jz      loc_18000CC5E
0x18000cbd8  sub     rax, 4
0x18000cbdc  jz      short loc_18000CC54
0x18000cbde  cmp     rax, 2
0x18000cbe2  jz      short loc_18000CC4A
0x18000cbe4  xor     ebx, ebx
0x18000cbe6  jmp     short loc_18000CBA0
0x18000cbe8  call    cs:__imp_GetLastError
0x18000cbef  nop     dword ptr [rax+rax+00h]
0x18000cbf4  mov     ebx, eax
0x18000cbf6  test    eax, eax
0x18000cbf8  jle     short loc_18000CBB0
0x18000cbfa  movzx   ebx, ax
0x18000cbfd  or      ebx, 80070000h
0x18000cc03  jmp     short loc_18000CBB0
0x18000cc05  mov     r9d, 1; bWait
0x18000cc0b  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x18000cc0f  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18000cc13  mov     rcx, rsi; hFile
0x18000cc16  call    cs:__imp_GetOverlappedResult
0x18000cc1d  nop     dword ptr [rax+rax+00h]
0x18000cc22  test    eax, eax
0x18000cc24  jnz     short loc_18000CBE4
0x18000cc26  call    cs:__imp_GetLastError
0x18000cc2d  nop     dword ptr [rax+rax+00h]
0x18000cc32  mov     ebx, eax
0x18000cc34  test    eax, eax
0x18000cc36  jle     loc_18000CBA0
0x18000cc3c  movzx   ebx, ax
0x18000cc3f  or      ebx, 80070000h
0x18000cc45  jmp     loc_18000CBA0
0x18000cc4a  mov     ebx, 80070515h
0x18000cc4f  jmp     loc_18000CBA0
0x18000cc54  mov     ebx, 800700EAh
0x18000cc59  jmp     loc_18000CBA0
0x18000cc5e  mov     ebx, 80070015h
0x18000cc63  jmp     loc_18000CBA0
0x18000cc68  mov     ebx, 80070006h
0x18000cc6d  jmp     loc_18000CBB0
```
