# Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__Rdp::Avenc::Ic3::CVirtualFrame::CVirtualFrame_::_2_::_lambda_1__&_

- ea: `0x180057f44`
- end: `0x180058114`
- name: `Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__Rdp::Avenc::Ic3::CVirtualFrame::CVirtualFrame_::_2_::_lambda_1__&_`
- size: `464`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057e0c`

## callees

- `0x180006580`
- `0x18000b07c`
- `0x18000e82c`
- `0x180057cc0`
- `0x180057f44`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058038`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058081`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058038`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180058081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058060`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005806c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005806c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180058030`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800580c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180058030`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800580c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180058019`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005809e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800580b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180058019`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005809e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800580b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180058027`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800580c0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180058027`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800580c0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180057f80`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180057f80`

## string_xrefs

- `0x180058102`: `onecoreuap\termsrv\rdp_bin\win\common\inc\ThreadPoolWait.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__Rdp::Avenc::Ic3::CVirtualFrame::CVirtualFrame_::_2_::_lambda_1____(
        PFILETIME *pv,
        void **a2,
        _QWORD *a3,
        struct _TP_CALLBACK_ENVIRON_V3 *a4)
{
  struct _TP_WAIT *ThreadpoolWait; // rdi
  const char *v8; // r9
  _QWORD *v9; // rdx
  PTP_WAIT *v10; // rsi
  struct _TP_WAIT *v11; // rbp
  DWORD LastError; // ebx
  HANDLE *v13; // rbx
  void *v14; // r12
  HANDLE v15; // rbp
  DWORD v16; // r13d
  unsigned int v17; // r8d
  const char *v18; // r9
  struct _TP_WAIT *v19; // [rsp+20h] [rbp-98h] BYREF
  _QWORD v20[7]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD *v21; // [rsp+68h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  ThreadpoolWait = CreateThreadpoolWait(
                     Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::OnWaitCallback,
                     pv,
                     a4);
  v19 = ThreadpoolWait;
  if ( !ThreadpoolWait )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common\\inc\\ThreadPoolWait.h",
      v8);
  v20[0] = off_18008C220;
  v20[1] = *a3;
  v21 = v20;
  std::function<bool (long)>::swap(v20, pv + 2);
  if ( v21 )
  {
    v9 = v20;
    LOBYTE(v9) = v21 != v20;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v21 + 32LL))(v21, v9);
  }
  v10 = (PTP_WAIT *)(pv + 1);
  if ( pv + 1 != (PFILETIME *)&v19 )
  {
    v11 = *v10;
    if ( *v10 )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v11, 0, 0);
      WaitForThreadpoolWaitCallbacks(v11, 1);
      CloseThreadpoolWait(v11);
      SetLastError(LastError);
    }
    *v10 = ThreadpoolWait;
    v19 = 0;
    ThreadpoolWait = 0;
  }
  v13 = (HANDLE *)(pv + 10);
  if ( pv + 10 != (PFILETIME *)a2 )
  {
    v14 = *a2;
    v15 = *v13;
    if ( *v13 )
    {
      v16 = GetLastError();
      if ( !CloseHandle(v15) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
      SetLastError(v16);
    }
    *v13 = v14;
    *a2 = 0;
  }
  SetThreadpoolWait(*v10, *v13, pv[24]);
  if ( ThreadpoolWait )
  {
    SetThreadpoolWait(ThreadpoolWait, 0, 0);
    WaitForThreadpoolWaitCallbacks(ThreadpoolWait, 1);
    CloseThreadpoolWait(ThreadpoolWait);
  }
}

