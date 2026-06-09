# rasSrvrAcquireAddressEx

- ea: `0x1800597d4`
- end: `0x180059b72`
- name: `rasSrvrAcquireAddressEx`
- size: `926`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180050d54`
- `0x1800538b0`

## callees

- `0x1800597d4`
- `0x18005a844`
- `0x18005ad18`
- `0x18005d948`
- `0x18006076c`
- `0x1800755b8`
- `0x1800771b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180059ad3`
- `KERNEL32!LeaveCriticalSection` at `0x180059ad3`
- `KERNEL32!EnterCriticalSection` at `0x1800598a2`
- `KERNEL32!EnterCriticalSection` at `0x1800598a2`
- `rtutils!LogEventA` at `0x180059b34`
- `rtutils!LogEventA` at `0x180059b34`

## string_xrefs

- `0x1800598d7`: `RDID:%ws - rasSrvrAcquireAddressEx... nboIpAddr : %x%x`
- `0x1800599c7`: `RDID:%ws - Address 0x%x is already in use`
- `0x180059b0e`: `rasSrvrAcquireAddressEx: Failed to allocate ip address`

## pseudocode

```c
__int64 __fastcall rasSrvrAcquireAddressEx(__int128 *a1, __int64 a2, u_long *a3, u_long *a4, _DWORD *a5)
{
  unsigned int v5; // ebx
  __int128 v7; // xmm6
  unsigned int RoutingDomainAddressPool; // edi
  int v9; // r14d
  __int64 v10; // rdx
  __int64 v11; // r9
  u_long v12; // r12d
  int v13; // r15d
  unsigned int v14; // eax
  __int64 *v15; // rax
  unsigned int v16; // eax
  _QWORD v18[3]; // [rsp+20h] [rbp-E8h] BYREF
  u_long *v19; // [rsp+38h] [rbp-D0h]
  __int64 v20; // [rsp+40h] [rbp-C8h]
  __int64 v21; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD *plpwsSubStrings; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD plpwsSubStrings_8[4]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+98h] [rbp-70h]
  int v25; // [rsp+A0h] [rbp-68h]
  wchar_t v26; // [rsp+A4h] [rbp-64h]
  __int16 v27; // [rsp+A6h] [rbp-62h]
  int v28; // [rsp+A8h] [rbp-60h] BYREF
  char v29[2044]; // [rsp+ACh] [rbp-5Ch] BYREF

  v5 = 0;
  v7 = *a1;
  RoutingDomainAddressPool = 0;
  plpwsSubStrings_8[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v9 = 0;
  v25 = *(_DWORD *)L"0}";
  plpwsSubStrings_8[2] = *(_OWORD *)L"000-0000-000000000000}";
  plpwsSubStrings_8[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v26 = a00000000000000[38];
  v20 = a2;
  v24 = *(_QWORD *)L"00000}";
  v19 = a4;
  *(_OWORD *)&v18[1] = v7;
  v21 = 0;
  plpwsSubStrings_8[3] = *(_OWORD *)L"-000000000000}";
  v27 = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  EnterCriticalSection(&RasSrvrCriticalSection);
  MprConvertGuidToString(&v18[1], v10, plpwsSubStrings_8);
  if ( a5 )
    *a5 = 0;
  if ( (_QWORD)xmmword_1800D0740 )
  {
    v11 = *a3;
    LOWORD(v28) = 0;
    FormatRRASErrorString(
      &v28,
      L"RDID:%ws - rasSrvrAcquireAddressEx... nboIpAddr : %x%x",
      plpwsSubStrings_8,
      v11,
      *(_OWORD *)&v18[1]);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v28);
  }
  v12 = *a3;
  v13 = 0;
  while ( 1 )
  {
    if ( !v12 )
    {
      if ( dword_1800D08DC )
      {
        v14 = RasDhcpAcquireAddress(v20, a3, v19, a5);
      }
      else
      {
        *(_OWORD *)&v18[1] = v7;
        v14 = ((__int64 (__fastcall *)(_QWORD *, __int64, u_long *, u_long *))RasStatAcquireAddress)(
                &v18[1],
                v20,
                a3,
                v19);
      }
      v5 = v14;
      if ( v14 )
        break;
    }
    *(_OWORD *)&v18[1] = v7;
    RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v18[1], 1, &v21);
    if ( !RoutingDomainAddressPool && (v9 = 1, v21) && (v15 = *(__int64 **)(v21 + 24)) != 0 )
    {
      while ( *((_DWORD *)v15 + 4) != *a3 )
      {
        v15 = (__int64 *)*v15;
        if ( !v15 )
        {
          v5 = 0;
          v13 = 1;
          goto LABEL_22;
        }
      }
      if ( v12 )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v28) = 0;
          FormatRRASErrorString(&v28, L"RDID:%ws - Address 0x%x is already in use", plpwsSubStrings_8);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v28);
        }
        v5 = 735;
        goto LABEL_29;
      }
    }
    else
    {
      v5 = 0;
      v13 = 1;
      if ( v9 != 1 )
        goto LABEL_32;
    }
