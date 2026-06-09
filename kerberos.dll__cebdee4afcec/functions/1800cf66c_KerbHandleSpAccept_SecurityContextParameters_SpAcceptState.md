# KerbHandleSpAccept(SecurityContextParameters &,SpAcceptState &)

- ea: `0x1800cf66c`
- end: `0x1800cfc6c`
- name: `?KerbHandleSpAccept@@YAXAEAUSecurityContextParameters@@AEAUSpAcceptState@@@Z`
- size: `1536`
- prototype: `void __fastcall(struct SecurityContextParameters *this, struct SpAcceptState *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800cefe4`

## callees

- `0x180006920`
- `0x180010e90`
- `0x180020e10`
- `0x180045e58`
- `0x1800484f8`
- `0x1800621d0`
- `0x1800744cf`
- `0x180082ef4`
- `0x18008587c`
- `0x18008a8cc`
- `0x18008b70c`
- `0x180092c24`
- `0x1800c22ec`
- `0x1800c2360`
- `0x1800c237c`
- `0x1800c23b4`
- `0x1800cf5b8`
- `0x1800cf66c`
- `0x1800cfd78`

## import_xrefs

- `MSASN1!ASN1intx2int32` at `0x1800cf6c2`
- `MSASN1!ASN1intx2int32` at `0x1800cf6c2`
- `MSASN1!ASN1intx2uint32` at `0x1800cf6ba`
- `MSASN1!ASN1intx2uint32` at `0x1800cf6ba`
- `MSASN1!ASN1intxisuint32` at `0x1800cf6a8`
- `MSASN1!ASN1intxisuint32` at `0x1800cf6a8`

## string_xrefs

- `0x1800cf9dd`: `Output token is too small - sent in %d, needed %d`
- `0x1800cf976`: `Output token missing`
- `0x1800cf861`: `Failed to create token from ticket: 0x%x`
- `0x1800cfbd3`: `Failed to create or update server context: 0x%x`
- `0x1800cf70a`: `AcceptLsaModeContext: Creating token from ticket`
- `0x1800cf8bf`: `SpAcceptLsaModeContext encountered null output token`

## pseudocode

