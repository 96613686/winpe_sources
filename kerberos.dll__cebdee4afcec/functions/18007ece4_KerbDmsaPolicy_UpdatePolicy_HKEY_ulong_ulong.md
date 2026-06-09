# KerbDmsaPolicy::UpdatePolicy(HKEY__ *,ulong,ulong)

- ea: `0x18007ece4`
- end: `0x18007f013`
- name: `?UpdatePolicy@KerbDmsaPolicy@@SAXPEAUHKEY__@@KK@Z`
- size: `815`
- prototype: `void __fastcall(HKEY hKey, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18007b8ac`

## callees

- `0x18000e510`
- `0x1800659ac`
- `0x18006d058`
- `0x18006f13c`
- `0x18006ff94`
- `0x180070050`
- `0x180070680`
- `0x1800798b8`
- `0x180079ad0`
- `0x18007a0a8`
- `0x18007a690`
- `0x18007a848`
- `0x18007a93c`
- `0x18007e308`
- `0x18007ece4`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007ed15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007ed15`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ed96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007edfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ed96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007edfc`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18007eeba`
- `msvcp_win!??Bios_base@std@@QEBA_NXZ` at `0x18007eeba`

## string_xrefs

- `0x18007ed55`: `KerbDmsaPolicy::UpdatePolicy`
- `0x18007ef7f`: `KerbDmsaPolicy::UpdatePolicy`
- `0x18007efbb`: `KerbDmsaPolicy::UpdatePolicy`
- `0x18007eff1`: `KerbDmsaPolicy::UpdatePolicy`
- `0x18007ef72`: `Querying the DMSA realms from the registry failed Error: 0x%08X, Type: %d\n`
- `0x18007efae`: `Querying the DMSA realms from the registry failed Error: 0x%08X, Type: %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
void __fastcall KerbDmsaPolicy::UpdatePolicy(HKEY hKey, unsigned int a2, unsigned int a3)
{
  __int64 v6; // rdx
  LSTATUS v7; // eax
  DWORD v8; // r8d
  LSTATUS v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  DWORD Type; // [rsp+30h] [rbp-178h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-174h] BYREF
  RTL_SRWLOCK *v14; // [rsp+38h] [rbp-170h] BYREF
  LPBYTE lpData; // [rsp+40h] [rbp-168h] BYREF
  __int128 v16; // [rsp+48h] [rbp-160h] BYREF
  __int64 v17; // [rsp+58h] [rbp-150h]
  _BYTE v18[240]; // [rsp+60h] [rbp-148h] BYREF
  __int128 v19; // [rsp+150h] [rbp-58h] BYREF
  __int128 v20; // [rsp+160h] [rbp-48h]

  AcquireSRWLockExclusive(&KerbDmsaPolicy::Lock);
  v14 = &KerbDmsaPolicy::Lock;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DMSAClient>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DMSAClient>::GetImpl'::`2'::impl,
    v6);
  KerbDmsaPolicy::PermissionWriteTimer = a2;
  KerbDmsaPolicy::DmsaEnabled = a3;
  if ( !hKey )
  {
    KerbTracerT::Log(1, "KerbDmsaPolicy::UpdatePolicy", 737, "Null PolicyParamKey encountered\n");
LABEL_16:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v14);
    return;
  }
  Type = 4;
  cbData = 0;
  v7 = RegQueryValueExW(hKey, L"DmsaRealms", 0, &Type, 0, &cbData);
  if ( v7 == 2 )
  {
    v8 = cbData;
    goto LABEL_20;
  }
  v8 = cbData;
  if ( !cbData )
  {
LABEL_20:
    KerbTracerT::Log(
      3,
      "KerbDmsaPolicy::UpdatePolicy",
      757,
      "DmsaRealm reg value not found, continuing with defaults, size: %d\n",
      v8);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v14);
    return;
  }
  if ( v7 || Type != 7 )
  {
    KerbTracerT::Log(
      1,
      "KerbDmsaPolicy::UpdatePolicy",
      762,
      "Querying the DMSA realms from the registry failed Error: 0x%08X, Type: %d\n",
      v7,
      Type);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v14);
  }
  else
  {
    KerbAllocateClientBufferUnique<unsigned char>(&lpData, cbData);
    v9 = RegQueryValueExW(hKey, L"DmsaRealms", 0, &Type, lpData, &cbData);
    if ( !v9 && Type == 7 )
    {
      v19 = 0;
      v20 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v19, lpData, (unsigned __int64)cbData >> 1);
      std::basic_istringstream<unsigned short>::basic_istringstream<unsigned short>(v18, &v19);
      std::wstring::_Tidy_deallocate(&v19);
      v19 = 0;
      *(_QWORD *)&v20 = 0;
      *((_QWORD *)&v20 + 1) = 7;
      LOWORD(v19) = 0;
      v16 = 0;
      v17 = 0;
      while ( 1 )
      {
        v10 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v18, &v19, 0);
        if ( !(unsigned __int8)std::ios_base::operator bool(v10 + *(int *)(*(_QWORD *)v10 + 4LL)) )
          break;
        if ( (_QWORD)v20 )
        {
          if ( *((_QWORD *)&v16 + 1) == v17 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v16, *((_QWORD *)&v16 + 1), &v19);
          }
          else
          {
            std::wstring::wstring(*((_QWORD *)&v16 + 1), &v19);
            *((_QWORD *)&v16 + 1) += 32LL;
          }
        }
      }
      std::vector<std::wstring>::operator=(v11, &v16);
      std::vector<std::wstring>::_Tidy(&v16);
      std::wstring::_Tidy_deallocate(&v19);
      std::basic_istringstream<unsigned short>::`vbase destructor'(v18);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void KerbFreeClientBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void KerbFreeClientBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpData);
      goto LABEL_16;
    }
    KerbTracerT::Log(
      1,
      "KerbDmsaPolicy::UpdatePolicy",
      777,
      "Querying the DMSA realms from the registry failed Error: 0x%08X, Type: %d\n",
      v9,
      Type);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void KerbFreeClientBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void KerbFreeClientBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpData);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v14);
  }
}

```

