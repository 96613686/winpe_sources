# CHandleT<_TP_WAIT *,ThreadPoolWaitTrait>::~CHandleT<_TP_WAIT *,ThreadPoolWaitTrait>(void)

- ea: `0x180003158`
- end: `0x18000316f`
- name: `??1?$CHandleT@PEAU_TP_WAIT@@UThreadPoolWaitTrait@@@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(struct _TP_WAIT **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003224`

## callees

- `0x180003158`

## import_xrefs

- `KERNEL32!CloseThreadpoolWait` at `0x180003164`
- `KERNEL32!CloseThreadpoolWait` at `0x180003164`

## pseudocode

```c
void __fastcall CHandleT<_TP_WAIT *,ThreadPoolWaitTrait>::~CHandleT<_TP_WAIT *,ThreadPoolWaitTrait>(
        struct _TP_WAIT **a1)
{
  struct _TP_WAIT *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolWait(v1);
}

```

## disassembly

```asm
0x180003158  sub     rsp, 28h
0x18000315c  mov     rcx, [rcx]; pwa
0x18000315f  test    rcx, rcx
0x180003162  jz      short loc_18000316A
0x180003164  call    cs:__imp_CloseThreadpoolWait
0x18000316a  add     rsp, 28h
0x18000316e  retn
```
