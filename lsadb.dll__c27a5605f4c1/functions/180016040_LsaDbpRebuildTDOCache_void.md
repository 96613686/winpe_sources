# LsaDbpRebuildTDOCache(void)

- ea: `0x180016040`
- end: `0x180016084`
- name: `?LsaDbpRebuildTDOCache@@YAJXZ`
- size: `68`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180009ec4`
- `0x18000c400`
- `0x180016040`

## import_xrefs

- `LSASRV!LsapDbExpMakeCacheValid` at `0x180016070`
- `LSASRV!LsapDbExpMakeCacheValid` at `0x180016070`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180016046`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180016046`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180016076`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180016076`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180016051`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180016051`

## pseudocode

```c
__int64 __fastcall LsaDbpRebuildTDOCache(__int64 a1)
{
  __int64 v1; // rcx
  int v2; // ebx

  LsapDbExpAcquireWriteLockTrustedDomainList(a1);
  LsapDbExpMakeCacheInvalid(2);
  LsaDbpPurgeTrustedDomainCache();
  v2 = LsaDbpBuildTrustedDomainCacheIfNecessary(0, 1);
  if ( v2 >= 0 )
    LsapDbExpMakeCacheValid(2);
  LsapDbExpReleaseLockTrustedDomainList(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180016040  push    rbx
0x180016042  sub     rsp, 20h
0x180016046  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x18001604c  mov     ecx, 2
0x180016051  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x180016057  call    ?LsaDbpPurgeTrustedDomainCache@@YAXXZ; LsaDbpPurgeTrustedDomainCache(void)
0x18001605c  mov     dl, 1; unsigned __int8
0x18001605e  xor     ecx, ecx; unsigned __int8
0x180016060  call    ?LsaDbpBuildTrustedDomainCacheIfNecessary@@YAJEE@Z; LsaDbpBuildTrustedDomainCacheIfNecessary(uchar,uchar)
0x180016065  mov     ebx, eax
0x180016067  test    eax, eax
0x180016069  js      short loc_180016076
0x18001606b  mov     ecx, 2
0x180016070  call    cs:__imp_LsapDbExpMakeCacheValid
0x180016076  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18001607c  mov     eax, ebx
0x18001607e  add     rsp, 20h
0x180016082  pop     rbx
0x180016083  retn
```