```c
void __fastcall KerbHandleSpAccept(struct SecurityContextParameters *this, struct SpAcceptState *a2)
{
  _BYTE *v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  unsigned int *v8; // r15
  struct _KERB_CONTEXT **v9; // r12
  ULONG TrustLevel; // edi
  bool HasMechList; // al
  union _LARGE_INTEGER *v12; // r8
  __int64 v13; // r9
  struct _UNICODE_STRING *v14; // r10
  struct _UNICODE_STRING *v15; // r11
  int TokenFromTicket; // eax
  const char *v17; // r9
  __int64 v18; // r8
  bool HasOutputToken; // al
  SecurityContextParameters *v20; // rcx
  ULONG *v21; // r15
  void **v22; // rdi
  int v23; // eax
  unsigned int v24; // edx
  int v25; // edx
  ULONG v26; // ebx
  struct _SecBuffer *OutputToken; // rax
  struct _SecBuffer *v28; // rax
  struct _KERB_CONTEXT *v29; // rbx
  struct _SecBuffer *v30; // rax
  struct _SecBuffer *v31; // rax
  void *v32; // rdi
  size_t v33; // rbx
  struct _SecBuffer *v34; // rax
  void *v35; // rbx
  unsigned int v36; // ebx
  unsigned int v37; // edx
  unsigned int v38; // r9d
  unsigned int v39; // r10d
  unsigned int v40; // r11d
  unsigned int v41; // ebx
  struct KERB_AP_REQUEST *v42; // r8
  struct _LUID *v43; // [rsp+20h] [rbp-C8h]
  ULONG v44; // [rsp+F0h] [rbp+8h]

  if ( *((_DWORD *)a2 + 67) != 6 )
    KerbUpdateSkewTime(0);
  v4 = (_BYTE *)*((_QWORD *)a2 + 9);
  if ( v4 && (*v4 & 0x20) != 0 )
  {
    v5 = ASN1intxisuint32(v4 + 104, a2);
    v6 = *((_QWORD *)a2 + 9) + 104LL;
    if ( v5 )
      v7 = ASN1intx2uint32(v6);
    else
      v7 = ASN1intx2int32(v6);
  }
  else
  {
    v7 = 0;
  }
  v8 = (unsigned int *)((char *)a2 + 236);
  *((_DWORD *)a2 + 60) = v7;
  *((_DWORD *)a2 + 59) = v7;
  if ( (*((_DWORD *)this + 16) & 0x400000) != 0 )
    KerbTracerT::Log(1, "KerbHandleSpAccept", 890, "Deprecated flag ASC_REQ_CONTEXT_REPLAY");
  KerbTracerT::Log(14, "KerbHandleSpAccept", 897, "AcceptLsaModeContext: Creating token from ticket");
  v9 = (struct _KERB_CONTEXT **)((char *)a2 + 200);
  TrustLevel = KerbGetTrustLevel(a2);
  HasMechList = SecurityContextParameters::HasMechList(this);
  TokenFromTicket = KerbCreateTokenFromTicketEx(
                      TrustLevel,
                      HasMechList,
                      (struct _UNICODE_STRING **)((char *)a2 + 52),
                      *((struct KERB_AP_REQUEST **)a2 + 4),
                      *((_QWORD *)a2 + 8),
                      *((_QWORD *)a2 + 9),
                      *((_DWORD *)a2 + 56),
                      (__int64)a2 + 160,
                      v15,
                      v14,
                      (struct SpAcceptState *)((char *)a2 + 80),
                      *((_QWORD *)a2 + 25),
                      (LUID *)((char *)a2 + 52),
                      (PSID *)a2 + 32,
                      (HANDLE *)a2 + 27,
                      (const UNICODE_STRING *)a2 + 19,
                      (const UNICODE_STRING *)a2 + 20,
                      (struct _UNICODE_STRING *)a2 + 21,
                      v13,
                      v12);
  *((_DWORD *)a2 + 1) = TokenFromTicket;
  if ( TokenFromTicket == 280 )
  {
    *((_DWORD *)a2 + 66) = 41;
    KerbTracerT::Log(
      2,
      "KerbHandleSpAccept",
      934,
      "SpAcceptLsaModeContext LOOPBACK asking the caller to try with a new ticket");
    *((_DWORD *)a2 + 1) = KerbMapKerbError(*((_DWORD *)a2 + 66));
    KerbReturnErrorMessage(this, a2);
    return;
  }
  if ( TokenFromTicket < 0 )
  {
    v17 = "Failed to create token from ticket: 0x%x";
    v18 = 944;
LABEL_15:
    LODWORD(v43) = TokenFromTicket;
    KerbTracerT::Log(1, "KerbHandleSpAccept", v18, v17, v43);
LABEL_41:
    v25 = *((_DWORD *)a2 + 1);
    goto LABEL_42;
  }
  HasOutputToken = SecurityContextParameters::HasOutputToken(this);
  if ( (*((_DWORD *)a2 + 56) & 0x202) != 0 )
  {
    if ( !HasOutputToken )
    {
      *((_DWORD *)a2 + 1) = -2146893048;
      KerbTracerT::Log(1, "KerbHandleSpAccept", 963, "SpAcceptLsaModeContext encountered null output token");
      goto LABEL_41;
    }
    KerbTracerT::Log(14, "KerbHandleSpAccept", 972, "SpAcceptLsaModeContext: Building AP reply");
    v21 = (ULONG *)((char *)a2 + 48);
    v22 = (void **)((char *)a2 + 40);
    v23 = KerbBuildApReply(
            *((struct KERB_AUTHENTICATOR **)a2 + 9),
            *((struct KERB_AP_REQUEST **)a2 + 4),
            *((_DWORD *)a2 + 56),
            (unsigned int *)a2 + 57,
            (struct SpAcceptState *)((char *)a2 + 120),
            (struct SpAcceptState *)((char *)a2 + 80),
            (unsigned int *)a2 + 59,
            (unsigned __int8 **)a2 + 5,
            (unsigned int *)a2 + 12);
    *((_DWORD *)a2 + 1) = v23;
    if ( v23 < 0 )
    {
      KerbTracerT::Log(1, "KerbHandleSpAccept", 991, "Failed to build AP reply: 0x%x", v23);
      goto LABEL_41;
    }
    if ( !SecurityContextParameters::HasOutputToken(this) )
    {
      KerbTracerT::Log(1, "KerbHandleSpAccept", 998, "Output token missing");
      v25 = -1073741811;
      *((_DWORD *)a2 + 1) = -1073741811;
LABEL_42:
      KerbLogDebugStatus("KerbHandleSpAccept", v25);
      return;
    }
    KerbTelemetry::KerbRecordMaxTokenSize((KerbTelemetry *)*v21, v24);
    if ( (*((_DWORD *)this + 16) & 0x100) != 0 )
    {
      v35 = *v22;
      SecurityContextParameters::GetOutputToken(this)->pvBuffer = v35;
      *v22 = 0;
      **((_DWORD **)this + 12) |= 0x100u;
    }
    else
    {
      v26 = *v21;
      OutputToken = SecurityContextParameters::GetOutputToken(this);
      v44 = *v21;
      if ( OutputToken->cbBuffer < v26 )
      {
        v28 = SecurityContextParameters::GetOutputToken(this);
        KerbTracerT::Log(
          1,
          "KerbHandleSpAccept",
          1016,
          "Output token is too small - sent in %d, needed %d",
          v28->cbBuffer,
          v44);
        v29 = *v9;
        v30 = SecurityContextParameters::GetOutputToken(this);
        KerbReportBufferTooSmallError(*v21, v30->cbBuffer, v29, 0);
        LODWORD(v29) = *v21;
        v31 = SecurityContextParameters::GetOutputToken(this);
        v25 = -1073741789;
        v31->cbBuffer = (unsigned int)v29;
        *((_DWORD *)a2 + 1) = -1073741789;
        goto LABEL_42;
      }
      v32 = *v22;
      v33 = *v21;
      v34 = SecurityContextParameters::GetOutputToken(this);
      memcpy_0(v34->pvBuffer, v32, v33);
    }
    v36 = *v21;
    v8 = (unsigned int *)((char *)a2 + 236);
    SecurityContextParameters::GetOutputToken(this)->cbBuffer = v36;
    goto LABEL_31;
  }
  if ( HasOutputToken )
    SecurityContextParameters::GetOutputToken(v20)->cbBuffer = 0;
LABEL_31:
  if ( (*((_DWORD *)this + 16) & 0x400000) != 0 )
    *((_DWORD *)a2 + 56) |= 0x400000u;
  v37 = *((_DWORD *)a2 + 60);
  v38 = *v8;
  v39 = *((_DWORD *)a2 + 58);
  v40 = *((_DWORD *)a2 + 57);
  v41 = *((_DWORD *)a2 + 56);
  v42 = (struct KERB_AP_REQUEST *)*((_QWORD *)a2 + 4);
  if ( *v9 )
    TokenFromTicket = KerbUpdateServerContext(
                        *v9,
                        *((struct KERB_ENCRYPTED_TICKET **)a2 + 8),
                        v42,
                        (struct SpAcceptState *)((char *)a2 + 80),
                        (struct _LUID *)((char *)a2 + 52),
                        (void **)a2 + 32,
                        v41,
                        v40,
                        v39,
                        v38,
                        v37,
                        (void **)a2 + 27,
                        (PUNICODE_STRING)a2 + 19,
                        (PUNICODE_STRING)a2 + 20,
                        (PUNICODE_STRING)a2 + 21,
                        (union _LARGE_INTEGER *)a2 + 26);
  else
    TokenFromTicket = KerbCreateServerContext(
                        *((struct _KERB_LOGON_SESSION **)a2 + 2),
                        *((struct _KERB_CREDENTIAL **)a2 + 3),
                        *((struct KERB_ENCRYPTED_TICKET **)a2 + 8),
                        v42,
                        (struct SpAcceptState *)((char *)a2 + 80),
                        (struct _LUID *)((char *)a2 + 52),
                        (void **)a2 + 32,
                        v41,
                        v40,
                        v39,
                        v38,
                        v37,
                        (void **)a2 + 27,
                        (struct _UNICODE_STRING *)a2 + 19,
                        (struct _UNICODE_STRING *)a2 + 20,
                        (struct _UNICODE_STRING *)a2 + 21,
                        (struct _KERB_CONTEXT **)a2 + 25,
                        (union _LARGE_INTEGER *)a2 + 26);
  *((_DWORD *)a2 + 1) = TokenFromTicket;
  if ( TokenFromTicket < 0 )
  {
    v17 = "Failed to create or update server context: 0x%x";
    v18 = 1118;
    goto LABEL_15;
  }
  if ( (*((_DWORD *)*v9 + 49) & 0x400) != 0 )
  {
    KerbFreeKey((char *)*v9 + 376);
    if ( (unsigned int)KerbDuplicateAsn1KeyToKey((char *)*v9 + 376, *((_QWORD *)a2 + 9) + 80LL, *((_QWORD *)*v9 + 17)) )
    {
      *((_DWORD *)a2 + 1) = -1073741670;
      KerbTracerT::Log(1, "KerbHandleSpAccept", 1135, "failed to duplicate old session key");
      goto LABEL_41;
    }
  }
}

```

