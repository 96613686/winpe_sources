# FatInitializeCacheMap

- ea: `0x140001858`
- end: `0x14000189b`
- name: `FatInitializeCacheMap`
- size: `67`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400018a4`
- `0x14000363c`
- `0x140023380`
- `0x140023df4`
- `0x140023f58`
- `0x14003ad44`
- `0x14003b9d0`
- `0x140040674`
- `0x14004573c`
- `0x140048848`
- `0x14004af08`

## callees

- `0x140001858`

## import_xrefs

- `ntoskrnl!CcInitializeCacheMap` at `0x14000186b`
- `ntoskrnl!CcInitializeCacheMap` at `0x14000186b`
- `ntoskrnl!CcSetAdditionalCacheAttributesEx` at `0x140001888`
- `ntoskrnl!CcSetAdditionalCacheAttributesEx` at `0x140001888`

## pseudocode

```c
void __fastcall FatInitializeCacheMap(
        struct _FILE_OBJECT *a1,
        struct _CC_FILE_SIZES *a2,
        BOOLEAN a3,
        struct _CACHE_MANAGER_CALLBACKS *a4,
        PVOID LazyWriteContext)
{
  CcInitializeCacheMap(a1, a2, a3, a4, LazyWriteContext);
  if ( FatDiskAccountingEnabled )
    CcSetAdditionalCacheAttributesEx(a1, 16);
}

```

## disassembly

```asm
0x140001858  push    rbx
0x14000185a  sub     rsp, 30h
0x14000185e  mov     rax, [rsp+38h+arg_20]
0x140001863  mov     rbx, rcx
0x140001866  mov     [rsp+38h+LazyWriteContext], rax; LazyWriteContext
0x14000186b  call    cs:__imp_CcInitializeCacheMap
0x140001872  nop     dword ptr [rax+rax+00h]
0x140001877  cmp     cs:FatDiskAccountingEnabled, 0
0x14000187e  jz      short loc_140001894
0x140001880  mov     edx, 10h
0x140001885  mov     rcx, rbx
0x140001888  call    cs:__imp_CcSetAdditionalCacheAttributesEx
0x14000188f  nop     dword ptr [rax+rax+00h]
0x140001894  add     rsp, 30h
0x140001898  pop     rbx
0x140001899  retn
```
