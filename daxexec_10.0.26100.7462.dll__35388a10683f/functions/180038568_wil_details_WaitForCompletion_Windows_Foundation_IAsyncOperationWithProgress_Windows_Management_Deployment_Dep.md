# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180038568`
- end: `0x1800388a7`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ddec`

## callees

- `0x18000937c`
- `0x18000d508`
- `0x18000e234`
- `0x18000f2e0`
- `0x180038568`
- `0x180038d98`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038638`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180038638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038650`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038783`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038783`

## string_xrefs

- `0x1800386b3`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x1800386ff`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x180038727`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x1800387b0`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(
        __int64 a1,
        DWORD a2,
        DWORD a3,
        _BYTE *a4)
{
  _DWORD *v8; // rbx
  unsigned int v9; // edi
  wil::details *v10; // rcx
  HANDLE Event; // r15
  int v12; // eax
  int v13; // ebx
  _DWORD *v14; // rcx
  int LastErrorFailHr; // eax
  _DWORD *v17; // rcx
  HRESULT v18; // eax
  _DWORD *v19; // rcx
  __int64 v20; // rcx
  _DWORD *v21; // rcx
  _DWORD *v22; // rcx
  int lpdwindex; // [rsp+20h] [rbp-30h]
  int lpdwindexa; // [rsp+20h] [rbp-30h]
  DWORD dwindex; // [rsp+30h] [rbp-20h] BYREF
  _DWORD *v26; // [rsp+38h] [rbp-18h]
  __int64 v27; // [rsp+40h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v30; // [rsp+98h] [rbp+48h] BYREF

  if ( a4 )
    *a4 = 0;
  v26 = 0;
  v8 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v8 )
  {
    v9 = -2147024882;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65A,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)v9,
      lpdwindex);
    v17 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v9;
  }
  *(_QWORD *)v8 = &Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v8 + 2));
  v8[11] = 1;
  *(_QWORD *)v8 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'};
  *((_QWORD *)v8 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v8 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v8 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v8[12] = 0;
  *((_QWORD *)v8 + 7) = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v8 + 14,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v10);
    v9 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63D,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
        (const char *)(unsigned int)LastErrorFailHr,
        lpdwindex);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
      goto LABEL_15;
    }
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 8LL))(v8);
  v26 = v8;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  v12 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a1 + 64LL))(a1, v8);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v12,
      lpdwindex);
    v14 = v26;
    v26 = 0;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v14 + 16LL))(v14);
    return (unsigned int)v13;
  }
  pHandles = (HANDLE)*((_QWORD *)v26 + 7);
  dwindex = 0;
  v18 = CoWaitForMultipleHandles(a2, a3, 1u, &pHandles, &dwindex);
  v13 = v18;
  if ( a4 && v18 == -2147417835 )
  {
    *a4 = 1;
  }
  else
  {
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x667,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
        (const char *)(unsigned int)v18,
        lpdwindexa);
      v19 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return (unsigned int)v13;
    }
    if ( v26[12] != 1 )
    {
      v27 = 0;
      v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
              a1,
              &GUID_00000036_0000_0000_c000_000000000046,
              &v27);
      if ( v13 >= 0 )
      {
        v30 = -2147418113;
        v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 64LL))(v27, &v30);
        if ( v13 >= 0 )
          v13 = v30;
      }
      v20 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      v21 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v21 + 16LL))(v21);
      }
      return (unsigned int)v13;
    }
  }
  v22 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return 0;
}

