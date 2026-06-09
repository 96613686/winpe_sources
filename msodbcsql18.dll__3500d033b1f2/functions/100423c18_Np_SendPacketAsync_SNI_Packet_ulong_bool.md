# Np::SendPacketAsync(SNI_Packet *,ulong *,bool)

- ea: `0x100423c18`
- end: `0x100423f67`
- name: `?SendPacketAsync@Np@@AEAAKPEAVSNI_Packet@@PEAK_N@Z`
- size: `847`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet *, LPDWORD lpNumberOfBytesTransferred, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100424040`

## callees

- `0x100423c18`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043b1c4`
- `0x10043b1f8`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100546b88`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x100423d9a`
- `KERNEL32!GetOverlappedResult` at `0x100423d9a`
- `KERNEL32!GetLastError` at `0x100423ccc`
- `KERNEL32!GetLastError` at `0x100423da8`
- `KERNEL32!GetLastError` at `0x100423ccc`
- `KERNEL32!GetLastError` at `0x100423da8`
- `KERNEL32!WriteFile` at `0x100423cbe`
- `KERNEL32!WriteFile` at `0x100423cbe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::SendPacketAsync(
        HANDLE *this,
        struct SNI_Packet *a2,
        LPDWORD lpNumberOfBytesTransferred,
        char a4)
{
  DWORD LastError; // edi
  const void *v9; // r14
  DWORD v10; // r12d
  struct _OVERLAPPED *lpOverlapped; // rbp
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF

  v13 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7A40[0] )
    bidScopeEnterW(&v13, off_1005E7A40[0], *((unsigned int *)this + 11));
  LastError = 0;
  v9 = (const void *)(*((_QWORD *)a2 + 10) + *((unsigned int *)a2 + 24));
  v10 = *((_DWORD *)a2 + 22);
  if ( a4 )
  {
    lpOverlapped = (struct _OVERLAPPED *)a2;
    SNI::detail::Transport::PrepareForAsyncCall((SNI::detail::Transport *)this, a2);
  }
  else
  {
    lpOverlapped = (struct _OVERLAPPED *)(this + 11);
  }
  lpOverlapped->Offset = 0;
  lpOverlapped->OffsetHigh = 0;
  if ( !WriteFile(this[8], v9, v10, 0, lpOverlapped) )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E4E98[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 1125376, off_1005E4E98[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
      if ( (bidGblFlags & 0x24002) == 0x24002 && off_1005E4EA0[0] )
        bidTraceW(0, 1128448, off_1005E4EA0[0], v10);
      if ( (bidGblFlags & 0x24002) == 0x24002 )
        bidWriteBin(bidID, 16, v9, v10, 0);
      goto LABEL_28;
    }
    goto LABEL_23;
  }
  if ( !SNI::detail::Transport::FWillSkipCompletionPortOnSuccess((SNI::detail::Transport *)this) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4EB8[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        1150976,
        off_1005E4EB8[0],
        0);
    LastError = 997;
    goto LABEL_23;
  }
  if ( GetOverlappedResult(this[8], lpOverlapped, lpNumberOfBytesTransferred, 0) )
  {
    if ( (bidGblFlags & 0x24002) == 0x24002 && off_1005E4EB0[0] )
      bidTraceW(0, 1144832, off_1005E4EB0[0], *lpNumberOfBytesTransferred);
    if ( (bidGblFlags & 0x24002) == 0x24002 )
      bidWriteBin(bidID, 16, v9, *lpNumberOfBytesTransferred, 0);
  }
  else
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E4EA8[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 1140736, off_1005E4EA8[0], *((unsigned int *)this + 18));
    }
    SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
    if ( LastError == 997 )
    {
LABEL_23:
      if ( !a4 )
      {
        if ( (bidGblFlags & 0x20002) == 0x20002 && `SNIPacketAddRef'::`7'::_bidPtrSA_030_625[0] )
          bidTraceW(0, 640000, `SNIPacketAddRef'::`7'::_bidPtrSA_030_625[0], *((unsigned int *)a2 + 39));
        _InterlockedIncrement((volatile signed __int32 *)a2 + 25);
        this[15] = a2;
      }
    }
  }
