# ProvOperations::RemoveResourceManagerPackageMetadataForCsp(ushort const *,ushort const *)

- ea: `0x180017380`
- end: `0x1800175c1`
- name: `?RemoveResourceManagerPackageMetadataForCsp@ProvOperations@@UEAAJPEBG0@Z`
- size: `577`
- prototype: `__int64 __fastcall(ProvOperations *this, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180007674`
- `0x18000ca00`
- `0x18000d1e4`
- `0x18000e398`
- `0x1800122e4`
- `0x180017380`
- `0x1800187a4`
- `0x180019238`
- `0x1800210f0`
- `0x180022784`
- `0x18002bddc`
- `0x18002cef4`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180017518`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017518`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18001747a`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18001747a`

## string_xrefs

- `0x18001740b`: `Security`
- `0x180017429`: `AllowRemoveProvisioningPackage`

## pseudocode

```c
__int64 __fastcall ProvOperations::RemoveResourceManagerPackageMetadataForCsp(
        ProvOperations *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // rdi
  int PolicyInt; // eax
  unsigned int v7; // edi
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  wil *v12; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-278h] BYREF
  unsigned int v18; // [rsp+24h] [rbp-274h]
  unsigned __int16 *v19; // [rsp+28h] [rbp-270h]
  _QWORD *v20; // [rsp+30h] [rbp-268h]
  char v21; // [rsp+38h] [rbp-260h]
  void *v22; // [rsp+40h] [rbp-258h] BYREF
  __int64 v23; // [rsp+50h] [rbp-248h]
  unsigned __int64 v24; // [rsp+58h] [rbp-240h]
  _BYTE v25[96]; // [rsp+60h] [rbp-238h] BYREF
  _QWORD v26[42]; // [rsp+C0h] [rbp-1D8h] BYREF
  __int128 v27; // [rsp+210h] [rbp-88h] BYREF
  wchar_t v28; // [rsp+220h] [rbp-78h]
  _OWORD v29[2]; // [rsp+228h] [rbp-70h] BYREF
  _OWORD v30[2]; // [rsp+248h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v19 = a2;
  v5 = (const unsigned __int16 *)((char *)this + 16);
  if ( *((_QWORD *)this + 5) >= 8u )
    v5 = *(const unsigned __int16 **)v5;
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v26,
    "ProvOpsErasePackageMetadata");
  v26[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata::`vftable';
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata::StartActivity(
    (Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata *)v26,
    v5,
    a2);
  v20 = v26;
  v21 = 1;
  v17 = 0;
  v27 = *(_OWORD *)L"Security";
  v28 = aSecurity[8];
  v29[0] = *(_OWORD *)L"AllowRemoveProvisioningPackage";
  v29[1] = *(_OWORD *)L"oveProvisioningPackage";
  v30[0] = *(_OWORD *)L"sioningPackage";
  *(_OWORD *)((char *)v30 + 14) = *(_OWORD *)L"Package";
  PolicyInt = PolicyManager_GetPolicyInt(&v27, v29, &v17);
  v7 = PolicyInt;
  if ( PolicyInt < 0 )
  {
    v8 = (unsigned int)PolicyInt;
    v9 = 495;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)v8,
      v17);
    goto LABEL_18;
  }
  v7 = 0;
  if ( !v17 )
  {
    v7 = -2147024891;
    v8 = 2147942405LL;
    v9 = 496;
    goto LABEL_7;
  }
  v24 = 7;
  v23 = 0;
  LOWORD(v22) = 0;
  if ( *a2 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
  }
  else
  {
    v10 = 0;
  }
  try
  {
    std::wstring::assign(&v22, (char *)a2, v10);
    PackageEnroller::PackageEnroller((PackageEnroller *)v25);
    if ( v24 >= 8 )
      operator delete(v22);
    v24 = 7;
    v23 = 0;
    LOWORD(v22) = 0;
    PackageEnroller::UnenrollFromCsp((PackageEnroller *)v25, a3);
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v11, "D", a2);
    PackageEnroller::~PackageEnroller((PackageEnroller *)v25);
  }
  catch ( ... )
  {
    v14 = wil::ResultFromCaughtException(v12);
    v18 = v14;
    if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0dz_EventWriteTransfer(v16, v15, v14, v19);
    v7 = v18;
  }
