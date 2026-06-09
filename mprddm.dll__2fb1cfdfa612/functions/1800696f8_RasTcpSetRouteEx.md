# RasTcpSetRouteEx

- ea: `0x1800696f8`
- end: `0x18006997e`
- name: `RasTcpSetRouteEx`
- size: `646`
- prototype: `__int64 __fastcall(int, int, int, int, int, NET_LUID InterfaceLuid)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180053080`

## callees

- `0x1800696f8`
- `0x180069984`
- `0x180071cec`
- `0x1800753dc`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180069826`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180069826`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x1800698e4`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x1800698e4`

## pseudocode

```c
__int64 __fastcall RasTcpSetRouteEx(DWORD a1, __int64 a2, __int64 a3, int a4, int a5, NET_LUID InterfaceLuid)
{
  const char *v8; // rdi
  const char *v9; // rax
  const char *v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  DWORD v13; // eax
  __int64 v15; // [rsp+20h] [rbp-E0h]
  const char *v16; // [rsp+28h] [rbp-D8h]
  ULONG InterfaceIndex; // [rsp+40h] [rbp-C0h] BYREF
  struct _MIB_IPFORWARDROW pRoute; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  InterfaceIndex = 0;
  v19 = 0;
  memset(&pRoute, 0, sizeof(pRoute));
  memset_0(v20, 0, sizeof(v20));
  v8 = "Add";
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800CA088 )
    {
      LOWORD(v19) = 0;
      v9 = "Add";
      if ( !a4 )
        v9 = "Del";
      FormatRRASErrorString(
        &v19,
        L"RasTcpSetRouteEx(Dest: 0x%x, Mask: 0x%x, NextHop: 0x%x, Metric: %d, %hs)",
        a1,
        0xFFFFFFFFLL,
        0,
        1,
        v9);
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800CA088, &v19);
    }
  }
  else
  {
    v10 = "Add";
    if ( !a4 )
      v10 = "Del";
    v16 = v10;
    LODWORD(v15) = 1;
    TraceHlp("RasTcpSetRouteEx(Dest: 0x%x, Mask: 0x%x, NextHop: 0x%x, Metric: %d, %hs)");
  }
  memset(&pRoute, 0, sizeof(pRoute));
  v11 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
  v12 = v11;
  if ( v11 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( unk_1800CA080 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"ConvertInterfaceLuidToIndex failed with error 0x%x", v11);
LABEL_23:
        ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, unk_1800CA080, &v19);
      }
    }
    else
    {
      TraceHlp("ConvertInterfaceLuidToIndex failed with error 0x%x");
    }
  }
  else
  {
    pRoute.dwForwardIfIndex = InterfaceIndex;
    pRoute.dwForwardProto = 3;
    pRoute.dwForwardDest = a1;
    pRoute.dwForwardMask = -1;
    *(_QWORD *)&pRoute.dwForwardPolicy = 0;
    pRoute.dwForwardAge = -1;
    pRoute.dwForwardNextHopAS = 0;
    pRoute.dwForwardMetric1 = 1;
    *(__m128i *)&pRoute.dwForwardMetric2 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    if ( a4 )
    {
      pRoute.dwForwardType = 3;
      v13 = CreateOrSetIpForwardEntry(&pRoute, 0);
    }
    else
    {
      pRoute.dwForwardType = 2;
      v13 = DeleteIpForwardEntry(&pRoute);
    }
    v12 = v13;
    if ( v13 )
    {
      if ( !gIsIphlpEtwTracingAvailable )
      {
        TraceHlp("IpForwardEntry (%hs) failed with error 0x%x");
        return v12;
      }
      if ( unk_1800CA080 )
      {
        LOWORD(v19) = 0;
        if ( !a4 )
          v8 = "Del";
        FormatRRASErrorString(&v19, L"IpForwardEntry (%hs) failed with error 0x%x", v8, v13, v15, v16);
        goto LABEL_23;
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800696f8  push    rbp
0x1800696fa  push    rbx
0x1800696fb  push    rsi
0x1800696fc  push    rdi
0x1800696fd  push    r13
0x1800696ff  push    r14
0x180069701  lea     rbp, [rsp-798h]
0x180069709  sub     rsp, 898h
0x180069710  mov     rax, cs:__security_cookie
0x180069717  xor     rax, rsp
0x18006971a  mov     [rbp+7C0h+var_40], rax
0x180069721  xorps   xmm0, xmm0
0x180069724  mov     [rsp+8C0h+InterfaceIndex], 0
0x18006972c  xor     eax, eax
0x18006972e  mov     r14d, ecx
0x180069731  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180069735  mov     qword ptr [rsp+8C0h+pRoute.dwForwardMetric4], rax
0x18006973a  xor     edx, edx; Val
0x18006973c  mov     [rbp+7C0h+var_840], eax
0x18006973f  mov     r8d, 7FCh; Size
0x180069745  mov     esi, r9d
0x180069748  movups  xmmword ptr [rsp+8C0h+pRoute.dwForwardDest], xmm0
0x18006974d  movups  xmmword ptr [rsp+8C0h+pRoute.dwForwardIfIndex], xmm0
0x180069752  movups  xmmword ptr [rsp+8C0h+pRoute.dwForwardNextHopAS], xmm0
0x180069757  call    memset_0
0x18006975c  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180069763  lea     r13, aDel; "Del"
0x18006976a  lea     rdi, aAdd; "Add"
0x180069771  mov     ecx, 1
0x180069776  jz      short loc_1800697D9
0x180069778  cmp     qword ptr cs:xmmword_1800CA088, 0
0x180069780  jz      short loc_180069801
0x180069782  xor     eax, eax
0x180069784  lea     rdx, aRastcpsetroute_0; "RasTcpSetRouteEx(Dest: 0x%x, Mask: 0x%x"...
0x18006978b  mov     word ptr [rbp+7C0h+var_840], ax
0x18006978f  test    esi, esi
0x180069791  mov     rax, rdi
0x180069794  mov     r8d, r14d
0x180069797  cmovz   rax, r13
0x18006979b  or      r9d, 0FFFFFFFFh
0x18006979f  mov     [rsp+8C0h+var_890], rax
0x1800697a4  mov     dword ptr [rsp+8C0h+var_898], ecx
0x1800697a8  lea     rcx, [rbp+7C0h+var_840]
0x1800697ac  mov     dword ptr [rsp+8C0h+var_8A0], 0
0x1800697b4  call    FormatRRASErrorString
0x1800697b9  mov     rdx, qword ptr cs:xmmword_1800CA088
0x1800697c0  lea     r8, [rbp+7C0h+var_840]
0x1800697c4  mov     rcx, cs:gIphlpEtwContext
0x1800697cb  mov     rax, cs:gIphlpTemplateFunc
0x1800697d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697d7  jmp     short loc_180069801
0x1800697d9  test    esi, esi
0x1800697db  mov     rax, rdi
0x1800697de  mov     edx, r14d
0x1800697e1  cmovz   rax, r13
0x1800697e5  xor     r9d, r9d
0x1800697e8  mov     [rsp+8C0h+var_898], rax
0x1800697ed  or      r8d, 0FFFFFFFFh
0x1800697f1  mov     dword ptr [rsp+8C0h+var_8A0], ecx
0x1800697f5  lea     rcx, aRastcpsetroute; "RasTcpSetRouteEx(Dest: 0x%x, Mask: 0x%x"...
0x1800697fc  call    TraceHlp
0x180069801  xorps   xmm0, xmm0
0x180069804  lea     rdx, [rsp+8C0h+InterfaceIndex]; InterfaceIndex
0x180069809  xor     eax, eax
0x18006980b  lea     rcx, [rbp+7C0h+InterfaceLuid]; InterfaceLuid
0x180069812  movups  xmmword ptr [rsp+8C0h+pRoute.dwForwardDest], xmm0
0x180069817  mov     qword ptr [rsp+8C0h+pRoute.dwForwardMetric4], rax
0x18006981c  movups  xmmword ptr [rsp+8C0h+pRoute.dwForwardIfIndex], xmm0
0x180069821  movups  xmmword ptr [rsp+8C0h+pRoute.dwForwardNextHopAS], xmm0
0x180069826  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18006982c  mov     ebx, eax
0x18006982e  test    eax, eax
0x180069830  jz      short loc_18006987A
0x180069832  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x180069839  jz      short loc_180069867
0x18006983b  cmp     qword ptr cs:unk_1800CA080, 0
0x180069843  jz      loc_18006995D
0x180069849  xor     ecx, ecx
0x18006984b  lea     rdx, aConvertinterfa; "ConvertInterfaceLuidToIndex failed with"...
0x180069852  mov     word ptr [rbp+7C0h+var_840], cx
0x180069856  mov     r8d, eax
0x180069859  lea     rcx, [rbp+7C0h+var_840]
0x18006985d  call    FormatRRASErrorString
0x180069862  jmp     loc_180069925
0x180069867  mov     edx, eax
0x180069869  lea     rcx, aConvertinterfa_0; "ConvertInterfaceLuidToIndex failed with"...
0x180069870  call    TraceHlp
0x180069875  jmp     loc_18006995D
0x18006987a  mov     eax, [rsp+8C0h+InterfaceIndex]
0x18006987e  lea     rcx, [rsp+8C0h+pRoute]; pRoute
0x180069883  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18006988b  mov     [rsp+8C0h+pRoute.dwForwardIfIndex], eax
0x18006988f  mov     eax, 3
0x180069894  mov     dword ptr [rsp+8C0h+pRoute.18h], eax
0x180069898  mov     [rsp+8C0h+pRoute.dwForwardDest], r14d
0x18006989d  mov     [rsp+8C0h+pRoute.dwForwardMask], 0FFFFFFFFh
0x1800698a5  mov     qword ptr [rsp+8C0h+pRoute.dwForwardPolicy], 0
0x1800698ae  mov     [rsp+8C0h+pRoute.dwForwardAge], 0FFFFFFFFh
0x1800698b6  mov     [rsp+8C0h+pRoute.dwForwardNextHopAS], 0
0x1800698be  mov     [rsp+8C0h+pRoute.dwForwardMetric1], 1
0x1800698c6  movups  xmmword ptr [rsp+8C0h+pRoute.dwForwardMetric2], xmm0
0x1800698cb  test    esi, esi
0x1800698cd  jz      short loc_1800698DC
0x1800698cf  xor     edx, edx
0x1800698d1  mov     dword ptr [rsp+8C0h+pRoute.14h], eax
0x1800698d5  call    CreateOrSetIpForwardEntry
0x1800698da  jmp     short loc_1800698EA
0x1800698dc  mov     dword ptr [rsp+8C0h+pRoute.14h], 2
0x1800698e4  call    cs:__imp_DeleteIpForwardEntry
0x1800698ea  mov     ebx, eax
0x1800698ec  test    eax, eax
0x1800698ee  jz      short loc_18006995D
0x1800698f0  cmp     cs:gIsIphlpEtwTracingAvailable, 0
0x1800698f7  jz      short loc_180069945
0x1800698f9  cmp     qword ptr cs:unk_1800CA080, 0
0x180069901  jz      short loc_18006995D
0x180069903  xor     eax, eax
0x180069905  lea     rdx, aIpforwardentry; "IpForwardEntry (%hs) failed with error "...
0x18006990c  test    esi, esi
0x18006990e  mov     word ptr [rbp+7C0h+var_840], ax
0x180069912  mov     r9d, ebx
0x180069915  lea     rcx, [rbp+7C0h+var_840]
0x180069919  cmovz   rdi, r13
0x18006991d  mov     r8, rdi
0x180069920  call    FormatRRASErrorString
0x180069925  mov     rdx, qword ptr cs:unk_1800CA080
0x18006992c  lea     r8, [rbp+7C0h+var_840]
0x180069930  mov     rcx, cs:gIphlpEtwContext
0x180069937  mov     rax, cs:gIphlpTemplateFunc
0x18006993e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069943  jmp     short loc_18006995D
0x180069945  test    esi, esi
0x180069947  lea     rcx, aIpforwardentry_0; "IpForwardEntry (%hs) failed with error "...
0x18006994e  mov     r8d, ebx
0x180069951  cmovz   rdi, r13
0x180069955  mov     rdx, rdi
0x180069958  call    TraceHlp
0x18006995d  mov     eax, ebx
0x18006995f  mov     rcx, [rbp+7C0h+var_40]
0x180069966  xor     rcx, rsp; StackCookie
0x180069969  call    __security_check_cookie
0x18006996e  add     rsp, 898h
0x180069975  pop     r14
0x180069977  pop     r13
0x180069979  pop     rdi
0x18006997a  pop     rsi
0x18006997b  pop     rbx
0x18006997c  pop     rbp
0x18006997d  retn
```
