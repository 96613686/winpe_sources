# NCryptProtectSecret

- ea: `0x180006090`
- end: `0x18000671f`
- name: `NCryptProtectSecret`
- size: `1679`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003150`
- `0x18000382c`
- `0x180004a70`
- `0x1800050d0`
- `0x180006090`
- `0x180006be4`
- `0x180007958`
- `0x18000d02c`
- `0x18000e120`
- `0x18000f098`
- `0x180015c4c`
- `0x18001b808`
- `0x18001f145`
- `0x18001f175`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18000632e`
- `bcrypt!BCryptGenRandom` at `0x18000632e`

## string_xrefs

- `0x1800064aa`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x1800065fe`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180006665`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x1800066ab`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x18000620c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180006287`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800064d4`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180006591`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800065d3`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800066ee`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180006705`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall NCryptProtectSecret(
        _DWORD *a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 *a5,
        __int64 a6,
        _QWORD *a7,
        _DWORD *a8)
{
  int v9; // edi
  _DWORD *v11; // r15
  int v13; // edx
  int v14; // r8d
  __int64 *v15; // r14
  unsigned int Settings; // eax
  unsigned int BCryptOidInfo; // ebx
  __int64 v18; // rsi
  ULONG *v19; // rbx
  unsigned int v20; // ecx
  unsigned __int64 v21; // rdi
  ULONG *v22; // rax
  _QWORD *v23; // rcx
  __int64 ProcessName; // rax
  int v25; // ecx
  __int64 v26; // rcx
  void *v27; // rsp
  void *v28; // rsp
  unsigned int v29; // eax
  int v30; // edx
  int v31; // r8d
  _DWORD *v32; // rax
  _DWORD *v33; // rsi
  int v34; // edx
  int v35; // r8d
  _QWORD *v36; // rcx
  _BYTE *v37; // rax
  __int64 v39; // rcx
  __int64 v40; // r9
  __int64 v41; // rcx
  __int64 v42; // [rsp+0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+20h] [rbp-30h]
  const char *v44; // [rsp+28h] [rbp-28h]
  __int64 v45; // [rsp+30h] [rbp-20h]
  int v46; // [rsp+50h] [rbp+0h] BYREF
  ULONG cbBuffer[4]; // [rsp+58h] [rbp+8h] BYREF
  __int64 v48; // [rsp+68h] [rbp+18h] BYREF
  __int64 v49; // [rsp+70h] [rbp+20h] BYREF
  __int64 v50; // [rsp+78h] [rbp+28h]
  _OWORD v51[2]; // [rsp+80h] [rbp+30h] BYREF
  __int64 v52; // [rsp+A0h] [rbp+50h]
  _DWORD v53[4]; // [rsp+B0h] [rbp+60h] BYREF
  _OWORD *v54; // [rsp+C0h] [rbp+70h]
  ULONG *v55; // [rsp+C8h] [rbp+78h]

  v46 = a2;
  v9 = a2;
  v50 = a3;
  v11 = 0;
  memset_0(v53, 0, 0x40u);
  v48 = 0;
  v52 = 0;
  v49 = 0;
  v53[0] = 64;
  v51[0] = 0;
  *a7 = 0;
  v51[1] = 0;
  *(_OWORD *)cbBuffer = 0;
  *a8 = 0;
  if ( !a3 || !a4 )
  {
    BCryptOidInfo = -2146893785;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_18;
    LODWORD(v45) = 1228;
    v44 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c";
    LODWORD(v43) = -2146893785;
    goto LABEL_17;
  }
  if ( (v9 & 0xFFFFFFBF) != 0 )
  {
    BCryptOidInfo = -2146893815;
    v40 = 1240;
    v41 = 2148073481LL;
  }
  else
  {
    if ( !a1 || *a1 != 40 )
    {
      BCryptOidInfo = -2146893786;
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_18;
      LODWORD(v45) = 1249;
      v44 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c";
      LODWORD(v43) = -2146893786;
      goto LABEL_17;
    }
    v15 = &NCryptDefaultAllocPara;
    if ( a5 )
      v15 = a5;
    Settings = KeyProtRouter_GetSettings(&v49);
    BCryptOidInfo = Settings;
    if ( !Settings )
    {
      v18 = v49;
      BCryptOidInfo = CNG_FindBCryptOidInfo(
                        *(_QWORD *)(*(_QWORD *)(v49 + 8) + 40LL),
                        *(unsigned int *)(*(_QWORD *)(v49 + 8) + 32LL),
                        1,
                        &v48);
      if ( BCryptOidInfo )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_18;
        LODWORD(v45) = 1276;
        goto LABEL_60;
      }
      v19 = 0;
      v20 = (unsigned int)(*(_DWORD *)(v48 + 56) + 7) >> 3;
      v21 = v20;
      cbBuffer[0] = v20;
      if ( !v20
        || v20 > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)v20 + g_ulAdditionalProbeSize + 8 < v20
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_78;
      }
      v26 = v21 + 23;
      if ( v21 + 23 <= v21 + 8 )
        v26 = 0xFFFFFFFFFFFFFF0LL;
      v27 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
      v28 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
      v19 = (ULONG *)&v46;
      if ( &v42 == (__int64 *)-80LL || (v46 = 1801679955, (v19 = cbBuffer) == 0) )
      {
LABEL_78:
        if ( v21 + 8 >= v21 )
        {
          v22 = (ULONG *)((__int64 (*)(void))g_pfnAllocate)();
          v19 = v22;
          if ( v22 )
          {
            *v22 = 1885431112;
            v19 = v22 + 2;
          }
        }
      }
      *(_QWORD *)&cbBuffer[2] = v19;
      if ( !v19 )
      {
        BCryptOidInfo = -2146893810;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_18;
        LODWORD(v45) = 1286;
        v44 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c";
        LODWORD(v43) = -2146893810;
        goto LABEL_17;
      }
      v29 = BCryptGenRandom(0, (PUCHAR)v19, cbBuffer[0], 2u);
      BCryptOidInfo = v29;
      if ( v29 )
      {
        DebugTraceError(
          v29,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
          1298);
        goto LABEL_18;
      }
      *((_QWORD *)&v51[0] + 1) = *(_QWORD *)(*(_QWORD *)(v18 + 8) + 40LL);
      LODWORD(v51[0]) = *(_DWORD *)(*(_QWORD *)(v18 + 8) + 32LL);
      v52 = *(_QWORD *)(v18 + 8);
      v54 = v51;
      v55 = cbBuffer;
      if ( v15 && *(_DWORD *)v15 == 24 )
      {
        v32 = (_DWORD *)((__int64 (__fastcall *)(__int64))v15[1])(368);
        v33 = v32;
        if ( v32 )
        {
          memset_0(v32, 0, 0x170u);
          *v33 = 368;
          v33[1] = 1;
          v33[4] = 24;
          *((_QWORD *)v33 + 3) = v15[1];
          *((_QWORD *)v33 + 4) = v15[2];
          v33[2] = 0;
          *((_QWORD *)v33 + 8) = &off_180021000;
          if ( *((_QWORD *)v33 + 8) )
          {
            BCryptOidInfo = CMSG_InitEnveloped(v33, v53, v50, a4);
            if ( !BCryptOidInfo )
            {
              v11 = v33;
              *((_QWORD *)v33 + 27) = v33 + 56;
              BCryptOidInfo = I_AddRecipientsAndEncodeMessage(
                                (_DWORD)v33,
                                (_DWORD)a1,
                                cbBuffer[2],
                                cbBuffer[0],
                                (__int64)v15,
                                a6,
                                (__int64)a7,
                                (__int64)a8,
                                v46);
              if ( !BCryptOidInfo )
                goto LABEL_45;
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_18;
              LODWORD(v45) = 1341;
LABEL_60:
              v44 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c";
              LODWORD(v43) = BCryptOidInfo;
LABEL_17:
              WPP_SF_sDsd(v23[2], v13, v14, (unsigned int)"Status", v43, (__int64)v44, v45);
LABEL_18:
              v9 = v46;
              goto LABEL_19;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v34,
                v35,
                (unsigned int)"Status",
                BCryptOidInfo,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
                176);
          }
          else
          {
            BCryptOidInfo = -2146893783;
            DebugTraceError(
              2148073513LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
              407);
          }
          I_CMsgFree(v33);
LABEL_44:
          DebugTraceError(
            BCryptOidInfo,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
            1324);
          goto LABEL_18;
        }
        BCryptOidInfo = -2146893810;
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_44;
        LODWORD(v45) = 378;
        v44 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c";
        LODWORD(v43) = -2146893810;
      }
      else
      {
        BCryptOidInfo = -2146893785;
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_44;
        LODWORD(v45) = 365;
        v44 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c";
        LODWORD(v43) = -2146893785;
      }
      WPP_SF_sDsd(v36[2], v30, v31, (unsigned int)"Status", v43, (__int64)v44, v45);
      goto LABEL_44;
    }
    v40 = 1264;
    v41 = Settings;
  }
  DebugTraceError(
    v41,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
    v40);
LABEL_19:
  if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 2) != 0 )
  {
    ProcessName = I_GetProcessName();
    McTemplateU0ddz_EventWriteTransfer(
      v25,
      (unsigned int)ETW_LOG_NCRYPT_PROTECT_SECRET_FAILED,
      v9,
      BCryptOidInfo,
      ProcessName);
  }
LABEL_45:
  v37 = *(_BYTE **)&cbBuffer[2];
  if ( *(_QWORD *)&cbBuffer[2] )
  {
    v39 = cbBuffer[0];
    if ( cbBuffer[0] )
    {
      do
      {
        *v37++ = 0;
        --v39;
      }
      while ( v39 );
    }
    if ( *(_QWORD *)&cbBuffer[2] && *(_DWORD *)(*(_QWORD *)&cbBuffer[2] - 8LL) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  if ( v11 )
    NCryptMsgClose(v11);
  return BCryptOidInfo;
}

```

