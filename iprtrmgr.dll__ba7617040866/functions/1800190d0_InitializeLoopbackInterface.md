# InitializeLoopbackInterface

- ea: `0x1800190d0`
- end: `0x180019537`
- name: `InitializeLoopbackInterface`
- size: `1127`
- prototype: `__int64 __fastcall(struct _ICB *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022f60`

## callees

- `0x180011790`
- `0x1800177cc`
- `0x1800190d0`
- `0x18002ebd4`
- `0x18002ee20`
- `0x18003ec34`
- `0x18003ef88`
- `0x18003f1a4`
- `0x180057dd0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180019297`
- `ntdll!RtlAcquireResourceExclusive` at `0x180019297`
- `ntdll!RtlReleaseResource` at `0x180019378`
- `ntdll!RtlReleaseResource` at `0x180019505`
- `ntdll!RtlReleaseResource` at `0x180019378`
- `ntdll!RtlReleaseResource` at `0x180019505`
- `ntdll!RtlAcquireResourceShared` at `0x18001945d`
- `ntdll!RtlAcquireResourceShared` at `0x18001945d`
- `iprtprio!ComputeRouteMetric` at `0x1800193b5`
- `iprtprio!ComputeRouteMetric` at `0x1800193f7`
- `iprtprio!ComputeRouteMetric` at `0x1800193b5`
- `iprtprio!ComputeRouteMetric` at `0x1800193f7`

## pseudocode

