# NlInsertServerSession(_DOMAIN_INFO *,ushort *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,ulong,ulong,void *,ulong,ulong,ulong,_NL_TRANSPORT *,_NETLOGON_SESSION_KEY *,_CYPHER_BLOCK *,ushort const *,ushort const *,ushort const *,ACCOUNT_TYPE,ulong)

- ea: `0x1800541ac`
- end: `0x18005491b`
- name: `?NlInsertServerSession@@YAJPEAU_DOMAIN_INFO@@PEAG1W4_NETLOGON_SECURE_CHANNEL_TYPE@@KKKPEAXKKKPEAU_NL_TRANSPORT@@PEAU_NETLOGON_SESSION_KEY@@PEAU_CYPHER_BLOCK@@PEBG77W4ACCOUNT_TYPE@@K@Z`
- size: `1903`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005d780`
- `0x18005e190`

## callees

- `0x180003200`
- `0x180003670`
- `0x180007278`
- `0x18000bcec`
- `0x18000d710`
- `0x18000ed34`
- `0x1800395e8`
- `0x180050ca0`
- `0x18005378c`
- `0x180053920`
- `0x180053948`
- `0x1800541ac`
- `0x1800549c8`
- `0x180055ef0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800542f2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800542f2`
- `ntdll!RtlInitUnicodeStringEx` at `0x180054220`
- `ntdll!RtlInitUnicodeStringEx` at `0x180054220`
- `ntdll!RtlEqualUnicodeString` at `0x1800544b4`
- `ntdll!RtlEqualUnicodeString` at `0x1800544b4`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800544de`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800544de`
- `ntdll!RtlLeaveCriticalSection` at `0x1800548e7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800548e7`
- `ntdll!RtlEnterCriticalSection` at `0x1800541fa`
- `ntdll!RtlEnterCriticalSection` at `0x1800541fa`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x1800545dd`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x1800545dd`
- `ntdll!RtlFreeUnicodeString` at `0x1800548f1`
- `ntdll!RtlFreeUnicodeString` at `0x1800548f1`
- `ntdll!RtlInitUnicodeString` at `0x180054206`
- `ntdll!RtlInitUnicodeString` at `0x180054206`
- `CRYPTBASE!SystemFunction036` at `0x1800548c2`
- `CRYPTBASE!SystemFunction036` at `0x1800548c2`

## string_xrefs

- `0x1800543bb`: `onecore\ds\netapi\svcdlls\logonsrv\server\srvsess.cxx`
- `0x1800543f7`: `onecore\ds\netapi\svcdlls\logonsrv\server\srvsess.cxx`
- `0x18005437f`: `We were expecting an Os, Build and Service Pack field but we didn't get one\n`

## pseudocode

