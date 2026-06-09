# tlx::_delete<DbSession>(DbSession *)

- ea: `0x180010024`
- end: `0x180010044`
- name: `??$_delete@VDbSession@@@tlx@@YAXPEAVDbSession@@@Z`
- size: `32`
- prototype: `void __fastcall(DbSession *P)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001009c`
- `0x180010220`
- `0x1800105bc`
- `0x180011600`

## callees

- `0x18000be3c`
- `0x180010024`
- `0x180014514`

## pseudocode

```c
void __fastcall tlx::_delete<DbSession>(DbSession *P)
{
  if ( P )
  {
    DbSession::~DbSession(P);
    Common::GlobalHeap::Free(P);
  }
}

```

## disassembly

```asm
0x180010024  test    rcx, rcx
0x180010027  jz      short locret_180010043
0x180010029  push    rbx
0x18001002a  sub     rsp, 20h
0x18001002e  mov     rbx, rcx
0x180010031  call    ??1DbSession@@QEAA@XZ
0x180010036  mov     rcx, rbx; P
0x180010039  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z
0x18001003e  add     rsp, 20h
0x180010042  pop     rbx
0x180010043  retn
```
