# UnprovisionTBAL(_USER_CACHE_ENTRY *,_CloudAPCache *,bool *)

- ea: `0x18002d0a4`
- end: `0x18002d41d`
- name: `?UnprovisionTBAL@@YAJPEAU_USER_CACHE_ENTRY@@PEAU_CloudAPCache@@PEA_N@Z`
- size: `889`
- prototype: `int(struct _USER_CACHE_ENTRY *, struct _CloudAPCache *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180011960`
- `0x180052358`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002d0a4`
- `0x18002d4b8`
- `0x18002d71c`
- `0x18003f220`
- `0x180081010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002d209`
- `ntdll!RtlInitUnicodeString` at `0x18002d319`
- `ntdll!RtlInitUnicodeString` at `0x18002d209`
- `ntdll!RtlInitUnicodeString` at `0x18002d319`
- `LSASRV!LsarClose` at `0x18002d3d2`
- `LSASRV!LsarClose` at `0x18002d3fa`
- `LSASRV!LsarClose` at `0x18002d3d2`
- `LSASRV!LsarClose` at `0x18002d3fa`
- `LSASRV!LsarDeleteObject` at `0x18002d251`
- `LSASRV!LsarDeleteObject` at `0x18002d34c`
- `LSASRV!LsarDeleteObject` at `0x18002d251`
- `LSASRV!LsarDeleteObject` at `0x18002d34c`
- `LSASRV!LsarOpenSecret` at `0x18002d224`
- `LSASRV!LsarOpenSecret` at `0x18002d334`
- `LSASRV!LsarOpenSecret` at `0x18002d224`
- `LSASRV!LsarOpenSecret` at `0x18002d334`

## string_xrefs

- `0x18002d140`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18002d1c4`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18002d22a`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18002d167`: `RemoveCloudAPArsoCacheNode`
- `0x18002d26e`: `LsarDeleteObject`
- `0x18002d294`: `LsarOpenSecret`
- `0x18002d369`: `LsarDeleteObject TGT`
- `0x18002d38f`: `LsarOpenSecret TGT`

## pseudocode

```c
__int64 __fastcall UnprovisionTBAL(struct _USER_CACHE_ENTRY *a1, struct _CloudAPCache *a2, bool *a3)
{
  PCWSTR v6; // rsi
  unsigned int v7; // ebx
  const char *v8; // r9
  const char *v9; // rax
  bool v10; // zf
  unsigned int LSASecretName; // eax
  PCWSTR v12; // r12
  const char *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // r8
  const char *v25; // r9
  bool v27[8]; // [rsp+20h] [rbp-60h]
  bool v28[8]; // [rsp+20h] [rbp-60h]
  bool v29[8]; // [rsp+20h] [rbp-60h]
  const char *v30; // [rsp+28h] [rbp-58h]
  PCWSTR v31; // [rsp+40h] [rbp-40h] BYREF
  PCWSTR SourceString; // [rsp+48h] [rbp-38h] BYREF
  __int64 v33; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-28h] BYREF
  struct _UNICODE_STRING v35; // [rsp+68h] [rbp-18h] BYREF
  __int64 v36; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v37; // [rsp+D8h] [rbp+58h] BYREF

  v36 = 0;
  SourceString = 0;
  v37 = 0;
  v31 = 0;
  v6 = 0;
  DestinationString = 0;
  v35 = 0;
  if ( !a2 )
    goto LABEL_14;
  v33 = 0;
  if ( (int)GetCloudAPCacheNode(a2, 3, 0, 0, &v33) < 0 )
  {
    v7 = 0;
    goto LABEL_31;
  }
  v7 = RemoveCloudAPCacheNode(a2, 3u, 0, 0);
  if ( !v7 )
  {
    if ( a3 )
      *a3 = 1;
LABEL_14:
    LSASecretName = GetLSASecretName(
                      (UUID *)((char *)a1 + 248),
                      *((const unsigned __int16 **)a1 + 12),
                      (unsigned __int16 **)&SourceString,
                      0,
                      0);
    v12 = SourceString;
    v7 = LSASecretName;
    if ( LSASecretName )
    {
      v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      *(_DWORD *)v28 = 319;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v13, *(_QWORD *)v28, "GetLSASecretName", &Class);
      goto LABEL_29;
    }
    RtlInitUnicodeString(&DestinationString, SourceString);
    v16 = LsarOpenSecret(g_LsaPolicyHandle, &DestinationString, 983043, &v36);
    if ( v16 != -1073741772 )
    {
      if ( v16 )
      {
        v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        *(_DWORD *)v28 = 339;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, *(_QWORD *)v28, "LsarOpenSecret", &Class);
      }
      else if ( (unsigned int)LsarDeleteObject(&v36) )
      {
        v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        *(_DWORD *)v28 = 335;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v17, *(_QWORD *)v28, "LsarDeleteObject", &Class);
      }
    }
    v7 = GetLSASecretName(
           (UUID *)((char *)a1 + 248),
           *((const unsigned __int16 **)a1 + 12),
           (unsigned __int16 **)&v31,
           1,
           0);
    if ( v7 )
    {
      v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      *(_DWORD *)v29 = 351;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v21, *(_QWORD *)v29, "GetLSASecretName for TGT", &Class);
      v6 = v31;
      goto LABEL_29;
    }
    v6 = v31;
    RtlInitUnicodeString(&v35, v31);
    v22 = LsarOpenSecret(g_LsaPolicyHandle, &v35, 983043, &v37);
    v15 = v22;
    if ( v22 != -1073741772 )
    {
      if ( v22 )
      {
        v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        v30 = "LsarOpenSecret TGT";
        *(_DWORD *)v29 = 371;
      }
      else
      {
        v23 = LsarDeleteObject(&v37);
        v15 = v23;
        if ( !v23 )
          goto LABEL_29;
        v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        v30 = "LsarDeleteObject TGT";
        *(_DWORD *)v29 = 367;
      }
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v25, *(_QWORD *)v29, v30, &Class);
    }
LABEL_29:
    if ( v12 )
      ((void (__fastcall *)(PCWSTR, __int64, __int64))g_pLsaFunctionTable->FreeLsaHeap)(v12, v14, v15);
    goto LABEL_31;
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
  *(_DWORD *)v27 = 305;
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v8, *(_QWORD *)v27, "RemoveCloudAPArsoCacheNode", &Class);
LABEL_31:
  if ( v36 )
    LsarClose(&v36);
  if ( v6 )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v6);
  if ( v37 )
    LsarClose(&v37);
  return v7;
}

```

