# TenantRestrictions::OnPolicyChange(bool)

- ea: `0x18000b1d0`
- end: `0x18000b60b`
- name: `?OnPolicyChange@TenantRestrictions@@AEAAX_N@Z`
- size: `1083`
- prototype: `void __fastcall(RTL_SRWLOCK *this, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180009e80`
- `0x18000ac60`

## callees

- `0x180001a50`
- `0x180003e84`
- `0x180004518`
- `0x180008570`
- `0x180008c18`
- `0x180008d64`
- `0x180009da8`
- `0x180009dec`
- `0x18000a884`
- `0x18000ae7c`
- `0x18000b1d0`
- `0x18000c338`
- `0x18000c498`
- `0x18000c874`
- `0x180010174`
- `0x180010268`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b393`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b41c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b393`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000b41c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b59a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b59a`

## pseudocode

```c
void __fastcall TenantRestrictions::OnPolicyChange(RTL_SRWLOCK *this, bool a2)
{
  bool v4; // al
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  const OLECHAR *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  const OLECHAR *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  const wchar_t *v23; // rax
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rcx
  _BYTE v27[244]; // [rsp+30h] [rbp-218h] BYREF
  int v28; // [rsp+124h] [rbp-124h]
  _BYTE v29[16]; // [rsp+140h] [rbp-108h] BYREF
  __int64 v30; // [rsp+150h] [rbp-F8h]
  GUID pclsid; // [rsp+160h] [rbp-E8h] BYREF
  _BYTE v32[16]; // [rsp+170h] [rbp-D8h] BYREF
  __int64 v33; // [rsp+180h] [rbp-C8h]
  _BYTE v34[16]; // [rsp+190h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+1A0h] [rbp-A8h]
  _BYTE v36[32]; // [rsp+1B0h] [rbp-98h] BYREF
  _BYTE v37[32]; // [rsp+1D0h] [rbp-78h] BYREF
  _BYTE v38[32]; // [rsp+1F0h] [rbp-58h] BYREF
  _BYTE v39[16]; // [rsp+210h] [rbp-38h] BYREF
  const wchar_t *v40; // [rsp+220h] [rbp-28h]
  int v41; // [rsp+228h] [rbp-20h]
  int v42; // [rsp+22Ch] [rbp-1Ch]

  TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(
    (TenantRestrictionsLoggers::AutoMeasureLogger *)v27,
    "CloudidsvcPolicyChanged");
  v4 = IsTrv2Enabled();
  try
  {
    if ( v4 )
    {
      std::wstring::wstring(v38);
      std::wstring::wstring(v34);
      std::wstring::wstring(v32);
      if ( (int)ReadHeaderValuesFromRegistry((__int64)v38, (__int64)v34, (__int64)v32) >= 0 )
      {
        pclsid = 0;
        std::wstring::wstring(v37);
        std::wstring::wstring(v36);
        v5 = std::_WChar_traits<unsigned short>::length(L"{");
        std::wstring::_Assign<unsigned short>(v37, L"{", v5);
        v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
        std::wstring::_Append<unsigned short>(v37, v6, v35);
        v7 = std::_WChar_traits<unsigned short>::length(L"}");
        std::wstring::_Append<unsigned short>(v37, L"}", v7);
        v8 = std::_WChar_traits<unsigned short>::length(L"{");
        std::wstring::_Assign<unsigned short>(v36, L"{", v8);
        v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
        std::wstring::_Append<unsigned short>(v36, v9, v33);
        v10 = std::_WChar_traits<unsigned short>::length(L"}");
        std::wstring::_Append<unsigned short>(v36, L"}", v10);
        std::wstring::wstring(v29, &qword_180014598);
        v11 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
        if ( CLSIDFromString(v11, &pclsid) < 0 )
        {
          v12 = std::_WChar_traits<unsigned short>::length(L"tenantid");
          std::wstring::_Append<unsigned short>(v29, v13, v12);
          v14 = std::_WChar_traits<unsigned short>::length(L": ");
          std::wstring::_Append<unsigned short>(v29, L": ", v14);
          v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
          std::wstring::_Append<unsigned short>(v29, v15, v35);
        }
        v16 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
        if ( CLSIDFromString(v16, &pclsid) < 0 )
        {
          v17 = std::_WChar_traits<unsigned short>::length(L"\n");
          std::wstring::_Append<unsigned short>(v29, v18, v17);
          v19 = std::_WChar_traits<unsigned short>::length(L"policyid");
          std::wstring::_Append<unsigned short>(v29, v20, v19);
          v21 = std::_WChar_traits<unsigned short>::length(L": ");
          std::wstring::_Append<unsigned short>(v29, L": ", v21);
          v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
          std::wstring::_Append<unsigned short>(v29, v22, v33);
        }
        if ( v30 && (Microsoft_Windows_TenantRestrictionsEnableBits & 0x10) != 0 )
        {
          v23 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
          if ( v23 )
          {
            v25 = -1;
            do
              ++v25;
            while ( v23[v25] );
            v26 = (unsigned int)(2 * v25 + 2);
          }
          else
          {
            v23 = L"NULL";
            v26 = 10;
          }
          v40 = v23;
          v41 = v26;
          v42 = 0;
          McGenEventWrite_EventWriteTransfer(v26, InvalidPolicyGuid, v24, 2, v39);
        }
        std::wstring::_Tidy_deallocate(v29);
        std::wstring::_Tidy_deallocate(v36);
        std::wstring::_Tidy_deallocate(v37);
      }
      TenantRestrictions::CheckAndUpdatePolicyEndpointLkgData((TenantRestrictions *)this, a2);
      std::wstring::_Tidy_deallocate(v32);
      std::wstring::_Tidy_deallocate(v34);
      std::wstring::_Tidy_deallocate(v38);
    }
    else if ( !a2 )
    {
      AcquireSRWLockExclusive(this + 22);
      *(_QWORD *)&pclsid.Data1 = this + 22;
      LOBYTE(this[16].Ptr) = 0;
      LOBYTE(this[18].Ptr) = 0;
      LOBYTE(this[20].Ptr) = 0;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&pclsid);
    }
    v27[240] = 1;
    v28 = 0;
    TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)v27);
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x18000b1d0  mov     [rsp+arg_8], rbx
0x18000b1d5  mov     [rsp+arg_10], rsi
0x18000b1da  push    rdi
0x18000b1db  sub     rsp, 240h
0x18000b1e2  mov     rax, cs:__security_cookie
0x18000b1e9  xor     rax, rsp
0x18000b1ec  mov     [rsp+248h+var_18], rax
0x18000b1f4  mov     bl, dl
0x18000b1f6  mov     rdi, rcx
0x18000b1f9  lea     rdx, aCloudidsvcpoli; "CloudidsvcPolicyChanged"
0x18000b200  lea     rcx, [rsp+248h+var_218]; this
0x18000b205  call    ??0AutoMeasureLogger@TenantRestrictionsLoggers@@QEAA@PEBD@Z; TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(char const *)
0x18000b20a  nop
0x18000b20b  call    ?IsTrv2Enabled@@YA_NXZ; IsTrv2Enabled(void)
0x18000b210  xor     esi, esi
0x18000b212  test    al, al
0x18000b214  jz      loc_18000B58C
0x18000b21a  lea     rcx, [rsp+248h+var_58]
0x18000b222  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000b227  nop
0x18000b228  lea     rcx, [rsp+248h+var_B8]
0x18000b230  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000b235  nop
0x18000b236  lea     rcx, [rsp+248h+var_D8]
0x18000b23e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000b243  nop
0x18000b244  lea     r8, [rsp+248h+var_D8]
0x18000b24c  lea     rdx, [rsp+248h+var_B8]
0x18000b254  lea     rcx, [rsp+248h+var_58]
0x18000b25c  call    ?ReadHeaderValuesFromRegistry@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; ReadHeaderValuesFromRegistry(std::wstring &,std::wstring &,std::wstring &)
0x18000b261  test    eax, eax
0x18000b263  js      loc_18000B556
0x18000b269  xorps   xmm0, xmm0
0x18000b26c  movups  xmmword ptr [rsp+248h+pclsid.Data1], xmm0
0x18000b274  lea     rcx, [rsp+248h+var_78]
0x18000b27c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000b281  nop
0x18000b282  lea     rcx, [rsp+248h+var_98]
0x18000b28a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000b28f  nop
0x18000b290  lea     rcx, asc_1800149F0; "{"
0x18000b297  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b29c  mov     r8, rax
0x18000b29f  lea     rdx, asc_1800149F0; "{"
0x18000b2a6  lea     rcx, [rsp+248h+var_78]
0x18000b2ae  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000b2b3  lea     rcx, [rsp+248h+var_B8]
0x18000b2bb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b2c0  mov     rdx, rax
0x18000b2c3  mov     r8, [rsp+248h+var_A8]
0x18000b2cb  lea     rcx, [rsp+248h+var_78]
0x18000b2d3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b2d8  lea     rcx, asc_1800149F4; "}"
0x18000b2df  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b2e4  mov     r8, rax
0x18000b2e7  lea     rdx, asc_1800149F4; "}"
0x18000b2ee  lea     rcx, [rsp+248h+var_78]
0x18000b2f6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b2fb  lea     rcx, asc_1800149F0; "{"
0x18000b302  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b307  mov     r8, rax
0x18000b30a  lea     rdx, asc_1800149F0; "{"
0x18000b311  lea     rcx, [rsp+248h+var_98]
0x18000b319  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18000b31e  lea     rcx, [rsp+248h+var_D8]
0x18000b326  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b32b  mov     rdx, rax
0x18000b32e  mov     r8, [rsp+248h+var_C8]
0x18000b336  lea     rcx, [rsp+248h+var_98]
0x18000b33e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b343  lea     rcx, asc_1800149F4; "}"
0x18000b34a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b34f  mov     r8, rax
0x18000b352  lea     rdx, asc_1800149F4; "}"
0x18000b359  lea     rcx, [rsp+248h+var_98]
0x18000b361  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b366  lea     rdx, qword_180014598
0x18000b36d  lea     rcx, [rsp+248h+var_108]
0x18000b375  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000b37a  nop
0x18000b37b  lea     rcx, [rsp+248h+var_78]
0x18000b383  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b388  mov     rcx, rax; lpsz
0x18000b38b  lea     rdx, [rsp+248h+pclsid]; pclsid
0x18000b393  call    cs:__imp_CLSIDFromString
0x18000b399  test    eax, eax
0x18000b39b  jns     short loc_18000B404
0x18000b39d  lea     rcx, aTenantid; "tenantid"
0x18000b3a4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b3a9  mov     r8, rax
0x18000b3ac  mov     rdx, rcx
0x18000b3af  lea     rcx, [rsp+248h+var_108]
0x18000b3b7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b3bc  lea     rcx, asc_1800149F8; ": "
0x18000b3c3  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b3c8  mov     r8, rax
0x18000b3cb  lea     rdx, asc_1800149F8; ": "
0x18000b3d2  lea     rcx, [rsp+248h+var_108]
0x18000b3da  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b3df  lea     rcx, [rsp+248h+var_B8]
0x18000b3e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b3ec  mov     rdx, rax
0x18000b3ef  mov     r8, [rsp+248h+var_A8]
0x18000b3f7  lea     rcx, [rsp+248h+var_108]
0x18000b3ff  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b404  lea     rcx, [rsp+248h+var_98]
0x18000b40c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b411  mov     rcx, rax; lpsz
0x18000b414  lea     rdx, [rsp+248h+pclsid]; pclsid
0x18000b41c  call    cs:__imp_CLSIDFromString
0x18000b422  test    eax, eax
0x18000b424  jns     loc_18000B4B0
0x18000b42a  lea     rcx, asc_1800140E0; "\n"
0x18000b431  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b436  mov     r8, rax
0x18000b439  mov     rdx, rcx
0x18000b43c  lea     rcx, [rsp+248h+var_108]
0x18000b444  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b449  lea     rcx, aPolicyid; "policyid"
0x18000b450  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b455  mov     r8, rax
0x18000b458  mov     rdx, rcx
0x18000b45b  lea     rcx, [rsp+248h+var_108]
0x18000b463  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b468  lea     rcx, asc_1800149F8; ": "
0x18000b46f  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000b474  mov     r8, rax
0x18000b477  lea     rdx, asc_1800149F8; ": "
0x18000b47e  lea     rcx, [rsp+248h+var_108]
0x18000b486  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b48b  lea     rcx, [rsp+248h+var_D8]
0x18000b493  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b498  mov     rdx, rax
0x18000b49b  mov     r8, [rsp+248h+var_C8]
0x18000b4a3  lea     rcx, [rsp+248h+var_108]
0x18000b4ab  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000b4b0  cmp     [rsp+248h+var_F8], rsi
0x18000b4b8  jz      short loc_18000B52D
0x18000b4ba  test    cs:Microsoft_Windows_TenantRestrictionsEnableBits, 10h
0x18000b4c1  jz      short loc_18000B52D
0x18000b4c3  lea     rcx, [rsp+248h+var_108]
0x18000b4cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000b4d0  test    rax, rax
0x18000b4d3  jz      short loc_18000B4EB
0x18000b4d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b4d9  inc     rcx
0x18000b4dc  cmp     [rax+rcx*2], si
0x18000b4e0  jnz     short loc_18000B4D9
0x18000b4e2  lea     ecx, ds:2[rcx*2]
0x18000b4e9  jmp     short loc_18000B4F7
0x18000b4eb  lea     rax, aNull; "NULL"
0x18000b4f2  mov     ecx, 0Ah
0x18000b4f7  mov     [rsp+248h+var_28], rax
0x18000b4ff  mov     [rsp+248h+var_20], ecx
0x18000b506  mov     [rsp+248h+var_1C], esi
0x18000b50d  lea     rax, [rsp+248h+var_38]
0x18000b515  mov     [rsp+248h+var_228], rax
0x18000b51a  mov     r9d, 2
0x18000b520  lea     rdx, InvalidPolicyGuid
0x18000b527  call    McGenEventWrite_EventWriteTransfer
0x18000b52c  nop
0x18000b52d  lea     rcx, [rsp+248h+var_108]
0x18000b535  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b53a  nop
0x18000b53b  lea     rcx, [rsp+248h+var_98]
0x18000b543  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b548  nop
0x18000b549  lea     rcx, [rsp+248h+var_78]
0x18000b551  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b556  mov     dl, bl; bool
0x18000b558  mov     rcx, rdi; this
0x18000b55b  call    ?CheckAndUpdatePolicyEndpointLkgData@TenantRestrictions@@AEAAX_N@Z; TenantRestrictions::CheckAndUpdatePolicyEndpointLkgData(bool)
0x18000b560  nop
0x18000b561  lea     rcx, [rsp+248h+var_D8]
0x18000b569  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b56e  nop
0x18000b56f  lea     rcx, [rsp+248h+var_B8]
0x18000b577  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b57c  nop
0x18000b57d  lea     rcx, [rsp+248h+var_58]
0x18000b585  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000b58a  jmp     short loc_18000B5CA
0x18000b58c  test    bl, bl
0x18000b58e  jnz     short loc_18000B5CA
0x18000b590  lea     rbx, [rdi+0B0h]
0x18000b597  mov     rcx, rbx; SRWLock
0x18000b59a  call    cs:__imp_AcquireSRWLockExclusive
0x18000b5a0  mov     qword ptr [rsp+248h+pclsid.Data1], rbx
0x18000b5a8  mov     [rdi+80h], sil
0x18000b5af  mov     [rdi+90h], sil
0x18000b5b6  mov     [rdi+0A0h], sil
0x18000b5bd  lea     rcx, [rsp+248h+pclsid]
0x18000b5c5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b5ca  mov     [rsp+248h+var_128], 1
0x18000b5d2  mov     [rsp+248h+var_124], esi
0x18000b5d9  lea     rcx, [rsp+248h+var_218]; this
0x18000b5de  call    ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
0x18000b5e3  nop
0x18000b5e4  jmp     short $+2
0x18000b5e6  mov     rcx, [rsp+248h+var_18]
0x18000b5ee  xor     rcx, rsp; StackCookie
0x18000b5f1  call    __security_check_cookie
0x18000b5f6  lea     r11, [rsp+248h+var_8]
0x18000b5fe  mov     rbx, [r11+18h]
0x18000b602  mov     rsi, [r11+20h]
0x18000b606  mov     rsp, r11
0x18000b609  pop     rdi
0x18000b60a  retn
```
