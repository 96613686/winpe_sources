# Container::Manager::Core::Details::PolicyManager::Initialize(Csl::Path const &)

- ea: `0x1800fea78`
- end: `0x1800fef1c`
- name: `?Initialize@PolicyManager@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z`
- size: `1188`
- prototype: `__int64 __fastcall(PVOID pv, const struct Path *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180073848`

## callees

- `0x180004fc4`
- `0x180008bf0`
- `0x18000da68`
- `0x18000da88`
- `0x180016658`
- `0x180016774`
- `0x180023b68`
- `0x1800262e4`
- `0x18002fae4`
- `0x1800343f0`
- `0x180056330`
- `0x1800fe08c`
- `0x1800fea78`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800febb9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800febb9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800fed3e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800fed3e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800fee5a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800fee7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800fee5a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800fee7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fec00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fee49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fec00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fee49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fec1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fee68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fec1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fee68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fecc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fed70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fee91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fecc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fed70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fee91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800feb86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fec11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fec64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fec7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fecfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fed20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fedd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fedf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fee0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800feeb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800feb86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fec11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fec64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fec7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fecfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fed20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fedd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fedf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fee0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800feeb0`

## string_xrefs

- `0x1800febd8`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Containers\CmService\Policy`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::PolicyManager::Initialize(
        struct _TP_WAIT **pv,
        const struct Path *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  DWORD LastError; // ebx
  HKEY v10; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  const char *v13; // r9
  struct _TP_WAIT *ThreadpoolWait; // rsi
  const char *v15; // r9
  unsigned int v16; // r8d
  const char *v17; // r9
  char v18; // dl
  char v19; // r8
  HKEY v20; // rcx
  struct _TP_WAIT **v21; // rdi
  struct _TP_WAIT *v22; // r14
  DWORD v23; // ebx
  unsigned int v24; // r8d
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-39h]
  char v27; // [rsp+30h] [rbp-29h] BYREF
  HKEY v28[2]; // [rsp+38h] [rbp-21h]
  const wchar_t *v29; // [rsp+48h] [rbp-11h]
  __int64 v30; // [rsp+50h] [rbp-9h]
  HKEY v31; // [rsp+58h] [rbp-1h] BYREF
  HKEY v32; // [rsp+60h] [rbp+7h]
  char v33; // [rsp+68h] [rbp+Fh]
  void *v34[2]; // [rsp+70h] [rbp+17h] BYREF
  _WORD v35[24]; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  HKEY v37; // [rsp+C8h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+D0h] [rbp+77h] BYREF

  v37 = (HKEY)a2;
  v34[0] = v35;
  v34[1] = v35;
  v35[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v34,
                           Container::Manager::Core::g_registryRoot,
                           ((__int64)off_18021E510 - Container::Manager::Core::g_registryRoot) >> 1) )
  {
    v3 = 67;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\policy.cpp",
      (const char *)0x8007000ELL,
      v26);
    if ( v34[0] != v35 )
      operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v30 = 6;
  v29 = L"Policy";
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v34) )
  {
    v3 = 68;
    goto LABEL_5;
  }
  hKey = 0;
  LOBYTE(v37) = 0;
  v6 = Csl::CreateRegistryKey(v4, v34[0], 131103, &hKey);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\policy.cpp",
      (const char *)(unsigned int)v6,
      (int)&v37);
