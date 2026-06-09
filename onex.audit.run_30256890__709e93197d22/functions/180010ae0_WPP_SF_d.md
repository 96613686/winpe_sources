# WPP_SF_d

- ea: `0x180010ae0`
- end: `0x180010b19`
- name: `WPP_SF_d`
- size: `57`
- prototype: ``
- caller_count: `140`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001510`
- `0x180002470`
- `0x180002a30`
- `0x180002f64`
- `0x180003120`
- `0x1800037d0`
- `0x180003c80`
- `0x180004780`
- `0x180004b40`
- `0x180005640`
- `0x180005b00`
- `0x1800067e0`
- `0x180006bd0`
- `0x180007fb0`
- `0x1800084a0`
- `0x180008d40`
- `0x180009300`
- `0x180009540`
- `0x180009be0`
- `0x18000a318`
- `0x18000a550`
- `0x18000ade0`
- `0x18000b330`
- `0x18000ba30`
- `0x18000d310`
- `0x18000dd40`
- `0x18000e230`
- `0x18000ecd0`
- `0x18000f8c0`
- `0x18000fd20`
- `0x180010820`
- `0x180010d40`
- `0x180010f20`
- `0x180011310`
- `0x180011abc`
- `0x180011d08`
- `0x180012070`
- `0x180012478`
- `0x1800129b0`
- `0x180012cc0`
- `0x180012f90`
- `0x180013050`
- `0x180013560`
- `0x1800137f0`
- `0x180013a30`
- `0x180013e50`
- `0x180014190`
- `0x180014a20`
- `0x180014e50`
- `0x180015300`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180010b0e`
- `ntdll!EtwTraceMessage` at `0x180010b0e`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x180010ae0  mov     [rsp+arg_18], r9d
0x180010ae5  sub     rsp, 48h
0x180010ae9  mov     [rsp+48h+var_18], 0
0x180010af2  lea     rax, [rsp+48h+arg_18]
0x180010af7  movzx   r9d, dx
0x180010afb  mov     edx, 2Bh ; '+'
0x180010b00  mov     [rsp+48h+var_20], 4
0x180010b09  mov     [rsp+48h+var_28], rax
0x180010b0e  call    cs:__imp_EtwTraceMessage
0x180010b14  add     rsp, 48h
0x180010b18  retn
```
