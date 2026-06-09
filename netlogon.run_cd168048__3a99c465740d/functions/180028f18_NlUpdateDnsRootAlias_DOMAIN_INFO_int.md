# NlUpdateDnsRootAlias(_DOMAIN_INFO *,int *)

- ea: `0x180028f18`
- end: `0x180029211`
- name: `?NlUpdateDnsRootAlias@@YAJPEAU_DOMAIN_INFO@@PEAH@Z`
- size: `761`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180027fa4`
- `0x180075b60`

## callees

- `0x1800037f0`
- `0x180007518`
- `0x18000c130`
- `0x1800110ac`
- `0x180028f18`
- `0x180088584`
- `0x180089414`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f69`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f69`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800291c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800291d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800291c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800291d7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800290df`
- `ntdll!RtlLeaveCriticalSection` at `0x180029197`
- `ntdll!RtlLeaveCriticalSection` at `0x1800290df`
- `ntdll!RtlLeaveCriticalSection` at `0x180029197`
- `ntdll!RtlEnterCriticalSection` at `0x180029035`
- `ntdll!RtlEnterCriticalSection` at `0x1800290f2`
- `ntdll!RtlEnterCriticalSection` at `0x180029035`
- `ntdll!RtlEnterCriticalSection` at `0x1800290f2`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetDnsRootAlias` at `0x180028fc4`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!GetDnsRootAlias` at `0x180028fc4`

## string_xrefs

