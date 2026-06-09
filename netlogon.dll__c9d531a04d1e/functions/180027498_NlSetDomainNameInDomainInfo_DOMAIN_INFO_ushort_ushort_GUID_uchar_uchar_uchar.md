# NlSetDomainNameInDomainInfo(_DOMAIN_INFO *,ushort *,ushort *,_GUID *,uchar *,uchar *,uchar *)

- ea: `0x180027498`
- end: `0x18002785b`
- name: `?NlSetDomainNameInDomainInfo@@YAKPEAU_DOMAIN_INFO@@PEAG1PEAU_GUID@@PEAE33@Z`
- size: `963`
- prototype: `unsigned int __usercall@<eax>(struct _DOMAIN_INFO *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, struct _GUID *@<r9>, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024f08`
- `0x18005360c`
- `0x180069580`
- `0x18007070c`

## callees

- `0x180003670`
- `0x180007278`
- `0x18000ba1c`
- `0x18000bd98`
- `0x18002631c`
- `0x180027410`
- `0x180027498`
- `0x18003f294`
- `0x18008315c`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800276eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800276eb`
- `ntdll!RtlLeaveCriticalSection` at `0x18002780d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002781a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002780d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002781a`
- `ntdll!RtlEnterCriticalSection` at `0x1800274ff`
- `ntdll!RtlEnterCriticalSection` at `0x18002750c`
- `ntdll!RtlEnterCriticalSection` at `0x1800274ff`
- `ntdll!RtlEnterCriticalSection` at `0x18002750c`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x1800275b7`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x1800275b7`
- `ntdll!RtlInitUnicodeString` at `0x180027599`
- `ntdll!RtlInitUnicodeString` at `0x180027599`
- `netutils!NetpwNameCanonicalize` at `0x180027565`
- `netutils!NetpwNameCanonicalize` at `0x180027565`
- `netutils!NetpwNameCompare` at `0x18002752c`
- `netutils!NetpwNameCompare` at `0x18002752c`
- `DNSAPI!DnsValidateName_W` at `0x180027665`
- `DNSAPI!DnsValidateName_W` at `0x180027665`

## pseudocode

```c
__int64 __fastcall NlSetDomainNameInDomainInfo(
        struct _DOMAIN_INFO *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _GUID *a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        unsigned __int8 *a7)
{
  DWORD LastError; // ebx
  char v12; // r14
  unsigned __int8 *v13; // r12
  NTSTATUS v14; // eax
  __int128 v15; // xmm0
  __int64 v16; // r14
  __int64 v17; // rbx
  DNS_STATUS v18; // eax
  char *Utf8StrFromWStr; // rbp
  unsigned int v20; // r14d
  char *v21; // rax
  char *v22; // rsi
  __int64 v23; // r12
  char *v24; // rbx
  _QWORD *v25; // rcx
  bool v26; // zf
  struct _GUID *v27; // rax
  char *v29; // [rsp+80h] [rbp+18h]

