# ImpLsaQueryInformationPolicy

- ea: `0x1800206a4`
- end: `0x180020712`
- name: `ImpLsaQueryInformationPolicy`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011240`
- `0x180022898`

## callees

- `0x1800206a4`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206f1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800206e0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800206e0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800206bd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800206bd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800206d4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800206d4`

## string_xrefs

- `0x1800206f7`: `Failed to impersonate caller, error %lu\n`

## pseudocode

```c
__int64 __fastcall ImpLsaQueryInformationPolicy(void *a1, void *a2, POLICY_INFORMATION_CLASS a3, PVOID *a4)
{
  int v4; // edi
  unsigned int InformationPolicy; // ebx
  DWORD LastError; // eax

  v4 = 0;
  if ( a1 )
  {
    if ( !ImpersonateLoggedOnUser(a1) )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(4, "Failed to impersonate caller, error %lu\n", LastError);
      return (unsigned int)-1073741790;
    }
    v4 = 1;
  }
  InformationPolicy = LsaQueryInformationPolicy(a2, a3, a4);
  if ( v4 )
    RevertToSelf();
  return InformationPolicy;
}

```

## disassembly

```asm
0x1800206a4  push    rbx
0x1800206a6  push    rbp
0x1800206a7  push    rsi
0x1800206a8  push    rdi
0x1800206a9  sub     rsp, 28h
0x1800206ad  xor     edi, edi
0x1800206af  mov     rbx, r9
0x1800206b2  mov     esi, r8d
0x1800206b5  mov     rbp, rdx
0x1800206b8  test    rcx, rcx
0x1800206bb  jz      short loc_1800206CC
0x1800206bd  call    cs:__imp_ImpersonateLoggedOnUser
0x1800206c3  test    eax, eax
0x1800206c5  jz      short loc_1800206F1
0x1800206c7  mov     edi, 1
0x1800206cc  mov     r8, rbx; Buffer
0x1800206cf  mov     edx, esi; InformationClass
0x1800206d1  mov     rcx, rbp; PolicyHandle
0x1800206d4  call    cs:__imp_LsaQueryInformationPolicy
0x1800206da  mov     ebx, eax
0x1800206dc  test    edi, edi
0x1800206de  jz      short loc_1800206E6
0x1800206e0  call    cs:__imp_RevertToSelf
0x1800206e6  mov     eax, ebx
0x1800206e8  add     rsp, 28h
0x1800206ec  pop     rdi
0x1800206ed  pop     rsi
0x1800206ee  pop     rbp
0x1800206ef  pop     rbx
0x1800206f0  retn
0x1800206f1  call    cs:__imp_GetLastError
0x1800206f7  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x1800206fe  mov     ecx, 4
0x180020703  mov     r8d, eax
0x180020706  call    DsRolepLogPrintRoutine
0x18002070b  mov     ebx, 0C0000022h
0x180020710  jmp     short loc_1800206E6
```
