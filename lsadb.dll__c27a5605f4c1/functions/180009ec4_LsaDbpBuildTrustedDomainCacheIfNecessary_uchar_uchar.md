# LsaDbpBuildTrustedDomainCacheIfNecessary(uchar,uchar)

- ea: `0x180009ec4`
- end: `0x180009f47`
- name: `?LsaDbpBuildTrustedDomainCacheIfNecessary@@YAJEE@Z`
- size: `131`
- prototype: `__int64 __fastcall(unsigned __int8, unsigned __int8)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800099b4`
- `0x18000b050`
- `0x18000bae8`
- `0x18000beb4`
- `0x18000bf70`
- `0x18000bff4`
- `0x1800159b0`
- `0x180016040`
- `0x18001a6d8`
- `0x18002a15c`

## callees

- `0x180009b24`
- `0x180009ec4`

## import_xrefs

- `LSASRV!LsapDbExpConvertReadLockTrustedDomainListToExclusive` at `0x180009f0a`
- `LSASRV!LsapDbExpConvertReadLockTrustedDomainListToExclusive` at `0x180009f0a`
- `LSASRV!LsapDbExpIsCacheBuilding` at `0x180009efc`
- `LSASRV!LsapDbExpIsCacheBuilding` at `0x180009efc`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180009ee2`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180009ee2`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180009f2f`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180009f2f`
- `LSASRV!LsapDbExpIsCacheValid` at `0x180009eed`
- `LSASRV!LsapDbExpIsCacheValid` at `0x180009f15`
- `LSASRV!LsapDbExpIsCacheValid` at `0x180009eed`
- `LSASRV!LsapDbExpIsCacheValid` at `0x180009f15`

## pseudocode

```c
__int64 __fastcall LsaDbpBuildTrustedDomainCacheIfNecessary(__int64 a1, char a2)
{
  unsigned int v2; // edi
  char v4; // si
  __int64 v5; // rcx

  v2 = 0;
  v4 = a1;
  if ( !(_BYTE)a1 && !a2 )
    LsapDbExpAcquireReadLockTrustedDomainList(a1);
  if ( !(unsigned __int8)LsapDbExpIsCacheValid(2) && !(unsigned __int8)LsapDbExpIsCacheBuilding(2) )
  {
    if ( !a2 )
      LsapDbExpConvertReadLockTrustedDomainListToExclusive();
    if ( !(unsigned __int8)LsapDbExpIsCacheValid(2) )
      v2 = LsaDbpBuildTrustedDomainCache();
  }
  if ( !v4 && !a2 )
    LsapDbExpReleaseLockTrustedDomainList(v5);
  return v2;
}

```

## disassembly

```asm
0x180009ec4  mov     [rsp+arg_0], rbx
0x180009ec9  mov     [rsp+arg_8], rsi
0x180009ece  push    rdi
0x180009ecf  sub     rsp, 20h
0x180009ed3  xor     edi, edi
0x180009ed5  mov     bl, dl
0x180009ed7  mov     sil, cl
0x180009eda  test    cl, cl
0x180009edc  jnz     short loc_180009EE8
0x180009ede  test    dl, dl
0x180009ee0  jnz     short loc_180009EE8
0x180009ee2  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x180009ee8  mov     ecx, 2
0x180009eed  call    cs:__imp_LsapDbExpIsCacheValid
0x180009ef3  test    al, al
0x180009ef5  jnz     short loc_180009F26
0x180009ef7  mov     ecx, 2
0x180009efc  call    cs:__imp_LsapDbExpIsCacheBuilding
0x180009f02  test    al, al
0x180009f04  jnz     short loc_180009F26
0x180009f06  test    bl, bl
0x180009f08  jnz     short loc_180009F10
0x180009f0a  call    cs:__imp_LsapDbExpConvertReadLockTrustedDomainListToExclusive
0x180009f10  mov     ecx, 2
0x180009f15  call    cs:__imp_LsapDbExpIsCacheValid
0x180009f1b  test    al, al
0x180009f1d  jnz     short loc_180009F26
0x180009f1f  call    ?LsaDbpBuildTrustedDomainCache@@YAJXZ; LsaDbpBuildTrustedDomainCache(void)
0x180009f24  mov     edi, eax
0x180009f26  test    sil, sil
0x180009f29  jnz     short loc_180009F35
0x180009f2b  test    bl, bl
0x180009f2d  jnz     short loc_180009F35
0x180009f2f  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180009f35  mov     rbx, [rsp+28h+arg_0]
0x180009f3a  mov     eax, edi
0x180009f3c  mov     rsi, [rsp+28h+arg_8]
0x180009f41  add     rsp, 20h
0x180009f45  pop     rdi
0x180009f46  retn
```
