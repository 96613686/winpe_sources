# wil::CoCreateInstance<IExperimentationBroker,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18002cb84`
- end: `0x18002cbee`
- name: `??$CoCreateInstance@UIExperimentationBroker@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIExperimentationBroker@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180037d20`

## callees

- `0x1800109ac`
- `0x18002cb84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cbc0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cbc0`

## string_xrefs

- `0x18002cbd2`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall wil::CoCreateInstance<IExperimentationBroker,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_ExperimentationBroker, 0, 4u, &GUID_abf8427d_0bdf_4e3b_8a0d_323391e76bfe, a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x18002cb84  mov     rax, rsp
0x18002cb87  mov     [rax+8], rcx
0x18002cb8b  push    rbx
0x18002cb8c  sub     rsp, 40h
0x18002cb90  mov     rbx, rcx
0x18002cb93  mov     dword ptr [rax-18h], 0
0x18002cb9a  mov     dword ptr [rax-18h], 1
0x18002cba1  mov     qword ptr [rcx], 0
0x18002cba8  mov     [rax-28h], rcx
0x18002cbac  lea     r9, _GUID_abf8427d_0bdf_4e3b_8a0d_323391e76bfe; riid
0x18002cbb3  xor     edx, edx; pUnkOuter
0x18002cbb5  lea     r8d, [rdx+4]; dwClsContext
0x18002cbb9  lea     rcx, CLSID_ExperimentationBroker; rclsid
0x18002cbc0  call    cs:__imp_CoCreateInstance
0x18002cbc6  test    eax, eax
0x18002cbc8  jns     short loc_18002CBE4
0x18002cbca  mov     rcx, [rsp+48h]; this
0x18002cbcf  mov     r9d, eax; char *
0x18002cbd2  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cbd9  mov     edx, 1CBEh; void *
0x18002cbde  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cbe4  mov     rax, rbx
0x18002cbe7  add     rsp, 40h
0x18002cbeb  pop     rbx
0x18002cbec  retn
```
