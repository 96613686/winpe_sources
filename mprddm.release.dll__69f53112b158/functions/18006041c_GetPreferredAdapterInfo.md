# GetPreferredAdapterInfo

- ea: `0x18006041c`
- end: `0x180060766`
- name: `GetPreferredAdapterInfo`
- size: `842`
- prototype: `__int64 __usercall@<rax>(unsigned int *@<rcx>, unsigned int *@<rdx>, __int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800580c0`
- `0x18005f264`
- `0x18005f9a0`
- `0x18005ff60`

## callees

- `0x18005efac`
- `0x18006041c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006051c`
- `KERNEL32!LocalFree` at `0x180060734`
- `KERNEL32!LocalFree` at `0x18006051c`
- `KERNEL32!LocalFree` at `0x180060734`
- `KERNEL32!CompareStringA` at `0x180060681`
- `KERNEL32!CompareStringA` at `0x180060681`
- `KERNEL32!GetLastError` at `0x18006060d`
- `KERNEL32!GetLastError` at `0x18006060d`
- `KERNEL32!LocalAlloc` at `0x1800604ce`
- `KERNEL32!LocalAlloc` at `0x1800604ce`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180060502`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180060556`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180060502`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180060556`

## pseudocode

```c
__int64 __fastcall GetPreferredAdapterInfo(
        unsigned int *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int8 *a6)
{
  IP_ADAPTER_ADDRESSES_LH *v8; // rbx
  IP_ADAPTER_ADDRESSES_LH *v9; // r14
  __int64 v10; // rsi
  unsigned int i; // r15d
  IP_ADAPTER_ADDRESSES_LH *v12; // rax
  ULONG v13; // edi
  ULONG AdaptersAddresses; // eax
  __int64 v15; // r8
  const wchar_t *v16; // rdx
  DWORD LastError; // eax
  IP_ADAPTER_ADDRESSES_LH *v18; // rax
  unsigned int *v20; // [rsp+30h] [rbp-D0h]
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *v22; // [rsp+48h] [rbp-B8h]
  unsigned int *v23; // [rsp+50h] [rbp-B0h]
  unsigned int *v24; // [rsp+58h] [rbp-A8h]
  unsigned int *v25; // [rsp+60h] [rbp-A0h]
  int v26; // [rsp+70h] [rbp-90h] BYREF
  char v27[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v23 = a5;
  v25 = a3;
  v8 = 0;
  LODWORD(uBytes) = 0;
  v26 = 0;
  v22 = a6;
  v9 = 0;
  v24 = a4;
  v10 = -1;
  memset_0(v27, 0, sizeof(v27));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"GetPreferredAdapterInfo");
  for ( i = 1; ; ++i )
  {
    AdaptersAddresses = GetAdaptersAddresses(2u, 0xC6u, 0, 0, (PULONG)&uBytes);
    v13 = AdaptersAddresses;
    if ( AdaptersAddresses != 111 )
    {
      if ( !(_QWORD)xmmword_1800D0740 )
        goto LABEL_12;
      v15 = AdaptersAddresses;
      v16 = L"GetAdaptersAddresses call to query buffer size returns %d instead of ERROR_BUFFER_OVERFLOW";
      goto LABEL_11;
    }
    v12 = (IP_ADAPTER_ADDRESSES_LH *)LocalAlloc(0x40u, (unsigned int)uBytes);
    v10 = (__int64)v12;
    if ( !v12 )
      break;
    v8 = v12;
    v13 = GetAdaptersAddresses(2u, 0xC6u, 0, v12, (PULONG)&uBytes);
    if ( v13 != 111 || (LocalFree(v8), v8 = 0, LODWORD(uBytes) = 0, i > 3) )
    {
      v10 = (__int64)v8;
      goto LABEL_12;
    }
    v10 = 0;
  }
  LastError = GetLastError();
  v13 = LastError;
  if ( (_QWORD)xmmword_1800D0740 )
  {
    v15 = LastError;
    v16 = L"Unable to allocate memory for the GetAdaptersAddresses buffer: %d";
LABEL_11:
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, v16, v15);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v26);
  }
LABEL_12:
  if ( v13 )
  {
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, L"GetAdaptersAddresses fails with %d\n", v13);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v26);
    }
  }
  else
  {
    while ( v8 )
    {
      if ( ((v8->ConnectionType - 1) & 0xFFFFFFFD) == 0 && v8->OperStatus == IfOperStatusUp )
      {
        v18 = v8;
        if ( v9 )
          v18 = v9;
        v9 = v18;
        if ( !HIDWORD(qword_1800D08F0) || CompareStringA(0x7Fu, 1u, MultiByteStr, -1, v8->AdapterName, -1) == 2 )
          goto LABEL_29;
      }
      v8 = v8->Next;
    }
    if ( !HIDWORD(qword_1800D08F0) || !v9 )
    {
      v13 = 1168;
      goto LABEL_33;
    }
    v8 = v9;
LABEL_29:
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, L"Selecting %d as the preferred adapter", v8->IfIndex);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v26);
    }
    GetAdapterAddressInfo(v8, a1, a2, v25, v24, v23, v20, v22);
  }
LABEL_33:
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    LocalFree((HLOCAL)v10);
  return v13;
}

```

