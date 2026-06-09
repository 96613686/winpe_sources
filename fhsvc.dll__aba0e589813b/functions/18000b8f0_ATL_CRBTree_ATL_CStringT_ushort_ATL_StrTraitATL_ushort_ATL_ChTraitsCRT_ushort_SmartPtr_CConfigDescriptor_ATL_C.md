# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Find(ushort const *)

- ea: `0x18000b8f0`
- end: `0x18000b992`
- name: `?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000aa08`

## callees

- `0x18000b8f0`
- `0x18000bdfc`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Find(
        _QWORD **a1,
        unsigned __int16 *a2)
{
  _QWORD *v2; // rax
  _QWORD **v4; // r11
  _QWORD *v5; // r9
  unsigned __int16 *v6; // rcx
  int v7; // r10d
  int v8; // edx
  _QWORD *i; // rdx
  unsigned __int16 *v11; // rcx
  int v12; // r10d
  int v13; // r8d
  _QWORD *v14; // rax
  __int64 v15; // r9

  v2 = *a1;
  v4 = a1;
  v5 = 0;
  while ( v2 != v4[5] )
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
LABEL_14:
  for ( i = v5; ; i = v14 )
  {
    v14 = (_QWORD *)ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Predecessor(
                      v4,
                      i);
    if ( !v14 )
      break;
    v11 = a2;
    do
    {
      v12 = *(unsigned __int16 *)((char *)v11 + *v14 - (_QWORD)a2);
      v13 = *v11 - v12;
      if ( v13 )
        break;
      ++v11;
    }
    while ( v12 );
    if ( v13 )
      break;
  }
  return v15;
}

```

## disassembly

```asm
0x18000b8f0  push    rbx
0x18000b8f2  sub     rsp, 20h
0x18000b8f6  mov     rax, [rcx]
0x18000b8f9  mov     rbx, rdx
0x18000b8fc  mov     r11, rcx
0x18000b8ff  xor     r9d, r9d
0x18000b902  cmp     rax, [r11+28h]
0x18000b906  jz      short loc_18000B943
0x18000b908  test    r9, r9
0x18000b90b  jnz     short loc_18000B94C
0x18000b90d  mov     r8, [rax]
0x18000b910  mov     rcx, rbx
0x18000b913  sub     r8, rbx
0x18000b916  movzx   edx, word ptr [rcx]
0x18000b919  movzx   r10d, word ptr [rcx+r8]
0x18000b91e  sub     edx, r10d
0x18000b921  jnz     short loc_18000B92C
0x18000b923  add     rcx, 2
0x18000b927  test    r10d, r10d
0x18000b92a  jnz     short loc_18000B916
0x18000b92c  test    edx, edx
0x18000b92e  jnz     short loc_18000B935
0x18000b930  mov     r9, rax
0x18000b933  jmp     short loc_18000B902
0x18000b935  jns     short loc_18000B93D
0x18000b937  mov     rax, [rax+18h]
0x18000b93b  jmp     short loc_18000B902
0x18000b93d  mov     rax, [rax+20h]
0x18000b941  jmp     short loc_18000B902
0x18000b943  test    r9, r9
0x18000b946  jnz     short loc_18000B94C
0x18000b948  xor     eax, eax
0x18000b94a  jmp     short loc_18000B98C
0x18000b94c  mov     rdx, r9
0x18000b94f  jmp     short loc_18000B97C
0x18000b951  mov     rdx, [rax]
0x18000b954  mov     rcx, rbx
0x18000b957  sub     rdx, rbx
0x18000b95a  movzx   r8d, word ptr [rcx]
0x18000b95e  movzx   r10d, word ptr [rcx+rdx]
0x18000b963  sub     r8d, r10d
0x18000b966  jnz     short loc_18000B971
0x18000b968  add     rcx, 2
0x18000b96c  test    r10d, r10d
0x18000b96f  jnz     short loc_18000B95A
0x18000b971  test    r8d, r8d
0x18000b974  jnz     short loc_18000B989
0x18000b976  mov     r9, rax
0x18000b979  mov     rdx, rax
0x18000b97c  mov     rcx, r11
0x18000b97f  call    ?Predecessor@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Predecessor(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000b984  test    rax, rax
0x18000b987  jnz     short loc_18000B951
0x18000b989  mov     rax, r9
0x18000b98c  add     rsp, 20h
0x18000b990  pop     rbx
0x18000b991  retn
```
