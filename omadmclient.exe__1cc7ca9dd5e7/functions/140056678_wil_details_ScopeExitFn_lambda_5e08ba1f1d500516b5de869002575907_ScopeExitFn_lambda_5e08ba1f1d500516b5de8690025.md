# wil::details::ScopeExitFn__lambda_5e08ba1f1d500516b5de869002575907___::_ScopeExitFn__lambda_5e08ba1f1d500516b5de869002575907___

- ea: `0x140056678`
- end: `0x14005670c`
- name: `wil::details::ScopeExitFn__lambda_5e08ba1f1d500516b5de869002575907___::_ScopeExitFn__lambda_5e08ba1f1d500516b5de869002575907___`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140058a5c`
- `0x140067db5`

## callees

- `0x140056678`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400566db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400566db`
- `OLEAUT32!__imp_SysFreeString` at `0x1400566b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400566b1`

## pseudocode

```c
LPVOID *__fastcall wil::details::ScopeExitFn__lambda_5e08ba1f1d500516b5de869002575907___::_ScopeExitFn__lambda_5e08ba1f1d500516b5de869002575907___(
        __int64 a1)
{
  LPVOID *result; // rax
  __int64 i; // rsi

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    result = *(LPVOID **)a1;
    if ( **(_QWORD **)a1 )
    {
      for ( i = 0; (unsigned int)i < **(_DWORD **)(a1 + 8); i = (unsigned int)(i + 1) )
      {
        SysFreeString(*(BSTR *)(**(_QWORD **)a1 + 8 * i));
        *(_QWORD *)(**(_QWORD **)a1 + 8 * i) = 0;
      }
      CoTaskMemFree(**(LPVOID **)a1);
      **(_QWORD **)a1 = 0;
      result = *(LPVOID **)(a1 + 8);
      *(_DWORD *)result = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140056678  mov     [rsp+arg_0], rbx
0x14005667d  mov     [rsp+arg_8], rsi
0x140056682  push    rdi
0x140056683  sub     rsp, 20h
0x140056687  cmp     byte ptr [rcx+10h], 0
0x14005668b  mov     rdi, rcx
0x14005668e  jz      short loc_1400566FB
0x140056690  mov     byte ptr [rcx+10h], 0
0x140056694  mov     rax, [rcx]
0x140056697  cmp     qword ptr [rax], 0
0x14005669b  jz      short loc_1400566FB
0x14005669d  mov     rax, [rcx+8]
0x1400566a1  xor     esi, esi
0x1400566a3  cmp     [rax], esi
0x1400566a5  jbe     short loc_1400566D5
0x1400566a7  mov     rax, [rdi]
0x1400566aa  mov     rcx, [rax]
0x1400566ad  mov     rcx, [rcx+rsi*8]; bstrString
0x1400566b1  call    cs:__imp_SysFreeString
0x1400566b8  nop     dword ptr [rax+rax+00h]
0x1400566bd  mov     rax, [rdi]
0x1400566c0  mov     rcx, [rax]
0x1400566c3  mov     qword ptr [rcx+rsi*8], 0
0x1400566cb  inc     esi
0x1400566cd  mov     rax, [rdi+8]
0x1400566d1  cmp     esi, [rax]
0x1400566d3  jb      short loc_1400566A7
0x1400566d5  mov     rcx, [rdi]
0x1400566d8  mov     rcx, [rcx]; pv
0x1400566db  call    cs:__imp_CoTaskMemFree
0x1400566e2  nop     dword ptr [rax+rax+00h]
0x1400566e7  mov     rax, [rdi]
0x1400566ea  mov     qword ptr [rax], 0
0x1400566f1  mov     rax, [rdi+8]
0x1400566f5  mov     dword ptr [rax], 0
0x1400566fb  mov     rbx, [rsp+28h+arg_0]
0x140056700  mov     rsi, [rsp+28h+arg_8]
0x140056705  add     rsp, 20h
0x140056709  pop     rdi
0x14005670a  retn
```
