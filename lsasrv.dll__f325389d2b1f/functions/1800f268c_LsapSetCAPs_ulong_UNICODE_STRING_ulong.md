# LsapSetCAPs(ulong,_UNICODE_STRING *,ulong)

- ea: `0x1800f268c`
- end: `0x1800f2ac2`
- name: `?LsapSetCAPs@@YAJKPEAU_UNICODE_STRING@@K@Z`
- size: `1078`
- prototype: `__int64 __fastcall(unsigned int, struct _UNICODE_STRING *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f2e40`
- `0x180101050`

## callees

- `0x1800bace8`
- `0x1800f21e4`
- `0x1800f268c`
- `0x1800f6ab4`
- `0x1800f6de0`
- `0x1800f8218`
- `0x1800f82dc`
- `0x1800f8930`
- `0x1800f8b6c`
- `0x1800f90b8`
- `0x1800f9494`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f26f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2a83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2a9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f26f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2a83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f2a9d`
- `ntdll!RtlPublishWnfStateData` at `0x1800f278a`
- `ntdll!RtlPublishWnfStateData` at `0x1800f278a`
- `ntdll!NtCreateTransaction` at `0x1800f2959`
- `ntdll!NtCreateTransaction` at `0x1800f2959`
- `ntdll!NtCommitTransaction` at `0x1800f2a33`
- `ntdll!NtCommitTransaction` at `0x1800f2a33`
- `ntdll!NtRollbackTransaction` at `0x1800f271c`
- `ntdll!NtRollbackTransaction` at `0x1800f271c`
- `ntdll!NtSetValueKey` at `0x1800f2a09`
- `ntdll!NtSetValueKey` at `0x1800f2a09`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800f2804`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800f28c2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800f2804`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800f28c2`
- `ntdll!RtlReleaseResource` at `0x1800f27af`
- `ntdll!RtlReleaseResource` at `0x1800f27af`
- `ntdll!NtClose` at `0x1800f274c`
- `ntdll!NtClose` at `0x1800f274c`
- `ext-ms-win-authz-claimpolicies-l1-1-0!GetCentralAccessPoliciesByDN` at `0x1800f285e`
- `ext-ms-win-authz-claimpolicies-l1-1-0!GetCentralAccessPoliciesByDN` at `0x1800f285e`

## pseudocode

