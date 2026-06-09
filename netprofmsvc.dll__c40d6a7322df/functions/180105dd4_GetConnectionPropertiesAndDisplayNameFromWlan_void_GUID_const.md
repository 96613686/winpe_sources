# GetConnectionPropertiesAndDisplayNameFromWlan(void *,_GUID const &)

- ea: `0x180105dd4`
- end: `0x18010611c`
- name: `?GetConnectionPropertiesAndDisplayNameFromWlan@@YA@PEAXAEBU_GUID@@@Z`
- size: `840`
- prototype: `_QWORD(void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180064940`
- `0x180105948`

## callees

- `0x180013748`
- `0x180015608`
- `0x180018968`
- `0x180019eb4`
- `0x180026cf4`
- `0x18002a7ec`
- `0x18002b050`
- `0x18002bae4`
- `0x18002d8fc`
- `0x18003ce8c`
- `0x180051a4c`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800c738c`
- `0x180101368`
- `0x180105dd4`
- `0x180108940`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18010609b`
- `wlanapi!WlanFreeMemory` at `0x18010609b`
- `wlanapi!WlanQueryInterface` at `0x180105e55`
- `wlanapi!WlanQueryInterface` at `0x180105e55`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanUtf8SsidToDisplayName` at `0x180105f04`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanUtf8SsidToDisplayName` at `0x180105f04`

## string_xrefs

