# EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(void)

- ea: `0x18000c6e0`
- end: `0x18000c717`
- name: `?ReduceRefCount@ConnectionSessionInfo@Peer@EapHost@@QEAAXXZ`
- size: `55`
- prototype: `void __fastcall(EapHost::Peer::ConnectionSessionInfo *__hidden this)`
- caller_count: `13`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800059c4`
- `0x180005ab0`
- `0x180006100`
- `0x180007d40`
- `0x1800080c0`
- `0x18000b784`
- `0x18000bac0`
- `0x18000bd30`
- `0x18000c720`
- `0x18000c7d0`
- `0x18000c88c`
- `0x18000cae8`
- `0x18000e08c`

## callees

- `0x1800017a4`
- `0x18000b6ac`
- `0x18000c6e0`

## pseudocode

```c
void __fastcall EapHost::Peer::ConnectionSessionInfo::ReduceRefCount(EapHost::Peer::ConnectionSessionInfo *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 42, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      EapHost::Peer::ConnectionSessionInfo::~ConnectionSessionInfo(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x18000c6e0  push    rbx
0x18000c6e2  sub     rsp, 20h
0x18000c6e6  mov     rbx, rcx
0x18000c6e9  or      eax, 0FFFFFFFFh
0x18000c6ec  lock xadd [rcx+0A8h], eax
0x18000c6f4  cmp     eax, 1
0x18000c6f7  jnz     short loc_18000C710
0x18000c6f9  test    rcx, rcx
0x18000c6fc  jz      short loc_18000C710
0x18000c6fe  call    ??1ConnectionSessionInfo@Peer@EapHost@@AEAA@XZ; EapHost::Peer::ConnectionSessionInfo::~ConnectionSessionInfo(void)
0x18000c703  mov     edx, 0C8h; unsigned __int64
0x18000c708  mov     rcx, rbx; void *
0x18000c70b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c710  add     rsp, 20h
0x18000c714  pop     rbx
0x18000c715  retn
```
