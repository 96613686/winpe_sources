# DisableTokenBackupPrivilege(void *)

- ea: `0x180022030`
- end: `0x180022062`
- name: `?DisableTokenBackupPrivilege@@YAXPEAX@Z`
- size: `50`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180022030`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180022057`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180022057`

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
0x180022030  sub     rsp, 38h
0x180022034  mov     r8, cs:?g_pTokenPrivilege@@3PEAU_TOKEN_PRIVILEGES@@EA; NewState
0x18002203b  test    r8, r8
0x18002203e  jz      short loc_18002205D
0x180022040  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x180022049  xor     r9d, r9d; BufferLength
0x18002204c  xor     edx, edx; DisableAllPrivileges
0x18002204e  mov     [rsp+38h+PreviousState], 0; PreviousState
0x180022057  call    cs:__imp_AdjustTokenPrivileges
0x18002205d  add     rsp, 38h
0x180022061  retn
```
