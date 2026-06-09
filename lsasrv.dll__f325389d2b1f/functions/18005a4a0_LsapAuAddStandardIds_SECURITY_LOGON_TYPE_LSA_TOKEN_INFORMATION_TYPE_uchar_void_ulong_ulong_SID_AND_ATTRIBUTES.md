# LsapAuAddStandardIds(_SECURITY_LOGON_TYPE,_LSA_TOKEN_INFORMATION_TYPE,uchar,void *,ulong,ulong *,_SID_AND_ATTRIBUTES *)

- ea: `0x18005a4a0`
- end: `0x18005a8f5`
- name: `?LsapAuAddStandardIds@@YAJW4_SECURITY_LOGON_TYPE@@W4_LSA_TOKEN_INFORMATION_TYPE@@EPEAXKPEAKPEAU_SID_AND_ATTRIBUTES@@@Z`
- size: `1109`
- prototype: `int(enum _SECURITY_LOGON_TYPE, enum _LSA_TOKEN_INFORMATION_TYPE, unsigned __int8, void *, unsigned int, unsigned int *, struct _SID_AND_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180059a94`

## callees

- `0x180011278`
- `0x18005a4a0`
- `0x18005a8fc`
- `0x1800f0a2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005a4d8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005a4d8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18005a8d1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18005a8d1`
- `ntdll!RtlGetSuiteMask` at `0x18005a5ad`
- `ntdll!RtlGetSuiteMask` at `0x18005a5ad`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a553`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a69a`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a6ae`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a763`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a77b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a553`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a69a`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a6ae`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a763`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005a77b`
- `ntdll!RtlSubAuthoritySid` at `0x18005a569`
- `ntdll!RtlSubAuthoritySid` at `0x18005a6c2`
- `ntdll!RtlSubAuthoritySid` at `0x18005a78f`
- `ntdll!RtlSubAuthoritySid` at `0x18005a569`
- `ntdll!RtlSubAuthoritySid` at `0x18005a6c2`
- `ntdll!RtlSubAuthoritySid` at `0x18005a78f`
- `ntdll!NtQueryInformationToken` at `0x18005a632`
- `ntdll!NtQueryInformationToken` at `0x18005a632`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18005a652`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18005a652`

## pseudocode

```c
__int64 __fastcall LsapAuAddStandardIds(
        enum _SECURITY_LOGON_TYPE a1,
        enum _LSA_TOKEN_INFORMATION_TYPE a2,
        char a3,
        void *a4,
        ULONG ReturnLength,
        unsigned int *a6,
        struct _SID_AND_ATTRIBUTES *a7)
{
  unsigned int v8; // r12d
  int v11; // r13d
  _QWORD *Value; // rdx
  struct _SID_AND_ATTRIBUTES *v13; // rsi
  unsigned int v14; // edi
  __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  enum _LSA_TOKEN_INFORMATION_TYPE v17; // ebx
  int v18; // r14d
  int v19; // r14d
  int v20; // r14d
  void *v21; // rcx
  char v22; // al
  __int64 v23; // rdx
  PUCHAR v24; // rax
  __int64 v25; // rdx
  __int64 result; // rax
  PUCHAR v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  void *v30; // [rsp+30h] [rbp-10h] BYREF
  _QWORD *v31; // [rsp+38h] [rbp-8h]
  unsigned int TokenInformation; // [rsp+80h] [rbp+40h] BYREF
  enum _LSA_TOKEN_INFORMATION_TYPE v33; // [rsp+88h] [rbp+48h]
  char v34; // [rsp+90h] [rbp+50h] BYREF

