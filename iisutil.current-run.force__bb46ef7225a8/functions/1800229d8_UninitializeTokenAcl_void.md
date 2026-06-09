# UninitializeTokenAcl(void)

- ea: `0x1800229d8`
- end: `0x180022a55`
- name: `?UninitializeTokenAcl@@YAXXZ`
- size: `125`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001eba0`

## callees

- `0x1800229d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800229e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022a22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800229e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022a22`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022a05`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022a3f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022a05`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022a3f`

## pseudocode

```c
void UninitializeTokenAcl(void)
{
  if ( g_pSidWpg )
  {
    LocalFree(g_pSidWpg);
    g_pSidWpg = 0;
  }
  if ( g_pSidLocalSystem )
  {
    FreeSid(g_pSidLocalSystem);
    g_pSidLocalSystem = 0;
  }
  if ( g_pTokenPrivilege )
  {
    LocalFree(g_pTokenPrivilege);
    g_pTokenPrivilege = 0;
  }
  if ( g_pTokenIntegritySid )
  {
    FreeSid(g_pTokenIntegritySid);
    g_pTokenIntegritySid = 0;
  }
}

```

## disassembly

```asm
0x1800229d8  sub     rsp, 28h
0x1800229dc  mov     rcx, cs:?g_pSidWpg@@3PEAXEA; hMem
0x1800229e3  test    rcx, rcx
0x1800229e6  jz      short loc_1800229F9
0x1800229e8  call    cs:__imp_LocalFree
0x1800229ee  mov     cs:?g_pSidWpg@@3PEAXEA, 0; void * g_pSidWpg
0x1800229f9  mov     rcx, cs:?g_pSidLocalSystem@@3PEAXEA; pSid
0x180022a00  test    rcx, rcx
0x180022a03  jz      short loc_180022A16
0x180022a05  call    cs:__imp_FreeSid
0x180022a0b  mov     cs:?g_pSidLocalSystem@@3PEAXEA, 0; void * g_pSidLocalSystem
0x180022a16  mov     rcx, cs:?g_pTokenPrivilege@@3PEAU_TOKEN_PRIVILEGES@@EA; hMem
0x180022a1d  test    rcx, rcx
0x180022a20  jz      short loc_180022A33
0x180022a22  call    cs:__imp_LocalFree
0x180022a28  mov     cs:?g_pTokenPrivilege@@3PEAU_TOKEN_PRIVILEGES@@EA, 0; _TOKEN_PRIVILEGES * g_pTokenPrivilege
0x180022a33  mov     rcx, cs:?g_pTokenIntegritySid@@3PEAXEA; pSid
0x180022a3a  test    rcx, rcx
0x180022a3d  jz      short loc_180022A50
0x180022a3f  call    cs:__imp_FreeSid
0x180022a45  mov     cs:?g_pTokenIntegritySid@@3PEAXEA, 0; void * g_pTokenIntegritySid
0x180022a50  add     rsp, 28h
0x180022a54  retn
```
