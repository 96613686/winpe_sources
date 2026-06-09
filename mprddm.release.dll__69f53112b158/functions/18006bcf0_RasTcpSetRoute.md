# RasTcpSetRoute

- ea: `0x18006bcf0`
- end: `0x18006c122`
- name: `RasTcpSetRoute`
- size: `1074`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054d50`
- `0x1800582b0`

## callees

- `0x18006ac5c`
- `0x18006bcf0`
- `0x18006c3c4`
- `0x1800755b8`
- `0x18007919c`
- `0x180079774`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18006bec3`
- `KERNEL32!GetProcessHeap` at `0x18006bec3`
- `KERNEL32!GetLastError` at `0x18006bedb`
- `KERNEL32!GetLastError` at `0x18006bedb`
- `KERNEL32!HeapFree` at `0x18006c0f2`
- `KERNEL32!HeapFree` at `0x18006c0f2`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x18006c053`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x18006c053`

## pseudocode

```c
__int64 __fastcall RasTcpSetRoute(
        DWORD a1,
        DWORD a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        NET_IF_COMPARTMENT_ID a8,
        __int64 a9)
{
  __int64 v12; // rax
  DWORD RoutingDomainIdForCompartment; // ebx
  const char *v14; // rax
  const char *v15; // rax
  HANDLE ProcessHeap; // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  void *v19; // rsi
  DWORD LastError; // eax
  DWORD IpAddrTable; // eax
  void *v22; // rdi
  __int64 v23; // rax
  _DWORD *v24; // rcx
  DWORD v25; // eax
  const char *v27; // [rsp+30h] [rbp-D0h]
  const char *v28; // [rsp+38h] [rbp-C8h]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h]
  GUID v31; // [rsp+60h] [rbp-A0h] BYREF
  _MIB_IPFORWARDROW pRoute; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+A8h] [rbp-58h]
  int v34; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v35; // [rsp+BCh] [rbp-44h]
  __int128 v36; // [rsp+CCh] [rbp-34h]
  int v37; // [rsp+DCh] [rbp-24h]
  int v38; // [rsp+E0h] [rbp-20h] BYREF
  char v39[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v30 = a9;
  lpMem = 0;
  v38 = 0;
  v31 = GUID_NULL;
  memset_0(v39, 0, sizeof(v39));
  v34 = 0;
  v35 = 0;
  v37 = 0;
  v36 = 0;
  v33 = 0;
  if ( unk_1800D1080
    || __PAIR128__(xmmword_1800D1088, 0) != *((unsigned __int64 *)&xmmword_1800D1088 + 1)
    || (v12 = unk_1800D1098) != 0 && a8 != 1 )
  {
    RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(a8, &v31);
    if ( RoutingDomainIdForCompartment )
      return RoutingDomainIdForCompartment;
    v12 = unk_1800D1098;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v12 )
    {
      LOWORD(v38) = 0;
      v14 = "Add";
      LOWORD(v34) = 0;
      if ( !a5 )
        v14 = "Del";
      FormatRRASErrorString(
        &v38,
        L"RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, NextHop: 0x%x, Intf: 0x%x, %d, %hs, %hs)",
        a1,
        0xFFFFFFFFLL,
        a2,
        a4,
        1,
        v14,
        "Stack");
      ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        unk_1800D1098,
        &v38,
        &v31,
        0,
        &v34);
    }
  }
  else
  {
    v15 = "Add";
    if ( !a5 )
      v15 = "Del";
    v28 = "Stack";
    v27 = v15;
    TraceHlp("RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, NextHop: 0x%x, Intf: 0x%x, %d, %hs, %hs)");
  }
  memset(&pRoute, 0, sizeof(pRoute));
  ProcessHeap = GetProcessHeap();
  v19 = ProcessHeap;
  if ( !ProcessHeap )
  {
    LastError = GetLastError();
    RoutingDomainIdForCompartment = LastError;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800D1088 + 1) )
      {
        LOWORD(v38) = 0;
        LOWORD(v34) = 0;
        FormatRRASErrorString(&v38, L"GetProcessHeap failed and returned %d", LastError);
        ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800D1088 + 1),
          &v38,
          &v31,
          0,
          &v34,
          v27,
          v28);
      }
    }
    else
    {
      TraceHlp("GetProcessHeap failed and returned %d");
    }
    return RoutingDomainIdForCompartment;
  }
  IpAddrTable = AllocateAndGetIpAddrTable(&lpMem, v17, ProcessHeap, v18, a8);
  v22 = lpMem;
  RoutingDomainIdForCompartment = IpAddrTable;
  if ( IpAddrTable )
  {
    if ( !gIsIphlpEtwTracingAvailable )
    {
      TraceHlp("AllocateAndGetIpAddrTable failed and returned %d");
      goto LABEL_39;
    }
    if ( !*((_QWORD *)&xmmword_1800D1088 + 1) )
      goto LABEL_39;
    LOWORD(v38) = 0;
    LOWORD(v34) = 0;
    FormatRRASErrorString(&v38, L"AllocateAndGetIpAddrTable failed and returned %d", IpAddrTable);
LABEL_37:
    ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
      gIphlpEtwContext,
      *((_QWORD *)&xmmword_1800D1088 + 1),
      &v38,
      &v31,
      0,
      &v34,
      v27,
      v28);
    goto LABEL_39;
  }
  v23 = 0;
  if ( !*(_DWORD *)lpMem )
    goto LABEL_39;
  v24 = (char *)lpMem + 4;
  while ( a4 != *v24 )
  {
    v23 = (unsigned int)(v23 + 1);
    v24 += 6;
    if ( (unsigned int)v23 >= *(_DWORD *)lpMem )
      goto LABEL_39;
  }
  pRoute.dwForwardDest = a1;
  pRoute.dwForwardMask = -1;
  pRoute.dwForwardPolicy = 0;
  pRoute.dwForwardNextHop = a2;
  pRoute.dwForwardIfIndex = *((_DWORD *)lpMem + 6 * v23 + 2);
  pRoute.dwForwardProto = 3;
  pRoute.dwForwardAge = -1;
  pRoute.dwForwardNextHopAS = 0;
  pRoute.dwForwardMetric1 = 1;
  *(__m128i *)&pRoute.dwForwardMetric2 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( a5 )
  {
    pRoute.dwForwardType = 3;
    v25 = CreateOrSetIpForwardEntry(&pRoute, v30);
  }
  else
  {
    pRoute.dwForwardType = 2;
    v25 = DeleteIpForwardEntry(&pRoute);
  }
  RoutingDomainIdForCompartment = v25;
  if ( !v25 )
    goto LABEL_39;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( !*((_QWORD *)&xmmword_1800D1088 + 1) )
      goto LABEL_39;
    LOWORD(v38) = 0;
    LOWORD(v34) = 0;
    FormatRRASErrorString(&v38, L"SetIpForwardEntry%hs failed and returned 0x%x", "ToStack", v25);
    goto LABEL_37;
  }
  TraceHlp("SetIpForwardEntry%hs failed and returned 0x%x");
LABEL_39:
  if ( v22 )
    HeapFree(v19, 0, v22);
  return RoutingDomainIdForCompartment;
}

```

