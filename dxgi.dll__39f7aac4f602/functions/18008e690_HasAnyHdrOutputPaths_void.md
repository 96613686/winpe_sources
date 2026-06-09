# HasAnyHdrOutputPaths(void)

- ea: `0x18008e690`
- end: `0x18008ec82`
- name: `?HasAnyHdrOutputPaths@@YA_NXZ`
- size: `1522`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180058eb8`

## callees

- `0x18000fd40`
- `0x18004e190`
- `0x18004e368`
- `0x18004f870`
- `0x180050154`
- `0x18005301c`
- `0x180053898`
- `0x180058e6c`
- `0x180059230`
- `0x180071770`
- `0x180075fa0`
- `0x18008e690`
- `0x180092168`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x18008ea4e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x18008ea4e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18008eb7e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18008eb7e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18008e6d2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x18008e6d2`

## string_xrefs

- `0x18008e728`: `GetDisplayConfigBufferSizes failed unexpectedly`
- `0x18008eaac`: `QueryDisplayConfig failed unexpectedly`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char HasAnyHdrOutputPaths(void)
{
  char v1; // [rsp+30h] [rbp-128h]
  LONG DisplayConfigBufferSizes; // [rsp+34h] [rbp-124h]
  LONG v3; // [rsp+34h] [rbp-124h]
  UINT32 numPathArrayElements; // [rsp+4Ch] [rbp-10Ch] BYREF
  UINT32 numModeInfoArrayElements; // [rsp+50h] [rbp-108h] BYREF
  UINT32 i; // [rsp+54h] [rbp-104h]
  __int64 *v7; // [rsp+58h] [rbp-100h]
  LONG DeviceInfo; // [rsp+60h] [rbp-F8h]
  int v9; // [rsp+68h] [rbp-F0h]
  int v10; // [rsp+6Ch] [rbp-ECh]
  int v11; // [rsp+70h] [rbp-E8h]
  int v12; // [rsp+74h] [rbp-E4h]
  int v13; // [rsp+78h] [rbp-E0h]
  BOOL v14; // [rsp+7Ch] [rbp-DCh]
  unsigned int v15; // [rsp+80h] [rbp-D8h]
  int v16; // [rsp+84h] [rbp-D4h]
  unsigned int v17; // [rsp+88h] [rbp-D0h]
  unsigned int v18; // [rsp+8Ch] [rbp-CCh]
  unsigned int v19; // [rsp+90h] [rbp-C8h]
  int v20; // [rsp+94h] [rbp-C4h]
  unsigned int v21; // [rsp+98h] [rbp-C0h]
  __int64 v22; // [rsp+A0h] [rbp-B8h]
  _BYTE v23[24]; // [rsp+A8h] [rbp-B0h] BYREF
  __int64 *v24; // [rsp+C0h] [rbp-98h]
  DISPLAYCONFIG_MODE_INFO *modeInfoArray; // [rsp+C8h] [rbp-90h]
  DISPLAYCONFIG_PATH_INFO *pathArray; // [rsp+D0h] [rbp-88h]
  _BYTE v27[24]; // [rsp+D8h] [rbp-80h] BYREF
  __int64 *v28; // [rsp+F0h] [rbp-68h]
  __int64 *v29; // [rsp+F8h] [rbp-60h]
  __int64 *v30; // [rsp+110h] [rbp-48h]
  __int64 *v31; // [rsp+118h] [rbp-40h]
  __int64 *v32; // [rsp+120h] [rbp-38h]
  _BYTE requestPacket[32]; // [rsp+128h] [rbp-30h] BYREF

  numPathArrayElements = 0;
  numModeInfoArrayElements = 0;
  DisplayConfigBufferSizes = GetDisplayConfigBufferSizes(2u, &numPathArrayElements, &numModeInfoArrayElements);
  if ( DisplayConfigBufferSizes )
  {
    if ( DisplayConfigBufferSizes > 0 )
      v18 = (unsigned __int16)DisplayConfigBufferSizes | 0x80070000;
    else
      v18 = DisplayConfigBufferSizes;
    v21 = v18;
    RecordJournal(v18, "GetDisplayConfigBufferSizes failed unexpectedly", 0);
    return 0;
  }
  else
  {
    v24 = `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2602>::GetImpl'::`2'::impl;
    v7 = `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2602>::GetImpl'::`2'::impl;
    v28 = `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2602>::GetImpl'::`2'::impl;
    v29 = `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2602>::GetImpl'::`2'::impl;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_2602>::GetImpl'::`2'::impl);
    v30 = v7;
    v31 = v7;
    v32 = v7;
    v9 = 1;
    v10 = 1;
    v11 = 1;
    v12 = 1;
    v13 = 1;
    v14 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2602>::__private_IsEnabled(v7) != 0;
    if ( !v14 || numModeInfoArrayElements && numPathArrayElements )
    {
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(v23);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(v27);
      do
      {
        std::vector<DISPLAYCONFIG_PATH_INFO>::resize(v23, numPathArrayElements);
        std::vector<DISPLAYCONFIG_MODE_INFO>::resize(v27, numModeInfoArrayElements);
        modeInfoArray = (DISPLAYCONFIG_MODE_INFO *)std::vector<DISPLAYCONFIG_MODE_INFO>::operator[](v27, 0);
        pathArray = (DISPLAYCONFIG_PATH_INFO *)std::vector<DISPLAYCONFIG_PATH_INFO>::operator[](v23, 0);
        v3 = QueryDisplayConfig(2u, &numPathArrayElements, pathArray, &numModeInfoArrayElements, modeInfoArray, 0);
      }
      while ( v3 == 111 );
      if ( v3 )
      {
        if ( v3 > 0 )
          v15 = (unsigned __int16)v3 | 0x80070000;
        else
          v15 = v3;
        v19 = v15;
        RecordHRESULT(v15, "QueryDisplayConfig failed unexpectedly");
        std::vector<DISPLAYCONFIG_MODE_INFO>::~vector<DISPLAYCONFIG_MODE_INFO>(v27);
        std::vector<DISPLAYCONFIG_PATH_INFO>::~vector<DISPLAYCONFIG_PATH_INFO>(v23);
        return 0;
      }
      else
      {
        v1 = 0;
        for ( i = 0; i < numPathArrayElements; ++i )
        {
          v22 = std::vector<DISPLAYCONFIG_PATH_INFO>::operator[](v23, i);
          memset(requestPacket, 0, sizeof(requestPacket));
          *(_DWORD *)requestPacket = 9;
          *(_DWORD *)&requestPacket[4] = 32;
          *(_QWORD *)&requestPacket[8] = *(_QWORD *)(v22 + 20);
          *(_DWORD *)&requestPacket[16] = *(_DWORD *)(v22 + 28);
          DeviceInfo = DisplayConfigGetDeviceInfo((DISPLAYCONFIG_DEVICE_INFO_HEADER *)requestPacket);
          if ( DeviceInfo > 0 )
            v16 = (unsigned __int16)DeviceInfo | 0x80070000;
          else
            v16 = DeviceInfo;
          v20 = v16;
          v17 = v16;
          if ( v16 < 0 )
          {
            RecordHRESULT(v17, "GetAdvancedColorInfo failed");
            std::vector<DISPLAYCONFIG_MODE_INFO>::~vector<DISPLAYCONFIG_MODE_INFO>(v27);
            std::vector<DISPLAYCONFIG_PATH_INFO>::~vector<DISPLAYCONFIG_PATH_INFO>(v23);
            return 0;
          }
          if ( ((*(_DWORD *)&requestPacket[20] >> 1) & 1) != 0 && ((*(_DWORD *)&requestPacket[20] >> 2) & 1) == 0 )
          {
            v1 = 1;
            break;
          }
        }
        std::vector<DISPLAYCONFIG_MODE_INFO>::~vector<DISPLAYCONFIG_MODE_INFO>(v27);
        std::vector<DISPLAYCONFIG_PATH_INFO>::~vector<DISPLAYCONFIG_PATH_INFO>(v23);
        return v1;
      }
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18008e690  push    rdi
0x18008e692  sub     rsp, 150h
0x18008e699  mov     rax, cs:__security_cookie
0x18008e6a0  xor     rax, rsp
0x18008e6a3  mov     [rsp+158h+var_10], rax
0x18008e6ab  mov     [rsp+158h+var_124], 0
0x18008e6b3  mov     [rsp+158h+numPathArrayElements], 0
0x18008e6bb  mov     [rsp+158h+numModeInfoArrayElements], 0
0x18008e6c3  lea     r8, [rsp+158h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18008e6c8  lea     rdx, [rsp+158h+numPathArrayElements]; numPathArrayElements
0x18008e6cd  mov     ecx, 2; flags
0x18008e6d2  call    cs:__imp_GetDisplayConfigBufferSizes
0x18008e6d8  mov     [rsp+158h+var_124], eax
0x18008e6dc  cmp     [rsp+158h+var_124], 0
0x18008e6e1  jz      short loc_18008E73D
0x18008e6e3  cmp     [rsp+158h+var_124], 0
0x18008e6e8  jg      short loc_18008E6F7
0x18008e6ea  mov     eax, [rsp+158h+var_124]
0x18008e6ee  mov     [rsp+158h+var_CC], eax
0x18008e6f5  jmp     short loc_18008E710
0x18008e6f7  mov     eax, [rsp+158h+var_124]
0x18008e6fb  and     eax, 0FFFFh
0x18008e700  or      eax, 70000h
0x18008e705  bts     eax, 1Fh
0x18008e709  mov     [rsp+158h+var_CC], eax
0x18008e710  mov     eax, [rsp+158h+var_CC]
0x18008e717  mov     [rsp+158h+var_C0], eax
0x18008e71e  mov     eax, [rsp+158h+var_C0]
0x18008e725  xor     r8d, r8d; bool
0x18008e728  lea     rdx, aGetdisplayconf_1; "GetDisplayConfigBufferSizes failed unex"...
0x18008e72f  mov     ecx, eax; unsigned int
0x18008e731  call    ?RecordJournal@@YAXIPEBD_N@Z; RecordJournal(uint,char const *,bool)
0x18008e736  xor     al, al
0x18008e738  jmp     loc_18008EC69
0x18008e73d  lea     rax, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_2602@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2602@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2602> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_2602>::GetImpl(void)'::`2'::impl
0x18008e744  mov     [rsp+158h+var_98], rax
0x18008e74c  mov     rax, [rsp+158h+var_98]
0x18008e754  mov     [rsp+158h+var_100], rax
0x18008e759  mov     rax, [rsp+158h+var_100]
0x18008e75e  mov     [rsp+158h+var_68], rax
0x18008e766  mov     rax, [rsp+158h+var_100]
0x18008e76b  mov     [rsp+158h+var_60], rax
0x18008e773  xor     eax, eax
0x18008e775  test    eax, eax
0x18008e777  jz      short loc_18008E7A2
0x18008e779  mov     rax, [rsp+158h+var_100]
0x18008e77e  mov     [rsp+158h+var_58], rax
0x18008e786  mov     eax, 1
0x18008e78b  test    eax, eax
0x18008e78d  jnz     short loc_18008E7AF
0x18008e78f  mov     rax, [rsp+158h+var_100]
0x18008e794  mov     [rsp+158h+var_50], rax
0x18008e79c  xor     eax, eax
0x18008e79e  test    eax, eax
0x18008e7a0  jz      short loc_18008E7AF
0x18008e7a2  mov     rcx, [rsp+158h+var_100]
0x18008e7a7  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabledPreCheck(void)
0x18008e7ac  movzx   eax, al
0x18008e7af  mov     rax, [rsp+158h+var_100]
0x18008e7b4  mov     [rsp+158h+var_48], rax
0x18008e7bc  xor     eax, eax
0x18008e7be  test    eax, eax
0x18008e7c0  jnz     loc_18008E979
0x18008e7c6  mov     rax, [rsp+158h+var_100]
0x18008e7cb  mov     [rsp+158h+var_40], rax
0x18008e7d3  xor     eax, eax
0x18008e7d5  test    eax, eax
0x18008e7d7  jnz     loc_18008E96F
0x18008e7dd  mov     rax, [rsp+158h+var_100]
0x18008e7e2  mov     [rsp+158h+var_38], rax
0x18008e7ea  xor     eax, eax
0x18008e7ec  test    eax, eax
0x18008e7ee  jnz     loc_18008E93B
0x18008e7f4  xor     eax, eax
0x18008e7f6  cmp     eax, 1
0x18008e7f9  jz      loc_18008E931
0x18008e7ff  xor     eax, eax
0x18008e801  test    eax, eax
0x18008e803  jnz     loc_18008E8F4
0x18008e809  xor     eax, eax
0x18008e80b  cmp     eax, 1
0x18008e80e  jz      loc_18008E90E
0x18008e814  xor     eax, eax
0x18008e816  test    eax, eax
0x18008e818  jnz     loc_18008E8B7
0x18008e81e  xor     eax, eax
0x18008e820  cmp     eax, 1
0x18008e823  jz      loc_18008E8D1
0x18008e829  xor     eax, eax
0x18008e82b  test    eax, eax
0x18008e82d  jnz     short loc_18008E87A
0x18008e82f  xor     eax, eax
0x18008e831  cmp     eax, 1
0x18008e834  jz      short loc_18008E894
0x18008e836  xor     eax, eax
0x18008e838  cmp     eax, 1
0x18008e83b  jz      short loc_18008E857
0x18008e83d  mov     [rsp+158h+var_120], 1
0x18008e842  mov     al, [rsp+158h+var_120]
0x18008e846  movzx   eax, al
0x18008e849  test    eax, eax
0x18008e84b  jz      short loc_18008E857
0x18008e84d  mov     [rsp+158h+var_F0], 1
0x18008e855  jmp     short loc_18008E85F
0x18008e857  mov     [rsp+158h+var_F0], 0
0x18008e85f  mov     al, byte ptr [rsp+158h+var_F0]
0x18008e863  mov     [rsp+158h+var_11F], al
0x18008e867  mov     al, [rsp+158h+var_11F]
0x18008e86b  mov     [rsp+158h+var_11E], al
0x18008e86f  mov     al, [rsp+158h+var_11E]
0x18008e873  movzx   eax, al
0x18008e876  test    eax, eax
0x18008e878  jz      short loc_18008E894
0x18008e87a  mov     [rsp+158h+var_11D], 1
0x18008e87f  mov     al, [rsp+158h+var_11D]
0x18008e883  movzx   eax, al
0x18008e886  test    eax, eax
0x18008e888  jz      short loc_18008E894
0x18008e88a  mov     [rsp+158h+var_EC], 1
0x18008e892  jmp     short loc_18008E89C
0x18008e894  mov     [rsp+158h+var_EC], 0
0x18008e89c  mov     al, byte ptr [rsp+158h+var_EC]
0x18008e8a0  mov     [rsp+158h+var_11C], al
0x18008e8a4  mov     al, [rsp+158h+var_11C]
0x18008e8a8  mov     [rsp+158h+var_11B], al
0x18008e8ac  mov     al, [rsp+158h+var_11B]
0x18008e8b0  movzx   eax, al
0x18008e8b3  test    eax, eax
0x18008e8b5  jz      short loc_18008E8D1
0x18008e8b7  mov     [rsp+158h+var_11A], 1
0x18008e8bc  mov     al, [rsp+158h+var_11A]
0x18008e8c0  movzx   eax, al
0x18008e8c3  test    eax, eax
0x18008e8c5  jz      short loc_18008E8D1
0x18008e8c7  mov     [rsp+158h+var_E8], 1
0x18008e8cf  jmp     short loc_18008E8D9
0x18008e8d1  mov     [rsp+158h+var_E8], 0
0x18008e8d9  mov     al, byte ptr [rsp+158h+var_E8]
0x18008e8dd  mov     [rsp+158h+var_119], al
0x18008e8e1  mov     al, [rsp+158h+var_119]
0x18008e8e5  mov     [rsp+158h+var_118], al
0x18008e8e9  mov     al, [rsp+158h+var_118]
0x18008e8ed  movzx   eax, al
0x18008e8f0  test    eax, eax
0x18008e8f2  jz      short loc_18008E90E
0x18008e8f4  mov     [rsp+158h+var_117], 1
0x18008e8f9  mov     al, [rsp+158h+var_117]
0x18008e8fd  movzx   eax, al
0x18008e900  test    eax, eax
0x18008e902  jz      short loc_18008E90E
0x18008e904  mov     [rsp+158h+var_E4], 1
0x18008e90c  jmp     short loc_18008E916
0x18008e90e  mov     [rsp+158h+var_E4], 0
0x18008e916  mov     al, byte ptr [rsp+158h+var_E4]
0x18008e91a  mov     [rsp+158h+var_116], al
0x18008e91e  mov     al, [rsp+158h+var_116]
0x18008e922  mov     [rsp+158h+var_115], al
0x18008e926  mov     al, [rsp+158h+var_115]
0x18008e92a  movzx   eax, al
0x18008e92d  test    eax, eax
0x18008e92f  jnz     short loc_18008E93B
0x18008e931  mov     [rsp+158h+var_E0], 0
0x18008e939  jmp     short loc_18008E943
0x18008e93b  mov     [rsp+158h+var_E0], 1
0x18008e943  mov     al, byte ptr [rsp+158h+var_E0]
0x18008e947  mov     [rsp+158h+var_114], al
0x18008e94b  mov     al, [rsp+158h+var_114]
0x18008e94f  mov     [rsp+158h+var_113], al
0x18008e953  mov     al, [rsp+158h+var_113]
0x18008e957  movzx   eax, al
0x18008e95a  test    eax, eax
0x18008e95c  jz      short loc_18008E96F
0x18008e95e  mov     rcx, [rsp+158h+var_100]
0x18008e963  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_2602@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_2602>::__private_IsEnabled(void)
0x18008e968  movzx   eax, al
0x18008e96b  test    eax, eax
0x18008e96d  jnz     short loc_18008E979
0x18008e96f  mov     [rsp+158h+var_DC], 0
0x18008e977  jmp     short loc_18008E981
0x18008e979  mov     [rsp+158h+var_DC], 1
0x18008e981  mov     al, byte ptr [rsp+158h+var_DC]
0x18008e985  mov     [rsp+158h+var_112], al
0x18008e989  mov     al, [rsp+158h+var_112]
0x18008e98d  mov     [rsp+158h+var_111], al
0x18008e991  mov     al, [rsp+158h+var_111]
0x18008e995  movzx   eax, al
0x18008e998  test    eax, eax
0x18008e99a  jz      short loc_18008E9B1
0x18008e99c  cmp     [rsp+158h+numModeInfoArrayElements], 0
0x18008e9a1  jz      short loc_18008E9AA
0x18008e9a3  cmp     [rsp+158h+numPathArrayElements], 0
0x18008e9a8  jnz     short loc_18008E9B1
0x18008e9aa  xor     al, al
0x18008e9ac  jmp     loc_18008EC69
0x18008e9b1  lea     rcx, [rsp+158h+var_B0]
0x18008e9b9  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x18008e9be  nop
0x18008e9bf  lea     rcx, [rsp+158h+var_80]
0x18008e9c7  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x18008e9cc  nop
0x18008e9cd  mov     eax, [rsp+158h+numPathArrayElements]
0x18008e9d1  mov     edx, eax
0x18008e9d3  lea     rcx, [rsp+158h+var_B0]
0x18008e9db  call    ?resize@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAAX_K@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::resize(unsigned __int64)
0x18008e9e0  mov     eax, [rsp+158h+numModeInfoArrayElements]
0x18008e9e4  mov     edx, eax
0x18008e9e6  lea     rcx, [rsp+158h+var_80]
0x18008e9ee  call    ?resize@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@QEAAX_K@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::resize(unsigned __int64)
0x18008e9f3  xor     edx, edx
0x18008e9f5  lea     rcx, [rsp+158h+var_80]
0x18008e9fd  call    ??A?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@QEAAAEAUDISPLAYCONFIG_MODE_INFO@@_K@Z; std::vector<DISPLAYCONFIG_MODE_INFO>::operator[](unsigned __int64)
0x18008ea02  mov     [rsp+158h+var_90], rax
0x18008ea0a  xor     edx, edx
0x18008ea0c  lea     rcx, [rsp+158h+var_B0]
0x18008ea14  call    ??A?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAAAEAUDISPLAYCONFIG_PATH_INFO@@_K@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::operator[](unsigned __int64)
0x18008ea19  mov     [rsp+158h+pathArray], rax
0x18008ea21  mov     [rsp+158h+currentTopologyId], 0; currentTopologyId
0x18008ea2a  mov     rax, [rsp+158h+var_90]
0x18008ea32  mov     [rsp+158h+modeInfoArray], rax; modeInfoArray
0x18008ea37  lea     r9, [rsp+158h+numModeInfoArrayElements]; numModeInfoArrayElements
0x18008ea3c  mov     r8, [rsp+158h+pathArray]; pathArray
0x18008ea44  lea     rdx, [rsp+158h+numPathArrayElements]; numPathArrayElements
0x18008ea49  mov     ecx, 2; flags
0x18008ea4e  call    cs:__imp_QueryDisplayConfig
0x18008ea54  mov     [rsp+158h+var_124], eax
0x18008ea58  cmp     [rsp+158h+var_124], 6Fh ; 'o'
0x18008ea5d  jz      loc_18008E9CD
0x18008ea63  cmp     [rsp+158h+var_124], 0
0x18008ea68  jz      short loc_18008EAE4
0x18008ea6a  cmp     [rsp+158h+var_124], 0
0x18008ea6f  jg      short loc_18008EA7E
0x18008ea71  mov     eax, [rsp+158h+var_124]
0x18008ea75  mov     [rsp+158h+var_D8], eax
0x18008ea7c  jmp     short loc_18008EA97
0x18008ea7e  mov     eax, [rsp+158h+var_124]
0x18008ea82  and     eax, 0FFFFh
0x18008ea87  or      eax, 70000h
0x18008ea8c  bts     eax, 1Fh
0x18008ea90  mov     [rsp+158h+var_D8], eax
0x18008ea97  mov     eax, [rsp+158h+var_D8]
0x18008ea9e  mov     [rsp+158h+var_C8], eax
0x18008eaa5  mov     eax, [rsp+158h+var_C8]
0x18008eaac  lea     rdx, aQuerydisplayco_1; "QueryDisplayConfig failed unexpectedly"
0x18008eab3  mov     ecx, eax; unsigned int
0x18008eab5  call    ?RecordHRESULT@@YAJJPEBD@Z; RecordHRESULT(long,char const *)
0x18008eaba  nop
0x18008eabb  mov     [rsp+158h+var_110], 0
0x18008eac0  lea     rcx, [rsp+158h+var_80]
0x18008eac8  call    ??1?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@QEAA@XZ; std::vector<DISPLAYCONFIG_MODE_INFO>::~vector<DISPLAYCONFIG_MODE_INFO>(void)
0x18008eacd  nop
0x18008eace  lea     rcx, [rsp+158h+var_B0]
0x18008ead6  call    ??1?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAA@XZ; std::vector<DISPLAYCONFIG_PATH_INFO>::~vector<DISPLAYCONFIG_PATH_INFO>(void)
0x18008eadb  mov     al, [rsp+158h+var_110]
0x18008eadf  jmp     loc_18008EC69
0x18008eae4  mov     [rsp+158h+var_128], 0
0x18008eae9  mov     [rsp+158h+var_104], 0
0x18008eaf1  jmp     short loc_18008EAFD
0x18008eaf3  mov     eax, [rsp+158h+var_104]
0x18008eaf7  inc     eax
0x18008eaf9  mov     [rsp+158h+var_104], eax
0x18008eafd  mov     eax, [rsp+158h+numPathArrayElements]
0x18008eb01  cmp     [rsp+158h+var_104], eax
0x18008eb05  jnb     loc_18008EC42
0x18008eb0b  mov     eax, [rsp+158h+var_104]
0x18008eb0f  mov     edx, eax
0x18008eb11  lea     rcx, [rsp+158h+var_B0]
0x18008eb19  call    ??A?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@QEAAAEAUDISPLAYCONFIG_PATH_INFO@@_K@Z; std::vector<DISPLAYCONFIG_PATH_INFO>::operator[](unsigned __int64)
0x18008eb1e  mov     [rsp+158h+var_B8], rax
0x18008eb26  lea     rax, [rsp+158h+requestPacket]
0x18008eb2e  mov     rdi, rax
0x18008eb31  xor     eax, eax
0x18008eb33  mov     ecx, 20h ; ' '
0x18008eb38  rep stosb
0x18008eb3a  mov     [rsp+158h+requestPacket.type], 9
0x18008eb45  mov     [rsp+158h+requestPacket.size], 20h ; ' '
0x18008eb50  mov     rax, [rsp+158h+var_B8]
0x18008eb58  mov     rax, [rax+14h]
0x18008eb5c  mov     qword ptr [rsp+158h+requestPacket.adapterId.LowPart], rax
0x18008eb64  mov     rax, [rsp+158h+var_B8]
0x18008eb6c  mov     eax, [rax+1Ch]
0x18008eb6f  mov     [rsp+158h+requestPacket.id], eax
0x18008eb76  lea     rcx, [rsp+158h+requestPacket]; requestPacket
0x18008eb7e  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18008eb84  mov     [rsp+158h+var_F8], eax
0x18008eb88  cmp     [rsp+158h+var_F8], 0
0x18008eb8d  jg      short loc_18008EB9C
0x18008eb8f  mov     eax, [rsp+158h+var_F8]
0x18008eb93  mov     [rsp+158h+var_D4], eax
0x18008eb9a  jmp     short loc_18008EBB5
0x18008eb9c  mov     eax, [rsp+158h+var_F8]
0x18008eba0  and     eax, 0FFFFh
0x18008eba5  or      eax, 70000h
0x18008ebaa  bts     eax, 1Fh
0x18008ebae  mov     [rsp+158h+var_D4], eax
0x18008ebb5  mov     eax, [rsp+158h+var_D4]
0x18008ebbc  mov     [rsp+158h+var_C4], eax
0x18008ebc3  mov     eax, [rsp+158h+var_C4]
0x18008ebca  mov     [rsp+158h+var_D0], eax
0x18008ebd1  cmp     [rsp+158h+var_D0], 0
0x18008ebd9  jge     short loc_18008EC15
  ... truncated ...
```
