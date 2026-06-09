# NlInsertServerSession(_DOMAIN_INFO *,ushort *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,ulong,ulong,void *,ulong,ulong,ulong,_NL_TRANSPORT *,_NETLOGON_SESSION_KEY *,_CYPHER_BLOCK *,ushort const *,ushort const *,ushort const *,ACCOUNT_TYPE,ulong)

- ea: `0x180057c4c`
- end: `0x1800583f8`
- name: `?NlInsertServerSession@@YAJPEAU_DOMAIN_INFO@@PEAG1W4_NETLOGON_SECURE_CHANNEL_TYPE@@KKKPEAXKKKPEAU_NL_TRANSPORT@@PEAU_NETLOGON_SESSION_KEY@@PEAU_CYPHER_BLOCK@@PEBG77W4ACCOUNT_TYPE@@K@Z`
- size: `1964`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180061b40`
- `0x180062590`

## callees

- `0x180003320`
- `0x1800037f0`
- `0x180007518`
- `0x18000c38c`
- `0x18000dd00`
- `0x18000f3e4`
- `0x18003b8d4`
- `0x18005448c`
- `0x180057174`
- `0x180057320`
- `0x180057348`
- `0x180057c4c`
- `0x1800584b0`
- `0x180059c48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180057da4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180057da4`
- `ntdll!RtlInitUnicodeStringEx` at `0x180057ccc`
- `ntdll!RtlInitUnicodeStringEx` at `0x180057ccc`
- `ntdll!RtlEqualUnicodeString` at `0x180057f6c`
- `ntdll!RtlEqualUnicodeString` at `0x180057f6c`
- `ntdll!RtlCompareUnicodeStrings` at `0x180057f9c`
- `ntdll!RtlCompareUnicodeStrings` at `0x180057f9c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800583b7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800583b7`
- `ntdll!RtlEnterCriticalSection` at `0x180057c9a`
- `ntdll!RtlEnterCriticalSection` at `0x180057c9a`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x1800580a1`
- `ntdll!RtlUpcaseUnicodeToOemN` at `0x1800580a1`
- `ntdll!RtlFreeUnicodeString` at `0x1800583c7`
- `ntdll!RtlFreeUnicodeString` at `0x1800583c7`
- `ntdll!RtlInitUnicodeString` at `0x180057cac`
- `ntdll!RtlInitUnicodeString` at `0x180057cac`
- `CRYPTBASE!SystemFunction036` at `0x18005838c`
- `CRYPTBASE!SystemFunction036` at `0x18005838c`

## string_xrefs

