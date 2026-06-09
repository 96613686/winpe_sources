# NlUpdateDnsRootAlias(_DOMAIN_INFO *,int *)

- ea: `0x180027ab4`
- end: `0x180027d72`
- name: `?NlUpdateDnsRootAlias@@YAJPEAU_DOMAIN_INFO@@PEAH@Z`
- size: `702`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180026c90`
- `0x18007070c`

## callees

- `0x180003670`
- `0x180007278`
- `0x18000ba1c`
- `0x1800109fc`
- `0x180027ab4`
- `0x1800824b4`
- `0x180083250`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027b05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027b29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027b05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027b29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d3f`
- `ntdll!RtlLeaveCriticalSection` at `0x180027c5f`
- `ntdll!RtlLeaveCriticalSection` at `0x180027d0b`
- `ntdll!RtlLeaveCriticalSection` at `0x180027c5f`
- `ntdll!RtlLeaveCriticalSection` at `0x180027d0b`
- `ntdll!RtlEnterCriticalSection` at `0x180027bbb`
- `ntdll!RtlEnterCriticalSection` at `0x180027c6c`
- `ntdll!RtlEnterCriticalSection` at `0x180027bbb`
- `ntdll!RtlEnterCriticalSection` at `0x180027c6c`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetDnsRootAlias` at `0x180027b54`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetDnsRootAlias` at `0x180027b54`

## string_xrefs

- `0x180027add`: `NlUpdateDnsRootAlias: avoid DnsRootAlias update in setup mode\n`
- `0x180027d1d`: `NlUpdateDnsRootAlias: GetDnsRootAlias failed 0x%lx\n`
- `0x180027be5`: `NlUpdateDnsRootAlias: Ignoring DnsDomainNameAlias update for same active name: %hs %hs\n`
- `0x180027c08`: `NlUpdateDnsRootAlias: Ignoring DnsDomainNameAlias update for same alias name: %hs %hs\n`
- `0x180027c2a`: `NlUpdateDnsRootAlias: Updating DnsDomainNameAlias from %hs to %hs\n`
- `0x180027c8c`: `NlUpdateDnsRootAlias: Ignoring DnsForestNameAlias update for same active name: %hs %hs\n`
- `0x180027caf`: `NlUpdateDnsRootAlias: Ignoring DnsForestNameAlias update for same alias name: %hs %hs\n`
- `0x180027cd5`: `NlUpdateDnsRootAlias: Updating DnsForestNameAlias from %hs to %hs\n`

## pseudocode

