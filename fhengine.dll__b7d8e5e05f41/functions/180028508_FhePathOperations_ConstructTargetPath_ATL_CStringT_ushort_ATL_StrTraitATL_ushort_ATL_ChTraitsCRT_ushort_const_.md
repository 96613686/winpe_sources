# FhePathOperations::ConstructTargetPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180028508`
- end: `0x18002883f`
- name: `?ConstructTargetPath@FhePathOperations@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0JJ0AEAV23@@Z`
- size: `823`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, unsigned int, int, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180009d70`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x180008fa0`
- `0x1800091a4`
- `0x180009258`
- `0x1800097b0`
- `0x180009920`
- `0x18000a1ec`
- `0x18000baa8`
- `0x180028508`
- `0x180028c9c`
- `0x18002b590`
- `0x18002b5b8`

## pseudocode

```c
__int64 __fastcall FhePathOperations::ConstructTargetPath(
        __int64 *a1,
        _QWORD *a2,
        unsigned int a3,
        int a4,
        _QWORD *a5,
        _QWORD *a6)
{
  unsigned int v7; // r13d
  unsigned int v10; // edi
  _QWORD *v11; // rcx
  int v12; // edx
  int v13; // edi
  unsigned int v14; // esi
  __int64 v15; // rdx
  volatile signed __int32 *v16; // rcx
  int *v17; // r15
  volatile signed __int32 *v18; // r13
  int v19; // edx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  ATL::CStringData *v24; // r15
  _QWORD *v25; // rax
  _QWORD v27[2]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v28[7]; // [rsp+40h] [rbp-38h] BYREF

  v7 = a3;
  if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                       a2,
                       58,
                       0) == 1 )
  {
    v13 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
            a2,
            92);
    if ( v13 > 1 )
    {
      v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
              a2,
              46);
      if ( (int)v14 <= v13 )
        v14 = -1;
      v15 = *a1;
      v16 = (volatile signed __int32 *)(*a1 - 24);
      v17 = (int *)(*a6 - 24LL);
      if ( v16 != v17 )
      {
        if ( v17[4] >= 0 && *(_QWORD *)v16 == *(_QWORD *)v17 )
        {
          v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v16);
          ATL::CStringData::Release((ATL::CStringData *)v17);
          *a6 = v18 + 6;
          v7 = a3;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(a6, v15, *(unsigned int *)(v15 - 16));
        }
      }
      v19 = 90;
      if ( *(int *)(*a6 - 16LL) > 90 )
        v19 = *(_DWORD *)(*a6 - 16LL);
      if ( *(_DWORD *)(*a5 - 16LL) + *(_DWORD *)(*a2 - 16LL) + v19 - 1 >= 260 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v27);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          v27,
          L"%s\\%d\\%d%s",
          L"$OF",
          v7,
          a4,
          *a5);
        v24 = (ATL::CStringData *)(v27[0] - 24LL);
        ATL::CSimpleStringT<unsigned short,0>::Append(a6, v27[0], *(unsigned int *)(v27[0] - 24LL + 8));
        if ( v14 != -1 && *(_DWORD *)(*a2 - 16LL) - v14 <= 0xB )
        {
          v25 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                            a2,
                            v28,
                            v14);
          ATL::CSimpleStringT<unsigned short,0>::Append(a6, *v25, *(unsigned int *)(*v25 - 16LL));
          ATL::CStringData::Release((ATL::CStringData *)(v28[0] - 24LL));
        }
        v10 = 1;
        ATL::CStringData::Release(v24);
      }
      else
      {
        v20 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                          a2,
                          v27,
                          1);
        ATL::CSimpleStringT<unsigned short,0>::Append(a6, *v20, *(unsigned int *)(*v20 - 16LL));
        ATL::CStringData::Release((ATL::CStringData *)(v27[0] - 24LL));
        if ( v14 == -1 )
        {
          v21 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                            a2,
                            v27,
                            2);
          ATL::CSimpleStringT<unsigned short,0>::Append(a6, *v21, *(unsigned int *)(*v21 - 16LL));
          ATL::CStringData::Release((ATL::CStringData *)(v27[0] - 24LL));
          ATL::CSimpleStringT<unsigned short,0>::Append(a6, *a5, *(unsigned int *)(*a5 - 16LL));
        }
        else
        {
          v22 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                            a2,
                            v27,
                            2,
                            v14 - 2);
          ATL::CSimpleStringT<unsigned short,0>::Append(a6, *v22, *(unsigned int *)(*v22 - 16LL));
          ATL::CStringData::Release((ATL::CStringData *)(v27[0] - 24LL));
          ATL::CSimpleStringT<unsigned short,0>::Append(a6, *a5, *(unsigned int *)(*a5 - 16LL));
          v23 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                            a2,
                            v27,
                            v14);
          ATL::CSimpleStringT<unsigned short,0>::Append(a6, *v23, *(unsigned int *)(*v23 - 16LL));
          ATL::CStringData::Release((ATL::CStringData *)(v27[0] - 24LL));
        }
        return 0;
      }
    }
    else
    {
      v10 = -2147024809;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 11;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v10 = -2147024809;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 10;
LABEL_5:
      WPP_SF_Sd(v11[2], v12, (unsigned int)WPP_2bbfbd6d1cce324407bd34be6d03c45c_Traceguids, *a2, 87);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180028508  mov     [rsp+arg_0], rbx
0x18002850d  mov     [rsp+arg_10], r8d
0x180028512  mov     [rsp+arg_8], rdx
0x180028517  push    rsi
0x180028518  push    rdi
0x180028519  push    r12
0x18002851b  push    r13
0x18002851d  push    r15
0x18002851f  sub     rsp, 50h
0x180028523  mov     r12d, r9d
0x180028526  mov     r13d, r8d
0x180028529  mov     rbx, rdx
0x18002852c  mov     r15, rcx
0x18002852f  mov     edx, 3Ah ; ':'
0x180028534  xor     r8d, r8d
0x180028537  mov     rcx, rbx
0x18002853a  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort,int)
0x18002853f  cmp     eax, 1
0x180028542  jz      short loc_18002857D
0x180028544  mov     r8d, 80070057h
0x18002854a  mov     edi, r8d
0x18002854d  lea     rax, WPP_GLOBAL_Control
0x180028554  mov     rcx, cs:WPP_GLOBAL_Control
0x18002855b  cmp     rcx, rax
0x18002855e  jz      loc_180028828
0x180028564  test    byte ptr [rcx+1Ch], 1
0x180028568  jz      loc_180028828
0x18002856e  mov     edx, 0Ah
0x180028573  mov     [rsp+78h+var_58], r8d
0x180028578  jmp     loc_180028815
0x18002857d  mov     edx, 5Ch ; '\'
0x180028582  mov     rcx, rbx
0x180028585  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x18002858a  mov     edi, eax
0x18002858c  cmp     eax, 1
0x18002858f  jg      short loc_1800285C2
0x180028591  mov     r8d, 80070057h
0x180028597  mov     edi, r8d
0x18002859a  lea     rax, WPP_GLOBAL_Control
0x1800285a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285a8  cmp     rcx, rax
0x1800285ab  jz      loc_180028828
0x1800285b1  test    byte ptr [rcx+1Ch], 1
0x1800285b5  jz      loc_180028828
0x1800285bb  mov     edx, 0Bh
0x1800285c0  jmp     short loc_180028573
0x1800285c2  mov     edx, 2Eh ; '.'
0x1800285c7  mov     rcx, rbx
0x1800285ca  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x1800285cf  mov     esi, eax
0x1800285d1  or      eax, 0FFFFFFFFh
0x1800285d4  cmp     esi, edi
0x1800285d6  cmovle  esi, eax
0x1800285d9  mov     rdx, [r15]
0x1800285dc  lea     rcx, [rdx-18h]
0x1800285e0  mov     rdi, [rsp+78h+arg_28]
0x1800285e8  mov     r15, [rdi]
0x1800285eb  add     r15, 0FFFFFFFFFFFFFFE8h
0x1800285ef  cmp     rcx, r15
0x1800285f2  jz      short loc_180028630
0x1800285f4  cmp     dword ptr [r15+10h], 0
0x1800285f9  jl      short loc_180028624
0x1800285fb  mov     rax, [r15]
0x1800285fe  cmp     [rcx], rax
0x180028601  jnz     short loc_180028624
0x180028603  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180028608  mov     r13, rax
0x18002860b  mov     rcx, r15; this
0x18002860e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028613  lea     rax, [r13+18h]
0x180028617  mov     [rdi], rax
0x18002861a  mov     r13d, [rsp+78h+arg_10]
0x180028622  jmp     short loc_180028630
0x180028624  mov     r8d, [rdx-10h]
0x180028628  mov     rcx, rdi
0x18002862b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180028630  mov     rax, [rdi]
0x180028633  mov     edx, 5Ah ; 'Z'
0x180028638  cmp     [rax-10h], edx
0x18002863b  cmovg   edx, [rax-10h]
0x18002863f  mov     rcx, [rbx]
0x180028642  mov     r15, [rsp+78h+arg_20]
0x18002864a  mov     rax, [r15]
0x18002864d  mov     ecx, [rcx-10h]
0x180028650  add     ecx, [rax-10h]
0x180028653  lea     eax, [rdx-1]
0x180028656  add     eax, ecx
0x180028658  cmp     eax, 104h
0x18002865d  jge     loc_18002874A
0x180028663  mov     r8d, 1
0x180028669  lea     rdx, [rsp+78h+var_48]
0x18002866e  mov     rcx, rbx
0x180028671  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x180028676  nop
0x180028677  mov     rdx, [rax]
0x18002867a  mov     r8d, [rdx-10h]
0x18002867e  mov     rcx, rdi
0x180028681  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180028686  nop
0x180028687  mov     rcx, [rsp+78h+var_48]
0x18002868c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180028690  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028695  mov     r8d, 2
0x18002869b  lea     rdx, [rsp+78h+var_48]
0x1800286a0  mov     rcx, rbx
0x1800286a3  cmp     esi, 0FFFFFFFFh
0x1800286a6  jnz     short loc_1800286DD
0x1800286a8  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int)
0x1800286ad  nop
0x1800286ae  mov     rdx, [rax]
0x1800286b1  mov     r8d, [rdx-10h]
0x1800286b5  mov     rcx, rdi
0x1800286b8  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800286bd  nop
0x1800286be  mov     rcx, [rsp+78h+var_48]
0x1800286c3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800286c7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800286cc  mov     rdx, [r15]
0x1800286cf  mov     r8d, [rdx-10h]
0x1800286d3  mov     rcx, rdi
0x1800286d6  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800286db  jmp     short loc_180028743
0x1800286dd  lea     r9d, [rsi-2]
0x1800286e1  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x1800286e6  nop
0x1800286e7  mov     rdx, [rax]
0x1800286ea  mov     r8d, [rdx-10h]
0x1800286ee  mov     rcx, rdi
0x1800286f1  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800286f6  nop
0x1800286f7  mov     rcx, [rsp+78h+var_48]
0x1800286fc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180028700  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028705  mov     rdx, [r15]
0x180028708  mov     r8d, [rdx-10h]
0x18002870c  mov     rcx, rdi
0x18002870f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180028714  mov     r8d, esi
0x180028717  lea     rdx, [rsp+78h+var_48]
0x18002871c  mov     rcx, rbx
0x18002871f  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int)
0x180028724  nop
0x180028725  mov     rdx, [rax]
0x180028728  mov     r8d, [rdx-10h]
0x18002872c  mov     rcx, rdi
0x18002872f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180028734  nop
0x180028735  mov     rcx, [rsp+78h+var_48]
0x18002873a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002873e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028743  xor     edi, edi
0x180028745  jmp     loc_1800287E1
0x18002874a  lea     rcx, [rsp+78h+var_48]
0x18002874f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180028754  nop
0x180028755  mov     rax, [r15]
0x180028758  mov     [rsp+78h+var_50], rax
0x18002875d  mov     [rsp+78h+var_58], r12d
0x180028762  mov     r9d, r13d
0x180028765  lea     r8, aOf; "$OF"
0x18002876c  lea     rdx, aSDDS; "%s\\%d\\%d%s"
0x180028773  lea     rcx, [rsp+78h+var_48]
0x180028778  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18002877d  mov     rdx, [rsp+78h+var_48]
0x180028782  lea     r15, [rdx-18h]
0x180028786  mov     r8d, [r15+8]
0x18002878a  mov     rcx, rdi
0x18002878d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180028792  cmp     esi, 0FFFFFFFFh
0x180028795  jz      short loc_1800287D3
0x180028797  mov     rax, [rbx]
0x18002879a  mov     ecx, [rax-10h]
0x18002879d  sub     ecx, esi
0x18002879f  cmp     ecx, 0Bh
0x1800287a2  ja      short loc_1800287D3
0x1800287a4  mov     r8d, esi
0x1800287a7  lea     rdx, [rsp+78h+var_38]
0x1800287ac  mov     rcx, rbx
0x1800287af  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int)
0x1800287b4  nop
0x1800287b5  mov     rdx, [rax]
0x1800287b8  mov     r8d, [rdx-10h]
0x1800287bc  mov     rcx, rdi
0x1800287bf  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800287c4  nop
0x1800287c5  mov     rcx, [rsp+78h+var_38]
0x1800287ca  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800287ce  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800287d3  mov     edi, 1
0x1800287d8  mov     rcx, r15; this
0x1800287db  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800287e0  nop
0x1800287e1  jmp     short loc_1800287EF
0x1800287e3  mov     rbx, [rsp+78h+arg_8]
0x1800287eb  mov     edi, dword ptr [rsp+78h+var_48]
0x1800287ef  test    edi, edi
0x1800287f1  jns     short loc_180028828
0x1800287f3  lea     rax, WPP_GLOBAL_Control
0x1800287fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180028801  cmp     rcx, rax
0x180028804  jz      short loc_180028828
0x180028806  test    byte ptr [rcx+1Ch], 1
0x18002880a  jz      short loc_180028828
0x18002880c  mov     edx, 0Ch
0x180028811  mov     [rsp+78h+var_58], edi
0x180028815  mov     r9, [rbx]
0x180028818  lea     r8, WPP_2bbfbd6d1cce324407bd34be6d03c45c_Traceguids
0x18002881f  mov     rcx, [rcx+10h]
0x180028823  call    WPP_SF_Sd
0x180028828  mov     eax, edi
0x18002882a  mov     rbx, [rsp+78h+arg_0]
0x180028832  add     rsp, 50h
0x180028836  pop     r15
0x180028838  pop     r13
0x18002883a  pop     r12
0x18002883c  pop     rdi
0x18002883d  pop     rsi
0x18002883e  retn
```
