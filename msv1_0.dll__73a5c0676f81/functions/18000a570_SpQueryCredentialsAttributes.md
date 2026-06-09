# SpQueryCredentialsAttributes

- ea: `0x18000a570`
- end: `0x18000ad22`
- name: `SpQueryCredentialsAttributes`
- size: `1970`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a570`
- `0x18000ad30`
- `0x18000c5d0`
- `0x18002ee3c`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x18003509c`
- `0x18004c980`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a9f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a9f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a95e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a95e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a953`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a953`
- `ntdll!RtlReleaseResource` at `0x18000a67c`
- `ntdll!RtlReleaseResource` at `0x18000a903`
- `ntdll!RtlReleaseResource` at `0x18000a9a5`
- `ntdll!RtlReleaseResource` at `0x18000acb2`
- `ntdll!RtlReleaseResource` at `0x18000ad0c`
- `ntdll!RtlReleaseResource` at `0x18000a67c`
- `ntdll!RtlReleaseResource` at `0x18000a903`
- `ntdll!RtlReleaseResource` at `0x18000a9a5`
- `ntdll!RtlReleaseResource` at `0x18000acb2`
- `ntdll!RtlReleaseResource` at `0x18000ad0c`
- `ntdll!RtlAcquireResourceShared` at `0x18000a64c`
- `ntdll!RtlAcquireResourceShared` at `0x18000a97c`
- `ntdll!RtlAcquireResourceShared` at `0x18000a64c`
- `ntdll!RtlAcquireResourceShared` at `0x18000a97c`
- `LSASRV!LsaIFree_LSAPR_REFERENCED_DOMAIN_LIST` at `0x18000ad17`
- `LSASRV!LsaIFree_LSAPR_REFERENCED_DOMAIN_LIST` at `0x18000ad17`
- `LSASRV!LsarLookupSids` at `0x18000aa5f`
- `LSASRV!LsarLookupSids` at `0x18000aa5f`
- `LSASRV!LsaIFree_LSAPR_TRANSLATED_NAMES` at `0x18000a8e5`
- `LSASRV!LsaIFree_LSAPR_TRANSLATED_NAMES` at `0x18000a8e5`

## pseudocode

