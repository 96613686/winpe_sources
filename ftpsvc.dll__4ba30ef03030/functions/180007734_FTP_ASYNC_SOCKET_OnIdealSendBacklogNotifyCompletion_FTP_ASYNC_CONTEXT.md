# FTP_ASYNC_SOCKET::OnIdealSendBacklogNotifyCompletion(FTP_ASYNC_CONTEXT *)

- ea: `0x180007734`
- end: `0x180007870`
- name: `?OnIdealSendBacklogNotifyCompletion@FTP_ASYNC_SOCKET@@AEAAXPEAVFTP_ASYNC_CONTEXT@@@Z`
- size: `316`
- prototype: `void __fastcall(FTP_ASYNC_SOCKET *__hidden this, struct FTP_ASYNC_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006f70`

## callees

- `0x180007734`
- `0x180049010`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x1800077cc`
- `WS2_32!WSAIoctl` at `0x1800077cc`
- `WS2_32!__imp_setsockopt` at `0x180007810`
- `WS2_32!__imp_setsockopt` at `0x180007810`
- `WS2_32!__imp_WSAGetLastError` at `0x1800077d7`
- `WS2_32!__imp_WSAGetLastError` at `0x1800077d7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000776e`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000776e`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007819`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007819`

## pseudocode

```c
void __fastcall FTP_ASYNC_SOCKET::OnIdealSendBacklogNotifyCompletion(
        FTP_ASYNC_SOCKET *this,
        struct FTP_ASYNC_CONTEXT *a2)
{
  __int64 v2; // rbx
  char *v3; // rsi
  __int64 v4; // r14
  CReaderWriterLock3 *v5; // rbp
  SOCKET v8; // rcx
  unsigned int v9; // eax
  SOCKET v10; // rcx
  void (__fastcall *v11)(__int64); // rax
  unsigned int vOutBuffer; // [rsp+80h] [rbp+8h] BYREF
  DWORD cbBytesReturned; // [rsp+90h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 96);
  v3 = (char *)this + 708;
  v4 = *((unsigned int *)this + 177);
  v5 = (FTP_ASYNC_SOCKET *)((char *)this + 576);
  vOutBuffer = 0;
  CReaderWriterLock3::ReadLock((FTP_ASYNC_SOCKET *)((char *)this + 576));
  v8 = *((_QWORD *)this + 2);
  if ( v8 != -1 )
  {
    cbBytesReturned = 0;
    if ( WSAIoctl(v8, 0x4004747Bu, 0, 0, &vOutBuffer, 4u, &cbBytesReturned, 0, 0) == -1 )
    {
      WSAGetLastError();
    }
    else
    {
      v9 = FTP_ASYNC_SOCKET::sm_dwMaxISBCapPerConnection;
      v10 = *((_QWORD *)this + 2);
      if ( vOutBuffer < FTP_ASYNC_SOCKET::sm_dwMaxISBCapPerConnection )
        v9 = vOutBuffer;
      *(_DWORD *)v3 = v9;
      setsockopt(v10, 0xFFFF, 4097, v3, 4);
    }
  }
  CReaderWriterLock3::ReadUnlock(v5);
  if ( v2 )
  {
    *((_QWORD *)this + 96) = 0;
    if ( v2 != -24 )
    {
      *(_QWORD *)(v2 + 24) = v4;
      *(_QWORD *)(v2 + 32) = *(unsigned int *)v3;
    }
    *(_DWORD *)(v2 + 68) = *((_DWORD *)a2 + 17);
    v11 = *(void (__fastcall **)(__int64))(v2 + 8);
    *(_QWORD *)(v2 + 72) = 0;
    v11(v2);
  }
}

```

## disassembly

```asm
0x180007734  mov     rax, rsp
0x180007737  mov     [rax+10h], rbx
0x18000773b  push    rbp
0x18000773c  push    rsi
0x18000773d  push    rdi
0x18000773e  push    r14
0x180007740  push    r15
0x180007742  sub     rsp, 50h
0x180007746  mov     rbx, [rcx+300h]
0x18000774d  lea     rsi, [rcx+2C4h]
0x180007754  mov     r14d, [rsi]
0x180007757  lea     rbp, [rcx+240h]
0x18000775e  mov     rdi, rcx
0x180007761  mov     dword ptr [rax+8], 0
0x180007768  mov     rcx, rbp
0x18000776b  mov     r15, rdx
0x18000776e  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180007774  mov     rcx, [rdi+10h]; s
0x180007778  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000777c  jz      loc_180007816
0x180007782  mov     [rsp+78h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18000778b  lea     rax, [rsp+78h+cbBytesReturned]
0x180007793  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18000779c  xor     r9d, r9d; cbInBuffer
0x18000779f  mov     [rsp+78h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800077a4  xor     r8d, r8d; lpvInBuffer
0x1800077a7  lea     rax, [rsp+78h+vOutBuffer]
0x1800077af  mov     [rsp+78h+cbOutBuffer], 4; cbOutBuffer
0x1800077b7  mov     edx, 4004747Bh; dwIoControlCode
0x1800077bc  mov     [rsp+78h+lpvOutBuffer], rax; lpvOutBuffer
0x1800077c1  mov     [rsp+78h+cbBytesReturned], 0
0x1800077cc  call    cs:__imp_WSAIoctl
0x1800077d2  cmp     eax, 0FFFFFFFFh
0x1800077d5  jnz     short loc_1800077DF
0x1800077d7  call    cs:__imp_WSAGetLastError
0x1800077dd  jmp     short loc_180007816
0x1800077df  mov     eax, cs:?sm_dwMaxISBCapPerConnection@FTP_ASYNC_SOCKET@@0KA; ulong FTP_ASYNC_SOCKET::sm_dwMaxISBCapPerConnection
0x1800077e5  mov     r9, rsi; optval
0x1800077e8  cmp     [rsp+78h+vOutBuffer], eax
0x1800077ef  mov     edx, 0FFFFh; level
0x1800077f4  mov     rcx, [rdi+10h]; s
0x1800077f8  mov     r8d, 1001h; optname
0x1800077fe  cmovb   eax, [rsp+78h+vOutBuffer]
0x180007806  mov     [rsi], eax
0x180007808  mov     dword ptr [rsp+78h+lpvOutBuffer], 4; optlen
0x180007810  call    cs:__imp_setsockopt
0x180007816  mov     rcx, rbp
0x180007819  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000781f  test    rbx, rbx
0x180007822  jz      short loc_18000785C
0x180007824  lea     rcx, [rbx+18h]
0x180007828  mov     qword ptr [rdi+300h], 0
0x180007833  test    rcx, rcx
0x180007836  jz      short loc_180007841
0x180007838  mov     [rcx], r14
0x18000783b  mov     eax, [rsi]
0x18000783d  mov     [rcx+8], rax
0x180007841  mov     eax, [r15+44h]
0x180007845  mov     rcx, rbx
0x180007848  mov     [rbx+44h], eax
0x18000784b  mov     rax, [rbx+8]
0x18000784f  mov     qword ptr [rbx+48h], 0
0x180007857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785c  mov     rbx, [rsp+78h+arg_8]
0x180007864  add     rsp, 50h
0x180007868  pop     r15
0x18000786a  pop     r14
0x18000786c  pop     rdi
0x18000786d  pop     rsi
0x18000786e  pop     rbp
0x18000786f  retn
```