## disassembly

```asm
0x18007ece4  push    rbx
0x18007ece6  push    rsi
0x18007ece7  push    rdi
0x18007ece8  push    r14
0x18007ecea  sub     rsp, 188h
0x18007ecf1  mov     rax, cs:__security_cookie
0x18007ecf8  xor     rax, rsp
0x18007ecfb  mov     [rsp+1A8h+var_38], rax
0x18007ed03  mov     edi, r8d
0x18007ed06  mov     ebx, edx
0x18007ed08  mov     rsi, rcx
0x18007ed0b  lea     r14, ?Lock@KerbDmsaPolicy@@0Vsrwlock@wil@@A; wil::srwlock KerbDmsaPolicy::Lock
0x18007ed12  mov     rcx, r14; SRWLock
0x18007ed15  call    cs:__imp_AcquireSRWLockExclusive
0x18007ed1b  mov     [rsp+1A8h+var_170], r14
0x18007ed20  mov     r14d, 1
0x18007ed26  mov     dl, r14b
0x18007ed29  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DMSAClient@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DMSAClient@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DMSAClient> `wil::Feature<__WilFeatureTraits_Feature_DMSAClient>::GetImpl(void)'::`2'::impl
0x18007ed30  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DMSAClient@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DMSAClient>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007ed35  mov     cs:?PermissionWriteTimer@KerbDmsaPolicy@@0KA, ebx; ulong KerbDmsaPolicy::PermissionWriteTimer
0x18007ed3b  mov     cs:?DmsaEnabled@KerbDmsaPolicy@@0KA, edi; ulong KerbDmsaPolicy::DmsaEnabled
0x18007ed41  xor     ebx, ebx
0x18007ed43  test    rsi, rsi
0x18007ed46  jnz     short loc_18007ED69
0x18007ed48  lea     r9, aNullPolicypara; "Null PolicyParamKey encountered\n"
0x18007ed4f  mov     r8d, 2E1h
0x18007ed55  lea     rdx, aKerbdmsapolicy; "KerbDmsaPolicy::UpdatePolicy"
0x18007ed5c  mov     ecx, r14d
0x18007ed5f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007ed64  jmp     loc_18007EF43
0x18007ed69  mov     [rsp+1A8h+Type], 4
0x18007ed71  mov     [rsp+1A8h+cbData], ebx
0x18007ed75  lea     rax, [rsp+1A8h+cbData]
0x18007ed7a  mov     [rsp+1A8h+lpcbData], rax; lpcbData
0x18007ed7f  mov     [rsp+1A8h+lpData], rbx; lpData
0x18007ed84  lea     r9, [rsp+1A8h+Type]; lpType
0x18007ed89  xor     r8d, r8d; lpReserved
0x18007ed8c  lea     rdx, aDmsarealms; "DmsaRealms"
0x18007ed93  mov     rcx, rsi; hKey
0x18007ed96  call    cs:__imp_RegQueryValueExW
0x18007ed9c  cmp     eax, 2
0x18007ed9f  jz      loc_18007EFDA
0x18007eda5  mov     r8d, [rsp+1A8h+cbData]
0x18007edaa  test    r8d, r8d
0x18007edad  jz      loc_18007EFDF
0x18007edb3  mov     ecx, [rsp+1A8h+Type]
0x18007edb7  test    eax, eax
0x18007edb9  jnz     loc_18007EFA6
0x18007edbf  cmp     ecx, 7
0x18007edc2  jnz     loc_18007EFA6
0x18007edc8  mov     edx, r8d
0x18007edcb  lea     rcx, [rsp+1A8h+var_168]
0x18007edd0  call    ??$KerbAllocateClientBufferUnique@E@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?KerbFreeClientBuffer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@_K@Z; KerbAllocateClientBufferUnique<uchar>(unsigned __int64)
0x18007edd5  nop
0x18007edd6  lea     rax, [rsp+1A8h+cbData]
0x18007eddb  mov     [rsp+1A8h+lpcbData], rax; lpcbData
0x18007ede0  mov     rax, [rsp+1A8h+var_168]
0x18007ede5  mov     [rsp+1A8h+lpData], rax; lpData
0x18007edea  lea     r9, [rsp+1A8h+Type]; lpType
0x18007edef  xor     r8d, r8d; lpReserved
0x18007edf2  lea     rdx, aDmsarealms; "DmsaRealms"
0x18007edf9  mov     rcx, rsi; hKey
0x18007edfc  call    cs:__imp_RegQueryValueExW
0x18007ee02  mov     ecx, [rsp+1A8h+Type]
0x18007ee06  test    eax, eax
0x18007ee08  jnz     loc_18007EF6A
0x18007ee0e  cmp     ecx, 7
0x18007ee11  jnz     loc_18007EF6A
0x18007ee17  xorps   xmm0, xmm0
0x18007ee1a  movups  [rsp+1A8h+var_58], xmm0
0x18007ee22  xorps   xmm1, xmm1
0x18007ee25  movdqu  [rsp+1A8h+var_48], xmm1
0x18007ee2e  mov     r8d, [rsp+1A8h+cbData]
0x18007ee33  shr     r8, 1
0x18007ee36  mov     rdx, [rsp+1A8h+var_168]
0x18007ee3b  lea     rcx, [rsp+1A8h+var_58]
0x18007ee43  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007ee48  nop
0x18007ee49  lea     rdx, [rsp+1A8h+var_58]
0x18007ee51  lea     rcx, [rsp+1A8h+var_148]
0x18007ee56  call    ??0?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::basic_istringstream<ushort>::basic_istringstream<ushort>(std::wstring const &,int)
0x18007ee5b  nop
0x18007ee5c  lea     rcx, [rsp+1A8h+var_58]
0x18007ee64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ee69  xorps   xmm0, xmm0
0x18007ee6c  movups  [rsp+1A8h+var_58], xmm0
0x18007ee74  mov     qword ptr [rsp+1A8h+var_48], rbx
0x18007ee7c  mov     qword ptr [rsp+1A8h+var_48+8], 7
0x18007ee88  mov     word ptr [rsp+1A8h+var_58], bx
0x18007ee90  movdqu  [rsp+1A8h+var_160], xmm0
0x18007ee96  mov     [rsp+1A8h+var_150], rbx
0x18007ee9b  xor     r8d, r8d
0x18007ee9e  lea     rdx, [rsp+1A8h+var_58]
0x18007eea6  lea     rcx, [rsp+1A8h+var_148]
0x18007eeab  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@$$QEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@G@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &&,std::wstring &,ushort)
0x18007eeb0  mov     rcx, [rax]
0x18007eeb3  movsxd  rcx, dword ptr [rcx+4]
0x18007eeb7  add     rcx, rax
0x18007eeba  call    cs:__imp_??Bios_base@std@@QEBA_NXZ; std::ios_base::operator bool(void)
0x18007eec0  test    al, al
0x18007eec2  jz      short loc_18007EF09
0x18007eec4  cmp     qword ptr [rsp+1A8h+var_48], rbx
0x18007eecc  jz      short loc_18007EE9B
0x18007eece  mov     rax, qword ptr [rsp+1A8h+var_160+8]
0x18007eed3  cmp     rax, [rsp+1A8h+var_150]
0x18007eed8  jz      short loc_18007EEF2
0x18007eeda  lea     rdx, [rsp+1A8h+var_58]
0x18007eee2  mov     rcx, rax
0x18007eee5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007eeea  add     qword ptr [rsp+1A8h+var_160+8], 20h ; ' '
0x18007eef0  jmp     short loc_18007EE9B
0x18007eef2  lea     r8, [rsp+1A8h+var_58]
0x18007eefa  mov     rdx, rax
0x18007eefd  lea     rcx, [rsp+1A8h+var_160]
0x18007ef02  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18007ef07  jmp     short loc_18007EE9B
0x18007ef09  lea     rdx, [rsp+1A8h+var_160]
0x18007ef0e  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x18007ef13  nop
0x18007ef14  lea     rcx, [rsp+1A8h+var_160]
0x18007ef19  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18007ef1e  nop
0x18007ef1f  lea     rcx, [rsp+1A8h+var_58]
0x18007ef27  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ef2c  nop
0x18007ef2d  lea     rcx, [rsp+1A8h+var_148]
0x18007ef32  call    ??_D?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_istringstream<ushort>::`vbase destructor'(void)
0x18007ef37  nop
0x18007ef38  lea     rcx, [rsp+1A8h+var_168]
0x18007ef3d  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?KerbFreeClientBuffer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&KerbFreeClientBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&KerbFreeClientBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007ef42  nop
0x18007ef43  lea     rcx, [rsp+1A8h+var_170]
0x18007ef48  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18007ef4d  mov     rcx, [rsp+1A8h+var_38]
0x18007ef55  xor     rcx, rsp; StackCookie
0x18007ef58  call    __security_check_cookie
0x18007ef5d  add     rsp, 188h
0x18007ef64  pop     r14
0x18007ef66  pop     rdi
0x18007ef67  pop     rsi
0x18007ef68  pop     rbx
0x18007ef69  retn
0x18007ef6a  mov     dword ptr [rsp+1A8h+lpcbData], ecx
0x18007ef6e  mov     dword ptr [rsp+1A8h+lpData], eax
0x18007ef72  lea     r9, aQueryingTheDms; "Querying the DMSA realms from the regis"...
0x18007ef79  mov     r8d, 309h
0x18007ef7f  lea     rdx, aKerbdmsapolicy; "KerbDmsaPolicy::UpdatePolicy"
0x18007ef86  mov     ecx, r14d
0x18007ef89  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007ef8e  nop
0x18007ef8f  lea     rcx, [rsp+1A8h+var_168]
0x18007ef94  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?KerbFreeClientBuffer@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&KerbFreeClientBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&KerbFreeClientBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007ef99  nop
0x18007ef9a  lea     rcx, [rsp+1A8h+var_170]
0x18007ef9f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18007efa4  jmp     short loc_18007EF4D
0x18007efa6  mov     dword ptr [rsp+1A8h+lpcbData], ecx
0x18007efaa  mov     dword ptr [rsp+1A8h+lpData], eax
0x18007efae  lea     r9, aQueryingTheDms; "Querying the DMSA realms from the regis"...
0x18007efb5  mov     r8d, 2FAh
0x18007efbb  lea     rdx, aKerbdmsapolicy; "KerbDmsaPolicy::UpdatePolicy"
0x18007efc2  mov     ecx, r14d
0x18007efc5  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007efca  nop
0x18007efcb  lea     rcx, [rsp+1A8h+var_170]
0x18007efd0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18007efd5  jmp     loc_18007EF4D
0x18007efda  mov     r8d, [rsp+1A8h+cbData]
0x18007efdf  mov     dword ptr [rsp+1A8h+lpData], r8d
0x18007efe4  lea     r9, aDmsarealmRegVa; "DmsaRealm reg value not found, continui"...
0x18007efeb  mov     r8d, 2F5h
0x18007eff1  lea     rdx, aKerbdmsapolicy; "KerbDmsaPolicy::UpdatePolicy"
0x18007eff8  mov     ecx, 3
0x18007effd  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007f002  nop
0x18007f003  lea     rcx, [rsp+1A8h+var_170]
0x18007f008  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18007f00d  jmp     loc_18007EF4D
```
