# StopFactories(void)

- ea: `0x180010af8`
- end: `0x180010b53`
- name: `?StopFactories@@YAJXZ`
- size: `91`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000492c`
- `0x18000f600`

## callees

- `0x18000fca8`
- `0x180010af8`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180010b06`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180010b06`

## string_xrefs

- `0x180010b15`: `clientcore\ds\security\gina\profile\roaming\classfactory.cpp`

## pseudocode

```c
__int64 StopFactories(void)
{
  HRESULT v0; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( dwRegister )
  {
    v0 = CoRevokeClassObject(dwRegister);
    if ( v0 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC8,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\classfactory.cpp",
        (const char *)(unsigned int)v0);
  }
  if ( qword_18002B0F8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002B0F8 + 16LL))(qword_18002B0F8);
    qword_18002B0F8 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180010af8  sub     rsp, 28h
0x180010afc  mov     ecx, cs:dwRegister; dwRegister
0x180010b02  test    ecx, ecx
0x180010b04  jz      short loc_180010B29
0x180010b06  call    cs:__imp_CoRevokeClassObject
0x180010b0c  test    eax, eax
0x180010b0e  jns     short loc_180010B29
0x180010b10  mov     rcx, [rsp+28h]; this
0x180010b15  lea     r8, aClientcoreDsSe_2; "clientcore\\ds\\security\\gina\\profile"...
0x180010b1c  mov     r9d, eax; char *
0x180010b1f  mov     edx, 0C8h; void *
0x180010b24  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010b29  mov     rcx, cs:qword_18002B0F8
0x180010b30  test    rcx, rcx
0x180010b33  jz      short loc_180010B4C
0x180010b35  mov     rax, [rcx]
0x180010b38  mov     rax, [rax+10h]
0x180010b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b41  mov     cs:qword_18002B0F8, 0
0x180010b4c  xor     eax, eax
0x180010b4e  add     rsp, 28h
0x180010b52  retn
```
