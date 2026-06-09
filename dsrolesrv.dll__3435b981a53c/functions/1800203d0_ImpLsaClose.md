# ImpLsaClose

- ea: `0x1800203d0`
- end: `0x180020436`
- name: `ImpLsaClose`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
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

- `0x1800203d0`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020415`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020402`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020402`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800203e4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800203e4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800203f6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800203f6`

## string_xrefs

- `0x18002041b`: `Failed to impersonate caller, error %lu\n`

## pseudocode

```c
__int64 __fastcall ImpLsaClose(void *a1, void *a2)
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
  v4 = LsaClose(a2);
  if ( v2 )
    RevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x1800203d0  mov     [rsp+arg_0], rbx
0x1800203d5  push    rdi
0x1800203d6  sub     rsp, 20h
0x1800203da  xor     edi, edi
0x1800203dc  mov     rbx, rdx
0x1800203df  test    rcx, rcx
0x1800203e2  jz      short loc_1800203F3
0x1800203e4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800203ea  test    eax, eax
0x1800203ec  jz      short loc_180020415
0x1800203ee  mov     edi, 1
0x1800203f3  mov     rcx, rbx; ObjectHandle
0x1800203f6  call    cs:__imp_LsaClose
0x1800203fc  mov     ebx, eax
0x1800203fe  test    edi, edi
0x180020400  jz      short loc_180020408
0x180020402  call    cs:__imp_RevertToSelf
0x180020408  mov     eax, ebx
0x18002040a  mov     rbx, [rsp+28h+arg_0]
0x18002040f  add     rsp, 20h
0x180020413  pop     rdi
0x180020414  retn
0x180020415  call    cs:__imp_GetLastError
0x18002041b  lea     rdx, aFailedToImpers; "Failed to impersonate caller, error %lu"...
0x180020422  mov     ecx, 4
0x180020427  mov     r8d, eax
0x18002042a  call    DsRolepLogPrintRoutine
0x18002042f  mov     ebx, 0C0000022h
0x180020434  jmp     short loc_180020408
```
