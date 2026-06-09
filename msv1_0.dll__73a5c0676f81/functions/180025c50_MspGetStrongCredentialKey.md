# MspGetStrongCredentialKey

- ea: `0x180025c50`
- end: `0x180025fdf`
- name: `MspGetStrongCredentialKey`
- size: `911`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, _QWORD *, _DWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011090`
- `0x180012d10`

## callees

- `0x180001580`
- `0x18000dab4`
- `0x18000db30`
- `0x18000dc18`
- `0x18000dc84`
- `0x18000dea0`
- `0x1800144d4`
- `0x18001a278`
- `0x18001eebc`
- `0x180024bd0`
- `0x180025c50`
- `0x18002fb50`
- `0x180030844`
- `0x18006d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180025d43`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180025d43`
- `NtlmShared!MsvpPutClearOwfsInPrimaryCredentialNew` at `0x180025d8d`
- `NtlmShared!MsvpPutClearOwfsInPrimaryCredentialNew` at `0x180025d8d`
- `ntdll!RtlLengthSid` at `0x180025d54`
- `ntdll!RtlLengthSid` at `0x180025d54`
- `SspiCli!LsaGetLogonSessionData` at `0x180025dd9`
- `SspiCli!LsaGetLogonSessionData` at `0x180025dd9`
- `SspiCli!LsaFreeReturnBuffer` at `0x180025f8b`
- `SspiCli!LsaFreeReturnBuffer` at `0x180025f8b`

## pseudocode

