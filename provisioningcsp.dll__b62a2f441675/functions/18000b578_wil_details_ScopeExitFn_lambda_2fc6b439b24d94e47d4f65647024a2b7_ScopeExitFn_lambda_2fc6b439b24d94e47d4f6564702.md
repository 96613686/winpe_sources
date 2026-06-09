# wil::details::ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___::_ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___

- ea: `0x18000b578`
- end: `0x18000b5e1`
- name: `wil::details::ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___::_ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bb80`

## callees

- `0x18000b578`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b5c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b5c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b5ad`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b5ad`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___::_ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___(
        __int64 a1)
{
  unsigned int i; // edi

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    if ( **(_QWORD **)a1 )
    {
      for ( i = 0; i < **(_DWORD **)(a1 + 8); ++i )
        SysFreeString(*(BSTR *)(**(_QWORD **)a1 + 8LL * i));
      CoTaskMemFree(**(LPVOID **)a1);
    }
  }
}

```

## disassembly

```asm
0x18000b578  mov     [rsp+arg_0], rbx
0x18000b57d  push    rdi
0x18000b57e  sub     rsp, 20h
0x18000b582  mov     rbx, rcx
0x18000b585  xor     ecx, ecx
0x18000b587  cmp     [rbx+10h], cl
0x18000b58a  jz      short loc_18000B5D5
0x18000b58c  mov     [rbx+10h], cl
0x18000b58f  mov     rax, [rbx]
0x18000b592  cmp     [rax], rcx
0x18000b595  jz      short loc_18000B5D5
0x18000b597  mov     rax, [rbx+8]
0x18000b59b  mov     edi, ecx
0x18000b59d  cmp     [rax], ecx
0x18000b59f  jbe     short loc_18000B5C3
0x18000b5a1  mov     rax, [rbx]
0x18000b5a4  mov     edx, edi
0x18000b5a6  mov     rcx, [rax]
0x18000b5a9  mov     rcx, [rcx+rdx*8]; bstrString
0x18000b5ad  call    cs:__imp_SysFreeString
0x18000b5b4  nop     dword ptr [rax+rax+00h]
0x18000b5b9  mov     rax, [rbx+8]
0x18000b5bd  inc     edi
0x18000b5bf  cmp     edi, [rax]
0x18000b5c1  jb      short loc_18000B5A1
0x18000b5c3  mov     rcx, [rbx]
0x18000b5c6  mov     rcx, [rcx]; pv
0x18000b5c9  call    cs:__imp_CoTaskMemFree
0x18000b5d0  nop     dword ptr [rax+rax+00h]
0x18000b5d5  mov     rbx, [rsp+28h+arg_0]
0x18000b5da  add     rsp, 20h
0x18000b5de  pop     rdi
0x18000b5df  retn
```
