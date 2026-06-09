# Discovery::Execute(ActivityContext *)

- ea: `0x180077540`
- end: `0x180077992`
- name: `?Execute@Discovery@@UEAAJPEAVActivityContext@@@Z`
- size: `1106`
- prototype: `int(Discovery *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006950`
- `0x18000de50`
- `0x180010fcc`
- `0x180011938`
- `0x180019e8c`
- `0x18001a86c`
- `0x18001ac7c`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18003ebe0`
- `0x180041420`
- `0x180041490`
- `0x1800414fc`
- `0x1800415f4`
- `0x1800460a4`
- `0x18005ff20`
- `0x180072d44`
- `0x180077540`
- `0x180077af0`
- `0x180077ca0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800775a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180077626`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800775a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180077626`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x1800777ce`
- `omadmapi!__imp_OmaDmCreateInternalAcctID` at `0x1800777ce`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x18007778c`
- `ext-ms-win-devmgmt-dm-l1-1-2!Mmpc_Lockdown_IsLockedToMmpc` at `0x18007778c`

## string_xrefs

- `0x1800776a2`: `DiscoveryServiceFullURL`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Discovery::Execute(Discovery *this, struct ActivityContext *a2)
{
  int v3; // esi
  int v4; // r15d
  char *v5; // r14
  __int64 v6; // rdx
  CEnrollmentLogger *Logger; // rax
  int v8; // eax
  int v9; // r12d
  int EnrollmentType; // eax
  int IsLockedToMmpc; // ebx
  int EnrollmentString; // eax
  const unsigned __int16 *CorrelationID; // r14
  __int64 v14; // rdx
  Discovery *v15; // rcx
  int MmpcDiscoveryData; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v19; // [rsp+70h] [rbp-90h] BYREF
  int v20; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v21; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int16 *v22[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v23; // [rsp+90h] [rbp-70h] BYREF
  int v24; // [rsp+A0h] [rbp-60h] BYREF
  int v25; // [rsp+A4h] [rbp-5Ch] BYREF
  int v26; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v27; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v28; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v29; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v30; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v31; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v32; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v33[40]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v28 = 0;
  v20 = 0;
  v27 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v32 = 0;
  v3 = 0;
  v4 = 0;
  v5 = (char *)a2 + 448;
  if ( !(unsigned int)_o__wcsnicmp((char *)a2 + 448) )
  {
    ActivityContext::get_KeyAsString(a2, v33);
    v19 = 0;
    v23 = *(struct _GUID *)((char *)a2 + 8);
    EEDBManager::GetEnrollmentString(&v23, L"ProviderID", &v19);
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogRenewalEvent(Logger, v33, v19);
    v4 = 1;
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v19);
  }
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RecoveryFix55718774>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RecoveryFix55718774>::GetImpl'::`2'::impl,
    v6);
  v8 = _o__wcsnicmp(v5);
  v9 = v8;
  if ( !v4 && v8 )
  {
    IsLockedToMmpc = 1;
LABEL_11:
    v23 = *(struct _GUID *)((char *)a2 + 8);
    EnrollmentString = EEDBManager::GetEnrollmentString(&v23, L"DiscoveryServiceFullURL", &v28);
    if ( EnrollmentString < 0 )
      goto LABEL_12;
    v23 = *(struct _GUID *)((char *)a2 + 8);
    EEDBManager::GetEnrollmentString(&v23, L"AADTenantID", &v31);
    if ( *((char *)a2 + 72) < 0 )
    {
      ActivityContext::set_EnrollmentServiceFullURL(a2, v28);
      goto LABEL_40;
    }
    v23 = *(struct _GUID *)((char *)a2 + 8);
    EnrollmentString = EEDBManager::GetEnrollmentAuthPolicy(&v23, (enum MDMAuthPolicy *)&v20);
    if ( EnrollmentString < 0
      || ((unsigned int)(v20 - 1) <= 1
       || (v23 = *(struct _GUID *)((char *)a2 + 8), EEDBManager::GetEnrollmentString(&v23, L"DomainUsername", &v27) < 0))
      && (v23 = *(struct _GUID *)((char *)a2 + 8),
          EnrollmentString = EEDBManager::GetEnrollmentString(&v23, L"UPN", &v27),
          EnrollmentString < 0) )
    {
LABEL_12:
      IsLockedToMmpc = EnrollmentString;
      goto LABEL_40;
    }
    v19 = 0;
    v23 = *(struct _GUID *)((char *)a2 + 8);
    EEDBManager::GetEnrollmentString(&v23, L"SID", &v19);
    v21 = 0;
    v25 = 0;
    IsLockedToMmpc = Mmpc_Lockdown_IsLockedToMmpc(&v25);
    if ( (int)(IsLockedToMmpc + 0x80000000) >= 0 && IsLockedToMmpc != -2147024769 )
    {
LABEL_39:
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v19);
      goto LABEL_40;
    }
    v22[0] = 0;
    if ( ActivityContext::get_CorrelationID(a2) )
    {
      CorrelationID = ActivityContext::get_CorrelationID(a2);
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v22,
        0);
      IsLockedToMmpc = OmaDmCreateInternalAcctID(0, v22);
      if ( IsLockedToMmpc < 0 )
        goto LABEL_38;
      CorrelationID = v22[0];
    }
    v26 = 0;
    IsLockedToMmpc = Mmpc_IsOnPremiseSupportingDevice(&v26);
    if ( IsLockedToMmpc >= 0 )
    {
      LOBYTE(v14) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_RecoveryFix55718774>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_RecoveryFix55718774>::GetImpl'::`2'::impl,
        v14);
      if ( !v25 && !v26 )
      {
        if ( v4 && v3 )
          goto LABEL_35;
        if ( v9 || !v3 )
          goto LABEL_34;
      }
      if ( v4 && !v3 )
      {
LABEL_34:
        MmpcDiscoveryData = DiscoverEndpointEx2(
                              v19,
                              v28,
                              v27,
                              v31,
                              CorrelationID,
                              3,
                              *((_DWORD *)a2 + 18) & 0x100000,
                              &v21,
                              &v20,
                              &v30,
                              &v29,
                              &v32,
                              0);
        goto LABEL_36;
      }