LABEL_22:
    *(_OWORD *)&v18[1] = v7;
    RoutingDomainAddressPool = RasReleaseRoutingDomainAddressPool(&v18[1]);
    if ( RoutingDomainAddressPool )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v28) = 0;
        FormatRRASErrorString(
          &v28,
          L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
          RoutingDomainAddressPool);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v28);
      }
    }
    else
    {
      v9 = 0;
    }
    if ( v13 )
      break;
    v5 = 0;
  }
  if ( v9 != 1 )
    goto LABEL_32;
LABEL_29:
  *(_OWORD *)&v18[1] = v7;
  v16 = RasReleaseRoutingDomainAddressPool(&v18[1]);
  RoutingDomainAddressPool = v16;
  if ( v16 && (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v28, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v16);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v28);
  }
LABEL_32:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  if ( !v5 && RoutingDomainAddressPool )
    v5 = RoutingDomainAddressPool;
  if ( !v12 && v5 )
  {
    plpwsSubStrings = plpwsSubStrings_8;
    if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800D0740 + 1),
        L"rasSrvrAcquireAddressEx: Failed to allocate ip address");
    LogEventA(2u, 0x4EC7u, 1u, (LPSTR *)&plpwsSubStrings);
  }
  return v5;
}

```

## disassembly

```asm
0x1800597d4  mov     rax, rsp
0x1800597d7  mov     [rax+10h], rbx
0x1800597db  push    rbp
0x1800597dc  push    rsi
0x1800597dd  push    rdi
0x1800597de  push    r12
0x1800597e0  push    r13
0x1800597e2  push    r14
0x1800597e4  push    r15
0x1800597e6  lea     rbp, [rax-7F8h]
0x1800597ed  sub     rsp, 8C0h
0x1800597f4  movaps  xmmword ptr [rax-48h], xmm6
0x1800597f8  mov     rax, cs:__security_cookie
0x1800597ff  xor     rax, rsp
0x180059802  mov     [rbp+7F0h+var_50], rax
0x180059809  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180059810  xor     ebx, ebx
0x180059812  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x180059818  mov     rsi, r8
0x18005981b  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180059822  mov     r8d, 7FCh; Size
0x180059828  movaps  xmm6, xmmword ptr [rcx]
0x18005982b  mov     edi, ebx
0x18005982d  mov     r13, [rbp+7F0h+arg_20]
0x180059834  lea     rcx, [rbp+7F0h+var_84C]; void *
0x180059838  movaps  xmmword ptr [rsp+8F0h+plpwsSubStrings+8], xmm0
0x18005983d  mov     r14d, ebx
0x180059840  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180059847  mov     [rbp+7F0h+var_858], eax
0x18005984a  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x180059851  movaps  [rsp+8F0h+var_888+8], xmm0
0x180059856  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x18005985e  movaps  [rsp+8F0h+var_898+8], xmm1
0x180059863  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18005986a  mov     [rbp+7F0h+var_854], ax
0x18005986e  xor     eax, eax
0x180059870  mov     [rsp+8F0h+var_8B8], rdx
0x180059875  xor     edx, edx; Val
0x180059877  movsd   [rbp+7F0h+var_860], xmm0
0x18005987c  mov     [rsp+8F0h+var_8C0], r9
0x180059881  movaps  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x180059886  mov     [rsp+8F0h+var_8B0], rbx
0x18005988b  movaps  [rbp+7F0h+var_870], xmm1
0x18005988f  mov     [rbp+7F0h+var_852], ax
0x180059893  mov     [rbp+7F0h+var_850], ebx
0x180059896  call    memset_0
0x18005989b  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800598a2  call    cs:__imp_EnterCriticalSection
0x1800598a9  nop     dword ptr [rax+rax+00h]
0x1800598ae  lea     r8, [rsp+8F0h+plpwsSubStrings+8]
0x1800598b3  lea     rcx, [rsp+8F0h+var_8D8+8]
0x1800598b8  call    MprConvertGuidToString
0x1800598bd  test    r13, r13
0x1800598c0  jz      short loc_1800598C6
0x1800598c2  mov     [r13+0], ebx
0x1800598c6  cmp     qword ptr cs:xmmword_1800D0740, rbx
0x1800598cd  jz      short loc_180059909
0x1800598cf  mov     r9d, [rsi]
0x1800598d2  lea     r8, [rsp+8F0h+plpwsSubStrings+8]
0x1800598d7  lea     rdx, aRdidWsRassrvra; "RDID:%ws - rasSrvrAcquireAddressEx... n"...
0x1800598de  mov     word ptr [rbp+7F0h+var_850], bx
0x1800598e2  lea     rcx, [rbp+7F0h+var_850]
0x1800598e6  call    FormatRRASErrorString
0x1800598eb  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800598f2  lea     r8, [rbp+7F0h+var_850]
0x1800598f6  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800598fd  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059909  mov     r12d, [rsi]
0x18005990c  mov     r15d, ebx
0x18005990f  test    r12d, r12d
0x180059912  jnz     short loc_18005995B
0x180059914  cmp     cs:dword_1800D08DC, r12d
0x18005991b  jz      short loc_180059934
0x18005991d  mov     r8, [rsp+8F0h+var_8C0]
0x180059922  mov     r9, r13
0x180059925  mov     rcx, [rsp+8F0h+var_8B8]
0x18005992a  mov     rdx, rsi
0x18005992d  call    RasDhcpAcquireAddress
0x180059932  jmp     short loc_180059951
0x180059934  mov     r9, [rsp+8F0h+var_8C0]
0x180059939  lea     rcx, [rsp+8F0h+var_8D8+8]
0x18005993e  mov     rdx, [rsp+8F0h+var_8B8]
0x180059943  mov     r8, rsi
0x180059946  movdqa  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x18005994c  call    RasStatAcquireAddress
0x180059951  mov     ebx, eax
0x180059953  test    eax, eax
0x180059955  jnz     loc_180059A70
0x18005995b  lea     r8, [rsp+8F0h+var_8B0]
0x180059960  movdqa  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x180059966  mov     edx, 1
0x18005996b  lea     rcx, [rsp+8F0h+var_8D8+8]
0x180059970  call    RasGetRoutingDomainAddressPool
0x180059975  xor     ecx, ecx
0x180059977  mov     edi, eax
0x180059979  test    eax, eax
0x18005997b  jnz     short loc_1800599F8
0x18005997d  lea     r14d, [rax+1]
0x180059981  mov     rax, [rsp+8F0h+var_8B0]
0x180059986  test    rax, rax
0x180059989  jz      short loc_1800599F8
0x18005998b  mov     rax, [rax+18h]
0x18005998f  test    rax, rax
0x180059992  jz      short loc_1800599F8
0x180059994  mov     r9d, [rsi]
0x180059997  cmp     [rax+10h], r9d
0x18005999b  jz      short loc_1800599AC
0x18005999d  mov     rax, [rax]
0x1800599a0  test    rax, rax
0x1800599a3  jnz     short loc_180059997
0x1800599a5  mov     ebx, ecx
0x1800599a7  mov     r15d, r14d
0x1800599aa  jmp     short loc_180059A09
0x1800599ac  test    r12d, r12d
0x1800599af  jz      short loc_180059A09
0x1800599b1  cmp     qword ptr cs:xmmword_1800D0740, rcx
0x1800599b8  jz      short loc_1800599F1
0x1800599ba  mov     word ptr [rbp+7F0h+var_850], cx
0x1800599be  lea     r8, [rsp+8F0h+plpwsSubStrings+8]
0x1800599c3  lea     rcx, [rbp+7F0h+var_850]
0x1800599c7  lea     rdx, aRdidWsAddress0; "RDID:%ws - Address 0x%x is already in u"...
0x1800599ce  call    FormatRRASErrorString
0x1800599d3  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800599da  lea     r8, [rbp+7F0h+var_850]
0x1800599de  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800599e5  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800599ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599f1  mov     ebx, 2DFh
0x1800599f6  jmp     short loc_180059A76
0x1800599f8  mov     ebx, ecx
0x1800599fa  mov     r15d, 1
0x180059a00  cmp     r14d, r15d
0x180059a03  jnz     loc_180059ACC
0x180059a09  lea     rcx, [rsp+8F0h+var_8D8+8]
0x180059a0e  movdqa  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x180059a14  call    RasReleaseRoutingDomainAddressPool
0x180059a19  mov     edi, eax
0x180059a1b  xor     eax, eax
0x180059a1d  test    edi, edi
0x180059a1f  jz      short loc_180059A61
0x180059a21  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180059a28  jz      short loc_180059A64
0x180059a2a  mov     r8d, edi
0x180059a2d  mov     word ptr [rbp+7F0h+var_850], ax
0x180059a31  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180059a38  lea     rcx, [rbp+7F0h+var_850]
0x180059a3c  call    FormatRRASErrorString
0x180059a41  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180059a48  lea     r8, [rbp+7F0h+var_850]
0x180059a4c  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059a53  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a5f  jmp     short loc_180059A64
0x180059a61  mov     r14d, eax
0x180059a64  test    r15d, r15d
0x180059a67  jnz     short loc_180059A70
0x180059a69  xor     ebx, ebx
0x180059a6b  jmp     loc_18005990F
0x180059a70  cmp     r14d, 1
0x180059a74  jnz     short loc_180059ACC
0x180059a76  lea     rcx, [rsp+8F0h+var_8D8+8]
0x180059a7b  movdqa  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x180059a81  call    RasReleaseRoutingDomainAddressPool
0x180059a86  xor     esi, esi
0x180059a88  mov     edi, eax
0x180059a8a  test    eax, eax
0x180059a8c  jz      short loc_180059ACC
0x180059a8e  cmp     qword ptr cs:xmmword_1800D0740, rsi
0x180059a95  jz      short loc_180059ACC
0x180059a97  mov     r8d, eax
0x180059a9a  mov     word ptr [rbp+7F0h+var_850], si
0x180059a9e  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180059aa5  lea     rcx, [rbp+7F0h+var_850]
0x180059aa9  call    FormatRRASErrorString
0x180059aae  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180059ab5  lea     r8, [rbp+7F0h+var_850]
0x180059ab9  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059ac0  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059acc  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180059ad3  call    cs:__imp_LeaveCriticalSection
0x180059ada  nop     dword ptr [rax+rax+00h]
0x180059adf  test    ebx, ebx
0x180059ae1  jnz     short loc_180059AE8
0x180059ae3  test    edi, edi
0x180059ae5  cmovnz  ebx, edi
0x180059ae8  test    r12d, r12d
0x180059aeb  jnz     short loc_180059B40
0x180059aed  test    ebx, ebx
0x180059aef  jz      short loc_180059B40
0x180059af1  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x180059af8  lea     rax, [rsp+8F0h+plpwsSubStrings+8]
0x180059afd  mov     [rsp+8F0h+plpwsSubStrings], rax
0x180059b02  test    rdx, rdx
0x180059b05  jz      short loc_180059B21
0x180059b07  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059b0e  lea     r8, aRassrvracquire_7; "rasSrvrAcquireAddressEx: Failed to allo"...
0x180059b15  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b21  mov     ecx, 2; wEventType
0x180059b26  lea     r9, [rsp+8F0h+plpwsSubStrings]; plpwsSubStrings
0x180059b2b  mov     edx, 4EC7h; dwMessageId
0x180059b30  lea     r8d, [rcx-1]; cNumberOfSubStrings
0x180059b34  call    cs:__imp_LogEventA
0x180059b3b  nop     dword ptr [rax+rax+00h]
0x180059b40  mov     eax, ebx
0x180059b42  mov     rcx, [rbp+7F0h+var_50]
0x180059b49  xor     rcx, rsp; StackCookie
0x180059b4c  call    __security_check_cookie
0x180059b51  lea     r11, [rsp+8F0h+var_30]
0x180059b59  mov     rbx, [r11+48h]
0x180059b5d  movaps  xmm6, xmmword ptr [r11-10h]
0x180059b62  mov     rsp, r11
0x180059b65  pop     r15
0x180059b67  pop     r14
0x180059b69  pop     r13
0x180059b6b  pop     r12
0x180059b6d  pop     rdi
0x180059b6e  pop     rsi
0x180059b6f  pop     rbp
0x180059b70  retn
```
