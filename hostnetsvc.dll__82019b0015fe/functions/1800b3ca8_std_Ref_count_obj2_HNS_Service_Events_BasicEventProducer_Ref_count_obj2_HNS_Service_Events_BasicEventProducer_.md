# std::_Ref_count_obj2<HNS::Service::Events::BasicEventProducer>::_Ref_count_obj2<HNS::Service::Events::BasicEventProducer>(void)

- ea: `0x1800b3ca8`
- end: `0x1800b3e35`
- name: `??$?0$$V@?$_Ref_count_obj2@VBasicEventProducer@Events@Service@HNS@@@std@@QEAA@XZ`
- size: `397`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bef60`
- `0x1800ec7a0`

## callees

- `0x18005f59c`
- `0x18005ffc4`
- `0x1800663fc`
- `0x1800666d4`
- `0x1800b3ca8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b3d73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b3d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3d44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3d44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3d54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3d95`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3d54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800b3d95`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b3d62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b3d62`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b3d6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b3d6b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800b3d32`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800b3d32`

## string_xrefs

- `0x1800b3e23`: `onecore\vm\dv\net\hns\service\events\AsyncEventProducer.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Ref_count_obj2<HNS::Service::Events::BasicEventProducer>::_Ref_count_obj2<HNS::Service::Events::BasicEventProducer>(
        __int64 a1)
{
  __int64 v2; // rsi
  struct _TP_WAIT *ThreadpoolWait; // rbp
  const char *v4; // r9
  struct _TP_WAIT *v5; // r14
  DWORD LastError; // ebx
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<HNS::Service::Events::BasicEventProducer>::`vftable';
  v2 = a1 + 16;
  memset_0((void *)(a1 + 16), 0, 0x80u);
  *(_QWORD *)v2 = &HNS::Service::Events::IEventProducer::`vftable';
  *(_QWORD *)(v2 + 8) = &HNS::Service::Events::AsyncEventProducer::`vftable';
  *(_QWORD *)(v2 + 32) = &HNS::Service::Common::ConcurrentVector<std::shared_ptr<HNS::Service::Events::Event>>::`vftable';
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    v2 + 16,
    0);
  ThreadpoolWait = CreateThreadpoolWait(
                     _lambda_757920fc641ad800c54527e2324f6306_::_lambda_invoker_cdecl_,
                     (PVOID)(v2 + 8),
                     0);
  v5 = *(struct _TP_WAIT **)(v2 + 24);
  if ( v5 )
  {
    LastError = GetLastError();
    SetThreadpoolWait(v5, 0, 0);
    WaitForThreadpoolWaitCallbacks(v5, 1);
    CloseThreadpoolWait(v5);
    SetLastError(LastError);
  }
  *(_QWORD *)(v2 + 24) = ThreadpoolWait;
  if ( !ThreadpoolWait )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\events\\AsyncEventProducer.h",
      v4);
  SetThreadpoolWait(ThreadpoolWait, *(HANDLE *)(v2 + 16), 0);
  *(_DWORD *)(v2 + 72) = 1;
  *(_QWORD *)v2 = &HNS::Service::Events::BasicEventProducer::`vftable'{for `HNS::Service::Events::IEventProducer'};
  *(_QWORD *)(v2 + 8) = &HNS::Service::Events::BasicEventProducer::`vftable'{for `HNS::Service::Events::AsyncEventProducer'};
  *(_QWORD *)(v2 + 80) = 0;
  *(_QWORD *)(v2 + 88) = 0;
  v7 = operator new(0x78u);
  *v7 = v7;
  v7[1] = v7;
  *(_QWORD *)(v2 + 80) = v7;
  *(_QWORD *)(v2 + 96) = 0;
  *(_QWORD *)(v2 + 104) = 0;
  v8 = operator new(0x78u);
  *v8 = v8;
  v8[1] = v8;
  *(_QWORD *)(v2 + 96) = v8;
  *(_QWORD *)(v2 + 112) = 0;
  *(_QWORD *)(v2 + 120) = 0;
  return a1;
}