LABEL_35:
      MmpcDiscoveryData = Discovery::GetMmpcDiscoveryData(
                            v15,
                            v27,
                            v19,
                            v31,
                            CorrelationID,
                            v28,
                            &v21,
                            (enum MDMAuthPolicy *)&v20,
                            &v30,
                            &v29,
                            &v32);
LABEL_36:
      IsLockedToMmpc = MmpcDiscoveryData;
      if ( MmpcDiscoveryData >= 0 )
      {
        ActivityContext::set_PolicyServiceFullURL(a2, v30);
        ActivityContext::set_EnrollmentServiceFullURL(a2, v29);
        *((_DWORD *)a2 + 18) |= v21;
        ActivityContext::set_CorrelationID(a2, CorrelationID);
      }
    }
LABEL_38:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v22);
    goto LABEL_39;
  }
  v24 = 63;
  v23 = *(struct _GUID *)((char *)a2 + 8);
  EnrollmentType = EEDBManager::GetEnrollmentType(&v23, (enum EnrollmentEnrollType *)&v24);
  IsLockedToMmpc = EnrollmentType;
  if ( EnrollmentType >= 0 )
  {
    IsLockedToMmpc = 1;
    if ( ((v24 - 24) & 0xFFFFFFFD) == 0 )
      v3 = 1;
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5C,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmenroll\\discovery.cpp",
    (const char *)(unsigned int)EnrollmentType,
    v18);
LABEL_40:
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v32);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v29);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v30);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v31);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v27);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v28);
  return (unsigned int)IsLockedToMmpc;
}

