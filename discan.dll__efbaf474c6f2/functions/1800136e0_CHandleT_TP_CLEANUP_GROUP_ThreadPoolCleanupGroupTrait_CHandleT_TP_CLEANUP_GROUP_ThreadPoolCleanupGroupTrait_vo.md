# CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>::~CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>(void)

- ea: `0x1800136e0`
- end: `0x1800136f7`
- name: `??1?$CHandleT@PEAU_TP_CLEANUP_GROUP@@UThreadPoolCleanupGroupTrait@@@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(struct _TP_CLEANUP_GROUP **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180013820`
- `0x180013868`
- `0x180019a98`
- `0x180037da0`

## callees

- `0x1800136e0`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800136ec`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800136ec`

## pseudocode

```c
void __fastcall CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>::~CHandleT<_TP_CLEANUP_GROUP *,ThreadPoolCleanupGroupTrait>(
        struct _TP_CLEANUP_GROUP **a1)
{
  struct _TP_CLEANUP_GROUP *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolCleanupGroup(v1);
}

```

## disassembly

```asm
0x1800136e0  sub     rsp, 28h
0x1800136e4  mov     rcx, [rcx]; ptpcg
0x1800136e7  test    rcx, rcx
0x1800136ea  jz      short loc_1800136F2
0x1800136ec  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800136f2  add     rsp, 28h
0x1800136f6  retn
```
