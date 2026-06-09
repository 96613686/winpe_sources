# wil::CoCreateInstance<IFlightClientAPI,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x180061030`
- end: `0x180061098`
- name: `??$CoCreateInstance@UIFlightClientAPI@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIFlightClientAPI@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180064098`
- `0x180068d00`

## callees

- `0x1800109ac`
- `0x180061030`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006106b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006106b`

## string_xrefs

- `0x180061086`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall wil::CoCreateInstance<IFlightClientAPI,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, a1);
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
0x180061030  mov     rax, rsp
0x180061033  mov     [rax+8], rcx
0x180061037  push    rbx
0x180061038  sub     rsp, 40h
0x18006103c  mov     rbx, rcx
0x18006103f  mov     dword ptr [rax-18h], 0
0x180061046  mov     r8d, 1; dwClsContext
0x18006104c  mov     [rax-18h], r8d
0x180061050  mov     qword ptr [rcx], 0
0x180061057  mov     [rax-28h], rcx
0x18006105b  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x180061062  xor     edx, edx; pUnkOuter
0x180061064  lea     rcx, CLSID_FlightClientAPI; rclsid
0x18006106b  call    cs:__imp_CoCreateInstance
0x180061071  test    eax, eax
0x180061073  js      short loc_18006107E
0x180061075  mov     rax, rbx
0x180061078  add     rsp, 40h
0x18006107c  pop     rbx
0x18006107d  retn
0x18006107e  mov     rcx, [rsp+48h]; this
0x180061083  mov     r9d, eax; char *
0x180061086  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006108d  mov     edx, 1CBEh; void *
0x180061092  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
