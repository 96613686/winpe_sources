# CdPerformDevIoCtrl

- ea: `0x14000fcb0`
- end: `0x14000fcf2`
- name: `CdPerformDevIoCtrl`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140013e2c`
- `0x1400142d8`
- `0x140015090`

## callees

- `0x14000fcf8`

## pseudocode

```c
NTSTATUS __fastcall CdPerformDevIoCtrl(
        __int64 a1,
        ULONG a2,
        struct _DEVICE_OBJECT *a3,
        void *a4,
        ULONG a5,
        int a6,
        char a7,
        struct _IO_STATUS_BLOCK *a8)
{
  __int64 v9; // [rsp+38h] [rbp-20h]

  return CdPerformDevIoCtrlEx(a1, a2, a3, 0, 0, a4, a5, v9, a7, a8);
}

```

## disassembly

```asm
0x14000fcb0  sub     rsp, 58h
0x14000fcb4  mov     rax, [rsp+58h+arg_38]
0x14000fcbc  mov     [rsp+58h+var_10], rax
0x14000fcc1  mov     al, [rsp+58h+arg_30]
0x14000fcc8  mov     [rsp+58h+var_18], al
0x14000fccc  mov     eax, [rsp+58h+arg_20]
0x14000fcd3  mov     [rsp+58h+var_28], eax
0x14000fcd7  mov     [rsp+58h+var_30], r9
0x14000fcdc  xor     r9d, r9d
0x14000fcdf  mov     [rsp+58h+var_38], 0
0x14000fce7  call    CdPerformDevIoCtrlEx
0x14000fcec  add     rsp, 58h
0x14000fcf0  retn
```
