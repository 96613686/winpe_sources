# EapHost::SessionAccessor<EapHost::Peer::PeerSession>::SessionAccessor<EapHost::Peer::PeerSession>(Cache<EapHost::SessionTableOperation<EapHost::Peer::PeerSession>> &,uint,bool)

- ea: `0x180022ee4`
- end: `0x180022f77`
- name: `??0?$SessionAccessor@VPeerSession@Peer@EapHost@@@EapHost@@QEAA@AEAV?$Cache@V?$SessionTableOperation@VPeerSession@Peer@EapHost@@@EapHost@@@@I_N@Z`
- size: `147`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: `file_ops`

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

## callees

- `0x180004e24`
- `0x18001e7c0`
- `0x180022ee4`
- `0x180031c88`

## string_xrefs

- `0x180022f5e`: `SessionAccessor::SessionAccessor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CacheEntry **__fastcall EapHost::SessionAccessor<EapHost::Peer::PeerSession>::SessionAccessor<EapHost::Peer::PeerSession>(
        struct CacheEntry **a1,
        CacheEngine *a2,
        int a3,
        char a4)
{
  struct CacheEntry *v6; // rdi
  struct CacheEntry *v8; // [rsp+48h] [rbp+10h] BYREF
  int v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = a3;
  *a1 = 0;
  a1[1] = a2;
  if ( a3 )
  {
    v6 = CacheEngine::Remove(a2, &v9);
    v8 = v6;
    if ( v6 != *a1 )
    {
      SmartPointer<EapLm::IEapMethod>::~SmartPointer<EapLm::IEapMethod>(a1);
      *a1 = v6;
      if ( v6 )
        _InterlockedIncrement((volatile signed __int32 *)v6 + 2);
    }
    SmartPointer<EapLm::IEapMethod>::~SmartPointer<EapLm::IEapMethod>(&v8);
  }
  if ( !*a1 && !a4 )
    EapHost::EapException::Throw(L"SessionAccessor::SessionAccessor", L"sessionId", -2147024809);
  return a1;
}

```

## disassembly

```asm
0x180022ee4  mov     [rsp+arg_10], r8d
0x180022ee9  mov     [rsp+arg_0], rcx
0x180022eee  push    rbx
0x180022eef  push    rsi
0x180022ef0  push    rdi
0x180022ef1  sub     rsp, 20h
0x180022ef5  mov     sil, r9b
0x180022ef8  mov     rax, rdx
0x180022efb  mov     rbx, rcx
0x180022efe  mov     qword ptr [rcx], 0
0x180022f05  mov     [rcx+8], rdx
0x180022f09  test    r8d, r8d
0x180022f0c  jz      short loc_180022F46
0x180022f0e  lea     rdx, [rsp+38h+arg_10]; void *
0x180022f13  mov     rcx, rax; this
0x180022f16  call    ?Remove@CacheEngine@@QEAAPEAVCacheEntry@@PEBX@Z; CacheEngine::Remove(void const *)
0x180022f1b  mov     rdi, rax
0x180022f1e  mov     [rsp+38h+arg_8], rax
0x180022f23  cmp     rax, [rbx]
0x180022f26  jz      short loc_180022F3C
0x180022f28  mov     rcx, rbx
0x180022f2b  call    ??1?$SmartPointer@UIEapMethod@EapLm@@@@QEAA@XZ; SmartPointer<EapLm::IEapMethod>::~SmartPointer<EapLm::IEapMethod>(void)
0x180022f30  mov     [rbx], rdi
0x180022f33  test    rdi, rdi
0x180022f36  jz      short loc_180022F3C
0x180022f38  lock inc dword ptr [rdi+8]
0x180022f3c  lea     rcx, [rsp+38h+arg_8]
0x180022f41  call    ??1?$SmartPointer@UIEapMethod@EapLm@@@@QEAA@XZ; SmartPointer<EapLm::IEapMethod>::~SmartPointer<EapLm::IEapMethod>(void)
0x180022f46  cmp     qword ptr [rbx], 0
0x180022f4a  jnz     short loc_180022F6B
0x180022f4c  test    sil, sil
0x180022f4f  jnz     short loc_180022F6B
0x180022f51  mov     r8d, 80070057h; int
0x180022f57  lea     rdx, aSessionid; "sessionId"
0x180022f5e  lea     rcx, aSessionaccesso; "SessionAccessor::SessionAccessor"
0x180022f65  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180022f6b  mov     rax, rbx
0x180022f6e  add     rsp, 20h
0x180022f72  pop     rdi
0x180022f73  pop     rsi
0x180022f74  pop     rbx
0x180022f75  retn
```
