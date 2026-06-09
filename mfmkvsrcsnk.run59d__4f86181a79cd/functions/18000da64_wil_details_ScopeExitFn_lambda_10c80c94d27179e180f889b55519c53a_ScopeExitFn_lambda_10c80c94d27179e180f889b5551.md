# wil::details::ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___::_ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___

- ea: `0x18000da64`
- end: `0x18000da9a`
- name: `wil::details::ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___::_ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b09d5`

## callees

- `0x18000da64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da7d`

## pseudocode

```c
LPVOID *__fastcall wil::details::ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___::_ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___(
        __int64 a1)
{
  LPVOID *result; // rax

  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    CoTaskMemFree(**(LPVOID **)a1);
    result = *(LPVOID **)a1;
    **(_QWORD **)a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000da64  push    rbx
0x18000da66  sub     rsp, 20h
0x18000da6a  cmp     byte ptr [rcx+8], 0
0x18000da6e  mov     rbx, rcx
0x18000da71  jz      short loc_18000DA93
0x18000da73  mov     byte ptr [rcx+8], 0
0x18000da77  mov     rcx, [rcx]
0x18000da7a  mov     rcx, [rcx]; pv
0x18000da7d  call    cs:__imp_CoTaskMemFree
0x18000da84  nop     dword ptr [rax+rax+00h]
0x18000da89  mov     rax, [rbx]
0x18000da8c  mov     qword ptr [rax], 0
0x18000da93  add     rsp, 20h
0x18000da97  pop     rbx
0x18000da98  retn
```
