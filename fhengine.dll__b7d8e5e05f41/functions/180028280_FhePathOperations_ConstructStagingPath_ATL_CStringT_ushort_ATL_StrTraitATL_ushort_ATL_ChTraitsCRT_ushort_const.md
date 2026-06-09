# FhePathOperations::ConstructStagingPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180028280`
- end: `0x180028500`
- name: `?ConstructStagingPath@FhePathOperations@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0JJAEAV23@@Z`
- size: `640`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, unsigned int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180009a80`

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
- `0x180028280`
- `0x180028cdc`
- `0x18002b590`

## pseudocode

```c
__int64 __fastcall FhePathOperations::ConstructStagingPath(
        __int64 *a1,
        _QWORD *a2,
        unsigned int a3,
        int a4,
        _QWORD *a5)
{
  unsigned int v8; // r14d
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rcx
  _QWORD *v11; // rbx
  int *v12; // rsi
  volatile signed __int32 *v13; // r15
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  ATL::CStringData *v16; // rcx
  ATL::CStringData *v17; // rsi
  int v18; // r15d
  int v19; // eax
  _QWORD *v20; // rax
  int v22; // [rsp+20h] [rbp-48h]
  __int64 v23; // [rsp+70h] [rbp+8h] BYREF

  v8 = 0;
  v9 = *a1;
  v10 = (volatile signed __int32 *)(*a1 - 24);
  v11 = a5;
  v12 = (int *)(*a5 - 24LL);
  if ( v10 != v12 )
  {
    if ( v12[4] >= 0 && *(_QWORD *)v10 == *(_QWORD *)v12 )
    {
      v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v10);
      ATL::CStringData::Release((ATL::CStringData *)v12);
      *v11 = v13 + 6;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(a5, v9, *(unsigned int *)(v9 - 16));
    }
  }
  if ( *(_DWORD *)(*v11 - 16LL) + *(_DWORD *)(*a2 - 16LL) < 260 )
  {
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                         a2,
                         L":",
                         0) != 1 )
    {
      v8 = -2147024809;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_2bbfbd6d1cce324407bd34be6d03c45c_Traceguids,
          *a2,
          87);
      return v8;
    }
    ATL::CSimpleStringT<unsigned short,0>::Append(v11, L"\\", 1);
    v14 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                      a2,
                      &a5,
                      1);
    ATL::CSimpleStringT<unsigned short,0>::Append(v11, *v14, *(unsigned int *)(*v14 - 16LL));
    ATL::CStringData::Release((ATL::CStringData *)(a5 - 3));
    v15 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                      a2,
                      &a5,
                      2);
    ATL::CSimpleStringT<unsigned short,0>::Append(v11, *v15, *(unsigned int *)(*v15 - 16LL));
    v16 = (ATL::CStringData *)(a5 - 3);
LABEL_20:
    ATL::CStringData::Release(v16);
    return v8;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&a5);
  v22 = a4;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &a5,
    L"\\%s\\%d\\%d",
    L"$OF",
    a3,
    v22);
  v17 = (ATL::CStringData *)(a5 - 3);
  ATL::CSimpleStringT<unsigned short,0>::Append(v11, a5, *((unsigned int *)a5 - 4));
  v18 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
          a2,
          92);
  if ( v18 > 0 )
  {
    v19 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
            a2,
            46);
    if ( v19 > v18 )
    {
      v20 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                        a2,
                        &v23,
                        (unsigned int)v19);
      ATL::CSimpleStringT<unsigned short,0>::Append(v11, *v20, *(unsigned int *)(*v20 - 16LL));
      ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
    }
    v16 = v17;
    goto LABEL_20;
  }
  v8 = -2147024809;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_2bbfbd6d1cce324407bd34be6d03c45c_Traceguids,
      *a2,
      87);
  ATL::CStringData::Release(v17);
  return v8;
}