  LastError = 0;
  v29 = 0;
  v12 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  v13 = a7;
  if ( a7 )
    *a7 = 0;
  RtlEnterCriticalSection(&NlGlobalDomainCritSect);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a1 + 10);
  if ( a3 )
  {
    if ( (unsigned int)NetpwNameCompare(a3, (char *)a1 + 72, 6) )
    {
      NlPrintDomRoutine(0x400u, a1, L"Setting Netbios domain name to %ws\n", a3);
      LastError = NetpwNameCanonicalize(a3, (char *)a1 + 72, 32);
      if ( LastError )
      {
        NlPrintRoutine(0x100u, L"%ws: DomainName is invalid\n", a3);
LABEL_11:
        v12 = 0;
        goto LABEL_54;
      }
      RtlInitUnicodeString((PUNICODE_STRING)((char *)a1 + 56), (PCWSTR)a1 + 36);
      v14 = RtlUpcaseUnicodeToOemN(
              (PCHAR)a1 + 104,
              0xFu,
              (PULONG)a1 + 30,
              *((PCWCH *)a1 + 8),
              *((unsigned __int16 *)a1 + 28));
      if ( v14 < 0 )
      {
        NlPrintRoutine(0x100u, L"%ws: Unable to convert Domain name to OEM 0x%lx\n", a3, (unsigned int)v14);
        LastError = 8;
        goto LABEL_11;
      }
      v26 = NlGlobalMemberWorkstation == 0;
      *((_BYTE *)a1 + *((unsigned int *)a1 + 30) + 104) = 0;
      if ( v26 )
        v15 = *(_OWORD *)((char *)a1 + 56);
      else
        v15 = *((_OWORD *)a1 + 16);
      LastError = 0;
      v12 = 0;
      *(_OWORD *)((char *)a1 + 168) = v15;
      if ( a6 )
        *a6 = 1;
    }
    else
    {
      v12 = 0;
    }
  }
  if ( !(unsigned int)NlEqualDnsName(a2, *((const unsigned __int16 **)a1 + 18)) )
  {
    NlPrintDomRoutine(0x400u, a1, L"Setting DNS domain name to %ws\n", a2);
    if ( a2 )
    {
      v16 = -1;
      v17 = -1;
      do
        ++v17;
      while ( a2[v17] );
      v18 = DnsValidateName_W(a2, DnsNameDomain);
      if ( v18 )
      {
        if ( v18 != 9556 )
        {
          LastError = 1212;
          v12 = 0;
          goto LABEL_54;
        }
        NlPrintRoutine(2u, L"DnsDomainName contains underscore\n");
      }
      Utf8StrFromWStr = NetpCreateUtf8StrFromWStr(a2, 0, 0);
      v29 = Utf8StrFromWStr;
      if ( !Utf8StrFromWStr )
      {
        LastError = 8;
        v12 = 0;
        goto LABEL_54;
      }
      LastError = 2 * v17 + 2;
      do
        ++v16;
      while ( Utf8StrFromWStr[v16] );
      v20 = v16 + 1;
    }
    else
    {
      v20 = 0;
      Utf8StrFromWStr = 0;
    }
    NlFreeDnsDomainDomainInfo(a1);
    if ( LastError )
    {
      v21 = (char *)LocalAlloc(0, v20 + LastError);
      v22 = v21;
      if ( !v21 )
      {
        LastError = GetLastError();
        goto LABEL_11;
      }
      v23 = LastError;
      memcpy_0(v21, a2, LastError);
      *((_WORD *)a1 + 65) = LastError;
      *((_WORD *)a1 + 64) = LastError - 2;
      LastError = 0;
      *((_QWORD *)a1 + 18) = v22;
      *((_QWORD *)a1 + 17) = v22;
      if ( !v20 )
      {
        v13 = a7;
LABEL_40:
        v12 = 1;
        if ( a5 )
          *a5 = 1;
        goto LABEL_42;
      }
      v24 = &v22[v23];
      memcpy_0(&v22[v23], Utf8StrFromWStr, v20);
      v13 = a7;
      *((_QWORD *)a1 + 19) = v24;
    }
    LastError = 0;
    goto LABEL_40;
  }
LABEL_42:
  v25 = (_QWORD *)*((_QWORD *)a1 + 26);
  if ( !a4 )
  {
    v26 = v25 == 0;
    goto LABEL_48;
  }
  if ( v25 && *(_QWORD *)&a4->Data1 == *v25 )
  {
    v26 = *(_QWORD *)a4->Data4 == v25[1];
LABEL_48:
    if ( v26 )
      goto LABEL_54;
  }
  NlPrintDomRoutine(0x400u, a1, L"Setting Domain GUID to ");
  NlpDumpGuid(0x400u, a4);
  NlPrintRoutine(0x400u, L"\n");
  v27 = (struct _GUID *)((char *)a1 + 192);
  if ( a4 )
  {
    *v27 = *a4;
  }
  else
  {
    *v27 = 0;
    v27 = 0;
  }
  *((_QWORD *)a1 + 26) = v27;
  if ( v13 )
    *v13 = 1;
LABEL_54:
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 10);
  RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
  if ( v29 )
    NetpMemoryFree(v29);
  if ( v12 )
    NlSetDomainForestRoot(a1, 0);
  return LastError;
}