```c
__int64 __fastcall NlUpdateDnsRootAlias(struct _DOMAIN_INFO *a1, int *a2)
{
  int DnsRootAlias; // ebx
  WCHAR *v5; // r13
  const char *v6; // rsi
  char *Utf8StrFromWStr; // rdi
  WCHAR *v8; // r12
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx

  if ( a2 )
    *a2 = 0;
  if ( NlDoingSetup() )
  {
    NlPrintRoutine(2u, L"NlUpdateDnsRootAlias: avoid DnsRootAlias update in setup mode\n");
    return 0;
  }
  v5 = (WCHAR *)LocalAlloc(0x40u, 0x200u);
  if ( !v5 )
    return (unsigned int)-1073741801;
  v6 = 0;
  Utf8StrFromWStr = 0;
  v8 = (WCHAR *)LocalAlloc(0x40u, 0x200u);
  if ( v8 )
  {
    if ( (unsigned __int8)IsDsGetServersAndSitesForNetLogonPresent() )
    {
      DnsRootAlias = GetDnsRootAlias(v5, v8);
      if ( DnsRootAlias >= 0 )
      {
        v9 = -1;
        v10 = -1;
        do
          ++v10;
        while ( v5[v10] );
        if ( !v10 || (v6 = NetpCreateUtf8StrFromWStr(v5, 0, 0)) != 0 )
        {
          do
            ++v9;
          while ( v8[v9] );
          if ( !v9 || (Utf8StrFromWStr = NetpCreateUtf8StrFromWStr(v8, 0, 0)) != 0 )
          {
            RtlEnterCriticalSection(&NlGlobalDomainCritSect);
            if ( (unsigned int)NlEqualDnsNameUtf8(*((const char **)a1 + 19), v6) )
            {
              NlPrintRoutine(
                0x100u,
                L"NlUpdateDnsRootAlias: Ignoring DnsDomainNameAlias update for same active name: %hs %hs\n",
                *((_QWORD *)a1 + 19),
                v6);
            }
            else if ( (unsigned int)NlEqualDnsNameUtf8(*((const char **)a1 + 20), v6) )
            {
              NlPrintRoutine(
                0x100u,
                L"NlUpdateDnsRootAlias: Ignoring DnsDomainNameAlias update for same alias name: %hs %hs\n",
                *((_QWORD *)a1 + 20),
                v6);
            }
            else
            {
              if ( a2 )
                *a2 = 1;
              NlPrintRoutine(
                0x400u,
                L"NlUpdateDnsRootAlias: Updating DnsDomainNameAlias from %hs to %hs\n",
                *((_QWORD *)a1 + 20),
                v6);
              v11 = *((_QWORD *)a1 + 20);
              if ( v11 )
                NetpMemoryFree(v11);
              *((_QWORD *)a1 + 20) = v6;
              v6 = 0;
            }
            RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
            RtlEnterCriticalSection(&NlGlobalDnsForestNameCritSect);
            if ( (unsigned int)NlEqualDnsNameUtf8(NlGlobalUtf8DnsForestName, Utf8StrFromWStr) )
            {
              NlPrintRoutine(
                0x100u,
                L"NlUpdateDnsRootAlias: Ignoring DnsForestNameAlias update for same active name: %hs %hs\n",
                NlGlobalUtf8DnsForestName,
                Utf8StrFromWStr);
            }
            else if ( (unsigned int)NlEqualDnsNameUtf8(NlGlobalUtf8DnsForestNameAlias, Utf8StrFromWStr) )
            {
              NlPrintRoutine(
                0x100u,
                L"NlUpdateDnsRootAlias: Ignoring DnsForestNameAlias update for same alias name: %hs %hs\n",
                NlGlobalUtf8DnsForestNameAlias,
                Utf8StrFromWStr);
            }
            else
            {
              if ( a2 )
                *a2 = 1;
              NlPrintRoutine(
                0x400u,
                L"NlUpdateDnsRootAlias: Updating DnsForestNameAlias from %hs to %hs\n",
                NlGlobalUtf8DnsForestNameAlias,
                Utf8StrFromWStr);
              if ( NlGlobalUtf8DnsForestNameAlias )
                NetpMemoryFree(NlGlobalUtf8DnsForestNameAlias);
              NlGlobalUtf8DnsForestNameAlias = Utf8StrFromWStr;
              Utf8StrFromWStr = 0;
            }
            RtlLeaveCriticalSection(&NlGlobalDnsForestNameCritSect);
            DnsRootAlias = 0;
            goto LABEL_41;
          }
        }
        goto LABEL_8;
      }
    }
    else
    {
      DnsRootAlias = -1073741637;
    }
    NlPrintRoutine(0x100u, L"NlUpdateDnsRootAlias: GetDnsRootAlias failed 0x%lx\n", (unsigned int)DnsRootAlias);
    goto LABEL_41;
  }
LABEL_8:
  DnsRootAlias = -1073741801;
LABEL_41:
  LocalFree(v5);
  if ( v8 )
    LocalFree(v8);
  if ( v6 )
    NetpMemoryFree(v6);
  if ( Utf8StrFromWStr )
    NetpMemoryFree(Utf8StrFromWStr);
  return (unsigned int)DnsRootAlias;
}

```

## disassembly

