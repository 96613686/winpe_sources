# HNS::Service::Common::Notify::INotifyable::StartNotify(void)

- ea: `0x1800f55cc`
- end: `0x1800f5695`
- name: `?StartNotify@INotifyable@Notify@Common@Service@HNS@@IEAAXXZ`
- size: `201`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f5540`
- `0x18012b330`
- `0x18013b354`
- `0x18025b770`

## callees

- `0x1800663fc`
- `0x1800666d4`
- `0x1800759d8`
- `0x180075aac`
- `0x1800f55cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f5644`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f5644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5615`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f5625`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f565d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f5625`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f565d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800f5633`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800f5633`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800f563c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800f563c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800f5603`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800f5603`

## string_xrefs

- `0x1800f55df`: `HNS::Service::Common::Notify::INotifyable::StartNotify`
- `0x1800f5668`: `HNS::Service::Common::Notify::INotifyable::StartNotify`
- `0x1800f5683`: `onecore\vm\dv\net\hns\service\common\notify\INotifyable.h`

## pseudocode

```c
void __fastcall HNS::Service::Common::Notify::INotifyable::StartNotify(HANDLE *pv)
{
  PTP_WAIT ThreadpoolWait; // rax
  const char *v3; // r9
  struct _TP_WAIT *v4; // rbp
  struct _TP_WAIT *v5; // rdi
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  HNSTraceProvider::TraceEnter("HNS::Service::Common::Notify::INotifyable::StartNotify", 0x19Au);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    pv + 1,
    0);
  ThreadpoolWait = CreateThreadpoolWait(HNS::Service::Common::Notify::INotifyable::WaitCallback, pv, 0);
  v4 = (struct _TP_WAIT *)pv[2];
  v5 = ThreadpoolWait;
  if ( v4 )
  {
    LastError = GetLastError();
    SetThreadpoolWait(v4, 0, 0);
    WaitForThreadpoolWaitCallbacks(v4, 1);
    CloseThreadpoolWait(v4);
    SetLastError(LastError);
  }
  pv[2] = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\notify\\INotifyable.h",
      v3);
  SetThreadpoolWait(v5, pv[1], 0);
  HNSTraceProvider::TraceSuccess("HNS::Service::Common::Notify::INotifyable::StartNotify", 0x19Du);
}

```

## disassembly

```asm
0x1800f55cc  push    rbx
0x1800f55ce  push    rbp
0x1800f55cf  push    rsi
0x1800f55d0  push    rdi
0x1800f55d1  push    r14
0x1800f55d3  sub     rsp, 30h
0x1800f55d7  mov     rsi, rcx
0x1800f55da  mov     edx, 19Ah; unsigned int
0x1800f55df  lea     rcx, aHnsServiceComm_0; "HNS::Service::Common::Notify::INotifyab"...
0x1800f55e6  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800f55eb  xor     edx, edx
0x1800f55ed  lea     rcx, [rsi+8]
0x1800f55f1  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800f55f6  xor     r8d, r8d; pcbe
0x1800f55f9  lea     rcx, ?WaitCallback@INotifyable@Notify@Common@Service@HNS@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800f5600  mov     rdx, rsi; pv
0x1800f5603  call    cs:__imp_CreateThreadpoolWait
0x1800f5609  mov     rbp, [rsi+10h]
0x1800f560d  mov     rdi, rax
0x1800f5610  test    rbp, rbp
0x1800f5613  jz      short loc_1800F564A
0x1800f5615  call    cs:__imp_GetLastError
0x1800f561b  xor     r8d, r8d; pftTimeout
0x1800f561e  xor     edx, edx; h
0x1800f5620  mov     rcx, rbp; pwa
0x1800f5623  mov     ebx, eax
0x1800f5625  call    cs:__imp_SetThreadpoolWait
0x1800f562b  mov     edx, 1; fCancelPendingCallbacks
0x1800f5630  mov     rcx, rbp; pwa
0x1800f5633  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800f5639  mov     rcx, rbp; pwa
0x1800f563c  call    cs:__imp_CloseThreadpoolWait
0x1800f5642  mov     ecx, ebx; dwErrCode
0x1800f5644  call    cs:__imp_SetLastError
0x1800f564a  mov     [rsi+10h], rdi
0x1800f564e  test    rdi, rdi
0x1800f5651  jz      short loc_1800F567E
0x1800f5653  mov     rdx, [rsi+8]; h
0x1800f5657  xor     r8d, r8d; pftTimeout
0x1800f565a  mov     rcx, rdi; pwa
0x1800f565d  call    cs:__imp_SetThreadpoolWait
0x1800f5663  mov     edx, 19Dh; unsigned int
0x1800f5668  lea     rcx, aHnsServiceComm_0; "HNS::Service::Common::Notify::INotifyab"...
0x1800f566f  add     rsp, 30h
0x1800f5673  pop     r14
0x1800f5675  pop     rdi
0x1800f5676  pop     rsi
0x1800f5677  pop     rbp
0x1800f5678  pop     rbx
0x1800f5679  jmp     ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1800f567e  mov     rcx, [rsp+58h]; this
0x1800f5683  lea     r8, aOnecoreVmDvNet_155; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x1800f568a  mov     edx, 1CDh; void *
0x1800f568f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
