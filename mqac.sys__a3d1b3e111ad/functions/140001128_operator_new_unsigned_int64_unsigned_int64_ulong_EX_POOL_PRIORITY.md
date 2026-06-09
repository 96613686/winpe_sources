# operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)

- ea: `0x140001128`
- end: `0x140001167`
- name: `??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z`
- size: `63`
- prototype: `void *__fastcall(unsigned __int64, unsigned __int64, unsigned int, enum _EX_POOL_PRIORITY)`
- caller_count: `39`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011ac`
- `0x140003094`
- `0x140004d64`
- `0x1400050c8`
- `0x14000533c`
- `0x1400058fc`
- `0x140005cec`
- `0x140007460`
- `0x1400095e0`
- `0x14000bf14`
- `0x14000c100`
- `0x14000c388`
- `0x14000c5f0`
- `0x14000c914`
- `0x14000cef8`
- `0x14000da8c`
- `0x14000e30c`
- `0x14000e488`
- `0x14000e5f4`
- `0x14000e710`
- `0x14000e9a8`
- `0x14000efc8`
- `0x14000f204`
- `0x14000f390`
- `0x14000f54c`
- `0x14000fbbc`
- `0x140010568`
- `0x140011300`
- `0x140011ad0`
- `0x140014a58`
- `0x1400152d0`
- `0x140018c5c`
- `0x14001cc6c`
- `0x14001cf7c`
- `0x14001e768`
- `0x1400204d0`
- `0x140020658`
- `0x1400209b8`
- `0x14002186c`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x140001155`
- `ntoskrnl!ExAllocatePool3` at `0x140001155`

## pseudocode

```c
__int64 __fastcall operator new(__int64 a1, __int64 a2, __int64 a3, enum _EX_POOL_PRIORITY a4)
{
  __int64 v5; // [rsp+30h] [rbp-18h] BYREF
  enum _EX_POOL_PRIORITY v6; // [rsp+38h] [rbp-10h]
  int v7; // [rsp+3Ch] [rbp-Ch]

  v6 = a4;
  v7 = 0;
  v5 = 1;
  return ExAllocatePool3(a2, a1, a3, &v5, 1);
}

```

## disassembly

```asm
0x140001128  sub     rsp, 48h
0x14000112c  mov     rax, rdx
0x14000112f  mov     [rsp+48h+var_10], r9d
0x140001134  mov     edx, 1
0x140001139  mov     [rsp+48h+var_C], 0
0x140001141  mov     [rsp+48h+var_18], rdx
0x140001146  lea     r9, [rsp+48h+var_18]
0x14000114b  mov     [rsp+48h+var_28], edx
0x14000114f  mov     rdx, rcx
0x140001152  mov     rcx, rax
0x140001155  call    cs:__imp_ExAllocatePool3
0x14000115c  nop     dword ptr [rax+rax+00h]
0x140001161  add     rsp, 48h
0x140001165  retn
```