```c
__int64 __fastcall NlInsertServerSession(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        __int16 a5,
        int a6,
        int a7,
        PSID SourceSid,
        int a9,
        int a10,
        int a11,
        __int64 a12,
        _OWORD *a13,
        _QWORD *a14,
        wchar_t *Str,
        unsigned __int16 *a16,
        unsigned __int16 *a17,
        int a18,
        int a19)
{
  unsigned __int16 *v21; // rsi
  NTSTATUS TdoNameHashVal; // ebx
  NTSTATUS inited; // eax
  __int64 v25; // rdi
  wchar_t *v26; // rax
  __int64 v27; // r13
  unsigned int v28; // ebx
  __int64 v29; // rsi
  __int64 v30; // r11
  int v31; // eax
  char *v32; // r9
  int v33; // r13d
  struct _SERVER_SESSION *NamedServerSession; // rax
  struct _SERVER_SESSION *v35; // rsi
  int v36; // edx
  unsigned int v37; // ebx
  _QWORD *v38; // rdx
  int v39; // eax
  unsigned int v40; // ebx
  struct _SERVER_SESSION *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  _QWORD *v45; // rcx
  unsigned __int16 *v46; // rbx
  __int64 v47; // rdi
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  _QWORD *v51; // rcx
  __int64 v52; // r8
  __int64 v53; // rcx
  unsigned __int16 v54; // ax
  unsigned int v55; // edx
  unsigned __int16 *v56; // rbx
  unsigned __int16 v57; // ax
  PSID v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rax
  int v61; // eax
  __int16 v62; // di
  _QWORD *v63; // rbx
  _OWORD *v64; // rcx
  ULONG ResultSize; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v67; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v68; // [rsp+38h] [rbp-48h]
  __int64 v69; // [rsp+40h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-38h] BYREF
  UNICODE_STRING UniSource; // [rsp+58h] [rbp-28h] BYREF
  const wchar_t *v72; // [rsp+68h] [rbp-18h]
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+70h] [rbp-10h]
  unsigned int v74; // [rsp+C0h] [rbp+40h] BYREF
  unsigned __int16 *Src; // [rsp+D0h] [rbp+50h]
  unsigned __int8 v76; // [rsp+D8h] [rbp+58h]

  Src = a3;
  v67 = 0;
  v74 = 0;
  CriticalSection = (PRTL_CRITICAL_SECTION)(a1 + 504);
  v21 = a3;
  TdoNameHashVal = 0;
  DestinationString = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 504));
  RtlInitUnicodeString(&DestinationString, 0);
  if ( a4 == 3 )
  {
    UniSource = 0;
    inited = RtlInitUnicodeStringEx(&UniSource, v21);
    TdoNameHashVal = inited;
    if ( inited < 0 )
    {
      NlPrintRoutine(
        0x100u,
        L"NlInsertServerSession: RtlInitUnicodeStringEx on TdoName failed: 0x%08x\n",
        (unsigned int)inited);
      goto LABEL_97;
    }
    TdoNameHashVal = NlGetTdoNameHashVal(&UniSource, &DestinationString, &v67);
    if ( TdoNameHashVal < 0 )
      goto LABEL_97;
  }
  v25 = -1;
  v76 = 0;
  if ( a18 == 1 )
  {
    LODWORD(v69) = 0;
    *(_DWORD *)&UniSource.Length = 0;
    LODWORD(v68) = 0;
  }
  else
  {
    *(_QWORD *)&UniSource.Length = L"Windows";
    UniSource.Buffer = L"Azure Stack HCI";
    v72 = L"Hyper-V Server";
    v26 = Str;
    if ( !Str || !a16 || !a17 )
    {
      NlPrintRoutine(0x200u, L"We were expecting an Os, Build and Service Pack field but we didn't get one\n");
      goto LABEL_97;
    }
    v27 = -1;
    do
      ++v27;
    while ( Str[v27] );
    v68 = v27;
    if ( !(_DWORD)v27 )
      goto LABEL_12;
    v28 = 0;
    while ( !wcsstr(v26, *((const wchar_t **)&UniSource.Length + v28)) )
    {
      v26 = Str;
      if ( ++v28 >= 3 )
        goto LABEL_18;
    }
    v76 = 1;
LABEL_18:
    v29 = -1;
    do
      ++v29;
    while ( a16[v29] );
    v69 = v29;
    if ( !(_DWORD)v29 )
      goto LABEL_12;
    v30 = -1;
    do
      ++v30;
    while ( a17[v30] );
    *(_QWORD *)&UniSource.Length = v30;
    if ( !(_DWORD)v30 )
    {
LABEL_12:
      TdoNameHashVal = -1073741595;
      goto LABEL_97;
    }
    v21 = Src;
  }
  v31 = NlProcessAccountName(v21, &v74, a4);
  TdoNameHashVal = v31;
  if ( v31 < 0 )
  {
    NlPrintRoutine(
      0x100u,
      L"NlInsertServerSession: Error processing account name %wZ with status 0x%08x\n",
      v21,
      (unsigned int)v31);
    goto LABEL_97;
  }
  v33 = a19;
  if ( a4 == 7 )
  {
    if ( !a19 )
    {
      NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\srvsess.cxx", 3033, v32);
      NlPrintRoutine(0x100u, L"NlInsertServerSession: CdcBranchId should not be zero for a new RODC session %wZ\n", v21);
      TdoNameHashVal = -1073741811;
      goto LABEL_97;
    }
  }
  else if ( a19 )
  {
    NlAssertFailed("CdcBranchId == 0", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\srvsess.cxx", 3042, v32);
  }
  NamedServerSession = NlFindNamedServerSession((struct _DOMAIN_INFO *)a1, a2);
  v35 = NamedServerSession;
  if ( !NamedServerSession )
  {
    v37 = v74;
    goto LABEL_58;
  }
  v36 = *((_DWORD *)NamedServerSession + 8);
  if ( (unsigned int)(v36 - 3) <= 1 )
  {
    if ( a4 - 3 > 1 )
    {
      NlPrintRoutine(
        0x100u,
        L"NlInsertServerSession: Failing to insert new session for (%ws) due to existing trust session\n",
        a2);
      goto LABEL_45;
    }
LABEL_38:
    if ( (unsigned int)(v36 - 3) > 1 )
      goto LABEL_39;
    if ( a4 == 3
      && (v36 != 3 || !RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)NamedServerSession + 8, 0)) )
    {
      goto LABEL_40;
    }
    goto LABEL_49;
  }
  if ( a4 == 3 )
  {
LABEL_39:
    NlPrintRoutine(0x200u, L"NlInsertServerSession: deleting existing session for (%ws)\n", a2);
LABEL_40:
    v37 = v74;
    goto LABEL_41;
  }
  if ( a4 == 4 )
    goto LABEL_38;
LABEL_49:
  v37 = v74;
  if ( (unsigned int)RtlCompareUnicodeStrings(
                       *((_QWORD *)v35 + 21),
                       (unsigned __int64)*((unsigned __int16 *)v35 + 80) >> 1,
                       Src,
                       v74,
                       1) )
  {
    NlPrintRoutine(0x200u, L"NlInsertServerSession: Account name change.  Deleting existing session for (%ws)\n", a2);
    goto LABEL_41;
  }
  if ( *((_DWORD *)v35 + 57) != v76 )
  {
    NlPrintRoutine(
      0x200u,
      L"NlInsertServerSession: IsMachineOsWindows mismatch. Deleting existin session for (%ws)\n",
      a2);
LABEL_41:
    if ( !NlFreeServerSession(v35) )
    {
      NlPrintRoutine(0x100u, L"NlInsertServerSession: server session cannot be freed %ws\n", a2);
LABEL_45:
      TdoNameHashVal = -1073741790;
      goto LABEL_97;
    }
LABEL_58:
    ResultSize = 0;
    v39 = 240;
    if ( a4 == 3 )
      v39 = DestinationString.Length + 242;
    v40 = v39 + 2 * (v37 + 1);
    if ( a18 != 1 )
      v40 += 2 * (v68 + v69 + *(_DWORD *)&UniSource.Length) + 6;
    v41 = (struct _SERVER_SESSION *)NetpMemoryAllocate(v40);
    v35 = v41;
    if ( !v41 )
      goto LABEL_63;
    memset_0(v41, 0, v40);
    *((_QWORD *)v35 + 7) = a1;
    *((_DWORD *)v35 + 8) = 0;
    do
      ++v25;
    while ( a2[v25] );
    TdoNameHashVal = RtlUpcaseUnicodeToOemN((PCHAR)v35 + 36, 0xFu, &ResultSize, a2, 2 * v25);
    if ( TdoNameHashVal < 0 )
    {
      NetpMemoryFree(v35);
      goto LABEL_97;
    }
    *((_BYTE *)v35 + ResultSize + 36) = 0;
    if ( !*(_QWORD *)(a1 + 552) )
    {
      v42 = NetpMemoryAllocate(2048);
      *(_QWORD *)(a1 + 552) = v42;
      if ( !v42 )
      {
LABEL_70:
        NetpMemoryFree(v35);
LABEL_63:
        TdoNameHashVal = -1073741801;
        goto LABEL_97;
      }
      v43 = 0;
      do
      {
        v44 = v43++;
        v45 = (_QWORD *)(*(_QWORD *)(a1 + 552) + 16 * v44);
        v45[1] = v45;
        *v45 = v45;
      }
      while ( v43 != 128 );
    }
    v46 = (unsigned __int16 *)((char *)v35 + 240);
    if ( a4 == 3 )
    {
      v47 = NlpInitMarshalledUnicodeString(
              DestinationString.Buffer,
              DestinationString.Length,
              0,
              (struct _UNICODE_STRING *)v35 + 8,
              (unsigned __int16 *)v35 + 120);
      if ( !*(_QWORD *)(a1 + 560) )
      {
        v48 = NetpMemoryAllocate(2048);
        *(_QWORD *)(a1 + 560) = v48;
        if ( !v48 )
          goto LABEL_70;
        v49 = 0;
        do
        {
          v50 = v49++;
          v51 = (_QWORD *)(*(_QWORD *)(a1 + 560) + 16 * v50);
          v51[1] = v51;
          *v51 = v51;
        }
        while ( v49 != 128 );
      }
      v52 = *(_QWORD *)(a1 + 560) + 16LL * v67;
      v53 = *(_QWORD *)v52;
      if ( *(_QWORD *)(*(_QWORD *)v52 + 8LL) != v52 )
        goto LABEL_98;
      v46 = (unsigned __int16 *)((char *)v46 + v47);
      *((_QWORD *)v35 + 14) = v53;
      *((_QWORD *)v35 + 15) = v52;
      *(_QWORD *)(v53 + 8) = (char *)v35 + 112;
      *(_QWORD *)v52 = (char *)v35 + 112;
    }
    v54 = NlpInitMarshalledUnicodeString(Src, v74, 1, (struct _UNICODE_STRING *)v35 + 10, v46);
    if ( a18 != 1 )
    {
      v56 = (unsigned __int16 *)((char *)v46
                               + v54
                               + NlpInitMarshalledUnicodeString(
                                   Str,
                                   v68,
                                   1,
                                   (struct _UNICODE_STRING *)v35 + 11,
                                   (unsigned __int16 *)((char *)v46 + v54)));
      v57 = NlpInitMarshalledUnicodeString(a16, v69, 1, (struct _UNICODE_STRING *)v35 + 12, v56);
      NlpInitMarshalledUnicodeString(
        a17,
        UniSource.Length,
        1,
        (struct _UNICODE_STRING *)v35 + 13,
        (unsigned __int16 *)((char *)v56 + v57));
    }
    v58 = SourceSid;
    *((_DWORD *)v35 + 56) = a18;
    *((_DWORD *)v35 + 57) = v76;
    *((_DWORD *)v35 + 58) = v33;
    if ( v58 )
      *((_QWORD *)v35 + 19) = NlpCopySid(v58);
    v59 = *(_QWORD *)(a1 + 552) + 16LL * NlGetHashVal((char *)v35 + 36, v55);
    v60 = *(_QWORD *)v59;
    if ( *(_QWORD *)(*(_QWORD *)v59 + 8LL) == v59 )
    {
      *((_QWORD *)v35 + 1) = v59;
      *(_QWORD *)v35 = v60;
      *(_QWORD *)(v60 + 8) = v35;
      *(_QWORD *)v59 = v35;
      v38 = *(_QWORD **)(a1 + 576);
      if ( *v38 == a1 + 568 )
      {
        *((_QWORD *)v35 + 2) = a1 + 568;
        *((_QWORD *)v35 + 3) = v38;
        *v38 = (char *)v35 + 16;
        *(_QWORD *)(a1 + 576) = (char *)v35 + 16;
        goto LABEL_87;
      }
    }
LABEL_98:
    __fastfail(3u);
  }
  if ( a4 == 7 && *((_DWORD *)v35 + 58) != v33 )
  {
    NlPrintRoutine(
      0x200u,
      L"NlInsertServerSession: Cdc branch id change.  Deleting existing session for (%ws) Old:0x%x New:0x%x\n",
      a2);
    goto LABEL_41;
  }
LABEL_87:
  v61 = a6;
  v62 = a5;
  *((_WORD *)v35 + 33) |= a5;
  v63 = a14;
  *((_DWORD *)v35 + 37) = v61;
  *((_DWORD *)v35 + 36) = a7;
  *((_DWORD *)v35 + 13) = a9;
  if ( v63
    || dword_1800F12A4
    && (LOBYTE(v38) = 1,
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_SecureChannelRpcWithKerberos>::GetImpl'::`2'::impl,
          v38),
        (v62 & 0x100) != 0) )
  {
    *((_DWORD *)v35 + 18) = a10;
    *((_DWORD *)v35 + 17) = a11;
    *((_QWORD *)v35 + 10) = a12;
    *((_WORD *)v35 + 32) = 0;
    *((_DWORD *)v35 + 8) = a4;
    *((_WORD *)v35 + 33) = v62;
    if ( v63 )
      *((_QWORD *)v35 + 11) = *v63;
  }
  v64 = (_OWORD *)((char *)v35 + 96);
  if ( a13 )
  {
    *v64 = *a13;
  }
  else if ( !SystemFunction036(v64, 0x10u) )
  {
    NlPrintRoutine(0x100u, L"NlInsertServerSession: RtlGenRandom failed for (%ws)\n", a2);
  }
  TdoNameHashVal = 0;
