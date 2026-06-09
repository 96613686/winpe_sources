# OfficeSharedApiImpl::AddinSkillActionService::FireReplyEvent(unsigned __int64,IOsfControlContainer *,IOfficeSolutionFramework *,wchar_t const *,wchar_t const *,Osf::AddinSkillActions::AddinSkillActionInvokeResultCode)

- ea: `0x180f96d20`
- end: `0x180f97083`
- name: `?FireReplyEvent@AddinSkillActionService@OfficeSharedApiImpl@@CAJ_KPEAUIOsfControlContainer@@PEAUIOfficeSolutionFramework@@PEB_W3W4AddinSkillActionInvokeResultCode@AddinSkillActions@Osf@@@Z`
- size: `867`
- prototype: `static int __high(unsigned __int64, struct IOsfControlContainer *, struct IOfficeSolutionFramework *, const wchar_t *, const wchar_t *, enum Osf::AddinSkillActions::AddinSkillActionInvokeResultCode)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180f97090`

## callees

- `0x18006eaec`
- `0x1802ad37c`
- `0x1802e3f10`
- `0x1802e5190`
- `0x1804cc0ac`
- `0x1804dd7b4`
- `0x1804ddd58`
- `0x1805e4264`
- `0x18086bc94`
- `0x180910b04`
- `0x180f96d20`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180f96e26`
- `OLEAUT32!__imp_SysFreeString` at `0x180f96eb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180f96fc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180f97067`
- `OLEAUT32!__imp_SysFreeString` at `0x180f96e26`
- `OLEAUT32!__imp_SysFreeString` at `0x180f96eb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180f96fc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180f97067`
- `OLEAUT32!__imp_VariantInit` at `0x180f96e4f`
- `OLEAUT32!__imp_VariantInit` at `0x180f96e4f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180f96e9e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180f96fb1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180f96e9e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180f96fb1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180f96f0b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180f96f0b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180f96f29`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180f96fa0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180f97048`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180f96f29`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180f96fa0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180f97048`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180f96ecd`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180f96ecd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180f96f1a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180f96f1a`

## pseudocode

