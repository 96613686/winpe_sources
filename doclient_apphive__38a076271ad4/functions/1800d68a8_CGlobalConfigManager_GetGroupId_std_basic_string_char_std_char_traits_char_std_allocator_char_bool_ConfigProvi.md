# CGlobalConfigManager::GetGroupId(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,bool *,_ConfigProviderType *)

- ea: `0x1800d68a8`
- end: `0x1800d6ea6`
- name: `?GetGroupId@CGlobalConfigManager@@QEAAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEA_NPEAW4_ConfigProviderType@@@Z`
- size: `1534`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `8`
- callee_count: `21`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180040d4c`
- `0x18004b870`
- `0x18006cc14`
- `0x1800b14e0`
- `0x1800b1dec`
- `0x1800d9574`
- `0x1800d9ee0`
- `0x1800eb574`

## callees

- `0x180008d14`
- `0x1800095a0`
- `0x18000ef98`
- `0x1800179a4`
- `0x18001d5fc`
- `0x1800604f8`
- `0x18007ca54`
- `0x1800a1ea4`
- `0x1800a979c`
- `0x1800aa2bc`
- `0x1800aa4c0`
- `0x1800aaab4`
- `0x1800aaf1c`
- `0x1800ab094`
- `0x1800c96d0`
- `0x1800d64d8`
- `0x1800d68a8`
- `0x1800db900`
- `0x1800dcf24`
- `0x1800dd968`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d6a84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d6b73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d6d5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d6a84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d6b73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d6d5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d69db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d6ae4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d6be9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d6c59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d69db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d6ae4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d6be9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d6c59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d6a0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d6b16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d6c1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d6c66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d6a0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d6b16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d6c1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d6c66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6a53`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6b42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6d20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6a53`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6b42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6d20`

## string_xrefs

- `0x1800d6dc0`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\GlobalConfigManager.cpp`
- `0x1800d6cd4`: `DomainSID`
- `0x1800d6e29`: `CGlobalConfigManager::GetGroupId`
- `0x1800d6e6b`: `CGlobalConfigManager::GetGroupId`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CGlobalConfigManager::GetGroupId(void *a1, const char *a2, _BYTE *a3, _DWORD *a4)
{
  const char *v6; // r14
  const char *v8; // rax
  const char *v9; // rsi
  __int64 v10; // rax
  void **v11; // rdx
  void **v12; // rcx
  int v13; // eax
  void **v14; // rax
  void **v15; // rax
  int v16; // [rsp+20h] [rbp-59h]
  void *Src[2]; // [rsp+48h] [rbp-31h] BYREF
  size_t Size; // [rsp+58h] [rbp-21h]
  unsigned __int64 v19; // [rsp+60h] [rbp-19h]
  void *v20[2]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v21; // [rsp+78h] [rbp-1h]
  unsigned __int64 v22; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v6 = a2;
  *((_QWORD *)a2 + 2) = 0;
  v8 = a2;
  if ( *((_QWORD *)a2 + 3) > 0xFu )
    v8 = *(const char **)a2;
  *v8 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 99;
  *(_OWORD *)Src = 0;
  Size = 0;
  v19 = 15;
  LOBYTE(Src[0]) = 0;
  v9 = (const char *)&word_180129F2A;
  if ( (unsigned int)CGlobalConfigManager::GetDownloadMode(a1, 0, 0) != 2 )
    goto LABEL_22;
  v10 = CGlobalConfigManager::GetConfigValue<std::string>(a1, v20, 67);
  std::string::operator=(Src, v10);
  std::string::~string(v20);
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 1;
  v9 = "DOGroupId";
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl'::`2'::impl) )
    v9 = (const char *)&word_180129F2A;
  if ( Size )
  {
    v11 = Src;
    if ( v19 > 0xF )
      v11 = (void **)Src[0];
    UTF8toWstr(v20, v11, Size);
    v12 = v20;
    if ( v22 > 7 )
      v12 = (void **)v20[0];
    v13 = Sha2HashAndEncode(v12, 2 * v21 + 2);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2CF,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\GlobalConfigManager.cpp",
        (const char *)(unsigned int)v13,
        v16);
    std::wstring::~wstring(v20);
