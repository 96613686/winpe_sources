# CSidCacheItem::IsEqual(void *)

- ea: `0x18001b540`
- end: `0x18001b551`
- name: `?IsEqual@CSidCacheItem@@UEAAHPEAX@Z`
- size: `17`
- prototype: `__int64 __fastcall(CSidCacheItem *__hidden this, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x18001b54a`

## pseudocode

```c
BOOL __fastcall CSidCacheItem::IsEqual(PSID *this, void *a2)
{
  return EqualSid(a2, this[4]);
}

```

## disassembly

```asm
0x18001b540  mov     rax, rdx
0x18001b543  mov     rdx, [rcx+20h]
0x18001b547  mov     rcx, rax
0x18001b54a  jmp     cs:__imp_EqualSid
```