```c
__int64 __fastcall MspGetStrongCredentialKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  int ActualCredential; // ebx
  int v11; // ecx
  __int128 v12; // xmm0
  PSID Sid; // rdi
  int v14; // ebx
  int v15; // eax
  unsigned int v16; // esi
  char v17; // al
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  char *v21; // rax
  __int64 v22; // rcx
  struct NtlmCredIsoApi **v23; // rax
  char v25; // [rsp+60h] [rbp-A0h] BYREF
  char v26[3]; // [rsp+61h] [rbp-9Fh] BYREF
  unsigned int v27; // [rsp+64h] [rbp-9Ch] BYREF
  int v28; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+6Ch] [rbp-94h] BYREF
  int v30; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v31; // [rsp+74h] [rbp-8Ch] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+78h] [rbp-88h] BYREF
  _WORD v33[2]; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+84h] [rbp-7Ch]
  __int64 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  void *v37[2]; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int16 v39; // [rsp+B0h] [rbp-50h] BYREF
  char v40[30]; // [rsp+B2h] [rbp-4Eh] BYREF
  struct NtlmCredIsoApi *v41; // [rsp+D0h] [rbp-30h] BYREF
  char v42; // [rsp+D9h] [rbp-27h]
  __int128 v43; // [rsp+F6h] [rbp-Ah]
  _BYTE v44[40]; // [rsp+230h] [rbp+130h] BYREF

  v39 = 0;
  memset_0(v40, 0, 0x17Eu);
  ppLogonSessionData = 0;
  v44[0] = 0;
  v27 = 0;
  v36 = a1;
  v38 = 0;
  *a7 = 0;
  memset(&v44[1], 0, 39);
  *(_OWORD *)v37 = 0;
  if ( a4 < 0x58 )
    goto LABEL_2;
  v11 = *(_DWORD *)(a2 + 4);
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      if ( *(_DWORD *)(a2 + 48) == 3 )
      {
        if ( *(_DWORD *)(a2 + 52) == 16 )
        {
          v12 = *(_OWORD *)*(_QWORD *)(a2 + 56);
          v42 = 1;
          v43 = v12;
          goto LABEL_8;
        }
      }
      else if ( *(_DWORD *)(a2 + 48) == 2 )
      {
        v34 = 0;
        v35 = *(_QWORD *)(a2 + 56);
        v33[0] = *(_WORD *)(a2 + 52);
        v33[1] = v33[0];
        v15 = MsvpPutClearOwfsInPrimaryCredentialNew(v33, 0, &v41);
        ActualCredential = v15;
        if ( v15 < 0 )
        {
          NtlmTraceErrorWithStatusViaWpp(
            "MspGetStrongCredentialKey",
            0x36Bu,
            "MsvpPutClearOwfsInPrimaryCredentialNew",
            v15);
          goto LABEL_27;
        }
LABEL_8:
        Sid = *(PSID *)(a2 + 72);
        v41 = LocalhostNtLmCredIsoObj::IsoObj;
        if ( !IsValidSid(Sid) )
          goto LABEL_2;
        v14 = *(_DWORD *)(a2 + 64);
        if ( RtlLengthSid(Sid) != v14 )
          goto LABEL_2;
        goto LABEL_17;
      }
    }
LABEL_2:
    ActualCredential = -1073741811;
    goto LABEL_27;
  }
  ActualCredential = MspGetActualCredential((struct _LUID *)(a2 + 40), (struct _MSV1_0_PRIMARY_CREDENTIAL *)&v39);
  if ( ActualCredential < 0 )
    goto LABEL_27;
  ActualCredential = LsaGetLogonSessionData((PLUID)(a2 + 40), &ppLogonSessionData);
  if ( ActualCredential < 0 )
    goto LABEL_27;
  Sid = ppLogonSessionData->Sid;
LABEL_17:
  ActualCredential = MspDetermineUserCredentialKeyType(Sid, &v27);
  if ( ActualCredential >= 0 )
  {
    v16 = v27;
    ActualCredential = MspGetCredentialKeyWorker(&v39, Sid, v27, v44);
    if ( ActualCredential >= 0 )
    {
      *a6 = 68;
      ActualCredential = NlpAllocateClientBuffer((__int64)&v36, 68, 0x44u);
      if ( ActualCredential >= 0 )
      {
        memset_0(v37[1], 0, (unsigned int)*a6);
        v21 = (char *)v37[1];
        *(_DWORD *)v37[1] = 21;
        *((_DWORD *)v21 + 5) = 40;
        *(_OWORD *)(v21 + 24) = *(_OWORD *)v44;
        *(_OWORD *)(v21 + 40) = *(_OWORD *)&v44[16];
        *((_QWORD *)v21 + 7) = *(_QWORD *)&v44[32];
        ActualCredential = NlpFlushClientBuffer((__int64)&v36, a5);
      }
    }
    else if ( (unsigned int)dword_1800861D8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800861D8, 0x400000000000LL) )
    {
      if ( v41 )
        v17 = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *))(*(_QWORD *)v41 + 8LL))(v41);
      else
        v17 = 0;
      v25 = v17;
      v26[0] = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj + 16LL))(LocalhostNtLmCredIsoObj::IsoObj);
      v28 = *(_DWORD *)(a2 + 44);
      v29 = *(_DWORD *)(a2 + 40);
      v30 = *(_DWORD *)(a2 + 48);
      v27 = ActualCredential;
      v31 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v18,
        (unsigned int)&word_18007A39E,
        v19,
        v20,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)v26,
        (__int64)&v25);
    }
  }
LABEL_27:
  v22 = 352;
  v23 = &v41;
  do
  {
    *(_BYTE *)v23 = 0;
    v23 = (struct NtlmCredIsoApi **)((char *)v23 + 1);
    --v22;
  }
  while ( v22 );
  if ( ppLogonSessionData )
    LsaFreeReturnBuffer(ppLogonSessionData);
  if ( ActualCredential < 0 )
    NlpFreeClientBuffer(&v36);
  NtlmTraceStatusViaWpp("MspGetStrongCredentialKey", 1016, (unsigned int)ActualCredential);
  return (unsigned int)ActualCredential;
}

```

## disassembly

