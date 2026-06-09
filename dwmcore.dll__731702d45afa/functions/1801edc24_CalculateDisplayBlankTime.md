# CalculateDisplayBlankTime

- ea: `0x1801edc24`
- end: `0x1801edee5`
- name: `CalculateDisplayBlankTime`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1802545d4`

## callees

- `0x1800d32c0`
- `0x1801edc24`
- `0x180213cb8`
- `0x180226cdc`
- `0x180226de0`
- `0x180253fc4`
- `0x180254100`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x1801edd5f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x1801edd5f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x1801edc83`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x1801edc83`

## pseudocode

```c
__int64 __fastcall CalculateDisplayBlankTime(__int64 a1, int a2, double *a3)
{
  unsigned int DisplayConfigBufferSizes; // eax
  unsigned int v7; // r8d
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  DISPLAYCONFIG_MODE_INFO *v11; // r8
  UINT32 i; // r9d
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  double v15; // xmm0_8
  UINT64 v16; // rax
  unsigned int v18; // ebx
  unsigned int modeInfoArray; // [rsp+20h] [rbp-50h]
  UINT32 numPathArrayElements; // [rsp+30h] [rbp-40h] BYREF
  DISPLAYCONFIG_MODE_INFO *v21[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v22; // [rsp+48h] [rbp-28h]
  DISPLAYCONFIG_PATH_INFO *pathArray[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v24; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  UINT32 numModeInfoArrayElements; // [rsp+A8h] [rbp+38h] BYREF

  v24 = 0;
  *(_OWORD *)pathArray = 0;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  do
  {
    DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(0x42u, &numPathArrayElements, &numModeInfoArrayElements);
    if ( DisplayConfigBufferSizes )
    {
      v10 = 37;
      goto LABEL_35;
    }
    v8 = 0x8E38E38E38E38E39uLL * (((char *)pathArray[1] - (char *)pathArray[0]) >> 3);
    if ( numPathArrayElements >= v8 )
    {
      if ( numPathArrayElements > v8 )
      {
        if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL
                                   * ((signed __int64)(v24 - (unsigned __int64)pathArray[0]) >> 3) )
          pathArray[1] = (DISPLAYCONFIG_PATH_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                                                      pathArray[1],
                                                      numPathArrayElements - v8);
        else
          std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(pathArray);
      }
    }
    else
    {
      pathArray[1] = &pathArray[0][numPathArrayElements];
    }
    v9 = v21[1] - v21[0];
    if ( numModeInfoArrayElements >= v9 )
    {
      if ( numModeInfoArrayElements > v9 )
      {
        if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v22 - (unsigned __int64)v21[0]) >> 6) )
          v21[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                v21[1],
                                                numModeInfoArrayElements - v9);
        else
          std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(v21);
      }
    }
    else
    {
      v21[1] = &v21[0][(unsigned __int64)numModeInfoArrayElements];
    }
    DisplayConfigBufferSizes = QueryDisplayConfig(
                                 0x42u,
                                 &numPathArrayElements,
                                 pathArray[0],
                                 &numModeInfoArrayElements,
                                 v21[0],
                                 0);
  }
  while ( DisplayConfigBufferSizes == 122 );
  if ( DisplayConfigBufferSizes )
  {
    v10 = 50;
LABEL_35:
    v18 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v10,
            v7,
            (const char *)DisplayConfigBufferSizes,
            modeInfoArray);
    if ( v21[0] )
    {
      std::_Deallocate<16>(v21[0], (v22 - (unsigned __int64)v21[0]) & 0xFFFFFFFFFFFFFFC0uLL);
      v22 = 0;
      *(_OWORD *)v21 = 0;
    }
    if ( pathArray[0] )
      std::_Deallocate<16>(pathArray[0], 8 * ((signed __int64)(v24 - (unsigned __int64)pathArray[0]) >> 3));
    return v18;
  }
  v11 = v21[0];
  for ( i = 0; ; ++i )
  {
    if ( i >= numModeInfoArrayElements )
    {
      *a3 = 0.001000000047497451;
      goto LABEL_29;
    }
    v13 = (unsigned __int64)i << 6;
    if ( *(DISPLAYCONFIG_MODE_INFO_TYPE *)((char *)&v21[0]->infoType + v13) == DISPLAYCONFIG_MODE_INFO_TYPE_TARGET
      && (*(unsigned int *)((char *)&v21[0]->adapterId.LowPart + v13)
        | (unsigned __int64)((__int64)(int)HIDWORD(*(unsigned __int64 *)((char *)&v21[0]->adapterId + v13)) << 32)) == a1
      && *(UINT32 *)((char *)&v21[0]->id + v13) == a2 )
    {
      break;
    }
  }
  v14 = *(UINT64 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.pixelRate + v13);
  if ( v14 < 0 )
  {
    v16 = *(UINT64 *)((_BYTE *)&v21[0]->targetMode.targetVideoSignalInfo.pixelRate + v13) & 1
        | (*(UINT64 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.pixelRate + v13) >> 1);
    v15 = (double)(int)v16 + (double)(int)v16;
  }
  else
  {
    v15 = (double)(int)v14;
  }
  *a3 = (double)(*(UINT32 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.totalSize.cx + v13)
               * (*(UINT32 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.totalSize.cy + v13)
                - *(UINT32 *)((char *)&v21[0]->targetMode.targetVideoSignalInfo.activeSize.cy + v13)))
      / v15;
