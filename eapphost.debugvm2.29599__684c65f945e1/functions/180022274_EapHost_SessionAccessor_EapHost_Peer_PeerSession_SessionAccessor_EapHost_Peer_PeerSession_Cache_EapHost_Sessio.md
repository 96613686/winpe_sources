# EapHost::SessionAccessor<EapHost::Peer::PeerSession>::SessionAccessor<EapHost::Peer::PeerSession>(Cache<EapHost::SessionTableOperation<EapHost::Peer::PeerSession>> &,uint,bool)

- ea: `0x180022274`
- end: `0x180022319`
- name: `??0?$SessionAccessor@VPeerSession@Peer@EapHost@@@EapHost@@QEAA@AEAV?$Cache@V?$SessionTableOperation@VPeerSession@Peer@EapHost@@@EapHost@@@@I_N@Z`
- size: `165`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: `file_ops`

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

## callees

- `0x18001dcbc`
- `0x180022274`
- `0x18002f93c`
- `0x180030ad0`

## string_xrefs

- `0x1800222f9`: `SessionAccessor::SessionAccessor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ReferenceCounted **__fastcall EapHost::SessionAccessor<EapHost::Peer::PeerSession>::SessionAccessor<EapHost::Peer::PeerSession>(
        ReferenceCounted **a1,
        CacheEngine *a2,
        int a3,
        char a4)
{
  struct CacheEntry *v6; // rax
  volatile signed __int32 *v7; // rbx
  ReferenceCounted *v8; // rcx
  int v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  *a1 = 0;
  a1[1] = a2;
  if ( a3 )
  {
    v6 = CacheEngine::Remove(a2, &v10);
    v7 = (volatile signed __int32 *)v6;
    v8 = *a1;
    if ( v6 == *a1 )
    {
      if ( v6 )
        goto LABEL_8;
    }
    else
    {
      if ( v8 )
        ReferenceCounted::Release(v8);
      *a1 = (ReferenceCounted *)v7;
      if ( v7 )
      {
        _InterlockedIncrement(v7 + 2);
LABEL_8:
        ReferenceCounted::Release((ReferenceCounted *)v7);
      }
    }
  }
  if ( !*a1 && !a4 )
    EapHost::EapException::Throw(L"SessionAccessor::SessionAccessor", L"sessionId", -2147024809);
  return a1;
}

```

## disassembly

```asm
0x180022274  mov     r11, rsp
0x180022277  mov     [r11+10h], rbx
0x18002227b  mov     [r11+20h], rsi
0x18002227f  mov     [r11+18h], r8d
0x180022283  mov     [r11+8], rcx
0x180022287  push    rdi
0x180022288  sub     rsp, 20h
0x18002228c  mov     sil, r9b
0x18002228f  mov     rax, rdx
0x180022292  mov     rdi, rcx
0x180022295  mov     qword ptr [rcx], 0
0x18002229c  mov     [rcx+8], rdx
0x1800222a0  test    r8d, r8d
0x1800222a3  jz      short loc_1800222E1
0x1800222a5  lea     rdx, [r11+18h]; void *
0x1800222a9  mov     rcx, rax; this
0x1800222ac  call    ?Remove@CacheEngine@@QEAAPEAVCacheEntry@@PEBX@Z; CacheEngine::Remove(void const *)
0x1800222b1  mov     rbx, rax
0x1800222b4  mov     rcx, [rdi]; this
0x1800222b7  cmp     rax, rcx
0x1800222ba  jz      short loc_1800222D4
0x1800222bc  test    rcx, rcx
0x1800222bf  jz      short loc_1800222C6
0x1800222c1  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x1800222c6  mov     [rdi], rbx
0x1800222c9  test    rbx, rbx
0x1800222cc  jz      short loc_1800222E1
0x1800222ce  lock inc dword ptr [rbx+8]
0x1800222d2  jmp     short loc_1800222D9
0x1800222d4  test    rbx, rbx
0x1800222d7  jz      short loc_1800222E1
0x1800222d9  mov     rcx, rbx; this
0x1800222dc  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x1800222e1  cmp     qword ptr [rdi], 0
0x1800222e5  jnz     short loc_180022306
0x1800222e7  test    sil, sil
0x1800222ea  jnz     short loc_180022306
0x1800222ec  mov     r8d, 80070057h; int
0x1800222f2  lea     rdx, aSessionid; "sessionId"
0x1800222f9  lea     rcx, aSessionaccesso; "SessionAccessor::SessionAccessor"
0x180022300  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180022306  mov     rax, rdi
0x180022309  mov     rbx, [rsp+28h+arg_8]
0x18002230e  mov     rsi, [rsp+28h+arg_18]
0x180022313  add     rsp, 20h
0x180022317  pop     rdi
0x180022318  retn
```
