# RasTcpSetRoute

- ea: `0x1800692b4`
- end: `0x1800696ef`
- name: `RasTcpSetRoute`
- size: `1083`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053230`
- `0x1800564e0`

## callees

- `0x1800682f8`
- `0x1800692b4`
- `0x180069984`
- `0x180071cec`
- `0x1800753dc`
- `0x1800759b8`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18006949c`
- `KERNEL32!GetProcessHeap` at `0x18006949c`
- `KERNEL32!GetLastError` at `0x1800694ae`
- `KERNEL32!GetLastError` at `0x1800694ae`
- `KERNEL32!HeapFree` at `0x1800696c6`
- `KERNEL32!HeapFree` at `0x1800696c6`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x180069626`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x180069626`

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
  __int64 v23; // rcx
  DWORD v24; // eax
  const char *v26; // [rsp+30h] [rbp-D0h]
  const char *v27; // [rsp+38h] [rbp-C8h]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h]
  _MIB_IPFORWARDROW pRoute; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v31[2]; // [rsp+98h] [rbp-68h] BYREF
  int v32; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v33; // [rsp+BCh] [rbp-44h]
  __int128 v34; // [rsp+CCh] [rbp-34h]
  int v35; // [rsp+DCh] [rbp-24h]
  int v36; // [rsp+E0h] [rbp-20h] BYREF
  char v37[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  memset(&pRoute, 0, sizeof(pRoute));
  v29 = a9;
  lpMem = 0;
  memset(v31, 0, sizeof(v31));
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  if ( unk_1800CA080
    || __PAIR128__(xmmword_1800CA088, 0) != *((unsigned __int64 *)&xmmword_1800CA088 + 1)
    || (v12 = unk_1800CA098) != 0 && a8 != 1 )
  {
    RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(a8, v31);
    if ( RoutingDomainIdForCompartment )
      return RoutingDomainIdForCompartment;
    v12 = unk_1800CA098;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v12 )
    {
      LOWORD(v36) = 0;
      v14 = "Add";
      LOWORD(v32) = 0;
      if ( !a5 )
        v14 = "Del";
      FormatRRASErrorString(
        &v36,
        L"RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, NextHop: 0x%x, Intf: 0x%x, %d, %hs, %hs)",
        a1,
        0xFFFFFFFFLL,
        a2,
        a4,
        1,
        v14,
        "Stack");
      ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        unk_1800CA098,
        &v36,
        v31,
        0,
        &v32);
    }
  }
  else
  {
    v15 = "Add";
    if ( !a5 )
      v15 = "Del";
    v27 = "Stack";
    v26 = v15;
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
      if ( *((_QWORD *)&xmmword_1800CA088 + 1) )
      {
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString(&v36, L"GetProcessHeap failed and returned %d", LastError);
        ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_1800CA088 + 1),
          &v36,
          v31,
          0,
          &v32,
          v26,
          v27);
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
      goto LABEL_38;
    }
    if ( !*((_QWORD *)&xmmword_1800CA088 + 1) )
      goto LABEL_38;
    LOWORD(v36) = 0;
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v36, L"AllocateAndGetIpAddrTable failed and returned %d", IpAddrTable);
LABEL_36:
    ((void (__fastcall *)(__int64, _QWORD, int *, _OWORD *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
      gIphlpEtwContext,
      *((_QWORD *)&xmmword_1800CA088 + 1),
      &v36,
      v31,
      0,
      &v32,
      v26,
      v27);
    goto LABEL_38;
  }
  v23 = 0;
  if ( !*(_DWORD *)lpMem )
    goto LABEL_38;
  while ( a4 != *((_DWORD *)lpMem + 6 * v23 + 1) )
  {
    v23 = (unsigned int)(v23 + 1);
    if ( (unsigned int)v23 >= *(_DWORD *)lpMem )
      goto LABEL_38;
  }
  pRoute.dwForwardMask = -1;
  pRoute.dwForwardDest = a1;
  pRoute.dwForwardPolicy = 0;
  pRoute.dwForwardNextHop = a2;
  pRoute.dwForwardIfIndex = *((_DWORD *)lpMem + 6 * v23 + 2);
  pRoute.dwForwardAge = -1;
  pRoute.dwForwardProto = 3;
  pRoute.dwForwardNextHopAS = 0;
  pRoute.dwForwardMetric1 = 1;
  *(__m128i *)&pRoute.dwForwardMetric2 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( a5 )
  {
    pRoute.dwForwardType = 3;
    v24 = CreateOrSetIpForwardEntry(&pRoute, v29);
  }
  else
  {
    pRoute.dwForwardType = 2;
    v24 = DeleteIpForwardEntry(&pRoute);
  }
  RoutingDomainIdForCompartment = v24;
  if ( !v24 )
    goto LABEL_38;
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( !*((_QWORD *)&xmmword_1800CA088 + 1) )
      goto LABEL_38;
    LOWORD(v36) = 0;
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v36, L"SetIpForwardEntry%hs failed and returned 0x%x", "ToStack", v24);
    goto LABEL_36;
  }
  TraceHlp("SetIpForwardEntry%hs failed and returned 0x%x");
