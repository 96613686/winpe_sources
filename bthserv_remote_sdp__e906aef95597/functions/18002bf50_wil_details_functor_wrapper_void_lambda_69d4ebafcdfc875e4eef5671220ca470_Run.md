# wil::details::functor_wrapper_void__lambda_69d4ebafcdfc875e4eef5671220ca470___::Run

- ea: `0x18002bf50`
- end: `0x18002bfc3`
- name: `wil::details::functor_wrapper_void__lambda_69d4ebafcdfc875e4eef5671220ca470___::Run`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18002b02c`

## callees

- `0x18001f1cc`
- `0x18001f1e8`
- `0x18002bf50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002bf6e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002bf6e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002bf92`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002bf92`

## string_xrefs

- `0x18002bfb1`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingcontroller.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_69d4ebafcdfc875e4eef5671220ca470___::Run(__int64 a1)
{
  PVOID *v1; // rdi
  char *v2; // rbx
  PTP_WORK ThreadpoolWork; // rax
  const char *v4; // r9
  struct _TP_WORK *v5; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(PVOID **)(a1 + 8);
  v2 = (char *)*v1;
  ThreadpoolWork = CreateThreadpoolWork(
                     Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::s_PairingWorkerCallback,
                     *v1,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
    v2 + 16,
    ThreadpoolWork);
  v5 = (struct _TP_WORK *)*((_QWORD *)*v1 + 2);
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingcontroller.cpp",
      v4);
  SubmitThreadpoolWork(v5);
  return 0;
}

```

## disassembly

```asm
0x18002bf50  mov     [rsp+arg_0], rbx
0x18002bf55  push    rdi
0x18002bf56  sub     rsp, 20h
0x18002bf5a  mov     rdi, [rcx+8]
0x18002bf5e  xor     r8d, r8d; pcbe
0x18002bf61  lea     rcx, ?s_PairingWorkerCallback@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002bf68  mov     rbx, [rdi]
0x18002bf6b  mov     rdx, rbx; pv
0x18002bf6e  call    cs:__imp_CreateThreadpoolWork
0x18002bf75  nop     dword ptr [rax+rax+00h]
0x18002bf7a  mov     rdx, rax
0x18002bf7d  lea     rcx, [rbx+10h]
0x18002bf81  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18002bf86  mov     rax, [rdi]
0x18002bf89  mov     rcx, [rax+10h]; pwk
0x18002bf8d  test    rcx, rcx
0x18002bf90  jz      short loc_18002BFAC
0x18002bf92  call    cs:__imp_SubmitThreadpoolWork
0x18002bf99  nop     dword ptr [rax+rax+00h]
0x18002bf9e  mov     rbx, [rsp+28h+arg_0]
0x18002bfa3  xor     eax, eax
0x18002bfa5  add     rsp, 20h
0x18002bfa9  pop     rdi
0x18002bfaa  retn
0x18002bfac  mov     rcx, [rsp+28h]; this
0x18002bfb1  lea     r8, aOnecoreDrivers_12; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002bfb8  mov     edx, 138h; void *
0x18002bfbd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
