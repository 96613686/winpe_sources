# LogRouteInformation(void)

- ea: `0x180039f70`
- end: `0x18003a20a`
- name: `?LogRouteInformation@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x18002a3e4`
- `0x180039f70`
- `0x18003a210`
- `0x18003b464`

## import_xrefs

- `IPHLPAPI!FreeMibTable` at `0x18003a1e0`
- `IPHLPAPI!FreeMibTable` at `0x18003a1e0`
- `IPHLPAPI!GetIpForwardTable2` at `0x180039fb1`
- `IPHLPAPI!GetIpForwardTable2` at `0x180039fb1`

## string_xrefs

- `0x18003a180`: `\n >>>>>> GetIpForwardTable2 Information <<<<<<\n  InterfaceLuid: 0x%I64x\n  InterfaceIndex: %u\n  DestinationPrefix: %ws/%u\n  NextHop: %ws\n  SitePrefixLength: %u\n  ValidLifetime: %u\n  PreferredLifetime: %u\n  Metric: %u\n  Protocol: %ws\n  Loopback: %ws\n  AutoconfigureAddress: %ws\n  Publish: %ws\n  Immortal: %ws\n  Age: %u\n  Origin: %ws\n`
- `0x180039fc5`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LogRouteInformation(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int IpForwardTable2; // eax
  PMIB_IPFORWARD_TABLE2 v3; // rcx
  MIB_IPFORWARD_ROW2 *v4; // rdi
  NL_ROUTE_ORIGIN Origin; // ecx
  __int32 v6; // ecx
  __int32 v7; // ecx
  int v8; // ecx
  const wchar_t *v9; // rax
  const wchar_t *v10; // rax
  const wchar_t *v11; // rax
  const wchar_t *v12; // rax
  const wchar_t *v13; // rax
  const wchar_t *v14; // rsi
  ULONG Metric; // r14d
  ULONG PreferredLifetime; // r15d
  ULONG ValidLifetime; // r12d
  int SitePrefixLength; // r13d
  __int64 v19; // rbx
  int PrefixLength; // edi
  __int64 v21; // rax
  unsigned int v23; // [rsp+20h] [rbp-F0h]
  __int64 v24; // [rsp+28h] [rbp-E8h]
  __int64 v25; // [rsp+38h] [rbp-D8h]
  __int64 v26; // [rsp+40h] [rbp-D0h]
  __int64 v27; // [rsp+48h] [rbp-C8h]
  __int64 v28; // [rsp+50h] [rbp-C0h]
  __int64 v29; // [rsp+80h] [rbp-90h]
  const wchar_t *v30; // [rsp+90h] [rbp-80h]
  ULONG Age; // [rsp+9Ch] [rbp-74h]
  MIB_IPFORWARD_ROW2 *v32; // [rsp+A0h] [rbp-70h]
  const wchar_t *v33; // [rsp+A8h] [rbp-68h]
  const wchar_t *v34; // [rsp+B0h] [rbp-60h]
  const wchar_t *v35; // [rsp+B8h] [rbp-58h]
  const wchar_t *v36; // [rsp+C0h] [rbp-50h]
  struct _MIB_IPFORWARD_TABLE2 *v38; // [rsp+D0h] [rbp-40h]
  _BYTE v39[32]; // [rsp+F0h] [rbp-20h] BYREF
  _BYTE v40[32]; // [rsp+110h] [rbp+0h] BYREF
  _BYTE v41[32]; // [rsp+130h] [rbp+20h] BYREF
  PMIB_IPFORWARD_TABLE2 Table; // [rsp+150h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+98h]

  v1 = a1;
  Table = 0;
  IpForwardTable2 = GetIpForwardTable2(0, &Table);
  if ( IpForwardTable2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x481,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
      (const char *)IpForwardTable2,
      v23);
  std::wstring::wstring(v1);
  v3 = Table;
  v4 = Table->Table;
  v32 = Table->Table;
  v38 = (struct _MIB_IPFORWARD_TABLE2 *)&Table->Table[Table->NumEntries];
  if ( Table->Table != (MIB_IPFORWARD_ROW2 *)v38 )
  {
    do
    {
      Origin = v4->Origin;
      if ( Origin )
      {
        v6 = Origin - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            v8 = v7 - 1;
            if ( v8 )
            {
              if ( v8 == 1 )
                v9 = L"Nlro6to4";
              else
                v9 = L"(unknown NL_ROUTE_ORIGIN)";
            }
            else
            {
              v9 = L"NlroRouterAdvertisement";
            }
          }
          else
          {
            v9 = L"NlroDHCP";
          }
        }
        else
        {
          v9 = L"NlroWellKnown";
        }
      }
      else
      {
        v9 = L"NlroManual";
      }
      v30 = v9;
      Age = v4->Age;
      v10 = L"true";
      if ( !v4->Immortal )
        v10 = L"false";
      v33 = v10;
      v11 = L"true";
      if ( !v4->Publish )
        v11 = L"false";
      v34 = v11;
      v12 = L"true";
      if ( !v4->AutoconfigureAddress )
        v12 = L"false";
      v35 = v12;
      v13 = L"true";
      if ( !v4->Loopback )
        v13 = L"false";
      v36 = v13;
      v14 = ToString(&v4->Protocol);
      Metric = v4->Metric;
      PreferredLifetime = v4->PreferredLifetime;
      ValidLifetime = v4->ValidLifetime;
      SitePrefixLength = v4->SitePrefixLength;
      ToString(v41, &v4->NextHop);
      v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      PrefixLength = v4->DestinationPrefix.PrefixLength;
      ToString(v40, &v32->DestinationPrefix);
      v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      LODWORD(v29) = Age;
      LODWORD(v28) = Metric;
      LODWORD(v27) = PreferredLifetime;
      LODWORD(v26) = ValidLifetime;
      LODWORD(v25) = SitePrefixLength;
      LODWORD(v24) = PrefixLength;
      wil::str_printf<std::wstring>(
        (__int64)v39,
        (__int64)L"\n"
                  " >>>>>> GetIpForwardTable2 Information <<<<<<\n"
                  "  InterfaceLuid: 0x%I64x\n"
                  "  InterfaceIndex: %u\n"
                  "  DestinationPrefix: %ws/%u\n"
                  "  NextHop: %ws\n"
                  "  SitePrefixLength: %u\n"
                  "  ValidLifetime: %u\n"
                  "  PreferredLifetime: %u\n"
                  "  Metric: %u\n"
                  "  Protocol: %ws\n"
                  "  Loopback: %ws\n"
                  "  AutoconfigureAddress: %ws\n"
                  "  Publish: %ws\n"
                  "  Immortal: %ws\n"
                  "  Age: %u\n"
                  "  Origin: %ws\n",
        v32->InterfaceLuid.Value,
        v32->InterfaceIndex,
        v21,
        v24,
        v19,
        v25,
        v26,
        v27,
        v28,
        v14,
        v36,
        v35,
        v34,
        v33,
        v29,
        v30);
      v1 = a1;
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v39);
      std::wstring::_Tidy_deallocate((__int64)v40);
      std::wstring::_Tidy_deallocate((__int64)v41);
      v4 = v32 + 1;
      v32 = v4;
    }
    while ( v4 != (MIB_IPFORWARD_ROW2 *)v38 );
    v3 = Table;
  }
  FreeMibTable(v3);
  return v1;
}

