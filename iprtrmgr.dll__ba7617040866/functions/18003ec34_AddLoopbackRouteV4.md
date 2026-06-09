# AddLoopbackRouteV4

- ea: `0x18003ec34`
- end: `0x18003ef80`
- name: `AddLoopbackRouteV4`
- size: `844`
- prototype: `__int64 __fastcall(DWORD dwDestAddr, int, struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000b450`
- `0x1800190d0`

## callees

- `0x180011790`
- `0x18003ec34`
- `0x18003f1a4`
- `0x180051af4`
- `0x180057be0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!GetBestRoute` at `0x18003ed53`
- `IPHLPAPI!GetBestRoute` at `0x18003ed53`
- `iprtprio!ComputeRouteMetric` at `0x18003ed26`
- `iprtprio!ComputeRouteMetric` at `0x18003ed26`

## pseudocode

```c
int __fastcall AddLoopbackRouteV4(DWORD dwDestAddr, int a2, struct _GUID *a3)
{
  __int64 LoopbackInterfaceForRoutingDomain; // rax
  __int64 v7; // rsi
  const wchar_t *v8; // r8
  int v9; // eax
  __int64 *v10; // rdx
  __int128 *v11; // r9
  __int128 *v12; // r9
  __int64 v14; // [rsp+20h] [rbp-E0h]
  _DWORD v15[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v16[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+70h] [rbp-90h]
  DWORD v18; // [rsp+78h] [rbp-88h]
  __int64 v19; // [rsp+7Ch] [rbp-84h]
  unsigned int v20; // [rsp+90h] [rbp-70h]
  int v21; // [rsp+94h] [rbp-6Ch]
  int v22; // [rsp+98h] [rbp-68h]
  int v23; // [rsp+9Ch] [rbp-64h]
  int v24; // [rsp+A0h] [rbp-60h]
  __int128 v25; // [rsp+B0h] [rbp-50h] BYREF
  struct _MIB_IPFORWARDROW pBestRoute; // [rsp+C0h] [rbp-40h] BYREF
  int v27; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v28; // [rsp+FCh] [rbp-4h]
  __int128 v29; // [rsp+10Ch] [rbp+Ch]
  int v30; // [rsp+11Ch] [rbp+1Ch]
  int v31; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v32[2044]; // [rsp+124h] [rbp+24h] BYREF

  v15[0] = 0;
  memset_0(v16, 0, 0x48u);
  v31 = 0;
  memset(&pBestRoute, 0, sizeof(pBestRoute));
  memset_0(v32, 0, sizeof(v32));
  v27 = 0;
  v28 = 0;
  v30 = 0;
  v29 = 0;
  v25 = 0;
  LoopbackInterfaceForRoutingDomain = GetLoopbackInterfaceForRoutingDomain(a3, 0x21u);
  v7 = LoopbackInterfaceForRoutingDomain;
  if ( !LoopbackInterfaceForRoutingDomain )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return LoopbackInterfaceForRoutingDomain;
    LOWORD(v27) = 0;
    v8 = L"AddLoopbackRouteV4: No loopback interface";
    v14 = 0;
    goto LABEL_22;
  }
  v16[1] = -1;
  v16[3] = 16777343;
  v16[0] = dwDestAddr;
  v20 = *(_DWORD *)(LoopbackInterfaceForRoutingDomain + 16);
  v19 = 0;
  v9 = ComputeRouteMetric(2);
  v22 = 2;
  v23 = v9;
  v17 = 0;
  v24 = 3;
  v21 = 3;
  v16[2] = 0;
  LODWORD(LoopbackInterfaceForRoutingDomain) = GetBestRoute(dwDestAddr, 0, &pBestRoute);
  if ( (_DWORD)LoopbackInterfaceForRoutingDomain )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return LoopbackInterfaceForRoutingDomain;
    LOWORD(v31) = 0;
    LOWORD(v27) = 0;
    LODWORD(LoopbackInterfaceForRoutingDomain) = FormatRRASErrorString(
                                                   &v31,
                                                   L"AddLoopbackRouteV4: Stack query for loopback route associated with %d"
                                                    ".%d.%d.%d failed, error %d",
                                                   (unsigned __int8)dwDestAddr,
                                                   BYTE1(dwDestAddr),
                                                   BYTE2(dwDestAddr),
                                                   HIBYTE(dwDestAddr),
                                                   LoopbackInterfaceForRoutingDomain);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      return LoopbackInterfaceForRoutingDomain;
    v8 = (const wchar_t *)&v31;
    v10 = RasRtrMgrParamTraceError;
    v14 = *(_QWORD *)(v7 + 72);
    goto LABEL_23;
  }
  LODWORD(LoopbackInterfaceForRoutingDomain) = *(_DWORD *)(v7 + 16);
  if ( pBestRoute.dwForwardIfIndex != (_DWORD)LoopbackInterfaceForRoutingDomain )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return LoopbackInterfaceForRoutingDomain;
    LOWORD(v31) = 0;
    LOWORD(v27) = 0;
    LODWORD(LoopbackInterfaceForRoutingDomain) = FormatRRASErrorString(
                                                   &v31,
                                                   L"AddLoopbackRouteV4: No loopback route for %d.%d.%d.%d in stack",
                                                   (unsigned __int8)dwDestAddr,
                                                   BYTE1(dwDestAddr),
                                                   BYTE2(dwDestAddr),
                                                   HIBYTE(dwDestAddr));
    goto LABEL_20;
  }
  if ( (unsigned int)GetInterfaceMetricFromStack(v20, v15, 33) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v31) = 0;
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v31, L"AddDestinationRows: GetInterfaceMetricFromStack failed for interface index %d", v20);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v11 = &v25;
        if ( a3 )
          LODWORD(v11) = (_DWORD)a3;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v31,
          (_DWORD)v11,
          *(_QWORD *)(v7 + 72),
          (__int64)&v27);
      }
    }
  }
  v18 = pBestRoute.dwForwardMetric1 - v15[0];
  LODWORD(LoopbackInterfaceForRoutingDomain) = AddSingleRoute(
                                                 *(_DWORD *)(v7 + 16),
                                                 (int)v16,
                                                 a2,
                                                 0,
                                                 1,
                                                 0,
                                                 0,
                                                 1,
                                                 (struct _GUID *)(v7 + 688),
                                                 0);
  if ( (_DWORD)LoopbackInterfaceForRoutingDomain && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v31) = 0;
    LOWORD(v27) = 0;
    LODWORD(LoopbackInterfaceForRoutingDomain) = FormatRRASErrorString(
                                                   &v31,
                                                   L"AddLoopbackRouteV4: Couldnt add 127.0.0.1 route associated with %x",
                                                   dwDestAddr);
LABEL_20:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return LoopbackInterfaceForRoutingDomain;
    v8 = (const wchar_t *)&v31;
    v14 = *(_QWORD *)(v7 + 72);
LABEL_22:
    v10 = RasRtrmgrParamTraceInfo;
LABEL_23:
    v12 = &v25;
    if ( a3 )
      LODWORD(v12) = (_DWORD)a3;
    LODWORD(LoopbackInterfaceForRoutingDomain) = McTemplateU0zjzz_EventWriteTransfer(
                                                   (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                   (_DWORD)v10,
                                                   (_DWORD)v8,
                                                   (_DWORD)v12,
                                                   v14,
                                                   (__int64)&v27);
  }
  return LoopbackInterfaceForRoutingDomain;
}

```

