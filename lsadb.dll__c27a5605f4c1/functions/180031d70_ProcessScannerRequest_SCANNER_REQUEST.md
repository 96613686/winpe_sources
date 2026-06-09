# ProcessScannerRequest(_SCANNER_REQUEST *)

- ea: `0x180031d70`
- end: `0x180031ff2`
- name: `?ProcessScannerRequest@@YAXPEAU_SCANNER_REQUEST@@@Z`
- size: `642`
- prototype: `void __fastcall(struct _SCANNER_REQUEST *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800325c0`

## callees

- `0x18000fd40`
- `0x18000fd80`
- `0x18002b6f0`
- `0x18002f474`
- `0x18002f9d0`
- `0x18003080c`
- `0x180031cd8`
- `0x180031d70`
- `0x180032408`

## import_xrefs

- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180031e94`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180031f55`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180031fd4`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180031e94`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180031f55`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x180031fd4`
- `ntdll!RtlInitUnicodeString` at `0x180031e62`
- `ntdll!RtlInitUnicodeString` at `0x180031e7c`
- `ntdll!RtlInitUnicodeString` at `0x180031f36`
- `ntdll!RtlInitUnicodeString` at `0x180031f7f`
- `ntdll!RtlInitUnicodeString` at `0x180031e62`
- `ntdll!RtlInitUnicodeString` at `0x180031e7c`
- `ntdll!RtlInitUnicodeString` at `0x180031f36`
- `ntdll!RtlInitUnicodeString` at `0x180031f7f`

## pseudocode

```c
void __fastcall ProcessScannerRequest(struct _SCANNER_REQUEST *a1)
{
  PCWSTR *v2; // rsi
  int v3; // eax
  char v4; // r15
  struct _LIST_ENTRY *Flink; // rbx
  __int64 *v6; // rcx
  int v7; // r14d
  unsigned int v8; // esi
  unsigned int v9; // eax
  const WCHAR *v10; // rdx
  int v11; // eax
  __int64 *v12; // rcx
  __int64 v13; // [rsp+20h] [rbp-30h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  struct _LIST_ENTRY v15; // [rsp+40h] [rbp-10h] BYREF

  v15 = 0;
  DestinationString = 0;
  v2 = (PCWSTR *)((char *)a1 + 16);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      (unsigned int)&WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
      (unsigned int)*v2,
      *((_DWORD *)a1 + 6),
      *((_DWORD *)a1 + 7),
      *(_QWORD *)&DestinationString.Length,
      DestinationString.Buffer,
      v15.Flink,
      v15.Blink);
  v15.Blink = &v15;
  v15.Flink = &v15;
  v3 = CollectTrustsToScan(a1, &v15);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        &WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
        (unsigned int)v3);
    goto LABEL_39;
  }
  Flink = v15.Flink;
  if ( v15.Flink == &v15 )
  {
    if ( (*((_BYTE *)a1 + 28) & 2) == 0 )
      goto LABEL_33;
    if ( !*v2 )
    {
      RtlInitUnicodeString(&DestinationString, L"*");
      goto LABEL_13;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, *v2);
      v2 = (PCWSTR *)((char *)a1 + 16);
    }
    RtlInitUnicodeString(&DestinationString, *v2);
    v6 = LSA_PDC_MANUAL_TRUSTSCAN_NOTFOUND;
LABEL_14:
    SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)v6, L"u", &DestinationString);
    goto LABEL_39;
  }
  v7 = 0;
  while ( Flink != &v15 )
  {
    v8 = ScanTrust((struct _TRUST_SCAN_CONTEXT *)Flink);
    if ( v8 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          (unsigned int)&WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
          Flink[1].Flink,
          v4);
      goto LABEL_24;
    }
    v9 = ProcessScanResult((struct _TRUST_SCAN_CONTEXT *)Flink);
    v8 = v9;
    if ( v9 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          (unsigned int)&WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
          Flink[1].Flink,
          v9);
LABEL_24:
      v7 = 1;
      RtlInitUnicodeString(&DestinationString, (PCWSTR)Flink[1].Flink);
      LODWORD(v13) = v8;
      SpmpEventWrite(
        (const struct _EVENT_DESCRIPTOR *)LSA_PDC_SPECIFIC_TRUST_SCAN_FAILURE,
        L"udd",
        &DestinationString,
        v8,
        v13);
      goto LABEL_25;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
        Flink[1].Flink);
LABEL_25:
    Flink = Flink->Flink;
  }
  v10 = (const WCHAR *)*((_QWORD *)a1 + 2);
  if ( !v10 )
    v10 = L"*";
  RtlInitUnicodeString(&DestinationString, v10);
  v11 = *((_DWORD *)a1 + 7) & 2;
  if ( !v7 )
  {
    if ( !v11 )
    {
      if ( *((_QWORD *)a1 + 2) )
      {
        v6 = LSA_PDC_SPECIFIC_TRUSTSCAN_SUCCESS;
        goto LABEL_14;
      }
LABEL_33:
      v12 = LSA_PDC_FULL_TRUSTSCAN_SUCCESS;
LABEL_38:
      SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)v12, 0);
      goto LABEL_39;
    }
LABEL_13:
    v6 = LSA_PDC_MANUAL_TRUSTSCAN_SUCCESS;
    goto LABEL_14;
  }
  if ( v11 )
  {
    v6 = LSA_PDC_MANUAL_TRUSTSCAN_FAILURE;
    goto LABEL_14;
  }
  if ( !*((_QWORD *)a1 + 2) )
  {
    v12 = LSA_PDC_FULL_TRUSTSCAN_FAILURE;
    goto LABEL_38;
  }
LABEL_39:
  FreeTrustScanContextList(&v15);
}

```

