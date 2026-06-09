# sub_1800E7DBC

- ea: `0x1800e7dbc`
- end: `0x1800e7e29`
- name: `sub_1800E7DBC`
- size: `109`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e7d48`
- `0x1800f05b4`
- `0x1800f0f68`

## callees

- `0x1800e7dbc`
- `0x1800e83a0`
- `0x1800fe33c`

## pseudocode

```c
__int64 __fastcall sub_1800E7DBC(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v6; // ebx
  unsigned int v8; // [rsp+30h] [rbp-18h] BYREF
  void *v9; // [rsp+38h] [rbp-10h] BYREF

  v9 = 0;
  v8 = 0;
  v6 = sub_1800FE33C(a1, a2, a3, 0, &v9, &v8);
  if ( v6 >= 0 )
    v6 = ((__int64 (__fastcall *)(void *, _QWORD, __int64, __int64))loc_1800F947C)(v9, v8, a4, a5);
  sub_1800E83A0(v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800e7dbc  mov     r11, rsp
0x1800e7dbf  mov     [r11+8], rbx
0x1800e7dc3  push    rdi
0x1800e7dc4  sub     rsp, 40h
0x1800e7dc8  lea     rax, [r11-18h]
0x1800e7dcc  mov     qword ptr [r11-10h], 0
0x1800e7dd4  mov     [r11-20h], rax
0x1800e7dd8  mov     rdi, r9
0x1800e7ddb  lea     rax, [r11-10h]
0x1800e7ddf  mov     [rsp+48h+var_18], 0
0x1800e7de7  xor     r9d, r9d
0x1800e7dea  mov     [r11-28h], rax
0x1800e7dee  call    sub_1800FE33C
0x1800e7df3  mov     ebx, eax
0x1800e7df5  test    eax, eax
0x1800e7df7  js      short loc_1800E7E11
0x1800e7df9  mov     r9, [rsp+48h+arg_20]
0x1800e7dfe  mov     r8, rdi
0x1800e7e01  mov     edx, [rsp+48h+var_18]
0x1800e7e05  mov     rcx, [rsp+48h+var_10]
0x1800e7e0a  call    loc_1800F947C
0x1800e7e0f  mov     ebx, eax
0x1800e7e11  mov     rcx, [rsp+48h+var_10]
0x1800e7e16  call    sub_1800E83A0
0x1800e7e1b  mov     eax, ebx
0x1800e7e1d  mov     rbx, [rsp+48h+arg_0]
0x1800e7e22  add     rsp, 40h
0x1800e7e26  pop     rdi
0x1800e7e27  retn
```