- `0x180028f41`: `NlUpdateDnsRootAlias: avoid DnsRootAlias update in setup mode\n`
- `0x1800291af`: `NlUpdateDnsRootAlias: GetDnsRootAlias failed 0x%lx\n`
- `0x180029065`: `NlUpdateDnsRootAlias: Ignoring DnsDomainNameAlias update for same active name: %hs %hs\n`
- `0x180029088`: `NlUpdateDnsRootAlias: Ignoring DnsDomainNameAlias update for same alias name: %hs %hs\n`
- `0x1800290aa`: `NlUpdateDnsRootAlias: Updating DnsDomainNameAlias from %hs to %hs\n`
- `0x180029118`: `NlUpdateDnsRootAlias: Ignoring DnsForestNameAlias update for same active name: %hs %hs\n`
- `0x18002913b`: `NlUpdateDnsRootAlias: Ignoring DnsForestNameAlias update for same alias name: %hs %hs\n`
- `0x180029161`: `NlUpdateDnsRootAlias: Updating DnsForestNameAlias from %hs to %hs\n`

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
0x180028f18  push    rbx
0x180028f1a  push    rbp
0x180028f1b  push    rsi
0x180028f1c  push    rdi
0x180028f1d  push    r12
0x180028f1f  push    r13
0x180028f21  push    r14
0x180028f23  push    r15
0x180028f25  sub     rsp, 28h
0x180028f29  xor     ebp, ebp
0x180028f2b  mov     r14, rdx
0x180028f2e  mov     r15, rcx
0x180028f31  test    rdx, rdx
0x180028f34  jz      short loc_180028F38
0x180028f36  mov     [rdx], ebp
0x180028f38  call    ?NlDoingSetup@@YAEXZ; NlDoingSetup(void)
0x180028f3d  test    al, al
0x180028f3f  jz      short loc_180028F59
0x180028f41  lea     rdx, aNlupdatednsroo_2; "NlUpdateDnsRootAlias: avoid DnsRootAlia"...
0x180028f48  mov     ecx, 2; unsigned int
0x180028f4d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180028f52  mov     ebx, ebp
0x180028f54  jmp     loc_1800291FD
0x180028f59  mov     ebx, 200h
0x180028f5e  mov     r12d, 40h ; '@'
0x180028f64  mov     edx, ebx; uBytes
0x180028f66  mov     ecx, r12d; uFlags
0x180028f69  call    cs:__imp_LocalAlloc
0x180028f70  nop     dword ptr [rax+rax+00h]
0x180028f75  mov     r13, rax
0x180028f78  test    rax, rax
0x180028f7b  jnz     short loc_180028F87
0x180028f7d  mov     ebx, 0C0000017h
0x180028f82  jmp     loc_1800291FD
0x180028f87  mov     rdx, rbx; uBytes
0x180028f8a  mov     ecx, r12d; uFlags
0x180028f8d  mov     rsi, rbp
0x180028f90  mov     rdi, rbp
0x180028f93  call    cs:__imp_LocalAlloc
0x180028f9a  nop     dword ptr [rax+rax+00h]
0x180028f9f  mov     r12, rax
0x180028fa2  test    rax, rax
0x180028fa5  jnz     short loc_180028FB1
0x180028fa7  mov     ebx, 0C0000017h
0x180028fac  jmp     loc_1800291C0
0x180028fb1  call    IsDsGetServersAndSitesForNetLogonPresent
0x180028fb6  test    al, al
0x180028fb8  jz      loc_1800291A7
0x180028fbe  mov     rdx, r12
0x180028fc1  mov     rcx, r13
0x180028fc4  call    cs:__imp_GetDnsRootAlias
0x180028fcb  nop     dword ptr [rax+rax+00h]
0x180028fd0  mov     ebx, eax
0x180028fd2  test    eax, eax
0x180028fd4  js      loc_1800291AC
0x180028fda  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028fde  mov     rax, rbx
0x180028fe1  inc     rax
0x180028fe4  cmp     [r13+rax*2+0], bp
0x180028fea  jnz     short loc_180028FE1
0x180028fec  test    rax, rax
0x180028fef  jz      short loc_180029006
0x180028ff1  xor     r8d, r8d; int
0x180028ff4  xor     edx, edx; lpMultiByteStr
0x180028ff6  mov     rcx, r13; lpWideCharStr
0x180028ff9  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180028ffe  mov     rsi, rax
0x180029001  test    rax, rax
0x180029004  jz      short loc_180028FA7
0x180029006  inc     rbx
0x180029009  cmp     [r12+rbx*2], bp
0x18002900e  jnz     short loc_180029006
0x180029010  test    rbx, rbx
0x180029013  jz      short loc_18002902E
0x180029015  xor     r8d, r8d; int
0x180029018  xor     edx, edx; lpMultiByteStr
0x18002901a  mov     rcx, r12; lpWideCharStr
0x18002901d  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180029022  mov     rdi, rax
0x180029025  test    rax, rax
0x180029028  jz      loc_180028FA7
0x18002902e  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180029035  call    cs:__imp_RtlEnterCriticalSection
0x18002903c  nop     dword ptr [rax+rax+00h]
0x180029041  mov     rcx, [r15+98h]; char *
0x180029048  mov     rdx, rsi; char *
0x18002904b  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x180029050  mov     ebx, 1
0x180029055  mov     ebp, 100h
0x18002905a  test    eax, eax
0x18002905c  jz      short loc_18002906E
0x18002905e  mov     r8, [r15+98h]
0x180029065  lea     rdx, aNlupdatednsroo_3; "NlUpdateDnsRootAlias: Ignoring DnsDomai"...
0x18002906c  jmp     short loc_18002908F
0x18002906e  mov     rcx, [r15+0A0h]; char *
0x180029075  mov     rdx, rsi; char *
0x180029078  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x18002907d  test    eax, eax
0x18002907f  jz      short loc_18002909B
0x180029081  mov     r8, [r15+0A0h]
0x180029088  lea     rdx, aNlupdatednsroo; "NlUpdateDnsRootAlias: Ignoring DnsDomai"...
0x18002908f  mov     r9, rsi
0x180029092  mov     ecx, ebp; unsigned int
0x180029094  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029099  jmp     short loc_1800290D8
0x18002909b  test    r14, r14
0x18002909e  jz      short loc_1800290A3
0x1800290a0  mov     [r14], ebx
0x1800290a3  mov     r8, [r15+0A0h]
0x1800290aa  lea     rdx, aNlupdatednsroo_5; "NlUpdateDnsRootAlias: Updating DnsDomai"...
0x1800290b1  mov     r9, rsi
0x1800290b4  mov     ecx, 400h; unsigned int
0x1800290b9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800290be  mov     rcx, [r15+0A0h]
0x1800290c5  test    rcx, rcx
0x1800290c8  jz      short loc_1800290CF
0x1800290ca  call    NetpMemoryFree
0x1800290cf  mov     [r15+0A0h], rsi
0x1800290d6  xor     esi, esi
0x1800290d8  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800290df  call    cs:__imp_RtlLeaveCriticalSection
0x1800290e6  nop     dword ptr [rax+rax+00h]
0x1800290eb  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800290f2  call    cs:__imp_RtlEnterCriticalSection
0x1800290f9  nop     dword ptr [rax+rax+00h]
0x1800290fe  mov     rcx, cs:?NlGlobalUtf8DnsForestName@@3PEADEA; char *
0x180029105  mov     rdx, rdi; char *
0x180029108  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x18002910d  test    eax, eax
0x18002910f  jz      short loc_180029121
0x180029111  mov     r8, cs:?NlGlobalUtf8DnsForestName@@3PEADEA; char * NlGlobalUtf8DnsForestName
0x180029118  lea     rdx, aNlupdatednsroo_1; "NlUpdateDnsRootAlias: Ignoring DnsFores"...
0x18002911f  jmp     short loc_180029142
0x180029121  mov     rcx, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char *
0x180029128  mov     rdx, rdi; char *
0x18002912b  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x180029130  test    eax, eax
0x180029132  jz      short loc_180029150
0x180029134  mov     r8, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x18002913b  lea     rdx, aNlupdatednsroo_4; "NlUpdateDnsRootAlias: Ignoring DnsFores"...
0x180029142  mov     r9, rdi
0x180029145  mov     ecx, ebp; unsigned int
0x180029147  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002914c  xor     ebp, ebp
0x18002914e  jmp     short loc_180029190
0x180029150  xor     ebp, ebp
0x180029152  test    r14, r14
0x180029155  jz      short loc_18002915A
0x180029157  mov     [r14], ebx
0x18002915a  mov     r8, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x180029161  lea     rdx, aNlupdatednsroo_6; "NlUpdateDnsRootAlias: Updating DnsFores"...
0x180029168  mov     r9, rdi
0x18002916b  mov     ecx, 400h; unsigned int
0x180029170  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029175  mov     rcx, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x18002917c  test    rcx, rcx
0x18002917f  jz      short loc_180029186
0x180029181  call    NetpMemoryFree
0x180029186  mov     cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA, rdi; char * NlGlobalUtf8DnsForestNameAlias
0x18002918d  mov     rdi, rbp
0x180029190  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180029197  call    cs:__imp_RtlLeaveCriticalSection
0x18002919e  nop     dword ptr [rax+rax+00h]
0x1800291a3  mov     ebx, ebp
0x1800291a5  jmp     short loc_1800291C0
0x1800291a7  mov     ebx, 0C00000BBh
0x1800291ac  mov     r8d, ebx
0x1800291af  lea     rdx, aNlupdatednsroo_0; "NlUpdateDnsRootAlias: GetDnsRootAlias f"...
0x1800291b6  mov     ecx, 100h; unsigned int
0x1800291bb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800291c0  mov     rcx, r13; hMem
0x1800291c3  call    cs:__imp_LocalFree
0x1800291ca  nop     dword ptr [rax+rax+00h]
0x1800291cf  test    r12, r12
0x1800291d2  jz      short loc_1800291E3
0x1800291d4  mov     rcx, r12; hMem
0x1800291d7  call    cs:__imp_LocalFree
0x1800291de  nop     dword ptr [rax+rax+00h]
0x1800291e3  test    rsi, rsi
0x1800291e6  jz      short loc_1800291F0
0x1800291e8  mov     rcx, rsi
0x1800291eb  call    NetpMemoryFree
0x1800291f0  test    rdi, rdi
0x1800291f3  jz      short loc_1800291FD
0x1800291f5  mov     rcx, rdi
0x1800291f8  call    NetpMemoryFree
0x1800291fd  mov     eax, ebx
0x1800291ff  add     rsp, 28h
0x180029203  pop     r15
0x180029205  pop     r14
0x180029207  pop     r13
0x180029209  pop     r12
0x18002920b  pop     rdi
0x18002920c  pop     rsi
0x18002920d  pop     rbp
0x18002920e  pop     rbx
0x18002920f  retn
```