```c
__int64 __fastcall LsapSetCAPs(unsigned int a1, struct _UNICODE_STRING *a2, int a3)
{
  struct _CENTRAL_ACCESS_POLICY *v5; // rcx
  struct _CENTRAL_ACCESS_POLICY_ENTRY *v6; // r12
  unsigned int v7; // r13d
  unsigned int v8; // r15d
  bool v9; // di
  int v10; // r14d
  NTSTATUS CAPs; // ebx
  __int64 v12; // rdx
  unsigned int v14; // r8d
  unsigned int v15; // r9d
  __int64 i; // rsi
  unsigned int j; // esi
  HLOCAL *v18; // rax
  unsigned int k; // esi
  unsigned int v20; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v21; // [rsp+54h] [rbp-2Ch] BYREF
  unsigned int Data; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v23; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v24; // [rsp+64h] [rbp-1Ch] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-18h] BYREF
  struct _CENTRAL_ACCESS_POLICY *v26; // [rsp+70h] [rbp-10h] BYREF
  struct _CENTRAL_ACCESS_POLICY_ENTRY *v27; // [rsp+78h] [rbp-8h] BYREF
  BOOLEAN v28; // [rsp+C0h] [rbp+40h]
  char v29; // [rsp+D8h] [rbp+58h]

  v26 = 0;
  v20 = 0;
  v5 = 0;
  v27 = 0;
  v6 = 0;
  v21 = 0;
  v7 = 0;
  Data = 0;
  v8 = 0;
  v29 = 0;
  v9 = 0;
  v28 = 0;
  v23 = 0;
  v24 = 0;
  hMem = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
LABEL_3:
      v10 = -1073741811;
      CAPs = -1073741811;
LABEL_4:
      LocalFree(v5);
      goto LABEL_5;
    }
  }
  else if ( a2 )
  {
    goto LABEL_3;
  }
  if ( (a3 & 0xFFFFFFFE) != 0 )
    goto LABEL_3;
  v10 = -1073741811;
  if ( (a3 & 1) != 0 )
  {
    v28 = RtlAcquireResourceExclusive(&stru_18019EF20, 1u);
    if ( !v28 )
    {
LABEL_24:
      CAPs = -1073741595;
      goto LABEL_58;
    }
    CAPs = LsapLoadCAPs(0);
    if ( CAPs >= 0 )
      goto LABEL_57;
  }
  else
  {
    if ( a1 )
    {
      if ( !(unsigned __int8)IsGetCentralAccessPoliciesByDNPresent(0) )
      {
        CAPs = -1073741511;
        goto LABEL_58;
      }
      if ( (unsigned int)GetCentralAccessPoliciesByDN(a2, a1, &v26, &hMem, &v20) || v20 != a1 )
      {
        if ( v20 < a1 )
          LsapEventCAPDownloadFailures(a1, a2, v20, (struct _UNICODE_STRING *)hMem);
        CAPs = -1073740539;
        goto LABEL_58;
      }
      CAPs = LsapValidateAndUpdateFlags(v26, v20, &v27, &v21, &Data, &v23, &v24);
      if ( CAPs < 0 )
        goto LABEL_58;
      v6 = v27;
      v7 = v21;
      v8 = Data;
    }
    v28 = RtlAcquireResourceExclusive(&stru_18019EF20, 1u);
    if ( !v28 )
      goto LABEL_24;
    if ( Handle )
      CAPs = -1073741811;
    else
      CAPs = NtCreateTransaction(&Handle, 2031679, 0, 0, 0, 0, 0, 0, 0, 0);
    v9 = CAPs >= 0;
    if ( CAPs >= 0 )
    {
      CAPs = LsapCapDbWipeClean();
      if ( CAPs >= 0 )
      {
        for ( i = 0; (unsigned int)i < v20; i = (unsigned int)(i + 1) )
        {
          CAPs = LsapCapDbCreateCAP(&v26[i], i, v6, v15);
          if ( CAPs < 0 )
            goto LABEL_58;
        }
        for ( j = 0; j < v7; ++j )
        {
          CAPs = LsapCapDbCreateCAPE(&v6[j], j, v14);
          if ( CAPs < 0 )
            goto LABEL_58;
        }
        Data = v8;
        if ( v8 > 0xFFFF )
          goto LABEL_54;
        CAPs = NtSetValueKey(CAPDbState, &MaxDataSizeValueName, 0, 4u, &Data, 4u);
        if ( CAPs < 0 )
          goto LABEL_58;
        if ( !Handle )
        {
LABEL_54:
          CAPs = -1073741811;
          goto LABEL_58;
        }
        LOBYTE(v12) = 1;
        CAPs = NtCommitTransaction(Handle, v12);
        if ( CAPs >= 0 )
        {
          LsapCapDbSetCAPs(0, v26, v20, v23, v6, v7);
          v9 = 0;
LABEL_57:
          v29 = 1;
        }
      }
    }
  }
LABEL_58:
  v18 = (HLOCAL *)hMem;
  if ( hMem )
  {
    for ( k = 0; k < v20; ++k )
    {
      LocalFree(v18[2 * k + 1]);
      v18 = (HLOCAL *)hMem;
    }
    LocalFree(v18);
    hMem = 0;
  }
  if ( CAPs < 0 )
  {
    v5 = v26;
    goto LABEL_4;
  }
LABEL_5:
  if ( v9 )
  {
    if ( Handle )
    {
      LOBYTE(v12) = 1;
      v10 = NtRollbackTransaction(Handle, v12);
    }
    if ( CAPs >= 0 && v10 < 0 )
      CAPs = v10;
  }
  if ( v28 == 1 && Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( v29 == 1 )
  {
    CAPs = LsapApplyCAPsUpdate(0);
    RtlPublishWnfStateData(WNF_CAPS_CENTRAL_ACCESS_POLICIES_CHANGED, 0, 0, 0, 0);
    if ( CAPs >= 0 )
      LsapUpdateCAPAwareComponents(v24);
  }
  if ( v28 == 1 )
    RtlReleaseResource(&stru_18019EF20);
  return (unsigned int)CAPs;
}

```

## disassembly

