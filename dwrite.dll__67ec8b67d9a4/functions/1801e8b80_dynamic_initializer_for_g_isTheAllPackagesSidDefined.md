# _dynamic_initializer_for__g_isTheAllPackagesSidDefined__

- ea: `0x1801e8b80`
- end: `0x1801e8bae`
- name: `_dynamic_initializer_for__g_isTheAllPackagesSidDefined__`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1801e8b80`

## import_xrefs

- `kernel32!GetLastError` at `0x1801e8ba3`
- `kernel32!GetLastError` at `0x1801e8ba3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801e8b99`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801e8b99`

## pseudocode

```c
DWORD dynamic_initializer_for__g_isTheAllPackagesSidDefined__()
{
  DWORD result; // eax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  cbSid = 0;
  result = CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, 0, &cbSid);
  if ( !result )
    return GetLastError();
  return result;
}

```

## disassembly

```asm
0x1801e8b80  sub     rsp, 28h
0x1801e8b84  xor     edx, edx; DomainSid
0x1801e8b86  mov     [rsp+28h+cbSid], 0
0x1801e8b8e  lea     r9, [rsp+28h+cbSid]; cbSid
0x1801e8b93  xor     r8d, r8d; pSid
0x1801e8b96  lea     ecx, [rdx+54h]; WellKnownSidType
0x1801e8b99  call    cs:__imp_CreateWellKnownSid
0x1801e8b9f  test    eax, eax
0x1801e8ba1  jnz     short loc_1801E8BA9
0x1801e8ba3  call    cs:__imp_GetLastError
0x1801e8ba9  add     rsp, 28h
0x1801e8bad  retn
```
