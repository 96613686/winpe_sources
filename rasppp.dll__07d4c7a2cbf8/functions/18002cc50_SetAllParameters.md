# SetAllParameters

- ea: `0x18002cc50`
- end: `0x18002ccd9`
- name: `SetAllParameters`
- size: `137`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c76c`
- `0x18002c8dc`
- `0x18002cbd4`
- `0x18002cce0`
- `0x18002cda0`

## callees

- `0x180001d3e`

## import_xrefs

- `NSI!NsiSetAllParametersEx` at `0x18002ccc1`
- `NSI!NsiSetAllParametersEx` at `0x18002ccc1`

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
0x18002cc50  mov     [rsp+arg_0], rbx
0x18002cc55  mov     [rsp+arg_8], rsi
0x18002cc5a  push    rdi
0x18002cc5b  sub     rsp, 70h
0x18002cc5f  mov     rbx, rdx
0x18002cc62  lea     rcx, [rsp+78h+var_58]; void *
0x18002cc67  xor     edx, edx; Val
0x18002cc69  mov     edi, r8d
0x18002cc6c  mov     rsi, r9
0x18002cc6f  lea     r8d, [rdx+48h]; Size
0x18002cc73  call    memset_0
0x18002cc78  mov     eax, [rsp+78h+arg_38]
0x18002cc7f  lea     rcx, [rsp+78h+var_58]
0x18002cc84  mov     [rsp+78h+var_34], eax
0x18002cc88  mov     eax, [rsp+78h+arg_20]
0x18002cc8f  mov     [rsp+78h+var_28], eax
0x18002cc93  mov     rax, [rsp+78h+arg_28]
0x18002cc9b  mov     [rsp+78h+var_20], rax
0x18002cca0  mov     eax, [rsp+78h+arg_30]
0x18002cca7  mov     [rsp+78h+var_18], eax
0x18002ccab  mov     [rsp+78h+var_48], rbx
0x18002ccb0  mov     [rsp+78h+var_40], edi
0x18002ccb4  mov     [rsp+78h+var_38], 1
0x18002ccbc  mov     [rsp+78h+var_30], rsi
0x18002ccc1  call    cs:__imp_NsiSetAllParametersEx
0x18002ccc7  lea     r11, [rsp+78h+var_8]
0x18002cccc  mov     rbx, [r11+10h]
0x18002ccd0  mov     rsi, [r11+18h]
0x18002ccd4  mov     rsp, r11
0x18002ccd7  pop     rdi
0x18002ccd8  retn
```