## disassembly

```asm
0x18006bcf0  push    rbp
0x18006bcf2  push    rbx
0x18006bcf3  push    rsi
0x18006bcf4  push    rdi
0x18006bcf5  push    r12
0x18006bcf7  push    r13
0x18006bcf9  push    r15
0x18006bcfb  lea     rbp, [rsp-7F0h]
0x18006bd03  sub     rsp, 8F0h
0x18006bd0a  mov     rax, cs:__security_cookie
0x18006bd11  xor     rax, rsp
0x18006bd14  mov     [rbp+820h+var_40], rax
0x18006bd1b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006bd22  mov     rax, [rbp+820h+arg_40]
0x18006bd29  mov     r13d, edx
0x18006bd2c  mov     r12d, ecx
0x18006bd2f  mov     [rsp+920h+var_8C8], rax
0x18006bd34  xor     esi, esi
0x18006bd36  lea     rcx, [rbp+820h+var_83C]; void *
0x18006bd3a  xor     edx, edx; Val
0x18006bd3c  mov     [rsp+920h+lpMem], rsi
0x18006bd41  mov     r8d, 7FCh; Size
0x18006bd47  mov     [rbp+820h+var_840], esi
0x18006bd4a  movdqu  [rsp+920h+var_8C0], xmm0
0x18006bd50  mov     r15d, r9d
0x18006bd53  call    memset_0
0x18006bd58  mov     edi, [rbp+820h+arg_38]
0x18006bd5e  xorps   xmm0, xmm0
0x18006bd61  xor     eax, eax
0x18006bd63  mov     [rbp+820h+var_868], esi
0x18006bd66  cmp     qword ptr cs:unk_1800D1080, rsi
0x18006bd6d  movups  [rbp+820h+var_864], xmm0
0x18006bd71  mov     [rbp+820h+var_844], eax
0x18006bd74  movups  [rbp+820h+var_854], xmm0
0x18006bd78  movups  [rbp+820h+var_878], xmm0
0x18006bd7c  jnz     short loc_18006BDA1
0x18006bd7e  cmp     qword ptr cs:xmmword_1800D1088, rsi
0x18006bd85  jnz     short loc_18006BDA1
0x18006bd87  cmp     qword ptr cs:xmmword_1800D1088+8, rsi
0x18006bd8e  jnz     short loc_18006BDA1
0x18006bd90  mov     rax, qword ptr cs:unk_1800D1098
0x18006bd97  test    rax, rax
0x18006bd9a  jz      short loc_18006BDBE
0x18006bd9c  cmp     edi, 1
0x18006bd9f  jz      short loc_18006BDBE
0x18006bda1  lea     rdx, [rsp+920h+var_8C0]
0x18006bda6  mov     ecx, edi
0x18006bda8  call    NsiGetRoutingDomainIdForCompartment
0x18006bdad  mov     ebx, eax
0x18006bdaf  test    eax, eax
0x18006bdb1  jnz     loc_18006C0FE
0x18006bdb7  mov     rax, qword ptr cs:unk_1800D1098
0x18006bdbe  or      edx, 0FFFFFFFFh
0x18006bdc1  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x18006bdc7  jz      loc_18006BE62
0x18006bdcd  test    rax, rax
0x18006bdd0  jz      loc_18006BEAD
0x18006bdd6  cmp     [rbp+820h+arg_20], esi
0x18006bddc  lea     rcx, aDel; "Del"
0x18006bde3  mov     r9d, edx
0x18006bde6  mov     word ptr [rbp+820h+var_840], si
0x18006bdea  lea     rax, aAdd; "Add"
0x18006bdf1  mov     word ptr [rbp+820h+var_868], si
0x18006bdf5  cmovz   rax, rcx
0x18006bdf9  lea     rdx, aRastcpsetroute_2; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x18006be00  lea     rcx, aStack; "Stack"
0x18006be07  mov     r8d, r12d
0x18006be0a  mov     [rsp+920h+var_8E0], rcx
0x18006be0f  lea     rcx, [rbp+820h+var_840]
0x18006be13  mov     [rsp+920h+var_8E8], rax
0x18006be18  mov     dword ptr [rsp+920h+var_8F0], 1
0x18006be20  mov     dword ptr [rsp+920h+var_8F8], r15d
0x18006be25  mov     dword ptr [rsp+920h+var_900], r13d
0x18006be2a  call    FormatRRASErrorString
0x18006be2f  mov     rdx, qword ptr cs:unk_1800D1098
0x18006be36  lea     rax, [rbp+820h+var_868]
0x18006be3a  mov     rcx, cs:gIphlpEtwContext
0x18006be41  lea     r9, [rsp+920h+var_8C0]
0x18006be46  mov     [rsp+920h+var_8F8], rax
0x18006be4b  lea     r8, [rbp+820h+var_840]
0x18006be4f  mov     rax, cs:gIphlpParamTemplateFunc
0x18006be56  mov     [rsp+920h+var_900], rsi
0x18006be5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be60  jmp     short loc_18006BEAD
0x18006be62  cmp     [rbp+820h+arg_20], esi
0x18006be68  lea     rcx, aDel; "Del"
0x18006be6f  mov     r8d, edx
0x18006be72  lea     rax, aAdd; "Add"
0x18006be79  cmovz   rax, rcx
0x18006be7d  mov     r9d, r13d
0x18006be80  lea     rcx, aStack; "Stack"
0x18006be87  mov     edx, r12d
0x18006be8a  mov     [rsp+920h+var_8E8], rcx
0x18006be8f  lea     rcx, aRastcpsetroute_1; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x18006be96  mov     [rsp+920h+var_8F0], rax
0x18006be9b  mov     dword ptr [rsp+920h+var_8F8], 1
0x18006bea3  mov     dword ptr [rsp+920h+var_900], r15d
0x18006bea8  call    TraceHlp
0x18006bead  xorps   xmm0, xmm0
0x18006beb0  xor     eax, eax
0x18006beb2  movups  xmmword ptr [rsp+920h+pRoute.dwForwardDest], xmm0
0x18006beb7  mov     qword ptr [rbp+820h+pRoute.dwForwardMetric4], rax
0x18006bebb  movups  xmmword ptr [rbp+820h+pRoute.dwForwardIfIndex], xmm0
0x18006bebf  movups  xmmword ptr [rbp+820h+pRoute.dwForwardNextHopAS], xmm0
0x18006bec3  call    cs:__imp_GetProcessHeap
0x18006beca  nop     dword ptr [rax+rax+00h]
0x18006becf  mov     rsi, rax
0x18006bed2  test    rax, rax
0x18006bed5  jnz     loc_18006BF64
0x18006bedb  call    cs:__imp_GetLastError
0x18006bee2  nop     dword ptr [rax+rax+00h]
0x18006bee7  xor     edi, edi
0x18006bee9  mov     ebx, eax
0x18006beeb  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x18006bef1  jz      short loc_18006BF51
0x18006bef3  cmp     qword ptr cs:xmmword_1800D1088+8, rdi
0x18006befa  jz      loc_18006C0FE
0x18006bf00  mov     r8d, eax
0x18006bf03  mov     word ptr [rbp+820h+var_840], di
0x18006bf07  lea     rdx, aGetprocessheap; "GetProcessHeap failed and returned %d"
0x18006bf0e  mov     word ptr [rbp+820h+var_868], di
0x18006bf12  lea     rcx, [rbp+820h+var_840]
0x18006bf16  call    FormatRRASErrorString
0x18006bf1b  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006bf22  lea     rax, [rbp+820h+var_868]
0x18006bf26  mov     rcx, cs:gIphlpEtwContext
0x18006bf2d  lea     r9, [rsp+920h+var_8C0]
0x18006bf32  mov     [rsp+920h+var_8F8], rax
0x18006bf37  lea     r8, [rbp+820h+var_840]
0x18006bf3b  mov     rax, cs:gIphlpParamTemplateFunc
0x18006bf42  mov     [rsp+920h+var_900], rdi
0x18006bf47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf4c  jmp     loc_18006C0FE
0x18006bf51  mov     edx, eax
0x18006bf53  lea     rcx, aGetprocessheap_0; "GetProcessHeap failed and returned %d"
0x18006bf5a  call    TraceHlp
0x18006bf5f  jmp     loc_18006C0FE
0x18006bf64  mov     r8, rsi
0x18006bf67  mov     dword ptr [rsp+920h+var_900], edi
0x18006bf6b  lea     rcx, [rsp+920h+lpMem]
0x18006bf70  call    AllocateAndGetIpAddrTable
0x18006bf75  mov     rdi, [rsp+920h+lpMem]
0x18006bf7a  xor     edx, edx
0x18006bf7c  mov     ebx, eax
0x18006bf7e  test    eax, eax
0x18006bf80  jz      short loc_18006BFCA
0x18006bf82  cmp     cs:gIsIphlpEtwTracingAvailable, edx
0x18006bf88  jz      short loc_18006BFB7
0x18006bf8a  cmp     qword ptr cs:xmmword_1800D1088+8, rdx
0x18006bf91  jz      loc_18006C0E5
0x18006bf97  mov     word ptr [rbp+820h+var_840], dx
0x18006bf9b  lea     rcx, [rbp+820h+var_840]
0x18006bf9f  mov     word ptr [rbp+820h+var_868], dx
0x18006bfa3  mov     r8d, eax
0x18006bfa6  lea     rdx, aAllocateandget_8; "AllocateAndGetIpAddrTable failed and re"...
0x18006bfad  call    FormatRRASErrorString
0x18006bfb2  jmp     loc_18006C09A
0x18006bfb7  mov     edx, eax
0x18006bfb9  lea     rcx, aAllocateandget_2; "AllocateAndGetIpAddrTable failed and re"...
0x18006bfc0  call    TraceHlp
0x18006bfc5  jmp     loc_18006C0E5
0x18006bfca  mov     eax, edx
0x18006bfcc  cmp     [rdi], edx
0x18006bfce  jbe     loc_18006C0E5
0x18006bfd4  lea     rcx, [rdi+4]
0x18006bfd8  cmp     r15d, [rcx]
0x18006bfdb  jz      short loc_18006BFEC
0x18006bfdd  inc     eax
0x18006bfdf  add     rcx, 18h
0x18006bfe3  cmp     eax, [rdi]
0x18006bfe5  jb      short loc_18006BFD8
0x18006bfe7  jmp     loc_18006C0E5
0x18006bfec  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18006bff4  lea     rcx, [rax+rax*2]
0x18006bff8  or      r8d, 0FFFFFFFFh
0x18006bffc  mov     [rsp+920h+pRoute.dwForwardDest], r12d
0x18006c001  mov     [rsp+920h+pRoute.dwForwardMask], r8d
0x18006c006  mov     [rsp+920h+pRoute.dwForwardPolicy], edx
0x18006c00a  mov     [rsp+920h+pRoute.dwForwardNextHop], r13d
0x18006c00f  mov     eax, [rdi+rcx*8+8]
0x18006c013  lea     rcx, [rsp+920h+pRoute]; pRoute
0x18006c018  mov     [rbp+820h+pRoute.dwForwardIfIndex], eax
0x18006c01b  mov     eax, 3
0x18006c020  mov     dword ptr [rbp+820h+pRoute.18h], eax
0x18006c023  mov     [rbp+820h+pRoute.dwForwardAge], r8d
0x18006c027  mov     [rbp+820h+pRoute.dwForwardNextHopAS], edx
0x18006c02a  mov     [rbp+820h+pRoute.dwForwardMetric1], 1
0x18006c031  movups  xmmword ptr [rbp+820h+pRoute.dwForwardMetric2], xmm0
0x18006c035  cmp     [rbp+820h+arg_20], edx
0x18006c03b  jz      short loc_18006C04C
0x18006c03d  mov     rdx, [rsp+920h+var_8C8]
0x18006c042  mov     dword ptr [rbp+820h+pRoute.14h], eax
0x18006c045  call    CreateOrSetIpForwardEntry
0x18006c04a  jmp     short loc_18006C05F
0x18006c04c  mov     dword ptr [rbp+820h+pRoute.14h], 2
0x18006c053  call    cs:__imp_DeleteIpForwardEntry
0x18006c05a  nop     dword ptr [rax+rax+00h]
0x18006c05f  xor     edx, edx
0x18006c061  mov     ebx, eax
0x18006c063  test    eax, eax
0x18006c065  jz      short loc_18006C0E5
0x18006c067  cmp     cs:gIsIphlpEtwTracingAvailable, edx
0x18006c06d  jz      short loc_18006C0CF
0x18006c06f  cmp     qword ptr cs:xmmword_1800D1088+8, rdx
0x18006c076  jz      short loc_18006C0E5
0x18006c078  mov     word ptr [rbp+820h+var_840], dx
0x18006c07c  lea     r8, aTostack; "ToStack"
0x18006c083  mov     word ptr [rbp+820h+var_868], dx
0x18006c087  lea     rcx, [rbp+820h+var_840]
0x18006c08b  lea     rdx, aSetipforwarden_0; "SetIpForwardEntry%hs failed and returne"...
0x18006c092  mov     r9d, eax
0x18006c095  call    FormatRRASErrorString
0x18006c09a  mov     rdx, qword ptr cs:xmmword_1800D1088+8
0x18006c0a1  lea     rax, [rbp+820h+var_868]
0x18006c0a5  mov     rcx, cs:gIphlpEtwContext
0x18006c0ac  lea     r9, [rsp+920h+var_8C0]
0x18006c0b1  mov     [rsp+920h+var_8F8], rax
0x18006c0b6  lea     r8, [rbp+820h+var_840]
0x18006c0ba  xor     eax, eax
0x18006c0bc  mov     [rsp+920h+var_900], rax
0x18006c0c1  mov     rax, cs:gIphlpParamTemplateFunc
0x18006c0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0cd  jmp     short loc_18006C0E5
0x18006c0cf  mov     r8d, ebx
0x18006c0d2  lea     rdx, aTostack; "ToStack"
0x18006c0d9  lea     rcx, aSetipforwarden; "SetIpForwardEntry%hs failed and returne"...
0x18006c0e0  call    TraceHlp
0x18006c0e5  test    rdi, rdi
0x18006c0e8  jz      short loc_18006C0FE
0x18006c0ea  mov     r8, rdi; lpMem
0x18006c0ed  xor     edx, edx; dwFlags
0x18006c0ef  mov     rcx, rsi; hHeap
0x18006c0f2  call    cs:__imp_HeapFree
0x18006c0f9  nop     dword ptr [rax+rax+00h]
0x18006c0fe  mov     eax, ebx
0x18006c100  mov     rcx, [rbp+820h+var_40]
0x18006c107  xor     rcx, rsp; StackCookie
0x18006c10a  call    __security_check_cookie
0x18006c10f  add     rsp, 8F0h
0x18006c116  pop     r15
0x18006c118  pop     r13
0x18006c11a  pop     r12
0x18006c11c  pop     rdi
0x18006c11d  pop     rsi
0x18006c11e  pop     rbx
0x18006c11f  pop     rbp
0x18006c120  retn
```
