# _lambda_fca37cefd63776a0e871ccafc44a49bc_::operator()(void)

- ea: `0x180004820`
- end: `0x1800049f7`
- name: `??R_lambda_fca37cefd63776a0e871ccafc44a49bc_@@QEBA@XZ`
- size: `471`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006dc0`

## callees

- `0x1800026d0`
- `0x18000289c`
- `0x180004820`
- `0x180004f8c`
- `0x180004fc4`
- `0x180006cf4`
- `0x180006d14`
- `0x180006e94`
- `0x180006f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000487a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000487a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800049b8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800049b8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800049a8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800049df`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800049a8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800049df`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000483e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000483e`

## string_xrefs

- `0x18000485f`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180004962`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall _lambda_fca37cefd63776a0e871ccafc44a49bc_::operator()(__int64 a1)
{
  const char *v2; // r9
  __int64 v3; // rdx
  LPVOID v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rax
  int v10; // edi
  __int64 v11; // rdx
  CloudIdSvcModule *v12; // rcx
  __int64 v13; // [rsp+20h] [rbp-28h]
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = RegisterServiceCtrlHandlerExW(
                                       L"cloudidsvc",
                                       Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic,
                                       *(LPVOID *)a1);
  if ( !*(_QWORD *)(*(_QWORD *)a1 + 8LL) )
  {
    v3 = 509;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
             v2);
  }
  *(_QWORD *)(*(_QWORD *)a1 + 48LL) = CreateEventW(0, 0, 0, 0);
  v5 = *(LPVOID *)a1;
  if ( !*(_QWORD *)(*(_QWORD *)a1 + 48LL) )
  {
    v3 = 512;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v3,
             (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
             v2);
  }
  if ( **(_BYTE **)(a1 + 8) )
  {
    v6 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create();
    if ( *(_QWORD *)(v6 + 48) )
      goto LABEL_12;
    byte_180019950 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_180019948 = (__int64)Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync;
    v9 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_;
    byte_180019938 = 0;
    qword_180019940 = (__int64)v5;
  }
  else
  {
    v6 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create();
    if ( *(_QWORD *)(v6 + 48) )
      goto LABEL_12;
    byte_180019920 = 1;
    Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable';
    qword_180019918 = (__int64)Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync;
    v9 = &Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_;
    byte_180019908 = 0;
    qword_180019910 = (__int64)v5;
  }
  *(_QWORD *)(v6 + 48) = v9;
LABEL_12:
  **(_QWORD **)(a1 + 16) = v6;
  v10 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
          **(_QWORD **)(a1 + 16),
          **(_BYTE **)(a1 + 8),
          v7,
          v8,
          v13);
  if ( v10 < 0 )
  {
    v11 = 545;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v10,
      v14);
    return (unsigned int)v10;
  }
  v10 = CloudIdSvcModule::ServiceStarted(*(CloudIdSvcModule **)a1);
  **(_DWORD **)(a1 + 24) = v10;
  if ( v10 < 0 )
  {
    v11 = 547;
    goto LABEL_14;
  }
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v16, *(_QWORD *)a1);
  SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
  WaitForSingleObject(*(HANDLE *)(*(_QWORD *)a1 + 48LL), 0xFFFFFFFF);
  v12 = *(CloudIdSvcModule **)a1;
  if ( ((*(_DWORD *)(*(_QWORD *)a1 + 20LL) - 1) & 0xFFFFFFFD) != 0 )
  {
    *((_DWORD *)v12 + 5) = 3;
    SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(*(_QWORD *)a1 + 8LL), (LPSERVICE_STATUS)(*(_QWORD *)a1 + 16LL));
  }
  CloudIdSvcModule::ServiceStopped(v12);
  return 0;
}

