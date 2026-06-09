# wil::CoCreateInstance<INetworkListManager,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18000d5e4`
- end: `0x18000d64d`
- name: `??$CoCreateInstance@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b1b8`

## callees

- `0x18000d5e4`
- `0x18002a928`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d61f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d61f`

## string_xrefs

- `0x18000d631`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<INetworkListManager,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(
               &GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b,
               0,
               1u,
               &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Instance,
      v4);
  return a1;
}

```

## disassembly

```asm
0x18000d5e4  mov     rax, rsp
0x18000d5e7  mov     [rax+8], rcx
0x18000d5eb  push    rbx
0x18000d5ec  sub     rsp, 40h
0x18000d5f0  mov     rbx, rcx
0x18000d5f3  mov     dword ptr [rax-18h], 0
0x18000d5fa  mov     r8d, 1; dwClsContext
0x18000d600  mov     [rax-18h], r8d
0x18000d604  mov     qword ptr [rcx], 0
0x18000d60b  mov     [rax-28h], rcx
0x18000d60f  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x18000d616  xor     edx, edx; pUnkOuter
0x18000d618  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x18000d61f  call    cs:__imp_CoCreateInstance
0x18000d625  test    eax, eax
0x18000d627  jns     short loc_18000D643
0x18000d629  mov     rcx, [rsp+48h]; this
0x18000d62e  mov     r9d, eax; char *
0x18000d631  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d638  mov     edx, 1CBEh; void *
0x18000d63d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d643  mov     rax, rbx
0x18000d646  add     rsp, 40h
0x18000d64a  pop     rbx
0x18000d64b  retn
```
