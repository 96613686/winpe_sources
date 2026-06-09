# IsMarkedMeteredByDhcp

- ea: `0x18003d244`
- end: `0x18003d354`
- name: `IsMarkedMeteredByDhcp`
- size: `272`
- prototype: `__int64 __fastcall(IID *rclsid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003d360`

## callees

- `0x1800011bc`
- `0x180007c90`
- `0x180013444`
- `0x18003d06c`
- `0x18003d0f4`
- `0x18003d244`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003d27b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003d27b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003d2b5`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003d2b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsMarkedMeteredByDhcp(IID *rclsid)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // ebx
  _DWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebx
  int v11; // [rsp+30h] [rbp-40h] BYREF
  IID *v12; // [rsp+38h] [rbp-38h] BYREF
  void **v13; // [rsp+40h] [rbp-30h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-28h] BYREF
  char v15; // [rsp+50h] [rbp-20h]
  unsigned int v16; // [rsp+58h] [rbp-18h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h] BYREF

  InitOnceExecuteOnce(&g_initOnce, IsMarkedMeteredByDhcp_::_2_::_lambda_1_::_lambda_invoker_cdecl_, 0, 0);
  if ( !g_dhcpIsMeteredDetected )
    return 0;
  v17 = 0;
  v13 = (void **)&v17;
  lpsz = 0;
  v15 = 1;
  v3 = (unsigned int)StringFromCLSID(rclsid, &lpsz) >> 31;
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&v13);
  if ( !(_BYTE)v3 )
  {
    v16 = 0;
    v6 = ((__int64 (__fastcall *)(__int64, unsigned int *))g_dhcpIsMeteredDetected)(v17, &v16);
    if ( !v6 )
    {
      v10 = v16;
      goto LABEL_8;
    }
    v7 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v5, v4) + 8);
    if ( *v7 > 5u )
    {
      v11 = v6;
      v12 = rclsid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        (int)v7,
        (int)word_18005B8AA,
        v8,
        v9,
        (__int64 *)&v12,
        (__int64)&v11);
    }
  }
  v10 = 0;
LABEL_8:
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v17);
  return v10;
}

```

## disassembly

```asm
0x18003d244  mov     [rsp-8+arg_8], rbx
0x18003d249  mov     [rsp-8+arg_10], rdi
0x18003d24e  push    rbp
0x18003d24f  mov     rbp, rsp
0x18003d252  sub     rsp, 70h
0x18003d256  mov     rax, cs:__security_cookie
0x18003d25d  xor     rax, rsp
0x18003d260  mov     [rbp+var_8], rax
0x18003d264  mov     rdi, rcx
0x18003d267  xor     r9d, r9d; Context
0x18003d26a  xor     r8d, r8d; Parameter
0x18003d26d  lea     rdx, _IsMarkedMeteredByDhcp____2____lambda_1____lambda_invoker_cdecl_; InitFn
0x18003d274  lea     rcx, ?g_initOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18003d27b  call    cs:__imp_InitOnceExecuteOnce
0x18003d281  cmp     cs:?g_dhcpIsMeteredDetected@@3P6AKPEB_WPEAH@ZEA, 0; ulong (*g_dhcpIsMeteredDetected)(wchar_t const *,int *)
0x18003d289  jnz     short loc_18003D292
0x18003d28b  xor     eax, eax
0x18003d28d  jmp     loc_18003D330
0x18003d292  mov     [rbp+var_10], 0
0x18003d29a  lea     rax, [rbp+var_10]
0x18003d29e  mov     [rbp+var_30], rax
0x18003d2a2  mov     [rbp+lpsz], 0
0x18003d2aa  mov     [rbp+var_20], 1
0x18003d2ae  lea     rdx, [rbp+lpsz]; lplpsz
0x18003d2b2  mov     rcx, rdi; rclsid
0x18003d2b5  call    cs:__imp_StringFromCLSID
0x18003d2bb  mov     ebx, eax
0x18003d2bd  shr     ebx, 1Fh
0x18003d2c0  lea     rcx, [rbp+var_30]
0x18003d2c4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)
0x18003d2c9  test    bl, bl
0x18003d2cb  jnz     short loc_18003D323
0x18003d2cd  mov     [rbp+var_18], 0
0x18003d2d4  lea     rdx, [rbp+var_18]
0x18003d2d8  mov     rcx, [rbp+var_10]
0x18003d2dc  mov     rax, cs:?g_dhcpIsMeteredDetected@@3P6AKPEB_WPEAH@ZEA; ulong (*g_dhcpIsMeteredDetected)(wchar_t const *,int *)
0x18003d2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2e8  mov     ebx, eax
0x18003d2ea  test    eax, eax
0x18003d2ec  jz      short loc_18003D34E
0x18003d2ee  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003d2f3  mov     rcx, [rax+8]
0x18003d2f7  mov     edx, [rcx]
0x18003d2f9  cmp     edx, 5
0x18003d2fc  jbe     short loc_18003D323
0x18003d2fe  mov     [rbp+var_40], ebx
0x18003d301  mov     [rbp+var_38], rdi
0x18003d305  lea     rax, [rbp+var_40]
0x18003d309  mov     [rsp+70h+var_48], rax
0x18003d30e  lea     rax, [rbp+var_38]
0x18003d312  mov     [rsp+70h+var_50], rax
0x18003d317  lea     rdx, word_18005B8AA
0x18003d31e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18003d323  xor     ebx, ebx
0x18003d325  lea     rcx, [rbp+var_10]
0x18003d329  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18003d32e  mov     eax, ebx
0x18003d330  mov     rcx, [rbp+var_8]
0x18003d334  xor     rcx, rsp; StackCookie
0x18003d337  call    __security_check_cookie
0x18003d33c  lea     r11, [rsp+70h+var_s0]
0x18003d341  mov     rbx, [r11+18h]
0x18003d345  mov     rdi, [r11+20h]
0x18003d349  mov     rsp, r11
0x18003d34c  pop     rbp
0x18003d34d  retn
0x18003d34e  mov     ebx, [rbp+var_18]
0x18003d351  jmp     short loc_18003D325
```