  v33 = a2;
  v8 = 0;
  v34 = 0;
  v30 = 0;
  v11 = 0;
  Value = TlsGetValue(dwCallInfo);
  v13 = a7;
  v31 = Value;
  v14 = *a6;
  if ( !a3 )
  {
    v15 = v14++;
    a7[v15].Sid = (PSID)*((_QWORD *)WellKnownSids + 6);
    v13[v15].Attributes = 7;
    Value = v31;
  }
  switch ( a1 )
  {
    case Interactive:
LABEL_56:
      v16 = *((_QWORD *)WellKnownSids + 66);
      goto LABEL_57;
    case Network:
      goto LABEL_55;
    case Batch:
      v16 = *((_QWORD *)WellKnownSids + 60);
      goto LABEL_57;
  }
  v16 = (unsigned int)(a1 - 5);
  if ( a1 == Service )
  {
    v17 = v33;
    if ( v33 && a4 && *RtlSubAuthorityCountSid(a4) && *RtlSubAuthoritySid(a4, 0) != 99 )
    {
      Value = (_QWORD *)(2LL * v14);
      v16 = *((_QWORD *)WellKnownSids + 72);
      v13[v14].Sid = (PSID)v16;
    }
    v11 = 1;
LABEL_13:
    if ( v13[v14].Sid )
      v13[v14++].Attributes = 7;
    if ( (RtlGetSuiteMask(v16, Value) & 0x10) != 0 )
    {
      v18 = a1 - 2;
      if ( v18 )
      {
        v19 = v18 - 7;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            if ( v20 != 1 )
              goto LABEL_20;
          }
          else
          {
            v29 = v14++;
            v13[v29].Sid = (PSID)*((_QWORD *)WellKnownSids + 66);
            v13[v29].Attributes = 7;
          }
        }
      }
      if ( IsTSUSerSidEnabled() )
      {
        if ( v17 )
        {
          if ( a4 )
          {
            if ( *RtlSubAuthorityCountSid(a4) )
            {
              v27 = RtlSubAuthorityCountSid(a4);
              if ( *RtlSubAuthoritySid(a4, (unsigned int)*v27 - 1) != 501 )
              {
                v28 = v14++;
                v13[v28].Sid = (PSID)*((_QWORD *)WellKnownSids + 150);
                v13[v28].Attributes = 7;
              }
            }
          }
        }
      }
    }
LABEL_20:
    if ( v11 )
    {
      if ( LsapEnableLocalLogonSid )
      {
        TokenInformation = 0;
        ReturnLength = 4;
        if ( v31 )
        {
          v21 = (void *)v31[34];
          if ( v21 )
          {
            v8 = NtQueryInformationToken(v21, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
            if ( (v8 & 0x80000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_fac8e1c640d53114d3306e5e667a867e_Traceguids, v8);
              }
              return v8;
            }
            if ( (unsigned __int8)WinStationIsSessionRemoteable(0, TokenInformation, &v34) )
            {
              v22 = v34;
              goto LABEL_27;
            }
            if ( TokenInformation == WTSGetActiveConsoleSessionId() )
            {
              v22 = 0;
              v34 = 0;
LABEL_27:
              if ( !v22 )
              {
                v23 = v14++;
                v13[v23].Sid = (PSID)*((_QWORD *)WellKnownSids + 276);
                v13[v23].Attributes = 7;
              }
              goto LABEL_29;
            }
            v34 = 1;
          }
        }
      }
    }
