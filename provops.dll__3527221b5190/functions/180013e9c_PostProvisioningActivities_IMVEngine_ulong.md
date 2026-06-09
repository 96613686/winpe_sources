# PostProvisioningActivities(IMVEngine *,ulong)

- ea: `0x180013e9c`
- end: `0x1800142a7`
- name: `?PostProvisioningActivities@@YAXPEAUIMVEngine@@K@Z`
- size: `1035`
- prototype: `void __fastcall(struct IMVEngine *, unsigned int)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d574`
- `0x18000ebbc`
- `0x18000f8d0`
- `0x180010b40`

## callees

- `0x180001678`
- `0x180001760`
- `0x180006f50`
- `0x18000d170`
- `0x18000d94c`
- `0x1800121d0`
- `0x180013e9c`
- `0x180017938`
- `0x1800181f4`
- `0x180019118`
- `0x18001b388`
- `0x18001f8e4`
- `0x180028854`
- `0x180033e9a`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180013f9d`
- `OLEAUT32!__imp_VariantInit` at `0x180013ff4`
- `OLEAUT32!__imp_VariantInit` at `0x180013f9d`
- `OLEAUT32!__imp_VariantInit` at `0x180013ff4`
- `OLEAUT32!__imp_VariantClear` at `0x180013fe7`
- `OLEAUT32!__imp_VariantClear` at `0x180014039`
- `OLEAUT32!__imp_VariantClear` at `0x180013fe7`
- `OLEAUT32!__imp_VariantClear` at `0x180014039`
- `ntdll!RtlPublishWnfStateData` at `0x180014058`
- `ntdll!RtlPublishWnfStateData` at `0x180014058`
- `ext-ms-win-provisioning-platform-l1-1-0!ConfigureAppLaunch` at `0x18001407b`
- `ext-ms-win-provisioning-platform-l1-1-0!ConfigureAppLaunch` at `0x18001407b`

## string_xrefs

- `0x180014091`: `ProvOps ConfigureAppLaunch() Failed`

## pseudocode

```c
void __fastcall PostProvisioningActivities(struct IMVEngine *a1, unsigned int a2)
{
  LONG lVal; // eax
  LONG v5; // eax
  int v6; // eax
  unsigned int v7; // r8d
  wil::details::in1diag3 *v8; // rcx
  const struct _tlgProvider_t *v9; // rax
  int v10; // r9d
  const struct _tlgProvider_t *v11; // rax
  int v12; // edx
  const char *v13; // r9
  int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+34h] [rbp-CCh] BYREF
  int v17[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v19; // [rsp+48h] [rbp-B8h]
  void ***v20; // [rsp+50h] [rbp-B0h]
  char v21; // [rsp+58h] [rbp-A8h]
  unsigned int v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+64h] [rbp-9Ch]
  void **v24; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+78h] [rbp-88h] BYREF
  char v26; // [rsp+7Ch] [rbp-84h]
  int v27; // [rsp+A0h] [rbp-60h] BYREF
  const char *v28; // [rsp+A8h] [rbp-58h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  char v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+C0h] [rbp-40h]
  _BYTE v32[152]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v33; // [rsp+160h] [rbp+60h]
  int v34; // [rsp+170h] [rbp+70h]
  __int64 v35; // [rsp+178h] [rbp+78h]
  int *v36; // [rsp+180h] [rbp+80h]
  __int64 v37; // [rsp+188h] [rbp+88h]
  __int64 v38; // [rsp+190h] [rbp+90h]
  void ***v39; // [rsp+198h] [rbp+98h]
  __int64 v40; // [rsp+1A0h] [rbp+A0h]
  int v41; // [rsp+1A8h] [rbp+A8h]
  int *v42; // [rsp+1B0h] [rbp+B0h]
  char v43; // [rsp+1B8h] [rbp+B8h]
  VARIANTARG pvarg; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v25 = 0;
  v26 = 0;
  v30 = 0;
  v27 = 0;
  v28 = "PostProvisioningActivities";
  v29 = 0;
  v31 = 0;
  v33 = 0;
  memset_0(v32, 0, sizeof(v32));
  v34 = 1;
  v35 = 0;
  v36 = &v25;
  v37 = 0;
  v38 = 0;
  v39 = &v24;
  v40 = 0;
  v41 = 0;
  v42 = &v27;
  v43 = 0;
  v24 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities::`vftable';
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities::StartActivity((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities *)&v24);
  v20 = &v24;
  v21 = 1;
  v22 = a2;
  v23 = 0;
  if ( a1 )
  {
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(struct IMVEngine *, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)a1 + 56LL))(
           a1,
           L"ChangesMade",
           &pvarg) >= 0 )
    {
      lVal = v23;
      if ( pvarg.vt == 19 )
        lVal = pvarg.lVal;
      LODWORD(v23) = lVal;
    }
    VariantClear(&pvarg);
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(struct IMVEngine *, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)a1 + 56LL))(
           a1,
           L"CellularSequence",
           &pvarg) >= 0 )
    {
      v5 = HIDWORD(v23);
      if ( pvarg.vt == 19 )
        v5 = pvarg.lVal;
      HIDWORD(v23) = v5;
    }
    VariantClear(&pvarg);
  }
  v14 = 0;
  v6 = RtlPublishWnfStateData(WNF_PROV_TURN_COMPLETE, 0, &v22, 12);
  v8 = retaddr;
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_NtStatus(retaddr, (void *)0xB9, v7, (const char *)(unsigned int)v6, 0);
  if ( a2 == 4 && (int)ConfigureAppLaunch(v8) < 0 )
  {
    v9 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    if ( *(_DWORD *)v9 > 5u )
    {
      *(_QWORD *)v17 = "ProvOps ConfigureAppLaunch() Failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v9,
        (unsigned int)&word_18003FC2E,
        0,
        v10,
        (__int64)v17);
    }
  }
  if ( a1 )
  {
    RetrySchedule::RetrySchedule((RetrySchedule *)v18);
    v15 = 0;
    if ( (*(int (__fastcall **)(struct IMVEngine *, unsigned int *))(*(_QWORD *)a1 + 80LL))(a1, &v15) >= 0 && v15 )
    {
      v12 = v19;
      if ( v19 > 0xFFFFFFFF )
        v12 = -1;
      v13 = v19 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0LL;
      if ( v19 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2C,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\retryschedule.cpp",
          v13,
          v14);
      if ( v15 < v12 + 2 )
      {
        v17[0] = 0;
        (*(void (__fastcall **)(struct IMVEngine *, int *, __int64, const char *))(*(_QWORD *)a1 + 88LL))(
          a1,
          v17,
          0xFFFFFFFFLL,
          v13);
        ScheduleRetryTask(v15, (struct RetrySchedule *)v18, v17[0]);
      }
    }
    v16 = 0;
    if ( (*(int (__fastcall **)(struct IMVEngine *, _QWORD, int *))(*(_QWORD *)a1 + 112LL))(a1, a2, &v16) >= 0
      && v16
      && (*(unsigned int (__fastcall **)(struct IMVEngine *, _QWORD))(*(_QWORD *)a1 + 120LL))(a1, a2) == -2147021886 )
    {
      (*(void (__fastcall **)(struct IMVEngine *))(*(_QWORD *)a1 + 128LL))(a1);
      (*(void (__fastcall **)(struct IMVEngine *, __int64))(*(_QWORD *)a1 + 136LL))(a1, 1);
    }
    if ( a2 == 1 || a2 == 2 || a2 == 3 || a2 != 5 && a2 != 7 )
      (*(void (__fastcall **)(struct IMVEngine *, _QWORD))(*(_QWORD *)a1 + 144LL))(a1, a2);
    else
      (*(void (__fastcall **)(struct IMVEngine *))(*(_QWORD *)a1 + 96LL))(a1);
    std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v18);
  }
  else
  {
    v11 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    if ( *(_DWORD *)v11 > 5u )
      tlgWriteTransfer_EventWriteTransfer(v11, byte_18003F8F9, v36 + 2, 0);
  }
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v24);
  v24 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities::`vftable';
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v24);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>(&v24);
}

