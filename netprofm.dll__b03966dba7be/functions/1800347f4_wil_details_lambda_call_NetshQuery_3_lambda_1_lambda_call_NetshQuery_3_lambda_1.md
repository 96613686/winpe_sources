# wil::details::lambda_call__NetshQuery_::_3_::_lambda_1___::_lambda_call__NetshQuery_::_3_::_lambda_1___

- ea: `0x1800347f4`
- end: `0x18003480d`
- name: `wil::details::lambda_call__NetshQuery_::_3_::_lambda_1___::_lambda_call__NetshQuery_::_3_::_lambda_1___`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003ff9d`

## callees

- `0x1800347f4`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180034802`
- `WS2_32!__imp_WSACleanup` at `0x180034802`

## pseudocode

```c
int __fastcall wil::details::lambda_call__NetshQuery_::_3_::_lambda_1___::_lambda_call__NetshQuery_::_3_::_lambda_1___(
        __int64 a1)
{
  int result; // eax

  if ( *(_BYTE *)(a1 + 1) )
  {
    *(_BYTE *)(a1 + 1) = 0;
    return WSACleanup();
  }
  return result;
}

```

## disassembly

```asm
0x1800347f4  sub     rsp, 28h
0x1800347f8  cmp     byte ptr [rcx+1], 0
0x1800347fc  jz      short loc_180034808
0x1800347fe  mov     byte ptr [rcx+1], 0
0x180034802  call    cs:__imp_WSACleanup
0x180034808  add     rsp, 28h
0x18003480c  retn
```