LABEL_29:
    if ( v17 && a4 && *RtlSubAuthorityCountSid(a4) )
    {
      v24 = RtlSubAuthorityCountSid(a4);
      if ( *RtlSubAuthoritySid(a4, (unsigned int)*v24 - 1) != 501 )
      {
        v25 = v14++;
        v13[v25].Sid = (PSID)*((_QWORD *)WellKnownSids + 132);
        v13[v25].Attributes = 7;
      }
    }
    *a6 = v14;
    return v8;
  }
  if ( a1 == NetworkCleartext )
  {
LABEL_55:
    Value = (_QWORD *)(2LL * v14);
    v16 = *((_QWORD *)WellKnownSids + 54);
    v13[v14].Sid = (PSID)v16;
    goto LABEL_41;
  }
  v16 = (unsigned int)(a1 - 9);
  if ( a1 != NewCredentials )
  {
    v16 = (unsigned int)(a1 - 10);
    if ( a1 != RemoteInteractive )
    {
      if ( a1 != CachedInteractive )
      {
LABEL_41:
        v17 = v33;
        goto LABEL_13;
      }
      goto LABEL_56;
    }
    v16 = *((_QWORD *)WellKnownSids + 174);
LABEL_57:
    Value = (_QWORD *)(2LL * v14);
    v13[v14].Sid = (PSID)v16;
    goto LABEL_58;
  }
  if ( !Value )
    goto LABEL_41;
  v16 = Value[34];
  if ( !v16 )
    goto LABEL_41;
  result = DetectCallerLogonTypeSid((HANDLE)v16, &v30);
  v8 = result;
  if ( (int)result >= 0 )
  {
    v16 = (unsigned __int64)v30;
    if ( !v30 )
      goto LABEL_41;
    v13[v14].Sid = v30;
LABEL_58:
    v11 = 1;
    goto LABEL_41;
  }
  return result;
}

