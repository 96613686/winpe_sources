# ImpLsaOpenTrustedDomain

- ea: `0x1800205ac`
- end: `0x180020620`
- name: `ImpLsaOpenTrustedDomain`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021e98`
- `0x180021f68`
- `0x180022340`

## callees

- `0x1800205ac`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205ff`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800205ee`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800205ee`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800205c5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800205c5`
- `ADVAPI32!LsaOpenTrustedDomain` at `0x1800205e2`
- `ADVAPI32!LsaOpenTrustedDomain` at `0x1800205e2`

## string_xrefs

- `0x180020605`: `Failed to impersonate caller, error %lu\n`

## pseudocode

```c
__int64 __fastcall ImpLsaOpenTrustedDomain(void *a1, void *a2, void *a3, ACCESS_MASK a4, PVOID *TrustedDomainHandle)
{
  int v5; // edi
  unsigned int v9; // ebx
  DWORD LastError; // eax

  v5 = 0;
  if ( a1 )
  {
    if ( !ImpersonateLoggedOnUser(a1) )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(4, "Failed to impersonate caller, error %lu\n", LastError);
      return (unsigned int)-1073741790;
    }
    v5 = 1;
  }
  v9 = LsaOpenTrustedDomain(a2, a3, a4, TrustedDomainHandle);
  if ( v5 )
    RevertToSelf();
  return v9;
}

```

## disassembly

```asm
0x1800205ac  push    rbx
0x1800205ae  push    rbp
0x1800205af  push    rsi
0x1800205b0  push    rdi
0x1800205b1  sub     rsp, 28h
0x1800205b5  xor     edi, edi
0x1800205b7  mov     ebx, r9d
0x1800205ba  mov     rsi, r8
0x1800205bd  mov     rbp, rdx
0x1800205c0  test    rcx, rcx
0x1800205c3  jz      short loc_1800205D4
0x1800205c5  call    cs:__imp_ImpersonateLoggedOnUser
0x1800205cb  test    eax, eax
0x1800205cd  jz      short loc_1800205FF
0x1800205cf  mov     edi, 1
0x1800205d4  mov     r9, [rsp+48h+TrustedDomainHandle]; TrustedDomainHandle
0x1800205d9  mov     r8d, ebx; DesiredAccess
0x1800205dc  mov     rdx, rsi; TrustedDomainSid
0x1800205df  mov     rcx, rbp; PolicyHandle
0x1800205e2  call    cs:__imp_LsaOpenTrustedDomain
0x1800205e8  mov     ebx, eax
0x1800205ea  test    edi, edi
0x1800205ec  jz      short loc_1800205F4
0x1800205ee  call    cs:__imp_RevertToSelf
0x1800205f4  mov     eax, ebx
0x1800205f6  add     rsp, 28h
0x1800205fa  pop     rdi
0x1800205fb  pop     rsi
0x1800205fc  pop     rbp
0x1800205fd  pop     rbx
0x1800205fe  retn
0x1800205ff  call    cs:__imp_GetLastError
0x180020605  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x18002060c  mov     ecx, 4
0x180020611  mov     r8d, eax
0x180020614  call    DsRolepLogPrintRoutine
0x180020619  mov     ebx, 0C0000022h
0x18002061e  jmp     short loc_1800205F4
```
