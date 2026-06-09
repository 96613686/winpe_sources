# _InitializeWellKnownGroups(void)

- ea: `0x1800b1644`
- end: `0x1800b19fc`
- name: `?_InitializeWellKnownGroups@@YAJXZ`
- size: `952`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008399c`

## callees

- `0x180011278`
- `0x1800b1644`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b17eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b17fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b180b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b18f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b197a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b198a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b199a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b16ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b17eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b17fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b180b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1880`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b18f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b197a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b198a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b199a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b16b8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b1756`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b17db`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b1860`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b18e5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b196a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b16b8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b1756`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b17db`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b1860`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b18e5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b196a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b167a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b167a`

## pseudocode

```c
__int64 _InitializeWellKnownGroups(void)
{
  signed int v0; // ebx
  LsaHandleCache *v1; // rcx
  __int64 v2; // rdx
  DWORD cbSid; // [rsp+40h] [rbp+20h] BYREF

  cbSid = 0;
  if ( !dword_1801A0CD0 )
  {
    while ( _InterlockedCompareExchange(&g_lLock, 1, 0) )
      Sleep(1u);
    if ( !dword_1801A0CD0 )
    {
      cbSid = 68;
      if ( !CreateWellKnownSid(WinWorldSid, 0, &g_abWorldSid, &cbSid) )
      {
        v0 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
        if ( v0 < 0 )
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_58;
          }
          v2 = 59;
          goto LABEL_15;
        }
      }
      cbSid = 68;
      if ( !CreateWellKnownSid(WinAuthenticatedUserSid, 0, &g_abAuthUsersSid, &cbSid) )
      {
        v0 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
        if ( v0 < 0 )
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_58;
          }
          v2 = 60;
          goto LABEL_15;
        }
      }
      cbSid = 68;
      if ( !CreateWellKnownSid(WinInteractiveSid, 0, &g_abInteractiveSid, &cbSid) )
      {
        v0 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
        if ( v0 < 0 )
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_58;
          }
          v2 = 61;
          goto LABEL_15;
        }
      }
      cbSid = 68;
      if ( !CreateWellKnownSid(WinConsoleLogonSid, 0, &g_abConsoleLogonSid, &cbSid) )
      {
        v0 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
        if ( v0 < 0 )
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_58;
          }
          v2 = 62;
          goto LABEL_15;
        }
      }
      cbSid = 68;
      if ( !CreateWellKnownSid(WinRemoteLogonIdSid, 0, &g_abRemoteInteractiveSid, &cbSid) )
      {
        v0 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
        if ( v0 < 0 )
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_58;
          }
          v2 = 63;
          goto LABEL_15;
        }
      }
      cbSid = 68;
      if ( !CreateWellKnownSid(WinTerminalServerSid, 0, &g_abTerminalServerSid, &cbSid) )
      {
        v0 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
        if ( v0 < 0 )
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_58;
          }
          v2 = 64;
LABEL_15:
          WPP_SF_d(*((_QWORD *)v1 + 2), v2, WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids, (unsigned int)v0);
LABEL_58:
          g_lLock = 0;
          return (unsigned int)v0;
        }
      }
      dword_1801A0CD0 = 1;
    }
    v0 = 0;
    goto LABEL_58;
  }
  return 0;
}