LABEL_18:
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v26);
  v26[0] = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata::`vftable';
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v26);
  return v7;
}

```

## disassembly

```asm
0x180017380  push    rbx
0x180017382  push    rsi
0x180017383  push    rdi
0x180017384  push    r14
0x180017386  push    r15
0x180017388  sub     rsp, 270h
0x18001738f  mov     rax, cs:__security_cookie
0x180017396  xor     rax, rsp
0x180017399  mov     [rsp+298h+var_30], rax
0x1800173a1  mov     r14, r8
0x1800173a4  mov     rbx, rdx
0x1800173a7  mov     [rsp+298h+var_270], rdx
0x1800173ac  lea     rdi, [rcx+10h]
0x1800173b0  cmp     qword ptr [rdi+18h], 8
0x1800173b5  jb      short loc_1800173BA
0x1800173b7  mov     rdi, [rdi]
0x1800173ba  lea     rdx, aProvopserasepa; "ProvOpsErasePackageMetadata"
0x1800173c1  lea     rcx, [rsp+298h+var_1D8]
0x1800173c9  call    ??0?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800173ce  lea     rsi, ??_7ProvOpsErasePackageMetadata@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata::`vftable'
0x1800173d5  mov     [rsp+298h+var_1D8], rsi
0x1800173dd  mov     r8, rbx; unsigned __int16 *
0x1800173e0  mov     rdx, rdi; unsigned __int16 *
0x1800173e3  lea     rcx, [rsp+298h+var_1D8]; this
0x1800173eb  call    ?StartActivity@ProvOpsErasePackageMetadata@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXPEBG0@Z; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata::StartActivity(ushort const *,ushort const *)
0x1800173f0  nop
0x1800173f1  lea     rax, [rsp+298h+var_1D8]
0x1800173f9  mov     [rsp+298h+var_268], rax
0x1800173fe  mov     [rsp+298h+var_260], 1
0x180017403  xor     r15d, r15d
0x180017406  mov     [rsp+298h+var_278], r15d; int
0x18001740b  movups  xmm0, xmmword ptr cs:aSecurity; "Security"
0x180017412  movups  [rsp+298h+var_88], xmm0
0x18001741a  movzx   eax, word ptr cs:aSecurity+10h; ""
0x180017421  mov     [rsp+298h+var_78], ax
0x180017429  movups  xmm0, xmmword ptr cs:aAllowremovepro; "AllowRemoveProvisioningPackage"
0x180017430  movups  [rsp+298h+var_70], xmm0
0x180017438  movups  xmm1, xmmword ptr cs:aAllowremovepro+10h; "oveProvisioningPackage"
0x18001743f  movups  [rsp+298h+var_60], xmm1
0x180017447  movups  xmm0, xmmword ptr cs:aAllowremovepro+20h; "sioningPackage"
0x18001744e  movups  xmmword ptr [rsp+298h+var_50], xmm0
0x180017456  movups  xmm1, xmmword ptr cs:aAllowremovepro+2Eh; "Package"
0x18001745d  movups  xmmword ptr [rsp+298h+var_50+0Eh], xmm1
0x180017465  lea     r8, [rsp+298h+var_278]
0x18001746a  lea     rdx, [rsp+298h+var_70]
0x180017472  lea     rcx, [rsp+298h+var_88]
0x18001747a  call    cs:__imp_PolicyManager_GetPolicyInt
0x180017480  mov     edi, eax
0x180017482  test    eax, eax
0x180017484  jns     short loc_180017490
0x180017486  mov     r9d, eax
0x180017489  mov     edx, 1EFh
0x18001748e  jmp     short loc_1800174A7
0x180017490  mov     edi, r15d
0x180017493  cmp     [rsp+298h+var_278], r15d
0x180017498  jnz     short loc_1800174C0
0x18001749a  mov     edi, 80070005h
0x18001749f  mov     r9d, edi; char *
0x1800174a2  mov     edx, 1F0h; void *
0x1800174a7  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x1800174ae  mov     rcx, [rsp+298h]; this
0x1800174b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174bb  jmp     loc_180017570
0x1800174c0  mov     [rsp+298h+var_240], 7
0x1800174c9  mov     [rsp+298h+var_248], r15
0x1800174ce  mov     word ptr [rsp+298h+var_258], r15w
0x1800174d4  cmp     [rbx], r15w
0x1800174d8  jnz     short loc_1800174DF
0x1800174da  mov     r8, r15
0x1800174dd  jmp     short loc_1800174ED
0x1800174df  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800174e3  inc     r8
0x1800174e6  cmp     [rbx+r8*2], r15w
0x1800174eb  jnz     short loc_1800174E3
0x1800174ed  mov     rdx, rbx; Src
0x1800174f0  lea     rcx, [rsp+298h+var_258]; void *
0x1800174f5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800174fa  nop
0x1800174fb  lea     rdx, [rsp+298h+var_258]
0x180017500  lea     rcx, [rsp+298h+var_238]; this
0x180017505  call    ??0PackageEnroller@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageEnroller::PackageEnroller(std::wstring const &)
0x18001750a  nop
0x18001750b  cmp     [rsp+298h+var_240], 8
0x180017511  jb      short loc_18001751E
0x180017513  mov     rcx, [rsp+298h+var_258]
0x180017518  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001751e  mov     [rsp+298h+var_240], 7
0x180017527  mov     [rsp+298h+var_248], r15
0x18001752c  mov     word ptr [rsp+298h+var_258], r15w
0x180017532  mov     rdx, r14; unsigned __int16 *
0x180017535  lea     rcx, [rsp+298h+var_238]; this
0x18001753a  call    ?UnenrollFromCsp@PackageEnroller@@QEAAXPEBG@Z; PackageEnroller::UnenrollFromCsp(ushort const *)
0x18001753f  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x180017546  jz      short loc_180017558
0x180017548  mov     r8, rbx
0x18001754b  lea     rdx, ProvOpsRemoveResourceManagerPackageMetadataForCspSucceeded; "D"
0x180017552  call    McTemplateU0z_EventWriteTransfer
0x180017557  nop
0x180017558  lea     rcx, [rsp+298h+var_238]; this
0x18001755d  call    ??1PackageEnroller@@QEAA@XZ; PackageEnroller::~PackageEnroller(void)
0x180017562  nop
0x180017563  jmp     short loc_180017570
0x180017565  lea     rsi, ??_7ProvOpsErasePackageMetadata@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::ProvOpsErasePackageMetadata::`vftable'
0x18001756c  mov     edi, [rsp+298h+var_274]
0x180017570  lea     rcx, [rsp+298h+var_1D8]
0x180017578  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001757d  nop
0x18001757e  mov     [rsp+298h+var_1D8], rsi
0x180017586  lea     rcx, [rsp+298h+var_1D8]
0x18001758e  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017593  lea     rcx, [rsp+298h+var_1D8]
0x18001759b  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800175a0  mov     eax, edi
0x1800175a2  mov     rcx, [rsp+298h+var_30]
0x1800175aa  xor     rcx, rsp; StackCookie
0x1800175ad  call    __security_check_cookie
0x1800175b2  add     rsp, 270h
0x1800175b9  pop     r15
0x1800175bb  pop     r14
0x1800175bd  pop     rdi
0x1800175be  pop     rsi
0x1800175bf  pop     rbx
0x1800175c0  retn
```
