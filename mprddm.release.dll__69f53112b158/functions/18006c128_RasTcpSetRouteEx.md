# RasTcpSetRouteEx

- ea: `0x18006c128`
- end: `0x18006c3bc`
- name: `RasTcpSetRouteEx`
- size: `660`
- prototype: `__int64 __fastcall(int, int, int, int, int, NET_LUID InterfaceLuid)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180054b80`

## callees

- `0x18006c128`
- `0x18006c3c4`
- `0x1800755b8`
- `0x18007919c`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18006c24d`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18006c24d`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x18006c302`
- `IPHLPAPI!DeleteIpForwardEntry` at `0x18006c302`

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
  __int64 v15; // [rsp+28h] [rbp-E0h]
  const char *v16; // [rsp+30h] [rbp-D8h]
  ULONG InterfaceIndex; // [rsp+48h] [rbp-C0h] BYREF
  struct _MIB_IPFORWARDROW pRoute; // [rsp+50h] [rbp-B8h] BYREF
  int v19; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v20[2044]; // [rsp+8Ch] [rbp-7Ch] BYREF

  InterfaceIndex = 0;
  pRoute.dwForwardType = 0;
  v19 = 0;
  *(_OWORD *)&pRoute.dwForwardMetric2 = 0;
  memset_0(v20, 0, sizeof(v20));
  v8 = "Add";
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800D1088 )
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
      ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, xmmword_1800D1088, &v19);
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
  pRoute.dwForwardType = 0;
  *(_OWORD *)&pRoute.dwForwardMetric2 = 0;
  v11 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
  v12 = v11;
  if ( v11 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( unk_1800D1080 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"ConvertInterfaceLuidToIndex failed with error 0x%x", v11);
LABEL_23:
        ((void (__fastcall *)(__int64, _QWORD, int *))gIphlpTemplateFunc)(gIphlpEtwContext, unk_1800D1080, &v19);
      }
    }
    else
    {
      TraceHlp("ConvertInterfaceLuidToIndex failed with error 0x%x");
    }
  }
  else
  {
    pRoute.dwForwardMask = -1;
    pRoute.dwForwardAge = -1;
    pRoute.dwForwardIfIndex = InterfaceIndex;
    pRoute.dwForwardProto = 3;
    pRoute.dwForwardDest = a1;
    *(_QWORD *)&pRoute.dwForwardPolicy = 0;
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
      if ( unk_1800D1080 )
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
0x18006c128  mov     rax, rsp
0x18006c12b  mov     [rax+10h], rbx
0x18006c12f  mov     [rax+18h], rsi
0x18006c133  mov     [rax+20h], rdi
0x18006c137  push    rbp
0x18006c138  push    r14
0x18006c13a  push    r15
0x18006c13c  lea     rbp, [rax-7A8h]
0x18006c143  sub     rsp, 890h
0x18006c14a  mov     rax, cs:__security_cookie
0x18006c151  xor     rax, rsp
0x18006c154  mov     [rbp+7A0h+var_20], rax
0x18006c15b  xor     r15d, r15d
0x18006c15e  mov     r14d, ecx
0x18006c161  xorps   xmm0, xmm0
0x18006c164  mov     [rsp+8A0h+InterfaceIndex], r15d
0x18006c169  lea     rcx, [rbp+7A0h+var_81C]; void *
0x18006c16d  mov     dword ptr [rsp+8A0h+pRoute.14h], r15d
0x18006c172  xor     edx, edx; Val
0x18006c174  mov     [rbp+7A0h+var_820], r15d
0x18006c178  mov     r8d, 7FCh; Size
0x18006c17e  mov     esi, r9d
0x18006c181  movdqu  xmmword ptr [rsp+8A0h+pRoute.dwForwardMetric2], xmm0
0x18006c187  call    memset_0
0x18006c18c  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006c193  lea     rcx, aDel; "Del"
0x18006c19a  lea     rdi, aAdd; "Add"
0x18006c1a1  jz      short loc_18006C207
0x18006c1a3  cmp     qword ptr cs:xmmword_1800D1088, r15
0x18006c1aa  jz      loc_18006C233
0x18006c1b0  test    esi, esi
0x18006c1b2  mov     word ptr [rbp+7A0h+var_820], r15w
0x18006c1b7  mov     rax, rdi
0x18006c1ba  lea     rdx, aRastcpsetroute_0; "RasTcpSetRouteEx(Dest: 0x%x, Mask: 0x%x"...
0x18006c1c1  cmovz   rax, rcx
0x18006c1c5  mov     r8d, r14d
0x18006c1c8  mov     [rsp+8A0h+var_870], rax
0x18006c1cd  lea     rcx, [rbp+7A0h+var_820]
0x18006c1d1  mov     dword ptr [rsp+8A0h+var_878], 1
0x18006c1d9  or      r9d, 0FFFFFFFFh
0x18006c1dd  mov     dword ptr [rsp+8A0h+var_880], r15d
0x18006c1e2  call    FormatRRASErrorString
0x18006c1e7  mov     rdx, qword ptr cs:xmmword_1800D1088
0x18006c1ee  lea     r8, [rbp+7A0h+var_820]
0x18006c1f2  mov     rcx, cs:gIphlpEtwContext
0x18006c1f9  mov     rax, cs:gIphlpTemplateFunc
0x18006c200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c205  jmp     short loc_18006C233
0x18006c207  test    esi, esi
0x18006c209  mov     rax, rdi
0x18006c20c  mov     edx, r14d
0x18006c20f  cmovz   rax, rcx
0x18006c213  xor     r9d, r9d
0x18006c216  mov     [rsp+8A0h+var_878], rax
0x18006c21b  lea     rcx, aRastcpsetroute; "RasTcpSetRouteEx(Dest: 0x%x, Mask: 0x%x"...
0x18006c222  or      r8d, 0FFFFFFFFh
0x18006c226  mov     dword ptr [rsp+8A0h+var_880], 1
0x18006c22e  call    TraceHlp
0x18006c233  xorps   xmm0, xmm0
0x18006c236  mov     dword ptr [rsp+8A0h+pRoute.14h], r15d
0x18006c23b  lea     rdx, [rsp+8A0h+InterfaceIndex]; InterfaceIndex
0x18006c240  lea     rcx, [rbp+7A0h+InterfaceLuid]; InterfaceLuid
0x18006c247  movdqu  xmmword ptr [rsp+8A0h+pRoute.dwForwardMetric2], xmm0
0x18006c24d  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18006c254  nop     dword ptr [rax+rax+00h]
0x18006c259  mov     ebx, eax
0x18006c25b  test    eax, eax
0x18006c25d  jz      short loc_18006C2A5
0x18006c25f  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006c266  jz      short loc_18006C292
0x18006c268  cmp     qword ptr cs:unk_1800D1080, r15
0x18006c26f  jz      loc_18006C38D
0x18006c275  mov     r8d, eax
0x18006c278  mov     word ptr [rbp+7A0h+var_820], r15w
0x18006c27d  lea     rdx, aConvertinterfa; "ConvertInterfaceLuidToIndex failed with"...
0x18006c284  lea     rcx, [rbp+7A0h+var_820]
0x18006c288  call    FormatRRASErrorString
0x18006c28d  jmp     loc_18006C34E
0x18006c292  mov     edx, eax
0x18006c294  lea     rcx, aConvertinterfa_0; "ConvertInterfaceLuidToIndex failed with"...
0x18006c29b  call    TraceHlp
0x18006c2a0  jmp     loc_18006C38D
0x18006c2a5  mov     eax, [rsp+8A0h+InterfaceIndex]
0x18006c2a9  lea     rcx, [rsp+8A0h+pRoute]; pRoute
0x18006c2ae  or      [rsp+8A0h+pRoute.dwForwardMask], 0FFFFFFFFh
0x18006c2b3  or      [rsp+8A0h+pRoute.dwForwardAge], 0FFFFFFFFh
0x18006c2b8  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18006c2c0  mov     [rsp+8A0h+pRoute.dwForwardIfIndex], eax
0x18006c2c4  mov     eax, 3
0x18006c2c9  mov     dword ptr [rsp+8A0h+pRoute.18h], eax
0x18006c2cd  mov     [rsp+8A0h+pRoute.dwForwardDest], r14d
0x18006c2d2  mov     qword ptr [rsp+8A0h+pRoute.dwForwardPolicy], r15
0x18006c2d7  mov     [rsp+8A0h+pRoute.dwForwardNextHopAS], r15d
0x18006c2dc  mov     [rsp+8A0h+pRoute.dwForwardMetric1], 1
0x18006c2e4  movups  xmmword ptr [rsp+8A0h+pRoute.dwForwardMetric2], xmm0
0x18006c2e9  test    esi, esi
0x18006c2eb  jz      short loc_18006C2FA
0x18006c2ed  xor     edx, edx
0x18006c2ef  mov     dword ptr [rsp+8A0h+pRoute.14h], eax
0x18006c2f3  call    CreateOrSetIpForwardEntry
0x18006c2f8  jmp     short loc_18006C30E
0x18006c2fa  mov     dword ptr [rsp+8A0h+pRoute.14h], 2
0x18006c302  call    cs:__imp_DeleteIpForwardEntry
0x18006c309  nop     dword ptr [rax+rax+00h]
0x18006c30e  mov     ebx, eax
0x18006c310  test    eax, eax
0x18006c312  jz      short loc_18006C38D
0x18006c314  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18006c31b  jz      short loc_18006C36E
0x18006c31d  cmp     qword ptr cs:unk_1800D1080, r15
0x18006c324  jz      short loc_18006C38D
0x18006c326  test    esi, esi
0x18006c328  mov     word ptr [rbp+7A0h+var_820], r15w
0x18006c32d  lea     rax, aDel; "Del"
0x18006c334  mov     r9d, ebx
0x18006c337  cmovz   rdi, rax
0x18006c33b  lea     rdx, aIpforwardentry; "IpForwardEntry (%hs) failed with error "...
0x18006c342  mov     r8, rdi
0x18006c345  lea     rcx, [rbp+7A0h+var_820]
0x18006c349  call    FormatRRASErrorString
0x18006c34e  mov     rdx, qword ptr cs:unk_1800D1080
0x18006c355  lea     r8, [rbp+7A0h+var_820]
0x18006c359  mov     rcx, cs:gIphlpEtwContext
0x18006c360  mov     rax, cs:gIphlpTemplateFunc
0x18006c367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c36c  jmp     short loc_18006C38D
0x18006c36e  test    esi, esi
0x18006c370  lea     rax, aDel; "Del"
0x18006c377  mov     r8d, ebx
0x18006c37a  lea     rcx, aIpforwardentry_0; "IpForwardEntry (%hs) failed with error "...
0x18006c381  cmovz   rdi, rax
0x18006c385  mov     rdx, rdi
0x18006c388  call    TraceHlp
0x18006c38d  mov     eax, ebx
0x18006c38f  mov     rcx, [rbp+7A0h+var_20]
0x18006c396  xor     rcx, rsp; StackCookie
0x18006c399  call    __security_check_cookie
0x18006c39e  lea     r11, [rsp+8A0h+var_10]
0x18006c3a6  mov     rbx, [r11+28h]
0x18006c3aa  mov     rsi, [r11+30h]
0x18006c3ae  mov     rdi, [r11+38h]
0x18006c3b2  mov     rsp, r11
0x18006c3b5  pop     r15
0x18006c3b7  pop     r14
0x18006c3b9  pop     rbp
0x18006c3ba  retn
```
