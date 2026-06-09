# wil::details::ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000___::_ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000___

- ea: `0x180003270`
- end: `0x180003290`
- name: `wil::details::ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000___::_ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000___`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006cf6`
- `0x180007040`

## callees

- `0x180003270`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003285`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003285`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000___::_ScopeExitFn__lambda_ad248e0ab71bdb01f4ac6bd623336000___(
        __int64 a1)
{
  _DWORD *v1; // rax

  if ( *(_BYTE *)(a1 + 8) )
  {
    v1 = *(_DWORD **)a1;
    *(_BYTE *)(a1 + 8) = 0;
    if ( *v1 )
      CoUninitialize();
  }
}

```

## disassembly

```asm
0x180003270  sub     rsp, 28h
0x180003274  xor     edx, edx
0x180003276  cmp     [rcx+8], dl
0x180003279  jz      short loc_18000328B
0x18000327b  mov     rax, [rcx]
0x18000327e  mov     [rcx+8], dl
0x180003281  cmp     [rax], edx
0x180003283  jz      short loc_18000328B
0x180003285  call    cs:__imp_CoUninitialize
0x18000328b  add     rsp, 28h
0x18000328f  retn
```
