# wil::details::ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3___::_ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3___

- ea: `0x18000a4b8`
- end: `0x18000a4d7`
- name: `wil::details::ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3___::_ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3___`
- size: `31`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800187b1`
- `0x180018b15`

## callees

- `0x18000a4b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000a4cc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000a4cc`

## pseudocode

```c
BOOL __fastcall wil::details::ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3___::_ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3___(
        __int64 a1)
{
  BOOL result; // eax

  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    return DeleteFileW(**(LPCWSTR **)a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000a4b8  sub     rsp, 28h
0x18000a4bc  cmp     byte ptr [rcx+8], 0
0x18000a4c0  jz      short loc_18000A4D2
0x18000a4c2  mov     byte ptr [rcx+8], 0
0x18000a4c6  mov     rcx, [rcx]
0x18000a4c9  mov     rcx, [rcx]; lpFileName
0x18000a4cc  call    cs:__imp_DeleteFileW
0x18000a4d2  add     rsp, 28h
0x18000a4d6  retn
```