```

## disassembly

```asm
0x180077540  push    rbp
0x180077542  push    rbx
0x180077543  push    rsi
0x180077544  push    rdi
0x180077545  push    r12
0x180077547  push    r13
0x180077549  push    r14
0x18007754b  push    r15
0x18007754d  lea     rbp, [rsp-48h]
0x180077552  sub     rsp, 148h
0x180077559  mov     rax, cs:__security_cookie
0x180077560  xor     rax, rsp
0x180077563  mov     [rbp+80h+var_50], rax
0x180077567  mov     rdi, rdx
0x18007756a  xor     r13d, r13d
0x18007756d  mov     [rbp+80h+var_C8], r13
0x180077571  mov     [rsp+180h+var_108], r13d
0x180077576  mov     [rbp+80h+var_D0], r13
0x18007757a  mov     [rbp+80h+var_B0], r13
0x18007757e  mov     [rbp+80h+var_B8], r13
0x180077582  mov     [rbp+80h+var_C0], r13
0x180077586  mov     [rbp+80h+var_A8], r13
0x18007758a  mov     esi, r13d
0x18007758d  mov     r15d, r13d
0x180077590  lea     r14, [rdx+1C0h]
0x180077597  mov     r8d, 104h
0x18007759d  mov     rdx, cs:off_1800AF248; "OR_RENEW"
0x1800775a4  mov     rcx, r14
0x1800775a7  call    cs:__imp__o__wcsnicmp
0x1800775ad  lea     r12d, [r13+1]
0x1800775b1  test    eax, eax
0x1800775b3  jnz     short loc_180077607
0x1800775b5  lea     rdx, [rbp+80h+var_A0]; unsigned __int16 *
0x1800775b9  mov     rcx, rdi; this
0x1800775bc  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x1800775c1  mov     [rsp+180h+var_110], r13
0x1800775c6  movups  xmm0, xmmword ptr [rdi+8]
0x1800775ca  movdqu  xmmword ptr [rbp+80h+var_F0.Data1], xmm0
0x1800775cf  lea     r8, [rsp+180h+var_110]; unsigned __int16 **
0x1800775d4  lea     rdx, aProviderid; "ProviderID"
0x1800775db  lea     rcx, [rbp+80h+var_F0]; struct _GUID
0x1800775df  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x1800775e4  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800775e9  mov     r8, [rsp+180h+var_110]; unsigned __int16 *
0x1800775ee  lea     rdx, [rbp+80h+var_A0]; unsigned __int16 *
0x1800775f2  mov     rcx, rax; this
0x1800775f5  call    ?LogRenewalEvent@CEnrollmentLogger@@QEAAXPEBG0@Z; CEnrollmentLogger::LogRenewalEvent(ushort const *,ushort const *)
0x1800775fa  mov     r15d, r12d
0x1800775fd  lea     rcx, [rsp+180h+var_110]
0x180077602  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180077607  mov     dl, r12b
0x18007760a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RecoveryFix55718774@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RecoveryFix55718774@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RecoveryFix55718774> `wil::Feature<__WilFeatureTraits_Feature_RecoveryFix55718774>::GetImpl(void)'::`2'::impl
0x180077611  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RecoveryFix55718774@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RecoveryFix55718774>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180077616  mov     r8d, 104h
0x18007761c  mov     rdx, cs:off_1800AF2C8; "OR_MDMRECOVERY"
0x180077623  mov     rcx, r14
0x180077626  call    cs:__imp__o__wcsnicmp
0x18007762c  mov     r12d, eax
0x18007762f  test    r15d, r15d
0x180077632  jnz     short loc_180077638
0x180077634  test    eax, eax
0x180077636  jnz     short loc_180077690
0x180077638  mov     [rbp+80h+var_E0], 3Fh ; '?'
0x18007763f  movups  xmm0, xmmword ptr [rdi+8]
0x180077643  movdqu  xmmword ptr [rbp+80h+var_F0.Data1], xmm0
0x180077648  lea     rdx, [rbp+80h+var_E0]; enum EnrollmentEnrollType *
0x18007764c  lea     rcx, [rbp+80h+var_F0]; struct _GUID
0x180077650  call    ?GetEnrollmentType@EEDBManager@@SAJU_GUID@@PEAW4EnrollmentEnrollType@@@Z; EEDBManager::GetEnrollmentType(_GUID,EnrollmentEnrollType *)
0x180077655  mov     ebx, eax
0x180077657  test    eax, eax
0x180077659  jns     short loc_18007767B
0x18007765b  mov     rcx, [rbp+88h]; this
0x180077662  mov     r9d, eax; char *
0x180077665  lea     r8, aOnecoreuapAdmi_24; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18007766c  mov     edx, 5Ch ; '\'; void *
0x180077671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077676  jmp     loc_180077935
0x18007767b  mov     eax, [rbp+80h+var_E0]
0x18007767e  add     eax, 0FFFFFFE8h
0x180077681  test    eax, 0FFFFFFFDh
0x180077686  mov     ebx, 1
0x18007768b  cmovz   esi, ebx
0x18007768e  jmp     short loc_180077695
0x180077690  mov     ebx, 1
0x180077695  movups  xmm0, xmmword ptr [rdi+8]
0x180077699  movdqu  xmmword ptr [rbp+80h+var_F0.Data1], xmm0
0x18007769e  lea     r8, [rbp+80h+var_C8]; unsigned __int16 **
0x1800776a2  lea     rdx, aDiscoveryservi; "DiscoveryServiceFullURL"
0x1800776a9  lea     rcx, [rbp+80h+var_F0]; struct _GUID
0x1800776ad  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x1800776b2  test    eax, eax
0x1800776b4  jns     short loc_1800776BD
0x1800776b6  mov     ebx, eax
0x1800776b8  jmp     loc_180077935
0x1800776bd  movups  xmm0, xmmword ptr [rdi+8]
0x1800776c1  movdqu  xmmword ptr [rbp+80h+var_F0.Data1], xmm0
0x1800776c6  lea     r8, [rbp+80h+var_B0]; unsigned __int16 **
0x1800776ca  lea     rdx, aAadtenantid; "AADTenantID"
0x1800776d1  lea     rcx, [rbp+80h+var_F0]; struct _GUID
0x1800776d5  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x1800776da  test    byte ptr [rdi+48h], 80h
0x1800776de  jz      short loc_1800776F1
0x1800776e0  mov     rdx, [rbp+80h+var_C8]; unsigned __int16 *
0x1800776e4  mov     rcx, rdi; this
0x1800776e7  call    ?set_EnrollmentServiceFullURL@ActivityContext@@QEAAXPEBG@Z; ActivityContext::set_EnrollmentServiceFullURL(ushort const *)
0x1800776ec  jmp     loc_180077935
0x1800776f1  movups  xmm0, xmmword ptr [rdi+8]
0x1800776f5  movdqu  xmmword ptr [rbp+80h+var_F0.Data1], xmm0
0x1800776fa  lea     rdx, [rsp+180h+var_108]; enum MDMAuthPolicy *
0x1800776ff  lea     rcx, [rbp+80h+var_F0]; struct _GUID
0x180077703  call    ?GetEnrollmentAuthPolicy@EEDBManager@@SAJU_GUID@@PEAW4MDMAuthPolicy@@@Z; EEDBManager::GetEnrollmentAuthPolicy(_GUID,MDMAuthPolicy *)
0x180077708  test    eax, eax
0x18007770a  js      short loc_1800776B6
0x18007770c  mov     eax, [rsp+180h+var_108]
0x180077710  dec     eax
0x180077712  cmp     eax, ebx
0x180077714  jbe     short loc_180077737
0x180077716  movups  xmm0, xmmword ptr [rdi+8]
0x18007771a  movdqu  xmmword ptr [rbp+80h+var_F0.Data1], xmm0
0x18007771f  lea     r8, [rbp+80h+var_D0]; unsigned __int16 **
0x180077723  lea     rdx, aDomainusername; "DomainUsername"
0x18007772a  lea     rcx, [rbp+80h+var_F0]; struct _GUID
0x18007772e  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x180077733  test    eax, eax
0x180077735  jns     short loc_18007775C
0x180077737  movups  xmm0, xmmword ptr [rdi+8]
0x18007773b  movdqu  xmmword ptr [rbp+80h+var_F0.Data1], xmm0
0x180077740  lea     r8, [rbp+80h+var_D0]; unsigned __int16 **
0x180077744  lea     rdx, aUpn; "UPN"
0x18007774b  lea     rcx, [rbp+80h+var_F0]; struct _GUID
0x18007774f  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x180077754  test    eax, eax
0x180077756  js      loc_1800776B6
0x18007775c  mov     [rsp+180h+var_110], r13
0x180077761  movups  xmm0, xmmword ptr [rdi+8]
0x180077765  movdqu  xmmword ptr [rbp+80h+var_F0.Data1], xmm0
0x18007776a  lea     r8, [rsp+180h+var_110]; unsigned __int16 **
0x18007776f  lea     rdx, aSid; "SID"
0x180077776  lea     rcx, [rbp+80h+var_F0]; struct _GUID
0x18007777a  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18007777f  mov     [rsp+180h+var_104], r13d
0x180077784  mov     [rbp+80h+var_DC], r13d
0x180077788  lea     rcx, [rbp+80h+var_DC]
0x18007778c  call    cs:__imp_Mmpc_Lockdown_IsLockedToMmpc
0x180077792  mov     ebx, eax
0x180077794  mov     eax, 80000000h
0x180077799  lea     ecx, [rbx+rax]
0x18007779c  test    eax, ecx
0x18007779e  jnz     short loc_1800777AC
0x1800777a0  cmp     ebx, 8007007Fh
0x1800777a6  jnz     loc_18007792A
0x1800777ac  mov     [rbp+80h+var_100], r13
0x1800777b0  mov     rcx, rdi; this
0x1800777b3  call    ?get_CorrelationID@ActivityContext@@QEBAPEBGXZ; ActivityContext::get_CorrelationID(void)
0x1800777b8  test    rax, rax
0x1800777bb  jnz     short loc_1800777E4
0x1800777bd  xor     edx, edx
0x1800777bf  lea     rcx, [rbp+80h+var_100]
0x1800777c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800777c8  lea     rdx, [rbp+80h+var_100]
0x1800777cc  xor     ecx, ecx
0x1800777ce  call    cs:__imp_OmaDmCreateInternalAcctID
0x1800777d4  mov     ebx, eax
0x1800777d6  test    eax, eax
0x1800777d8  js      loc_180077920
0x1800777de  mov     r14, [rbp+80h+var_100]
0x1800777e2  jmp     short loc_1800777EF
0x1800777e4  mov     rcx, rdi; this
0x1800777e7  call    ?get_CorrelationID@ActivityContext@@QEBAPEBGXZ; ActivityContext::get_CorrelationID(void)
0x1800777ec  mov     r14, rax
0x1800777ef  mov     [rbp+80h+var_D8], r13d
0x1800777f3  lea     rcx, [rbp+80h+var_D8]; int *
0x1800777f7  call    ?Mmpc_IsOnPremiseSupportingDevice@@YAJPEAH@Z; Mmpc_IsOnPremiseSupportingDevice(int *)
0x1800777fc  mov     ebx, eax
0x1800777fe  test    eax, eax
0x180077800  js      loc_180077920
0x180077806  mov     dl, 1
0x180077808  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RecoveryFix55718774@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RecoveryFix55718774@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RecoveryFix55718774> `wil::Feature<__WilFeatureTraits_Feature_RecoveryFix55718774>::GetImpl(void)'::`2'::impl
0x18007780f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RecoveryFix55718774@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RecoveryFix55718774>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180077814  cmp     [rbp+80h+var_DC], r13d
0x180077818  jnz     short loc_180077832
0x18007781a  cmp     [rbp+80h+var_D8], r13d
0x18007781e  jnz     short loc_180077832
0x180077820  test    r15d, r15d
0x180077823  jz      short loc_180077829
0x180077825  test    esi, esi
0x180077827  jnz     short loc_1800778A0
0x180077829  test    r12d, r12d
0x18007782c  jnz     short loc_18007783B
0x18007782e  test    esi, esi
0x180077830  jz      short loc_18007783B
0x180077832  test    r15d, r15d
0x180077835  jz      short loc_1800778A0
0x180077837  test    esi, esi
0x180077839  jnz     short loc_1800778A0
0x18007783b  mov     eax, [rdi+48h]
0x18007783e  and     eax, 100000h
0x180077843  mov     [rsp+180h+var_120], r13
0x180077848  lea     rcx, [rbp+80h+var_A8]
0x18007784c  mov     [rsp+180h+var_128], rcx
0x180077851  lea     rcx, [rbp+80h+var_C0]
0x180077855  mov     [rsp+180h+var_130], rcx
0x18007785a  lea     rcx, [rbp+80h+var_B8]
0x18007785e  mov     [rsp+180h+var_138], rcx
0x180077863  lea     rcx, [rsp+180h+var_108]
0x180077868  mov     [rsp+180h+var_140], rcx
0x18007786d  lea     rcx, [rsp+180h+var_104]
0x180077872  mov     [rsp+180h+var_148], rcx
0x180077877  mov     dword ptr [rsp+180h+var_150], eax
0x18007787b  mov     dword ptr [rsp+180h+var_158], 3
0x180077883  mov     [rsp+180h+var_160], r14
0x180077888  mov     r9, [rbp+80h+var_B0]
0x18007788c  mov     r8, [rbp+80h+var_D0]
0x180077890  mov     rdx, [rbp+80h+var_C8]
0x180077894  mov     rcx, [rsp+180h+var_110]
0x180077899  call    DiscoverEndpointEx2
0x18007789e  jmp     short loc_1800778EF
0x1800778a0  lea     rax, [rbp+80h+var_A8]
0x1800778a4  mov     [rsp+180h+var_130], rax; unsigned __int16 **
0x1800778a9  lea     rax, [rbp+80h+var_C0]
0x1800778ad  mov     [rsp+180h+var_138], rax; unsigned __int16 **
0x1800778b2  lea     rax, [rbp+80h+var_B8]
0x1800778b6  mov     [rsp+180h+var_140], rax; unsigned __int16 **
0x1800778bb  lea     rax, [rsp+180h+var_108]
0x1800778c0  mov     [rsp+180h+var_148], rax; enum MDMAuthPolicy *
0x1800778c5  lea     rax, [rsp+180h+var_104]
0x1800778ca  mov     [rsp+180h+var_150], rax; unsigned int *
0x1800778cf  mov     rax, [rbp+80h+var_C8]
0x1800778d3  mov     [rsp+180h+var_158], rax; unsigned __int16 *
0x1800778d8  mov     [rsp+180h+var_160], r14; unsigned __int16 *
0x1800778dd  mov     r9, [rbp+80h+var_B0]; unsigned __int16 *
0x1800778e1  mov     r8, [rsp+180h+var_110]; unsigned __int16 *
0x1800778e6  mov     rdx, [rbp+80h+var_D0]; unsigned __int16 *
0x1800778ea  call    ?GetMmpcDiscoveryData@Discovery@@AEBAJPEBG0000PEAKPEAW4MDMAuthPolicy@@PEAPEAG33@Z; Discovery::GetMmpcDiscoveryData(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong *,MDMAuthPolicy *,ushort * *,ushort * *,ushort * *)
0x1800778ef  mov     ebx, eax
0x1800778f1  test    eax, eax
0x1800778f3  js      short loc_180077920
0x1800778f5  mov     rdx, [rbp+80h+var_B8]; unsigned __int16 *
0x1800778f9  mov     rcx, rdi; this
0x1800778fc  call    ?set_PolicyServiceFullURL@ActivityContext@@QEAAXPEBG@Z; ActivityContext::set_PolicyServiceFullURL(ushort const *)
0x180077901  mov     rdx, [rbp+80h+var_C0]; unsigned __int16 *
0x180077905  mov     rcx, rdi; this
0x180077908  call    ?set_EnrollmentServiceFullURL@ActivityContext@@QEAAXPEBG@Z; ActivityContext::set_EnrollmentServiceFullURL(ushort const *)
0x18007790d  mov     eax, [rsp+180h+var_104]
0x180077911  or      [rdi+48h], eax
0x180077914  mov     rdx, r14; unsigned __int16 *
0x180077917  mov     rcx, rdi; this
0x18007791a  call    ?set_CorrelationID@ActivityContext@@QEAAXPEBG@Z; ActivityContext::set_CorrelationID(ushort const *)
0x18007791f  nop
0x180077920  lea     rcx, [rbp+80h+var_100]
0x180077924  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180077929  nop
0x18007792a  lea     rcx, [rsp+180h+var_110]
0x18007792f  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180077934  nop
0x180077935  lea     rcx, [rbp+80h+var_A8]
0x180077939  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18007793e  nop
0x18007793f  lea     rcx, [rbp+80h+var_C0]
0x180077943  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180077948  nop
0x180077949  lea     rcx, [rbp+80h+var_B8]
0x18007794d  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180077952  nop
0x180077953  lea     rcx, [rbp+80h+var_B0]
0x180077957  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18007795c  nop
0x18007795d  lea     rcx, [rbp+80h+var_D0]
0x180077961  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180077966  nop
0x180077967  lea     rcx, [rbp+80h+var_C8]
0x18007796b  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180077970  mov     eax, ebx
0x180077972  mov     rcx, [rbp+80h+var_50]
0x180077976  xor     rcx, rsp; StackCookie
0x180077979  call    __security_check_cookie
0x18007797e  add     rsp, 148h
0x180077985  pop     r15
0x180077987  pop     r14
0x180077989  pop     r13
0x18007798b  pop     r12
0x18007798d  pop     rdi
0x18007798e  pop     rsi
0x18007798f  pop     rbx
0x180077990  pop     rbp
0x180077991  retn
```
