# DWriteRenderingParams::GetMonitorInvertedFromDeviceName(wchar_t const *,bool *)

- ea: `0x180130ad0`
- end: `0x180131110`
- name: `?GetMonitorInvertedFromDeviceName@DWriteRenderingParams@@CAJPEB_WPEA_N@Z`
- size: `1600`
- prototype: `__int64 __fastcall(const wchar_t *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1801300e4`

## callees

- `0x18011ef30`
- `0x180130ad0`
- `0x180131118`
- `0x1801efaac`
- `0x180206e04`
- `0x1802073d0`
- `0x180207614`
- `0x180207708`
- `0x1802077f0`
- `0x180212490`
- `0x180212f4c`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180130c66`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180130df4`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180130f84`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180130c66`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180130df4`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180130f84`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180130bf1`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x180130bf1`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180130b3e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x180130b3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DWriteRenderingParams::GetMonitorInvertedFromDeviceName(const wchar_t *a1, bool *a2)
{
  _BYTE *v4; // rdx
  unsigned int DisplayConfigBufferSizes; // ebx
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rcx
  LONG v8; // eax
  UINT32 v9; // r8d
  DISPLAYCONFIG_PATH_INFO *v10; // rcx
  UINT32 i; // edi
  __int64 v12; // rsi
  LONG DeviceInfo; // eax
  char v14; // r14
  __int64 k; // rdi
  UINT32 v17; // edx
  const wchar_t *v18; // rbx
  LONG v19; // eax
  char v20; // al
  unsigned __int64 v21; // rax
  DISPLAYCONFIG_PATH_INFO *v22; // rcx
  __int64 v23; // rdx
  char *j; // rax
  const wchar_t *v25; // rcx
  signed __int64 v26; // rax
  int v27; // r8d
  int v28; // edx
  __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  DISPLAYCONFIG_MODE_INFO *modeInfoArray[2]; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v32; // [rsp+40h] [rbp-99h]
  UINT32 numPathArrayElements; // [rsp+48h] [rbp-91h] BYREF
  DISPLAYCONFIG_PATH_INFO *pathArray; // [rsp+50h] [rbp-89h] BYREF
  DISPLAYCONFIG_PATH_INFO *v35; // [rsp+58h] [rbp-81h]
  __int64 v36; // [rsp+60h] [rbp-79h]
  UINT32 numModeInfoArrayElements; // [rsp+68h] [rbp-71h] BYREF
  _BYTE requestPacket[24]; // [rsp+70h] [rbp-69h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER v39; // [rsp+90h] [rbp-49h] BYREF
  char v40; // [rsp+A4h] [rbp-35h] BYREF

  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&pathArray);
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(modeInfoArray);
  *v4 = 0;
  do
  {
    DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, &numModeInfoArrayElements);
    if ( (DisplayConfigBufferSizes & 0x80000000) != 0 )
    {
      if ( modeInfoArray[0] )
      {
        std::_Deallocate<16>(modeInfoArray[0], (v32 - (unsigned __int64)modeInfoArray[0]) & 0xFFFFFFFFFFFFFFC0uLL);
        *(_OWORD *)modeInfoArray = 0;
        v32 = 0;
      }
      std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(&pathArray);
      return DisplayConfigBufferSizes;
    }
    v6 = 0x8E38E38E38E38E39uLL * (((char *)v35 - (char *)pathArray) >> 3);
    if ( numPathArrayElements < v6 )
    {
      v35 = &pathArray[numPathArrayElements];
    }
    else if ( numPathArrayElements > v6 )
    {
      if ( numPathArrayElements <= 0x8E38E38E38E38E39uLL * ((v36 - (__int64)pathArray) >> 3) )
        v35 = (DISPLAYCONFIG_PATH_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_PATH_INFO>>(
                                           v35,
                                           numPathArrayElements - v6);
      else
        std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(&pathArray);
    }
    v7 = modeInfoArray[1] - modeInfoArray[0];
    if ( numModeInfoArrayElements < v7 )
    {
      modeInfoArray[1] = &modeInfoArray[0][(unsigned __int64)numModeInfoArrayElements];
    }
    else if ( numModeInfoArrayElements > v7 )
    {
      if ( numModeInfoArrayElements <= (unsigned __int64)((signed __int64)(v32 - (unsigned __int64)modeInfoArray[0]) >> 6) )
        modeInfoArray[1] = (DISPLAYCONFIG_MODE_INFO *)std::_Uninitialized_value_construct_n<std::allocator<DISPLAYCONFIG_MODE_INFO>>(
                                                        modeInfoArray[1],
                                                        numModeInfoArrayElements - v7);
      else
        std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(modeInfoArray);
    }
    v8 = QueryDisplayConfig(2u, &numPathArrayElements, pathArray, &numModeInfoArrayElements, modeInfoArray[0], 0);
    DisplayConfigBufferSizes = v8;
  }
  while ( v8 == -2147024774 );
  if ( v8 < 0 )
  {
    if ( modeInfoArray[0] )
    {
      std::_Deallocate<16>(modeInfoArray[0], (v32 - (unsigned __int64)modeInfoArray[0]) & 0xFFFFFFFFFFFFFFC0uLL);
      *(_OWORD *)modeInfoArray = 0;
      v32 = 0;
    }
    v22 = pathArray;
    if ( !pathArray )
      return DisplayConfigBufferSizes;
    v23 = (v36 - (__int64)pathArray) >> 3;
LABEL_56:
    std::_Deallocate<16>(v22, 8 * v23);
    return DisplayConfigBufferSizes;
  }
  if ( !numPathArrayElements )
  {
LABEL_36:
    if ( modeInfoArray[0] )
    {
      std::_Deallocate<16>(modeInfoArray[0], (v32 - (unsigned __int64)modeInfoArray[0]) & 0xFFFFFFFFFFFFFFC0uLL);
      *(_OWORD *)modeInfoArray = 0;
      v32 = 0;
    }
    v10 = pathArray;
    goto LABEL_59;
  }
  if ( a1 )
  {
    v18 = SkipDeviceNamePrefix(a1);
    for ( i = 0; ; ++i )
    {
      if ( i >= v17 )
        goto LABEL_36;
      memset_0(&v39.size, 0, 0x50u);
      v39.type = DISPLAYCONFIG_DEVICE_INFO_GET_SOURCE_NAME;
      v39.adapterId = pathArray[i].sourceInfo.adapterId;
      v39.id = pathArray[i].sourceInfo.id;
      v39.size = 84;
      if ( DisplayConfigGetDeviceInfo(&v39) )
        goto LABEL_92;
      for ( j = &v40; ; j += v29 )
      {
        if ( *(_WORD *)j == 92 )
        {
          v29 = 2;
          continue;
        }
        if ( *(_WORD *)j != 46 || *((_WORD *)j + 1) != 92 )
          break;
        v29 = 4;
      }
      v25 = v18;
      v26 = j - (char *)v18;
      do
      {
        v27 = *(const wchar_t *)((char *)v25 + v26);
        v28 = *v25 - v27;
        if ( v28 )
          break;
        ++v25;
      }
      while ( v27 );
      if ( !v28 )
      {
        v10 = pathArray;
        goto LABEL_18;
      }
LABEL_92:
      v17 = numPathArrayElements;
    }
  }
  v9 = 1;
  v10 = pathArray;
  while ( v9 < numPathArrayElements )
  {
    if ( pathArray[v9].sourceInfo.adapterId.HighPart != pathArray->sourceInfo.adapterId.HighPart
      || pathArray[v9].sourceInfo.adapterId.LowPart != pathArray->sourceInfo.adapterId.LowPart
      || pathArray[v9].sourceInfo.id != pathArray->sourceInfo.id )
    {
      if ( modeInfoArray[0] )
      {
        std::_Deallocate<16>(modeInfoArray[0], (v32 - (unsigned __int64)modeInfoArray[0]) & 0xFFFFFFFFFFFFFFC0uLL);
        *(_OWORD *)modeInfoArray = 0;
        v32 = 0;
        v10 = pathArray;
      }
LABEL_59:
      if ( v10 )
      {
        v21 = 0x8E38E38E38E38E39uLL * ((v36 - (__int64)v10) >> 3);
LABEL_50:
        std::_Deallocate<16>(v10, 72 * v21);
      }
      return 2147500037LL;
    }
    ++v9;
  }
  i = 0;
