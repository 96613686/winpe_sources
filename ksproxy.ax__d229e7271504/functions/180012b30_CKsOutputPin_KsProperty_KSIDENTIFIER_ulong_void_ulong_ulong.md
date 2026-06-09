# CKsOutputPin::KsProperty(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x180012b30`
- end: `0x180012cb8`
- name: `?KsProperty@CKsOutputPin@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `392`
- prototype: `__int64 __fastcall(CKsOutputPin *this, struct KSIDENTIFIER *, DWORD, void *, DWORD nOutBufferSize, unsigned int *lpNumberOfBytesTransferred)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180012b30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180012bce`
- `KERNEL32!GetLastError` at `0x180012c32`
- `KERNEL32!GetLastError` at `0x180012c70`
- `KERNEL32!GetLastError` at `0x180012bce`
- `KERNEL32!GetLastError` at `0x180012c32`
- `KERNEL32!GetLastError` at `0x180012c70`
- `KERNEL32!CreateEventW` at `0x180012b6f`
- `KERNEL32!CreateEventW` at `0x180012b6f`
- `KERNEL32!CloseHandle` at `0x180012bf7`
- `KERNEL32!CloseHandle` at `0x180012bf7`
- `KERNEL32!GetOverlappedResult` at `0x180012c60`
- `KERNEL32!GetOverlappedResult` at `0x180012c60`
- `KERNEL32!DeviceIoControl` at `0x180012bbe`
- `KERNEL32!DeviceIoControl` at `0x180012bbe`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::KsProperty(
        CKsOutputPin *this,
        struct KSIDENTIFIER *a2,
        DWORD a3,
        void *a4,
        DWORD nOutBufferSize,
        unsigned int *lpNumberOfBytesTransferred)
{
  char *v6; // rsi
  signed int LastError; // eax
  unsigned int v11; // ebx
  signed int v13; // eax
  signed int v14; // eax
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-48h] BYREF

  v6 = *(char **)&this->m_bRunTimeError;
  if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return (unsigned int)-2147024890;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(v6, 0x2F0003u, a2, a3, a4, nOutBufferSize, lpNumberOfBytesTransferred, &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101uLL:
          v11 = -2147024875;
          goto LABEL_7;
        case 0x105uLL:
          v11 = -2147024662;
          goto LABEL_7;
        case 0x107uLL:
          v11 = -2147023595;
          goto LABEL_7;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 != -2147023899 )
        goto LABEL_7;
      if ( !GetOverlappedResult(v6, &Overlapped, lpNumberOfBytesTransferred, 1) )
      {
        v14 = GetLastError();
        v11 = v14;
        if ( v14 > 0 )
          v11 = (unsigned __int16)v14 | 0x80070000;
        goto LABEL_7;
      }
    }
    v11 = 0;
LABEL_7:
    CloseHandle(Overlapped.hEvent);
    return v11;
  }
  v13 = GetLastError();
  v11 = v13;
  if ( v13 > 0 )
    return (unsigned __int16)v13 | 0x80070000;
  return v11;
}

```

## disassembly

