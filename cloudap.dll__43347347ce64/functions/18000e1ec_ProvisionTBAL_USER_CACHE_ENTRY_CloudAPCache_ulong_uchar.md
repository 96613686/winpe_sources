# ProvisionTBAL(_USER_CACHE_ENTRY *,_CloudAPCache *,ulong,uchar *)

- ea: `0x18000e1ec`
- end: `0x18000e7d7`
- name: `?ProvisionTBAL@@YAJPEAU_USER_CACHE_ENTRY@@PEAU_CloudAPCache@@KPEAE@Z`
- size: `1515`
- prototype: `__int64 __fastcall(struct _USER_CACHE_ENTRY *, struct _CloudAPCache *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e990`
- `0x180011960`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000e1ec`
- `0x180024bb0`
- `0x18002d71c`
- `0x180042410`
- `0x180043340`
- `0x18005b110`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e76f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e76f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e761`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e761`
- `bcrypt!BCryptGenRandom` at `0x18000e26c`
- `bcrypt!BCryptGenRandom` at `0x18000e26c`
- `ntdll!RtlInitUnicodeString` at `0x18000e3f5`
- `ntdll!RtlInitUnicodeString` at `0x18000e616`
- `ntdll!RtlInitUnicodeString` at `0x18000e3f5`
- `ntdll!RtlInitUnicodeString` at `0x18000e616`
- `LSASRV!LsarClose` at `0x18000e737`
- `LSASRV!LsarClose` at `0x18000e7af`
- `LSASRV!LsarClose` at `0x18000e737`
- `LSASRV!LsarClose` at `0x18000e7af`
- `LSASRV!LsarSetSecret` at `0x18000e56a`
- `LSASRV!LsarSetSecret` at `0x18000e6d6`
- `LSASRV!LsarSetSecret` at `0x18000e56a`
- `LSASRV!LsarSetSecret` at `0x18000e6d6`
- `LSASRV!LsarCreateSecret` at `0x18000e496`
- `LSASRV!LsarCreateSecret` at `0x18000e686`
- `LSASRV!LsarCreateSecret` at `0x18000e496`
- `LSASRV!LsarCreateSecret` at `0x18000e686`
- `LSASRV!LsarOpenSecret` at `0x18000e40e`
- `LSASRV!LsarOpenSecret` at `0x18000e632`
- `LSASRV!LsarOpenSecret` at `0x18000e40e`
- `LSASRV!LsarOpenSecret` at `0x18000e632`
- `ext-ms-win-cloudap-tbal-l1-1-0!TbalSealBuffer` at `0x18000e50b`
- `ext-ms-win-cloudap-tbal-l1-1-0!TbalSealBuffer` at `0x18000e50b`

## string_xrefs

- `0x18000e282`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18000e320`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18000e391`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18000e419`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18000e336`: `AddCloudAPCacheNode`
- `0x18000e4be`: `LsarCreateSecret`
- `0x18000e6a3`: `LsarCreateSecret`

## pseudocode

```c
__int64 __fastcall ProvisionTBAL(struct _USER_CACHE_ENTRY *a1, struct _CloudAPCache *a2, int a3, unsigned __int8 *a4)
{
  PCWSTR v6; // r12
  unsigned int LSASecretName; // edi
  const char *v8; // rbx
  const char *v9; // rax
  bool v10; // zf
  const char *v11; // rax
  const char *v12; // rbx
  const char *v13; // rax
  bool v14; // zf
  __int64 v15; // rdx
  unsigned __int64 v16; // r8
  const char *v17; // rbx
  const char *v18; // r9
  const char *v19; // rax
  bool v20; // zf
  const char *v21; // rax
  bool v22; // zf
  const char *v23; // r9
  char v24; // bl
  const char *v25; // r9
  void *v26; // rax
  unsigned int v27; // eax
  const char *v28; // rax
  __int64 v29; // r8
  unsigned __int16 v30; // bx
  const char *v31; // rax
  const char *v32; // r9
  __int64 v33; // r8
  unsigned int v34; // eax
  const char *v35; // r9
  __int64 v36; // r8
  _BYTE *v37; // rbx
  __int64 v38; // rax
  HANDLE ProcessHeap; // rax
  UCHAR *v40; // rax
  __int64 v41; // rcx
  __int64 v43; // [rsp+20h] [rbp-E0h]
  __int64 v44; // [rsp+20h] [rbp-E0h]
  const char *Source; // [rsp+28h] [rbp-D8h]
  unsigned int v46; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR v47; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  int v51; // [rsp+78h] [rbp-88h]
  PCWSTR SourceString; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 *v53; // [rsp+88h] [rbp-78h]
  __int128 v54; // [rsp+90h] [rbp-70h] BYREF
  __int128 v55; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v57; // [rsp+C0h] [rbp-40h] BYREF
  UCHAR pbBuffer[96]; // [rsp+D0h] [rbp-30h] BYREF

  v53 = a4;
  v51 = a3;
  v46 = 96;
  lpMem = 0;
  v48 = 0;
  SourceString = 0;
  v49 = 0;
  v47 = 0;
  DestinationString = 0;
  v6 = 0;
  v54 = 0;
  v57 = 0;
  v55 = 0;
  LSASecretName = BCryptGenRandom(0, pbBuffer, 0x60u, 2u);
  if ( !LSASecretName )
  {
    LSASecretName = AddCloudAPCacheNode(
                      a2,
                      0,
                      3u,
                      pbBuffer,
                      0x60u,
                      *((struct _CREDENTIAL_KEY **)a1 + 33),
                      (struct _USER_CACHE_ENTRY *)((char *)a1 + 280),
                      0,
                      0);
    if ( LSASecretName )
    {
      v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      LODWORD(v43) = 158;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v11, v43, "AddCloudAPCacheNode", &Class);
      goto LABEL_55;
    }
    LSASecretName = GetLSASecretName(
                      (UUID *)((char *)a1 + 248),
                      *((const unsigned __int16 **)a1 + 12),
                      (unsigned __int16 **)&SourceString,
                      0,
                      0);
    if ( LSASecretName )
    {
      v12 = "";
      while ( 1 )
      {
        v13 = v12--;
        v14 = *v12 == 92;
        if ( *v12 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp" )
        {
          v14 = *v12 == 92;
          break;
        }
      }
      if ( v14 )
        v12 = v13;
      LODWORD(v44) = 165;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v12, v44, "GetLSASecretName", &Class);
      goto LABEL_19;
    }
    RtlInitUnicodeString(&DestinationString, SourceString);
    if ( (unsigned int)LsarOpenSecret(g_LsaPolicyHandle, &DestinationString, 3, &v48) == -1073741772 )
    {
      v17 = "";
      v18 = "";
      while ( 1 )
      {
        v19 = v18--;
        v20 = *v18 == 92;
        if ( *v18 == 92 )
          break;
        if ( v18 <= "onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp" )
        {
          v20 = *v18 == 92;
          break;
        }
      }
      if ( v20 )
        v18 = v19;
      LODWORD(v44) = 177;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225524LL, v18, v44, "TBAL secret not found", &Class);
      LSASecretName = LsarCreateSecret(g_LsaPolicyHandle, &DestinationString, 983043, &v48);
      if ( LSASecretName )
      {
        while ( 1 )
        {
          v21 = v17--;
          v22 = *v17 == 92;
          if ( *v17 == 92 )
            break;
          if ( v17 <= "onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp" )
          {
            v22 = *v17 == 92;
            break;
          }
        }
        if ( v22 )
          v17 = v21;
        v23 = v17;
        Source = "LsarCreateSecret";
        LODWORD(v44) = 184;
LABEL_34:
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v23, v44, Source, &Class);
LABEL_19:
        v6 = v47;
        goto LABEL_53;
      }
      v6 = v47;
    }
    v24 = 0;
    if ( (unsigned __int8)IsTbalSealBufferPresent() )
    {
      if ( !IsHyperVGuestOS() )
      {
        v24 = 1;
        LSASecretName = TbalSealBuffer(pbBuffer, 96, &lpMem, &v46);
        if ( LSASecretName )
        {
          v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
          LODWORD(v44) = 193;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v25, v44, "TbalSealBuffer", &Class);
LABEL_53:
          if ( SourceString )
            ((void (__fastcall *)(PCWSTR, __int64, unsigned __int64))g_pLsaFunctionTable->FreeLsaHeap)(
              SourceString,
              v15,
              v16);
          goto LABEL_55;
        }
      }
    }
    DWORD1(v54) = (unsigned __int16)v46;
    LODWORD(v54) = (unsigned __int16)v46;
    v26 = pbBuffer;
    if ( v24 )
      v26 = lpMem;
    *((_QWORD *)&v54 + 1) = v26;
    v27 = LsarSetSecret(v48, &v54, 0);
    v16 = (unsigned __int64)"LsarSetSecret";
    LSASecretName = v27;
    if ( v27 )
    {
      v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      LODWORD(v44) = 202;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v28, v44, v29, &Class);
    }
    v30 = v51;
    if ( !v51 || !v53 )
      goto LABEL_53;
    LSASecretName = GetLSASecretName(
                      (UUID *)((char *)a1 + 248),
                      *((const unsigned __int16 **)a1 + 12),
                      (unsigned __int16 **)&v47,
                      1,
                      0);
    if ( !LSASecretName )
    {
      v6 = v47;
      RtlInitUnicodeString(&v57, v47);
      if ( (unsigned int)LsarOpenSecret(g_LsaPolicyHandle, &v57, 3, &v49) == -1073741772
        && (v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp"),
            LODWORD(v44) = 227,
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 0, v31, v44, "Tgt TBAL secret not found", &Class),
            (unsigned int)LsarCreateSecret(g_LsaPolicyHandle, &v57, 983043, &v49)) )
      {
        v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        LODWORD(v44) = 233;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v33, v32, v44, "LsarCreateSecret", &Class);
      }
      else
      {
        DWORD1(v55) = v30;
        LODWORD(v55) = v30;
        *((_QWORD *)&v55 + 1) = v53;
        v34 = LsarSetSecret(v49, &v55, 0);
        v16 = v34;
        if ( v34 )
        {
          v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
          LODWORD(v44) = 241;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v36, v35, v44, "LsarSetSecret", &Class);
        }
      }
      goto LABEL_53;
    }
    v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
    Source = "GetLSASecretName for TGT";
    LODWORD(v44) = 215;
    goto LABEL_34;
  }
  v8 = "";
  while ( 1 )
  {
    v9 = v8--;
    v10 = *v8 == 92;
    if ( *v8 == 92 )
      break;
    if ( v8 <= "onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp" )
    {
      v10 = *v8 == 92;
      break;
    }
  }
  if ( v10 )
    v8 = v9;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v8, 146, "BCryptGenRandom", &Class);
  v6 = v47;
