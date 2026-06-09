# GetTokenInformation_0

- ea: `0x140010ca4`
- end: `0x140010caa`
- name: `GetTokenInformation_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, LPVOID TokenInformation, DWORD TokenInformationLength, PDWORD ReturnLength)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001cf8c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140010ca4`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall GetTokenInformation_0(
        HANDLE TokenHandle,
        TOKEN_INFORMATION_CLASS TokenInformationClass,
        LPVOID TokenInformation,
        DWORD TokenInformationLength,
        PDWORD ReturnLength)
{
  return GetTokenInformation(TokenHandle, TokenInformationClass, TokenInformation, TokenInformationLength, ReturnLength);
}

```

## disassembly

```asm
0x140010ca4  jmp     cs:__imp_GetTokenInformation
```
