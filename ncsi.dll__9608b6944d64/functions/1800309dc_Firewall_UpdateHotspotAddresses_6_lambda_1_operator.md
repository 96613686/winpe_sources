# _Firewall::UpdateHotspotAddresses_::_6_::_lambda_1_::operator()

- ea: `0x1800309dc`
- end: `0x1800310d2`
- name: `_Firewall::UpdateHotspotAddresses_::_6_::_lambda_1_::operator()`
- size: `1782`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180055820`

## callees

- `0x180003e78`
- `0x18000ce20`
- `0x18000e59c`
- `0x1800212c8`
- `0x18002b2dc`
- `0x1800301e8`
- `0x1800309dc`
- `0x18003eca8`
- `0x180042d00`
- `0x180047240`
- `0x180047f6c`
- `0x180047f78`
- `0x18004f5f0`
- `0x180055060`
- `0x1800551b4`
- `0x1800552ec`
- `0x1800556b4`
- `0x18005582c`
- `0x1800558c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030d9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030d9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030a57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030a57`
- `WS2_32!WSAAddressToStringW` at `0x180030b1f`
- `WS2_32!WSAAddressToStringW` at `0x180030cb8`
- `WS2_32!WSAAddressToStringW` at `0x180030b1f`
- `WS2_32!WSAAddressToStringW` at `0x180030cb8`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWIndicateTupleInUse` at `0x180030e99`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWIndicateTupleInUse` at `0x180030f09`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWIndicateTupleInUse` at `0x180030e99`
- `ext-ms-win-firewallapi-webproxy-l1-1-0!FWIndicateTupleInUse` at `0x180030f09`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 Firewall::UpdateHotspotAddresses_::_6_::_lambda_1_::operator()()
{
  NCSI_INTERFACE_ATTRIBUTES *v0; // r15
  struct NCSI_INTERFACE_ATTRIBUTES *v1; // r13
  LPSOCKADDR v2; // r14
  struct sockaddr *v3; // r12
  DWORD v4; // edx
  __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  __int64 v7; // rsi
  __int128 *p_Src; // rdi
  LPSOCKADDR v9; // r14
  struct sockaddr *v10; // r12
  __int64 v11; // rdx
  __int64 v12; // rax
  DWORD v13; // edx
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rsi
  __int128 *v17; // rdi
  __int64 v18; // rbx
  int v19; // eax
  wil::details::in1diag3 *v20; // rcx
  __int64 v21; // rbx
  int v22; // eax
  DWORD v23; // eax
  DWORD v24; // edi
  DWORD v25; // eax
  DWORD v26; // ebx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  const size_t *v30; // rax
  __int64 result; // rax
  const char *v32; // r9
  unsigned int lpdwAddressStringLength; // [rsp+20h] [rbp-1E8h]
  __int64 v34; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 v35; // [rsp+58h] [rbp-1B0h] BYREF
  __int64 v36; // [rsp+60h] [rbp-1A8h] BYREF
  const size_t *v37; // [rsp+68h] [rbp-1A0h] BYREF
  char v38[24]; // [rsp+70h] [rbp-198h] BYREF
  unsigned int v39; // [rsp+88h] [rbp-180h] BYREF
  __int64 v40; // [rsp+90h] [rbp-178h]
  unsigned int v41; // [rsp+A8h] [rbp-160h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-158h]
  DWORD dwAddressStringLength; // [rsp+C0h] [rbp-148h] BYREF
  DWORD v44; // [rsp+C4h] [rbp-144h] BYREF
  __int128 Src; // [rsp+C8h] [rbp-140h] BYREF
  __int64 v46; // [rsp+D8h] [rbp-130h]
  unsigned __int64 v47; // [rsp+E0h] [rbp-128h]
  __int128 v48; // [rsp+E8h] [rbp-120h] BYREF
  __int64 v49; // [rsp+F8h] [rbp-110h]
  __int128 v50; // [rsp+100h] [rbp-108h] BYREF
  __int64 v51; // [rsp+110h] [rbp-F8h]
  LPSOCKADDR lpsaAddress; // [rsp+118h] [rbp-F0h] BYREF
  struct sockaddr *v53; // [rsp+120h] [rbp-E8h]
  WCHAR szAddressString[72]; // [rsp+130h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  Src = 0;
  v46 = 0;
  v47 = 7;
  LOWORD(Src) = 0;
  v50 = 0;
  v51 = 0;
  v48 = 0;
  v49 = 0;
  EnterCriticalSection(&g_ncsiLock);
  v35 = (__int64)&g_ncsiLock;
  v0 = g_ncsiInterfaceList;
  v1 = xmmword_18009DCC0;
  try
  {
    while ( v0 != v1 )
    {
      NCSI_INTERFACE_ATTRIBUTES::GetHotspotAddresses(v0, &lpsaAddress, 0);
      v2 = lpsaAddress;
      v3 = v53;
      while ( v2 != v3 )
      {
        LODWORD(v34) = *(_DWORD *)&v2->sa_data[2];
        HIDWORD(v34) = v34;
        if ( *((_QWORD *)&v50 + 1) == v51 )
        {
          std::vector<_tag_FW_IPV4_ADDRESS_RANGE>::_Emplace_reallocate<_tag_FW_IPV4_ADDRESS_RANGE>(
            &v50,
            *((_QWORD *)&v50 + 1),
            &v34);
        }
        else
        {
          **((_QWORD **)&v50 + 1) = v34;
          *((_QWORD *)&v50 + 1) += 8LL;
        }
        dwAddressStringLength = 65;
        v4 = 28;
        if ( v2->sa_family != 23 )
          v4 = 16;
        if ( WSAAddressToStringW(v2, v4, 0, szAddressString, &dwAddressStringLength) != -1 )
        {
          v5 = v46;
          if ( v46 )
          {
            std::wstring::push_back(&Src, 44);
            v5 = v46;
          }
          v6 = -1;
          do
            ++v6;
          while ( szAddressString[v6] );
          if ( v6 > v47 - v5 )
          {
            ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
              &Src,
              v6);
          }
          else
          {
            v7 = v6 + v5;
            v46 = v6 + v5;
            p_Src = &Src;
            if ( v47 > 7 )
              p_Src = (__int128 *)Src;
            memmove_0((char *)p_Src + 2 * v5, szAddressString, 2 * v6);
            *((_WORD *)p_Src + v7) = 0;
          }
        }
        v2 = (LPSOCKADDR)((char *)v2 + 28);
      }
      std::vector<_SOCKADDR_INET>::_Tidy(&lpsaAddress);
      NCSI_INTERFACE_ATTRIBUTES::GetHotspotAddresses(v0, &lpsaAddress, 1);
      v9 = lpsaAddress;
      v10 = v53;
      while ( v9 != v10 )
      {
        v11 = *((_QWORD *)&v48 + 1);
        if ( *((_QWORD *)&v48 + 1) == v49 )
        {
          std::vector<_tag_FW_IPV6_ADDRESS_RANGE>::_Emplace_reallocate<>(&v48);
          v12 = *((_QWORD *)&v48 + 1);
        }
        else
        {
          **((_OWORD **)&v48 + 1) = 0;
          *(_OWORD *)(v11 + 16) = 0;
          v12 = *((_QWORD *)&v48 + 1) + 32LL;
          *((_QWORD *)&v48 + 1) += 32LL;
        }
        *(struct sockaddr *)(v12 - 32) = *(struct sockaddr *)&v9->sa_data[6];
        *(struct sockaddr *)(*((_QWORD *)&v48 + 1) - 16LL) = *(struct sockaddr *)&v9->sa_data[6];
        v44 = 65;
        v13 = 28;
        if ( v9->sa_family != 23 )
          v13 = 16;
        if ( WSAAddressToStringW(v9, v13, 0, szAddressString, &v44) != -1 )
        {
          v14 = v46;
          if ( v46 )
          {
            std::wstring::push_back(&Src, 44);
            v14 = v46;
          }
          v15 = -1;
          do
            ++v15;
          while ( szAddressString[v15] );
          if ( v15 > v47 - v14 )
          {
            ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
              &Src,
              v15);
          }
          else
          {
            v16 = v15 + v14;
            v46 = v15 + v14;
            v17 = &Src;
            if ( v47 > 7 )
              v17 = (__int128 *)Src;
            memmove_0((char *)v17 + 2 * v14, szAddressString, 2 * v15);
            *((_WORD *)v17 + v16) = 0;
          }
        }
        v9 = (LPSOCKADDR)((char *)v9 + 28);
      }
      std::vector<_SOCKADDR_INET>::_Tidy(&lpsaAddress);
      v0 = (NCSI_INTERFACE_ATTRIBUTES *)((char *)v0 + 12888);
    }
    if ( &g_ncsiLock )
      LeaveCriticalSection(&g_ncsiLock);
    memset_0(v38, 0, 0x48u);
    v18 = v50;
    if ( (_QWORD)v50 != *((_QWORD *)&v50 + 1) )
    {
      v19 = LongLongToULong((__int64)(*((_QWORD *)&v50 + 1) - v50) >> 3, &v39);
      if ( v19 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\firewallutil.cpp",
          (const char *)(unsigned int)v19,
          lpdwAddressStringLength);
      v40 = v18;
    }
    v20 = (wil::details::in1diag3 *)*((_QWORD *)&v48 + 1);
    v21 = v48;
    if ( (_QWORD)v48 == *((_QWORD *)&v48 + 1) )
    {
      v21 = v42;
    }
    else
    {
      v22 = LongLongToULong((__int64)(*((_QWORD *)&v48 + 1) - v48) >> 5, &v41);
      v20 = retaddr;
      if ( v22 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x8C,
          (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\firewallutil.cpp",
          (const char *)(unsigned int)v22,
          lpdwAddressStringLength);
      v42 = v21;
    }
    if ( v40 || v21 )
    {
      LOWORD(lpdwAddressStringLength) = 0;
      v23 = FWIndicateTupleInUse(9, 0, 1, 256);
      v24 = v23;
      if ( !qword_18009DA10 && !v23 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( v24 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x96,
          (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\firewallutil.cpp",
          (const char *)v24,
          lpdwAddressStringLength);
      LOWORD(lpdwAddressStringLength) = 0;
      v25 = FWIndicateTupleInUse(9, 0, 2, 256);
      v26 = v25;
      if ( !qword_18009DA08 && !v25 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( v26 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x9B,
          (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\firewallutil.cpp",
          (const char *)v26,
          lpdwAddressStringLength);
      if ( (unsigned int)dword_18009A048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A048, 0x400000000000LL) )
      {
        v34 = qword_18009DA08;
        v44 = v26;
        v36 = qword_18009DA10;
        dwAddressStringLength = v24;
        v30 = (const size_t *)&Src;
        if ( v47 > 7 )
          v30 = (const size_t *)Src;
        v37 = v30;
        v35 = 2048;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v27,
          (int)&word_18008699E,
          v28,
          v29,
          (__int64)&v35,
          &v37,
          (__int64)&dwAddressStringLength,
          (__int64)&v36,
          (__int64)&v44,
          (__int64)&v34);
      }
    }
    else
    {
      ResetFirewallHotspotHostAddresses(v20);
    }
    if ( (_QWORD)v48 )
    {
      std::_Deallocate<16>((void *)v48, (v49 - v48) & 0xFFFFFFFFFFFFFFE0uLL);
      v48 = 0;
      v49 = 0;
    }
    if ( (_QWORD)v50 )
    {
      std::_Deallocate<16>((void *)v50, (v51 - v50) & 0xFFFFFFFFFFFFFFF8uLL);
      v50 = 0;
      v51 = 0;
    }
    result = std::wstring::_Tidy_deallocate(&Src);
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0xAD,
             (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\firewallutil.cpp",
             v32);
  }
  return result;
}

```

## disassembly

```asm
0x1800309dc  mov     r11, rsp
0x1800309df  push    rbx
0x1800309e0  push    rsi
0x1800309e1  push    rdi
0x1800309e2  push    r12
0x1800309e4  push    r13
0x1800309e6  push    r14
0x1800309e8  push    r15
0x1800309ea  sub     rsp, 1D0h
0x1800309f1  mov     rax, cs:__security_cookie
0x1800309f8  xor     rax, rsp
0x1800309fb  mov     [rsp+208h+var_48], rax
0x180030a03  xorps   xmm0, xmm0
0x180030a06  movups  [rsp+208h+Src], xmm0
0x180030a0e  xor     esi, esi
0x180030a10  mov     [r11-130h], rsi
0x180030a17  mov     qword ptr [r11-128h], 7
0x180030a22  mov     word ptr [rsp+208h+Src], si
0x180030a2a  xorps   xmm1, xmm1
0x180030a2d  movdqu  [rsp+208h+var_108], xmm1
0x180030a36  mov     [r11-0F8h], rsi
0x180030a3d  movdqu  [rsp+208h+var_120], xmm1
0x180030a46  mov     [r11-110h], rsi
0x180030a4d  lea     rbx, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x180030a54  mov     rcx, rbx; lpCriticalSection
0x180030a57  call    cs:__imp_EnterCriticalSection
0x180030a5d  mov     [rsp+208h+var_1B0], rbx
0x180030a62  mov     r15, cs:?g_ncsiInterfaceList@@3V?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@A; std::vector<NCSI_INTERFACE_ATTRIBUTES> g_ncsiInterfaceList
0x180030a69  mov     r13, qword ptr cs:xmmword_18009DCC0
0x180030a70  lea     edi, [rsi+10h]
0x180030a73  cmp     r15, r13
0x180030a76  jz      loc_180030D97
0x180030a7c  xor     r8d, r8d
0x180030a7f  lea     rdx, [rsp+208h+lpsaAddress]
0x180030a87  mov     rcx, r15
0x180030a8a  call    ?GetHotspotAddresses@NCSI_INTERFACE_ATTRIBUTES@@QEBA?AV?$vector@T_SOCKADDR_INET@@V?$allocator@T_SOCKADDR_INET@@@std@@@std@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::GetHotspotAddresses(_NLA_CONNECTIVITY_FAMILY)
0x180030a8f  nop
0x180030a90  mov     r14, [rsp+208h+lpsaAddress]
0x180030a98  mov     r12, [rsp+208h+var_E8]
0x180030aa0  cmp     r14, r12
0x180030aa3  jz      loc_180030BE5
0x180030aa9  mov     eax, [r14+4]
0x180030aad  mov     dword ptr [rsp+208h+var_1B8], eax
0x180030ab1  mov     dword ptr [rsp+208h+var_1B8+4], eax
0x180030ab5  mov     rdx, qword ptr [rsp+208h+var_108+8]
0x180030abd  cmp     rdx, [rsp+208h+var_F8]
0x180030ac5  jz      short loc_180030ADA
0x180030ac7  mov     rax, [rsp+208h+var_1B8]
0x180030acc  mov     [rdx], rax
0x180030acf  add     qword ptr [rsp+208h+var_108+8], 8
0x180030ad8  jmp     short loc_180030AEC
0x180030ada  lea     r8, [rsp+208h+var_1B8]
0x180030adf  lea     rcx, [rsp+208h+var_108]
0x180030ae7  call    ??$_Emplace_reallocate@U_tag_FW_IPV4_ADDRESS_RANGE@@@?$vector@U_tag_FW_IPV4_ADDRESS_RANGE@@V?$allocator@U_tag_FW_IPV4_ADDRESS_RANGE@@@std@@@std@@AEAAPEAU_tag_FW_IPV4_ADDRESS_RANGE@@QEAU2@$$QEAU2@@Z; std::vector<_tag_FW_IPV4_ADDRESS_RANGE>::_Emplace_reallocate<_tag_FW_IPV4_ADDRESS_RANGE>(_tag_FW_IPV4_ADDRESS_RANGE * const,_tag_FW_IPV4_ADDRESS_RANGE &&)
0x180030aec  mov     [rsp+208h+dwAddressStringLength], 41h ; 'A'
0x180030af7  mov     edx, 1Ch
0x180030afc  cmp     word ptr [r14], 17h
0x180030b01  cmovnz  edx, edi; dwAddressLength
0x180030b04  lea     rax, [rsp+208h+dwAddressStringLength]
0x180030b0c  mov     [rsp+208h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x180030b11  lea     r9, [rsp+208h+szAddressString]; lpszAddressString
0x180030b19  xor     r8d, r8d; lpProtocolInfo
0x180030b1c  mov     rcx, r14; lpsaAddress
0x180030b1f  call    cs:__imp_WSAAddressToStringW
0x180030b25  cmp     eax, 0FFFFFFFFh
0x180030b28  jz      loc_180030BDC
0x180030b2e  mov     rcx, [rsp+208h+var_130]
0x180030b36  test    rcx, rcx
0x180030b39  jz      short loc_180030B55
0x180030b3b  mov     edx, 2Ch ; ','
0x180030b40  lea     rcx, [rsp+208h+Src]
0x180030b48  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180030b4d  mov     rcx, [rsp+208h+var_130]
0x180030b55  lea     rax, [rsp+208h+szAddressString]
0x180030b5d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180030b61  inc     rdx
0x180030b64  cmp     [rax+rdx*2], si
0x180030b68  jnz     short loc_180030B61
0x180030b6a  mov     rax, [rsp+208h+var_128]
0x180030b72  sub     rax, rcx
0x180030b75  cmp     rdx, rax
0x180030b78  ja      short loc_180030BC2
0x180030b7a  lea     rsi, [rdx+rcx]
0x180030b7e  mov     [rsp+208h+var_130], rsi
0x180030b86  lea     rdi, [rsp+208h+Src]
0x180030b8e  cmp     [rsp+208h+var_128], 7
0x180030b97  cmova   rdi, qword ptr [rsp+208h+Src]
0x180030ba0  lea     r8, [rdx+rdx]; Size
0x180030ba4  lea     rcx, [rdi+rcx*2]; void *
0x180030ba8  lea     rdx, [rsp+208h+szAddressString]; Src
0x180030bb0  call    memmove_0
0x180030bb5  xor     eax, eax
0x180030bb7  mov     [rdi+rsi*2], ax
0x180030bbb  xor     esi, esi
0x180030bbd  lea     edi, [rax+10h]
0x180030bc0  jmp     short loc_180030BDC
0x180030bc2  mov     [rsp+208h+lpdwAddressStringLength], rdx; __int64
0x180030bc7  lea     r9, [rsp+208h+szAddressString]
0x180030bcf  lea     rcx, [rsp+208h+Src]; Src
0x180030bd7  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180030bdc  add     r14, 1Ch
0x180030be0  jmp     loc_180030AA0
0x180030be5  lea     rcx, [rsp+208h+lpsaAddress]
0x180030bed  call    ?_Tidy@?$vector@T_SOCKADDR_INET@@V?$allocator@T_SOCKADDR_INET@@@std@@@std@@AEAAXXZ; std::vector<_SOCKADDR_INET>::_Tidy(void)
0x180030bf2  mov     r8d, 1
0x180030bf8  lea     rdx, [rsp+208h+lpsaAddress]
0x180030c00  mov     rcx, r15
0x180030c03  call    ?GetHotspotAddresses@NCSI_INTERFACE_ATTRIBUTES@@QEBA?AV?$vector@T_SOCKADDR_INET@@V?$allocator@T_SOCKADDR_INET@@@std@@@std@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::GetHotspotAddresses(_NLA_CONNECTIVITY_FAMILY)
0x180030c08  nop
0x180030c09  mov     r14, [rsp+208h+lpsaAddress]
0x180030c11  mov     r12, [rsp+208h+var_E8]
0x180030c19  cmp     r14, r12
0x180030c1c  jz      loc_180030D7E
0x180030c22  mov     rdx, qword ptr [rsp+208h+var_120+8]
0x180030c2a  cmp     rdx, [rsp+208h+var_110]
0x180030c32  jz      short loc_180030C54
0x180030c34  xorps   xmm0, xmm0
0x180030c37  movups  xmmword ptr [rdx], xmm0
0x180030c3a  movups  xmmword ptr [rdx+10h], xmm0
0x180030c3e  mov     rax, qword ptr [rsp+208h+var_120+8]
0x180030c46  add     rax, 20h ; ' '
0x180030c4a  mov     qword ptr [rsp+208h+var_120+8], rax
0x180030c52  jmp     short loc_180030C69
0x180030c54  lea     rcx, [rsp+208h+var_120]
0x180030c5c  call    ??$_Emplace_reallocate@$$V@?$vector@U_tag_FW_IPV6_ADDRESS_RANGE@@V?$allocator@U_tag_FW_IPV6_ADDRESS_RANGE@@@std@@@std@@AEAAPEAU_tag_FW_IPV6_ADDRESS_RANGE@@QEAU2@@Z; std::vector<_tag_FW_IPV6_ADDRESS_RANGE>::_Emplace_reallocate<>(_tag_FW_IPV6_ADDRESS_RANGE * const)
0x180030c61  mov     rax, qword ptr [rsp+208h+var_120+8]
0x180030c69  movups  xmm0, xmmword ptr [r14+8]
0x180030c6e  movdqu  xmmword ptr [rax-20h], xmm0
0x180030c73  movups  xmm1, xmmword ptr [r14+8]
0x180030c78  mov     rax, qword ptr [rsp+208h+var_120+8]
0x180030c80  movdqu  xmmword ptr [rax-10h], xmm1
0x180030c85  mov     [rsp+208h+var_144], 41h ; 'A'
0x180030c90  mov     edx, 1Ch
0x180030c95  cmp     word ptr [r14], 17h
0x180030c9a  cmovnz  edx, edi; dwAddressLength
0x180030c9d  lea     rax, [rsp+208h+var_144]
0x180030ca5  mov     [rsp+208h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x180030caa  lea     r9, [rsp+208h+szAddressString]; lpszAddressString
0x180030cb2  xor     r8d, r8d; lpProtocolInfo
0x180030cb5  mov     rcx, r14; lpsaAddress
0x180030cb8  call    cs:__imp_WSAAddressToStringW
0x180030cbe  cmp     eax, 0FFFFFFFFh
0x180030cc1  jz      loc_180030D75
0x180030cc7  mov     rcx, [rsp+208h+var_130]
0x180030ccf  test    rcx, rcx
0x180030cd2  jz      short loc_180030CEE
0x180030cd4  mov     edx, 2Ch ; ','
0x180030cd9  lea     rcx, [rsp+208h+Src]
0x180030ce1  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180030ce6  mov     rcx, [rsp+208h+var_130]
0x180030cee  lea     rax, [rsp+208h+szAddressString]
0x180030cf6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180030cfa  inc     rdx
0x180030cfd  cmp     [rax+rdx*2], si
0x180030d01  jnz     short loc_180030CFA
0x180030d03  mov     rax, [rsp+208h+var_128]
0x180030d0b  sub     rax, rcx
0x180030d0e  cmp     rdx, rax
0x180030d11  ja      short loc_180030D5B
0x180030d13  lea     rsi, [rdx+rcx]
0x180030d17  mov     [rsp+208h+var_130], rsi
0x180030d1f  lea     rdi, [rsp+208h+Src]
0x180030d27  cmp     [rsp+208h+var_128], 7
0x180030d30  cmova   rdi, qword ptr [rsp+208h+Src]
0x180030d39  lea     r8, [rdx+rdx]; Size
0x180030d3d  lea     rcx, [rdi+rcx*2]; void *
0x180030d41  lea     rdx, [rsp+208h+szAddressString]; Src
0x180030d49  call    memmove_0
0x180030d4e  xor     eax, eax
0x180030d50  mov     [rdi+rsi*2], ax
0x180030d54  xor     esi, esi
0x180030d56  lea     edi, [rax+10h]
0x180030d59  jmp     short loc_180030D75
0x180030d5b  mov     [rsp+208h+lpdwAddressStringLength], rdx; __int64
0x180030d60  lea     r9, [rsp+208h+szAddressString]
0x180030d68  lea     rcx, [rsp+208h+Src]; Src
0x180030d70  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180030d75  add     r14, 1Ch
0x180030d79  jmp     loc_180030C19
0x180030d7e  lea     rcx, [rsp+208h+lpsaAddress]
0x180030d86  call    ?_Tidy@?$vector@T_SOCKADDR_INET@@V?$allocator@T_SOCKADDR_INET@@@std@@@std@@AEAAXXZ; std::vector<_SOCKADDR_INET>::_Tidy(void)
0x180030d8b  add     r15, 3258h
0x180030d92  jmp     loc_180030A73
0x180030d97  test    rbx, rbx
0x180030d9a  jz      short loc_180030DA5
0x180030d9c  mov     rcx, rbx; lpCriticalSection
0x180030d9f  call    cs:__imp_LeaveCriticalSection
0x180030da5  xor     edx, edx; Val
0x180030da7  lea     r8d, [rdx+48h]; Size
0x180030dab  lea     rcx, [rsp+208h+var_198]; void *
0x180030db0  call    memset_0
0x180030db5  mov     rcx, qword ptr [rsp+208h+var_108+8]
0x180030dbd  mov     rbx, qword ptr [rsp+208h+var_108]
0x180030dc5  cmp     rbx, rcx
0x180030dc8  jz      short loc_180030DF6
0x180030dca  sub     rcx, rbx
0x180030dcd  sar     rcx, 3; __int64
0x180030dd1  lea     rdx, [rsp+208h+var_180]; unsigned int *
0x180030dd9  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180030dde  mov     rcx, [rsp+208h]; this
0x180030de6  test    eax, eax
0x180030de8  js      loc_1800310A8
0x180030dee  mov     [rsp+208h+var_178], rbx
0x180030df6  mov     rcx, qword ptr [rsp+208h+var_120+8]
0x180030dfe  mov     rbx, qword ptr [rsp+208h+var_120]
0x180030e06  cmp     rbx, rcx
0x180030e09  jz      short loc_180030E39
0x180030e0b  sub     rcx, rbx
0x180030e0e  sar     rcx, 5; __int64
0x180030e12  lea     rdx, [rsp+208h+var_160]; unsigned int *
0x180030e1a  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180030e1f  mov     rcx, [rsp+208h]; this
0x180030e27  test    eax, eax
0x180030e29  js      loc_1800310BC
0x180030e2f  mov     [rsp+208h+var_158], rbx
0x180030e37  jmp     short loc_180030E41
0x180030e39  mov     rbx, [rsp+208h+var_158]
0x180030e41  cmp     [rsp+208h+var_178], rsi
0x180030e49  jnz     short loc_180030E5A
0x180030e4b  test    rbx, rbx
0x180030e4e  jnz     short loc_180030E5A
0x180030e50  call    ResetFirewallHotspotHostAddresses
0x180030e55  jmp     loc_18003100D
0x180030e5a  mov     ebx, 100h
0x180030e5f  mov     r9d, ebx
0x180030e62  lea     rdx, qword_18009DA10
0x180030e69  mov     [rsp+208h+var_1C0], rdx
0x180030e6e  mov     [rsp+208h+var_1C8], rsi
0x180030e73  lea     rdx, [rsp+208h+var_198]
0x180030e78  mov     [rsp+208h+var_1D0], rdx
0x180030e7d  mov     [rsp+208h+var_1D8], rsi
0x180030e82  mov     word ptr [rsp+208h+var_1E0], si
0x180030e87  mov     word ptr [rsp+208h+lpdwAddressStringLength], si; unsigned int
0x180030e8c  xor     edx, edx
0x180030e8e  lea     r8d, [rdx+1]
0x180030e92  lea     r14d, [rdx+9]
0x180030e96  mov     ecx, r14d
0x180030e99  call    cs:__imp_FWIndicateTupleInUse
0x180030e9f  mov     edi, eax
0x180030ea1  cmp     cs:qword_18009DA10, rsi
0x180030ea8  jnz     short loc_180030EB3
0x180030eaa  test    eax, eax
0x180030eac  jnz     short loc_180030EB3
0x180030eae  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030eb3  mov     rcx, [rsp+208h]; this
0x180030ebb  test    edi, edi
0x180030ebd  jz      short loc_180030ED3
0x180030ebf  mov     r9d, edi; char *
0x180030ec2  lea     r8, aOnecoreNetDiag_8; "onecore\\net\\diagnostics\\ncsi\\lib\\f"...
0x180030ec9  mov     edx, 96h; void *
0x180030ece  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180030ed3  mov     r9d, ebx
0x180030ed6  lea     r8, qword_18009DA08
0x180030edd  mov     [rsp+208h+var_1C0], r8
0x180030ee2  mov     [rsp+208h+var_1C8], rsi
0x180030ee7  lea     r8, [rsp+208h+var_198]
0x180030eec  mov     [rsp+208h+var_1D0], r8
0x180030ef1  mov     [rsp+208h+var_1D8], rsi
0x180030ef6  mov     word ptr [rsp+208h+var_1E0], si
0x180030efb  mov     word ptr [rsp+208h+lpdwAddressStringLength], si; unsigned int
0x180030f00  xor     edx, edx
0x180030f02  lea     r8d, [rdx+2]
0x180030f06  mov     ecx, r14d
0x180030f09  call    cs:__imp_FWIndicateTupleInUse
0x180030f0f  mov     ebx, eax
0x180030f11  cmp     cs:qword_18009DA08, rsi
0x180030f18  jnz     short loc_180030F23
0x180030f1a  test    eax, eax
0x180030f1c  jnz     short loc_180030F23
0x180030f1e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030f23  mov     rcx, [rsp+208h]; this
0x180030f2b  test    ebx, ebx
0x180030f2d  jz      short loc_180030F43
0x180030f2f  mov     r9d, ebx; char *
0x180030f32  lea     r8, aOnecoreNetDiag_8; "onecore\\net\\diagnostics\\ncsi\\lib\\f"...
0x180030f39  mov     edx, 9Bh; void *
0x180030f3e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180030f43  mov     eax, cs:dword_18009A048
0x180030f49  cmp     eax, 5
0x180030f4c  jbe     loc_18003100D
0x180030f52  mov     rdx, 400000000000h
0x180030f5c  lea     rcx, dword_18009A048
0x180030f63  call    _tlgKeywordOn
0x180030f68  test    al, al
0x180030f6a  jz      loc_18003100D
0x180030f70  mov     rax, cs:qword_18009DA08
0x180030f77  mov     [rsp+208h+var_1B8], rax
0x180030f7c  mov     [rsp+208h+var_144], ebx
0x180030f83  mov     rax, cs:qword_18009DA10
0x180030f8a  mov     [rsp+208h+var_1A8], rax
0x180030f8f  mov     [rsp+208h+dwAddressStringLength], edi
0x180030f96  lea     rax, [rsp+208h+Src]
0x180030f9e  cmp     [rsp+208h+var_128], 7
0x180030fa7  cmova   rax, qword ptr [rsp+208h+Src]
0x180030fb0  mov     [rsp+208h+var_1A0], rax
0x180030fb5  mov     [rsp+208h+var_1B0], 800h
0x180030fbe  lea     rax, [rsp+208h+var_1B8]
0x180030fc3  mov     [rsp+208h+var_1C0], rax
0x180030fc8  lea     rax, [rsp+208h+var_144]
0x180030fd0  mov     [rsp+208h+var_1C8], rax
  ... truncated ...
```
