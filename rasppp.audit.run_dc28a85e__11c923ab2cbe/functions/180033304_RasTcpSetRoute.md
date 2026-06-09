# RasTcpSetRoute

- ea: `0x180033304`
- end: `0x18003371b`
- name: `RasTcpSetRoute`
- size: `1047`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032b1c`
- `0x180032fa4`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x18002d9fc`
- `0x18002dcfc`
- `0x18003230c`
- `0x180032358`
- `0x180033304`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800336eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800336eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800334c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800334c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334df`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x18003364e`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x18003364e`

## pseudocode

```c
__int64 __fastcall RasTcpSetRoute(DWORD a1, DWORD a2, DWORD a3, int a4, int a5)
{
  int v5; // ebx
  __int64 v9; // rcx
  DWORD RoutingDomainIdForCompartment; // ebx
  const char *v11; // rax
  const char *v12; // rax
  HANDLE ProcessHeap; // rax
  __int64 v14; // rdx
  void *v15; // rsi
  DWORD LastError; // eax
  DWORD IpAddrTable; // eax
  void *v18; // rdi
  __int64 i; // rcx
  DWORD v20; // eax
  const char *v22; // [rsp+30h] [rbp-D0h]
  const char *v23; // [rsp+38h] [rbp-C8h]
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  _MIB_IPFORWARDROW pRoute; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v27[2]; // [rsp+98h] [rbp-68h] BYREF
  int v28; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v29; // [rsp+BCh] [rbp-44h]
  __int128 v30; // [rsp+CCh] [rbp-34h]
  int v31; // [rsp+DCh] [rbp-24h]
  int v32; // [rsp+E0h] [rbp-20h] BYREF
  char v33[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v5 = a4;
  memset(&pRoute, 0, sizeof(pRoute));
  lpMem = 0;
  memset(v27, 0, sizeof(v27));
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  v28 = 0;
  v29 = 0;
  v31 = 0;
  v30 = 0;
  if ( qword_18004D640 || qword_18004D648 || qword_18004D650 )
  {
    RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(v9, v27);
    if ( RoutingDomainIdForCompartment )
      return RoutingDomainIdForCompartment;
    v5 = a4;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004D658 )
    {
      v11 = "Add";
      LOWORD(v32) = 0;
      if ( !a5 )
        v11 = "Del";
      LOWORD(v28) = 0;
      FormatRRASErrorString(
        &v32,
        L"RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, NextHop: 0x%x, Intf: 0x%x, %d, %hs, %hs)",
        a1,
        a3,
        a2,
        v5,
        1,
        v11,
        "Stack");
      ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        qword_18004D658,
        &v32,
        v27,
        0,
        &v28);
    }
  }
  else
  {
    v12 = "Add";
    if ( !a5 )
      v12 = "Del";
    v23 = "Stack";
    v22 = v12;
    TraceHlp("RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, NextHop: 0x%x, Intf: 0x%x, %d, %hs, %hs)");
  }
  memset(&pRoute, 0, sizeof(pRoute));
  ProcessHeap = GetProcessHeap();
  v15 = ProcessHeap;
  if ( ProcessHeap )
  {
    IpAddrTable = AllocateAndGetIpAddrTable(&lpMem, v14, ProcessHeap);
    v18 = lpMem;
    RoutingDomainIdForCompartment = IpAddrTable;
    if ( IpAddrTable )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( qword_18004D650 )
        {
          LOWORD(v32) = 0;
          LOWORD(v28) = 0;
          FormatRRASErrorString(&v32, L"AllocateAndGetIpAddrTable failed and returned %d", IpAddrTable);
LABEL_35:
          ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            qword_18004D650,
            &v32,
            v27,
            0,
            &v28,
            v22,
            v23);
        }
      }
      else
      {
        TraceHlp("AllocateAndGetIpAddrTable failed and returned %d");
      }
    }
    else
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)lpMem; i = (unsigned int)(i + 1) )
      {
        if ( a4 == *((_DWORD *)lpMem + 6 * i + 1) )
        {
          pRoute.dwForwardDest = a1;
          pRoute.dwForwardPolicy = 0;
          pRoute.dwForwardMask = a3;
          pRoute.dwForwardNextHop = a2;
          pRoute.dwForwardIfIndex = *((_DWORD *)lpMem + 6 * i + 2);
          pRoute.dwForwardProto = 3;
          pRoute.dwForwardAge = -1;
          pRoute.dwForwardNextHopAS = 0;
          pRoute.dwForwardMetric1 = 1;
          *(__m128i *)&pRoute.dwForwardMetric2 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
          if ( a5 )
          {
            pRoute.dwForwardType = 3;
            v20 = CreateOrSetIpForwardEntry(&pRoute);
          }
          else
          {
            pRoute.dwForwardType = 2;
            v20 = DeleteIpForwardEntry(&pRoute);
          }
          RoutingDomainIdForCompartment = v20;
          if ( !v20 )
            break;
          if ( !gIsIphlpEtwTracingAvailable )
          {
            TraceHlp("SetIpForwardEntry%hs failed and returned 0x%x");
            break;
          }
          if ( !qword_18004D650 )
            break;
          LOWORD(v32) = 0;
          LOWORD(v28) = 0;
          FormatRRASErrorString(&v32, L"SetIpForwardEntry%hs failed and returned 0x%x", "ToStack", v20);
          goto LABEL_35;
        }
      }
    }
    if ( v18 )
      HeapFree(v15, 0, v18);
  }
  else
  {
    LastError = GetLastError();
    RoutingDomainIdForCompartment = LastError;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004D650 )
      {
        LOWORD(v32) = 0;
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v32, L"GetProcessHeap failed and returned %d", LastError);
        ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          qword_18004D650,
          &v32,
          v27,
          0,
          &v28,
          v22,
          v23);
      }
    }
    else
    {
      TraceHlp("GetProcessHeap failed and returned %d");
    }
  }
  return RoutingDomainIdForCompartment;
}