LABEL_97:
  RtlLeaveCriticalSection(CriticalSection);
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)TdoNameHashVal;
}

```

## disassembly

```asm
0x1800541ac  mov     [rsp-38h+arg_8], rbx
0x1800541b1  mov     [rsp-38h+Src], r8
0x1800541b6  push    rbp
0x1800541b7  push    rsi
0x1800541b8  push    rdi
0x1800541b9  push    r12
0x1800541bb  push    r13
0x1800541bd  push    r14
0x1800541bf  push    r15
0x1800541c1  mov     rbp, rsp
0x1800541c4  sub     rsp, 80h
0x1800541cb  lea     rax, [rcx+1F8h]
0x1800541d2  xor     r13d, r13d
0x1800541d5  mov     r15, rcx
0x1800541d8  mov     [rbp+var_4C], r13d
0x1800541dc  xorps   xmm0, xmm0
0x1800541df  mov     [rbp+arg_0], r13d
0x1800541e3  mov     rcx, rax; CriticalSection
0x1800541e6  mov     [rbp+CriticalSection], rax
0x1800541ea  mov     r14d, r9d
0x1800541ed  mov     rsi, r8
0x1800541f0  mov     r12, rdx
0x1800541f3  mov     ebx, r13d
0x1800541f6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800541fa  call    cs:__imp_RtlEnterCriticalSection
0x180054200  xor     edx, edx; SourceString
0x180054202  lea     rcx, [rbp+DestinationString]; DestinationString
0x180054206  call    cs:__imp_RtlInitUnicodeString
0x18005420c  cmp     r14d, 3
0x180054210  jnz     short loc_180054260
0x180054212  xorps   xmm0, xmm0
0x180054215  lea     rcx, [rbp+UniSource]; DestinationString
0x180054219  mov     rdx, rsi; SourceString
0x18005421c  movups  xmmword ptr [rbp+UniSource.Length], xmm0
0x180054220  call    cs:__imp_RtlInitUnicodeStringEx
0x180054226  mov     ebx, eax
0x180054228  test    eax, eax
0x18005422a  jns     short loc_180054245
0x18005422c  mov     r8d, eax
0x18005422f  lea     rdx, aNlinsertserver_2; "NlInsertServerSession: RtlInitUnicodeSt"...
0x180054236  mov     ecx, 100h; unsigned int
0x18005423b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054240  jmp     loc_1800548E3
0x180054245  lea     r8, [rbp+var_4C]; unsigned int *
0x180054249  lea     rdx, [rbp+DestinationString]; UniDest
0x18005424d  lea     rcx, [rbp+UniSource]; UniSource
0x180054251  call    ?NlGetTdoNameHashVal@@YAJPEAU_UNICODE_STRING@@0PEAK@Z; NlGetTdoNameHashVal(_UNICODE_STRING *,_UNICODE_STRING *,ulong *)
0x180054256  mov     ebx, eax
0x180054258  test    eax, eax
0x18005425a  js      loc_1800548E3
0x180054260  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180054264  mov     [rbp+arg_18], r13b
0x180054268  cmp     [rbp+arg_88], 1
0x18005426f  jz      loc_180054395
0x180054275  lea     rax, aWindows; "Windows"
0x18005427c  mov     qword ptr [rbp+UniSource.Length], rax
0x180054280  lea     rax, aAzureStackHci; "Azure Stack HCI"
0x180054287  mov     [rbp+UniSource.Buffer], rax
0x18005428b  lea     rax, aHyperVServer; "Hyper-V Server"
0x180054292  mov     [rbp+var_18], rax
0x180054296  mov     rax, [rbp+Str]
0x18005429d  test    rax, rax
0x1800542a0  jz      loc_18005437F
0x1800542a6  cmp     [rbp+arg_78], r13
0x1800542ad  jz      loc_18005437F
0x1800542b3  cmp     [rbp+arg_80], r13
0x1800542ba  jz      loc_18005437F
0x1800542c0  mov     r13, rdi
0x1800542c3  xor     ecx, ecx
0x1800542c5  inc     r13
0x1800542c8  cmp     [rax+r13*2], cx
0x1800542cd  jnz     short loc_1800542C5
0x1800542cf  mov     [rbp+var_48], r13
0x1800542d3  test    r13d, r13d
0x1800542d6  jnz     short loc_1800542E2
0x1800542d8  mov     ebx, 0C00000E5h
0x1800542dd  jmp     loc_1800548E3
0x1800542e2  xor     r13d, r13d
0x1800542e5  mov     ebx, r13d
0x1800542e8  mov     edx, ebx
0x1800542ea  mov     rcx, rax; Str
0x1800542ed  mov     rdx, qword ptr [rbp+rdx*8+UniSource.Length]; SubStr
0x1800542f2  call    cs:__imp_wcsstr
0x1800542f8  test    rax, rax
0x1800542fb  jnz     short loc_18005430D
0x1800542fd  mov     rax, [rbp+Str]
0x180054304  inc     ebx
0x180054306  cmp     ebx, 3
0x180054309  jb      short loc_1800542E8
0x18005430b  jmp     short loc_180054311
0x18005430d  mov     [rbp+arg_18], 1
0x180054311  mov     rax, [rbp+arg_78]
0x180054318  mov     rsi, rdi
0x18005431b  inc     rsi
0x18005431e  cmp     [rax+rsi*2], r13w
0x180054323  jnz     short loc_18005431B
0x180054325  mov     [rbp+var_40], rsi
0x180054329  test    esi, esi
0x18005432b  jz      short loc_1800542D8
0x18005432d  mov     rax, [rbp+arg_80]
0x180054334  mov     r11, rdi
0x180054337  inc     r11
0x18005433a  cmp     [rax+r11*2], r13w
0x18005433f  jnz     short loc_180054337
0x180054341  mov     qword ptr [rbp+UniSource.Length], r11
0x180054345  test    r11d, r11d
0x180054348  jz      short loc_1800542D8
0x18005434a  mov     rsi, [rbp+Src]
0x18005434e  mov     r8d, r14d
0x180054351  lea     rdx, [rbp+arg_0]
0x180054355  mov     rcx, rsi
0x180054358  call    ?NlProcessAccountName@@YAJPEAGPEAKW4_NETLOGON_SECURE_CHANNEL_TYPE@@@Z; NlProcessAccountName(ushort *,ulong *,_NETLOGON_SECURE_CHANNEL_TYPE)
0x18005435d  mov     ebx, eax
0x18005435f  test    eax, eax
0x180054361  jns     short loc_1800543A3
0x180054363  mov     r9d, eax
0x180054366  lea     rdx, aNlinsertserver_4; "NlInsertServerSession: Error processing"...
0x18005436d  mov     r8, rsi
0x180054370  mov     ecx, 100h; unsigned int
0x180054375  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005437a  jmp     loc_1800548E3
0x18005437f  lea     rdx, aWeWereExpectin; "We were expecting an Os, Build and Serv"...
0x180054386  mov     ecx, 200h; unsigned int
0x18005438b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054390  jmp     loc_1800548E3
0x180054395  mov     dword ptr [rbp+var_40], r13d
0x180054399  mov     dword ptr [rbp+UniSource.Length], r13d
0x18005439d  mov     dword ptr [rbp+var_48], r13d
0x1800543a1  jmp     short loc_18005434E
0x1800543a3  mov     r13d, [rbp+arg_90]
0x1800543aa  cmp     r14d, 7
0x1800543ae  jnz     short loc_1800543EC
0x1800543b0  test    r13d, r13d
0x1800543b3  jnz     short loc_18005440A
0x1800543b5  mov     r8d, 0BD9h; unsigned int
0x1800543bb  lea     rdx, aOnecoreDsNetap_2; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800543c2  lea     rcx, aFalse; "FALSE"
0x1800543c9  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800543ce  mov     r8, rsi
0x1800543d1  lea     rdx, aNlinsertserver_6; "NlInsertServerSession: CdcBranchId shou"...
0x1800543d8  mov     ecx, 100h; unsigned int
0x1800543dd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800543e2  mov     ebx, 0C000000Dh
0x1800543e7  jmp     loc_1800548E3
0x1800543ec  test    r13d, r13d
0x1800543ef  jz      short loc_18005440A
0x1800543f1  mov     r8d, 0BE2h; unsigned int
0x1800543f7  lea     rdx, aOnecoreDsNetap_2; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800543fe  lea     rcx, aCdcbranchid0; "CdcBranchId == 0"
0x180054405  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005440a  mov     rdx, r12; unsigned __int16 *
0x18005440d  mov     rcx, r15; struct _DOMAIN_INFO *
0x180054410  call    ?NlFindNamedServerSession@@YAPEAU_SERVER_SESSION@@PEAU_DOMAIN_INFO@@PEAG@Z; NlFindNamedServerSession(_DOMAIN_INFO *,ushort *)
0x180054415  mov     rsi, rax
0x180054418  test    rax, rax
0x18005441b  jz      loc_18005454E
0x180054421  mov     edx, [rax+20h]
0x180054424  lea     ecx, [rdx-3]
0x180054427  cmp     ecx, 1
0x18005442a  jbe     short loc_180054474
0x18005442c  cmp     r14d, 3
0x180054430  jz      short loc_180054444
0x180054432  cmp     r14d, 4
0x180054436  jnz     loc_1800544BE
0x18005443c  lea     eax, [rdx-3]
0x18005443f  cmp     eax, 1
0x180054442  jbe     short loc_18005449B
0x180054444  mov     r8, r12
0x180054447  lea     rdx, aNlinsertserver_0; "NlInsertServerSession: deleting existin"...
0x18005444e  mov     ecx, 200h; unsigned int
0x180054453  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054458  mov     ebx, [rbp+arg_0]
0x18005445b  mov     rcx, rsi; struct _SERVER_SESSION *
0x18005445e  call    ?NlFreeServerSession@@YAEPEAU_SERVER_SESSION@@@Z; NlFreeServerSession(_SERVER_SESSION *)
0x180054463  test    al, al
0x180054465  jnz     loc_180054551
0x18005446b  lea     rdx, aNlinsertserver_5; "NlInsertServerSession: server session c"...
0x180054472  jmp     short loc_180054484
0x180054474  lea     eax, [r14-3]
0x180054478  cmp     eax, 1
0x18005447b  jbe     short loc_18005443C
0x18005447d  lea     rdx, aNlinsertserver_8; "NlInsertServerSession: Failing to inser"...
0x180054484  mov     r8, r12
0x180054487  mov     ecx, 100h; unsigned int
0x18005448c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054491  mov     ebx, 0C0000022h
0x180054496  jmp     loc_1800548E3
0x18005449b  cmp     r14d, 3
0x18005449f  jnz     short loc_1800544BE
0x1800544a1  cmp     edx, r14d
0x1800544a4  jnz     short loc_180054458
0x1800544a6  lea     rdx, [rsi+80h]; String2
0x1800544ad  xor     r8d, r8d; CaseInsensitive
0x1800544b0  lea     rcx, [rbp+DestinationString]; String1
0x1800544b4  call    cs:__imp_RtlEqualUnicodeString
0x1800544ba  test    al, al
0x1800544bc  jz      short loc_180054458
0x1800544be  movzx   edx, word ptr [rsi+0A0h]
0x1800544c5  mov     ebx, [rbp+arg_0]
0x1800544c8  mov     r8, [rbp+Src]
0x1800544cc  mov     r9d, ebx
0x1800544cf  mov     rcx, [rsi+0A8h]
0x1800544d6  shr     rdx, 1
0x1800544d9  mov     byte ptr [rsp+80h+UnicodeSize], 1
0x1800544de  call    cs:__imp_RtlCompareUnicodeStrings
0x1800544e4  test    eax, eax
0x1800544e6  jz      short loc_1800544F1
0x1800544e8  lea     rdx, aNlinsertserver_7; "NlInsertServerSession: Account name cha"...
0x1800544ef  jmp     short loc_180054504
0x1800544f1  movzx   eax, [rbp+arg_18]
0x1800544f5  cmp     [rsi+0E4h], eax
0x1800544fb  jz      short loc_180054516
0x1800544fd  lea     rdx, aNlinsertserver_3; "NlInsertServerSession: IsMachineOsWindo"...
0x180054504  mov     r8, r12
0x180054507  mov     ecx, 200h; unsigned int
0x18005450c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054511  jmp     loc_18005445B
0x180054516  cmp     r14d, 7
0x18005451a  jnz     loc_180054820
0x180054520  mov     r9d, [rsi+0E8h]
0x180054527  cmp     r9d, r13d
0x18005452a  jz      loc_180054820
0x180054530  mov     r8, r12
0x180054533  mov     [rsp+80h+UnicodeSize], r13d
0x180054538  lea     rdx, aNlinsertserver; "NlInsertServerSession: Cdc branch id ch"...
0x18005453f  mov     ecx, 200h; unsigned int
0x180054544  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054549  jmp     loc_18005445B
0x18005454e  mov     ebx, [rbp+arg_0]
0x180054551  mov     [rbp+ResultSize], 0
0x180054558  mov     eax, 0F0h
0x18005455d  cmp     r14d, 3
0x180054561  jnz     short loc_18005456C
0x180054563  movzx   eax, [rbp+DestinationString.Length]
0x180054567  add     eax, 0F2h
0x18005456c  inc     ebx
0x18005456e  cmp     [rbp+arg_88], 1
0x180054575  lea     ebx, [rax+rbx*2]
0x180054578  jz      short loc_18005458D
0x18005457a  mov     rax, qword ptr [rbp+UniSource.Length]
0x18005457e  mov     rcx, [rbp+var_40]
0x180054582  add     eax, ecx
0x180054584  add     eax, dword ptr [rbp+var_48]
0x180054587  lea     ebx, [rbx+rax*2]
0x18005458a  add     ebx, 6
0x18005458d  mov     ecx, ebx
0x18005458f  call    NetpMemoryAllocate
0x180054594  mov     rsi, rax
0x180054597  test    rax, rax
0x18005459a  jnz     short loc_1800545A6
0x18005459c  mov     ebx, 0C0000017h
0x1800545a1  jmp     loc_1800548E3
0x1800545a6  mov     r8d, ebx; Size
0x1800545a9  xor     edx, edx; Val
0x1800545ab  mov     rcx, rsi; void *
0x1800545ae  call    memset_0
0x1800545b3  xor     eax, eax
0x1800545b5  mov     [rsi+38h], r15
0x1800545b9  mov     [rsi+20h], eax
0x1800545bc  inc     rdi
0x1800545bf  cmp     [r12+rdi*2], ax
0x1800545c4  jnz     short loc_1800545BC
0x1800545c6  lea     eax, [rdi+rdi]
0x1800545c9  mov     r9, r12; UnicodeString
0x1800545cc  lea     rcx, [rsi+24h]; OemString
0x1800545d0  mov     [rsp+80h+UnicodeSize], eax; UnicodeSize
0x1800545d4  lea     r8, [rbp+ResultSize]; ResultSize
0x1800545d8  mov     edx, 0Fh; OemSize
0x1800545dd  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x1800545e3  xor     edi, edi
0x1800545e5  mov     ebx, eax
0x1800545e7  test    eax, eax
0x1800545e9  jns     short loc_1800545F8
0x1800545eb  mov     rcx, rsi
0x1800545ee  call    NetpMemoryFree
0x1800545f3  jmp     loc_1800548E3
0x1800545f8  mov     eax, [rbp+ResultSize]
0x1800545fb  mov     [rax+rsi+24h], dil
0x180054600  cmp     [r15+228h], rdi
0x180054607  jnz     short loc_180054650
0x180054609  mov     ecx, 800h
0x18005460e  call    NetpMemoryAllocate
0x180054613  mov     [r15+228h], rax
0x18005461a  test    rax, rax
0x18005461d  jnz     short loc_18005462C
0x18005461f  mov     rcx, rsi
0x180054622  call    NetpMemoryFree
0x180054627  jmp     loc_18005459C
0x18005462c  mov     rdx, rdi
0x18005462f  mov     rcx, rdx
0x180054632  inc     rdx
0x180054635  shl     rcx, 4
0x180054639  add     rcx, [r15+228h]
0x180054640  mov     [rcx+8], rcx
0x180054644  mov     [rcx], rcx
0x180054647  cmp     rdx, 80h
0x18005464e  jnz     short loc_18005462F
0x180054650  lea     rbx, [rsi+0F0h]
0x180054657  cmp     r14d, 3
0x18005465b  jnz     loc_1800546FA
  ... truncated ...
```
