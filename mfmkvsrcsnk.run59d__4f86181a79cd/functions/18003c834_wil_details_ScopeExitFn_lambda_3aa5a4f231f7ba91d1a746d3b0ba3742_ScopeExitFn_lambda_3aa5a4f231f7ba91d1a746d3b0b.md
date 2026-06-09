# wil::details::ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___::_ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___

- ea: `0x18003c834`
- end: `0x18003c85a`
- name: `wil::details::ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___::_ScopeExitFn__lambda_3aa5a4f231f7ba91d1a746d3b0ba3742___`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b18c7`
- `0x1800b1945`

## callees

- `0x18003c834`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c848`

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
0x18003c834  sub     rsp, 28h
0x18003c838  cmp     byte ptr [rcx+8], 0
0x18003c83c  jz      short loc_18003C854
0x18003c83e  mov     byte ptr [rcx+8], 0
0x18003c842  mov     rcx, [rcx]
0x18003c845  mov     rcx, [rcx]; pv
0x18003c848  call    cs:__imp_CoTaskMemFree
0x18003c84f  nop     dword ptr [rax+rax+00h]
0x18003c854  add     rsp, 28h
0x18003c858  retn
```
