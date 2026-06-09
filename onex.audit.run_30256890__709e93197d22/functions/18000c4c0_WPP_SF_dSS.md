# WPP_SF_dSS

- ea: `0x18000c4c0`
- end: `0x18000c597`
- name: `WPP_SF_dSS`
- size: `215`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001ac0`
- `0x180002020`
- `0x180002f64`
- `0x18000ba30`
- `0x18000d310`
- `0x1800183c0`
- `0x18001be88`
- `0x18001e290`
- `0x18002830c`

## callees

- `0x18000c4c0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000c57e`
- `ntdll!EtwTraceMessage` at `0x18000c57e`

## pseudocode

```c
__int64 __fastcall WPP_SF_dSS(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, __int64 a5, __int64 a6)
{
  __int64 v6; // r9
  __int64 v7; // rax
  bool v8; // zf
  int v10; // [rsp+88h] [rbp+20h] BYREF

  v10 = a4;
  v6 = -1;
  if ( a6 )
  {
    v7 = -1;
    do
      v8 = *(_WORD *)(a6 + 2 * v7++ + 2) == 0;
    while ( !v8 );
  }
  if ( a5 )
  {
    do
      v8 = *(_WORD *)(a5 + 2 * v6++ + 2) == 0;
    while ( !v8 );
  }
  return EtwTraceMessage(a1, 43, a3, a2, &v10);
}

```

## disassembly

```asm
0x18000c4c0  mov     [rsp+arg_0], rbx
0x18000c4c5  mov     [rsp+arg_18], r9d
0x18000c4ca  push    rdi
0x18000c4cb  sub     rsp, 60h
0x18000c4cf  mov     r10, [rsp+68h+arg_28]
0x18000c4d7  mov     rbx, rcx
0x18000c4da  mov     r11d, 0Ah
0x18000c4e0  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18000c4e7  test    r10, r10
0x18000c4ea  jz      loc_18000C58F
0x18000c4f0  mov     rax, r9
0x18000c4f3  cmp     word ptr [r10+rax*2+2], 0
0x18000c4fa  lea     rax, [rax+1]
0x18000c4fe  jnz     short loc_18000C4F3
0x18000c500  lea     rcx, ds:2[rax*2]
0x18000c508  mov     rax, [rsp+68h+arg_20]
0x18000c510  lea     rdi, aNull_0; "NULL"
0x18000c517  test    r10, r10
0x18000c51a  cmovz   r10, rdi
0x18000c51e  test    rax, rax
0x18000c521  jz      short loc_18000C53B
0x18000c523  cmp     word ptr [rax+r9*2+2], 0
0x18000c52a  lea     r9, [r9+1]
0x18000c52e  jnz     short loc_18000C523
0x18000c530  lea     r11, ds:2[r9*2]
0x18000c538  test    rax, rax
0x18000c53b  mov     [rsp+68h+var_18], 0
0x18000c544  cmovz   rax, rdi
0x18000c548  mov     [rsp+68h+var_20], rcx
0x18000c54d  mov     rcx, rbx
0x18000c550  mov     [rsp+68h+var_28], r10
0x18000c555  mov     [rsp+68h+var_30], r11
0x18000c55a  mov     [rsp+68h+var_38], rax
0x18000c55f  lea     rax, [rsp+68h+arg_18]
0x18000c567  movzx   r9d, dx
0x18000c56b  mov     edx, 2Bh ; '+'
0x18000c570  mov     [rsp+68h+var_40], 4
0x18000c579  mov     [rsp+68h+var_48], rax
0x18000c57e  call    cs:__imp_EtwTraceMessage
0x18000c584  mov     rbx, [rsp+68h+arg_0]
0x18000c589  add     rsp, 60h
0x18000c58d  pop     rdi
0x18000c58e  retn
0x18000c58f  mov     rcx, r11
0x18000c592  jmp     loc_18000C508
```
