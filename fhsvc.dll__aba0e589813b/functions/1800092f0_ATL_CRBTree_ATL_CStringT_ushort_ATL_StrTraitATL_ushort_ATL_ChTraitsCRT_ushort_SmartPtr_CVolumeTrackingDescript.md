# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(ushort const *)

- ea: `0x1800092f0`
- end: `0x1800093d7`
- name: `?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z`
- size: `231`
- prototype: `_QWORD *__fastcall(__int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a360`
- `0x18000ac48`

## callees

- `0x1800092f0`

## pseudocode

```c
_QWORD *__fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::Find(
        __int64 a1,
        unsigned __int16 *a2)
{
  _QWORD *v2; // r9
  _QWORD *v4; // r11
  _QWORD *v5; // r10
  unsigned __int16 *v6; // rax
  int v7; // ecx
  int v8; // edx
  _QWORD *v10; // r9
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  char v13; // cl
  unsigned __int16 *v14; // rax
  int v15; // ecx
  int v16; // edx

  v2 = *(_QWORD **)a1;
  v4 = *(_QWORD **)(a1 + 40);
  v5 = 0;
  while ( v2 != v4 )
  {
    if ( v5 )
      goto LABEL_14;
    v6 = a2;
    do
    {
      v7 = *(unsigned __int16 *)((char *)v6 + *v2 - (_QWORD)a2);
      v8 = *v6 - v7;
      if ( v8 )
        break;
      ++v6;
    }
    while ( v7 );
    if ( v8 )
    {
      if ( v8 >= 0 )
        v2 = (_QWORD *)v2[4];
      else
        v2 = (_QWORD *)v2[3];
    }
    else
    {
      v5 = v2;
    }
  }
  if ( !v5 )
    return 0;
  while ( 1 )
  {
LABEL_14:
    v10 = (_QWORD *)v5[3];
    if ( v10 == v4 )
    {
      v11 = (_QWORD *)v5[5];
      v12 = v5;
      while ( v11 != v4 )
      {
        if ( v12 != (_QWORD *)v11[3] )
        {
          v13 = 0;
          goto LABEL_24;
        }
        v12 = v11;
        v11 = (_QWORD *)v11[5];
      }
      v13 = 1;
LABEL_24:
      v10 = 0;
      if ( !v13 )
        v10 = v11;
    }
    else if ( v10 )
    {
      while ( (_QWORD *)v10[4] != v4 )
        v10 = (_QWORD *)v10[4];
    }
    if ( !v10 )
      return v5;
    v14 = a2;
    do
    {
      v15 = *(unsigned __int16 *)((char *)v14 + *v10 - (_QWORD)a2);
      v16 = *v14 - v15;
      if ( v16 )
        break;
      ++v14;
    }
    while ( v15 );
    if ( v16 )
      return v5;
    v5 = v10;
  }
}

```

## disassembly

```asm
0x1800092f0  mov     [rsp+arg_0], rbx
0x1800092f5  mov     r9, [rcx]
0x1800092f8  mov     rbx, rdx
0x1800092fb  mov     r11, [rcx+28h]
0x1800092ff  xor     r10d, r10d
0x180009302  cmp     r9, r11
0x180009305  jz      short loc_18000934B
0x180009307  test    r10, r10
0x18000930a  jnz     short loc_18000935D
0x18000930c  mov     r8, [r9]
0x18000930f  mov     rax, rbx
0x180009312  sub     r8, rbx
0x180009315  nop     word ptr [rax+rax+00000000h]
0x180009320  movzx   edx, word ptr [rax]
0x180009323  movzx   ecx, word ptr [rax+r8]
0x180009328  sub     edx, ecx
0x18000932a  jnz     short loc_180009334
0x18000932c  add     rax, 2
0x180009330  test    ecx, ecx
0x180009332  jnz     short loc_180009320
0x180009334  test    edx, edx
0x180009336  jnz     short loc_18000933D
0x180009338  mov     r10, r9
0x18000933b  jmp     short loc_180009302
0x18000933d  jns     short loc_180009345
0x18000933f  mov     r9, [r9+18h]
0x180009343  jmp     short loc_180009302
0x180009345  mov     r9, [r9+20h]
0x180009349  jmp     short loc_180009302
0x18000934b  test    r10, r10
0x18000934e  jnz     short loc_18000935D
0x180009350  xor     eax, eax
0x180009352  mov     rbx, [rsp+arg_0]
0x180009357  retn
0x180009358  test    r10, r10
0x18000935b  jz      short loc_1800093CE
0x18000935d  mov     r9, [r10+18h]
0x180009361  cmp     r9, r11
0x180009364  jz      short loc_180009379
0x180009366  test    r9, r9
0x180009369  jz      short loc_1800093A3
0x18000936b  mov     rax, [r9+20h]
0x18000936f  cmp     rax, r11
0x180009372  jz      short loc_1800093A3
0x180009374  mov     r9, rax
0x180009377  jmp     short loc_18000936B
0x180009379  mov     rax, [r10+28h]
0x18000937d  mov     rcx, r10
0x180009380  cmp     rax, r11
0x180009383  jz      short loc_180009398
0x180009385  cmp     rcx, [rax+18h]
0x180009389  jnz     short loc_180009394
0x18000938b  mov     rcx, rax
0x18000938e  mov     rax, [rax+28h]
0x180009392  jmp     short loc_180009380
0x180009394  xor     cl, cl
0x180009396  jmp     short loc_18000939A
0x180009398  mov     cl, 1
0x18000939a  xor     r9d, r9d
0x18000939d  test    cl, cl
0x18000939f  cmovz   r9, rax
0x1800093a3  test    r9, r9
0x1800093a6  jz      short loc_1800093CE
0x1800093a8  mov     r8, [r9]
0x1800093ab  mov     rax, rbx
0x1800093ae  sub     r8, rbx
0x1800093b1  movzx   edx, word ptr [rax]
0x1800093b4  movzx   ecx, word ptr [rax+r8]
0x1800093b9  sub     edx, ecx
0x1800093bb  jnz     short loc_1800093C5
0x1800093bd  add     rax, 2
0x1800093c1  test    ecx, ecx
0x1800093c3  jnz     short loc_1800093B1
0x1800093c5  test    edx, edx
0x1800093c7  jnz     short loc_1800093CE
0x1800093c9  mov     r10, r9
0x1800093cc  jmp     short loc_180009358
0x1800093ce  mov     rbx, [rsp+arg_0]
0x1800093d3  mov     rax, r10
0x1800093d6  retn
```
