# DevicePostureHelpers::IsValidTabletDisplayConfig(void)

- ea: `0x180146110`
- end: `0x180146311`
- name: `?IsValidTabletDisplayConfig@DevicePostureHelpers@@YA_NXZ`
- size: `513`
- prototype: `bool __fastcall(DevicePostureHelpers *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180145b18`

## callees

- `0x18008a058`
- `0x18008a910`
- `0x18008aa38`
- `0x1801457d0`
- `0x180145820`
- `0x180145870`
- `0x180145974`
- `0x180145c50`
- `0x1801460a4`
- `0x180146110`
- `0x180146474`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18014614a`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18014614a`
- `api-ms-win-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x1801461b5`
- `api-ms-win-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x1801461b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall DevicePostureHelpers::IsValidTabletDisplayConfig(DevicePostureHelpers *this)
{
  bool IsIgnoringDisplayConfig; // r14
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rcx
  bool v5; // si
  bool v6; // di
  DISPLAYCONFIG_PATH_INFO *v7; // rdx
  char v8; // bl
  DISPLAYCONFIG_PATH_INFO *pathArray[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v10; // [rsp+40h] [rbp-20h]
  DISPLAYCONFIG_MODE_INFO *modeInfoArray[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v12; // [rsp+58h] [rbp-8h]
  UINT32 numPathArrayElements; // [rsp+80h] [rbp+20h] BYREF
  UINT32 numModeInfoArrayElements; // [rsp+88h] [rbp+28h] BYREF

  IsIgnoringDisplayConfig = DevicePostureHelpers::IsIgnoringDisplayConfig(this);
  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  if ( GetDisplayConfigBufferSizes(0x12u, &numPathArrayElements, &numModeInfoArrayElements) )
    return 0;
  *(_OWORD *)pathArray = 0;
  v10 = 0;
  std::vector<DISPLAYCONFIG_PATH_INFO>::_Construct_n<>(pathArray, numPathArrayElements);
  *(_OWORD *)modeInfoArray = 0;
  v12 = 0;
  std::vector<DISPLAYCONFIG_MODE_INFO>::_Construct_n<>(modeInfoArray, numModeInfoArrayElements);
  if ( QueryDisplayConfig(0x12u, &numPathArrayElements, pathArray[0], &numModeInfoArrayElements, modeInfoArray[0], 0) )
    goto LABEL_28;
  v3 = 0x8E38E38E38E38E39uLL * (((char *)pathArray[1] - (char *)pathArray[0]) >> 3);
  if ( numPathArrayElements >= v3 )
  {
    if ( numPathArrayElements > v3 )
    {
      if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL * ((signed __int64)(v10 - (unsigned __int64)pathArray[0]) >> 3) )
        pathArray[1] = (DISPLAYCONFIG_PATH_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                                                    pathArray[1],
                                                    numPathArrayElements - v3);
      else
        std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(pathArray);
    }
  }
  else
  {
    pathArray[1] = &pathArray[0][numPathArrayElements];
  }
  v4 = modeInfoArray[1] - modeInfoArray[0];
  if ( numModeInfoArrayElements >= v4 )
  {
    if ( numModeInfoArrayElements > v4 )
    {
      if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v12 - (unsigned __int64)modeInfoArray[0]) >> 6) )
        modeInfoArray[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                        modeInfoArray[1],
                                                        numModeInfoArrayElements - v4);
      else
        std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(modeInfoArray);
    }
  }
  else
  {
    modeInfoArray[1] = &modeInfoArray[0][(unsigned __int64)numModeInfoArrayElements];
  }
  v5 = 0;
  v6 = 0;
  v7 = pathArray[0];
  v8 = 1;
  while ( v7 != pathArray[1] )
  {
    if ( v7->targetInfo.outputTechnology == 0x80000000
      || v7->targetInfo.outputTechnology == DISPLAYCONFIG_OUTPUT_TECHNOLOGY_DISPLAYPORT_EMBEDDED
      || v7->targetInfo.outputTechnology == DISPLAYCONFIG_OUTPUT_TECHNOLOGY_UDI_EMBEDDED )
    {
      v5 = 1;
    }
    if ( *(_QWORD *)&modeInfoArray[0][(unsigned __int64)*((unsigned __int16 *)&v7->sourceInfo.1 + 1)].desktopImageInfo.DesktopImageRegion.top )
    {
      v6 = 1;
      break;
    }
    ++v7;
  }
  if ( (InputTraceLogging::Postures::EvaluateDisplayConfig(IsIgnoringDisplayConfig, v6, v5), !v5)
    && !IsIgnoringDisplayConfig
    || v6 )
  {
LABEL_28:
    v8 = 0;
  }
  std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(modeInfoArray);
  std::vector<HidChannelValueInfo>::~vector<HidChannelValueInfo>(pathArray);
  return v8;
}

```

