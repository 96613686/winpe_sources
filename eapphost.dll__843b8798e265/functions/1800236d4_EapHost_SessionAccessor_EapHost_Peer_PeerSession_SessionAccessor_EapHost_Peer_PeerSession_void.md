# EapHost::SessionAccessor<EapHost::Peer::PeerSession>::~SessionAccessor<EapHost::Peer::PeerSession>(void)

- ea: `0x1800236d4`
- end: `0x1800236fb`
- name: `??1?$SessionAccessor@VPeerSession@Peer@EapHost@@@EapHost@@QEAA@XZ`
- size: `39`
- prototype: ``
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x180005f60`
- `0x180025770`
- `0x180025ebc`
- `0x1800263cc`
- `0x180026850`
- `0x180027254`
- `0x1800272e4`
- `0x1800291a8`
- `0x18002a7f0`
- `0x18002abf8`
- `0x18002aee0`
- `0x180037cc6`
- `0x180037cd8`
- `0x180037d0e`
- `0x180037dc2`
- `0x180038231`
- `0x180038282`

## callees

- `0x180004e24`
- `0x1800236d4`
- `0x180031bf8`

## pseudocode

```c
__int64 __fastcall EapHost::SessionAccessor<EapHost::Peer::PeerSession>::~SessionAccessor<EapHost::Peer::PeerSession>(
        struct CacheEntry **a1,
        __int64 a2,
        bool a3)
{
  if ( *a1 )
    CacheEngine::Insert(a1[1], *a1, a3);
  return SmartPointer<EapLm::IEapMethod>::~SmartPointer<EapLm::IEapMethod>(a1);
}

```

## disassembly

```asm
0x1800236d4  push    rbx
0x1800236d6  sub     rsp, 20h
0x1800236da  mov     rdx, [rcx]; struct CacheEntry *
0x1800236dd  mov     rbx, rcx
0x1800236e0  test    rdx, rdx
0x1800236e3  jz      short loc_1800236EE
0x1800236e5  mov     rcx, [rcx+8]; this
0x1800236e9  call    ?Insert@CacheEngine@@QEAA_NPEAVCacheEntry@@_N@Z; CacheEngine::Insert(CacheEntry *,bool)
0x1800236ee  mov     rcx, rbx
0x1800236f1  add     rsp, 20h
0x1800236f5  pop     rbx
0x1800236f6  jmp     ??1?$SmartPointer@UIEapMethod@EapLm@@@@QEAA@XZ; SmartPointer<EapLm::IEapMethod>::~SmartPointer<EapLm::IEapMethod>(void)
```
