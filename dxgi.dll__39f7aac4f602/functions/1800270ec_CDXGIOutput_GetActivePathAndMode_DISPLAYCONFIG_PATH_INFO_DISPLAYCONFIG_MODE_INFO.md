# CDXGIOutput::GetActivePathAndMode(DISPLAYCONFIG_PATH_INFO &,DISPLAYCONFIG_MODE_INFO &)

- ea: `0x1800270ec`
- end: `0x1800273e4`
- name: `?GetActivePathAndMode@CDXGIOutput@@QEAAJAEAUDISPLAYCONFIG_PATH_INFO@@AEAUDISPLAYCONFIG_MODE_INFO@@@Z`
- size: `760`
- prototype: `__int64 __fastcall(CDXGIOutput *__hidden this, struct DISPLAYCONFIG_PATH_INFO *, struct DISPLAYCONFIG_MODE_INFO *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800131c0`
- `0x180027038`
- `0x18008767c`

## callees

- `0x1800148b8`
- `0x18001960c`
- `0x1800270ec`
- `0x180044640`
- `0x18004e19c`
- `0x18004e3e4`
- `0x18004e690`
- `0x180053084`
- `0x18006d024`
- `0x180088468`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180027246`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180027246`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180027147`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180027147`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDXGIOutput::GetActivePathAndMode(
        CDXGIOutput *this,
        struct DISPLAYCONFIG_PATH_INFO *a2,
        struct DISPLAYCONFIG_MODE_INFO *a3)
{
  CDXGIOutput *v6; // rcx
  LONG DisplayConfigBufferSizes; // eax
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  LONG v12; // eax
  __int64 v13; // rdx
  DISPLAYCONFIG_PATH_INFO *v14; // rdi
  __int64 v15; // rbx
  unsigned __int64 v16; // rcx
  DISPLAYCONFIG_MODE_INFO *v17; // rax
  UINT32 numModeInfoArrayElements[4]; // [rsp+30h] [rbp-40h] BYREF
  DISPLAYCONFIG_PATH_INFO *pathArray[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+50h] [rbp-20h]
  DISPLAYCONFIG_MODE_INFO *modeInfoArray[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v22; // [rsp+68h] [rbp-8h]
  UINT32 numPathArrayElements; // [rsp+B8h] [rbp+48h] BYREF

  if ( CDXGIOutput::IsRemoteXddmOutput(this) )
    return 2289696802LL;
  CDXGIOutput::GetAdapterLuid(v6);
  numPathArrayElements = 0;
  numModeInfoArrayElements[0] = 0;
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, numModeInfoArrayElements);
  if ( DisplayConfigBufferSizes == 31 )
    return 2147500037LL;
  if ( DisplayConfigBufferSizes )
    return 2289696805LL;
  *(_OWORD *)pathArray = 0;
  v9 = 0;
  v20 = 0;
  *(_OWORD *)modeInfoArray = 0;
  v22 = 0;
  while ( 1 )
  {
    v10 = 0x8E38E38E38E38E39uLL * (((char *)pathArray[1] - (char *)pathArray[0]) >> 3);
    if ( numPathArrayElements >= v10 )
    {
      if ( numPathArrayElements > v10 )
      {
        if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL
                                   * ((signed __int64)(v9 - (unsigned __int64)pathArray[0]) >> 3) )
          pathArray[1] = (DISPLAYCONFIG_PATH_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                                                      pathArray[1],
                                                      numPathArrayElements - v10);
        else
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(pathArray);
      }
    }
    else
    {
      pathArray[1] = &pathArray[0][numPathArrayElements];
    }
    v11 = modeInfoArray[1] - modeInfoArray[0];
    if ( numModeInfoArrayElements[0] >= v11 )
    {
      if ( numModeInfoArrayElements[0] > v11 )
      {
        if ( numModeInfoArrayElements[0] <= (unsigned __int64)((signed __int64)(v22 - (unsigned __int64)modeInfoArray[0]) >> 6) )
          modeInfoArray[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                          modeInfoArray[1],
                                                          numModeInfoArrayElements[0] - v11);
        else
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(modeInfoArray);
      }
    }
    else
    {
      modeInfoArray[1] = &modeInfoArray[0][(unsigned __int64)numModeInfoArrayElements[0]];
    }
    v12 = QueryDisplayConfig(2u, &numPathArrayElements, pathArray[0], numModeInfoArrayElements, modeInfoArray[0], 0);
    if ( v12 != 111 )
      break;
    v9 = v20;
  }
  if ( v12 == 31 )
    goto LABEL_21;
  if ( v12 )
  {
    std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(modeInfoArray);
    if ( pathArray[0] )
      std::_Deallocate<16>(pathArray[0], 8 * ((signed __int64)(v20 - (unsigned __int64)pathArray[0]) >> 3));
    return 2289696805LL;
  }
  if ( !numPathArrayElements )
  {
LABEL_21:
    std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(modeInfoArray);
    if ( pathArray[0] )
      std::_Deallocate<16>(pathArray[0], 8 * ((signed __int64)(v20 - (unsigned __int64)pathArray[0]) >> 3));
    return 2147500037LL;
  }
  v13 = 0;
  v14 = pathArray[0];
  while ( 1 )
  {
    v15 = v13;
    if ( pathArray[0][v13].sourceInfo.adapterId.LowPart == numModeInfoArrayElements[2]
      && *(_QWORD *)&pathArray[0][v13].sourceInfo.adapterId.HighPart == __PAIR64__(
                                                                          *((_DWORD *)this + 64),
                                                                          numModeInfoArrayElements[3]) )
    {
      break;
    }
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= numPathArrayElements )
      goto LABEL_21;
  }
  *(_OWORD *)&a2->sourceInfo.adapterId.LowPart = *(_OWORD *)&pathArray[0][v13].sourceInfo.adapterId.LowPart;
  *(_OWORD *)&a2->sourceInfo.statusFlags = *(_OWORD *)&v14[v13].sourceInfo.statusFlags;
  *(_OWORD *)&a2->targetInfo.modeInfoIdx = *(_OWORD *)&v14[v13].targetInfo.modeInfoIdx;
  *(_OWORD *)&a2->targetInfo.refreshRate.Numerator = *(_OWORD *)&v14[v13].targetInfo.refreshRate.Numerator;
  *(_QWORD *)&a2->targetInfo.statusFlags = *(_QWORD *)&v14[v13].targetInfo.statusFlags;
  v16 = (unsigned __int64)v14[v13].sourceInfo.modeInfoIdx << 6;
  v17 = modeInfoArray[0];
  *(_OWORD *)&a3->infoType = *(_OWORD *)((char *)&modeInfoArray[0]->infoType + v16);
  *(_OWORD *)&a3->targetMode.targetVideoSignalInfo.pixelRate = *(_OWORD *)((char *)&v17->targetMode.targetVideoSignalInfo.pixelRate
                                                                         + v16);
  *(_OWORD *)&a3->desktopImageInfo.DesktopImageRegion.right = *(_OWORD *)((char *)&v17->desktopImageInfo.DesktopImageRegion.right
                                                                        + v16);
  *(_OWORD *)&a3->desktopImageInfo.DesktopImageClip.right = *(_OWORD *)((char *)&v17->desktopImageInfo.DesktopImageClip.right
                                                                      + v16);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl'::`2'::impl) )
  {
    *((_DWORD *)this + 125) = v14[v15].targetInfo.outputTechnology;
    *((_BYTE *)this + 504) = 1;
  }
  std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(modeInfoArray);
  if ( pathArray[0] )
    std::_Deallocate<16>(pathArray[0], 8 * ((signed __int64)(v20 - (unsigned __int64)pathArray[0]) >> 3));
  return 0;
}