```

## disassembly

```asm
0x180057f44  mov     [rsp+arg_10], rbx
0x180057f49  push    rbp
0x180057f4a  push    rsi
0x180057f4b  push    rdi
0x180057f4c  push    r12
0x180057f4e  push    r13
0x180057f50  push    r14
0x180057f52  push    r15
0x180057f54  sub     rsp, 80h
0x180057f5b  mov     rax, cs:__security_cookie
0x180057f62  xor     rax, rsp
0x180057f65  mov     [rsp+0B8h+var_48], rax
0x180057f6a  mov     rbx, r8
0x180057f6d  mov     r15, rdx
0x180057f70  mov     r14, rcx
0x180057f73  mov     r8, r9; pcbe
0x180057f76  mov     rdx, rcx; pv
0x180057f79  lea     rcx, ?OnWaitCallback@?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180057f80  call    cs:__imp_CreateThreadpoolWait
0x180057f86  mov     rdi, rax
0x180057f89  mov     [rsp+0B8h+var_98], rax
0x180057f8e  xor     eax, eax
0x180057f90  test    rdi, rdi
0x180057f93  setnz   al
0x180057f96  mov     rcx, [rsp+0B8h]; this
0x180057f9e  test    eax, eax
0x180057fa0  jz      loc_180058102
0x180057fa6  lea     rax, off_18008C220
0x180057fad  mov     [rsp+0B8h+var_88], rax
0x180057fb2  mov     rax, [rbx]
0x180057fb5  mov     [rsp+0B8h+var_80], rax
0x180057fba  lea     rax, [rsp+0B8h+var_88]
0x180057fbf  mov     [rsp+0B8h+var_50], rax
0x180057fc4  lea     rdx, [r14+10h]
0x180057fc8  lea     rcx, [rsp+0B8h+var_88]
0x180057fcd  call    ?swap@?$function@$$A6A_NJ@Z@std@@QEAAXAEAV12@@Z; std::function<bool (long)>::swap(std::function<bool (long)> &)
0x180057fd2  mov     rcx, [rsp+0B8h+var_50]
0x180057fd7  test    rcx, rcx
0x180057fda  jz      short loc_180057FF3
0x180057fdc  mov     rax, [rcx]
0x180057fdf  lea     rdx, [rsp+0B8h+var_88]
0x180057fe4  cmp     rcx, rdx
0x180057fe7  setnz   dl
0x180057fea  mov     rax, [rax+20h]
0x180057fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ff3  lea     rsi, [r14+8]
0x180057ff7  lea     rax, [rsp+0B8h+var_98]
0x180057ffc  cmp     rsi, rax
0x180057fff  jz      short loc_18005804C
0x180058001  mov     rbp, [rsi]
0x180058004  test    rbp, rbp
0x180058007  jz      short loc_18005803E
0x180058009  call    cs:__imp_GetLastError
0x18005800f  mov     ebx, eax
0x180058011  xor     r8d, r8d; pftTimeout
0x180058014  xor     edx, edx; h
0x180058016  mov     rcx, rbp; pwa
0x180058019  call    cs:__imp_SetThreadpoolWait
0x18005801f  mov     edx, 1; fCancelPendingCallbacks
0x180058024  mov     rcx, rbp; pwa
0x180058027  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005802d  mov     rcx, rbp; pwa
0x180058030  call    cs:__imp_CloseThreadpoolWait
0x180058036  mov     ecx, ebx; dwErrCode
0x180058038  call    cs:__imp_SetLastError
0x18005803e  mov     [rsi], rdi
0x180058041  mov     [rsp+0B8h+var_98], 0
0x18005804a  xor     edi, edi
0x18005804c  lea     rbx, [r14+50h]
0x180058050  cmp     rbx, r15
0x180058053  jz      short loc_180058091
0x180058055  mov     r12, [r15]
0x180058058  mov     rbp, [rbx]
0x18005805b  test    rbp, rbp
0x18005805e  jz      short loc_180058087
0x180058060  call    cs:__imp_GetLastError
0x180058066  mov     r13d, eax
0x180058069  mov     rcx, rbp; hObject
0x18005806c  call    cs:__imp_CloseHandle
0x180058072  mov     rcx, [rsp+0B8h]; this
0x18005807a  test    eax, eax
0x18005807c  jz      short loc_1800580F7
0x18005807e  mov     ecx, r13d; dwErrCode
0x180058081  call    cs:__imp_SetLastError
0x180058087  mov     [rbx], r12
0x18005808a  mov     qword ptr [r15], 0
0x180058091  mov     r8, [r14+0C0h]; pftTimeout
0x180058098  mov     rdx, [rbx]; h
0x18005809b  mov     rcx, [rsi]; pwa
0x18005809e  call    cs:__imp_SetThreadpoolWait
0x1800580a4  nop
0x1800580a5  test    rdi, rdi
0x1800580a8  jz      short loc_1800580CF
0x1800580aa  xor     r8d, r8d; pftTimeout
0x1800580ad  xor     edx, edx; h
0x1800580af  mov     rcx, rdi; pwa
0x1800580b2  call    cs:__imp_SetThreadpoolWait
0x1800580b8  mov     edx, 1; fCancelPendingCallbacks
0x1800580bd  mov     rcx, rdi; pwa
0x1800580c0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800580c6  mov     rcx, rdi; pwa
0x1800580c9  call    cs:__imp_CloseThreadpoolWait
0x1800580cf  mov     rcx, [rsp+0B8h+var_48]
0x1800580d4  xor     rcx, rsp; StackCookie
0x1800580d7  call    __security_check_cookie
0x1800580dc  mov     rbx, [rsp+0B8h+arg_10]
0x1800580e4  add     rsp, 80h
0x1800580eb  pop     r15
0x1800580ed  pop     r14
0x1800580ef  pop     r13
0x1800580f1  pop     r12
0x1800580f3  pop     rdi
0x1800580f4  pop     rsi
0x1800580f5  pop     rbp
0x1800580f6  retn
0x1800580f7  mov     edx, 0A0Bh; void *
0x1800580fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180058102  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180058109  mov     edx, 14Ah; void *
0x18005810e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
