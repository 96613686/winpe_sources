# fnEfsLogTrace2

- ea: `0x180006590`
- end: `0x180006626`
- name: `fnEfsLogTrace2`
- size: `150`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006708`
- `0x1800068c8`
- `0x180006a98`
- `0x180006c1c`
- `0x180006e60`
- `0x180006f60`
- `0x180009b2c`

## callees

- `0x180006590`
- `0x180012040`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800065bf`
- `ntdll!EtwEventEnabled` at `0x1800065bf`
- `ntdll!EtwEventWrite` at `0x180006609`
- `ntdll!EtwEventWrite` at `0x180006609`

## pseudocode

```c
__int64 __fastcall fnEfsLogTrace2(__int64 a1, __int64 a2, unsigned int a3, int a4, char a5, char a6)
{
  __int64 v6; // rdi
  _QWORD v9[8]; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v10; // [rsp+A0h] [rbp+30h] BYREF
  int v11; // [rsp+A8h] [rbp+38h] BYREF

  v11 = a4;
  v10 = a3;
  v6 = g_hPublisher;
  if ( (unsigned __int8)EtwEventEnabled(g_hPublisher) )
  {
    v9[0] = &a5;
    v9[1] = 4;
    v9[2] = &a6;
    v9[3] = 4;
    v9[4] = &v10;
    v9[5] = 4;
    v9[6] = &v11;
    v9[7] = 4;
    ((void (__fastcall *)(__int64, __int64, __int64, _QWORD *))EtwEventWrite)(v6, a2, 4, v9);
  }
  return v10;
}

```

## disassembly

```asm
0x180006590  mov     [rsp-18h+arg_18], r9d
0x180006595  mov     [rsp-18h+arg_10], r8d
0x18000659a  push    rbp
0x18000659b  push    rbx
0x18000659c  push    rdi
0x18000659d  mov     rbp, rsp
0x1800065a0  sub     rsp, 70h
0x1800065a4  mov     rax, cs:__security_cookie
0x1800065ab  xor     rax, rsp
0x1800065ae  mov     [rbp+var_10], rax
0x1800065b2  mov     rdi, cs:g_hPublisher
0x1800065b9  mov     rbx, rdx
0x1800065bc  mov     rcx, rdi
0x1800065bf  call    cs:__imp_EtwEventEnabled
0x1800065c5  test    al, al
0x1800065c7  jz      short loc_18000660F
0x1800065c9  mov     r8d, 4
0x1800065cf  lea     rax, [rbp+arg_20]
0x1800065d3  mov     [rbp+var_50], rax
0x1800065d7  lea     r9, [rbp+var_50]
0x1800065db  lea     rax, [rbp+arg_28]
0x1800065df  mov     [rbp+var_48], r8
0x1800065e3  mov     [rbp+var_40], rax
0x1800065e7  mov     rdx, rbx
0x1800065ea  lea     rax, [rbp+arg_10]
0x1800065ee  mov     [rbp+var_38], r8
0x1800065f2  mov     [rbp+var_30], rax
0x1800065f6  mov     rcx, rdi
0x1800065f9  lea     rax, [rbp+arg_18]
0x1800065fd  mov     [rbp+var_28], r8
0x180006601  mov     [rbp+var_20], rax
0x180006605  mov     [rbp+var_18], r8
0x180006609  call    cs:__imp_EtwEventWrite
0x18000660f  mov     eax, [rbp+arg_10]
0x180006612  mov     rcx, [rbp+var_10]
0x180006616  xor     rcx, rsp; StackCookie
0x180006619  call    __security_check_cookie
0x18000661e  add     rsp, 70h
0x180006622  pop     rdi
0x180006623  pop     rbx
0x180006624  pop     rbp
0x180006625  retn
```
