# UninitializeTokenAcl(void)

- ea: `0x1800241e8`
- end: `0x18002427e`
- name: `?UninitializeTokenAcl@@YAXXZ`
- size: `150`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001fda0`

## callees

- `0x1800241e8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002423e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002423e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002421b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180024261`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002421b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180024261`

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
0x1800241e8  sub     rsp, 28h
0x1800241ec  mov     rcx, cs:?g_pSidWpg@@3PEAXEA; hMem
0x1800241f3  test    rcx, rcx
0x1800241f6  jz      short loc_18002420F
0x1800241f8  call    cs:__imp_LocalFree
0x1800241ff  nop     dword ptr [rax+rax+00h]
0x180024204  mov     cs:?g_pSidWpg@@3PEAXEA, 0; void * g_pSidWpg
0x18002420f  mov     rcx, cs:?g_pSidLocalSystem@@3PEAXEA; pSid
0x180024216  test    rcx, rcx
0x180024219  jz      short loc_180024232
0x18002421b  call    cs:__imp_FreeSid
0x180024222  nop     dword ptr [rax+rax+00h]
0x180024227  mov     cs:?g_pSidLocalSystem@@3PEAXEA, 0; void * g_pSidLocalSystem
0x180024232  mov     rcx, cs:?g_pTokenPrivilege@@3PEAU_TOKEN_PRIVILEGES@@EA; hMem
0x180024239  test    rcx, rcx
0x18002423c  jz      short loc_180024255
0x18002423e  call    cs:__imp_LocalFree
0x180024245  nop     dword ptr [rax+rax+00h]
0x18002424a  mov     cs:?g_pTokenPrivilege@@3PEAU_TOKEN_PRIVILEGES@@EA, 0; _TOKEN_PRIVILEGES * g_pTokenPrivilege
0x180024255  mov     rcx, cs:?g_pTokenIntegritySid@@3PEAXEA; pSid
0x18002425c  test    rcx, rcx
0x18002425f  jz      short loc_180024278
0x180024261  call    cs:__imp_FreeSid
0x180024268  nop     dword ptr [rax+rax+00h]
0x18002426d  mov     cs:?g_pTokenIntegritySid@@3PEAXEA, 0; void * g_pTokenIntegritySid
0x180024278  add     rsp, 28h
0x18002427c  retn
```
