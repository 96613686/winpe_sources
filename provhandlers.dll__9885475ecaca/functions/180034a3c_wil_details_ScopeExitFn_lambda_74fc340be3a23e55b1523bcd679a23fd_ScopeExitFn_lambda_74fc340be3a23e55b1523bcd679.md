# wil::details::ScopeExitFn__lambda_74fc340be3a23e55b1523bcd679a23fd___::_ScopeExitFn__lambda_74fc340be3a23e55b1523bcd679a23fd___

- ea: `0x180034a3c`
- end: `0x180034a9a`
- name: `wil::details::ScopeExitFn__lambda_74fc340be3a23e55b1523bcd679a23fd___::_ScopeExitFn__lambda_74fc340be3a23e55b1523bcd679a23fd___`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003d8c0`

## callees

- `0x180034a3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034a70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034a70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a68`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180034a8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180034a8b`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_74fc340be3a23e55b1523bcd679a23fd___::_ScopeExitFn__lambda_74fc340be3a23e55b1523bcd679a23fd___(
        __int64 a1)
{
  HKEY *v2; // rsi
  HKEY v3; // rbp
  DWORD LastError; // ebx

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    v2 = *(HKEY **)a1;
    v3 = **(HKEY **)a1;
    if ( v3 )
    {
      LastError = GetLastError();
      RegCloseKey(v3);
      SetLastError(LastError);
    }
    *v2 = 0;
    RegDeleteTreeW(**(HKEY **)(a1 + 8), L"Undo");
  }
}

```

## disassembly

```asm
0x180034a3c  push    rbx
0x180034a3e  push    rbp
0x180034a3f  push    rsi
0x180034a40  push    rdi
0x180034a41  sub     rsp, 28h
0x180034a45  cmp     byte ptr [rcx+10h], 0
0x180034a49  mov     rdi, rcx
0x180034a4c  jz      short loc_180034A91
0x180034a4e  mov     byte ptr [rcx+10h], 0
0x180034a52  mov     rsi, [rcx]
0x180034a55  mov     rbp, [rsi]
0x180034a58  test    rbp, rbp
0x180034a5b  jz      short loc_180034A76
0x180034a5d  call    cs:__imp_GetLastError
0x180034a63  mov     rcx, rbp; hKey
0x180034a66  mov     ebx, eax
0x180034a68  call    cs:__imp_RegCloseKey
0x180034a6e  mov     ecx, ebx; dwErrCode
0x180034a70  call    cs:__imp_SetLastError
0x180034a76  mov     qword ptr [rsi], 0
0x180034a7d  lea     rdx, ?gc_wszUndo@@3QBGB; "Undo"
0x180034a84  mov     rcx, [rdi+8]
0x180034a88  mov     rcx, [rcx]; hKey
0x180034a8b  call    cs:__imp_RegDeleteTreeW
0x180034a91  add     rsp, 28h
0x180034a95  pop     rdi
0x180034a96  pop     rsi
0x180034a97  pop     rbp
0x180034a98  pop     rbx
0x180034a99  retn
```