LABEL_18:
  *(_QWORD *)&requestPacket[8] = 0;
  *(_QWORD *)&requestPacket[16] = 0;
  *(_DWORD *)requestPacket = -9;
  *(_DWORD *)&requestPacket[4] = 24;
  v12 = i;
  *(LUID *)&requestPacket[8] = v10[i].targetInfo.adapterId;
  *(_DWORD *)&requestPacket[16] = v10[i].targetInfo.id;
  DeviceInfo = DisplayConfigGetDeviceInfo((DISPLAYCONFIG_DEVICE_INFO_HEADER *)requestPacket);
  DisplayConfigBufferSizes = DeviceInfo;
  if ( DeviceInfo )
  {
    if ( DeviceInfo > 0 )
      DisplayConfigBufferSizes = (unsigned __int16)DeviceInfo | 0x80070000;
    if ( modeInfoArray[0] )
    {
      std::_Deallocate<16>(modeInfoArray[0], (v32 - (unsigned __int64)modeInfoArray[0]) & 0xFFFFFFFFFFFFFFC0uLL);
      *(_OWORD *)modeInfoArray = 0;
      v32 = 0;
    }
    v22 = pathArray;
    if ( !pathArray )
      return DisplayConfigBufferSizes;
    v30 = 0x8E38E38E38E38E39uLL * ((v36 - (__int64)pathArray) >> 3);
LABEL_82:
    v23 = 9 * v30;
    goto LABEL_56;
  }
  v14 = *(_DWORD *)&requestPacket[20] != 0;
  v10 = pathArray;
  if ( pathArray[i].targetInfo.rotation == DISPLAYCONFIG_ROTATION_ROTATE180 )
    v14 = *(_DWORD *)&requestPacket[20] == 0;
  for ( k = i + 1; ; k = (unsigned int)(k + 1) )
  {
    if ( (unsigned int)k >= numPathArrayElements )
    {
      *a2 = v14;
      if ( modeInfoArray[0] )
      {
        std::_Deallocate<16>(modeInfoArray[0], (v32 - (unsigned __int64)modeInfoArray[0]) & 0xFFFFFFFFFFFFFFC0uLL);
        *(_OWORD *)modeInfoArray = 0;
        v32 = 0;
      }
      std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(&pathArray);
      return 0;
    }
    if ( v10[k].sourceInfo.adapterId.HighPart != v10[v12].sourceInfo.adapterId.HighPart
      || v10[k].sourceInfo.adapterId.LowPart != v10[v12].sourceInfo.adapterId.LowPart
      || v10[k].sourceInfo.id != v10[v12].sourceInfo.id )
    {
      continue;
    }
    *(LUID *)&requestPacket[8] = v10[v12].targetInfo.adapterId;
    *(_DWORD *)&requestPacket[16] = v10[v12].targetInfo.id;
    v19 = DisplayConfigGetDeviceInfo((DISPLAYCONFIG_DEVICE_INFO_HEADER *)requestPacket);
    DisplayConfigBufferSizes = v19;
    if ( v19 )
      break;
    v20 = *(_DWORD *)&requestPacket[20] != 0;
    v10 = pathArray;
    if ( pathArray[k].targetInfo.rotation == DISPLAYCONFIG_ROTATION_ROTATE180 )
      v20 = *(_DWORD *)&requestPacket[20] == 0;
    if ( v14 != v20 )
    {
      if ( modeInfoArray[0] )
      {
        std::_Deallocate<16>(modeInfoArray[0], (v32 - (unsigned __int64)modeInfoArray[0]) & 0xFFFFFFFFFFFFFFC0uLL);
        *(_OWORD *)modeInfoArray = 0;
        v32 = 0;
        v10 = pathArray;
      }
      if ( v10 )
      {
        v21 = 0x8E38E38E38E38E39uLL * ((v36 - (__int64)v10) >> 3);
        goto LABEL_50;
      }
      return 2147500037LL;
    }
  }
  if ( v19 > 0 )
    DisplayConfigBufferSizes = (unsigned __int16)v19 | 0x80070000;
  if ( modeInfoArray[0] )
  {
    std::_Deallocate<16>(modeInfoArray[0], (v32 - (unsigned __int64)modeInfoArray[0]) & 0xFFFFFFFFFFFFFFC0uLL);
    *(_OWORD *)modeInfoArray = 0;
    v32 = 0;
  }
  v22 = pathArray;
  if ( pathArray )
  {
    v30 = 0x8E38E38E38E38E39uLL * ((v36 - (__int64)pathArray) >> 3);
    goto LABEL_82;
  }
  return DisplayConfigBufferSizes;
}

