# Np::SendPacketAsync(SNI_Packet *,ulong *,bool)

- ea: `0x1801609d0`
- end: `0x180160d81`
- name: `?SendPacketAsync@Np@@AEAAKPEAVSNI_Packet@@PEAK_N@Z`
- size: `945`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet *, LPDWORD lpNumberOfBytesTransferred, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180160e80`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003250`
- `0x180003d80`
- `0x18015a6f0`
- `0x18015a880`
- `0x1801609d0`
- `0x18017f0e0`
- `0x18017f1b0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180160a8f`
- `KERNEL32!GetLastError` at `0x180160b90`
- `KERNEL32!GetLastError` at `0x180160a8f`
- `KERNEL32!GetLastError` at `0x180160b90`
- `KERNEL32!GetOverlappedResult` at `0x180160b86`
- `KERNEL32!GetOverlappedResult` at `0x180160b86`
- `KERNEL32!WriteFile` at `0x180160a81`
- `KERNEL32!WriteFile` at `0x180160a81`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Np::SendPacketAsync(
        HANDLE *this,
        struct SNI_Packet *a2,
        LPDWORD lpNumberOfBytesTransferred,
        char a4)
{
  DWORD LastError; // edi
  const void *v9; // rbp
  DWORD v10; // r12d
  struct _OVERLAPPED *lpOverlapped; // r15
  __int64 v13; // [rsp+38h] [rbp-50h] BYREF

  v13 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266930[0] )
    bidScopeEnterW(&v13, off_180266930[0], *((unsigned int *)this + 11), a2);
  LastError = 0;
  v9 = (const void *)(*((_QWORD *)a2 + 9) + *((unsigned int *)a2 + 22));
  v10 = *((_DWORD *)a2 + 20);
  if ( a4 )
  {
    lpOverlapped = (struct _OVERLAPPED *)((char *)a2 + 16);
    SNI::detail::Transport::PrepareForAsyncCall((SNI::detail::Transport *)this, a2);
  }
  else
  {
    lpOverlapped = (struct _OVERLAPPED *)(this + 11);
  }
  lpOverlapped->Pointer = 0;
  if ( !WriteFile(this[8], v9, v10, 0, lpOverlapped) )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180264330[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(off_180260FE8[0], 1119232, off_180264330[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
      if ( (bidGblFlags & 0x24002) == 0x24002 && off_180264338[0] )
        bidTraceW(off_180260FF0[0], 1122304, off_180264338[0], v10);
      if ( (bidGblFlags & 0x24002) == 0x24002 )
        bidWriteBin(bidID, 16, v9, v10, 0);
      goto LABEL_39;
    }
    goto LABEL_34;
  }
  if ( !SNI::detail::Transport::FWillSkipCompletionPortOnSuccess((SNI::detail::Transport *)this) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264350[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        off_180261008[0],
        1144832,
        off_180264350[0],
        0);
    LastError = 997;
    goto LABEL_34;
  }
  if ( !GetOverlappedResult(this[8], lpOverlapped, lpNumberOfBytesTransferred, 0) )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_180264340[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(off_180260FF8[0], 1134592, off_180264340[0], *((unsigned int *)this + 18));
    }
    SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
    if ( LastError != 997 )
      goto LABEL_39;
LABEL_34:
    if ( !a4 )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && `SNIPacketAddRef'::`7'::_bidPtrSA_030_616[0] )
        bidTraceW(
          `SNIPacketAddRef'::`7'::_bidSrcFileA[0],
          630784,
          `SNIPacketAddRef'::`7'::_bidPtrSA_030_616[0],
          *((unsigned int *)a2 + 37));
      _InterlockedIncrement((volatile signed __int32 *)a2 + 23);
      this[15] = a2;
    }
    goto LABEL_39;
  }
  if ( (bidGblFlags & 0x24002) == 0x24002 && off_180264348[0] )
    bidTraceW(off_180261000[0], 1138688, off_180264348[0], *lpNumberOfBytesTransferred);
  if ( (bidGblFlags & 0x24002) == 0x24002 )
    bidWriteBin(bidID, 16, v9, *lpNumberOfBytesTransferred, 0);
