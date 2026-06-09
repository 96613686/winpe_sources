# ActiveProbeManager::PerFamilyInterfaceProbeInfo::PerFamilyInterfaceProbeInfo(_NET_LUID_LH,NcsiProbePerformReason,_NLA_CONNECTIVITY_FAMILY,unsigned __int64,bool)

- ea: `0x1800422b8`
- end: `0x180042385`
- name: `??0PerFamilyInterfaceProbeInfo@ActiveProbeManager@@QEAA@T_NET_LUID_LH@@W4NcsiProbePerformReason@@W4_NLA_CONNECTIVITY_FAMILY@@_K_N@Z`
- size: `205`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180042220`

## callees

- `0x18002e960`
- `0x1800422b8`
- `0x180055860`
- `0x180069774`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004231a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004231a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800422e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800422e3`

## pseudocode

```c
__int64 __fastcall ActiveProbeManager::PerFamilyInterfaceProbeInfo::PerFamilyInterfaceProbeInfo(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        char a6)
{
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  InitializeCriticalSectionEx((LPCRITICAL_SECTION)a1, 0x1F4u, 0);
  ActiveProbeManager::PerFamilyInterfaceProbeInfo::_unnamed_type_m_lockedData_::_unnamed_type_m_lockedData_(a1 + 40);
  *(_QWORD *)(a1 + 3224) = 0;
  *(_DWORD *)(a1 + 3232) = 0;
  *(_QWORD *)(a1 + 3240) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(
                      ActiveProbeManager::PerFamilyInterfaceProbeInfo::NcsiQueueActiveInternetProbe,
                      (PVOID)a1,
                      0);
  if ( !ThreadpoolTimer )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\activeprobemanager\\lib\\activeprobemanager.cpp",
      v11);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    a1 + 3240,
    ThreadpoolTimer);
  *(_QWORD *)(a1 + 3224) = a2;
  *(_DWORD *)(a1 + 3232) = a4;
  *(_QWORD *)(a1 + 3120) = a5;
  *(_BYTE *)(a1 + 3129) = a6;
  *(_DWORD *)(a1 + 3096) = a3;
  return a1;
}

```

## disassembly

```asm
0x1800422b8  mov     [rsp+arg_8], rbx
0x1800422bd  mov     [rsp+arg_10], rbp
0x1800422c2  mov     [rsp+arg_0], rcx
0x1800422c7  push    rsi
0x1800422c8  push    rdi
0x1800422c9  push    r14
0x1800422cb  sub     rsp, 20h
0x1800422cf  mov     ebp, r9d
0x1800422d2  mov     r14d, r8d
0x1800422d5  mov     rbx, rdx
0x1800422d8  mov     rdi, rcx
0x1800422db  xor     r8d, r8d; Flags
0x1800422de  mov     edx, 1F4h; dwSpinCount
0x1800422e3  call    cs:__imp_InitializeCriticalSectionEx
0x1800422e9  nop
0x1800422ea  lea     rcx, [rdi+28h]
0x1800422ee  call    ActiveProbeManager__PerFamilyInterfaceProbeInfo___unnamed_type_m_lockedData____unnamed_type_m_lockedData_
0x1800422f3  nop
0x1800422f4  xor     eax, eax
0x1800422f6  mov     [rdi+0C98h], rax
0x1800422fd  mov     [rdi+0CA0h], eax
0x180042303  lea     rsi, [rdi+0CA8h]
0x18004230a  mov     [rsi], rax
0x18004230d  xor     r8d, r8d; pcbe
0x180042310  mov     rdx, rdi; pv
0x180042313  lea     rcx, ?NcsiQueueActiveInternetProbe@PerFamilyInterfaceProbeInfo@ActiveProbeManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004231a  call    cs:__imp_CreateThreadpoolTimer
0x180042320  mov     rcx, [rsp+38h]; this
0x180042325  test    rax, rax
0x180042328  jnz     short loc_18004233A
0x18004232a  lea     r8, aOnecoreNetDiag_0; "onecore\\net\\diagnostics\\ncsi\\active"...
0x180042331  lea     edx, [rax+73h]; void *
0x180042334  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004233a  mov     rdx, rax
0x18004233d  mov     rcx, rsi
0x180042340  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180042345  mov     [rdi+0C98h], rbx
0x18004234c  mov     [rdi+0CA0h], ebp
0x180042352  mov     rax, [rsp+38h+arg_20]
0x180042357  mov     [rdi+0C30h], rax
0x18004235e  mov     al, [rsp+38h+arg_28]
0x180042362  mov     [rdi+0C39h], al
0x180042368  mov     [rdi+0C18h], r14d
0x18004236f  mov     rax, rdi
0x180042372  mov     rbx, [rsp+38h+arg_8]
0x180042377  mov     rbp, [rsp+38h+arg_10]
0x18004237c  add     rsp, 20h
0x180042380  pop     r14
0x180042382  pop     rdi
0x180042383  pop     rsi
0x180042384  retn
```