```asm
0x180025c50  mov     [rsp-8+arg_0], rbx
0x180025c55  mov     [rsp-8+arg_10], rsi
0x180025c5a  push    rbp
0x180025c5b  push    rdi
0x180025c5c  push    r12
0x180025c5e  push    r14
0x180025c60  push    r15
0x180025c62  lea     rbp, [rsp-160h]
0x180025c6a  sub     rsp, 260h
0x180025c71  mov     rax, cs:__security_cookie
0x180025c78  xor     rax, rsp
0x180025c7b  mov     [rbp+180h+var_28], rax
0x180025c82  mov     r12, [rbp+180h+arg_20]
0x180025c89  mov     r14, rdx
0x180025c8c  mov     r15, [rbp+180h+arg_28]
0x180025c93  mov     rbx, rcx
0x180025c96  mov     rdi, [rbp+180h+arg_30]
0x180025c9d  lea     rcx, [rbp+180h+var_1CE]; void *
0x180025ca1  xor     eax, eax
0x180025ca3  xor     edx, edx; Val
0x180025ca5  mov     r8d, 17Eh; Size
0x180025cab  mov     [rbp+180h+var_1D0], ax
0x180025caf  mov     esi, r9d
0x180025cb2  call    memset_0
0x180025cb7  xor     eax, eax
0x180025cb9  mov     [rsp+280h+ppLogonSessionData], 0
0x180025cc2  mov     byte ptr [rbp+180h+var_50], 0
0x180025cc9  xorps   xmm0, xmm0
0x180025ccc  mov     [rsp+280h+var_21C], eax
0x180025cd0  mov     [rbp+180h+var_1F0], rbx
0x180025cd4  mov     [rbp+180h+var_1D8], rax
0x180025cd8  mov     [rdi], eax
0x180025cda  movups  [rbp+180h+var_3F], xmm0
0x180025ce1  mov     qword ptr [rbp+180h+var_3F+0Fh], rax
0x180025ce8  movups  [rbp+180h+var_50+1], xmm0
0x180025cef  movdqu  xmmword ptr [rbp+180h+var_1E8], xmm0
0x180025cf4  cmp     esi, 58h ; 'X'
0x180025cf7  jnb     short loc_180025D03
0x180025cf9  mov     ebx, 0C000000Dh
0x180025cfe  jmp     loc_180025F6C
0x180025d03  mov     ecx, [r14+4]
0x180025d07  test    ecx, ecx
0x180025d09  jz      loc_180025DB9
0x180025d0f  cmp     ecx, 1
0x180025d12  jnz     short loc_180025CF9
0x180025d14  cmp     dword ptr [r14+30h], 3
0x180025d19  jnz     short loc_180025D64
0x180025d1b  cmp     dword ptr [r14+34h], 10h
0x180025d20  jnz     short loc_180025CF9
0x180025d22  mov     rax, [r14+38h]
0x180025d26  movups  xmm0, xmmword ptr [rax]
0x180025d29  mov     [rbp+180h+var_1A7], cl
0x180025d2c  movdqu  [rbp+180h+var_18A], xmm0
0x180025d31  mov     rdi, [r14+48h]
0x180025d35  mov     rax, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x180025d3c  mov     rcx, rdi; pSid
0x180025d3f  mov     [rbp+180h+var_1B0], rax
0x180025d43  call    cs:__imp_IsValidSid
0x180025d49  test    eax, eax
0x180025d4b  jz      short loc_180025CF9
0x180025d4d  mov     ebx, [r14+40h]
0x180025d51  mov     rcx, rdi; Sid
0x180025d54  call    cs:__imp_RtlLengthSid
0x180025d5a  cmp     eax, ebx
0x180025d5c  jz      loc_180025DF2
0x180025d62  jmp     short loc_180025CF9
0x180025d64  cmp     dword ptr [r14+30h], 2
0x180025d69  jnz     short loc_180025CF9
0x180025d6b  mov     [rbp+180h+var_1FC], eax
0x180025d6e  lea     r8, [rbp+180h+var_1B0]
0x180025d72  mov     rax, [r14+38h]
0x180025d76  lea     rcx, [rbp+180h+var_200]
0x180025d7a  mov     [rbp+180h+var_1F8], rax
0x180025d7e  xor     edx, edx
0x180025d80  movzx   eax, word ptr [r14+34h]
0x180025d85  mov     [rbp+180h+var_200], ax
0x180025d89  mov     [rbp+180h+var_1FE], ax
0x180025d8d  call    cs:__imp_MsvpPutClearOwfsInPrimaryCredentialNew
0x180025d93  mov     ebx, eax
0x180025d95  test    eax, eax
0x180025d97  jns     short loc_180025D31
0x180025d99  mov     r9d, eax; int
0x180025d9c  lea     r8, aMsvpputclearow_0; "MsvpPutClearOwfsInPrimaryCredentialNew"
0x180025da3  mov     edx, 36Bh; unsigned int
0x180025da8  lea     rcx, aMspgetstrongcr; "MspGetStrongCredentialKey"
0x180025daf  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x180025db4  jmp     loc_180025F6C
0x180025db9  lea     rdx, [rbp+180h+var_1D0]; struct _MSV1_0_PRIMARY_CREDENTIAL *
0x180025dbd  lea     rcx, [r14+28h]; struct _LUID *
0x180025dc1  call    ?MspGetActualCredential@@YAJPEAU_LUID@@PEAU_MSV1_0_PRIMARY_CREDENTIAL@@@Z; MspGetActualCredential(_LUID *,_MSV1_0_PRIMARY_CREDENTIAL *)
0x180025dc6  mov     ebx, eax
0x180025dc8  test    eax, eax
0x180025dca  js      loc_180025F6C
0x180025dd0  lea     rdx, [rsp+280h+ppLogonSessionData]; ppLogonSessionData
0x180025dd5  lea     rcx, [r14+28h]; LogonId
0x180025dd9  call    cs:__imp_LsaGetLogonSessionData
0x180025ddf  mov     ebx, eax
0x180025de1  test    eax, eax
0x180025de3  js      loc_180025F6C
0x180025de9  mov     rax, [rsp+280h+ppLogonSessionData]
0x180025dee  mov     rdi, [rax+48h]
0x180025df2  lea     rdx, [rsp+280h+var_21C]
0x180025df7  mov     rcx, rdi
0x180025dfa  call    MspDetermineUserCredentialKeyType
0x180025dff  mov     ebx, eax
0x180025e01  test    eax, eax
0x180025e03  js      loc_180025F6C
0x180025e09  mov     esi, [rsp+280h+var_21C]
0x180025e0d  lea     r9, [rbp+180h+var_50]
0x180025e14  mov     r8d, esi
0x180025e17  lea     rcx, [rbp+180h+var_1D0]
0x180025e1b  mov     rdx, rdi
0x180025e1e  call    MspGetCredentialKeyWorker
0x180025e23  mov     ebx, eax
0x180025e25  test    eax, eax
0x180025e27  jns     loc_180025F02
0x180025e2d  mov     eax, cs:dword_1800861D8
0x180025e33  cmp     eax, 5
0x180025e36  jbe     loc_180025F6C
0x180025e3c  mov     rdx, 400000000000h
0x180025e46  lea     rcx, dword_1800861D8
0x180025e4d  call    _tlgKeywordOn
0x180025e52  test    al, al
0x180025e54  jz      loc_180025F6C
0x180025e5a  mov     rcx, [rbp+180h+var_1B0]
0x180025e5e  test    rcx, rcx
0x180025e61  jz      short loc_180025E71
0x180025e63  mov     rax, [rcx]
0x180025e66  mov     rax, [rax+8]
0x180025e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e6f  jmp     short loc_180025E73
0x180025e71  xor     al, al
0x180025e73  mov     rcx, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x180025e7a  mov     [rsp+280h+var_220], al
0x180025e7e  mov     rax, [rcx]
0x180025e81  mov     rax, [rax+10h]
0x180025e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e8a  mov     [rsp+280h+var_21F], al
0x180025e8e  lea     rdx, word_18007A39E
0x180025e95  mov     eax, [r14+2Ch]
0x180025e99  mov     [rsp+280h+var_218], eax
0x180025e9d  mov     eax, [r14+28h]
0x180025ea1  mov     [rsp+280h+var_214], eax
0x180025ea5  mov     eax, [r14+30h]
0x180025ea9  mov     [rsp+280h+var_210], eax
0x180025ead  lea     rax, [rsp+280h+var_220]
0x180025eb2  mov     [rsp+280h+var_230], rax
0x180025eb7  lea     rax, [rsp+280h+var_21F]
0x180025ebc  mov     [rsp+280h+var_238], rax
0x180025ec1  lea     rax, [rsp+280h+var_21C]
0x180025ec6  mov     [rsp+280h+var_240], rax
0x180025ecb  lea     rax, [rsp+280h+var_218]
0x180025ed0  mov     [rsp+280h+var_248], rax
0x180025ed5  lea     rax, [rsp+280h+var_214]
0x180025eda  mov     [rsp+280h+var_250], rax
0x180025edf  lea     rax, [rsp+280h+var_210]
0x180025ee4  mov     [rsp+280h+var_258], rax
0x180025ee9  lea     rax, [rsp+280h+var_20C]
0x180025eee  mov     [rsp+280h+var_260], rax
0x180025ef3  mov     [rsp+280h+var_21C], ebx
0x180025ef7  mov     [rsp+280h+var_20C], esi
0x180025efb  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3333AEBU?$_tlgWrapperByVal@$00@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x180025f00  jmp     short loc_180025F6C
0x180025f02  mov     edx, 44h ; 'D'
0x180025f07  lea     rcx, [rbp+180h+var_1F0]
0x180025f0b  mov     r8d, edx
0x180025f0e  mov     [r15], edx
0x180025f11  call    NlpAllocateClientBuffer
0x180025f16  mov     ebx, eax
0x180025f18  test    eax, eax
0x180025f1a  js      short loc_180025F6C
0x180025f1c  mov     r8d, [r15]; Size
0x180025f1f  xor     edx, edx; Val
0x180025f21  mov     rcx, [rbp+180h+var_1E8+8]; void *
0x180025f25  call    memset_0
0x180025f2a  mov     rax, [rbp+180h+var_1E8+8]
0x180025f2e  lea     rcx, [rbp+180h+var_1F0]
0x180025f32  mov     rdx, r12
0x180025f35  mov     dword ptr [rax], 15h
0x180025f3b  mov     dword ptr [rax+14h], 28h ; '('
0x180025f42  movups  xmm0, [rbp+180h+var_50]
0x180025f49  movups  xmmword ptr [rax+18h], xmm0
0x180025f4d  movups  xmm1, xmmword ptr [rbp+140h]
0x180025f54  movups  xmmword ptr [rax+28h], xmm1
0x180025f58  movsd   xmm0, qword ptr [rbp+180h+var_3F+0Fh]
0x180025f60  movsd   qword ptr [rax+38h], xmm0
0x180025f65  call    NlpFlushClientBuffer
0x180025f6a  mov     ebx, eax
0x180025f6c  mov     ecx, 160h
0x180025f71  lea     rax, [rbp+180h+var_1B0]
0x180025f75  mov     byte ptr [rax], 0
0x180025f78  inc     rax
0x180025f7b  sub     rcx, 1
0x180025f7f  jnz     short loc_180025F75
0x180025f81  mov     rcx, [rsp+280h+ppLogonSessionData]; Buffer
0x180025f86  test    rcx, rcx
0x180025f89  jz      short loc_180025F91
0x180025f8b  call    cs:__imp_LsaFreeReturnBuffer
0x180025f91  test    ebx, ebx
0x180025f93  jns     short loc_180025F9E
0x180025f95  lea     rcx, [rbp+180h+var_1F0]
0x180025f99  call    NlpFreeClientBuffer
0x180025f9e  mov     r8d, ebx
0x180025fa1  lea     rcx, aMspgetstrongcr; "MspGetStrongCredentialKey"
0x180025fa8  mov     edx, 3F8h
0x180025fad  call    NtlmTraceStatusViaWpp
0x180025fb2  mov     eax, ebx
0x180025fb4  mov     rcx, [rbp+180h+var_28]
0x180025fbb  xor     rcx, rsp; StackCookie
0x180025fbe  call    __security_check_cookie
0x180025fc3  lea     r11, [rsp+280h+var_20]
0x180025fcb  mov     rbx, [r11+30h]
0x180025fcf  mov     rsi, [r11+40h]
0x180025fd3  mov     rsp, r11
0x180025fd6  pop     r15
0x180025fd8  pop     r14
0x180025fda  pop     r12
0x180025fdc  pop     rdi
0x180025fdd  pop     rbp
0x180025fde  retn
```