```c
__int64 __fastcall InitializeLoopbackInterface(struct _ICB *a1, unsigned int a2)
{
  unsigned int v4; // r12d
  __int128 *v5; // r9
  struct _GUID *v6; // rcx
  __int128 *v7; // r9
  __int64 v9; // rax
  _DWORD *InterfaceBinding; // rax
  _DWORD *v11; // rcx
  __int64 v12; // r8
  __int128 *v13; // r9
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  __int64 i; // r15
  __int64 *v18; // r13
  __int64 v19; // rdi
  __int64 v20; // rdx
  DWORD v21; // ecx
  __int128 v22; // xmm0
  __int64 v23; // rdx
  int v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+74h] [rbp-8Ch]
  int v31; // [rsp+78h] [rbp-88h]
  int v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+84h] [rbp-7Ch]
  int v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+8Ch] [rbp-74h]
  int v36; // [rsp+90h] [rbp-70h]
  __int128 v37; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v38; // [rsp+C0h] [rbp-40h] BYREF
  int v39; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v40; // [rsp+D4h] [rbp-2Ch]
  __int128 v41; // [rsp+E4h] [rbp-1Ch]
  int v42; // [rsp+F4h] [rbp-Ch]
  int v43; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v44[2044]; // [rsp+104h] [rbp+4h] BYREF

  memset_0(v24, 0, 0x48u);
  v4 = 0;
  v43 = 0;
  memset_0(v44, 0, sizeof(v44));
  v39 = 0;
  v42 = 0;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v39) = 0;
    v5 = &v38;
    if ( a1 != (struct _ICB *)-688LL )
      LODWORD(v5) = (_DWORD)a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"InitializeLoopbackInterface",
      (_DWORD)v5,
      *((_QWORD *)a1 + 9),
      (__int64)&v39);
  }
  v6 = (struct _GUID *)((char *)a1 + 688);
  if ( a2 )
  {
    SetLoopbackInterfaceForRoutingDomain(v6, 0x21u, a1);
    if ( (unsigned int)GetAdapterInfoV4(16777343, *((_DWORD *)a1 + 176), (int)a1 + 16, (int)a1 + 524, (__int64)a1 + 528) )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
      {
        LOWORD(v39) = 0;
        v7 = &v38;
        if ( a1 != (struct _ICB *)-688LL )
          LODWORD(v7) = (_DWORD)a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)L"InitLoopIf: Couldnt find adapter id for loopback interface",
          (_DWORD)v7,
          *((_QWORD *)a1 + 9),
          (__int64)&v39);
      }
      return 1003;
    }
  }
  else
  {
    SetLoopbackInterfaceForRoutingDomain(v6, 0x57u, a1);
  }
  v9 = *((_QWORD *)a1 + 89);
  *((_DWORD *)a1 + 167) = 1;
  *((_DWORD *)a1 + 128) = 1;
  if ( a2 )
  {
    *(_DWORD *)v9 = 16777343;
    *(_DWORD *)(*((_QWORD *)a1 + 89) + 4LL) = 255;
  }
  else
  {
    *(_QWORD *)(v9 + 4) = 0;
    *(_DWORD *)(v9 + 12) = 0;
    *(_DWORD *)(v9 + 16) = 0x100000;
    **((_DWORD **)a1 + 89) = 128;
  }
  *(_DWORD *)(*((_QWORD *)a1 + 89) + 24LL) = 1;
  RtlAcquireResourceExclusive(&stru_18008C500, 1u);
  InterfaceBinding = (_DWORD *)GetInterfaceBinding(*((unsigned int *)a1 + 4), a2);
  v11 = InterfaceBinding;
  if ( InterfaceBinding )
  {
    InterfaceBinding[4] = 1;
    InterfaceBinding[13] = 1;
    InterfaceBinding[19] = 0;
    if ( a2 )
    {
      InterfaceBinding[27] = 255;
      v14 = 16777343;
    }
    else
    {
      *(_QWORD *)(InterfaceBinding + 27) = 0;
      InterfaceBinding[29] = 0;
      InterfaceBinding[30] = 0x100000;
      v14 = 128;
    }
    v11[26] = v14;
    v11[32] = 1;
    v11[23] = *((_DWORD *)a1 + 131);
    v11[24] = *((_DWORD *)a1 + 132);
    v11[12] = *((_DWORD *)a1 + 36);
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v12 = *((_QWORD *)a1 + 9);
      LOWORD(v43) = 0;
      LOWORD(v39) = 0;
      FormatRRASErrorString(&v43, L"IniteLoopIf: Binding not found for %ws", v12);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v13 = &v38;
        if ( a1 != (struct _ICB *)-688LL )
          LODWORD(v13) = (_DWORD)a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v43,
          (_DWORD)v13,
          *((_QWORD *)a1 + 9),
          (__int64)&v39);
      }
    }
    AddBinding(a1);
  }
  RtlReleaseResource(&stru_18008C500);
  v32 = *((_DWORD *)a1 + 4);
  if ( a2 )
  {
    v26 = 16777343;
    v24[1] = 255;
    v24[0] = 127;
    v28 = 1;
    v29 = 0;
    v36 = 3;
    v15 = ComputeRouteMetric(2);
    v27 = 0;
    v25 = 0;
  }
  else
  {
    *(_QWORD *)v24 = 0;
    v25 = 0;
    v26 = 0x100000;
    v27 = 128;
    v31 = 0;
    v28 = 0;
    v29 = 0x100000;
    v15 = ComputeRouteMetric(2);
    v36 = 1;
    v30 = -1;
  }
  v16 = *((_DWORD *)a1 + 4);
  v35 = v15;
  v33 = 3;
  v34 = 2;
  AddSingleRoute(v16, (int)v24, a2 != 0 ? 255 : 128, 0, 0, 0, 0, a2, (struct _GUID *)a1 + 43, 0);
  RtlAcquireResourceShared(&stru_18008C500, 1u);
  for ( i = 0; i != 57; ++i )
  {
    v18 = &g_leBindingTable[2 * i];
    v19 = *v18;
    while ( (__int64 *)v19 != v18 )
    {
      if ( *(_DWORD *)(v19 + 52) )
      {
        do
        {
          if ( a2 == *(_DWORD *)(v19 + 20) && *(_DWORD *)(v19 + 56) == *((_DWORD *)a1 + 176) )
          {
            v20 = 28LL * v4;
            if ( a2 )
            {
              v21 = *(_DWORD *)(v20 + v19 + 104);
              if ( v21 )
                AddLoopbackRouteV4(v21, *(_DWORD *)(v20 + v19 + 108), (struct _GUID *)a1 + 43);
            }
            else if ( *(_DWORD *)(v20 + v19 + 128) )
            {
              v22 = *(_OWORD *)(v20 + v19 + 108);
              v23 = *(unsigned int *)(v20 + v19 + 104);
              v37 = v22;
              AddLoopbackRouteV6(&v37, v23, (char *)a1 + 688);
            }
          }
          ++v4;
        }
        while ( v4 < *(_DWORD *)(v19 + 52) );
      }
      v19 = *(_QWORD *)v19;
      v4 = 0;
    }
  }
  RtlReleaseResource(&stru_18008C500);
  return 0;
}

```

