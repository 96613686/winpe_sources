# NlSetDomainNameInDomainInfo(_DOMAIN_INFO *,ushort *,ushort *,_GUID *,uchar *,uchar *,uchar *)

- ea: `0x180028860`
- end: `0x180028c6a`
- name: `?NlSetDomainNameInDomainInfo@@YAKPEAU_DOMAIN_INFO@@PEAG1PEAU_GUID@@PEAE33@Z`
- size: `1034`
- prototype: `unsigned int __usercall@<eax>(struct _DOMAIN_INFO *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, struct _GUID *@<r9>, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025f54`
- `0x180056fd4`
- `0x18006e50c`
- `0x180075b60`

## callees

- `0x1800037f0`
- `0x180007518`
- `0x18000c130`
- `0x18000c440`
- `0x18002751c`
- `0x1800287c0`
- `0x180028860`
- `0x180041b98`
- `0x1800892fc`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028af5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028ae1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028ae1`
- `ntdll!RtlLeaveCriticalSection` at `0x180028c0f`
- `ntdll!RtlLeaveCriticalSection` at `0x180028c22`
- `ntdll!RtlLeaveCriticalSection` at `0x180028c0f`
- `ntdll!RtlLeaveCriticalSection` at `0x180028c22`
- `ntdll!RtlEnterCriticalSection` at `0x1800288c7`
- `ntdll!RtlEnterCriticalSection` at `0x1800288da`
- `ntdll!RtlEnterCriticalSection` at `0x1800288c7`
- `ntdll!RtlEnterCriticalSection` at `0x1800288da`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x18002899d`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x18002899d`
- `ntdll!RtlInitUnicodeString` at `0x180028979`
- `ntdll!RtlInitUnicodeString` at `0x180028979`
- `netutils!NetpwNameCanonicalize` at `0x18002893f`
- `netutils!NetpwNameCanonicalize` at `0x18002893f`
- `netutils!NetpwNameCompare` at `0x180028900`
- `netutils!NetpwNameCompare` at `0x180028900`
- `DNSAPI!DnsValidateName_W` at `0x180028a51`
- `DNSAPI!DnsValidateName_W` at `0x180028a51`

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
0x180028860  mov     [rsp+arg_8], rbx
0x180028865  push    rbp
0x180028866  push    rsi
0x180028867  push    rdi
0x180028868  push    r12
0x18002886a  push    r13
0x18002886c  push    r14
0x18002886e  push    r15
0x180028870  sub     rsp, 30h
0x180028874  mov     rax, [rsp+68h+arg_20]
0x18002887c  xor     ebx, ebx
0x18002887e  mov     [rsp+68h+arg_10], rbx
0x180028886  mov     r13, r9
0x180028889  mov     [rsp+68h+arg_0], bl
0x18002888d  mov     rbp, r8
0x180028890  mov     r15, rdx
0x180028893  mov     rdi, rcx
0x180028896  mov     r14b, bl
0x180028899  test    rax, rax
0x18002889c  jz      short loc_1800288A0
0x18002889e  mov     [rax], bl
0x1800288a0  mov     rsi, [rsp+68h+arg_28]
0x1800288a8  test    rsi, rsi
0x1800288ab  jz      short loc_1800288AF
0x1800288ad  mov     [rsi], bl
0x1800288af  mov     r12, [rsp+68h+arg_30]
0x1800288b7  test    r12, r12
0x1800288ba  jz      short loc_1800288C0
0x1800288bc  mov     [r12], bl
0x1800288c0  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800288c7  call    cs:__imp_RtlEnterCriticalSection
0x1800288ce  nop     dword ptr [rax+rax+00h]
0x1800288d3  lea     rcx, [rdi+190h]; CriticalSection
0x1800288da  call    cs:__imp_RtlEnterCriticalSection
0x1800288e1  nop     dword ptr [rax+rax+00h]
0x1800288e6  test    rbp, rbp
0x1800288e9  jz      loc_180028A02
0x1800288ef  xor     r9d, r9d
0x1800288f2  lea     r14, [rdi+48h]
0x1800288f6  mov     rdx, r14
0x1800288f9  mov     rcx, rbp
0x1800288fc  lea     r8d, [r9+6]
0x180028900  call    cs:__imp_NetpwNameCompare
0x180028907  nop     dword ptr [rax+rax+00h]
0x18002890c  test    eax, eax
0x18002890e  jz      loc_1800289FF
0x180028914  mov     r9, rbp
0x180028917  lea     r8, aSettingNetbios; "Setting Netbios domain name to %ws\n"
0x18002891e  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180028921  mov     ecx, 400h; unsigned int
0x180028926  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002892b  mov     r9d, 6
0x180028931  mov     [rsp+68h+UnicodeSize], ebx
0x180028935  mov     rdx, r14
0x180028938  mov     rcx, rbp
0x18002893b  lea     r8d, [r9+1Ah]
0x18002893f  call    cs:__imp_NetpwNameCanonicalize
0x180028946  nop     dword ptr [rax+rax+00h]
0x18002894b  mov     ebx, eax
0x18002894d  test    eax, eax
0x18002894f  jz      short loc_18002896F
0x180028951  mov     r8, rbp
0x180028954  lea     rdx, aWsDomainnameIs; "%ws: DomainName is invalid\n"
0x18002895b  mov     ecx, 100h; unsigned int
0x180028960  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180028965  mov     r14b, [rsp+68h+arg_0]
0x18002896a  jmp     loc_180028C08
0x18002896f  lea     rbx, [rdi+38h]
0x180028973  mov     rdx, r14; SourceString
0x180028976  mov     rcx, rbx; DestinationString
0x180028979  call    cs:__imp_RtlInitUnicodeString
0x180028980  nop     dword ptr [rax+rax+00h]
0x180028985  movzx   eax, word ptr [rbx]
0x180028988  lea     rcx, [rdi+68h]; OemString
0x18002898c  mov     r9, [rdi+40h]; UnicodeString
0x180028990  lea     r8, [rdi+78h]; ResultSize
0x180028994  mov     edx, 0Fh; OemSize
0x180028999  mov     [rsp+68h+UnicodeSize], eax; UnicodeSize
0x18002899d  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x1800289a4  nop     dword ptr [rax+rax+00h]
0x1800289a9  xor     ecx, ecx
0x1800289ab  test    eax, eax
0x1800289ad  jns     short loc_1800289CD
0x1800289af  mov     r9d, eax
0x1800289b2  lea     rdx, aWsUnableToConv; "%ws: Unable to convert Domain name to O"...
0x1800289b9  mov     r8, rbp
0x1800289bc  mov     ecx, 100h; unsigned int
0x1800289c1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800289c6  mov     ebx, 8
0x1800289cb  jmp     short loc_180028965
0x1800289cd  cmp     cs:?NlGlobalMemberWorkstation@@3HA, ecx; int NlGlobalMemberWorkstation
0x1800289d3  mov     eax, [rdi+78h]
0x1800289d6  mov     [rax+rdi+68h], cl
0x1800289da  jz      short loc_1800289E5
0x1800289dc  movups  xmm0, xmmword ptr [rdi+100h]
0x1800289e3  jmp     short loc_1800289E8
0x1800289e5  movups  xmm0, xmmword ptr [rbx]
0x1800289e8  xor     ebx, ebx
0x1800289ea  mov     r14b, cl
0x1800289ed  movdqu  xmmword ptr [rdi+0A8h], xmm0
0x1800289f5  test    rsi, rsi
0x1800289f8  jz      short loc_180028A02
0x1800289fa  mov     byte ptr [rsi], 1
0x1800289fd  jmp     short loc_180028A02
0x1800289ff  mov     r14b, bl
0x180028a02  mov     rdx, [rdi+90h]; unsigned __int16 *
0x180028a09  mov     rcx, r15; unsigned __int16 *
0x180028a0c  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180028a11  test    eax, eax
0x180028a13  jnz     loc_180028B76
0x180028a19  mov     r9, r15
0x180028a1c  lea     r8, aSettingDnsDoma; "Setting DNS domain name to %ws\n"
0x180028a23  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180028a26  mov     ecx, 400h; unsigned int
0x180028a2b  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180028a30  test    r15, r15
0x180028a33  jz      loc_180028AC5
0x180028a39  or      r14, 0FFFFFFFFFFFFFFFFh
0x180028a3d  mov     rbx, r14
0x180028a40  xor     esi, esi
0x180028a42  inc     rbx
0x180028a45  cmp     [r15+rbx*2], si
0x180028a4a  jnz     short loc_180028A42
0x180028a4c  xor     edx, edx; Format
0x180028a4e  mov     rcx, r15; pszName
0x180028a51  call    cs:__imp_DnsValidateName_W
0x180028a58  nop     dword ptr [rax+rax+00h]
0x180028a5d  test    eax, eax
0x180028a5f  jz      short loc_180028A86
0x180028a61  cmp     eax, 2554h
0x180028a66  jz      short loc_180028A75
0x180028a68  mov     ebx, 4BCh
0x180028a6d  mov     r14b, sil
0x180028a70  jmp     loc_180028C08
0x180028a75  lea     rdx, aDnsdomainnameC; "DnsDomainName contains underscore\n"
0x180028a7c  mov     ecx, 2; unsigned int
0x180028a81  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180028a86  xor     r8d, r8d; int
0x180028a89  xor     edx, edx; lpMultiByteStr
0x180028a8b  mov     rcx, r15; lpWideCharStr
0x180028a8e  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180028a93  mov     rbp, rax
0x180028a96  mov     [rsp+68h+arg_10], rax
0x180028a9e  xor     eax, eax
0x180028aa0  test    rbp, rbp
0x180028aa3  jnz     short loc_180028AB0
0x180028aa5  lea     ebx, [rbp+8]
0x180028aa8  mov     r14b, al
0x180028aab  jmp     loc_180028C08
0x180028ab0  lea     ebx, ds:2[rbx*2]
0x180028ab7  inc     r14
0x180028aba  cmp     [r14+rbp], al
0x180028abe  jnz     short loc_180028AB7
0x180028ac0  inc     r14d
0x180028ac3  jmp     short loc_180028ACB
0x180028ac5  xor     r14d, r14d
0x180028ac8  mov     ebp, r14d
0x180028acb  mov     rcx, rdi; struct _DOMAIN_INFO *
0x180028ace  call    ?NlFreeDnsDomainDomainInfo@@YAXPEAU_DOMAIN_INFO@@@Z; NlFreeDnsDomainDomainInfo(_DOMAIN_INFO *)
0x180028ad3  test    ebx, ebx
0x180028ad5  jz      loc_180028B61
0x180028adb  lea     edx, [r14+rbx]; uBytes
0x180028adf  xor     ecx, ecx; uFlags
0x180028ae1  call    cs:__imp_LocalAlloc
0x180028ae8  nop     dword ptr [rax+rax+00h]
0x180028aed  mov     rsi, rax
0x180028af0  test    rax, rax
0x180028af3  jnz     short loc_180028B08
0x180028af5  call    cs:__imp_GetLastError
0x180028afc  nop     dword ptr [rax+rax+00h]
0x180028b01  mov     ebx, eax
0x180028b03  jmp     loc_180028965
0x180028b08  mov     r8d, ebx; Size
0x180028b0b  mov     rdx, r15; Src
0x180028b0e  mov     rcx, rsi; void *
0x180028b11  mov     r12d, ebx
0x180028b14  call    memcpy_0
0x180028b19  mov     [rdi+82h], bx
0x180028b20  sub     bx, 2
0x180028b24  mov     [rdi+80h], bx
0x180028b2b  xor     ebx, ebx
0x180028b2d  mov     [rdi+90h], rsi
0x180028b34  mov     [rdi+88h], rsi
0x180028b3b  test    r14d, r14d
0x180028b3e  jz      short loc_180028B87
0x180028b40  lea     rbx, [r12+rsi]
0x180028b44  mov     r8d, r14d; Size
0x180028b47  mov     rcx, rbx; void *
0x180028b4a  mov     rdx, rbp; Src
0x180028b4d  call    memcpy_0
0x180028b52  mov     r12, [rsp+68h+arg_30]
0x180028b5a  mov     [rdi+98h], rbx
0x180028b61  xor     ebx, ebx
0x180028b63  mov     rax, [rsp+68h+arg_20]
0x180028b6b  mov     r14b, 1
0x180028b6e  test    rax, rax
0x180028b71  jz      short loc_180028B76
0x180028b73  mov     [rax], r14b
0x180028b76  mov     rcx, [rdi+0D0h]
0x180028b7d  test    r13, r13
0x180028b80  jnz     short loc_180028B91
0x180028b82  test    rcx, rcx
0x180028b85  jmp     short loc_180028BA7
0x180028b87  mov     r12, [rsp+68h+arg_30]
0x180028b8f  jmp     short loc_180028B63
0x180028b91  test    rcx, rcx
0x180028b94  jz      short loc_180028BA9
0x180028b96  mov     rax, [r13+0]
0x180028b9a  cmp     rax, [rcx]
0x180028b9d  jnz     short loc_180028BA9
0x180028b9f  mov     rax, [r13+8]
0x180028ba3  cmp     rax, [rcx+8]
0x180028ba7  jz      short loc_180028C08
0x180028ba9  mov     esi, 400h
0x180028bae  lea     r8, aSettingDomainG; "Setting Domain GUID to "
0x180028bb5  mov     ecx, esi; unsigned int
0x180028bb7  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180028bba  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180028bbf  mov     rdx, r13; Uuid
0x180028bc2  mov     ecx, esi; unsigned int
0x180028bc4  call    ?NlpDumpGuid@@YAXKPEAU_GUID@@@Z; NlpDumpGuid(ulong,_GUID *)
0x180028bc9  lea     rdx, asc_18009D398; "\n"
0x180028bd0  mov     ecx, esi; unsigned int
0x180028bd2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180028bd7  lea     rax, [rdi+0C0h]
0x180028bde  test    r13, r13
0x180028be1  jz      short loc_180028BEE
0x180028be3  movups  xmm0, xmmword ptr [r13+0]
0x180028be8  movdqu  xmmword ptr [rax], xmm0
0x180028bec  jmp     short loc_180028BF7
0x180028bee  xorps   xmm0, xmm0
0x180028bf1  movups  xmmword ptr [rax], xmm0
0x180028bf4  mov     rax, rbx
0x180028bf7  mov     [rdi+0D0h], rax
0x180028bfe  test    r12, r12
0x180028c01  jz      short loc_180028C08
0x180028c03  mov     byte ptr [r12], 1
0x180028c08  lea     rcx, [rdi+190h]; CriticalSection
0x180028c0f  call    cs:__imp_RtlLeaveCriticalSection
0x180028c16  nop     dword ptr [rax+rax+00h]
0x180028c1b  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028c22  call    cs:__imp_RtlLeaveCriticalSection
0x180028c29  nop     dword ptr [rax+rax+00h]
0x180028c2e  mov     rax, [rsp+68h+arg_10]
0x180028c36  test    rax, rax
0x180028c39  jz      short loc_180028C43
0x180028c3b  mov     rcx, rax
0x180028c3e  call    NetpMemoryFree
0x180028c43  test    r14b, r14b
0x180028c46  jz      short loc_180028C52
0x180028c48  xor     edx, edx; void *
0x180028c4a  mov     rcx, rdi; struct _DOMAIN_INFO *
0x180028c4d  call    ?NlSetDomainForestRoot@@YAKPEAU_DOMAIN_INFO@@PEAX@Z; NlSetDomainForestRoot(_DOMAIN_INFO *,void *)
0x180028c52  mov     eax, ebx
0x180028c54  mov     rbx, [rsp+68h+arg_8]
0x180028c59  add     rsp, 30h
0x180028c5d  pop     r15
0x180028c5f  pop     r14
0x180028c61  pop     r13
0x180028c63  pop     r12
0x180028c65  pop     rdi
0x180028c66  pop     rsi
0x180028c67  pop     rbp
0x180028c68  retn
```
