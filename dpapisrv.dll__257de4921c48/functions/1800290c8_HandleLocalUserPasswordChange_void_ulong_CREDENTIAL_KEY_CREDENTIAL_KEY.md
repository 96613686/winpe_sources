# HandleLocalUserPasswordChange(void *,ulong,_CREDENTIAL_KEY *,_CREDENTIAL_KEY *)

- ea: `0x1800290c8`
- end: `0x180029553`
- name: `?HandleLocalUserPasswordChange@@YAKPEAXKPEAU_CREDENTIAL_KEY@@1@Z`
- size: `1163`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _CREDENTIAL_KEY *, struct _CREDENTIAL_KEY *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028900`

## callees

- `0x180001184`
- `0x1800011e0`
- `0x180007f10`
- `0x18000c4a0`
- `0x180013a18`
- `0x180013ac0`
- `0x180013f2c`
- `0x18001467c`
- `0x18001d810`
- `0x1800285dc`
- `0x1800290c8`
- `0x180029ed4`
- `0x18002ae48`
- `0x180038234`
- `0x18003c620`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002926c`
- `RPCRT4!UuidCreate` at `0x18002926c`
- `ntdll!RtlNtStatusToDosError` at `0x180029362`
- `ntdll!RtlNtStatusToDosError` at `0x18002940c`
- `ntdll!RtlNtStatusToDosError` at `0x180029362`
- `ntdll!RtlNtStatusToDosError` at `0x18002940c`
- `CRYPTSP!SystemFunction007` at `0x18002934e`
- `CRYPTSP!SystemFunction007` at `0x1800293f8`
- `CRYPTSP!SystemFunction007` at `0x18002934e`
- `CRYPTSP!SystemFunction007` at `0x1800293f8`

## string_xrefs

- `0x1800294a6`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall HandleLocalUserPasswordChange(
        void *a1,
        unsigned int a2,
        struct _CREDENTIAL_KEY *a3,
        struct _CREDENTIAL_KEY *a4)
{
  _DWORD *v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // eax
  unsigned int v12; // ecx
  char *v13; // rcx
  ULONG v14; // edx
  __int64 v15; // r9
  ULONG v16; // edx
  __int64 v17; // rcx
  NTSTATUS v18; // eax
  unsigned int v19; // edi
  ULONG v20; // eax
  unsigned int v21; // ebx
  const char *v22; // rdx
  __int64 v23; // rcx
  unsigned int v24; // eax
  NTSTATUS v25; // eax
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rdx
  _BYTE *v29; // rax
  UUID *v30; // rax
  unsigned int v32; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING v33; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v34; // [rsp+48h] [rbp-B8h] BYREF
  int v35; // [rsp+58h] [rbp-A8h] BYREF
  char v36; // [rsp+5Ch] [rbp-A4h]
  _BYTE v37[16]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v38[4]; // [rsp+70h] [rbp-90h] BYREF
  UUID Buf1[4]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v40[4]; // [rsp+C0h] [rbp-40h] BYREF

