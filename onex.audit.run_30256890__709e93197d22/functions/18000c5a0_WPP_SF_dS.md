# WPP_SF_dS

- ea: `0x18000c5a0`
- end: `0x18000c624`
- name: `WPP_SF_dS`
- size: `132`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001ac0`
- `0x180002020`
- `0x1800067e0`
- `0x18000b330`
- `0x18000ba30`
- `0x180012660`
- `0x1800127a0`
- `0x180013050`
- `0x1800183c0`
- `0x18001ac0c`
- `0x18001be88`
- `0x18001efbc`
- `0x18001fb58`
- `0x180026930`

## callees

- `0x18000c5a0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000c612`
- `ntdll!EtwTraceMessage` at `0x18000c612`

## pseudocode

```c
__int64 __fastcall WPP_SF_dS(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v5; // rax
  int v8; // [rsp+78h] [rbp+20h] BYREF

  v8 = a4;
  if ( a5 )
  {
    v5 = -1;
    while ( *(_WORD *)(a5 + 2 * v5++ + 2) != 0 )
      ;
  }
  return EtwTraceMessage(a1, 43, a3, a2, &v8);
}

```

## disassembly

```asm
0x18000c5a0  mov     [rsp+arg_18], r9d
0x18000c5a5  sub     rsp, 58h
0x18000c5a9  mov     r9, [rsp+58h+arg_20]
0x18000c5b1  test    r9, r9
0x18000c5b4  jz      short loc_18000C61D
0x18000c5b6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c5bd  nop     dword ptr [rax]
0x18000c5c0  cmp     word ptr [r9+rax*2+2], 0
0x18000c5c7  lea     rax, [rax+1]
0x18000c5cb  jnz     short loc_18000C5C0
0x18000c5cd  lea     rax, ds:2[rax*2]
0x18000c5d5  mov     [rsp+58h+var_18], 0
0x18000c5de  lea     r10, aNull_0; "NULL"
0x18000c5e5  mov     [rsp+58h+var_20], rax
0x18000c5ea  test    r9, r9
0x18000c5ed  lea     rax, [rsp+58h+arg_18]
0x18000c5f2  cmovz   r9, r10
0x18000c5f6  mov     [rsp+58h+var_28], r9
0x18000c5fb  movzx   r9d, dx
0x18000c5ff  mov     edx, 2Bh ; '+'
0x18000c604  mov     [rsp+58h+var_30], 4
0x18000c60d  mov     [rsp+58h+var_38], rax
0x18000c612  call    cs:__imp_EtwTraceMessage
0x18000c618  add     rsp, 58h
0x18000c61c  retn
0x18000c61d  mov     eax, 0Ah
0x18000c622  jmp     short loc_18000C5D5
```
