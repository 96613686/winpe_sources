# wil::CoCreateInstance<ISmartFeatureRolloutBroker,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18002cbf4`
- end: `0x18002cc5e`
- name: `??$CoCreateInstance@UISmartFeatureRolloutBroker@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UISmartFeatureRolloutBroker@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800384d0`
- `0x180049700`

## callees

- `0x1800109ac`
- `0x18002cbf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cc30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002cc30`

## string_xrefs

- `0x18002cc42`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<ISmartFeatureRolloutBroker,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_SmartFeatureRolloutBroker, 0, 4u, &GUID_0e9e3f02_a93d_4a67_ac89_a2107d681c19, a1);
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
0x18002cbf4  mov     rax, rsp
0x18002cbf7  mov     [rax+8], rcx
0x18002cbfb  push    rbx
0x18002cbfc  sub     rsp, 40h
0x18002cc00  mov     rbx, rcx
0x18002cc03  mov     dword ptr [rax-18h], 0
0x18002cc0a  mov     dword ptr [rax-18h], 1
0x18002cc11  mov     qword ptr [rcx], 0
0x18002cc18  mov     [rax-28h], rcx
0x18002cc1c  lea     r9, _GUID_0e9e3f02_a93d_4a67_ac89_a2107d681c19; riid
0x18002cc23  xor     edx, edx; pUnkOuter
0x18002cc25  lea     r8d, [rdx+4]; dwClsContext
0x18002cc29  lea     rcx, CLSID_SmartFeatureRolloutBroker; rclsid
0x18002cc30  call    cs:__imp_CoCreateInstance
0x18002cc36  test    eax, eax
0x18002cc38  jns     short loc_18002CC54
0x18002cc3a  mov     rcx, [rsp+48h]; this
0x18002cc3f  mov     r9d, eax; char *
0x18002cc42  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cc49  mov     edx, 1CBEh; void *
0x18002cc4e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cc54  mov     rax, rbx
0x18002cc57  add     rsp, 40h
0x18002cc5b  pop     rbx
0x18002cc5c  retn
```
