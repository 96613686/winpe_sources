# CTVOCache::~CTVOCache(void)

- ea: `0x18001dd94`
- end: `0x18001ddb0`
- name: `??1CTVOCache@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(CTVOCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001dd5c`

## callees

- `0x18001dd94`

## import_xrefs

- `CRYPT32!I_CryptFreeLruCache` at `0x18001dda5`
- `CRYPT32!I_CryptFreeLruCache` at `0x18001dda5`

## pseudocode

```c
void __fastcall CTVOCache::~CTVOCache(CTVOCache *this)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)this;
  if ( v1 )
    I_CryptFreeLruCache(v1, 0, 0);
}

```

## disassembly

```asm
0x18001dd94  sub     rsp, 28h
0x18001dd98  mov     rcx, [rcx]
0x18001dd9b  test    rcx, rcx
0x18001dd9e  jz      short loc_18001DDAB
0x18001dda0  xor     r8d, r8d
0x18001dda3  xor     edx, edx
0x18001dda5  call    cs:__imp_I_CryptFreeLruCache
0x18001ddab  add     rsp, 28h
0x18001ddaf  retn
```
