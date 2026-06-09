# ImpLsaCreateTrustedDomainEx

- ea: `0x18002043c`
- end: `0x1800204be`
- name: `ImpLsaCreateTrustedDomainEx`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800217f0`
- `0x180021f68`

## callees

- `0x18002043c`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002049d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002049d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002048c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002048c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020455`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020455`
- `ADVAPI32!LsaCreateTrustedDomainEx` at `0x180020480`
- `ADVAPI32!LsaCreateTrustedDomainEx` at `0x180020480`

## string_xrefs

- `0x1800204a3`: `Failed to impersonate caller, error %lu\n`

## pseudocode

```c
__int64 __fastcall ImpLsaCreateTrustedDomainEx(
        void *a1,
        void *a2,
        struct _TRUSTED_DOMAIN_INFORMATION_EX *a3,
        struct _TRUSTED_DOMAIN_AUTH_INFORMATION *a4,
        __int64 a5,
        PVOID *TrustedDomainHandle)
{
  int v6; // edi
  unsigned int TrustedDomain; // ebx
  DWORD LastError; // eax

  v6 = 0;
  if ( a1 )
  {
    if ( !ImpersonateLoggedOnUser(a1) )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(4, "Failed to impersonate caller, error %lu\n", LastError);
      return (unsigned int)-1073741790;
    }
    v6 = 1;
  }
  TrustedDomain = LsaCreateTrustedDomainEx(a2, a3, a4, 0x10000u, TrustedDomainHandle);
  if ( v6 )
    RevertToSelf();
  return TrustedDomain;
}

```

## disassembly

```asm
0x18002043c  push    rbx
0x18002043e  push    rbp
0x18002043f  push    rsi
0x180020440  push    rdi
0x180020441  sub     rsp, 38h
0x180020445  xor     edi, edi
0x180020447  mov     rbx, r9
0x18002044a  mov     rsi, r8
0x18002044d  mov     rbp, rdx
0x180020450  test    rcx, rcx
0x180020453  jz      short loc_180020464
0x180020455  call    cs:__imp_ImpersonateLoggedOnUser
0x18002045b  test    eax, eax
0x18002045d  jz      short loc_18002049D
0x18002045f  mov     edi, 1
0x180020464  mov     rax, [rsp+58h+arg_28]
0x18002046c  mov     r9d, 10000h; DesiredAccess
0x180020472  mov     r8, rbx; AuthenticationInformation
0x180020475  mov     [rsp+58h+TrustedDomainHandle], rax; TrustedDomainHandle
0x18002047a  mov     rdx, rsi; TrustedDomainInformation
0x18002047d  mov     rcx, rbp; PolicyHandle
0x180020480  call    cs:__imp_LsaCreateTrustedDomainEx
0x180020486  mov     ebx, eax
0x180020488  test    edi, edi
0x18002048a  jz      short loc_180020492
0x18002048c  call    cs:__imp_RevertToSelf
0x180020492  mov     eax, ebx
0x180020494  add     rsp, 38h
0x180020498  pop     rdi
0x180020499  pop     rsi
0x18002049a  pop     rbp
0x18002049b  pop     rbx
0x18002049c  retn
0x18002049d  call    cs:__imp_GetLastError
0x1800204a3  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x1800204aa  mov     ecx, 4
0x1800204af  mov     r8d, eax
0x1800204b2  call    DsRolepLogPrintRoutine
0x1800204b7  mov     ebx, 0C0000022h
0x1800204bc  jmp     short loc_180020492
```
