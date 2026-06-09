# SetAllParameters

- ea: `0x18002dda0`
- end: `0x18002de30`
- name: `SetAllParameters`
- size: `144`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18002d88c`
- `0x18002d9fc`
- `0x18002dd20`
- `0x18002de38`
- `0x18002df00`

## callees

- `0x180001d3e`

## import_xrefs

- `NSI!NsiSetAllParametersEx` at `0x18002de11`
- `NSI!NsiSetAllParametersEx` at `0x18002de11`

## pseudocode

```c
__int64 __fastcall SetAllParameters(__int64 a1, __int64 a2, int a3, __int64 a4, int a5, __int64 a6, int a7, int a8)
{
  _BYTE v12[16]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v13; // [rsp+30h] [rbp-48h]
  int v14; // [rsp+38h] [rbp-40h]
  int v15; // [rsp+40h] [rbp-38h]
  int v16; // [rsp+44h] [rbp-34h]
  __int64 v17; // [rsp+48h] [rbp-30h]
  int v18; // [rsp+50h] [rbp-28h]
  __int64 v19; // [rsp+58h] [rbp-20h]
  int v20; // [rsp+60h] [rbp-18h]

  memset_0(v12, 0, 0x48u);
  v16 = a8;
  v18 = a5;
  v19 = a6;
  v20 = a7;
  v13 = a2;
  v14 = a3;
  v15 = 1;
  v17 = a4;
  return NsiSetAllParametersEx(v12);
}

```

## disassembly

```asm
0x18002dda0  mov     [rsp+arg_0], rbx
0x18002dda5  mov     [rsp+arg_8], rsi
0x18002ddaa  push    rdi
0x18002ddab  sub     rsp, 70h
0x18002ddaf  mov     rbx, rdx
0x18002ddb2  lea     rcx, [rsp+78h+var_58]; void *
0x18002ddb7  xor     edx, edx; Val
0x18002ddb9  mov     edi, r8d
0x18002ddbc  mov     rsi, r9
0x18002ddbf  lea     r8d, [rdx+48h]; Size
0x18002ddc3  call    memset_0
0x18002ddc8  mov     eax, [rsp+78h+arg_38]
0x18002ddcf  lea     rcx, [rsp+78h+var_58]
0x18002ddd4  mov     [rsp+78h+var_34], eax
0x18002ddd8  mov     eax, [rsp+78h+arg_20]
0x18002dddf  mov     [rsp+78h+var_28], eax
0x18002dde3  mov     rax, [rsp+78h+arg_28]
0x18002ddeb  mov     [rsp+78h+var_20], rax
0x18002ddf0  mov     eax, [rsp+78h+arg_30]
0x18002ddf7  mov     [rsp+78h+var_18], eax
0x18002ddfb  mov     [rsp+78h+var_48], rbx
0x18002de00  mov     [rsp+78h+var_40], edi
0x18002de04  mov     [rsp+78h+var_38], 1
0x18002de0c  mov     [rsp+78h+var_30], rsi
0x18002de11  call    cs:__imp_NsiSetAllParametersEx
0x18002de18  nop     dword ptr [rax+rax+00h]
0x18002de1d  lea     r11, [rsp+78h+var_8]
0x18002de22  mov     rbx, [r11+10h]
0x18002de26  mov     rsi, [r11+18h]
0x18002de2a  mov     rsp, r11
0x18002de2d  pop     rdi
0x18002de2e  retn
```