## disassembly

```asm
0x180031d70  push    rbp
0x180031d72  push    rbx
0x180031d73  push    rsi
0x180031d74  push    rdi
0x180031d75  push    r13
0x180031d77  push    r14
0x180031d79  push    r15
0x180031d7b  mov     rbp, rsp
0x180031d7e  sub     rsp, 50h
0x180031d82  xorps   xmm0, xmm0
0x180031d85  xorps   xmm1, xmm1
0x180031d88  movups  xmmword ptr [rbp+var_10.Flink], xmm0
0x180031d8c  mov     rdi, rcx
0x180031d8f  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180031d93  lea     rsi, [rcx+10h]
0x180031d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d9e  lea     r13, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x180031da5  test    byte ptr [rcx+1Ch], 10h
0x180031da9  jz      short loc_180031DCD
0x180031dab  mov     eax, [rdi+1Ch]
0x180031dae  mov     edx, 36h ; '6'
0x180031db3  mov     r9, [rsi]
0x180031db6  mov     r8, r13
0x180031db9  mov     rcx, [rcx+10h]
0x180031dbd  mov     [rsp+50h+var_28], eax
0x180031dc1  mov     eax, [rdi+18h]
0x180031dc4  mov     dword ptr [rsp+50h+var_30], eax
0x180031dc8  call    WPP_SF_SDD
0x180031dcd  lea     rax, [rbp+var_10]
0x180031dd1  mov     rcx, rdi; struct _SCANNER_REQUEST *
0x180031dd4  mov     [rbp+var_10.Blink], rax
0x180031dd8  lea     rdx, [rbp+var_10]; struct _LIST_ENTRY *
0x180031ddc  lea     rax, [rbp+var_10]
0x180031de0  mov     [rbp+var_10.Flink], rax
0x180031de4  call    ?CollectTrustsToScan@@YAJPEAU_SCANNER_REQUEST@@PEAU_LIST_ENTRY@@@Z; CollectTrustsToScan(_SCANNER_REQUEST *,_LIST_ENTRY *)
0x180031de9  mov     r15d, eax
0x180031dec  test    eax, eax
0x180031dee  jns     short loc_180031E1A
0x180031df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180031df7  test    byte ptr [rcx+1Ch], 10h
0x180031dfb  jz      loc_180031FDA
0x180031e01  mov     rcx, [rcx+10h]
0x180031e05  mov     edx, 37h ; '7'
0x180031e0a  mov     r9d, eax
0x180031e0d  mov     r8, r13
0x180031e10  call    WPP_SF_d
0x180031e15  jmp     loc_180031FDA
0x180031e1a  mov     rbx, [rbp+var_10.Flink]
0x180031e1e  lea     rax, [rbp+var_10]
0x180031e22  cmp     rbx, rax
0x180031e25  jnz     short loc_180031E9F
0x180031e27  test    byte ptr [rdi+1Ch], 2
0x180031e2b  jz      loc_180031FAB
0x180031e31  mov     r9, [rsi]
0x180031e34  test    r9, r9
0x180031e37  jz      short loc_180031E71
0x180031e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e40  test    byte ptr [rcx+1Ch], 10h
0x180031e44  jz      short loc_180031E5B
0x180031e46  mov     rcx, [rcx+10h]
0x180031e4a  mov     edx, 3Bh ; ';'
0x180031e4f  mov     r8, r13
0x180031e52  call    WPP_SF_S
0x180031e57  lea     rsi, [rdi+10h]
0x180031e5b  mov     rdx, [rsi]; SourceString
0x180031e5e  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031e62  call    cs:__imp_RtlInitUnicodeString
0x180031e68  lea     rcx, LSA_PDC_MANUAL_TRUSTSCAN_NOTFOUND
0x180031e6f  jmp     short loc_180031E89
0x180031e71  lea     rdx, asc_18003E5C8; "*"
0x180031e78  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031e7c  call    cs:__imp_RtlInitUnicodeString
0x180031e82  lea     rcx, LSA_PDC_MANUAL_TRUSTSCAN_SUCCESS
0x180031e89  lea     rdx, aU; "u"
0x180031e90  lea     r8, [rbp+DestinationString]
0x180031e94  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180031e9a  jmp     loc_180031FDA
0x180031e9f  xor     r14d, r14d
0x180031ea2  jmp     loc_180031F5E
0x180031ea7  mov     rcx, rbx; struct _TRUST_SCAN_CONTEXT *
0x180031eaa  call    ?ScanTrust@@YAKPEAU_TRUST_SCAN_CONTEXT@@@Z; ScanTrust(_TRUST_SCAN_CONTEXT *)
0x180031eaf  mov     esi, eax
0x180031eb1  test    eax, eax
0x180031eb3  jnz     short loc_180031F01
0x180031eb5  mov     rcx, rbx; struct _TRUST_SCAN_CONTEXT *
0x180031eb8  call    ?ProcessScanResult@@YAKPEAU_TRUST_SCAN_CONTEXT@@@Z; ProcessScanResult(_TRUST_SCAN_CONTEXT *)
0x180031ebd  mov     esi, eax
0x180031ebf  test    eax, eax
0x180031ec1  jnz     short loc_180031EE9
0x180031ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180031eca  test    byte ptr [rcx+1Ch], 10h
0x180031ece  jz      loc_180031F5B
0x180031ed4  mov     r9, [rbx+10h]
0x180031ed8  lea     edx, [rax+38h]
0x180031edb  mov     rcx, [rcx+10h]
0x180031edf  mov     r8, r13
0x180031ee2  call    WPP_SF_S
0x180031ee7  jmp     short loc_180031F5B
0x180031ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ef0  test    byte ptr [rcx+1Ch], 10h
0x180031ef4  jz      short loc_180031F28
0x180031ef6  mov     edx, 39h ; '9'
0x180031efb  mov     dword ptr [rsp+50h+var_30], eax
0x180031eff  jmp     short loc_180031F18
0x180031f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f08  test    byte ptr [rcx+1Ch], 10h
0x180031f0c  jz      short loc_180031F28
0x180031f0e  mov     edx, 3Ah ; ':'
0x180031f13  mov     dword ptr [rsp+50h+var_30], r15d
0x180031f18  mov     r9, [rbx+10h]
0x180031f1c  mov     r8, r13
0x180031f1f  mov     rcx, [rcx+10h]
0x180031f23  call    WPP_SF_SD
0x180031f28  mov     rdx, [rbx+10h]; SourceString
0x180031f2c  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031f30  mov     r14d, 1
0x180031f36  call    cs:__imp_RtlInitUnicodeString
0x180031f3c  mov     r9d, esi
0x180031f3f  mov     dword ptr [rsp+50h+var_30], esi
0x180031f43  lea     r8, [rbp+DestinationString]
0x180031f47  lea     rdx, aUdd; "udd"
0x180031f4e  lea     rcx, LSA_PDC_SPECIFIC_TRUST_SCAN_FAILURE
0x180031f55  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180031f5b  mov     rbx, [rbx]
0x180031f5e  lea     rax, [rbp+var_10]
0x180031f62  cmp     rbx, rax
0x180031f65  jnz     loc_180031EA7
0x180031f6b  mov     rdx, [rdi+10h]
0x180031f6f  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031f73  test    rdx, rdx
0x180031f76  jnz     short loc_180031F7F
0x180031f78  lea     rdx, asc_18003E5C8; "*"
0x180031f7f  call    cs:__imp_RtlInitUnicodeString
0x180031f85  mov     eax, [rdi+1Ch]
0x180031f88  and     eax, 2
0x180031f8b  test    r14d, r14d
0x180031f8e  jnz     short loc_180031FB4
0x180031f90  test    eax, eax
0x180031f92  jnz     loc_180031E82
0x180031f98  cmp     qword ptr [rdi+10h], 0
0x180031f9d  jz      short loc_180031FAB
0x180031f9f  lea     rcx, LSA_PDC_SPECIFIC_TRUSTSCAN_SUCCESS
0x180031fa6  jmp     loc_180031E89
0x180031fab  lea     rcx, LSA_PDC_FULL_TRUSTSCAN_SUCCESS
0x180031fb2  jmp     short loc_180031FD2
0x180031fb4  test    eax, eax
0x180031fb6  jz      short loc_180031FC4
0x180031fb8  lea     rcx, LSA_PDC_MANUAL_TRUSTSCAN_FAILURE
0x180031fbf  jmp     loc_180031E89
0x180031fc4  cmp     qword ptr [rdi+10h], 0
0x180031fc9  jnz     short loc_180031FDA
0x180031fcb  lea     rcx, LSA_PDC_FULL_TRUSTSCAN_FAILURE
0x180031fd2  xor     edx, edx
0x180031fd4  call    cs:__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ; SpmpEventWrite(_EVENT_DESCRIPTOR const *,ushort *,...)
0x180031fda  lea     rcx, [rbp+var_10]; struct _LIST_ENTRY *
0x180031fde  call    ?FreeTrustScanContextList@@YAXPEAU_LIST_ENTRY@@@Z; FreeTrustScanContextList(_LIST_ENTRY *)
0x180031fe3  add     rsp, 50h
0x180031fe7  pop     r15
0x180031fe9  pop     r14
0x180031feb  pop     r13
0x180031fed  pop     rdi
0x180031fee  pop     rsi
0x180031fef  pop     rbx
0x180031ff0  pop     rbp
0x180031ff1  retn
```