```

## disassembly

```asm
0x180033304  push    rbp
0x180033306  push    rbx
0x180033307  push    rsi
0x180033308  push    rdi
0x180033309  push    r12
0x18003330b  push    r13
0x18003330d  push    r15
0x18003330f  lea     rbp, [rsp-7F0h]
0x180033317  sub     rsp, 8F0h
0x18003331e  mov     rax, cs:__security_cookie
0x180033325  xor     rax, rsp
0x180033328  mov     [rbp+820h+var_40], rax
0x18003332f  xorps   xmm0, xmm0
0x180033332  mov     ebx, r9d
0x180033335  movups  xmmword ptr [rsp+920h+pRoute.dwForwardDest], xmm0
0x18003333a  mov     r13d, r8d
0x18003333d  mov     r12d, edx
0x180033340  movups  xmmword ptr [rsp+920h+pRoute.dwForwardIfIndex], xmm0
0x180033345  mov     r15d, ecx
0x180033348  xor     edi, edi
0x18003334a  movups  xmmword ptr [rbp+820h+pRoute.dwForwardNextHopAS], xmm0
0x18003334e  xor     eax, eax
0x180033350  xor     edx, edx; Val
0x180033352  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180033359  mov     r8d, 7FCh; Size
0x18003335f  mov     [rsp+920h+var_8D0], ebx
0x180033363  lea     rcx, [rbp+820h+var_83C]; void *
0x180033367  mov     [rsp+920h+lpMem], rdi
0x18003336c  movdqu  [rbp+820h+var_888], xmm0
0x180033371  mov     qword ptr [rbp+820h+pRoute.dwForwardMetric4], rax
0x180033375  mov     [rbp+820h+var_840], edi
0x180033378  call    memset_0
0x18003337d  xorps   xmm0, xmm0
0x180033380  mov     [rbp+820h+var_868], edi
0x180033383  xor     eax, eax
0x180033385  cmp     cs:qword_18004D640, rdi
0x18003338c  movups  [rbp+820h+var_864], xmm0
0x180033390  mov     [rbp+820h+var_844], eax
0x180033393  movups  [rbp+820h+var_854], xmm0
0x180033397  movups  [rbp+820h+var_878], xmm0
0x18003339b  jnz     short loc_1800333AF
0x18003339d  cmp     cs:qword_18004D648, rdi
0x1800333a4  jnz     short loc_1800333AF
0x1800333a6  cmp     cs:qword_18004D650, rdi
0x1800333ad  jz      short loc_1800333C6
0x1800333af  lea     rdx, [rbp+820h+var_888]
0x1800333b3  call    NsiGetRoutingDomainIdForCompartment
0x1800333b8  mov     ebx, eax
0x1800333ba  test    eax, eax
0x1800333bc  jnz     loc_1800336F7
0x1800333c2  mov     ebx, [rsp+920h+var_8D0]
0x1800333c6  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x1800333cc  mov     edx, 1
0x1800333d1  jz      loc_18003346A
0x1800333d7  cmp     cs:qword_18004D658, rdi
0x1800333de  jz      loc_1800334B0
0x1800333e4  cmp     [rbp+820h+arg_20], edi
0x1800333ea  lea     rcx, aDel; "Del"
0x1800333f1  lea     rax, aAdd; "Add"
0x1800333f8  mov     word ptr [rbp+820h+var_840], di
0x1800333fc  cmovz   rax, rcx
0x180033400  mov     word ptr [rbp+820h+var_868], di
0x180033404  lea     rcx, aStack; "Stack"
0x18003340b  mov     r9d, r13d
0x18003340e  mov     [rsp+920h+var_8E0], rcx
0x180033413  mov     r8d, r15d
0x180033416  mov     [rsp+920h+var_8E8], rax
0x18003341b  lea     rcx, [rbp+820h+var_840]
0x18003341f  mov     dword ptr [rsp+920h+var_8F0], edx
0x180033423  lea     rdx, aRastcpsetroute_2; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x18003342a  mov     dword ptr [rsp+920h+var_8F8], ebx
0x18003342e  mov     dword ptr [rsp+920h+var_900], r12d
0x180033433  call    FormatRRASErrorString
0x180033438  mov     rdx, cs:qword_18004D658
0x18003343f  lea     rax, [rbp+820h+var_868]
0x180033443  mov     rcx, cs:gIphlpEtwContext
0x18003344a  lea     r9, [rbp+820h+var_888]
0x18003344e  mov     [rsp+920h+var_8F8], rax
0x180033453  lea     r8, [rbp+820h+var_840]
0x180033457  mov     rax, cs:gIphlpParamTemplateFunc
0x18003345e  mov     [rsp+920h+var_900], rdi
0x180033463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033468  jmp     short loc_1800334B0
0x18003346a  cmp     [rbp+820h+arg_20], edi
0x180033470  lea     rcx, aDel; "Del"
0x180033477  lea     rax, aAdd; "Add"
0x18003347e  mov     r9d, r12d
0x180033481  cmovz   rax, rcx
0x180033485  mov     r8d, r13d
0x180033488  lea     rcx, aStack; "Stack"
0x18003348f  mov     [rsp+920h+var_8E8], rcx
0x180033494  lea     rcx, aRastcpsetroute_1; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x18003349b  mov     [rsp+920h+var_8F0], rax
0x1800334a0  mov     dword ptr [rsp+920h+var_8F8], edx
0x1800334a4  mov     edx, r15d
0x1800334a7  mov     dword ptr [rsp+920h+var_900], ebx
0x1800334ab  call    TraceHlp
0x1800334b0  xorps   xmm0, xmm0
0x1800334b3  xor     eax, eax
0x1800334b5  movups  xmmword ptr [rsp+920h+pRoute.dwForwardDest], xmm0
0x1800334ba  mov     qword ptr [rbp+820h+pRoute.dwForwardMetric4], rax
0x1800334be  movups  xmmword ptr [rsp+920h+pRoute.dwForwardIfIndex], xmm0
0x1800334c3  movups  xmmword ptr [rbp+820h+pRoute.dwForwardNextHopAS], xmm0
0x1800334c7  call    cs:__imp_GetProcessHeap
0x1800334ce  nop     dword ptr [rax+rax+00h]
0x1800334d3  mov     rsi, rax
0x1800334d6  test    rax, rax
0x1800334d9  jnz     loc_180033565
0x1800334df  call    cs:__imp_GetLastError
0x1800334e6  nop     dword ptr [rax+rax+00h]
0x1800334eb  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x1800334f1  mov     ebx, eax
0x1800334f3  jz      short loc_180033552
0x1800334f5  cmp     cs:qword_18004D650, rdi
0x1800334fc  jz      loc_1800336F7
0x180033502  mov     r8d, eax
0x180033505  mov     word ptr [rbp+820h+var_840], di
0x180033509  lea     rdx, aGetprocessheap; "GetProcessHeap failed and returned %d"
0x180033510  mov     word ptr [rbp+820h+var_868], di
0x180033514  lea     rcx, [rbp+820h+var_840]
0x180033518  call    FormatRRASErrorString
0x18003351d  mov     rdx, cs:qword_18004D650
0x180033524  lea     rax, [rbp+820h+var_868]
0x180033528  mov     rcx, cs:gIphlpEtwContext
0x18003352f  lea     r9, [rbp+820h+var_888]
0x180033533  mov     [rsp+920h+var_8F8], rax
0x180033538  lea     r8, [rbp+820h+var_840]
0x18003353c  mov     rax, cs:gIphlpParamTemplateFunc
0x180033543  mov     [rsp+920h+var_900], rdi
0x180033548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003354d  jmp     loc_1800336F7
0x180033552  mov     edx, eax
0x180033554  lea     rcx, aGetprocessheap_0; "GetProcessHeap failed and returned %d"
0x18003355b  call    TraceHlp
0x180033560  jmp     loc_1800336F7
0x180033565  mov     r8, rsi
0x180033568  lea     rcx, [rsp+920h+lpMem]
0x18003356d  call    AllocateAndGetIpAddrTable
0x180033572  mov     rdi, [rsp+920h+lpMem]
0x180033577  mov     ebx, eax
0x180033579  test    eax, eax
0x18003357b  jz      short loc_1800335CB
0x18003357d  xor     r15d, r15d
0x180033580  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180033587  jz      short loc_1800335B8
0x180033589  cmp     cs:qword_18004D650, r15
0x180033590  jz      loc_1800336DE
0x180033596  mov     r8d, eax
0x180033599  mov     word ptr [rbp+820h+var_840], r15w
0x18003359e  lea     rdx, aAllocateandget_16; "AllocateAndGetIpAddrTable failed and re"...
0x1800335a5  mov     word ptr [rbp+820h+var_868], r15w
0x1800335aa  lea     rcx, [rbp+820h+var_840]
0x1800335ae  call    FormatRRASErrorString
0x1800335b3  jmp     loc_180033696
0x1800335b8  mov     edx, eax
0x1800335ba  lea     rcx, aAllocateandget_6; "AllocateAndGetIpAddrTable failed and re"...
0x1800335c1  call    TraceHlp
0x1800335c6  jmp     loc_1800336DE
0x1800335cb  mov     edx, [rsp+920h+var_8D0]
0x1800335cf  xor     ecx, ecx
0x1800335d1  cmp     ecx, [rdi]
0x1800335d3  jnb     loc_1800336DE
0x1800335d9  lea     rax, [rcx+rcx*2]
0x1800335dd  cmp     edx, [rdi+rax*8+4]
0x1800335e1  jz      short loc_1800335E7
0x1800335e3  inc     ecx
0x1800335e5  jmp     short loc_1800335D1
0x1800335e7  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800335ef  lea     rcx, [rsp+920h+pRoute]; pRoute
0x1800335f4  mov     [rsp+920h+pRoute.dwForwardDest], r15d
0x1800335f9  xor     r15d, r15d
0x1800335fc  mov     [rsp+920h+pRoute.dwForwardPolicy], r15d
0x180033601  mov     [rsp+920h+pRoute.dwForwardMask], r13d
0x180033606  mov     [rsp+920h+pRoute.dwForwardNextHop], r12d
0x18003360b  mov     eax, [rdi+rax*8+8]
0x18003360f  mov     [rsp+920h+pRoute.dwForwardIfIndex], eax
0x180033613  lea     eax, [r15+3]
0x180033617  mov     dword ptr [rsp+920h+pRoute.18h], eax
0x18003361b  mov     [rsp+920h+pRoute.dwForwardAge], 0FFFFFFFFh
0x180033623  mov     [rbp+820h+pRoute.dwForwardNextHopAS], r15d
0x180033627  mov     [rbp+820h+pRoute.dwForwardMetric1], 1
0x18003362e  movups  xmmword ptr [rbp+820h+pRoute.dwForwardMetric2], xmm0
0x180033632  cmp     [rbp+820h+arg_20], r15d
0x180033639  jz      short loc_180033646
0x18003363b  mov     dword ptr [rsp+920h+pRoute.14h], eax
0x18003363f  call    CreateOrSetIpForwardEntry
0x180033644  jmp     short loc_18003365A
0x180033646  mov     dword ptr [rsp+920h+pRoute.14h], 2
0x18003364e  call    cs:__imp_DeleteIpForwardEntry
0x180033655  nop     dword ptr [rax+rax+00h]
0x18003365a  mov     ebx, eax
0x18003365c  test    eax, eax
0x18003365e  jz      short loc_1800336DE
0x180033660  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180033667  jz      short loc_1800336C8
0x180033669  cmp     cs:qword_18004D650, r15
0x180033670  jz      short loc_1800336DE
0x180033672  mov     r9d, eax
0x180033675  mov     word ptr [rbp+820h+var_840], r15w
0x18003367a  lea     r8, aTostack; "ToStack"
0x180033681  mov     word ptr [rbp+820h+var_868], r15w
0x180033686  lea     rdx, aSetipforwarden_1; "SetIpForwardEntry%hs failed and returne"...
0x18003368d  lea     rcx, [rbp+820h+var_840]
0x180033691  call    FormatRRASErrorString
0x180033696  mov     rdx, cs:qword_18004D650
0x18003369d  lea     rax, [rbp+820h+var_868]
0x1800336a1  mov     rcx, cs:gIphlpEtwContext
0x1800336a8  lea     r9, [rbp+820h+var_888]
0x1800336ac  mov     [rsp+920h+var_8F8], rax
0x1800336b1  lea     r8, [rbp+820h+var_840]
0x1800336b5  mov     rax, cs:gIphlpParamTemplateFunc
0x1800336bc  mov     [rsp+920h+var_900], r15
0x1800336c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336c6  jmp     short loc_1800336DE
0x1800336c8  mov     r8d, ebx
0x1800336cb  lea     rdx, aTostack; "ToStack"
0x1800336d2  lea     rcx, aSetipforwarden_0; "SetIpForwardEntry%hs failed and returne"...
0x1800336d9  call    TraceHlp
0x1800336de  test    rdi, rdi
0x1800336e1  jz      short loc_1800336F7
0x1800336e3  mov     r8, rdi; lpMem
0x1800336e6  xor     edx, edx; dwFlags
0x1800336e8  mov     rcx, rsi; hHeap
0x1800336eb  call    cs:__imp_HeapFree
0x1800336f2  nop     dword ptr [rax+rax+00h]
0x1800336f7  mov     eax, ebx
0x1800336f9  mov     rcx, [rbp+820h+var_40]
0x180033700  xor     rcx, rsp; StackCookie
0x180033703  call    __security_check_cookie
0x180033708  add     rsp, 8F0h
0x18003370f  pop     r15
0x180033711  pop     r13
0x180033713  pop     r12
0x180033715  pop     rdi
0x180033716  pop     rsi
0x180033717  pop     rbx
0x180033718  pop     rbp
0x180033719  retn
```
