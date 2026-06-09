# ImpLsaDelete

- ea: `0x1800204c4`
- end: `0x18002052a`
- name: `ImpLsaDelete`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021a70`
- `0x180021e98`
- `0x180021f68`
- `0x180022340`

## callees

- `0x1800204c4`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020509`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800204f6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800204f6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800204d8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800204d8`
- `api-ms-win-security-lsapolicy-l1-1-1!LsaDelete` at `0x1800204ea`
- `api-ms-win-security-lsapolicy-l1-1-1!LsaDelete` at `0x1800204ea`

## string_xrefs

- `0x18002050f`: `Failed to impersonate caller, error %lu\n`

## pseudocode

```c
__int64 __fastcall ImpLsaDelete(void *a1, void *a2)
{
  int v2; // edi
  unsigned int v4; // ebx
  DWORD LastError; // eax

  v2 = 0;
  if ( a1 )
  {
    if ( !ImpersonateLoggedOnUser(a1) )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(4, "Failed to impersonate caller, error %lu\n", LastError);
      return (unsigned int)-1073741790;
    }
    v2 = 1;
  }
  v4 = LsaDelete(a2);
  if ( v2 )
    RevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x1800204c4  mov     [rsp+arg_0], rbx
0x1800204c9  push    rdi
0x1800204ca  sub     rsp, 20h
0x1800204ce  xor     edi, edi
0x1800204d0  mov     rbx, rdx
0x1800204d3  test    rcx, rcx
0x1800204d6  jz      short loc_1800204E7
0x1800204d8  call    cs:__imp_ImpersonateLoggedOnUser
0x1800204de  test    eax, eax
0x1800204e0  jz      short loc_180020509
0x1800204e2  mov     edi, 1
0x1800204e7  mov     rcx, rbx; ObjectHandle
0x1800204ea  call    cs:__imp_LsaDelete
0x1800204f0  mov     ebx, eax
0x1800204f2  test    edi, edi
0x1800204f4  jz      short loc_1800204FC
0x1800204f6  call    cs:__imp_RevertToSelf
0x1800204fc  mov     eax, ebx
0x1800204fe  mov     rbx, [rsp+28h+arg_0]
0x180020503  add     rsp, 20h
0x180020507  pop     rdi
0x180020508  retn
0x180020509  call    cs:__imp_GetLastError
0x18002050f  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x180020516  mov     ecx, 4
0x18002051b  mov     r8d, eax
0x18002051e  call    DsRolepLogPrintRoutine
0x180020523  mov     ebx, 0C0000022h
0x180020528  jmp     short loc_1800204FC
```
