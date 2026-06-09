# wil::details::lambda_call__lambda_59686f5bdc64e0b3030b8493370b48bc___::_lambda_call__lambda_59686f5bdc64e0b3030b8493370b48bc___

- ea: `0x140005cf4`
- end: `0x140005d1a`
- name: `wil::details::lambda_call__lambda_59686f5bdc64e0b3030b8493370b48bc___::_lambda_call__lambda_59686f5bdc64e0b3030b8493370b48bc___`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400186ca`

## callees

- `0x140005cf4`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140005d0f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140005d0f`

## pseudocode

```c
BOOL __fastcall wil::details::lambda_call__lambda_59686f5bdc64e0b3030b8493370b48bc___::_lambda_call__lambda_59686f5bdc64e0b3030b8493370b48bc___(
        __int64 a1)
{
  BOOL result; // eax

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    return MoveFileExW(*(LPCWSTR *)a1, *(LPCWSTR *)(a1 + 8), 1u);
  }
  return result;
}

```

## disassembly

```asm
0x140005cf4  sub     rsp, 28h
0x140005cf8  cmp     byte ptr [rcx+10h], 0
0x140005cfc  jz      short loc_140005D15
0x140005cfe  mov     byte ptr [rcx+10h], 0
0x140005d02  mov     r8d, 1; dwFlags
0x140005d08  mov     rdx, [rcx+8]; lpNewFileName
0x140005d0c  mov     rcx, [rcx]; lpExistingFileName
0x140005d0f  call    cs:__imp_MoveFileExW
0x140005d15  add     rsp, 28h
0x140005d19  retn
```