```asm
0x180012b30  push    rbx
0x180012b32  push    rbp
0x180012b33  push    rsi
0x180012b34  push    rdi
0x180012b35  push    r14
0x180012b37  sub     rsp, 60h
0x180012b3b  mov     rsi, [rcx+48h]
0x180012b3f  mov     rbx, r9
0x180012b42  mov     edi, r8d
0x180012b45  mov     r14, rdx
0x180012b48  lea     rax, [rsi-1]
0x180012b4c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012b50  ja      loc_180012CAE
0x180012b56  xorps   xmm0, xmm0
0x180012b59  xor     r9d, r9d; lpName
0x180012b5c  xor     r8d, r8d; bInitialState
0x180012b5f  xor     ecx, ecx; lpEventAttributes
0x180012b61  movups  xmmword ptr [rsp+88h+Overlapped.Internal], xmm0
0x180012b66  lea     edx, [r9+1]; bManualReset
0x180012b6a  movups  xmmword ptr [rsp+88h+Overlapped.10h], xmm0
0x180012b6f  call    cs:__imp_CreateEventW
0x180012b76  nop     dword ptr [rax+rax+00h]
0x180012b7b  mov     [rsp+88h+Overlapped.hEvent], rax
0x180012b80  test    rax, rax
0x180012b83  jz      loc_180012C32
0x180012b89  mov     rbp, [rsp+88h+lpNumberOfBytesTransferred]
0x180012b91  lea     rax, [rsp+88h+Overlapped]
0x180012b96  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x180012b9b  mov     r9d, edi; nInBufferSize
0x180012b9e  mov     eax, [rsp+88h+arg_20]
0x180012ba5  mov     r8, r14; lpInBuffer
0x180012ba8  mov     [rsp+88h+lpBytesReturned], rbp; lpBytesReturned
0x180012bad  mov     edx, 2F0003h; dwIoControlCode
0x180012bb2  mov     [rsp+88h+nOutBufferSize], eax; nOutBufferSize
0x180012bb6  mov     rcx, rsi; hDevice
0x180012bb9  mov     [rsp+88h+lpOutBuffer], rbx; lpOutBuffer
0x180012bbe  call    cs:__imp_DeviceIoControl
0x180012bc5  nop     dword ptr [rax+rax+00h]
0x180012bca  test    eax, eax
0x180012bcc  jnz     short loc_180012C11
0x180012bce  call    cs:__imp_GetLastError
0x180012bd5  nop     dword ptr [rax+rax+00h]
0x180012bda  mov     ebx, eax
0x180012bdc  mov     edi, 80070000h
0x180012be1  test    eax, eax
0x180012be3  jle     short loc_180012BEA
0x180012be5  movzx   ebx, ax
0x180012be8  or      ebx, edi
0x180012bea  cmp     ebx, 800703E5h
0x180012bf0  jz      short loc_180012C4F
0x180012bf2  mov     rcx, [rsp+88h+Overlapped.hEvent]; hObject
0x180012bf7  call    cs:__imp_CloseHandle
0x180012bfe  nop     dword ptr [rax+rax+00h]
0x180012c03  mov     eax, ebx
0x180012c05  add     rsp, 60h
0x180012c09  pop     r14
0x180012c0b  pop     rdi
0x180012c0c  pop     rsi
0x180012c0d  pop     rbp
0x180012c0e  pop     rbx
0x180012c0f  retn
0x180012c11  mov     rax, [rsp+88h+Overlapped.Internal]
0x180012c16  sub     rax, 101h
0x180012c1c  jz      loc_180012CA4
0x180012c22  sub     rax, 4
0x180012c26  jz      short loc_180012C9A
0x180012c28  cmp     rax, 2
0x180012c2c  jz      short loc_180012C90
0x180012c2e  xor     ebx, ebx
0x180012c30  jmp     short loc_180012BF2
0x180012c32  call    cs:__imp_GetLastError
0x180012c39  nop     dword ptr [rax+rax+00h]
0x180012c3e  mov     ebx, eax
0x180012c40  test    eax, eax
0x180012c42  jle     short loc_180012C03
0x180012c44  movzx   ebx, ax
0x180012c47  or      ebx, 80070000h
0x180012c4d  jmp     short loc_180012C03
0x180012c4f  mov     r9d, 1; bWait
0x180012c55  lea     rdx, [rsp+88h+Overlapped]; lpOverlapped
0x180012c5a  mov     r8, rbp; lpNumberOfBytesTransferred
0x180012c5d  mov     rcx, rsi; hFile
0x180012c60  call    cs:__imp_GetOverlappedResult
0x180012c67  nop     dword ptr [rax+rax+00h]
0x180012c6c  test    eax, eax
0x180012c6e  jnz     short loc_180012C2E
0x180012c70  call    cs:__imp_GetLastError
0x180012c77  nop     dword ptr [rax+rax+00h]
0x180012c7c  mov     ebx, eax
0x180012c7e  test    eax, eax
0x180012c80  jle     loc_180012BF2
0x180012c86  movzx   ebx, ax
0x180012c89  or      ebx, edi
0x180012c8b  jmp     loc_180012BF2
0x180012c90  mov     ebx, 80070515h
0x180012c95  jmp     loc_180012BF2
0x180012c9a  mov     ebx, 800700EAh
0x180012c9f  jmp     loc_180012BF2
0x180012ca4  mov     ebx, 80070015h
0x180012ca9  jmp     loc_180012BF2
0x180012cae  mov     ebx, 80070006h
0x180012cb3  jmp     loc_180012C03
```
