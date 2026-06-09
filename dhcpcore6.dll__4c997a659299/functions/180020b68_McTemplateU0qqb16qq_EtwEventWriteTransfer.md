# McTemplateU0qqb16qq_EtwEventWriteTransfer

- ea: `0x180020b68`
- end: `0x180020c15`
- name: `McTemplateU0qqb16qq_EtwEventWriteTransfer`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025094`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0qqb16qq_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        char a6,
        char a7)
{
  _BYTE v8[16]; // [rsp+30h] [rbp-31h] BYREF
  int *v9; // [rsp+40h] [rbp-21h]
  __int64 v10; // [rsp+48h] [rbp-19h]
  int *v11; // [rsp+50h] [rbp-11h]
  __int64 v12; // [rsp+58h] [rbp-9h]
  __int64 v13; // [rsp+60h] [rbp-1h]
  __int64 v14; // [rsp+68h] [rbp+7h]
  char *v15; // [rsp+70h] [rbp+Fh]
  __int64 v16; // [rsp+78h] [rbp+17h]
  char *v17; // [rsp+80h] [rbp+1Fh]
  __int64 v18; // [rsp+88h] [rbp+27h]
  int v19; // [rsp+C0h] [rbp+5Fh] BYREF
  int v20; // [rsp+C8h] [rbp+67h] BYREF

  v20 = a4;
  v19 = a3;
  v10 = 4;
  v9 = &v19;
  v12 = 4;
  v11 = &v20;
  v13 = a5;
  v15 = &a6;
  v17 = &a7;
  v14 = 16;
  v16 = 4;
  v18 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(
           &Dhcpv6_Context,
           (__int64)AbandonSolicitInCSSinceV6Stateless,
           a3,
           6,
           (__int64)v8);
}

```

## disassembly

```asm
0x180020b68  mov     [rsp-8+arg_18], r9d
0x180020b6d  mov     [rsp-8+arg_10], r8d
0x180020b72  push    rbp
0x180020b73  lea     rbp, [rsp-3Fh]
0x180020b78  sub     rsp, 0A0h
0x180020b7f  mov     rax, cs:__security_cookie
0x180020b86  xor     rax, rsp
0x180020b89  mov     [rbp+3Fh+var_10], rax
0x180020b8d  lea     rax, [rbp+3Fh+arg_10]
0x180020b91  mov     [rbp+3Fh+var_58], 4
0x180020b99  mov     [rbp+3Fh+var_60], rax
0x180020b9d  lea     rdx, AbandonSolicitInCSSinceV6Stateless
0x180020ba4  lea     rax, [rbp+3Fh+arg_18]
0x180020ba8  mov     [rbp+3Fh+var_48], 4
0x180020bb0  mov     [rbp+3Fh+var_50], rax
0x180020bb4  lea     rcx, Dhcpv6_Context
0x180020bbb  mov     rax, [rbp+3Fh+arg_20]
0x180020bbf  mov     r9d, 6
0x180020bc5  mov     [rbp+3Fh+var_40], rax
0x180020bc9  lea     rax, [rbp+3Fh+arg_28]
0x180020bcd  mov     [rbp+3Fh+var_30], rax
0x180020bd1  lea     rax, [rbp+3Fh+arg_30]
0x180020bd5  mov     [rbp+3Fh+var_20], rax
0x180020bd9  lea     rax, [rbp+3Fh+var_70]
0x180020bdd  mov     [rsp+0A0h+var_80], rax
0x180020be2  mov     [rbp+3Fh+var_38], 10h
0x180020bea  mov     [rbp+3Fh+var_28], 4
0x180020bf2  mov     [rbp+3Fh+var_18], 4
0x180020bfa  call    McGenEventWrite_EtwEventWriteTransfer
0x180020bff  mov     rcx, [rbp+3Fh+var_10]
0x180020c03  xor     rcx, rsp; StackCookie
0x180020c06  call    __security_check_cookie
0x180020c0b  add     rsp, 0A0h
0x180020c12  pop     rbp
0x180020c13  retn
```