LABEL_22:
    if ( Size )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl'::`2'::impl) )
      {
        if ( *((_QWORD *)v6 + 3) > 0xFu )
          v6 = *(const char **)v6;
        v14 = Src;
        if ( v19 > 0xF )
          v14 = (void **)Src[0];
        LogMessage(
          5u,
          "CGlobalConfigManager::GetGroupId",
          0x2D8u,
          "GroupID = %s, SHA2-encoded = %s, Source = %s",
          (const char *)v14,
          v6,
          v9);
      }
      else
      {
        if ( *((_QWORD *)v6 + 3) > 0xFu )
          v6 = *(const char **)v6;
        v15 = Src;
        if ( v19 > 0xF )
          v15 = (void **)Src[0];
        LogMessage(
          5u,
          "CGlobalConfigManager::GetGroupId",
          0x2DCu,
          "GroupID = %s, SHA2-encoded = %s",
          (const char *)v15,
          v6);
      }
    }
  }
  std::string::~string(Src);
}

```

## disassembly

```asm
0x1800d68a8  push    rbp
0x1800d68aa  push    rbx
0x1800d68ab  push    rsi
0x1800d68ac  push    rdi
0x1800d68ad  push    r12
0x1800d68af  push    r13
0x1800d68b1  push    r14
0x1800d68b3  push    r15
0x1800d68b5  lea     rbp, [rsp-1Fh]
0x1800d68ba  sub     rsp, 98h
0x1800d68c1  mov     rax, cs:__security_cookie
0x1800d68c8  xor     rax, rsp
0x1800d68cb  mov     [rbp+57h+var_48], rax
0x1800d68cf  mov     rdi, r9
0x1800d68d2  mov     rbx, r8
0x1800d68d5  mov     r14, rdx
0x1800d68d8  mov     r15, rcx
0x1800d68db  xor     r12d, r12d
0x1800d68de  mov     [rdx+10h], r12
0x1800d68e2  mov     rax, rdx
0x1800d68e5  cmp     qword ptr [rdx+18h], 0Fh
0x1800d68ea  jbe     short loc_1800D68EF
0x1800d68ec  mov     rax, [rdx]
0x1800d68ef  mov     [rax], r12b
0x1800d68f2  test    rbx, rbx
0x1800d68f5  jz      short loc_1800D68FA
0x1800d68f7  mov     [r8], r12b
0x1800d68fa  test    rdi, rdi
0x1800d68fd  jz      short loc_1800D6906
0x1800d68ff  mov     dword ptr [r9], 63h ; 'c'
0x1800d6906  xorps   xmm0, xmm0
0x1800d6909  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1800d690d  mov     [rbp+57h+Size], r12
0x1800d6911  mov     [rbp+57h+var_70], 0Fh
0x1800d6919  mov     byte ptr [rbp+57h+Src], r12b
0x1800d691d  lea     rsi, word_180129F2A
0x1800d6924  xor     r8d, r8d
0x1800d6927  xor     edx, edx
0x1800d6929  call    ?GetDownloadMode@CGlobalConfigManager@@QEAA?AW4_DownloadMode@@PEA_NPEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetDownloadMode(bool *,_ConfigProviderType *)
0x1800d692e  cmp     eax, 2
0x1800d6931  jnz     loc_1800D6DDB
0x1800d6937  mov     [rbp+57h+var_90], r12d
0x1800d693b  lea     r9, [rbp+57h+var_90]
0x1800d693f  lea     r8d, [rax+41h]
0x1800d6943  lea     rdx, [rbp+57h+var_68]
0x1800d6947  mov     rcx, r15
0x1800d694a  call    ??$GetConfigValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@CGlobalConfigManager@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Index@DOConfig@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetConfigValue<std::string>(DOConfig::Index,_ConfigProviderType *)
0x1800d694f  mov     rdx, rax
0x1800d6952  lea     rcx, [rbp+57h+Src]
0x1800d6956  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800d695b  lea     rcx, [rbp+57h+var_68]; void *
0x1800d695f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800d6964  mov     eax, [rbp+57h+var_90]
0x1800d6967  test    rdi, rdi
0x1800d696a  jz      short loc_1800D696E
0x1800d696c  mov     [rdi], eax
0x1800d696e  cmp     eax, 63h ; 'c'
0x1800d6971  jz      short loc_1800D699C
0x1800d6973  test    rbx, rbx
0x1800d6976  jz      short loc_1800D697B
0x1800d6978  mov     byte ptr [rbx], 1
0x1800d697b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl(void)'::`2'::impl
0x1800d6982  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(void)
0x1800d6987  mov     rcx, rsi
0x1800d698a  lea     rsi, aDogroupid; "DOGroupId"
0x1800d6991  test    al, al
0x1800d6993  cmovz   rsi, rcx
0x1800d6997  jmp     loc_1800D6D68
0x1800d699c  mov     r8, rdi
0x1800d699f  mov     edx, 44h ; 'D'
0x1800d69a4  mov     rcx, r15
0x1800d69a7  call    ??$GetConfigValue@I@CGlobalConfigManager@@QEBAIW4Index@DOConfig@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetConfigValue<uint>(DOConfig::Index,_ConfigProviderType *)
0x1800d69ac  mov     r13d, eax
0x1800d69af  mov     ecx, eax
0x1800d69b1  sub     ecx, 3
0x1800d69b4  jz      loc_1800D6ACB
0x1800d69ba  cmp     ecx, 1
0x1800d69bd  jnz     loc_1800D6BB5
0x1800d69c3  xorps   xmm0, xmm0
0x1800d69c6  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800d69ca  lea     rdi, [r15+0A8h]
0x1800d69d1  mov     [rbp+57h+var_68], rdi
0x1800d69d5  mov     byte ptr [rbp+57h+var_68+8], cl
0x1800d69d8  mov     rcx, rdi; SRWLock
0x1800d69db  call    cs:__imp_AcquireSRWLockShared
0x1800d69e1  nop
0x1800d69e2  lea     rbx, [r15+68h]
0x1800d69e6  lea     rax, [rbp+57h+Src]
0x1800d69ea  cmp     rax, rbx
0x1800d69ed  jz      short loc_1800D6A0A
0x1800d69ef  mov     rdx, rbx
0x1800d69f2  cmp     qword ptr [rbx+18h], 0Fh
0x1800d69f7  jbe     short loc_1800D69FC
0x1800d69f9  mov     rdx, [rbx]; Src
0x1800d69fc  mov     r8, [rbx+10h]; Size
0x1800d6a00  lea     rcx, [rbp+57h+Src]; void *
0x1800d6a04  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800d6a09  nop
0x1800d6a0a  mov     rcx, rdi; SRWLock
0x1800d6a0d  call    cs:__imp_ReleaseSRWLockShared
0x1800d6a13  cmp     [rbp+57h+Size], r12
0x1800d6a17  jnz     loc_1800D6AAB
0x1800d6a1d  lea     rcx, [rbp+57h+var_68]
0x1800d6a21  call    ?GetLocalDnsSuffix@CNetworkInterface@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; CNetworkInterface::GetLocalDnsSuffix(void)
0x1800d6a26  mov     rdx, rax
0x1800d6a29  lea     rcx, [rbp+57h+Src]
0x1800d6a2d  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800d6a32  lea     rcx, [rbp+57h+var_68]; void *
0x1800d6a36  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800d6a3b  cmp     [rbp+57h+Size], r12
0x1800d6a3f  jz      loc_1800D6B94
0x1800d6a45  xorps   xmm0, xmm0
0x1800d6a48  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800d6a4c  mov     [rbp+57h+var_68], rdi
0x1800d6a50  mov     rcx, rdi; SRWLock
0x1800d6a53  call    cs:__imp_AcquireSRWLockExclusive
0x1800d6a59  mov     byte ptr [rbp+57h+var_68+8], 1
0x1800d6a5d  lea     rax, [rbp+57h+Src]
0x1800d6a61  cmp     rbx, rax
0x1800d6a64  jz      short loc_1800D6A81
0x1800d6a66  lea     rdx, [rbp+57h+Src]
0x1800d6a6a  cmp     [rbp+57h+var_70], 0Fh
0x1800d6a6f  cmova   rdx, [rbp+57h+Src]; Src
0x1800d6a74  mov     r8, [rbp+57h+Size]; Size
0x1800d6a78  mov     rcx, rbx; void *
0x1800d6a7b  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800d6a80  nop
0x1800d6a81  mov     rcx, rdi; SRWLock
0x1800d6a84  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d6a8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl(void)'::`2'::impl
0x1800d6a91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(void)
0x1800d6a96  mov     rcx, rsi
0x1800d6a99  lea     rsi, aDnssuffix; "DnsSuffix"
0x1800d6aa0  test    al, al
0x1800d6aa2  cmovz   rsi, rcx
0x1800d6aa6  jmp     loc_1800D6BB5
0x1800d6aab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl(void)'::`2'::impl
0x1800d6ab2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(void)
0x1800d6ab7  test    al, al
0x1800d6ab9  jz      loc_1800D6BB5
0x1800d6abf  lea     rsi, aDnssuffix; "DnsSuffix"
0x1800d6ac6  jmp     loc_1800D6BB5
0x1800d6acb  xorps   xmm0, xmm0
0x1800d6ace  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800d6ad2  lea     rdi, [r15+0A8h]
0x1800d6ad9  mov     [rbp+57h+var_68], rdi
0x1800d6add  mov     byte ptr [rbp+57h+var_68+8], 1
0x1800d6ae1  mov     rcx, rdi; SRWLock
0x1800d6ae4  call    cs:__imp_AcquireSRWLockShared
0x1800d6aea  nop
0x1800d6aeb  lea     rbx, [r15+20h]
0x1800d6aef  lea     rax, [rbp+57h+Src]
0x1800d6af3  cmp     rax, rbx
0x1800d6af6  jz      short loc_1800D6B13
0x1800d6af8  mov     rdx, rbx
0x1800d6afb  cmp     qword ptr [rbx+18h], 0Fh
0x1800d6b00  jbe     short loc_1800D6B05
0x1800d6b02  mov     rdx, [rbx]; Src
0x1800d6b05  mov     r8, [rbx+10h]; Size
0x1800d6b09  lea     rcx, [rbp+57h+Src]; void *
0x1800d6b0d  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800d6b12  nop
0x1800d6b13  mov     rcx, rdi; SRWLock
0x1800d6b16  call    cs:__imp_ReleaseSRWLockShared
0x1800d6b1c  cmp     [rbp+57h+Size], r12
0x1800d6b20  jnz     short loc_1800D6B99
0x1800d6b22  lea     rdx, [rbp+57h+Src]
0x1800d6b26  mov     ecx, 0EAh
0x1800d6b2b  call    ?GetDhcpOptionString@@YAJIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; GetDhcpOptionString(uint,std::string &)
0x1800d6b30  test    eax, eax
0x1800d6b32  js      short loc_1800D6B94
0x1800d6b34  xorps   xmm0, xmm0
0x1800d6b37  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800d6b3b  mov     [rbp+57h+var_68], rdi
0x1800d6b3f  mov     rcx, rdi; SRWLock
0x1800d6b42  call    cs:__imp_AcquireSRWLockExclusive
0x1800d6b48  mov     byte ptr [rbp+57h+var_68+8], 1
0x1800d6b4c  lea     rax, [rbp+57h+Src]
0x1800d6b50  cmp     rbx, rax
0x1800d6b53  jz      short loc_1800D6B70
0x1800d6b55  lea     rdx, [rbp+57h+Src]
0x1800d6b59  cmp     [rbp+57h+var_70], 0Fh
0x1800d6b5e  cmova   rdx, [rbp+57h+Src]; Src
0x1800d6b63  mov     r8, [rbp+57h+Size]; Size
0x1800d6b67  mov     rcx, rbx; void *
0x1800d6b6a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800d6b6f  nop
0x1800d6b70  mov     rcx, rdi; SRWLock
0x1800d6b73  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d6b79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl(void)'::`2'::impl
0x1800d6b80  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(void)
0x1800d6b85  mov     rcx, rsi
0x1800d6b88  lea     rsi, aDhcpoption234; "DhcpOption234"
0x1800d6b8f  jmp     loc_1800D6AA0
0x1800d6b94  mov     r13d, r12d
0x1800d6b97  jmp     short loc_1800D6BB5
0x1800d6b99  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl(void)'::`2'::impl
0x1800d6ba0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(void)
0x1800d6ba5  lea     rdx, aDhcpoption234; "DhcpOption234"
0x1800d6bac  test    al, al
0x1800d6bae  cmovz   rdx, rsi
0x1800d6bb2  mov     rsi, rdx
0x1800d6bb5  mov     eax, r13d
0x1800d6bb8  test    r13d, r13d
0x1800d6bbb  jz      short loc_1800D6BD0
0x1800d6bbd  sub     eax, 1
0x1800d6bc0  jz      short loc_1800D6BD0
0x1800d6bc2  sub     eax, 1
0x1800d6bc5  jz      short loc_1800D6BD0
0x1800d6bc7  cmp     eax, 3
0x1800d6bca  jnz     loc_1800D6D68
0x1800d6bd0  xorps   xmm0, xmm0
0x1800d6bd3  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800d6bd7  lea     r12, [r15+0A8h]
0x1800d6bde  mov     [rbp+57h+var_68], r12
0x1800d6be2  mov     byte ptr [rbp+57h+var_68+8], 1
0x1800d6be6  mov     rcx, r12; SRWLock
0x1800d6be9  call    cs:__imp_AcquireSRWLockShared
0x1800d6bef  nop
0x1800d6bf0  lea     rax, [rbp+57h+Src]
0x1800d6bf4  cmp     rax, r15
0x1800d6bf7  jz      short loc_1800D6C13
0x1800d6bf9  mov     rdx, r15
0x1800d6bfc  cmp     qword ptr [r15+18h], 0Fh
0x1800d6c01  jbe     short loc_1800D6C06
0x1800d6c03  mov     rdx, [r15]; Src
0x1800d6c06  mov     r8, [r15+10h]; Size
0x1800d6c0a  lea     rcx, [rbp+57h+Src]; void *
0x1800d6c0e  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800d6c13  mov     bl, [r15+2AFh]
0x1800d6c1a  mov     rcx, r12; SRWLock
0x1800d6c1d  call    cs:__imp_ReleaseSRWLockShared
0x1800d6c23  cmp     [rbp+57h+Size], 0
0x1800d6c28  jnz     loc_1800D6D74
0x1800d6c2e  test    bl, bl
0x1800d6c30  jz      loc_1800D6E7D
0x1800d6c36  cmp     r13d, 5
0x1800d6c3a  jz      loc_1800D6CE6
0x1800d6c40  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x1800d6c45  mov     rbx, rax
0x1800d6c48  xor     edx, edx; bool
0x1800d6c4a  mov     rcx, rax; this
0x1800d6c4d  call    ?UpdateDeviceOptions@CDeviceProfile@@QEAAX_N@Z; CDeviceProfile::UpdateDeviceOptions(bool)
0x1800d6c52  lea     rdi, [rbx+8]
0x1800d6c56  mov     rcx, rdi; SRWLock
0x1800d6c59  call    cs:__imp_AcquireSRWLockShared
0x1800d6c5f  movzx   ebx, word ptr [rbx+2]
0x1800d6c63  mov     rcx, rdi; SRWLock
0x1800d6c66  call    cs:__imp_ReleaseSRWLockShared
0x1800d6c6c  bt      ebx, 2
0x1800d6c70  jnb     short loc_1800D6CDD
0x1800d6c72  cmp     r13d, 2
0x1800d6c76  jz      short loc_1800D6CA3
0x1800d6c78  lea     rcx, [rbp+57h+Src]; void *
0x1800d6c7c  call    ?GetActiveDirectorySiteId@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; GetActiveDirectorySiteId(std::string &)
0x1800d6c81  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl(void)'::`2'::impl
0x1800d6c88  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(void)
0x1800d6c8d  test    al, al
0x1800d6c8f  jz      short loc_1800D6CA3
0x1800d6c91  mov     rax, [rbp+57h+Size]
0x1800d6c95  test    rax, rax
0x1800d6c98  jz      short loc_1800D6CAC
0x1800d6c9a  lea     rsi, aAdsiteid; "ADSiteId"
0x1800d6ca1  jmp     short loc_1800D6CA7
0x1800d6ca3  mov     rax, [rbp+57h+Size]
0x1800d6ca7  test    rax, rax
0x1800d6caa  jnz     short loc_1800D6D12
0x1800d6cac  cmp     r13d, 1
0x1800d6cb0  jz      short loc_1800D6CE1
0x1800d6cb2  lea     rcx, [rbp+57h+Src]
0x1800d6cb6  call    ?GetPrimaryDomainSid@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; GetPrimaryDomainSid(std::string &)
0x1800d6cbb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl(void)'::`2'::impl
0x1800d6cc2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(void)
0x1800d6cc7  test    al, al
0x1800d6cc9  jz      short loc_1800D6CDD
0x1800d6ccb  mov     rax, [rbp+57h+Size]
0x1800d6ccf  test    rax, rax
0x1800d6cd2  jz      short loc_1800D6CE6
0x1800d6cd4  lea     rsi, aDomainsid; "DomainSID"
0x1800d6cdb  jmp     short loc_1800D6CE1
0x1800d6cdd  mov     rax, [rbp+57h+Size]
0x1800d6ce1  test    rax, rax
0x1800d6ce4  jnz     short loc_1800D6D12
0x1800d6ce6  lea     rcx, [rbp+57h+Src]
0x1800d6cea  call    ?GetAzureActiveDirectoryTenantId@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; GetAzureActiveDirectoryTenantId(std::string &)
0x1800d6cef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::GetImpl(void)'::`2'::impl
0x1800d6cf6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_v15_56129939_LogGroupIdSource>::__private_IsEnabled(void)
0x1800d6cfb  test    al, al
0x1800d6cfd  jz      short loc_1800D6D12
0x1800d6cff  lea     rax, aEntratenantid; "EntraTenantId"
0x1800d6d06  cmp     [rbp+57h+Size], 0
0x1800d6d0b  cmovz   rax, rsi
0x1800d6d0f  mov     rsi, rax
0x1800d6d12  xorps   xmm0, xmm0
0x1800d6d15  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1800d6d19  mov     [rbp+57h+var_68], r12
0x1800d6d1d  mov     rcx, r12; SRWLock
0x1800d6d20  call    cs:__imp_AcquireSRWLockExclusive
0x1800d6d26  mov     byte ptr [rbp+57h+var_68+8], 1
0x1800d6d2a  mov     r8, [rbp+57h+Size]; Size
  ... truncated ...
```