LABEL_38:
  if ( v22 )
    HeapFree(v19, 0, v22);
  return RoutingDomainIdForCompartment;
}

```

## disassembly

```asm
0x1800692b4  push    rbp
0x1800692b6  push    rbx
0x1800692b7  push    rsi
0x1800692b8  push    rdi
0x1800692b9  push    r12
0x1800692bb  push    r13
0x1800692bd  push    r15
0x1800692bf  lea     rbp, [rsp-7F0h]
0x1800692c7  sub     rsp, 8F0h
0x1800692ce  mov     rax, cs:__security_cookie
0x1800692d5  xor     rax, rsp
0x1800692d8  mov     [rbp+820h+var_40], rax
0x1800692df  mov     rax, [rbp+820h+arg_40]
0x1800692e6  xorps   xmm0, xmm0
0x1800692e9  movups  xmmword ptr [rsp+920h+pRoute.dwForwardDest], xmm0
0x1800692ee  mov     [rsp+920h+var_8C8], rax
0x1800692f3  mov     r12d, edx
0x1800692f6  movups  xmmword ptr [rsp+920h+pRoute.dwForwardIfIndex], xmm0
0x1800692fb  mov     r15d, ecx
0x1800692fe  xor     esi, esi
0x180069300  movups  xmmword ptr [rbp+820h+pRoute.dwForwardNextHopAS], xmm0
0x180069304  xor     eax, eax
0x180069306  xor     edx, edx; Val
0x180069308  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006930f  mov     r8d, 7FCh; Size
0x180069315  mov     [rsp+920h+lpMem], rsi
0x18006931a  lea     rcx, [rbp+820h+var_83C]; void *
0x18006931e  mov     qword ptr [rbp+820h+pRoute.dwForwardMetric4], rax
0x180069322  movdqu  [rbp+820h+var_888], xmm0
0x180069327  mov     r13d, r9d
0x18006932a  mov     [rbp+820h+var_840], esi
0x18006932d  call    memset_0
0x180069332  mov     edi, [rbp+820h+arg_38]
0x180069338  xorps   xmm0, xmm0
0x18006933b  xor     eax, eax
0x18006933d  mov     [rbp+820h+var_868], esi
0x180069340  cmp     qword ptr cs:unk_1800CA080, rsi
0x180069347  movups  [rbp+820h+var_864], xmm0
0x18006934b  mov     [rbp+820h+var_844], eax
0x18006934e  movups  [rbp+820h+var_854], xmm0
0x180069352  movups  [rbp+820h+var_878], xmm0
0x180069356  jnz     short loc_18006937B
0x180069358  cmp     qword ptr cs:xmmword_1800CA088, rsi
0x18006935f  jnz     short loc_18006937B
0x180069361  cmp     qword ptr cs:xmmword_1800CA088+8, rsi
0x180069368  jnz     short loc_18006937B
0x18006936a  mov     rax, qword ptr cs:unk_1800CA098
0x180069371  test    rax, rax
0x180069374  jz      short loc_180069397
0x180069376  cmp     edi, 1
0x180069379  jz      short loc_180069397
0x18006937b  lea     rdx, [rbp+820h+var_888]
0x18006937f  mov     ecx, edi
0x180069381  call    NsiGetRoutingDomainIdForCompartment
0x180069386  mov     ebx, eax
0x180069388  test    eax, eax
0x18006938a  jnz     loc_1800696CC
0x180069390  mov     rax, qword ptr cs:unk_1800CA098
0x180069397  or      edx, 0FFFFFFFFh
0x18006939a  cmp     cs:gIsIphlpEtwTracingAvailable, esi
0x1800693a0  jz      loc_18006943A
0x1800693a6  test    rax, rax
0x1800693a9  jz      loc_180069485
0x1800693af  cmp     [rbp+820h+arg_20], esi
0x1800693b5  lea     rcx, aDel; "Del"
0x1800693bc  mov     r9d, edx
0x1800693bf  mov     word ptr [rbp+820h+var_840], si
0x1800693c3  lea     rax, aAdd; "Add"
0x1800693ca  mov     word ptr [rbp+820h+var_868], si
0x1800693ce  cmovz   rax, rcx
0x1800693d2  lea     rdx, aRastcpsetroute_2; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x1800693d9  lea     rcx, aStack; "Stack"
0x1800693e0  mov     r8d, r15d
0x1800693e3  mov     [rsp+920h+var_8E0], rcx
0x1800693e8  lea     rcx, [rbp+820h+var_840]
0x1800693ec  mov     [rsp+920h+var_8E8], rax
0x1800693f1  mov     dword ptr [rsp+920h+var_8F0], 1
0x1800693f9  mov     dword ptr [rsp+920h+var_8F8], r13d
0x1800693fe  mov     dword ptr [rsp+920h+var_900], r12d
0x180069403  call    FormatRRASErrorString
0x180069408  mov     rdx, qword ptr cs:unk_1800CA098
0x18006940f  lea     rax, [rbp+820h+var_868]
0x180069413  mov     rcx, cs:gIphlpEtwContext
0x18006941a  lea     r9, [rbp+820h+var_888]
0x18006941e  mov     [rsp+920h+var_8F8], rax
0x180069423  lea     r8, [rbp+820h+var_840]
0x180069427  mov     rax, cs:gIphlpParamTemplateFunc
0x18006942e  mov     [rsp+920h+var_900], rsi
0x180069433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069438  jmp     short loc_180069485
0x18006943a  cmp     [rbp+820h+arg_20], esi
0x180069440  lea     rcx, aDel; "Del"
0x180069447  mov     r8d, edx
0x18006944a  lea     rax, aAdd; "Add"
0x180069451  cmovz   rax, rcx
0x180069455  mov     r9d, r12d
0x180069458  lea     rcx, aStack; "Stack"
0x18006945f  mov     edx, r15d
0x180069462  mov     [rsp+920h+var_8E8], rcx
0x180069467  lea     rcx, aRastcpsetroute_1; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x18006946e  mov     [rsp+920h+var_8F0], rax
0x180069473  mov     dword ptr [rsp+920h+var_8F8], 1
0x18006947b  mov     dword ptr [rsp+920h+var_900], r13d
0x180069480  call    TraceHlp
0x180069485  xorps   xmm0, xmm0
0x180069488  xor     eax, eax
0x18006948a  movups  xmmword ptr [rsp+920h+pRoute.dwForwardDest], xmm0
0x18006948f  mov     qword ptr [rbp+820h+pRoute.dwForwardMetric4], rax
0x180069493  movups  xmmword ptr [rsp+920h+pRoute.dwForwardIfIndex], xmm0
0x180069498  movups  xmmword ptr [rbp+820h+pRoute.dwForwardNextHopAS], xmm0
0x18006949c  call    cs:__imp_GetProcessHeap
0x1800694a2  mov     rsi, rax
0x1800694a5  test    rax, rax
0x1800694a8  jnz     loc_180069530
0x1800694ae  call    cs:__imp_GetLastError
0x1800694b4  xor     edi, edi
0x1800694b6  mov     ebx, eax
0x1800694b8  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x1800694be  jz      short loc_18006951D
0x1800694c0  cmp     qword ptr cs:xmmword_1800CA088+8, rdi
0x1800694c7  jz      loc_1800696CC
0x1800694cd  mov     r8d, eax
0x1800694d0  mov     word ptr [rbp+820h+var_840], di
0x1800694d4  lea     rdx, aGetprocessheap; "GetProcessHeap failed and returned %d"
0x1800694db  mov     word ptr [rbp+820h+var_868], di
0x1800694df  lea     rcx, [rbp+820h+var_840]
0x1800694e3  call    FormatRRASErrorString
0x1800694e8  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x1800694ef  lea     rax, [rbp+820h+var_868]
0x1800694f3  mov     rcx, cs:gIphlpEtwContext
0x1800694fa  lea     r9, [rbp+820h+var_888]
0x1800694fe  mov     [rsp+920h+var_8F8], rax
0x180069503  lea     r8, [rbp+820h+var_840]
0x180069507  mov     rax, cs:gIphlpParamTemplateFunc
0x18006950e  mov     [rsp+920h+var_900], rdi
0x180069513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069518  jmp     loc_1800696CC
0x18006951d  mov     edx, eax
0x18006951f  lea     rcx, aGetprocessheap_0; "GetProcessHeap failed and returned %d"
0x180069526  call    TraceHlp
0x18006952b  jmp     loc_1800696CC
0x180069530  mov     r8, rsi
0x180069533  mov     dword ptr [rsp+920h+var_900], edi
0x180069537  lea     rcx, [rsp+920h+lpMem]
0x18006953c  call    AllocateAndGetIpAddrTable
0x180069541  mov     rdi, [rsp+920h+lpMem]
0x180069546  mov     ebx, eax
0x180069548  test    eax, eax
0x18006954a  jz      short loc_180069598
0x18006954c  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180069553  jz      short loc_180069585
0x180069555  cmp     qword ptr cs:xmmword_1800CA088+8, 0
0x18006955d  jz      loc_1800696B9
0x180069563  xor     eax, eax
0x180069565  lea     rdx, aAllocateandget_8; "AllocateAndGetIpAddrTable failed and re"...
0x18006956c  mov     r8d, ebx
0x18006956f  mov     word ptr [rbp+820h+var_840], ax
0x180069573  lea     rcx, [rbp+820h+var_840]
0x180069577  mov     word ptr [rbp+820h+var_868], ax
0x18006957b  call    FormatRRASErrorString
0x180069580  jmp     loc_18006966D
0x180069585  mov     edx, ebx
0x180069587  lea     rcx, aAllocateandget_2; "AllocateAndGetIpAddrTable failed and re"...
0x18006958e  call    TraceHlp
0x180069593  jmp     loc_1800696B9
0x180069598  xor     ecx, ecx
0x18006959a  cmp     [rdi], ecx
0x18006959c  jbe     loc_1800696B9
0x1800695a2  lea     rax, [rcx+rcx*2]
0x1800695a6  cmp     r13d, [rdi+rax*8+4]
0x1800695ab  jz      short loc_1800695B8
0x1800695ad  inc     ecx
0x1800695af  cmp     ecx, [rdi]
0x1800695b1  jb      short loc_1800695A2
0x1800695b3  jmp     loc_1800696B9
0x1800695b8  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800695c0  or      ecx, 0FFFFFFFFh
0x1800695c3  cmp     [rbp+820h+arg_20], 0
0x1800695ca  mov     [rsp+920h+pRoute.dwForwardMask], ecx
0x1800695ce  mov     [rsp+920h+pRoute.dwForwardDest], r15d
0x1800695d3  mov     [rsp+920h+pRoute.dwForwardPolicy], 0
0x1800695db  mov     [rsp+920h+pRoute.dwForwardNextHop], r12d
0x1800695e0  mov     eax, [rdi+rax*8+8]
0x1800695e4  mov     [rsp+920h+pRoute.dwForwardIfIndex], eax
0x1800695e8  mov     eax, 3
0x1800695ed  mov     [rsp+920h+pRoute.dwForwardAge], ecx
0x1800695f1  lea     rcx, [rsp+920h+pRoute]; pRoute
0x1800695f6  mov     dword ptr [rsp+920h+pRoute.18h], eax
0x1800695fa  mov     [rbp+820h+pRoute.dwForwardNextHopAS], 0
0x180069601  mov     [rbp+820h+pRoute.dwForwardMetric1], 1
0x180069608  movups  xmmword ptr [rbp+820h+pRoute.dwForwardMetric2], xmm0
0x18006960c  jz      short loc_18006961E
0x18006960e  mov     rdx, [rsp+920h+var_8C8]
0x180069613  mov     dword ptr [rsp+920h+pRoute.14h], eax
0x180069617  call    CreateOrSetIpForwardEntry
0x18006961c  jmp     short loc_18006962C
0x18006961e  mov     dword ptr [rsp+920h+pRoute.14h], 2
0x180069626  call    cs:__imp_DeleteIpForwardEntry
0x18006962c  mov     ebx, eax
0x18006962e  test    eax, eax
0x180069630  jz      loc_1800696B9
0x180069636  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x18006963d  jz      short loc_1800696A3
0x18006963f  cmp     qword ptr cs:xmmword_1800CA088+8, 0
0x180069647  jz      short loc_1800696B9
0x180069649  xor     eax, eax
0x18006964b  lea     r8, aTostack; "ToStack"
0x180069652  mov     r9d, ebx
0x180069655  mov     word ptr [rbp+820h+var_840], ax
0x180069659  lea     rdx, aSetipforwarden_0; "SetIpForwardEntry%hs failed and returne"...
0x180069660  mov     word ptr [rbp+820h+var_868], ax
0x180069664  lea     rcx, [rbp+820h+var_840]
0x180069668  call    FormatRRASErrorString
0x18006966d  mov     rdx, qword ptr cs:xmmword_1800CA088+8
0x180069674  lea     rax, [rbp+820h+var_868]
0x180069678  mov     rcx, cs:gIphlpEtwContext
0x18006967f  lea     r9, [rbp+820h+var_888]
0x180069683  mov     [rsp+920h+var_8F8], rax
0x180069688  lea     r8, [rbp+820h+var_840]
0x18006968c  mov     rax, cs:gIphlpParamTemplateFunc
0x180069693  mov     [rsp+920h+var_900], 0
0x18006969c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696a1  jmp     short loc_1800696B9
0x1800696a3  mov     r8d, ebx
0x1800696a6  lea     rdx, aTostack; "ToStack"
0x1800696ad  lea     rcx, aSetipforwarden; "SetIpForwardEntry%hs failed and returne"...
0x1800696b4  call    TraceHlp
0x1800696b9  test    rdi, rdi
0x1800696bc  jz      short loc_1800696CC
0x1800696be  mov     r8, rdi; lpMem
0x1800696c1  xor     edx, edx; dwFlags
0x1800696c3  mov     rcx, rsi; hHeap
0x1800696c6  call    cs:__imp_HeapFree
0x1800696cc  mov     eax, ebx
0x1800696ce  mov     rcx, [rbp+820h+var_40]
0x1800696d5  xor     rcx, rsp; StackCookie
0x1800696d8  call    __security_check_cookie
0x1800696dd  add     rsp, 8F0h
0x1800696e4  pop     r15
0x1800696e6  pop     r13
0x1800696e8  pop     r12
0x1800696ea  pop     rdi
0x1800696eb  pop     rsi
0x1800696ec  pop     rbx
0x1800696ed  pop     rbp
0x1800696ee  retn
```
