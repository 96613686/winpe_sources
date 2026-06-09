# FindOutputCounts(std::vector<DISPLAYCONFIG_PATH_INFO,std::allocator<DISPLAYCONFIG_PATH_INFO>> &,std::map<_LUID,int,std::less<_LUID>,std::allocator<std::pair<_LUID const,int>>> &,_LUID &)

- ea: `0x18004de58`
- end: `0x18004e188`
- name: `?FindOutputCounts@@YAJAEAV?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAV?$map@U_LUID@@HU?$less@U_LUID@@@std@@V?$allocator@U?$pair@$$CBU_LUID@@H@std@@@3@@2@AEAU_LUID@@@Z`
- size: `816`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001d0a0`

## callees

- `0x18000c6b0`
- `0x18004de58`
- `0x18004e19c`
- `0x18004e210`
- `0x18004e3e4`
- `0x18004e690`
- `0x180053084`
- `0x18006d024`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x18004df5a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x18004df5a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18004deb1`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18004deb1`

## string_xrefs

- `0x18004e0a9`: `GetDisplayConfigBufferSizes failed on WNF_DX_DISPLAY_CONFIG_CHANGE_NOTIFICATION event`
- `0x18004e0d6`: `QueryDisplayConfig failed on WNF_DX_DISPLAY_CONFIG_CHANGE_NOTIFICATION event`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindOutputCounts(__int64 a1, __int64 a2, LUID *a3)
{
  CModule *v6; // rcx
  int DisplayConfigBufferSizes; // ebx
  bool v8; // r9
  DISPLAYCONFIG_PATH_INFO *v9; // r8
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  LONG v12; // eax
  DISPLAYCONFIG_PATH_INFO *v13; // r8
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  __int64 v16; // rsi
  DISPLAYCONFIG_PATH_INFO *i; // rcx
  DISPLAYCONFIG_PATH_INFO *v18; // r14
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  int v22; // esi
  unsigned int v23; // edx
  const char *v24; // r8
  UINT32 numModeInfoArrayElements; // [rsp+30h] [rbp-30h] BYREF
  char v26[16]; // [rsp+38h] [rbp-28h] BYREF
  DISPLAYCONFIG_MODE_INFO *modeInfoArray[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v28; // [rsp+58h] [rbp-8h]
  UINT32 numPathArrayElements; // [rsp+A8h] [rbp+48h] BYREF

  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  *(_OWORD *)modeInfoArray = 0;
  v28 = 0;
  do
  {
    DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(0x12u, &numPathArrayElements, &numModeInfoArrayElements);
    if ( DisplayConfigBufferSizes )
    {
      v22 = (unsigned __int16)DisplayConfigBufferSizes;
      if ( DisplayConfigBufferSizes > 0 )
        v23 = (unsigned __int16)DisplayConfigBufferSizes | 0x80070000;
      else
        v23 = DisplayConfigBufferSizes;
      v24 = "GetDisplayConfigBufferSizes failed on WNF_DX_DISPLAY_CONFIG_CHANGE_NOTIFICATION event";
      goto LABEL_31;
    }
    v9 = *(DISPLAYCONFIG_PATH_INFO **)a1;
    v10 = 0x8E38E38E38E38E39uLL * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3);
    if ( numPathArrayElements < v10 )
    {
      *(_QWORD *)(a1 + 8) = &v9[numPathArrayElements];
    }
    else if ( numPathArrayElements > v10 )
    {
      if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL * ((__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)v9) >> 3) )
        *(_QWORD *)(a1 + 8) = std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                                *(_QWORD *)(a1 + 8),
                                numPathArrayElements - v10);
      else
        std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(a1);
    }
    v11 = modeInfoArray[1] - modeInfoArray[0];
    if ( numModeInfoArrayElements < v11 )
    {
      modeInfoArray[1] = &modeInfoArray[0][(unsigned __int64)numModeInfoArrayElements];
    }
    else if ( numModeInfoArrayElements > v11 )
    {
      if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v28 - (unsigned __int64)modeInfoArray[0]) >> 6) )
        modeInfoArray[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                        modeInfoArray[1],
                                                        numModeInfoArrayElements - v11);
      else
        std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(modeInfoArray);
    }
    v12 = QueryDisplayConfig(
            0x12u,
            &numPathArrayElements,
            *(DISPLAYCONFIG_PATH_INFO **)a1,
            &numModeInfoArrayElements,
            modeInfoArray[0],
            0);
    DisplayConfigBufferSizes = v12;
  }
  while ( v12 == 122 );
  if ( !v12 )
  {
    v13 = *(DISPLAYCONFIG_PATH_INFO **)a1;
    v14 = 0x8E38E38E38E38E39uLL * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3);
    if ( numPathArrayElements < v14 )
    {
      *(_QWORD *)(a1 + 8) = &v13[numPathArrayElements];
    }
    else if ( numPathArrayElements > v14 )
    {
      if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL * ((__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)v13) >> 3) )
        *(_QWORD *)(a1 + 8) = std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                                *(_QWORD *)(a1 + 8),
                                numPathArrayElements - v14);
      else
        std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(a1);
    }
    v15 = modeInfoArray[1] - modeInfoArray[0];
    if ( numModeInfoArrayElements < v15 )
    {
      modeInfoArray[1] = &modeInfoArray[0][(unsigned __int64)numModeInfoArrayElements];
    }
    else if ( numModeInfoArrayElements > v15 )
    {
      if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v28 - (unsigned __int64)modeInfoArray[0]) >> 6) )
        modeInfoArray[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                        modeInfoArray[1],
                                                        numModeInfoArrayElements - v15);
      else
        std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(modeInfoArray);
    }
    v16 = 0;
    for ( i = *(DISPLAYCONFIG_PATH_INFO **)a1;
          (unsigned int)v16 < 954437177 * (unsigned int)((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3);
          i = *(DISPLAYCONFIG_PATH_INFO **)a1 )
    {
      v18 = &i[v16];
      v19 = std::map<_LUID,int>::_Try_emplace<_LUID const &,>(a2, v26, v18);
      ++*(_DWORD *)(*(_QWORD *)v19 + 36LL);
      v20 = (unsigned __int64)*(unsigned __int16 *)(*(_QWORD *)a1 + 72 * v16 + 14) << 6;
      if ( !*(UINT32 *)((char *)&modeInfoArray[0]->targetMode.targetVideoSignalInfo.hSyncFreq.Denominator + v20)
        && !*(UINT32 *)((char *)&modeInfoArray[0]->targetMode.targetVideoSignalInfo.vSyncFreq.Numerator + v20)
        && !*(_QWORD *)a3 )
      {
        *a3 = v18->sourceInfo.adapterId;
      }
      v16 = (unsigned int)(v16 + 1);
    }
    std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(modeInfoArray);
    return 0;
  }
  v22 = (unsigned __int16)v12;
  if ( v12 > 0 )
    v23 = (unsigned __int16)v12 | 0x80070000;
  else
    v23 = v12;
  v24 = "QueryDisplayConfig failed on WNF_DX_DISPLAY_CONFIG_CHANGE_NOTIFICATION event";
LABEL_31:
  CModule::RecordJournalImpl(v6, v23, v24, v8);
  if ( DisplayConfigBufferSizes > 0 )
    DisplayConfigBufferSizes = v22 | 0x80070000;
  std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(modeInfoArray);
  return (unsigned int)DisplayConfigBufferSizes;
}

```