```

## disassembly

```asm
0x1800b1644  mov     [rsp-18h+arg_8], rbx
0x1800b1649  mov     [rsp-18h+arg_10], rsi
0x1800b164e  push    rbp
0x1800b164f  push    r14
0x1800b1651  push    r15
0x1800b1653  mov     rbp, rsp
0x1800b1656  sub     rsp, 20h
0x1800b165a  cmp     cs:dword_1801A0CD0, 0
0x1800b1661  mov     [rbp+cbSid], 0
0x1800b1668  jz      short loc_1800B1671
0x1800b166a  xor     ebx, ebx
0x1800b166c  jmp     loc_1800B19E5
0x1800b1671  mov     esi, 1
0x1800b1676  jmp     short loc_1800B1686
0x1800b1678  mov     ecx, esi; dwMilliseconds
0x1800b167a  call    cs:__imp_Sleep
0x1800b1681  nop     dword ptr [rax+rax+00h]
0x1800b1686  xor     eax, eax
0x1800b1688  lock cmpxchg cs:?g_lLock@@3JA, esi; long g_lLock
0x1800b1690  jnz     short loc_1800B1678
0x1800b1692  cmp     cs:dword_1801A0CD0, 0
0x1800b1699  jnz     loc_1800B19D9
0x1800b169f  mov     r15d, 44h ; 'D'
0x1800b16a5  lea     r9, [rbp+cbSid]; cbSid
0x1800b16a9  lea     r8, ?g_abWorldSid@@3PAEA; pSid
0x1800b16b0  mov     [rbp+cbSid], r15d
0x1800b16b4  xor     edx, edx; DomainSid
0x1800b16b6  mov     ecx, esi; WellKnownSidType
0x1800b16b8  call    cs:__imp_CreateWellKnownSid
0x1800b16bf  nop     dword ptr [rax+rax+00h]
0x1800b16c4  mov     r14d, 0C0070000h
0x1800b16ca  test    eax, eax
0x1800b16cc  jnz     short loc_1800B1742
0x1800b16ce  call    cs:__imp_GetLastError
0x1800b16d5  nop     dword ptr [rax+rax+00h]
0x1800b16da  test    eax, eax
0x1800b16dc  jg      short loc_1800B16EE
0x1800b16de  call    cs:__imp_GetLastError
0x1800b16e5  nop     dword ptr [rax+rax+00h]
0x1800b16ea  mov     ebx, eax
0x1800b16ec  jmp     short loc_1800B1700
0x1800b16ee  call    cs:__imp_GetLastError
0x1800b16f5  nop     dword ptr [rax+rax+00h]
0x1800b16fa  movzx   ebx, ax
0x1800b16fd  or      ebx, r14d
0x1800b1700  test    ebx, ebx
0x1800b1702  jns     short loc_1800B1742
0x1800b1704  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b170b  lea     rax, WPP_GLOBAL_Control
0x1800b1712  cmp     rcx, rax
0x1800b1715  jz      loc_1800B19DB
0x1800b171b  test    [rcx+1Ch], sil
0x1800b171f  jz      loc_1800B19DB
0x1800b1725  mov     edx, 3Bh ; ';'
0x1800b172a  mov     rcx, [rcx+10h]
0x1800b172e  lea     r8, WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids
0x1800b1735  mov     r9d, ebx
0x1800b1738  call    WPP_SF_d
0x1800b173d  jmp     loc_1800B19DB
0x1800b1742  xor     edx, edx; DomainSid
0x1800b1744  mov     [rbp+cbSid], r15d
0x1800b1748  lea     r9, [rbp+cbSid]; cbSid
0x1800b174c  lea     r8, ?g_abAuthUsersSid@@3PAEA; pSid
0x1800b1753  lea     ecx, [rdx+11h]; WellKnownSidType
0x1800b1756  call    cs:__imp_CreateWellKnownSid
0x1800b175d  nop     dword ptr [rax+rax+00h]
0x1800b1762  test    eax, eax
0x1800b1764  jnz     short loc_1800B17C7
0x1800b1766  call    cs:__imp_GetLastError
0x1800b176d  nop     dword ptr [rax+rax+00h]
0x1800b1772  test    eax, eax
0x1800b1774  jg      short loc_1800B1786
0x1800b1776  call    cs:__imp_GetLastError
0x1800b177d  nop     dword ptr [rax+rax+00h]
0x1800b1782  mov     ebx, eax
0x1800b1784  jmp     short loc_1800B1798
0x1800b1786  call    cs:__imp_GetLastError
0x1800b178d  nop     dword ptr [rax+rax+00h]
0x1800b1792  movzx   ebx, ax
0x1800b1795  or      ebx, r14d
0x1800b1798  test    ebx, ebx
0x1800b179a  jns     short loc_1800B17C7
0x1800b179c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b17a3  lea     rax, WPP_GLOBAL_Control
0x1800b17aa  cmp     rcx, rax
0x1800b17ad  jz      loc_1800B19DB
0x1800b17b3  test    [rcx+1Ch], sil
0x1800b17b7  jz      loc_1800B19DB
0x1800b17bd  mov     edx, 3Ch ; '<'
0x1800b17c2  jmp     loc_1800B172A
0x1800b17c7  xor     edx, edx; DomainSid
0x1800b17c9  mov     [rbp+cbSid], r15d
0x1800b17cd  lea     r9, [rbp+cbSid]; cbSid
0x1800b17d1  lea     r8, ?g_abInteractiveSid@@3PAEA; pSid
0x1800b17d8  lea     ecx, [rdx+0Bh]; WellKnownSidType
0x1800b17db  call    cs:__imp_CreateWellKnownSid
0x1800b17e2  nop     dword ptr [rax+rax+00h]
0x1800b17e7  test    eax, eax
0x1800b17e9  jnz     short loc_1800B184C
0x1800b17eb  call    cs:__imp_GetLastError
0x1800b17f2  nop     dword ptr [rax+rax+00h]
0x1800b17f7  test    eax, eax
0x1800b17f9  jg      short loc_1800B180B
0x1800b17fb  call    cs:__imp_GetLastError
0x1800b1802  nop     dword ptr [rax+rax+00h]
0x1800b1807  mov     ebx, eax
0x1800b1809  jmp     short loc_1800B181D
0x1800b180b  call    cs:__imp_GetLastError
0x1800b1812  nop     dword ptr [rax+rax+00h]
0x1800b1817  movzx   ebx, ax
0x1800b181a  or      ebx, r14d
0x1800b181d  test    ebx, ebx
0x1800b181f  jns     short loc_1800B184C
0x1800b1821  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1828  lea     rax, WPP_GLOBAL_Control
0x1800b182f  cmp     rcx, rax
0x1800b1832  jz      loc_1800B19DB
0x1800b1838  test    [rcx+1Ch], sil
0x1800b183c  jz      loc_1800B19DB
0x1800b1842  mov     edx, 3Dh ; '='
0x1800b1847  jmp     loc_1800B172A
0x1800b184c  xor     edx, edx; DomainSid
0x1800b184e  mov     [rbp+cbSid], r15d
0x1800b1852  lea     r9, [rbp+cbSid]; cbSid
0x1800b1856  lea     r8, ?g_abConsoleLogonSid@@3PAEA; pSid
0x1800b185d  lea     ecx, [rdx+51h]; WellKnownSidType
0x1800b1860  call    cs:__imp_CreateWellKnownSid
0x1800b1867  nop     dword ptr [rax+rax+00h]
0x1800b186c  test    eax, eax
0x1800b186e  jnz     short loc_1800B18D1
0x1800b1870  call    cs:__imp_GetLastError
0x1800b1877  nop     dword ptr [rax+rax+00h]
0x1800b187c  test    eax, eax
0x1800b187e  jg      short loc_1800B1890
0x1800b1880  call    cs:__imp_GetLastError
0x1800b1887  nop     dword ptr [rax+rax+00h]
0x1800b188c  mov     ebx, eax
0x1800b188e  jmp     short loc_1800B18A2
0x1800b1890  call    cs:__imp_GetLastError
0x1800b1897  nop     dword ptr [rax+rax+00h]
0x1800b189c  movzx   ebx, ax
0x1800b189f  or      ebx, r14d
0x1800b18a2  test    ebx, ebx
0x1800b18a4  jns     short loc_1800B18D1
0x1800b18a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b18ad  lea     rax, WPP_GLOBAL_Control
0x1800b18b4  cmp     rcx, rax
0x1800b18b7  jz      loc_1800B19DB
0x1800b18bd  test    [rcx+1Ch], sil
0x1800b18c1  jz      loc_1800B19DB
0x1800b18c7  mov     edx, 3Eh ; '>'
0x1800b18cc  jmp     loc_1800B172A
0x1800b18d1  xor     edx, edx; DomainSid
0x1800b18d3  mov     [rbp+cbSid], r15d
0x1800b18d7  lea     r9, [rbp+cbSid]; cbSid
0x1800b18db  lea     r8, ?g_abRemoteInteractiveSid@@3PAEA; pSid
0x1800b18e2  lea     ecx, [rdx+14h]; WellKnownSidType
0x1800b18e5  call    cs:__imp_CreateWellKnownSid
0x1800b18ec  nop     dword ptr [rax+rax+00h]
0x1800b18f1  test    eax, eax
0x1800b18f3  jnz     short loc_1800B1956
0x1800b18f5  call    cs:__imp_GetLastError
0x1800b18fc  nop     dword ptr [rax+rax+00h]
0x1800b1901  test    eax, eax
0x1800b1903  jg      short loc_1800B1915
0x1800b1905  call    cs:__imp_GetLastError
0x1800b190c  nop     dword ptr [rax+rax+00h]
0x1800b1911  mov     ebx, eax
0x1800b1913  jmp     short loc_1800B1927
0x1800b1915  call    cs:__imp_GetLastError
0x1800b191c  nop     dword ptr [rax+rax+00h]
0x1800b1921  movzx   ebx, ax
0x1800b1924  or      ebx, r14d
0x1800b1927  test    ebx, ebx
0x1800b1929  jns     short loc_1800B1956
0x1800b192b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1932  lea     rax, WPP_GLOBAL_Control
0x1800b1939  cmp     rcx, rax
0x1800b193c  jz      loc_1800B19DB
0x1800b1942  test    [rcx+1Ch], sil
0x1800b1946  jz      loc_1800B19DB
0x1800b194c  mov     edx, 3Fh ; '?'
0x1800b1951  jmp     loc_1800B172A
0x1800b1956  xor     edx, edx; DomainSid
0x1800b1958  mov     [rbp+cbSid], r15d
0x1800b195c  lea     r9, [rbp+cbSid]; cbSid
0x1800b1960  lea     r8, ?g_abTerminalServerSid@@3PAEA; pSid
0x1800b1967  lea     ecx, [rdx+13h]; WellKnownSidType
0x1800b196a  call    cs:__imp_CreateWellKnownSid
0x1800b1971  nop     dword ptr [rax+rax+00h]
0x1800b1976  test    eax, eax
0x1800b1978  jnz     short loc_1800B19D3
0x1800b197a  call    cs:__imp_GetLastError
0x1800b1981  nop     dword ptr [rax+rax+00h]
0x1800b1986  test    eax, eax
0x1800b1988  jg      short loc_1800B199A
0x1800b198a  call    cs:__imp_GetLastError
0x1800b1991  nop     dword ptr [rax+rax+00h]
0x1800b1996  mov     ebx, eax
0x1800b1998  jmp     short loc_1800B19AC
0x1800b199a  call    cs:__imp_GetLastError
0x1800b19a1  nop     dword ptr [rax+rax+00h]
0x1800b19a6  movzx   ebx, ax
0x1800b19a9  or      ebx, r14d
0x1800b19ac  test    ebx, ebx
0x1800b19ae  jns     short loc_1800B19D3
0x1800b19b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b19b7  lea     rax, WPP_GLOBAL_Control
0x1800b19be  cmp     rcx, rax
0x1800b19c1  jz      short loc_1800B19DB
0x1800b19c3  test    [rcx+1Ch], sil
0x1800b19c7  jz      short loc_1800B19DB
0x1800b19c9  mov     edx, 40h ; '@'
0x1800b19ce  jmp     loc_1800B172A
0x1800b19d3  mov     cs:dword_1801A0CD0, esi
0x1800b19d9  xor     ebx, ebx
0x1800b19db  mov     cs:?g_lLock@@3JA, 0; long g_lLock
0x1800b19e5  mov     rsi, [rsp+20h+arg_10]
0x1800b19ea  mov     eax, ebx
0x1800b19ec  mov     rbx, [rsp+20h+arg_8]
0x1800b19f1  add     rsp, 20h
0x1800b19f5  pop     r15
0x1800b19f7  pop     r14
0x1800b19f9  pop     rbp
0x1800b19fa  retn
```
