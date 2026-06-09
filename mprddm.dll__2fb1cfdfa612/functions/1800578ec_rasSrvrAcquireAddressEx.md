# rasSrvrAcquireAddressEx

- ea: `0x1800578ec`
- end: `0x180057c6e`
- name: `rasSrvrAcquireAddressEx`
- size: `898`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18004f4e4`
- `0x180051e80`

## callees

- `0x1800578ec`
- `0x1800588f4`
- `0x180058dc4`
- `0x18005b774`
- `0x18005e344`
- `0x180071cec`
- `0x180073664`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180057bdc`
- `KERNEL32!LeaveCriticalSection` at `0x180057bdc`
- `KERNEL32!EnterCriticalSection` at `0x1800579aa`
- `KERNEL32!EnterCriticalSection` at `0x1800579aa`
- `rtutils!LogEventA` at `0x180057c37`
- `rtutils!LogEventA` at `0x180057c37`

## string_xrefs

- `0x1800579e0`: `RDID:%ws - rasSrvrAcquireAddressEx... nboIpAddr : %x%x`
- `0x180057acd`: `RDID:%ws - Address 0x%x is already in use`
- `0x180057c11`: `rasSrvrAcquireAddressEx: Failed to allocate ip address`

## pseudocode

```c
__int64 __fastcall rasSrvrAcquireAddressEx(__int128 *a1, __int64 a2, u_long *a3, u_long *a4, _DWORD *a5)
{
  __int128 v6; // xmm6
  __int64 v7; // rdx
  __int64 v8; // r9
  u_long v9; // r12d
  unsigned int RoutingDomainAddressPool; // edi
  int v11; // esi
  int v12; // r15d
  unsigned int v13; // ebx
  unsigned int v14; // eax
  __int64 *v15; // rax
  _QWORD v17[3]; // [rsp+20h] [rbp-E8h] BYREF
  u_long *v18; // [rsp+38h] [rbp-D0h]
  __int64 v19; // [rsp+40h] [rbp-C8h]
  __int64 v20; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD *plpwsSubStrings; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD plpwsSubStrings_8[3]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v23[30]; // [rsp+88h] [rbp-80h]
  __int16 v24; // [rsp+A6h] [rbp-62h]
  int v25; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v26[2044]; // [rsp+ACh] [rbp-5Ch] BYREF

  v6 = *a1;
  plpwsSubStrings_8[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  plpwsSubStrings_8[2] = *(_OWORD *)L"000-0000-000000000000}";
  v19 = a2;
  plpwsSubStrings_8[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  *(_OWORD *)v23 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v23[14] = *(_OWORD *)L"000000}";
  v18 = a4;
  *(_OWORD *)&v17[1] = v6;
  v20 = 0;
  plpwsSubStrings = 0;
  v24 = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  EnterCriticalSection(&RasSrvrCriticalSection);
  MprConvertGuidToString(&v17[1], v7, plpwsSubStrings_8);
  if ( a5 )
    *a5 = 0;
  if ( (_QWORD)xmmword_1800C9740 )
  {
    v8 = *a3;
    LOWORD(v25) = 0;
    FormatRRASErrorString(
      &v25,
      L"RDID:%ws - rasSrvrAcquireAddressEx... nboIpAddr : %x%x",
      plpwsSubStrings_8,
      v8,
      *(_OWORD *)&v17[1]);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v25);
  }
  v9 = *a3;
  RoutingDomainAddressPool = 0;
  v11 = 0;
  v12 = 0;
  do
  {
    v13 = 0;
    if ( !v9 )
    {
      if ( dword_1800C98DC )
      {
        v14 = RasDhcpAcquireAddress(v19, a3, v18, a5);
      }
      else
      {
        *(_OWORD *)&v17[1] = v6;
        v14 = ((__int64 (__fastcall *)(_QWORD *, __int64, u_long *, u_long *))RasStatAcquireAddress)(
                &v17[1],
                v19,
                a3,
                v18);
      }
      v13 = v14;
      if ( v14 )
        break;
    }
    *(_OWORD *)&v17[1] = v6;
    RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v17[1], 1, &v20);
    if ( !RoutingDomainAddressPool && (v11 = 1, v20) && (v15 = *(__int64 **)(v20 + 24)) != 0 )
    {
      while ( *((_DWORD *)v15 + 4) != *a3 )
      {
        v15 = (__int64 *)*v15;
        if ( !v15 )
        {
          v13 = 0;
          v12 = 1;
          goto LABEL_22;
        }
      }
      if ( v9 )
      {
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v25) = 0;
          FormatRRASErrorString(&v25, L"RDID:%ws - Address 0x%x is already in use", plpwsSubStrings_8);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v25);
        }
        v13 = 735;
        goto LABEL_28;
      }
    }
    else
    {
      v13 = 0;
      v12 = 1;
      if ( v11 != 1 )
        goto LABEL_31;
    }
LABEL_22:
    *(_OWORD *)&v17[1] = v6;
    RoutingDomainAddressPool = RasReleaseRoutingDomainAddressPool(&v17[1]);
    if ( RoutingDomainAddressPool )
    {
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v25) = 0;
        FormatRRASErrorString(
          &v25,
          L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
          RoutingDomainAddressPool);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v25);
      }
    }
    else
    {
      v11 = 0;
    }
  }
  while ( !v12 );
  if ( v11 != 1 )
    goto LABEL_31;
LABEL_28:
  *(_OWORD *)&v17[1] = v6;
  RoutingDomainAddressPool = RasReleaseRoutingDomainAddressPool(&v17[1]);
  if ( RoutingDomainAddressPool && (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(
      &v25,
      L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
      RoutingDomainAddressPool);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v25);
  }
LABEL_31:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  if ( !v13 && RoutingDomainAddressPool )
    v13 = RoutingDomainAddressPool;
  if ( !v9 && v13 )
  {
    plpwsSubStrings = plpwsSubStrings_8;
    if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800C9740 + 1),
        L"rasSrvrAcquireAddressEx: Failed to allocate ip address");
    LogEventA(2u, 0x4EC7u, 1u, (LPSTR *)&plpwsSubStrings);
  }
  return v13;
}

```

