# CKsProxy::KsMethod(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x180010840`
- end: `0x1800109cb`
- name: `?KsMethod@CKsProxy@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `395`
- prototype: `__int64 __fastcall(CKsProxy *this, struct KSIDENTIFIER *, DWORD, void *, DWORD nOutBufferSize, unsigned int *lpNumberOfBytesTransferred)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180010840`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800108e1`
- `KERNEL32!GetLastError` at `0x180010945`
- `KERNEL32!GetLastError` at `0x180010983`
- `KERNEL32!GetLastError` at `0x1800108e1`
- `KERNEL32!GetLastError` at `0x180010945`
- `KERNEL32!GetLastError` at `0x180010983`
- `KERNEL32!CreateEventW` at `0x180010882`
- `KERNEL32!CreateEventW` at `0x180010882`
- `KERNEL32!CloseHandle` at `0x18001090a`
- `KERNEL32!CloseHandle` at `0x18001090a`
- `KERNEL32!GetOverlappedResult` at `0x180010973`
- `KERNEL32!GetOverlappedResult` at `0x180010973`
- `KERNEL32!DeviceIoControl` at `0x1800108d1`
- `KERNEL32!DeviceIoControl` at `0x1800108d1`

## pseudocode

```c
__int64 __fastcall CKsProxy::KsMethod(
        CKsProxy *this,
        struct KSIDENTIFIER *a2,
        DWORD a3,
        void *a4,
        DWORD nOutBufferSize,
        unsigned int *lpNumberOfBytesTransferred)
{
  IMediaSeeking_vtbl *v6; // rsi
  signed int LastError; // eax
  unsigned int v11; // ebx
  signed int v13; // eax
  signed int v14; // eax
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-48h] BYREF

  v6 = this->IMediaSeeking::IUnknown::__vftable;
  if ( (unsigned __int64)&v6[-1].GetPreroll + 7 > 0xFFFFFFFFFFFFFFFDuLL )
    return (unsigned int)-2147024890;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(v6, 0x2F000Fu, a2, a3, a4, nOutBufferSize, lpNumberOfBytesTransferred, &Overlapped) )
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
0x180010840  push    rbx
0x180010842  push    rbp
0x180010843  push    rsi
0x180010844  push    rdi
0x180010845  push    r14
0x180010847  sub     rsp, 60h
0x18001084b  mov     rsi, [rcx+0A0h]
0x180010852  mov     rbx, r9
0x180010855  mov     edi, r8d
0x180010858  mov     r14, rdx
0x18001085b  lea     rax, [rsi-1]
0x18001085f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010863  ja      loc_1800109C1
0x180010869  xorps   xmm0, xmm0
0x18001086c  xor     r9d, r9d; lpName
0x18001086f  xor     r8d, r8d; bInitialState
0x180010872  xor     ecx, ecx; lpEventAttributes
0x180010874  movups  xmmword ptr [rsp+88h+Overlapped.Internal], xmm0
0x180010879  lea     edx, [r9+1]; bManualReset
0x18001087d  movups  xmmword ptr [rsp+88h+Overlapped.10h], xmm0
0x180010882  call    cs:__imp_CreateEventW
0x180010889  nop     dword ptr [rax+rax+00h]
0x18001088e  mov     [rsp+88h+Overlapped.hEvent], rax
0x180010893  test    rax, rax
0x180010896  jz      loc_180010945
0x18001089c  mov     rbp, [rsp+88h+lpNumberOfBytesTransferred]
0x1800108a4  lea     rax, [rsp+88h+Overlapped]
0x1800108a9  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x1800108ae  mov     r9d, edi; nInBufferSize
0x1800108b1  mov     eax, [rsp+88h+arg_20]
0x1800108b8  mov     r8, r14; lpInBuffer
0x1800108bb  mov     [rsp+88h+lpBytesReturned], rbp; lpBytesReturned
0x1800108c0  mov     edx, 2F000Fh; dwIoControlCode
0x1800108c5  mov     [rsp+88h+nOutBufferSize], eax; nOutBufferSize
0x1800108c9  mov     rcx, rsi; hDevice
0x1800108cc  mov     [rsp+88h+lpOutBuffer], rbx; lpOutBuffer
0x1800108d1  call    cs:__imp_DeviceIoControl
0x1800108d8  nop     dword ptr [rax+rax+00h]
0x1800108dd  test    eax, eax
0x1800108df  jnz     short loc_180010924
0x1800108e1  call    cs:__imp_GetLastError
0x1800108e8  nop     dword ptr [rax+rax+00h]
0x1800108ed  mov     ebx, eax
0x1800108ef  mov     edi, 80070000h
0x1800108f4  test    eax, eax
0x1800108f6  jle     short loc_1800108FD
0x1800108f8  movzx   ebx, ax
0x1800108fb  or      ebx, edi
0x1800108fd  cmp     ebx, 800703E5h
0x180010903  jz      short loc_180010962
0x180010905  mov     rcx, [rsp+88h+Overlapped.hEvent]; hObject
0x18001090a  call    cs:__imp_CloseHandle
0x180010911  nop     dword ptr [rax+rax+00h]
0x180010916  mov     eax, ebx
0x180010918  add     rsp, 60h
0x18001091c  pop     r14
0x18001091e  pop     rdi
0x18001091f  pop     rsi
0x180010920  pop     rbp
0x180010921  pop     rbx
0x180010922  retn
0x180010924  mov     rax, [rsp+88h+Overlapped.Internal]
0x180010929  sub     rax, 101h
0x18001092f  jz      loc_1800109B7
0x180010935  sub     rax, 4
0x180010939  jz      short loc_1800109AD
0x18001093b  cmp     rax, 2
0x18001093f  jz      short loc_1800109A3
0x180010941  xor     ebx, ebx
0x180010943  jmp     short loc_180010905
0x180010945  call    cs:__imp_GetLastError
0x18001094c  nop     dword ptr [rax+rax+00h]
0x180010951  mov     ebx, eax
0x180010953  test    eax, eax
0x180010955  jle     short loc_180010916
0x180010957  movzx   ebx, ax
0x18001095a  or      ebx, 80070000h
0x180010960  jmp     short loc_180010916
0x180010962  mov     r9d, 1; bWait
0x180010968  lea     rdx, [rsp+88h+Overlapped]; lpOverlapped
0x18001096d  mov     r8, rbp; lpNumberOfBytesTransferred
0x180010970  mov     rcx, rsi; hFile
0x180010973  call    cs:__imp_GetOverlappedResult
0x18001097a  nop     dword ptr [rax+rax+00h]
0x18001097f  test    eax, eax
0x180010981  jnz     short loc_180010941
0x180010983  call    cs:__imp_GetLastError
0x18001098a  nop     dword ptr [rax+rax+00h]
0x18001098f  mov     ebx, eax
0x180010991  test    eax, eax
0x180010993  jle     loc_180010905
0x180010999  movzx   ebx, ax
0x18001099c  or      ebx, edi
0x18001099e  jmp     loc_180010905
0x1800109a3  mov     ebx, 80070515h
0x1800109a8  jmp     loc_180010905
0x1800109ad  mov     ebx, 800700EAh
0x1800109b2  jmp     loc_180010905
0x1800109b7  mov     ebx, 80070015h
0x1800109bc  jmp     loc_180010905
0x1800109c1  mov     ebx, 80070006h
0x1800109c6  jmp     loc_180010916
```