  v34 = 0;
  v33 = 0;
  memset(v40, 0, 60);
  memset(Buf1, 0, 60);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 48, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, a2);
  v35 = 0;
  v36 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v35);
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
  {
    if ( v36 && (v38[0] || v38[1] || v38[2] || v38[3]) )
      v8 = v38;
    else
      LODWORD(v8) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (int)&dword_18004C260,
      (int)word_180044AAA,
      (int)v37,
      (int)v8);
  }
  if ( !a3 || !a4 )
  {
    v15 = 2859;
    goto LABEL_53;
  }
  v9 = *((_DWORD *)a3 + 3);
  if ( v9 > 0xFFFF || (v10 = *((_DWORD *)a3 + 2), v10 > *(_DWORD *)a3) || v10 + v9 > *(_DWORD *)a3 )
  {
    v15 = 2870;
    goto LABEL_53;
  }
  v11 = *((_DWORD *)a4 + 3);
  if ( v11 > 0xFFFF || (v12 = *((_DWORD *)a4 + 2), v12 > *(_DWORD *)a4) || v12 + v11 > *(_DWORD *)a4 )
  {
    v15 = 2881;
    goto LABEL_53;
  }
  LODWORD(v40[1]) = *((_DWORD *)a3 + 1);
  Buf1[1].Data1 = *((_DWORD *)a4 + 1);
  v40[0] = *((_OWORD *)a3 + 1);
  Buf1[0] = *((UUID *)a4 + 1);
  if ( !memcmp_0(Buf1, &qword_180042E10, 0x10u) )
  {
    UuidCreate(Buf1);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF__guid_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 49, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, Buf1);
  }
  v13 = (char *)a3 + *((unsigned int *)a3 + 2);
  *((_QWORD *)&v34 + 1) = v13;
  LOWORD(v34) = *((_WORD *)a3 + 6);
  v33.Buffer = (PWSTR)((char *)a4 + *((unsigned int *)a4 + 2));
  v33.Length = *((_WORD *)a4 + 6);
  v14 = *((_DWORD *)a3 + 3);
  if ( (*((_DWORD *)a3 + 1) & 4) != 0 )
  {
    if ( v14 != 40 )
    {
      v15 = 2917;
LABEL_53:
      v17 = 87;
      goto LABEL_54;
    }
    *(_OWORD *)((char *)&v40[1] + 4) = *(_OWORD *)v13;
    DWORD1(v40[2]) = *((_DWORD *)v13 + 4);
    *(_OWORD *)((char *)&v40[2] + 8) = *(_OWORD *)(v13 + 20);
    DWORD2(v40[3]) = *((_DWORD *)v13 + 9);
  }
  else
  {
    if ( !(unsigned int)FMyPrimitiveSHA((PUCHAR)v13, v14, (PUCHAR)&v40[1] + 4) )
    {
      v17 = 13;
      v15 = 2935;
LABEL_54:
      v21 = v17;
      goto LABEL_55;
    }
    v18 = SystemFunction007(&v34, (char *)&v40[2] + 8);
    v19 = v18;
    if ( v18 < 0 )
    {
      v20 = RtlNtStatusToDosError(v18);
      v15 = 2946;
      goto LABEL_37;
    }
  }
  v16 = *((_DWORD *)a4 + 3);
  if ( (*((_DWORD *)a4 + 1) & 4) == 0 )
  {
    if ( !(unsigned int)FMyPrimitiveSHA((PUCHAR)a4 + *((unsigned int *)a4 + 2), v16, (PUCHAR)&Buf1[1].Data2) )
    {
      v17 = 13;
      v15 = 2974;
      goto LABEL_54;
    }
    v25 = SystemFunction007(&v33, Buf1[2].Data4);
    v19 = v25;
    if ( v25 >= 0 )
      goto LABEL_39;
    v20 = RtlNtStatusToDosError(v25);
    v15 = 2986;
LABEL_37:
    v21 = v20;
    v22 = "Status";
    v17 = v19;
LABEL_56:
    DebugTraceError(v17, v22, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v15);
    goto LABEL_57;
  }
  if ( v16 != 40 )
  {
    v15 = 2956;
    goto LABEL_53;
  }
  v23 = *((unsigned int *)a4 + 2);
  *(UUID *)&Buf1[1].Data2 = *(UUID *)((char *)a4 + v23);
  *(_DWORD *)&Buf1[2].Data2 = *(_DWORD *)((char *)a4 + v23 + 16);
  *(UUID *)Buf1[2].Data4 = *(UUID *)((char *)a4 + v23 + 20);
  *(_DWORD *)Buf1[3].Data4 = *(_DWORD *)((char *)a4 + v23 + 36);
LABEL_39:
  v24 = DPAPIChangePassword(a1);
  v21 = v24;
  if ( v24 )
  {
    v15 = 3013;
    v17 = v24;
LABEL_55:
    v22 = "dwStatus";
    goto LABEL_56;
  }
  DPAPISynchronizeMasterKeys(a1, a2, (struct DP_KEK *)v40, (struct DP_KEK *)Buf1);
  v21 = RecoverChangePasswordNotify(a1, (unsigned __int8 *)&v40[1] + 4, &v33);
  if ( v21 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 58, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, v21);
    v21 = 0;
  }
