# RasTcpSetRoute

- ea: `0x180031d0c`
- end: `0x18003210a`
- name: `RasTcpSetRoute`
- size: `1022`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003153c`
- `0x1800319ac`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002c8dc`
- `0x18002cbb4`
- `0x180030da4`
- `0x180030de8`
- `0x180031d0c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800320e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800320e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ecf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031ee1`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x18003204a`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x18003204a`

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
  if ( qword_18004C640 || qword_18004C648 || qword_18004C650 )
  {
    RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(v9, v27);
    if ( RoutingDomainIdForCompartment )
      return RoutingDomainIdForCompartment;
    v5 = a4;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( qword_18004C658 )
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
        qword_18004C658,
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
        if ( qword_18004C650 )
        {
          LOWORD(v32) = 0;
          LOWORD(v28) = 0;
          FormatRRASErrorString(&v32, L"AllocateAndGetIpAddrTable failed and returned %d", IpAddrTable);
LABEL_35:
          ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            qword_18004C650,
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
          if ( !qword_18004C650 )
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
      if ( qword_18004C650 )
      {
        LOWORD(v32) = 0;
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v32, L"GetProcessHeap failed and returned %d", LastError);
        ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *, const char *, const char *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          qword_18004C650,
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
0x180031d0c  push    rbp
0x180031d0e  push    rbx
0x180031d0f  push    rsi
0x180031d10  push    rdi
0x180031d11  push    r12
0x180031d13  push    r13
0x180031d15  push    r15
0x180031d17  lea     rbp, [rsp-7F0h]
0x180031d1f  sub     rsp, 8F0h
0x180031d26  mov     rax, cs:__security_cookie
0x180031d2d  xor     rax, rsp
0x180031d30  mov     [rbp+820h+var_40], rax
0x180031d37  xorps   xmm0, xmm0
0x180031d3a  mov     ebx, r9d
0x180031d3d  movups  xmmword ptr [rsp+920h+pRoute.dwForwardDest], xmm0
0x180031d42  mov     r13d, r8d
0x180031d45  mov     r12d, edx
0x180031d48  movups  xmmword ptr [rsp+920h+pRoute.dwForwardIfIndex], xmm0
0x180031d4d  mov     r15d, ecx
0x180031d50  xor     edi, edi
0x180031d52  movups  xmmword ptr [rbp+820h+pRoute.dwForwardNextHopAS], xmm0
0x180031d56  xor     eax, eax
0x180031d58  xor     edx, edx; Val
0x180031d5a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180031d61  mov     r8d, 7FCh; Size
0x180031d67  mov     [rsp+920h+var_8D0], ebx
0x180031d6b  lea     rcx, [rbp+820h+var_83C]; void *
0x180031d6f  mov     [rsp+920h+lpMem], rdi
0x180031d74  movdqu  [rbp+820h+var_888], xmm0
0x180031d79  mov     qword ptr [rbp+820h+pRoute.dwForwardMetric4], rax
0x180031d7d  mov     [rbp+820h+var_840], edi
0x180031d80  call    memset_0
0x180031d85  xorps   xmm0, xmm0
0x180031d88  mov     [rbp+820h+var_868], edi
0x180031d8b  xor     eax, eax
0x180031d8d  cmp     cs:qword_18004C640, rdi
0x180031d94  movups  [rbp+820h+var_864], xmm0
0x180031d98  mov     [rbp+820h+var_844], eax
0x180031d9b  movups  [rbp+820h+var_854], xmm0
0x180031d9f  movups  [rbp+820h+var_878], xmm0
0x180031da3  jnz     short loc_180031DB7
0x180031da5  cmp     cs:qword_18004C648, rdi
0x180031dac  jnz     short loc_180031DB7
0x180031dae  cmp     cs:qword_18004C650, rdi
0x180031db5  jz      short loc_180031DCE
0x180031db7  lea     rdx, [rbp+820h+var_888]
0x180031dbb  call    NsiGetRoutingDomainIdForCompartment
0x180031dc0  mov     ebx, eax
0x180031dc2  test    eax, eax
0x180031dc4  jnz     loc_1800320E7
0x180031dca  mov     ebx, [rsp+920h+var_8D0]
0x180031dce  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x180031dd4  mov     edx, 1
0x180031dd9  jz      loc_180031E72
0x180031ddf  cmp     cs:qword_18004C658, rdi
0x180031de6  jz      loc_180031EB8
0x180031dec  cmp     [rbp+820h+arg_20], edi
0x180031df2  lea     rcx, aDel; "Del"
0x180031df9  lea     rax, aAdd; "Add"
0x180031e00  mov     word ptr [rbp+820h+var_840], di
0x180031e04  cmovz   rax, rcx
0x180031e08  mov     word ptr [rbp+820h+var_868], di
0x180031e0c  lea     rcx, aStack; "Stack"
0x180031e13  mov     r9d, r13d
0x180031e16  mov     [rsp+920h+var_8E0], rcx
0x180031e1b  mov     r8d, r15d
0x180031e1e  mov     [rsp+920h+var_8E8], rax
0x180031e23  lea     rcx, [rbp+820h+var_840]
0x180031e27  mov     dword ptr [rsp+920h+var_8F0], edx
0x180031e2b  lea     rdx, aRastcpsetroute_2; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x180031e32  mov     dword ptr [rsp+920h+var_8F8], ebx
0x180031e36  mov     dword ptr [rsp+920h+var_900], r12d
0x180031e3b  call    FormatRRASErrorString
0x180031e40  mov     rdx, cs:qword_18004C658
0x180031e47  lea     rax, [rbp+820h+var_868]
0x180031e4b  mov     rcx, cs:gIphlpEtwContext
0x180031e52  lea     r9, [rbp+820h+var_888]
0x180031e56  mov     [rsp+920h+var_8F8], rax
0x180031e5b  lea     r8, [rbp+820h+var_840]
0x180031e5f  mov     rax, cs:gIphlpParamTemplateFunc
0x180031e66  mov     [rsp+920h+var_900], rdi
0x180031e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e70  jmp     short loc_180031EB8
0x180031e72  cmp     [rbp+820h+arg_20], edi
0x180031e78  lea     rcx, aDel; "Del"
0x180031e7f  lea     rax, aAdd; "Add"
0x180031e86  mov     r9d, r12d
0x180031e89  cmovz   rax, rcx
0x180031e8d  mov     r8d, r13d
0x180031e90  lea     rcx, aStack; "Stack"
0x180031e97  mov     [rsp+920h+var_8E8], rcx
0x180031e9c  lea     rcx, aRastcpsetroute_1; "RasTcpSetRoute(Dest: 0x%x, Mask: 0x%x, "...
0x180031ea3  mov     [rsp+920h+var_8F0], rax
0x180031ea8  mov     dword ptr [rsp+920h+var_8F8], edx
0x180031eac  mov     edx, r15d
0x180031eaf  mov     dword ptr [rsp+920h+var_900], ebx
0x180031eb3  call    TraceHlp
0x180031eb8  xorps   xmm0, xmm0
0x180031ebb  xor     eax, eax
0x180031ebd  movups  xmmword ptr [rsp+920h+pRoute.dwForwardDest], xmm0
0x180031ec2  mov     qword ptr [rbp+820h+pRoute.dwForwardMetric4], rax
0x180031ec6  movups  xmmword ptr [rsp+920h+pRoute.dwForwardIfIndex], xmm0
0x180031ecb  movups  xmmword ptr [rbp+820h+pRoute.dwForwardNextHopAS], xmm0
0x180031ecf  call    cs:__imp_GetProcessHeap
0x180031ed5  mov     rsi, rax
0x180031ed8  test    rax, rax
0x180031edb  jnz     loc_180031F61
0x180031ee1  call    cs:__imp_GetLastError
0x180031ee7  cmp     cs:gIsIphlpEtwTracingAvailable, edi
0x180031eed  mov     ebx, eax
0x180031eef  jz      short loc_180031F4E
0x180031ef1  cmp     cs:qword_18004C650, rdi
0x180031ef8  jz      loc_1800320E7
0x180031efe  mov     r8d, eax
0x180031f01  mov     word ptr [rbp+820h+var_840], di
0x180031f05  lea     rdx, aGetprocessheap; "GetProcessHeap failed and returned %d"
0x180031f0c  mov     word ptr [rbp+820h+var_868], di
0x180031f10  lea     rcx, [rbp+820h+var_840]
0x180031f14  call    FormatRRASErrorString
0x180031f19  mov     rdx, cs:qword_18004C650
0x180031f20  lea     rax, [rbp+820h+var_868]
0x180031f24  mov     rcx, cs:gIphlpEtwContext
0x180031f2b  lea     r9, [rbp+820h+var_888]
0x180031f2f  mov     [rsp+920h+var_8F8], rax
0x180031f34  lea     r8, [rbp+820h+var_840]
0x180031f38  mov     rax, cs:gIphlpParamTemplateFunc
0x180031f3f  mov     [rsp+920h+var_900], rdi
0x180031f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f49  jmp     loc_1800320E7
0x180031f4e  mov     edx, eax
0x180031f50  lea     rcx, aGetprocessheap_0; "GetProcessHeap failed and returned %d"
0x180031f57  call    TraceHlp
0x180031f5c  jmp     loc_1800320E7
0x180031f61  mov     r8, rsi
0x180031f64  lea     rcx, [rsp+920h+lpMem]
0x180031f69  call    AllocateAndGetIpAddrTable
0x180031f6e  mov     rdi, [rsp+920h+lpMem]
0x180031f73  mov     ebx, eax
0x180031f75  test    eax, eax
0x180031f77  jz      short loc_180031FC7
0x180031f79  xor     r15d, r15d
0x180031f7c  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x180031f83  jz      short loc_180031FB4
0x180031f85  cmp     cs:qword_18004C650, r15
0x180031f8c  jz      loc_1800320D4
0x180031f92  mov     r8d, eax
0x180031f95  mov     word ptr [rbp+820h+var_840], r15w
0x180031f9a  lea     rdx, aAllocateandget_16; "AllocateAndGetIpAddrTable failed and re"...
0x180031fa1  mov     word ptr [rbp+820h+var_868], r15w
0x180031fa6  lea     rcx, [rbp+820h+var_840]
0x180031faa  call    FormatRRASErrorString
0x180031faf  jmp     loc_18003208C
0x180031fb4  mov     edx, eax
0x180031fb6  lea     rcx, aAllocateandget_6; "AllocateAndGetIpAddrTable failed and re"...
0x180031fbd  call    TraceHlp
0x180031fc2  jmp     loc_1800320D4
0x180031fc7  mov     edx, [rsp+920h+var_8D0]
0x180031fcb  xor     ecx, ecx
0x180031fcd  cmp     ecx, [rdi]
0x180031fcf  jnb     loc_1800320D4
0x180031fd5  lea     rax, [rcx+rcx*2]
0x180031fd9  cmp     edx, [rdi+rax*8+4]
0x180031fdd  jz      short loc_180031FE3
0x180031fdf  inc     ecx
0x180031fe1  jmp     short loc_180031FCD
0x180031fe3  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180031feb  lea     rcx, [rsp+920h+pRoute]; pRoute
0x180031ff0  mov     [rsp+920h+pRoute.dwForwardDest], r15d
0x180031ff5  xor     r15d, r15d
0x180031ff8  mov     [rsp+920h+pRoute.dwForwardPolicy], r15d
0x180031ffd  mov     [rsp+920h+pRoute.dwForwardMask], r13d
0x180032002  mov     [rsp+920h+pRoute.dwForwardNextHop], r12d
0x180032007  mov     eax, [rdi+rax*8+8]
0x18003200b  mov     [rsp+920h+pRoute.dwForwardIfIndex], eax
0x18003200f  lea     eax, [r15+3]
0x180032013  mov     dword ptr [rsp+920h+pRoute.18h], eax
0x180032017  mov     [rsp+920h+pRoute.dwForwardAge], 0FFFFFFFFh
0x18003201f  mov     [rbp+820h+pRoute.dwForwardNextHopAS], r15d
0x180032023  mov     [rbp+820h+pRoute.dwForwardMetric1], 1
0x18003202a  movups  xmmword ptr [rbp+820h+pRoute.dwForwardMetric2], xmm0
0x18003202e  cmp     [rbp+820h+arg_20], r15d
0x180032035  jz      short loc_180032042
0x180032037  mov     dword ptr [rsp+920h+pRoute.14h], eax
0x18003203b  call    CreateOrSetIpForwardEntry
0x180032040  jmp     short loc_180032050
0x180032042  mov     dword ptr [rsp+920h+pRoute.14h], 2
0x18003204a  call    cs:__imp_DeleteIpForwardEntry
0x180032050  mov     ebx, eax
0x180032052  test    eax, eax
0x180032054  jz      short loc_1800320D4
0x180032056  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18003205d  jz      short loc_1800320BE
0x18003205f  cmp     cs:qword_18004C650, r15
0x180032066  jz      short loc_1800320D4
0x180032068  mov     r9d, eax
0x18003206b  mov     word ptr [rbp+820h+var_840], r15w
0x180032070  lea     r8, aTostack; "ToStack"
0x180032077  mov     word ptr [rbp+820h+var_868], r15w
0x18003207c  lea     rdx, aSetipforwarden_1; "SetIpForwardEntry%hs failed and returne"...
0x180032083  lea     rcx, [rbp+820h+var_840]
0x180032087  call    FormatRRASErrorString
0x18003208c  mov     rdx, cs:qword_18004C650
0x180032093  lea     rax, [rbp+820h+var_868]
0x180032097  mov     rcx, cs:gIphlpEtwContext
0x18003209e  lea     r9, [rbp+820h+var_888]
0x1800320a2  mov     [rsp+920h+var_8F8], rax
0x1800320a7  lea     r8, [rbp+820h+var_840]
0x1800320ab  mov     rax, cs:gIphlpParamTemplateFunc
0x1800320b2  mov     [rsp+920h+var_900], r15
0x1800320b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320bc  jmp     short loc_1800320D4
0x1800320be  mov     r8d, ebx
0x1800320c1  lea     rdx, aTostack; "ToStack"
0x1800320c8  lea     rcx, aSetipforwarden_0; "SetIpForwardEntry%hs failed and returne"...
0x1800320cf  call    TraceHlp
0x1800320d4  test    rdi, rdi
0x1800320d7  jz      short loc_1800320E7
0x1800320d9  mov     r8, rdi; lpMem
0x1800320dc  xor     edx, edx; dwFlags
0x1800320de  mov     rcx, rsi; hHeap
0x1800320e1  call    cs:__imp_HeapFree
0x1800320e7  mov     eax, ebx
0x1800320e9  mov     rcx, [rbp+820h+var_40]
0x1800320f0  xor     rcx, rsp; StackCookie
0x1800320f3  call    __security_check_cookie
0x1800320f8  add     rsp, 8F0h
0x1800320ff  pop     r15
0x180032101  pop     r13
0x180032103  pop     r12
0x180032105  pop     rdi
0x180032106  pop     rsi
0x180032107  pop     rbx
0x180032108  pop     rbp
0x180032109  retn
```
