# wil::CoCreateInstance<IFlagConfigurationBroker,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x180096ac4`
- end: `0x180096b2d`
- name: `??$CoCreateInstance@UIFlagConfigurationBroker@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIFlagConfigurationBroker@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180097bf0`
- `0x180097f50`
- `0x1800985c0`
- `0x18009a260`
- `0x18009a8f0`

## callees

- `0x1800109ac`
- `0x180096ac4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180096b00`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180096b00`

## string_xrefs

- `0x180096b1b`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
LPVOID *__fastcall wil::CoCreateInstance<IFlagConfigurationBroker,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_FlagConfigurationBroker, 0, 4u, &GUID_6c8111ba_cf2b_4511_b325_6e85a4827cd9, a1);
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
0x180096ac4  mov     rax, rsp
0x180096ac7  mov     [rax+8], rcx
0x180096acb  push    rbx
0x180096acc  sub     rsp, 40h
0x180096ad0  mov     rbx, rcx
0x180096ad3  mov     dword ptr [rax-18h], 0
0x180096ada  mov     dword ptr [rax-18h], 1
0x180096ae1  mov     qword ptr [rcx], 0
0x180096ae8  mov     [rax-28h], rcx
0x180096aec  lea     r9, _GUID_6c8111ba_cf2b_4511_b325_6e85a4827cd9; riid
0x180096af3  xor     edx, edx; pUnkOuter
0x180096af5  lea     r8d, [rdx+4]; dwClsContext
0x180096af9  lea     rcx, CLSID_FlagConfigurationBroker; rclsid
0x180096b00  call    cs:__imp_CoCreateInstance
0x180096b06  test    eax, eax
0x180096b08  js      short loc_180096B13
0x180096b0a  mov     rax, rbx
0x180096b0d  add     rsp, 40h
0x180096b11  pop     rbx
0x180096b12  retn
0x180096b13  mov     rcx, [rsp+48h]; this
0x180096b18  mov     r9d, eax; char *
0x180096b1b  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180096b22  mov     edx, 1CBEh; void *
0x180096b27  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
