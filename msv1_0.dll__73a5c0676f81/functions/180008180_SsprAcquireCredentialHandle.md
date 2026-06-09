# SsprAcquireCredentialHandle

- ea: `0x180008180`
- end: `0x1800088c3`
- name: `SsprAcquireCredentialHandle`
- size: `1859`
- prototype: `__int64 __usercall@<rax>(struct _LUID *@<rcx>, HANDLE TokenHandle@<rdx>, __int64, __int64, __int64, struct _UNICODE_STRING *, PCUNICODE_STRING String2, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a20`

## callees

- `0x180006c50`
- `0x180008180`
- `0x1800088d0`
- `0x1800094d0`
- `0x180009580`
- `0x18002ee3c`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x18002fb90`
- `0x180030844`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008773`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008773`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800085b4`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800085b4`
- `ntdll!NtQueryInformationToken` at `0x18000840d`
- `ntdll!NtQueryInformationToken` at `0x18000840d`
- `ntdll!NtDuplicateObject` at `0x180008588`
- `ntdll!NtDuplicateObject` at `0x180008588`
- `ntdll!NtClose` at `0x180008896`
- `ntdll!NtClose` at `0x180008896`
- `ntdll!RtlReleaseResource` at `0x180008725`
- `ntdll!RtlReleaseResource` at `0x180008725`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x1800086aa`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x1800086aa`

## pseudocode

```c
__int64 __fastcall SsprAcquireCredentialHandle(
        struct _LUID *a1,
        HANDLE TokenHandle,
        __int64 a3,
        unsigned int a4,
        struct _SSP_CREDENTIAL **a5,
        __int64 a6,
        struct _LSA_TOKEN_INFO_HEADER **a7,
        struct _UNICODE_STRING *a8,
        UNICODE_STRING *String2,
        struct _UNICODE_STRING *a10)
{
  HANDLE v10; // r10
  struct _LUID *v12; // rdx
  _QWORD *v13; // rcx
  int v14; // ebx
  ULONG v15; // r9d
  struct _SSP_CREDENTIAL *v16; // rdi
  PWSTR Buffer; // rcx
  PWSTR v18; // rcx
  PWSTR v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rax
  struct _SSP_CREDENTIAL *v23; // rax
  NTSTATUS v24; // eax
  __int64 v25; // rcx
  _BOOL8 v26; // r8
  struct _LSA_TOKEN_INFO_HEADER **v27; // rcx
  bool v28; // zf
  NTSTATUS v29; // eax
  struct _LIST_ENTRY *Flink; // rax
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  PWSTR v33; // rsi
  int Length; // r15d
  size_t v35; // rbx
  void *v36; // rcx
  unsigned int *ReturnLength; // [rsp+20h] [rbp-E0h]
  struct _LUID *v38; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v39; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE SourceHandle; // [rsp+50h] [rbp-B0h]
  __int64 v41; // [rsp+58h] [rbp-A8h]
  struct _LSA_TOKEN_INFO_HEADER **v42; // [rsp+60h] [rbp-A0h]
  __int64 v43; // [rsp+68h] [rbp-98h]
  __int128 v44; // [rsp+70h] [rbp-90h] BYREF
  __int64 v45; // [rsp+80h] [rbp-80h]
  int TokenInformation; // [rsp+88h] [rbp-78h] BYREF
  __int128 v47; // [rsp+8Ch] [rbp-74h]
  __int128 v48; // [rsp+9Ch] [rbp-64h]
  _DWORD v49[5]; // [rsp+ACh] [rbp-54h] BYREF
  _WORD v50[520]; // [rsp+C0h] [rbp-40h] BYREF