```

## disassembly

```asm
0x180027498  mov     [rsp+arg_8], rbx
0x18002749d  push    rbp
0x18002749e  push    rsi
0x18002749f  push    rdi
0x1800274a0  push    r12
0x1800274a2  push    r13
0x1800274a4  push    r14
0x1800274a6  push    r15
0x1800274a8  sub     rsp, 30h
0x1800274ac  mov     rax, [rsp+68h+arg_20]
0x1800274b4  xor     ebx, ebx
0x1800274b6  mov     [rsp+68h+arg_10], rbx
0x1800274be  mov     r13, r9
0x1800274c1  mov     [rsp+68h+arg_0], bl
0x1800274c5  mov     rbp, r8
0x1800274c8  mov     r15, rdx
0x1800274cb  mov     rdi, rcx
0x1800274ce  mov     r14b, bl
0x1800274d1  test    rax, rax
0x1800274d4  jz      short loc_1800274D8
0x1800274d6  mov     [rax], bl
0x1800274d8  mov     rsi, [rsp+68h+arg_28]
0x1800274e0  test    rsi, rsi
0x1800274e3  jz      short loc_1800274E7
0x1800274e5  mov     [rsi], bl
0x1800274e7  mov     r12, [rsp+68h+arg_30]
0x1800274ef  test    r12, r12
0x1800274f2  jz      short loc_1800274F8
0x1800274f4  mov     [r12], bl
0x1800274f8  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800274ff  call    cs:__imp_RtlEnterCriticalSection
0x180027505  lea     rcx, [rdi+190h]; CriticalSection
0x18002750c  call    cs:__imp_RtlEnterCriticalSection
0x180027512  test    rbp, rbp
0x180027515  jz      loc_180027616
0x18002751b  xor     r9d, r9d
0x18002751e  lea     r14, [rdi+48h]
0x180027522  mov     rdx, r14
0x180027525  mov     rcx, rbp
0x180027528  lea     r8d, [r9+6]
0x18002752c  call    cs:__imp_NetpwNameCompare
0x180027532  test    eax, eax
0x180027534  jz      loc_180027613
0x18002753a  mov     r9, rbp
0x18002753d  lea     r8, aSettingNetbios; "Setting Netbios domain name to %ws\n"
0x180027544  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180027547  mov     ecx, 400h; unsigned int
0x18002754c  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027551  mov     r9d, 6
0x180027557  mov     [rsp+68h+UnicodeSize], ebx
0x18002755b  mov     rdx, r14
0x18002755e  mov     rcx, rbp
0x180027561  lea     r8d, [r9+1Ah]
0x180027565  call    cs:__imp_NetpwNameCanonicalize
0x18002756b  mov     ebx, eax
0x18002756d  test    eax, eax
0x18002756f  jz      short loc_18002758F
0x180027571  mov     r8, rbp
0x180027574  lea     rdx, aWsDomainnameIs; "%ws: DomainName is invalid\n"
0x18002757b  mov     ecx, 100h; unsigned int
0x180027580  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027585  mov     r14b, [rsp+68h+arg_0]
0x18002758a  jmp     loc_180027806
0x18002758f  lea     rbx, [rdi+38h]
0x180027593  mov     rdx, r14; SourceString
0x180027596  mov     rcx, rbx; DestinationString
0x180027599  call    cs:__imp_RtlInitUnicodeString
0x18002759f  movzx   eax, word ptr [rbx]
0x1800275a2  lea     rcx, [rdi+68h]; OemString
0x1800275a6  mov     r9, [rdi+40h]; UnicodeString
0x1800275aa  lea     r8, [rdi+78h]; ResultSize
0x1800275ae  mov     edx, 0Fh; OemSize
0x1800275b3  mov     [rsp+68h+UnicodeSize], eax; UnicodeSize
0x1800275b7  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x1800275bd  xor     ecx, ecx
0x1800275bf  test    eax, eax
0x1800275c1  jns     short loc_1800275E1
0x1800275c3  mov     r9d, eax
0x1800275c6  lea     rdx, aWsUnableToConv; "%ws: Unable to convert Domain name to O"...
0x1800275cd  mov     r8, rbp
0x1800275d0  mov     ecx, 100h; unsigned int
0x1800275d5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800275da  mov     ebx, 8
0x1800275df  jmp     short loc_180027585
0x1800275e1  cmp     cs:?NlGlobalMemberWorkstation@@3HA, ecx; int NlGlobalMemberWorkstation
0x1800275e7  mov     eax, [rdi+78h]
0x1800275ea  mov     [rax+rdi+68h], cl
0x1800275ee  jz      short loc_1800275F9
0x1800275f0  movups  xmm0, xmmword ptr [rdi+100h]
0x1800275f7  jmp     short loc_1800275FC
0x1800275f9  movups  xmm0, xmmword ptr [rbx]
0x1800275fc  xor     ebx, ebx
0x1800275fe  mov     r14b, cl
0x180027601  movdqu  xmmword ptr [rdi+0A8h], xmm0
0x180027609  test    rsi, rsi
0x18002760c  jz      short loc_180027616
0x18002760e  mov     byte ptr [rsi], 1
0x180027611  jmp     short loc_180027616
0x180027613  mov     r14b, bl
0x180027616  mov     rdx, [rdi+90h]; unsigned __int16 *
0x18002761d  mov     rcx, r15; unsigned __int16 *
0x180027620  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180027625  test    eax, eax
0x180027627  jnz     loc_180027774
0x18002762d  mov     r9, r15
0x180027630  lea     r8, aSettingDnsDoma; "Setting DNS domain name to %ws\n"
0x180027637  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18002763a  mov     ecx, 400h; unsigned int
0x18002763f  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027644  test    r15, r15
0x180027647  jz      loc_1800276D3
0x18002764d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180027651  mov     rbx, r14
0x180027654  xor     esi, esi
0x180027656  inc     rbx
0x180027659  cmp     [r15+rbx*2], si
0x18002765e  jnz     short loc_180027656
0x180027660  xor     edx, edx; Format
0x180027662  mov     rcx, r15; pszName
0x180027665  call    cs:__imp_DnsValidateName_W
0x18002766b  test    eax, eax
0x18002766d  jz      short loc_180027694
0x18002766f  cmp     eax, 2554h
0x180027674  jz      short loc_180027683
0x180027676  mov     ebx, 4BCh
0x18002767b  mov     r14b, sil
0x18002767e  jmp     loc_180027806
0x180027683  lea     rdx, aDnsdomainnameC; "DnsDomainName contains underscore\n"
0x18002768a  mov     ecx, 2; unsigned int
0x18002768f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027694  xor     r8d, r8d; int
0x180027697  xor     edx, edx; lpMultiByteStr
0x180027699  mov     rcx, r15; lpWideCharStr
0x18002769c  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x1800276a1  mov     rbp, rax
0x1800276a4  mov     [rsp+68h+arg_10], rax
0x1800276ac  xor     eax, eax
0x1800276ae  test    rbp, rbp
0x1800276b1  jnz     short loc_1800276BE
0x1800276b3  lea     ebx, [rbp+8]
0x1800276b6  mov     r14b, al
0x1800276b9  jmp     loc_180027806
0x1800276be  lea     ebx, ds:2[rbx*2]
0x1800276c5  inc     r14
0x1800276c8  cmp     [r14+rbp], al
0x1800276cc  jnz     short loc_1800276C5
0x1800276ce  inc     r14d
0x1800276d1  jmp     short loc_1800276D9
0x1800276d3  xor     r14d, r14d
0x1800276d6  mov     ebp, r14d
0x1800276d9  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800276dc  call    ?NlFreeDnsDomainDomainInfo@@YAXPEAU_DOMAIN_INFO@@@Z; NlFreeDnsDomainDomainInfo(_DOMAIN_INFO *)
0x1800276e1  test    ebx, ebx
0x1800276e3  jz      short loc_18002775F
0x1800276e5  lea     edx, [r14+rbx]; uBytes
0x1800276e9  xor     ecx, ecx; uFlags
0x1800276eb  call    cs:__imp_LocalAlloc
0x1800276f1  mov     rsi, rax
0x1800276f4  test    rax, rax
0x1800276f7  jnz     short loc_180027706
0x1800276f9  call    cs:__imp_GetLastError
0x1800276ff  mov     ebx, eax
0x180027701  jmp     loc_180027585
0x180027706  mov     r8d, ebx; Size
0x180027709  mov     rdx, r15; Src
0x18002770c  mov     rcx, rsi; void *
0x18002770f  mov     r12d, ebx
0x180027712  call    memcpy_0
0x180027717  mov     [rdi+82h], bx
0x18002771e  sub     bx, 2
0x180027722  mov     [rdi+80h], bx
0x180027729  xor     ebx, ebx
0x18002772b  mov     [rdi+90h], rsi
0x180027732  mov     [rdi+88h], rsi
0x180027739  test    r14d, r14d
0x18002773c  jz      short loc_180027785
0x18002773e  lea     rbx, [r12+rsi]
0x180027742  mov     r8d, r14d; Size
0x180027745  mov     rcx, rbx; void *
0x180027748  mov     rdx, rbp; Src
0x18002774b  call    memcpy_0
0x180027750  mov     r12, [rsp+68h+arg_30]
0x180027758  mov     [rdi+98h], rbx
0x18002775f  xor     ebx, ebx
0x180027761  mov     rax, [rsp+68h+arg_20]
0x180027769  mov     r14b, 1
0x18002776c  test    rax, rax
0x18002776f  jz      short loc_180027774
0x180027771  mov     [rax], r14b
0x180027774  mov     rcx, [rdi+0D0h]
0x18002777b  test    r13, r13
0x18002777e  jnz     short loc_18002778F
0x180027780  test    rcx, rcx
0x180027783  jmp     short loc_1800277A5
0x180027785  mov     r12, [rsp+68h+arg_30]
0x18002778d  jmp     short loc_180027761
0x18002778f  test    rcx, rcx
0x180027792  jz      short loc_1800277A7
0x180027794  mov     rax, [r13+0]
0x180027798  cmp     rax, [rcx]
0x18002779b  jnz     short loc_1800277A7
0x18002779d  mov     rax, [r13+8]
0x1800277a1  cmp     rax, [rcx+8]
0x1800277a5  jz      short loc_180027806
0x1800277a7  mov     esi, 400h
0x1800277ac  lea     r8, aSettingDomainG; "Setting Domain GUID to "
0x1800277b3  mov     ecx, esi; unsigned int
0x1800277b5  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800277b8  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800277bd  mov     rdx, r13; Uuid
0x1800277c0  mov     ecx, esi; unsigned int
0x1800277c2  call    ?NlpDumpGuid@@YAXKPEAU_GUID@@@Z; NlpDumpGuid(ulong,_GUID *)
0x1800277c7  lea     rdx, asc_180096388; "\n"
0x1800277ce  mov     ecx, esi; unsigned int
0x1800277d0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800277d5  lea     rax, [rdi+0C0h]
0x1800277dc  test    r13, r13
0x1800277df  jz      short loc_1800277EC
0x1800277e1  movups  xmm0, xmmword ptr [r13+0]
0x1800277e6  movdqu  xmmword ptr [rax], xmm0
0x1800277ea  jmp     short loc_1800277F5
0x1800277ec  xorps   xmm0, xmm0
0x1800277ef  movups  xmmword ptr [rax], xmm0
0x1800277f2  mov     rax, rbx
0x1800277f5  mov     [rdi+0D0h], rax
0x1800277fc  test    r12, r12
0x1800277ff  jz      short loc_180027806
0x180027801  mov     byte ptr [r12], 1
0x180027806  lea     rcx, [rdi+190h]; CriticalSection
0x18002780d  call    cs:__imp_RtlLeaveCriticalSection
0x180027813  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002781a  call    cs:__imp_RtlLeaveCriticalSection
0x180027820  mov     rax, [rsp+68h+arg_10]
0x180027828  test    rax, rax
0x18002782b  jz      short loc_180027835
0x18002782d  mov     rcx, rax
0x180027830  call    NetpMemoryFree
0x180027835  test    r14b, r14b
0x180027838  jz      short loc_180027844
0x18002783a  xor     edx, edx; void *
0x18002783c  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18002783f  call    ?NlSetDomainForestRoot@@YAKPEAU_DOMAIN_INFO@@PEAX@Z; NlSetDomainForestRoot(_DOMAIN_INFO *,void *)
0x180027844  mov     eax, ebx
0x180027846  mov     rbx, [rsp+68h+arg_8]
0x18002784b  add     rsp, 30h
0x18002784f  pop     r15
0x180027851  pop     r14
0x180027853  pop     r13
0x180027855  pop     r12
0x180027857  pop     rdi
0x180027858  pop     rsi
0x180027859  pop     rbp
0x18002785a  retn
```
