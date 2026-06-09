# RemoveAndFreeOfflineUrlCacheEntry(_OFFLINE_URL_CACHE_ENTRY *)

- ea: `0x180020108`
- end: `0x180020138`
- name: `?RemoveAndFreeOfflineUrlCacheEntry@@YAXPEAU_OFFLINE_URL_CACHE_ENTRY@@@Z`
- size: `48`
- prototype: `void __fastcall(struct _OFFLINE_URL_CACHE_ENTRY *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017ed0`
- `0x18001ac80`
- `0x180020140`
- `0x1800201e0`

## callees

- `0x18000a990`
- `0x180020108`

## pseudocode

```c
void __fastcall RemoveAndFreeOfflineUrlCacheEntry(struct _OFFLINE_URL_CACHE_ENTRY *a1)
{
  __int64 v1; // r8
  __int64 v2; // r8

  v1 = *((_QWORD *)a1 + 6);
  if ( v1 )
    *(_QWORD *)(v1 + 56) = *((_QWORD *)a1 + 7);
  v2 = *((_QWORD *)a1 + 7);
  if ( v2 )
    *(_QWORD *)(v2 + 48) = *((_QWORD *)a1 + 6);
  else
    pOfflineUrlCacheHead = (struct _OFFLINE_URL_CACHE_ENTRY *)*((_QWORD *)a1 + 6);
  operator delete(a1);
}

```

## disassembly

```asm
0x180020108  mov     r8, [rcx+30h]
0x18002010c  test    r8, r8
0x18002010f  jz      short loc_180020119
0x180020111  mov     rax, [rcx+38h]
0x180020115  mov     [r8+38h], rax
0x180020119  mov     r8, [rcx+38h]
0x18002011d  mov     rax, [rcx+30h]
0x180020121  test    r8, r8
0x180020124  jz      short loc_18002012C
0x180020126  mov     [r8+30h], rax
0x18002012a  jmp     short loc_180020133
0x18002012c  mov     cs:?pOfflineUrlCacheHead@@3PEAU_OFFLINE_URL_CACHE_ENTRY@@EA, rax; _OFFLINE_URL_CACHE_ENTRY * pOfflineUrlCacheHead
0x180020133  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
