# WriteIndexSubTables

- ea: `0x180013c38`
- end: `0x180013ed9`
- name: `WriteIndexSubTables`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013364`

## callees

- `0x180013c38`
- `0x18001975c`
- `0x18001a060`
- `0x18001a808`
- `0x18001a9c0`

## pseudocode

```c
__int16 __fastcall WriteIndexSubTables(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        unsigned int a5,
        unsigned int a6,
        _DWORD *a7)
{
  unsigned int v7; // ebx
  __int64 v9; // rdi
  unsigned __int16 v10; // r15
  unsigned int v12; // r13d
  unsigned int v13; // edx
  _WORD *v14; // rdi
  __int16 result; // ax
  unsigned __int16 v16; // si
  unsigned __int8 *v17; // r8
  int v18; // edx
  __int64 v19; // rdx
  unsigned __int16 v20; // [rsp+30h] [rbp-20h]
  _WORD v21[2]; // [rsp+40h] [rbp-10h] BYREF
  _DWORD v22[3]; // [rsp+44h] [rbp-Ch] BYREF
  unsigned __int16 v24; // [rsp+A8h] [rbp+58h]

  v24 = a4;
  v7 = a5;
  v9 = a3;
  v21[0] = 0;
  v10 = 0;
  v22[0] = 0;
  v12 = a5;
  while ( v10 < a4 )
  {
    v13 = a6;
    if ( *(_DWORD *)(a2 + 8LL * v10 + 4) < a6 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v13 = a6;
    }
    v14 = (_WORD *)(*(unsigned int *)(a2 + 8LL * v10 + 4) - (unsigned __int64)v13 + v9);
    *(_DWORD *)(a2 + 8LL * v10 + 4) = v13 + v7 - v12;
    if ( *v14 == 1 )
    {
      v16 = *(_WORD *)(a2 + 8LL * v10 + 2) - *(_WORD *)(a2 + 8LL * v10) + 2;
      result = WriteGeneric(a1, (__int64)v14, 8u, (unsigned __int8 *)INDEXSUBTABLE1_CONTROL, v7, v21);
      if ( result )
        return result;
      v20 = 4;
      v17 = (unsigned __int8 *)LONG_CONTROL;
    }
    else
    {
      if ( *v14 == 2 )
      {
        result = WriteGeneric(a1, (__int64)v14, 0x14u, (unsigned __int8 *)INDEXSUBTABLE2_CONTROL, v7, v21);
        if ( result )
          return result;
        v18 = v21[0];
        goto LABEL_23;
      }
      if ( *v14 != 3 )
      {
        if ( *v14 == 4 )
        {
          result = WriteGeneric(a1, (__int64)v14, 0xCu, (unsigned __int8 *)&INDEXSUBTABLE4_CONTROL, v7, v21);
          if ( result )
            return result;
          v7 += v21[0];
          result = WriteGenericRepeat(
                     a1,
                     (__int64)(v14 + 6),
                     (unsigned __int8 *)&CODEOFFSETPAIR_CONTROL,
                     v7,
                     v22,
                     v14[4] + 1,
                     4u);
        }
        else
        {
          if ( *v14 != 5 )
            return 1086;
          result = WriteGeneric(a1, (__int64)v14, 0x18u, (unsigned __int8 *)INDEXSUBTABLE5_CONTROL, v7, v21);
          if ( result )
            return result;
          v7 += v21[0];
          result = WriteGenericRepeat(a1, (__int64)(v14 + 12), (unsigned __int8 *)&WORD_CONTROL, v7, v22, v14[10], 2u);
        }
        goto LABEL_21;
      }
      v16 = *(_WORD *)(a2 + 8LL * v10 + 2) - *(_WORD *)(a2 + 8LL * v10) + 2;
      result = WriteGeneric(a1, (__int64)v14, 8u, (unsigned __int8 *)INDEXSUBTABLE3_CONTROL, v7, v21);
      if ( result )
        return result;
      v20 = 2;
      v17 = (unsigned __int8 *)&WORD_CONTROL;
    }
    v7 += v21[0];
    result = WriteGenericRepeat(a1, (__int64)(v14 + 4), v17, v7, v22, v16, v20);
LABEL_21:
    if ( result )
      return result;
    v18 = v22[0];
LABEL_23:
    v19 = v7 + v18;
    a5 = v19;
    result = ZeroLongWordAlign(a1, v19, &a5);
    if ( result )
      return result;
    v7 = a5;
    ++v10;
    a4 = v24;
    v9 = a3;
  }
  *a7 = v7 - v12;
  return 0;
}