## disassembly

```asm
0x1800cf66c  push    rbx
0x1800cf66e  push    rbp
0x1800cf66f  push    rsi
0x1800cf670  push    rdi
0x1800cf671  push    r12
0x1800cf673  push    r13
0x1800cf675  push    r14
0x1800cf677  push    r15
0x1800cf679  sub     rsp, 0A8h
0x1800cf680  cmp     dword ptr [rdx+10Ch], 6
0x1800cf687  mov     rsi, rdx
0x1800cf68a  mov     rbp, rcx
0x1800cf68d  jz      short loc_1800CF696
0x1800cf68f  xor     ecx, ecx; unsigned __int8
0x1800cf691  call    ?KerbUpdateSkewTime@@YAXE@Z; KerbUpdateSkewTime(uchar)
0x1800cf696  mov     rcx, [rsi+48h]
0x1800cf69a  test    rcx, rcx
0x1800cf69d  jz      short loc_1800CF6CA
0x1800cf69f  test    byte ptr [rcx], 20h
0x1800cf6a2  jz      short loc_1800CF6CA
0x1800cf6a4  add     rcx, 68h ; 'h'
0x1800cf6a8  call    cs:__imp_ASN1intxisuint32
0x1800cf6ae  mov     rcx, [rsi+48h]
0x1800cf6b2  add     rcx, 68h ; 'h'
0x1800cf6b6  test    eax, eax
0x1800cf6b8  jz      short loc_1800CF6C2
0x1800cf6ba  call    cs:__imp_ASN1intx2uint32
0x1800cf6c0  jmp     short loc_1800CF6CC
0x1800cf6c2  call    cs:__imp_ASN1intx2int32
0x1800cf6c8  jmp     short loc_1800CF6CC
0x1800cf6ca  xor     eax, eax
0x1800cf6cc  mov     r14d, 0F0h
0x1800cf6d2  lea     r15, [rsi+0ECh]
0x1800cf6d9  mov     r13, rsi
0x1800cf6dc  mov     [r14+rsi], eax
0x1800cf6e0  mov     [r15], eax
0x1800cf6e3  test    dword ptr [rbp+40h], 400000h
0x1800cf6ea  jz      short loc_1800CF70A
0x1800cf6ec  lea     r9, aDeprecatedFlag; "Deprecated flag ASC_REQ_CONTEXT_REPLAY"
0x1800cf6f3  mov     r8d, 37Ah
0x1800cf6f9  lea     rdx, aKerbhandlespac; "KerbHandleSpAccept"
0x1800cf700  mov     ecx, 1
0x1800cf705  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cf70a  lea     r9, aAcceptlsamodec; "AcceptLsaModeContext: Creating token fr"...
0x1800cf711  mov     r8d, 381h
0x1800cf717  lea     rdx, aKerbhandlespac; "KerbHandleSpAccept"
0x1800cf71e  mov     ecx, 0Eh
0x1800cf723  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cf728  mov     rcx, rsi
0x1800cf72b  call    KerbGetTrustLevel
0x1800cf730  mov     rcx, rbp; this
0x1800cf733  lea     r12, [rsi+0C8h]
0x1800cf73a  mov     edi, eax
0x1800cf73c  lea     r8, [rsi+198h]
0x1800cf743  lea     r9, [rsi+188h]
0x1800cf74a  lea     r10, [rsi+120h]
0x1800cf751  lea     r11, [rsi+110h]
0x1800cf758  lea     rbx, [rsi+0A0h]
0x1800cf75f  call    ?HasMechList@SecurityContextParameters@@QEAA_NXZ; SecurityContextParameters::HasMechList(void)
0x1800cf764  mov     [rsp+0E8h+var_50], r8
0x1800cf76c  lea     rcx, [rsi+34h]
0x1800cf770  mov     [rsp+0E8h+var_58], r9
0x1800cf778  mov     r8, rcx
0x1800cf77b  mov     r9, [rsi+20h]
0x1800cf77f  movzx   edx, al
0x1800cf782  lea     rax, [rsi+150h]
0x1800cf789  mov     [rsp+0E8h+var_60], rax
0x1800cf791  lea     rax, [rsi+140h]
0x1800cf798  mov     [rsp+0E8h+var_68], rax
0x1800cf7a0  lea     rax, [rsi+130h]
0x1800cf7a7  mov     [rsp+0E8h+var_70], rax
0x1800cf7ac  lea     rax, [rsi+0D8h]
0x1800cf7b3  mov     [rsp+0E8h+var_78], rax
0x1800cf7b8  lea     rax, [rsi+100h]
0x1800cf7bf  mov     [rsp+0E8h+var_80], rax
0x1800cf7c4  mov     rax, [r12]
0x1800cf7c8  mov     [rsp+0E8h+DestinationString], rcx
0x1800cf7cd  mov     ecx, edi
0x1800cf7cf  mov     [rsp+0E8h+var_90], rax
0x1800cf7d4  lea     rax, [rsi+50h]
0x1800cf7d8  mov     qword ptr [rsp+0E8h+var_98], rax
0x1800cf7dd  mov     eax, [rsi+0E0h]
0x1800cf7e3  mov     qword ptr [rsp+0E8h+var_A0], r10
0x1800cf7e8  mov     [rsp+0E8h+var_A8], r11
0x1800cf7ed  mov     [rsp+0E8h+var_B0], rbx
0x1800cf7f2  mov     dword ptr [rsp+0E8h+var_B8], eax
0x1800cf7f6  mov     rax, [rsi+48h]
0x1800cf7fa  mov     [rsp+0E8h+var_C0], rax
0x1800cf7ff  mov     rax, [rsi+40h]
0x1800cf803  mov     [rsp+0E8h+var_C8], rax
0x1800cf808  call    ?KerbCreateTokenFromTicketEx@@YAJW4KerbCreateTokenPacTrustLevel@@HPEAU_LUID@@PEAUKERB_AP_REQUEST@@PEAUKERB_ENCRYPTED_TICKET@@PEAUKERB_AUTHENTICATOR@@KPEAU_KERB_ENCRYPTION_KEY@@PEAU_UNICODE_STRING@@65PEAU_KERB_CONTEXT@@1PEAPEAX8666PEAPEAU_S4U_DELEGATION_INFO@@PEAT_LARGE_INTEGER@@@Z; KerbCreateTokenFromTicketEx(KerbCreateTokenPacTrustLevel,int,_LUID *,KERB_AP_REQUEST *,KERB_ENCRYPTED_TICKET *,KERB_AUTHENTICATOR *,ulong,_KERB_ENCRYPTION_KEY *,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_ENCRYPTION_KEY *,_KERB_CONTEXT *,_LUID *,void * *,void * *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_S4U_DELEGATION_INFO * *,_LARGE_INTEGER *)
0x1800cf80d  mov     [rsi+4], eax
0x1800cf810  cmp     eax, 118h
0x1800cf815  jnz     short loc_1800CF85D
0x1800cf817  lea     r9, aSpacceptlsamod_13; "SpAcceptLsaModeContext LOOPBACK asking "...
0x1800cf81e  mov     dword ptr [rsi+108h], 29h ; ')'
0x1800cf828  mov     r8d, 3A6h
0x1800cf82e  lea     rdx, aKerbhandlespac; "KerbHandleSpAccept"
0x1800cf835  mov     ecx, 2
0x1800cf83a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cf83f  mov     ecx, [rsi+108h]; int
0x1800cf845  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x1800cf84a  mov     rdx, rsi; struct SpAcceptState *
0x1800cf84d  mov     [rsi+4], eax
0x1800cf850  mov     rcx, rbp; this
0x1800cf853  call    ?KerbReturnErrorMessage@@YAXAEAUSecurityContextParameters@@AEAUSpAcceptState@@@Z; KerbReturnErrorMessage(SecurityContextParameters &,SpAcceptState &)
0x1800cf858  jmp     loc_1800CFC58
0x1800cf85d  test    eax, eax
0x1800cf85f  jns     short loc_1800CF888
0x1800cf861  lea     r9, aFailedToCreate_38; "Failed to create token from ticket: 0x%"...
0x1800cf868  mov     r8d, 3B0h
0x1800cf86e  lea     rdx, aKerbhandlespac; "KerbHandleSpAccept"
0x1800cf875  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800cf879  mov     ecx, 1
0x1800cf87e  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cf883  jmp     loc_1800CFC49
0x1800cf888  mov     rcx, rbp; this
0x1800cf88b  call    ?HasOutputToken@SecurityContextParameters@@QEAA_NXZ; SecurityContextParameters::HasOutputToken(void)
0x1800cf890  test    dword ptr [rsi+0E0h], 202h
0x1800cf89a  jnz     short loc_1800CF8B4
0x1800cf89c  test    al, al
0x1800cf89e  jz      loc_1800CFA90
0x1800cf8a4  call    ?GetOutputToken@SecurityContextParameters@@QEAAAEAU_SecBuffer@@XZ; SecurityContextParameters::GetOutputToken(void)
0x1800cf8a9  mov     dword ptr [rax], 0
0x1800cf8af  jmp     loc_1800CFA90
0x1800cf8b4  test    al, al
0x1800cf8b6  jnz     short loc_1800CF8D1
0x1800cf8b8  mov     dword ptr [rsi+4], 80090308h
0x1800cf8bf  lea     r9, aSpacceptlsamod_24; "SpAcceptLsaModeContext encountered null"...
0x1800cf8c6  mov     r8d, 3C3h
0x1800cf8cc  jmp     loc_1800CFC38
0x1800cf8d1  lea     rbx, aKerbhandlespac; "KerbHandleSpAccept"
0x1800cf8d8  mov     r8d, 3CCh
0x1800cf8de  mov     rdx, rbx
0x1800cf8e1  lea     r9, aSpacceptlsamod_5; "SpAcceptLsaModeContext: Building AP rep"...
0x1800cf8e8  mov     ecx, 0Eh
0x1800cf8ed  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cf8f2  mov     r8d, [rsi+0E0h]; unsigned int
0x1800cf8f9  lea     rcx, [rsi+0ECh]
0x1800cf900  mov     rdx, [rsi+20h]; struct KERB_AP_REQUEST *
0x1800cf904  lea     rax, [rsi+78h]
0x1800cf908  lea     r15, [rsi+30h]
0x1800cf90c  mov     [rsp+0E8h+var_A8], r15; unsigned int *
0x1800cf911  lea     rdi, [rsi+28h]
0x1800cf915  mov     [rsp+0E8h+var_B0], rdi; unsigned __int8 **
0x1800cf91a  lea     r9, [rsi+0E4h]; unsigned int *
0x1800cf921  mov     [rsp+0E8h+var_B8], rcx; unsigned int *
0x1800cf926  lea     rcx, [rsi+50h]
0x1800cf92a  mov     [rsp+0E8h+var_C0], rcx; struct _KERB_ENCRYPTION_KEY *
0x1800cf92f  mov     rcx, [rsi+48h]; struct KERB_AUTHENTICATOR *
0x1800cf933  mov     [rsp+0E8h+var_C8], rax; struct _KERB_ENCRYPTION_KEY *
0x1800cf938  call    ?KerbBuildApReply@@YAJPEAUKERB_AUTHENTICATOR@@PEAUKERB_AP_REQUEST@@KPEAKPEAU_KERB_ENCRYPTION_KEY@@32PEAPEAE2@Z; KerbBuildApReply(KERB_AUTHENTICATOR *,KERB_AP_REQUEST *,ulong,ulong *,_KERB_ENCRYPTION_KEY *,_KERB_ENCRYPTION_KEY *,ulong *,uchar * *,ulong *)
0x1800cf93d  mov     [rsi+4], eax
0x1800cf940  test    eax, eax
0x1800cf942  jns     short loc_1800CF96A
0x1800cf944  lea     r9, aFailedToBuildA_0; "Failed to build AP reply: 0x%x"
0x1800cf94b  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800cf94f  mov     r8d, 3DFh
0x1800cf955  mov     rdx, rbx
0x1800cf958  mov     ecx, 1
0x1800cf95d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cf962  mov     rcx, rbx
0x1800cf965  jmp     loc_1800CFC50
0x1800cf96a  mov     rcx, rbp; this
0x1800cf96d  call    ?HasOutputToken@SecurityContextParameters@@QEAA_NXZ; SecurityContextParameters::HasOutputToken(void)
0x1800cf972  test    al, al
0x1800cf974  jnz     short loc_1800CF9A0
0x1800cf976  lea     r9, aOutputTokenMis_0; "Output token missing"
0x1800cf97d  mov     r8d, 3E6h
0x1800cf983  mov     rdx, rbx
0x1800cf986  mov     ecx, 1
0x1800cf98b  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cf990  mov     edx, 0C000000Dh
0x1800cf995  mov     rcx, rbx
0x1800cf998  mov     [rsi+4], edx
0x1800cf99b  jmp     loc_1800CFC53
0x1800cf9a0  mov     ecx, [r15]; this
0x1800cf9a3  call    ?KerbRecordMaxTokenSize@KerbTelemetry@@YAXK@Z; KerbTelemetry::KerbRecordMaxTokenSize(ulong)
0x1800cf9a8  test    dword ptr [rbp+40h], 100h
0x1800cf9af  mov     rcx, rbp; this
0x1800cf9b2  jnz     loc_1800CFA61
0x1800cf9b8  mov     ebx, [r15]
0x1800cf9bb  call    ?GetOutputToken@SecurityContextParameters@@QEAAAEAU_SecBuffer@@XZ; SecurityContextParameters::GetOutputToken(void)
0x1800cf9c0  mov     ecx, [r15]
0x1800cf9c3  mov     [rsp+0E8h+arg_0], ecx
0x1800cf9ca  cmp     [rax], ebx
0x1800cf9cc  jnb     short loc_1800CFA42
0x1800cf9ce  mov     rcx, rbp; this
0x1800cf9d1  call    ?GetOutputToken@SecurityContextParameters@@QEAAAEAU_SecBuffer@@XZ; SecurityContextParameters::GetOutputToken(void)
0x1800cf9d6  mov     ecx, [rsp+0E8h+arg_0]
0x1800cf9dd  lea     r9, aOutputTokenIsT; "Output token is too small - sent in %d,"...
0x1800cf9e4  mov     dword ptr [rsp+0E8h+var_C0], ecx
0x1800cf9e8  lea     rdx, aKerbhandlespac; "KerbHandleSpAccept"
0x1800cf9ef  mov     r8d, 3F8h
0x1800cf9f5  mov     ecx, 1
0x1800cf9fa  mov     eax, [rax]
0x1800cf9fc  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800cfa00  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800cfa05  mov     rbx, [r12]
0x1800cfa09  mov     rcx, rbp; this
0x1800cfa0c  call    ?GetOutputToken@SecurityContextParameters@@QEAAAEAU_SecBuffer@@XZ; SecurityContextParameters::GetOutputToken(void)
0x1800cfa11  mov     ecx, [r15]; Value
0x1800cfa14  xor     r9d, r9d; struct _KERB_TICKET_CACHE_ENTRY *
0x1800cfa17  mov     r8, rbx; struct _KERB_CONTEXT *
0x1800cfa1a  mov     edx, [rax]; ULONG
0x1800cfa1c  call    ?KerbReportBufferTooSmallError@@YAXKKPEAU_KERB_CONTEXT@@PEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbReportBufferTooSmallError(ulong,ulong,_KERB_CONTEXT *,_KERB_TICKET_CACHE_ENTRY *)
0x1800cfa21  mov     ebx, [r15]
0x1800cfa24  mov     rcx, rbp; this
0x1800cfa27  call    ?GetOutputToken@SecurityContextParameters@@QEAAAEAU_SecBuffer@@XZ; SecurityContextParameters::GetOutputToken(void)
0x1800cfa2c  mov     edx, 0C0000023h
0x1800cfa31  lea     rcx, aKerbhandlespac; "KerbHandleSpAccept"
0x1800cfa38  mov     [rax], ebx
0x1800cfa3a  mov     [rsi+4], edx
0x1800cfa3d  jmp     loc_1800CFC53
0x1800cfa42  mov     rdi, [rdi]
0x1800cfa45  mov     rbx, rcx
0x1800cfa48  mov     rcx, rbp; this
0x1800cfa4b  call    ?GetOutputToken@SecurityContextParameters@@QEAAAEAU_SecBuffer@@XZ; SecurityContextParameters::GetOutputToken(void)
0x1800cfa50  mov     r8, rbx; Size
0x1800cfa53  mov     rdx, rdi; Src
0x1800cfa56  mov     rcx, [rax+8]; void *
0x1800cfa5a  call    memcpy_0
0x1800cfa5f  jmp     short loc_1800CFA7C
0x1800cfa61  mov     rbx, [rdi]
0x1800cfa64  call    ?GetOutputToken@SecurityContextParameters@@QEAAAEAU_SecBuffer@@XZ; SecurityContextParameters::GetOutputToken(void)
0x1800cfa69  mov     [rax+8], rbx
0x1800cfa6d  mov     qword ptr [rdi], 0
0x1800cfa74  mov     rax, [rbp+60h]
0x1800cfa78  bts     dword ptr [rax], 8
0x1800cfa7c  mov     ebx, [r15]
0x1800cfa7f  mov     rcx, rbp; this
0x1800cfa82  call    ?GetOutputToken@SecurityContextParameters@@QEAAAEAU_SecBuffer@@XZ; SecurityContextParameters::GetOutputToken(void)
0x1800cfa87  lea     r15, [rsi+0ECh]
0x1800cfa8e  mov     [rax], ebx
0x1800cfa90  mov     eax, 400000h
0x1800cfa95  test    [rbp+40h], eax
0x1800cfa98  jz      short loc_1800CFAA0
0x1800cfa9a  or      [rsi+0E0h], eax
0x1800cfaa0  mov     rcx, [r12]; struct _KERB_CONTEXT *
0x1800cfaa4  lea     rax, [rsi+0D0h]
0x1800cfaab  mov     edx, [r14+r13]
0x1800cfaaf  mov     r9d, [r15]
0x1800cfab2  mov     r10d, [rsi+0E8h]
0x1800cfab9  mov     r11d, [rsi+0E4h]
0x1800cfac0  mov     ebx, [rsi+0E0h]
0x1800cfac6  mov     r8, [rsi+20h]; struct KERB_AP_REQUEST *
0x1800cfaca  test    rcx, rcx
0x1800cfacd  jnz     loc_1800CFB5E
0x1800cfad3  mov     rcx, [rsi+10h]; struct _KERB_LOGON_SESSION *
0x1800cfad7  mov     [rsp+0E8h+var_60], rax; union _LARGE_INTEGER *
0x1800cfadf  lea     rax, [rsi+150h]
0x1800cfae6  mov     [rsp+0E8h+var_68], r12; struct _KERB_CONTEXT **
0x1800cfaee  mov     [rsp+0E8h+var_70], rax; struct _UNICODE_STRING *
0x1800cfaf3  lea     rax, [rsi+140h]
0x1800cfafa  mov     [rsp+0E8h+var_78], rax; struct _UNICODE_STRING *
0x1800cfaff  lea     rax, [rsi+130h]
0x1800cfb06  mov     [rsp+0E8h+var_80], rax; struct _UNICODE_STRING *
0x1800cfb0b  lea     rax, [rsi+0D8h]
0x1800cfb12  mov     [rsp+0E8h+DestinationString], rax; void **
0x1800cfb17  lea     rax, [rsi+100h]
0x1800cfb1e  mov     dword ptr [rsp+0E8h+var_90], edx; unsigned int
0x1800cfb22  mov     rdx, [rsi+18h]; struct _KERB_CREDENTIAL *
0x1800cfb26  mov     [rsp+0E8h+var_98], r9d; unsigned int
0x1800cfb2b  mov     r9, r8; struct KERB_AP_REQUEST *
0x1800cfb2e  mov     r8, [rsi+40h]; struct KERB_ENCRYPTED_TICKET *
0x1800cfb32  mov     [rsp+0E8h+var_A0], r10d; unsigned int
0x1800cfb37  mov     dword ptr [rsp+0E8h+var_A8], r11d; unsigned int
0x1800cfb3c  mov     dword ptr [rsp+0E8h+var_B0], ebx; unsigned int
0x1800cfb40  mov     [rsp+0E8h+var_B8], rax; void **
0x1800cfb45  lea     rax, [rsi+34h]
0x1800cfb49  mov     [rsp+0E8h+var_C0], rax; struct _LUID *
0x1800cfb4e  lea     rax, [rsi+50h]
0x1800cfb52  mov     [rsp+0E8h+var_C8], rax; struct _KERB_ENCRYPTION_KEY *
0x1800cfb57  call    ?KerbCreateServerContext@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAUKERB_ENCRYPTED_TICKET@@PEAUKERB_AP_REQUEST@@PEAU_KERB_ENCRYPTION_KEY@@PEAU_LUID@@PEAPEAXKKKKK6PEAU_UNICODE_STRING@@77PEAPEAU_KERB_CONTEXT@@PEAT_LARGE_INTEGER@@@Z; KerbCreateServerContext(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,KERB_ENCRYPTED_TICKET *,KERB_AP_REQUEST *,_KERB_ENCRYPTION_KEY *,_LUID *,void * *,ulong,ulong,ulong,ulong,ulong,void * *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_CONTEXT * *,_LARGE_INTEGER *)
0x1800cfb5c  jmp     short loc_1800CFBCC
0x1800cfb5e  mov     [rsp+0E8h+var_70], rax; union _LARGE_INTEGER *
0x1800cfb63  lea     rax, [rsi+150h]
0x1800cfb6a  mov     [rsp+0E8h+var_78], rax; PUNICODE_STRING
0x1800cfb6f  lea     rax, [rsi+140h]
0x1800cfb76  mov     [rsp+0E8h+var_80], rax; PUNICODE_STRING
0x1800cfb7b  lea     rax, [rsi+130h]
0x1800cfb82  mov     [rsp+0E8h+DestinationString], rax; DestinationString
0x1800cfb87  lea     rax, [rsi+0D8h]
0x1800cfb8e  mov     [rsp+0E8h+var_90], rax; void **
0x1800cfb93  lea     rax, [rsi+100h]
0x1800cfb9a  mov     [rsp+0E8h+var_98], edx; unsigned int
0x1800cfb9e  mov     rdx, [rsi+40h]; struct KERB_ENCRYPTED_TICKET *
0x1800cfba2  mov     [rsp+0E8h+var_A0], r9d; unsigned int
0x1800cfba7  lea     r9, [rsi+50h]; struct _KERB_ENCRYPTION_KEY *
0x1800cfbab  mov     dword ptr [rsp+0E8h+var_A8], r10d; unsigned int
0x1800cfbb0  mov     dword ptr [rsp+0E8h+var_B0], r11d; unsigned int
0x1800cfbb5  mov     dword ptr [rsp+0E8h+var_B8], ebx; unsigned int
0x1800cfbb9  mov     [rsp+0E8h+var_C0], rax; void **
0x1800cfbbe  lea     rax, [rsi+34h]
0x1800cfbc2  mov     [rsp+0E8h+var_C8], rax; struct _LUID *
0x1800cfbc7  call    ?KerbUpdateServerContext@@YAJPEAU_KERB_CONTEXT@@PEAUKERB_ENCRYPTED_TICKET@@PEAUKERB_AP_REQUEST@@PEAU_KERB_ENCRYPTION_KEY@@PEAU_LUID@@PEAPEAXKKKKK5PEAU_UNICODE_STRING@@66PEAT_LARGE_INTEGER@@@Z; KerbUpdateServerContext(_KERB_CONTEXT *,KERB_ENCRYPTED_TICKET *,KERB_AP_REQUEST *,_KERB_ENCRYPTION_KEY *,_LUID *,void * *,ulong,ulong,ulong,ulong,ulong,void * *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_LARGE_INTEGER *)
0x1800cfbcc  mov     [rsi+4], eax
0x1800cfbcf  test    eax, eax
0x1800cfbd1  jns     short loc_1800CFBE5
0x1800cfbd3  lea     r9, aFailedToCreate_8; "Failed to create or update server conte"...
  ... truncated ...
```
