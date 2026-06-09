# FTP_ASYNC_SOCKET::UpdateAcceptedConnection(FTP_ASYNC_SOCKET *)

- ea: `0x180008224`
- end: `0x1800082b2`
- name: `?UpdateAcceptedConnection@FTP_ASYNC_SOCKET@@QEAAJPEAV1@@Z`
- size: `142`
- prototype: `__int64 __fastcall(FTP_ASYNC_SOCKET *__hidden this, struct FTP_ASYNC_SOCKET *)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180032490`
- `0x180040118`

## callees

- `0x180008224`

## import_xrefs

- `WS2_32!__imp_setsockopt` at `0x180008286`
- `WS2_32!__imp_setsockopt` at `0x180008286`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000823d`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008256`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000823d`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180008256`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008298`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800082a1`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008298`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800082a1`

## pseudocode

```c
__int64 __fastcall FTP_ASYNC_SOCKET::UpdateAcceptedConnection(FTP_ASYNC_SOCKET *this, struct FTP_ASYNC_SOCKET *a2)
{
  CReaderWriterLock3 *v2; // rsi
  SOCKET v5; // rcx
  unsigned int v6; // ebx
  __int64 optval; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct FTP_ASYNC_SOCKET *)((char *)a2 + 576);
  CReaderWriterLock3::ReadLock((struct FTP_ASYNC_SOCKET *)((char *)a2 + 576));
  optval = *((_QWORD *)a2 + 2);
  CReaderWriterLock3::ReadLock((FTP_ASYNC_SOCKET *)((char *)this + 576));
  if ( optval == -1 || (v5 = *((_QWORD *)this + 2), v5 == -1) )
    v6 = -2147023660;
  else
    v6 = setsockopt(v5, 0xFFFF, 28683, (const char *)&optval, 8);
  CReaderWriterLock3::ReadUnlock((FTP_ASYNC_SOCKET *)((char *)this + 576));
  CReaderWriterLock3::ReadUnlock(v2);
  return v6;
}

```

## disassembly

```asm
0x180008224  push    rbx
0x180008226  push    rbp
0x180008227  push    rsi
0x180008228  push    rdi
0x180008229  sub     rsp, 38h
0x18000822d  lea     rsi, [rdx+240h]
0x180008234  mov     rdi, rcx
0x180008237  mov     rcx, rsi
0x18000823a  mov     rbx, rdx
0x18000823d  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180008243  mov     rax, [rbx+10h]
0x180008247  lea     rbp, [rdi+240h]
0x18000824e  mov     rcx, rbp
0x180008251  mov     [rsp+58h+optval], rax
0x180008256  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000825c  cmp     [rsp+58h+optval], 0FFFFFFFFFFFFFFFFh
0x180008262  jz      short loc_180008290
0x180008264  mov     rcx, [rdi+10h]; s
0x180008268  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000826c  jz      short loc_180008290
0x18000826e  lea     r9, [rsp+58h+optval]; optval
0x180008273  mov     [rsp+58h+optlen], 8; optlen
0x18000827b  mov     edx, 0FFFFh; level
0x180008280  mov     r8d, 700Bh; optname
0x180008286  call    cs:__imp_setsockopt
0x18000828c  mov     ebx, eax
0x18000828e  jmp     short loc_180008295
0x180008290  mov     ebx, 800704D4h
0x180008295  mov     rcx, rbp
0x180008298  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000829e  mov     rcx, rsi
0x1800082a1  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800082a7  mov     eax, ebx
0x1800082a9  add     rsp, 38h
0x1800082ad  pop     rdi
0x1800082ae  pop     rsi
0x1800082af  pop     rbp
0x1800082b0  pop     rbx
0x1800082b1  retn
```