  v10 = TokenHandle;
  SourceHandle = TokenHandle;
  v12 = a1;
  v43 = a6;
  v42 = a7;
  v41 = a3;
  v38 = a1;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
    v13 = WPP_GLOBAL_Control;
    v12 = v38;
    v10 = SourceHandle;
  }
  v14 = 0;
  TokenInformation = 0;
  v15 = 56;
  v39 = 56;
  v47 = 0;
  v48 = 0;
  memset(v49, 0, sizeof(v49));
  if ( (a4 & 2) != 0 )
  {
    SsprCheckMachineLogon(String2, a8, a10, v12, ReturnLength);
    v15 = v39;
    v13 = WPP_GLOBAL_Control;
    v10 = SourceHandle;
  }
  if ( (!a8 || !a8->Buffer) && (!String2 || !String2->Buffer) && (!a10 || !a10->Buffer) )
  {
    if ( !v10 )
    {
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      {
        WPP_SF_(v13[2], 21, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
        v13 = WPP_GLOBAL_Control;
      }
      v14 = -1073741700;
      goto LABEL_19;
    }
    v24 = NtQueryInformationToken(v10, TokenStatistics, &TokenInformation, v15, &v39);
    v14 = v24;
    if ( v24 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (unsigned int)v14;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids,
        (unsigned int)v24);
      goto LABEL_18;
    }
  }
  v16 = SspCredentialLookupCredential(
          v38,
          a4,
          (enum _SECURITY_IMPERSONATION_LEVEL)*(_DWORD *)(v41 + 20),
          *a7,
          (struct _LUID *)&v49[3],
          String2,
          a8,
          a10);
  if ( v16 )
  {
    if ( String2 )
    {
      Buffer = String2->Buffer;
      if ( Buffer )
      {
        NtLmFree(Buffer);
        String2->Buffer = 0;
      }
    }
    if ( a8 )
    {
      v18 = a8->Buffer;
      if ( v18 )
      {
        NtLmFree(v18);
        a8->Buffer = 0;
      }
    }
    if ( a10 )
    {
      v19 = a10->Buffer;
      if ( v19 )
      {
        memset_0(v19, 0, a10->Length);
        NtLmFree(a10->Buffer);
        a10->Buffer = 0;
      }
    }
    *((_DWORD *)v16 + 25) = 0;
    goto LABEL_17;
  }
  v45 = 0;
  v44 = 0;
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v44) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
    v14 = -1073741823;
    goto LABEL_19;
  }
  if ( NtLmState == 1 )
    v23 = (struct _SSP_CREDENTIAL *)((__int64 (__fastcall *)(__int64))LsaFunctions->AllocatePrivateHeap)(176);
  else
    v23 = (struct _SSP_CREDENTIAL *)LocalAlloc(0x40u, 0xB0u);
  v16 = v23;
  if ( v23 )
  {
    memset_0(v23, 0, 0xB0u);
    v25 = v41;
    *((_DWORD *)v16 + 4) = 1;
    *((_DWORD *)v16 + 8) = *(_DWORD *)(v25 + 8);
    *((_DWORD *)v16 + 5) = a4;
    *((_DWORD *)v16 + 25) = 0;
    *((_DWORD *)v16 + 10) = *(_DWORD *)(v25 + 20);
    *((_BYTE *)v16 + 96) = 1;
    *((_BYTE *)v16 + 97) = BYTE8(v44) & 1;
    *((struct _LUID *)v16 + 3) = *v38;
    if ( a8 )
      *((struct _UNICODE_STRING *)v16 + 3) = *a8;
    v26 = 0;
    if ( String2 )
    {
      *((UNICODE_STRING *)v16 + 4) = *String2;
      v33 = String2->Buffer;
      if ( v33 )
      {
        Length = String2->Length;
        if ( (_WORD)Length )
        {
          memset_0(v50, 0, 0x408u);
          v35 = 1030;
          if ( (Length & 0xFFFEu) <= 0x406 )
            v35 = Length & 0xFFFFFFFE;
          memcpy_0(v50, v33, v35);
          if ( v35 >= 0x408 )
            _report_rangecheckfailure();
          *(_WORD *)((char *)v50 + v35) = 0;
          LODWORD(v38) = 0;
          v14 = CredParseUserNameWithType(v50, 0, 0, &v38);
          if ( v14 < 0 )
          {
            v31 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_86;
            v32 = 25;
LABEL_58:
            WPP_SF_(v31[2], v32, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
LABEL_86:
            v36 = (void *)*((_QWORD *)v16 + 14);
            if ( v36 )
              NtClose(v36);
            NtLmFree(v16);
            goto LABEL_18;
          }
          v26 = (_DWORD)v38 == 3;
        }
      }
    }
    if ( a10 )
    {
      *((struct _UNICODE_STRING *)v16 + 5) = *a10;
      if ( !a10->Buffer || !a10->Length )
        v26 = 1;
      v14 = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *, struct _SSP_CREDENTIAL *, _BOOL8))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj
                                                                                                 + 176LL))(
              LocalhostNtLmCredIsoObj::IsoObj,
              v16,
              v26);
      if ( v14 < 0 )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_86;
        v32 = 26;
        goto LABEL_58;
      }
      SspHidePassword((char *)v16 + 80);
    }
    v27 = v42;
    *((_QWORD *)v16 + 13) = *v42;
    v28 = *(_QWORD *)&v49[3] == 0;
    *v27 = 0;
    if ( !v28 )
    {
      v29 = NtDuplicateObject(
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              SourceHandle,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              (PHANDLE)v16 + 14,
              0,
              0,
              2u);
      v14 = v29;
      if ( v29 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids,
            (unsigned int)v29);
        goto LABEL_86;
      }
    }
    *((_QWORD *)v16 + 15) = *(_QWORD *)&v49[3];
    *((_BYTE *)v16 + 96) = 0;
    *((_DWORD *)v16 + 9) = 1097101891;
    RtlAcquireResourceExclusive(&SspCredentialCritSect, 1u);
    Flink = SspCredentialList.Flink;
    if ( SspCredentialList.Flink->Blink != &SspCredentialList )
      __fastfail(3u);
    *((_QWORD *)v16 + 1) = &SspCredentialList;
    *(_QWORD *)v16 = Flink;
    Flink->Blink = (struct _LIST_ENTRY *)v16;
    SspCredentialList.Flink = (struct _LIST_ENTRY *)v16;
    RtlReleaseResource(&SspCredentialCritSect);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids, v16);
