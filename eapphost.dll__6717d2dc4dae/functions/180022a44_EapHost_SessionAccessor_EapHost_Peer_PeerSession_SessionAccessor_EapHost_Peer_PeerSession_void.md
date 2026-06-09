# EapHost::SessionAccessor<EapHost::Peer::PeerSession>::~SessionAccessor<EapHost::Peer::PeerSession>(void)

- ea: `0x180022a44`
- end: `0x180022a71`
- name: `??1?$SessionAccessor@VPeerSession@Peer@EapHost@@@EapHost@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(struct CacheEntry **, __int64, bool)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x180005d30`
- `0x180024a8c`
- `0x1800251b0`
- `0x1800256a4`
- `0x180025b18`
- `0x1800264e8`
- `0x180026578`
- `0x1800283b8`
- `0x1800299a0`
- `0x180029dac`
- `0x18002a0b8`
- `0x1800368f8`
- `0x18003690a`
- `0x180036940`
- `0x1800369f4`
- `0x180036e5e`
- `0x180036eae`

## callees

- `0x180022a44`
- `0x18002f93c`
- `0x180030a40`

## pseudocode

```c
void __fastcall EapHost::SessionAccessor<EapHost::Peer::PeerSession>::~SessionAccessor<EapHost::Peer::PeerSession>(
        struct CacheEntry **a1,
        __int64 a2,
        bool a3)
{
  if ( *a1 )
    CacheEngine::Insert(a1[1], *a1, a3);
  if ( *a1 )
    ReferenceCounted::Release(*a1);
}

```

## disassembly

```asm
0x180022a44  push    rbx
0x180022a46  sub     rsp, 20h
0x180022a4a  mov     rdx, [rcx]; struct CacheEntry *
0x180022a4d  mov     rbx, rcx
0x180022a50  test    rdx, rdx
0x180022a53  jz      short loc_180022A5E
0x180022a55  mov     rcx, [rcx+8]; this
0x180022a59  call    ?Insert@CacheEngine@@QEAA_NPEAVCacheEntry@@_N@Z; CacheEngine::Insert(CacheEntry *,bool)
0x180022a5e  mov     rcx, [rbx]; this
0x180022a61  test    rcx, rcx
0x180022a64  jz      short loc_180022A6B
0x180022a66  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180022a6b  add     rsp, 20h
0x180022a6f  pop     rbx
0x180022a70  retn
```