LABEL_28:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4EC0[0] )
    bidTraceW(0, 1173504, off_1005E4EC0[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v13);
  return LastError;
}

```

## disassembly

```asm
0x100423c18  mov     r11, rsp
0x100423c1b  push    rbp
0x100423c1c  push    rsi
0x100423c1d  push    rdi
0x100423c1e  push    r12
0x100423c20  push    r13
0x100423c22  push    r14
0x100423c24  push    r15
0x100423c26  sub     rsp, 40h
0x100423c2a  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x100423c32  mov     [r11+10h], rbx
0x100423c36  mov     r13b, r9b
0x100423c39  mov     r15, r8
0x100423c3c  mov     rbx, rdx
0x100423c3f  mov     rsi, rcx
0x100423c42  or      qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x100423c47  mov     eax, cs:_bidGblFlags
0x100423c4d  mov     ecx, 20004h
0x100423c52  and     eax, ecx
0x100423c54  cmp     eax, ecx
0x100423c56  jnz     short loc_100423C7F
0x100423c58  mov     rax, cs:off_1005E7A40; "<Np::SendPacketAsync|API|SNI> %u#, pPac"...
0x100423c5f  test    rax, rax
0x100423c62  jz      short loc_100423C7F
0x100423c64  mov     [r11-58h], r8
0x100423c68  mov     r9, rdx
0x100423c6b  mov     r8d, [rsi+2Ch]
0x100423c6f  mov     rdx, cs:off_1005E7A40; "<Np::SendPacketAsync|API|SNI> %u#, pPac"...
0x100423c76  lea     rcx, [r11+8]
0x100423c7a  call    _bidScopeEnterW
0x100423c7f  xor     edi, edi
0x100423c81  mov     r14d, [rbx+60h]
0x100423c85  add     r14, [rbx+50h]
0x100423c89  mov     r12d, [rbx+58h]
0x100423c8d  test    r13b, r13b
0x100423c90  jz      short loc_100423CA2
0x100423c92  mov     rbp, rbx
0x100423c95  mov     rdx, rbx; struct SNI_Packet *
0x100423c98  mov     rcx, rsi; this
0x100423c9b  call    ?PrepareForAsyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForAsyncCall(SNI_Packet *)
0x100423ca0  jmp     short loc_100423CA6
0x100423ca2  lea     rbp, [rsi+58h]
0x100423ca6  and     [rbp+10h], edi
0x100423ca9  and     [rbp+14h], edi
0x100423cac  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x100423cb1  xor     r9d, r9d; lpNumberOfBytesWritten
0x100423cb4  mov     r8d, r12d; nNumberOfBytesToWrite
0x100423cb7  mov     rdx, r14; lpBuffer
0x100423cba  mov     rcx, [rsi+40h]; hFile
0x100423cbe  call    cs:__imp_WriteFile
0x100423cc4  test    eax, eax
0x100423cc6  jnz     loc_100423D7D
0x100423ccc  call    cs:__imp_GetLastError
0x100423cd2  mov     edi, eax
0x100423cd4  cmp     eax, 3E5h
0x100423cd9  jz      loc_100423E05
0x100423cdf  mov     ebp, 0C3B4h
0x100423ce4  test    byte ptr cs:_bidGblFlags, 2
0x100423ceb  jz      short loc_100423D1F
0x100423ced  mov     rcx, cs:off_1005E4E98; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x100423cf4  test    rcx, rcx
0x100423cf7  jz      short loc_100423D1F
0x100423cf9  mov     ecx, ebp; unsigned int
0x100423cfb  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100423d00  mov     [rsp+78h+var_50], edi
0x100423d04  mov     dword ptr [rsp+78h+lpOverlapped], eax
0x100423d08  mov     r9d, [rsi+48h]
0x100423d0c  mov     r8, cs:off_1005E4E98; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x100423d13  mov     edx, 112C00h
0x100423d18  xor     ecx, ecx
0x100423d1a  call    _bidTraceW
0x100423d1f  mov     r8d, ebp
0x100423d22  mov     edx, edi
0x100423d24  mov     ecx, [rsi+48h]
0x100423d27  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100423d2c  mov     eax, cs:_bidGblFlags
0x100423d32  mov     ebx, 24002h
0x100423d37  and     eax, ebx
0x100423d39  cmp     eax, ebx
0x100423d3b  jnz     short loc_100423D5F
0x100423d3d  mov     rax, cs:off_1005E4EA0; "<Np::SendPacketAsync|ERR|SNI> Send Pack"...
0x100423d44  test    rax, rax
0x100423d47  jz      short loc_100423D5F
0x100423d49  mov     r9d, r12d
0x100423d4c  mov     r8, cs:off_1005E4EA0; "<Np::SendPacketAsync|ERR|SNI> Send Pack"...
0x100423d53  mov     edx, 113800h
0x100423d58  xor     ecx, ecx
0x100423d5a  call    _bidTraceW
0x100423d5f  mov     eax, cs:_bidGblFlags
0x100423d65  and     eax, ebx
0x100423d67  cmp     eax, ebx
0x100423d69  jnz     loc_100423E4E
0x100423d6f  and     [rsp+78h+lpOverlapped], 0
0x100423d75  mov     r9d, r12d
0x100423d78  jmp     loc_100423EF4
0x100423d7d  mov     rcx, rsi; this
0x100423d80  call    ?FWillSkipCompletionPortOnSuccess@Transport@detail@SNI@@IEBA_NXZ; SNI::detail::Transport::FWillSkipCompletionPortOnSuccess(void)
0x100423d85  test    al, al
0x100423d87  jz      loc_100423F0D
0x100423d8d  xor     r9d, r9d; bWait
0x100423d90  mov     r8, r15; lpNumberOfBytesTransferred
0x100423d93  mov     rdx, rbp; lpOverlapped
0x100423d96  mov     rcx, [rsi+40h]; hFile
0x100423d9a  call    cs:__imp_GetOverlappedResult
0x100423da0  test    eax, eax
0x100423da2  jnz     loc_100423EA9
0x100423da8  call    cs:__imp_GetLastError
0x100423dae  mov     edi, eax
0x100423db0  mov     ebp, 0C3B4h
0x100423db5  test    byte ptr cs:_bidGblFlags, 2
0x100423dbc  jz      short loc_100423DF0
0x100423dbe  mov     rax, cs:off_1005E4EA8; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x100423dc5  test    rax, rax
0x100423dc8  jz      short loc_100423DF0
0x100423dca  mov     ecx, ebp; unsigned int
0x100423dcc  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100423dd1  mov     [rsp+78h+var_50], edi
0x100423dd5  mov     dword ptr [rsp+78h+lpOverlapped], eax
0x100423dd9  mov     r9d, [rsi+48h]
0x100423ddd  mov     r8, cs:off_1005E4EA8; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x100423de4  mov     edx, 116800h
0x100423de9  xor     ecx, ecx
0x100423deb  call    _bidTraceW
0x100423df0  mov     r8d, ebp
0x100423df3  mov     edx, edi
0x100423df5  mov     ecx, [rsi+48h]
0x100423df8  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100423dfd  cmp     edi, 3E5h
0x100423e03  jnz     short loc_100423E4E
0x100423e05  mov     ebp, 20002h
0x100423e0a  test    r13b, r13b
0x100423e0d  jnz     short loc_100423E4E
0x100423e0f  mov     eax, cs:_bidGblFlags
0x100423e15  and     eax, ebp
0x100423e17  cmp     eax, ebp
0x100423e19  jnz     short loc_100423E46
0x100423e1b  mov     rax, cs:?_bidPtrSA_030_625@?6??SNIPacketAddRef@@9@4REBGEB; ushort const * const `SNIPacketAddRef'::`7'::_bidPtrSA_030_625
0x100423e22  test    rax, rax
0x100423e25  jz      short loc_100423E46
0x100423e27  mov     [rsp+78h+lpOverlapped], rbx
0x100423e2c  mov     r9d, [rbx+9Ch]
0x100423e33  mov     r8, cs:?_bidPtrSA_030_625@?6??SNIPacketAddRef@@9@4REBGEB; ushort const * const `SNIPacketAddRef'::`7'::_bidPtrSA_030_625
0x100423e3a  mov     edx, 9C400h
0x100423e3f  xor     ecx, ecx
0x100423e41  call    _bidTraceW
0x100423e46  lock inc dword ptr [rbx+64h]
0x100423e4a  mov     [rsi+78h], rbx
0x100423e4e  mov     eax, cs:_bidGblFlags
0x100423e54  mov     ecx, 20002h
0x100423e59  and     eax, ecx
0x100423e5b  cmp     eax, ecx
0x100423e5d  jnz     short loc_100423E82
0x100423e5f  mov     rax, cs:off_1005E4EC0; "<Np::SendPacketAsync|RET|SNI> %d{WINERR"...
0x100423e66  test    rax, rax
0x100423e69  jz      short loc_100423E82
0x100423e6b  mov     r9d, edi
0x100423e6e  mov     r8, cs:off_1005E4EC0; "<Np::SendPacketAsync|RET|SNI> %d{WINERR"...
0x100423e75  mov     edx, 11E800h
0x100423e7a  xor     ecx, ecx
0x100423e7c  call    _bidTraceW
0x100423e81  nop
0x100423e82  lea     rcx, [rsp+78h+arg_0]; this
0x100423e8a  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100423e8f  mov     eax, edi
0x100423e91  mov     rbx, [rsp+78h+arg_8]
0x100423e99  add     rsp, 40h
0x100423e9d  pop     r15
0x100423e9f  pop     r14
0x100423ea1  pop     r13
0x100423ea3  pop     r12
0x100423ea5  pop     rdi
0x100423ea6  pop     rsi
0x100423ea7  pop     rbp
0x100423ea8  retn
0x100423ea9  mov     eax, cs:_bidGblFlags
0x100423eaf  mov     ebx, 24002h
0x100423eb4  and     eax, ebx
0x100423eb6  cmp     eax, ebx
0x100423eb8  jnz     short loc_100423EDC
0x100423eba  mov     rax, cs:off_1005E4EB0; "<Np::SendPacketAsync|SNI> Send Packet, "...
0x100423ec1  test    rax, rax
0x100423ec4  jz      short loc_100423EDC
0x100423ec6  mov     r9d, [r15]
0x100423ec9  mov     r8, cs:off_1005E4EB0; "<Np::SendPacketAsync|SNI> Send Packet, "...
0x100423ed0  mov     edx, 117800h
0x100423ed5  xor     ecx, ecx
0x100423ed7  call    _bidTraceW
0x100423edc  mov     eax, cs:_bidGblFlags
0x100423ee2  and     eax, ebx
0x100423ee4  cmp     eax, ebx
0x100423ee6  jnz     loc_100423E4E
0x100423eec  and     [rsp+78h+lpOverlapped], rdi
0x100423ef1  mov     r9d, [r15]
0x100423ef4  mov     r8, r14
0x100423ef7  mov     edx, 10h
0x100423efc  mov     rcx, cs:_bidID
0x100423f03  call    _bidWriteBin
0x100423f08  jmp     loc_100423E4E
0x100423f0d  mov     eax, cs:_bidGblFlags
0x100423f13  mov     ebp, 20002h
0x100423f18  and     eax, ebp
0x100423f1a  cmp     eax, ebp
0x100423f1c  jnz     short loc_100423F5C
0x100423f1e  mov     rax, cs:off_1005E4EB8; "<Np::SendPacketAsync|SNI> Suppressing s"...
0x100423f25  test    rax, rax
0x100423f28  jz      short loc_100423F5C
0x100423f2a  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100423f32  jz      short loc_100423F5C
0x100423f34  mov     rax, cs:off_1005D39E0
0x100423f3b  and     [rsp+78h+lpOverlapped], rdi
0x100423f40  mov     r9, cs:off_1005E4EB8; "<Np::SendPacketAsync|SNI> Suppressing s"...
0x100423f47  xor     edx, edx
0x100423f49  mov     r8d, 119000h
0x100423f4f  mov     rcx, cs:_bidID
0x100423f56  call    cs:__guard_dispatch_icall_fptr
0x100423f5c  mov     edi, 3E5h
0x100423f61  jmp     loc_100423E0A
```