```

## disassembly

```asm
0x1800270ec  mov     [rsp-28h+arg_0], rbx
0x1800270f1  mov     [rsp-28h+arg_8], rsi
0x1800270f6  push    rbp
0x1800270f7  push    rdi
0x1800270f8  push    r13
0x1800270fa  push    r14
0x1800270fc  push    r15
0x1800270fe  mov     rbp, rsp
0x180027101  sub     rsp, 70h
0x180027105  mov     r15, r8
0x180027108  mov     r14, rdx
0x18002710b  mov     rsi, rcx
0x18002710e  call    ?IsRemoteXddmOutput@CDXGIOutput@@QEAA_NXZ; CDXGIOutput::IsRemoteXddmOutput(void)
0x180027113  test    al, al
0x180027115  jz      short loc_180027121
0x180027117  mov     eax, 887A0022h
0x18002711c  jmp     loc_180027293
0x180027121  lea     rdx, [rbp+var_38]
0x180027125  call    ?GetAdapterLuid@CDXGIOutput@@QEBA?AU_LUID@@XZ; CDXGIOutput::GetAdapterLuid(void)
0x18002712a  mov     [rbp+numPathArrayElements], 0
0x180027131  mov     [rbp+numModeInfoArrayElements], 0
0x180027138  lea     r8, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x18002713c  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x180027140  mov     ebx, 2
0x180027145  mov     ecx, ebx; flags
0x180027147  call    cs:__imp_GetDisplayConfigBufferSizes
0x18002714d  cmp     eax, 1Fh
0x180027150  jz      loc_18002728E
0x180027156  test    eax, eax
0x180027158  jnz     loc_1800272DF
0x18002715e  xorps   xmm0, xmm0
0x180027161  movdqu  xmmword ptr [rbp+pathArray], xmm0
0x180027166  xor     eax, eax
0x180027168  mov     [rbp+var_20], rax
0x18002716c  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180027171  mov     [rbp+var_8], rax
0x180027175  mov     r13, 8E38E38E38E38E39h
0x18002717f  mov     edx, [rbp+numPathArrayElements]
0x180027182  mov     r8, [rbp+pathArray]
0x180027186  mov     rcx, [rbp+pathArray+8]
0x18002718a  sub     rcx, r8
0x18002718d  sar     rcx, 3
0x180027191  imul    rcx, r13
0x180027195  cmp     rdx, rcx
0x180027198  jnb     short loc_1800271A8
0x18002719a  lea     rax, [rdx+rdx*8]
0x18002719e  lea     rcx, [r8+rax*8]
0x1800271a2  mov     [rbp+pathArray+8], rcx
0x1800271a6  jmp     short loc_1800271D5
0x1800271a8  jbe     short loc_1800271D5
0x1800271aa  sub     rax, r8
0x1800271ad  sar     rax, 3
0x1800271b1  imul    rax, r13
0x1800271b5  cmp     rdx, rax
0x1800271b8  jbe     short loc_1800271C5
0x1800271ba  lea     rcx, [rbp+pathArray]
0x1800271be  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800271c3  jmp     short loc_1800271D5
0x1800271c5  sub     rdx, rcx
0x1800271c8  mov     rcx, [rbp+pathArray+8]
0x1800271cc  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x1800271d1  mov     [rbp+pathArray+8], rax
0x1800271d5  mov     edx, [rbp+numModeInfoArrayElements]
0x1800271d8  mov     r8, [rbp+var_18]
0x1800271dc  mov     rcx, [rbp+var_18+8]
0x1800271e0  sub     rcx, r8
0x1800271e3  sar     rcx, 6
0x1800271e7  cmp     rdx, rcx
0x1800271ea  jnb     short loc_1800271F9
0x1800271ec  shl     rdx, 6
0x1800271f0  add     rdx, r8
0x1800271f3  mov     [rbp+var_18+8], rdx
0x1800271f7  jmp     short loc_180027226
0x1800271f9  jbe     short loc_180027226
0x1800271fb  mov     rax, [rbp+var_8]
0x1800271ff  sub     rax, r8
0x180027202  sar     rax, 6
0x180027206  cmp     rdx, rax
0x180027209  jbe     short loc_180027216
0x18002720b  lea     rcx, [rbp+var_18]
0x18002720f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180027214  jmp     short loc_180027226
0x180027216  sub     rdx, rcx
0x180027219  mov     rcx, [rbp+var_18+8]
0x18002721d  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x180027222  mov     [rbp+var_18+8], rax
0x180027226  mov     rax, [rbp+var_18]
0x18002722a  mov     [rsp+70h+currentTopologyId], 0; currentTopologyId
0x180027233  mov     [rsp+70h+modeInfoArray], rax; modeInfoArray
0x180027238  lea     r9, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x18002723c  mov     r8, [rbp+pathArray]; pathArray
0x180027240  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x180027244  mov     ecx, ebx; flags
0x180027246  call    cs:__imp_QueryDisplayConfig
0x18002724c  cmp     eax, 6Fh ; 'o'
0x18002724f  jnz     short loc_18002725A
0x180027251  mov     rax, [rbp+var_20]
0x180027255  jmp     loc_18002717F
0x18002725a  cmp     eax, 1Fh
0x18002725d  jnz     short loc_1800272AC
0x18002725f  lea     rcx, [rbp+var_18]
0x180027263  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x180027268  nop
0x180027269  mov     rcx, [rbp+pathArray]
0x18002726d  test    rcx, rcx
0x180027270  jz      short loc_18002728E
0x180027272  mov     rax, [rbp+var_20]
0x180027276  sub     rax, rcx
0x180027279  sar     rax, 3
0x18002727d  imul    rax, r13
0x180027281  lea     rdx, [rax+rax*8]
0x180027285  shl     rdx, 3
0x180027289  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002728e  mov     eax, 80004005h
0x180027293  lea     r11, [rsp+70h+var_s0]
0x180027298  mov     rbx, [r11+30h]
0x18002729c  mov     rsi, [r11+38h]
0x1800272a0  mov     rsp, r11
0x1800272a3  pop     r15
0x1800272a5  pop     r14
0x1800272a7  pop     r13
0x1800272a9  pop     rdi
0x1800272aa  pop     rbp
0x1800272ab  retn
0x1800272ac  test    eax, eax
0x1800272ae  jz      short loc_1800272E6
0x1800272b0  lea     rcx, [rbp+var_18]
0x1800272b4  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x1800272b9  nop
0x1800272ba  mov     rcx, [rbp+pathArray]
0x1800272be  test    rcx, rcx
0x1800272c1  jz      short loc_1800272DF
0x1800272c3  mov     rax, [rbp+var_20]
0x1800272c7  sub     rax, rcx
0x1800272ca  sar     rax, 3
0x1800272ce  imul    rax, r13
0x1800272d2  lea     rdx, [rax+rax*8]
0x1800272d6  shl     rdx, 3
0x1800272da  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800272df  mov     eax, 887A0025h
0x1800272e4  jmp     short loc_180027293
0x1800272e6  mov     r8d, [rbp+numPathArrayElements]
0x1800272ea  test    r8d, r8d
0x1800272ed  jz      loc_18002725F
0x1800272f3  xor     edx, edx
0x1800272f5  mov     rax, [rbp+var_38]
0x1800272f9  mov     r9d, dword ptr [rbp+var_38+4]
0x1800272fd  mov     rdi, [rbp+pathArray]
0x180027301  lea     rbx, [rdx+rdx*8]
0x180027305  cmp     [rdi+rbx*8], eax
0x180027308  jnz     short loc_18002731D
0x18002730a  cmp     [rdi+rbx*8+4], r9d
0x18002730f  jnz     short loc_18002731D
0x180027311  mov     ecx, [rsi+100h]
0x180027317  cmp     [rdi+rbx*8+8], ecx
0x18002731b  jz      short loc_180027329
0x18002731d  inc     edx
0x18002731f  cmp     edx, r8d
0x180027322  jb      short loc_180027301
0x180027324  jmp     loc_18002725F
0x180027329  movups  xmm0, xmmword ptr [rdi+rbx*8]
0x18002732d  movaps  xmmword ptr [r14], xmm0
0x180027331  movups  xmm1, xmmword ptr [rdi+rbx*8+10h]
0x180027336  movaps  xmmword ptr [r14+10h], xmm1
0x18002733b  movups  xmm0, xmmword ptr [rdi+rbx*8+20h]
0x180027340  movaps  xmmword ptr [r14+20h], xmm0
0x180027345  movups  xmm1, xmmword ptr [rdi+rbx*8+30h]
0x18002734a  movaps  xmmword ptr [r14+30h], xmm1
0x18002734f  movsd   xmm0, qword ptr [rdi+rbx*8+40h]
0x180027355  movsd   qword ptr [r14+40h], xmm0
0x18002735b  mov     ecx, [rdi+rbx*8+0Ch]
0x18002735f  shl     rcx, 6
0x180027363  mov     rax, [rbp+var_18]
0x180027367  movups  xmm0, xmmword ptr [rcx+rax]
0x18002736b  movaps  xmmword ptr [r15], xmm0
0x18002736f  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x180027374  movaps  xmmword ptr [r15+10h], xmm1
0x180027379  movups  xmm0, xmmword ptr [rcx+rax+20h]
0x18002737e  movaps  xmmword ptr [r15+20h], xmm0
0x180027383  movups  xmm1, xmmword ptr [rcx+rax+30h]
0x180027388  movaps  xmmword ptr [r15+30h], xmm1
0x18002738d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2603@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2603>::GetImpl(void)'::`2'::impl
0x180027394  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2603@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2603>::__private_IsEnabled(void)
0x180027399  test    al, al
0x18002739b  jz      short loc_1800273AE
0x18002739d  mov     eax, [rdi+rbx*8+24h]
0x1800273a1  mov     [rsi+1F4h], eax
0x1800273a7  mov     byte ptr [rsi+1F8h], 1
0x1800273ae  lea     rcx, [rbp+var_18]
0x1800273b2  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x1800273b7  nop
0x1800273b8  mov     rcx, [rbp+pathArray]
0x1800273bc  test    rcx, rcx
0x1800273bf  jz      short loc_1800273DD
0x1800273c1  mov     rax, [rbp+var_20]
0x1800273c5  sub     rax, rcx
0x1800273c8  sar     rax, 3
0x1800273cc  imul    rax, r13
0x1800273d0  lea     rdx, [rax+rax*8]
0x1800273d4  shl     rdx, 3
0x1800273d8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800273dd  xor     eax, eax
0x1800273df  jmp     loc_180027293
```