## disassembly

```asm
0x180146110  mov     [rsp-18h+arg_10], rbx
0x180146115  mov     [rsp-18h+arg_18], rsi
0x18014611a  push    rbp
0x18014611b  push    rdi
0x18014611c  push    r14
0x18014611e  mov     rbp, rsp
0x180146121  sub     rsp, 60h
0x180146125  call    ?IsIgnoringDisplayConfig@DevicePostureHelpers@@YA_NXZ; DevicePostureHelpers::IsIgnoringDisplayConfig(void)
0x18014612a  mov     r14b, al
0x18014612d  mov     [rbp+numPathArrayElements], 0
0x180146134  mov     [rbp+numModeInfoArrayElements], 0
0x18014613b  lea     r8, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x18014613f  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x180146143  mov     ebx, 12h
0x180146148  mov     ecx, ebx; flags
0x18014614a  call    cs:__imp_GetDisplayConfigBufferSizes
0x180146150  test    eax, eax
0x180146152  jz      short loc_18014615B
0x180146154  xor     al, al
0x180146156  jmp     loc_1801462FC
0x18014615b  xorps   xmm0, xmm0
0x18014615e  movdqu  xmmword ptr [rbp+pathArray], xmm0
0x180146163  mov     [rbp+var_20], 0
0x18014616b  mov     edx, [rbp+numPathArrayElements]
0x18014616e  lea     rcx, [rbp+pathArray]
0x180146172  call    ??$_Construct_n@$$V@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_K@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Construct_n<>(unsigned __int64)
0x180146177  nop
0x180146178  xorps   xmm0, xmm0
0x18014617b  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180146180  mov     [rbp+var_8], 0
0x180146188  mov     edx, [rbp+numModeInfoArrayElements]
0x18014618b  lea     rcx, [rbp+var_18]
0x18014618f  call    ??$_Construct_n@$$V@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_K@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Construct_n<>(unsigned __int64)
0x180146194  nop
0x180146195  mov     rax, [rbp+var_18]
0x180146199  mov     [rsp+60h+currentTopologyId], 0; currentTopologyId
0x1801461a2  mov     [rsp+60h+modeInfoArray], rax; modeInfoArray
0x1801461a7  lea     r9, [rbp+numModeInfoArrayElements]; numModeInfoArrayElements
0x1801461ab  mov     r8, [rbp+pathArray]; pathArray
0x1801461af  lea     rdx, [rbp+numPathArrayElements]; numPathArrayElements
0x1801461b3  mov     ecx, ebx; flags
0x1801461b5  call    cs:__imp_QueryDisplayConfig
0x1801461bb  test    eax, eax
0x1801461bd  jnz     loc_1801462E5
0x1801461c3  mov     edx, [rbp+numPathArrayElements]
0x1801461c6  mov     r8, [rbp+pathArray]
0x1801461ca  mov     rcx, [rbp+pathArray+8]
0x1801461ce  sub     rcx, r8
0x1801461d1  sar     rcx, 3
0x1801461d5  mov     r9, 8E38E38E38E38E39h
0x1801461df  imul    rcx, r9
0x1801461e3  cmp     rdx, rcx
0x1801461e6  jnb     short loc_1801461F6
0x1801461e8  lea     rax, [rdx+rdx*8]
0x1801461ec  lea     rcx, [r8+rax*8]
0x1801461f0  mov     [rbp+pathArray+8], rcx
0x1801461f4  jmp     short loc_180146227
0x1801461f6  jbe     short loc_180146227
0x1801461f8  mov     rax, [rbp+var_20]
0x1801461fc  sub     rax, r8
0x1801461ff  sar     rax, 3
0x180146203  imul    rax, r9
0x180146207  cmp     rdx, rax
0x18014620a  jbe     short loc_180146217
0x18014620c  lea     rcx, [rbp+pathArray]
0x180146210  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180146215  jmp     short loc_180146227
0x180146217  sub     rdx, rcx
0x18014621a  mov     rcx, [rbp+pathArray+8]
0x18014621e  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(DISPLAYCONFIG_PATH_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_PATH_INFO> &)
0x180146223  mov     [rbp+pathArray+8], rax
0x180146227  mov     edx, [rbp+numModeInfoArrayElements]
0x18014622a  mov     r8, [rbp+var_18]
0x18014622e  mov     rcx, [rbp+var_18+8]
0x180146232  sub     rcx, r8
0x180146235  sar     rcx, 6
0x180146239  cmp     rdx, rcx
0x18014623c  jnb     short loc_18014624B
0x18014623e  shl     rdx, 6
0x180146242  add     rdx, r8
0x180146245  mov     [rbp+var_18+8], rdx
0x180146249  jmp     short loc_180146278
0x18014624b  jbe     short loc_180146278
0x18014624d  mov     rax, [rbp+var_8]
0x180146251  sub     rax, r8
0x180146254  sar     rax, 6
0x180146258  cmp     rdx, rax
0x18014625b  jbe     short loc_180146268
0x18014625d  lea     rcx, [rbp+var_18]
0x180146261  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180146266  jmp     short loc_180146278
0x180146268  sub     rdx, rcx
0x18014626b  mov     rcx, [rbp+var_18+8]
0x18014626f  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@PEAU1@_KAEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(DISPLAYCONFIG_MODE_INFO *,unsigned __int64,std::allocator<DISPLAYCONFIG_MODE_INFO> &)
0x180146274  mov     [rbp+var_18+8], rax
0x180146278  xor     sil, sil
0x18014627b  xor     dil, dil
0x18014627e  mov     rdx, [rbp+pathArray]
0x180146282  mov     bl, 1
0x180146284  cmp     rdx, [rbp+pathArray+8]
0x180146288  jz      short loc_1801462C8
0x18014628a  cmp     dword ptr [rdx+24h], 80000000h
0x180146291  jz      short loc_18014629F
0x180146293  cmp     dword ptr [rdx+24h], 0Bh
0x180146297  jz      short loc_18014629F
0x180146299  cmp     dword ptr [rdx+24h], 0Dh
0x18014629d  jnz     short loc_1801462A2
0x18014629f  mov     sil, bl
0x1801462a2  movzx   ecx, word ptr [rdx+0Eh]
0x1801462a6  shl     rcx, 6
0x1801462aa  mov     rax, [rbp+var_18]
0x1801462ae  mov     rax, [rcx+rax+1Ch]
0x1801462b3  test    eax, eax
0x1801462b5  jnz     short loc_1801462C5
0x1801462b7  shr     rax, 20h
0x1801462bb  test    eax, eax
0x1801462bd  jnz     short loc_1801462C5
0x1801462bf  add     rdx, 48h ; 'H'
0x1801462c3  jmp     short loc_180146284
0x1801462c5  mov     dil, bl
0x1801462c8  mov     r8b, sil; bool
0x1801462cb  mov     dl, dil; bool
0x1801462ce  mov     cl, r14b; bool
0x1801462d1  call    ?EvaluateDisplayConfig@Postures@InputTraceLogging@@SAX_N00@Z; InputTraceLogging::Postures::EvaluateDisplayConfig(bool,bool,bool)
0x1801462d6  test    sil, sil
0x1801462d9  jnz     short loc_1801462E0
0x1801462db  test    r14b, r14b
0x1801462de  jz      short loc_1801462E5
0x1801462e0  test    dil, dil
0x1801462e3  jz      short loc_1801462E7
0x1801462e5  xor     bl, bl
0x1801462e7  lea     rcx, [rbp+var_18]
0x1801462eb  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x1801462f0  nop
0x1801462f1  lea     rcx, [rbp+pathArray]
0x1801462f5  call    ??1?$vector@VHidChannelValueInfo@@V?$allocator@VHidChannelValueInfo@@@std@@@std@@QEAA@XZ; std::vector<HidChannelValueInfo>::~vector<HidChannelValueInfo>(void)
0x1801462fa  mov     al, bl
0x1801462fc  lea     r11, [rsp+60h+var_s0]
0x180146301  mov     rbx, [r11+30h]
0x180146305  mov     rsi, [r11+38h]
0x180146309  mov     rsp, r11
0x18014630c  pop     r14
0x18014630e  pop     rdi
0x18014630f  pop     rbp
0x180146310  retn
```