```

## disassembly

```asm
0x180028280  mov     [rsp+arg_8], rbx
0x180028285  mov     [rsp+arg_10], rsi
0x18002828a  push    rdi
0x18002828b  push    r12
0x18002828d  push    r13
0x18002828f  push    r14
0x180028291  push    r15
0x180028293  sub     rsp, 40h
0x180028297  mov     r12d, r9d
0x18002829a  mov     r13d, r8d
0x18002829d  mov     rdi, rdx
0x1800282a0  xor     r14d, r14d
0x1800282a3  mov     rdx, [rcx]
0x1800282a6  lea     rcx, [rdx-18h]
0x1800282aa  mov     rbx, [rsp+68h+arg_20]
0x1800282b2  mov     rsi, [rbx]
0x1800282b5  add     rsi, 0FFFFFFFFFFFFFFE8h
0x1800282b9  cmp     rcx, rsi
0x1800282bc  jz      short loc_1800282F1
0x1800282be  cmp     [rsi+10h], r14d
0x1800282c2  jl      short loc_1800282E5
0x1800282c4  mov     rax, [rsi]
0x1800282c7  cmp     [rcx], rax
0x1800282ca  jnz     short loc_1800282E5
0x1800282cc  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800282d1  mov     r15, rax
0x1800282d4  mov     rcx, rsi; this
0x1800282d7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800282dc  lea     rax, [r15+18h]
0x1800282e0  mov     [rbx], rax
0x1800282e3  jmp     short loc_1800282F1
0x1800282e5  mov     r8d, [rdx-10h]
0x1800282e9  mov     rcx, rbx
0x1800282ec  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800282f1  mov     rax, [rdi]
0x1800282f4  mov     rcx, [rbx]
0x1800282f7  mov     edx, [rax-10h]
0x1800282fa  add     edx, [rcx-10h]
0x1800282fd  cmp     edx, 104h
0x180028303  jge     loc_1800283E8
0x180028309  xor     r8d, r8d
0x18002830c  lea     rdx, asc_1800384A8; ":"
0x180028313  mov     rcx, rdi
0x180028316  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x18002831b  cmp     eax, 1
0x18002831e  jz      short loc_180028363
0x180028320  mov     eax, 80070057h
0x180028325  mov     r14d, eax
0x180028328  lea     rdx, WPP_GLOBAL_Control
0x18002832f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028336  cmp     rcx, rdx
0x180028339  jz      short loc_18002835E
0x18002833b  test    byte ptr [rcx+1Ch], 1
0x18002833f  jz      short loc_18002835E
0x180028341  mov     edx, 0Dh
0x180028346  mov     [rsp+68h+var_48], eax
0x18002834a  mov     r9, [rdi]
0x18002834d  lea     r8, WPP_2bbfbd6d1cce324407bd34be6d03c45c_Traceguids
0x180028354  mov     rcx, [rcx+10h]
0x180028358  call    WPP_SF_Sd
0x18002835d  nop
0x18002835e  jmp     loc_1800284E3
0x180028363  mov     r8d, 1
0x180028369  lea     rdx, asc_180037180; "\\"
0x180028370  mov     rcx, rbx
0x180028373  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180028378  mov     r8d, 1
0x18002837e  lea     rdx, [rsp+68h+arg_20]
0x180028386  mov     rcx, rdi
0x180028389  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18002838e  nop
0x18002838f  mov     rdx, [rax]
0x180028392  mov     r8d, [rdx-10h]
0x180028396  mov     rcx, rbx
0x180028399  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18002839e  nop
0x18002839f  mov     rcx, [rsp+68h+arg_20]
0x1800283a7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800283ab  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800283b0  mov     r8d, 2
0x1800283b6  lea     rdx, [rsp+68h+arg_20]
0x1800283be  mov     rcx, rdi
0x1800283c1  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int)
0x1800283c6  nop
0x1800283c7  mov     rdx, [rax]
0x1800283ca  mov     r8d, [rdx-10h]
0x1800283ce  mov     rcx, rbx
0x1800283d1  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800283d6  nop
0x1800283d7  mov     rcx, [rsp+68h+arg_20]
0x1800283df  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1800283e3  jmp     loc_1800284D3
0x1800283e8  lea     rcx, [rsp+68h+arg_20]
0x1800283f0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800283f5  nop
0x1800283f6  mov     [rsp+68h+var_48], r12d
0x1800283fb  mov     r9d, r13d
0x1800283fe  lea     r8, aOf; "$OF"
0x180028405  lea     rdx, aSDD; "\\%s\\%d\\%d"
0x18002840c  lea     rcx, [rsp+68h+arg_20]
0x180028414  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180028419  mov     rdx, [rsp+68h+arg_20]
0x180028421  lea     rsi, [rdx-18h]
0x180028425  mov     r8d, [rsi+8]
0x180028429  mov     rcx, rbx
0x18002842c  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180028431  mov     edx, 5Ch ; '\'
0x180028436  mov     rcx, rdi
0x180028439  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x18002843e  mov     r15d, eax
0x180028441  test    eax, eax
0x180028443  jg      short loc_18002848E
0x180028445  mov     eax, 80070057h
0x18002844a  mov     r14d, eax
0x18002844d  lea     rdx, WPP_GLOBAL_Control
0x180028454  mov     rcx, cs:WPP_GLOBAL_Control
0x18002845b  cmp     rcx, rdx
0x18002845e  jz      short loc_180028483
0x180028460  test    byte ptr [rcx+1Ch], 1
0x180028464  jz      short loc_180028483
0x180028466  mov     edx, 0Eh
0x18002846b  mov     [rsp+68h+var_48], eax
0x18002846f  mov     r9, [rdi]
0x180028472  lea     r8, WPP_2bbfbd6d1cce324407bd34be6d03c45c_Traceguids
0x180028479  mov     rcx, [rcx+10h]
0x18002847d  call    WPP_SF_Sd
0x180028482  nop
0x180028483  mov     rcx, rsi; this
0x180028486  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002848b  nop
0x18002848c  jmp     short loc_1800284E3
0x18002848e  mov     edx, 2Eh ; '.'
0x180028493  mov     rcx, rdi
0x180028496  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x18002849b  cmp     eax, r15d
0x18002849e  jle     short loc_1800284D0
0x1800284a0  mov     r8d, eax
0x1800284a3  lea     rdx, [rsp+68h+arg_0]
0x1800284a8  mov     rcx, rdi
0x1800284ab  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int)
0x1800284b0  nop
0x1800284b1  mov     rdx, [rax]
0x1800284b4  mov     r8d, [rdx-10h]
0x1800284b8  mov     rcx, rbx
0x1800284bb  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800284c0  nop
0x1800284c1  mov     rcx, [rsp+68h+arg_0]
0x1800284c6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800284ca  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800284cf  nop
0x1800284d0  mov     rcx, rsi; this
0x1800284d3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800284d8  nop
0x1800284d9  jmp     short loc_1800284E3
0x1800284db  mov     r14d, dword ptr [rsp+68h+arg_20]
0x1800284e3  mov     eax, r14d
0x1800284e6  lea     r11, [rsp+68h+var_28]
0x1800284eb  mov     rbx, [r11+38h]
0x1800284ef  mov     rsi, [r11+40h]
0x1800284f3  mov     rsp, r11
0x1800284f6  pop     r15
0x1800284f8  pop     r14
0x1800284fa  pop     r13
0x1800284fc  pop     r12
0x1800284fe  pop     rdi
0x1800284ff  retn
```