LABEL_29:
  if ( v11 )
  {
    std::_Deallocate<16>(v11, (v22 - (_QWORD)v11) & 0xFFFFFFFFFFFFFFC0uLL);
    v22 = 0;
    *(_OWORD *)v21 = 0;
  }
  if ( pathArray[0] )
    std::_Deallocate<16>(pathArray[0], 8 * ((signed __int64)(v24 - (unsigned __int64)pathArray[0]) >> 3));
  return 0;
}

```

## disassembly

```asm
0x1801edc24  mov     [rsp-18h+arg_0], rbx
0x1801edc29  mov     [rsp-18h+arg_8], rsi
0x1801edc2e  push    rbp
0x1801edc2f  push    rdi
0x1801edc30  push    r15
0x1801edc32  mov     rbp, rsp
0x1801edc35  sub     rsp, 70h
0x1801edc39  xorps   xmm0, xmm0
0x1801edc3c  mov     [rbp+var_10], 0
0x1801edc44  movdqu  xmmword ptr [rbp+pathArray], xmm0
0x1801edc49  mov     rbx, r8
0x1801edc4c  mov     edi, edx
0x1801edc4e  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1801edc53  mov     rsi, rcx
0x1801edc56  mov     [rbp+var_28], 0
0x1801edc5e  mov     [rbp+numPathArrayElements], 0
0x1801edc65  mov     r15, 8E38E38E38E38E39h
0x1801edc6f  mov     [rbp+numModeInfoArrayElements], 0
0x1801edc76  lea     r8, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x1801edc7a  mov     ecx, 42h ; 'B'; flags
0x1801edc7f  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x1801edc83  call    cs:__imp_GetDisplayConfigBufferSizes
0x1801edc89  test    eax, eax
0x1801edc8b  jnz     loc_1801EDE6D
0x1801edc91  mov     r8, [rbp+pathArray]
0x1801edc95  mov     rcx, [rbp+pathArray+8]
0x1801edc99  mov     edx, [rbp+numPathArrayElements]
0x1801edc9c  sub     rcx, r8
0x1801edc9f  sar     rcx, 3
0x1801edca3  imul    rcx, r15
0x1801edca7  cmp     rdx, rcx
0x1801edcaa  jnb     short loc_1801EDCBA
0x1801edcac  lea     rax, [rdx+rdx*8]
0x1801edcb0  lea     rcx, [r8+rax*8]
0x1801edcb4  mov     [rbp+pathArray+8], rcx
0x1801edcb8  jmp     short loc_1801EDCEB
0x1801edcba  jbe     short loc_1801EDCEB
0x1801edcbc  mov     rax, [rbp+var_10]
0x1801edcc0  sub     rax, r8
0x1801edcc3  sar     rax, 3
0x1801edcc7  imul    rax, r15
0x1801edccb  cmp     rdx, rax
0x1801edcce  jbe     short loc_1801EDCDB
0x1801edcd0  lea     rcx, [rbp+pathArray]
0x1801edcd4  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1801edcd9  jmp     short loc_1801EDCEB
0x1801edcdb  sub     rdx, rcx
0x1801edcde  mov     rcx, [rbp+pathArray+8]
0x1801edce2  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x1801edce7  mov     [rbp+pathArray+8], rax
0x1801edceb  mov     r8, [rbp+var_38]
0x1801edcef  mov     rcx, [rbp+var_38+8]
0x1801edcf3  mov     edx, [rbp+numModeInfoArrayElements]
0x1801edcf6  sub     rcx, r8
0x1801edcf9  sar     rcx, 6
0x1801edcfd  cmp     rdx, rcx
0x1801edd00  jnb     short loc_1801EDD0F
0x1801edd02  shl     rdx, 6
0x1801edd06  add     rdx, r8
0x1801edd09  mov     [rbp+var_38+8], rdx
0x1801edd0d  jmp     short loc_1801EDD3C
0x1801edd0f  jbe     short loc_1801EDD3C
0x1801edd11  mov     rax, [rbp+var_28]
0x1801edd15  sub     rax, r8
0x1801edd18  sar     rax, 6
0x1801edd1c  cmp     rdx, rax
0x1801edd1f  jbe     short loc_1801EDD2C
0x1801edd21  lea     rcx, [rbp+var_38]
0x1801edd25  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1801edd2a  jmp     short loc_1801EDD3C
0x1801edd2c  sub     rdx, rcx
0x1801edd2f  mov     rcx, [rbp+var_38+8]
0x1801edd33  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x1801edd38  mov     [rbp+var_38+8], rax
0x1801edd3c  mov     rax, [rbp+var_38]
0x1801edd40  lea     r9, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x1801edd44  mov     r8, [rbp+pathArray]; pathArray
0x1801edd48  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x1801edd4c  mov     [rsp+70h+currentTopologyId], 0; currentTopologyId
0x1801edd55  mov     ecx, 42h ; 'B'; flags
0x1801edd5a  mov     [rsp+70h+modeInfoArray], rax; modeInfoArray
0x1801edd5f  call    cs:__imp_QueryDisplayConfig
0x1801edd65  cmp     eax, 7Ah ; 'z'
0x1801edd68  jz      loc_1801EDC76
0x1801edd6e  test    eax, eax
0x1801edd70  jz      short loc_1801EDD7C
0x1801edd72  mov     edx, 32h ; '2'
0x1801edd77  jmp     loc_1801EDE72
0x1801edd7c  mov     r8, [rbp+var_38]
0x1801edd80  xor     r9d, r9d
0x1801edd83  cmp     r9d, [rbp+numModeInfoArrayElements]
0x1801edd87  jnb     loc_1801EDE0F
0x1801edd8d  mov     edx, r9d
0x1801edd90  shl     rdx, 6
0x1801edd94  cmp     dword ptr [rdx+r8], 2
0x1801edd99  jnz     short loc_1801EDDBF
0x1801edd9b  mov     rax, [rdx+r8+8]
0x1801edda0  shr     rax, 20h
0x1801edda4  movsxd  rcx, eax
0x1801edda7  mov     eax, [rdx+r8+8]
0x1801eddac  shl     rcx, 20h
0x1801eddb0  or      rcx, rax
0x1801eddb3  cmp     rcx, rsi
0x1801eddb6  jnz     short loc_1801EDDBF
0x1801eddb8  cmp     [rdx+r8+4], edi
0x1801eddbd  jz      short loc_1801EDDC4
0x1801eddbf  inc     r9d
0x1801eddc2  jmp     short loc_1801EDD83
0x1801eddc4  mov     eax, [rdx+r8+34h]
0x1801eddc9  xorps   xmm1, xmm1
0x1801eddcc  sub     eax, [rdx+r8+2Ch]
0x1801eddd1  xorps   xmm0, xmm0
0x1801eddd4  imul    eax, [rdx+r8+30h]
0x1801eddda  mov     rcx, [rdx+r8+10h]
0x1801edddf  cvtsi2sd xmm1, rax
0x1801edde4  test    rcx, rcx
0x1801edde7  js      short loc_1801EDDF0
0x1801edde9  cvtsi2sd xmm0, rcx
0x1801eddee  jmp     short loc_1801EDE05
0x1801eddf0  mov     rax, rcx
0x1801eddf3  and     ecx, 1
0x1801eddf6  shr     rax, 1
0x1801eddf9  or      rax, rcx
0x1801eddfc  cvtsi2sd xmm0, rax
0x1801ede01  addsd   xmm0, xmm0
0x1801ede05  divsd   xmm1, xmm0
0x1801ede09  movsd   qword ptr [rbx], xmm1
0x1801ede0d  jmp     short loc_1801EDE1C
0x1801ede0f  mov     rax, 3F50624DE0000000h
0x1801ede19  mov     [rbx], rax
0x1801ede1c  test    r8, r8
0x1801ede1f  jz      short loc_1801EDE44
0x1801ede21  mov     rdx, [rbp+var_28]
0x1801ede25  mov     rcx, r8
0x1801ede28  sub     rdx, r8
0x1801ede2b  and     rdx, 0FFFFFFFFFFFFFFC0h
0x1801ede2f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801ede34  xorps   xmm0, xmm0
0x1801ede37  mov     [rbp+var_28], 0
0x1801ede3f  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1801ede44  mov     rcx, [rbp+pathArray]
0x1801ede48  test    rcx, rcx
0x1801ede4b  jz      short loc_1801EDE69
0x1801ede4d  mov     rax, [rbp+var_10]
0x1801ede51  sub     rax, rcx
0x1801ede54  sar     rax, 3
0x1801ede58  imul    rax, r15
0x1801ede5c  lea     rdx, [rax+rax*8]
0x1801ede60  shl     rdx, 3
0x1801ede64  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801ede69  xor     eax, eax
0x1801ede6b  jmp     short loc_1801EDED0
0x1801ede6d  mov     edx, 25h ; '%'; void *
0x1801ede72  mov     rcx, [rbp+18h]; this
0x1801ede76  mov     r9d, eax; char *
0x1801ede79  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801ede7e  mov     rcx, [rbp+var_38]
0x1801ede82  mov     ebx, eax
0x1801ede84  test    rcx, rcx
0x1801ede87  jz      short loc_1801EDEA9
0x1801ede89  mov     rdx, [rbp+var_28]
0x1801ede8d  sub     rdx, rcx
0x1801ede90  and     rdx, 0FFFFFFFFFFFFFFC0h
0x1801ede94  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801ede99  xorps   xmm0, xmm0
0x1801ede9c  mov     [rbp+var_28], 0
0x1801edea4  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1801edea9  mov     rcx, [rbp+pathArray]
0x1801edead  test    rcx, rcx
0x1801edeb0  jz      short loc_1801EDECE
0x1801edeb2  mov     rax, [rbp+var_10]
0x1801edeb6  sub     rax, rcx
0x1801edeb9  sar     rax, 3
0x1801edebd  imul    rax, r15
0x1801edec1  lea     rdx, [rax+rax*8]
0x1801edec5  shl     rdx, 3
0x1801edec9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801edece  mov     eax, ebx
0x1801eded0  lea     r11, [rsp+70h+var_s0]
0x1801eded5  mov     rbx, [r11+20h]
0x1801eded9  mov     rsi, [r11+28h]
0x1801ededd  mov     rsp, r11
0x1801edee0  pop     r15
0x1801edee2  pop     rdi
0x1801edee3  pop     rbp
0x1801edee4  retn
```