LABEL_57:
  v35 = 2;
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
  {
    v32 = v21;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)&dword_18004C260,
      (int)&dword_180044A74,
      (int)v37,
      v26,
      (__int64)&v32);
  }
  v27 = 60;
  v28 = 60;
  v29 = v40;
  do
  {
    *v29++ = 0;
    --v28;
  }
  while ( v28 );
  v30 = Buf1;
  do
  {
    LOBYTE(v30->Data1) = 0;
    v30 = (UUID *)((char *)v30 + 1);
    --v27;
  }
  while ( v27 );
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v35);
  return v21;
}

```

## disassembly

```asm
0x1800290c8  push    rbp
0x1800290ca  push    rbx
0x1800290cb  push    rsi
0x1800290cc  push    rdi
0x1800290cd  push    r14
0x1800290cf  lea     rbp, [rsp-10h]
0x1800290d4  sub     rsp, 110h
0x1800290db  mov     rax, cs:__security_cookie
0x1800290e2  xor     rax, rsp
0x1800290e5  mov     [rbp+30h+var_30], rax
0x1800290e9  mov     rbx, r9
0x1800290ec  mov     rdi, r8
0x1800290ef  mov     r14d, edx
0x1800290f2  mov     rsi, rcx
0x1800290f5  xorps   xmm0, xmm0
0x1800290f8  movups  [rsp+130h+var_E8], xmm0
0x1800290fd  xorps   xmm1, xmm1
0x180029100  movups  xmmword ptr [rsp+130h+var_F8.Length], xmm1
0x180029105  xor     eax, eax
0x180029107  movups  [rbp+30h+var_70], xmm0
0x18002910b  movups  xmmword ptr [rbp+30h+var_60], xmm0
0x18002910f  movups  [rbp+30h+var_50], xmm0
0x180029113  movups  [rbp+30h+var_50+0Ch], xmm0
0x180029117  movups  [rbp+30h+Buf1], xmm1
0x18002911b  movups  xmmword ptr [rbp+30h+var_A0], xmm1
0x18002911f  movups  [rbp+30h+var_90], xmm1
0x180029123  movups  [rbp+30h+var_90+0Ch], xmm1
0x180029127  lea     rax, WPP_GLOBAL_Control
0x18002912e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029135  cmp     rcx, rax
0x180029138  jz      short loc_180029158
0x18002913a  test    byte ptr [rcx+1Ch], 4
0x18002913e  jz      short loc_180029158
0x180029140  mov     edx, 30h ; '0'
0x180029145  mov     r9d, r14d
0x180029148  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x18002914f  mov     rcx, [rcx+10h]
0x180029153  call    WPP_SF_d
0x180029158  mov     [rsp+130h+var_D8], 0
0x180029160  mov     [rsp+130h+var_D4], 0
0x180029165  lea     rcx, [rsp+130h+var_D8]
0x18002916a  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDpapiTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18002916f  mov     eax, cs:dword_18004C260
0x180029175  cmp     eax, 5
0x180029178  jbe     short loc_1800291D9
0x18002917a  mov     rdx, 400000000000h
0x180029184  lea     rcx, dword_18004C260
0x18002918b  call    _tlgKeywordOn
0x180029190  test    al, al
0x180029192  jz      short loc_1800291D9
0x180029194  cmp     [rsp+130h+var_D4], 0
0x180029199  jz      short loc_1800291BE
0x18002919b  cmp     [rsp+130h+var_C0], 0
0x1800291a0  jnz     short loc_1800291B7
0x1800291a2  cmp     [rsp+130h+var_BC], 0
0x1800291a7  jnz     short loc_1800291B7
0x1800291a9  cmp     [rsp+130h+var_B8], 0
0x1800291ae  jnz     short loc_1800291B7
0x1800291b0  cmp     [rsp+130h+var_B4], 0
0x1800291b5  jz      short loc_1800291BE
0x1800291b7  lea     r9, [rsp+130h+var_C0]
0x1800291bc  jmp     short loc_1800291C1
0x1800291be  xor     r9d, r9d
0x1800291c1  lea     r8, [rsp+130h+var_D0]
0x1800291c6  lea     rdx, word_180044AAA
0x1800291cd  lea     rcx, dword_18004C260
0x1800291d4  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800291d9  test    rdi, rdi
0x1800291dc  jz      loc_180029492
0x1800291e2  test    rbx, rbx
0x1800291e5  jz      loc_180029492
0x1800291eb  mov     eax, [rdi+0Ch]
0x1800291ee  mov     edx, 0FFFFh
0x1800291f3  cmp     eax, edx
0x1800291f5  ja      loc_18002948A
0x1800291fb  mov     ecx, [rdi+8]
0x1800291fe  cmp     ecx, [rdi]
0x180029200  ja      loc_18002948A
0x180029206  add     eax, ecx
0x180029208  cmp     eax, [rdi]
0x18002920a  ja      loc_18002948A
0x180029210  mov     eax, [rbx+0Ch]
0x180029213  cmp     eax, edx
0x180029215  ja      loc_180029482
0x18002921b  mov     ecx, [rbx+8]
0x18002921e  cmp     ecx, [rbx]
0x180029220  ja      loc_180029482
0x180029226  add     eax, ecx
0x180029228  cmp     eax, [rbx]
0x18002922a  ja      loc_180029482
0x180029230  mov     eax, [rdi+4]
0x180029233  mov     dword ptr [rbp+30h+var_60], eax
0x180029236  mov     eax, [rbx+4]
0x180029239  mov     dword ptr [rbp+30h+var_A0], eax
0x18002923c  movups  xmm0, xmmword ptr [rdi+10h]
0x180029240  movdqu  [rbp+30h+var_70], xmm0
0x180029245  movups  xmm1, xmmword ptr [rbx+10h]
0x180029249  movdqu  [rbp+30h+Buf1], xmm1
0x18002924e  mov     r8d, 10h; Size
0x180029254  lea     rdx, qword_180042E10; Buf2
0x18002925b  lea     rcx, [rbp+30h+Buf1]; Buf1
0x18002925f  call    memcmp_0
0x180029264  test    eax, eax
0x180029266  jnz     short loc_1800292AA
0x180029268  lea     rcx, [rbp+30h+Buf1]; Uuid
0x18002926c  call    cs:__imp_UuidCreate
0x180029273  nop     dword ptr [rax+rax+00h]
0x180029278  mov     rcx, cs:WPP_GLOBAL_Control
0x18002927f  lea     rax, WPP_GLOBAL_Control
0x180029286  cmp     rcx, rax
0x180029289  jz      short loc_1800292AA
0x18002928b  test    byte ptr [rcx+1Ch], 4
0x18002928f  jz      short loc_1800292AA
0x180029291  mov     edx, 31h ; '1'
0x180029296  lea     r9, [rbp+30h+Buf1]
0x18002929a  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x1800292a1  mov     rcx, [rcx+10h]
0x1800292a5  call    WPP_SF__guid_
0x1800292aa  mov     ecx, [rdi+8]
0x1800292ad  add     rcx, rdi; pbInput
0x1800292b0  mov     qword ptr [rsp+130h+var_E8+8], rcx
0x1800292b5  movzx   eax, word ptr [rdi+0Ch]
0x1800292b9  mov     word ptr [rsp+130h+var_E8], ax
0x1800292be  mov     eax, [rbx+8]
0x1800292c1  add     rax, rbx
0x1800292c4  mov     [rsp+130h+var_F8.Buffer], rax
0x1800292c9  movzx   eax, word ptr [rbx+0Ch]
0x1800292cd  mov     [rsp+130h+var_F8.Length], ax
0x1800292d2  mov     edx, [rdi+0Ch]; cbInput
0x1800292d5  mov     eax, [rdi+4]
0x1800292d8  test    al, 4
0x1800292da  jz      short loc_180029325
0x1800292dc  cmp     edx, 28h ; '('
0x1800292df  jz      short loc_1800292EC
0x1800292e1  mov     r9d, 0B65h
0x1800292e7  jmp     loc_180029498
0x1800292ec  movups  xmm0, xmmword ptr [rcx]
0x1800292ef  movups  xmmword ptr [rbp+30h+var_60+4], xmm0
0x1800292f3  mov     eax, [rcx+10h]
0x1800292f6  mov     dword ptr [rbp+30h+var_50+4], eax
0x1800292f9  movups  xmm0, xmmword ptr [rcx+14h]
0x1800292fd  movups  [rbp+30h+var_50+8], xmm0
0x180029301  mov     eax, [rcx+24h]
0x180029304  mov     [rbp+30h+var_38], eax
0x180029307  mov     edx, [rbx+0Ch]; cbInput
0x18002930a  mov     eax, [rbx+4]
0x18002930d  test    al, 4
0x18002930f  jz      loc_1800293C9
0x180029315  cmp     edx, 28h ; '('
0x180029318  jz      short loc_180029384
0x18002931a  mov     r9d, 0B8Ch
0x180029320  jmp     loc_180029498
0x180029325  lea     rax, [rbp+30h+var_60+4]
0x180029329  mov     [rsp+130h+var_110], rax; PUCHAR
0x18002932e  call    FMyPrimitiveSHA
0x180029333  test    eax, eax
0x180029335  jnz     short loc_180029345
0x180029337  lea     ecx, [rax+0Dh]
0x18002933a  mov     r9d, 0B77h
0x180029340  jmp     loc_18002949D
0x180029345  lea     rdx, [rbp+30h+var_50+8]
0x180029349  lea     rcx, [rsp+130h+var_E8]
0x18002934e  call    cs:__imp_SystemFunction007
0x180029355  nop     dword ptr [rax+rax+00h]
0x18002935a  mov     edi, eax
0x18002935c  test    eax, eax
0x18002935e  jns     short loc_180029307
0x180029360  mov     ecx, eax; Status
0x180029362  call    cs:__imp_RtlNtStatusToDosError
0x180029369  nop     dword ptr [rax+rax+00h]
0x18002936e  mov     r9d, 0B82h
0x180029374  mov     ebx, eax
0x180029376  lea     rdx, aStatus; "Status"
0x18002937d  mov     ecx, edi
0x18002937f  jmp     loc_1800294A6
0x180029384  mov     ecx, [rbx+8]
0x180029387  movups  xmm0, xmmword ptr [rcx+rbx]
0x18002938b  movups  xmmword ptr [rbp+30h+var_A0+4], xmm0
0x18002938f  mov     eax, [rcx+rbx+10h]
0x180029393  mov     dword ptr [rbp+30h+var_90+4], eax
0x180029396  movups  xmm0, xmmword ptr [rcx+rbx+14h]
0x18002939b  movups  [rbp+30h+var_90+8], xmm0
0x18002939f  mov     eax, [rcx+rbx+24h]
0x1800293a3  mov     [rbp+30h+var_78], eax
0x1800293a6  lea     r8, [rbp+30h+Buf1]
0x1800293aa  lea     rdx, [rbp+30h+var_70]
0x1800293ae  mov     rcx, rsi; hToken
0x1800293b1  call    DPAPIChangePassword
0x1800293b6  mov     ebx, eax
0x1800293b8  test    eax, eax
0x1800293ba  jz      short loc_180029423
0x1800293bc  mov     r9d, 0BC5h
0x1800293c2  mov     ecx, eax
0x1800293c4  jmp     loc_18002949F
0x1800293c9  mov     ecx, [rbx+8]
0x1800293cc  add     rcx, rbx; pbInput
0x1800293cf  lea     rax, [rbp+30h+var_A0+4]
0x1800293d3  mov     [rsp+130h+var_110], rax; PUCHAR
0x1800293d8  call    FMyPrimitiveSHA
0x1800293dd  test    eax, eax
0x1800293df  jnz     short loc_1800293EF
0x1800293e1  lea     ecx, [rax+0Dh]
0x1800293e4  mov     r9d, 0B9Eh
0x1800293ea  jmp     loc_18002949D
0x1800293ef  lea     rdx, [rbp+30h+var_90+8]
0x1800293f3  lea     rcx, [rsp+130h+var_F8]
0x1800293f8  call    cs:__imp_SystemFunction007
0x1800293ff  nop     dword ptr [rax+rax+00h]
0x180029404  mov     edi, eax
0x180029406  test    eax, eax
0x180029408  jns     short loc_1800293A6
0x18002940a  mov     ecx, eax; Status
0x18002940c  call    cs:__imp_RtlNtStatusToDosError
0x180029413  nop     dword ptr [rax+rax+00h]
0x180029418  mov     r9d, 0BAAh
0x18002941e  jmp     loc_180029374
0x180029423  lea     r9, [rbp+30h+Buf1]; struct DP_KEK *
0x180029427  lea     r8, [rbp+30h+var_70]; struct DP_KEK *
0x18002942b  mov     edx, r14d; unsigned int
0x18002942e  mov     rcx, rsi; hToken
0x180029431  call    ?DPAPISynchronizeMasterKeys@@YAXPEAXKPEAUDP_KEK@@1@Z; DPAPISynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *)
0x180029436  lea     r8, [rsp+130h+var_F8]; struct _UNICODE_STRING *
0x18002943b  lea     rdx, [rbp+30h+var_60+4]; unsigned __int8 *
0x18002943f  mov     rcx, rsi; void *
0x180029442  call    RecoverChangePasswordNotify
0x180029447  mov     ebx, eax
0x180029449  test    eax, eax
0x18002944b  jz      short loc_1800294B2
0x18002944d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029454  lea     rax, WPP_GLOBAL_Control
0x18002945b  cmp     rcx, rax
0x18002945e  jz      short loc_18002947E
0x180029460  test    byte ptr [rcx+1Ch], 8
0x180029464  jz      short loc_18002947E
0x180029466  mov     edx, 3Ah ; ':'
0x18002946b  mov     r9d, ebx
0x18002946e  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180029475  mov     rcx, [rcx+10h]
0x180029479  call    WPP_SF_d
0x18002947e  xor     ebx, ebx
0x180029480  jmp     short loc_1800294B2
0x180029482  mov     r9d, 0B41h
0x180029488  jmp     short loc_180029498
0x18002948a  mov     r9d, 0B36h
0x180029490  jmp     short loc_180029498
0x180029492  mov     r9d, 0B2Bh
0x180029498  mov     ecx, 57h ; 'W'
0x18002949d  mov     ebx, ecx
0x18002949f  lea     rdx, aDwstatus; "dwStatus"
0x1800294a6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800294ad  call    DebugTraceError
0x1800294b2  mov     [rsp+130h+var_D8], 2
0x1800294ba  mov     eax, cs:dword_18004C260
0x1800294c0  cmp     eax, 5
0x1800294c3  jbe     short loc_180029505
0x1800294c5  mov     rdx, 400000000000h
0x1800294cf  lea     rcx, dword_18004C260
0x1800294d6  call    _tlgKeywordOn
0x1800294db  test    al, al
0x1800294dd  jz      short loc_180029505
0x1800294df  mov     [rsp+130h+var_100], ebx
0x1800294e3  lea     rax, [rsp+130h+var_100]
0x1800294e8  mov     [rsp+130h+var_110], rax
0x1800294ed  lea     r8, [rsp+130h+var_D0]
0x1800294f2  lea     rdx, dword_180044A74
0x1800294f9  lea     rcx, dword_18004C260
0x180029500  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180029505  mov     ecx, 3Ch ; '<'
0x18002950a  mov     edx, ecx
0x18002950c  lea     rax, [rbp+30h+var_70]
0x180029510  mov     byte ptr [rax], 0
0x180029513  inc     rax
0x180029516  sub     rdx, 1
0x18002951a  jnz     short loc_180029510
0x18002951c  lea     rax, [rbp+30h+Buf1]
0x180029520  mov     byte ptr [rax], 0
0x180029523  inc     rax
0x180029526  sub     rcx, 1
0x18002952a  jnz     short loc_180029520
0x18002952c  lea     rcx, [rsp+130h+var_D8]
0x180029531  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDpapiTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180029536  mov     eax, ebx
0x180029538  mov     rcx, [rbp+30h+var_30]
0x18002953c  xor     rcx, rsp; StackCookie
0x18002953f  call    __security_check_cookie
0x180029544  add     rsp, 110h
0x18002954b  pop     r14
0x18002954d  pop     rdi
0x18002954e  pop     rsi
0x18002954f  pop     rbx
0x180029550  pop     rbp
0x180029551  retn
```