LABEL_55:
  if ( v48 )
    LsarClose(&v48);
  v37 = lpMem;
  if ( lpMem )
  {
    v38 = v46;
    if ( v46 )
    {
      do
      {
        *v37++ = 0;
        --v38;
      }
      while ( v38 );
      v37 = lpMem;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v37);
  }
  v40 = pbBuffer;
  v41 = 96;
  do
  {
    *v40++ = 0;
    --v41;
  }
  while ( v41 );
  if ( v6 )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v6);
  if ( v49 )
    LsarClose(&v49);
  return LSASecretName;
}

```

## disassembly

```asm
0x18000e1ec  push    rbp
0x18000e1ee  push    rbx
0x18000e1ef  push    rsi
0x18000e1f0  push    rdi
0x18000e1f1  push    r12
0x18000e1f3  push    r13
0x18000e1f5  push    r14
0x18000e1f7  push    r15
0x18000e1f9  lea     rbp, [rsp-48h]
0x18000e1fe  sub     rsp, 148h
0x18000e205  mov     rax, cs:__security_cookie
0x18000e20c  xor     rax, rsp
0x18000e20f  mov     [rbp+80h+var_50], rax
0x18000e213  xor     r14d, r14d
0x18000e216  mov     [rbp+80h+var_F8], r9
0x18000e21a  mov     ebx, 60h ; '`'
0x18000e21f  mov     [rsp+180h+var_108], r8d
0x18000e224  xorps   xmm0, xmm0
0x18000e227  mov     [rsp+180h+var_130], ebx
0x18000e22b  xorps   xmm1, xmm1
0x18000e22e  mov     [rsp+180h+lpMem], r14
0x18000e233  mov     rsi, rdx
0x18000e236  mov     [rsp+180h+var_120], r14
0x18000e23b  mov     r13, rcx
0x18000e23e  mov     [rbp+80h+SourceString], r14
0x18000e242  lea     r9d, [rbx-5Eh]; dwFlags
0x18000e246  mov     [rsp+180h+var_118], r14
0x18000e24b  mov     r8d, ebx; cbBuffer
0x18000e24e  mov     [rsp+180h+var_128], r14
0x18000e253  lea     rdx, [rbp+80h+pbBuffer]; pbBuffer
0x18000e257  xor     ecx, ecx; hAlgorithm
0x18000e259  movups  xmmword ptr [rbp+80h+DestinationString.Length], xmm0
0x18000e25d  mov     r12d, r14d
0x18000e260  movups  [rbp+80h+var_F0], xmm1
0x18000e264  movups  xmmword ptr [rbp+80h+var_C0.Length], xmm0
0x18000e268  movups  [rbp+80h+var_E0], xmm1
0x18000e26c  call    cs:__imp_BCryptGenRandom
0x18000e272  mov     edi, eax
0x18000e274  test    eax, eax
0x18000e276  jz      short loc_18000E2DE
0x18000e278  lea     rbx, aOnecoreDsExtCl_8+23h; ""
0x18000e27f  mov     r12b, 5Ch ; '\'
0x18000e282  lea     rsi, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18000e289  mov     rax, rbx
0x18000e28c  dec     rbx
0x18000e28f  cmp     [rbx], r12b
0x18000e292  jz      short loc_18000E29C
0x18000e294  cmp     rbx, rsi
0x18000e297  ja      short loc_18000E289
0x18000e299  cmp     [rbx], r12b
0x18000e29c  cmovz   rbx, rax
0x18000e2a0  lea     r15, Class
0x18000e2a7  lea     rax, aBcryptgenrando; "BCryptGenRandom"
0x18000e2ae  mov     [rsp+180h+var_150], r15
0x18000e2b3  mov     [rsp+180h+Source], rax
0x18000e2b8  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000e2bf  mov     r9, rbx
0x18000e2c2  mov     dword ptr [rsp+180h+var_160], 92h
0x18000e2ca  mov     r8d, edi
0x18000e2cd  xor     ecx, ecx
0x18000e2cf  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000e2d4  mov     r12, [rsp+180h+var_128]
0x18000e2d9  jmp     loc_18000E72A
0x18000e2de  mov     [rsp+180h+var_140], r14; struct _tagCacheNodeIdentifier *
0x18000e2e3  lea     rax, [r13+118h]
0x18000e2ea  mov     [rsp+180h+var_148], r14; struct _SCARD_PIN *
0x18000e2ef  lea     r9, [rbp+80h+pbBuffer]; unsigned __int8 *
0x18000e2f3  mov     [rsp+180h+var_150], rax; struct _AP_BLOB *
0x18000e2f8  xor     edx, edx; unsigned int
0x18000e2fa  mov     rax, [r13+108h]
0x18000e301  mov     rcx, rsi; struct _CloudAPCache *
0x18000e304  mov     [rsp+180h+Source], rax; Source
0x18000e309  mov     dword ptr [rsp+180h+var_160], ebx; unsigned int
0x18000e30d  mov     ebx, 3
0x18000e312  mov     r8d, ebx; unsigned int
0x18000e315  call    ?AddCloudAPCacheNode@@YAJPEAU_CloudAPCache@@KKPEAEKPEAU_CREDENTIAL_KEY@@PEAU_AP_BLOB@@PEAU_SCARD_PIN@@PEAU_tagCacheNodeIdentifier@@@Z; AddCloudAPCacheNode(_CloudAPCache *,ulong,ulong,uchar *,ulong,_CREDENTIAL_KEY *,_AP_BLOB *,_SCARD_PIN *,_tagCacheNodeIdentifier *)
0x18000e31a  mov     edi, eax
0x18000e31c  test    eax, eax
0x18000e31e  jz      short loc_18000E365
0x18000e320  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18000e327  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e32c  mov     r9, rax
0x18000e32f  lea     r15, Class
0x18000e336  lea     rax, aAddcloudapcach; "AddCloudAPCacheNode"
0x18000e33d  mov     [rsp+180h+var_150], r15
0x18000e342  mov     [rsp+180h+Source], rax
0x18000e347  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000e34e  mov     r8d, edi
0x18000e351  mov     dword ptr [rsp+180h+var_160], 9Eh
0x18000e359  xor     ecx, ecx
0x18000e35b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000e360  jmp     loc_18000E72A
0x18000e365  mov     rdx, [r13+60h]; unsigned __int16 *
0x18000e369  lea     rcx, [r13+0F8h]; Uuid
0x18000e370  xor     r9d, r9d; bool
0x18000e373  mov     [rsp+180h+var_160], r14b; bool
0x18000e378  lea     r8, [rbp+80h+SourceString]; unsigned __int16 **
0x18000e37c  call    ?GetLSASecretName@@YAJPEBU_GUID@@PEBGPEAPEAG_N3@Z; GetLSASecretName(_GUID const *,ushort const *,ushort * *,bool,bool)
0x18000e381  mov     edi, eax
0x18000e383  test    eax, eax
0x18000e385  jz      short loc_18000E3ED
0x18000e387  lea     rbx, aOnecoreDsExtCl_8+23h; ""
0x18000e38e  mov     r12b, 5Ch ; '\'
0x18000e391  lea     rsi, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18000e398  mov     rax, rbx
0x18000e39b  dec     rbx
0x18000e39e  cmp     [rbx], r12b
0x18000e3a1  jz      short loc_18000E3AB
0x18000e3a3  cmp     rbx, rsi
0x18000e3a6  ja      short loc_18000E398
0x18000e3a8  cmp     [rbx], r12b
0x18000e3ab  cmovz   rbx, rax
0x18000e3af  lea     r15, Class
0x18000e3b6  mov     [rsp+180h+var_150], r15
0x18000e3bb  lea     rax, aGetlsasecretna; "GetLSASecretName"
0x18000e3c2  mov     [rsp+180h+Source], rax
0x18000e3c7  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000e3ce  mov     dword ptr [rsp+180h+var_160], 0A5h
0x18000e3d6  mov     r9, rbx
0x18000e3d9  mov     r8d, edi
0x18000e3dc  xor     ecx, ecx
0x18000e3de  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000e3e3  mov     r12, [rsp+180h+var_128]
0x18000e3e8  jmp     loc_18000E711
0x18000e3ed  mov     rdx, [rbp+80h+SourceString]; SourceString
0x18000e3f1  lea     rcx, [rbp+80h+DestinationString]; DestinationString
0x18000e3f5  call    cs:__imp_RtlInitUnicodeString
0x18000e3fb  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18000e402  lea     r9, [rsp+180h+var_120]
0x18000e407  mov     r8d, ebx
0x18000e40a  lea     rdx, [rbp+80h+DestinationString]
0x18000e40e  call    cs:__imp_LsarOpenSecret
0x18000e414  mov     ecx, 0C0000034h
0x18000e419  lea     rsi, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18000e420  lea     r15, Class
0x18000e427  lea     r14, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000e42e  cmp     eax, ecx
0x18000e430  jnz     loc_18000E4E2
0x18000e436  lea     rbx, aOnecoreDsExtCl_8+23h; ""
0x18000e43d  mov     r12b, 5Ch ; '\'
0x18000e440  mov     r9, rbx
0x18000e443  mov     rax, r9
0x18000e446  dec     r9
0x18000e449  cmp     [r9], r12b
0x18000e44c  jz      short loc_18000E456
0x18000e44e  cmp     r9, rsi
0x18000e451  ja      short loc_18000E443
0x18000e453  cmp     [r9], r12b
0x18000e456  cmovz   r9, rax
0x18000e45a  mov     [rsp+180h+var_150], r15
0x18000e45f  lea     rax, aTbalSecretNotF; "TBAL secret not found"
0x18000e466  mov     r8d, ecx
0x18000e469  mov     [rsp+180h+Source], rax
0x18000e46e  mov     rdx, r14
0x18000e471  xor     ecx, ecx
0x18000e473  mov     dword ptr [rsp+180h+var_160], 0B1h
0x18000e47b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000e480  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18000e487  lea     r9, [rsp+180h+var_120]
0x18000e48c  mov     r8d, 0F0003h
0x18000e492  lea     rdx, [rbp+80h+DestinationString]
0x18000e496  call    cs:__imp_LsarCreateSecret
0x18000e49c  mov     edi, eax
0x18000e49e  test    eax, eax
0x18000e4a0  jz      short loc_18000E4DD
0x18000e4a2  mov     rax, rbx
0x18000e4a5  dec     rbx
0x18000e4a8  cmp     [rbx], r12b
0x18000e4ab  jz      short loc_18000E4B5
0x18000e4ad  cmp     rbx, rsi
0x18000e4b0  ja      short loc_18000E4A2
0x18000e4b2  cmp     [rbx], r12b
0x18000e4b5  cmovz   rbx, rax
0x18000e4b9  mov     [rsp+180h+var_150], r15
0x18000e4be  lea     rax, aLsarcreatesecr; "LsarCreateSecret"
0x18000e4c5  mov     r9, rbx
0x18000e4c8  mov     [rsp+180h+Source], rax
0x18000e4cd  mov     dword ptr [rsp+180h+var_160], 0B8h
0x18000e4d5  mov     rdx, r14
0x18000e4d8  jmp     loc_18000E3D9
0x18000e4dd  mov     r12, [rsp+180h+var_128]
0x18000e4e2  xor     bl, bl
0x18000e4e4  call    IsTbalSealBufferPresent
0x18000e4e9  test    al, al
0x18000e4eb  jz      short loc_18000E543
0x18000e4ed  call    ?IsHyperVGuestOS@@YA_NXZ; IsHyperVGuestOS(void)
0x18000e4f2  test    al, al
0x18000e4f4  jnz     short loc_18000E543
0x18000e4f6  lea     r9, [rsp+180h+var_130]
0x18000e4fb  mov     edx, 60h ; '`'
0x18000e500  lea     r8, [rsp+180h+lpMem]
0x18000e505  mov     bl, 1
0x18000e507  lea     rcx, [rbp+80h+pbBuffer]
0x18000e50b  call    cs:__imp_TbalSealBuffer
0x18000e511  mov     edi, eax
0x18000e513  test    eax, eax
0x18000e515  jz      short loc_18000E543
0x18000e517  mov     rcx, rsi; char *
0x18000e51a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e51f  mov     [rsp+180h+var_150], r15
0x18000e524  mov     r9, rax
0x18000e527  lea     rax, aTbalsealbuffer_0; "TbalSealBuffer"
0x18000e52e  mov     r8d, edi
0x18000e531  mov     [rsp+180h+Source], rax
0x18000e536  mov     dword ptr [rsp+180h+var_160], 0C1h
0x18000e53e  jmp     loc_18000E707
0x18000e543  movzx   eax, word ptr [rsp+180h+var_130]
0x18000e548  lea     rdx, [rbp+80h+var_F0]
0x18000e54c  mov     rcx, [rsp+180h+var_120]
0x18000e551  test    bl, bl
0x18000e553  mov     dword ptr [rbp+80h+var_F0+4], eax
0x18000e556  mov     dword ptr [rbp+80h+var_F0], eax
0x18000e559  lea     rax, [rbp+80h+pbBuffer]
0x18000e55d  cmovnz  rax, [rsp+180h+lpMem]
0x18000e563  xor     r8d, r8d
0x18000e566  mov     qword ptr [rbp+80h+var_F0+8], rax
0x18000e56a  call    cs:__imp_LsarSetSecret
0x18000e570  lea     r8, aLsarsetsecret; "LsarSetSecret"
0x18000e577  mov     edi, eax
0x18000e579  test    eax, eax
0x18000e57b  jz      short loc_18000E5A7
0x18000e57d  mov     rcx, rsi; char *
0x18000e580  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e585  mov     [rsp+180h+var_150], r15
0x18000e58a  mov     r9, rax
0x18000e58d  mov     [rsp+180h+Source], r8
0x18000e592  mov     rdx, r14
0x18000e595  mov     r8d, edi
0x18000e598  mov     dword ptr [rsp+180h+var_160], 0CAh
0x18000e5a0  xor     ecx, ecx
0x18000e5a2  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000e5a7  mov     ebx, [rsp+180h+var_108]
0x18000e5ab  test    ebx, ebx
0x18000e5ad  jz      loc_18000E711
0x18000e5b3  cmp     [rbp+80h+var_F8], 0
0x18000e5b8  jz      loc_18000E711
0x18000e5be  mov     rdx, [r13+60h]; unsigned __int16 *
0x18000e5c2  lea     r8, [rsp+180h+var_128]; unsigned __int16 **
0x18000e5c7  mov     r9b, 1; bool
0x18000e5ca  mov     [rsp+180h+var_160], 0; bool
0x18000e5cf  lea     rcx, [r13+0F8h]; Uuid
0x18000e5d6  call    ?GetLSASecretName@@YAJPEBU_GUID@@PEBGPEAPEAG_N3@Z; GetLSASecretName(_GUID const *,ushort const *,ushort * *,bool,bool)
0x18000e5db  mov     edi, eax
0x18000e5dd  test    eax, eax
0x18000e5df  jz      short loc_18000E60A
0x18000e5e1  mov     rcx, rsi; char *
0x18000e5e4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e5e9  mov     [rsp+180h+var_150], r15
0x18000e5ee  mov     r9, rax
0x18000e5f1  lea     rax, aGetlsasecretna_0; "GetLSASecretName for TGT"
0x18000e5f8  mov     [rsp+180h+Source], rax
0x18000e5fd  mov     dword ptr [rsp+180h+var_160], 0D7h
0x18000e605  jmp     loc_18000E4D5
0x18000e60a  mov     r12, [rsp+180h+var_128]
0x18000e60f  lea     rcx, [rbp+80h+var_C0]; DestinationString
0x18000e613  mov     rdx, r12; SourceString
0x18000e616  call    cs:__imp_RtlInitUnicodeString
0x18000e61c  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18000e623  lea     r9, [rsp+180h+var_118]
0x18000e628  mov     r8d, 3
0x18000e62e  lea     rdx, [rbp+80h+var_C0]
0x18000e632  call    cs:__imp_LsarOpenSecret
0x18000e638  cmp     eax, 0C0000034h
0x18000e63d  jnz     short loc_18000E6B9
0x18000e63f  mov     rcx, rsi; char *
0x18000e642  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e647  mov     r9, rax
0x18000e64a  mov     [rsp+180h+var_150], r15
0x18000e64f  lea     rax, aTgtTbalSecretN; "Tgt TBAL secret not found"
0x18000e656  xor     r8d, r8d
0x18000e659  mov     [rsp+180h+Source], rax
0x18000e65e  mov     rdx, r14
0x18000e661  xor     ecx, ecx
0x18000e663  mov     dword ptr [rsp+180h+var_160], 0E3h
0x18000e66b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000e670  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18000e677  lea     r9, [rsp+180h+var_118]
0x18000e67c  mov     r8d, 0F0003h
0x18000e682  lea     rdx, [rbp+80h+var_C0]
0x18000e686  call    cs:__imp_LsarCreateSecret
0x18000e68c  mov     r8d, eax
0x18000e68f  test    eax, eax
0x18000e691  jz      short loc_18000E6B9
0x18000e693  mov     rcx, rsi; char *
0x18000e696  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e69b  mov     [rsp+180h+var_150], r15
0x18000e6a0  mov     r9, rax
0x18000e6a3  lea     rax, aLsarcreatesecr; "LsarCreateSecret"
0x18000e6aa  mov     [rsp+180h+Source], rax
0x18000e6af  mov     dword ptr [rsp+180h+var_160], 0E9h
0x18000e6b7  jmp     short loc_18000E707
0x18000e6b9  mov     rcx, [rsp+180h+var_118]
0x18000e6be  lea     rdx, [rbp+80h+var_E0]
0x18000e6c2  movzx   eax, bx
0x18000e6c5  xor     r8d, r8d
0x18000e6c8  mov     dword ptr [rbp+80h+var_E0+4], eax
0x18000e6cb  mov     dword ptr [rbp+80h+var_E0], eax
0x18000e6ce  mov     rax, [rbp+80h+var_F8]
0x18000e6d2  mov     qword ptr [rbp+80h+var_E0+8], rax
0x18000e6d6  call    cs:__imp_LsarSetSecret
  ... truncated ...
```
