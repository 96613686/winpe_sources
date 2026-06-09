# CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(void)

- ea: `0x180003180`
- end: `0x180003197`
- name: `??1?$CHandleT@PEAU_TP_WORK@@UThreadPoolWorkTrait@@@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(struct _TP_WORK **)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003224`
- `0x180013948`
- `0x18001bb24`
- `0x18001c06c`
- `0x180024b24`
- `0x180037e46`
- `0x1800384e6`
- `0x1800384ff`

## callees

- `0x180003180`

## import_xrefs

- `KERNEL32!CloseThreadpoolWork` at `0x18000318c`
- `KERNEL32!CloseThreadpoolWork` at `0x18000318c`

## pseudocode

```c
void __fastcall CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(
        struct _TP_WORK **a1)
{
  struct _TP_WORK *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolWork(v1);
}

```

## disassembly

```asm
0x180003180  sub     rsp, 28h
0x180003184  mov     rcx, [rcx]; pwk
0x180003187  test    rcx, rcx
0x18000318a  jz      short loc_180003192
0x18000318c  call    cs:__imp_CloseThreadpoolWork
0x180003192  add     rsp, 28h
0x180003196  retn
```