## disassembly

```asm
0x18003ec34  mov     [rsp-8+arg_18], rbx
0x18003ec39  push    rbp
0x18003ec3a  push    rsi
0x18003ec3b  push    rdi
0x18003ec3c  push    r12
0x18003ec3e  push    r14
0x18003ec40  lea     rbp, [rsp-830h]
0x18003ec48  sub     rsp, 930h
0x18003ec4f  mov     rax, cs:__security_cookie
0x18003ec56  xor     rax, rsp
0x18003ec59  mov     [rbp+850h+var_30], rax
0x18003ec60  xor     r12d, r12d
0x18003ec63  mov     rbx, r8
0x18003ec66  mov     r14d, edx
0x18003ec69  mov     [rsp+950h+var_900], r12d
0x18003ec6e  mov     edi, ecx
0x18003ec70  xor     edx, edx; Val
0x18003ec72  lea     rcx, [rsp+950h+var_8F0]; void *
0x18003ec77  lea     r8d, [r12+48h]; Size
0x18003ec7c  call    memset_0
0x18003ec81  xorps   xmm0, xmm0
0x18003ec84  mov     [rbp+850h+var_830], r12d
0x18003ec88  xor     eax, eax
0x18003ec8a  lea     rcx, [rbp+850h+var_82C]; void *
0x18003ec8e  xor     edx, edx; Val
0x18003ec90  mov     qword ptr [rbp+850h+pBestRoute.dwForwardMetric4], rax
0x18003ec94  mov     r8d, 7FCh; Size
0x18003ec9a  movups  xmmword ptr [rbp+850h+pBestRoute.dwForwardDest], xmm0
0x18003ec9e  movups  xmmword ptr [rbp+850h+pBestRoute.dwForwardIfIndex], xmm0
0x18003eca2  movups  xmmword ptr [rbp+850h+pBestRoute.dwForwardNextHopAS], xmm0
0x18003eca6  call    memset_0
0x18003ecab  xorps   xmm0, xmm0
0x18003ecae  mov     [rbp+850h+var_858], r12d
0x18003ecb2  xor     eax, eax
0x18003ecb4  mov     rcx, rbx; struct _GUID *
0x18003ecb7  movups  [rbp+850h+var_854], xmm0
0x18003ecbb  mov     [rbp+850h+var_834], eax
0x18003ecbe  movups  [rbp+850h+var_844], xmm0
0x18003ecc2  lea     edx, [rax+21h]; unsigned int
0x18003ecc5  movups  [rbp+850h+var_8A0], xmm0
0x18003ecc9  call    GetLoopbackInterfaceForRoutingDomain
0x18003ecce  mov     rsi, rax
0x18003ecd1  test    rax, rax
0x18003ecd4  jnz     short loc_18003ED02
0x18003ecd6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003ecdd  jz      loc_18003EF5A
0x18003ece3  lea     rax, [rbp+850h+var_858]
0x18003ece7  mov     word ptr [rbp+850h+var_858], r12w
0x18003ecec  mov     qword ptr [rsp+950h+var_928], rax
0x18003ecf1  lea     r8, aAddloopbackrou_0; "AddLoopbackRouteV4: No loopback interfa"...
0x18003ecf8  mov     qword ptr [rsp+950h+var_930], r12
0x18003ecfd  jmp     loc_18003EF3C
0x18003ed02  mov     [rsp+950h+var_8EC], 0FFFFFFFFh
0x18003ed0a  mov     ecx, 2
0x18003ed0f  mov     [rsp+950h+var_8E4], 100007Fh
0x18003ed17  mov     [rsp+950h+var_8F0], edi
0x18003ed1b  mov     eax, [rax+10h]
0x18003ed1e  mov     [rbp+850h+var_8C0], eax
0x18003ed21  mov     [rsp+950h+var_8D4], r12
0x18003ed26  call    cs:__imp_ComputeRouteMetric
0x18003ed2c  lea     r8, [rbp+850h+pBestRoute]; pBestRoute
0x18003ed30  mov     [rbp+850h+var_8B8], 2
0x18003ed37  mov     [rbp+850h+var_8B4], eax
0x18003ed3a  xor     edx, edx; dwSourceAddr
0x18003ed3c  mov     eax, 3
0x18003ed41  mov     [rsp+950h+var_8E0], r12
0x18003ed46  mov     ecx, edi; dwDestAddr
0x18003ed48  mov     [rbp+850h+var_8B0], eax
0x18003ed4b  mov     [rbp+850h+var_8BC], eax
0x18003ed4e  mov     [rsp+950h+var_8E8], r12d
0x18003ed53  call    cs:__imp_GetBestRoute
0x18003ed59  mov     r10d, eax
0x18003ed5c  test    eax, eax
0x18003ed5e  jz      short loc_18003EDDD
0x18003ed60  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003ed67  jz      loc_18003EF5A
0x18003ed6d  mov     [rsp+950h+var_920], r10d
0x18003ed72  mov     eax, edi
0x18003ed74  shr     eax, 10h
0x18003ed77  mov     edx, edi
0x18003ed79  movzx   ecx, al
0x18003ed7c  mov     eax, edi
0x18003ed7e  shr     edx, 18h
0x18003ed81  mov     [rsp+950h+var_928], edx
0x18003ed85  lea     rdx, aAddloopbackrou_1; "AddLoopbackRouteV4: Stack query for loo"...
0x18003ed8c  shr     eax, 8
0x18003ed8f  mov     [rsp+950h+var_930], ecx
0x18003ed93  lea     rcx, [rbp+850h+var_830]
0x18003ed97  movzx   r9d, al
0x18003ed9b  movzx   r8d, dil
0x18003ed9f  mov     word ptr [rbp+850h+var_830], r12w
0x18003eda4  mov     word ptr [rbp+850h+var_858], r12w
0x18003eda9  call    FormatRRASErrorString
0x18003edae  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18003edb5  jz      loc_18003EF5A
0x18003edbb  lea     rax, [rbp+850h+var_858]
0x18003edbf  mov     qword ptr [rsp+950h+var_928], rax
0x18003edc4  lea     r8, [rbp+850h+var_830]
0x18003edc8  mov     rax, [rsi+48h]
0x18003edcc  lea     rdx, RasRtrMgrParamTraceError
0x18003edd3  mov     qword ptr [rsp+950h+var_930], rax
0x18003edd8  jmp     loc_18003EF43
0x18003eddd  mov     eax, [rsi+10h]
0x18003ede0  cmp     [rbp+850h+pBestRoute.dwForwardIfIndex], eax
0x18003ede3  jz      short loc_18003EE33
0x18003ede5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003edec  jge     loc_18003EF5A
0x18003edf2  mov     eax, edi
0x18003edf4  movzx   r8d, dil
0x18003edf8  shr     eax, 10h
0x18003edfb  mov     edx, edi
0x18003edfd  movzx   ecx, al
0x18003ee00  mov     eax, edi
0x18003ee02  shr     edx, 18h
0x18003ee05  mov     [rsp+950h+var_928], edx
0x18003ee09  lea     rdx, aAddloopbackrou_4; "AddLoopbackRouteV4: No loopback route f"...
0x18003ee10  shr     eax, 8
0x18003ee13  mov     [rsp+950h+var_930], ecx
0x18003ee17  lea     rcx, [rbp+850h+var_830]
0x18003ee1b  movzx   r9d, al
0x18003ee1f  mov     word ptr [rbp+850h+var_830], r12w
0x18003ee24  mov     word ptr [rbp+850h+var_858], r12w
0x18003ee29  call    FormatRRASErrorString
0x18003ee2e  jmp     loc_18003EF1D
0x18003ee33  mov     ecx, [rbp+850h+var_8C0]
0x18003ee36  lea     rdx, [rsp+950h+var_900]
0x18003ee3b  mov     r8d, 21h ; '!'
0x18003ee41  call    GetInterfaceMetricFromStack
0x18003ee46  test    eax, eax
0x18003ee48  jz      short loc_18003EEAE
0x18003ee4a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003ee51  jge     short loc_18003EEAE
0x18003ee53  mov     r8d, [rbp+850h+var_8C0]
0x18003ee57  lea     rdx, aAdddestination; "AddDestinationRows: GetInterfaceMetricF"...
0x18003ee5e  lea     rcx, [rbp+850h+var_830]
0x18003ee62  mov     word ptr [rbp+850h+var_830], r12w
0x18003ee67  mov     word ptr [rbp+850h+var_858], r12w
0x18003ee6c  call    FormatRRASErrorString
0x18003ee71  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003ee78  jge     short loc_18003EEAE
0x18003ee7a  lea     rax, [rbp+850h+var_858]
0x18003ee7e  test    rbx, rbx
0x18003ee81  mov     qword ptr [rsp+950h+var_928], rax
0x18003ee86  lea     r9, [rbp+850h+var_8A0]
0x18003ee8a  mov     rax, [rsi+48h]
0x18003ee8e  lea     r8, [rbp+850h+var_830]
0x18003ee92  cmovnz  r9, rbx
0x18003ee96  mov     qword ptr [rsp+950h+var_930], rax
0x18003ee9b  lea     rdx, RasRtrmgrParamTraceInfo
0x18003eea2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003eea9  call    McTemplateU0zjzz_EventWriteTransfer
0x18003eeae  mov     eax, [rbp+850h+pBestRoute.dwForwardMetric1]
0x18003eeb1  lea     rdx, [rsp+950h+var_8F0]; int
0x18003eeb6  sub     eax, [rsp+950h+var_900]
0x18003eeba  xor     r9d, r9d; int
0x18003eebd  mov     [rsp+950h+var_908], r12; __int64
0x18003eec2  mov     r8d, r14d; int
0x18003eec5  mov     [rsp+950h+var_8D8], eax
0x18003eec9  lea     rax, [rsi+2B0h]
0x18003eed0  mov     ecx, [rsi+10h]; int
0x18003eed3  mov     [rsp+950h+var_910], rax; struct _GUID *
0x18003eed8  lea     eax, [r9+1]
0x18003eedc  mov     [rsp+950h+var_918], eax; int
0x18003eee0  mov     [rsp+950h+var_920], r12d; int
0x18003eee5  mov     [rsp+950h+var_928], r12d; int
0x18003eeea  mov     [rsp+950h+var_930], eax; int
0x18003eeee  call    AddSingleRoute
0x18003eef3  test    eax, eax
0x18003eef5  jz      short loc_18003EF5A
0x18003eef7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003eefe  jge     short loc_18003EF5A
0x18003ef00  mov     r8d, edi
0x18003ef03  mov     word ptr [rbp+850h+var_830], r12w
0x18003ef08  lea     rdx, aAddloopbackrou_2; "AddLoopbackRouteV4: Couldnt add 127.0.0"...
0x18003ef0f  mov     word ptr [rbp+850h+var_858], r12w
0x18003ef14  lea     rcx, [rbp+850h+var_830]
0x18003ef18  call    FormatRRASErrorString
0x18003ef1d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18003ef24  jge     short loc_18003EF5A
0x18003ef26  lea     rax, [rbp+850h+var_858]
0x18003ef2a  mov     qword ptr [rsp+950h+var_928], rax
0x18003ef2f  lea     r8, [rbp+850h+var_830]
0x18003ef33  mov     rax, [rsi+48h]
0x18003ef37  mov     qword ptr [rsp+950h+var_930], rax
0x18003ef3c  lea     rdx, RasRtrmgrParamTraceInfo
0x18003ef43  test    rbx, rbx
0x18003ef46  lea     r9, [rbp+850h+var_8A0]
0x18003ef4a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003ef51  cmovnz  r9, rbx
0x18003ef55  call    McTemplateU0zjzz_EventWriteTransfer
0x18003ef5a  mov     rcx, [rbp+850h+var_30]
0x18003ef61  xor     rcx, rsp; StackCookie
0x18003ef64  call    __security_check_cookie
0x18003ef69  mov     rbx, [rsp+950h+arg_18]
0x18003ef71  add     rsp, 930h
0x18003ef78  pop     r14
0x18003ef7a  pop     r12
0x18003ef7c  pop     rdi
0x18003ef7d  pop     rsi
0x18003ef7e  pop     rbp
0x18003ef7f  retn
```