## disassembly

```asm
0x18004de58  mov     [rsp-28h+arg_0], rbx
0x18004de5d  mov     [rsp-28h+arg_8], rsi
0x18004de62  push    rbp
0x18004de63  push    rdi
0x18004de64  push    r12
0x18004de66  push    r14
0x18004de68  push    r15
0x18004de6a  mov     rbp, rsp
0x18004de6d  sub     rsp, 60h
0x18004de71  mov     r15, r8
0x18004de74  mov     r12, rdx
0x18004de77  mov     rdi, rcx
0x18004de7a  mov     [rbp+numPathArrayElements], 0
0x18004de81  mov     [rbp+numModeInfoArrayElements], 0
0x18004de88  xorps   xmm0, xmm0
0x18004de8b  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18004de90  mov     [rbp+var_8], 0
0x18004de98  mov     esi, 12h
0x18004de9d  mov     r14, 8E38E38E38E38E39h
0x18004dea7  lea     r8, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x18004deab  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x18004deaf  mov     ecx, esi; flags
0x18004deb1  call    cs:__imp_GetDisplayConfigBufferSizes
0x18004deb7  mov     ebx, eax
0x18004deb9  test    eax, eax
0x18004debb  jnz     loc_18004E097
0x18004dec1  mov     edx, [rbp+numPathArrayElements]
0x18004dec4  mov     r8, [rdi]
0x18004dec7  mov     rcx, [rdi+8]
0x18004decb  sub     rcx, r8
0x18004dece  sar     rcx, 3
0x18004ded2  imul    rcx, r14
0x18004ded6  cmp     rdx, rcx
0x18004ded9  jb      loc_18004E111
0x18004dedf  jbe     short loc_18004DF01
0x18004dee1  mov     rax, [rdi+10h]
0x18004dee5  sub     rax, r8
0x18004dee8  sar     rax, 3
0x18004deec  imul    rax, r14
0x18004def0  cmp     rdx, rax
0x18004def3  jbe     loc_18004E133
0x18004def9  mov     rcx, rdi
0x18004defc  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18004df01  mov     edx, [rbp+numModeInfoArrayElements]
0x18004df04  mov     r8, [rbp+var_18]
0x18004df08  mov     rcx, [rbp+var_18+8]
0x18004df0c  sub     rcx, r8
0x18004df0f  sar     rcx, 6
0x18004df13  cmp     rdx, rcx
0x18004df16  jb      loc_18004E0F1
0x18004df1c  jbe     short loc_18004DF3B
0x18004df1e  mov     rax, [rbp+var_8]
0x18004df22  sub     rax, r8
0x18004df25  sar     rax, 6
0x18004df29  cmp     rdx, rax
0x18004df2c  jbe     loc_18004E148
0x18004df32  lea     rcx, [rbp+var_18]
0x18004df36  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18004df3b  mov     rax, [rbp+var_18]
0x18004df3f  mov     [rsp+60h+currentTopologyId], 0; currentTopologyId
0x18004df48  mov     [rsp+60h+modeInfoArray], rax; modeInfoArray
0x18004df4d  lea     r9, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x18004df51  mov     r8, [rdi]; pathArray
0x18004df54  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x18004df58  mov     ecx, esi; flags
0x18004df5a  call    cs:__imp_QueryDisplayConfig
0x18004df60  mov     ebx, eax
0x18004df62  cmp     eax, 7Ah ; 'z'
0x18004df65  jz      loc_18004DEA7
0x18004df6b  test    eax, eax
0x18004df6d  jnz     loc_18004E0C6
0x18004df73  mov     edx, [rbp+numPathArrayElements]
0x18004df76  mov     r8, [rdi]
0x18004df79  mov     rcx, [rdi+8]
0x18004df7d  sub     rcx, r8
0x18004df80  sar     rcx, 3
0x18004df84  imul    rcx, r14
0x18004df88  cmp     rdx, rcx
0x18004df8b  jb      loc_18004E122
0x18004df91  jbe     short loc_18004DFB3
0x18004df93  mov     rax, [rdi+10h]
0x18004df97  sub     rax, r8
0x18004df9a  sar     rax, 3
0x18004df9e  imul    rax, r14
0x18004dfa2  cmp     rdx, rax
0x18004dfa5  jbe     loc_18004E15D
0x18004dfab  mov     rcx, rdi
0x18004dfae  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18004dfb3  mov     edx, [rbp+numModeInfoArrayElements]
0x18004dfb6  mov     r8, [rbp+var_18]
0x18004dfba  mov     rcx, [rbp+var_18+8]
0x18004dfbe  sub     rcx, r8
0x18004dfc1  sar     rcx, 6
0x18004dfc5  cmp     rdx, rcx
0x18004dfc8  jb      loc_18004E101
0x18004dfce  jbe     short loc_18004DFED
0x18004dfd0  mov     rax, [rbp+var_8]
0x18004dfd4  sub     rax, r8
0x18004dfd7  sar     rax, 6
0x18004dfdb  cmp     rdx, rax
0x18004dfde  jbe     loc_18004E172
0x18004dfe4  lea     rcx, [rbp+var_18]
0x18004dfe8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18004dfed  xor     esi, esi
0x18004dfef  mov     rcx, [rdi]
0x18004dff2  mov     rax, [rdi+8]
0x18004dff6  sub     rax, rcx
0x18004dff9  sar     rax, 3
0x18004dffd  imul    rax, r14
0x18004e001  test    eax, eax
0x18004e003  jz      short loc_18004E05B
0x18004e005  lea     rbx, [rsi+rsi*8]
0x18004e009  lea     r14, [rcx+rbx*8]
0x18004e00d  mov     r8, r14
0x18004e010  lea     rdx, [rbp+var_28]
0x18004e014  mov     rcx, r12
0x18004e017  call    ??$_Try_emplace@AEBU_LUID@@$$V@?$map@U_LUID@@HU?$less@U_LUID@@@std@@V?$allocator@U?$pair@$$CBU_LUID@@H@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_LUID@@H@std@@PEAX@std@@_N@1@AEBU_LUID@@@Z; std::map<_LUID,int>::_Try_emplace<_LUID const &,>(_LUID const &)
0x18004e01c  mov     rcx, [rax]
0x18004e01f  inc     dword ptr [rcx+24h]
0x18004e022  mov     rax, [rdi]
0x18004e025  movzx   ecx, word ptr [rax+rbx*8+0Eh]
0x18004e02a  shl     rcx, 6
0x18004e02e  mov     rax, [rbp+var_18]
0x18004e032  cmp     dword ptr [rcx+rax+1Ch], 0
0x18004e037  jz      short loc_18004E07F
0x18004e039  inc     esi
0x18004e03b  mov     rcx, [rdi]
0x18004e03e  mov     rax, [rdi+8]
0x18004e042  sub     rax, rcx
0x18004e045  sar     rax, 3
0x18004e049  mov     rdx, 8E38E38E38E38E39h
0x18004e053  imul    rax, rdx
0x18004e057  cmp     esi, eax
0x18004e059  jb      short loc_18004E005
0x18004e05b  lea     rcx, [rbp+var_18]
0x18004e05f  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x18004e064  xor     eax, eax
0x18004e066  lea     r11, [rsp+60h+var_s0]
0x18004e06b  mov     rbx, [r11+30h]
0x18004e06f  mov     rsi, [r11+38h]
0x18004e073  mov     rsp, r11
0x18004e076  pop     r15
0x18004e078  pop     r14
0x18004e07a  pop     r12
0x18004e07c  pop     rdi
0x18004e07d  pop     rbp
0x18004e07e  retn
0x18004e07f  cmp     dword ptr [rcx+rax+20h], 0
0x18004e084  jnz     short loc_18004E039
0x18004e086  mov     eax, [r15+4]
0x18004e08a  or      eax, [r15]
0x18004e08d  jnz     short loc_18004E039
0x18004e08f  mov     rax, [r14]
0x18004e092  mov     [r15], rax
0x18004e095  jmp     short loc_18004E039
0x18004e097  movzx   esi, bx
0x18004e09a  mov     edi, 80070000h
0x18004e09f  test    ebx, ebx
0x18004e0a1  jg      short loc_18004E0E5
0x18004e0a3  mov     edx, ebx; unsigned int
0x18004e0a5  test    edx, edx
0x18004e0a7  jns     short loc_18004E0B5
0x18004e0a9  lea     r8, aGetdisplayconf_0; "GetDisplayConfigBufferSizes failed on W"...
0x18004e0b0  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18004e0b5  test    ebx, ebx
0x18004e0b7  jg      short loc_18004E0DF
0x18004e0b9  lea     rcx, [rbp+var_18]
0x18004e0bd  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x18004e0c2  mov     eax, ebx
0x18004e0c4  jmp     short loc_18004E066
0x18004e0c6  movzx   esi, bx
0x18004e0c9  mov     edi, 80070000h
0x18004e0ce  jg      short loc_18004E0EB
0x18004e0d0  mov     edx, ebx
0x18004e0d2  test    edx, edx
0x18004e0d4  jns     short loc_18004E0B5
0x18004e0d6  lea     r8, aQuerydisplayco_2; "QueryDisplayConfig failed on WNF_DX_DIS"...
0x18004e0dd  jmp     short loc_18004E0B0
0x18004e0df  mov     ebx, esi
0x18004e0e1  or      ebx, edi
0x18004e0e3  jmp     short loc_18004E0B9
0x18004e0e5  mov     edx, esi
0x18004e0e7  or      edx, edi
0x18004e0e9  jmp     short loc_18004E0A5
0x18004e0eb  mov     edx, esi
0x18004e0ed  or      edx, edi
0x18004e0ef  jmp     short loc_18004E0D2
0x18004e0f1  shl     rdx, 6
0x18004e0f5  add     rdx, r8
0x18004e0f8  mov     [rbp+var_18+8], rdx
0x18004e0fc  jmp     loc_18004DF3B
0x18004e101  shl     rdx, 6
0x18004e105  add     rdx, r8
0x18004e108  mov     [rbp+var_18+8], rdx
0x18004e10c  jmp     loc_18004DFED
0x18004e111  lea     rax, [rdx+rdx*8]
0x18004e115  lea     rcx, [r8+rax*8]
0x18004e119  mov     [rdi+8], rcx
0x18004e11d  jmp     loc_18004DF01
0x18004e122  lea     rax, [rdx+rdx*8]
0x18004e126  lea     rcx, [r8+rax*8]
0x18004e12a  mov     [rdi+8], rcx
0x18004e12e  jmp     loc_18004DFB3
0x18004e133  sub     rdx, rcx
0x18004e136  mov     rcx, [rdi+8]
0x18004e13a  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x18004e13f  mov     [rdi+8], rax
0x18004e143  jmp     loc_18004DF01
0x18004e148  sub     rdx, rcx
0x18004e14b  mov     rcx, [rbp+var_18+8]
0x18004e14f  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x18004e154  mov     [rbp+var_18+8], rax
0x18004e158  jmp     loc_18004DF3B
0x18004e15d  sub     rdx, rcx
0x18004e160  mov     rcx, [rdi+8]
0x18004e164  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x18004e169  mov     [rdi+8], rax
0x18004e16d  jmp     loc_18004DFB3
0x18004e172  sub     rdx, rcx
0x18004e175  mov     rcx, [rbp+var_18+8]
0x18004e179  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x18004e17e  mov     [rbp+var_18+8], rax
0x18004e182  jmp     loc_18004DFED
```
