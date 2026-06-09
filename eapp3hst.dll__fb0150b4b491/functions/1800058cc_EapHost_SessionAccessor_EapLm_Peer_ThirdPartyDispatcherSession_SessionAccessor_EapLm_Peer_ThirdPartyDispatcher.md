# EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(Cache<EapHost::SessionTableOperation<EapLm::Peer::ThirdPartyDispatcherSession>> &,uint,bool)

- ea: `0x1800058cc`
- end: `0x180005960`
- name: `??0?$SessionAccessor@VThirdPartyDispatcherSession@Peer@EapLm@@@EapHost@@QEAA@AEAV?$Cache@V?$SessionTableOperation@VThirdPartyDispatcherSession@Peer@EapLm@@@EapHost@@@@I_N@Z`
- size: `148`
- prototype: `ReferenceCounted **__fastcall(ReferenceCounted **, CacheEngine *, int)`
- caller_count: `8`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180006f20`
- `0x180007de0`
- `0x180007fe0`
- `0x1800081b0`
- `0x180008660`
- `0x180009590`
- `0x18000aa90`
- `0x18000ac20`

## callees

- `0x1800058cc`
- `0x180011430`
- `0x180012c10`
- `0x180015534`

## string_xrefs

- `0x180005945`: `SessionAccessor::SessionAccessor`

## pseudocode

```c
ReferenceCounted **__fastcall EapHost::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>::SessionAccessor<EapLm::Peer::ThirdPartyDispatcherSession>(
        ReferenceCounted **a1,
        CacheEngine *a2,
        int a3)
{
  struct CacheEntry *v4; // rax
  volatile signed __int32 *v5; // rbx
  ReferenceCounted *v6; // rcx
  int v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = a3;
  *a1 = 0;
  a1[1] = a2;
  if ( a3 )
  {
    v4 = CacheEngine::Remove(a2, &v8);
    v5 = (volatile signed __int32 *)v4;
    v6 = *a1;
    if ( v4 == *a1 )
    {
      if ( !v4 )
        goto LABEL_9;
      goto LABEL_8;
    }
    if ( v6 )
      ReferenceCounted::Release(v6);
    *a1 = (ReferenceCounted *)v5;
    if ( v5 )
    {
      _InterlockedIncrement(v5 + 2);
LABEL_8:
      ReferenceCounted::Release((ReferenceCounted *)v5);
    }
  }
LABEL_9:
  if ( !*a1 )
    EapHost::EapException::Throw(L"SessionAccessor::SessionAccessor", L"sessionId", -2147024809);
  return a1;
}

```

## disassembly

```asm
0x1800058cc  mov     r11, rsp
0x1800058cf  mov     [r11+10h], rbx
0x1800058d3  mov     [r11+18h], r8d
0x1800058d7  mov     [r11+8], rcx
0x1800058db  push    rdi
0x1800058dc  sub     rsp, 20h
0x1800058e0  mov     rax, rdx
0x1800058e3  mov     rdi, rcx
0x1800058e6  mov     qword ptr [rcx], 0
0x1800058ed  mov     [rcx+8], rdx
0x1800058f1  test    r8d, r8d
0x1800058f4  jz      short loc_180005932
0x1800058f6  lea     rdx, [r11+18h]; void *
0x1800058fa  mov     rcx, rax; this
0x1800058fd  call    ?Remove@CacheEngine@@QEAAPEAVCacheEntry@@PEBX@Z; CacheEngine::Remove(void const *)
0x180005902  mov     rbx, rax
0x180005905  mov     rcx, [rdi]; this
0x180005908  cmp     rax, rcx
0x18000590b  jz      short loc_180005925
0x18000590d  test    rcx, rcx
0x180005910  jz      short loc_180005917
0x180005912  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180005917  mov     [rdi], rbx
0x18000591a  test    rbx, rbx
0x18000591d  jz      short loc_180005932
0x18000591f  lock inc dword ptr [rbx+8]
0x180005923  jmp     short loc_18000592A
0x180005925  test    rbx, rbx
0x180005928  jz      short loc_180005932
0x18000592a  mov     rcx, rbx; this
0x18000592d  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180005932  cmp     qword ptr [rdi], 0
0x180005936  jnz     short loc_180005952
0x180005938  mov     r8d, 80070057h; int
0x18000593e  lea     rdx, aSessionid; "sessionId"
0x180005945  lea     rcx, aSessionaccesso; "SessionAccessor::SessionAccessor"
0x18000594c  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
0x180005952  mov     rax, rdi
0x180005955  mov     rbx, [rsp+28h+arg_8]
0x18000595a  add     rsp, 20h
0x18000595e  pop     rdi
0x18000595f  retn
```
