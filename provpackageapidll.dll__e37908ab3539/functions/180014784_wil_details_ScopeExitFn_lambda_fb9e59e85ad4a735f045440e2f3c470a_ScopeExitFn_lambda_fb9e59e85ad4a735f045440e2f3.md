# wil::details::ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a___::_ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a___

- ea: `0x180014784`
- end: `0x1800147b6`
- name: `wil::details::ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a___::_ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a___`
- size: `50`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800189f1`

## callees

- `0x180014784`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001479d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800147aa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001479d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800147aa`

## pseudocode

```c
BOOL __fastcall wil::details::ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a___::_ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a___(
        __int64 a1)
{
  BOOL result; // eax

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    DeleteFileW(**(LPCWSTR **)a1);
    return DeleteFileW(**(LPCWSTR **)(a1 + 8));
  }
  return result;
}

```

## disassembly

```asm
0x180014784  push    rbx
0x180014786  sub     rsp, 20h
0x18001478a  cmp     byte ptr [rcx+10h], 0
0x18001478e  mov     rbx, rcx
0x180014791  jz      short loc_1800147B0
0x180014793  mov     byte ptr [rcx+10h], 0
0x180014797  mov     rcx, [rcx]
0x18001479a  mov     rcx, [rcx]; lpFileName
0x18001479d  call    cs:__imp_DeleteFileW
0x1800147a3  mov     rcx, [rbx+8]
0x1800147a7  mov     rcx, [rcx]; lpFileName
0x1800147aa  call    cs:__imp_DeleteFileW
0x1800147b0  add     rsp, 20h
0x1800147b4  pop     rbx
0x1800147b5  retn
```