```

## disassembly

```asm
0x18005a4a0  mov     [rsp-38h+arg_18], rbx
0x18005a4a5  mov     [rsp-38h+arg_8], edx
0x18005a4a9  push    rbp
0x18005a4aa  push    rsi
0x18005a4ab  push    rdi
0x18005a4ac  push    r12
0x18005a4ae  push    r13
0x18005a4b0  push    r14
0x18005a4b2  push    r15
0x18005a4b4  mov     rbp, rsp
0x18005a4b7  sub     rsp, 40h
0x18005a4bb  mov     r14d, ecx
0x18005a4be  xor     r12d, r12d
0x18005a4c1  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x18005a4c7  mov     r15, r9
0x18005a4ca  mov     [rbp+arg_10], r12b
0x18005a4ce  mov     bl, r8b
0x18005a4d1  mov     [rbp+var_10], r12
0x18005a4d5  xor     r13d, r13d
0x18005a4d8  call    cs:__imp_TlsGetValue
0x18005a4df  nop     dword ptr [rax+rax+00h]
0x18005a4e4  mov     rdi, [rbp+arg_28]
0x18005a4e8  mov     rdx, rax
0x18005a4eb  mov     rsi, [rbp+arg_30]
0x18005a4ef  mov     [rbp+var_8], rax
0x18005a4f3  mov     edi, [rdi]
0x18005a4f5  test    bl, bl
0x18005a4f7  jnz     short loc_18005A51B
0x18005a4f9  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a500  mov     edx, edi
0x18005a502  add     rdx, rdx
0x18005a505  inc     edi
0x18005a507  mov     rcx, [rax+30h]
0x18005a50b  mov     [rsi+rdx*8], rcx
0x18005a50f  mov     dword ptr [rsi+rdx*8+8], 7
0x18005a517  mov     rdx, [rbp+var_8]
0x18005a51b  mov     ecx, r14d
0x18005a51e  mov     ebx, 1
0x18005a523  sub     ecx, 2
0x18005a526  jz      loc_18005A84E
0x18005a52c  sub     ecx, ebx
0x18005a52e  jz      loc_18005A832
0x18005a534  sub     ecx, ebx
0x18005a536  jz      loc_18005A822
0x18005a53c  sub     ecx, ebx
0x18005a53e  jnz     loc_18005A719
0x18005a544  mov     ebx, [rbp+arg_8]
0x18005a547  test    ebx, ebx
0x18005a549  jz      short loc_18005A591
0x18005a54b  test    r15, r15
0x18005a54e  jz      short loc_18005A591
0x18005a550  mov     rcx, r15; Sid
0x18005a553  call    cs:__imp_RtlSubAuthorityCountSid
0x18005a55a  nop     dword ptr [rax+rax+00h]
0x18005a55f  cmp     [rax], r12b
0x18005a562  jbe     short loc_18005A591
0x18005a564  xor     edx, edx; SubAuthority
0x18005a566  mov     rcx, r15; Sid
0x18005a569  call    cs:__imp_RtlSubAuthoritySid
0x18005a570  nop     dword ptr [rax+rax+00h]
0x18005a575  cmp     dword ptr [rax], 63h ; 'c'
0x18005a578  jz      short loc_18005A591
0x18005a57a  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a581  mov     edx, edi
0x18005a583  add     rdx, rdx
0x18005a586  mov     rcx, [rax+240h]
0x18005a58d  mov     [rsi+rdx*8], rcx
0x18005a591  mov     r13d, 1
0x18005a597  mov     eax, edi
0x18005a599  add     rax, rax
0x18005a59c  cmp     qword ptr [rsi+rax*8], 0
0x18005a5a1  jz      short loc_18005A5AD
0x18005a5a3  mov     dword ptr [rsi+rax*8+8], 7
0x18005a5ab  inc     edi
0x18005a5ad  call    cs:__imp_RtlGetSuiteMask
0x18005a5b4  nop     dword ptr [rax+rax+00h]
0x18005a5b9  test    al, 10h
0x18005a5bb  jz      short loc_18005A5E5
0x18005a5bd  sub     r14d, 2
0x18005a5c1  jz      loc_18005A742
0x18005a5c7  sub     r14d, 7
0x18005a5cb  jz      loc_18005A742
0x18005a5d1  sub     r14d, 1
0x18005a5d5  jz      loc_18005A86D
0x18005a5db  cmp     r14d, 1
0x18005a5df  jz      loc_18005A742
0x18005a5e5  test    r13d, r13d
0x18005a5e8  jz      loc_18005A68E
0x18005a5ee  cmp     cs:?LsapEnableLocalLogonSid@@3KA, 0; ulong LsapEnableLocalLogonSid
0x18005a5f5  jz      loc_18005A68E
0x18005a5fb  mov     rcx, [rbp+var_8]
0x18005a5ff  mov     r9d, 4; TokenInformationLength
0x18005a605  mov     [rbp+TokenInformation], 0
0x18005a60c  mov     [rbp+arg_20], r9d
0x18005a610  test    rcx, rcx
0x18005a613  jz      short loc_18005A68E
0x18005a615  mov     rcx, [rcx+110h]; TokenHandle
0x18005a61c  test    rcx, rcx
0x18005a61f  jz      short loc_18005A68E
0x18005a621  lea     rax, [rbp+arg_20]
0x18005a625  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18005a629  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18005a62e  lea     edx, [r9+8]; TokenInformationClass
0x18005a632  call    cs:__imp_NtQueryInformationToken
0x18005a639  nop     dword ptr [rax+rax+00h]
0x18005a63e  mov     r12d, eax
0x18005a641  test    eax, eax
0x18005a643  js      loc_18005A893
0x18005a649  mov     edx, [rbp+TokenInformation]
0x18005a64c  lea     r8, [rbp+arg_10]
0x18005a650  xor     ecx, ecx
0x18005a652  call    cs:__imp_WinStationIsSessionRemoteable
0x18005a659  nop     dword ptr [rax+rax+00h]
0x18005a65e  test    al, al
0x18005a660  jz      loc_18005A8D1
0x18005a666  mov     al, [rbp+arg_10]
0x18005a669  test    al, al
0x18005a66b  jnz     short loc_18005A68E
0x18005a66d  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a674  mov     edx, edi
0x18005a676  add     rdx, rdx
0x18005a679  inc     edi
0x18005a67b  mov     rcx, [rax+8A0h]
0x18005a682  mov     [rsi+rdx*8], rcx
0x18005a686  mov     dword ptr [rsi+rdx*8+8], 7
0x18005a68e  test    ebx, ebx
0x18005a690  jz      short loc_18005A6F7
0x18005a692  test    r15, r15
0x18005a695  jz      short loc_18005A6F7
0x18005a697  mov     rcx, r15; Sid
0x18005a69a  call    cs:__imp_RtlSubAuthorityCountSid
0x18005a6a1  nop     dword ptr [rax+rax+00h]
0x18005a6a6  cmp     byte ptr [rax], 0
0x18005a6a9  jbe     short loc_18005A6F7
0x18005a6ab  mov     rcx, r15; Sid
0x18005a6ae  call    cs:__imp_RtlSubAuthorityCountSid
0x18005a6b5  nop     dword ptr [rax+rax+00h]
0x18005a6ba  mov     rcx, r15; Sid
0x18005a6bd  movzx   edx, byte ptr [rax]
0x18005a6c0  dec     edx; SubAuthority
0x18005a6c2  call    cs:__imp_RtlSubAuthoritySid
0x18005a6c9  nop     dword ptr [rax+rax+00h]
0x18005a6ce  cmp     dword ptr [rax], 1F5h
0x18005a6d4  jz      short loc_18005A6F7
0x18005a6d6  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a6dd  mov     edx, edi
0x18005a6df  add     rdx, rdx
0x18005a6e2  inc     edi
0x18005a6e4  mov     rcx, [rax+420h]
0x18005a6eb  mov     [rsi+rdx*8], rcx
0x18005a6ef  mov     dword ptr [rsi+rdx*8+8], 7
0x18005a6f7  mov     rax, [rbp+arg_28]
0x18005a6fb  mov     [rax], edi
0x18005a6fd  mov     eax, r12d
0x18005a700  mov     rbx, [rsp+40h+arg_18]
0x18005a708  add     rsp, 40h
0x18005a70c  pop     r15
0x18005a70e  pop     r14
0x18005a710  pop     r13
0x18005a712  pop     r12
0x18005a714  pop     rdi
0x18005a715  pop     rsi
0x18005a716  pop     rbp
0x18005a717  retn
0x18005a719  sub     ecx, 3
0x18005a71c  jz      loc_18005A832
0x18005a722  sub     ecx, ebx
0x18005a724  jz      loc_18005A7CD
0x18005a72a  sub     ecx, ebx
0x18005a72c  jz      loc_18005A812
0x18005a732  cmp     ecx, ebx
0x18005a734  jz      loc_18005A84E
0x18005a73a  mov     ebx, [rbp+arg_8]
0x18005a73d  jmp     loc_18005A597
0x18005a742  call    ?IsTSUSerSidEnabled@@YAEXZ; IsTSUSerSidEnabled(void)
0x18005a747  test    al, al
0x18005a749  jz      loc_18005A5E5
0x18005a74f  test    ebx, ebx
0x18005a751  jz      loc_18005A5E5
0x18005a757  test    r15, r15
0x18005a75a  jz      loc_18005A5E5
0x18005a760  mov     rcx, r15; Sid
0x18005a763  call    cs:__imp_RtlSubAuthorityCountSid
0x18005a76a  nop     dword ptr [rax+rax+00h]
0x18005a76f  cmp     byte ptr [rax], 0
0x18005a772  jbe     loc_18005A5E5
0x18005a778  mov     rcx, r15; Sid
0x18005a77b  call    cs:__imp_RtlSubAuthorityCountSid
0x18005a782  nop     dword ptr [rax+rax+00h]
0x18005a787  mov     rcx, r15; Sid
0x18005a78a  movzx   edx, byte ptr [rax]
0x18005a78d  dec     edx; SubAuthority
0x18005a78f  call    cs:__imp_RtlSubAuthoritySid
0x18005a796  nop     dword ptr [rax+rax+00h]
0x18005a79b  cmp     dword ptr [rax], 1F5h
0x18005a7a1  jz      loc_18005A5E5
0x18005a7a7  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a7ae  mov     edx, edi
0x18005a7b0  add     rdx, rdx
0x18005a7b3  inc     edi
0x18005a7b5  mov     rcx, [rax+4B0h]
0x18005a7bc  mov     [rsi+rdx*8], rcx
0x18005a7c0  mov     dword ptr [rsi+rdx*8+8], 7
0x18005a7c8  jmp     loc_18005A5E5
0x18005a7cd  test    rdx, rdx
0x18005a7d0  jz      loc_18005A73A
0x18005a7d6  mov     rcx, [rdx+110h]; TokenHandle
0x18005a7dd  test    rcx, rcx
0x18005a7e0  jz      loc_18005A73A
0x18005a7e6  lea     rdx, [rbp+var_10]; void **
0x18005a7ea  call    ?DetectCallerLogonTypeSid@@YAJPEAXPEAPEAX@Z; DetectCallerLogonTypeSid(void *,void * *)
0x18005a7ef  mov     r12d, eax
0x18005a7f2  test    eax, eax
0x18005a7f4  js      loc_18005A700
0x18005a7fa  mov     rcx, [rbp+var_10]
0x18005a7fe  test    rcx, rcx
0x18005a801  jz      loc_18005A73A
0x18005a807  mov     eax, edi
0x18005a809  add     rax, rax
0x18005a80c  mov     [rsi+rax*8], rcx
0x18005a810  jmp     short loc_18005A865
0x18005a812  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a819  mov     rcx, [rax+570h]
0x18005a820  jmp     short loc_18005A85C
0x18005a822  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a829  mov     rcx, [rax+1E0h]
0x18005a830  jmp     short loc_18005A85C
0x18005a832  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a839  mov     edx, edi
0x18005a83b  add     rdx, rdx
0x18005a83e  mov     rcx, [rax+1B0h]
0x18005a845  mov     [rsi+rdx*8], rcx
0x18005a849  jmp     loc_18005A73A
0x18005a84e  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a855  mov     rcx, [rax+210h]
0x18005a85c  mov     edx, edi
0x18005a85e  add     rdx, rdx
0x18005a861  mov     [rsi+rdx*8], rcx
0x18005a865  mov     r13d, ebx
0x18005a868  jmp     loc_18005A73A
0x18005a86d  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18005a874  mov     edx, edi
0x18005a876  add     rdx, rdx
0x18005a879  inc     edi
0x18005a87b  mov     rcx, [rax+210h]
0x18005a882  mov     [rsi+rdx*8], rcx
0x18005a886  mov     dword ptr [rsi+rdx*8+8], 7
0x18005a88e  jmp     loc_18005A742
0x18005a893  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a89a  lea     rax, WPP_GLOBAL_Control
0x18005a8a1  cmp     rcx, rax
0x18005a8a4  jz      loc_18005A6FD
0x18005a8aa  test    byte ptr [rcx+1Ch], 1
0x18005a8ae  jz      loc_18005A6FD
0x18005a8b4  mov     rcx, [rcx+10h]
0x18005a8b8  lea     r8, WPP_fac8e1c640d53114d3306e5e667a867e_Traceguids
0x18005a8bf  mov     edx, 11h
0x18005a8c4  mov     r9d, r12d
0x18005a8c7  call    WPP_SF_d
0x18005a8cc  jmp     loc_18005A6FD
0x18005a8d1  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18005a8d8  nop     dword ptr [rax+rax+00h]
0x18005a8dd  cmp     [rbp+TokenInformation], eax
0x18005a8e0  jz      short loc_18005A8EB
0x18005a8e2  mov     [rbp+arg_10], 1
0x18005a8e6  jmp     loc_18005A68E
0x18005a8eb  xor     al, al
0x18005a8ed  mov     [rbp+arg_10], al
0x18005a8f0  jmp     loc_18005A669
```
