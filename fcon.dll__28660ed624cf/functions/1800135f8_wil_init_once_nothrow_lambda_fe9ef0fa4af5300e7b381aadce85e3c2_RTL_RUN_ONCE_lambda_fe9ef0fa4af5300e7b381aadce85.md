# wil::init_once_nothrow<_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_>(_RTL_RUN_ONCE &,_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_,bool *)

- ea: `0x1800135f8`
- end: `0x1800136af`
- name: `??$init_once_nothrow@V_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_@@@wil@@YAJAEAT_RTL_RUN_ONCE@@V_lambda_fe9ef0fa4af5300e7b381aadce85e3c2_@@PEA_N@Z`
- size: `183`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c6e0`

## callees

- `0x180005fcc`
- `0x18000947c`
- `0x180012bd8`
- `0x1800135f8`
- `0x1800196d4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001369c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001369c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001361e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001361e`

## string_xrefs

- `0x180013663`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\fc\fc_registry_store.h`

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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
    InitOnceComplete(lpInitOnce, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800135f8  mov     rax, rsp
0x1800135fb  mov     [rax+8], rbx
0x1800135ff  mov     [rax+18h], r8
0x180013603  push    rdi; int
0x180013604  sub     rsp, 20h
0x180013608  mov     rbx, rdx
0x18001360b  mov     dword ptr [rax+18h], 0
0x180013612  xor     edx, edx; dwFlags
0x180013614  lea     r8, [rax+18h]; fPending
0x180013618  xor     r9d, r9d; lpContext
0x18001361b  mov     rdi, rcx
0x18001361e  call    cs:__imp_InitOnceBeginInitialize
0x180013624  test    eax, eax
0x180013626  jnz     short loc_180013640
0x180013628  mov     rcx, [rsp+28h]; this
0x18001362d  lea     r8, aWil; "wil"
0x180013634  mov     edx, 37Ah; void *
0x180013639  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001363e  jmp     short loc_1800136A4
0x180013640  cmp     [rsp+28h+arg_10], 0
0x180013645  jz      short loc_1800136A2
0x180013647  lea     rcx, [rsp+28h+arg_18]
0x18001364c  mov     [rsp+28h+arg_18], 0
0x180013655  call    ??$create_global_mutex@$$V@details@fc@@YAJAEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEBG@Z
0x18001365a  test    eax, eax
0x18001365c  jns     short loc_180013679
0x18001365e  mov     rcx, [rsp+28h]; this
0x180013663  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001366a  mov     r9d, eax; char *
0x18001366d  mov     edx, 2Eh ; '.'; void *
0x180013672  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013677  jmp     short loc_18001368A
0x180013679  mov     rax, [rsp+28h+arg_18]
0x18001367e  mov     [rbx], rax
0x180013681  mov     [rsp+28h+arg_18], 0
0x18001368a  lea     rcx, [rsp+28h+arg_18]
0x18001368f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013694  xor     r8d, r8d; lpContext
0x180013697  xor     edx, edx; dwFlags
0x180013699  mov     rcx, rdi; lpInitOnce
0x18001369c  call    cs:__imp_InitOnceComplete
0x1800136a2  xor     eax, eax
0x1800136a4  mov     rbx, [rsp+28h+arg_0]
0x1800136a9  add     rsp, 20h
0x1800136ad  pop     rdi
0x1800136ae  retn
```
