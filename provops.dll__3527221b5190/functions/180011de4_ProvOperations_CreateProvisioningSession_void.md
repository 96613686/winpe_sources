# ProvOperations::CreateProvisioningSession(void)

- ea: `0x180011de4`
- end: `0x1800120b6`
- name: `?CreateProvisioningSession@ProvOperations@@AEAAJXZ`
- size: `722`
- prototype: `__int64 __fastcall(ProvOperations *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017f00`

## callees

- `0x180001760`
- `0x180003e78`
- `0x180006f50`
- `0x180007674`
- `0x180009ce0`
- `0x18000d170`
- `0x180011de4`
- `0x1800121d0`
- `0x180017a44`
- `0x1800180ac`
- `0x180019118`
- `0x18001b60c`
- `0x180033e9a`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012042`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012068`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012042`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012068`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011eee`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011eee`
- `RPCRT4!UuidCreate` at `0x180011fe2`
- `RPCRT4!UuidCreate` at `0x180011fe2`

## string_xrefs

- `0x180011e26`: `CreateProvisioningSession`

## pseudocode

```c
__int64 __fastcall ProvOperations::CreateProvisioningSession(ProvOperations *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rcx
  HRESULT Instance; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  bool v7; // dl
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r9
  _BYTE *v10; // rax
  _BYTE *v11; // rbx
  void *v12; // rcx
  struct TraceLoggingCorrelationVector *v13; // rax
  void *v14; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  UUID Uuid; // [rsp+30h] [rbp-D0h] BYREF
  void **v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  char v20; // [rsp+4Ch] [rbp-B4h]
  int v21; // [rsp+70h] [rbp-90h] BYREF
  const char *v22; // [rsp+78h] [rbp-88h]
  __int64 v23; // [rsp+80h] [rbp-80h]
  char v24; // [rsp+88h] [rbp-78h]
  int v25; // [rsp+90h] [rbp-70h]
  char v26[152]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v27; // [rsp+130h] [rbp+30h]
  int v28; // [rsp+140h] [rbp+40h]
  __int64 v29; // [rsp+148h] [rbp+48h]
  int *v30; // [rsp+150h] [rbp+50h]
  __int64 v31; // [rsp+158h] [rbp+58h]
  __int64 v32; // [rsp+160h] [rbp+60h]
  void ***v33; // [rsp+168h] [rbp+68h]
  __int64 v34; // [rsp+170h] [rbp+70h]
  int v35; // [rsp+178h] [rbp+78h]
  int *v36; // [rsp+180h] [rbp+80h]
  char v37; // [rsp+188h] [rbp+88h]
  char Source[144]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v19 = 0;
  v20 = 0;
  v24 = 0;
  v21 = 0;
  v22 = "CreateProvisioningSession";
  v23 = 0;
  v25 = 0;
  v27 = 0;
  memset_0(v26, 0, sizeof(v26));
  v28 = 1;
  v29 = 0;
  v30 = &v19;
  v31 = 0;
  v32 = 0;
  v33 = &v18;
  v34 = 0;
  v35 = 0;
  v36 = &v21;
  v37 = 0;
  v18 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession::`vftable';
  Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession::StartActivity((Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession *)&v18);
  *(_QWORD *)&Uuid.Data1 = &v18;
  Uuid.Data4[0] = 1;
  v2 = (_QWORD *)((char *)this + 48);
  v3 = *((_QWORD *)this + 6);
  if ( v3 )
  {
    *v2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  Instance = CoCreateInstance(
               &GUID_e7a8b38f_ae80_4753_b520_433d402e6379,
               0,
               1u,
               &GUID_4ebf49ca_8a92_4057_93ee_237fc110897d,
               (LPVOID *)this + 6);
  v5 = Instance;
  if ( Instance < 0 )
  {
    v6 = 1323;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\prov\\provops\\lib\\provops.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
    goto LABEL_20;
  }
  Instance = (*(__int64 (**)(void))(*(_QWORD *)*v2 + 24LL))();
  v5 = Instance;
  if ( Instance < 0 )
  {
    v6 = 1325;
    goto LABEL_7;
  }
  (*(void (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v2 + 48LL))(*v2, 129, Source);
  if ( (unsigned __int8)TraceLoggingCorrelationVector::ValidateImpl(Source, 0) )
  {
    v13 = TraceLoggingCorrelationVector::Set(Source, v7);
    v14 = (void *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v13;
    if ( v14 )
      operator delete(v14);
    v5 = 0;
  }
  else
  {
    v8 = Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      *(_QWORD *)&Uuid.Data1 = Source;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)v8,
        (__int64)&dword_18004045C,
        (__int64)(v30 + 2),
        v9,
        &Uuid);
    }
    v10 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v11 = v10;
    *(_QWORD *)&Uuid.Data1 = v10;
    if ( v10 )
    {
      v10[130] = 65;
      Uuid = 0;
      UuidCreate(&Uuid);
      v11[129] = 17;
      *((_QWORD *)v11 + 17) = 0x1300000000LL;
      memset_0(v11, 0, 0x81u);
      TLV::Base64Encode<129>(&Uuid, 12, v11);
      *((_WORD *)v11 + 8) = 46;
    }
    else
    {
      v11 = 0;
    }
    v12 = (void *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v11;
    if ( v12 )
      operator delete(v12);
    v5 = -2147467259;
  }
LABEL_20:
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v18);
  v18 = &Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession::`vftable';
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v18);
  wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>(&v18);
  return v5;
}

```

