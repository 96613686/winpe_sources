# DrSession::ServerAnnounceWrite(void)

- ea: `0x14001d698`
- end: `0x14001d70a`
- name: `?ServerAnnounceWrite@DrSession@@AEAAJXZ`
- size: `114`
- prototype: `__int64 __fastcall(DrSession *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001bf2c`
- `0x14001d710`

## callees

- `0x140006480`
- `0x140024cf0`

## pseudocode

```c
__int64 __fastcall DrSession::ServerAnnounceWrite(DrSession *this)
{
  _DWORD v2[4]; // [rsp+40h] [rbp-28h] BYREF

  v2[2] = *((_DWORD *)this + 170);
  v2[0] = 1231963250;
  v2[1] = 851969;
  return DrSession::PrivateSendToClient(
           this,
           v2,
           0xCu,
           (struct ISessionPacketSender *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
           0,
           0,
           0,
           0);
}

```

## disassembly

```asm
0x14001d698  sub     rsp, 68h
0x14001d69c  mov     rax, cs:__security_cookie
0x14001d6a3  xor     rax, rsp
0x14001d6a6  mov     [rsp+68h+var_18], rax
0x14001d6ab  mov     eax, [rcx+2A8h]
0x14001d6b1  lea     rdx, [rcx+20h]
0x14001d6b5  mov     [rsp+68h+var_20], eax
0x14001d6b9  mov     rax, rcx
0x14001d6bc  neg     rax
0x14001d6bf  mov     [rsp+68h+var_28], 496E4472h
0x14001d6c7  mov     [rsp+68h+var_24], 0D0001h
0x14001d6cf  sbb     r9, r9
0x14001d6d2  xor     eax, eax
0x14001d6d4  mov     [rsp+68h+var_30], rax; void *
0x14001d6d9  and     r9, rdx; struct ISessionPacketSender *
0x14001d6dc  mov     [rsp+68h+var_38], eax; int
0x14001d6e0  lea     rdx, [rsp+68h+var_28]; void *
0x14001d6e5  mov     [rsp+68h+var_40], eax; int
0x14001d6e9  lea     r8d, [rax+0Ch]; unsigned int
0x14001d6ed  mov     [rsp+68h+var_48], rax; int (*)(void *, struct _IO_STATUS_BLOCK *)
0x14001d6f2  call    ?PrivateSendToClient@DrSession@@AEAAJPEAXKPEAVISessionPacketSender@@P6AJ0PEAU_IO_STATUS_BLOCK@@@ZHH0@Z; DrSession::PrivateSendToClient(void *,ulong,ISessionPacketSender *,long (*)(void *,_IO_STATUS_BLOCK *),int,int,void *)
0x14001d6f7  mov     rcx, [rsp+68h+var_18]
0x14001d6fc  xor     rcx, rsp; StackCookie
0x14001d6ff  call    __security_check_cookie
0x14001d704  add     rsp, 68h
0x14001d708  retn
```
