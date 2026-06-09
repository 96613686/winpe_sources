# NlSamInitialize

- ea: `0x1800205b4`
- end: `0x180020ba7`
- name: `NlSamInitialize`
- size: `1523`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013d2c`
- `0x18001a470`
- `0x180033148`
- `0x18004339c`

## callees

- `0x180006c50`
- `0x1800205b4`
- `0x180020bb0`
- `0x18002ee7c`
- `0x18002f014`
- `0x18004d7dc`
- `0x18004d878`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180020774`
- `ntdll!RtlLengthSid` at `0x180020794`
- `ntdll!RtlLengthSid` at `0x180020811`
- `ntdll!RtlLengthSid` at `0x180020835`
- `ntdll!RtlLengthSid` at `0x180020774`
- `ntdll!RtlLengthSid` at `0x180020794`
- `ntdll!RtlLengthSid` at `0x180020811`
- `ntdll!RtlLengthSid` at `0x180020835`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800209af`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800209af`
- `ntdll!RtlReleaseResource` at `0x180020a6b`
- `ntdll!RtlReleaseResource` at `0x180020a6b`
- `SAMSRV!SamIConnect` at `0x1800208a4`
- `SAMSRV!SamIConnect` at `0x1800208a4`
- `SAMSRV!SamrCloseHandle` at `0x180020aec`
- `SAMSRV!SamrCloseHandle` at `0x180020b24`
- `SAMSRV!SamrCloseHandle` at `0x180020b84`
- `SAMSRV!SamrCloseHandle` at `0x180020aec`
- `SAMSRV!SamrCloseHandle` at `0x180020b24`
- `SAMSRV!SamrCloseHandle` at `0x180020b84`
- `SAMSRV!SamrOpenDomain` at `0x180020902`
- `SAMSRV!SamrOpenDomain` at `0x180020953`
- `SAMSRV!SamrOpenDomain` at `0x180020902`
- `SAMSRV!SamrOpenDomain` at `0x180020953`
- `LSASRV!LsarQueryInformationPolicy` at `0x180020642`
- `LSASRV!LsarQueryInformationPolicy` at `0x18002067a`
- `LSASRV!LsarQueryInformationPolicy` at `0x1800206cd`
- `LSASRV!LsarQueryInformationPolicy` at `0x180020642`
- `LSASRV!LsarQueryInformationPolicy` at `0x18002067a`
- `LSASRV!LsarQueryInformationPolicy` at `0x1800206cd`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180020b4c`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180020b60`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180020b74`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180020b4c`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180020b60`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180020b74`

## string_xrefs

- `0x1800205d1`: `\SAM_SERVICE_STARTED`

## pseudocode

