# UserSecurityContext::ReleaseNonCacheableCryptoProvider(void)

- ea: `0x1800175c0`
- end: `0x1800175e8`
- name: `?ReleaseNonCacheableCryptoProvider@UserSecurityContext@@AEAAXXZ`
- size: `40`
- prototype: `void __fastcall(UserSecurityContext *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016278`
- `0x1800166dc`

## callees

- `0x1800175c0`

## import_xrefs

- `ADVAPI32!CryptReleaseContext` at `0x1800175d4`
- `ADVAPI32!CryptReleaseContext` at `0x1800175d4`

## pseudocode

```c
void __fastcall UserSecurityContext::ReleaseNonCacheableCryptoProvider(UserSecurityContext *this)
{
  HCRYPTPROV v2; // rcx

  v2 = *((_QWORD *)this + 9);
  if ( v2 )
  {
    CryptReleaseContext(v2, 0);
    *((_QWORD *)this + 9) = 0;
  }
}

```

## disassembly

```asm
0x1800175c0  push    rbx
0x1800175c2  sub     rsp, 20h
0x1800175c6  mov     rbx, rcx
0x1800175c9  mov     rcx, [rcx+48h]; hProv
0x1800175cd  test    rcx, rcx
0x1800175d0  jz      short loc_1800175E2
0x1800175d2  xor     edx, edx; dwFlags
0x1800175d4  call    cs:__imp_CryptReleaseContext
0x1800175da  mov     qword ptr [rbx+48h], 0
0x1800175e2  add     rsp, 20h
0x1800175e6  pop     rbx
0x1800175e7  retn
```
