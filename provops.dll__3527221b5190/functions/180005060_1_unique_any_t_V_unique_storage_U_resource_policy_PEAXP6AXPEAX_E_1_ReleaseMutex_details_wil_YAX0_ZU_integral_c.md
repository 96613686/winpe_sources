# ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ

- ea: `0x180005060`
- end: `0x180005092`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180036269`
- `0x1800362bd`
- `0x180036331`

## callees

- `0x180005060`
- `0x18000864c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000506c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000506c`

## string_xrefs

- `0x180005080`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *a1;
  if ( v1 )
  {
    if ( !ReleaseMutex(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v2);
  }
}

```

## disassembly

```asm
0x180005060  sub     rsp, 28h
0x180005064  mov     rcx, [rcx]; hMutex
0x180005067  test    rcx, rcx
0x18000506a  jz      short loc_180005076
0x18000506c  call    cs:__imp_ReleaseMutex
0x180005072  test    eax, eax
0x180005074  jz      short loc_18000507B
0x180005076  add     rsp, 28h
0x18000507a  retn
0x18000507b  mov     rcx, [rsp+28h]; this
0x180005080  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005087  mov     edx, 0A15h; void *
0x18000508c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
