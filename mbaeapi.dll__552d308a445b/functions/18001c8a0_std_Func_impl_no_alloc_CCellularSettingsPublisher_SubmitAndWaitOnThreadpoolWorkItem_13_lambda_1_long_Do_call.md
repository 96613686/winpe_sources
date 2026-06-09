# std::_Func_impl_no_alloc__CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1__long_::_Do_call

- ea: `0x18001c8a0`
- end: `0x18001c947`
- name: `std::_Func_impl_no_alloc__CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1__long_::_Do_call`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009474`
- `0x18001adf8`
- `0x18001c8a0`
- `0x18005c010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c8f7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001c8f7`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001c8b2`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001c8b2`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001c92a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001c932`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001c92a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001c932`

## string_xrefs

- `0x18001c8c3`: `[Publisher]COM initialization failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Func_impl_no_alloc__CCellularSettingsPublisher::_SubmitAndWaitOnThreadpoolWorkItem_::_13_::_lambda_1__long_::_Do_call(
        __int64 a1)
{
  int v2; // ebx
  __int64 v3; // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  const char *v7; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = RoInitialize(1);
  if ( v2 >= 0 )
  {
    v3 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL);
    if ( !v3 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    v2 = v4;
    if ( v4 >= 0 )
    {
      RoUninitialize();
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccspublisher.cpp",
        (const char *)(unsigned int)v4,
        v6);
      RoUninitialize();
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccspublisher.cpp",
      (const char *)(unsigned int)v2,
      (int)"[Publisher]COM initialization failed",
      v7);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001c8a0  mov     [rsp+arg_0], rbx
0x18001c8a5  push    rdi
0x18001c8a6  sub     rsp, 30h
0x18001c8aa  mov     rdi, rcx
0x18001c8ad  mov     ecx, 1
0x18001c8b2  call    cs:__imp_RoInitialize
0x18001c8b8  mov     ebx, eax
0x18001c8ba  test    eax, eax
0x18001c8bc  jns     short loc_18001C8E5
0x18001c8be  mov     rcx, [rsp+38h]; this
0x18001c8c3  lea     rax, aPublisherComIn; "[Publisher]COM initialization failed"
0x18001c8ca  mov     qword ptr [rsp+38h+var_18], rax; int
0x18001c8cf  mov     r9d, ebx; char *
0x18001c8d2  lea     r8, aOnecoreuapNetM_0; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18001c8d9  mov     edx, 0B1h; void *
0x18001c8de  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001c8e3  jmp     short loc_18001C93A
0x18001c8e5  mov     [rsp+38h+arg_9], 1
0x18001c8ea  mov     rax, [rdi+8]
0x18001c8ee  mov     rcx, [rax+38h]
0x18001c8f2  test    rcx, rcx
0x18001c8f5  jnz     short loc_18001C8FE
0x18001c8f7  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001c8fd  int     3; Trap to Debugger
0x18001c8fe  mov     rax, [rcx]
0x18001c901  mov     rax, [rax+10h]
0x18001c905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c90a  mov     ebx, eax
0x18001c90c  test    eax, eax
0x18001c90e  jns     short loc_18001C932
0x18001c910  mov     rcx, [rsp+38h]; this
0x18001c915  mov     r9d, eax; char *
0x18001c918  lea     r8, aOnecoreuapNetM_0; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18001c91f  mov     edx, 0B5h; void *
0x18001c924  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c929  nop
0x18001c92a  call    cs:__imp_RoUninitialize
0x18001c930  jmp     short loc_18001C93A
0x18001c932  call    cs:__imp_RoUninitialize
0x18001c938  xor     ebx, ebx
0x18001c93a  mov     eax, ebx
0x18001c93c  mov     rbx, [rsp+38h+arg_0]
0x18001c941  add     rsp, 30h
0x18001c945  pop     rdi
0x18001c946  retn
```