- `0x1801060dd`: `onecore\net\netprofiles\service\src\l2manager\lib\l2manager.cpp`
- `0x1801060f2`: `onecore\net\netprofiles\service\src\l2manager\lib\l2manager.cpp`
- `0x18010610a`: `onecore\net\netprofiles\service\src\l2manager\lib\l2manager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall GetConnectionPropertiesAndDisplayNameFromWlan(char *a1, struct _GUID *a2, const GUID *a3)
{
  DWORD v4; // edi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  char v8; // al
  _DWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // edi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  _DWORD *v18; // rdi
  int v19; // edx
  int v20; // edx
  unsigned int pdwDataSize; // [rsp+20h] [rbp-E0h]
  PVOID *p_pMemory; // [rsp+50h] [rbp-B0h] BYREF
  PVOID ppData; // [rsp+58h] [rbp-A8h] BYREF
  char v25; // [rsp+60h] [rbp-A0h]
  PVOID pMemory; // [rsp+70h] [rbp-90h] BYREF
  DWORD v27; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+84h] [rbp-7Ch] BYREF
  _QWORD v29[2]; // [rsp+88h] [rbp-78h] BYREF
  __m128i si128; // [rsp+98h] [rbp-68h]
  char v31; // [rsp+A8h] [rbp-58h]
  _BYTE v32[40]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v33; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v34; // [rsp+E0h] [rbp-20h]
  __int64 v35; // [rsp+F0h] [rbp-10h]
  char v36; // [rsp+F8h] [rbp-8h]
  char v37; // [rsp+100h] [rbp+0h]
  _BYTE v38[512]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v37 = 0;
  v31 = 0;
  v27 = 0;
  pMemory = 0;
  p_pMemory = &pMemory;
  ppData = 0;
  v25 = 1;
  v4 = WlanQueryInterface(a2, a3, wlan_intf_opcode_current_connection, 0, &v27, &ppData, 0);
  wil::details::out_param_ptr_t<_WLAN_PROFILE_INFO_LIST * *,wistd::unique_ptr<_WLAN_PROFILE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_ptr_t<_WLAN_PROFILE_INFO_LIST * *,wistd::unique_ptr<_WLAN_PROFILE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>(&p_pMemory);
  if ( v4 == 5023 )
  {
    v9 = pMemory;
  }
  else
  {
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x539,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\l2manager.cpp",
        (const char *)v4,
        pdwDataSize);
    if ( v27 >= 0x25C || (MicrosoftTelemetryAssertTriggeredNoArgs(retaddr, v5, v6, v7), v8 = 1, v27 >= 0x25C) )
      v8 = 0;
    if ( v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x53B,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\l2manager.cpp",
        (const char *)0x8000FFFFLL,
        pdwDataSize);
    v9 = pMemory;
    if ( *(_DWORD *)pMemory == 1 )
    {
      std::optional<ConnectionProperties>::emplace<>((ConnectionProperties *)v32);
      std::wstring::assign(v32, (char *)pMemory + 8);
      memset_0(v38, 0, sizeof(v38));
      v28 = 256;
      v12 = WlanUtf8SsidToDisplayName((char *)pMemory + 520, 1, v38, &v28);
      if ( v12 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v13, v14);
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x547,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\l2manager.cpp",
          (const char *)v12,
          pdwDataSize);
      }
      std::_Optional_destruct_base<std::wstring,0>::reset(v29);
      std::wstring::wstring(v29, v38);
      v31 = 1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::GetImpl'::`2'::impl) )
      {
        std::_Variant_base<std::monostate,WlanConnectionProperties>::_Destroy(&v33);
        v33 = 0;
        v34 = 0;
        v35 = 0;
        v36 = 1;
        v18 = (char *)pMemory + 520;
        if ( *((_DWORD *)pMemory + 130) <= 0x20u
          || (MicrosoftTelemetryAssertTriggeredNoArgs(pMemory, v15, v16, v17), v9 = pMemory, *v18 <= 0x20u) )
        {
          std::vector<unsigned char>::assign<unsigned char const *,0>(
            &v33,
            v18 + 1,
            (char *)v18 + (unsigned int)*v18 + 4);
          v9 = pMemory;
        }
        v19 = v9[140] + 1;
        if ( v9[140] == -1 )
          v19 = *((unsigned __int16 *)v9 + 282) - 0xFFFF;
        LOBYTE(v35) = v19 == 0;
        BYTE1(v35) = v9[147] != 0;
      }
      else
      {
        v9 = pMemory;
        v20 = *((_DWORD *)pMemory + 140) + 1;
        if ( *((_DWORD *)pMemory + 140) == -1 )
          v20 = *((unsigned __int16 *)pMemory + 282) - 0xFFFF;
        v32[32] = v20 == 0;
        v32[33] = *((_DWORD *)pMemory + 147) != 0;
      }
    }
  }
  a1[80] = 0;
  if ( v37 )
  {
    ConnectionProperties::ConnectionProperties(a1, v32);
    a1[80] = 1;
    v9 = pMemory;
  }
  a1[120] = 0;
  if ( v31 )
  {
    *((_QWORD *)a1 + 11) = v29[0];
    *((_QWORD *)a1 + 12) = v29[1];
    *(__m128i *)(a1 + 104) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v29[0]) = 0;
    a1[120] = 1;
  }
  pMemory = 0;
  if ( v9 )
    WlanFreeMemory(v9);
  std::optional<std::wstring>::~optional<std::wstring>(v29);
  std::optional<ConnectionProperties>::~optional<ConnectionProperties>(v32);
  return a1;
}