```

## disassembly

```asm
0x180130ad0  mov     [rsp-8+arg_10], rbx
0x180130ad5  push    rbp
0x180130ad6  push    rsi
0x180130ad7  push    rdi
0x180130ad8  push    r12
0x180130ada  push    r13
0x180130adc  push    r14
0x180130ade  push    r15
0x180130ae0  lea     rbp, [rsp-27h]
0x180130ae5  sub     rsp, 100h
0x180130aec  mov     rax, cs:__security_cookie
0x180130af3  xor     rax, rsp
0x180130af6  mov     [rbp+57h+var_40], rax
0x180130afa  mov     r12, rdx
0x180130afd  mov     rdi, rcx
0x180130b00  xor     r13d, r13d
0x180130b03  mov     [rsp+130h+numPathArrayElements], r13d
0x180130b08  mov     [rbp+57h+numModeInfoArrayElements], r13d
0x180130b0c  lea     rcx, [rsp+130h+pathArray]; void *
0x180130b11  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180130b16  nop
0x180130b17  lea     rcx, [rsp+130h+var_100]; void *
0x180130b1c  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x180130b21  nop
0x180130b22  mov     [rdx], r13b
0x180130b25  lea     esi, [r13+2]
0x180130b29  mov     r14, 8E38E38E38E38E39h
0x180130b33  lea     r8, [rbp+57h+numModeInfoArrayElements]; numModeInfoArrayElements
0x180130b37  lea     rdx, [rsp+130h+numPathArrayElements]; numPathArrayElements
0x180130b3c  mov     ecx, esi; flags
0x180130b3e  call    cs:__imp_GetDisplayConfigBufferSizes
0x180130b44  mov     ebx, eax
0x180130b46  test    eax, eax
0x180130b48  js      loc_180130CD5
0x180130b4e  mov     edx, [rsp+130h+numPathArrayElements]
0x180130b52  mov     r8, [rsp+130h+pathArray]
0x180130b57  mov     rcx, [rsp+130h+var_D8]
0x180130b5c  sub     rcx, r8
0x180130b5f  sar     rcx, 3
0x180130b63  imul    rcx, r14
0x180130b67  cmp     rdx, rcx
0x180130b6a  jb      loc_180131092
0x180130b70  jbe     short loc_180130B94
0x180130b72  mov     rax, [rbp+57h+var_D0]
0x180130b76  sub     rax, r8
0x180130b79  sar     rax, 3
0x180130b7d  imul    rax, r14
0x180130b81  cmp     rdx, rax
0x180130b84  jbe     loc_1801310A4
0x180130b8a  lea     rcx, [rsp+130h+pathArray]
0x180130b8f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180130b94  mov     edx, [rbp+57h+numModeInfoArrayElements]
0x180130b97  mov     r8, [rsp+130h+var_100]
0x180130b9c  mov     rcx, [rsp+130h+var_100+8]
0x180130ba1  sub     rcx, r8
0x180130ba4  sar     rcx, 6
0x180130ba8  cmp     rdx, rcx
0x180130bab  jb      loc_180130F38
0x180130bb1  jbe     short loc_180130BD2
0x180130bb3  mov     rax, [rsp+130h+var_F0]
0x180130bb8  sub     rax, r8
0x180130bbb  sar     rax, 6
0x180130bbf  cmp     rdx, rax
0x180130bc2  jbe     loc_1801310BB
0x180130bc8  lea     rcx, [rsp+130h+var_100]
0x180130bcd  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180130bd2  mov     rax, [rsp+130h+var_100]
0x180130bd7  mov     [rsp+130h+currentTopologyId], r13; currentTopologyId
0x180130bdc  mov     [rsp+130h+modeInfoArray], rax; modeInfoArray
0x180130be1  lea     r9, [rbp+57h+numModeInfoArrayElements]; numModeInfoArrayElements
0x180130be5  mov     r8, [rsp+130h+pathArray]; pathArray
0x180130bea  lea     rdx, [rsp+130h+numPathArrayElements]; numPathArrayElements
0x180130bef  mov     ecx, esi; flags
0x180130bf1  call    cs:__imp_QueryDisplayConfig
0x180130bf7  mov     ebx, eax
0x180130bf9  cmp     eax, 8007007Ah
0x180130bfe  jz      loc_180130B33
0x180130c04  test    eax, eax
0x180130c06  js      loc_180130E8B
0x180130c0c  mov     edx, [rsp+130h+numPathArrayElements]
0x180130c10  test    edx, edx
0x180130c12  jz      loc_180130D7E
0x180130c18  test    rdi, rdi
0x180130c1b  jnz     loc_180130D68
0x180130c21  lea     r8d, [rdi+1]
0x180130c25  mov     rcx, [rsp+130h+pathArray]
0x180130c2a  cmp     r8d, edx
0x180130c2d  jb      loc_180130D31
0x180130c33  mov     edi, r13d
0x180130c36  mov     qword ptr [rbp+57h+requestPacket+8], r13
0x180130c3a  mov     qword ptr [rbp+57h+requestPacket+10h], r13
0x180130c3e  mov     dword ptr [rbp+57h+requestPacket], 0FFFFFFF7h
0x180130c45  mov     dword ptr [rbp+57h+requestPacket+4], 18h
0x180130c4c  mov     eax, edi
0x180130c4e  lea     rsi, [rax+rax*8]
0x180130c52  mov     rax, [rcx+rsi*8+14h]
0x180130c57  mov     qword ptr [rbp+57h+requestPacket+8], rax
0x180130c5b  mov     eax, [rcx+rsi*8+1Ch]
0x180130c5f  mov     dword ptr [rbp+57h+requestPacket+10h], eax
0x180130c62  lea     rcx, [rbp+57h+requestPacket]; requestPacket
0x180130c66  call    cs:__imp_DisplayConfigGetDeviceInfo
0x180130c6c  mov     ebx, eax
0x180130c6e  test    eax, eax
0x180130c70  jnz     loc_180131044
0x180130c76  cmp     dword ptr [rbp+57h+requestPacket+14h], r13d
0x180130c7a  setnz   r14b
0x180130c7e  mov     rcx, [rsp+130h+pathArray]
0x180130c83  cmp     dword ptr [rcx+rsi*8+28h], 3
0x180130c88  jz      loc_1801310EB
0x180130c8e  inc     edi
0x180130c90  cmp     edi, [rsp+130h+numPathArrayElements]
0x180130c94  jb      loc_180130DB1
0x180130c9a  mov     [r12], r14b
0x180130c9e  mov     rcx, [rsp+130h+var_100]
0x180130ca3  test    rcx, rcx
0x180130ca6  jz      short loc_180130CC7
0x180130ca8  mov     rdx, [rsp+130h+var_F0]
0x180130cad  sub     rdx, rcx
0x180130cb0  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180130cb4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130cb9  xorps   xmm0, xmm0
0x180130cbc  movdqu  xmmword ptr [rsp+130h+var_100], xmm0
0x180130cc2  mov     [rsp+130h+var_F0], r13
0x180130cc7  lea     rcx, [rsp+130h+pathArray]
0x180130ccc  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180130cd1  xor     eax, eax
0x180130cd3  jmp     short loc_180130D0A
0x180130cd5  mov     rcx, [rsp+130h+var_100]
0x180130cda  test    rcx, rcx
0x180130cdd  jz      short loc_180130CFE
0x180130cdf  mov     rdx, [rsp+130h+var_F0]
0x180130ce4  sub     rdx, rcx
0x180130ce7  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180130ceb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130cf0  xorps   xmm0, xmm0
0x180130cf3  movdqu  xmmword ptr [rsp+130h+var_100], xmm0
0x180130cf9  mov     [rsp+130h+var_F0], r13
0x180130cfe  lea     rcx, [rsp+130h+pathArray]
0x180130d03  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x180130d08  mov     eax, ebx
0x180130d0a  mov     rcx, [rbp+57h+var_40]
0x180130d0e  xor     rcx, rsp; StackCookie
0x180130d11  call    __security_check_cookie
0x180130d16  mov     rbx, [rsp+130h+arg_10]
0x180130d1e  add     rsp, 100h
0x180130d25  pop     r15
0x180130d27  pop     r14
0x180130d29  pop     r13
0x180130d2b  pop     r12
0x180130d2d  pop     rdi
0x180130d2e  pop     rsi
0x180130d2f  pop     rbp
0x180130d30  retn
0x180130d31  mov     eax, r8d
0x180130d34  lea     r9, [rax+rax*8]
0x180130d38  mov     eax, [rcx+4]
0x180130d3b  cmp     [rcx+r9*8+4], eax
0x180130d40  jnz     loc_180130EE3
0x180130d46  mov     eax, [rcx]
0x180130d48  cmp     [rcx+r9*8], eax
0x180130d4c  jnz     loc_180130EE3
0x180130d52  mov     eax, [rcx+8]
0x180130d55  cmp     [rcx+r9*8+8], eax
0x180130d5a  jnz     loc_180130EE3
0x180130d60  inc     r8d
0x180130d63  jmp     loc_180130C2A
0x180130d68  mov     rcx, rdi; wchar_t *
0x180130d6b  call    ?SkipDeviceNamePrefix@@YAPEB_WPEB_W@Z; SkipDeviceNamePrefix(wchar_t const *)
0x180130d70  mov     rbx, rax
0x180130d73  mov     edi, r13d
0x180130d76  cmp     edi, edx
0x180130d78  jb      loc_180130F49
0x180130d7e  mov     rcx, [rsp+130h+var_100]
0x180130d83  test    rcx, rcx
0x180130d86  jz      short loc_180130DA7
0x180130d88  mov     rdx, [rsp+130h+var_F0]
0x180130d8d  sub     rdx, rcx
0x180130d90  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180130d94  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130d99  xorps   xmm0, xmm0
0x180130d9c  movdqu  xmmword ptr [rsp+130h+var_100], xmm0
0x180130da2  mov     [rsp+130h+var_F0], r13
0x180130da7  mov     rcx, [rsp+130h+pathArray]
0x180130dac  jmp     loc_180130F14
0x180130db1  lea     r15, [rdi+rdi*8]
0x180130db5  mov     eax, [rcx+rsi*8+4]
0x180130db9  cmp     [rcx+r15*8+4], eax
0x180130dbe  jnz     loc_180130F31
0x180130dc4  mov     eax, [rcx+rsi*8]
0x180130dc7  cmp     [rcx+r15*8], eax
0x180130dcb  jnz     loc_180130F31
0x180130dd1  mov     eax, [rcx+rsi*8+8]
0x180130dd5  cmp     [rcx+r15*8+8], eax
0x180130dda  jnz     loc_180130F31
0x180130de0  mov     rax, [rcx+rsi*8+14h]
0x180130de5  mov     qword ptr [rbp+57h+requestPacket+8], rax
0x180130de9  mov     eax, [rcx+rsi*8+1Ch]
0x180130ded  mov     dword ptr [rbp+57h+requestPacket+10h], eax
0x180130df0  lea     rcx, [rbp+57h+requestPacket]; requestPacket
0x180130df4  call    cs:__imp_DisplayConfigGetDeviceInfo
0x180130dfa  mov     ebx, eax
0x180130dfc  test    eax, eax
0x180130dfe  jnz     loc_180130FE5
0x180130e04  cmp     dword ptr [rbp+57h+requestPacket+14h], r13d
0x180130e08  setnz   al
0x180130e0b  mov     rcx, [rsp+130h+pathArray]
0x180130e10  cmp     dword ptr [rcx+r15*8+28h], 3
0x180130e16  jz      loc_1801310F7
0x180130e1c  cmp     r14b, al
0x180130e1f  jz      loc_180130F31
0x180130e25  mov     rax, [rsp+130h+var_100]
0x180130e2a  test    rax, rax
0x180130e2d  jz      short loc_180130E56
0x180130e2f  mov     rdx, [rsp+130h+var_F0]
0x180130e34  sub     rdx, rax
0x180130e37  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180130e3b  mov     rcx, rax
0x180130e3e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130e43  xorps   xmm0, xmm0
0x180130e46  movdqu  xmmword ptr [rsp+130h+var_100], xmm0
0x180130e4c  mov     [rsp+130h+var_F0], r13
0x180130e51  mov     rcx, [rsp+130h+pathArray]
0x180130e56  test    rcx, rcx
0x180130e59  jz      short loc_180130E81
0x180130e5b  mov     rax, [rbp+57h+var_D0]
0x180130e5f  sub     rax, rcx
0x180130e62  sar     rax, 3
0x180130e66  mov     r8, 8E38E38E38E38E39h
0x180130e70  imul    rax, r8
0x180130e74  lea     rdx, [rax+rax*8]
0x180130e78  shl     rdx, 3
0x180130e7c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130e81  mov     eax, 80004005h
0x180130e86  jmp     loc_180130D0A
0x180130e8b  mov     rcx, [rsp+130h+var_100]
0x180130e90  test    rcx, rcx
0x180130e93  jz      short loc_180130EB4
0x180130e95  mov     rdx, [rsp+130h+var_F0]
0x180130e9a  sub     rdx, rcx
0x180130e9d  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180130ea1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130ea6  xorps   xmm0, xmm0
0x180130ea9  movdqu  xmmword ptr [rsp+130h+var_100], xmm0
0x180130eaf  mov     [rsp+130h+var_F0], r13
0x180130eb4  mov     rcx, [rsp+130h+pathArray]
0x180130eb9  test    rcx, rcx
0x180130ebc  jz      loc_180130D08
0x180130ec2  mov     rax, [rbp+57h+var_D0]
0x180130ec6  sub     rax, rcx
0x180130ec9  sar     rax, 3
0x180130ecd  imul    rax, r14
0x180130ed1  lea     rdx, [rax+rax*8]
0x180130ed5  shl     rdx, 3
0x180130ed9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130ede  jmp     loc_180130D08
0x180130ee3  mov     rax, [rsp+130h+var_100]
0x180130ee8  test    rax, rax
0x180130eeb  jz      short loc_180130F14
0x180130eed  mov     rdx, [rsp+130h+var_F0]
0x180130ef2  sub     rdx, rax
0x180130ef5  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180130ef9  mov     rcx, rax
0x180130efc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180130f01  xorps   xmm0, xmm0
0x180130f04  movdqu  xmmword ptr [rsp+130h+var_100], xmm0
0x180130f0a  mov     [rsp+130h+var_F0], r13
0x180130f0f  mov     rcx, [rsp+130h+pathArray]
0x180130f14  test    rcx, rcx
0x180130f17  jz      loc_180130E81
0x180130f1d  mov     rax, [rbp+57h+var_D0]
0x180130f21  sub     rax, rcx
0x180130f24  sar     rax, 3
0x180130f28  imul    rax, r14
0x180130f2c  jmp     loc_180130E74
0x180130f31  inc     edi
0x180130f33  jmp     loc_180130C90
0x180130f38  shl     rdx, 6
0x180130f3c  add     rdx, r8
0x180130f3f  mov     [rsp+130h+var_100+8], rdx
0x180130f44  jmp     loc_180130BD2
0x180130f49  xor     edx, edx; Val
0x180130f4b  lea     r8d, [rdx+50h]; Size
0x180130f4f  lea     rcx, [rbp+57h+var_A0.size]; void *
0x180130f53  call    memset_0
0x180130f58  mov     [rbp+57h+var_A0.type], 1
0x180130f5f  mov     eax, edi
0x180130f61  lea     rdx, [rax+rax*8]
0x180130f65  mov     rcx, [rsp+130h+pathArray]
0x180130f6a  mov     rax, [rcx+rdx*8]
0x180130f6e  mov     qword ptr [rbp+57h+var_A0.adapterId.LowPart], rax
0x180130f72  mov     eax, [rcx+rdx*8+8]
0x180130f76  mov     [rbp+57h+var_A0.id], eax
0x180130f79  mov     [rbp+57h+var_A0.size], 54h ; 'T'
0x180130f80  lea     rcx, [rbp+57h+var_A0]; requestPacket
0x180130f84  call    cs:__imp_DisplayConfigGetDeviceInfo
0x180130f8a  test    eax, eax
0x180130f8c  jnz     loc_1801310D2
0x180130f92  lea     rax, [rbp+57h+var_8C]
0x180130f96  cmp     word ptr [rax], 5Ch ; '\'
0x180130f9a  jz      short loc_180130FCF
  ... truncated ...
```