LABEL_17:
    v20 = (_QWORD *)v43;
    v21 = NtLmGlobalForever;
    *a5 = v16;
    *v20 = v21;
    if ( v14 < 0 && v16 )
      goto LABEL_86;
LABEL_18:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  v14 = -1073741801;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids, 3221225495LL);
    goto LABEL_18;
  }
LABEL_19:
  if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x200) != 0 )
    WPP_SF_(v13[2], 29, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180008180  push    rbp
0x180008182  push    rbx
0x180008183  push    rsi
0x180008184  push    rdi
0x180008185  push    r12
0x180008187  push    r13
0x180008189  push    r14
0x18000818b  push    r15
0x18000818d  lea     rbp, [rsp-3E8h]
0x180008195  sub     rsp, 4E8h
0x18000819c  mov     rax, cs:__security_cookie
0x1800081a3  xor     rax, rsp
0x1800081a6  mov     [rbp+420h+var_50], rax
0x1800081ad  mov     rax, [rbp+420h+arg_28]
0x1800081b4  mov     r10, rdx
0x1800081b7  mov     rdi, [rbp+420h+arg_30]
0x1800081be  mov     r12d, r9d
0x1800081c1  mov     r15, [rbp+420h+String2]
0x1800081c8  mov     r14, [rbp+420h+arg_48]
0x1800081cf  mov     r13, [rbp+420h+arg_20]
0x1800081d6  mov     rsi, [rbp+420h+arg_38]
0x1800081dd  mov     [rsp+520h+SourceHandle], rdx
0x1800081e2  mov     rdx, rcx
0x1800081e5  mov     [rsp+520h+var_4B8], rax
0x1800081ea  mov     [rsp+520h+var_4C0], rdi
0x1800081ef  mov     [rsp+520h+var_4C8], r8
0x1800081f4  mov     [rsp+520h+var_4E0], rcx
0x1800081f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008200  lea     rax, WPP_GLOBAL_Control
0x180008207  cmp     rcx, rax
0x18000820a  jnz     loc_18000845B
0x180008210  xorps   xmm0, xmm0
0x180008213  xor     ebx, ebx
0x180008215  xor     eax, eax
0x180008217  mov     [rbp+420h+TokenInformation], ebx
0x18000821a  mov     dword ptr [rbp+420h+var_474+10h], eax
0x18000821d  mov     r9d, 38h ; '8'; TokenInformationLength
0x180008223  mov     [rsp+520h+var_4D8], r9d
0x180008228  movups  [rbp+420h+var_494], xmm0
0x18000822c  movups  [rbp+420h+var_484], xmm0
0x180008230  movups  xmmword ptr [rbp+420h+var_474], xmm0
0x180008234  test    r12b, 2
0x180008238  jnz     loc_1800086E5
0x18000823e  test    rsi, rsi
0x180008241  jz      loc_1800083D0
0x180008247  cmp     [rsi+8], rbx
0x18000824b  jz      loc_1800083D0
0x180008251  mov     r8, [rsp+520h+var_4C8]
0x180008256  lea     rax, [rbp+420h+var_474+0Ch]
0x18000825a  mov     r9, [rdi]; struct _LSA_TOKEN_INFO_HEADER *
0x18000825d  mov     edx, r12d; unsigned int
0x180008260  mov     rcx, [rsp+520h+var_4E0]; struct _LUID *
0x180008265  mov     [rsp+520h+var_4E8], r14; struct _UNICODE_STRING *
0x18000826a  mov     r8d, [r8+14h]; enum _SECURITY_IMPERSONATION_LEVEL
0x18000826e  mov     qword ptr [rsp+520h+Options], rsi; struct _UNICODE_STRING *
0x180008273  mov     qword ptr [rsp+520h+HandleAttributes], r15; struct _UNICODE_STRING *
0x180008278  mov     [rsp+520h+ReturnLength], rax; struct _LUID *
0x18000827d  call    ?SspCredentialLookupCredential@@YAPEAU_SSP_CREDENTIAL@@PEAU_LUID@@KW4_SECURITY_IMPERSONATION_LEVEL@@PEAU_LSA_TOKEN_INFO_HEADER@@0PEAU_UNICODE_STRING@@33@Z; SspCredentialLookupCredential(_LUID *,ulong,_SECURITY_IMPERSONATION_LEVEL,_LSA_TOKEN_INFO_HEADER *,_LUID *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180008282  mov     rdi, rax
0x180008285  test    rax, rax
0x180008288  jz      loc_18000832B
0x18000828e  test    r15, r15
0x180008291  jz      short loc_1800082A0
0x180008293  mov     rcx, [r15+8]
0x180008297  test    rcx, rcx
0x18000829a  jnz     loc_1800087B6
0x1800082a0  test    rsi, rsi
0x1800082a3  jz      short loc_1800082B2
0x1800082a5  mov     rcx, [rsi+8]
0x1800082a9  test    rcx, rcx
0x1800082ac  jnz     loc_1800087C8
0x1800082b2  test    r14, r14
0x1800082b5  jz      short loc_1800082C4
0x1800082b7  mov     rcx, [r14+8]; void *
0x1800082bb  test    rcx, rcx
0x1800082be  jnz     loc_1800087DA
0x1800082c4  mov     dword ptr [rdi+64h], 0
0x1800082cb  lea     rsi, WPP_GLOBAL_Control
0x1800082d2  mov     rcx, [rsp+520h+var_4B8]
0x1800082d7  mov     rax, cs:NtLmGlobalForever
0x1800082de  mov     [r13+0], rdi
0x1800082e2  mov     [rcx], rax
0x1800082e5  test    ebx, ebx
0x1800082e7  js      loc_180008884
0x1800082ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082f4  cmp     rcx, rsi
0x1800082f7  jz      short loc_180008306
0x1800082f9  test    dword ptr [rcx+1Ch], 200h
0x180008300  jnz     loc_1800088A9
0x180008306  mov     eax, ebx
0x180008308  mov     rcx, [rbp+420h+var_50]
0x18000830f  xor     rcx, rsp; StackCookie
0x180008312  call    __security_check_cookie
0x180008317  add     rsp, 4E8h
0x18000831e  pop     r15
0x180008320  pop     r14
0x180008322  pop     r13
0x180008324  pop     r12
0x180008326  pop     rdi
0x180008327  pop     rsi
0x180008328  pop     rbx
0x180008329  pop     rbp
0x18000832a  retn
0x18000832b  xor     eax, eax
0x18000832d  lea     rcx, [rsp+520h+var_4B0]
0x180008332  mov     [rbp+420h+var_4A0], rax
0x180008336  xorps   xmm0, xmm0
0x180008339  mov     rax, cs:LsaFunctions
0x180008340  movups  [rsp+520h+var_4B0], xmm0
0x180008345  mov     rax, [rax+0C0h]
0x18000834c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008351  test    al, al
0x180008353  jz      loc_1800087FB
0x180008359  cmp     cs:NtLmState, 1
0x180008360  jnz     loc_180008769
0x180008366  mov     rax, cs:LsaFunctions
0x18000836d  mov     ecx, 0B0h
0x180008372  mov     rax, [rax+180h]
0x180008379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000837e  mov     rdi, rax
0x180008381  test    rax, rax
0x180008384  jnz     loc_180008493
0x18000838a  mov     ebx, 0C0000017h
0x18000838f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008396  lea     rsi, WPP_GLOBAL_Control
0x18000839d  cmp     rcx, rsi
0x1800083a0  jz      loc_180008306
0x1800083a6  test    byte ptr [rcx+1Ch], 1
0x1800083aa  jz      loc_1800082F4
0x1800083b0  mov     rcx, [rcx+10h]
0x1800083b4  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x1800083bb  mov     edx, 18h
0x1800083c0  mov     r9d, 0C0000017h
0x1800083c6  call    WPP_SF_d
0x1800083cb  jmp     loc_1800082ED
0x1800083d0  test    r15, r15
0x1800083d3  jz      short loc_1800083DF
0x1800083d5  cmp     [r15+8], rbx
0x1800083d9  jnz     loc_180008251
0x1800083df  test    r14, r14
0x1800083e2  jz      short loc_1800083EE
0x1800083e4  cmp     [r14+8], rbx
0x1800083e8  jnz     loc_180008251
0x1800083ee  test    r10, r10
0x1800083f1  jz      loc_18000877E
0x1800083f7  lea     rax, [rsp+520h+var_4D8]
0x1800083fc  mov     edx, 0Ah; TokenInformationClass
0x180008401  lea     r8, [rbp+420h+TokenInformation]; TokenInformation
0x180008405  mov     [rsp+520h+ReturnLength], rax; ReturnLength
0x18000840a  mov     rcx, r10; TokenHandle
0x18000840d  call    cs:__imp_NtQueryInformationToken
0x180008413  mov     ebx, eax
0x180008415  test    eax, eax
0x180008417  jns     loc_180008251
0x18000841d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008424  lea     rsi, WPP_GLOBAL_Control
0x18000842b  cmp     rcx, rsi
0x18000842e  jz      loc_180008306
0x180008434  test    byte ptr [rcx+1Ch], 1
0x180008438  jz      loc_1800082F4
0x18000843e  mov     rcx, [rcx+10h]
0x180008442  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x180008449  mov     edx, 16h
0x18000844e  mov     r9d, eax
0x180008451  call    WPP_SF_d
0x180008456  jmp     loc_1800082ED
0x18000845b  test    dword ptr [rcx+1Ch], 200h
0x180008462  jz      loc_180008210
0x180008468  mov     rcx, [rcx+10h]
0x18000846c  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x180008473  mov     edx, 14h
0x180008478  call    WPP_SF_
0x18000847d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008484  mov     rdx, [rsp+520h+var_4E0]
0x180008489  mov     r10, [rsp+520h+SourceHandle]
0x18000848e  jmp     loc_180008210
0x180008493  xor     edx, edx; Val
0x180008495  mov     r8d, 0B0h; Size
0x18000849b  mov     rcx, rdi; void *
0x18000849e  call    memset_0
0x1800084a3  mov     rcx, [rsp+520h+var_4C8]
0x1800084a8  mov     dword ptr [rdi+10h], 1
0x1800084af  mov     eax, [rcx+8]
0x1800084b2  mov     [rdi+20h], eax
0x1800084b5  mov     [rdi+14h], r12d
0x1800084b9  mov     dword ptr [rdi+64h], 0
0x1800084c0  mov     eax, [rcx+14h]
0x1800084c3  mov     [rdi+28h], eax
0x1800084c6  mov     byte ptr [rdi+60h], 1
0x1800084ca  movzx   eax, byte ptr [rsp+520h+var_4B0+8]
0x1800084cf  and     al, 1
0x1800084d1  mov     [rdi+61h], al
0x1800084d4  mov     rax, [rsp+520h+var_4E0]
0x1800084d9  mov     rax, [rax]
0x1800084dc  mov     [rdi+18h], rax
0x1800084e0  test    rsi, rsi
0x1800084e3  jz      short loc_1800084EC
0x1800084e5  movups  xmm0, xmmword ptr [rsi]
0x1800084e8  movups  xmmword ptr [rdi+30h], xmm0
0x1800084ec  xor     r8d, r8d
0x1800084ef  test    r15, r15
0x1800084f2  jnz     loc_180008624
0x1800084f8  test    r14, r14
0x1800084fb  jz      short loc_180008542
0x1800084fd  movups  xmm0, xmmword ptr [r14]
0x180008501  movups  xmmword ptr [rdi+50h], xmm0
0x180008505  cmp     qword ptr [r14+8], 0
0x18000850a  jnz     loc_1800085D9
0x180008510  mov     r8d, 1
0x180008516  mov     rcx, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x18000851d  mov     rdx, rdi
0x180008520  mov     rax, [rcx]
0x180008523  mov     rax, [rax+0B0h]
0x18000852a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000852f  mov     ebx, eax
0x180008531  test    eax, eax
0x180008533  js      loc_1800085E9
0x180008539  lea     rcx, [rdi+50h]
0x18000853d  call    SspHidePassword
0x180008542  mov     rcx, [rsp+520h+var_4C0]
0x180008547  mov     rax, [rcx]
0x18000854a  mov     [rdi+68h], rax
0x18000854e  mov     eax, dword ptr [rbp+420h+var_474+10h]
0x180008551  or      eax, dword ptr [rbp+420h+var_474+0Ch]
0x180008554  mov     qword ptr [rcx], 0
0x18000855b  jz      short loc_180008598
0x18000855d  mov     rdx, [rsp+520h+SourceHandle]; SourceHandle
0x180008562  lea     r9, [rdi+70h]; TargetHandle
0x180008566  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x18000856d  mov     [rsp+520h+Options], 2; Options
0x180008575  mov     rcx, r8; SourceProcessHandle
0x180008578  mov     [rsp+520h+HandleAttributes], 0; HandleAttributes
0x180008580  mov     dword ptr [rsp+520h+ReturnLength], 0; DesiredAccess
0x180008588  call    cs:__imp_NtDuplicateObject
0x18000858e  mov     ebx, eax
0x180008590  test    eax, eax
0x180008592  js      loc_180008851
0x180008598  mov     rax, qword ptr [rbp+420h+var_474+0Ch]
0x18000859c  lea     rcx, ?SspCredentialCritSect@@3U_RTL_RESOURCE@@A; Resource
0x1800085a3  mov     dl, 1; Wait
0x1800085a5  mov     [rdi+78h], rax
0x1800085a9  mov     byte ptr [rdi+60h], 0
0x1800085ad  mov     dword ptr [rdi+24h], 41647243h
0x1800085b4  call    cs:__imp_RtlAcquireResourceExclusive
0x1800085ba  mov     rax, cs:?SspCredentialList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SspCredentialList
0x1800085c1  lea     rcx, ?SspCredentialList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SspCredentialList
0x1800085c8  cmp     [rax+8], rcx
0x1800085cc  jz      loc_18000870C
0x1800085d2  mov     ecx, 3
0x1800085d7  int     29h; Win8: RtlFailFast(ecx)
0x1800085d9  cmp     word ptr [r14], 0
0x1800085de  jnz     loc_180008516
0x1800085e4  jmp     loc_180008510
0x1800085e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085f0  lea     rsi, WPP_GLOBAL_Control
0x1800085f7  cmp     rcx, rsi
0x1800085fa  jz      loc_18000888D
0x180008600  test    byte ptr [rcx+1Ch], 1
0x180008604  jz      loc_18000888D
0x18000860a  mov     edx, 1Ah
0x18000860f  mov     rcx, [rcx+10h]
0x180008613  lea     r8, WPP_589a2f61f8ac3b6ff36408465b886615_Traceguids
0x18000861a  call    WPP_SF_
0x18000861f  jmp     loc_18000888D
0x180008624  movups  xmm0, xmmword ptr [r15]
0x180008628  movups  xmmword ptr [rdi+40h], xmm0
0x18000862c  mov     rsi, [r15+8]
0x180008630  test    rsi, rsi
0x180008633  jz      loc_1800084F8
0x180008639  movzx   r15d, word ptr [r15]
0x18000863d  test    r15w, r15w
0x180008641  jz      loc_1800084F8
0x180008647  xor     edx, edx; Val
0x180008649  lea     rcx, [rbp+420h+var_460]; void *
0x18000864d  mov     r8d, 408h; Size
0x180008653  call    memset_0
0x180008658  movzx   eax, r15w
0x18000865c  mov     ecx, 0FFFEh
0x180008661  and     ax, cx
0x180008664  mov     ebx, 406h
0x180008669  cmp     bx, ax
0x18000866c  jb      short loc_180008675
0x18000866e  mov     ebx, r15d
0x180008671  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180008675  mov     r8, rbx; Size
0x180008678  lea     rcx, [rbp+420h+var_460]; void *
0x18000867c  mov     rdx, rsi; Src
0x18000867f  call    memcpy_0
0x180008684  cmp     rbx, 408h
0x18000868b  jnb     loc_18000884B
0x180008691  xor     eax, eax
0x180008693  lea     r9, [rsp+520h+var_4E0]
0x180008698  xor     r8d, r8d
0x18000869b  mov     [rbp+rbx+420h+var_460], ax
0x1800086a0  xor     edx, edx
0x1800086a2  mov     dword ptr [rsp+520h+var_4E0], eax
0x1800086a6  lea     rcx, [rbp+420h+var_460]
0x1800086aa  call    cs:__imp_CredParseUserNameWithType
0x1800086b0  mov     ebx, eax
0x1800086b2  test    eax, eax
  ... truncated ...
```
