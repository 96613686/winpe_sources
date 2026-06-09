# wil::CoCreateInstance<ISmartFeatureTuningBroker,wil::err_exception_policy>(_GUID const &,ulong)

- ea: `0x18007f570`
- end: `0x18007f5d9`
- name: `??$CoCreateInstance@UISmartFeatureTuningBroker@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UISmartFeatureTuningBroker@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007faf0`

## callees

- `0x1800109ac`
- `0x18007f570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007f5ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007f5ac`

## string_xrefs

- `0x18007f5c7`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall wil::CoCreateInstance<ISmartFeatureTuningBroker,wil::err_exception_policy>(LPVOID *a1)
{
  HRESULT Instance; // eax
  int v4; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_SmartFeatureTuningBroker, 0, 4u, &GUID_dbdef05f_183b_423c_a326_e79308a68a4e, a1);
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
0x18007f570  mov     rax, rsp
0x18007f573  mov     [rax+8], rcx
0x18007f577  push    rbx
0x18007f578  sub     rsp, 40h
0x18007f57c  mov     rbx, rcx
0x18007f57f  mov     dword ptr [rax-18h], 0
0x18007f586  mov     dword ptr [rax-18h], 1
0x18007f58d  mov     qword ptr [rcx], 0
0x18007f594  mov     [rax-28h], rcx
0x18007f598  lea     r9, _GUID_dbdef05f_183b_423c_a326_e79308a68a4e; riid
0x18007f59f  xor     edx, edx; pUnkOuter
0x18007f5a1  lea     r8d, [rdx+4]; dwClsContext
0x18007f5a5  lea     rcx, CLSID_SmartFeatureTuningBroker; rclsid
0x18007f5ac  call    cs:__imp_CoCreateInstance
0x18007f5b2  test    eax, eax
0x18007f5b4  js      short loc_18007F5BF
0x18007f5b6  mov     rax, rbx
0x18007f5b9  add     rsp, 40h
0x18007f5bd  pop     rbx
0x18007f5be  retn
0x18007f5bf  mov     rcx, [rsp+48h]; this
0x18007f5c4  mov     r9d, eax; char *
0x18007f5c7  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007f5ce  mov     edx, 1CBEh; void *
0x18007f5d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