## disassembly

```asm
0x180006090  push    rbp
0x180006092  push    rbx
0x180006093  push    rsi
0x180006094  push    rdi
0x180006095  push    r12
0x180006097  push    r13
0x180006099  push    r14
0x18000609b  push    r15
0x18000609d  sub     rsp, 108h
0x1800060a4  lea     rbp, [rsp+50h]
0x1800060a9  mov     rax, cs:__security_cookie
0x1800060b0  xor     rax, rbp
0x1800060b3  mov     [rbp+0F0h+var_50], rax
0x1800060ba  mov     rbx, r8
0x1800060bd  mov     [rbp+0F0h+var_F0], edx
0x1800060c0  mov     edi, edx
0x1800060c2  mov     [rbp+0F0h+var_C8], rbx
0x1800060c6  mov     r12, rcx
0x1800060c9  xor     r15d, r15d
0x1800060cc  xor     edx, edx; Val
0x1800060ce  lea     rcx, [rbp+0F0h+var_90]; void *
0x1800060d2  mov     r13d, r9d
0x1800060d5  lea     esi, [r15+40h]
0x1800060d9  mov     r8d, esi; Size
0x1800060dc  call    memset_0
0x1800060e1  xor     eax, eax
0x1800060e3  mov     [rbp+0F0h+var_D8], r15
0x1800060e7  mov     [rbp+0F0h+var_A0], rax
0x1800060eb  xorps   xmm0, xmm0
0x1800060ee  mov     rax, [rbp+0F0h+arg_30]
0x1800060f5  mov     [rbp+0F0h+var_D0], r15
0x1800060f9  mov     [rbp+0F0h+var_90], esi
0x1800060fc  movups  [rbp+0F0h+var_C0], xmm0
0x180006100  mov     [rax], r15
0x180006103  mov     rax, [rbp+0F0h+arg_38]
0x18000610a  movups  [rbp+0F0h+var_B0], xmm0
0x18000610e  movups  xmmword ptr [rbp+0F0h+cbBuffer], xmm0
0x180006112  mov     [rax], r15d
0x180006115  test    rbx, rbx
0x180006118  jz      loc_1800061E6
0x18000611e  cmp     r13d, 1
0x180006122  jb      loc_1800061E6
0x180006128  test    edi, 0FFFFFFBFh
0x18000612e  jnz     loc_1800066CD
0x180006134  test    r12, r12
0x180006137  jz      loc_180006261
0x18000613d  cmp     dword ptr [r12], 28h ; '('
0x180006142  jnz     loc_180006261
0x180006148  mov     rax, [rbp+0F0h+arg_20]
0x18000614f  lea     r14, NCryptDefaultAllocPara
0x180006156  test    rax, rax
0x180006159  lea     rcx, [rbp+0F0h+var_D0]
0x18000615d  cmovnz  r14, rax
0x180006161  call    KeyProtRouter_GetSettings
0x180006166  mov     ebx, eax
0x180006168  test    eax, eax
0x18000616a  jnz     loc_1800066DF
0x180006170  mov     rsi, [rbp+0F0h+var_D0]
0x180006174  lea     r9, [rbp+0F0h+var_D8]
0x180006178  lea     r8d, [r15+1]
0x18000617c  mov     rcx, [rsi+8]
0x180006180  mov     edx, [rcx+20h]
0x180006183  mov     rcx, [rcx+28h]
0x180006187  call    CNG_FindBCryptOidInfo
0x18000618c  mov     ebx, eax
0x18000618e  test    eax, eax
0x180006190  jnz     loc_1800065AA
0x180006196  mov     rax, [rbp+0F0h+var_D8]
0x18000619a  xor     ebx, ebx
0x18000619c  mov     ecx, [rax+38h]
0x18000619f  add     ecx, 7
0x1800061a2  shr     ecx, 3
0x1800061a5  mov     edi, ecx
0x1800061a7  mov     [rbp+0F0h+cbBuffer], edi
0x1800061aa  test    ecx, ecx
0x1800061ac  jnz     loc_18000629D
0x1800061b2  lea     rcx, [rdi+8]
0x1800061b6  cmp     rcx, rdi
0x1800061b9  jb      loc_180006312
0x1800061bf  mov     rax, cs:g_pfnAllocate
0x1800061c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061cb  mov     rbx, rax
0x1800061ce  test    rax, rax
0x1800061d1  jz      loc_180006312
0x1800061d7  mov     dword ptr [rax], 70616548h
0x1800061dd  add     rbx, 8
0x1800061e1  jmp     loc_180006312
0x1800061e6  mov     ebx, 80090027h
0x1800061eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061f2  lea     rdi, WPP_GLOBAL_Control
0x1800061f9  cmp     rcx, rdi
0x1800061fc  jz      short loc_180006230
0x1800061fe  test    byte ptr [rcx+1Ch], 1
0x180006202  jz      short loc_180006230
0x180006204  mov     dword ptr [rsp+140h+var_110], 4CCh
0x18000620c  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006213  mov     [rsp+140h+var_118], rax
0x180006218  mov     dword ptr [rsp+140h+var_120], 80090027h
0x180006220  mov     rcx, [rcx+10h]
0x180006224  lea     r9, aStatus; "Status"
0x18000622b  call    WPP_SF_sDsd
0x180006230  mov     edi, [rbp+0F0h+var_F0]
0x180006233  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 2
0x18000623a  jz      loc_1800064F1
0x180006240  call    I_GetProcessName
0x180006245  mov     r9d, ebx
0x180006248  mov     [rsp+140h+var_120], rax
0x18000624d  mov     r8d, edi
0x180006250  lea     rdx, ETW_LOG_NCRYPT_PROTECT_SECRET_FAILED
0x180006257  call    McTemplateU0ddz_EventWriteTransfer
0x18000625c  jmp     loc_1800064F1
0x180006261  mov     ebx, 80090026h
0x180006266  mov     rcx, cs:WPP_GLOBAL_Control
0x18000626d  lea     rdi, WPP_GLOBAL_Control
0x180006274  cmp     rcx, rdi
0x180006277  jz      short loc_180006230
0x180006279  test    byte ptr [rcx+1Ch], 1
0x18000627d  jz      short loc_180006230
0x18000627f  mov     dword ptr [rsp+140h+var_110], 4E1h
0x180006287  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000628e  mov     [rsp+140h+var_118], rax
0x180006293  mov     dword ptr [rsp+140h+var_120], 80090026h
0x18000629b  jmp     short loc_180006220
0x18000629d  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800062a4  ja      loc_1800061B2
0x1800062aa  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800062b1  add     rcx, 8
0x1800062b5  add     rcx, rdi
0x1800062b8  cmp     rcx, rdi
0x1800062bb  jb      loc_1800061B2
0x1800062c1  call    VerifyStackAvailable
0x1800062c6  test    eax, eax
0x1800062c8  jz      loc_1800061B2
0x1800062ce  lea     rax, [rdi+8]
0x1800062d2  lea     rcx, [rax+0Fh]
0x1800062d6  cmp     rcx, rax
0x1800062d9  ja      short loc_1800062E5
0x1800062db  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800062e5  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800062e9  mov     rax, rcx
0x1800062ec  call    __chkstk_0
0x1800062f1  sub     rsp, rcx
0x1800062f4  lea     rbx, [rsp+140h+var_F0]
0x1800062f9  test    rbx, rbx
0x1800062fc  jz      loc_1800061B2
0x180006302  mov     dword ptr [rbx], 6B637453h
0x180006308  add     rbx, 8
0x18000630c  jz      loc_1800061B2
0x180006312  mov     qword ptr [rbp+0F0h+cbBuffer+8], rbx
0x180006316  test    rbx, rbx
0x180006319  jz      loc_180006563
0x18000631f  mov     r8d, [rbp+0F0h+cbBuffer]; cbBuffer
0x180006323  mov     r9d, 2; dwFlags
0x180006329  mov     rdx, rbx; pbBuffer
0x18000632c  xor     ecx, ecx; hAlgorithm
0x18000632e  call    cs:__imp_BCryptGenRandom
0x180006334  mov     ebx, eax
0x180006336  test    eax, eax
0x180006338  jnz     loc_1800066FF
0x18000633e  mov     rax, [rsi+8]
0x180006342  mov     rcx, [rax+28h]
0x180006346  mov     qword ptr [rbp+0F0h+var_C0+8], rcx
0x18000634a  mov     rax, [rsi+8]
0x18000634e  mov     ecx, [rax+20h]
0x180006351  mov     dword ptr [rbp+0F0h+var_C0], ecx
0x180006354  mov     rax, [rsi+8]
0x180006358  mov     [rbp+0F0h+var_A0], rax
0x18000635c  lea     rax, [rbp+0F0h+var_C0]
0x180006360  mov     [rbp+0F0h+var_80], rax
0x180006364  lea     rax, [rbp+0F0h+cbBuffer]
0x180006368  mov     [rbp+0F0h+var_78], rax
0x18000636c  test    r14, r14
0x18000636f  jz      loc_180006484
0x180006375  cmp     dword ptr [r14], 18h
0x180006379  jnz     loc_180006484
0x18000637f  mov     rax, [r14+8]
0x180006383  mov     ebx, 170h
0x180006388  mov     ecx, ebx
0x18000638a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000638f  mov     rsi, rax
0x180006392  test    rax, rax
0x180006395  jz      loc_180006637
0x18000639b  mov     r8d, ebx; Size
0x18000639e  xor     edx, edx; Val
0x1800063a0  mov     rcx, rax; void *
0x1800063a3  call    memset_0
0x1800063a8  mov     [rsi], ebx
0x1800063aa  lea     rdx, off_180021000; "1.2.840.113549.1.7.3"
0x1800063b1  mov     dword ptr [rsi+4], 1
0x1800063b8  mov     dword ptr [rsi+10h], 18h
0x1800063bf  mov     rax, [r14+8]
0x1800063c3  mov     [rsi+18h], rax
0x1800063c7  mov     rax, [r14+10h]
0x1800063cb  mov     [rsi+20h], rax
0x1800063cf  xor     eax, eax
0x1800063d1  mov     [rsi+8], r15d
0x1800063d5  cmp     rax, 1
0x1800063d9  jnb     short loc_1800063F6
0x1800063db  mov     rcx, rax
0x1800063de  shl     rcx, 5
0x1800063e2  cmp     dword ptr [rcx+rdx+1Ch], 3
0x1800063e7  jz      short loc_1800063EE
0x1800063e9  inc     rax
0x1800063ec  jmp     short loc_1800063D5
0x1800063ee  lea     rax, [rcx+rdx]
0x1800063f2  mov     [rsi+40h], rax
0x1800063f6  lea     rdi, WPP_GLOBAL_Control
0x1800063fd  cmp     [rsi+40h], r15
0x180006401  jz      loc_1800066A5
0x180006407  mov     r8, [rbp+0F0h+var_C8]
0x18000640b  lea     rdx, [rbp+0F0h+var_90]
0x18000640f  mov     r9d, r13d
0x180006412  mov     rcx, rsi
0x180006415  call    CMSG_InitEnveloped
0x18000641a  mov     ebx, eax
0x18000641c  test    eax, eax
0x18000641e  jnz     loc_1800065E8
0x180006424  lea     rax, [rsi+0E0h]
0x18000642b  mov     r15, rsi
0x18000642e  mov     [rsi+0D8h], rax
0x180006435  mov     eax, [rbp+0F0h+var_F0]
0x180006438  mov     rdx, r12
0x18000643b  mov     r9d, [rbp+0F0h+cbBuffer]
0x18000643f  mov     rcx, r15
0x180006442  mov     r8, qword ptr [rbp+0F0h+cbBuffer+8]
0x180006446  mov     [rsp+140h+var_100], eax
0x18000644a  mov     rax, [rbp+0F0h+arg_38]
0x180006451  mov     [rsp+140h+var_108], rax
0x180006456  mov     rax, [rbp+0F0h+arg_30]
0x18000645d  mov     [rsp+140h+var_110], rax
0x180006462  mov     rax, [rbp+0F0h+arg_28]
0x180006469  mov     [rsp+140h+var_118], rax
0x18000646e  mov     [rsp+140h+var_120], r14
0x180006473  call    I_AddRecipientsAndEncodeMessage
0x180006478  mov     ebx, eax
0x18000647a  test    eax, eax
0x18000647c  jnz     loc_18000667E
0x180006482  jmp     short loc_1800064F1
0x180006484  mov     ebx, 80090027h
0x180006489  mov     rcx, cs:WPP_GLOBAL_Control
0x180006490  lea     rdi, WPP_GLOBAL_Control
0x180006497  cmp     rcx, rdi
0x18000649a  jz      short loc_1800064CE
0x18000649c  test    byte ptr [rcx+1Ch], 1
0x1800064a0  jz      short loc_1800064CE
0x1800064a2  mov     dword ptr [rsp+140h+var_110], 16Dh
0x1800064aa  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800064b1  mov     [rsp+140h+var_118], rax
0x1800064b6  mov     dword ptr [rsp+140h+var_120], 80090027h
0x1800064be  mov     rcx, [rcx+10h]
0x1800064c2  lea     r9, aStatus; "Status"
0x1800064c9  call    WPP_SF_sDsd
0x1800064ce  mov     r9d, 52Ch
0x1800064d4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800064db  lea     rdx, aStatus; "Status"
0x1800064e2  mov     ecx, ebx
0x1800064e4  call    DebugTraceError
0x1800064e9  test    ebx, ebx
0x1800064eb  jnz     loc_180006230
0x1800064f1  mov     rax, qword ptr [rbp+0F0h+cbBuffer+8]
0x1800064f5  test    rax, rax
0x1800064f8  jnz     short loc_18000652C
0x1800064fa  test    r15, r15
0x1800064fd  jz      short loc_180006507
0x1800064ff  mov     rcx, r15
0x180006502  call    NCryptMsgClose
0x180006507  mov     eax, ebx
0x180006509  mov     rcx, [rbp+0F0h+var_50]
0x180006510  xor     rcx, rbp; StackCookie
0x180006513  call    __security_check_cookie
0x180006518  lea     rsp, [rbp+0B8h]
0x18000651f  pop     r15
0x180006521  pop     r14
0x180006523  pop     r13
0x180006525  pop     r12
0x180006527  pop     rdi
0x180006528  pop     rsi
0x180006529  pop     rbx
0x18000652a  pop     rbp
0x18000652b  retn
0x18000652c  mov     ecx, [rbp+0F0h+cbBuffer]
0x18000652f  test    rcx, rcx
0x180006532  jz      short loc_180006540
0x180006534  mov     byte ptr [rax], 0
0x180006537  inc     rax
0x18000653a  sub     rcx, 1
0x18000653e  jnz     short loc_180006534
0x180006540  mov     rax, qword ptr [rbp+0F0h+cbBuffer+8]
0x180006544  test    rax, rax
0x180006547  jz      short loc_1800064FA
0x180006549  lea     rcx, [rax-8]
0x18000654d  cmp     dword ptr [rcx], 70616548h
0x180006553  jnz     short loc_1800064FA
0x180006555  mov     rax, cs:g_pfnFree
0x18000655c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006561  jmp     short loc_1800064FA
0x180006563  mov     ebx, 8009000Eh
0x180006568  mov     rcx, cs:WPP_GLOBAL_Control
0x18000656f  lea     rdi, WPP_GLOBAL_Control
0x180006576  cmp     rcx, rdi
  ... truncated ...
```