```

## disassembly

```asm
0x1800b3ca8  mov     [rsp+arg_10], rbx
0x1800b3cad  mov     [rsp+arg_18], rbp
0x1800b3cb2  push    rsi
0x1800b3cb3  push    rdi
0x1800b3cb4  push    r12
0x1800b3cb6  push    r14
0x1800b3cb8  push    r15
0x1800b3cba  sub     rsp, 30h
0x1800b3cbe  mov     r15, rcx
0x1800b3cc1  mov     dword ptr [rcx+8], 1
0x1800b3cc8  mov     dword ptr [rcx+0Ch], 1
0x1800b3ccf  lea     rax, ??_7?$_Ref_count_obj2@VBasicEventProducer@Events@Service@HNS@@@std@@6B@; const std::_Ref_count_obj2<HNS::Service::Events::BasicEventProducer>::`vftable'
0x1800b3cd6  mov     [rcx], rax
0x1800b3cd9  lea     rsi, [rcx+10h]
0x1800b3cdd  mov     [rsp+58h+arg_0], rsi
0x1800b3ce2  xor     edx, edx; Val
0x1800b3ce4  mov     r8d, 80h; Size
0x1800b3cea  mov     rcx, rsi; void *
0x1800b3ced  call    memset_0
0x1800b3cf2  lea     rax, ??_7IEventProducer@Events@Service@HNS@@6B@; const HNS::Service::Events::IEventProducer::`vftable'
0x1800b3cf9  mov     [rsi], rax
0x1800b3cfc  lea     rdi, [rsi+8]
0x1800b3d00  mov     [rsp+58h+arg_8], rdi
0x1800b3d05  lea     rax, ??_7AsyncEventProducer@Events@Service@HNS@@6B@; const HNS::Service::Events::AsyncEventProducer::`vftable'
0x1800b3d0c  mov     [rdi], rax
0x1800b3d0f  lea     rax, ??_7?$ConcurrentVector@V?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Common@Service@HNS@@6B@; const HNS::Service::Common::ConcurrentVector<std::shared_ptr<HNS::Service::Events::Event>>::`vftable'
0x1800b3d16  mov     [rdi+18h], rax
0x1800b3d1a  xor     edx, edx
0x1800b3d1c  lea     rcx, [rdi+8]
0x1800b3d20  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800b3d25  xor     r8d, r8d; pcbe
0x1800b3d28  mov     rdx, rdi; pv
0x1800b3d2b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_757920fc641ad800c54527e2324f6306_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800b3d32  call    cs:__imp_CreateThreadpoolWait
0x1800b3d38  mov     rbp, rax
0x1800b3d3b  mov     r14, [rdi+10h]
0x1800b3d3f  test    r14, r14
0x1800b3d42  jz      short loc_1800B3D79
0x1800b3d44  call    cs:__imp_GetLastError
0x1800b3d4a  mov     ebx, eax
0x1800b3d4c  xor     r8d, r8d; pftTimeout
0x1800b3d4f  xor     edx, edx; h
0x1800b3d51  mov     rcx, r14; pwa
0x1800b3d54  call    cs:__imp_SetThreadpoolWait
0x1800b3d5a  mov     edx, 1; fCancelPendingCallbacks
0x1800b3d5f  mov     rcx, r14; pwa
0x1800b3d62  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800b3d68  mov     rcx, r14; pwa
0x1800b3d6b  call    cs:__imp_CloseThreadpoolWait
0x1800b3d71  mov     ecx, ebx; dwErrCode
0x1800b3d73  call    cs:__imp_SetLastError
0x1800b3d79  mov     [rdi+10h], rbp
0x1800b3d7d  mov     rcx, [rsp+58h]; this
0x1800b3d82  test    rbp, rbp
0x1800b3d85  jz      loc_1800B3E23
0x1800b3d8b  xor     r8d, r8d; pftTimeout
0x1800b3d8e  mov     rdx, [rdi+8]; h
0x1800b3d92  mov     rcx, rbp; pwa
0x1800b3d95  call    cs:__imp_SetThreadpoolWait
0x1800b3d9b  mov     dword ptr [rdi+40h], 1
0x1800b3da2  lea     rax, ??_7BasicEventProducer@Events@Service@HNS@@6BIEventProducer@123@@; const HNS::Service::Events::BasicEventProducer::`vftable'{for `HNS::Service::Events::IEventProducer'}
0x1800b3da9  mov     [rsi], rax
0x1800b3dac  lea     rax, ??_7BasicEventProducer@Events@Service@HNS@@6BAsyncEventProducer@123@@; const HNS::Service::Events::BasicEventProducer::`vftable'{for `HNS::Service::Events::AsyncEventProducer'}
0x1800b3db3  mov     [rdi], rax
0x1800b3db6  mov     qword ptr [rsi+50h], 0
0x1800b3dbe  mov     qword ptr [rsi+58h], 0
0x1800b3dc6  mov     ebx, 78h ; 'x'
0x1800b3dcb  mov     ecx, ebx; Size
0x1800b3dcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b3dd2  mov     [rax], rax
0x1800b3dd5  mov     [rax+8], rax
0x1800b3dd9  mov     [rsi+50h], rax
0x1800b3ddd  mov     qword ptr [rsi+60h], 0
0x1800b3de5  mov     qword ptr [rsi+68h], 0
0x1800b3ded  mov     ecx, ebx; Size
0x1800b3def  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b3df4  mov     [rax], rax
0x1800b3df7  mov     [rax+8], rax
0x1800b3dfb  mov     [rsi+60h], rax
0x1800b3dff  xor     eax, eax
0x1800b3e01  mov     [rsi+70h], rax
0x1800b3e05  mov     [rsi+78h], rax
0x1800b3e09  mov     rax, r15
0x1800b3e0c  mov     rbx, [rsp+58h+arg_10]
0x1800b3e11  mov     rbp, [rsp+58h+arg_18]
0x1800b3e16  add     rsp, 30h
0x1800b3e1a  pop     r15
0x1800b3e1c  pop     r14
0x1800b3e1e  pop     r12
0x1800b3e20  pop     rdi
0x1800b3e21  pop     rsi
0x1800b3e22  retn
0x1800b3e23  lea     r8, aOnecoreVmDvNet_196; "onecore\\vm\\dv\\net\\hns\\service\\eve"...
0x1800b3e2a  mov     edx, 71h ; 'q'; void *
0x1800b3e2f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