```

## disassembly

```asm
0x180039f70  push    rbp
0x180039f72  push    rbx
0x180039f73  push    rsi
0x180039f74  push    rdi
0x180039f75  push    r12
0x180039f77  push    r13
0x180039f79  push    r14
0x180039f7b  push    r15
0x180039f7d  lea     rbp, [rsp-58h]
0x180039f82  sub     rsp, 168h
0x180039f89  mov     rax, cs:__security_cookie
0x180039f90  xor     rax, rsp
0x180039f93  mov     [rbp+90h+var_48], rax
0x180039f97  mov     rbx, rcx
0x180039f9a  mov     [rbp+90h+var_D8], rcx
0x180039f9e  mov     [rbp+90h+var_C8], rcx
0x180039fa2  xor     esi, esi
0x180039fa4  mov     [rbp+90h+var_108], esi
0x180039fa7  mov     [rbp+90h+Table], rsi
0x180039fab  xor     ecx, ecx; Family
0x180039fad  lea     rdx, [rbp+90h+Table]; Table
0x180039fb1  call    cs:__imp_GetIpForwardTable2
0x180039fb7  mov     rcx, [rbp+98h]; this
0x180039fbe  test    eax, eax
0x180039fc0  jz      short loc_180039FD7
0x180039fc2  mov     r9d, eax; char *
0x180039fc5  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x180039fcc  mov     edx, 481h; void *
0x180039fd1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180039fd7  lea     rax, [rbp+90h+Table]
0x180039fdb  mov     [rbp+90h+var_C0], rax
0x180039fdf  mov     [rbp+90h+var_B8], 1
0x180039fe3  mov     rcx, rbx
0x180039fe6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180039feb  mov     [rbp+90h+var_108], 1
0x180039ff2  mov     rcx, [rbp+90h+Table]
0x180039ff6  lea     rdi, [rcx+8]
0x180039ffa  mov     [rbp+90h+var_100], rdi
0x180039ffe  mov     eax, [rcx]
0x18003a000  imul    rax, 68h ; 'h'
0x18003a004  add     rax, rdi
0x18003a007  mov     [rbp+90h+var_D0], rax
0x18003a00b  cmp     rdi, rax
0x18003a00e  jz      loc_18003A1E0
0x18003a014  lea     rdx, aFalse_0; "false"
0x18003a01b  mov     ecx, [rdi+64h]
0x18003a01e  test    ecx, ecx
0x18003a020  jz      short loc_18003A063
0x18003a022  sub     ecx, 1
0x18003a025  jz      short loc_18003A05A
0x18003a027  sub     ecx, 1
0x18003a02a  jz      short loc_18003A051
0x18003a02c  sub     ecx, 1
0x18003a02f  jz      short loc_18003A048
0x18003a031  cmp     ecx, 1
0x18003a034  jz      short loc_18003A03F
0x18003a036  lea     rax, aUnknownNlRoute_0; "(unknown NL_ROUTE_ORIGIN)"
0x18003a03d  jmp     short loc_18003A06A
0x18003a03f  lea     rax, aNlro6to4; "Nlro6to4"
0x18003a046  jmp     short loc_18003A06A
0x18003a048  lea     rax, aNlrorouteradve; "NlroRouterAdvertisement"
0x18003a04f  jmp     short loc_18003A06A
0x18003a051  lea     rax, aNlrodhcp; "NlroDHCP"
0x18003a058  jmp     short loc_18003A06A
0x18003a05a  lea     rax, aNlrowellknown; "NlroWellKnown"
0x18003a061  jmp     short loc_18003A06A
0x18003a063  lea     rax, aNlromanual; "NlroManual"
0x18003a06a  mov     [rbp+90h+var_110], rax
0x18003a06e  mov     eax, [rdi+60h]
0x18003a071  mov     [rbp+90h+var_104], eax
0x18003a074  lea     rax, aTrue_0; "true"
0x18003a07b  cmp     [rdi+5Fh], sil
0x18003a07f  cmovz   rax, rdx
0x18003a083  mov     [rbp+90h+var_F8], rax
0x18003a087  lea     rax, aTrue_0; "true"
0x18003a08e  cmp     [rdi+5Eh], sil
0x18003a092  cmovz   rax, rdx
0x18003a096  mov     [rbp+90h+var_F0], rax
0x18003a09a  lea     rax, aTrue_0; "true"
0x18003a0a1  cmp     [rdi+5Dh], sil
0x18003a0a5  cmovz   rax, rdx
0x18003a0a9  mov     [rbp+90h+var_E8], rax
0x18003a0ad  lea     rax, aTrue_0; "true"
0x18003a0b4  cmp     [rdi+5Ch], sil
0x18003a0b8  cmovz   rax, rdx
0x18003a0bc  mov     [rbp+90h+var_E0], rax
0x18003a0c0  lea     rcx, [rdi+58h]; enum NL_ROUTE_PROTOCOL *
0x18003a0c4  call    ?ToString@@YAPEB_WAEBW4NL_ROUTE_PROTOCOL@@@Z; ToString(NL_ROUTE_PROTOCOL const &)
0x18003a0c9  mov     rsi, rax
0x18003a0cc  mov     r14d, [rdi+54h]
0x18003a0d0  mov     r15d, [rdi+50h]
0x18003a0d4  mov     r12d, [rdi+4Ch]
0x18003a0d8  movzx   r13d, byte ptr [rdi+48h]
0x18003a0dd  lea     rdx, [rdi+2Ch]
0x18003a0e1  lea     rcx, [rbp+90h+var_70]
0x18003a0e5  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBT_SOCKADDR_INET@@@Z; ToString(_SOCKADDR_INET const &)
0x18003a0ea  nop
0x18003a0eb  mov     rcx, rax
0x18003a0ee  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003a0f3  mov     rbx, rax
0x18003a0f6  movzx   edi, byte ptr [rdi+28h]
0x18003a0fa  mov     rdx, [rbp+90h+var_100]
0x18003a0fe  add     rdx, 0Ch
0x18003a102  lea     rcx, [rbp+90h+var_90]
0x18003a106  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBT_SOCKADDR_INET@@@Z; ToString(_SOCKADDR_INET const &)
0x18003a10b  nop
0x18003a10c  mov     rcx, rax
0x18003a10f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003a114  mov     rcx, [rbp+90h+var_110]
0x18003a118  mov     [rsp+1A0h+var_118], rcx
0x18003a120  mov     ecx, [rbp+90h+var_104]
0x18003a123  mov     dword ptr [rsp+1A0h+var_120], ecx
0x18003a12a  mov     rcx, [rbp+90h+var_F8]
0x18003a12e  mov     [rsp+1A0h+var_128], rcx
0x18003a133  mov     rcx, [rbp+90h+var_F0]
0x18003a137  mov     [rsp+1A0h+var_130], rcx
0x18003a13c  mov     rcx, [rbp+90h+var_E8]
0x18003a140  mov     [rsp+1A0h+var_138], rcx
0x18003a145  mov     rcx, [rbp+90h+var_E0]
0x18003a149  mov     [rsp+1A0h+var_140], rcx
0x18003a14e  mov     [rsp+1A0h+var_148], rsi
0x18003a153  mov     dword ptr [rsp+1A0h+var_150], r14d
0x18003a158  mov     dword ptr [rsp+1A0h+var_158], r15d
0x18003a15d  mov     dword ptr [rsp+1A0h+var_160], r12d
0x18003a162  mov     dword ptr [rsp+1A0h+var_168], r13d
0x18003a167  mov     [rsp+1A0h+var_170], rbx
0x18003a16c  mov     dword ptr [rsp+1A0h+var_178], edi
0x18003a170  mov     [rsp+1A0h+var_180], rax
0x18003a175  mov     rdi, [rbp+90h+var_100]
0x18003a179  mov     r9d, [rdi+8]
0x18003a17d  mov     r8, [rdi]
0x18003a180  lea     rdx, aGetipforwardta_0; "\n >>>>>> GetIpForwardTable2 Informatio"...
0x18003a187  lea     rcx, [rbp+90h+var_B0]
0x18003a18b  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x18003a190  nop
0x18003a191  mov     rdx, rax
0x18003a194  mov     rbx, [rbp+90h+var_D8]
0x18003a198  mov     rcx, rbx
0x18003a19b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003a1a0  nop
0x18003a1a1  lea     rcx, [rbp+90h+var_B0]
0x18003a1a5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a1aa  nop
0x18003a1ab  lea     rcx, [rbp+90h+var_90]
0x18003a1af  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a1b4  nop
0x18003a1b5  lea     rcx, [rbp+90h+var_70]
0x18003a1b9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a1be  add     rdi, 68h ; 'h'
0x18003a1c2  mov     [rbp+90h+var_100], rdi
0x18003a1c6  cmp     rdi, [rbp+90h+var_D0]
0x18003a1ca  mov     esi, 0
0x18003a1cf  lea     rdx, aFalse_0; "false"
0x18003a1d6  jnz     loc_18003A01B
0x18003a1dc  mov     rcx, [rbp+90h+Table]; Memory
0x18003a1e0  call    cs:__imp_FreeMibTable
0x18003a1e6  mov     rax, rbx
0x18003a1e9  mov     rcx, [rbp+90h+var_48]
0x18003a1ed  xor     rcx, rsp; StackCookie
0x18003a1f0  call    __security_check_cookie
0x18003a1f5  add     rsp, 168h
0x18003a1fc  pop     r15
0x18003a1fe  pop     r14
0x18003a200  pop     r13
0x18003a202  pop     r12
0x18003a204  pop     rdi
0x18003a205  pop     rsi
0x18003a206  pop     rbx
0x18003a207  pop     rbp
0x18003a208  retn
```