LABEL_39:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264358[0] )
    bidTraceW(off_180261010[0], 1167360, off_180264358[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v13);
  return LastError;
}

```

## disassembly

```asm
0x1801609d0  mov     [rsp+arg_18], rbx
0x1801609d5  push    rbp
0x1801609d6  push    rsi
0x1801609d7  push    rdi
0x1801609d8  push    r12
0x1801609da  push    r13
0x1801609dc  push    r14
0x1801609de  push    r15
0x1801609e0  sub     rsp, 50h
0x1801609e4  mov     rax, cs:__security_cookie
0x1801609eb  xor     rax, rsp
0x1801609ee  mov     [rsp+88h+var_48], rax
0x1801609f3  movzx   r13d, r9b
0x1801609f7  mov     r14, r8
0x1801609fa  mov     rbx, rdx
0x1801609fd  mov     rsi, rcx
0x180160a00  mov     [rsp+88h+var_50], 0FFFFFFFFFFFFFFFFh
0x180160a09  mov     eax, cs:_bidGblFlags
0x180160a0f  and     eax, 20004h
0x180160a14  cmp     eax, 20004h
0x180160a19  jnz     short loc_180160A44
0x180160a1b  mov     rax, cs:off_180266930; "<Np::SendPacketAsync|API|SNI> %u#, pPac"...
0x180160a22  test    rax, rax
0x180160a25  jz      short loc_180160A44
0x180160a27  mov     [rsp+88h+lpOverlapped], r8
0x180160a2c  mov     r9, rdx
0x180160a2f  mov     r8d, [rcx+2Ch]
0x180160a33  mov     rdx, cs:off_180266930; "<Np::SendPacketAsync|API|SNI> %u#, pPac"...
0x180160a3a  lea     rcx, [rsp+88h+var_50]
0x180160a3f  call    _bidScopeEnterW
0x180160a44  xor     edi, edi
0x180160a46  mov     ebp, [rbx+58h]
0x180160a49  add     rbp, [rbx+48h]
0x180160a4d  mov     r12d, [rbx+50h]
0x180160a51  test    r13b, r13b
0x180160a54  jz      short loc_180160A67
0x180160a56  lea     r15, [rbx+10h]
0x180160a5a  mov     rdx, rbx; struct SNI_Packet *
0x180160a5d  mov     rcx, rsi; this
0x180160a60  call    ?PrepareForAsyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForAsyncCall(SNI_Packet *)
0x180160a65  jmp     short loc_180160A6B
0x180160a67  lea     r15, [rsi+58h]
0x180160a6b  mov     [r15+10h], rdi
0x180160a6f  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x180160a74  xor     r9d, r9d; lpNumberOfBytesWritten
0x180160a77  mov     r8d, r12d; nNumberOfBytesToWrite
0x180160a7a  mov     rdx, rbp; lpBuffer
0x180160a7d  mov     rcx, [rsi+40h]; hFile
0x180160a81  call    cs:__imp_WriteFile
0x180160a87  test    eax, eax
0x180160a89  jnz     loc_180160B69
0x180160a8f  call    cs:__imp_GetLastError
0x180160a95  mov     edi, eax
0x180160a97  cmp     eax, 3E5h
0x180160a9c  jz      loc_180160CC6
0x180160aa2  test    byte ptr cs:_bidGblFlags, 2
0x180160aa9  jz      short loc_180160AE5
0x180160aab  mov     rcx, cs:off_180264330; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x180160ab2  test    rcx, rcx
0x180160ab5  jz      short loc_180160AE5
0x180160ab7  mov     ecx, 0C3B4h; unsigned int
0x180160abc  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180160ac1  mov     [rsp+88h+var_60], edi
0x180160ac5  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x180160ac9  mov     r9d, [rsi+48h]
0x180160acd  mov     r8, cs:off_180264330; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x180160ad4  mov     edx, 111400h
0x180160ad9  mov     rcx, cs:off_180260FE8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160ae0  call    _bidTraceW
0x180160ae5  mov     r8d, 0C3B4h
0x180160aeb  mov     edx, edi
0x180160aed  mov     ecx, [rsi+48h]
0x180160af0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180160af5  mov     eax, cs:_bidGblFlags
0x180160afb  and     eax, 24002h
0x180160b00  cmp     eax, 24002h
0x180160b05  jnz     short loc_180160B2E
0x180160b07  mov     rax, cs:off_180264338; "<Np::SendPacketAsync|ERR|SNI> Send Pack"...
0x180160b0e  test    rax, rax
0x180160b11  jz      short loc_180160B2E
0x180160b13  mov     r9d, r12d
0x180160b16  mov     r8, cs:off_180264338; "<Np::SendPacketAsync|ERR|SNI> Send Pack"...
0x180160b1d  mov     edx, 112000h
0x180160b22  mov     rcx, cs:off_180260FF0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160b29  call    _bidTraceW
0x180160b2e  mov     eax, cs:_bidGblFlags
0x180160b34  and     eax, 24002h
0x180160b39  cmp     eax, 24002h
0x180160b3e  jnz     loc_180160D15
0x180160b44  mov     [rsp+88h+lpOverlapped], 0
0x180160b4d  mov     r9d, r12d
0x180160b50  mov     r8, rbp
0x180160b53  mov     edx, 10h
0x180160b58  mov     rcx, cs:_bidID
0x180160b5f  call    _bidWriteBin
0x180160b64  jmp     loc_180160D15
0x180160b69  mov     rcx, rsi; this
0x180160b6c  call    ?FWillSkipCompletionPortOnSuccess@Transport@detail@SNI@@IEBA_NXZ; SNI::detail::Transport::FWillSkipCompletionPortOnSuccess(void)
0x180160b71  test    al, al
0x180160b73  jz      loc_180160C6C
0x180160b79  xor     r9d, r9d; bWait
0x180160b7c  mov     r8, r14; lpNumberOfBytesTransferred
0x180160b7f  mov     rdx, r15; lpOverlapped
0x180160b82  mov     rcx, [rsi+40h]; hFile
0x180160b86  call    cs:__imp_GetOverlappedResult
0x180160b8c  test    eax, eax
0x180160b8e  jnz     short loc_180160BFC
0x180160b90  call    cs:__imp_GetLastError
0x180160b96  mov     edi, eax
0x180160b98  test    byte ptr cs:_bidGblFlags, 2
0x180160b9f  jz      short loc_180160BDB
0x180160ba1  mov     rax, cs:off_180264340; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x180160ba8  test    rax, rax
0x180160bab  jz      short loc_180160BDB
0x180160bad  mov     ecx, 0C3B4h; unsigned int
0x180160bb2  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180160bb7  mov     [rsp+88h+var_60], edi
0x180160bbb  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x180160bbf  mov     r9d, [rsi+48h]
0x180160bc3  mov     r8, cs:off_180264340; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x180160bca  mov     edx, 115000h
0x180160bcf  mov     rcx, cs:off_180260FF8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160bd6  call    _bidTraceW
0x180160bdb  mov     r8d, 0C3B4h
0x180160be1  mov     edx, edi
0x180160be3  mov     ecx, [rsi+48h]
0x180160be6  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180160beb  cmp     edi, 3E5h
0x180160bf1  jz      loc_180160CC6
0x180160bf7  jmp     loc_180160D15
0x180160bfc  mov     eax, cs:_bidGblFlags
0x180160c02  and     eax, 24002h
0x180160c07  cmp     eax, 24002h
0x180160c0c  jnz     short loc_180160C35
0x180160c0e  mov     rax, cs:off_180264348; "<Np::SendPacketAsync|SNI> Send Packet, "...
0x180160c15  test    rax, rax
0x180160c18  jz      short loc_180160C35
0x180160c1a  mov     r9d, [r14]
0x180160c1d  mov     r8, cs:off_180264348; "<Np::SendPacketAsync|SNI> Send Packet, "...
0x180160c24  mov     edx, 116000h
0x180160c29  mov     rcx, cs:off_180261000; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160c30  call    _bidTraceW
0x180160c35  mov     eax, cs:_bidGblFlags
0x180160c3b  and     eax, 24002h
0x180160c40  cmp     eax, 24002h
0x180160c45  jnz     loc_180160D15
0x180160c4b  mov     [rsp+88h+lpOverlapped], rdi
0x180160c50  mov     r9d, [r14]
0x180160c53  mov     r8, rbp
0x180160c56  mov     edx, 10h
0x180160c5b  mov     rcx, cs:_bidID
0x180160c62  call    _bidWriteBin
0x180160c67  jmp     loc_180160D15
0x180160c6c  mov     eax, cs:_bidGblFlags
0x180160c72  and     eax, 20002h
0x180160c77  cmp     eax, 20002h
0x180160c7c  jnz     short loc_180160CC1
0x180160c7e  mov     rax, cs:off_180264350; "<Np::SendPacketAsync|SNI> Suppressing s"...
0x180160c85  test    rax, rax
0x180160c88  jz      short loc_180160CC1
0x180160c8a  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180160c92  jz      short loc_180160CC1
0x180160c94  mov     rax, cs:off_180248050
0x180160c9b  mov     [rsp+88h+lpOverlapped], rdi
0x180160ca0  mov     r9, cs:off_180264350; "<Np::SendPacketAsync|SNI> Suppressing s"...
0x180160ca7  mov     r8d, 117800h
0x180160cad  mov     rdx, cs:off_180261008; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160cb4  mov     rcx, cs:_bidID
0x180160cbb  call    cs:__guard_dispatch_icall_fptr
0x180160cc1  mov     edi, 3E5h
0x180160cc6  test    r13b, r13b
0x180160cc9  jnz     short loc_180160D15
0x180160ccb  mov     eax, cs:_bidGblFlags
0x180160cd1  and     eax, 20002h
0x180160cd6  cmp     eax, 20002h
0x180160cdb  jnz     short loc_180160D0D
0x180160cdd  mov     rax, cs:?_bidPtrSA_030_616@?6??SNIPacketAddRef@@9@4REB_WEB; wchar_t const * const `SNIPacketAddRef'::`7'::_bidPtrSA_030_616
0x180160ce4  test    rax, rax
0x180160ce7  jz      short loc_180160D0D
0x180160ce9  mov     [rsp+88h+lpOverlapped], rbx
0x180160cee  mov     r9d, [rbx+94h]
0x180160cf5  mov     r8, cs:?_bidPtrSA_030_616@?6??SNIPacketAddRef@@9@4REB_WEB; wchar_t const * const `SNIPacketAddRef'::`7'::_bidPtrSA_030_616
0x180160cfc  mov     edx, 9A000h
0x180160d01  mov     rcx, cs:?_bidSrcFileA@?6??SNIPacketAddRef@@9@4REBDEB; char const * const `SNIPacketAddRef'::`7'::_bidSrcFileA
0x180160d08  call    _bidTraceW
0x180160d0d  lock inc dword ptr [rbx+5Ch]
0x180160d11  mov     [rsi+78h], rbx
0x180160d15  mov     eax, cs:_bidGblFlags
0x180160d1b  and     eax, 20002h
0x180160d20  cmp     eax, 20002h
0x180160d25  jnz     short loc_180160D4F
0x180160d27  mov     rax, cs:off_180264358; "<Np::SendPacketAsync|RET|SNI> %d{WINERR"...
0x180160d2e  test    rax, rax
0x180160d31  jz      short loc_180160D4F
0x180160d33  mov     r9d, edi
0x180160d36  mov     r8, cs:off_180264358; "<Np::SendPacketAsync|RET|SNI> %d{WINERR"...
0x180160d3d  mov     edx, 11D000h
0x180160d42  mov     rcx, cs:off_180261010; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160d49  call    _bidTraceW
0x180160d4e  nop
0x180160d4f  lea     rcx, [rsp+88h+var_50]; this
0x180160d54  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180160d59  nop
0x180160d5a  mov     eax, edi
0x180160d5c  mov     rcx, [rsp+88h+var_48]
0x180160d61  xor     rcx, rsp; StackCookie
0x180160d64  call    __security_check_cookie
0x180160d69  mov     rbx, [rsp+88h+arg_18]
0x180160d71  add     rsp, 50h
0x180160d75  pop     r15
0x180160d77  pop     r14
0x180160d79  pop     r13
0x180160d7b  pop     r12
0x180160d7d  pop     rdi
0x180160d7e  pop     rsi
0x180160d7f  pop     rbp
0x180160d80  retn
```
