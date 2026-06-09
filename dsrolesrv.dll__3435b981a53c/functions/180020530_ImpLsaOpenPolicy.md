# ImpLsaOpenPolicy

- ea: `0x180020530`
- end: `0x1800205a4`
- name: `ImpLsaOpenPolicy`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011240`
- `0x180021a70`
- `0x180021e98`
- `0x180022340`
- `0x180022898`

## callees

- `0x180020530`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020583`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020583`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020572`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020572`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020549`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180020549`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180020566`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180020566`

## string_xrefs

- `0x180020589`: `Failed to impersonate caller, error %lu\n`

## pseudocode

```c
__int64 __fastcall ImpLsaOpenPolicy(
        void *a1,
        struct _LSA_UNICODE_STRING *a2,
        struct _LSA_OBJECT_ATTRIBUTES *a3,
        ACCESS_MASK a4,
        PVOID *PolicyHandle)
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
  v9 = LsaOpenPolicy(a2, a3, a4, PolicyHandle);
  if ( v5 )
    RevertToSelf();
  return v9;
}

```

## disassembly

```asm
0x180020530  push    rbx
0x180020532  push    rbp
0x180020533  push    rsi
0x180020534  push    rdi
0x180020535  sub     rsp, 28h
0x180020539  xor     edi, edi
0x18002053b  mov     ebx, r9d
0x18002053e  mov     rsi, r8
0x180020541  mov     rbp, rdx
0x180020544  test    rcx, rcx
0x180020547  jz      short loc_180020558
0x180020549  call    cs:__imp_ImpersonateLoggedOnUser
0x18002054f  test    eax, eax
0x180020551  jz      short loc_180020583
0x180020553  mov     edi, 1
0x180020558  mov     r9, [rsp+48h+PolicyHandle]; PolicyHandle
0x18002055d  mov     r8d, ebx; DesiredAccess
0x180020560  mov     rdx, rsi; ObjectAttributes
0x180020563  mov     rcx, rbp; SystemName
0x180020566  call    cs:__imp_LsaOpenPolicy
0x18002056c  mov     ebx, eax
0x18002056e  test    edi, edi
0x180020570  jz      short loc_180020578
0x180020572  call    cs:__imp_RevertToSelf
0x180020578  mov     eax, ebx
0x18002057a  add     rsp, 28h
0x18002057e  pop     rdi
0x18002057f  pop     rsi
0x180020580  pop     rbp
0x180020581  pop     rbx
0x180020582  retn
0x180020583  call    cs:__imp_GetLastError
0x180020589  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x180020590  mov     ecx, 4
0x180020595  mov     r8d, eax
0x180020598  call    DsRolepLogPrintRoutine
0x18002059d  mov     ebx, 0C0000022h
0x1800205a2  jmp     short loc_180020578
```