```

## disassembly

```asm
0x180038568  mov     [rsp-28h+arg_0], rbx
0x18003856d  mov     [rsp-28h+arg_8], rsi
0x180038572  mov     [rsp-28h+arg_10], rdi
0x180038577  push    rbp
0x180038578  push    r12
0x18003857a  push    r13
0x18003857c  push    r14
0x18003857e  push    r15
0x180038580  mov     rbp, rsp
0x180038583  sub     rsp, 50h
0x180038587  mov     rsi, r9
0x18003858a  mov     r12d, r8d
0x18003858d  mov     r13d, edx
0x180038590  mov     r14, rcx
0x180038593  xor     r15d, r15d
0x180038596  test    r9, r9
0x180038599  jz      short loc_18003859E
0x18003859b  mov     [r9], r15b
0x18003859e  mov     [rbp+var_18], r15
0x1800385a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800385a9  mov     ecx, 40h ; '@'; unsigned __int64
0x1800385ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800385b3  mov     rbx, rax
0x1800385b6  test    rax, rax
0x1800385b9  jnz     short loc_1800385C5
0x1800385bb  mov     edi, 8007000Eh
0x1800385c0  jmp     loc_180038720
0x1800385c5  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable'
0x1800385cc  mov     [rbx], rax
0x1800385cf  lea     rdi, [rbx+8]
0x1800385d3  mov     rcx, rdi; this
0x1800385d6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800385db  mov     dword ptr [rbx+2Ch], 1
0x1800385e2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'}
0x1800385e9  mov     [rbx], rax
0x1800385ec  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800385f3  mov     [rdi], rax
0x1800385f6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800385fd  test    rcx, rcx
0x180038600  jz      short loc_18003860F
0x180038602  mov     rax, [rcx]
0x180038605  mov     rax, [rax+8]
0x180038609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003860e  nop
0x18003860f  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>'}
0x180038616  mov     [rbx], rax
0x180038619  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180038620  mov     [rdi], rax
0x180038623  mov     [rbx+30h], r15d
0x180038627  mov     [rbx+38h], r15
0x18003862b  mov     r9d, 1F0003h; dwDesiredAccess
0x180038631  xor     r8d, r8d; dwFlags
0x180038634  xor     edx, edx; lpName
0x180038636  xor     ecx, ecx; lpEventAttributes
0x180038638  call    cs:__imp_CreateEventExW
0x18003863f  nop     dword ptr [rax+rax+00h]
0x180038644  mov     r15, rax
0x180038647  test    rax, rax
0x18003864a  jz      loc_1800386E6
0x180038650  call    cs:__imp_GetLastError
0x180038657  nop     dword ptr [rax+rax+00h]
0x18003865c  mov     rdx, r15
0x18003865f  lea     rcx, [rbx+38h]
0x180038663  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180038668  xor     r15d, r15d
0x18003866b  mov     rax, [rbx]
0x18003866e  mov     rcx, rbx
0x180038671  mov     rax, [rax+8]
0x180038675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003867a  nop
0x18003867b  mov     [rbp+var_18], rbx
0x18003867f  mov     rax, [rbx]
0x180038682  mov     rcx, rbx
0x180038685  mov     rax, [rax+10h]
0x180038689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003868e  nop
0x18003868f  mov     rax, [r14]
0x180038692  mov     rdx, [rbp+var_18]
0x180038696  mov     rcx, r14
0x180038699  mov     rax, [rax+40h]
0x18003869d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386a2  mov     ebx, eax
0x1800386a4  test    eax, eax
0x1800386a6  jns     loc_18003875A
0x1800386ac  mov     rcx, [rbp+28h]; this
0x1800386b0  mov     r9d, eax; char *
0x1800386b3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800386ba  mov     edx, 65Bh; void *
0x1800386bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800386c4  nop
0x1800386c5  mov     rcx, [rbp+var_18]
0x1800386c9  test    rcx, rcx
0x1800386cc  jz      short loc_1800386DF
0x1800386ce  mov     [rbp+var_18], r15
0x1800386d2  mov     rax, [rcx]
0x1800386d5  mov     rax, [rax+10h]
0x1800386d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386de  nop
0x1800386df  mov     eax, ebx
0x1800386e1  jmp     loc_180038888
0x1800386e6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800386eb  mov     edi, eax
0x1800386ed  xor     r15d, r15d
0x1800386f0  test    eax, eax
0x1800386f2  jns     loc_18003866B
0x1800386f8  mov     rcx, [rbp+28h]; this
0x1800386fc  mov     r9d, eax; char *
0x1800386ff  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180038706  mov     edx, 63Dh; void *
0x18003870b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038710  mov     rax, [rbx]
0x180038713  mov     rcx, rbx
0x180038716  mov     rax, [rax+10h]
0x18003871a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003871f  nop
0x180038720  mov     rcx, [rbp+28h]; this
0x180038724  mov     r9d, edi; char *
0x180038727  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003872e  mov     edx, 65Ah; void *
0x180038733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038738  nop
0x180038739  mov     rcx, [rbp+var_18]
0x18003873d  test    rcx, rcx
0x180038740  jz      short loc_180038753
0x180038742  mov     [rbp+var_18], r15
0x180038746  mov     rdx, [rcx]
0x180038749  mov     rax, [rdx+10h]
0x18003874d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038752  nop
0x180038753  mov     eax, edi
0x180038755  jmp     loc_180038888
0x18003875a  mov     rax, [rbp+var_18]
0x18003875e  mov     rcx, [rax+38h]
0x180038762  mov     [rbp+pHandles], rcx
0x180038766  mov     [rbp+dwindex], r15d
0x18003876a  lea     rax, [rbp+dwindex]
0x18003876e  mov     qword ptr [rsp+50h+lpdwindex], rax; int
0x180038773  lea     r9, [rbp+pHandles]; pHandles
0x180038777  mov     r8d, 1; cHandles
0x18003877d  mov     edx, r12d; dwTimeout
0x180038780  mov     ecx, r13d; dwFlags
0x180038783  call    cs:__imp_CoWaitForMultipleHandles
0x18003878a  nop     dword ptr [rax+rax+00h]
0x18003878f  mov     ebx, eax
0x180038791  test    rsi, rsi
0x180038794  jz      short loc_1800387A5
0x180038796  cmp     eax, 80010115h
0x18003879b  jnz     short loc_1800387A5
0x18003879d  mov     byte ptr [rsi], 1
0x1800387a0  jmp     loc_18003886C
0x1800387a5  test    ebx, ebx
0x1800387a7  jns     short loc_1800387E1
0x1800387a9  mov     rcx, [rbp+28h]; this
0x1800387ad  mov     r9d, ebx; char *
0x1800387b0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800387b7  mov     edx, 667h; void *
0x1800387bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800387c1  nop
0x1800387c2  mov     rcx, [rbp+var_18]
0x1800387c6  test    rcx, rcx
0x1800387c9  jz      short loc_1800387DC
0x1800387cb  mov     [rbp+var_18], r15
0x1800387cf  mov     rax, [rcx]
0x1800387d2  mov     rax, [rax+10h]
0x1800387d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387db  nop
0x1800387dc  jmp     loc_1800386DF
0x1800387e1  mov     rax, [rbp+var_18]
0x1800387e5  mov     ecx, [rax+30h]
0x1800387e8  cmp     ecx, 1
0x1800387eb  jz      short loc_18003886C
0x1800387ed  mov     [rbp+var_10], r15
0x1800387f1  mov     rax, [r14]
0x1800387f4  lea     r8, [rbp+var_10]
0x1800387f8  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800387ff  mov     rcx, r14
0x180038802  mov     rax, [rax]
0x180038805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003880a  mov     ebx, eax
0x18003880c  test    eax, eax
0x18003880e  js      short loc_180038833
0x180038810  mov     [rbp+arg_18], 8000FFFFh
0x180038817  mov     rcx, [rbp+var_10]
0x18003881b  mov     rax, [rcx]
0x18003881e  lea     rdx, [rbp+arg_18]
0x180038822  mov     rax, [rax+40h]
0x180038826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003882b  mov     ebx, eax
0x18003882d  test    eax, eax
0x18003882f  cmovns  ebx, [rbp+arg_18]
0x180038833  mov     rcx, [rbp+var_10]
0x180038837  test    rcx, rcx
0x18003883a  jz      short loc_18003884D
0x18003883c  mov     [rbp+var_10], r15
0x180038840  mov     rax, [rcx]
0x180038843  mov     rax, [rax+10h]
0x180038847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003884c  nop
0x18003884d  mov     rcx, [rbp+var_18]
0x180038851  test    rcx, rcx
0x180038854  jz      short loc_180038867
0x180038856  mov     [rbp+var_18], r15
0x18003885a  mov     rax, [rcx]
0x18003885d  mov     rax, [rax+10h]
0x180038861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038866  nop
0x180038867  jmp     loc_1800386DF
0x18003886c  mov     rcx, [rbp+var_18]
0x180038870  test    rcx, rcx
0x180038873  jz      short loc_180038886
0x180038875  mov     [rbp+var_18], r15
0x180038879  mov     rax, [rcx]
0x18003887c  mov     rax, [rax+10h]
0x180038880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038885  nop
0x180038886  xor     eax, eax
0x180038888  lea     r11, [rsp+50h+var_s0]
0x18003888d  mov     rbx, [r11+30h]
0x180038891  mov     rsi, [r11+38h]
0x180038895  mov     rdi, [r11+40h]
0x180038899  mov     rsp, r11
0x18003889c  pop     r15
0x18003889e  pop     r14
0x1800388a0  pop     r13
0x1800388a2  pop     r12
0x1800388a4  pop     rbp
0x1800388a5  retn
```