```c
__int64 NlSamInitialize()
{
  void *v0; // r15
  void *v1; // r14
  WCHAR *v2; // rsi
  WCHAR *v3; // r13
  __int64 v4; // rdi
  int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  size_t v8; // r12
  WCHAR *v9; // rax
  WCHAR *v10; // r12
  __int64 (__fastcall *v11)(_QWORD); // rbx
  ULONG v12; // eax
  ULONG v13; // eax
  unsigned int v14; // ebx
  WCHAR *v15; // rax
  __int64 v16; // r9
  __int64 (__fastcall *v17)(_QWORD); // rbx
  ULONG v18; // eax
  ULONG v19; // eax
  unsigned int v20; // ebx
  WCHAR *v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v25; // [rsp+20h] [rbp-60h] BYREF
  __int64 v26; // [rsp+28h] [rbp-58h] BYREF
  __int64 v27; // [rsp+30h] [rbp-50h] BYREF
  const void **v28; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING v29; // [rsp+40h] [rbp-40h]
  UNICODE_STRING v30; // [rsp+50h] [rbp-30h]
  __int128 v31; // [rsp+60h] [rbp-20h] BYREF
  __int128 v32; // [rsp+70h] [rbp-10h]
  WCHAR *v33; // [rsp+C8h] [rbp+48h]
  __int64 v34; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v35; // [rsp+D8h] [rbp+58h] BYREF

  *(_QWORD *)&v30.Length = 0;
  v29 = (struct _UNICODE_STRING)0LL;
  v32 = 0;
  v0 = 0;
  v25 = 0;
  v1 = 0;
  v26 = 0;
  v31 = 0u;
  v2 = 0;
  v28 = 0;
  v3 = 0;
  v34 = 0;
  v4 = 0;
  v35 = 0;
  v27 = 0;
  v33 = 0;
  v5 = NlWaitForEvent(L"\\SAM_SERVICE_STARTED", 0x4B0u);
  if ( v5 < 0 )
    goto LABEL_60;
  v5 = LsarQueryInformationPolicy(NtLmGlobalPolicyHandle, 5, &v34);
  if ( v5 < 0 )
    goto LABEL_60;
  if ( !*(_QWORD *)(v34 + 16) || !*(_WORD *)v34 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids);
    v10 = 0;
    v5 = -1073741601;
    goto LABEL_54;
  }
  v5 = LsarQueryInformationPolicy(NtLmGlobalPolicyHandle, 3, &v28);
  if ( v5 < 0 )
    goto LABEL_60;
  if ( !*(_WORD *)v28 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    v7 = 30;
LABEL_17:
    WPP_SF_(v6[2], v7, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids);
LABEL_18:
    v5 = -1073741601;
    goto LABEL_60;
  }
  if ( !NlpWorkstation )
  {
    v5 = LsarQueryInformationPolicy(NtLmGlobalPolicyHandle, 14, &v35);
    if ( v5 < 0 )
      goto LABEL_60;
    if ( !*(_QWORD *)(v35 + 16) || !*(_WORD *)v35 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_18;
      v7 = 31;
      goto LABEL_17;
    }
  }
  v8 = *(unsigned __int16 *)v28;
  v9 = (WCHAR *)((__int64 (__fastcall *)(size_t))qword_180088390)(v8);
  v2 = v9;
  if ( v9 )
  {
    memcpy_0(v9, v28[1], v8);
    v11 = (__int64 (__fastcall *)(_QWORD))qword_180088390;
    v12 = RtlLengthSid(*(PSID *)(v34 + 16));
    v0 = (void *)v11(v12);
    if ( v0 )
    {
      v13 = RtlLengthSid(*(PSID *)(v34 + 16));
      memcpy_0(v0, *(const void **)(v34 + 16), v13);
      v30.Length = *(_WORD *)v34;
      v14 = (unsigned __int16)(v30.Length + 2);
      v30.MaximumLength = v30.Length + 2;
      v15 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))qword_180088390)((unsigned __int16)(v30.Length + 2));
      v33 = v15;
      v30.Buffer = v15;
      if ( v15 )
      {
        memcpy_0(v15, *(const void **)(v34 + 8), v14);
        if ( NlpWorkstation )
        {
LABEL_28:
          LOBYTE(v16) = 1;
          v5 = SamIConnect(0, &v27, 1, v16);
          if ( v5 < 0 )
          {
            v27 = 0;
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_21;
            v23 = 32;
            goto LABEL_32;
          }
          v5 = SamrOpenDomain(v27, 985087, v0, &v25);
          if ( v5 < 0 )
          {
            v25 = 0;
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_21;
            v23 = 33;
            goto LABEL_32;
          }
          if ( !NlpWorkstation )
          {
            v5 = SamrOpenDomain(v27, 985087, v1, &v26);
            if ( v5 < 0 )
            {
              v26 = 0;
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_21;
              }
              v23 = 34;
LABEL_32:
              WPP_SF_d(v22[2], v23, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids, (unsigned int)v5);
              goto LABEL_21;
            }
          }
          if ( !NlpSamInitialized )
          {
            SsprQueryTreeName(&v31);
            v4 = *((_QWORD *)&v31 + 1);
          }
          v5 = 0;
          RtlAcquireResourceExclusive(&NtLmGlobalCritSect, 1u);
          if ( NlpSamInitialized )
          {
            v10 = v33;
          }
          else
          {
            *(_DWORD *)(&NlpPrimaryDomainName.MaximumLength + 1) = DWORD1(v32);
            NlpSamDomainHandle = v25;
            NlpPrimaryDomainName.Length = v8;
            NlpPrimaryDomainName.MaximumLength = v8;
            NlpPrimaryDomainName.Buffer = v2;
            NlpSamDomainId = v0;
            NlpSamLocalDomainId = v1;
            NlpSamLocalDomainHandle = v26;
            NlpSamDomainName = v30;
            NlpSamLocalDomainName = v29;
            if ( *((_QWORD *)&NtLmGlobalUnicodeDnsTreeName + 1) )
              NtLmFree(*((_QWORD *)&NtLmGlobalUnicodeDnsTreeName + 1));
            NtLmGlobalUnicodeDnsTreeName = v31;
            SsprUpdateTargetInfo();
            v2 = 0;
            NlpSamInitialized = 1;
            v0 = 0;
            v25 = 0;
            v10 = 0;
            v26 = 0;
            v1 = 0;
            v3 = 0;
            v4 = 0;
          }
          RtlReleaseResource(&NtLmGlobalCritSect);
LABEL_54:
          if ( v4 )
            NtLmFree(v4);
          goto LABEL_56;
        }
        v17 = (__int64 (__fastcall *)(_QWORD))qword_180088390;
        v18 = RtlLengthSid(*(PSID *)(v35 + 16));
        v1 = (void *)v17(v18);
        if ( v1 )
        {
          v19 = RtlLengthSid(*(PSID *)(v35 + 16));
          memcpy_0(v1, *(const void **)(v35 + 16), v19);
          v29.Length = *(_WORD *)v35;
          v20 = (unsigned __int16)(v29.Length + 2);
          v29.MaximumLength = v29.Length + 2;
          v21 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))qword_180088390)((unsigned __int16)(v29.Length + 2));
          v29.Buffer = v21;
          v3 = v21;
          if ( v21 )
          {
            memcpy_0(v21, *(const void **)(v35 + 8), v20);
            goto LABEL_28;
          }
        }
      }
    }
  }
  v5 = -1073741801;
LABEL_21:
  v10 = v33;
LABEL_56:
  if ( v2 )
    ((void (__fastcall *)(WCHAR *))qword_180088398)(v2);
  if ( v10 )
    ((void (__fastcall *)(WCHAR *))qword_180088398)(v10);
LABEL_60:
  if ( v25 )
    SamrCloseHandle(&v25);
  if ( v0 )
    ((void (__fastcall *)(void *))qword_180088398)(v0);
  if ( v3 )
    ((void (__fastcall *)(WCHAR *))qword_180088398)(v3);
  if ( v26 )
    SamrCloseHandle(&v26);
  if ( v1 )
    ((void (__fastcall *)(void *))qword_180088398)(v1);
  if ( v34 )
    LsaIFree_LSAPR_POLICY_INFORMATION(5);
  if ( v35 )
    LsaIFree_LSAPR_POLICY_INFORMATION(14);
  if ( v28 )
    LsaIFree_LSAPR_POLICY_INFORMATION(3);
  if ( v27 )
    SamrCloseHandle(&v27);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800205b4  mov     [rsp-38h+arg_0], rbx
0x1800205b9  push    rbp
0x1800205ba  push    rsi
0x1800205bb  push    rdi
0x1800205bc  push    r12
0x1800205be  push    r13
0x1800205c0  push    r14
0x1800205c2  push    r15
0x1800205c4  mov     rbp, rsp
0x1800205c7  sub     rsp, 80h
0x1800205ce  xor     r12d, r12d
0x1800205d1  lea     rcx, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x1800205d8  xorps   xmm0, xmm0
0x1800205db  mov     qword ptr [rbp+var_30], r12
0x1800205df  movups  [rbp+var_40], xmm0
0x1800205e3  mov     edx, 4B0h; unsigned int
0x1800205e8  mov     qword ptr [rbp+var_40+8], r12
0x1800205ec  movups  [rbp+var_10], xmm0
0x1800205f0  mov     r15d, r12d
0x1800205f3  mov     [rbp+var_60], r12
0x1800205f7  mov     r14d, r12d
0x1800205fa  mov     [rbp+var_58], r12
0x1800205fe  mov     qword ptr [rbp+var_20], r12
0x180020602  mov     esi, r12d
0x180020605  mov     [rbp+var_48], r12
0x180020609  mov     r13d, r12d
0x18002060c  mov     [rbp+arg_10], r12
0x180020610  mov     edi, r12d
0x180020613  mov     [rbp+arg_18], r12
0x180020617  mov     [rbp+var_50], r12
0x18002061b  mov     [rbp+arg_8], r12
0x18002061f  mov     qword ptr [rbp+var_20+8], r12
0x180020623  call    ?NlWaitForEvent@@YAJPEAGK@Z; NlWaitForEvent(ushort *,ulong)
0x180020628  mov     ebx, eax
0x18002062a  test    eax, eax
0x18002062c  js      loc_180020AE2
0x180020632  mov     rcx, cs:NtLmGlobalPolicyHandle
0x180020639  lea     r8, [rbp+arg_10]
0x18002063d  lea     edx, [r12+5]
0x180020642  call    cs:__imp_LsarQueryInformationPolicy
0x180020648  mov     ebx, eax
0x18002064a  test    eax, eax
0x18002064c  js      loc_180020AE2
0x180020652  mov     rdx, [rbp+arg_10]
0x180020656  cmp     [rdx+10h], r12
0x18002065a  jz      loc_180020A73
0x180020660  cmp     [rdx], r12w
0x180020664  jz      loc_180020A73
0x18002066a  mov     rcx, cs:NtLmGlobalPolicyHandle
0x180020671  lea     r8, [rbp+var_48]
0x180020675  lea     edx, [r12+3]
0x18002067a  call    cs:__imp_LsarQueryInformationPolicy
0x180020680  mov     ebx, eax
0x180020682  test    eax, eax
0x180020684  js      loc_180020AE2
0x18002068a  mov     rax, [rbp+var_48]
0x18002068e  cmp     [rax], r12w
0x180020692  jnz     short loc_1800206B4
0x180020694  mov     rcx, cs:WPP_GLOBAL_Control
0x18002069b  lea     rax, WPP_GLOBAL_Control
0x1800206a2  cmp     rcx, rax
0x1800206a5  jz      short loc_18002071B
0x1800206a7  test    byte ptr [rcx+1Ch], 1
0x1800206ab  jz      short loc_18002071B
0x1800206ad  lea     edx, [r12+1Eh]
0x1800206b2  jmp     short loc_18002070B
0x1800206b4  cmp     cs:NlpWorkstation, r12b
0x1800206bb  jnz     short loc_180020725
0x1800206bd  mov     rcx, cs:NtLmGlobalPolicyHandle
0x1800206c4  lea     r8, [rbp+arg_18]
0x1800206c8  mov     edx, 0Eh
0x1800206cd  call    cs:__imp_LsarQueryInformationPolicy
0x1800206d3  mov     ebx, eax
0x1800206d5  test    eax, eax
0x1800206d7  js      loc_180020AE2
0x1800206dd  mov     rdx, [rbp+arg_18]
0x1800206e1  cmp     [rdx+10h], r12
0x1800206e5  jz      short loc_1800206ED
0x1800206e7  cmp     [rdx], r12w
0x1800206eb  jnz     short loc_180020725
0x1800206ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206f4  lea     rax, WPP_GLOBAL_Control
0x1800206fb  cmp     rcx, rax
0x1800206fe  jz      short loc_18002071B
0x180020700  test    byte ptr [rcx+1Ch], 8
0x180020704  jz      short loc_18002071B
0x180020706  mov     edx, 1Fh
0x18002070b  mov     rcx, [rcx+10h]
0x18002070f  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x180020716  call    WPP_SF_
0x18002071b  mov     ebx, 0C00000DFh
0x180020720  jmp     loc_180020AE2
0x180020725  mov     rax, [rbp+var_48]
0x180020729  movzx   r12d, word ptr [rax]
0x18002072d  mov     rax, cs:qword_180088390
0x180020734  mov     ecx, r12d
0x180020737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002073c  mov     rsi, rax
0x18002073f  test    rax, rax
0x180020742  jnz     short loc_180020752
0x180020744  mov     ebx, 0C0000017h
0x180020749  mov     r12, [rbp+arg_8]
0x18002074d  jmp     loc_180020AB7
0x180020752  mov     rdx, [rbp+var_48]
0x180020756  mov     r8, r12; Size
0x180020759  mov     rcx, rsi; void *
0x18002075c  mov     rdx, [rdx+8]; Src
0x180020760  call    memcpy_0
0x180020765  mov     rcx, [rbp+arg_10]
0x180020769  mov     rbx, cs:qword_180088390
0x180020770  mov     rcx, [rcx+10h]; Sid
0x180020774  call    cs:__imp_RtlLengthSid
0x18002077a  mov     ecx, eax
0x18002077c  mov     rax, rbx
0x18002077f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020784  mov     r15, rax
0x180020787  test    rax, rax
0x18002078a  jz      short loc_180020744
0x18002078c  mov     rcx, [rbp+arg_10]
0x180020790  mov     rcx, [rcx+10h]; Sid
0x180020794  call    cs:__imp_RtlLengthSid
0x18002079a  mov     rdx, [rbp+arg_10]
0x18002079e  mov     rcx, r15; void *
0x1800207a1  mov     r8d, eax; Size
0x1800207a4  mov     rdx, [rdx+10h]; Src
0x1800207a8  call    memcpy_0
0x1800207ad  mov     rax, [rbp+arg_10]
0x1800207b1  movzx   ecx, word ptr [rax]
0x1800207b4  mov     rax, cs:qword_180088390
0x1800207bb  mov     word ptr [rbp+var_30], cx
0x1800207bf  add     cx, 2
0x1800207c3  movzx   ebx, cx
0x1800207c6  mov     ecx, ebx
0x1800207c8  mov     word ptr [rbp+var_30+2], bx
0x1800207cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207d1  mov     [rbp+arg_8], rax
0x1800207d5  mov     qword ptr [rbp+var_30+8], rax
0x1800207d9  test    rax, rax
0x1800207dc  jz      loc_180020744
0x1800207e2  mov     rdx, [rbp+arg_10]
0x1800207e6  mov     r8d, ebx; Size
0x1800207e9  mov     rcx, rax; void *
0x1800207ec  mov     rdx, [rdx+8]; Src
0x1800207f0  call    memcpy_0
0x1800207f5  cmp     cs:NlpWorkstation, dil
0x1800207fc  jnz     loc_180020895
0x180020802  mov     rcx, [rbp+arg_18]
0x180020806  mov     rbx, cs:qword_180088390
0x18002080d  mov     rcx, [rcx+10h]; Sid
0x180020811  call    cs:__imp_RtlLengthSid
0x180020817  mov     ecx, eax
0x180020819  mov     rax, rbx
0x18002081c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020821  mov     r14, rax
0x180020824  test    rax, rax
0x180020827  jz      loc_180020744
0x18002082d  mov     rcx, [rbp+arg_18]
0x180020831  mov     rcx, [rcx+10h]; Sid
0x180020835  call    cs:__imp_RtlLengthSid
0x18002083b  mov     rdx, [rbp+arg_18]
0x18002083f  mov     rcx, r14; void *
0x180020842  mov     r8d, eax; Size
0x180020845  mov     rdx, [rdx+10h]; Src
0x180020849  call    memcpy_0
0x18002084e  mov     rax, [rbp+arg_18]
0x180020852  movzx   ecx, word ptr [rax]
0x180020855  mov     rax, cs:qword_180088390
0x18002085c  mov     word ptr [rbp+var_40], cx
0x180020860  add     cx, 2
0x180020864  movzx   ebx, cx
0x180020867  mov     ecx, ebx
0x180020869  mov     word ptr [rbp+var_40+2], bx
0x18002086d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020872  mov     qword ptr [rbp+var_40+8], rax
0x180020876  mov     r13, rax
0x180020879  test    rax, rax
0x18002087c  jz      loc_180020744
0x180020882  mov     rdx, [rbp+arg_18]
0x180020886  mov     r8d, ebx; Size
0x180020889  mov     rcx, rax; void *
0x18002088c  mov     rdx, [rdx+8]; Src
0x180020890  call    memcpy_0
0x180020895  mov     r9b, 1
0x180020898  lea     rdx, [rbp+var_50]
0x18002089c  mov     r8d, 1
0x1800208a2  xor     ecx, ecx
0x1800208a4  call    cs:__imp_SamIConnect
0x1800208aa  mov     ebx, eax
0x1800208ac  test    eax, eax
0x1800208ae  jns     short loc_1800208F2
0x1800208b0  mov     [rbp+var_50], rdi
0x1800208b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208bb  lea     rax, WPP_GLOBAL_Control
0x1800208c2  cmp     rcx, rax
0x1800208c5  jz      loc_180020749
0x1800208cb  test    byte ptr [rcx+1Ch], 1
0x1800208cf  jz      loc_180020749
0x1800208d5  mov     edx, 20h ; ' '
0x1800208da  mov     rcx, [rcx+10h]
0x1800208de  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x1800208e5  mov     r9d, ebx
0x1800208e8  call    WPP_SF_d
0x1800208ed  jmp     loc_180020749
0x1800208f2  mov     rcx, [rbp+var_50]
0x1800208f6  lea     r9, [rbp+var_60]
0x1800208fa  mov     r8, r15
0x1800208fd  mov     edx, 0F07FFh
0x180020902  call    cs:__imp_SamrOpenDomain
0x180020908  mov     ebx, eax
0x18002090a  test    eax, eax
0x18002090c  jns     short loc_18002093A
0x18002090e  mov     [rbp+var_60], rdi
0x180020912  mov     rcx, cs:WPP_GLOBAL_Control
0x180020919  lea     rax, WPP_GLOBAL_Control
0x180020920  cmp     rcx, rax
0x180020923  jz      loc_180020749
0x180020929  test    byte ptr [rcx+1Ch], 1
0x18002092d  jz      loc_180020749
0x180020933  mov     edx, 21h ; '!'
0x180020938  jmp     short loc_1800208DA
0x18002093a  cmp     cs:NlpWorkstation, dil
0x180020941  jnz     short loc_18002098E
0x180020943  mov     rcx, [rbp+var_50]
0x180020947  lea     r9, [rbp+var_58]
0x18002094b  mov     r8, r14
0x18002094e  mov     edx, 0F07FFh
0x180020953  call    cs:__imp_SamrOpenDomain
0x180020959  mov     ebx, eax
0x18002095b  test    eax, eax
0x18002095d  jns     short loc_18002098E
0x18002095f  mov     [rbp+var_58], rdi
0x180020963  mov     rcx, cs:WPP_GLOBAL_Control
0x18002096a  lea     rax, WPP_GLOBAL_Control
0x180020971  cmp     rcx, rax
0x180020974  jz      loc_180020749
0x18002097a  test    byte ptr [rcx+1Ch], 1
0x18002097e  jz      loc_180020749
0x180020984  mov     edx, 22h ; '"'
0x180020989  jmp     loc_1800208DA
0x18002098e  cmp     cs:NlpSamInitialized, dil
0x180020995  jnz     short loc_1800209A4
0x180020997  lea     rcx, [rbp+var_20]
0x18002099b  call    SsprQueryTreeName
0x1800209a0  mov     rdi, qword ptr [rbp+var_20+8]
0x1800209a4  mov     dl, 1; Wait
0x1800209a6  lea     rcx, NtLmGlobalCritSect; Resource
0x1800209ad  xor     ebx, ebx
0x1800209af  call    cs:__imp_RtlAcquireResourceExclusive
0x1800209b5  cmp     cs:NlpSamInitialized, bl
0x1800209bb  jnz     loc_180020A60
0x1800209c1  movups  xmm0, [rbp+var_30]
0x1800209c5  mov     eax, dword ptr [rbp+var_10+4]
0x1800209c8  mov     rcx, qword ptr cs:NtLmGlobalUnicodeDnsTreeName+8
0x1800209cf  mov     dword ptr cs:NlpPrimaryDomainName+4, eax
0x1800209d5  mov     rax, [rbp+var_60]
0x1800209d9  mov     cs:NlpSamDomainHandle, rax
0x1800209e0  mov     rax, [rbp+var_58]
0x1800209e4  mov     cs:NlpPrimaryDomainName.Length, r12w
0x1800209ec  mov     cs:NlpPrimaryDomainName.MaximumLength, r12w
0x1800209f4  mov     cs:NlpPrimaryDomainName.Buffer, rsi
0x1800209fb  mov     cs:NlpSamDomainId, r15
0x180020a02  mov     cs:NlpSamLocalDomainId, r14
0x180020a09  mov     cs:NlpSamLocalDomainHandle, rax
0x180020a10  movdqu  xmmword ptr cs:NlpSamDomainName.Length, xmm0
0x180020a18  movups  xmm0, [rbp+var_40]
0x180020a1c  movdqu  xmmword ptr cs:NlpSamLocalDomainName.Length, xmm0
0x180020a24  test    rcx, rcx
0x180020a27  jz      short loc_180020A2E
0x180020a29  call    NtLmFree
0x180020a2e  movups  xmm0, [rbp+var_20]
0x180020a32  movdqu  cs:NtLmGlobalUnicodeDnsTreeName, xmm0
0x180020a3a  call    SsprUpdateTargetInfo
0x180020a3f  xor     esi, esi
0x180020a41  mov     cs:NlpSamInitialized, 1
0x180020a48  xor     r15d, r15d
0x180020a4b  mov     [rbp+var_60], rbx
0x180020a4f  xor     r12d, r12d
0x180020a52  mov     [rbp+var_58], rbx
0x180020a56  xor     r14d, r14d
0x180020a59  xor     r13d, r13d
0x180020a5c  xor     edi, edi
0x180020a5e  jmp     short loc_180020A64
0x180020a60  mov     r12, [rbp+arg_8]
0x180020a64  lea     rcx, NtLmGlobalCritSect; Resource
0x180020a6b  call    cs:__imp_RtlReleaseResource
0x180020a71  jmp     short loc_180020AAA
0x180020a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a7a  lea     rax, WPP_GLOBAL_Control
0x180020a81  cmp     rcx, rax
0x180020a84  jz      short loc_180020AA1
0x180020a86  test    byte ptr [rcx+1Ch], 8
0x180020a8a  jz      short loc_180020AA1
0x180020a8c  mov     rcx, [rcx+10h]
0x180020a90  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x180020a97  mov     edx, 1Dh
0x180020a9c  call    WPP_SF_
0x180020aa1  mov     r12, [rbp+arg_8]
0x180020aa5  mov     ebx, 0C00000DFh
0x180020aaa  test    rdi, rdi
0x180020aad  jz      short loc_180020AB7
  ... truncated ...
```