```

## disassembly

```asm
0x180013e9c  mov     [rsp-8+arg_10], rbx
0x180013ea1  push    rbp
0x180013ea2  push    rsi
0x180013ea3  push    rdi
0x180013ea4  push    r14
0x180013ea6  push    r15
0x180013ea8  lea     rbp, [rsp-0F0h]
0x180013eb0  sub     rsp, 1F0h
0x180013eb7  mov     rax, cs:__security_cookie
0x180013ebe  xor     rax, rsp
0x180013ec1  mov     [rbp+110h+var_30], rax
0x180013ec8  mov     edi, edx
0x180013eca  mov     rbx, rcx
0x180013ecd  xor     esi, esi
0x180013ecf  mov     [rsp+210h+var_198], esi
0x180013ed3  mov     [rsp+210h+var_194], sil
0x180013ed8  mov     [rbp+110h+var_158], sil
0x180013edc  mov     [rbp+110h+var_170], esi
0x180013edf  lea     rax, aPostprovisioni; "PostProvisioningActivities"
0x180013ee6  mov     [rbp+110h+var_168], rax
0x180013eea  mov     [rbp+110h+var_160], rsi
0x180013eee  mov     [rbp+110h+var_150], esi
0x180013ef1  xorps   xmm0, xmm0
0x180013ef4  movdqa  [rbp+110h+var_B0], xmm0
0x180013ef9  xor     edx, edx; Val
0x180013efb  mov     r8d, 98h; Size
0x180013f01  lea     rcx, [rbp+110h+var_148]; void *
0x180013f05  call    memset_0
0x180013f0a  mov     [rbp+110h+var_A0], 1
0x180013f11  xor     eax, eax
0x180013f13  mov     [rbp+110h+var_98], rax
0x180013f17  lea     rax, [rsp+210h+var_198]
0x180013f1c  mov     [rbp+110h+var_90], rax
0x180013f23  mov     [rbp+110h+var_88], rsi
0x180013f2a  mov     [rbp+110h+var_80], rsi
0x180013f31  lea     rax, [rsp+210h+var_1A0]
0x180013f36  mov     [rbp+110h+var_78], rax
0x180013f3d  mov     [rbp+110h+var_70], rsi
0x180013f44  mov     [rbp+110h+var_68], esi
0x180013f4a  lea     rax, [rbp+110h+var_170]
0x180013f4e  mov     [rbp+110h+var_60], rax
0x180013f55  mov     [rbp+110h+var_58], sil
0x180013f5c  lea     r15, ??_7PostProvisioningActivities@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities::`vftable'
0x180013f63  mov     [rsp+210h+var_1A0], r15
0x180013f68  lea     rcx, [rsp+210h+var_1A0]; this
0x180013f6d  call    ?StartActivity@PostProvisioningActivities@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::PostProvisioningActivities::StartActivity(void)
0x180013f72  nop
0x180013f73  lea     rax, [rsp+210h+var_1A0]
0x180013f78  mov     [rsp+210h+var_1C0], rax
0x180013f7d  mov     [rsp+210h+var_1B8], 1
0x180013f82  mov     [rsp+210h+var_1B0], edi
0x180013f86  xor     eax, eax
0x180013f88  mov     [rsp+210h+var_1AC], rax
0x180013f8d  test    rbx, rbx
0x180013f90  jz      loc_18001403F
0x180013f96  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180013f9d  call    cs:__imp_VariantInit
0x180013fa3  nop
0x180013fa4  mov     rax, [rbx]
0x180013fa7  lea     r8, [rbp+110h+pvarg]
0x180013fae  lea     rdx, ?gc_wszChangesMade@@3QBGB; "ChangesMade"
0x180013fb5  mov     rcx, rbx
0x180013fb8  mov     rax, [rax+38h]
0x180013fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fc1  lea     r14d, [rsi+13h]
0x180013fc5  test    eax, eax
0x180013fc7  js      short loc_180013FE0
0x180013fc9  mov     eax, dword ptr [rsp+210h+var_1AC]
0x180013fcd  cmp     r14w, word ptr [rbp+110h+pvarg]
0x180013fd5  cmovz   eax, dword ptr [rbp+110h+pvarg+8]
0x180013fdc  mov     dword ptr [rsp+210h+var_1AC], eax
0x180013fe0  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180013fe7  call    cs:__imp_VariantClear
0x180013fed  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180013ff4  call    cs:__imp_VariantInit
0x180013ffa  mov     rax, [rbx]
0x180013ffd  lea     r8, [rbp+110h+pvarg]
0x180014004  lea     rdx, ?gc_wszCellularSequence@@3QBGB; "CellularSequence"
0x18001400b  mov     rcx, rbx
0x18001400e  mov     rax, [rax+38h]
0x180014012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014017  test    eax, eax
0x180014019  js      short loc_180014032
0x18001401b  mov     eax, dword ptr [rsp+210h+var_1AC+4]
0x18001401f  cmp     r14w, word ptr [rbp+110h+pvarg]
0x180014027  cmovz   eax, dword ptr [rbp+110h+pvarg+8]
0x18001402e  mov     dword ptr [rsp+210h+var_1AC+4], eax
0x180014032  lea     rcx, [rbp+110h+pvarg]; pvarg
0x180014039  call    cs:__imp_VariantClear
0x18001403f  mov     qword ptr [rsp+210h+var_1F0], rsi; int
0x180014044  mov     r9d, 0Ch
0x18001404a  lea     r8, [rsp+210h+var_1B0]
0x18001404f  xor     edx, edx
0x180014051  mov     rcx, cs:WNF_PROV_TURN_COMPLETE
0x180014058  call    cs:__imp_RtlPublishWnfStateData
0x18001405e  mov     rcx, [rbp+118h]; this
0x180014065  test    eax, eax
0x180014067  jns     short loc_180014076
0x180014069  mov     r9d, eax; char *
0x18001406c  mov     edx, 0B9h; void *
0x180014071  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180014076  cmp     edi, 4
0x180014079  jnz     short loc_1800140B9
0x18001407b  call    cs:__imp_ConfigureAppLaunch
0x180014081  test    eax, eax
0x180014083  jns     short loc_1800140B9
0x180014085  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x18001408a  mov     ecx, [rax]
0x18001408c  cmp     ecx, 5
0x18001408f  jbe     short loc_1800140B9
0x180014091  lea     rcx, aProvopsConfigu; "ProvOps ConfigureAppLaunch() Failed"
0x180014098  mov     qword ptr [rsp+210h+var_1D8], rcx
0x18001409d  lea     rcx, [rsp+210h+var_1D8]
0x1800140a2  mov     qword ptr [rsp+210h+var_1F0], rcx; int
0x1800140a7  xor     r8d, r8d
0x1800140aa  lea     rdx, word_18003FC2E
0x1800140b1  mov     rcx, rax
0x1800140b4  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800140b9  test    rbx, rbx
0x1800140bc  jnz     short loc_180014104
0x1800140be  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x1800140c3  mov     ecx, [rax]
0x1800140c5  cmp     ecx, 5
0x1800140c8  jbe     loc_180014248
0x1800140ce  mov     r8, [rbp+110h+var_90]
0x1800140d5  add     r8, 8
0x1800140d9  lea     rcx, [rbp+110h+pvarg]
0x1800140e0  mov     [rsp+210h+var_1E8], rcx
0x1800140e5  mov     [rsp+210h+var_1F0], 2
0x1800140ed  xor     r9d, r9d
0x1800140f0  lea     rdx, byte_18003F8F9
0x1800140f7  mov     rcx, rax
0x1800140fa  call    _tlgWriteTransfer_EventWriteTransfer
0x1800140ff  jmp     loc_180014248
0x180014104  lea     rcx, [rsp+210h+var_1D0]; this
0x180014109  call    ??0RetrySchedule@@QEAA@XZ; RetrySchedule::RetrySchedule(void)
0x18001410e  nop
0x18001410f  mov     [rsp+210h+var_1E0], esi
0x180014113  mov     rax, [rbx]
0x180014116  lea     rdx, [rsp+210h+var_1E0]
0x18001411b  mov     rcx, rbx
0x18001411e  mov     rax, [rax+50h]
0x180014122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014127  test    eax, eax
0x180014129  js      short loc_180014197
0x18001412b  mov     ecx, [rsp+210h+var_1E0]
0x18001412f  test    ecx, ecx
0x180014131  jz      short loc_180014197
0x180014133  mov     rax, [rsp+210h+var_1C8]
0x180014138  mov     r8d, 0FFFFFFFFh
0x18001413e  cmp     rax, r8
0x180014141  mov     edx, eax
0x180014143  jbe     short loc_180014148
0x180014145  mov     edx, r8d
0x180014148  cmp     r8, rax
0x18001414b  sbb     r9d, r9d
0x18001414e  and     r9d, 80070216h; char *
0x180014155  mov     r10, [rbp+118h]
0x18001415c  cmp     rax, r8
0x18001415f  ja      loc_180014292
0x180014165  lea     eax, [rdx+2]
0x180014168  cmp     ecx, eax
0x18001416a  jnb     short loc_180014197
0x18001416c  mov     [rsp+210h+var_1D8], esi
0x180014170  mov     rax, [rbx]
0x180014173  lea     rdx, [rsp+210h+var_1D8]
0x180014178  mov     rcx, rbx
0x18001417b  mov     rax, [rax+58h]
0x18001417f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014184  mov     r8d, [rsp+210h+var_1D8]; int
0x180014189  lea     rdx, [rsp+210h+var_1D0]; struct RetrySchedule *
0x18001418e  mov     ecx, [rsp+210h+var_1E0]; unsigned int
0x180014192  call    ?ScheduleRetryTask@@YAJKAEAVRetrySchedule@@H@Z; ScheduleRetryTask(ulong,RetrySchedule &,int)
0x180014197  mov     [rsp+210h+var_1DC], esi
0x18001419b  mov     rax, [rbx]
0x18001419e  lea     r8, [rsp+210h+var_1DC]
0x1800141a3  mov     edx, edi
0x1800141a5  mov     rcx, rbx
0x1800141a8  mov     rax, [rax+70h]
0x1800141ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141b1  test    eax, eax
0x1800141b3  js      short loc_1800141FC
0x1800141b5  cmp     [rsp+210h+var_1DC], esi
0x1800141b9  jz      short loc_1800141FC
0x1800141bb  mov     rax, [rbx]
0x1800141be  mov     edx, edi
0x1800141c0  mov     rcx, rbx
0x1800141c3  mov     rax, [rax+78h]
0x1800141c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141cc  cmp     eax, 80070BC2h
0x1800141d1  jnz     short loc_1800141FC
0x1800141d3  mov     rax, [rbx]
0x1800141d6  mov     rcx, rbx
0x1800141d9  mov     rax, [rax+80h]
0x1800141e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141e5  mov     rax, [rbx]
0x1800141e8  mov     edx, 1
0x1800141ed  mov     rcx, rbx
0x1800141f0  mov     rax, [rax+88h]
0x1800141f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141fc  mov     ecx, edi
0x1800141fe  sub     ecx, 1
0x180014201  jz      short loc_180014228
0x180014203  sub     ecx, 1
0x180014206  jz      short loc_180014228
0x180014208  sub     ecx, 1
0x18001420b  jz      short loc_180014228
0x18001420d  sub     ecx, 2
0x180014210  jz      short loc_180014217
0x180014212  cmp     ecx, 2
0x180014215  jnz     short loc_180014228
0x180014217  mov     rax, [rbx]
0x18001421a  mov     rcx, rbx
0x18001421d  mov     rax, [rax+60h]
0x180014221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014226  jmp     short loc_18001423D
0x180014228  mov     rax, [rbx]
0x18001422b  mov     edx, edi
0x18001422d  mov     rcx, rbx
0x180014230  mov     rax, [rax+90h]
0x180014237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001423c  nop
0x18001423d  lea     rcx, [rsp+210h+var_1D0]
0x180014242  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ulong,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(void)
0x180014247  nop
0x180014248  lea     rcx, [rsp+210h+var_1A0]
0x18001424d  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180014252  nop
0x180014253  mov     [rsp+210h+var_1A0], r15
0x180014258  lea     rcx, [rsp+210h+var_1A0]
0x18001425d  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014262  lea     rcx, [rsp+210h+var_1A0]
0x180014267  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001426c  mov     rcx, [rbp+110h+var_30]
0x180014273  xor     rcx, rsp; StackCookie
0x180014276  call    __security_check_cookie
0x18001427b  mov     rbx, [rsp+210h+arg_10]
0x180014283  add     rsp, 1F0h
0x18001428a  pop     r15
0x18001428c  pop     r14
0x18001428e  pop     rdi
0x18001428f  pop     rsi
0x180014290  pop     rbp
0x180014291  retn
0x180014292  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\lib\\retrysche"...
0x180014299  mov     edx, 2Ch ; ','; void *
0x18001429e  mov     rcx, r10; this
0x1800142a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