```asm
0x1800f268c  mov     [rsp-38h+arg_8], rbx
0x1800f2691  push    rbp
0x1800f2692  push    rsi
0x1800f2693  push    rdi
0x1800f2694  push    r12
0x1800f2696  push    r13
0x1800f2698  push    r14
0x1800f269a  push    r15
0x1800f269c  mov     rbp, rsp
0x1800f269f  sub     rsp, 80h
0x1800f26a6  xor     eax, eax
0x1800f26a8  mov     ebx, ecx
0x1800f26aa  mov     [rbp+var_10], rax
0x1800f26ae  mov     rsi, rdx
0x1800f26b1  mov     [rbp+var_30], eax
0x1800f26b4  mov     ecx, eax; hMem
0x1800f26b6  mov     [rbp+var_8], rax
0x1800f26ba  mov     r12d, eax
0x1800f26bd  mov     [rbp+var_2C], eax
0x1800f26c0  mov     r13d, eax
0x1800f26c3  mov     [rbp+var_28], eax
0x1800f26c6  mov     r15d, eax
0x1800f26c9  mov     [rbp+arg_18], al
0x1800f26cc  mov     dil, al
0x1800f26cf  mov     [rbp+arg_0], al
0x1800f26d2  mov     [rbp+var_20], eax
0x1800f26d5  mov     [rbp+var_1C], eax
0x1800f26d8  mov     [rbp+hMem], rax
0x1800f26dc  test    ebx, ebx
0x1800f26de  jz      loc_1800F27D9
0x1800f26e4  test    rdx, rdx
0x1800f26e7  jnz     loc_1800F27E2
0x1800f26ed  mov     r14d, 0C000000Dh
0x1800f26f3  mov     ebx, r14d
0x1800f26f6  call    cs:__imp_LocalFree
0x1800f26fd  nop     dword ptr [rax+rax+00h]
0x1800f2702  cmp     dil, 1
0x1800f2706  jnz     short loc_1800F2736
0x1800f2708  cmp     cs:Handle, 0
0x1800f2710  jz      short loc_1800F272B
0x1800f2712  mov     rcx, cs:Handle
0x1800f2719  mov     dl, dil
0x1800f271c  call    cs:__imp_NtRollbackTransaction
0x1800f2723  nop     dword ptr [rax+rax+00h]
0x1800f2728  mov     r14d, eax
0x1800f272b  test    ebx, ebx
0x1800f272d  js      short loc_1800F2736
0x1800f272f  test    r14d, r14d
0x1800f2732  cmovs   ebx, r14d
0x1800f2736  mov     dil, [rbp+arg_0]
0x1800f273a  cmp     dil, 1
0x1800f273e  jnz     short loc_1800F2763
0x1800f2740  mov     rcx, cs:Handle; Handle
0x1800f2747  test    rcx, rcx
0x1800f274a  jz      short loc_1800F2763
0x1800f274c  call    cs:__imp_NtClose
0x1800f2753  nop     dword ptr [rax+rax+00h]
0x1800f2758  mov     cs:Handle, 0
0x1800f2763  cmp     [rbp+arg_18], 1
0x1800f2767  jnz     short loc_1800F27A2
0x1800f2769  xor     ecx, ecx; unsigned __int8
0x1800f276b  call    ?LsapApplyCAPsUpdate@@YAJE@Z; LsapApplyCAPsUpdate(uchar)
0x1800f2770  mov     rcx, cs:WNF_CAPS_CENTRAL_ACCESS_POLICIES_CHANGED
0x1800f2777  xor     r9d, r9d
0x1800f277a  xor     r8d, r8d
0x1800f277d  mov     [rsp+80h+Data], 0
0x1800f2786  xor     edx, edx
0x1800f2788  mov     ebx, eax
0x1800f278a  call    cs:__imp_RtlPublishWnfStateData
0x1800f2791  nop     dword ptr [rax+rax+00h]
0x1800f2796  test    ebx, ebx
0x1800f2798  js      short loc_1800F27A2
0x1800f279a  mov     ecx, [rbp+var_1C]; unsigned int
0x1800f279d  call    ?LsapUpdateCAPAwareComponents@@YAJK@Z; LsapUpdateCAPAwareComponents(ulong)
0x1800f27a2  cmp     dil, 1
0x1800f27a6  jnz     short loc_1800F27BB
0x1800f27a8  lea     rcx, stru_18019EF20; Resource
0x1800f27af  call    cs:__imp_RtlReleaseResource
0x1800f27b6  nop     dword ptr [rax+rax+00h]
0x1800f27bb  mov     eax, ebx
0x1800f27bd  mov     rbx, [rsp+80h+arg_8]
0x1800f27c5  add     rsp, 80h
0x1800f27cc  pop     r15
0x1800f27ce  pop     r14
0x1800f27d0  pop     r13
0x1800f27d2  pop     r12
0x1800f27d4  pop     rdi
0x1800f27d5  pop     rsi
0x1800f27d6  pop     rbp
0x1800f27d7  retn
0x1800f27d9  test    rsi, rsi
0x1800f27dc  jnz     loc_1800F26ED
0x1800f27e2  test    r8d, 0FFFFFFFEh
0x1800f27e9  jnz     loc_1800F26ED
0x1800f27ef  mov     r14d, 0C000000Dh
0x1800f27f5  test    r8b, 1
0x1800f27f9  jz      short loc_1800F2837
0x1800f27fb  mov     dl, 1; Wait
0x1800f27fd  lea     rcx, stru_18019EF20; Resource
0x1800f2804  call    cs:__imp_RtlAcquireResourceExclusive
0x1800f280b  nop     dword ptr [rax+rax+00h]
0x1800f2810  mov     [rbp+arg_0], al
0x1800f2813  test    al, al
0x1800f2815  jnz     short loc_1800F2821
0x1800f2817  mov     ebx, 0C00000E5h
0x1800f281c  jmp     loc_1800F2A69
0x1800f2821  xor     ecx, ecx; unsigned __int8
0x1800f2823  call    ?LsapLoadCAPs@@YAJE@Z; LsapLoadCAPs(uchar)
0x1800f2828  mov     ebx, eax
0x1800f282a  test    eax, eax
0x1800f282c  js      loc_1800F2A69
0x1800f2832  jmp     loc_1800F2A65
0x1800f2837  test    ebx, ebx
0x1800f2839  jz      short loc_1800F28B9
0x1800f283b  call    IsGetCentralAccessPoliciesByDNPresent
0x1800f2840  test    al, al
0x1800f2842  jz      loc_1800F290A
0x1800f2848  lea     rax, [rbp+var_30]
0x1800f284c  mov     edx, ebx
0x1800f284e  lea     r9, [rbp+hMem]
0x1800f2852  mov     [rsp+80h+Data], rax
0x1800f2857  lea     r8, [rbp+var_10]
0x1800f285b  mov     rcx, rsi
0x1800f285e  call    cs:__imp_GetCentralAccessPoliciesByDN
0x1800f2865  nop     dword ptr [rax+rax+00h]
0x1800f286a  test    eax, eax
0x1800f286c  jnz     short loc_1800F28E8
0x1800f286e  mov     eax, [rbp+var_30]
0x1800f2871  cmp     eax, ebx
0x1800f2873  jnz     short loc_1800F28E8
0x1800f2875  lea     rcx, [rbp+var_1C]
0x1800f2879  mov     edx, eax; unsigned int
0x1800f287b  mov     [rsp+80h+var_50], rcx; unsigned int *
0x1800f2880  lea     r9, [rbp+var_2C]; unsigned int *
0x1800f2884  lea     rcx, [rbp+var_20]
0x1800f2888  mov     qword ptr [rsp+80h+DataSize], rcx; unsigned int *
0x1800f288d  lea     r8, [rbp+var_8]; struct _CENTRAL_ACCESS_POLICY_ENTRY **
0x1800f2891  lea     rcx, [rbp+var_28]
0x1800f2895  mov     [rsp+80h+Data], rcx; unsigned int *
0x1800f289a  mov     rcx, [rbp+var_10]; struct _CENTRAL_ACCESS_POLICY *
0x1800f289e  call    ?LsapValidateAndUpdateFlags@@YAJQEAU_CENTRAL_ACCESS_POLICY@@KQEAPEAU_CENTRAL_ACCESS_POLICY_ENTRY@@PEAK222@Z; LsapValidateAndUpdateFlags(_CENTRAL_ACCESS_POLICY * const,ulong,_CENTRAL_ACCESS_POLICY_ENTRY * * const,ulong *,ulong *,ulong *,ulong *)
0x1800f28a3  mov     ebx, eax
0x1800f28a5  test    eax, eax
0x1800f28a7  js      loc_1800F2A69
0x1800f28ad  mov     r12, [rbp+var_8]
0x1800f28b1  mov     r13d, [rbp+var_2C]
0x1800f28b5  mov     r15d, [rbp+var_28]
0x1800f28b9  mov     dl, 1; Wait
0x1800f28bb  lea     rcx, stru_18019EF20; Resource
0x1800f28c2  call    cs:__imp_RtlAcquireResourceExclusive
0x1800f28c9  nop     dword ptr [rax+rax+00h]
0x1800f28ce  mov     [rbp+arg_0], al
0x1800f28d1  test    al, al
0x1800f28d3  jz      loc_1800F2817
0x1800f28d9  cmp     cs:Handle, 0
0x1800f28e1  jz      short loc_1800F2914
0x1800f28e3  mov     ebx, r14d
0x1800f28e6  jmp     short loc_1800F2967
0x1800f28e8  mov     eax, [rbp+var_30]
0x1800f28eb  cmp     eax, ebx
0x1800f28ed  jnb     short loc_1800F2900
0x1800f28ef  mov     r9, [rbp+hMem]; struct _UNICODE_STRING *
0x1800f28f3  mov     r8d, eax; unsigned int
0x1800f28f6  mov     rdx, rsi; struct _UNICODE_STRING *
0x1800f28f9  mov     ecx, ebx; unsigned int
0x1800f28fb  call    ?LsapEventCAPDownloadFailures@@YAXKPEAU_UNICODE_STRING@@K0@Z; LsapEventCAPDownloadFailures(ulong,_UNICODE_STRING *,ulong,_UNICODE_STRING *)
0x1800f2900  mov     ebx, 0C0000505h
0x1800f2905  jmp     loc_1800F2A69
0x1800f290a  mov     ebx, 0C0000139h
0x1800f290f  jmp     loc_1800F2A69
0x1800f2914  mov     [rsp+80h+var_38], 0
0x1800f291d  lea     rcx, Handle
0x1800f2924  mov     [rsp+80h+var_40], 0
0x1800f292d  xor     r9d, r9d
0x1800f2930  mov     [rsp+80h+var_48], 0
0x1800f2938  xor     r8d, r8d
0x1800f293b  mov     dword ptr [rsp+80h+var_50], 0
0x1800f2943  mov     edx, 1F003Fh
0x1800f2948  mov     [rsp+80h+DataSize], 0
0x1800f2950  mov     [rsp+80h+Data], 0
0x1800f2959  call    cs:__imp_NtCreateTransaction
0x1800f2960  nop     dword ptr [rax+rax+00h]
0x1800f2965  mov     ebx, eax
0x1800f2967  mov     edi, ebx
0x1800f2969  shr     edi, 1Fh
0x1800f296c  xor     dil, 1
0x1800f2970  test    ebx, ebx
0x1800f2972  js      loc_1800F2A69
0x1800f2978  call    ?LsapCapDbWipeClean@@YAJXZ; LsapCapDbWipeClean(void)
0x1800f297d  mov     ebx, eax
0x1800f297f  test    eax, eax
0x1800f2981  js      loc_1800F2A69
0x1800f2987  xor     esi, esi
0x1800f2989  cmp     esi, [rbp+var_30]
0x1800f298c  jnb     short loc_1800F29B2
0x1800f298e  mov     rax, [rbp+var_10]
0x1800f2992  lea     rcx, [rsi+rsi*8]
0x1800f2996  mov     r8, r12; struct _CENTRAL_ACCESS_POLICY_ENTRY *
0x1800f2999  mov     edx, esi; unsigned int
0x1800f299b  lea     rcx, [rax+rcx*8]; struct _CENTRAL_ACCESS_POLICY *
0x1800f299f  call    ?LsapCapDbCreateCAP@@YAJPEAU_CENTRAL_ACCESS_POLICY@@KPEBU_CENTRAL_ACCESS_POLICY_ENTRY@@K@Z; LsapCapDbCreateCAP(_CENTRAL_ACCESS_POLICY *,ulong,_CENTRAL_ACCESS_POLICY_ENTRY const *,ulong)
0x1800f29a4  mov     ebx, eax
0x1800f29a6  test    eax, eax
0x1800f29a8  js      loc_1800F2A69
0x1800f29ae  inc     esi
0x1800f29b0  jmp     short loc_1800F2989
0x1800f29b2  xor     esi, esi
0x1800f29b4  cmp     esi, r13d
0x1800f29b7  jnb     short loc_1800F29D7
0x1800f29b9  mov     eax, esi
0x1800f29bb  mov     edx, esi; unsigned int
0x1800f29bd  imul    rcx, rax, 68h ; 'h'
0x1800f29c1  add     rcx, r12; struct _CENTRAL_ACCESS_POLICY_ENTRY *
0x1800f29c4  call    ?LsapCapDbCreateCAPE@@YAJPEAU_CENTRAL_ACCESS_POLICY_ENTRY@@KK@Z; LsapCapDbCreateCAPE(_CENTRAL_ACCESS_POLICY_ENTRY *,ulong,ulong)
0x1800f29c9  mov     ebx, eax
0x1800f29cb  test    eax, eax
0x1800f29cd  js      loc_1800F2A69
0x1800f29d3  inc     esi
0x1800f29d5  jmp     short loc_1800F29B4
0x1800f29d7  mov     [rbp+var_28], r15d
0x1800f29db  cmp     r15d, 0FFFFh
0x1800f29e2  ja      short loc_1800F2A25
0x1800f29e4  mov     rcx, cs:?CAPDbState@@3U_LSAP_CAP_DB_STATE@@A; KeyHandle
0x1800f29eb  lea     rax, [rbp+var_28]
0x1800f29ef  mov     r9d, 4; Type
0x1800f29f5  lea     rdx, ?MaxDataSizeValueName@@3U_UNICODE_STRING@@A; ValueName
0x1800f29fc  mov     [rsp+80h+DataSize], r9d; DataSize
0x1800f2a01  xor     r8d, r8d; TitleIndex
0x1800f2a04  mov     [rsp+80h+Data], rax; Data
0x1800f2a09  call    cs:__imp_NtSetValueKey
0x1800f2a10  nop     dword ptr [rax+rax+00h]
0x1800f2a15  mov     ebx, eax
0x1800f2a17  test    eax, eax
0x1800f2a19  js      short loc_1800F2A69
0x1800f2a1b  cmp     cs:Handle, 0
0x1800f2a23  jnz     short loc_1800F2A2A
0x1800f2a25  mov     ebx, r14d
0x1800f2a28  jmp     short loc_1800F2A69
0x1800f2a2a  mov     rcx, cs:Handle
0x1800f2a31  mov     dl, 1
0x1800f2a33  call    cs:__imp_NtCommitTransaction
0x1800f2a3a  nop     dword ptr [rax+rax+00h]
0x1800f2a3f  mov     ebx, eax
0x1800f2a41  test    eax, eax
0x1800f2a43  js      short loc_1800F2A69
0x1800f2a45  mov     r9d, [rbp+var_20]; unsigned int
0x1800f2a49  xor     ecx, ecx; unsigned __int8
0x1800f2a4b  mov     r8d, [rbp+var_30]; unsigned int
0x1800f2a4f  mov     rdx, [rbp+var_10]; struct _CENTRAL_ACCESS_POLICY *
0x1800f2a53  mov     [rsp+80h+DataSize], r13d; unsigned int
0x1800f2a58  mov     [rsp+80h+Data], r12; struct _CENTRAL_ACCESS_POLICY_ENTRY *
0x1800f2a5d  call    ?LsapCapDbSetCAPs@@YAXEPEAU_CENTRAL_ACCESS_POLICY@@KKPEAU_CENTRAL_ACCESS_POLICY_ENTRY@@K@Z; LsapCapDbSetCAPs(uchar,_CENTRAL_ACCESS_POLICY *,ulong,ulong,_CENTRAL_ACCESS_POLICY_ENTRY *,ulong)
0x1800f2a62  xor     dil, dil
0x1800f2a65  mov     [rbp+arg_18], 1
0x1800f2a69  mov     rax, [rbp+hMem]
0x1800f2a6d  test    rax, rax
0x1800f2a70  jz      short loc_1800F2AB1
0x1800f2a72  xor     esi, esi
0x1800f2a74  cmp     [rbp+var_30], esi
0x1800f2a77  jbe     short loc_1800F2A9A
0x1800f2a79  mov     ecx, esi
0x1800f2a7b  add     rcx, rcx
0x1800f2a7e  mov     rcx, [rax+rcx*8+8]; hMem
0x1800f2a83  call    cs:__imp_LocalFree
0x1800f2a8a  nop     dword ptr [rax+rax+00h]
0x1800f2a8f  mov     rax, [rbp+hMem]
0x1800f2a93  inc     esi
0x1800f2a95  cmp     esi, [rbp+var_30]
0x1800f2a98  jb      short loc_1800F2A79
0x1800f2a9a  mov     rcx, rax; hMem
0x1800f2a9d  call    cs:__imp_LocalFree
0x1800f2aa4  nop     dword ptr [rax+rax+00h]
0x1800f2aa9  mov     [rbp+hMem], 0
0x1800f2ab1  test    ebx, ebx
0x1800f2ab3  jns     loc_1800F2702
0x1800f2ab9  mov     rcx, [rbp+var_10]
0x1800f2abd  jmp     loc_1800F26F6
```
