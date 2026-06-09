# Rdp::Utils::TP::details::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void_(__cdecl_)(_TP_IO__)_&Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_______::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void_(__cdecl_)(_TP_IO__)_&Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_________Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1___

- ea: `0x18001b3a0`
- end: `0x18001b464`
- name: `Rdp::Utils::TP::details::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void_(__cdecl_)(_TP_IO__)_&Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_______::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void_(__cdecl_)(_TP_IO__)_&Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_________Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1___`
- size: `196`
- prototype: `__int64 __fastcall(PVOID pv, HANDLE fl)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001b510`

## callees

- `0x180004f84`
- `0x180005290`
- `0x180018870`
- `0x180019264`
- `0x18001b3a0`
- `0x18001b46c`
- `0x18001c3e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001b3de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001b3de`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PTP_IO *Rdp::Utils::TP::details::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void____cdecl____TP_IO_____Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_______::CThreadPoolIo_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_IO___void____cdecl____TP_IO_____Rdp::Utils::TP::details::DestroyThreadpoolIo_wistd::integral_constant_unsigned___int64_0___TP_IO____TP_IO___0_std::nullptr_t_________Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1___(
        PTP_IO *pv,
        HANDLE fl,
        __int64 a3,
        ...)
{
  PTP_IO ThreadpoolIo; // rsi
  unsigned int v6; // r8d
  const char *v7; // r9
  Rdp::Utils::TP::details *v8; // rdi
  struct _TP_IO *v9; // rdx
  _QWORD v11[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v13 = va_arg(va1, _QWORD);
  *pv = 0;
  pv[8] = 0;
  ThreadpoolIo = CreateThreadpoolIo(
                   fl,
                   Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>::OnIoCallback,
                   pv,
                   0);
  v11[0] = ThreadpoolIo;
  if ( !ThreadpoolIo )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, 0, v6, v7);
  std::function_void___cdecl_void___unsigned_long_unsigned___int64__::operator___Rdp::Stack::Shim::CCtrlChannel::StartFileIo_::_2_::_lambda_1__0_(
    pv + 1,
    a3);
  if ( pv != v11 )
  {
    v8 = *pv;
    if ( *pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)va);
      Rdp::Utils::TP::details::DestroyThreadpoolIo(v8, v9);
      wil::last_error_context::~last_error_context((wil::last_error_context *)va);
    }
    *pv = ThreadpoolIo;
    v11[0] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>(v11);
  return pv;
}

```

## disassembly

```asm
0x18001b3a0  mov     [rsp+arg_8], rbx
0x18001b3a5  mov     [rsp+arg_18], r9
0x18001b3aa  mov     [rsp+arg_0], rcx
0x18001b3af  push    rbp
0x18001b3b0  push    rsi
0x18001b3b1  push    rdi
0x18001b3b2  sub     rsp, 30h
0x18001b3b6  mov     rbp, r8
0x18001b3b9  mov     rax, rdx
0x18001b3bc  mov     rbx, rcx
0x18001b3bf  mov     qword ptr [rcx], 0
0x18001b3c6  mov     qword ptr [rcx+40h], 0
0x18001b3ce  xor     r9d, r9d; pcbe
0x18001b3d1  mov     r8, rcx; pv
0x18001b3d4  lea     rdx, ?OnIoCallback@?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18001b3db  mov     rcx, rax; fl
0x18001b3de  call    cs:__imp_CreateThreadpoolIo
0x18001b3e4  mov     rsi, rax
0x18001b3e7  mov     [rsp+48h+var_28], rax
0x18001b3ec  xor     edx, edx
0x18001b3ee  test    rax, rax
0x18001b3f1  setnz   dl; void *
0x18001b3f4  mov     rcx, [rsp+48h]; this
0x18001b3f9  test    edx, edx
0x18001b3fb  jnz     short loc_18001B403
0x18001b3fd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001b403  mov     rdx, rbp
0x18001b406  lea     rcx, [rbx+8]
0x18001b40a  call    std__function_void___cdecl_void___unsigned_long_unsigned___int64____operator___Rdp__Stack__Shim__CCtrlChannel__StartFileIo____2____lambda_1__0_
0x18001b40f  lea     rax, [rsp+48h+var_28]
0x18001b414  cmp     rbx, rax
0x18001b417  jz      short loc_18001B449
0x18001b419  mov     rdi, [rbx]
0x18001b41c  test    rdi, rdi
0x18001b41f  jz      short loc_18001B43D
0x18001b421  lea     rcx, [rsp+48h+arg_18]; this
0x18001b426  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001b42b  mov     rcx, rdi; this
0x18001b42e  call    ?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAXPEAU_TP_IO@@@Z; Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *)
0x18001b433  lea     rcx, [rsp+48h+arg_18]; this
0x18001b438  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001b43d  mov     [rbx], rsi
0x18001b440  mov     [rsp+48h+var_28], 0
0x18001b449  lea     rcx, [rsp+48h+var_28]
0x18001b44e  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>(void)
0x18001b453  nop
0x18001b454  mov     rax, rbx
0x18001b457  mov     rbx, [rsp+48h+arg_8]
0x18001b45c  add     rsp, 30h
0x18001b460  pop     rdi
0x18001b461  pop     rsi
0x18001b462  pop     rbp
0x18001b463  retn
```
