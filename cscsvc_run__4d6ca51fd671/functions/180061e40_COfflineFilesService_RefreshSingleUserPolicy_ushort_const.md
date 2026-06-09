# COfflineFilesService::RefreshSingleUserPolicy(ushort const *)

- ea: `0x180061e40`
- end: `0x180061eae`
- name: `?RefreshSingleUserPolicy@COfflineFilesService@@UEAAJPEBG@Z`
- size: `110`
- prototype: `int(COfflineFilesService *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18005daf8`
- `0x180061e40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061e76`
- `KERNEL32!LocalFree` at `0x180061ea0`
- `KERNEL32!LocalFree` at `0x180061ea0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180061e6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180061e6c`

## pseudocode

```c
__int64 __fastcall COfflineFilesService::RefreshSingleUserPolicy(
        COfflineFilesService *this,
        const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  PSID v3; // r8
  signed int LastError; // eax
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  v2 = -2147483634;
  if ( g_PolicyAuthority != 1 )
    return v2;
  v3 = 0;
  Sid = 0;
  if ( !a2 )
  {
LABEL_7:
    v2 = CPolicyChgMonitor::Refresh(this, 1u, v3);
    LocalFree(Sid);
    return v2;
  }
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    v3 = Sid;
    goto LABEL_7;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v2;
}

```

## disassembly

```asm
0x180061e40  push    rbx
0x180061e42  sub     rsp, 20h
0x180061e46  cmp     cs:?g_PolicyAuthority@@3W4POLICY_AUTHORITY@@A, 1; POLICY_AUTHORITY g_PolicyAuthority
0x180061e4d  mov     rax, rdx
0x180061e50  mov     ebx, 8000000Eh
0x180061e55  jnz     short loc_180061EA6
0x180061e57  xor     r8d, r8d
0x180061e5a  mov     [rsp+28h+Sid], r8
0x180061e5f  test    rax, rax
0x180061e62  jz      short loc_180061E92
0x180061e64  lea     rdx, [rsp+28h+Sid]; Sid
0x180061e69  mov     rcx, rax; StringSid
0x180061e6c  call    cs:__imp_ConvertStringSidToSidW
0x180061e72  test    eax, eax
0x180061e74  jnz     short loc_180061E8D
0x180061e76  call    cs:__imp_GetLastError
0x180061e7c  mov     ebx, eax
0x180061e7e  test    eax, eax
0x180061e80  jle     short loc_180061EA6
0x180061e82  movzx   ebx, ax
0x180061e85  or      ebx, 80070000h
0x180061e8b  jmp     short loc_180061EA6
0x180061e8d  mov     r8, [rsp+28h+Sid]; void *
0x180061e92  mov     dl, 1; unsigned __int8
0x180061e94  call    ?Refresh@CPolicyChgMonitor@@QEAAJEPEAX@Z; CPolicyChgMonitor::Refresh(uchar,void *)
0x180061e99  mov     rcx, [rsp+28h+Sid]; hMem
0x180061e9e  mov     ebx, eax
0x180061ea0  call    cs:__imp_LocalFree
0x180061ea6  mov     eax, ebx
0x180061ea8  add     rsp, 20h
0x180061eac  pop     rbx
0x180061ead  retn
```