## disassembly

```asm
0x18006041c  push    rbp
0x18006041e  push    rbx
0x18006041f  push    rsi
0x180060420  push    rdi
0x180060421  push    r12
0x180060423  push    r13
0x180060425  push    r14
0x180060427  push    r15
0x180060429  lea     rbp, [rsp-788h]
0x180060431  sub     rsp, 888h
0x180060438  mov     rax, cs:__security_cookie
0x18006043f  xor     rax, rsp
0x180060442  mov     [rbp+7C0h+var_50], rax
0x180060449  mov     rax, [rbp+7C0h+arg_20]
0x180060450  mov     r13, rdx
0x180060453  mov     [rsp+8C0h+var_870], rax
0x180060458  mov     r12, rcx
0x18006045b  mov     rax, [rbp+7C0h+arg_28]
0x180060462  lea     rcx, [rsp+8C0h+var_84C]; void *
0x180060467  mov     [rsp+8C0h+var_860], r8
0x18006046c  xor     ebx, ebx
0x18006046e  and     dword ptr [rsp+8C0h+uBytes], ebx
0x180060472  xor     edx, edx; Val
0x180060474  and     [rsp+8C0h+var_850], ebx
0x180060478  mov     r8d, 7FCh; Size
0x18006047e  mov     [rsp+8C0h+var_878], rax
0x180060483  xor     r14d, r14d
0x180060486  mov     [rsp+8C0h+var_868], r9
0x18006048b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006048f  call    memset_0
0x180060494  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18006049b  test    rdx, rdx
0x18006049e  jz      short loc_1800604BA
0x1800604a0  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800604a7  lea     r8, aGetpreferredad; "GetPreferredAdapterInfo"
0x1800604ae  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800604b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604ba  mov     r15d, 1
0x1800604c0  xor     r9d, r9d
0x1800604c3  jmp     short loc_180060540
0x1800604c5  mov     edx, dword ptr [rsp+8C0h+uBytes]; uBytes
0x1800604c9  mov     ecx, 40h ; '@'; uFlags
0x1800604ce  call    cs:__imp_LocalAlloc
0x1800604d5  nop     dword ptr [rax+rax+00h]
0x1800604da  mov     rsi, rax
0x1800604dd  test    rax, rax
0x1800604e0  jz      loc_18006060D
0x1800604e6  mov     rbx, rax
0x1800604e9  xor     r8d, r8d; Reserved
0x1800604ec  lea     rax, [rsp+8C0h+uBytes]
0x1800604f1  mov     r9, rbx; AdapterAddresses
0x1800604f4  mov     edx, 0C6h; Flags
0x1800604f9  mov     [rsp+8C0h+SizePointer], rax; SizePointer
0x1800604fe  lea     ecx, [r8+2]; Family
0x180060502  call    cs:__imp_GetAdaptersAddresses
0x180060509  nop     dword ptr [rax+rax+00h]
0x18006050e  mov     edi, eax
0x180060510  cmp     eax, 6Fh ; 'o'
0x180060513  jnz     loc_180060605
0x180060519  mov     rcx, rbx; hMem
0x18006051c  call    cs:__imp_LocalFree
0x180060523  nop     dword ptr [rax+rax+00h]
0x180060528  xor     ebx, ebx
0x18006052a  and     dword ptr [rsp+8C0h+uBytes], ebx
0x18006052e  cmp     r15d, 3
0x180060532  ja      loc_180060605
0x180060538  mov     esi, ebx
0x18006053a  inc     r15d
0x18006053d  mov     r9d, ebx; AdapterAddresses
0x180060540  xor     r8d, r8d; Reserved
0x180060543  lea     rax, [rsp+8C0h+uBytes]
0x180060548  mov     edx, 0C6h; Flags
0x18006054d  mov     [rsp+8C0h+SizePointer], rax; SizePointer
0x180060552  lea     ecx, [r8+2]; Family
0x180060556  call    cs:__imp_GetAdaptersAddresses
0x18006055d  nop     dword ptr [rax+rax+00h]
0x180060562  mov     edi, eax
0x180060564  cmp     eax, 6Fh ; 'o'
0x180060567  jz      loc_1800604C5
0x18006056d  xor     r15d, r15d
0x180060570  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180060577  jz      short loc_1800605B2
0x180060579  mov     r8d, eax
0x18006057c  lea     rdx, aGetadaptersadd; "GetAdaptersAddresses call to query buff"...
0x180060583  lea     rcx, [rsp+8C0h+var_850]
0x180060588  mov     word ptr [rsp+8C0h+var_850], r15w
0x18006058e  call    FormatRRASErrorString
0x180060593  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18006059a  lea     r8, [rsp+8C0h+var_850]
0x18006059f  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800605a6  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800605ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800605b2  test    edi, edi
0x1800605b4  jz      loc_180060696
0x1800605ba  cmp     qword ptr cs:xmmword_1800D0740, r15
0x1800605c1  jz      loc_180060727
0x1800605c7  mov     r8d, edi
0x1800605ca  mov     word ptr [rsp+8C0h+var_850], r15w
0x1800605d0  lea     rdx, aGetadaptersadd_0; "GetAdaptersAddresses fails with %d\n"
0x1800605d7  lea     rcx, [rsp+8C0h+var_850]
0x1800605dc  call    FormatRRASErrorString
0x1800605e1  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800605e8  lea     r8, [rsp+8C0h+var_850]
0x1800605ed  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800605f4  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800605fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060600  jmp     loc_180060727
0x180060605  mov     rsi, rbx
0x180060608  xor     r15d, r15d
0x18006060b  jmp     short loc_1800605B2
0x18006060d  call    cs:__imp_GetLastError
0x180060614  nop     dword ptr [rax+rax+00h]
0x180060619  xor     r15d, r15d
0x18006061c  mov     edi, eax
0x18006061e  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180060625  jz      short loc_1800605B2
0x180060627  mov     r8d, eax
0x18006062a  lea     rdx, aUnableToAlloca; "Unable to allocate memory for the GetAd"...
0x180060631  jmp     loc_180060583
0x180060636  mov     eax, [rbx+10Ch]
0x18006063c  dec     eax
0x18006063e  test    eax, 0FFFFFFFDh
0x180060643  jnz     short loc_180060692
0x180060645  cmp     dword ptr [rbx+68h], 1
0x180060649  jnz     short loc_180060692
0x18006064b  test    r14, r14
0x18006064e  mov     rax, rbx
0x180060651  cmovnz  rax, r14
0x180060655  cmp     dword ptr cs:qword_1800D08F0+4, r15d
0x18006065c  mov     r14, rax
0x18006065f  jz      short loc_1800606AC
0x180060661  mov     rax, [rbx+10h]
0x180060665  lea     r8, MultiByteStr; lpString1
0x18006066c  or      dword ptr [rsp+8C0h+var_898], 0FFFFFFFFh
0x180060671  or      r9d, 0FFFFFFFFh; cchCount1
0x180060675  mov     [rsp+8C0h+SizePointer], rax; lpString2
0x18006067a  lea     edx, [r9+2]; dwCmpFlags
0x18006067e  lea     ecx, [rdx+7Eh]; Locale
0x180060681  call    cs:__imp_CompareStringA
0x180060688  nop     dword ptr [rax+rax+00h]
0x18006068d  cmp     eax, 2
0x180060690  jz      short loc_1800606AC
0x180060692  mov     rbx, [rbx+8]
0x180060696  test    rbx, rbx
0x180060699  jnz     short loc_180060636
0x18006069b  cmp     dword ptr cs:qword_1800D08F0+4, r15d
0x1800606a2  jz      short loc_180060722
0x1800606a4  test    r14, r14
0x1800606a7  jz      short loc_180060722
0x1800606a9  mov     rbx, r14
0x1800606ac  cmp     qword ptr cs:xmmword_1800D0740, r15
0x1800606b3  jz      short loc_1800606EF
0x1800606b5  mov     word ptr [rsp+8C0h+var_850], r15w
0x1800606bb  lea     rdx, aSelectingDAsTh; "Selecting %d as the preferred adapter"
0x1800606c2  mov     r8d, [rbx+4]
0x1800606c6  lea     rcx, [rsp+8C0h+var_850]
0x1800606cb  call    FormatRRASErrorString
0x1800606d0  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800606d7  lea     r8, [rsp+8C0h+var_850]
0x1800606dc  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800606e3  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800606ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800606ef  mov     rax, [rsp+8C0h+var_878]
0x1800606f4  mov     r8, r13; unsigned int *
0x1800606f7  mov     r9, [rsp+8C0h+var_860]; unsigned int *
0x1800606fc  mov     rdx, r12; unsigned int *
0x1800606ff  mov     [rsp+8C0h+var_888], rax; unsigned __int8 *
0x180060704  mov     rcx, rbx; struct _IP_ADAPTER_ADDRESSES_LH *
0x180060707  mov     rax, [rsp+8C0h+var_870]
0x18006070c  mov     [rsp+8C0h+var_898], rax; unsigned int *
0x180060711  mov     rax, [rsp+8C0h+var_868]
0x180060716  mov     [rsp+8C0h+SizePointer], rax; unsigned int *
0x18006071b  call    ?GetAdapterAddressInfo@@YAKPEAU_IP_ADAPTER_ADDRESSES_LH@@PEAK11111PEAE@Z; GetAdapterAddressInfo(_IP_ADAPTER_ADDRESSES_LH *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,uchar *)
0x180060720  jmp     short loc_180060727
0x180060722  mov     edi, 490h
0x180060727  lea     rax, [rsi-1]
0x18006072b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006072f  ja      short loc_180060740
0x180060731  mov     rcx, rsi; hMem
0x180060734  call    cs:__imp_LocalFree
0x18006073b  nop     dword ptr [rax+rax+00h]
0x180060740  mov     eax, edi
0x180060742  mov     rcx, [rbp+7C0h+var_50]
0x180060749  xor     rcx, rsp; StackCookie
0x18006074c  call    __security_check_cookie
0x180060751  add     rsp, 888h
0x180060758  pop     r15
0x18006075a  pop     r14
0x18006075c  pop     r13
0x18006075e  pop     r12
0x180060760  pop     rdi
0x180060761  pop     rsi
0x180060762  pop     rbx
0x180060763  pop     rbp
0x180060764  retn
```
