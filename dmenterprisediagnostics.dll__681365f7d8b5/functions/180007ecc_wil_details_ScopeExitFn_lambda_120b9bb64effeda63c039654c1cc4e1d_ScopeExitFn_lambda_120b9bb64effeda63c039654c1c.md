# wil::details::ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___::_ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___

- ea: `0x180007ecc`
- end: `0x180007ef2`
- name: `wil::details::ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___::_ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800259dd`

## callees

- `0x180007ecc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007ee0`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___::_ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___(
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
0x180007ecc  sub     rsp, 28h
0x180007ed0  cmp     byte ptr [rcx+8], 0
0x180007ed4  jz      short loc_180007EEC
0x180007ed6  mov     byte ptr [rcx+8], 0
0x180007eda  mov     rcx, [rcx]
0x180007edd  mov     rcx, [rcx]; pv
0x180007ee0  call    cs:__imp_CoTaskMemFree
0x180007ee7  nop     dword ptr [rax+rax+00h]
0x180007eec  add     rsp, 28h
0x180007ef0  retn
```
