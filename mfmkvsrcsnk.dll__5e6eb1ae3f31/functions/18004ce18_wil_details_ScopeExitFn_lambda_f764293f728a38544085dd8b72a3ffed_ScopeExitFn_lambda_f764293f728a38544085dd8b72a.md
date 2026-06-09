# wil::details::ScopeExitFn__lambda_f764293f728a38544085dd8b72a3ffed___::_ScopeExitFn__lambda_f764293f728a38544085dd8b72a3ffed___

- ea: `0x18004ce18`
- end: `0x18004ce4e`
- name: `wil::details::ScopeExitFn__lambda_f764293f728a38544085dd8b72a3ffed___::_ScopeExitFn__lambda_f764293f728a38544085dd8b72a3ffed___`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ae264`

## callees

- `0x18004ce18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ce37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ce37`

## pseudocode

```c
__int64 __fastcall wil::details::ScopeExitFn__lambda_f764293f728a38544085dd8b72a3ffed___::_ScopeExitFn__lambda_f764293f728a38544085dd8b72a3ffed___(
        _BYTE *a1)
{
  __int64 result; // rax
  void *v3; // rcx

  if ( a1[8] )
  {
    a1[8] = 0;
    result = *(_QWORD *)a1;
    v3 = *(void **)(*(_QWORD *)a1 + 8LL);
    if ( v3 )
    {
      CoTaskMemFree(v3);
      result = *(_QWORD *)a1;
      *(_QWORD *)(*(_QWORD *)a1 + 8LL) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004ce18  push    rbx
0x18004ce1a  sub     rsp, 20h
0x18004ce1e  cmp     byte ptr [rcx+8], 0
0x18004ce22  mov     rbx, rcx
0x18004ce25  jz      short loc_18004CE48
0x18004ce27  mov     byte ptr [rcx+8], 0
0x18004ce2b  mov     rax, [rcx]
0x18004ce2e  mov     rcx, [rax+8]; pv
0x18004ce32  test    rcx, rcx
0x18004ce35  jz      short loc_18004CE48
0x18004ce37  call    cs:__imp_CoTaskMemFree
0x18004ce3d  mov     rax, [rbx]
0x18004ce40  mov     qword ptr [rax+8], 0
0x18004ce48  add     rsp, 20h
0x18004ce4c  pop     rbx
0x18004ce4d  retn
```
