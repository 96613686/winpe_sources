# NlGetDomainName(ushort * *,ushort * *,void * *,void * *,_GUID * *,uchar *)

- ea: `0x180027748`
- end: `0x180027c63`
- name: `?NlGetDomainName@@YAKPEAPEAG0PEAPEAX1PEAPEAU_GUID@@PEAE@Z`
- size: `1307`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned __int16 **, void **, void **, struct _GUID **, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180027fa4`
- `0x180075b60`

## callees

- `0x180007518`
- `0x180007e90`
- `0x18000dd00`
- `0x18002520c`
- `0x180027748`
- `0x18002a6f4`
- `0x18007331c`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002786a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027ac3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027afb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027b4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027be4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002786a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027ac3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027afb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027b4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027be4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027974`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027974`
- `LSASRV!LsarClose` at `0x1800279c7`
- `LSASRV!LsarClose` at `0x1800279c7`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180027997`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800279b1`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180027997`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x1800279b1`
- `LSASRV!LsarQueryInformationPolicy` at `0x180027821`
- `LSASRV!LsarQueryInformationPolicy` at `0x1800278ab`
- `LSASRV!LsarQueryInformationPolicy` at `0x180027a24`
- `LSASRV!LsarQueryInformationPolicy` at `0x180027821`
- `LSASRV!LsarQueryInformationPolicy` at `0x1800278ab`
- `LSASRV!LsarQueryInformationPolicy` at `0x180027a24`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180027796`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180027796`
- `ntdll!RtlGetNtProductType` at `0x1800277d4`
- `ntdll!RtlGetNtProductType` at `0x1800277d4`
- `ntdll!RtlLengthSid` at `0x180027858`
- `ntdll!RtlLengthSid` at `0x180027ab1`
- `ntdll!RtlLengthSid` at `0x180027858`
- `ntdll!RtlLengthSid` at `0x180027ab1`
- `netutils!NetApiBufferFree` at `0x18002795d`
- `netutils!NetApiBufferFree` at `0x18002795d`
- `SAMSRV!SampDsIsRunning` at `0x1800277fc`
- `SAMSRV!SampDsIsRunning` at `0x1800277fc`

## string_xrefs

- `0x1800277af`: `NlGetDomainName: Can't LsaIOpenPolicyTrusted: 0x%lx.\n`
- `0x1800279dd`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`

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
    dword_1800F824C = 0;
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
    NlAssertFailed("NT_SUCCESS(Status)", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\domain.cxx", 0x1B5u, v23);
  return v18;
}

```

## disassembly