## disassembly

```asm
0x1800578ec  mov     rax, rsp
0x1800578ef  mov     [rax+10h], rbx
0x1800578f3  push    rbp
0x1800578f4  push    rsi
0x1800578f5  push    rdi
0x1800578f6  push    r12
0x1800578f8  push    r13
0x1800578fa  push    r14
0x1800578fc  push    r15
0x1800578fe  lea     rbp, [rax-7F8h]
0x180057905  sub     rsp, 8C0h
0x18005790c  movaps  xmmword ptr [rax-48h], xmm6
0x180057910  mov     rax, cs:__security_cookie
0x180057917  xor     rax, rsp
0x18005791a  mov     [rbp+7F0h+var_50], rax
0x180057921  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180057928  xor     eax, eax
0x18005792a  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180057931  mov     r14, r8
0x180057934  movaps  xmm6, xmmword ptr [rcx]
0x180057937  mov     r8d, 7FCh; Size
0x18005793d  mov     r13, [rbp+7F0h+arg_20]
0x180057944  lea     rcx, [rbp+7F0h+var_84C]; void *
0x180057948  movaps  xmmword ptr [rsp+8F0h+plpwsSubStrings+8], xmm0
0x18005794d  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180057954  movaps  [rsp+8F0h+var_888+8], xmm0
0x180057959  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x180057960  mov     [rsp+8F0h+var_8B8], rdx
0x180057965  xor     edx, edx; Val
0x180057967  movaps  [rsp+8F0h+var_898+8], xmm1
0x18005796c  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180057973  movaps  xmmword ptr [rbp+7F0h+var_870], xmm1
0x180057977  movups  xmmword ptr [rbp+7F0h+var_870+0Eh], xmm0
0x18005797b  mov     [rsp+8F0h+var_8C0], r9
0x180057980  movaps  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x180057985  mov     [rsp+8F0h+var_8B0], 0
0x18005798e  mov     [rsp+8F0h+plpwsSubStrings], 0
0x180057997  mov     [rbp+7F0h+var_852], ax
0x18005799b  mov     [rbp+7F0h+var_850], eax
0x18005799e  call    memset_0
0x1800579a3  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800579aa  call    cs:__imp_EnterCriticalSection
0x1800579b0  lea     r8, [rsp+8F0h+plpwsSubStrings+8]
0x1800579b5  lea     rcx, [rsp+8F0h+var_8D8+8]
0x1800579ba  call    MprConvertGuidToString
0x1800579bf  test    r13, r13
0x1800579c2  jz      short loc_1800579CC
0x1800579c4  mov     dword ptr [r13+0], 0
0x1800579cc  cmp     qword ptr cs:xmmword_1800C9740, 0
0x1800579d4  jz      short loc_180057A12
0x1800579d6  mov     r9d, [r14]
0x1800579d9  lea     r8, [rsp+8F0h+plpwsSubStrings+8]
0x1800579de  xor     eax, eax
0x1800579e0  lea     rdx, aRdidWsRassrvra; "RDID:%ws - rasSrvrAcquireAddressEx... n"...
0x1800579e7  lea     rcx, [rbp+7F0h+var_850]
0x1800579eb  mov     word ptr [rbp+7F0h+var_850], ax
0x1800579ef  call    FormatRRASErrorString
0x1800579f4  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800579fb  lea     r8, [rbp+7F0h+var_850]
0x1800579ff  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180057a06  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180057a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a12  mov     r12d, [r14]
0x180057a15  xor     edi, edi
0x180057a17  xor     esi, esi
0x180057a19  xor     r15d, r15d
0x180057a1c  xor     ebx, ebx
0x180057a1e  test    r12d, r12d
0x180057a21  jnz     short loc_180057A69
0x180057a23  cmp     cs:dword_1800C98DC, ebx
0x180057a29  jz      short loc_180057A42
0x180057a2b  mov     r8, [rsp+8F0h+var_8C0]
0x180057a30  mov     r9, r13
0x180057a33  mov     rcx, [rsp+8F0h+var_8B8]
0x180057a38  mov     rdx, r14
0x180057a3b  call    RasDhcpAcquireAddress
0x180057a40  jmp     short loc_180057A5F
0x180057a42  mov     r9, [rsp+8F0h+var_8C0]
0x180057a47  lea     rcx, [rsp+8F0h+var_8D8+8]
0x180057a4c  mov     rdx, [rsp+8F0h+var_8B8]
0x180057a51  mov     r8, r14
0x180057a54  movdqa  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x180057a5a  call    RasStatAcquireAddress
0x180057a5f  mov     ebx, eax
0x180057a61  test    eax, eax
0x180057a63  jnz     loc_180057B79
0x180057a69  lea     r8, [rsp+8F0h+var_8B0]
0x180057a6e  movdqa  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x180057a74  mov     edx, 1
0x180057a79  lea     rcx, [rsp+8F0h+var_8D8+8]
0x180057a7e  call    RasGetRoutingDomainAddressPool
0x180057a83  mov     edi, eax
0x180057a85  test    eax, eax
0x180057a87  jnz     short loc_180057B06
0x180057a89  lea     esi, [rax+1]
0x180057a8c  mov     rax, [rsp+8F0h+var_8B0]
0x180057a91  test    rax, rax
0x180057a94  jz      short loc_180057B06
0x180057a96  mov     rax, [rax+18h]
0x180057a9a  test    rax, rax
0x180057a9d  jz      short loc_180057B06
0x180057a9f  mov     r9d, [r14]
0x180057aa2  cmp     [rax+10h], r9d
0x180057aa6  jz      short loc_180057AB7
0x180057aa8  mov     rax, [rax]
0x180057aab  test    rax, rax
0x180057aae  jnz     short loc_180057AA2
0x180057ab0  xor     ebx, ebx
0x180057ab2  mov     r15d, esi
0x180057ab5  jmp     short loc_180057B15
0x180057ab7  test    r12d, r12d
0x180057aba  jz      short loc_180057B15
0x180057abc  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180057ac4  jz      short loc_180057AFF
0x180057ac6  xor     eax, eax
0x180057ac8  lea     r8, [rsp+8F0h+plpwsSubStrings+8]
0x180057acd  lea     rdx, aRdidWsAddress0; "RDID:%ws - Address 0x%x is already in u"...
0x180057ad4  mov     word ptr [rbp+7F0h+var_850], ax
0x180057ad8  lea     rcx, [rbp+7F0h+var_850]
0x180057adc  call    FormatRRASErrorString
0x180057ae1  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180057ae8  lea     r8, [rbp+7F0h+var_850]
0x180057aec  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180057af3  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180057afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057aff  mov     ebx, 2DFh
0x180057b04  jmp     short loc_180057B7E
0x180057b06  xor     ebx, ebx
0x180057b08  lea     r15d, [rbx+1]
0x180057b0c  cmp     esi, r15d
0x180057b0f  jnz     loc_180057BD5
0x180057b15  lea     rcx, [rsp+8F0h+var_8D8+8]
0x180057b1a  movdqa  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x180057b20  call    RasReleaseRoutingDomainAddressPool
0x180057b25  mov     edi, eax
0x180057b27  test    eax, eax
0x180057b29  jz      short loc_180057B6E
0x180057b2b  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180057b33  jz      short loc_180057B70
0x180057b35  xor     eax, eax
0x180057b37  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180057b3e  mov     r8d, edi
0x180057b41  mov     word ptr [rbp+7F0h+var_850], ax
0x180057b45  lea     rcx, [rbp+7F0h+var_850]
0x180057b49  call    FormatRRASErrorString
0x180057b4e  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180057b55  lea     r8, [rbp+7F0h+var_850]
0x180057b59  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180057b60  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180057b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b6c  jmp     short loc_180057B70
0x180057b6e  xor     esi, esi
0x180057b70  test    r15d, r15d
0x180057b73  jz      loc_180057A1C
0x180057b79  cmp     esi, 1
0x180057b7c  jnz     short loc_180057BD5
0x180057b7e  lea     rcx, [rsp+8F0h+var_8D8+8]
0x180057b83  movdqa  xmmword ptr [rsp+8F0h+var_8D8+8], xmm6
0x180057b89  call    RasReleaseRoutingDomainAddressPool
0x180057b8e  mov     edi, eax
0x180057b90  test    eax, eax
0x180057b92  jz      short loc_180057BD5
0x180057b94  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180057b9c  jz      short loc_180057BD5
0x180057b9e  xor     eax, eax
0x180057ba0  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180057ba7  mov     r8d, edi
0x180057baa  mov     word ptr [rbp+7F0h+var_850], ax
0x180057bae  lea     rcx, [rbp+7F0h+var_850]
0x180057bb2  call    FormatRRASErrorString
0x180057bb7  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180057bbe  lea     r8, [rbp+7F0h+var_850]
0x180057bc2  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180057bc9  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180057bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057bd5  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180057bdc  call    cs:__imp_LeaveCriticalSection
0x180057be2  test    ebx, ebx
0x180057be4  jnz     short loc_180057BEB
0x180057be6  test    edi, edi
0x180057be8  cmovnz  ebx, edi
0x180057beb  test    r12d, r12d
0x180057bee  jnz     short loc_180057C3D
0x180057bf0  test    ebx, ebx
0x180057bf2  jz      short loc_180057C3D
0x180057bf4  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x180057bfb  lea     rax, [rsp+8F0h+plpwsSubStrings+8]
0x180057c00  mov     [rsp+8F0h+plpwsSubStrings], rax
0x180057c05  test    rdx, rdx
0x180057c08  jz      short loc_180057C24
0x180057c0a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180057c11  lea     r8, aRassrvracquire_7; "rasSrvrAcquireAddressEx: Failed to allo"...
0x180057c18  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180057c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c24  mov     ecx, 2; wEventType
0x180057c29  lea     r9, [rsp+8F0h+plpwsSubStrings]; plpwsSubStrings
0x180057c2e  mov     edx, 4EC7h; dwMessageId
0x180057c33  lea     r8d, [rcx-1]; cNumberOfSubStrings
0x180057c37  call    cs:__imp_LogEventA
0x180057c3d  mov     eax, ebx
0x180057c3f  mov     rcx, [rbp+7F0h+var_50]
0x180057c46  xor     rcx, rsp; StackCookie
0x180057c49  call    __security_check_cookie
0x180057c4e  lea     r11, [rsp+8F0h+var_30]
0x180057c56  mov     rbx, [r11+48h]
0x180057c5a  movaps  xmm6, xmmword ptr [r11-10h]
0x180057c5f  mov     rsp, r11
0x180057c62  pop     r15
0x180057c64  pop     r14
0x180057c66  pop     r13
0x180057c68  pop     r12
0x180057c6a  pop     rdi
0x180057c6b  pop     rsi
0x180057c6c  pop     rbp
0x180057c6d  retn
```
