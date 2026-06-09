# sfac_ComputeIndex6

- ea: `0x140094f40`
- end: `0x14009502a`
- name: `sfac_ComputeIndex6`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140013240`
- `0x140026160`
- `0x140026190`
- `0x14002e960`
- `0x140030bb0`
- `0x140047508`
- `0x140094f40`

## pseudocode

```c
unsigned __int16 __fastcall sfac_ComputeIndex6(unsigned __int16 *a1, int a2, unsigned __int16 a3)
{
  __int64 v4; // rdx
  _QWORD *v5; // rax
  unsigned __int16 *v6; // rdi
  __int64 v7; // rdx
  unsigned __int16 *v9; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v10; // [rsp+28h] [rbp-18h] BYREF
  _BYTE v11[8]; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-8h] BYREF
  int v13; // [rsp+60h] [rbp+20h] BYREF
  unsigned __int16 v14; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int16 v15; // [rsp+70h] [rbp+30h] BYREF

  v13 = a2;
  v15 = a3;
  v4 = *(unsigned int *)SafeInt<unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<int>(
                          &v13,
                          &v14,
                          4);
  v9 = a1;
  if ( (unsigned __int64)a1 > *(_QWORD *)operator+=<unsigned char const,unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>(
                                           &v9,
                                           v4) )
    return 0;
  v14 = _byteswap_ushort(*a1);
  SubtractionHelper<unsigned short,unsigned short,0>::SubtractThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(
    &v15,
    &v14,
    &v15);
  if ( _byteswap_ushort(a1[1]) <= v15 )
    return 0;
  v10 = a1 + 2;
  v9 = (unsigned __int16 *)v15;
  v5 = (_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                   &v9,
                   v11,
                   2);
  v6 = *(unsigned __int16 **)SafeInt<unsigned __int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator+<__int64>(
                               &v10,
                               v12,
                               *v5);
  v7 = *(unsigned int *)SafeInt<unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<unsigned __int64>(
                          &v13,
                          &v15);
  v10 = a1;
  if ( (unsigned __int64)v6 > *(_QWORD *)operator+=<unsigned char const,unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>(
                                           &v10,
                                           v7) )
    return 0;
  else
    return _byteswap_ushort(*v6);
}

```

## disassembly

```asm
0x140094f40  push    rbp
0x140094f42  push    rbx
0x140094f43  push    rdi
0x140094f44  mov     rbp, rsp
0x140094f47  sub     rsp, 40h
0x140094f4b  mov     rbx, rcx
0x140094f4e  mov     [rbp+arg_0], edx
0x140094f51  mov     [rbp+arg_10], r8w
0x140094f56  lea     rdx, [rbp+arg_8]
0x140094f5a  mov     r8d, 4
0x140094f60  lea     rcx, [rbp+arg_0]
0x140094f64  call    ??$?GH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<int>(int)
0x140094f69  lea     rcx, [rbp+var_20]
0x140094f6d  mov     edx, [rax]
0x140094f6f  mov     [rbp+var_20], rbx
0x140094f73  call    ??$?Y$$CBEIV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEBEAEAPEBEV?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<uchar const,uint,SafeIntExceptionHandler<SafeIntRasterizerException>>(uchar const * &,SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140094f78  cmp     rbx, [rax]
0x140094f7b  ja      loc_140095020
0x140094f81  movzx   ecx, byte ptr [rbx]
0x140094f84  lea     r8, [rbp+arg_10]
0x140094f88  movzx   eax, byte ptr [rbx+1]
0x140094f8c  lea     rdx, [rbp+arg_8]
0x140094f90  shl     cx, 8
0x140094f94  or      cx, ax
0x140094f97  mov     [rbp+arg_8], cx
0x140094f9b  lea     rcx, [rbp+arg_10]
0x140094f9f  call    ??$SubtractThrow@V?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@?$SubtractionHelper@GG$0A@@@SAXAEBG0AEAG@Z; SubtractionHelper<ushort,ushort,0>::SubtractThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(ushort const &,ushort const &,ushort &)
0x140094fa4  movzx   ecx, byte ptr [rbx+2]
0x140094fa8  movzx   eax, byte ptr [rbx+3]
0x140094fac  shl     cx, 8
0x140094fb0  or      cx, ax
0x140094fb3  cmp     cx, [rbp+arg_10]
0x140094fb7  jbe     short loc_140095020
0x140094fb9  lea     rax, [rbx+4]
0x140094fbd  mov     r8d, 2
0x140094fc3  mov     [rbp+var_18], rax
0x140094fc7  lea     rdx, [rbp+var_10]
0x140094fcb  movzx   eax, [rbp+arg_10]
0x140094fcf  lea     rcx, [rbp+var_20]
0x140094fd3  mov     [rbp+var_20], rax
0x140094fd7  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140094fdc  lea     rdx, [rbp+var_8]
0x140094fe0  lea     rcx, [rbp+var_18]
0x140094fe4  mov     r8, [rax]
0x140094fe7  call    ??$?H_J@?$SafeInt@_KV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_J@Z; SafeInt<unsigned __int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator+<__int64>(__int64)
0x140094fec  lea     rdx, [rbp+arg_10]
0x140094ff0  lea     rcx, [rbp+arg_0]
0x140094ff4  mov     rdi, [rax]
0x140094ff7  call    ??$?G_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<unsigned __int64>(unsigned __int64)
0x140094ffc  lea     rcx, [rbp+var_18]
0x140095000  mov     edx, [rax]
0x140095002  mov     [rbp+var_18], rbx
0x140095006  call    ??$?Y$$CBEIV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEBEAEAPEBEV?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<uchar const,uint,SafeIntExceptionHandler<SafeIntRasterizerException>>(uchar const * &,SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x14009500b  cmp     rdi, [rax]
0x14009500e  ja      short loc_140095020
0x140095010  movzx   eax, byte ptr [rdi]
0x140095013  movzx   ecx, byte ptr [rdi+1]
0x140095017  shl     ax, 8
0x14009501b  or      ax, cx
0x14009501e  jmp     short loc_140095022
0x140095020  xor     eax, eax
0x140095022  add     rsp, 40h
0x140095026  pop     rdi
0x140095027  pop     rbx
0x140095028  pop     rbp
0x140095029  retn
```
