# wil::init_once_nothrow<_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_>(_RTL_RUN_ONCE &,_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_,bool *)

- ea: `0x18005cfb8`
- end: `0x18005d06f`
- name: `??$init_once_nothrow@V_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_@@@wil@@YAJAEAT_RTL_RUN_ONCE@@V_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_@@PEA_N@Z`
- size: `183`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800168e4`

## callees

- `0x18000b4f0`
- `0x1800179ac`
- `0x180039bf0`
- `0x18005c0ec`
- `0x18005cfb8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005d05c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18005d05c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18005cfde`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18005cfde`

## string_xrefs

- `0x18005d023`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow<_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_>(
        LPINIT_ONCE lpInitOnce,
        _QWORD *a2,
        __int64 a3)
{
  const char *v5; // r9
  int global; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL v10; // [rsp+40h] [rbp+18h] BYREF
  int v11; // [rsp+44h] [rbp+1Ch]
  __int64 v12; // [rsp+48h] [rbp+20h] BYREF

  v11 = HIDWORD(a3);
  v10 = 0;
  if ( !InitOnceBeginInitialize(lpInitOnce, 0, &v10, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v5);
  if ( v10 )
  {
    v12 = 0;
    global = fc::details::create_global_mutex<>((__int64)&v12);
    if ( global >= 0 )
    {
      *a2 = v12;
      v12 = 0;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_registry_store.h",
        (const char *)(unsigned int)global,
        v8);
    }
    __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v12);
    InitOnceComplete(lpInitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18005cfb8  mov     rax, rsp
0x18005cfbb  mov     [rax+8], rbx
0x18005cfbf  mov     [rax+18h], r8
0x18005cfc3  push    rdi; int
0x18005cfc4  sub     rsp, 20h
0x18005cfc8  mov     rbx, rdx
0x18005cfcb  mov     dword ptr [rax+18h], 0
0x18005cfd2  xor     edx, edx; dwFlags
0x18005cfd4  lea     r8, [rax+18h]; fPending
0x18005cfd8  xor     r9d, r9d; lpContext
0x18005cfdb  mov     rdi, rcx
0x18005cfde  call    cs:__imp_InitOnceBeginInitialize
0x18005cfe4  test    eax, eax
0x18005cfe6  jnz     short loc_18005D000
0x18005cfe8  mov     rcx, [rsp+28h]; this
0x18005cfed  lea     r8, aWil; "wil"
0x18005cff4  mov     edx, 37Ah; void *
0x18005cff9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005cffe  jmp     short loc_18005D064
0x18005d000  cmp     [rsp+28h+arg_10], 0
0x18005d005  jz      short loc_18005D062
0x18005d007  lea     rcx, [rsp+28h+arg_18]
0x18005d00c  mov     [rsp+28h+arg_18], 0
0x18005d015  call    ??$create_global_mutex@$$V@details@fc@@YAJAEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEBG@Z
0x18005d01a  test    eax, eax
0x18005d01c  jns     short loc_18005D039
0x18005d01e  mov     rcx, [rsp+28h]; this
0x18005d023  lea     r8, aOnecoreInterna_11; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18005d02a  mov     r9d, eax; char *
0x18005d02d  mov     edx, 2Eh ; '.'; void *
0x18005d032  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005d037  jmp     short loc_18005D04A
0x18005d039  mov     rax, [rsp+28h+arg_18]
0x18005d03e  mov     [rbx], rax
0x18005d041  mov     [rsp+28h+arg_18], 0
0x18005d04a  lea     rcx, [rsp+28h+arg_18]
0x18005d04f  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x18005d054  xor     r8d, r8d; lpContext
0x18005d057  xor     edx, edx; dwFlags
0x18005d059  mov     rcx, rdi; lpInitOnce
0x18005d05c  call    cs:__imp_InitOnceComplete
0x18005d062  xor     eax, eax
0x18005d064  mov     rbx, [rsp+28h+arg_0]
0x18005d069  add     rsp, 20h
0x18005d06d  pop     rdi
0x18005d06e  retn
```
