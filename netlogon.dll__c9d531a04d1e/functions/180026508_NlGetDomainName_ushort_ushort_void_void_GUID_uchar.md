# NlGetDomainName(ushort * *,ushort * *,void * *,void * *,_GUID * *,uchar *)

- ea: `0x180026508`
- end: `0x18002699c`
- name: `?NlGetDomainName@@YAKPEAPEAG0PEAPEAX1PEAPEAU_GUID@@PEAE@Z`
- size: `1172`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned __int16 **, void **, void **, struct _GUID **, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180026c90`
- `0x18007070c`

## callees

- `0x180007278`
- `0x180007b50`
- `0x18000d710`
- `0x180024158`
- `0x180026508`
- `0x180029020`
- `0x18006e0ec`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026608`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026814`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026846`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026892`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026923`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026608`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026814`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026846`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026892`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026923`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002669e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800266b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800266c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800266ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002669e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800266b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800266c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800266ea`
- `LSASRV!LsarClose` at `0x18002672b`
- `LSASRV!LsarClose` at `0x18002672b`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180026707`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18002671b`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180026707`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18002671b`
- `LSASRV!LsarQueryInformationPolicy` at `0x1800265cb`
- `LSASRV!LsarQueryInformationPolicy` at `0x180026643`
- `LSASRV!LsarQueryInformationPolicy` at `0x180026781`
- `LSASRV!LsarQueryInformationPolicy` at `0x1800265cb`
- `LSASRV!LsarQueryInformationPolicy` at `0x180026643`
- `LSASRV!LsarQueryInformationPolicy` at `0x180026781`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180026556`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180026556`
- `ntdll!RtlGetNtProductType` at `0x18002658e`
- `ntdll!RtlGetNtProductType` at `0x18002658e`
- `ntdll!RtlLengthSid` at `0x1800265fc`
- `ntdll!RtlLengthSid` at `0x180026808`
- `ntdll!RtlLengthSid` at `0x1800265fc`
- `ntdll!RtlLengthSid` at `0x180026808`
- `netutils!NetApiBufferFree` at `0x1800266d9`
- `netutils!NetApiBufferFree` at `0x1800266d9`
- `SAMSRV!SampDsIsRunning` at `0x1800265b0`
- `SAMSRV!SampDsIsRunning` at `0x1800265b0`

## string_xrefs