## disassembly

```asm
0x1800190d0  mov     [rsp-8+arg_10], rbx
0x1800190d5  push    rbp
0x1800190d6  push    rsi
0x1800190d7  push    rdi
0x1800190d8  push    r12
0x1800190da  push    r13
0x1800190dc  push    r14
0x1800190de  push    r15
0x1800190e0  lea     rbp, [rsp-810h]
0x1800190e8  sub     rsp, 910h
0x1800190ef  mov     rax, cs:__security_cookie
0x1800190f6  xor     rax, rsp
0x1800190f9  mov     [rbp+840h+var_40], rax
0x180019100  mov     r14d, edx
0x180019103  mov     rbx, rcx
0x180019106  xor     edx, edx; Val
0x180019108  lea     rcx, [rsp+940h+var_8F0]; void *
0x18001910d  lea     r8d, [rdx+48h]; Size
0x180019111  call    memset_0
0x180019116  xor     r12d, r12d
0x180019119  lea     rcx, [rbp+840h+var_83C]; void *
0x18001911d  xor     edx, edx; Val
0x18001911f  mov     [rbp+840h+var_840], r12d
0x180019123  mov     r8d, 7FCh; Size
0x180019129  call    memset_0
0x18001912e  xorps   xmm0, xmm0
0x180019131  mov     [rbp+840h+var_870], r12d
0x180019135  xor     eax, eax
0x180019137  lea     rsi, [rbx+2B0h]
0x18001913e  mov     r13d, 80h
0x180019144  mov     [rbp+840h+var_84C], eax
0x180019147  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x18001914e  movups  [rbp+840h+var_86C], xmm0
0x180019152  movups  [rbp+840h+var_85C], xmm0
0x180019156  movups  [rbp+840h+var_880], xmm0
0x18001915a  jz      short loc_180019198
0x18001915c  lea     rax, [rbp+840h+var_870]
0x180019160  mov     word ptr [rbp+840h+var_870], r12w
0x180019165  mov     qword ptr [rsp+940h+var_918], rax
0x18001916a  lea     r9, [rbp+840h+var_880]
0x18001916e  mov     rax, [rbx+48h]
0x180019172  lea     r8, aInitializeloop; "InitializeLoopbackInterface"
0x180019179  test    rsi, rsi
0x18001917c  mov     qword ptr [rsp+940h+var_920], rax
0x180019181  lea     rdx, RasRtrmgrParamTraceInfo
0x180019188  cmovnz  r9, rsi
0x18001918c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180019193  call    McTemplateU0zjzz_EventWriteTransfer
0x180019198  mov     edi, 100007Fh
0x18001919d  mov     r8, rbx; struct _ICB *
0x1800191a0  mov     rcx, rsi; struct _GUID *
0x1800191a3  test    r14d, r14d
0x1800191a6  jz      loc_18001922D
0x1800191ac  mov     edx, 21h ; '!'; unsigned int
0x1800191b1  call    SetLoopbackInterfaceForRoutingDomain
0x1800191b6  mov     edx, [rbx+2C0h]
0x1800191bc  lea     rax, [rbx+210h]
0x1800191c3  lea     r9, [rbx+20Ch]
0x1800191ca  mov     qword ptr [rsp+940h+var_920], rax
0x1800191cf  lea     r8, [rbx+10h]
0x1800191d3  mov     ecx, edi
0x1800191d5  call    GetAdapterInfoV4
0x1800191da  test    eax, eax
0x1800191dc  jz      short loc_180019237
0x1800191de  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x1800191e5  jz      short loc_180019223
0x1800191e7  lea     rax, [rbp+840h+var_870]
0x1800191eb  mov     word ptr [rbp+840h+var_870], r12w
0x1800191f0  mov     qword ptr [rsp+940h+var_918], rax
0x1800191f5  lea     r9, [rbp+840h+var_880]
0x1800191f9  mov     rax, [rbx+48h]
0x1800191fd  lea     r8, aInitloopifCoul; "InitLoopIf: Couldnt find adapter id for"...
0x180019204  test    rsi, rsi
0x180019207  mov     qword ptr [rsp+940h+var_920], rax
0x18001920c  lea     rdx, RasRtrmgrParamTraceInfo
0x180019213  cmovnz  r9, rsi
0x180019217  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001921e  call    McTemplateU0zjzz_EventWriteTransfer
0x180019223  mov     eax, 3EBh
0x180019228  jmp     loc_18001950D
0x18001922d  mov     edx, 57h ; 'W'; unsigned int
0x180019232  call    SetLoopbackInterfaceForRoutingDomain
0x180019237  mov     rax, [rbx+2C8h]
0x18001923e  mov     r15d, 1
0x180019244  mov     [rbx+29Ch], r15d
0x18001924b  mov     [rbx+200h], r15d
0x180019252  test    r14d, r14d
0x180019255  jz      short loc_180019269
0x180019257  mov     [rax], edi
0x180019259  mov     rax, [rbx+2C8h]
0x180019260  mov     dword ptr [rax+4], 0FFh
0x180019267  jmp     short loc_180019282
0x180019269  mov     [rax+4], r12
0x18001926d  mov     [rax+0Ch], r12d
0x180019271  mov     dword ptr [rax+10h], 100000h
0x180019278  mov     rax, [rbx+2C8h]
0x18001927f  mov     [rax], r13d
0x180019282  mov     rax, [rbx+2C8h]
0x180019289  lea     rcx, stru_18008C500; Resource
0x180019290  mov     dl, r15b; Wait
0x180019293  mov     [rax+18h], r15d
0x180019297  call    cs:__imp_RtlAcquireResourceExclusive
0x18001929d  mov     ecx, [rbx+10h]
0x1800192a0  mov     edx, r14d
0x1800192a3  call    GetInterfaceBinding
0x1800192a8  mov     rcx, rax
0x1800192ab  test    rax, rax
0x1800192ae  jnz     short loc_18001931E
0x1800192b0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800192b7  jge     short loc_180019314
0x1800192b9  mov     r8, [rbx+48h]
0x1800192bd  lea     rdx, aIniteloopifBin; "IniteLoopIf: Binding not found for %ws"
0x1800192c4  lea     rcx, [rbp+840h+var_840]
0x1800192c8  mov     word ptr [rbp+840h+var_840], r12w
0x1800192cd  mov     word ptr [rbp+840h+var_870], r12w
0x1800192d2  call    FormatRRASErrorString
0x1800192d7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800192de  jge     short loc_180019314
0x1800192e0  lea     rax, [rbp+840h+var_870]
0x1800192e4  test    rsi, rsi
0x1800192e7  mov     qword ptr [rsp+940h+var_918], rax
0x1800192ec  lea     r9, [rbp+840h+var_880]
0x1800192f0  mov     rax, [rbx+48h]
0x1800192f4  lea     r8, [rbp+840h+var_840]
0x1800192f8  cmovnz  r9, rsi
0x1800192fc  mov     qword ptr [rsp+940h+var_920], rax
0x180019301  lea     rdx, RasRtrmgrParamTraceInfo
0x180019308  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001930f  call    McTemplateU0zjzz_EventWriteTransfer
0x180019314  mov     rcx, rbx
0x180019317  call    AddBinding
0x18001931c  jmp     short loc_180019371
0x18001931e  mov     [rax+10h], r15d
0x180019322  mov     [rax+34h], r15d
0x180019326  mov     [rax+4Ch], r12d
0x18001932a  test    r14d, r14d
0x18001932d  jz      short loc_18001933A
0x18001932f  mov     dword ptr [rax+6Ch], 0FFh
0x180019336  mov     eax, edi
0x180019338  jmp     short loc_18001934C
0x18001933a  mov     [rax+6Ch], r12
0x18001933e  mov     [rax+74h], r12d
0x180019342  mov     dword ptr [rax+78h], 100000h
0x180019349  mov     eax, r13d
0x18001934c  mov     [rcx+68h], eax
0x18001934f  mov     [rcx+80h], r15d
0x180019356  mov     eax, [rbx+20Ch]
0x18001935c  mov     [rcx+5Ch], eax
0x18001935f  mov     eax, [rbx+210h]
0x180019365  mov     [rcx+60h], eax
0x180019368  mov     eax, [rbx+90h]
0x18001936e  mov     [rcx+30h], eax
0x180019371  lea     rcx, stru_18008C500; Resource
0x180019378  call    cs:__imp_RtlReleaseResource
0x18001937e  mov     eax, [rbx+10h]
0x180019381  mov     [rbp+840h+var_8C0], eax
0x180019384  test    r14d, r14d
0x180019387  jz      short loc_1800193C7
0x180019389  mov     [rsp+940h+var_8E4], edi
0x18001938d  mov     edi, 2
0x180019392  mov     ecx, edi
0x180019394  mov     [rsp+940h+var_8F0+4], 0FFh
0x18001939c  mov     [rsp+940h+var_8F0], 7Fh
0x1800193a4  mov     [rsp+940h+var_8D8], r15
0x1800193a9  mov     [rsp+940h+var_8D0], r12d
0x1800193ae  mov     [rbp+840h+var_8B0], 3
0x1800193b5  call    cs:__imp_ComputeRouteMetric
0x1800193bb  mov     [rsp+940h+var_8E0], r12
0x1800193c0  mov     [rsp+940h+var_8E8], r12d
0x1800193c5  jmp     short loc_180019409
0x1800193c7  mov     edi, 2
0x1800193cc  mov     qword ptr [rsp+940h+var_8F0], r12
0x1800193d1  mov     ecx, edi
0x1800193d3  mov     [rsp+940h+var_8E8], r12d
0x1800193d8  mov     [rsp+940h+var_8E4], 100000h
0x1800193e0  mov     [rsp+940h+var_8E0], r13
0x1800193e5  mov     [rsp+940h+var_8C8], r12d
0x1800193ea  mov     [rsp+940h+var_8D8], r12
0x1800193ef  mov     [rsp+940h+var_8D0], 100000h
0x1800193f7  call    cs:__imp_ComputeRouteMetric
0x1800193fd  mov     [rbp+840h+var_8B0], r15d
0x180019401  mov     [rsp+940h+var_8CC], 0FFFFFFFFh
0x180019409  mov     ecx, [rbx+10h]; int
0x18001940c  lea     rdx, [rsp+940h+var_8F0]; int
0x180019411  mov     [rsp+940h+var_8F8], r12; __int64
0x180019416  xor     r9d, r9d; int
0x180019419  mov     [rsp+940h+var_900], rsi; struct _GUID *
0x18001941e  mov     [rbp+840h+var_8B4], eax
0x180019421  mov     eax, r14d
0x180019424  mov     [rsp+940h+var_908], r14d; int
0x180019429  neg     eax
0x18001942b  mov     [rsp+940h+var_910], r12d; int
0x180019430  sbb     r8d, r8d
0x180019433  mov     [rsp+940h+var_918], r12d; int
0x180019438  and     r8d, 7Fh
0x18001943c  mov     [rbp+840h+var_8BC], 3
0x180019443  add     r8d, r13d; int
0x180019446  mov     [rbp+840h+var_8B8], edi
0x180019449  mov     [rsp+940h+var_920], r12d; int
0x18001944e  call    AddSingleRoute
0x180019453  mov     dl, r15b; Wait
0x180019456  lea     rcx, stru_18008C500; Resource
0x18001945d  call    cs:__imp_RtlAcquireResourceShared
0x180019463  mov     r15, r12
0x180019466  mov     r13, r15
0x180019469  lea     rcx, g_leBindingTable
0x180019470  shl     r13, 4
0x180019474  add     r13, rcx
0x180019477  mov     rdi, [r13+0]
0x18001947b  jmp     short loc_1800194EC
0x18001947d  cmp     dword ptr [rdi+34h], 0
0x180019481  jbe     short loc_1800194E3
0x180019483  cmp     r14d, [rdi+14h]
0x180019487  jnz     short loc_1800194DA
0x180019489  mov     eax, [rbx+2C0h]
0x18001948f  cmp     [rdi+38h], eax
0x180019492  jnz     short loc_1800194DA
0x180019494  mov     eax, r12d
0x180019497  imul    rdx, rax, 1Ch
0x18001949b  test    r14d, r14d
0x18001949e  jz      short loc_1800194B6
0x1800194a0  mov     ecx, [rdx+rdi+68h]; dwDestAddr
0x1800194a4  test    ecx, ecx
0x1800194a6  jz      short loc_1800194DA
0x1800194a8  mov     edx, [rdx+rdi+6Ch]; int
0x1800194ac  mov     r8, rsi; struct _GUID *
0x1800194af  call    AddLoopbackRouteV4
0x1800194b4  jmp     short loc_1800194DA
0x1800194b6  cmp     dword ptr [rdx+rdi+80h], 0
0x1800194be  jz      short loc_1800194DA
0x1800194c0  movups  xmm0, xmmword ptr [rdx+rdi+6Ch]
0x1800194c5  mov     edx, [rdx+rdi+68h]
0x1800194c9  lea     rcx, [rbp+840h+var_890]
0x1800194cd  mov     r8, rsi
0x1800194d0  movdqu  [rbp+840h+var_890], xmm0
0x1800194d5  call    AddLoopbackRouteV6
0x1800194da  inc     r12d
0x1800194dd  cmp     r12d, [rdi+34h]
0x1800194e1  jb      short loc_180019483
0x1800194e3  mov     rdi, [rdi]
0x1800194e6  mov     r12d, 0
0x1800194ec  cmp     rdi, r13
0x1800194ef  jnz     short loc_18001947D
0x1800194f1  inc     r15
0x1800194f4  cmp     r15, 39h ; '9'
0x1800194f8  jnz     loc_180019466
0x1800194fe  lea     rcx, stru_18008C500; Resource
0x180019505  call    cs:__imp_RtlReleaseResource
0x18001950b  xor     eax, eax
0x18001950d  mov     rcx, [rbp+840h+var_40]
0x180019514  xor     rcx, rsp; StackCookie
0x180019517  call    __security_check_cookie
0x18001951c  mov     rbx, [rsp+940h+arg_10]
0x180019524  add     rsp, 910h
0x18001952b  pop     r15
0x18001952d  pop     r14
0x18001952f  pop     r13
0x180019531  pop     r12
0x180019533  pop     rdi
0x180019534  pop     rsi
0x180019535  pop     rbp
0x180019536  retn
```