- `0x180057e73`: `onecore\ds\netapi\svcdlls\logonsrv\server\srvsess.cxx`
- `0x180057eaf`: `onecore\ds\netapi\svcdlls\logonsrv\server\srvsess.cxx`
- `0x180057e37`: `We were expecting an Os, Build and Service Pack field but we didn't get one\n`

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
      NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\srvsess.cxx", 0xBD9u, v32);
      NlPrintRoutine(0x100u, L"NlInsertServerSession: CdcBranchId should not be zero for a new RODC session %wZ\n", v21);
      TdoNameHashVal = -1073741811;
      goto LABEL_97;
    }
  }
  else if ( a19 )
  {
    NlAssertFailed("CdcBranchId == 0", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\srvsess.cxx", 0xBE2u, v32);
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
    || dword_1800F82A4
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
0x180057c4c  mov     [rsp-38h+arg_8], rbx
0x180057c51  mov     [rsp-38h+Src], r8
0x180057c56  push    rbp
0x180057c57  push    rsi
0x180057c58  push    rdi
0x180057c59  push    r12
0x180057c5b  push    r13
0x180057c5d  push    r14
0x180057c5f  push    r15
0x180057c61  mov     rbp, rsp
0x180057c64  sub     rsp, 80h
0x180057c6b  lea     rax, [rcx+1F8h]
0x180057c72  xor     r13d, r13d
0x180057c75  mov     r15, rcx
0x180057c78  mov     [rbp+var_4C], r13d
0x180057c7c  xorps   xmm0, xmm0
0x180057c7f  mov     [rbp+arg_0], r13d
0x180057c83  mov     rcx, rax; CriticalSection
0x180057c86  mov     [rbp+CriticalSection], rax
0x180057c8a  mov     r14d, r9d
0x180057c8d  mov     rsi, r8
0x180057c90  mov     r12, rdx
0x180057c93  mov     ebx, r13d
0x180057c96  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180057c9a  call    cs:__imp_RtlEnterCriticalSection
0x180057ca1  nop     dword ptr [rax+rax+00h]
0x180057ca6  xor     edx, edx; SourceString
0x180057ca8  lea     rcx, [rbp+DestinationString]; DestinationString
0x180057cac  call    cs:__imp_RtlInitUnicodeString
0x180057cb3  nop     dword ptr [rax+rax+00h]
0x180057cb8  cmp     r14d, 3
0x180057cbc  jnz     short loc_180057D12
0x180057cbe  xorps   xmm0, xmm0
0x180057cc1  lea     rcx, [rbp+UniSource]; DestinationString
0x180057cc5  mov     rdx, rsi; SourceString
0x180057cc8  movups  xmmword ptr [rbp+UniSource.Length], xmm0
0x180057ccc  call    cs:__imp_RtlInitUnicodeStringEx
0x180057cd3  nop     dword ptr [rax+rax+00h]
0x180057cd8  mov     ebx, eax
0x180057cda  test    eax, eax
0x180057cdc  jns     short loc_180057CF7
0x180057cde  mov     r8d, eax
0x180057ce1  lea     rdx, aNlinsertserver_2; "NlInsertServerSession: RtlInitUnicodeSt"...
0x180057ce8  mov     ecx, 100h; unsigned int
0x180057ced  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057cf2  jmp     loc_1800583B3
0x180057cf7  lea     r8, [rbp+var_4C]; unsigned int *
0x180057cfb  lea     rdx, [rbp+DestinationString]; UniDest
0x180057cff  lea     rcx, [rbp+UniSource]; UniSource
0x180057d03  call    ?NlGetTdoNameHashVal@@YAJPEAU_UNICODE_STRING@@0PEAK@Z; NlGetTdoNameHashVal(_UNICODE_STRING *,_UNICODE_STRING *,ulong *)
0x180057d08  mov     ebx, eax
0x180057d0a  test    eax, eax
0x180057d0c  js      loc_1800583B3
0x180057d12  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180057d16  mov     [rbp+arg_18], r13b
0x180057d1a  cmp     [rbp+arg_88], 1
0x180057d21  jz      loc_180057E4D
0x180057d27  lea     rax, aWindows; "Windows"
0x180057d2e  mov     qword ptr [rbp+UniSource.Length], rax
0x180057d32  lea     rax, aAzureStackHci; "Azure Stack HCI"
0x180057d39  mov     [rbp+UniSource.Buffer], rax
0x180057d3d  lea     rax, aHyperVServer; "Hyper-V Server"
0x180057d44  mov     [rbp+var_18], rax
0x180057d48  mov     rax, [rbp+Str]
0x180057d4f  test    rax, rax
0x180057d52  jz      loc_180057E37
0x180057d58  cmp     [rbp+arg_78], r13
0x180057d5f  jz      loc_180057E37
0x180057d65  cmp     [rbp+arg_80], r13
0x180057d6c  jz      loc_180057E37
0x180057d72  mov     r13, rdi
0x180057d75  xor     ecx, ecx
0x180057d77  inc     r13
0x180057d7a  cmp     [rax+r13*2], cx
0x180057d7f  jnz     short loc_180057D77
0x180057d81  mov     [rbp+var_48], r13
0x180057d85  test    r13d, r13d
0x180057d88  jnz     short loc_180057D94
0x180057d8a  mov     ebx, 0C00000E5h
0x180057d8f  jmp     loc_1800583B3
0x180057d94  xor     r13d, r13d
0x180057d97  mov     ebx, r13d
0x180057d9a  mov     edx, ebx
0x180057d9c  mov     rcx, rax; Str
0x180057d9f  mov     rdx, qword ptr [rbp+rdx*8+UniSource.Length]; SubStr
0x180057da4  call    cs:__imp_wcsstr
0x180057dab  nop     dword ptr [rax+rax+00h]
0x180057db0  test    rax, rax
0x180057db3  jnz     short loc_180057DC5
0x180057db5  mov     rax, [rbp+Str]
0x180057dbc  inc     ebx
0x180057dbe  cmp     ebx, 3
0x180057dc1  jb      short loc_180057D9A
0x180057dc3  jmp     short loc_180057DC9
0x180057dc5  mov     [rbp+arg_18], 1
0x180057dc9  mov     rax, [rbp+arg_78]
0x180057dd0  mov     rsi, rdi
0x180057dd3  inc     rsi
0x180057dd6  cmp     [rax+rsi*2], r13w
0x180057ddb  jnz     short loc_180057DD3
0x180057ddd  mov     [rbp+var_40], rsi
0x180057de1  test    esi, esi
0x180057de3  jz      short loc_180057D8A
0x180057de5  mov     rax, [rbp+arg_80]
0x180057dec  mov     r11, rdi
0x180057def  inc     r11
0x180057df2  cmp     [rax+r11*2], r13w
0x180057df7  jnz     short loc_180057DEF
0x180057df9  mov     qword ptr [rbp+UniSource.Length], r11
0x180057dfd  test    r11d, r11d
0x180057e00  jz      short loc_180057D8A
0x180057e02  mov     rsi, [rbp+Src]
0x180057e06  mov     r8d, r14d
0x180057e09  lea     rdx, [rbp+arg_0]
0x180057e0d  mov     rcx, rsi
0x180057e10  call    ?NlProcessAccountName@@YAJPEAGPEAKW4_NETLOGON_SECURE_CHANNEL_TYPE@@@Z; NlProcessAccountName(ushort *,ulong *,_NETLOGON_SECURE_CHANNEL_TYPE)
0x180057e15  mov     ebx, eax
0x180057e17  test    eax, eax
0x180057e19  jns     short loc_180057E5B
0x180057e1b  mov     r9d, eax
0x180057e1e  lea     rdx, aNlinsertserver_4; "NlInsertServerSession: Error processing"...
0x180057e25  mov     r8, rsi
0x180057e28  mov     ecx, 100h; unsigned int
0x180057e2d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057e32  jmp     loc_1800583B3
0x180057e37  lea     rdx, aWeWereExpectin; "We were expecting an Os, Build and Serv"...
0x180057e3e  mov     ecx, 200h; unsigned int
0x180057e43  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057e48  jmp     loc_1800583B3
0x180057e4d  mov     dword ptr [rbp+var_40], r13d
0x180057e51  mov     dword ptr [rbp+UniSource.Length], r13d
0x180057e55  mov     dword ptr [rbp+var_48], r13d
0x180057e59  jmp     short loc_180057E06
0x180057e5b  mov     r13d, [rbp+arg_90]
0x180057e62  cmp     r14d, 7
0x180057e66  jnz     short loc_180057EA4
0x180057e68  test    r13d, r13d
0x180057e6b  jnz     short loc_180057EC2
0x180057e6d  mov     r8d, 0BD9h; unsigned int
0x180057e73  lea     rdx, aOnecoreDsNetap_2; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180057e7a  lea     rcx, aFalse; "FALSE"
0x180057e81  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180057e86  mov     r8, rsi
0x180057e89  lea     rdx, aNlinsertserver_6; "NlInsertServerSession: CdcBranchId shou"...
0x180057e90  mov     ecx, 100h; unsigned int
0x180057e95  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057e9a  mov     ebx, 0C000000Dh
0x180057e9f  jmp     loc_1800583B3
0x180057ea4  test    r13d, r13d
0x180057ea7  jz      short loc_180057EC2
0x180057ea9  mov     r8d, 0BE2h; unsigned int
0x180057eaf  lea     rdx, aOnecoreDsNetap_2; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180057eb6  lea     rcx, aCdcbranchid0; "CdcBranchId == 0"
0x180057ebd  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180057ec2  mov     rdx, r12; unsigned __int16 *
0x180057ec5  mov     rcx, r15; struct _DOMAIN_INFO *
0x180057ec8  call    ?NlFindNamedServerSession@@YAPEAU_SERVER_SESSION@@PEAU_DOMAIN_INFO@@PEAG@Z; NlFindNamedServerSession(_DOMAIN_INFO *,ushort *)
0x180057ecd  mov     rsi, rax
0x180057ed0  test    rax, rax
0x180057ed3  jz      loc_180058012
0x180057ed9  mov     edx, [rax+20h]
0x180057edc  lea     ecx, [rdx-3]
0x180057edf  cmp     ecx, 1
0x180057ee2  jbe     short loc_180057F2C
0x180057ee4  cmp     r14d, 3
0x180057ee8  jz      short loc_180057EFC
0x180057eea  cmp     r14d, 4
0x180057eee  jnz     loc_180057F7C
0x180057ef4  lea     eax, [rdx-3]
0x180057ef7  cmp     eax, 1
0x180057efa  jbe     short loc_180057F53
0x180057efc  mov     r8, r12
0x180057eff  lea     rdx, aNlinsertserver_0; "NlInsertServerSession: deleting existin"...
0x180057f06  mov     ecx, 200h; unsigned int
0x180057f0b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057f10  mov     ebx, [rbp+arg_0]
0x180057f13  mov     rcx, rsi; struct _SERVER_SESSION *
0x180057f16  call    ?NlFreeServerSession@@YAEPEAU_SERVER_SESSION@@@Z; NlFreeServerSession(_SERVER_SESSION *)
0x180057f1b  test    al, al
0x180057f1d  jnz     loc_180058015
0x180057f23  lea     rdx, aNlinsertserver_5; "NlInsertServerSession: server session c"...
0x180057f2a  jmp     short loc_180057F3C
0x180057f2c  lea     eax, [r14-3]
0x180057f30  cmp     eax, 1
0x180057f33  jbe     short loc_180057EF4
0x180057f35  lea     rdx, aNlinsertserver_8; "NlInsertServerSession: Failing to inser"...
0x180057f3c  mov     r8, r12
0x180057f3f  mov     ecx, 100h; unsigned int
0x180057f44  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057f49  mov     ebx, 0C0000022h
0x180057f4e  jmp     loc_1800583B3
0x180057f53  cmp     r14d, 3
0x180057f57  jnz     short loc_180057F7C
0x180057f59  cmp     edx, r14d
0x180057f5c  jnz     short loc_180057F10
0x180057f5e  lea     rdx, [rsi+80h]; String2
0x180057f65  xor     r8d, r8d; CaseInsensitive
0x180057f68  lea     rcx, [rbp+DestinationString]; String1
0x180057f6c  call    cs:__imp_RtlEqualUnicodeString
0x180057f73  nop     dword ptr [rax+rax+00h]
0x180057f78  test    al, al
0x180057f7a  jz      short loc_180057F10
0x180057f7c  movzx   edx, word ptr [rsi+0A0h]
0x180057f83  mov     ebx, [rbp+arg_0]
0x180057f86  mov     r8, [rbp+Src]
0x180057f8a  mov     r9d, ebx
0x180057f8d  mov     rcx, [rsi+0A8h]
0x180057f94  shr     rdx, 1
0x180057f97  mov     byte ptr [rsp+80h+UnicodeSize], 1
0x180057f9c  call    cs:__imp_RtlCompareUnicodeStrings
0x180057fa3  nop     dword ptr [rax+rax+00h]
0x180057fa8  test    eax, eax
0x180057faa  jz      short loc_180057FB5
0x180057fac  lea     rdx, aNlinsertserver_7; "NlInsertServerSession: Account name cha"...
0x180057fb3  jmp     short loc_180057FC8
0x180057fb5  movzx   eax, [rbp+arg_18]
0x180057fb9  cmp     [rsi+0E4h], eax
0x180057fbf  jz      short loc_180057FDA
0x180057fc1  lea     rdx, aNlinsertserver_3; "NlInsertServerSession: IsMachineOsWindo"...
0x180057fc8  mov     r8, r12
0x180057fcb  mov     ecx, 200h; unsigned int
0x180057fd0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057fd5  jmp     loc_180057F13
0x180057fda  cmp     r14d, 7
0x180057fde  jnz     loc_1800582EA
0x180057fe4  mov     r9d, [rsi+0E8h]
0x180057feb  cmp     r9d, r13d
0x180057fee  jz      loc_1800582EA
0x180057ff4  mov     r8, r12
0x180057ff7  mov     [rsp+80h+UnicodeSize], r13d
0x180057ffc  lea     rdx, aNlinsertserver; "NlInsertServerSession: Cdc branch id ch"...
0x180058003  mov     ecx, 200h; unsigned int
0x180058008  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005800d  jmp     loc_180057F13
0x180058012  mov     ebx, [rbp+arg_0]
0x180058015  mov     [rbp+ResultSize], 0
0x18005801c  mov     eax, 0F0h
0x180058021  cmp     r14d, 3
0x180058025  jnz     short loc_180058030
0x180058027  movzx   eax, [rbp+DestinationString.Length]
0x18005802b  add     eax, 0F2h
0x180058030  inc     ebx
0x180058032  cmp     [rbp+arg_88], 1
0x180058039  lea     ebx, [rax+rbx*2]
0x18005803c  jz      short loc_180058051
0x18005803e  mov     rax, qword ptr [rbp+UniSource.Length]
0x180058042  mov     rcx, [rbp+var_40]
0x180058046  add     eax, ecx
0x180058048  add     eax, dword ptr [rbp+var_48]
0x18005804b  lea     ebx, [rbx+rax*2]
0x18005804e  add     ebx, 6
0x180058051  mov     ecx, ebx
0x180058053  call    NetpMemoryAllocate
0x180058058  mov     rsi, rax
0x18005805b  test    rax, rax
0x18005805e  jnz     short loc_18005806A
0x180058060  mov     ebx, 0C0000017h
0x180058065  jmp     loc_1800583B3
0x18005806a  mov     r8d, ebx; Size
0x18005806d  xor     edx, edx; Val
0x18005806f  mov     rcx, rsi; void *
0x180058072  call    memset_0
0x180058077  xor     eax, eax
0x180058079  mov     [rsi+38h], r15
0x18005807d  mov     [rsi+20h], eax
0x180058080  inc     rdi
0x180058083  cmp     [r12+rdi*2], ax
0x180058088  jnz     short loc_180058080
0x18005808a  lea     eax, [rdi+rdi]
0x18005808d  mov     r9, r12; UnicodeString
0x180058090  lea     rcx, [rsi+24h]; OemString
0x180058094  mov     [rsp+80h+UnicodeSize], eax; UnicodeSize
0x180058098  lea     r8, [rbp+ResultSize]; ResultSize
0x18005809c  mov     edx, 0Fh; OemSize
0x1800580a1  call    cs:__imp_RtlUpcaseUnicodeToOemN
0x1800580a8  nop     dword ptr [rax+rax+00h]
0x1800580ad  xor     edi, edi
0x1800580af  mov     ebx, eax
0x1800580b1  test    eax, eax
0x1800580b3  jns     short loc_1800580C2
0x1800580b5  mov     rcx, rsi
0x1800580b8  call    NetpMemoryFree
0x1800580bd  jmp     loc_1800583B3
0x1800580c2  mov     eax, [rbp+ResultSize]
0x1800580c5  mov     [rax+rsi+24h], dil
0x1800580ca  cmp     [r15+228h], rdi
0x1800580d1  jnz     short loc_18005811A
0x1800580d3  mov     ecx, 800h
0x1800580d8  call    NetpMemoryAllocate
0x1800580dd  mov     [r15+228h], rax
0x1800580e4  test    rax, rax
0x1800580e7  jnz     short loc_1800580F6
0x1800580e9  mov     rcx, rsi
0x1800580ec  call    NetpMemoryFree
0x1800580f1  jmp     loc_180058060
0x1800580f6  mov     rdx, rdi
0x1800580f9  mov     rcx, rdx
0x1800580fc  inc     rdx
0x1800580ff  shl     rcx, 4
0x180058103  add     rcx, [r15+228h]
  ... truncated ...
```
