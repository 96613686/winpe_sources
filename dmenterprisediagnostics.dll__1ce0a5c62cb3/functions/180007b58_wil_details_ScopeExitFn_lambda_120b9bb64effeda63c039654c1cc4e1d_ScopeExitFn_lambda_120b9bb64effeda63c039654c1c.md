# wil::details::ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___::_ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___

- ea: `0x180007b58`
- end: `0x180007b77`
- name: `wil::details::ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___::_ScopeExitFn__lambda_120b9bb64effeda63c039654c1cc4e1d___`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024b1d`

## callees

- `0x180007b58`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b6c`

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
0x180007b58  sub     rsp, 28h
0x180007b5c  cmp     byte ptr [rcx+8], 0
0x180007b60  jz      short loc_180007B72
0x180007b62  mov     byte ptr [rcx+8], 0
0x180007b66  mov     rcx, [rcx]
0x180007b69  mov     rcx, [rcx]; pv
0x180007b6c  call    cs:__imp_CoTaskMemFree
0x180007b72  add     rsp, 28h
0x180007b76  retn
```
