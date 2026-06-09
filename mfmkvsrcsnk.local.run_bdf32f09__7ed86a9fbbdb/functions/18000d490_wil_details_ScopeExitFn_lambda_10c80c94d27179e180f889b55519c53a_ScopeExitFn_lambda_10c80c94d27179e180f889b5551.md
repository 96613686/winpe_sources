# wil::details::ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___::_ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___

- ea: `0x18000d490`
- end: `0x18000d4bf`
- name: `wil::details::ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___::_ScopeExitFn__lambda_10c80c94d27179e180f889b55519c53a___`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800abc67`

## callees

- `0x18000d490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4a9`

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
0x18000d490  push    rbx
0x18000d492  sub     rsp, 20h
0x18000d496  cmp     byte ptr [rcx+8], 0
0x18000d49a  mov     rbx, rcx
0x18000d49d  jz      short loc_18000D4B9
0x18000d49f  mov     byte ptr [rcx+8], 0
0x18000d4a3  mov     rcx, [rcx]
0x18000d4a6  mov     rcx, [rcx]; pv
0x18000d4a9  call    cs:__imp_CoTaskMemFree
0x18000d4af  mov     rax, [rbx]
0x18000d4b2  mov     qword ptr [rax], 0
0x18000d4b9  add     rsp, 20h
0x18000d4bd  pop     rbx
0x18000d4be  retn
```
