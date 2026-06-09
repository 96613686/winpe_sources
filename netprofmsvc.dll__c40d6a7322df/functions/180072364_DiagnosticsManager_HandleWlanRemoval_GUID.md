# DiagnosticsManager::HandleWlanRemoval(_GUID)

- ea: `0x180072364`
- end: `0x1800724ad`
- name: `?HandleWlanRemoval@DiagnosticsManager@@SAXU_GUID@@@Z`
- size: `329`
- prototype: `void __fastcall(struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180104678`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800713b8`
- `0x180072364`
- `0x1800a88a0`
- `0x18010f3dc`
- `0x18010f49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072433`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072464`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072433`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072464`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180072479`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180072479`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800723dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800723dd`

## string_xrefs

- `0x1800723a8`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::HandleWlanRemoval(struct _GUID *a1)
{
  std::_Ref_count_base *v2; // rbx
  const char *v3; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v5[2]; // [rsp+28h] [rbp-50h] BYREF
  struct _GUID v6; // [rsp+38h] [rbp-40h]
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-30h] BYREF
  std::_Ref_count_base *v8[2]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_OWORD *)v8 = 0;
  std::weak_ptr<DiagnosticsManager>::lock(a1, v8);
  v2 = v8[0];
  if ( v8[0] )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v5[0] = v2;
    v5[1] = PerformanceCount.QuadPart;
    v6 = *a1;
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, (char *)v2 + 1264);
    try
    {
      if ( *((_BYTE *)v2 + 1528) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *((_DWORD *)v2 + 314) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::HandleWlanRemoval_::_3_::_lambda_1___(
            (char *)v2 + 1408,
            v5);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::HandleWlanRemoval_::_3_::_lambda_1___(
            (char *)v2 + 1488,
            v5);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)v2 + 174);
        SubmitThreadpoolWork(*((PTP_WORK *)v2 + 173));
      }
      if ( v8[1] )
        std::_Ref_count_base::_Decref(v8[1]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x4F9,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v3);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x4E3,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
      (const char *)0x45B,
      (unsigned int)lpCriticalSection);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
  }
}

```

## disassembly

```asm
0x180072364  mov     [rsp+arg_0], rbx
0x180072369  push    rdi
0x18007236a  sub     rsp, 70h
0x18007236e  mov     rax, cs:__security_cookie
0x180072375  xor     rax, rsp
0x180072378  mov     [rsp+78h+var_18], rax
0x18007237d  mov     rdi, rcx
0x180072380  xorps   xmm0, xmm0
0x180072383  movups  xmmword ptr [rsp+78h+var_28], xmm0
0x180072388  lea     rdx, [rsp+78h+var_28]
0x18007238d  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x180072392  nop
0x180072393  mov     rbx, [rsp+78h+var_28]
0x180072398  test    rbx, rbx
0x18007239b  jnz     short loc_1800723CF
0x18007239d  mov     rcx, [rsp+78h]; this
0x1800723a2  mov     r9d, 45Bh; char *
0x1800723a8  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x1800723af  mov     edx, 4E3h; void *
0x1800723b4  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800723b9  nop
0x1800723ba  mov     rcx, [rsp+78h+var_28+8]; this
0x1800723bf  test    rcx, rcx
0x1800723c2  jz      short loc_1800723CA
0x1800723c4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800723c9  nop
0x1800723ca  jmp     loc_180072492
0x1800723cf  mov     qword ptr [rsp+78h+PerformanceCount], 0
0x1800723d8  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x1800723dd  call    cs:__imp_QueryPerformanceCounter
0x1800723e3  mov     [rsp+78h+var_50], rbx
0x1800723e8  mov     eax, dword ptr [rsp+78h+PerformanceCount]
0x1800723ec  mov     dword ptr [rsp+78h+var_48], eax
0x1800723f0  mov     eax, dword ptr [rsp+78h+PerformanceCount+4]
0x1800723f4  mov     dword ptr [rsp+78h+var_48+4], eax
0x1800723f8  movups  xmm0, xmmword ptr [rdi]
0x1800723fb  movdqu  [rsp+78h+var_40], xmm0
0x180072401  mov     [rsp+78h+lpCriticalSection], 0
0x18007240a  lea     rdx, [rbx+4F0h]
0x180072411  lea     rcx, [rsp+78h+lpCriticalSection]
0x180072416  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007241b  nop
0x18007241c  lea     rcx, [rbx+580h]
0x180072423  cmp     byte ptr [rcx+78h], 0
0x180072427  jz      short loc_18007243B
0x180072429  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18007242e  test    rcx, rcx
0x180072431  jz      short loc_180072480
0x180072433  call    cs:__imp_LeaveCriticalSection
0x180072439  jmp     short loc_180072480
0x18007243b  lea     rdx, [rsp+78h+var_50]
0x180072440  cmp     dword ptr [rbx+4E8h], 1
0x180072447  jnz     short loc_180072450
0x180072449  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__HandleWlanRemoval____3____lambda_1___
0x18007244e  jmp     short loc_18007245A
0x180072450  add     rcx, 50h ; 'P'
0x180072454  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__HandleWlanRemoval____3____lambda_1___
0x180072459  nop
0x18007245a  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18007245f  test    rcx, rcx
0x180072462  jz      short loc_18007246A
0x180072464  call    cs:__imp_LeaveCriticalSection
0x18007246a  lock inc qword ptr [rbx+570h]
0x180072472  mov     rcx, [rbx+568h]; pwk
0x180072479  call    cs:__imp_SubmitThreadpoolWork
0x18007247f  nop
0x180072480  mov     rcx, [rsp+78h+var_28+8]; this
0x180072485  test    rcx, rcx
0x180072488  jz      short loc_180072490
0x18007248a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007248f  nop
0x180072490  jmp     short $+2
0x180072492  mov     rcx, [rsp+78h+var_18]
0x180072497  xor     rcx, rsp; StackCookie
0x18007249a  call    __security_check_cookie
0x18007249f  mov     rbx, [rsp+78h+arg_0]
0x1800724a7  add     rsp, 70h
0x1800724ab  pop     rdi
0x1800724ac  retn
```
