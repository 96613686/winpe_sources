# sfac_ComputeIndex2

- ea: `0x140094d60`
- end: `0x140094f33`
- name: `sfac_ComputeIndex2`
- size: `467`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140013240`
- `0x140026160`
- `0x140026190`
- `0x14002926c`
- `0x14002e960`
- `0x140030bb0`
- `0x140047508`
- `0x140094d60`

## pseudocode

```c
__int64 __fastcall sfac_ComputeIndex2(unsigned __int64 a1, int a2, unsigned __int16 a3)
{
  __int64 v3; // r14
  unsigned __int16 v4; // si
  _QWORD *v6; // rax
  unsigned __int64 v7; // rbx
  __int64 v8; // rdx
  bool v9; // zf
  unsigned __int64 v10; // rbx
  __int64 v11; // rdx
  _QWORD *v12; // rax
  _WORD *v13; // rsi
  __int64 v14; // rdx
  __int64 v17; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int64 v18; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int64 v19; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v20[8]; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v21[16]; // [rsp+40h] [rbp-10h] BYREF
  int v22; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int16 v23; // [rsp+88h] [rbp+38h] BYREF
  unsigned __int16 v24; // [rsp+90h] [rbp+40h] BYREF

  v22 = a2;
  v3 = HIBYTE(a3);
  LOBYTE(v4) = a3;
  v18 = a1;
  v17 = v3;
  v6 = (_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                   &v17,
                   &v19,
                   2);
  v7 = *(_QWORD *)SafeInt<unsigned __int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator+<__int64>(
                    &v18,
                    v20,
                    *v6);
  v8 = *(unsigned int *)SafeInt<unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<unsigned __int64>(
                          &v22,
                          &v24);
  v18 = a1;
  if ( v7 <= *(_QWORD *)operator+=<unsigned char const,unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>(
                          &v18,
                          v8) )
  {
    v4 = (unsigned __int8)v4;
    v9 = *(_WORD *)(a1 + 2 * v3) == 0;
    v18 = a1 + 512;
    if ( v9 )
      v4 = v3;
    v24 = v4;
    v10 = *(_QWORD *)operator+=<unsigned char,unsigned short,SafeIntExceptionHandler<SafeIntRasterizerException>>(&v18);
    v11 = *(unsigned int *)SafeInt<unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<int>(
                             &v22,
                             &v23,
                             8);
    v17 = a1;
    if ( v10 <= *(_QWORD *)operator+=<unsigned char const,unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>(
                             &v17,
                             v11) )
    {
      v23 = _byteswap_ushort(*(_WORD *)v10);
      SubtractionHelper<unsigned short,unsigned short,0>::SubtractThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(
        &v24,
        &v23,
        &v24);
      if ( _byteswap_ushort(*(_WORD *)(v10 + 2)) <= v24 )
        return 0;
      v19 = v10 + (((unsigned __int64)*(unsigned __int8 *)(v10 + 6) << 8) | *(unsigned __int8 *)(v10 + 7)) + 6;
      v17 = v24;
      v12 = (_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                        &v17,
                        v20,
                        2);
      v13 = *(_WORD **)SafeInt<unsigned __int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator+<__int64>(
                         &v19,
                         v21,
                         *v12);
      v14 = *(unsigned int *)SafeInt<unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<unsigned __int64>(
                               &v22,
                               &v24);
      v19 = a1;
      if ( (unsigned __int64)v13 <= *(_QWORD *)operator+=<unsigned char const,unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>(
                                                 &v19,
                                                 v14) )
      {
        if ( *v13 )
          return (unsigned __int16)((HIBYTE(*v13) | ((unsigned __int8)*v13 << 8)) + _byteswap_ushort(*(_WORD *)(v10 + 4)));
        return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140094d60  mov     [rsp-28h+arg_18], rbx
0x140094d65  push    rbp
0x140094d66  push    rsi
0x140094d67  push    rdi
0x140094d68  push    r14
0x140094d6a  push    r15
0x140094d6c  mov     rbp, rsp
0x140094d6f  sub     rsp, 50h
0x140094d73  movzx   eax, r8w
0x140094d77  mov     [rbp+arg_0], edx
0x140094d7a  shr     ax, 8
0x140094d7e  lea     rdx, [rbp+var_20]
0x140094d82  movzx   r14d, ax
0x140094d86  movzx   esi, r8w
0x140094d8a  mov     rdi, rcx
0x140094d8d  mov     [rbp+var_28], rcx
0x140094d91  mov     r8d, 2
0x140094d97  mov     [rbp+var_30], r14
0x140094d9b  lea     rcx, [rbp+var_30]
0x140094d9f  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140094da4  lea     rdx, [rbp+var_18]
0x140094da8  lea     rcx, [rbp+var_28]
0x140094dac  mov     r8, [rax]
0x140094daf  call    ??$?H_J@?$SafeInt@_KV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_J@Z; SafeInt<unsigned __int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator+<__int64>(__int64)
0x140094db4  lea     rdx, [rbp+arg_10]
0x140094db8  lea     rcx, [rbp+arg_0]
0x140094dbc  mov     rbx, [rax]
0x140094dbf  call    ??$?G_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<unsigned __int64>(unsigned __int64)
0x140094dc4  lea     rcx, [rbp+var_28]
0x140094dc8  mov     edx, [rax]
0x140094dca  mov     [rbp+var_28], rdi
0x140094dce  call    ??$?Y$$CBEIV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEBEAEAPEBEV?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<uchar const,uint,SafeIntExceptionHandler<SafeIntRasterizerException>>(uchar const * &,SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140094dd3  xor     r15d, r15d
0x140094dd6  cmp     rbx, [rax]
0x140094dd9  ja      loc_140094F1C
0x140094ddf  movzx   edx, byte ptr [rdi+r14*2+1]
0x140094de5  lea     rcx, [rbp+var_28]
0x140094de9  mov     eax, 0FFh
0x140094dee  and     si, ax
0x140094df1  lea     rax, [rdi+200h]
0x140094df8  cmp     [rdi+r14*2], r15w
0x140094dfd  mov     [rbp+var_28], rax
0x140094e01  movzx   eax, byte ptr [rdi+r14*2]
0x140094e06  cmovz   si, r14w
0x140094e0b  shl     ax, 8
0x140094e0f  or      dx, ax
0x140094e12  mov     [rbp+arg_10], si
0x140094e16  call    ??$?YEGV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEAEAEAPEAEV?$SafeInt@GV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<uchar,ushort,SafeIntExceptionHandler<SafeIntRasterizerException>>(uchar * &,SafeInt<ushort,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140094e1b  lea     r8d, [r15+8]
0x140094e1f  lea     rdx, [rbp+arg_8]
0x140094e23  lea     rcx, [rbp+arg_0]
0x140094e27  mov     rbx, [rax]
0x140094e2a  call    ??$?GH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<int>(int)
0x140094e2f  lea     rcx, [rbp+var_30]
0x140094e33  mov     edx, [rax]
0x140094e35  mov     [rbp+var_30], rdi
0x140094e39  call    ??$?Y$$CBEIV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEBEAEAPEBEV?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<uchar const,uint,SafeIntExceptionHandler<SafeIntRasterizerException>>(uchar const * &,SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140094e3e  cmp     rbx, [rax]
0x140094e41  ja      loc_140094F1C
0x140094e47  movzx   ecx, byte ptr [rbx+1]
0x140094e4b  lea     r8, [rbp+arg_10]
0x140094e4f  movzx   eax, byte ptr [rbx]
0x140094e52  lea     rdx, [rbp+arg_8]
0x140094e56  shl     ax, 8
0x140094e5a  or      cx, ax
0x140094e5d  mov     [rbp+arg_8], cx
0x140094e61  lea     rcx, [rbp+arg_10]
0x140094e65  call    ??$SubtractThrow@V?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@?$SubtractionHelper@GG$0A@@@SAXAEBG0AEAG@Z; SubtractionHelper<ushort,ushort,0>::SubtractThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(ushort const &,ushort const &,ushort &)
0x140094e6a  movzx   ecx, byte ptr [rbx+2]
0x140094e6e  movzx   eax, byte ptr [rbx+3]
0x140094e72  shl     cx, 8
0x140094e76  or      cx, ax
0x140094e79  cmp     cx, [rbp+arg_10]
0x140094e7d  jbe     loc_140094F14
0x140094e83  movzx   ecx, byte ptr [rbx+6]
0x140094e87  lea     r8d, [r15+2]
0x140094e8b  movzx   eax, byte ptr [rbx+7]
0x140094e8f  lea     rdx, [rbp+var_18]
0x140094e93  shl     rcx, 8
0x140094e97  or      rax, rcx
0x140094e9a  lea     rcx, [rbp+var_30]
0x140094e9e  add     rax, 6
0x140094ea2  add     rax, rbx
0x140094ea5  mov     [rbp+var_20], rax
0x140094ea9  movzx   eax, [rbp+arg_10]
0x140094ead  mov     [rbp+var_30], rax
0x140094eb1  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140094eb6  lea     rdx, [rbp+var_10]
0x140094eba  lea     rcx, [rbp+var_20]
0x140094ebe  mov     r8, [rax]
0x140094ec1  call    ??$?H_J@?$SafeInt@_KV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_J@Z; SafeInt<unsigned __int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator+<__int64>(__int64)
0x140094ec6  lea     rdx, [rbp+arg_10]
0x140094eca  lea     rcx, [rbp+arg_0]
0x140094ece  mov     rsi, [rax]
0x140094ed1  call    ??$?G_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator-<unsigned __int64>(unsigned __int64)
0x140094ed6  lea     rcx, [rbp+var_20]
0x140094eda  mov     edx, [rax]
0x140094edc  mov     [rbp+var_20], rdi
0x140094ee0  call    ??$?Y$$CBEIV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEBEAEAPEBEV?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<uchar const,uint,SafeIntExceptionHandler<SafeIntRasterizerException>>(uchar const * &,SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x140094ee5  cmp     rsi, [rax]
0x140094ee8  ja      short loc_140094F1C
0x140094eea  movzx   edx, word ptr [rsi]
0x140094eed  test    dx, dx
0x140094ef0  jz      short loc_140094F14
0x140094ef2  movzx   eax, byte ptr [rbx+5]
0x140094ef6  movzx   ecx, byte ptr [rbx+4]
0x140094efa  shl     cx, 8
0x140094efe  or      cx, ax
0x140094f01  movzx   eax, dl
0x140094f04  shl     ax, 8
0x140094f08  shr     dx, 8
0x140094f0c  or      ax, dx
0x140094f0f  add     cx, ax
0x140094f12  jmp     short loc_140094F17
0x140094f14  mov     ecx, r15d
0x140094f17  movzx   eax, cx
0x140094f1a  jmp     short loc_140094F1F
0x140094f1c  mov     eax, r15d
0x140094f1f  mov     rbx, [rsp+50h+arg_18]
0x140094f27  add     rsp, 50h
0x140094f2b  pop     r15
0x140094f2d  pop     r14
0x140094f2f  pop     rdi
0x140094f30  pop     rsi
0x140094f31  pop     rbp
0x140094f32  retn
```
