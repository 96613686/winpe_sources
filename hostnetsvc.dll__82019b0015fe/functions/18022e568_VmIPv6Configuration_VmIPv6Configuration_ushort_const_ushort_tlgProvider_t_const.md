# VmIPv6Configuration::VmIPv6Configuration(ushort const *,ushort,_tlgProvider_t const *)

- ea: `0x18022e568`
- end: `0x18022ebdc`
- name: `??0VmIPv6Configuration@@IEAA@PEBGGPEBU_tlgProvider_t@@@Z`
- size: `1652`
- prototype: `VmIPv6Configuration *__fastcall(VmIPv6Configuration *__hidden this, const unsigned __int16 *, unsigned __int16, const struct _tlgProvider_t *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180230118`

## callees

- `0x180001b68`
- `0x18000414c`
- `0x180005628`
- `0x18005f0c0`
- `0x18005f59c`
- `0x18005ffc4`
- `0x180061240`
- `0x1800666b4`
- `0x180067c00`
- `0x18006c530`
- `0x180167f78`
- `0x180180c8c`
- `0x18022e310`
- `0x18022e568`
- `0x18022ebe4`
- `0x18022ec7c`
- `0x1802301a4`
- `0x180230374`
- `0x1802304a4`
- `0x180230624`
- `0x1802307dc`
- `0x1802b7010`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18022ea0f`
- `WS2_32!__imp_htonl` at `0x18022ea1c`
- `WS2_32!__imp_htonl` at `0x18022ea0f`
- `WS2_32!__imp_htonl` at `0x18022ea1c`
- `WS2_32!__imp_htons` at `0x18022e938`
- `WS2_32!__imp_htons` at `0x18022e946`
- `WS2_32!__imp_htons` at `0x18022e938`
- `WS2_32!__imp_htons` at `0x18022e946`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022e735`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022e735`
- `ntdll!RtlIpv6StringToAddressW` at `0x18022e929`
- `ntdll!RtlIpv6StringToAddressW` at `0x18022e929`
- `ntdll!RtlIpv4StringToAddressW` at `0x18022e9fc`
- `ntdll!RtlIpv4StringToAddressW` at `0x18022e9fc`
- `OLEAUT32!__imp_SysAllocString` at `0x18022e6fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18022e6fa`
- `OLEAUT32!__imp_VariantClear` at `0x18022eb5a`
- `OLEAUT32!__imp_VariantClear` at `0x18022eb5a`

## string_xrefs

- `0x18022ebca`: `onecore\vm\common\vml\VmCom.h`
- `0x18022eb8f`: `onecore\vm\common\netmgmtwmi\vmipv6configuration.cpp`
- `0x18022ea51`: `IsLinkLocalAddress`
- `0x18022e980`: `!IsLinkLocalAddress`
- `0x18022ebb5`: `onecore\vm\common\vml\VmVariant.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
VmIPv6Configuration *__fastcall VmIPv6Configuration::VmIPv6Configuration(
        VmIPv6Configuration *this,
        const unsigned __int16 *a2,
        __int16 a3,
        const struct _tlgProvider_t *a4)
{
  const unsigned __int16 *v8; // rdx
  Vml::VmSharableObject *v9; // rax
  const struct type_info *v10; // rdx
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // r8
  _DWORD *v13; // rcx
  HRESULT v14; // eax
  int v15; // eax
  int v16; // r8d
  int v17; // r9d
  _DWORD *v18; // rcx
  const wchar_t *v19; // rdx
  __int128 *v20; // rax
  unsigned int v21; // esi
  __int64 i; // rdx
  const WCHAR *v23; // rcx
  int v24; // r8d
  int v25; // r9d
  u_short v26; // bx
  _DWORD *v27; // rcx
  const WCHAR *v28; // rax
  __int64 *v29; // r8
  char *v30; // rdx
  __int64 v31; // rcx
  u_long v32; // ebx
  _DWORD *v33; // rcx
  const WCHAR *v34; // rax
  int v35; // r8d
  int v36; // r9d
  _DWORD *v37; // rcx
  unsigned int v39; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+28h] [rbp-D8h]
  int v44; // [rsp+30h] [rbp-D0h]
  __int64 v45; // [rsp+38h] [rbp-C8h]
  __int64 v47; // [rsp+40h] [rbp-C0h]
  PCWSTR Terminator; // [rsp+48h] [rbp-B8h] BYREF
  struct in6_addr Addr; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v50; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR S[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v52; // [rsp+78h] [rbp-88h]
  unsigned __int64 v53; // [rsp+80h] [rbp-80h]
  __int128 v54; // [rsp+88h] [rbp-78h] BYREF
  __int64 v55; // [rsp+98h] [rbp-68h]
  __int128 Src; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v57; // [rsp+B0h] [rbp-50h]
  __int64 v58; // [rsp+B8h] [rbp-48h]
  __int128 v59; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v61; // [rsp+D8h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v63[32]; // [rsp+100h] [rbp+0h] BYREF
  const char *v64; // [rsp+120h] [rbp+20h]
  __int64 v65; // [rsp+128h] [rbp+28h]
  PCWSTR *p_Terminator; // [rsp+130h] [rbp+30h]
  __int64 v67; // [rsp+138h] [rbp+38h]
  struct in6_addr *p_Addr; // [rsp+140h] [rbp+40h]
  __int64 v69; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  Vml::VmSharableObject::VmSharableObject(this);
  *(_QWORD *)this = &VmIPv6Configuration::`vftable';
  Terminator = (PCWSTR)operator new(0x68u);
  memset_0((void *)Terminator, 0, 0x68u);
  v9 = VmWbemCore::VmWbemCore((VmWbemCore *)Terminator, v8);
  *((_QWORD *)this + 10) = v9;
  if ( v9 )
    Vml::VmSharableObject::AddUserInternal(v9, v10);
  *(_OWORD *)((char *)this + 88) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  std::wstring::_Construct<1,unsigned short const *>((char **)this + 11, a2, v12);
  *((_WORD *)this + 62) = a3;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  if ( !a4 )
    a4 = (const struct _tlgProvider_t *)&dword_1803840A8;
  *((_QWORD *)this + 23) = a4;
  *((_DWORD *)this + 30) = VmIPv6Configuration::GetInterfaceIndex(this, a2);
  v13 = (_DWORD *)*((_QWORD *)this + 23);
  if ( *v13 > 4u )
  {
    *(_DWORD *)Addr.u.Byte = *((_DWORD *)this + 30);
    Terminator = (PCWSTR)this;
    p_Addr = &Addr;
    v69 = 4;
    p_Terminator = &Terminator;
    v67 = 8;
    v64 = "GetInterfaceIndex";
    v65 = 18;
    tlgWriteTransfer_EventWriteTransfer(v13, &unk_18034353C, 0, 0, 5, v63);
  }
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"All");
  if ( !pvarg.llVal )
  {
    v39 = wil::verify_hresult<long>(2147942414LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3CA,
      (unsigned int)"onecore\\vm\\common\\vml\\VmVariant.h",
      (const char *)v39,
      ppv);
  }
  v50 = 0;
  v14 = CoCreateInstance(&CLSID_WbemContext, 0, 1u, &GUID_44aca674_e8fc_11d0_a07c_00c04fb68820, &v50);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x95F,
      (unsigned int)"onecore\\vm\\common\\vml\\VmCom.h",
      (const char *)(unsigned int)v14,
      ppva);
  v15 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, VARIANTARG *))(*(_QWORD *)v50 + 64LL))(
          v50,
          L"PolicyStore",
          0,
          &pvarg);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\vm\\common\\netmgmtwmi\\vmipv6configuration.cpp",
      (const char *)(unsigned int)v15,
      ppva);
  Src = 0;
  v57 = 0;
  v58 = 7;
  LOWORD(Src) = 0;
  Vml::FormatString(
    &Src,
    (wchar_t *)L"SELECT * FROM MSFT_NetIPAddress WHERE InterfaceIndex = %u AND AddressFamily = %u AND (PrefixOrigin = %u O"
                "R SuffixOrigin = %u) AND Type = %u AND SkipAsSource = %u");
  VmIPv6Configuration::GetWmiInstances(this, &Src, (char *)this + 128, v50, 1, 1, 1, 0, this);
  v18 = (_DWORD *)*((_QWORD *)this + 23);
  if ( *v18 > 4u )
  {
    Terminator = (PCWSTR)((__int64)(*((_QWORD *)this + 17) - *((_QWORD *)this + 16)) >> 3);
    *(_QWORD *)Addr.u.Byte = "Static Addresses";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v18,
      (unsigned int)&unk_180343499,
      v16,
      v17,
      (__int64)&Addr,
      (__int64)&Terminator);
  }
  v19 = L"0.0.0.0/0";
  if ( *((_WORD *)this + 62) != 2 )
    v19 = L"::/0";
  v59 = 0;
  v60 = 0;
  v61 = 0;
  do
    ++v11;
  while ( v19[v11] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v59, v19, v11);
  v20 = &v59;
  if ( v61 > 7 )
    LODWORD(v20) = v59;
  ppvb = (int)v20;
  Vml::FormatString(
    &Src,
    (wchar_t *)L"SELECT * FROM MSFT_NetRoute WHERE InterfaceIndex = %u AND AddressFamily = %u AND DestinationPrefix = '%ws'");
  v54 = 0;
  v55 = 0;
  VmIPv6Configuration::GetWmiInstances(this, &Src, &v54, v50, ppvb, v43, v44, v45, v47);
  v21 = 0;
  for ( i = v54; v21 < (unsigned __int64)((__int64)(*((_QWORD *)&v54 + 1) - v54) >> 3); i = v54 )
  {
    *(_OWORD *)S = 0;
    v52 = 0;
    v53 = 7;
    LOWORD(S[0]) = 0;
    VmWbemCore::GetProperty(*((VmWbemCore **)this + 10), *(struct IWbemClassObject **)(i + 8LL * v21));
    v23 = (const WCHAR *)S;
    if ( v53 > 7 )
      v23 = S[0];
    Terminator = 0;
    if ( *((_WORD *)this + 62) == 23 )
    {
      Addr = 0;
      if ( RtlIpv6StringToAddressW(v23, &Terminator, &Addr) >= 0 )
      {
        v26 = htons(0xFE80u);
        if ( (htons(0xFFC0u) & Addr.u.Word[0]) == v26 )
          goto LABEL_36;
      }
    }
    else
    {
      *(_DWORD *)Addr.u.Byte = 0;
      if ( RtlIpv4StringToAddressW(v23, 1u, &Terminator, (struct in_addr *)&Addr) >= 0 )
      {
        v32 = htonl(0xA9FE0000);
        if ( (*(_DWORD *)Addr.u.Byte & htonl(0xFFFF0000)) == v32 )
        {
LABEL_36:
          v33 = (_DWORD *)*((_QWORD *)this + 23);
          if ( *v33 > 4u )
          {
            v34 = (const WCHAR *)S;
            if ( v53 > 7 )
              v34 = S[0];
            Terminator = v34;
            *(_QWORD *)Addr.u.Byte = "IsLinkLocalAddress";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v33,
              (unsigned int)&unk_1803433F1,
              v24,
              v25,
              (__int64)&Addr,
              (__int64)&Terminator);
          }
          goto LABEL_41;
        }
      }
    }
    v27 = (_DWORD *)*((_QWORD *)this + 23);
    if ( *v27 > 4u )
    {
      v28 = (const WCHAR *)S;
      if ( v53 > 7 )
        v28 = S[0];
      Terminator = v28;
      *(_QWORD *)Addr.u.Byte = "!IsLinkLocalAddress";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v27,
        (unsigned int)&unk_1803434EB,
        v24,
        v25,
        (__int64)&Addr,
        (__int64)&Terminator);
    }
    v29 = (__int64 *)(v54 + 8LL * v21);
    v30 = (char *)*((_QWORD *)this + 20);
    if ( v30 == *((char **)this + 21) )
    {
      std::vector<Vml::VmComPtr<IWbemClassObject>>::_Emplace_reallocate<Vml::VmComPtr<IWbemClassObject> const &>(
        (char **)this + 19,
        v30,
        v29);
    }
    else
    {
      v31 = *v29;
      *(_QWORD *)v30 = *v29;
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      *((_QWORD *)this + 20) += 8LL;
    }
LABEL_41:
    std::wstring::~wstring(S);
    ++v21;
  }
  Vml::FormatString(
    &Src,
    (wchar_t *)L"SELECT * FROM MSFT_DNSClientServerAddress WHERE InterfaceIndex = %u AND AddressFamily = %u");
  VmIPv6Configuration::TryGetOneWmiInstance(this, &Src, (char *)this + 176);
  v37 = (_DWORD *)*((_QWORD *)this + 23);
  if ( *v37 > 4u )
  {
    Terminator = (PCWSTR)*((_QWORD *)this + 22);
    *(_QWORD *)Addr.u.Byte = "DNS Server Addresses";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v37,
      (unsigned int)&unk_180343442,
      v35,
      v36,
      (__int64)&Addr,
      (__int64)&Terminator);
  }
  std::vector<Vml::VmComPtr<IWbemClassObject>>::~vector<Vml::VmComPtr<IWbemClassObject>>(&v54);
  std::wstring::~wstring(&v59);
  std::wstring::~wstring(&Src);
  if ( v50 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v50 + 16LL))(v50);
  VariantClear(&pvarg);
  return this;
}

```

## disassembly

```asm
0x18022e568  mov     [rsp-8+arg_10], rbx
0x18022e56d  mov     [rsp-8+arg_18], rsi
0x18022e572  push    rbp
0x18022e573  push    rdi
0x18022e574  push    r12
0x18022e576  push    r14
0x18022e578  push    r15
0x18022e57a  lea     rbp, [rsp-60h]
0x18022e57f  sub     rsp, 160h
0x18022e586  mov     rax, cs:__security_cookie
0x18022e58d  xor     rax, rsp
0x18022e590  mov     [rbp+80h+var_30], rax
0x18022e594  mov     r14, r9
0x18022e597  movzx   r15d, r8w
0x18022e59b  mov     rsi, rdx
0x18022e59e  mov     rdi, rcx
0x18022e5a1  mov     [rsp+180h+var_140], rcx
0x18022e5a6  call    ??0VmSharableObject@Vml@@IEAA@XZ; Vml::VmSharableObject::VmSharableObject(void)
0x18022e5ab  nop
0x18022e5ac  lea     rax, ??_7VmIPv6Configuration@@6B@; const VmIPv6Configuration::`vftable'
0x18022e5b3  mov     [rdi], rax
0x18022e5b6  mov     r12d, 68h ; 'h'
0x18022e5bc  mov     ecx, r12d; Size
0x18022e5bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022e5c4  mov     rbx, rax
0x18022e5c7  mov     [rsp+180h+Terminator], rax
0x18022e5cc  mov     r8d, r12d; Size
0x18022e5cf  xor     edx, edx; Val
0x18022e5d1  mov     rcx, rax; void *
0x18022e5d4  call    memset_0
0x18022e5d9  mov     rcx, rbx; this
0x18022e5dc  call    ??0VmWbemCore@@QEAA@PEBG@Z; VmWbemCore::VmWbemCore(ushort const *)
0x18022e5e1  nop
0x18022e5e2  mov     [rdi+50h], rax
0x18022e5e6  xor     r12d, r12d
0x18022e5e9  test    rax, rax
0x18022e5ec  jz      short loc_18022E5F7
0x18022e5ee  mov     rcx, rax; this
0x18022e5f1  call    ?AddUserInternal@VmSharableObject@Vml@@AEAAKAEBVtype_info@@@Z; Vml::VmSharableObject::AddUserInternal(type_info const &)
0x18022e5f6  nop
0x18022e5f7  lea     rcx, [rdi+58h]
0x18022e5fb  xorps   xmm0, xmm0
0x18022e5fe  movups  xmmword ptr [rcx], xmm0
0x18022e601  mov     [rcx+10h], r12
0x18022e605  mov     [rcx+18h], r12
0x18022e609  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18022e60d  mov     r8, rbx
0x18022e610  inc     r8
0x18022e613  cmp     [rsi+r8*2], r12w
0x18022e618  jnz     short loc_18022E610
0x18022e61a  mov     rdx, rsi
0x18022e61d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18022e622  nop
0x18022e623  mov     [rdi+7Ch], r15w
0x18022e628  mov     [rdi+80h], r12
0x18022e62f  mov     [rdi+88h], r12
0x18022e636  mov     [rdi+90h], r12
0x18022e63d  mov     [rdi+98h], r12
0x18022e644  mov     [rdi+0A0h], r12
0x18022e64b  mov     [rdi+0A8h], r12
0x18022e652  mov     [rdi+0B0h], r12
0x18022e659  lea     rax, dword_1803840A8
0x18022e660  test    r14, r14
0x18022e663  cmovz   r14, rax
0x18022e667  mov     [rdi+0B8h], r14
0x18022e66e  mov     rdx, rsi; unsigned __int16 *
0x18022e671  mov     rcx, rdi; this
0x18022e674  call    ?GetInterfaceIndex@VmIPv6Configuration@@AEAAIPEBG@Z; VmIPv6Configuration::GetInterfaceIndex(ushort const *)
0x18022e679  mov     [rdi+78h], eax
0x18022e67c  mov     rcx, [rdi+0B8h]
0x18022e683  mov     eax, [rcx]
0x18022e685  mov     esi, 8
0x18022e68a  cmp     eax, 4
0x18022e68d  jbe     short loc_18022E6EF
0x18022e68f  mov     eax, [rdi+78h]
0x18022e692  mov     dword ptr [rsp+180h+Addr.u], eax
0x18022e696  mov     [rsp+180h+Terminator], rdi
0x18022e69b  lea     rax, [rsp+180h+Addr]
0x18022e6a0  mov     [rbp+80h+var_40], rax
0x18022e6a4  mov     [rbp+80h+var_38], 4
0x18022e6ac  lea     rax, [rsp+180h+Terminator]
0x18022e6b1  mov     [rbp+80h+var_50], rax
0x18022e6b5  mov     [rbp+80h+var_48], rsi
0x18022e6b9  lea     rax, aGetinterfacein; "GetInterfaceIndex"
0x18022e6c0  mov     [rbp+80h+var_60], rax
0x18022e6c4  mov     [rbp+80h+var_58], 12h
0x18022e6cc  lea     rax, [rbp+80h+var_80]
0x18022e6d0  mov     [rsp+180h+var_158], rax
0x18022e6d5  mov     dword ptr [rsp+180h+ppv], 5; int
0x18022e6dd  xor     r9d, r9d
0x18022e6e0  xor     r8d, r8d
0x18022e6e3  lea     rdx, unk_18034353C
0x18022e6ea  call    _tlgWriteTransfer_EventWriteTransfer
0x18022e6ef  mov     word ptr [rbp+80h+pvarg], si
0x18022e6f3  lea     rcx, aAll_0; "All"
0x18022e6fa  call    cs:__imp_SysAllocString
0x18022e700  mov     qword ptr [rbp+80h+pvarg+8], rax
0x18022e704  test    rax, rax
0x18022e707  jz      loc_18022EBA1
0x18022e70d  mov     [rsp+180h+var_120], r12
0x18022e712  lea     rax, [rsp+180h+var_120]
0x18022e717  mov     [rsp+180h+ppv], rax; int
0x18022e71c  lea     r9, _GUID_44aca674_e8fc_11d0_a07c_00c04fb68820; riid
0x18022e723  mov     r15d, 1
0x18022e729  mov     r8d, r15d; dwClsContext
0x18022e72c  xor     edx, edx; pUnkOuter
0x18022e72e  lea     rcx, CLSID_WbemContext; rclsid
0x18022e735  call    cs:__imp_CoCreateInstance
0x18022e73b  mov     rcx, [rbp+88h]; this
0x18022e742  test    eax, eax
0x18022e744  js      loc_18022EBC7
0x18022e74a  mov     rcx, [rsp+180h+var_120]
0x18022e74f  mov     rax, [rcx]
0x18022e752  lea     r9, [rbp+80h+pvarg]
0x18022e756  xor     r8d, r8d
0x18022e759  lea     rdx, aPolicystore; "PolicyStore"
0x18022e760  mov     rax, [rax+40h]
0x18022e764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022e769  mov     rcx, [rbp+88h]; this
0x18022e770  test    eax, eax
0x18022e772  js      loc_18022EB8C
0x18022e778  xorps   xmm0, xmm0
0x18022e77b  movups  [rbp+80h+Src], xmm0
0x18022e77f  mov     [rbp+80h+var_D0], r12
0x18022e783  mov     [rbp+80h+var_C8], 7
0x18022e78b  mov     word ptr [rbp+80h+Src], r12w
0x18022e790  movzx   r9d, word ptr [rdi+7Ch]
0x18022e795  mov     [rsp+180h+var_148], r12
0x18022e79a  mov     [rsp+180h+var_150], r15d
0x18022e79f  mov     dword ptr [rsp+180h+var_158], r15d
0x18022e7a4  mov     dword ptr [rsp+180h+ppv], r15d
0x18022e7a9  mov     r8d, [rdi+78h]
0x18022e7ad  lea     rdx, aSelectFromMsft; "SELECT * FROM MSFT_NetIPAddress WHERE I"...
0x18022e7b4  lea     rcx, [rbp+80h+Src]; Src
0x18022e7b8  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x18022e7bd  lea     rsi, [rdi+80h]
0x18022e7c4  mov     r9, [rsp+180h+var_120]
0x18022e7c9  mov     r8, rsi
0x18022e7cc  lea     rdx, [rbp+80h+Src]
0x18022e7d0  mov     rcx, rdi
0x18022e7d3  call    ?GetWmiInstances@VmIPv6Configuration@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$VmComPtr@UIWbemClassObject@@@Vml@@V?$allocator@V?$VmComPtr@UIWbemClassObject@@@Vml@@@std@@@3@PEAUIWbemContext@@@Z; VmIPv6Configuration::GetWmiInstances(std::wstring const &,std::vector<Vml::VmComPtr<IWbemClassObject>> &,IWbemContext *)
0x18022e7d8  mov     rcx, [rdi+0B8h]
0x18022e7df  mov     eax, [rcx]
0x18022e7e1  cmp     eax, 4
0x18022e7e4  jbe     short loc_18022E822
0x18022e7e6  mov     rax, [rsi+8]
0x18022e7ea  sub     rax, [rsi]
0x18022e7ed  sar     rax, 3
0x18022e7f1  mov     [rsp+180h+Terminator], rax
0x18022e7f6  lea     rax, aStaticAddresse; "Static Addresses"
0x18022e7fd  mov     qword ptr [rsp+180h+Addr.u], rax
0x18022e802  lea     rax, [rsp+180h+Terminator]
0x18022e807  mov     [rsp+180h+var_158], rax
0x18022e80c  lea     rax, [rsp+180h+Addr]
0x18022e811  mov     [rsp+180h+ppv], rax
0x18022e816  lea     rdx, unk_180343499
0x18022e81d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18022e822  lea     rax, a0; "::/0"
0x18022e829  lea     rdx, a00000; "0.0.0.0/0"
0x18022e830  cmp     word ptr [rdi+7Ch], 2
0x18022e835  cmovnz  rdx, rax
0x18022e839  xorps   xmm0, xmm0
0x18022e83c  movups  [rbp+80h+var_C0], xmm0
0x18022e840  mov     [rbp+80h+var_B0], r12
0x18022e844  mov     [rbp+80h+var_A8], r12
0x18022e848  inc     rbx
0x18022e84b  cmp     [rdx+rbx*2], r12w
0x18022e850  jnz     short loc_18022E848
0x18022e852  mov     r8, rbx
0x18022e855  lea     rcx, [rbp+80h+var_C0]
0x18022e859  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18022e85e  nop
0x18022e85f  lea     rax, [rbp+80h+var_C0]
0x18022e863  cmp     [rbp+80h+var_A8], 7
0x18022e868  cmova   rax, qword ptr [rbp+80h+var_C0]
0x18022e86d  movzx   r9d, word ptr [rdi+7Ch]
0x18022e872  mov     [rsp+180h+ppv], rax
0x18022e877  mov     r8d, [rdi+78h]
0x18022e87b  lea     rdx, aSelectFromMsft_2; "SELECT * FROM MSFT_NetRoute WHERE Inter"...
0x18022e882  lea     rcx, [rbp+80h+Src]; Src
0x18022e886  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x18022e88b  xorps   xmm1, xmm1
0x18022e88e  movdqu  [rbp+80h+var_F8], xmm1
0x18022e893  mov     [rbp+80h+var_E8], r12
0x18022e897  mov     r9, [rsp+180h+var_120]
0x18022e89c  lea     r8, [rbp+80h+var_F8]
0x18022e8a0  lea     rdx, [rbp+80h+Src]
0x18022e8a4  mov     rcx, rdi
0x18022e8a7  call    ?GetWmiInstances@VmIPv6Configuration@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$VmComPtr@UIWbemClassObject@@@Vml@@V?$allocator@V?$VmComPtr@UIWbemClassObject@@@Vml@@@std@@@3@PEAUIWbemContext@@@Z; VmIPv6Configuration::GetWmiInstances(std::wstring const &,std::vector<Vml::VmComPtr<IWbemClassObject>> &,IWbemContext *)
0x18022e8ac  mov     esi, r12d
0x18022e8af  mov     rax, qword ptr [rbp+80h+var_F8+8]
0x18022e8b3  mov     rdx, qword ptr [rbp+80h+var_F8]
0x18022e8b7  sub     rax, rdx
0x18022e8ba  sar     rax, 3
0x18022e8be  test    rax, rax
0x18022e8c1  jz      loc_18022EAAF
0x18022e8c7  xorps   xmm0, xmm0
0x18022e8ca  movups  xmmword ptr [rsp+180h+S], xmm0
0x18022e8cf  mov     [rsp+180h+var_108], r12
0x18022e8d4  mov     [rbp+80h+var_100], 7
0x18022e8dc  mov     word ptr [rsp+180h+S], r12w
0x18022e8e2  mov     r14d, esi
0x18022e8e5  lea     r9, [rsp+180h+S]
0x18022e8ea  mov     rdx, [rdx+r14*8]
0x18022e8ee  mov     rcx, [rdi+50h]
0x18022e8f2  call    ?GetProperty@VmWbemCore@@QEAAXPEAUIWbemClassObject@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; VmWbemCore::GetProperty(IWbemClassObject *,ushort const *,std::wstring &)
0x18022e8f7  lea     rcx, [rsp+180h+S]
0x18022e8fc  cmp     [rbp+80h+var_100], 7
0x18022e901  cmova   rcx, [rsp+180h+S]; S
0x18022e907  mov     [rsp+180h+Terminator], r12
0x18022e90c  cmp     word ptr [rdi+7Ch], 17h
0x18022e911  jnz     loc_18022E9EA
0x18022e917  xorps   xmm0, xmm0
0x18022e91a  movups  xmmword ptr [rsp+180h+Addr.u], xmm0
0x18022e91f  lea     r8, [rsp+180h+Addr]; Addr
0x18022e924  lea     rdx, [rsp+180h+Terminator]; Terminator
0x18022e929  call    cs:__imp_RtlIpv6StringToAddressW
0x18022e92f  test    eax, eax
0x18022e931  js      short loc_18022E95D
0x18022e933  mov     ecx, 0FE80h; hostshort
0x18022e938  call    cs:__imp_htons
0x18022e93e  movzx   ebx, ax
0x18022e941  mov     ecx, 0FFC0h; hostshort
0x18022e946  call    cs:__imp_htons
0x18022e94c  movzx   ecx, word ptr [rsp+180h+Addr.u]
0x18022e951  and     cx, ax
0x18022e954  cmp     cx, bx
0x18022e957  jz      loc_18022EA2E
0x18022e95d  mov     rcx, [rdi+0B8h]
0x18022e964  mov     eax, [rcx]
0x18022e966  cmp     eax, 4
0x18022e969  jbe     short loc_18022E9AC
0x18022e96b  lea     rax, [rsp+180h+S]
0x18022e970  cmp     [rbp+80h+var_100], 7
0x18022e975  cmova   rax, [rsp+180h+S]
0x18022e97b  mov     [rsp+180h+Terminator], rax
0x18022e980  lea     rax, aIslinklocaladd; "!IsLinkLocalAddress"
0x18022e987  mov     qword ptr [rsp+180h+Addr.u], rax
0x18022e98c  lea     rax, [rsp+180h+Terminator]
0x18022e991  mov     [rsp+180h+var_158], rax
0x18022e996  lea     rax, [rsp+180h+Addr]
0x18022e99b  mov     [rsp+180h+ppv], rax
0x18022e9a0  lea     rdx, unk_1803434EB
0x18022e9a7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18022e9ac  lea     rbx, [rdi+98h]
0x18022e9b3  mov     rax, qword ptr [rbp+80h+var_F8]
0x18022e9b7  lea     r8, [rax+r14*8]
0x18022e9bb  mov     rdx, [rbx+8]
0x18022e9bf  cmp     rdx, [rbx+10h]
0x18022e9c3  jz      loc_18022EA7F
0x18022e9c9  mov     rcx, [r8]
0x18022e9cc  mov     [rdx], rcx
0x18022e9cf  test    rcx, rcx
0x18022e9d2  jz      short loc_18022E9E0
0x18022e9d4  mov     rax, [rcx]
0x18022e9d7  mov     rax, [rax+8]
0x18022e9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022e9e0  add     qword ptr [rbx+8], 8
0x18022e9e5  jmp     loc_18022EA88
0x18022e9ea  mov     dword ptr [rsp+180h+Addr.u], r12d
0x18022e9ef  lea     r9, [rsp+180h+Addr]; Addr
0x18022e9f4  lea     r8, [rsp+180h+Terminator]; Terminator
0x18022e9f9  mov     dl, r15b; Strict
0x18022e9fc  call    cs:__imp_RtlIpv4StringToAddressW
0x18022ea02  test    eax, eax
0x18022ea04  js      loc_18022E95D
0x18022ea0a  mov     ecx, 0A9FE0000h; hostlong
0x18022ea0f  call    cs:__imp_htonl
0x18022ea15  mov     ebx, eax
0x18022ea17  mov     ecx, 0FFFF0000h; hostlong
0x18022ea1c  call    cs:__imp_htonl
0x18022ea22  and     eax, dword ptr [rsp+180h+Addr.u]
0x18022ea26  cmp     eax, ebx
0x18022ea28  jnz     loc_18022E95D
0x18022ea2e  mov     rcx, [rdi+0B8h]
0x18022ea35  mov     eax, [rcx]
0x18022ea37  cmp     eax, 4
0x18022ea3a  jbe     short loc_18022EA88
0x18022ea3c  lea     rax, [rsp+180h+S]
0x18022ea41  cmp     [rbp+80h+var_100], 7
0x18022ea46  cmova   rax, [rsp+180h+S]
0x18022ea4c  mov     [rsp+180h+Terminator], rax
0x18022ea51  lea     rax, aIslinklocaladd_0; "IsLinkLocalAddress"
0x18022ea58  mov     qword ptr [rsp+180h+Addr.u], rax
0x18022ea5d  lea     rax, [rsp+180h+Terminator]
0x18022ea62  mov     [rsp+180h+var_158], rax
0x18022ea67  lea     rax, [rsp+180h+Addr]
0x18022ea6c  mov     [rsp+180h+ppv], rax
0x18022ea71  lea     rdx, unk_1803433F1
0x18022ea78  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18022ea7d  jmp     short loc_18022EA88
0x18022ea7f  mov     rcx, rbx
0x18022ea82  call    ??$_Emplace_reallocate@AEBV?$VmComPtr@UIWbemClassObject@@@Vml@@@?$vector@V?$VmComPtr@UIWbemClassObject@@@Vml@@V?$allocator@V?$VmComPtr@UIWbemClassObject@@@Vml@@@std@@@std@@AEAAPEAV?$VmComPtr@UIWbemClassObject@@@Vml@@QEAV23@AEBV23@@Z; std::vector<Vml::VmComPtr<IWbemClassObject>>::_Emplace_reallocate<Vml::VmComPtr<IWbemClassObject> const &>(Vml::VmComPtr<IWbemClassObject> * const,Vml::VmComPtr<IWbemClassObject> const &)
0x18022ea87  nop
0x18022ea88  lea     rcx, [rsp+180h+S]; void *
0x18022ea8d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18022ea92  add     esi, r15d
0x18022ea95  mov     rcx, qword ptr [rbp+80h+var_F8+8]
0x18022ea99  mov     rdx, qword ptr [rbp+80h+var_F8]
0x18022ea9d  sub     rcx, rdx
  ... truncated ...
```