```asm
0x180027748  mov     [rsp-40h+arg_18], r9
0x18002774d  mov     [rsp-40h+arg_8], rdx
0x180027752  push    rbp
0x180027753  push    rbx
0x180027754  push    rsi
0x180027755  push    rdi
0x180027756  push    r12
0x180027758  push    r13
0x18002775a  push    r14
0x18002775c  push    r15
0x18002775e  mov     rbp, rsp
0x180027761  sub     rsp, 38h
0x180027765  mov     r15, [rbp+arg_20]
0x180027769  xor     esi, esi
0x18002776b  mov     r13, rcx
0x18002776e  mov     [rcx], rsi
0x180027771  lea     rcx, [rbp+var_10]
0x180027775  mov     [rbp+arg_10], rsi
0x180027779  mov     r14, r9
0x18002777c  mov     [rbp+var_18], rsi
0x180027780  mov     [r15], rsi
0x180027783  mov     r12, r8
0x180027786  mov     [rbp+var_10], rsi
0x18002778a  mov     [rbp+ProductType], esi
0x18002778d  mov     [rdx], rsi
0x180027790  mov     [r8], rsi
0x180027793  mov     [r9], rsi
0x180027796  call    cs:__imp_LsaIOpenPolicyTrusted
0x18002779d  nop     dword ptr [rax+rax+00h]
0x1800277a2  mov     ebx, eax
0x1800277a4  test    eax, eax
0x1800277a6  jns     short loc_1800277D0
0x1800277a8  mov     r8d, eax
0x1800277ab  mov     byte ptr [rbp+arg_20], sil
0x1800277af  lea     rdx, aNlgetdomainnam_1; "NlGetDomainName: Can't LsaIOpenPolicyTr"...
0x1800277b6  mov     ecx, 100h; unsigned int
0x1800277bb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800277c0  mov     ecx, ebx; Status
0x1800277c2  call    NetpNtStatusToApiStatus
0x1800277c7  lea     r8d, [rsi+1]
0x1800277cb  jmp     loc_180027A54
0x1800277d0  lea     rcx, [rbp+ProductType]; ProductType
0x1800277d4  call    cs:__imp_RtlGetNtProductType
0x1800277db  nop     dword ptr [rax+rax+00h]
0x1800277e0  mov     edi, 1
0x1800277e5  test    al, al
0x1800277e7  jnz     short loc_1800277F0
0x1800277e9  mov     eax, edi
0x1800277eb  mov     [rbp+ProductType], eax
0x1800277ee  jmp     short loc_1800277F3
0x1800277f0  mov     eax, [rbp+ProductType]
0x1800277f3  cmp     eax, 2
0x1800277f6  jnz     loc_18002789A
0x1800277fc  call    cs:__imp_SampDsIsRunning
0x180027803  nop     dword ptr [rax+rax+00h]
0x180027808  test    al, al
0x18002780a  jnz     loc_18002789A
0x180027810  mov     rcx, [rbp+var_10]
0x180027814  lea     r8, [rbp+var_18]
0x180027818  mov     edx, 0Eh
0x18002781d  mov     byte ptr [rbp+arg_20], dil
0x180027821  call    cs:__imp_LsarQueryInformationPolicy
0x180027828  nop     dword ptr [rax+rax+00h]
0x18002782d  mov     ebx, eax
0x18002782f  test    eax, eax
0x180027831  jns     short loc_18002783F
0x180027833  lea     rdx, aNlgetdomainnam_2; "NlGetDomainName: Can't LsarQueryInforma"...
0x18002783a  jmp     loc_180027A3D
0x18002783f  mov     rcx, [rbp+var_18]
0x180027843  movzx   eax, word ptr [rcx]
0x180027846  sub     ax, di
0x180027849  cmp     ax, 1Dh
0x18002784d  ja      short loc_180027891
0x18002784f  mov     rcx, [rcx+10h]; Sid
0x180027853  test    rcx, rcx
0x180027856  jz      short loc_180027891
0x180027858  call    cs:__imp_RtlLengthSid
0x18002785f  nop     dword ptr [rax+rax+00h]
0x180027864  mov     edx, eax; uBytes
0x180027866  xor     ecx, ecx; uFlags
0x180027868  mov     ebx, eax
0x18002786a  call    cs:__imp_LocalAlloc
0x180027871  nop     dword ptr [rax+rax+00h]
0x180027876  mov     [r12], rax
0x18002787a  test    rax, rax
0x18002787d  jnz     loc_180027A04
0x180027883  mov     ebx, 8
0x180027888  mov     edx, ebx
0x18002788a  mov     ecx, 0BEEh
0x18002788f  jmp     short loc_180027900
0x180027891  lea     rdx, aLocalAccountDo; "Local Account domain info from LSA inva"...
0x180027898  jmp     short loc_1800278ED
0x18002789a  mov     rcx, [rbp+var_10]
0x18002789e  lea     r8, [rbp+var_18]
0x1800278a2  mov     edx, 5
0x1800278a7  mov     byte ptr [rbp+arg_20], sil
0x1800278ab  call    cs:__imp_LsarQueryInformationPolicy
0x1800278b2  nop     dword ptr [rax+rax+00h]
0x1800278b7  mov     ebx, eax
0x1800278b9  test    eax, eax
0x1800278bb  jns     short loc_1800278C9
0x1800278bd  lea     rdx, aNlgetdomainnam; "NlGetDomainName: Can't LsarQueryInforma"...
0x1800278c4  jmp     loc_180027A3D
0x1800278c9  mov     rcx, [rbp+var_18]
0x1800278cd  movzx   eax, word ptr [rcx]
0x1800278d0  sub     ax, di
0x1800278d3  cmp     ax, 1Dh
0x1800278d7  ja      short loc_1800278E6
0x1800278d9  mov     rcx, [rcx+10h]
0x1800278dd  test    rcx, rcx
0x1800278e0  jnz     loc_180027858
0x1800278e6  lea     rdx, aAccountDomainI; "Account domain info from LSA invalid.\n"
0x1800278ed  mov     ecx, 100h; unsigned int
0x1800278f2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800278f7  mov     ebx, 0C17h
0x1800278fc  xor     edx, edx
0x1800278fe  mov     ecx, ebx
0x180027900  mov     r8d, edi
0x180027903  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180027908  mov     rcx, [r14]; hMem
0x18002790b  test    rcx, rcx
0x18002790e  jz      short loc_18002791F
0x180027910  call    cs:__imp_LocalFree
0x180027917  nop     dword ptr [rax+rax+00h]
0x18002791c  mov     [r14], rsi
0x18002791f  mov     rcx, [r12]; hMem
0x180027923  test    rcx, rcx
0x180027926  jz      short loc_180027938
0x180027928  call    cs:__imp_LocalFree
0x18002792f  nop     dword ptr [rax+rax+00h]
0x180027934  mov     [r12], rsi
0x180027938  mov     rcx, [r13+0]; hMem
0x18002793c  test    rcx, rcx
0x18002793f  jz      short loc_180027951
0x180027941  call    cs:__imp_LocalFree
0x180027948  nop     dword ptr [rax+rax+00h]
0x18002794d  mov     [r13+0], rsi
0x180027951  mov     rdi, [rbp+arg_8]
0x180027955  mov     rcx, [rdi]; Buffer
0x180027958  test    rcx, rcx
0x18002795b  jz      short loc_18002796C
0x18002795d  call    cs:__imp_NetApiBufferFree
0x180027964  nop     dword ptr [rax+rax+00h]
0x180027969  mov     [rdi], rsi
0x18002796c  mov     rcx, [r15]; hMem
0x18002796f  test    rcx, rcx
0x180027972  jz      short loc_180027983
0x180027974  call    cs:__imp_LocalFree
0x18002797b  nop     dword ptr [rax+rax+00h]
0x180027980  mov     [r15], rsi
0x180027983  mov     rdx, [rbp+var_18]
0x180027987  test    rdx, rdx
0x18002798a  jz      short loc_1800279A3
0x18002798c  neg     byte ptr [rbp+arg_20]
0x18002798f  sbb     ecx, ecx
0x180027991  and     ecx, 9
0x180027994  add     ecx, 5
0x180027997  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x18002799e  nop     dword ptr [rax+rax+00h]
0x1800279a3  mov     rdx, [rbp+arg_10]
0x1800279a7  test    rdx, rdx
0x1800279aa  jz      short loc_1800279BD
0x1800279ac  mov     ecx, 0Ch
0x1800279b1  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x1800279b8  nop     dword ptr [rax+rax+00h]
0x1800279bd  cmp     [rbp+var_10], rsi
0x1800279c1  jz      short loc_1800279F0
0x1800279c3  lea     rcx, [rbp+var_10]
0x1800279c7  call    cs:__imp_LsarClose
0x1800279ce  nop     dword ptr [rax+rax+00h]
0x1800279d3  test    eax, eax
0x1800279d5  jns     short loc_1800279F0
0x1800279d7  mov     r8d, 1B5h; unsigned int
0x1800279dd  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800279e4  lea     rcx, aNtSuccessStatu_4; "NT_SUCCESS(Status)"
0x1800279eb  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800279f0  mov     eax, ebx
0x1800279f2  add     rsp, 38h
0x1800279f6  pop     r15
0x1800279f8  pop     r14
0x1800279fa  pop     r13
0x1800279fc  pop     r12
0x1800279fe  pop     rdi
0x1800279ff  pop     rsi
0x180027a00  pop     rbx
0x180027a01  pop     rbp
0x180027a02  retn
0x180027a04  mov     rdx, [rbp+var_18]
0x180027a08  mov     r8, rbx; Size
0x180027a0b  mov     rcx, rax; void *
0x180027a0e  mov     rdx, [rdx+10h]; Src
0x180027a12  call    memcpy_0
0x180027a17  mov     rcx, [rbp+var_10]
0x180027a1b  lea     r8, [rbp+arg_10]
0x180027a1f  mov     edx, 0Ch
0x180027a24  call    cs:__imp_LsarQueryInformationPolicy
0x180027a2b  nop     dword ptr [rax+rax+00h]
0x180027a30  mov     ebx, eax
0x180027a32  test    eax, eax
0x180027a34  jns     short loc_180027A6F
0x180027a36  lea     rdx, aNlgetdomainnam_0; "NlGetDomainName: Can't LsarQueryInforma"...
0x180027a3d  mov     r8d, ebx
0x180027a40  mov     ecx, 100h; unsigned int
0x180027a45  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180027a4a  mov     ecx, ebx; Status
0x180027a4c  call    NetpNtStatusToApiStatus
0x180027a51  mov     r8d, edi
0x180027a54  mov     edx, eax
0x180027a56  mov     ecx, 15E2h
0x180027a5b  mov     ebx, eax
0x180027a5d  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180027a62  test    ebx, ebx
0x180027a64  jz      loc_180027983
0x180027a6a  jmp     loc_180027908
0x180027a6f  mov     rcx, [rbp+arg_10]
0x180027a73  movzx   eax, word ptr [rcx]
0x180027a76  sub     ax, di
0x180027a79  cmp     ax, 1Dh
0x180027a7d  ja      loc_180027C42
0x180027a83  mov     rax, [rcx+40h]
0x180027a87  test    rax, rax
0x180027a8a  jz      loc_180027C42
0x180027a90  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x180027a96  jnz     short loc_180027AAE
0x180027a98  movzx   eax, word ptr [rcx+10h]
0x180027a9c  mov     edx, 1FDh
0x180027aa1  sub     ax, di
0x180027aa4  cmp     ax, dx
0x180027aa7  jbe     short loc_180027AF2
0x180027aa9  jmp     loc_1800278F7
0x180027aae  mov     rcx, rax; Sid
0x180027ab1  call    cs:__imp_RtlLengthSid
0x180027ab8  nop     dword ptr [rax+rax+00h]
0x180027abd  mov     edx, eax; uBytes
0x180027abf  xor     ecx, ecx; uFlags
0x180027ac1  mov     ebx, eax
0x180027ac3  call    cs:__imp_LocalAlloc
0x180027aca  nop     dword ptr [rax+rax+00h]
0x180027acf  mov     [r14], rax
0x180027ad2  test    rax, rax
0x180027ad5  jz      loc_180027883
0x180027adb  mov     rdx, [rbp+arg_10]
0x180027adf  mov     r8d, ebx; Size
0x180027ae2  mov     rcx, rax; void *
0x180027ae5  mov     rdx, [rdx+40h]; Src
0x180027ae9  call    memcpy_0
0x180027aee  mov     rcx, [rbp+arg_10]
0x180027af2  movzx   edx, word ptr [rcx]
0x180027af5  xor     ecx, ecx; uFlags
0x180027af7  add     rdx, 2; uBytes
0x180027afb  call    cs:__imp_LocalAlloc
0x180027b02  nop     dword ptr [rax+rax+00h]
0x180027b07  mov     [r13+0], rax
0x180027b0b  mov     rbx, rax
0x180027b0e  test    rax, rax
0x180027b11  jz      loc_180027883
0x180027b17  mov     rdx, [rbp+arg_10]
0x180027b1b  mov     rcx, rax; void *
0x180027b1e  movzx   r8d, word ptr [rdx]; Size
0x180027b22  mov     rdx, [rdx+8]; Src
0x180027b26  call    memcpy_0
0x180027b2b  mov     rax, [rbp+arg_10]
0x180027b2f  movzx   ecx, word ptr [rax]
0x180027b32  shr     rcx, 1
0x180027b35  mov     [rbx+rcx*2], si
0x180027b39  mov     rcx, [rbp+arg_10]
0x180027b3d  movzx   ebx, word ptr [rcx+10h]
0x180027b41  shr     ebx, 1
0x180027b43  jz      short loc_180027BBB
0x180027b45  lea     edx, [rbx+2]
0x180027b48  xor     ecx, ecx; uFlags
0x180027b4a  add     rdx, rdx; uBytes
0x180027b4d  call    cs:__imp_LocalAlloc
0x180027b54  nop     dword ptr [rax+rax+00h]
0x180027b59  mov     rsi, rax
0x180027b5c  mov     rax, [rbp+arg_8]
0x180027b60  mov     [rax], rsi
0x180027b63  test    rsi, rsi
0x180027b66  jnz     short loc_180027B7F
0x180027b68  lea     ebx, [rsi+8]
0x180027b6b  mov     r8d, edi
0x180027b6e  mov     edx, ebx
0x180027b70  mov     ecx, 0BEEh
0x180027b75  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180027b7a  jmp     loc_180027908
0x180027b7f  mov     rdx, [rbp+arg_10]
0x180027b83  lea     r14, [rbx+rbx]
0x180027b87  mov     r8, r14; Size
0x180027b8a  mov     rcx, rsi; void *
0x180027b8d  mov     rdx, [rdx+18h]; Src
0x180027b91  call    memcpy_0
0x180027b96  lea     ecx, [rbx-1]
0x180027b99  mov     eax, 2Eh ; '.'
0x180027b9e  cmp     [rsi+rcx*2], ax
0x180027ba2  jz      short loc_180027BAB
0x180027ba4  mov     [r14+rsi], ax
0x180027ba9  inc     ebx
0x180027bab  mov     r14, [rbp+arg_18]
0x180027baf  xor     eax, eax
0x180027bb1  mov     [rsi+rbx*2], ax
  ... truncated ...
```
