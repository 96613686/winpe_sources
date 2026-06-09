# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::InsertImpl(ushort const *,SmartPtr<CVolumeTrackingDescriptor> const &)

- ea: `0x18000f4e4`
- end: `0x18000f582`
- name: `?InsertImpl@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAPEAVCNode@12@PEBGAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(__int64 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fcd4`

## callees

- `0x18000bac8`
- `0x18000f4e4`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::InsertImpl(
        __int64 *a1,
        unsigned __int16 *a2)
{
  __int64 v4; // rax
  _QWORD *v5; // rdx
  __int64 v6; // r9
  _QWORD *v7; // r8
  unsigned __int16 *v8; // rax
  int v9; // r10d
  int v10; // r11d
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // ecx
  int v14; // eax

  v4 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::NewNode();
  v5 = (_QWORD *)*a1;
  v6 = v4;
  v7 = 0;
  while ( v5 != (_QWORD *)a1[5] )
  {
    v7 = v5;
    v8 = a2;
    do
    {
      v9 = *(unsigned __int16 *)((char *)v8 + *v5 - (_QWORD)a2);
      v10 = *v8 - v9;
      if ( v10 )
        break;
      ++v8;
    }
    while ( v9 );
    v11 = 3;
    if ( v10 > 0 )
      v11 = 4;
    v5 = (_QWORD *)v5[v11];
  }
  *(_QWORD *)(v6 + 40) = v7;
  if ( v7 )
  {
    v12 = *v7 - (_QWORD)a2;
    do
    {
      v13 = *(unsigned __int16 *)((char *)a2 + v12);
      v14 = *a2 - v13;
      if ( v14 )
        break;
      ++a2;
    }
    while ( v13 );
    if ( v14 > 0 )
      v7[4] = v6;
    else
      v7[3] = v6;
  }
  else
  {
    *a1 = v6;
  }
  return v6;
}

```

## disassembly

```asm
0x18000f4e4  mov     [rsp+arg_0], rbx
0x18000f4e9  push    rdi
0x18000f4ea  sub     rsp, 20h
0x18000f4ee  mov     rbx, rdx
0x18000f4f1  mov     rdi, rcx
0x18000f4f4  call    ?NewNode@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCVolumeTrackingDescriptor@@@@@2@@ATL@@AEAAPEAVCNode@12@PEBGAEBV?$SmartPtr@VCVolumeTrackingDescriptor@@@@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CVolumeTrackingDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CVolumeTrackingDescriptor>>>::NewNode(ushort const *,SmartPtr<CVolumeTrackingDescriptor> const &)
0x18000f4f9  mov     rdx, [rdi]
0x18000f4fc  mov     r9, rax
0x18000f4ff  xor     r8d, r8d
0x18000f502  cmp     rdx, [rdi+28h]
0x18000f506  jz      short loc_18000F53F
0x18000f508  mov     rcx, [rdx]
0x18000f50b  mov     r8, rdx
0x18000f50e  sub     rcx, rbx
0x18000f511  mov     rax, rbx
0x18000f514  movzx   r11d, word ptr [rax]
0x18000f518  movzx   r10d, word ptr [rax+rcx]
0x18000f51d  sub     r11d, r10d
0x18000f520  jnz     short loc_18000F52B
0x18000f522  add     rax, 2
0x18000f526  test    r10d, r10d
0x18000f529  jnz     short loc_18000F514
0x18000f52b  mov     eax, 18h
0x18000f530  test    r11d, r11d
0x18000f533  lea     ecx, [rax+8]
0x18000f536  cmovg   eax, ecx
0x18000f539  mov     rdx, [rax+rdx]
0x18000f53d  jmp     short loc_18000F502
0x18000f53f  mov     [r9+28h], r8
0x18000f543  test    r8, r8
0x18000f546  jnz     short loc_18000F54D
0x18000f548  mov     [rdi], r9
0x18000f54b  jmp     short loc_18000F574
0x18000f54d  mov     rdx, [r8]
0x18000f550  sub     rdx, rbx
0x18000f553  movzx   eax, word ptr [rbx]
0x18000f556  movzx   ecx, word ptr [rbx+rdx]
0x18000f55a  sub     eax, ecx
0x18000f55c  jnz     short loc_18000F566
0x18000f55e  add     rbx, 2
0x18000f562  test    ecx, ecx
0x18000f564  jnz     short loc_18000F553
0x18000f566  test    eax, eax
0x18000f568  jg      short loc_18000F570
0x18000f56a  mov     [r8+18h], r9
0x18000f56e  jmp     short loc_18000F574
0x18000f570  mov     [r8+20h], r9
0x18000f574  mov     rbx, [rsp+28h+arg_0]
0x18000f579  mov     rax, r9
0x18000f57c  add     rsp, 20h
0x18000f580  pop     rdi
0x18000f581  retn
```