```asm
0x180027ab4  push    rbx
0x180027ab6  push    rbp
0x180027ab7  push    rsi
0x180027ab8  push    rdi
0x180027ab9  push    r12
0x180027abb  push    r13
0x180027abd  push    r14
0x180027abf  push    r15
0x180027ac1  sub     rsp, 28h
0x180027ac5  xor     ebp, ebp
0x180027ac7  mov     r14, rdx
0x180027aca  mov     r15, rcx
0x180027acd  test    rdx, rdx
0x180027ad0  jz      short loc_180027AD4
0x180027ad2  mov     [rdx], ebp
0x180027ad4  call    ?NlDoingSetup@@YAEXZ; NlDoingSetup(void)
0x180027ad9  test    al, al
0x180027adb  jz      short loc_180027AF5
0x180027add  lea     rdx, aNlupdatednsroo_2; "NlUpdateDnsRootAlias: avoid DnsRootAlia"...
0x180027ae4  mov     ecx, 2; unsigned int
0x180027ae9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027aee  mov     ebx, ebp
0x180027af0  jmp     loc_180027D5F
0x180027af5  mov     ebx, 200h
0x180027afa  mov     r12d, 40h ; '@'
0x180027b00  mov     edx, ebx; uBytes
0x180027b02  mov     ecx, r12d; uFlags
0x180027b05  call    cs:__imp_LocalAlloc
0x180027b0b  mov     r13, rax
0x180027b0e  test    rax, rax
0x180027b11  jnz     short loc_180027B1D
0x180027b13  mov     ebx, 0C0000017h
0x180027b18  jmp     loc_180027D5F
0x180027b1d  mov     rdx, rbx; uBytes
0x180027b20  mov     ecx, r12d; uFlags
0x180027b23  mov     rsi, rbp
0x180027b26  mov     rdi, rbp
0x180027b29  call    cs:__imp_LocalAlloc
0x180027b2f  mov     r12, rax
0x180027b32  test    rax, rax
0x180027b35  jnz     short loc_180027B41
0x180027b37  mov     ebx, 0C0000017h
0x180027b3c  jmp     loc_180027D2E
0x180027b41  call    IsDsGetServersAndSitesForNetLogonPresent
0x180027b46  test    al, al
0x180027b48  jz      loc_180027D15
0x180027b4e  mov     rdx, r12
0x180027b51  mov     rcx, r13
0x180027b54  call    cs:__imp_GetDnsRootAlias
0x180027b5a  mov     ebx, eax
0x180027b5c  test    eax, eax
0x180027b5e  js      loc_180027D1A
0x180027b64  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180027b68  mov     rax, rbx
0x180027b6b  inc     rax
0x180027b6e  cmp     [r13+rax*2+0], bp
0x180027b74  jnz     short loc_180027B6B
0x180027b76  test    rax, rax
0x180027b79  jz      short loc_180027B90
0x180027b7b  xor     r8d, r8d; int
0x180027b7e  xor     edx, edx; lpMultiByteStr
0x180027b80  mov     rcx, r13; lpWideCharStr
0x180027b83  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180027b88  mov     rsi, rax
0x180027b8b  test    rax, rax
0x180027b8e  jz      short loc_180027B37
0x180027b90  inc     rbx
0x180027b93  cmp     [r12+rbx*2], bp
0x180027b98  jnz     short loc_180027B90
0x180027b9a  test    rbx, rbx
0x180027b9d  jz      short loc_180027BB4
0x180027b9f  xor     r8d, r8d; int
0x180027ba2  xor     edx, edx; lpMultiByteStr
0x180027ba4  mov     rcx, r12; lpWideCharStr
0x180027ba7  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180027bac  mov     rdi, rax
0x180027baf  test    rax, rax
0x180027bb2  jz      short loc_180027B37
0x180027bb4  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180027bbb  call    cs:__imp_RtlEnterCriticalSection
0x180027bc1  mov     rcx, [r15+98h]; char *
0x180027bc8  mov     rdx, rsi; char *
0x180027bcb  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x180027bd0  mov     ebx, 1
0x180027bd5  mov     ebp, 100h
0x180027bda  test    eax, eax
0x180027bdc  jz      short loc_180027BEE
0x180027bde  mov     r8, [r15+98h]
0x180027be5  lea     rdx, aNlupdatednsroo_3; "NlUpdateDnsRootAlias: Ignoring DnsDomai"...
0x180027bec  jmp     short loc_180027C0F
0x180027bee  mov     rcx, [r15+0A0h]; char *
0x180027bf5  mov     rdx, rsi; char *
0x180027bf8  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x180027bfd  test    eax, eax
0x180027bff  jz      short loc_180027C1B
0x180027c01  mov     r8, [r15+0A0h]
0x180027c08  lea     rdx, aNlupdatednsroo; "NlUpdateDnsRootAlias: Ignoring DnsDomai"...
0x180027c0f  mov     r9, rsi
0x180027c12  mov     ecx, ebp; unsigned int
0x180027c14  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027c19  jmp     short loc_180027C58
0x180027c1b  test    r14, r14
0x180027c1e  jz      short loc_180027C23
0x180027c20  mov     [r14], ebx
0x180027c23  mov     r8, [r15+0A0h]
0x180027c2a  lea     rdx, aNlupdatednsroo_5; "NlUpdateDnsRootAlias: Updating DnsDomai"...
0x180027c31  mov     r9, rsi
0x180027c34  mov     ecx, 400h; unsigned int
0x180027c39  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027c3e  mov     rcx, [r15+0A0h]
0x180027c45  test    rcx, rcx
0x180027c48  jz      short loc_180027C4F
0x180027c4a  call    NetpMemoryFree
0x180027c4f  mov     [r15+0A0h], rsi
0x180027c56  xor     esi, esi
0x180027c58  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180027c5f  call    cs:__imp_RtlLeaveCriticalSection
0x180027c65  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180027c6c  call    cs:__imp_RtlEnterCriticalSection
0x180027c72  mov     rcx, cs:?NlGlobalUtf8DnsForestName@@3PEADEA; char *
0x180027c79  mov     rdx, rdi; char *
0x180027c7c  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x180027c81  test    eax, eax
0x180027c83  jz      short loc_180027C95
0x180027c85  mov     r8, cs:?NlGlobalUtf8DnsForestName@@3PEADEA; char * NlGlobalUtf8DnsForestName
0x180027c8c  lea     rdx, aNlupdatednsroo_1; "NlUpdateDnsRootAlias: Ignoring DnsFores"...
0x180027c93  jmp     short loc_180027CB6
0x180027c95  mov     rcx, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char *
0x180027c9c  mov     rdx, rdi; char *
0x180027c9f  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x180027ca4  test    eax, eax
0x180027ca6  jz      short loc_180027CC4
0x180027ca8  mov     r8, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x180027caf  lea     rdx, aNlupdatednsroo_4; "NlUpdateDnsRootAlias: Ignoring DnsFores"...
0x180027cb6  mov     r9, rdi
0x180027cb9  mov     ecx, ebp; unsigned int
0x180027cbb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027cc0  xor     ebp, ebp
0x180027cc2  jmp     short loc_180027D04
0x180027cc4  xor     ebp, ebp
0x180027cc6  test    r14, r14
0x180027cc9  jz      short loc_180027CCE
0x180027ccb  mov     [r14], ebx
0x180027cce  mov     r8, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x180027cd5  lea     rdx, aNlupdatednsroo_6; "NlUpdateDnsRootAlias: Updating DnsFores"...
0x180027cdc  mov     r9, rdi
0x180027cdf  mov     ecx, 400h; unsigned int
0x180027ce4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027ce9  mov     rcx, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x180027cf0  test    rcx, rcx
0x180027cf3  jz      short loc_180027CFA
0x180027cf5  call    NetpMemoryFree
0x180027cfa  mov     cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA, rdi; char * NlGlobalUtf8DnsForestNameAlias
0x180027d01  mov     rdi, rbp
0x180027d04  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180027d0b  call    cs:__imp_RtlLeaveCriticalSection
0x180027d11  mov     ebx, ebp
0x180027d13  jmp     short loc_180027D2E
0x180027d15  mov     ebx, 0C00000BBh
0x180027d1a  mov     r8d, ebx
0x180027d1d  lea     rdx, aNlupdatednsroo_0; "NlUpdateDnsRootAlias: GetDnsRootAlias f"...
0x180027d24  mov     ecx, 100h; unsigned int
0x180027d29  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027d2e  mov     rcx, r13; hMem
0x180027d31  call    cs:__imp_LocalFree
0x180027d37  test    r12, r12
0x180027d3a  jz      short loc_180027D45
0x180027d3c  mov     rcx, r12; hMem
0x180027d3f  call    cs:__imp_LocalFree
0x180027d45  test    rsi, rsi
0x180027d48  jz      short loc_180027D52
0x180027d4a  mov     rcx, rsi
0x180027d4d  call    NetpMemoryFree
0x180027d52  test    rdi, rdi
0x180027d55  jz      short loc_180027D5F
0x180027d57  mov     rcx, rdi
0x180027d5a  call    NetpMemoryFree
0x180027d5f  mov     eax, ebx
0x180027d61  add     rsp, 28h
0x180027d65  pop     r15
0x180027d67  pop     r14
0x180027d69  pop     r13
0x180027d6b  pop     r12
0x180027d6d  pop     rdi
0x180027d6e  pop     rsi
0x180027d6f  pop     rbp
0x180027d70  pop     rbx
0x180027d71  retn
```
