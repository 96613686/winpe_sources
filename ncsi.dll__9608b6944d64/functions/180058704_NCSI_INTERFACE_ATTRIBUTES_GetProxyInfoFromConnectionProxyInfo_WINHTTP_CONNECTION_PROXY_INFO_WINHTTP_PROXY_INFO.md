# NCSI_INTERFACE_ATTRIBUTES::GetProxyInfoFromConnectionProxyInfo(_WINHTTP_CONNECTION_PROXY_INFO &,_WINHTTP_PROXY_INFO &)

- ea: `0x180058704`
- end: `0x180058b67`
- name: `?GetProxyInfoFromConnectionProxyInfo@NCSI_INTERFACE_ATTRIBUTES@@AEAAKAEAU_WINHTTP_CONNECTION_PROXY_INFO@@AEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `1123`
- prototype: `unsigned int __fastcall(NET_LUID *InterfaceLuid, struct _WINHTTP_CONNECTION_PROXY_INFO *, struct _WINHTTP_PROXY_INFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021c38`

## callees

- `0x180010200`
- `0x180011a58`
- `0x180013e48`
- `0x18001814c`
- `0x180026790`
- `0x180027d64`
- `0x18002ad50`
- `0x180047240`
- `0x180047f78`
- `0x180054e78`
- `0x180058704`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058ad9`
- `WINHTTP!WinHttpOpen` at `0x180058970`
- `WINHTTP!WinHttpOpen` at `0x180058970`
- `WINHTTP!WinHttpSetOption` at `0x180058a0b`
- `WINHTTP!WinHttpSetOption` at `0x180058a83`
- `WINHTTP!WinHttpSetOption` at `0x180058a0b`
- `WINHTTP!WinHttpSetOption` at `0x180058a83`
- `WINHTTP!WinHttpCloseHandle` at `0x1800589d6`
- `WINHTTP!WinHttpCloseHandle` at `0x180058a64`
- `WINHTTP!WinHttpCloseHandle` at `0x180058b3b`
- `WINHTTP!WinHttpCloseHandle` at `0x1800589d6`
- `WINHTTP!WinHttpCloseHandle` at `0x180058a64`
- `WINHTTP!WinHttpCloseHandle` at `0x180058b3b`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180058acf`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x180058acf`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180058989`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180058989`

## pseudocode

```c
__int64 __fastcall NCSI_INTERFACE_ATTRIBUTES::GetProxyInfoFromConnectionProxyInfo(
        NET_LUID *InterfaceLuid,
        struct _WINHTTP_CONNECTION_PROXY_INFO *a2,
        struct _WINHTTP_PROXY_INFO *a3)
{
  int v3; // eax
  __int64 v7; // r8
  const char *v8; // r9
  int v9; // eax
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  void *v16; // rbx
  unsigned int v17; // eax
  unsigned int v18; // esi
  DWORD LastError; // edi
  __int64 v20; // r10
  __int64 v21; // rdx
  __int64 dwFlags; // [rsp+20h] [rbp-E0h]
  WINHTTP_AUTOPROXY_OPTIONS pAutoProxyOptions; // [rsp+30h] [rbp-D0h] BYREF
  ULONG InterfaceIndex[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD Buffer[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v26[1568]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR cwszUrl[272]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v3 = *((_DWORD *)a2 + 5);
  if ( !v3 )
  {
    memset_0(cwszUrl, 0, 0x208u);
    if ( *((_QWORD *)a2 + 3) )
    {
      if ( (int)StringCchPrintfW(cwszUrl, 0x104u, L"%s:%d") < 0 )
      {
        v9 = StringCchPrintfW(cwszUrl, 0x104u, L"%s:%d", *((_QWORD *)a2 + 3), *((unsigned __int16 *)a2 + 32));
        v10 = *((_QWORD *)a2 + 3);
        LODWORD(dwFlags) = *((unsigned __int16 *)a2 + 32);
        v11 = (v9 & 0x1FFF0000) == 0x70000
            ? (unsigned __int16)StringCchPrintfW(cwszUrl, 0x104u, L"%s:%d", v10, dwFlags)
            : StringCchPrintfW(cwszUrl, 0x104u, L"%s:%d", v10, dwFlags);
        if ( v11 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids);
          }
          return v11;
        }
      }
      *(_QWORD *)InterfaceIndex = 0;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        InterfaceIndex,
        (char *)cwszUrl,
        v7,
        v8);
      v13 = *(_QWORD *)InterfaceIndex;
      if ( !*(_QWORD *)InterfaceIndex )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(InterfaceIndex);
        return 14;
      }
      *(_QWORD *)InterfaceIndex = 0;
      *((_QWORD *)a3 + 1) = v13;
      *((_QWORD *)a3 + 2) = 0;
      *(_DWORD *)a3 = 3;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(InterfaceIndex);
      return 0;
    }
    return 1168;
  }
  memset(&pAutoProxyOptions, 0, sizeof(pAutoProxyOptions));
  if ( v3 == 1 )
  {
    pAutoProxyOptions.lpszAutoConfigUrl = (LPCWSTR)*((_QWORD *)a2 + 3);
    v14 = 2;
  }
  else
  {
    if ( v3 != 2 )
      return 1168;
    v14 = 1;
    pAutoProxyOptions.dwAutoDetectFlags = 3;
  }
  pAutoProxyOptions.fAutoLogonIfChallenged = 1;
  pAutoProxyOptions.dwFlags = v14 | 0x20000;
  memset_0(v26, 0, 0x61Au);
  NcsiConfigData::GetWebProbeDataForFamily(v15, 0, v26);
  v11 = StringCchPrintfW(cwszUrl, 0x10Bu, L"http://%s", v26);
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids, v11);
    }
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v11;
    return v11;
  }
  InterfaceIndex[0] = 0;
  v16 = WinHttpOpen(c_userAgent, 1u, 0, 0, 0x10000000u);
  v17 = ConvertInterfaceLuidToIndex(InterfaceLuid, InterfaceIndex);
  v18 = v17;
  if ( v17 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids, v17);
    }
    if ( v16 )
      WinHttpCloseHandle(v16);
    return v18;
  }
  memset(Buffer, 0, sizeof(Buffer));
  HIDWORD(Buffer[0]) = 3;
  if ( !WinHttpSetOption(v16, 0xAAu, Buffer, 0x20u) )
  {
    LastError = GetLastError();
    v20 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
      || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_41;
    }
    v21 = 37;
    goto LABEL_40;
  }
  if ( WinHttpSetOption(v16, 0x70u, InterfaceIndex, 4u) )
  {
    if ( WinHttpGetProxyForUrl(v16, cwszUrl, &pAutoProxyOptions, (WINHTTP_PROXY_INFO *)a3) )
    {
      if ( v16 )
        WinHttpCloseHandle(v16);
      return 0;
    }
    LastError = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        39,
        (unsigned int)WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids,
        (unsigned int)cwszUrl,
        LastError);
    }
    if ( LastError == 12180 )
      LastError = 1168;
    goto LABEL_41;
  }
  LastError = GetLastError();
  v20 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v21 = 38;
LABEL_40:
    WPP_SF_dd(*(_QWORD *)(v20 + 16), v21, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids, InterfaceIndex[0], LastError);
  }
LABEL_41:
  if ( v16 )
    WinHttpCloseHandle(v16);
  return LastError;
}

```

## disassembly

```asm
0x180058704  push    rbp
0x180058706  push    rbx
0x180058707  push    rsi
0x180058708  push    rdi
0x180058709  push    r15
0x18005870b  lea     rbp, [rsp-7D0h]
0x180058713  sub     rsp, 8D0h
0x18005871a  mov     rax, cs:__security_cookie
0x180058721  xor     rax, rsp
0x180058724  mov     [rbp+7F0h+var_30], rax
0x18005872b  mov     eax, [rdx+14h]
0x18005872e  mov     rdi, r8
0x180058731  mov     rbx, rdx
0x180058734  mov     rsi, rcx
0x180058737  test    eax, eax
0x180058739  jnz     loc_180058881
0x18005873f  xor     edx, edx; Val
0x180058741  lea     rcx, [rbp+7F0h+cwszUrl]; void *
0x180058748  mov     r8d, 208h; Size
0x18005874e  call    memset_0
0x180058753  mov     r9, [rbx+18h]
0x180058757  test    r9, r9
0x18005875a  jz      loc_180058B45
0x180058760  movzx   eax, word ptr [rbx+40h]
0x180058764  lea     rsi, aSD; "%s:%d"
0x18005876b  mov     r15d, 104h
0x180058771  mov     [rsp+8F0h+dwFlags], eax
0x180058775  mov     r8, rsi; unsigned __int16 *
0x180058778  lea     rcx, [rbp+7F0h+cwszUrl]; unsigned __int16 *
0x18005877f  mov     edx, r15d; unsigned __int64
0x180058782  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058787  test    eax, eax
0x180058789  jns     loc_180058824
0x18005878f  movzx   eax, word ptr [rbx+40h]
0x180058793  lea     rcx, [rbp+7F0h+cwszUrl]; unsigned __int16 *
0x18005879a  mov     r9, [rbx+18h]
0x18005879e  mov     r8, rsi; unsigned __int16 *
0x1800587a1  mov     edx, r15d; unsigned __int64
0x1800587a4  mov     [rsp+8F0h+dwFlags], eax
0x1800587a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800587ad  movzx   ecx, word ptr [rbx+40h]
0x1800587b1  and     eax, 1FFF0000h
0x1800587b6  mov     r9, [rbx+18h]
0x1800587ba  mov     r8, rsi; unsigned __int16 *
0x1800587bd  mov     [rsp+8F0h+dwFlags], ecx
0x1800587c1  lea     rcx, [rbp+7F0h+cwszUrl]; unsigned __int16 *
0x1800587c8  mov     edx, r15d; unsigned __int64
0x1800587cb  cmp     eax, 70000h
0x1800587d0  jnz     short loc_1800587DC
0x1800587d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800587d7  movzx   ebx, ax
0x1800587da  jmp     short loc_1800587E3
0x1800587dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800587e1  mov     ebx, eax
0x1800587e3  test    ebx, ebx
0x1800587e5  jz      short loc_180058824
0x1800587e7  mov     r9, cs:WPP_GLOBAL_Control
0x1800587ee  lea     rcx, WPP_GLOBAL_Control
0x1800587f5  cmp     r9, rcx
0x1800587f8  jz      short loc_18005881D
0x1800587fa  test    byte ptr [r9+1Ch], 10h
0x1800587ff  jz      short loc_18005881D
0x180058801  cmp     byte ptr [r9+19h], 2
0x180058806  jb      short loc_18005881D
0x180058808  mov     rcx, [r9+10h]
0x18005880c  lea     r8, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids
0x180058813  mov     edx, 22h ; '"'
0x180058818  call    WPP_SF_
0x18005881d  mov     eax, ebx
0x18005881f  jmp     loc_180058B4A
0x180058824  lea     rdx, [rbp+7F0h+cwszUrl]
0x18005882b  mov     qword ptr [rsp+8F0h+InterfaceIndex], 0
0x180058834  lea     rcx, [rsp+8F0h+InterfaceIndex]
0x180058839  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005883e  mov     rax, qword ptr [rsp+8F0h+InterfaceIndex]
0x180058843  lea     rcx, [rsp+8F0h+InterfaceIndex]
0x180058848  test    rax, rax
0x18005884b  jnz     short loc_18005885C
0x18005884d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180058852  mov     eax, 0Eh
0x180058857  jmp     loc_180058B4A
0x18005885c  mov     qword ptr [rsp+8F0h+InterfaceIndex], 0
0x180058865  mov     [rdi+8], rax
0x180058869  mov     qword ptr [rdi+10h], 0
0x180058871  mov     dword ptr [rdi], 3
0x180058877  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005887c  jmp     loc_180058B41
0x180058881  xorps   xmm0, xmm0
0x180058884  mov     r15d, 1
0x18005888a  movups  xmmword ptr [rsp+8F0h+pAutoProxyOptions.dwFlags], xmm0
0x18005888f  movups  xmmword ptr [rsp+8F0h+pAutoProxyOptions.lpvReserved], xmm0
0x180058894  cmp     eax, r15d
0x180058897  jnz     short loc_1800588A8
0x180058899  mov     rax, [rdx+18h]
0x18005889d  mov     [rsp+8F0h+pAutoProxyOptions.lpszAutoConfigUrl], rax
0x1800588a2  lea     eax, [r15+1]
0x1800588a6  jmp     short loc_1800588BC
0x1800588a8  cmp     eax, 2
0x1800588ab  jnz     loc_180058B45
0x1800588b1  mov     eax, r15d
0x1800588b4  mov     [rsp+8F0h+pAutoProxyOptions.dwAutoDetectFlags], 3
0x1800588bc  bts     eax, 11h
0x1800588c0  mov     [rsp+8F0h+pAutoProxyOptions.fAutoLogonIfChallenged], r15d
0x1800588c5  xor     edx, edx; Val
0x1800588c7  mov     [rsp+8F0h+pAutoProxyOptions.dwFlags], eax
0x1800588cb  mov     r8d, 61Ah; Size
0x1800588d1  lea     rcx, [rbp+7F0h+var_870]; void *
0x1800588d5  call    memset_0
0x1800588da  lea     r8, [rbp+7F0h+var_870]
0x1800588de  xor     edx, edx
0x1800588e0  call    ?GetWebProbeDataForFamily@NcsiConfigData@@QEAAXW4_NLA_CONNECTIVITY_FAMILY@@PEAU_NCSI_WEB_PROBE_CONFIG@@@Z; NcsiConfigData::GetWebProbeDataForFamily(_NLA_CONNECTIVITY_FAMILY,_NCSI_WEB_PROBE_CONFIG *)
0x1800588e5  lea     r9, [rbp+7F0h+var_870]
0x1800588e9  mov     edx, 10Bh; unsigned __int64
0x1800588ee  lea     r8, aHttpS; "http://%s"
0x1800588f5  lea     rcx, [rbp+7F0h+cwszUrl]; unsigned __int16 *
0x1800588fc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180058901  mov     ebx, eax
0x180058903  test    eax, eax
0x180058905  jns     short loc_180058958
0x180058907  mov     rax, cs:WPP_GLOBAL_Control
0x18005890e  lea     rcx, WPP_GLOBAL_Control
0x180058915  cmp     rax, rcx
0x180058918  jz      short loc_18005893E
0x18005891a  test    byte ptr [rax+1Ch], 10h
0x18005891e  jz      short loc_18005893E
0x180058920  cmp     byte ptr [rax+19h], 2
0x180058924  jb      short loc_18005893E
0x180058926  mov     rcx, [rax+10h]
0x18005892a  lea     r8, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids
0x180058931  mov     edx, 23h ; '#'
0x180058936  mov     r9d, ebx
0x180058939  call    WPP_SF_d
0x18005893e  mov     eax, ebx
0x180058940  and     eax, 1FFF0000h
0x180058945  cmp     eax, 70000h
0x18005894a  jnz     loc_18005881D
0x180058950  movzx   ebx, bx
0x180058953  jmp     loc_18005881D
0x180058958  mov     rcx, cs:?c_userAgent@@3V?$basic_zstring_view@G@wil@@B; pszAgentW
0x18005895f  xor     r9d, r9d; pszProxyBypassW
0x180058962  xor     r8d, r8d; pszProxyW
0x180058965  mov     [rsp+8F0h+dwFlags], 10000000h; dwFlags
0x18005896d  mov     edx, r15d; dwAccessType
0x180058970  call    cs:__imp_WinHttpOpen
0x180058976  lea     rdx, [rsp+8F0h+InterfaceIndex]; InterfaceIndex
0x18005897b  mov     [rsp+8F0h+InterfaceIndex], 0
0x180058983  mov     rcx, rsi; InterfaceLuid
0x180058986  mov     rbx, rax
0x180058989  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18005898f  mov     esi, eax
0x180058991  test    eax, eax
0x180058993  jz      short loc_1800589E3
0x180058995  mov     r10, cs:WPP_GLOBAL_Control
0x18005899c  lea     rcx, WPP_GLOBAL_Control
0x1800589a3  cmp     r10, rcx
0x1800589a6  jz      short loc_1800589CE
0x1800589a8  test    byte ptr [r10+1Ch], 10h
0x1800589ad  jz      short loc_1800589CE
0x1800589af  cmp     byte ptr [r10+19h], 2
0x1800589b4  jb      short loc_1800589CE
0x1800589b6  mov     rcx, [r10+10h]
0x1800589ba  lea     r8, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids
0x1800589c1  mov     edx, 24h ; '$'
0x1800589c6  mov     r9d, eax
0x1800589c9  call    WPP_SF_d
0x1800589ce  test    rbx, rbx
0x1800589d1  jz      short loc_1800589DC
0x1800589d3  mov     rcx, rbx; hInternet
0x1800589d6  call    cs:__imp_WinHttpCloseHandle
0x1800589dc  mov     eax, esi
0x1800589de  jmp     loc_180058B4A
0x1800589e3  xorps   xmm0, xmm0
0x1800589e6  lea     r8, [rsp+8F0h+Buffer]; lpBuffer
0x1800589eb  movups  [rsp+8F0h+Buffer], xmm0
0x1800589f0  mov     r9d, 20h ; ' '; dwBufferLength
0x1800589f6  mov     dword ptr [rsp+8F0h+Buffer+0Ch], 3
0x1800589fe  mov     edx, 0AAh; dwOption
0x180058a03  mov     rcx, rbx; hInternet
0x180058a06  movups  [rsp+8F0h+var_888], xmm0
0x180058a0b  call    cs:__imp_WinHttpSetOption
0x180058a11  test    eax, eax
0x180058a13  jnz     short loc_180058A71
0x180058a15  call    cs:__imp_GetLastError
0x180058a1b  mov     edi, eax
0x180058a1d  mov     r10, cs:WPP_GLOBAL_Control
0x180058a24  lea     rcx, WPP_GLOBAL_Control
0x180058a2b  cmp     r10, rcx
0x180058a2e  jz      short loc_180058A5C
0x180058a30  test    byte ptr [r10+1Ch], 10h
0x180058a35  jz      short loc_180058A5C
0x180058a37  cmp     byte ptr [r10+19h], 2
0x180058a3c  jb      short loc_180058A5C
0x180058a3e  mov     edx, 25h ; '%'
0x180058a43  mov     r9d, [rsp+8F0h+InterfaceIndex]
0x180058a48  lea     r8, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids
0x180058a4f  mov     rcx, [r10+10h]
0x180058a53  mov     [rsp+8F0h+dwFlags], edi
0x180058a57  call    WPP_SF_dd
0x180058a5c  test    rbx, rbx
0x180058a5f  jz      short loc_180058A6A
0x180058a61  mov     rcx, rbx; hInternet
0x180058a64  call    cs:__imp_WinHttpCloseHandle
0x180058a6a  mov     eax, edi
0x180058a6c  jmp     loc_180058B4A
0x180058a71  mov     r9d, 4; dwBufferLength
0x180058a77  lea     r8, [rsp+8F0h+InterfaceIndex]; lpBuffer
0x180058a7c  mov     rcx, rbx; hInternet
0x180058a7f  lea     edx, [r9+6Ch]; dwOption
0x180058a83  call    cs:__imp_WinHttpSetOption
0x180058a89  test    eax, eax
0x180058a8b  jnz     short loc_180058ABD
0x180058a8d  call    cs:__imp_GetLastError
0x180058a93  mov     edi, eax
0x180058a95  mov     r10, cs:WPP_GLOBAL_Control
0x180058a9c  lea     rcx, WPP_GLOBAL_Control
0x180058aa3  cmp     r10, rcx
0x180058aa6  jz      short loc_180058A5C
0x180058aa8  test    byte ptr [r10+1Ch], 10h
0x180058aad  jz      short loc_180058A5C
0x180058aaf  cmp     byte ptr [r10+19h], 2
0x180058ab4  jb      short loc_180058A5C
0x180058ab6  mov     edx, 26h ; '&'
0x180058abb  jmp     short loc_180058A43
0x180058abd  mov     r9, rdi; pProxyInfo
0x180058ac0  lea     r8, [rsp+8F0h+pAutoProxyOptions]; pAutoProxyOptions
0x180058ac5  lea     rdx, [rbp+7F0h+cwszUrl]; lpcwszUrl
0x180058acc  mov     rcx, rbx; hSession
0x180058acf  call    cs:__imp_WinHttpGetProxyForUrl
0x180058ad5  test    eax, eax
0x180058ad7  jnz     short loc_180058B33
0x180058ad9  call    cs:__imp_GetLastError
0x180058adf  mov     edi, eax
0x180058ae1  mov     rax, cs:WPP_GLOBAL_Control
0x180058ae8  lea     rcx, WPP_GLOBAL_Control
0x180058aef  cmp     rax, rcx
0x180058af2  jz      short loc_180058B20
0x180058af4  test    byte ptr [rax+1Ch], 10h
0x180058af8  jz      short loc_180058B20
0x180058afa  cmp     byte ptr [rax+19h], 2
0x180058afe  jb      short loc_180058B20
0x180058b00  mov     rcx, [rax+10h]
0x180058b04  lea     r9, [rbp+7F0h+cwszUrl]
0x180058b0b  mov     edx, 27h ; '''
0x180058b10  mov     [rsp+8F0h+dwFlags], edi
0x180058b14  lea     r8, WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids
0x180058b1b  call    WPP_SF_SD
0x180058b20  cmp     edi, 2F94h
0x180058b26  mov     eax, 490h
0x180058b2b  cmovz   edi, eax
0x180058b2e  jmp     loc_180058A5C
0x180058b33  test    rbx, rbx
0x180058b36  jz      short loc_180058B41
0x180058b38  mov     rcx, rbx; hInternet
0x180058b3b  call    cs:__imp_WinHttpCloseHandle
0x180058b41  xor     eax, eax
0x180058b43  jmp     short loc_180058B4A
0x180058b45  mov     eax, 490h
0x180058b4a  mov     rcx, [rbp+7F0h+var_30]
0x180058b51  xor     rcx, rsp; StackCookie
0x180058b54  call    __security_check_cookie
0x180058b59  add     rsp, 8D0h
0x180058b60  pop     r15
0x180058b62  pop     rdi
0x180058b63  pop     rsi
0x180058b64  pop     rbx
0x180058b65  pop     rbp
0x180058b66  retn
```