```

## disassembly

```asm
0x180013c38  mov     [rsp-38h+arg_0], rbx
0x180013c3d  mov     [rsp-38h+arg_18], r9w
0x180013c43  mov     [rsp-38h+arg_10], r8
0x180013c48  push    rbp
0x180013c49  push    rsi
0x180013c4a  push    rdi
0x180013c4b  push    r12
0x180013c4d  push    r13
0x180013c4f  push    r14
0x180013c51  push    r15
0x180013c53  mov     rbp, rsp
0x180013c56  sub     rsp, 50h
0x180013c5a  mov     ebx, [rbp+arg_20]
0x180013c5d  mov     r14, rcx
0x180013c60  xor     ecx, ecx
0x180013c62  mov     rdi, r8
0x180013c65  mov     [rbp+var_10], cx
0x180013c69  mov     r15d, ecx
0x180013c6c  mov     [rbp+var_C], ecx
0x180013c6f  mov     r12, rdx
0x180013c72  mov     r13d, ebx
0x180013c75  mov     r8d, 2
0x180013c7b  cmp     r15w, r9w
0x180013c7f  jnb     loc_180013EB6
0x180013c85  mov     edx, [rbp+arg_28]
0x180013c88  movzx   esi, r15w
0x180013c8c  cmp     [r12+rsi*8+4], edx
0x180013c91  jnb     short loc_180013CA1
0x180013c93  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013c98  mov     edx, [rbp+arg_28]
0x180013c9b  mov     r8d, 2
0x180013ca1  mov     ecx, [r12+rsi*8+4]
0x180013ca6  mov     eax, edx
0x180013ca8  sub     rcx, rax
0x180013cab  mov     eax, ebx
0x180013cad  sub     eax, r13d
0x180013cb0  add     rdi, rcx
0x180013cb3  add     eax, edx
0x180013cb5  mov     [r12+rsi*8+4], eax
0x180013cba  movzx   ecx, word ptr [rdi]
0x180013cbd  sub     ecx, 1
0x180013cc0  jz      loc_180013E10
0x180013cc6  sub     ecx, 1
0x180013cc9  jz      loc_180013DDC
0x180013ccf  sub     ecx, 1
0x180013cd2  jz      loc_180013D8F
0x180013cd8  sub     ecx, 1
0x180013cdb  jz      short loc_180013D38
0x180013cdd  cmp     ecx, 1
0x180013ce0  jnz     loc_180013EAF
0x180013ce6  lea     rax, [rbp+var_10]
0x180013cea  mov     rdx, rdi
0x180013ced  lea     r8d, [rcx+17h]
0x180013cf1  mov     [rsp+50h+var_28], rax
0x180013cf6  lea     r9, INDEXSUBTABLE5_CONTROL
0x180013cfd  mov     dword ptr [rsp+50h+var_30], ebx
0x180013d01  mov     rcx, r14
0x180013d04  call    WriteGeneric
0x180013d09  test    ax, ax
0x180013d0c  jnz     loc_180013EC1
0x180013d12  movzx   eax, [rbp+var_10]
0x180013d16  lea     rdx, [rdi+18h]
0x180013d1a  add     ebx, eax
0x180013d1c  mov     [rsp+50h+var_20], 2
0x180013d23  movzx   eax, word ptr [rdi+14h]
0x180013d27  lea     r8, WORD_CONTROL
0x180013d2e  mov     word ptr [rsp+50h+var_28], ax
0x180013d33  jmp     loc_180013E66
0x180013d38  lea     rax, [rbp+var_10]
0x180013d3c  mov     r8d, 0Ch
0x180013d42  mov     [rsp+50h+var_28], rax
0x180013d47  lea     r9, INDEXSUBTABLE4_CONTROL
0x180013d4e  mov     rdx, rdi
0x180013d51  mov     dword ptr [rsp+50h+var_30], ebx
0x180013d55  mov     rcx, r14
0x180013d58  call    WriteGeneric
0x180013d5d  test    ax, ax
0x180013d60  jnz     loc_180013EC1
0x180013d66  movzx   eax, [rbp+var_10]
0x180013d6a  lea     rdx, [rdi+0Ch]
0x180013d6e  add     ebx, eax
0x180013d70  mov     [rsp+50h+var_20], 4
0x180013d77  movzx   eax, word ptr [rdi+8]
0x180013d7b  lea     r8, CODEOFFSETPAIR_CONTROL
0x180013d82  inc     ax
0x180013d85  mov     word ptr [rsp+50h+var_28], ax
0x180013d8a  jmp     loc_180013E66
0x180013d8f  movzx   eax, word ptr [r12+rsi*8+2]
0x180013d95  lea     r9, INDEXSUBTABLE3_CONTROL
0x180013d9c  sub     ax, [r12+rsi*8]
0x180013da1  mov     rdx, rdi
0x180013da4  mov     rcx, r14
0x180013da7  lea     esi, [r8+rax]
0x180013dab  mov     r8d, 8
0x180013db1  lea     rax, [rbp+var_10]
0x180013db5  mov     [rsp+50h+var_28], rax
0x180013dba  mov     dword ptr [rsp+50h+var_30], ebx
0x180013dbe  call    WriteGeneric
0x180013dc3  test    ax, ax
0x180013dc6  jnz     loc_180013EC1
0x180013dcc  mov     [rsp+50h+var_20], 2
0x180013dd3  lea     r8, WORD_CONTROL
0x180013dda  jmp     short loc_180013E57
0x180013ddc  lea     rax, [rbp+var_10]
0x180013de0  mov     r8d, 14h
0x180013de6  mov     [rsp+50h+var_28], rax
0x180013deb  lea     r9, INDEXSUBTABLE2_CONTROL
0x180013df2  mov     rdx, rdi
0x180013df5  mov     dword ptr [rsp+50h+var_30], ebx
0x180013df9  mov     rcx, r14
0x180013dfc  call    WriteGeneric
0x180013e01  test    ax, ax
0x180013e04  jnz     loc_180013EC1
0x180013e0a  movzx   edx, [rbp+var_10]
0x180013e0e  jmp     short loc_180013E82
0x180013e10  movzx   eax, word ptr [r12+rsi*8+2]
0x180013e16  lea     r9, INDEXSUBTABLE1_CONTROL
0x180013e1d  sub     ax, [r12+rsi*8]
0x180013e22  mov     rdx, rdi
0x180013e25  mov     rcx, r14
0x180013e28  lea     esi, [r8+rax]
0x180013e2c  mov     r8d, 8
0x180013e32  lea     rax, [rbp+var_10]
0x180013e36  mov     [rsp+50h+var_28], rax
0x180013e3b  mov     dword ptr [rsp+50h+var_30], ebx
0x180013e3f  call    WriteGeneric
0x180013e44  test    ax, ax
0x180013e47  jnz     short loc_180013EC1
0x180013e49  mov     [rsp+50h+var_20], 4
0x180013e50  lea     r8, LONG_CONTROL
0x180013e57  movzx   eax, [rbp+var_10]
0x180013e5b  lea     rdx, [rdi+8]
0x180013e5f  add     ebx, eax
0x180013e61  mov     word ptr [rsp+50h+var_28], si
0x180013e66  lea     rax, [rbp+var_C]
0x180013e6a  mov     r9d, ebx
0x180013e6d  mov     rcx, r14
0x180013e70  mov     [rsp+50h+var_30], rax
0x180013e75  call    WriteGenericRepeat
0x180013e7a  test    ax, ax
0x180013e7d  jnz     short loc_180013EC1
0x180013e7f  mov     edx, [rbp+var_C]
0x180013e82  add     edx, ebx
0x180013e84  lea     r8, [rbp+arg_20]
0x180013e88  mov     rcx, r14
0x180013e8b  mov     [rbp+arg_20], edx
0x180013e8e  call    ZeroLongWordAlign
0x180013e93  xor     ecx, ecx
0x180013e95  test    ax, ax
0x180013e98  jnz     short loc_180013EC1
0x180013e9a  mov     ebx, [rbp+arg_20]
0x180013e9d  inc     r15w
0x180013ea1  movzx   r9d, [rbp+arg_18]
0x180013ea6  mov     rdi, [rbp+arg_10]
0x180013eaa  jmp     loc_180013C75
0x180013eaf  mov     eax, 43Eh
0x180013eb4  jmp     short loc_180013EC1
0x180013eb6  mov     rax, [rbp+arg_30]
0x180013eba  sub     ebx, r13d
0x180013ebd  mov     [rax], ebx
0x180013ebf  mov     eax, ecx
0x180013ec1  mov     rbx, [rsp+50h+arg_0]
0x180013ec9  add     rsp, 50h
0x180013ecd  pop     r15
0x180013ecf  pop     r14
0x180013ed1  pop     r13
0x180013ed3  pop     r12
0x180013ed5  pop     rdi
0x180013ed6  pop     rsi
0x180013ed7  pop     rbp
0x180013ed8  retn
```
