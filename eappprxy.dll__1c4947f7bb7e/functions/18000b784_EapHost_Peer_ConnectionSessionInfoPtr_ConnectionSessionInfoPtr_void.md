# EapHost::Peer::ConnectionSessionInfoPtr::~ConnectionSessionInfoPtr(void)

- ea: `0x18000b784`
- end: `0x18000b79b`
- name: `??1ConnectionSessionInfoPtr@Peer@EapHost@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(EapHost::Peer::ConnectionSessionInfoPtr *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e07a`
- `0x18000e125`
- `0x18000e1a7`

## callees

- `0x18000b784`
- `0x18000c6e0`

## pseudocode

```c
void __fastcall EapHost::Peer::ConnectionSessionInfoPtr::~ConnectionSessionInfoPtr(
        EapHost::Peer::ConnectionSessionInfo **this)
{
  EapHost::Peer::ConnectionSessionInfo *v1; // rcx

  v1 = *this;
  if ( v1 )
    EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(v1);
}

```

## disassembly

```asm
0x18000b784  sub     rsp, 28h
0x18000b788  mov     rcx, [rcx]; this
0x18000b78b  test    rcx, rcx
0x18000b78e  jz      short loc_18000B795
0x18000b790  call    ?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ; EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)
0x18000b795  add     rsp, 28h
0x18000b799  retn
```
