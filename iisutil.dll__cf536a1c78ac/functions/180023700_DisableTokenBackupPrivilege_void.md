# DisableTokenBackupPrivilege(void *)

- ea: `0x180023700`
- end: `0x180023739`
- name: `?DisableTokenBackupPrivilege@@YAXPEAX@Z`
- size: `57`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180023700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180023727`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180023727`

## pseudocode

```c
void __fastcall DisableTokenBackupPrivilege(void *a1)
{
  if ( g_pTokenPrivilege )
    AdjustTokenPrivileges(a1, 0, g_pTokenPrivilege, 0, 0, 0);
}

```

## disassembly

```asm
0x180023700  sub     rsp, 38h
0x180023704  mov     r8, cs:?g_pTokenPrivilege@@3PEAU_TOKEN_PRIVILEGES@@EA; NewState
0x18002370b  test    r8, r8
0x18002370e  jz      short loc_180023733
0x180023710  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180023719  xor     r9d, r9d; BufferLength
0x18002371c  xor     edx, edx; DisableAllPrivileges
0x18002371e  mov     [rsp+38h+PreviousState], 0; PreviousState
0x180023727  call    cs:__imp_AdjustTokenPrivileges
0x18002372e  nop     dword ptr [rax+rax+00h]
0x180023733  add     rsp, 38h
0x180023737  retn
```