- `0x180026569`: `NlGetDomainName: Can't LsaIOpenPolicyTrusted: 0x%lx.\n`
- `0x18002673b`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`

## pseudocode

```c
__int64 __fastcall NlGetDomainName(
        HLOCAL *a1,
        LPVOID *a2,
        void **a3,
        void **a4,
        struct _GUID **a5,
        unsigned __int8 *a6)
{
  HLOCAL *v6; // r15
  void **v8; // r14
  int v10; // eax
  NTSTATUS v11; // ebx
  unsigned int v12; // eax
  enum _NT_PRODUCT_TYPE v13; // eax
  NTSTATUS v14; // ebx
  void *v15; // rcx
  SIZE_T v16; // rbx
  HLOCAL v17; // rax
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rcx
  LPVOID *v21; // rdi
  bool v22; // cf
  char *v23; // r9
  unsigned __int16 *v25; // rcx
  ULONG v26; // ebx
  HLOCAL v27; // rax
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // rbx
  struct _UNICODE_STRING *v30; // rcx
  __int64 v31; // rbx
  HLOCAL v32; // rsi
  __int64 v33; // rax
  _OWORD *v34; // rax
  unsigned int v35; // eax
  __int64 v36; // [rsp+20h] [rbp-18h] BYREF
  _QWORD v37[2]; // [rsp+28h] [rbp-10h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+80h] [rbp+48h] BYREF
  LPVOID *v39; // [rsp+88h] [rbp+50h]
  unsigned __int16 *v40; // [rsp+90h] [rbp+58h] BYREF
  void **v41; // [rsp+98h] [rbp+60h]

  v41 = a4;
  v39 = a2;
  v6 = (HLOCAL *)a5;
  *a1 = 0;
  v40 = 0;
  v8 = a4;
  v36 = 0;
  *v6 = 0;
  v37[0] = 0;
  ProductType = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v10 = LsaIOpenPolicyTrusted(v37);
  v11 = v10;
  if ( v10 < 0 )
  {
    LOBYTE(a5) = 0;
    NlPrintRoutine(0x100u, L"NlGetDomainName: Can't LsaIOpenPolicyTrusted: 0x%lx.\n", (unsigned int)v10);
    v12 = NetpNtStatusToApiStatus(v11);
    goto LABEL_44;
  }
  if ( RtlGetNtProductType(&ProductType) )
  {
    v13 = ProductType;
  }
  else
  {
    v13 = NtProductWinNt;
    ProductType = NtProductWinNt;
  }
  if ( v13 == NtProductLanManNt && !(unsigned __int8)SampDsIsRunning() )
  {
    LOBYTE(a5) = 1;
    v14 = LsarQueryInformationPolicy(v37[0], 14, &v36);
    if ( v14 < 0 )
    {
      NlPrintRoutine(
        0x100u,
        L"NlGetDomainName: Can't LsarQueryInformationPolicy (LocalAccountDomain): 0x%lx.\n",
        (unsigned int)v14);
LABEL_43:
      v12 = NetpNtStatusToApiStatus(v14);
LABEL_44:
      v18 = v12;
      NlExit(5602, v12, 1);
      if ( !v18 )
        goto LABEL_33;
      goto LABEL_23;
    }
    if ( (unsigned __int16)(*(_WORD *)v36 - 1) <= 0x1Du )
    {
      v15 = *(void **)(v36 + 16);
      if ( v15 )
        goto LABEL_12;
    }
    NlPrintRoutine(0x100u, L"Local Account domain info from LSA invalid.\n");
LABEL_21:
    v18 = 3095;
    v19 = 0;
    v20 = 3095;
    goto LABEL_22;
  }
  LOBYTE(a5) = 0;
  v14 = LsarQueryInformationPolicy(v37[0], 5, &v36);
  if ( v14 < 0 )
  {
    NlPrintRoutine(
      0x100u,
      L"NlGetDomainName: Can't LsarQueryInformationPolicy (AccountDomain): 0x%lx.\n",
      (unsigned int)v14);
    goto LABEL_43;
  }
  if ( (unsigned __int16)(*(_WORD *)v36 - 1) > 0x1Du || (v15 = *(void **)(v36 + 16)) == 0 )
  {
    NlPrintRoutine(0x100u, L"Account domain info from LSA invalid.\n");
    goto LABEL_21;
  }
LABEL_12:
  v16 = RtlLengthSid(v15);
  v17 = LocalAlloc(0, v16);
  *a3 = v17;
  if ( !v17 )
    goto LABEL_13;
  memcpy_0(v17, *(const void **)(v36 + 16), v16);
  v14 = LsarQueryInformationPolicy(v37[0], 12, &v40);
  if ( v14 < 0 )
  {
    NlPrintRoutine(
      0x100u,
      L"NlGetDomainName: Can't LsarQueryInformationPolicy (DnsDomain): 0x%lx.\n",
      (unsigned int)v14);
    goto LABEL_43;
  }
  v25 = v40;
  if ( (unsigned __int16)(*v40 - 1) > 0x1Du || !*((_QWORD *)v40 + 8) )
  {
    NlPrintRoutine(0x100u, L"Primary domain info from LSA invalid.\n");
    dword_1800F124C = 0;
    NlCreateSysvolShares();
    goto LABEL_21;
  }
  if ( NlGlobalMemberWorkstation )
  {
    v26 = RtlLengthSid(*((PSID *)v40 + 8));
    v27 = LocalAlloc(0, v26);
    *v8 = v27;
    if ( !v27 )
      goto LABEL_13;
    memcpy_0(v27, *((const void **)v40 + 8), v26);
    v25 = v40;
  }
  else if ( (unsigned __int16)(v40[8] - 1) > 0x1FDu )
  {
    goto LABEL_21;
  }
  v28 = (unsigned __int16 *)LocalAlloc(0, *v25 + 2LL);
  *a1 = v28;
  v29 = v28;
  if ( v28 )
  {
    memcpy_0(v28, *((const void **)v40 + 1), *v40);
    v29[(unsigned __int64)*v40 >> 1] = 0;
    v30 = (struct _UNICODE_STRING *)v40;
    v31 = v40[8] >> 1;
    if ( (_DWORD)v31 )
    {
      v32 = LocalAlloc(0, 2LL * (unsigned int)(v31 + 2));
      *v39 = v32;
      if ( !v32 )
      {
        v18 = 8;
        NlExit(3054, 8, 1);
        goto LABEL_23;
      }
      memcpy_0(v32, *((const void **)v40 + 3), 2LL * (unsigned int)v31);
      if ( *((_WORD *)v32 + (unsigned int)(v31 - 1)) != 46 )
      {
        *((_WORD *)v32 + (unsigned int)v31) = 46;
        v31 = (unsigned int)(v31 + 1);
      }
      v8 = v41;
      *((_WORD *)v32 + v31) = 0;
      v30 = (struct _UNICODE_STRING *)v40;
    }
    v33 = *(_QWORD *)&v30[3].Length - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
    if ( !v33 )
      v33 = (__int64)v30[3].Buffer - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
    if ( v33 )
    {
      v34 = LocalAlloc(0, 0x10u);
      *v6 = v34;
      if ( !v34 )
        goto LABEL_13;
      *v34 = *((_OWORD *)v40 + 3);
      v30 = (struct _UNICODE_STRING *)v40;
    }
    else
    {
      *v6 = 0;
    }
    v35 = NlSetDnsForestName(v30 + 2, a6);
    v18 = v35;
    if ( !v35 )
    {
      v18 = 0;
      goto LABEL_33;
    }
    NlPrintRoutine(0x100u, L"Can't NlSetDnsForestName %ld\n", v35);
    goto LABEL_14;
  }
LABEL_13:
  v18 = 8;
LABEL_14:
  v19 = v18;
  v20 = 3054;
LABEL_22:
  NlExit(v20, v19, 1);
LABEL_23:
  if ( *v8 )
  {
    LocalFree(*v8);
    *v8 = 0;
  }
  if ( *a3 )
  {
    LocalFree(*a3);
    *a3 = 0;
  }
  if ( *a1 )
  {
    LocalFree(*a1);
    *a1 = 0;
  }
  v21 = v39;
  if ( *v39 )
  {
    NetApiBufferFree(*v39);
    *v21 = 0;
  }
  if ( *v6 )
  {
    LocalFree(*v6);
    *v6 = 0;
  }
LABEL_33:
  if ( v36 )
  {
    v22 = (_BYTE)a5 != 0;
    LOBYTE(a5) = -(char)a5;
    LsaIFree_LSAPR_POLICY_INFORMATION(v22 ? 14 : 5);
  }
  if ( v40 )
    LsaIFree_LSAPR_POLICY_INFORMATION(12);
  if ( v37[0] && (int)LsarClose(v37) < 0 )
    NlAssertFailed("NT_SUCCESS(Status)", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\domain.cxx", 437, v23);
  return v18;
}

```

## disassembly

```asm
0x180026508  mov     [rsp-40h+arg_18], r9
0x18002650d  mov     [rsp-40h+arg_8], rdx
0x180026512  push    rbp
0x180026513  push    rbx
0x180026514  push    rsi
0x180026515  push    rdi
0x180026516  push    r12
0x180026518  push    r13
0x18002651a  push    r14
0x18002651c  push    r15
0x18002651e  mov     rbp, rsp
0x180026521  sub     rsp, 38h
0x180026525  mov     r15, [rbp+arg_20]
0x180026529  xor     esi, esi
0x18002652b  mov     r13, rcx
0x18002652e  mov     [rcx], rsi
0x180026531  lea     rcx, [rbp+var_10]
0x180026535  mov     [rbp+arg_10], rsi
0x180026539  mov     r14, r9
0x18002653c  mov     [rbp+var_18], rsi
0x180026540  mov     [r15], rsi
0x180026543  mov     r12, r8
0x180026546  mov     [rbp+var_10], rsi
0x18002654a  mov     [rbp+ProductType], esi
0x18002654d  mov     [rdx], rsi
0x180026550  mov     [r8], rsi
0x180026553  mov     [r9], rsi
0x180026556  call    cs:__imp_LsaIOpenPolicyTrusted
0x18002655c  mov     ebx, eax
0x18002655e  test    eax, eax
0x180026560  jns     short loc_18002658A
0x180026562  mov     r8d, eax
0x180026565  mov     byte ptr [rbp+arg_20], sil
0x180026569  lea     rdx, aNlgetdomainnam_1; "NlGetDomainName: Can't LsaIOpenPolicyTr"...
0x180026570  mov     ecx, 100h; unsigned int
0x180026575  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002657a  mov     ecx, ebx; Status
0x18002657c  call    NetpNtStatusToApiStatus
0x180026581  lea     r8d, [rsi+1]
0x180026585  jmp     loc_1800267AB
0x18002658a  lea     rcx, [rbp+ProductType]; ProductType
0x18002658e  call    cs:__imp_RtlGetNtProductType
0x180026594  mov     edi, 1
0x180026599  test    al, al
0x18002659b  jnz     short loc_1800265A4
0x18002659d  mov     eax, edi
0x18002659f  mov     [rbp+ProductType], eax
0x1800265a2  jmp     short loc_1800265A7
0x1800265a4  mov     eax, [rbp+ProductType]
0x1800265a7  cmp     eax, 2
0x1800265aa  jnz     loc_180026632
0x1800265b0  call    cs:__imp_SampDsIsRunning
0x1800265b6  test    al, al
0x1800265b8  jnz     short loc_180026632
0x1800265ba  mov     rcx, [rbp+var_10]
0x1800265be  lea     r8, [rbp+var_18]
0x1800265c2  mov     edx, 0Eh
0x1800265c7  mov     byte ptr [rbp+arg_20], dil
0x1800265cb  call    cs:__imp_LsarQueryInformationPolicy
0x1800265d1  mov     ebx, eax
0x1800265d3  test    eax, eax
0x1800265d5  jns     short loc_1800265E3
0x1800265d7  lea     rdx, aNlgetdomainnam_2; "NlGetDomainName: Can't LsarQueryInforma"...
0x1800265de  jmp     loc_180026794
0x1800265e3  mov     rcx, [rbp+var_18]
0x1800265e7  movzx   eax, word ptr [rcx]
0x1800265ea  sub     ax, di
0x1800265ed  cmp     ax, 1Dh
0x1800265f1  ja      short loc_180026629
0x1800265f3  mov     rcx, [rcx+10h]; Sid
0x1800265f7  test    rcx, rcx
0x1800265fa  jz      short loc_180026629
0x1800265fc  call    cs:__imp_RtlLengthSid
0x180026602  mov     edx, eax; uBytes
0x180026604  xor     ecx, ecx; uFlags
0x180026606  mov     ebx, eax
0x180026608  call    cs:__imp_LocalAlloc
0x18002660e  mov     [r12], rax
0x180026612  test    rax, rax
0x180026615  jnz     loc_180026761
0x18002661b  mov     ebx, 8
0x180026620  mov     edx, ebx
0x180026622  mov     ecx, 0BEEh
0x180026627  jmp     short loc_18002668E
0x180026629  lea     rdx, aLocalAccountDo; "Local Account domain info from LSA inva"...
0x180026630  jmp     short loc_18002667B
0x180026632  mov     rcx, [rbp+var_10]
0x180026636  lea     r8, [rbp+var_18]
0x18002663a  mov     edx, 5
0x18002663f  mov     byte ptr [rbp+arg_20], sil
0x180026643  call    cs:__imp_LsarQueryInformationPolicy
0x180026649  mov     ebx, eax
0x18002664b  test    eax, eax
0x18002664d  jns     short loc_18002665B
0x18002664f  lea     rdx, aNlgetdomainnam; "NlGetDomainName: Can't LsarQueryInforma"...
0x180026656  jmp     loc_180026794
0x18002665b  mov     rcx, [rbp+var_18]
0x18002665f  movzx   eax, word ptr [rcx]
0x180026662  sub     ax, di
0x180026665  cmp     ax, 1Dh
0x180026669  ja      short loc_180026674
0x18002666b  mov     rcx, [rcx+10h]
0x18002666f  test    rcx, rcx
0x180026672  jnz     short loc_1800265FC
0x180026674  lea     rdx, aAccountDomainI; "Account domain info from LSA invalid.\n"
0x18002667b  mov     ecx, 100h; unsigned int
0x180026680  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180026685  mov     ebx, 0C17h
0x18002668a  xor     edx, edx
0x18002668c  mov     ecx, ebx
0x18002668e  mov     r8d, edi
0x180026691  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180026696  mov     rcx, [r14]; hMem
0x180026699  test    rcx, rcx
0x18002669c  jz      short loc_1800266A7
0x18002669e  call    cs:__imp_LocalFree
0x1800266a4  mov     [r14], rsi
0x1800266a7  mov     rcx, [r12]; hMem
0x1800266ab  test    rcx, rcx
0x1800266ae  jz      short loc_1800266BA
0x1800266b0  call    cs:__imp_LocalFree
0x1800266b6  mov     [r12], rsi
0x1800266ba  mov     rcx, [r13+0]; hMem
0x1800266be  test    rcx, rcx
0x1800266c1  jz      short loc_1800266CD
0x1800266c3  call    cs:__imp_LocalFree
0x1800266c9  mov     [r13+0], rsi
0x1800266cd  mov     rdi, [rbp+arg_8]
0x1800266d1  mov     rcx, [rdi]; Buffer
0x1800266d4  test    rcx, rcx
0x1800266d7  jz      short loc_1800266E2
0x1800266d9  call    cs:__imp_NetApiBufferFree
0x1800266df  mov     [rdi], rsi
0x1800266e2  mov     rcx, [r15]; hMem
0x1800266e5  test    rcx, rcx
0x1800266e8  jz      short loc_1800266F3
0x1800266ea  call    cs:__imp_LocalFree
0x1800266f0  mov     [r15], rsi
0x1800266f3  mov     rdx, [rbp+var_18]
0x1800266f7  test    rdx, rdx
0x1800266fa  jz      short loc_18002670D
0x1800266fc  neg     byte ptr [rbp+arg_20]
0x1800266ff  sbb     ecx, ecx
0x180026701  and     ecx, 9
0x180026704  add     ecx, 5
0x180026707  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x18002670d  mov     rdx, [rbp+arg_10]
0x180026711  test    rdx, rdx
0x180026714  jz      short loc_180026721
0x180026716  mov     ecx, 0Ch
0x18002671b  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x180026721  cmp     [rbp+var_10], rsi
0x180026725  jz      short loc_18002674E
0x180026727  lea     rcx, [rbp+var_10]
0x18002672b  call    cs:__imp_LsarClose
0x180026731  test    eax, eax
0x180026733  jns     short loc_18002674E
0x180026735  mov     r8d, 1B5h; unsigned int
0x18002673b  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180026742  lea     rcx, aNtSuccessStatu_4; "NT_SUCCESS(Status)"
0x180026749  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002674e  mov     eax, ebx
0x180026750  add     rsp, 38h
0x180026754  pop     r15
0x180026756  pop     r14
0x180026758  pop     r13
0x18002675a  pop     r12
0x18002675c  pop     rdi
0x18002675d  pop     rsi
0x18002675e  pop     rbx
0x18002675f  pop     rbp
0x180026760  retn
0x180026761  mov     rdx, [rbp+var_18]
0x180026765  mov     r8, rbx; Size
0x180026768  mov     rcx, rax; void *
0x18002676b  mov     rdx, [rdx+10h]; Src
0x18002676f  call    memcpy_0
0x180026774  mov     rcx, [rbp+var_10]
0x180026778  lea     r8, [rbp+arg_10]
0x18002677c  mov     edx, 0Ch
0x180026781  call    cs:__imp_LsarQueryInformationPolicy
0x180026787  mov     ebx, eax
0x180026789  test    eax, eax
0x18002678b  jns     short loc_1800267C6
0x18002678d  lea     rdx, aNlgetdomainnam_0; "NlGetDomainName: Can't LsarQueryInforma"...
0x180026794  mov     r8d, ebx
0x180026797  mov     ecx, 100h; unsigned int
0x18002679c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800267a1  mov     ecx, ebx; Status
0x1800267a3  call    NetpNtStatusToApiStatus
0x1800267a8  mov     r8d, edi
0x1800267ab  mov     edx, eax
0x1800267ad  mov     ecx, 15E2h
0x1800267b2  mov     ebx, eax
0x1800267b4  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x1800267b9  test    ebx, ebx
0x1800267bb  jz      loc_1800266F3
0x1800267c1  jmp     loc_180026696
0x1800267c6  mov     rcx, [rbp+arg_10]
0x1800267ca  movzx   eax, word ptr [rcx]
0x1800267cd  sub     ax, di
0x1800267d0  cmp     ax, 1Dh
0x1800267d4  ja      loc_18002697B
0x1800267da  mov     rax, [rcx+40h]
0x1800267de  test    rax, rax
0x1800267e1  jz      loc_18002697B
0x1800267e7  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x1800267ed  jnz     short loc_180026805
0x1800267ef  movzx   eax, word ptr [rcx+10h]
0x1800267f3  mov     edx, 1FDh
0x1800267f8  sub     ax, di
0x1800267fb  cmp     ax, dx
0x1800267fe  jbe     short loc_18002683D
0x180026800  jmp     loc_180026685
0x180026805  mov     rcx, rax; Sid
0x180026808  call    cs:__imp_RtlLengthSid
0x18002680e  mov     edx, eax; uBytes
0x180026810  xor     ecx, ecx; uFlags
0x180026812  mov     ebx, eax
0x180026814  call    cs:__imp_LocalAlloc
0x18002681a  mov     [r14], rax
0x18002681d  test    rax, rax
0x180026820  jz      loc_18002661B
0x180026826  mov     rdx, [rbp+arg_10]
0x18002682a  mov     r8d, ebx; Size
0x18002682d  mov     rcx, rax; void *
0x180026830  mov     rdx, [rdx+40h]; Src
0x180026834  call    memcpy_0
0x180026839  mov     rcx, [rbp+arg_10]
0x18002683d  movzx   edx, word ptr [rcx]
0x180026840  xor     ecx, ecx; uFlags
0x180026842  add     rdx, 2; uBytes
0x180026846  call    cs:__imp_LocalAlloc
0x18002684c  mov     [r13+0], rax
0x180026850  mov     rbx, rax
0x180026853  test    rax, rax
0x180026856  jz      loc_18002661B
0x18002685c  mov     rdx, [rbp+arg_10]
0x180026860  mov     rcx, rax; void *
0x180026863  movzx   r8d, word ptr [rdx]; Size
0x180026867  mov     rdx, [rdx+8]; Src
0x18002686b  call    memcpy_0
0x180026870  mov     rax, [rbp+arg_10]
0x180026874  movzx   ecx, word ptr [rax]
0x180026877  shr     rcx, 1
0x18002687a  mov     [rbx+rcx*2], si
0x18002687e  mov     rcx, [rbp+arg_10]
0x180026882  movzx   ebx, word ptr [rcx+10h]
0x180026886  shr     ebx, 1
0x180026888  jz      short loc_1800268FA
0x18002688a  lea     edx, [rbx+2]
0x18002688d  xor     ecx, ecx; uFlags
0x18002688f  add     rdx, rdx; uBytes
0x180026892  call    cs:__imp_LocalAlloc
0x180026898  mov     rsi, rax
0x18002689b  mov     rax, [rbp+arg_8]
0x18002689f  mov     [rax], rsi
0x1800268a2  test    rsi, rsi
0x1800268a5  jnz     short loc_1800268BE
0x1800268a7  lea     ebx, [rsi+8]
0x1800268aa  mov     r8d, edi
0x1800268ad  mov     edx, ebx
0x1800268af  mov     ecx, 0BEEh
0x1800268b4  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x1800268b9  jmp     loc_180026696
0x1800268be  mov     rdx, [rbp+arg_10]
0x1800268c2  lea     r14, [rbx+rbx]
0x1800268c6  mov     r8, r14; Size
0x1800268c9  mov     rcx, rsi; void *
0x1800268cc  mov     rdx, [rdx+18h]; Src
0x1800268d0  call    memcpy_0
0x1800268d5  lea     ecx, [rbx-1]
0x1800268d8  mov     eax, 2Eh ; '.'
0x1800268dd  cmp     [rsi+rcx*2], ax
0x1800268e1  jz      short loc_1800268EA
0x1800268e3  mov     [r14+rsi], ax
0x1800268e8  inc     ebx
0x1800268ea  mov     r14, [rbp+arg_18]
0x1800268ee  xor     eax, eax
0x1800268f0  mov     [rsi+rbx*2], ax
0x1800268f4  xor     esi, esi
0x1800268f6  mov     rcx, [rbp+arg_10]
0x1800268fa  mov     rax, [rcx+30h]
0x1800268fe  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180026905  jnz     short loc_180026912
0x180026907  mov     rax, [rcx+38h]
0x18002690b  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180026912  test    rax, rax
0x180026915  jnz     short loc_18002691C
0x180026917  mov     [r15], rsi
0x18002691a  jmp     short loc_180026948
0x18002691c  mov     edx, 10h; uBytes
0x180026921  xor     ecx, ecx; uFlags
0x180026923  call    cs:__imp_LocalAlloc
0x180026929  mov     [r15], rax
0x18002692c  mov     rcx, rax
0x18002692f  test    rax, rax
0x180026932  jz      loc_18002661B
0x180026938  mov     rax, [rbp+arg_10]
0x18002693c  movups  xmm0, xmmword ptr [rax+30h]
  ... truncated ...
```