```c
__int64 __fastcall OfficeSharedApiImpl::AddinSkillActionService::FireReplyEvent(
        SAFEARRAY *a1,
        struct IOsfControlContainer *a2,
        __int64 a3,
        const wchar_t *a4,
        BSTR bstrString,
        unsigned int a6)
{
  SAFEARRAY *v8; // rax
  SAFEARRAY *v9; // rsi
  __int64 v10; // rax
  OLECHAR *v11; // rbx
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  OLECHAR *v14; // rdi
  __int64 v15; // rax
  int v16; // edi
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v19; // rdi
  SAFEARRAY *v20; // rcx
  unsigned int v21; // r8d
  SAFEARRAY *v22; // rdx
  OsfHostEventData *v23; // rax
  SAFEARRAY *v24; // rsi
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // r8
  BSTR v28; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v29[8]; // [rsp+38h] [rbp-38h] BYREF
  void *ppvData[2]; // [rsp+40h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  SAFEARRAY *psa; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v33; // [rsp+B0h] [rbp+40h] BYREF

  v33 = a3;
  psa = a1;
  v8 = (SAFEARRAY *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x40, (unsigned __int64)a2, a3);
  v9 = v8;
  if ( v8 )
  {
    v8->rgsabound[0].lLbound = 0;
    v8[1].rgsabound[0].lLbound = 0;
    *(_QWORD *)&v8->cDims = &OfficeSharedApiImpl::AddinSkillActionReplyEventArgs::`vftable'{for `OfficeSharedApi::IAddinSkillActionReplyEventArgs'};
    *(_QWORD *)&v8->cLocks = &OfficeSharedApiImpl::AddinSkillActionReplyEventArgs::`vftable'{for `OfficeExtension::ServerRuntime::IRichApiTypeInfo'};
    v8->pvData = &OfficeSharedApiImpl::AddinSkillActionReplyEventArgs::`vftable'{for `OfficeExtension::ServerRuntime::INativeIDispatchObjectHolder'};
    v8->rgsabound[0].cElements = 0;
    *(_QWORD *)&v8[1].cDims = 0;
    *(_QWORD *)&v8[1].cLocks = 0;
    v8[1].pvData = 0;
    v8[1].rgsabound[0].cElements = 0;
  }
  else
  {
    v9 = 0;
  }
  psa = v9;
  if ( v9 )
    (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&v9->cDims + 8LL))(v9);
  v28 = 0;
  Mso::BStrHolder::TryCopyFrom((Mso::BStrHolder *)&v28, a4);
  v10 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&psa);
  v11 = v28;
  (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v10 + 64LL))(v10, v28);
  v12 = bstrString;
  if ( bstrString )
  {
    bstrString = 0;
    Mso::BStrHolder::TryCopyFrom((Mso::BStrHolder *)&bstrString, v12);
    v13 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&psa);
    v14 = bstrString;
    (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v13 + 80LL))(v13, bstrString);
    if ( v14 )
      SysFreeString(v14);
  }
  v15 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&psa);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 96LL))(v15, a6);
  VariantInit(&pvarg);
  pvarg.vt = 9;
  pvarg.llVal = (LONGLONG)v9;
  psa = 0;
  v16 = OfficeExtension::ServerRuntime::RichApi::CreateOsfEventDataArray(
          0x10000,
          65555,
          (__int64)&WindowName,
          0,
          (OfficeExtension::ServerRuntime::RichApi *)&pvarg,
          &psa);
  if ( v16 < 0 )
  {
    if ( psa )
      SafeArrayDestroy(psa);
    Mso::VariantHolder::Empty((Mso::VariantHolder *)&pvarg);
    if ( v11 )
      SysFreeString(v11);
    return (unsigned int)v16;
  }
  Vector = SafeArrayCreateVector(0xCu, 0, 1u);
  v19 = Vector;
  if ( !Vector )
  {
    SendTraceEvent(0x30303030u, -2147024882);
    v20 = psa;
    if ( !psa )
    {
LABEL_30:
      Mso::VariantHolder::Empty((Mso::VariantHolder *)&pvarg);
      if ( v11 )
        SysFreeString(v11);
      return 2147942414LL;
    }
LABEL_29:
    SafeArrayDestroy(v20);
    goto LABEL_30;
  }
  ppvData[0] = Vector;
  ppvData[1] = 0;
  if ( SafeArrayAccessData(Vector, &ppvData[1]) < 0 )
  {
    MsoShipAssertTagProc(528089233);
    if ( ppvData[0] )
      SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
    *(_OWORD *)ppvData = 0;
  }
  *(_WORD *)ppvData[1] = 8204;
  v22 = psa;
  *((_QWORD *)ppvData[1] + 1) = psa;
  v23 = (OsfHostEventData *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x40, (unsigned __int64)v22, v21);
  if ( v23 )
    v24 = (SAFEARRAY *)OsfHostEventData::OsfHostEventData(v23, 33, 0, 0, a2, 0);
  else
    v24 = 0;
  psa = v24;
  if ( !v24 )
  {
    SendTraceEvent(0x30303030u, -2147024882);
    if ( ppvData[0] )
      SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
    *(_OWORD *)ppvData = 0;
    v20 = v19;
    goto LABEL_29;
  }
  v25 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&psa);
  (*(void (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v25 + 96LL))(v25, v19);
  qi_cast<IOsfEventSink,IOfficeSolutionFramework *,1>(v29, &v33);
  v26 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(v29);
  LOBYTE(v27) = 1;
  (*(void (__fastcall **)(__int64, SAFEARRAY *, __int64))(*(_QWORD *)v26 + 32LL))(v26, v24, v27);
  Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(v29);
  (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&v24->cDims + 16LL))(v24);
  if ( ppvData[0] )
    SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
  *(_OWORD *)ppvData = 0;
  Mso::VariantHolder::Empty((Mso::VariantHolder *)&pvarg);
  if ( v11 )
    SysFreeString(v11);
  return 0;
}

