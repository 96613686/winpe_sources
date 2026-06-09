# FTP_ASYNC_SOCKET::RegisterForIdealSendBacklogChange(FTP_ASYNC_CONTEXT *)

- ea: `0x180007dc8`
- end: `0x180007eba`
- name: `?RegisterForIdealSendBacklogChange@FTP_ASYNC_SOCKET@@QEAAJPEAVFTP_ASYNC_CONTEXT@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(FTP_ASYNC_SOCKET *__hidden this, struct FTP_ASYNC_CONTEXT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180040000`
- `0x180041160`

## callees

- `0x180007dc8`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x180007e72`
- `WS2_32!WSAIoctl` at `0x180007e72`
- `WS2_32!__imp_WSAGetLastError` at `0x180007e7d`
- `WS2_32!__imp_WSAGetLastError` at `0x180007e8a`
- `WS2_32!__imp_WSAGetLastError` at `0x180007e7d`
- `WS2_32!__imp_WSAGetLastError` at `0x180007e8a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007e26`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007e26`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007ea2`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007ea2`

## pseudocode

```c
__int64 __fastcall FTP_ASYNC_SOCKET::RegisterForIdealSendBacklogChange(
        struct _OVERLAPPED *this,
        struct FTP_ASYNC_CONTEXT *a2)
{
  CReaderWriterLock3 *v3; // rsi
  SOCKET Pointer; // rcx
  unsigned int v5; // edi
  int Error; // eax
  DWORD cbBytesReturned; // [rsp+60h] [rbp+8h] BYREF

  this[24].InternalHigh = 4;
  this[22].Pointer = FTP_ASYNC_SOCKET::AsyncCompletionRoutine;
  this[22].hEvent = this;
  this[24].Pointer = 0;
  if ( a2 )
  {
    *(_OWORD *)((char *)a2 + 24) = 0;
    *(_OWORD *)((char *)a2 + 40) = 0;
  }
  v3 = (CReaderWriterLock3 *)&this[18];
  this[24].Internal = (ULONG_PTR)a2;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&this[18]);
  Pointer = (SOCKET)this->Pointer;
  if ( Pointer == -1 )
  {
    v5 = -2147023660;
  }
  else
  {
    v5 = 0;
    cbBytesReturned = 0;
    if ( WSAIoctl(Pointer, 0x2000747Au, 0, 0, 0, 0, &cbBytesReturned, this + 23, 0) == -1 && WSAGetLastError() != 997 )
    {
      Error = WSAGetLastError();
      v5 = Error;
      if ( Error > 0 )
        v5 = (unsigned __int16)Error | 0x80070000;
    }
  }
  CReaderWriterLock3::ReadUnlock(v3);
  return v5;
}

```

## disassembly

```asm
0x180007dc8  mov     [rsp+arg_8], rbx
0x180007dcd  mov     [rsp+arg_10], rsi
0x180007dd2  push    rdi
0x180007dd3  sub     rsp, 50h
0x180007dd7  mov     qword ptr [rcx+308h], 4
0x180007de2  lea     rax, ?AsyncCompletionRoutine@FTP_ASYNC_SOCKET@@SAXPEAVFTP_ASYNC_CONTEXT@@@Z; FTP_ASYNC_SOCKET::AsyncCompletionRoutine(FTP_ASYNC_CONTEXT *)
0x180007de9  mov     [rcx+2D0h], rax
0x180007df0  mov     rbx, rcx
0x180007df3  mov     [rcx+2D8h], rcx
0x180007dfa  mov     qword ptr [rcx+310h], 0
0x180007e05  test    rdx, rdx
0x180007e08  jz      short loc_180007E15
0x180007e0a  xorps   xmm0, xmm0
0x180007e0d  movups  xmmword ptr [rdx+18h], xmm0
0x180007e11  movups  xmmword ptr [rdx+28h], xmm0
0x180007e15  lea     rsi, [rcx+240h]
0x180007e1c  mov     [rcx+300h], rdx
0x180007e23  mov     rcx, rsi
0x180007e26  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180007e2c  mov     rcx, [rbx+10h]; s
0x180007e30  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180007e34  jnz     short loc_180007E3D
0x180007e36  mov     edi, 800704D4h
0x180007e3b  jmp     short loc_180007E9F
0x180007e3d  xor     edi, edi
0x180007e3f  lea     rax, [rbx+2E0h]
0x180007e46  mov     [rsp+58h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x180007e4b  xor     r9d, r9d; cbInBuffer
0x180007e4e  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x180007e53  xor     r8d, r8d; lpvInBuffer
0x180007e56  lea     rax, [rsp+58h+cbBytesReturned]
0x180007e5b  mov     [rsp+58h+cbBytesReturned], edi
0x180007e5f  mov     [rsp+58h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180007e64  mov     edx, 2000747Ah; dwIoControlCode
0x180007e69  mov     [rsp+58h+cbOutBuffer], edi; cbOutBuffer
0x180007e6d  mov     [rsp+58h+lpvOutBuffer], rdi; lpvOutBuffer
0x180007e72  call    cs:__imp_WSAIoctl
0x180007e78  cmp     eax, 0FFFFFFFFh
0x180007e7b  jnz     short loc_180007E9F
0x180007e7d  call    cs:__imp_WSAGetLastError
0x180007e83  cmp     eax, 3E5h
0x180007e88  jz      short loc_180007E9F
0x180007e8a  call    cs:__imp_WSAGetLastError
0x180007e90  mov     edi, eax
0x180007e92  test    eax, eax
0x180007e94  jle     short loc_180007E9F
0x180007e96  movzx   edi, ax
0x180007e99  or      edi, 80070000h
0x180007e9f  mov     rcx, rsi
0x180007ea2  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180007ea8  mov     rbx, [rsp+58h+arg_8]
0x180007ead  mov     eax, edi
0x180007eaf  mov     rsi, [rsp+58h+arg_10]
0x180007eb4  add     rsp, 50h
0x180007eb8  pop     rdi
0x180007eb9  retn
```
