# LsaDbINotifyGCStatusChange(uchar)

- ea: `0x180024e10`
- end: `0x180024e4a`
- name: `?LsaDbINotifyGCStatusChange@@YAXE@Z`
- size: `58`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180024e10`
- `0x180026594`

## import_xrefs

- `LSASRV!LsapDbExpConvertReadLockTrustedDomainListToExclusive` at `0x180024e34`
- `LSASRV!LsapDbExpConvertReadLockTrustedDomainListToExclusive` at `0x180024e34`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180024e21`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180024e21`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180024e3f`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180024e3f`

## pseudocode

```c
void __fastcall LsaDbINotifyGCStatusChange(__int64 a1)
{
  __int64 v1; // rcx

  if ( !DcInRootDomain && !(_BYTE)a1 )
  {
    LsapDbExpAcquireReadLockTrustedDomainList(a1);
    if ( *((_BYTE *)g_FTCache + 2) )
    {
      LsapDbExpConvertReadLockTrustedDomainListToExclusive();
      LsaDbpForestTrustCacheSetInvalid();
    }
    LsapDbExpReleaseLockTrustedDomainList(v1);
  }
}

```

## disassembly

```asm
0x180024e10  sub     rsp, 28h
0x180024e14  cmp     cs:?DcInRootDomain@@3EA, 0; uchar DcInRootDomain
0x180024e1b  jnz     short loc_180024E45
0x180024e1d  test    cl, cl
0x180024e1f  jnz     short loc_180024E45
0x180024e21  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x180024e27  mov     rax, cs:?g_FTCache@@3PEAVFTCache@@EA; FTCache * g_FTCache
0x180024e2e  cmp     byte ptr [rax+2], 0
0x180024e32  jz      short loc_180024E3F
0x180024e34  call    cs:__imp_LsapDbExpConvertReadLockTrustedDomainListToExclusive
0x180024e3a  call    ?LsaDbpForestTrustCacheSetInvalid@@YAXXZ; LsaDbpForestTrustCacheSetInvalid(void)
0x180024e3f  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180024e45  add     rsp, 28h
0x180024e49  retn
```