## disassembly

```asm
0x180011de4  push    rbp
0x180011de6  push    rbx
0x180011de7  push    rsi
0x180011de8  push    rdi
0x180011de9  push    r14
0x180011deb  push    r15
0x180011ded  lea     rbp, [rsp-138h]
0x180011df5  sub     rsp, 238h
0x180011dfc  mov     rax, cs:__security_cookie
0x180011e03  xor     rax, rsp
0x180011e06  mov     [rbp+160h+var_40], rax
0x180011e0d  mov     rdi, rcx
0x180011e10  xor     r14d, r14d
0x180011e13  mov     [rsp+260h+var_218], r14d
0x180011e18  mov     [rsp+260h+var_214], r14b
0x180011e1d  mov     [rbp+160h+var_1D8], r14b
0x180011e21  mov     [rsp+260h+var_1F0], r14d
0x180011e26  lea     rax, aCreateprovisio; "CreateProvisioningSession"
0x180011e2d  mov     [rsp+260h+var_1E8], rax
0x180011e32  mov     [rbp+160h+var_1E0], r14
0x180011e36  mov     [rbp+160h+var_1D0], r14d
0x180011e3a  xorps   xmm0, xmm0
0x180011e3d  movdqa  [rbp+160h+var_130], xmm0
0x180011e42  xor     edx, edx; Val
0x180011e44  mov     r8d, 98h; Size
0x180011e4a  lea     rcx, [rbp+160h+var_1C8]; void *
0x180011e4e  call    memset_0
0x180011e53  lea     ebx, [r14+1]
0x180011e57  mov     [rbp+160h+var_120], ebx
0x180011e5a  xor     eax, eax
0x180011e5c  mov     [rbp+160h+var_118], rax
0x180011e60  lea     rax, [rsp+260h+var_218]
0x180011e65  mov     [rbp+160h+var_110], rax
0x180011e69  mov     [rbp+160h+var_108], r14
0x180011e6d  mov     [rbp+160h+var_100], r14
0x180011e71  lea     rax, [rsp+260h+var_220]
0x180011e76  mov     [rbp+160h+var_F8], rax
0x180011e7a  mov     [rbp+160h+var_F0], r14
0x180011e7e  mov     [rbp+160h+var_E8], r14d
0x180011e82  lea     rax, [rsp+260h+var_1F0]
0x180011e87  mov     [rbp+160h+var_E0], rax
0x180011e8e  mov     [rbp+160h+var_D8], r14b
0x180011e95  lea     r15, ??_7CreateProvisioningSession@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession::`vftable'
0x180011e9c  mov     [rsp+260h+var_220], r15
0x180011ea1  lea     rcx, [rsp+260h+var_220]; this
0x180011ea6  call    ?StartActivity@CreateProvisioningSession@ProvOpsTelemetry@Logging@Provisioning@Management@Internal@Windows@@QEAAXXZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsTelemetry::CreateProvisioningSession::StartActivity(void)
0x180011eab  nop
0x180011eac  lea     rax, [rsp+260h+var_220]
0x180011eb1  mov     qword ptr [rsp+260h+Uuid.Data1], rax
0x180011eb6  mov     [rsp+260h+Uuid.Data4], bl
0x180011eba  lea     rsi, [rdi+30h]
0x180011ebe  mov     rcx, [rsi]
0x180011ec1  test    rcx, rcx
0x180011ec4  jz      short loc_180011ED6
0x180011ec6  mov     [rsi], r14
0x180011ec9  mov     rax, [rcx]
0x180011ecc  mov     rax, [rax+10h]
0x180011ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed5  nop
0x180011ed6  mov     qword ptr [rsp+260h+ppv], rsi; int
0x180011edb  lea     r9, _GUID_4ebf49ca_8a92_4057_93ee_237fc110897d; riid
0x180011ee2  mov     r8d, ebx; dwClsContext
0x180011ee5  xor     edx, edx; pUnkOuter
0x180011ee7  lea     rcx, _GUID_e7a8b38f_ae80_4753_b520_433d402e6379; rclsid
0x180011eee  call    cs:__imp_CoCreateInstance
0x180011ef4  mov     ebx, eax
0x180011ef6  test    eax, eax
0x180011ef8  jns     short loc_180011F01
0x180011efa  mov     edx, 52Bh
0x180011eff  jmp     short loc_180011F29
0x180011f01  mov     rcx, [rsi]
0x180011f04  mov     rax, [rcx]
0x180011f07  lea     rdx, [rdi+10h]
0x180011f0b  cmp     qword ptr [rdx+18h], 8
0x180011f10  jb      short loc_180011F15
0x180011f12  mov     rdx, [rdx]
0x180011f15  mov     rax, [rax+18h]
0x180011f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f1e  mov     ebx, eax
0x180011f20  test    eax, eax
0x180011f22  jns     short loc_180011F44
0x180011f24  mov     edx, 52Dh; void *
0x180011f29  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\prov\\provops\\lib\\"...
0x180011f30  mov     r9d, eax; char *
0x180011f33  mov     rcx, [rbp+168h]; this
0x180011f3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f3f  jmp     loc_180012071
0x180011f44  mov     rcx, [rsi]
0x180011f47  mov     rax, [rcx]
0x180011f4a  lea     r8, [rbp+160h+Source]
0x180011f51  mov     esi, 81h
0x180011f56  mov     edx, esi
0x180011f58  mov     rax, [rax+30h]
0x180011f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f61  xor     edx, edx
0x180011f63  lea     rcx, [rbp+160h+Source]
0x180011f6a  call    ?ValidateImpl@TraceLoggingCorrelationVector@@CA?AW4CvVersion@1@PEBD_N@Z; TraceLoggingCorrelationVector::ValidateImpl(char const *,bool)
0x180011f6f  test    al, al
0x180011f71  jnz     loc_18001204F
0x180011f77  call    ?Provider@ProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider::Provider(void)
0x180011f7c  mov     ecx, [rax]
0x180011f7e  cmp     ecx, 5
0x180011f81  jbe     short loc_180011FB0
0x180011f83  lea     rcx, [rbp+160h+Source]
0x180011f8a  mov     qword ptr [rsp+260h+Uuid.Data1], rcx
0x180011f8f  mov     r8, [rbp+160h+var_110]
0x180011f93  add     r8, 8
0x180011f97  lea     rcx, [rsp+260h+Uuid]
0x180011f9c  mov     qword ptr [rsp+260h+ppv], rcx
0x180011fa1  lea     rdx, dword_18004045C
0x180011fa8  mov     rcx, rax
0x180011fab  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180011fb0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011fb7  mov     ecx, 90h; unsigned __int64
0x180011fbc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011fc1  mov     rbx, rax
0x180011fc4  mov     qword ptr [rsp+260h+Uuid.Data1], rax
0x180011fc9  test    rax, rax
0x180011fcc  jz      short loc_180012032
0x180011fce  mov     byte ptr [rax+82h], 41h ; 'A'
0x180011fd5  xorps   xmm0, xmm0
0x180011fd8  movups  xmmword ptr [rsp+260h+Uuid.Data1], xmm0
0x180011fdd  lea     rcx, [rsp+260h+Uuid]; Uuid
0x180011fe2  call    cs:__imp_UuidCreate
0x180011fe8  movaps  xmm0, xmmword ptr [rsp+260h+Uuid.Data1]
0x180011fed  movdqa  xmmword ptr [rsp+260h+Uuid.Data1], xmm0
0x180011ff3  mov     byte ptr [rbx+81h], 11h
0x180011ffa  mov     rax, 1300000000h
0x180012004  mov     [rbx+88h], rax
0x18001200b  mov     r8, rsi; Size
0x18001200e  xor     edx, edx; Val
0x180012010  mov     rcx, rbx; void *
0x180012013  call    memset_0
0x180012018  mov     r8, rbx
0x18001201b  mov     edx, 0Ch
0x180012020  lea     rcx, [rsp+260h+Uuid]
0x180012025  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18001202a  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180012030  jmp     short loc_180012035
0x180012032  mov     rbx, r14
0x180012035  mov     rcx, [rdi+38h]
0x180012039  mov     [rdi+38h], rbx
0x18001203d  test    rcx, rcx
0x180012040  jz      short loc_180012048
0x180012042  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012048  mov     ebx, 80004005h
0x18001204d  jmp     short loc_180012071
0x18001204f  lea     rcx, [rbp+160h+Source]; Source
0x180012056  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x18001205b  mov     rcx, [rdi+38h]
0x18001205f  mov     [rdi+38h], rax
0x180012063  test    rcx, rcx
0x180012066  jz      short loc_18001206E
0x180012068  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001206e  mov     ebx, r14d
0x180012071  lea     rcx, [rsp+260h+var_220]
0x180012076  call    ?Stop@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001207b  nop
0x18001207c  mov     [rsp+260h+var_220], r15
0x180012081  lea     rcx, [rsp+260h+var_220]
0x180012086  call    ?Destroy@?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001208b  lea     rcx, [rsp+260h+var_220]
0x180012090  call    ??1?$ActivityBase@VProvOpsLoggingProvider@Logging@Provisioning@Management@Internal@Windows@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Management::Provisioning::Logging::ProvOpsLoggingProvider,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180012095  mov     eax, ebx
0x180012097  mov     rcx, [rbp+160h+var_40]
0x18001209e  xor     rcx, rsp; StackCookie
0x1800120a1  call    __security_check_cookie
0x1800120a6  add     rsp, 238h
0x1800120ad  pop     r15
0x1800120af  pop     r14
0x1800120b1  pop     rdi
0x1800120b2  pop     rsi
0x1800120b3  pop     rbx
0x1800120b4  pop     rbp
0x1800120b5  retn
```
