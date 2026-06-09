# CTVOCache::RemoveCacheEntry(_TVO_CACHE_ENTRY *,int)

- ea: `0x180012e1c`
- end: `0x180012e59`
- name: `?RemoveCacheEntry@CTVOCache@@QEAAXPEAU_TVO_CACHE_ENTRY@@H@Z`
- size: `61`
- prototype: `void __fastcall(CTVOCache *this, struct _TVO_CACHE_ENTRY *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f80`
- `0x18001e410`

## callees

- `0x180012f60`

## import_xrefs

- `CRYPT32!I_CryptRemoveLruEntry` at `0x180012e52`

## pseudocode

```c
void __fastcall CTVOCache::RemoveCacheEntry(CTVOCache *this, struct _TVO_CACHE_ENTRY *a2, int a3)
{
  __int64 v5; // rdx

  RemoveCrlPreFetchEntry(a2);
  v5 = 4;
  if ( a3 != 1 )
    v5 = 0;
  I_CryptRemoveLruEntry(*((_QWORD *)a2 + 15), v5, 0);
}

```

## disassembly

```asm
0x180012e1c  mov     [rsp+arg_0], rbx
0x180012e21  push    rdi
0x180012e22  sub     rsp, 20h
0x180012e26  mov     rcx, rdx; struct _TVO_CACHE_ENTRY *
0x180012e29  mov     ebx, r8d
0x180012e2c  mov     rdi, rdx
0x180012e2f  call    ?RemoveCrlPreFetchEntry@@YAXPEAU_TVO_CACHE_ENTRY@@@Z; RemoveCrlPreFetchEntry(_TVO_CACHE_ENTRY *)
0x180012e34  mov     rcx, [rdi+78h]
0x180012e38  xor     eax, eax
0x180012e3a  cmp     ebx, 1
0x180012e3d  mov     edx, 4
0x180012e42  cmovnz  edx, eax
0x180012e45  xor     r8d, r8d
0x180012e48  mov     rbx, [rsp+28h+arg_0]
0x180012e4d  add     rsp, 20h
0x180012e51  pop     rdi
0x180012e52  jmp     cs:__imp_I_CryptRemoveLruEntry
```
