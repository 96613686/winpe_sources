# wil::details::ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___::_ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___

- ea: `0x18003ae84`
- end: `0x18003aea3`
- name: `wil::details::ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___::_ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800acb4f`
- `0x1800acbcd`

## callees

- `0x18003ae84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae98`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___::_ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    CoTaskMemFree(**(LPVOID **)a1);
  }
}

```

## disassembly

```asm
0x18003ae84  sub     rsp, 28h
0x18003ae88  cmp     byte ptr [rcx+8], 0
0x18003ae8c  jz      short loc_18003AE9E
0x18003ae8e  mov     byte ptr [rcx+8], 0
0x18003ae92  mov     rcx, [rcx]
0x18003ae95  mov     rcx, [rcx]; pv
0x18003ae98  call    cs:__imp_CoTaskMemFree
0x18003ae9e  add     rsp, 28h
0x18003aea2  retn
```