```

## disassembly

```asm
0x180f96d20  mov     [rsp-28h+arg_8], rbx
0x180f96d25  mov     [rsp-28h+arg_10], r8
0x180f96d2a  mov     [rsp-28h+psa], rcx
0x180f96d2f  push    rbp
0x180f96d30  push    rsi
0x180f96d31  push    rdi
0x180f96d32  push    r14
0x180f96d34  push    r15
0x180f96d36  mov     rbp, rsp
0x180f96d39  sub     rsp, 70h
0x180f96d3d  mov     rbx, r9
0x180f96d40  mov     r14, rdx
0x180f96d43  mov     ecx, 40h ; '@'; this
0x180f96d48  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180f96d4d  mov     rsi, rax
0x180f96d50  xor     r15d, r15d
0x180f96d53  test    rax, rax
0x180f96d56  jz      short loc_180F96D96
0x180f96d58  mov     [rax+1Ch], r15d
0x180f96d5c  mov     [rax+3Ch], r15d
0x180f96d60  lea     rax, ??_7AddinSkillActionReplyEventArgs@OfficeSharedApiImpl@@6BIAddinSkillActionReplyEventArgs@OfficeSharedApi@@@; const OfficeSharedApiImpl::AddinSkillActionReplyEventArgs::`vftable'{for `OfficeSharedApi::IAddinSkillActionReplyEventArgs'}
0x180f96d67  mov     [rsi], rax
0x180f96d6a  lea     rax, ??_7AddinSkillActionReplyEventArgs@OfficeSharedApiImpl@@6BIRichApiTypeInfo@ServerRuntime@OfficeExtension@@@; const OfficeSharedApiImpl::AddinSkillActionReplyEventArgs::`vftable'{for `OfficeExtension::ServerRuntime::IRichApiTypeInfo'}
0x180f96d71  mov     [rsi+8], rax
0x180f96d75  lea     rax, ??_7AddinSkillActionReplyEventArgs@OfficeSharedApiImpl@@6BINativeIDispatchObjectHolder@ServerRuntime@OfficeExtension@@@; const OfficeSharedApiImpl::AddinSkillActionReplyEventArgs::`vftable'{for `OfficeExtension::ServerRuntime::INativeIDispatchObjectHolder'}
0x180f96d7c  mov     [rsi+10h], rax
0x180f96d80  mov     [rsi+18h], r15d
0x180f96d84  mov     [rsi+20h], r15
0x180f96d88  mov     [rsi+28h], r15
0x180f96d8c  mov     [rsi+30h], r15
0x180f96d90  mov     [rsi+38h], r15d
0x180f96d94  jmp     short loc_180F96D99
0x180f96d96  mov     rsi, r15
0x180f96d99  mov     [rbp+psa], rsi
0x180f96d9d  test    rsi, rsi
0x180f96da0  jz      short loc_180F96DB2
0x180f96da2  mov     rax, [rsi]
0x180f96da5  mov     rcx, rsi
0x180f96da8  mov     rax, [rax+8]
0x180f96dac  call    cs:__guard_dispatch_icall_fptr
0x180f96db2  mov     [rbp+var_40], r15
0x180f96db6  mov     rdx, rbx; wchar_t *
0x180f96db9  lea     rcx, [rbp+var_40]; this
0x180f96dbd  call    ?TryCopyFrom@BStrHolder@Mso@@QEAA_NPEB_W@Z; Mso::BStrHolder::TryCopyFrom(wchar_t const *)
0x180f96dc2  lea     rcx, [rbp+psa]
0x180f96dc6  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f96dcb  mov     r8, rax
0x180f96dce  mov     rcx, [rax]
0x180f96dd1  mov     rax, [rcx+40h]
0x180f96dd5  mov     rbx, [rbp+var_40]
0x180f96dd9  mov     rdx, rbx
0x180f96ddc  mov     rcx, r8
0x180f96ddf  call    cs:__guard_dispatch_icall_fptr
0x180f96de5  mov     rdx, [rbp+bstrString]; wchar_t *
0x180f96de9  test    rdx, rdx
0x180f96dec  jz      short loc_180F96E2C
0x180f96dee  mov     [rbp+bstrString], r15
0x180f96df2  lea     rcx, [rbp+bstrString]; this
0x180f96df6  call    ?TryCopyFrom@BStrHolder@Mso@@QEAA_NPEB_W@Z; Mso::BStrHolder::TryCopyFrom(wchar_t const *)
0x180f96dfb  lea     rcx, [rbp+psa]
0x180f96dff  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f96e04  mov     r8, rax
0x180f96e07  mov     rcx, [rax]
0x180f96e0a  mov     rax, [rcx+50h]
0x180f96e0e  mov     rdi, [rbp+bstrString]
0x180f96e12  mov     rdx, rdi
0x180f96e15  mov     rcx, r8
0x180f96e18  call    cs:__guard_dispatch_icall_fptr
0x180f96e1e  test    rdi, rdi
0x180f96e21  jz      short loc_180F96E2C
0x180f96e23  mov     rcx, rdi; bstrString
0x180f96e26  call    cs:__imp_SysFreeString
0x180f96e2c  lea     rcx, [rbp+psa]
0x180f96e30  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f96e35  mov     r8, rax
0x180f96e38  mov     rcx, [rax]
0x180f96e3b  mov     rax, [rcx+60h]
0x180f96e3f  mov     edx, [rbp+arg_28]
0x180f96e42  mov     rcx, r8
0x180f96e45  call    cs:__guard_dispatch_icall_fptr
0x180f96e4b  lea     rcx, [rbp+pvarg]; pvarg
0x180f96e4f  call    cs:__imp_VariantInit
0x180f96e55  mov     eax, 9
0x180f96e5a  mov     word ptr [rbp+pvarg], ax
0x180f96e5e  mov     qword ptr [rbp+pvarg+8], rsi
0x180f96e62  mov     [rbp+psa], r15
0x180f96e66  lea     rax, [rbp+psa]
0x180f96e6a  mov     [rsp+70h+Source], rax
0x180f96e6f  lea     rax, [rbp+pvarg]
0x180f96e73  mov     [rsp+70h+var_50], rax
0x180f96e78  xor     r9d, r9d
0x180f96e7b  lea     r8, WindowName
0x180f96e82  mov     edx, 10013h
0x180f96e87  lea     ecx, [rdx-13h]
0x180f96e8a  call    ?CreateOsfEventDataArray@RichApi@ServerRuntime@OfficeExtension@@YAJHHPEB_WHAEBUtagVARIANT@@AEAV?$THolder@PEAUtagSAFEARRAY@@USafeArrayHelper@Mso@@U?$EmptyTraits@PEAUtagSAFEARRAY@@@3@@Mso@@@Z; OfficeExtension::ServerRuntime::RichApi::CreateOsfEventDataArray(int,int,wchar_t const *,int,tagVARIANT const &,Mso::THolder<tagSAFEARRAY *,Mso::SafeArrayHelper,Mso::EmptyTraits<tagSAFEARRAY *>> &)
0x180f96e8f  mov     edi, eax
0x180f96e91  test    eax, eax
0x180f96e93  jns     short loc_180F96EC2
0x180f96e95  mov     rcx, [rbp+psa]; psa
0x180f96e99  test    rcx, rcx
0x180f96e9c  jz      short loc_180F96EA4
0x180f96e9e  call    cs:__imp_SafeArrayDestroy
0x180f96ea4  lea     rcx, [rbp+pvarg]; this
0x180f96ea8  call    ?Empty@VariantHolder@Mso@@QEAAXXZ; Mso::VariantHolder::Empty(void)
0x180f96ead  test    rbx, rbx
0x180f96eb0  jz      short loc_180F96EBB
0x180f96eb2  mov     rcx, rbx; bstrString
0x180f96eb5  call    cs:__imp_SysFreeString
0x180f96ebb  mov     eax, edi
0x180f96ebd  jmp     loc_180F9706F
0x180f96ec2  mov     ecx, 0Ch; vt
0x180f96ec7  xor     edx, edx; lLbound
0x180f96ec9  lea     r8d, [rcx-0Bh]; cElements
0x180f96ecd  call    cs:__imp_SafeArrayCreateVector
0x180f96ed3  mov     rdi, rax
0x180f96ed6  test    rax, rax
0x180f96ed9  jnz     short loc_180F96EFC
0x180f96edb  mov     edx, 8007000Eh; int
0x180f96ee0  mov     ecx, 30303030h; unsigned int
0x180f96ee5  call    ?SendTraceEvent@@YAXKJ@Z; SendTraceEvent(ulong,long)
0x180f96eea  mov     rcx, [rbp+psa]
0x180f96eee  test    rcx, rcx
0x180f96ef1  jz      loc_180F96FB7
0x180f96ef7  jmp     loc_180F96FB1
0x180f96efc  mov     [rbp+ppvData], rdi
0x180f96f00  mov     [rbp+ppvData+8], r15
0x180f96f04  lea     rdx, [rbp+ppvData+8]; ppvData
0x180f96f08  mov     rcx, rdi; psa
0x180f96f0b  call    cs:__imp_SafeArrayAccessData
0x180f96f11  test    eax, eax
0x180f96f13  jns     short loc_180F96F37
0x180f96f15  mov     ecx, 1F7A0091h
0x180f96f1a  call    cs:__imp_MsoShipAssertTagProc
0x180f96f20  mov     rcx, [rbp+ppvData]; psa
0x180f96f24  test    rcx, rcx
0x180f96f27  jz      short loc_180F96F2F
0x180f96f29  call    cs:__imp_SafeArrayUnaccessData
0x180f96f2f  xorps   xmm0, xmm0
0x180f96f32  movdqu  xmmword ptr [rbp+ppvData], xmm0
0x180f96f37  mov     rax, [rbp+ppvData+8]
0x180f96f3b  mov     word ptr [rax], 200Ch
0x180f96f40  mov     rdx, [rbp+psa]; unsigned __int64
0x180f96f44  mov     rax, [rbp+ppvData+8]
0x180f96f48  mov     [rax+8], rdx
0x180f96f4c  mov     ecx, 40h ; '@'; this
0x180f96f51  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180f96f56  test    rax, rax
0x180f96f59  jz      short loc_180F96F7C
0x180f96f5b  mov     [rsp+70h+Source], r15; Source
0x180f96f60  mov     [rsp+70h+var_50], r14; struct IOsfControlContainer *
0x180f96f65  xor     r9d, r9d; unsigned __int64
0x180f96f68  xor     r8d, r8d; unsigned __int64
0x180f96f6b  lea     edx, [r9+21h]; int
0x180f96f6f  mov     rcx, rax; this
0x180f96f72  call    ??0OsfHostEventData@@QEAA@J_K0PEAUIOsfControlContainer@@PEB_W@Z; OsfHostEventData::OsfHostEventData(long,unsigned __int64,unsigned __int64,IOsfControlContainer *,wchar_t const *)
0x180f96f77  mov     rsi, rax
0x180f96f7a  jmp     short loc_180F96F7F
0x180f96f7c  mov     rsi, r15
0x180f96f7f  mov     [rbp+psa], rsi
0x180f96f83  test    rsi, rsi
0x180f96f86  jnz     short loc_180F96FD8
0x180f96f88  mov     edx, 8007000Eh; int
0x180f96f8d  mov     ecx, 30303030h; unsigned int
0x180f96f92  call    ?SendTraceEvent@@YAXKJ@Z; SendTraceEvent(ulong,long)
0x180f96f97  mov     rcx, [rbp+ppvData]; psa
0x180f96f9b  test    rcx, rcx
0x180f96f9e  jz      short loc_180F96FA6
0x180f96fa0  call    cs:__imp_SafeArrayUnaccessData
0x180f96fa6  xorps   xmm0, xmm0
0x180f96fa9  movdqu  xmmword ptr [rbp+ppvData], xmm0
0x180f96fae  mov     rcx, rdi; psa
0x180f96fb1  call    cs:__imp_SafeArrayDestroy
0x180f96fb7  lea     rcx, [rbp+pvarg]; this
0x180f96fbb  call    ?Empty@VariantHolder@Mso@@QEAAXXZ; Mso::VariantHolder::Empty(void)
0x180f96fc0  test    rbx, rbx
0x180f96fc3  jz      short loc_180F96FCE
0x180f96fc5  mov     rcx, rbx; bstrString
0x180f96fc8  call    cs:__imp_SysFreeString
0x180f96fce  mov     eax, 8007000Eh
0x180f96fd3  jmp     loc_180F9706F
0x180f96fd8  lea     rcx, [rbp+psa]
0x180f96fdc  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f96fe1  mov     r9, rax
0x180f96fe4  mov     rcx, [rax]
0x180f96fe7  mov     rax, [rcx+60h]
0x180f96feb  mov     rdx, rdi
0x180f96fee  mov     rcx, r9
0x180f96ff1  call    cs:__guard_dispatch_icall_fptr
0x180f96ff7  lea     rdx, [rbp+arg_10]
0x180f96ffb  lea     rcx, [rbp+var_38]
0x180f96fff  call    ??$qi_cast@UIOsfEventSink@@PEAUIOfficeSolutionFramework@@$00@@YA?AV?$TCntPtr@UIOsfEventSink@@@Mso@@AEBQEAUIOfficeSolutionFramework@@AEBU_GUID@@@Z; qi_cast<IOsfEventSink,IOfficeSolutionFramework *,1>(IOfficeSolutionFramework * const &,_GUID const &)
0x180f97004  lea     rcx, [rbp+var_38]
0x180f97008  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x180f9700d  mov     r9, rax
0x180f97010  mov     rcx, [rax]
0x180f97013  mov     rax, [rcx+20h]
0x180f97017  mov     r8b, 1
0x180f9701a  mov     rdx, rsi
0x180f9701d  mov     rcx, r9
0x180f97020  call    cs:__guard_dispatch_icall_fptr
0x180f97026  lea     rcx, [rbp+var_38]
0x180f9702a  call    ??1?$Functor@$$A6AXPEAUIOsfControlContainer@@_K@Z@Mso@@QEAA@XZ; Mso::Functor<void (IOsfControlContainer *,unsigned __int64)>::~Functor<void (IOsfControlContainer *,unsigned __int64)>(void)
0x180f9702f  mov     rax, [rsi]
0x180f97032  mov     rcx, rsi
0x180f97035  mov     rax, [rax+10h]
0x180f97039  call    cs:__guard_dispatch_icall_fptr
0x180f9703f  mov     rcx, [rbp+ppvData]; psa
0x180f97043  test    rcx, rcx
0x180f97046  jz      short loc_180F9704E
0x180f97048  call    cs:__imp_SafeArrayUnaccessData
0x180f9704e  xorps   xmm0, xmm0
0x180f97051  movdqu  xmmword ptr [rbp+ppvData], xmm0
0x180f97056  lea     rcx, [rbp+pvarg]; this
0x180f9705a  call    ?Empty@VariantHolder@Mso@@QEAAXXZ; Mso::VariantHolder::Empty(void)
0x180f9705f  test    rbx, rbx
0x180f97062  jz      short loc_180F9706D
0x180f97064  mov     rcx, rbx; bstrString
0x180f97067  call    cs:__imp_SysFreeString
0x180f9706d  xor     eax, eax
0x180f9706f  mov     rbx, [rsp+70h+arg_8]
0x180f97077  add     rsp, 70h
0x180f9707b  pop     r15
0x180f9707d  pop     r14
0x180f9707f  pop     rdi
0x180f97080  pop     rsi
0x180f97081  pop     rbp
0x180f97082  retn
```
