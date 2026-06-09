# McTemplateU0qbr0qbr2qbr4qbr6_EtwEventWriteTransfer

- ea: `0x18002a810`
- end: `0x18002a8e6`
- name: `McTemplateU0qbr0qbr2qbr4qbr6_EtwEventWriteTransfer`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001564c`

## callees

- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0qbr0qbr2qbr4qbr6_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9,
        __int64 a10)
{
  _BYTE v11[16]; // [rsp+30h] [rbp-79h] BYREF
  int *v12; // [rsp+40h] [rbp-69h]
  __int64 v13; // [rsp+48h] [rbp-61h]
  __int64 v14; // [rsp+50h] [rbp-59h]
  int v15; // [rsp+58h] [rbp-51h]
  int v16; // [rsp+5Ch] [rbp-4Dh]
  int *v17; // [rsp+60h] [rbp-49h]
  __int64 v18; // [rsp+68h] [rbp-41h]
  __int64 v19; // [rsp+70h] [rbp-39h]
  int v20; // [rsp+78h] [rbp-31h]
  int v21; // [rsp+7Ch] [rbp-2Dh]
  int *v22; // [rsp+80h] [rbp-29h]
  __int64 v23; // [rsp+88h] [rbp-21h]
  __int64 v24; // [rsp+90h] [rbp-19h]
  int v25; // [rsp+98h] [rbp-11h]
  int v26; // [rsp+9Ch] [rbp-Dh]
  int *v27; // [rsp+A0h] [rbp-9h]
  __int64 v28; // [rsp+A8h] [rbp-1h]
  __int64 v29; // [rsp+B0h] [rbp+7h]
  int v30; // [rsp+B8h] [rbp+Fh]
  int v31; // [rsp+BCh] [rbp+13h]
  int v32; // [rsp+F0h] [rbp+47h] BYREF

  v32 = a3;
  v14 = a4;
  v16 = 0;
  v12 = &v32;
  v21 = 0;
  v17 = &a5;
  v19 = a6;
  v20 = a5;
  v22 = &a7;
  v24 = a8;
  v25 = a7;
  v27 = &a9;
  v29 = a10;
  v30 = a9;
  v26 = 0;
  v31 = 0;
  v13 = 4;
  v15 = a3;
  v18 = 4;
  v23 = 4;
  v28 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(
           &Dhcpv6_Context,
           (__int64)DHCPv6DUIDValidationFailed,
           a3,
           9,
           (__int64)v11);
}

```

## disassembly

```asm
0x18002a810  mov     [rsp-8+arg_10], r8d
0x18002a815  push    rbp
0x18002a816  lea     rbp, [rsp-27h]
0x18002a81b  sub     rsp, 0D0h
0x18002a822  mov     rax, cs:__security_cookie
0x18002a829  xor     rax, rsp
0x18002a82c  mov     [rbp+27h+var_10], rax
0x18002a830  xor     edx, edx
0x18002a832  mov     [rbp+27h+var_80], r9
0x18002a836  lea     rax, [rbp+27h+arg_10]
0x18002a83a  mov     [rbp+27h+var_74], edx
0x18002a83d  mov     [rbp+27h+var_90], rax
0x18002a841  lea     rcx, Dhcpv6_Context
0x18002a848  lea     rax, [rbp+27h+arg_20]
0x18002a84c  mov     [rbp+27h+var_54], edx
0x18002a84f  mov     [rbp+27h+var_70], rax
0x18002a853  lea     r9d, [rdx+9]
0x18002a857  mov     rax, [rbp+27h+arg_28]
0x18002a85b  mov     [rbp+27h+var_60], rax
0x18002a85f  mov     eax, [rbp+27h+arg_20]
0x18002a862  mov     [rbp+27h+var_58], eax
0x18002a865  lea     rax, [rbp+27h+arg_30]
0x18002a869  mov     [rbp+27h+var_50], rax
0x18002a86d  mov     rax, [rbp+27h+arg_38]
0x18002a871  mov     [rbp+27h+var_40], rax
0x18002a875  mov     eax, [rbp+27h+arg_30]
0x18002a878  mov     [rbp+27h+var_38], eax
0x18002a87b  lea     rax, [rbp+27h+arg_40]
0x18002a87f  mov     [rbp+27h+var_30], rax
0x18002a883  mov     rax, [rbp+27h+arg_48]
0x18002a887  mov     [rbp+27h+var_20], rax
0x18002a88b  mov     eax, [rbp+27h+arg_40]
0x18002a88e  mov     [rbp+27h+var_18], eax
0x18002a891  lea     rax, [rbp+27h+var_A0]
0x18002a895  mov     [rbp+27h+var_34], edx
0x18002a898  mov     [rbp+27h+var_14], edx
0x18002a89b  lea     rdx, DHCPv6DUIDValidationFailed
0x18002a8a2  mov     [rsp+0D0h+var_B0], rax
0x18002a8a7  mov     [rbp+27h+var_88], 4
0x18002a8af  mov     [rbp+27h+var_78], r8d
0x18002a8b3  mov     [rbp+27h+var_68], 4
0x18002a8bb  mov     [rbp+27h+var_48], 4
0x18002a8c3  mov     [rbp+27h+var_28], 4
0x18002a8cb  call    McGenEventWrite_EtwEventWriteTransfer
0x18002a8d0  mov     rcx, [rbp+27h+var_10]
0x18002a8d4  xor     rcx, rsp; StackCookie
0x18002a8d7  call    __security_check_cookie
0x18002a8dc  add     rsp, 0D0h
0x18002a8e3  pop     rbp
0x18002a8e4  retn
```