```

## disassembly

```asm
0x180105dd4  mov     [rsp-8+arg_18], rbx
0x180105dd9  push    rbp
0x180105dda  push    rsi
0x180105ddb  push    rdi
0x180105ddc  lea     rbp, [rsp-220h]
0x180105de4  sub     rsp, 320h
0x180105deb  mov     rax, cs:__security_cookie
0x180105df2  xor     rax, rsp
0x180105df5  mov     [rbp+230h+var_20], rax
0x180105dfc  mov     r10, r8
0x180105dff  mov     rax, rdx
0x180105e02  mov     rbx, rcx
0x180105e05  mov     [rsp+330h+pMemory], rcx
0x180105e0a  xor     esi, esi
0x180105e0c  mov     [rbp+230h+var_230], sil
0x180105e10  mov     [rbp+230h+var_288], sil
0x180105e14  mov     [rbp+230h+var_2B0], esi
0x180105e17  mov     [rsp+330h+pMemory], rsi
0x180105e1c  lea     rcx, [rsp+330h+pMemory]
0x180105e21  mov     [rsp+330h+var_2E0], rcx
0x180105e26  mov     [rsp+330h+var_2D8], rsi
0x180105e2b  mov     [rsp+330h+var_2D0], 1
0x180105e30  mov     [rsp+330h+pWlanOpcodeValueType], rsi; pWlanOpcodeValueType
0x180105e35  lea     rcx, [rsp+330h+var_2D8]
0x180105e3a  mov     [rsp+330h+ppData], rcx; ppData
0x180105e3f  lea     rcx, [rbp+230h+var_2B0]
0x180105e43  mov     [rsp+330h+pdwDataSize], rcx; int
0x180105e48  xor     r9d, r9d; pReserved
0x180105e4b  lea     r8d, [rsi+7]; OpCode
0x180105e4f  mov     rdx, r10; pInterfaceGuid
0x180105e52  mov     rcx, rax; hClientHandle
0x180105e55  call    cs:__imp_WlanQueryInterface
0x180105e5b  mov     edi, eax
0x180105e5d  lea     rcx, [rsp+330h+var_2E0]
0x180105e62  call    ??1?$out_param_ptr_t@PEAPEAU_WLAN_PROFILE_INFO_LIST@@V?$unique_ptr@U_WLAN_PROFILE_INFO_LIST@@U?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<_WLAN_PROFILE_INFO_LIST * *,wistd::unique_ptr<_WLAN_PROFILE_INFO_LIST,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_ptr_t<_WLAN_PROFILE_INFO_LIST * *,wistd::unique_ptr<_WLAN_PROFILE_INFO_LIST,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)
0x180105e67  cmp     edi, 139Fh
0x180105e6d  jz      loc_18010602E
0x180105e73  mov     rcx, [rbp+238h]; this
0x180105e7a  test    edi, edi
0x180105e7c  jnz     loc_1801060EF
0x180105e82  mov     edi, 25Ch
0x180105e87  cmp     [rbp+230h+var_2B0], edi
0x180105e8a  jnb     short loc_180105E98
0x180105e8c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180105e91  cmp     [rbp+230h+var_2B0], edi
0x180105e94  mov     al, 1
0x180105e96  jb      short loc_180105E9B
0x180105e98  mov     al, sil
0x180105e9b  mov     rcx, [rbp+238h]; this
0x180105ea2  test    al, al
0x180105ea4  jnz     loc_180106104
0x180105eaa  mov     rcx, [rsp+330h+pMemory]
0x180105eaf  cmp     dword ptr [rcx], 1
0x180105eb2  jnz     loc_180106033
0x180105eb8  lea     rcx, [rbp+230h+var_280]; this
0x180105ebc  call    ??$emplace@$$V@?$optional@UConnectionProperties@@@std@@QEAAAEAUConnectionProperties@@XZ; std::optional<ConnectionProperties>::emplace<>(void)
0x180105ec1  mov     rdx, [rsp+330h+pMemory]
0x180105ec6  add     rdx, 8
0x180105eca  lea     rcx, [rbp+230h+var_280]
0x180105ece  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180105ed3  xor     edx, edx; Val
0x180105ed5  mov     r8d, 200h; Size
0x180105edb  lea     rcx, [rbp+230h+var_220]; void *
0x180105edf  call    memset_0
0x180105ee4  mov     [rbp+230h+var_2AC], 100h
0x180105eeb  mov     rcx, [rsp+330h+pMemory]
0x180105ef0  add     rcx, 208h
0x180105ef7  lea     r9, [rbp+230h+var_2AC]
0x180105efb  lea     r8, [rbp+230h+var_220]
0x180105eff  mov     edx, 1
0x180105f04  call    cs:__imp_WlanUtf8SsidToDisplayName
0x180105f0a  mov     edi, eax
0x180105f0c  test    eax, eax
0x180105f0e  jz      short loc_180105F15
0x180105f10  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180105f15  mov     rcx, [rbp+238h]; this
0x180105f1c  test    edi, edi
0x180105f1e  jnz     loc_1801060DA
0x180105f24  lea     rcx, [rbp+230h+var_2A8]
0x180105f28  call    ?reset@?$_Optional_destruct_base@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@std@@QEAAXXZ; std::_Optional_destruct_base<std::wstring,0>::reset(void)
0x180105f2d  lea     rdx, [rbp+230h+var_220]
0x180105f31  lea     rcx, [rbp+230h+var_2A8]
0x180105f35  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180105f3a  mov     [rbp+230h+var_288], 1
0x180105f3e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding> `wil::Feature<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::GetImpl(void)'::`2'::impl
0x180105f45  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NLM_Fix_WifiSignatureHexDecoding>::__private_IsEnabled(void)
0x180105f4a  test    al, al
0x180105f4c  jz      loc_180105FEE
0x180105f52  lea     rcx, [rbp+230h+var_258]
0x180105f56  call    ?_Destroy@?$_Variant_base@Umonostate@std@@UWlanConnectionProperties@@@std@@QEAAXXZ; std::_Variant_base<std::monostate,WlanConnectionProperties>::_Destroy(void)
0x180105f5b  xorps   xmm0, xmm0
0x180105f5e  movups  [rbp+230h+var_258], xmm0
0x180105f62  movups  [rbp+230h+var_248], xmm0
0x180105f66  mov     qword ptr [rbp+230h+var_258], rsi
0x180105f6a  movdqa  [rbp+230h+var_258+8], xmm0
0x180105f6f  mov     word ptr [rbp+230h+var_248+8], si
0x180105f73  mov     [rbp+230h+var_238], 1
0x180105f77  mov     rcx, [rsp+330h+pMemory]
0x180105f7c  lea     rdi, [rcx+208h]
0x180105f83  cmp     dword ptr [rdi], 20h ; ' '
0x180105f86  jbe     short loc_180105F97
0x180105f88  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180105f8d  mov     rcx, [rsp+330h+pMemory]
0x180105f92  cmp     dword ptr [rdi], 20h ; ' '
0x180105f95  ja      short loc_180105FB3
0x180105f97  mov     r8d, [rdi]
0x180105f9a  add     r8, 4
0x180105f9e  add     r8, rdi
0x180105fa1  lea     rdx, [rdi+4]
0x180105fa5  lea     rcx, [rbp+230h+var_258]
0x180105fa9  call    ??$assign@PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEBE0@Z; std::vector<uchar>::assign<uchar const *,0>(uchar const *,uchar const *)
0x180105fae  mov     rcx, [rsp+330h+pMemory]
0x180105fb3  mov     [rsp+330h+var_2F0], 0FFFFFFFFh
0x180105fbb  mov     [rsp+330h+var_2EC], 0FFFFh
0x180105fc2  mov     edx, [rcx+230h]
0x180105fc8  sub     edx, [rsp+330h+var_2F0]
0x180105fcc  jnz     short loc_180105FDC
0x180105fce  movzx   edx, word ptr [rcx+234h]
0x180105fd5  movzx   eax, [rsp+330h+var_2EC]
0x180105fda  sub     edx, eax
0x180105fdc  test    edx, edx
0x180105fde  setz    byte ptr [rbp+230h+var_248+8]
0x180105fe2  cmp     [rcx+24Ch], esi
0x180105fe8  setnz   byte ptr [rbp+230h+var_248+9]
0x180105fec  jmp     short loc_180106033
0x180105fee  mov     [rsp+330h+var_2F0], 0FFFFFFFFh
0x180105ff6  mov     [rsp+330h+var_2EC], 0FFFFh
0x180105ffd  mov     rcx, [rsp+330h+pMemory]
0x180106002  mov     edx, [rcx+230h]
0x180106008  sub     edx, [rsp+330h+var_2F0]
0x18010600c  jnz     short loc_18010601C
0x18010600e  movzx   edx, word ptr [rcx+234h]
0x180106015  movzx   eax, [rsp+330h+var_2EC]
0x18010601a  sub     edx, eax
0x18010601c  test    edx, edx
0x18010601e  setz    [rbp+230h+var_260]
0x180106022  cmp     [rcx+24Ch], esi
0x180106028  setnz   [rbp+230h+var_25F]
0x18010602c  jmp     short loc_180106033
0x18010602e  mov     rcx, [rsp+330h+pMemory]
0x180106033  mov     [rbx+50h], sil
0x180106037  cmp     [rbp+230h+var_230], sil
0x18010603b  jz      short loc_180106052
0x18010603d  lea     rdx, [rbp+230h+var_280]
0x180106041  mov     rcx, rbx
0x180106044  call    ??0ConnectionProperties@@QEAA@$$QEAU0@@Z; ConnectionProperties::ConnectionProperties(ConnectionProperties &&)
0x180106049  mov     byte ptr [rbx+50h], 1
0x18010604d  mov     rcx, [rsp+330h+pMemory]; pMemory
0x180106052  mov     [rbx+78h], sil
0x180106056  cmp     [rbp+230h+var_288], sil
0x18010605a  jz      short loc_180106091
0x18010605c  mov     rax, [rbp+230h+var_2A8]
0x180106060  mov     [rbx+58h], rax
0x180106064  mov     rax, [rbp+230h+var_2A0]
0x180106068  mov     [rbx+60h], rax
0x18010606c  mov     rax, qword ptr [rbp+230h+var_298]
0x180106070  mov     [rbx+68h], rax
0x180106074  mov     rax, qword ptr [rbp+230h+var_298+8]
0x180106078  mov     [rbx+70h], rax
0x18010607c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180106084  movdqu  [rbp+230h+var_298], xmm0
0x180106089  mov     word ptr [rbp+230h+var_2A8], si
0x18010608d  mov     byte ptr [rbx+78h], 1
0x180106091  mov     [rsp+330h+pMemory], rsi
0x180106096  test    rcx, rcx
0x180106099  jz      short loc_1801060A2
0x18010609b  call    cs:__imp_WlanFreeMemory
0x1801060a1  nop
0x1801060a2  lea     rcx, [rbp+230h+var_2A8]
0x1801060a6  call    ??1?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEAA@XZ; std::optional<std::wstring>::~optional<std::wstring>(void)
0x1801060ab  nop
0x1801060ac  lea     rcx, [rbp+230h+var_280]
0x1801060b0  call    ??1?$optional@UConnectionProperties@@@std@@QEAA@XZ; std::optional<ConnectionProperties>::~optional<ConnectionProperties>(void)
0x1801060b5  mov     rax, rbx
0x1801060b8  mov     rcx, [rbp+230h+var_20]
0x1801060bf  xor     rcx, rsp; StackCookie
0x1801060c2  call    __security_check_cookie
0x1801060c7  mov     rbx, [rsp+330h+arg_18]
0x1801060cf  add     rsp, 320h
0x1801060d6  pop     rdi
0x1801060d7  pop     rsi
0x1801060d8  pop     rbp
0x1801060d9  retn
0x1801060da  mov     r9d, edi; char *
0x1801060dd  lea     r8, aOnecoreNetNetp_55; "onecore\\net\\netprofiles\\service\\src"...
0x1801060e4  mov     edx, 547h; void *
0x1801060e9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801060ef  mov     r9d, edi; char *
0x1801060f2  lea     r8, aOnecoreNetNetp_55; "onecore\\net\\netprofiles\\service\\src"...
0x1801060f9  mov     edx, 539h; void *
0x1801060fe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180106104  mov     r9d, 8000FFFFh; char *
0x18010610a  lea     r8, aOnecoreNetNetp_55; "onecore\\net\\netprofiles\\service\\src"...
0x180106111  mov     edx, 53Bh; void *
0x180106116  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
