# CKsProxy::KsProperty(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x180007370`
- end: `0x1800075a9`
- name: `?KsProperty@CKsProxy@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `569`
- prototype: `int __fastcall(CKsProxy *this, struct KSIDENTIFIER *, DWORD, void *, DWORD nOutBufferSize, unsigned int *lpNumberOfBytesTransferred)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180007370`
- `0x1800081e4`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007446`
- `KERNEL32!GetLastError` at `0x1800074f6`
- `KERNEL32!GetLastError` at `0x18000753d`
- `KERNEL32!GetLastError` at `0x180007446`
- `KERNEL32!GetLastError` at `0x1800074f6`
- `KERNEL32!GetLastError` at `0x18000753d`
- `KERNEL32!CreateEventW` at `0x1800073df`
- `KERNEL32!CreateEventW` at `0x1800073df`
- `KERNEL32!CloseHandle` at `0x180007472`
- `KERNEL32!CloseHandle` at `0x180007472`
- `KERNEL32!GetOverlappedResult` at `0x180007529`
- `KERNEL32!GetOverlappedResult` at `0x180007529`
- `KERNEL32!DeviceIoControl` at `0x180007436`
- `KERNEL32!DeviceIoControl` at `0x180007436`

## pseudocode

```c
int __fastcall CKsProxy::KsProperty(
        CKsProxy *this,
        struct KSIDENTIFIER *a2,
        DWORD a3,
        void *a4,
        DWORD nOutBufferSize,
        unsigned int *lpNumberOfBytesTransferred)
{
  _QWORD *v6; // rax
  IMediaSeeking_vtbl *v11; // rdi
  signed int LastError; // eax
  unsigned int v13; // ebx
  int result; // eax
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  signed int v18; // eax
  int lpOutBuffer; // [rsp+20h] [rbp-68h]
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v6 = *(_QWORD **)&this->m_IoThreadCriticalSection.LockCount;
  if ( v6 )
  {
    if ( !a2 )
    {
      v16 = 2147942487LL;
      v17 = 42;
      goto LABEL_19;
    }
    if ( !*v6 )
    {
      v16 = 2147483662LL;
      v17 = 43;
      goto LABEL_19;
    }
    if ( (a2->Flags & 2) != 0 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, struct KSIDENTIFIER *, __int64))(*(_QWORD *)*v6 + 104LL))(*v6, a2, 24);
      if ( v15 < 0 )
      {
        v16 = (unsigned int)v15;
        v17 = 47;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\kscontrolwnfnotify.cpp",
          (const char *)v16,
          lpOutBuffer);
      }
    }
  }
  v11 = this->IMediaSeeking::IUnknown::__vftable;
  if ( (unsigned __int64)&v11[-1].GetPreroll + 7 > 0xFFFFFFFFFFFFFFFDuLL )
    return -2147024890;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(v11, 0x2F0003u, a2, a3, a4, nOutBufferSize, lpNumberOfBytesTransferred, &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101uLL:
          v13 = -2147024875;
          goto LABEL_11;
        case 0x105uLL:
          v13 = -2147024662;
          goto LABEL_11;
        case 0x107uLL:
          v13 = -2147023595;
          goto LABEL_11;
      }
    }
    else
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( v13 != -2147023899 )
        goto LABEL_11;
      if ( !GetOverlappedResult(v11, &Overlapped, lpNumberOfBytesTransferred, 1) )
      {
        v18 = GetLastError();
        v13 = v18;
        if ( v18 > 0 )
          v13 = (unsigned __int16)v18 | 0x80070000;
        goto LABEL_11;
      }
    }
    v13 = 0;
LABEL_11:
    CloseHandle(Overlapped.hEvent);
    return v13;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007370  push    rbx
0x180007372  push    rbp
0x180007373  push    rsi
0x180007374  push    rdi
0x180007375  sub     rsp, 68h
0x180007379  mov     rax, [rcx+1A0h]
0x180007380  mov     rsi, r9
0x180007383  mov     ebp, r8d
0x180007386  mov     rbx, rdx
0x180007389  mov     rdi, rcx
0x18000738c  test    rax, rax
0x18000738f  jz      short loc_1800073B0
0x180007391  test    rdx, rdx
0x180007394  jz      loc_180007561
0x18000739a  mov     rcx, [rax]
0x18000739d  test    rcx, rcx
0x1800073a0  jz      loc_180007571
0x1800073a6  test    byte ptr [rdx+14h], 2
0x1800073aa  jnz     loc_1800074BB
0x1800073b0  mov     rdi, [rdi+0A0h]
0x1800073b7  lea     rax, [rdi-1]
0x1800073bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800073bf  ja      loc_18000759F
0x1800073c5  xorps   xmm0, xmm0
0x1800073c8  xor     r9d, r9d; lpName
0x1800073cb  xor     r8d, r8d; bInitialState
0x1800073ce  mov     edx, 1; bManualReset
0x1800073d3  xor     ecx, ecx; lpEventAttributes
0x1800073d5  movups  xmmword ptr [rsp+88h+Overlapped.Internal], xmm0
0x1800073da  movups  xmmword ptr [rsp+88h+Overlapped.10h], xmm0
0x1800073df  call    cs:__imp_CreateEventW
0x1800073e6  nop     dword ptr [rax+rax+00h]
0x1800073eb  mov     [rsp+88h+Overlapped.hEvent], rax
0x1800073f0  test    rax, rax
0x1800073f3  jz      loc_1800074F6
0x1800073f9  lea     rax, [rsp+88h+Overlapped]
0x1800073fe  mov     [rsp+88h+arg_0], r14
0x180007406  mov     r14, [rsp+88h+lpNumberOfBytesTransferred]
0x18000740e  mov     r9d, ebp; nInBufferSize
0x180007411  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x180007416  mov     r8, rbx; lpInBuffer
0x180007419  mov     eax, [rsp+88h+arg_20]
0x180007420  mov     edx, 2F0003h; dwIoControlCode
0x180007425  mov     [rsp+88h+lpBytesReturned], r14; lpBytesReturned
0x18000742a  mov     rcx, rdi; hDevice
0x18000742d  mov     [rsp+88h+nOutBufferSize], eax; nOutBufferSize
0x180007431  mov     [rsp+88h+lpOutBuffer], rsi; lpOutBuffer
0x180007436  call    cs:__imp_DeviceIoControl
0x18000743d  nop     dword ptr [rax+rax+00h]
0x180007442  test    eax, eax
0x180007444  jnz     short loc_180007492
0x180007446  call    cs:__imp_GetLastError
0x18000744d  nop     dword ptr [rax+rax+00h]
0x180007452  mov     ebx, eax
0x180007454  test    eax, eax
0x180007456  jle     short loc_180007461
0x180007458  movzx   ebx, ax
0x18000745b  or      ebx, 80070000h
0x180007461  cmp     ebx, 800703E5h
0x180007467  jz      loc_180007518
0x18000746d  mov     rcx, [rsp+88h+Overlapped.hEvent]; hObject
0x180007472  call    cs:__imp_CloseHandle
0x180007479  nop     dword ptr [rax+rax+00h]
0x18000747e  mov     r14, [rsp+88h+arg_0]
0x180007486  mov     eax, ebx
0x180007488  add     rsp, 68h
0x18000748c  pop     rdi
0x18000748d  pop     rsi
0x18000748e  pop     rbp
0x18000748f  pop     rbx
0x180007490  retn
0x180007492  mov     rax, [rsp+88h+Overlapped.Internal]
0x180007497  sub     rax, 101h
0x18000749d  jz      loc_180007595
0x1800074a3  sub     rax, 4
0x1800074a7  jz      loc_18000758B
0x1800074ad  cmp     rax, 2
0x1800074b1  jz      loc_180007581
0x1800074b7  xor     ebx, ebx
0x1800074b9  jmp     short loc_18000746D
0x1800074bb  mov     rax, [rcx]
0x1800074be  mov     r8d, 18h
0x1800074c4  mov     rax, [rax+68h]
0x1800074c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074cd  test    eax, eax
0x1800074cf  jns     loc_1800073B0
0x1800074d5  mov     r9d, eax; char *
0x1800074d8  mov     edx, 2Fh ; '/'; void *
0x1800074dd  mov     rcx, [rsp+88h]; this
0x1800074e5  lea     r8, aMultimediaDsho_1; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1800074ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074f1  jmp     loc_1800073B0
0x1800074f6  call    cs:__imp_GetLastError
0x1800074fd  nop     dword ptr [rax+rax+00h]
0x180007502  test    eax, eax
0x180007504  jle     short loc_180007488
0x180007506  movzx   eax, ax
0x180007509  or      eax, 80070000h
0x18000750e  add     rsp, 68h
0x180007512  pop     rdi
0x180007513  pop     rsi
0x180007514  pop     rbp
0x180007515  pop     rbx
0x180007516  retn
0x180007518  mov     r9d, 1; bWait
0x18000751e  lea     rdx, [rsp+88h+Overlapped]; lpOverlapped
0x180007523  mov     r8, r14; lpNumberOfBytesTransferred
0x180007526  mov     rcx, rdi; hFile
0x180007529  call    cs:__imp_GetOverlappedResult
0x180007530  nop     dword ptr [rax+rax+00h]
0x180007535  test    eax, eax
0x180007537  jnz     loc_1800074B7
0x18000753d  call    cs:__imp_GetLastError
0x180007544  nop     dword ptr [rax+rax+00h]
0x180007549  mov     ebx, eax
0x18000754b  test    eax, eax
0x18000754d  jle     loc_18000746D
0x180007553  movzx   ebx, ax
0x180007556  or      ebx, 80070000h
0x18000755c  jmp     loc_18000746D
0x180007561  mov     r9d, 80070057h
0x180007567  mov     edx, 2Ah ; '*'
0x18000756c  jmp     loc_1800074DD
0x180007571  mov     r9d, 8000000Eh
0x180007577  mov     edx, 2Bh ; '+'
0x18000757c  jmp     loc_1800074DD
0x180007581  mov     ebx, 80070515h
0x180007586  jmp     loc_18000746D
0x18000758b  mov     ebx, 800700EAh
0x180007590  jmp     loc_18000746D
0x180007595  mov     ebx, 80070015h
0x18000759a  jmp     loc_18000746D
0x18000759f  mov     eax, 80070006h
0x1800075a4  jmp     loc_180007488
```