## disassembly

```asm
0x18002d0a4  mov     [rsp-38h+arg_0], rbx
0x18002d0a9  push    rbp
0x18002d0aa  push    rsi
0x18002d0ab  push    rdi
0x18002d0ac  push    r12
0x18002d0ae  push    r13
0x18002d0b0  push    r14
0x18002d0b2  push    r15
0x18002d0b4  mov     rbp, rsp
0x18002d0b7  sub     rsp, 80h
0x18002d0be  xor     r14d, r14d
0x18002d0c1  xorps   xmm0, xmm0
0x18002d0c4  mov     [rbp+arg_8], r14
0x18002d0c8  mov     rdi, r8
0x18002d0cb  mov     [rbp+SourceString], r14
0x18002d0cf  mov     rbx, rdx
0x18002d0d2  mov     [rbp+arg_18], r14
0x18002d0d6  mov     r13, rcx
0x18002d0d9  mov     [rbp+var_40], r14
0x18002d0dd  mov     esi, r14d
0x18002d0e0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002d0e4  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x18002d0e8  test    rdx, rdx
0x18002d0eb  jz      loc_18002D19E
0x18002d0f1  lea     rax, [rbp+var_30]
0x18002d0f5  mov     [rbp+var_30], r14
0x18002d0f9  lea     r15d, [r14+3]
0x18002d0fd  mov     qword ptr [rsp+80h+var_60], rax
0x18002d102  mov     edx, r15d
0x18002d105  xor     r9d, r9d
0x18002d108  xor     r8d, r8d
0x18002d10b  mov     rcx, rbx
0x18002d10e  call    GetCloudAPCacheNode
0x18002d113  shr     eax, 1Fh
0x18002d116  xor     al, 1
0x18002d118  jnz     short loc_18002D122
0x18002d11a  mov     ebx, r14d
0x18002d11d  jmp     loc_18002D3C8
0x18002d122  xor     r9d, r9d; unsigned int
0x18002d125  xor     r8d, r8d; unsigned __int8 *
0x18002d128  mov     edx, r15d; unsigned int
0x18002d12b  mov     rcx, rbx; struct _CloudAPCache *
0x18002d12e  call    ?RemoveCloudAPCacheNode@@YAJPEAU_CloudAPCache@@KPEAEK@Z; RemoveCloudAPCacheNode(_CloudAPCache *,ulong,uchar *,ulong)
0x18002d133  mov     ebx, eax
0x18002d135  test    eax, eax
0x18002d137  jz      short loc_18002D196
0x18002d139  lea     r9, aOnecoreDsExtCl_8+23h; ""
0x18002d140  lea     rdi, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002d147  mov     rax, r9
0x18002d14a  dec     r9
0x18002d14d  cmp     byte ptr [r9], 5Ch ; '\'
0x18002d151  jz      short loc_18002D15C
0x18002d153  cmp     r9, rdi
0x18002d156  ja      short loc_18002D147
0x18002d158  cmp     byte ptr [r9], 5Ch ; '\'
0x18002d15c  cmovz   r9, rax
0x18002d160  lea     r15, Class
0x18002d167  lea     rax, aRemovecloudapa; "RemoveCloudAPArsoCacheNode"
0x18002d16e  mov     [rsp+80h+var_50], r15
0x18002d173  mov     [rsp+80h+var_58], rax
0x18002d178  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002d17f  mov     r8d, ebx
0x18002d182  mov     dword ptr [rsp+80h+var_60], 131h
0x18002d18a  xor     ecx, ecx
0x18002d18c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002d191  jmp     loc_18002D3C8
0x18002d196  test    rdi, rdi
0x18002d199  jz      short loc_18002D19E
0x18002d19b  mov     byte ptr [rdi], 1
0x18002d19e  mov     rdx, [r13+60h]; unsigned __int16 *
0x18002d1a2  lea     rcx, [r13+0F8h]; Uuid
0x18002d1a9  xor     r9d, r9d; bool
0x18002d1ac  mov     [rsp+80h+var_60], r14b; bool
0x18002d1b1  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x18002d1b5  call    ?GetLSASecretName@@YAJPEBU_GUID@@PEBGPEAPEAG_N3@Z; GetLSASecretName(_GUID const *,ushort const *,ushort * *,bool,bool)
0x18002d1ba  mov     r12, [rbp+SourceString]
0x18002d1be  mov     ebx, eax
0x18002d1c0  test    eax, eax
0x18002d1c2  jz      short loc_18002D202
0x18002d1c4  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002d1cb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002d1d0  mov     r9, rax
0x18002d1d3  lea     r15, Class
0x18002d1da  mov     [rsp+80h+var_50], r15
0x18002d1df  lea     rax, aGetlsasecretna; "GetLSASecretName"
0x18002d1e6  mov     [rsp+80h+var_58], rax
0x18002d1eb  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002d1f2  mov     dword ptr [rsp+80h+var_60], 13Fh
0x18002d1fa  mov     r8d, ebx
0x18002d1fd  jmp     loc_18002D3A6
0x18002d202  mov     rdx, r12; SourceString
0x18002d205  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002d209  call    cs:__imp_RtlInitUnicodeString
0x18002d20f  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18002d216  lea     r9, [rbp+arg_8]
0x18002d21a  mov     r8d, 0F0003h
0x18002d220  lea     rdx, [rbp+DestinationString]
0x18002d224  call    cs:__imp_LsarOpenSecret
0x18002d22a  lea     rdi, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18002d231  mov     r8d, eax
0x18002d234  lea     r15, Class
0x18002d23b  lea     r14, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002d242  cmp     eax, 0C0000034h
0x18002d247  jz      short loc_18002D2B2
0x18002d249  test    eax, eax
0x18002d24b  jnz     short loc_18002D284
0x18002d24d  lea     rcx, [rbp+arg_8]
0x18002d251  call    cs:__imp_LsarDeleteObject
0x18002d257  mov     r8d, eax
0x18002d25a  test    eax, eax
0x18002d25c  jz      short loc_18002D2B2
0x18002d25e  mov     rcx, rdi; char *
0x18002d261  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002d266  mov     [rsp+80h+var_50], r15
0x18002d26b  mov     r9, rax
0x18002d26e  lea     rax, aLsardeleteobje_0; "LsarDeleteObject"
0x18002d275  mov     [rsp+80h+var_58], rax
0x18002d27a  mov     dword ptr [rsp+80h+var_60], 14Fh
0x18002d282  jmp     short loc_18002D2A8
0x18002d284  mov     rcx, rdi; char *
0x18002d287  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002d28c  mov     [rsp+80h+var_50], r15
0x18002d291  mov     r9, rax
0x18002d294  lea     rax, aLsaropensecret_0; "LsarOpenSecret"
0x18002d29b  mov     [rsp+80h+var_58], rax
0x18002d2a0  mov     dword ptr [rsp+80h+var_60], 153h
0x18002d2a8  mov     rdx, r14
0x18002d2ab  xor     ecx, ecx
0x18002d2ad  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002d2b2  mov     rdx, [r13+60h]; unsigned __int16 *
0x18002d2b6  lea     r8, [rbp+var_40]; unsigned __int16 **
0x18002d2ba  mov     r9b, 1; bool
0x18002d2bd  mov     [rsp+80h+var_60], sil; bool
0x18002d2c2  lea     rcx, [r13+0F8h]; Uuid
0x18002d2c9  call    ?GetLSASecretName@@YAJPEBU_GUID@@PEBGPEAPEAG_N3@Z; GetLSASecretName(_GUID const *,ushort const *,ushort * *,bool,bool)
0x18002d2ce  mov     ebx, eax
0x18002d2d0  test    eax, eax
0x18002d2d2  jz      short loc_18002D30E
0x18002d2d4  mov     rcx, rdi; char *
0x18002d2d7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002d2dc  mov     r9, rax
0x18002d2df  mov     [rsp+80h+var_50], r15
0x18002d2e4  lea     rax, aGetlsasecretna_0; "GetLSASecretName for TGT"
0x18002d2eb  mov     r8d, ebx
0x18002d2ee  mov     [rsp+80h+var_58], rax
0x18002d2f3  mov     rdx, r14
0x18002d2f6  xor     ecx, ecx
0x18002d2f8  mov     dword ptr [rsp+80h+var_60], 15Fh
0x18002d300  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002d305  mov     rsi, [rbp+var_40]
0x18002d309  jmp     loc_18002D3AD
0x18002d30e  mov     rsi, [rbp+var_40]
0x18002d312  lea     rcx, [rbp+var_18]; DestinationString
0x18002d316  mov     rdx, rsi; SourceString
0x18002d319  call    cs:__imp_RtlInitUnicodeString
0x18002d31f  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18002d326  lea     r9, [rbp+arg_18]
0x18002d32a  mov     r8d, 0F0003h
0x18002d330  lea     rdx, [rbp+var_18]
0x18002d334  call    cs:__imp_LsarOpenSecret
0x18002d33a  mov     r8d, eax
0x18002d33d  cmp     eax, 0C0000034h
0x18002d342  jz      short loc_18002D3AD
0x18002d344  test    eax, eax
0x18002d346  jnz     short loc_18002D37F
0x18002d348  lea     rcx, [rbp+arg_18]
0x18002d34c  call    cs:__imp_LsarDeleteObject
0x18002d352  mov     r8d, eax
0x18002d355  test    eax, eax
0x18002d357  jz      short loc_18002D3AD
0x18002d359  mov     rcx, rdi; char *
0x18002d35c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002d361  mov     [rsp+80h+var_50], r15
0x18002d366  mov     r9, rax
0x18002d369  lea     rax, aLsardeleteobje; "LsarDeleteObject TGT"
0x18002d370  mov     [rsp+80h+var_58], rax
0x18002d375  mov     dword ptr [rsp+80h+var_60], 16Fh
0x18002d37d  jmp     short loc_18002D3A3
0x18002d37f  mov     rcx, rdi; char *
0x18002d382  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002d387  mov     [rsp+80h+var_50], r15
0x18002d38c  mov     r9, rax
0x18002d38f  lea     rax, aLsaropensecret; "LsarOpenSecret TGT"
0x18002d396  mov     [rsp+80h+var_58], rax
0x18002d39b  mov     dword ptr [rsp+80h+var_60], 173h
0x18002d3a3  mov     rdx, r14
0x18002d3a6  xor     ecx, ecx
0x18002d3a8  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002d3ad  xor     r14d, r14d
0x18002d3b0  test    r12, r12
0x18002d3b3  jz      short loc_18002D3C8
0x18002d3b5  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002d3bc  mov     rcx, r12
0x18002d3bf  mov     rax, [rax+30h]
0x18002d3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3c8  cmp     [rbp+arg_8], r14
0x18002d3cc  jz      short loc_18002D3D8
0x18002d3ce  lea     rcx, [rbp+arg_8]
0x18002d3d2  call    cs:__imp_LsarClose
0x18002d3d8  test    rsi, rsi
0x18002d3db  jz      short loc_18002D3F0
0x18002d3dd  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002d3e4  mov     rcx, rsi
0x18002d3e7  mov     rax, [rax+30h]
0x18002d3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3f0  cmp     [rbp+arg_18], r14
0x18002d3f4  jz      short loc_18002D400
0x18002d3f6  lea     rcx, [rbp+arg_18]
0x18002d3fa  call    cs:__imp_LsarClose
0x18002d400  mov     eax, ebx
0x18002d402  mov     rbx, [rsp+80h+arg_0]
0x18002d40a  add     rsp, 80h
0x18002d411  pop     r15
0x18002d413  pop     r14
0x18002d415  pop     r13
0x18002d417  pop     r12
0x18002d419  pop     rdi
0x18002d41a  pop     rsi
0x18002d41b  pop     rbp
0x18002d41c  retn
```
