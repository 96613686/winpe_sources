# ImpLsaOpenTrustedDomainByName

- ea: `0x180020628`
- end: `0x18002069c`
- name: `ImpLsaOpenTrustedDomainByName`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021f68`

## callees

- `0x180020628`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002067b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002067b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002066a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002066a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020641`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020641`
- `ADVAPI32!LsaOpenTrustedDomainByName` at `0x18002065e`
- `ADVAPI32!LsaOpenTrustedDomainByName` at `0x18002065e`

## string_xrefs

- `0x180020681`: `Failed to impersonate caller, error %lu\n`

## pseudocode

```c
__int64 __fastcall ImpLsaOpenTrustedDomainByName(
        void *a1,
        void *a2,
        struct _LSA_UNICODE_STRING *a3,
        ACCESS_MASK a4,
        PVOID *TrustedDomainHandle)
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
  v9 = LsaOpenTrustedDomainByName(a2, a3, a4, TrustedDomainHandle);
  if ( v5 )
    RevertToSelf();
  return v9;
}

```

## disassembly

```asm
0x180020628  push    rbx
0x18002062a  push    rbp
0x18002062b  push    rsi
0x18002062c  push    rdi
0x18002062d  sub     rsp, 28h
0x180020631  xor     edi, edi
0x180020633  mov     ebx, r9d
0x180020636  mov     rsi, r8
0x180020639  mov     rbp, rdx
0x18002063c  test    rcx, rcx
0x18002063f  jz      short loc_180020650
0x180020641  call    cs:__imp_ImpersonateLoggedOnUser
0x180020647  test    eax, eax
0x180020649  jz      short loc_18002067B
0x18002064b  mov     edi, 1
0x180020650  mov     r9, [rsp+48h+TrustedDomainHandle]; TrustedDomainHandle
0x180020655  mov     r8d, ebx; DesiredAccess
0x180020658  mov     rdx, rsi; TrustedDomainName
0x18002065b  mov     rcx, rbp; PolicyHandle
0x18002065e  call    cs:__imp_LsaOpenTrustedDomainByName
0x180020664  mov     ebx, eax
0x180020666  test    edi, edi
0x180020668  jz      short loc_180020670
0x18002066a  call    cs:__imp_RevertToSelf
0x180020670  mov     eax, ebx
0x180020672  add     rsp, 28h
0x180020676  pop     rdi
0x180020677  pop     rsi
0x180020678  pop     rbp
0x180020679  pop     rbx
0x18002067a  retn
0x18002067b  call    cs:__imp_GetLastError
0x180020681  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x180020688  mov     ecx, 4
0x18002068d  mov     r8d, eax
0x180020690  call    DsRolepLogPrintRoutine
0x180020695  mov     ebx, 0C0000022h
0x18002069a  jmp     short loc_180020670
```
