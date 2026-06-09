# ReadSubTableInfo

- ea: `0x1800167ac`
- end: `0x1800168ca`
- name: `ReadSubTableInfo`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800154a4`

## callees

- `0x1800167ac`
- `0x18001a3bc`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall ReadSubTableInfo(__int64 a1, _WORD *a2, _DWORD *a3, _QWORD *a4, unsigned int a5)
{
  __int64 result; // rax
  __int64 v10; // rax
  __int16 v11; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v12[20]; // [rsp+38h] [rbp-48h] BYREF
  _DWORD v13[8]; // [rsp+50h] [rbp-30h] BYREF

  v11 = 0;
  memset(v13, 0, 28);
  memset(v12, 0, sizeof(v12));
  result = ReadGeneric(a1, (__int64)a2, 8u, (unsigned __int8 *)INDEXSUBHEADER_CONTROL, a5, &v11);
  if ( !(_WORD)result )
  {
    if ( *a2 == 2 )
    {
      result = ReadGeneric(a1, (__int64)v12, 0x14u, (unsigned __int8 *)INDEXSUBTABLE2_CONTROL, a5, &v11);
      if ( (_WORD)result )
        return result;
      *a3 = *(_DWORD *)&v12[8];
      v10 = *(_QWORD *)&v12[12];
    }
    else if ( *a2 == 5 )
    {
      result = ReadGeneric(a1, (__int64)v13, 0x18u, (unsigned __int8 *)INDEXSUBTABLE5_CONTROL, a5, &v11);
      if ( (_WORD)result )
        return result;
      *a3 = v13[2];
      v10 = *(_QWORD *)&v13[3];
    }
    else
    {
      *a3 = 0;
      v10 = 0;
    }
    *a4 = v10;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800167ac  push    rbp
0x1800167ae  push    rbx
0x1800167af  push    rsi
0x1800167b0  push    rdi
0x1800167b1  push    r12
0x1800167b3  push    r14
0x1800167b5  push    r15
0x1800167b7  mov     rbp, rsp
0x1800167ba  sub     rsp, 80h
0x1800167c1  mov     rax, cs:__security_cookie
0x1800167c8  xor     rax, rsp
0x1800167cb  mov     [rbp+var_10], rax
0x1800167cf  mov     r14d, [rbp+arg_20]
0x1800167d3  xor     eax, eax
0x1800167d5  xorps   xmm1, xmm1
0x1800167d8  mov     [rbp+var_38], eax
0x1800167db  xor     r12d, r12d
0x1800167de  lea     rax, [rbp+var_50]
0x1800167e2  mov     rdi, r9
0x1800167e5  mov     [rsp+80h+var_58], rax
0x1800167ea  mov     rbx, r8
0x1800167ed  mov     [rsp+80h+var_60], r14d
0x1800167f2  xorps   xmm0, xmm0
0x1800167f5  mov     [rbp+var_50], r12w
0x1800167fa  movups  xmmword ptr [rbp+var_30], xmm1
0x1800167fe  lea     r8d, [r12+8]
0x180016803  mov     r15, rdx
0x180016806  lea     r9, INDEXSUBHEADER_CONTROL
0x18001680d  mov     rsi, rcx
0x180016810  movups  [rbp+var_48], xmm0
0x180016814  movups  xmmword ptr [rbp+var_30+0Ch], xmm1
0x180016818  call    ReadGeneric
0x18001681d  test    ax, ax
0x180016820  jnz     loc_1800168AC
0x180016826  cmp     word ptr [r15], 2
0x18001682b  jnz     short loc_180016863
0x18001682d  lea     rax, [rbp+var_50]
0x180016831  mov     rcx, rsi
0x180016834  mov     [rsp+80h+var_58], rax
0x180016839  lea     r8d, [r12+14h]
0x18001683e  lea     r9, INDEXSUBTABLE2_CONTROL
0x180016845  mov     [rsp+80h+var_60], r14d
0x18001684a  lea     rdx, [rbp+var_48]
0x18001684e  call    ReadGeneric
0x180016853  test    ax, ax
0x180016856  jnz     short loc_1800168AC
0x180016858  mov     eax, dword ptr [rbp+var_48+8]
0x18001685b  mov     [rbx], eax
0x18001685d  mov     rax, qword ptr [rbp+var_48+0Ch]
0x180016861  jmp     short loc_1800168A6
0x180016863  cmp     word ptr [r15], 5
0x180016868  jnz     short loc_1800168A1
0x18001686a  lea     rax, [rbp+var_50]
0x18001686e  mov     r8d, 18h
0x180016874  mov     [rsp+80h+var_58], rax
0x180016879  lea     r9, INDEXSUBTABLE5_CONTROL
0x180016880  lea     rdx, [rbp+var_30]
0x180016884  mov     [rsp+80h+var_60], r14d
0x180016889  mov     rcx, rsi
0x18001688c  call    ReadGeneric
0x180016891  test    ax, ax
0x180016894  jnz     short loc_1800168AC
0x180016896  mov     eax, [rbp+var_30+8]
0x180016899  mov     [rbx], eax
0x18001689b  mov     rax, qword ptr [rbp+var_30+0Ch]
0x18001689f  jmp     short loc_1800168A6
0x1800168a1  mov     [rbx], r12d
0x1800168a4  xor     eax, eax
0x1800168a6  mov     [rdi], rax
0x1800168a9  mov     eax, r12d
0x1800168ac  mov     rcx, [rbp+var_10]
0x1800168b0  xor     rcx, rsp; StackCookie
0x1800168b3  call    __security_check_cookie
0x1800168b8  add     rsp, 80h
0x1800168bf  pop     r15
0x1800168c1  pop     r14
0x1800168c3  pop     r12
0x1800168c5  pop     rdi
0x1800168c6  pop     rsi
0x1800168c7  pop     rbx
0x1800168c8  pop     rbp
0x1800168c9  retn
```
