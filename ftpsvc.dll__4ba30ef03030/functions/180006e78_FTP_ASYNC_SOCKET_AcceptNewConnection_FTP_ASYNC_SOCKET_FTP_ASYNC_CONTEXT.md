# FTP_ASYNC_SOCKET::AcceptNewConnection(FTP_ASYNC_SOCKET *,FTP_ASYNC_CONTEXT *)

- ea: `0x180006e78`
- end: `0x180006f61`
- name: `?AcceptNewConnection@FTP_ASYNC_SOCKET@@QEAAJPEAV1@PEAVFTP_ASYNC_CONTEXT@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct _OVERLAPPED *this, struct FTP_ASYNC_SOCKET *, struct FTP_ASYNC_CONTEXT *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180031aa0`
- `0x18003ed9c`

## callees

- `0x180006e78`

## import_xrefs

- `WS2_32!__imp_WSAGetLastError` at `0x180006f12`
- `WS2_32!__imp_WSAGetLastError` at `0x180006f12`
- `MSWSOCK!AcceptEx` at `0x180006f08`
- `MSWSOCK!AcceptEx` at `0x180006f08`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006eaa`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006eba`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006eaa`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006eba`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180006f47`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180006f50`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180006f47`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180006f50`

## pseudocode

```c
__int64 __fastcall FTP_ASYNC_SOCKET::AcceptNewConnection(
        struct _OVERLAPPED *this,
        struct FTP_ASYNC_SOCKET *a2,
        struct FTP_ASYNC_CONTEXT *a3)
{
  CReaderWriterLock3 *v3; // rsi
  SOCKET v6; // rcx
  SOCKET Pointer; // rdx
  int Error; // eax
  unsigned int v9; // ebx
  DWORD dwBytesReceived; // [rsp+70h] [rbp+8h] BYREF

  v3 = (struct FTP_ASYNC_SOCKET *)((char *)a2 + 576);
  this[20].Internal = (ULONG_PTR)a3;
  LODWORD(this[20].InternalHigh) = 2;
  dwBytesReceived = 0;
  CReaderWriterLock3::ReadLock((struct FTP_ASYNC_SOCKET *)((char *)a2 + 576));
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&this[18]);
  v6 = *((_QWORD *)a2 + 2);
  if ( v6 == -1 || (Pointer = (SOCKET)this->Pointer, Pointer == -1) )
  {
    v9 = -2147023660;
  }
  else
  {
    HIDWORD(this[9].hEvent) = 1;
    if ( AcceptEx(v6, Pointer, &this->hEvent, 0, 0x90u, 0x90u, &dwBytesReceived, this + 19) )
      goto LABEL_8;
    Error = WSAGetLastError();
    v9 = Error;
    if ( Error > 0 )
      v9 = (unsigned __int16)Error | 0x80070000;
    if ( v9 == -2147023899 )
LABEL_8:
      v9 = 0;
    else
      HIDWORD(this[9].hEvent) = 0;
  }
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&this[18]);
  CReaderWriterLock3::ReadUnlock(v3);
  return v9;
}

```

## disassembly

```asm
0x180006e78  push    rbx
0x180006e7a  push    rbp
0x180006e7b  push    rsi
0x180006e7c  push    rdi
0x180006e7d  sub     rsp, 48h
0x180006e81  lea     rsi, [rdx+240h]
0x180006e88  mov     [rcx+280h], r8
0x180006e8f  mov     rdi, rcx
0x180006e92  mov     dword ptr [rcx+288h], 2
0x180006e9c  mov     rcx, rsi
0x180006e9f  mov     [rsp+68h+dwBytesReceived], 0
0x180006ea7  mov     rbx, rdx
0x180006eaa  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180006eb0  lea     rbp, [rdi+240h]
0x180006eb7  mov     rcx, rbp
0x180006eba  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180006ec0  mov     rcx, [rbx+10h]; sListenSocket
0x180006ec4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006ec8  jz      short loc_180006F3F
0x180006eca  mov     rdx, [rdi+10h]; sAcceptSocket
0x180006ece  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180006ed2  jz      short loc_180006F3F
0x180006ed4  lea     rax, [rdi+260h]
0x180006edb  mov     dword ptr [rdi+13Ch], 1
0x180006ee5  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x180006eea  lea     r8, [rdi+18h]; lpOutputBuffer
0x180006eee  lea     rax, [rsp+68h+dwBytesReceived]
0x180006ef3  xor     r9d, r9d; dwReceiveDataLength
0x180006ef6  mov     [rsp+68h+lpdwBytesReceived], rax; lpdwBytesReceived
0x180006efb  mov     eax, 90h
0x180006f00  mov     [rsp+68h+dwRemoteAddressLength], eax; dwRemoteAddressLength
0x180006f04  mov     [rsp+68h+dwLocalAddressLength], eax; dwLocalAddressLength
0x180006f08  call    cs:__imp_AcceptEx
0x180006f0e  test    eax, eax
0x180006f10  jnz     short loc_180006F3B
0x180006f12  call    cs:__imp_WSAGetLastError
0x180006f18  mov     ebx, eax
0x180006f1a  test    eax, eax
0x180006f1c  jle     short loc_180006F27
0x180006f1e  movzx   ebx, ax
0x180006f21  or      ebx, 80070000h
0x180006f27  cmp     ebx, 800703E5h
0x180006f2d  jz      short loc_180006F3B
0x180006f2f  mov     dword ptr [rdi+13Ch], 0
0x180006f39  jmp     short loc_180006F44
0x180006f3b  xor     ebx, ebx
0x180006f3d  jmp     short loc_180006F44
0x180006f3f  mov     ebx, 800704D4h
0x180006f44  mov     rcx, rbp
0x180006f47  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180006f4d  mov     rcx, rsi
0x180006f50  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180006f56  mov     eax, ebx
0x180006f58  add     rsp, 48h
0x180006f5c  pop     rdi
0x180006f5d  pop     rsi
0x180006f5e  pop     rbp
0x180006f5f  pop     rbx
0x180006f60  retn
```