```

## disassembly

```asm
0x180004820  mov     [rsp+arg_8], rbx
0x180004825  push    rdi
0x180004826  sub     rsp, 40h
0x18000482a  mov     r8, [rcx]; lpContext
0x18000482d  lea     rdx, ?HandlerExStatic@?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z; lpHandlerProc
0x180004834  mov     rbx, rcx
0x180004837  lea     rcx, ServiceName; "cloudidsvc"
0x18000483e  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180004844  mov     rdx, [rbx]
0x180004847  mov     [rdx+8], rax
0x18000484b  mov     rax, [rbx]
0x18000484e  cmp     qword ptr [rax+8], 0
0x180004853  jnz     short loc_180004870
0x180004855  mov     edx, 1FDh; void *
0x18000485a  mov     rcx, [rsp+48h]; this
0x18000485f  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180004866  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000486b  jmp     loc_1800049EC
0x180004870  xor     r9d, r9d; lpName
0x180004873  xor     r8d, r8d; bInitialState
0x180004876  xor     edx, edx; bManualReset
0x180004878  xor     ecx, ecx; lpEventAttributes
0x18000487a  call    cs:__imp_CreateEventW
0x180004880  mov     rcx, [rbx]
0x180004883  mov     [rcx+30h], rax
0x180004887  mov     rdi, [rbx]
0x18000488a  cmp     qword ptr [rdi+30h], 0
0x18000488f  jnz     short loc_180004898
0x180004891  mov     edx, 200h
0x180004896  jmp     short loc_18000485A
0x180004898  mov     rax, [rbx+8]
0x18000489c  cmp     byte ptr [rax], 0
0x18000489f  jz      short loc_1800048EE
0x1800048a1  call    ?Create@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVServiceModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::Create(void)
0x1800048a6  mov     rcx, rax
0x1800048a9  cmp     qword ptr [rax+30h], 0
0x1800048ae  jnz     loc_180004939
0x1800048b4  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x1800048bb  mov     cs:byte_180019950, 1
0x1800048c2  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x1800048c9  lea     rax, ?StopAsync@?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ; Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)
0x1800048d0  mov     cs:qword_180019948, rax
0x1800048d7  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::ServiceModule>::instance_
0x1800048de  mov     cs:byte_180019938, 0
0x1800048e5  mov     cs:qword_180019940, rdi
0x1800048ec  jmp     short loc_180004935
0x1800048ee  call    ?Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create(void)
0x1800048f3  mov     rcx, rax
0x1800048f6  cmp     qword ptr [rax+30h], 0
0x1800048fb  jnz     short loc_180004939
0x1800048fd  lea     rax, ??_7?$MethodReleaseNotifier@V?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`vftable'
0x180004904  mov     cs:byte_180019920, 1
0x18000490b  mov     cs:?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rax; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x180004912  lea     rax, ?StopAsync@?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ; Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)
0x180004919  mov     cs:qword_180019918, rax
0x180004920  lea     rax, ?instance_@?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::instance_
0x180004927  mov     cs:byte_180019908, 0
0x18000492e  mov     cs:qword_180019910, rdi
0x180004935  mov     [rcx+30h], rax
0x180004939  mov     rax, [rbx+10h]
0x18000493d  mov     [rax], rcx
0x180004940  mov     rdx, [rbx+8]
0x180004944  mov     rcx, [rbx+10h]
0x180004948  mov     dl, [rdx]
0x18000494a  mov     rcx, [rcx]
0x18000494d  call    ??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z; Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)
0x180004952  mov     edi, eax
0x180004954  test    eax, eax
0x180004956  jns     short loc_180004975
0x180004958  mov     edx, 221h; void *
0x18000495d  mov     rcx, [rsp+48h]; this
0x180004962  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180004969  mov     r9d, edi; char *
0x18000496c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004971  mov     eax, edi
0x180004973  jmp     short loc_1800049EC
0x180004975  mov     rcx, [rbx]; this
0x180004978  call    ?ServiceStarted@CloudIdSvcModule@@QEAAJXZ; CloudIdSvcModule::ServiceStarted(void)
0x18000497d  mov     rcx, [rbx+18h]
0x180004981  mov     edi, eax
0x180004983  mov     [rcx], eax
0x180004985  test    eax, eax
0x180004987  jns     short loc_180004990
0x180004989  mov     edx, 223h
0x18000498e  jmp     short loc_18000495D
0x180004990  mov     rdx, [rbx]
0x180004993  lea     rcx, [rsp+48h+arg_0]
0x180004998  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18000499d  mov     rcx, [rbx]
0x1800049a0  lea     rdx, [rcx+10h]; lpServiceStatus
0x1800049a4  mov     rcx, [rcx+8]; hServiceStatus
0x1800049a8  call    cs:__imp_SetServiceStatus
0x1800049ae  mov     rcx, [rbx]
0x1800049b1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800049b4  mov     rcx, [rcx+30h]; hHandle
0x1800049b8  call    cs:__imp_WaitForSingleObject
0x1800049be  mov     rcx, [rbx]
0x1800049c1  mov     eax, [rcx+14h]
0x1800049c4  dec     eax
0x1800049c6  test    eax, 0FFFFFFFDh
0x1800049cb  jz      short loc_1800049E5
0x1800049cd  mov     dword ptr [rcx+14h], 3
0x1800049d4  mov     rcx, [rbx]
0x1800049d7  lea     rdx, [rcx+10h]; lpServiceStatus
0x1800049db  mov     rcx, [rcx+8]; hServiceStatus
0x1800049df  call    cs:__imp_SetServiceStatus
0x1800049e5  call    ?ServiceStopped@CloudIdSvcModule@@QEAAXXZ; CloudIdSvcModule::ServiceStopped(void)
0x1800049ea  xor     eax, eax
0x1800049ec  mov     rbx, [rsp+48h+arg_8]
0x1800049f1  add     rsp, 40h
0x1800049f5  pop     rdi
0x1800049f6  retn
```