```c
__int64 __fastcall SpQueryCredentialsAttributes(unsigned __int16 *a1, unsigned int a2, __int64 a3)
{
  _WORD *v5; // r14
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  const void *v9; // r12
  void *v10; // rdi
  unsigned int v11; // r15d
  unsigned int v12; // esi
  __int64 v13; // rsi
  __int64 v14; // r15
  unsigned int v15; // r13d
  _WORD *v16; // rax
  char *v17; // rdi
  char v18; // si
  int v19; // edi
  PLSA_COPY_TO_CLIENT_BUFFER CopyToClientBuffer; // rax
  __int64 ActiveLogon; // rax
  int v23; // eax
  BOOL v24; // edi
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // rax
  char v29; // [rsp+38h] [rbp-D0h]
  char v30; // [rsp+39h] [rbp-CFh]
  __int64 v31; // [rsp+40h] [rbp-C8h] BYREF
  DWORD ReturnLength[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-B0h] BYREF
  void *Src; // [rsp+60h] [rbp-A8h]
  __int64 v36; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v37[3]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v38; // [rsp+88h] [rbp-80h] BYREF
  __int64 v39; // [rsp+98h] [rbp-70h]
  __int64 v40; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v41[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v42; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v43; // [rsp+C8h] [rbp-40h]
  __int64 TokenInformation[32]; // [rsp+D8h] [rbp-30h] BYREF

  v43 = 0;
  v37[0] = a3;
  v31 = 0;
  v5 = 0;
  v33 = 0;
  v36 = 0;
  *(_OWORD *)&v37[1] = 0;
  v42 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v31 = 0;
  if ( a2 != 1 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    {
      WPP_SF_d(v6[2], 48, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids, a2);
      v6 = WPP_GLOBAL_Control;
    }
    v19 = -1073741811;
    goto LABEL_67;
  }
  v39 = 0;
  v38 = 0;
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v38) )
  {
    v6 = WPP_GLOBAL_Control;
    v19 = -1073741595;
LABEL_47:
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 )
    {
LABEL_29:
      if ( v19 >= 0 )
        goto LABEL_30;
      goto LABEL_67;
    }
    WPP_SF_d(v6[2], 49, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids, (unsigned int)v19);
LABEL_28:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  if ( (BYTE8(v38) & 0x20) != 0 )
  {
    DWORD2(v38) |= 0x200u;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_LqL(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, (unsigned int)v38, a1, HIDWORD(v38));
  }
  RtlAcquireResourceShared(&SspCredentialCritSect, 1u);
  if ( *((_DWORD *)a1 + 9) != 1097101891 || (WORD4(v38) & 0x200) == 0 && *((_DWORD *)a1 + 8) != (_DWORD)v38 )
  {
    RtlReleaseResource(&SspCredentialCritSect);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids, a1);
      v6 = WPP_GLOBAL_Control;
    }
    v19 = -1073741816;
    goto LABEL_47;
  }
  v30 = 0;
  _InterlockedIncrement((volatile signed __int32 *)a1 + 4);
  RtlReleaseResource(&SspCredentialCritSect);
  if ( ((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v42) )
  {
    v9 = (const void *)*((_QWORD *)a1 + 9);
    v33 = *((_QWORD *)a1 + 3);
    if ( v9 || *((_QWORD *)a1 + 7) )
    {
      v10 = (void *)*((_QWORD *)a1 + 7);
      v11 = a1[24];
      v29 = 0;
      v12 = a1[32];
      goto LABEL_10;
    }
    RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
    ActiveLogon = NlpFindActiveLogon(&v33);
    if ( ActiveLogon )
    {
      v9 = *(const void **)(ActiveLogon + 80);
      v12 = *(unsigned __int16 *)(ActiveLogon + 72);
      v10 = *(void **)(ActiveLogon + 96);
      v11 = *(unsigned __int16 *)(ActiveLogon + 88);
      v29 = 1;
      goto LABEL_10;
    }
    ReturnLength[0] = 0;
    TokenHandle = 0;
    RtlReleaseResource(&NlpActiveLogonLock);
    v23 = ((__int64 (__fastcall *)(__int64 *, HANDLE *))LsaFunctions->OpenTokenByLogonId)(&v33, &TokenHandle);
    v19 = v23;
    if ( v23 >= 0 )
    {
      ReturnLength[0] = 256;
      v24 = GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, ReturnLength);
      CloseHandle(TokenHandle);
      if ( !v24
        || (v41[1] = &v40,
            v40 = TokenInformation[0],
            v41[0] = 1,
            ReturnLength[1] = 0,
            *(_OWORD *)&v37[1] = 0,
            v30 = 1,
            (int)LsarLookupSids(NtLmGlobalPolicyHandle, v41, &v36, &v37[1], 1, &ReturnLength[1]) < 0)
        || !ReturnLength[1]
        || !LODWORD(v37[1])
        || !v36
        || !*(_DWORD *)v36 )
      {
        v19 = -1073741729;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids);
        goto LABEL_27;
      }
      v29 = 0;
      v9 = *(const void **)(v37[2] + 16LL);
      v12 = *(unsigned __int16 *)(v37[2] + 8LL);
      v28 = *(_QWORD *)(v36 + 8);
      v10 = *(void **)(v28 + 24LL * *(int *)(v37[2] + 24LL) + 8);
      v11 = *(unsigned __int16 *)(v28 + 24LL * *(int *)(v37[2] + 24LL));
LABEL_10:
      v13 = v12 >> 1;
      v14 = v11 >> 1;
      Src = v10;
      if ( (unsigned int)v13 > 0x100 || (unsigned int)v14 > 0xFF )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            WPP_9f54ae5c059a34c647826de37781d01b_Traceguids,
            (unsigned int)v13,
            v14);
        v19 = -1073741726;
      }
      else
      {
        v15 = 2 * (v14 + v13) + 4;
        if ( NtLmState == 1 )
          v16 = (_WORD *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocatePrivateHeap)(v15);
        else
          v16 = LocalAlloc(0x40u, v15);
        v5 = v16;
        if ( v16 )
        {
          if ( v10 )
          {
            memcpy_0(v16, Src, 2 * v14);
            v5[v14] = 92;
            v17 = (char *)&v5[(unsigned int)(v14 + 1)];
          }
          else
          {
            v17 = (char *)v16;
          }
          if ( v9 )
            memcpy_0(v17, v9, 2LL * (unsigned int)v13);
          *(_WORD *)&v17[2 * v13] = 0;
          v18 = v29;
          if ( v29 )
          {
            RtlReleaseResource(&NlpActiveLogonLock);
            v18 = 0;
          }
          v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64 *))LsaFunctions->AllocateClientBuffer)(0, v15, &v31);
          if ( v19 < 0 )
            goto LABEL_27;
          v19 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _WORD *))LsaFunctions->CopyToClientBuffer)(
                  0,
                  v15,
                  v31,
                  v5);
          if ( v19 >= 0 )
          {
            CopyToClientBuffer = LsaFunctions->CopyToClientBuffer;
            if ( (BYTE8(v42) & 0x40) != 0 )
              v19 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, __int64 *))CopyToClientBuffer)(0, 4, v37[0], &v31);
            else
              v19 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, __int64 *))CopyToClientBuffer)(0, 8, v37[0], &v31);
          }
          goto LABEL_25;
        }
        v19 = -1073741801;
      }
      v18 = v29;
LABEL_25:
      if ( v18 )
        RtlReleaseResource(&NlpActiveLogonLock);
      goto LABEL_27;
    }
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v26 = 51;
      v27 = (unsigned int)v23;
      goto LABEL_79;
    }
LABEL_27:
    SspCredentialDereferenceCredential(a1);
    if ( v30 )
    {
      if ( v36 )
        LsaIFree_LSAPR_REFERENCED_DOMAIN_LIST();
      LsaIFree_LSAPR_TRANSLATED_NAMES(&v37[1]);
    }
    goto LABEL_28;
  }
  v19 = -1073741595;
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_27;
  v26 = 50;
  v27 = 3221225701LL;
LABEL_79:
  WPP_SF_d(v25[2], v26, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids, v27);
  SspCredentialDereferenceCredential(a1);
  v6 = WPP_GLOBAL_Control;
LABEL_67:
  if ( v31 )
  {
    ((void (__fastcall *)(_QWORD))LsaFunctions->FreeClientBuffer)(0);
    v6 = WPP_GLOBAL_Control;
  }
LABEL_30:
  if ( v5 )
  {
    if ( NtLmState == 1 )
      ((void (__fastcall *)(_WORD *))LsaFunctions->FreePrivateHeap)(v5);
    else
      LocalFree(v5);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x100) != 0 )
    WPP_SF_(v6[2], 54, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18000a570  mov     r11, rsp
0x18000a573  push    rbp
0x18000a574  push    rdi
0x18000a575  lea     rbp, [r11-118h]
0x18000a57c  sub     rsp, 208h
0x18000a583  mov     rax, cs:__security_cookie
0x18000a58a  xor     rax, rsp
0x18000a58d  mov     [rbp+110h+var_40], rax
0x18000a594  mov     [r11+20h], rbx
0x18000a598  xorps   xmm0, xmm0
0x18000a59b  mov     [r11-18h], rsi
0x18000a59f  xorps   xmm1, xmm1
0x18000a5a2  xor     esi, esi
0x18000a5a4  mov     [r11-28h], r13
0x18000a5a8  xor     eax, eax
0x18000a5aa  mov     [r11-30h], r14
0x18000a5ae  mov     [rbp+110h+var_150], rax
0x18000a5b2  mov     edi, edx
0x18000a5b4  mov     qword ptr [rsp+210h+var_1A8], r8
0x18000a5b9  mov     rbx, rcx
0x18000a5bc  mov     qword ptr [rsp+210h+var_1D8], rsi
0x18000a5c1  mov     r14d, esi
0x18000a5c4  mov     [rsp+210h+var_1C8], rsi
0x18000a5c9  mov     [rsp+210h+var_1B0], rsi
0x18000a5ce  movups  xmmword ptr [rsp+210h+var_1A8+8], xmm0
0x18000a5d3  movups  [rbp+110h+var_160], xmm1
0x18000a5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5de  lea     r13, WPP_GLOBAL_Control
0x18000a5e5  cmp     rcx, r13
0x18000a5e8  jnz     loc_18000A884
0x18000a5ee  mov     [rsp+210h+var_18], r12
0x18000a5f6  mov     [rsp+210h+var_30], r15
0x18000a5fe  mov     qword ptr [rsp+210h+var_1D8], rsi
0x18000a603  cmp     edi, 1
0x18000a606  jnz     loc_18000AAE5
0x18000a60c  xor     eax, eax
0x18000a60e  lea     rcx, [rbp+110h+var_190]
0x18000a612  mov     [rbp+110h+var_180], rax
0x18000a616  xorps   xmm0, xmm0
0x18000a619  mov     rax, cs:LsaFunctions
0x18000a620  movups  [rbp+110h+var_190], xmm0
0x18000a624  mov     rax, [rax+0C0h]
0x18000a62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a630  test    al, al
0x18000a632  jz      loc_18000AAA6
0x18000a638  mov     eax, dword ptr [rbp+110h+var_190+8]
0x18000a63b  test    al, 20h
0x18000a63d  jnz     loc_18000AB40
0x18000a643  mov     dl, 1; Wait
0x18000a645  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x18000a64c  call    cs:__imp_RtlAcquireResourceShared
0x18000a652  cmp     dword ptr [rbx+24h], 41647243h
0x18000a659  jnz     loc_18000A8FC
0x18000a65f  test    dword ptr [rbp+110h+var_190+8], 200h
0x18000a666  jz      loc_18000A8F0
0x18000a66c  mov     byte ptr [rsp+210h+var_1E0+1], sil
0x18000a671  lock inc dword ptr [rbx+10h]
0x18000a675  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x18000a67c  call    cs:__imp_RtlReleaseResource
0x18000a682  mov     rax, cs:LsaFunctions
0x18000a689  lea     rcx, [rbp+110h+var_160]
0x18000a68d  mov     rax, [rax+0C0h]
0x18000a694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a699  test    al, al
0x18000a69b  jz      loc_18000AB7F
0x18000a6a1  mov     r12, [rbx+48h]
0x18000a6a5  mov     rax, [rbx+18h]
0x18000a6a9  mov     [rsp+210h+var_1C8], rax
0x18000a6ae  test    r12, r12
0x18000a6b1  jz      loc_18000A969
0x18000a6b7  mov     rdi, [rbx+38h]
0x18000a6bb  movzx   r15d, word ptr [rbx+30h]
0x18000a6c0  mov     byte ptr [rsp+210h+var_1E0], sil
0x18000a6c5  movzx   esi, word ptr [rbx+40h]
0x18000a6c9  shr     esi, 1
0x18000a6cb  shr     r15d, 1
0x18000a6ce  mov     [rsp+210h+Src], rdi
0x18000a6d3  cmp     esi, 100h
0x18000a6d9  ja      loc_18000ACC7
0x18000a6df  cmp     r15d, 0FFh
0x18000a6e6  ja      loc_18000ACC7
0x18000a6ec  cmp     cs:NtLmState, 1
0x18000a6f3  lea     eax, [r15+rsi]
0x18000a6f7  lea     r13d, ds:4[rax*2]
0x18000a6ff  mov     edx, r13d; uBytes
0x18000a702  jnz     loc_18000A94E
0x18000a708  mov     rax, cs:LsaFunctions
0x18000a70f  mov     ecx, edx
0x18000a711  mov     rax, [rax+180h]
0x18000a718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a71d  mov     r14, rax
0x18000a720  test    rax, rax
0x18000a723  jz      loc_18000AC63
0x18000a729  test    rdi, rdi
0x18000a72c  jnz     loc_18000AC6D
0x18000a732  mov     rdi, rax
0x18000a735  test    r12, r12
0x18000a738  jnz     loc_18000AC95
0x18000a73e  xor     eax, eax
0x18000a740  mov     [rdi+rsi*2], ax
0x18000a744  movzx   esi, byte ptr [rsp+210h+var_1E0]
0x18000a749  test    sil, sil
0x18000a74c  jnz     loc_18000ACAB
0x18000a752  mov     rax, cs:LsaFunctions
0x18000a759  lea     r8, [rsp+210h+var_1D8]
0x18000a75e  mov     edx, r13d
0x18000a761  xor     ecx, ecx
0x18000a763  mov     rax, [rax+38h]
0x18000a767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a76c  mov     edi, eax
0x18000a76e  test    eax, eax
0x18000a770  js      short loc_18000A7CB
0x18000a772  mov     rax, cs:LsaFunctions
0x18000a779  mov     r9, r14
0x18000a77c  mov     r8, qword ptr [rsp+210h+var_1D8]
0x18000a781  mov     edx, r13d
0x18000a784  xor     ecx, ecx
0x18000a786  mov     rax, [rax+48h]
0x18000a78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a78f  mov     edi, eax
0x18000a791  test    eax, eax
0x18000a793  js      short loc_18000A7C2
0x18000a795  mov     rax, cs:LsaFunctions
0x18000a79c  lea     r9, [rsp+210h+var_1D8]
0x18000a7a1  mov     r8, qword ptr [rsp+210h+var_1A8]
0x18000a7a6  xor     ecx, ecx
0x18000a7a8  test    byte ptr [rbp+110h+var_160+8], 40h
0x18000a7ac  mov     rax, [rax+48h]
0x18000a7b0  jz      loc_18000A873
0x18000a7b6  mov     edx, 4
0x18000a7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c0  mov     edi, eax
0x18000a7c2  test    sil, sil
0x18000a7c5  jnz     loc_18000AD05
0x18000a7cb  mov     rcx, rbx; void *
0x18000a7ce  call    SspCredentialDereferenceCredential
0x18000a7d3  cmp     byte ptr [rsp+210h+var_1E0+1], 0
0x18000a7d8  jnz     loc_18000A8D2
0x18000a7de  lea     r13, WPP_GLOBAL_Control
0x18000a7e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7ec  test    edi, edi
0x18000a7ee  js      loc_18000AB14
0x18000a7f4  mov     r15, [rsp+210h+var_30]
0x18000a7fc  mov     r12, [rsp+210h+var_18]
0x18000a804  mov     rsi, [rsp+200h]
0x18000a80c  mov     rbx, [rsp+210h+arg_18]
0x18000a814  test    r14, r14
0x18000a817  jz      short loc_18000A843
0x18000a819  cmp     cs:NtLmState, 1
0x18000a820  mov     rcx, r14; hMem
0x18000a823  jnz     loc_18000A95E
0x18000a829  mov     rax, cs:LsaFunctions
0x18000a830  mov     rax, [rax+188h]
0x18000a837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a83c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a843  mov     r14, [rsp+210h+var_28]
0x18000a84b  cmp     rcx, r13
0x18000a84e  mov     r13, [rsp+210h+var_20]
0x18000a856  jnz     short loc_18000A8B2
0x18000a858  mov     eax, edi
0x18000a85a  mov     rcx, [rbp+110h+var_40]
0x18000a861  xor     rcx, rsp; StackCookie
0x18000a864  call    __security_check_cookie
0x18000a869  add     rsp, 208h
0x18000a870  pop     rdi
0x18000a871  pop     rbp
0x18000a872  retn
0x18000a873  mov     edx, 8
0x18000a878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a87d  mov     edi, eax
0x18000a87f  jmp     loc_18000A7C2
0x18000a884  test    dword ptr [rcx+1Ch], 100h
0x18000a88b  jz      loc_18000A5EE
0x18000a891  mov     rcx, [rcx+10h]
0x18000a895  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x18000a89c  mov     edx, 2Fh ; '/'
0x18000a8a1  call    WPP_SF_
0x18000a8a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8ad  jmp     loc_18000A5EE
0x18000a8b2  test    dword ptr [rcx+1Ch], 100h
0x18000a8b9  jz      short loc_18000A858
0x18000a8bb  mov     rcx, [rcx+10h]
0x18000a8bf  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x18000a8c6  mov     edx, 36h ; '6'
0x18000a8cb  call    WPP_SF_
0x18000a8d0  jmp     short loc_18000A858
0x18000a8d2  mov     rcx, [rsp+210h+var_1B0]
0x18000a8d7  test    rcx, rcx
0x18000a8da  jnz     loc_18000AD17
0x18000a8e0  lea     rcx, [rsp+210h+var_1A8+8]
0x18000a8e5  call    cs:__imp_LsaIFree_LSAPR_TRANSLATED_NAMES
0x18000a8eb  jmp     loc_18000A7DE
0x18000a8f0  mov     eax, dword ptr [rbp+110h+var_190]
0x18000a8f3  cmp     [rbx+20h], eax
0x18000a8f6  jz      loc_18000A66C
0x18000a8fc  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x18000a903  call    cs:__imp_RtlReleaseResource
0x18000a909  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a910  cmp     rcx, r13
0x18000a913  jnz     loc_18000AAB7
0x18000a919  mov     edi, 0C0000008h
0x18000a91e  cmp     rcx, r13
0x18000a921  jz      loc_18000A7EC
0x18000a927  test    byte ptr [rcx+1Ch], 1
0x18000a92b  jz      loc_18000A7EC
0x18000a931  mov     rcx, [rcx+10h]
0x18000a935  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x18000a93c  mov     edx, 31h ; '1'
0x18000a941  mov     r9d, edi
0x18000a944  call    WPP_SF_d
0x18000a949  jmp     loc_18000A7E5
0x18000a94e  mov     ecx, 40h ; '@'; uFlags
0x18000a953  call    cs:__imp_LocalAlloc
0x18000a959  jmp     loc_18000A71D
0x18000a95e  call    cs:__imp_LocalFree
0x18000a964  jmp     loc_18000A83C
0x18000a969  cmp     [rbx+38h], rsi
0x18000a96d  jnz     loc_18000A6B7
0x18000a973  mov     dl, 1; Wait
0x18000a975  lea     rcx, NlpActiveLogonLock; Resource
0x18000a97c  call    cs:__imp_RtlAcquireResourceShared
0x18000a982  lea     rcx, [rsp+210h+var_1C8]; void *
0x18000a987  call    NlpFindActiveLogon
0x18000a98c  test    rax, rax
0x18000a98f  jnz     loc_18000ABAB
0x18000a995  lea     rcx, NlpActiveLogonLock; Resource
0x18000a99c  mov     [rsp+210h+var_1D0], esi
0x18000a9a0  mov     [rsp+210h+TokenHandle], rsi
0x18000a9a5  call    cs:__imp_RtlReleaseResource
0x18000a9ab  mov     rax, cs:LsaFunctions
0x18000a9b2  lea     rdx, [rsp+210h+TokenHandle]
0x18000a9b7  lea     rcx, [rsp+210h+var_1C8]
0x18000a9bc  mov     rax, [rax+170h]
0x18000a9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9c8  mov     edi, eax
0x18000a9ca  test    eax, eax
0x18000a9cc  js      loc_18000ABC6
0x18000a9d2  mov     rcx, [rsp+210h+TokenHandle]; TokenHandle
0x18000a9d7  lea     rax, [rsp+210h+var_1D0]
0x18000a9dc  mov     r9d, 100h; TokenInformationLength
0x18000a9e2  mov     [rsp+210h+ReturnLength], rax; ReturnLength
0x18000a9e7  lea     r8, [rbp+110h+TokenInformation]; TokenInformation
0x18000a9eb  mov     [rsp+210h+var_1D0], 100h
0x18000a9f3  mov     edx, 1; TokenInformationClass
0x18000a9f8  call    cs:__imp_GetTokenInformation
0x18000a9fe  mov     rcx, [rsp+210h+TokenHandle]; hObject
0x18000aa03  mov     edi, eax
0x18000aa05  call    cs:__imp_CloseHandle
0x18000aa0b  test    edi, edi
0x18000aa0d  jz      short loc_18000AA6D
0x18000aa0f  mov     rcx, cs:NtLmGlobalPolicyHandle
0x18000aa16  lea     rax, [rbp+110h+var_178]
0x18000aa1a  mov     [rbp+110h+var_168], rax
0x18000aa1e  lea     r9, [rsp+210h+var_1A8+8]
0x18000aa23  mov     rax, [rbp+110h+TokenInformation]
0x18000aa27  lea     r8, [rsp+210h+var_1B0]
0x18000aa2c  mov     [rbp+110h+var_178], rax
0x18000aa30  lea     rdx, [rbp+110h+var_170]
0x18000aa34  lea     rax, [rsp+210h+var_1D0+4]
0x18000aa39  mov     [rbp+110h+var_170], 1
0x18000aa41  xorps   xmm0, xmm0
0x18000aa44  mov     qword ptr [rsp+210h+var_1E8], rax
0x18000aa49  mov     dword ptr [rsp+210h+ReturnLength], 1
0x18000aa51  mov     [rsp+210h+var_1D0+4], esi
0x18000aa55  movups  xmmword ptr [rsp+210h+var_1A8+8], xmm0
0x18000aa5a  mov     byte ptr [rsp+210h+var_1E0+1], 1
0x18000aa5f  call    cs:__imp_LsarLookupSids
0x18000aa65  test    eax, eax
0x18000aa67  jns     loc_18000AC0C
0x18000aa6d  mov     edi, 0C000005Fh
0x18000aa72  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa79  cmp     rcx, r13
0x18000aa7c  jz      loc_18000A7CB
0x18000aa82  test    byte ptr [rcx+1Ch], 1
0x18000aa86  jz      loc_18000A7CB
0x18000aa8c  mov     rcx, [rcx+10h]
0x18000aa90  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x18000aa97  mov     edx, 34h ; '4'
0x18000aa9c  call    WPP_SF_
0x18000aaa1  jmp     loc_18000A7CB
0x18000aaa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaad  mov     edi, 0C00000E5h
0x18000aab2  jmp     loc_18000A91E
0x18000aab7  test    byte ptr [rcx+1Ch], 1
0x18000aabb  jz      loc_18000A919
0x18000aac1  mov     rcx, [rcx+10h]
0x18000aac5  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x18000aacc  mov     edx, 0Bh
0x18000aad1  mov     r9, rbx
0x18000aad4  call    WPP_SF_q
0x18000aad9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aae0  jmp     loc_18000A919
0x18000aae5  cmp     rcx, r13
0x18000aae8  jz      short loc_18000AB0F
0x18000aaea  test    byte ptr [rcx+1Ch], 8
0x18000aaee  jz      short loc_18000AB0F
0x18000aaf0  mov     rcx, [rcx+10h]
0x18000aaf4  lea     r8, WPP_9f54ae5c059a34c647826de37781d01b_Traceguids
0x18000aafb  mov     edx, 30h ; '0'
0x18000ab00  mov     r9d, edi
  ... truncated ...
```