LABEL_10:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v34[0] != v35 )
      operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
    return v7;
  }
  *(_OWORD *)v28 = 0;
  if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    v37 = 0;
    v8 = Csl::OpenRegistryKey(
           -2147483646,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Containers\\CmService\\Policy",
           131103,
           &v37);
    v7 = v8;
    if ( v8 < 0 )
    {
      if ( v8 != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\policy.cpp",
          (const char *)(unsigned int)v8,
          (int)&v37);
        if ( v37 )
          RegCloseKey(v37);
        goto LABEL_36;
      }
      if ( LOBYTE(v28[1]) )
      {
        if ( v28[0] )
          RegCloseKey(v28[0]);
        LOBYTE(v28[1]) = 0;
      }
      v10 = v37;
    }
    else if ( LOBYTE(v28[1]) )
    {
      if ( v28[0] )
      {
        LastError = GetLastError();
        RegCloseKey(v28[0]);
        SetLastError(LastError);
      }
      v10 = 0;
      v28[0] = v37;
    }
    else
    {
      v10 = 0;
      v28[0] = v37;
      LOBYTE(v28[1]) = 1;
    }
    if ( v10 )
      RegCloseKey(v10);
  }
  v37 = 0;
  v11 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &v37,
          0);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\policy.cpp",
      (const char *)(unsigned int)v11,
      (int)&v37);
    if ( v37 && !CloseHandle(v37) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
LABEL_36:
    if ( LOBYTE(v28[1]) && v28[0] )
      RegCloseKey(v28[0]);
    goto LABEL_10;
  }
  ThreadpoolWait = CreateThreadpoolWait(Container::Manager::Core::Details::PolicyManager::OnPolicyKeyChanged, pv, 0);
  if ( !ThreadpoolWait )
  {
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x72,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\policy.cpp",
           v15);
    if ( v37 && !CloseHandle(v37) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    goto LABEL_36;
  }
  v18 = 0;
  LOBYTE(v29) = 0;
  v19 = 0;
  if ( LOBYTE(v28[1]) )
  {
    v20 = v28[0];
    v18 = 1;
    v19 = 1;
    v28[0] = 0;
  }
  else
  {
    v20 = (HKEY)v29;
  }
  v31 = hKey;
  LOBYTE(v32) = 0;
  v33 = 0;
  if ( v19 )
  {
    v32 = v20;
    v20 = 0;
    v33 = 1;
  }
  if ( v18 && v20 )
    RegCloseKey(v20);
  Csl::RegistryKeyWithOptionalImmutableFallback::operator=(pv, &v31);
  if ( v33 && v32 )
    RegCloseKey(v32);
  if ( v31 )
    RegCloseKey(v31);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    pv + 8,
    v34);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    pv + 3,
    &v37);
  v21 = pv + 4;
  if ( pv + 4 == (struct _TP_WAIT **)&v27 )
  {
    CloseThreadpoolWait(ThreadpoolWait);
  }
  else
  {
    v22 = *v21;
    if ( *v21 )
    {
      v23 = GetLastError();
      CloseThreadpoolWait(v22);
      SetLastError(v23);
    }
    *v21 = ThreadpoolWait;
  }
  if ( v37 && !CloseHandle(v37) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( LOBYTE(v28[1]) && v28[0] )
    RegCloseKey(v28[0]);
  if ( v34[0] != v35 )
    operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x1800fea78  mov     [rsp-8+arg_0], rbx
0x1800fea7d  mov     [rsp-8+arg_8], rdx
0x1800fea82  push    rbp
0x1800fea83  push    rsi
0x1800fea84  push    rdi
0x1800fea85  push    r14
0x1800fea87  push    r15
0x1800fea89  lea     rbp, [rsp-37h]
0x1800fea8e  sub     rsp, 90h
0x1800fea95  mov     rdx, cs:?g_registryRoot@Core@Manager@Container@@3VPath@Csl@@A; Csl::Path Container::Manager::Core::g_registryRoot
0x1800fea9c  lea     rax, [rbp+57h+var_30]
0x1800feaa0  mov     r8, cs:off_18021E510
0x1800feaa7  mov     r14, rcx
0x1800feaaa  mov     [rbp+57h+var_40], rax
0x1800feaae  lea     rcx, [rbp+57h+var_40]
0x1800feab2  sub     r8, rdx
0x1800feab5  lea     rax, [rbp+57h+var_30]
0x1800feab9  xor     r15d, r15d
0x1800feabc  sar     r8, 1
0x1800feabf  mov     [rbp+57h+var_38], rax
0x1800feac3  mov     [rbp+57h+var_30], r15w
0x1800feac8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800feacd  test    al, al
0x1800feacf  jnz     short loc_1800FEAD7
0x1800fead1  lea     edx, [r15+43h]
0x1800fead5  jmp     short loc_1800FEB00
0x1800fead7  lea     rax, aPolicy; "Policy"
0x1800feade  mov     [rbp+57h+var_60], 6
0x1800feae6  lea     rdx, [rbp+57h+var_68]
0x1800feaea  mov     [rbp+57h+var_68], rax
0x1800feaee  lea     rcx, [rbp+57h+var_40]; this
0x1800feaf2  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800feaf7  test    al, al
0x1800feaf9  jnz     short loc_1800FEB39
0x1800feafb  mov     edx, 44h ; 'D'; void *
0x1800feb00  mov     rcx, [rbp+5Fh]; this
0x1800feb04  lea     r8, aOnecoreBaseGen_75; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800feb0b  mov     r9d, 8007000Eh; char *
0x1800feb11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800feb16  mov     rcx, [rbp+57h+var_40]; void *
0x1800feb1a  lea     rax, [rbp+57h+var_30]
0x1800feb1e  cmp     rcx, rax
0x1800feb21  jz      short loc_1800FEB2F
0x1800feb23  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800feb2a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800feb2f  mov     eax, 8007000Eh
0x1800feb34  jmp     loc_1800FEED7
0x1800feb39  mov     rdx, [rbp+57h+var_40]
0x1800feb3d  lea     rax, [rbp+57h+arg_8]
0x1800feb41  mov     edi, 2001Fh
0x1800feb46  mov     [rbp+57h+hKey], r15
0x1800feb4a  mov     r8d, edi
0x1800feb4d  mov     byte ptr [rbp+57h+arg_8], r15b
0x1800feb51  lea     r9, [rbp+57h+hKey]
0x1800feb55  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800feb5a  call    ?CreateRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@AEA_N@Z; Csl::CreateRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &,bool &)
0x1800feb5f  mov     ebx, eax
0x1800feb61  test    eax, eax
0x1800feb63  jns     short loc_1800FEBB2
0x1800feb65  mov     rcx, [rbp+5Fh]; this
0x1800feb69  lea     r8, aOnecoreBaseGen_75; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800feb70  mov     r9d, eax; char *
0x1800feb73  mov     edx, 4Bh ; 'K'; void *
0x1800feb78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800feb7d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800feb81  test    rcx, rcx
0x1800feb84  jz      short loc_1800FEB92
0x1800feb86  call    cs:__imp_RegCloseKey
0x1800feb8d  nop     dword ptr [rax+rax+00h]
0x1800feb92  mov     rcx, [rbp+57h+var_40]; void *
0x1800feb96  lea     rax, [rbp+57h+var_30]
0x1800feb9a  cmp     rcx, rax
0x1800feb9d  jz      short loc_1800FEBAB
0x1800feb9f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800feba6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800febab  mov     eax, ebx
0x1800febad  jmp     loc_1800FEED7
0x1800febb2  xorps   xmm0, xmm0
0x1800febb5  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x1800febb9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800febc0  nop     dword ptr [rax+rax+00h]
0x1800febc5  test    al, al
0x1800febc7  jz      loc_1800FEC89
0x1800febcd  lea     r9, [rbp+57h+arg_8]
0x1800febd1  mov     [rbp+57h+arg_8], r15
0x1800febd5  mov     r8d, edi
0x1800febd8  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800febdf  mov     rcx, 0FFFFFFFF80000002h
0x1800febe6  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800febeb  mov     ebx, eax
0x1800febed  test    eax, eax
0x1800febef  js      short loc_1800FEC49
0x1800febf1  cmp     byte ptr [rbp+57h+var_78+8], r15b
0x1800febf5  jz      short loc_1800FEC38
0x1800febf7  mov     rdi, [rbp+57h+var_78]
0x1800febfb  test    rdi, rdi
0x1800febfe  jz      short loc_1800FEC2B
0x1800fec00  call    cs:__imp_GetLastError
0x1800fec07  nop     dword ptr [rax+rax+00h]
0x1800fec0c  mov     rcx, rdi; hKey
0x1800fec0f  mov     ebx, eax
0x1800fec11  call    cs:__imp_RegCloseKey
0x1800fec18  nop     dword ptr [rax+rax+00h]
0x1800fec1d  mov     ecx, ebx; dwErrCode
0x1800fec1f  call    cs:__imp_SetLastError
0x1800fec26  nop     dword ptr [rax+rax+00h]
0x1800fec2b  mov     rax, [rbp+57h+arg_8]
0x1800fec2f  mov     rcx, r15
0x1800fec32  mov     [rbp+57h+var_78], rax
0x1800fec36  jmp     short loc_1800FEC78
0x1800fec38  mov     rax, [rbp+57h+arg_8]
0x1800fec3c  mov     rcx, r15
0x1800fec3f  mov     [rbp+57h+var_78], rax
0x1800fec43  mov     byte ptr [rbp+57h+var_78+8], 1
0x1800fec47  jmp     short loc_1800FEC78
0x1800fec49  cmp     ebx, 80070002h
0x1800fec4f  jnz     loc_1800FECDC
0x1800fec55  cmp     byte ptr [rbp+57h+var_78+8], r15b
0x1800fec59  jz      short loc_1800FEC74
0x1800fec5b  mov     rcx, [rbp+57h+var_78]; hKey
0x1800fec5f  test    rcx, rcx
0x1800fec62  jz      short loc_1800FEC70
0x1800fec64  call    cs:__imp_RegCloseKey
0x1800fec6b  nop     dword ptr [rax+rax+00h]
0x1800fec70  mov     byte ptr [rbp+57h+var_78+8], r15b
0x1800fec74  mov     rcx, [rbp+57h+arg_8]; hKey
0x1800fec78  test    rcx, rcx
0x1800fec7b  jz      short loc_1800FEC89
0x1800fec7d  call    cs:__imp_RegCloseKey
0x1800fec84  nop     dword ptr [rax+rax+00h]
0x1800fec89  xor     r9d, r9d
0x1800fec8c  mov     [rbp+57h+arg_8], r15
0x1800fec90  xor     edx, edx
0x1800fec92  lea     rcx, [rbp+57h+arg_8]
0x1800fec96  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800fec9b  mov     ebx, eax
0x1800fec9d  test    eax, eax
0x1800fec9f  jns     loc_1800FED31
0x1800feca5  mov     rcx, [rbp+5Fh]; this
0x1800feca9  lea     r8, aOnecoreBaseGen_75; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fecb0  mov     r9d, eax; char *
0x1800fecb3  mov     edx, 6Ch ; 'l'; void *
0x1800fecb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fecbd  mov     rcx, [rbp+57h+arg_8]; hObject
0x1800fecc1  test    rcx, rcx
0x1800fecc4  jz      short loc_1800FED09
0x1800fecc6  call    cs:__imp_CloseHandle
0x1800feccd  nop     dword ptr [rax+rax+00h]
0x1800fecd2  test    eax, eax
0x1800fecd4  jz      loc_1800FEEFE
0x1800fecda  jmp     short loc_1800FED09
0x1800fecdc  mov     rcx, [rbp+5Fh]; this
0x1800fece0  lea     r8, aOnecoreBaseGen_75; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fece7  mov     r9d, ebx; char *
0x1800fecea  mov     edx, 66h ; 'f'; void *
0x1800fecef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fecf4  mov     rcx, [rbp+57h+arg_8]; hKey
0x1800fecf8  test    rcx, rcx
0x1800fecfb  jz      short loc_1800FED09
0x1800fecfd  call    cs:__imp_RegCloseKey
0x1800fed04  nop     dword ptr [rax+rax+00h]
0x1800fed09  cmp     byte ptr [rbp+57h+var_78+8], r15b
0x1800fed0d  jz      loc_1800FEB7D
0x1800fed13  mov     rcx, [rbp+57h+var_78]; hKey
0x1800fed17  test    rcx, rcx
0x1800fed1a  jz      loc_1800FEB7D
0x1800fed20  call    cs:__imp_RegCloseKey
0x1800fed27  nop     dword ptr [rax+rax+00h]
0x1800fed2c  jmp     loc_1800FEB7D
0x1800fed31  xor     r8d, r8d; pcbe
0x1800fed34  lea     rcx, ?OnPolicyKeyChanged@PolicyManager@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800fed3b  mov     rdx, r14; pv
0x1800fed3e  call    cs:__imp_CreateThreadpoolWait
0x1800fed45  nop     dword ptr [rax+rax+00h]
0x1800fed4a  mov     rsi, rax
0x1800fed4d  test    rax, rax
0x1800fed50  jnz     short loc_1800FED86
0x1800fed52  mov     rcx, [rbp+5Fh]; this
0x1800fed56  lea     r8, aOnecoreBaseGen_75; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fed5d  lea     edx, [rax+72h]; void *
0x1800fed60  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800fed65  mov     rcx, [rbp+57h+arg_8]; hObject
0x1800fed69  mov     ebx, eax
0x1800fed6b  test    rcx, rcx
0x1800fed6e  jz      short loc_1800FED09
0x1800fed70  call    cs:__imp_CloseHandle
0x1800fed77  nop     dword ptr [rax+rax+00h]
0x1800fed7c  test    eax, eax
0x1800fed7e  jz      loc_1800FEF0D
0x1800fed84  jmp     short loc_1800FED09
0x1800fed86  mov     dl, r15b
0x1800fed89  mov     byte ptr [rbp+57h+var_68], r15b
0x1800fed8d  mov     r8b, r15b
0x1800fed90  cmp     byte ptr [rbp+57h+var_78+8], r15b
0x1800fed94  jz      short loc_1800FEDA5
0x1800fed96  mov     rcx, [rbp+57h+var_78]
0x1800fed9a  mov     dl, 1
0x1800fed9c  mov     r8b, dl
0x1800fed9f  mov     [rbp+57h+var_78], r15
0x1800feda3  jmp     short loc_1800FEDA9
0x1800feda5  mov     rcx, [rbp+57h+var_68]
0x1800feda9  mov     rax, [rbp+57h+hKey]
0x1800fedad  mov     [rbp+57h+var_58], rax
0x1800fedb1  mov     byte ptr [rbp+57h+var_50], r15b
0x1800fedb5  mov     [rbp+57h+var_48], r15b
0x1800fedb9  test    r8b, r8b
0x1800fedbc  jz      short loc_1800FEDC9
0x1800fedbe  mov     [rbp+57h+var_50], rcx
0x1800fedc2  mov     rcx, r15; hKey
0x1800fedc5  mov     [rbp+57h+var_48], 1
0x1800fedc9  test    dl, dl
0x1800fedcb  jz      short loc_1800FEDDE
0x1800fedcd  test    rcx, rcx
0x1800fedd0  jz      short loc_1800FEDDE
0x1800fedd2  call    cs:__imp_RegCloseKey
0x1800fedd9  nop     dword ptr [rax+rax+00h]
0x1800fedde  lea     rdx, [rbp+57h+var_58]
0x1800fede2  mov     rcx, r14
0x1800fede5  call    ??4RegistryKeyWithOptionalImmutableFallback@Csl@@QEAAAEAV01@$$QEAV01@@Z; Csl::RegistryKeyWithOptionalImmutableFallback::operator=(Csl::RegistryKeyWithOptionalImmutableFallback &&)
0x1800fedea  cmp     [rbp+57h+var_48], r15b
0x1800fedee  jz      short loc_1800FEE05
0x1800fedf0  mov     rcx, [rbp+57h+var_50]; hKey
0x1800fedf4  test    rcx, rcx
0x1800fedf7  jz      short loc_1800FEE05
0x1800fedf9  call    cs:__imp_RegCloseKey
0x1800fee00  nop     dword ptr [rax+rax+00h]
0x1800fee05  mov     rcx, [rbp+57h+var_58]; hKey
0x1800fee09  test    rcx, rcx
0x1800fee0c  jz      short loc_1800FEE1A
0x1800fee0e  call    cs:__imp_RegCloseKey
0x1800fee15  nop     dword ptr [rax+rax+00h]
0x1800fee1a  lea     rcx, [r14+40h]
0x1800fee1e  lea     rdx, [rbp+57h+var_40]
0x1800fee22  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800fee27  lea     rcx, [r14+18h]
0x1800fee2b  lea     rdx, [rbp+57h+arg_8]
0x1800fee2f  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x1800fee34  lea     rax, [rbp+57h+var_80]
0x1800fee38  lea     rdi, [r14+20h]
0x1800fee3c  cmp     rdi, rax
0x1800fee3f  jz      short loc_1800FEE79
0x1800fee41  mov     r14, [rdi]
0x1800fee44  test    r14, r14
0x1800fee47  jz      short loc_1800FEE74
0x1800fee49  call    cs:__imp_GetLastError
0x1800fee50  nop     dword ptr [rax+rax+00h]
0x1800fee55  mov     rcx, r14; pwa
0x1800fee58  mov     ebx, eax
0x1800fee5a  call    cs:__imp_CloseThreadpoolWait
0x1800fee61  nop     dword ptr [rax+rax+00h]
0x1800fee66  mov     ecx, ebx; dwErrCode
0x1800fee68  call    cs:__imp_SetLastError
0x1800fee6f  nop     dword ptr [rax+rax+00h]
0x1800fee74  mov     [rdi], rsi
0x1800fee77  jmp     short loc_1800FEE88
0x1800fee79  mov     rcx, rsi; pwa
0x1800fee7c  call    cs:__imp_CloseThreadpoolWait
0x1800fee83  nop     dword ptr [rax+rax+00h]
0x1800fee88  mov     rcx, [rbp+57h+arg_8]; hObject
0x1800fee8c  test    rcx, rcx
0x1800fee8f  jz      short loc_1800FEEA1
0x1800fee91  call    cs:__imp_CloseHandle
0x1800fee98  nop     dword ptr [rax+rax+00h]
0x1800fee9d  test    eax, eax
0x1800fee9f  jz      short loc_1800FEEEF
0x1800feea1  cmp     byte ptr [rbp+57h+var_78+8], r15b
0x1800feea5  jz      short loc_1800FEEBC
0x1800feea7  mov     rcx, [rbp+57h+var_78]; hKey
0x1800feeab  test    rcx, rcx
0x1800feeae  jz      short loc_1800FEEBC
0x1800feeb0  call    cs:__imp_RegCloseKey
0x1800feeb7  nop     dword ptr [rax+rax+00h]
0x1800feebc  mov     rcx, [rbp+57h+var_40]; void *
0x1800feec0  lea     rax, [rbp+57h+var_30]
0x1800feec4  cmp     rcx, rax
0x1800feec7  jz      short loc_1800FEED5
0x1800feec9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800feed0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800feed5  xor     eax, eax
0x1800feed7  mov     rbx, [rsp+0B0h+arg_0]
0x1800feedf  add     rsp, 90h
0x1800feee6  pop     r15
0x1800feee8  pop     r14
0x1800feeea  pop     rdi
0x1800feeeb  pop     rsi
0x1800feeec  pop     rbp
0x1800feeed  retn
0x1800feeef  mov     rcx, [rbp+5Fh]; this
0x1800feef3  mov     edx, 0A0Bh; void *
0x1800feef8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800feefe  mov     rcx, [rbp+5Fh]; this
0x1800fef02  mov     edx, 0A0Bh; void *
0x1800fef07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800fef0d  mov     rcx, [rbp+5Fh]; this
0x1800fef11  mov     edx, 0A0Bh; void *
0x1800fef16  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
