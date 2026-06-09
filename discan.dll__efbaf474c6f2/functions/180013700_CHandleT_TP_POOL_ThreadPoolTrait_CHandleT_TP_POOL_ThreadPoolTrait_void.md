# CHandleT<_TP_POOL *,ThreadPoolTrait>::~CHandleT<_TP_POOL *,ThreadPoolTrait>(void)

- ea: `0x180013700`
- end: `0x180013717`
- name: `??1?$CHandleT@PEAU_TP_POOL@@UThreadPoolTrait@@@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(struct _TP_POOL **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180013868`
- `0x180037db6`

## callees

- `0x180013700`

## import_xrefs

- `KERNEL32!CloseThreadpool` at `0x18001370c`
- `KERNEL32!CloseThreadpool` at `0x18001370c`

## pseudocode

```c
void __fastcall CHandleT<_TP_POOL *,ThreadPoolTrait>::~CHandleT<_TP_POOL *,ThreadPoolTrait>(struct _TP_POOL **a1)
{
  struct _TP_POOL *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpool(v1);
}

```

## disassembly

```asm
0x180013700  sub     rsp, 28h
0x180013704  mov     rcx, [rcx]; ptpp
0x180013707  test    rcx, rcx
0x18001370a  jz      short loc_180013712
0x18001370c  call    cs:__imp_CloseThreadpool
0x180013712  add     rsp, 28h
0x180013716  retn
```
