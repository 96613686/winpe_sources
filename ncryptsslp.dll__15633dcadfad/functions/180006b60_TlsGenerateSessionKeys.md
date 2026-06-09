# TlsGenerateSessionKeys

- ea: `0x180006b60`
- end: `0x180007939`
- name: `TlsGenerateSessionKeys`
- size: `3545`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180005ec0`

## callees

- `0x180001690`
- `0x180001acc`
- `0x180003ef0`
- `0x180006b60`
- `0x180007940`
- `0x180008810`
- `0x180009160`
- `0x18000b594`
- `0x18000b654`
- `0x1800185e0`
- `0x180018ac0`
- `0x18001fb58`
- `0x18002032c`
- `0x180024ef0`
- `0x180024fb0`
- `0x180025660`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x180007385`
- `bcrypt!BCryptSetProperty` at `0x1800073d6`
- `bcrypt!BCryptSetProperty` at `0x180007385`
- `bcrypt!BCryptSetProperty` at `0x1800073d6`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006f7c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006fb2`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006f7c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180006fb2`
- `bcrypt!BCryptGenRandom` at `0x1800072a3`
- `bcrypt!BCryptGenRandom` at `0x1800072a3`

## string_xrefs

- `0x18000700a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800070e6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800071cb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000721d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007313`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007356`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800073ee`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000746d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007495`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800074c5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800076e6`: `client write key`
- `0x18000774d`: `server write key`

## pseudocode

```c
__int64 __fastcall TlsGenerateSessionKeys(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4, __int64 a5)
{
  __int64 v5; // r14
  unsigned int v6; // r13d
  _OWORD *v7; // rdi
  int v8; // r15d
  _OWORD *v9; // rbx
  int v10; // r12d
  __int64 v11; // rax
  __int128 v12; // xmm1
  _DWORD *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // ebx
  __int64 v17; // r12
  __int64 v18; // rcx
  bool v19; // cf
  void *v20; // r14
  char *v21; // rax
  char *v22; // r15
  UCHAR *v23; // rsi
  int v24; // eax
  size_t v25; // rax
  char *v26; // rax
  char *v27; // r14
  size_t v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rax
  unsigned int v31; // eax
  unsigned __int64 v32; // rbx
  unsigned __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  void *v36; // rsp
  void *v37; // rsp
  unsigned int v38; // ecx
  int SymmetricKey; // ebx
  bool v40; // zf
  __int64 v41; // r9
  unsigned int v42; // ebx
  UCHAR *v43; // r11
  UCHAR *v44; // rdx
  UCHAR *v45; // rcx
  UCHAR *v46; // r10
  UCHAR *v47; // rax
  void *v48; // rdx
  PUCHAR v49; // rdx
  ULONG v50; // edi
  UCHAR *v51; // rdi
  _QWORD *v52; // rcx
  __int64 v53; // rcx
  UCHAR *v54; // rax
  unsigned int v56; // ebx
  const void *v57; // rdx
  _QWORD *v58; // rcx
  ULONG v59; // r8d
  __int64 v60; // rax
  int KeyMaterial; // eax
  __int64 v62; // r9
  bool v63; // cc
  __int64 v64; // r8
  int HashEntry; // eax
  __int64 v66; // rcx
  UCHAR *v67; // rax
  int v68; // eax
  unsigned __int64 v69; // rcx
  char *v70; // r9
  unsigned __int64 v71; // rbx
  __int64 v72; // rcx
  void *v73; // rsp
  void *v74; // rsp
  char *v75; // rax
  __int64 v76; // r8
  unsigned int v77; // r10d
  __int64 v78; // r8
  _BYTE v79[32]; // [rsp+0h] [rbp-60h] BYREF
  PUCHAR pbSecret; // [rsp+20h] [rbp-40h]
  ULONG cbSecret[2]; // [rsp+28h] [rbp-38h]
  ULONG dwFlags; // [rsp+30h] [rbp-30h]
  size_t v83; // [rsp+60h] [rbp+0h] BYREF
  PUCHAR v84; // [rsp+68h] [rbp+8h] BYREF
  ULONG v85[2]; // [rsp+70h] [rbp+10h]
  size_t v86; // [rsp+78h] [rbp+18h]
  void *Src; // [rsp+80h] [rbp+20h]
  __int64 v88; // [rsp+88h] [rbp+28h]
  UCHAR *v89; // [rsp+90h] [rbp+30h]
  size_t Size; // [rsp+98h] [rbp+38h]
  __int64 v91; // [rsp+A0h] [rbp+40h]
  UCHAR *v92; // [rsp+A8h] [rbp+48h]
  PUCHAR pbInput; // [rsp+B0h] [rbp+50h]
  int v94; // [rsp+B8h] [rbp+58h]
  PUCHAR v95; // [rsp+C0h] [rbp+60h]
  _QWORD *v96; // [rsp+C8h] [rbp+68h]
  _QWORD *v97; // [rsp+D0h] [rbp+70h]
  _OWORD v98[4]; // [rsp+E0h] [rbp+80h] BYREF
  _OWORD v99[4]; // [rsp+120h] [rbp+C0h] BYREF

  v5 = a2;
  v97 = a4;
  v96 = a3;
  v88 = a2;
  v91 = a1;
  if ( !a5 || *(_DWORD *)a5 )
  {
    SymmetricKey = -2146893785;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      dwFlags = 2544;
LABEL_78:
      *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c";
      LODWORD(pbSecret) = -2146893785;
LABEL_79:
      WPP_SF_sDsd(v58[2], a2, (_DWORD)a3, (unsigned int)"Status", (char)pbSecret, *(__int64 *)cbSecret, dwFlags);
    }
    return (unsigned int)SymmetricKey;
  }
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  LODWORD(a3) = 0;
  while ( (unsigned int)a3 < *(_DWORD *)(a5 + 4) )
  {
    v11 = *(_QWORD *)(a5 + 8);
    LODWORD(a2) = 2 * (_DWORD)a3;
    if ( !*(_QWORD *)(v11 + 16LL * (unsigned int)a3 + 8) || !*(_DWORD *)(v11 + 16LL * (unsigned int)a3) )
    {
      SymmetricKey = -2146893785;
      DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 2558);
      return (unsigned int)SymmetricKey;
    }
    if ( *(_DWORD *)(v11 + 16LL * (unsigned int)a3 + 4) == 20 )
    {
      v7 = *(_OWORD **)(v11 + 16LL * (unsigned int)a3 + 8);
      v8 = *(_DWORD *)(v11 + 16LL * (unsigned int)a3);
      goto LABEL_9;
    }
    if ( *(_DWORD *)(v11 + 16LL * (unsigned int)a3 + 4) == 21 )
    {
      v9 = *(_OWORD **)(v11 + 16LL * (unsigned int)a3 + 8);
      v10 = *(_DWORD *)(v11 + 16LL * (unsigned int)a3);
      LODWORD(a3) = (_DWORD)a3 + 1;
    }
    else
    {
LABEL_9:
      LODWORD(a3) = (_DWORD)a3 + 1;
    }
  }
  if ( !v7 || v8 != 32 || !v9 || v10 != 32 )
  {
    SymmetricKey = -2146893785;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      dwFlags = 2584;
      goto LABEL_78;
    }
    return (unsigned int)SymmetricKey;
  }
  v98[0] = *v7;
  v98[1] = v7[1];
  v98[2] = *v9;
  v98[3] = v9[1];
  v99[0] = *v9;
  v99[1] = v9[1];
  v99[2] = *v7;
  v12 = v7[1];
  v13 = *(_DWORD **)(v5 + 16);
  v99[3] = v12;
  if ( !v13 )
  {
    SymmetricKey = -2146893779;
    DebugTraceError(2148073517LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 2604);
    return (unsigned int)SymmetricKey;
  }
  v14 = (unsigned int)v13[10];
  v15 = v91;
  if ( !(_DWORD)v14 )
  {
    v16 = 0;
    v17 = 0;
    LODWORD(v84) = 0;
    goto LABEL_17;
  }
  v17 = v91 + 16 * (v14 + 1);
  if ( *(_DWORD *)(v17 + 12) )
  {
LABEL_66:
    v16 = *(_DWORD *)(v17 + 8);
    LODWORD(v84) = v16;
    if ( !v16 || !*(_QWORD *)v17 )
    {
      SymmetricKey = -2146893783;
      DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 2630);
      return (unsigned int)SymmetricKey;
    }
LABEL_17:
    v18 = (unsigned int)v13[18];
    if ( (_DWORD)v18 )
    {
      v64 = v15 + 32 * v18 + 272;
      if ( !*(_DWORD *)(v64 + 28) )
      {
        HashEntry = I_GetHashEntry(v18, *(unsigned int *)(v15 + 12), v64);
        SymmetricKey = HashEntry;
        if ( HashEntry < 0 )
        {
          DebugTraceError(
            (unsigned int)HashEntry,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            2651);
          return (unsigned int)SymmetricKey;
        }
        v16 = (unsigned int)v84;
      }
    }
    v19 = *(_DWORD *)(v5 + 8) < 0x302u;
    LODWORD(v86) = v13[17];
    LODWORD(v84) = 0;
    v94 = 0;
    if ( v19 )
    {
      v20 = v13 + 9;
      LODWORD(v83) = v13[9];
    }
    else
    {
      if ( !wcscmp(*((const wchar_t **)v13 + 6), L"ChainingModeGCM") )
      {
        LODWORD(v86) = 0;
        Src = v13 + 9;
        LODWORD(v83) = 4;
        v94 = 1;
LABEL_22:
        Size = v16 + 112;
        v21 = (char *)SafeAllocaAllocateFromHeap(Size);
        v22 = v21;
        if ( !v21 )
        {
          SymmetricKey = -2146893810;
          DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 2690);
          return (unsigned int)SymmetricKey;
        }
        v89 = 0;
        v23 = 0;
        memset(v21, 0, Size);
        *((_DWORD *)v22 + 1) = 1936944179;
        *(_DWORD *)v22 = v16 + 112;
        *((_DWORD *)v22 + 2) = *(_DWORD *)(v5 + 8);
        v24 = (_DWORD)v84 + 112;
        *((_QWORD *)v22 + 2) = v13;
        v25 = v16 + v24;
        *((_DWORD *)v22 + 6) = 1;
        v85[0] = v25;
        Size = v25;
        v26 = (char *)SafeAllocaAllocateFromHeap((unsigned int)v25);
        v27 = v26;
        if ( !v26 )
        {
          SymmetricKey = -1073741801;
          v62 = 2707;
          v66 = 3221225495LL;
          goto LABEL_106;
        }
        memset(v26, 0, Size);
        LODWORD(v29) = (_DWORD)v84;
        *(_DWORD *)v27 = v85[0];
        v30 = v88;
        *((_DWORD *)v27 + 1) = 1936944179;
        *((_DWORD *)v27 + 2) = *(_DWORD *)(v30 + 8);
        *((_QWORD *)v27 + 2) = v13;
        *((_DWORD *)v27 + 6) = 0;
        if ( (_DWORD)v29 )
        {
          v59 = *(_DWORD *)Src;
          if ( *(_DWORD *)Src <= 1u || v59 > (unsigned int)v29 )
          {
            SymmetricKey = -2146893779;
            v62 = 2725;
            v66 = 2148073517LL;
            goto LABEL_106;
          }
          *((_DWORD *)v27 + 12) = v29;
          *((_QWORD *)v27 + 5) = &v27[v16 + 112];
          v60 = (unsigned int)v29 - v59;
          *((_DWORD *)v27 + 13) = v60;
          KeyMaterial = BCryptGenRandom(0, (PUCHAR)&v27[v60 + 112 + v16], v59, 2u);
          SymmetricKey = KeyMaterial;
          if ( KeyMaterial < 0 )
          {
            v62 = 2746;
LABEL_105:
            v66 = (unsigned int)KeyMaterial;
LABEL_106:
            DebugTraceError(v66, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v62);
            goto LABEL_54;
          }
        }
        v6 = 2 * (v13[8] + v86 + v83);
        v31 = v6 + 16;
        v32 = v6 + 16;
        if ( v6 == -16 )
          goto LABEL_165;
        if ( v31 > (unsigned __int64)g_ulMaxStackAllocSize )
          goto LABEL_165;
        v33 = v31 + g_ulAdditionalProbeSize + 8;
        if ( v33 < v31 || !(unsigned int)VerifyStackAvailable(v33) )
          goto LABEL_165;
        LODWORD(v29) = -16;
        v34 = v32 + 23;
        if ( v32 + 23 <= v32 + 8 )
          v34 = 0xFFFFFFFFFFFFFF0LL;
        v35 = v34 & 0xFFFFFFFFFFFFFFF0uLL;
        v36 = alloca(v35);
        v37 = alloca(v35);
        v23 = (UCHAR *)&v83;
        if ( v79 == (_BYTE *)-96LL || (LODWORD(v83) = 1801679955, (v23 = (UCHAR *)&v84) == 0) )
        {
LABEL_165:
          if ( v32 + 8 >= v32 )
          {
            v67 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
            v23 = v67;
            if ( v67 )
            {
              *(_DWORD *)v67 = 1885431112;
              v23 = v67 + 8;
            }
          }
        }
        if ( !v23 )
        {
          SymmetricKey = -2146893810;
          v52 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            dwFlags = 2767;
            *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c";
            LODWORD(pbSecret) = -2146893810;
LABEL_53:
            WPP_SF_sDsd(v52[2], v29, v28, (unsigned int)"Status", (char)pbSecret, *(__int64 *)cbSecret, dwFlags);
            goto LABEL_54;
          }
          goto LABEL_54;
        }
        v38 = *(_DWORD *)(v88 + 8);
        if ( v38 < 0x301 )
        {
          v68 = (v6 >> 4) + 1;
          if ( (v6 & 0xF) == 0 )
            v68 = v6 >> 4;
          dwFlags = 16 * v68;
          *(_QWORD *)cbSecret = v23;
          KeyMaterial = Ssl3GenerateKeyMaterial(v91, v88 + 28, 48, v99);
          SymmetricKey = KeyMaterial;
          if ( KeyMaterial < 0 )
          {
            v62 = 2813;
            goto LABEL_105;
          }
        }
        else
        {
          SymmetricKey = Tls1Prf(
                           v38,
                           *((const WCHAR **)v13 + 13),
                           *((_QWORD *)v13 + 17),
                           (UCHAR *)(v88 + 28),
                           0x30u,
                           (__int64)"key expansion",
                           13,
                           (__int64)v99,
                           64,
                           (__int64)v23,
                           v6);
          if ( SymmetricKey < 0 )
          {
            v52 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              dwFlags = 2788;
              goto LABEL_83;
            }
            goto LABEL_54;
          }
        }
        v40 = v13[32] == 0;
        v41 = (unsigned int)v13[8];
        v28 = (unsigned int)v86;
        v42 = v83;
        *(_QWORD *)v85 = v41;
        v43 = &v23[(unsigned int)v86];
        v44 = &v43[(unsigned int)v86];
        v95 = v43;
        v45 = &v44[v41];
        v84 = v44;
        v46 = &v44[v41 + v41];
        Size = (size_t)&v44[v41];
        pbInput = v46;
        Src = &v46[(unsigned int)v83];
        if ( v40 )
        {
LABEL_37:
          v29 = *(unsigned int *)(v88 + 24);
          if ( (_DWORD)v29 )
          {
            Size = (size_t)v23;
            pbInput = v46;
          }
          else
          {
            Size = (size_t)v43;
            v43 = v23;
            pbInput = (PUCHAR)Src;
            Src = v46;
          }
          v47 = v84;
          if ( !(_DWORD)v29 )
          {
            v47 = v45;
            v45 = v84;
          }
          v92 = v45;
          v95 = v47;
          if ( (_DWORD)v28 )
          {
            *((_DWORD *)v22 + 26) = v28;
            v56 = v28;
            memmove(v22 + 56, v43, v28);
            v57 = (const void *)Size;
            *((_DWORD *)v27 + 26) = v86;
            memmove(v27 + 56, v57, v56);
          }
          else
          {
            if ( !v94 )
              goto LABEL_45;
            v48 = Src;
            *((_DWORD *)v22 + 26) = v42;
            memmove(v22 + 56, v48, v42);
            v49 = pbInput;
            *((_DWORD *)v27 + 26) = v42;
            memmove(v27 + 56, v49, v42);
            LODWORD(v83) = 0;
          }
          v41 = *(_QWORD *)v85;
          v45 = v92;
LABEL_45:
          if ( !v13[10] )
          {
LABEL_49:
            SymmetricKey = 0;
            v51 = v89;
            *v96 = v22;
            *v97 = v27;
LABEL_57:
            v53 = v6;
            v54 = v23;
            if ( v6 )
            {
              do
              {
                *v54++ = 0;
                --v53;
              }
              while ( v53 );
            }
            if ( *((_DWORD *)v23 - 2) == 1885431112 )
              ((void (__fastcall *)(UCHAR *, __int64, size_t, __int64))g_pfnFree)(v23 - 8, v29, v28, v41);
LABEL_61:
            if ( v51 && *((_DWORD *)v51 - 2) == 1885431112 )
              ((void (__fastcall *)(UCHAR *))g_pfnFree)(v51 - 8);
            return (unsigned int)SymmetricKey;
          }
          SymmetricKey = BCryptGenerateSymmetricKey(
                           *(BCRYPT_ALG_HANDLE *)v17,
                           (BCRYPT_KEY_HANDLE *)v22 + 4,
                           (PUCHAR)v22 + 112,
                           *(_DWORD *)(v17 + 8),
                           v45,
                           v41,
                           0);
          if ( SymmetricKey < 0 )
          {
            v52 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_54;
            dwFlags = 3074;
          }
          else
          {
            SymmetricKey = BCryptGenerateSymmetricKey(
                             *(BCRYPT_ALG_HANDLE *)v17,
                             (BCRYPT_KEY_HANDLE *)v27 + 4,
                             (PUCHAR)v27 + 112,
                             *(_DWORD *)(v17 + 8),
                             v95,
                             v85[0],
                             0);
            if ( SymmetricKey >= 0 )
            {
              v50 = v83;
              if ( (unsigned int)v83 <= 1 )
                goto LABEL_49;
              SymmetricKey = BCryptSetProperty(*((BCRYPT_HANDLE *)v22 + 4), L"IV", (PUCHAR)Src, v83, 0);
              if ( SymmetricKey < 0 )
              {
                v52 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  dwFlags = 3104;
                  goto LABEL_83;
                }
LABEL_54:
                v51 = v89;
                MSCryptFree(v22);
                if ( v27 )
                  MSCryptFree(v27);
                if ( !v23 )
                  goto LABEL_61;
                goto LABEL_57;
              }
              KeyMaterial = BCryptSetProperty(*((BCRYPT_HANDLE *)v27 + 4), L"IV", pbInput, v50, 0);
              SymmetricKey = KeyMaterial;
              if ( KeyMaterial >= 0 )
                goto LABEL_49;
              v62 = 3117;
              goto LABEL_105;
            }
            v52 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_54;
            dwFlags = 3089;
          }
LABEL_83:
          *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c";
          LODWORD(pbSecret) = SymmetricKey;
          goto LABEL_53;
        }
        v69 = 8;
        if ( v13[6] != 26113 )
          v69 = 16;
        v70 = 0;
        *(_QWORD *)v85 = v69;
        v89 = 0;
        v71 = (unsigned int)(2 * v69);
        if ( v71 <= g_ulMaxStackAllocSize && v71 + g_ulAdditionalProbeSize + 8 >= v71 )
        {
          if ( (unsigned int)VerifyStackAvailable(v71 + g_ulAdditionalProbeSize + 8) )
          {
            v72 = v71 + 23;
            if ( v71 + 23 <= v71 + 8 )
              v72 = 0xFFFFFFFFFFFFFF0LL;
            v69 = v72 & 0xFFFFFFFFFFFFFFF0uLL;
            v73 = alloca(v69);
            v44 = v84;
            v74 = alloca(v69);
            LODWORD(v69) = v85[0];
            v70 = (char *)&v83;
            v89 = (UCHAR *)&v83;
            if ( v79 != (_BYTE *)-96LL )
            {
              LODWORD(v83) = 1801679955;
              v70 = (char *)&v84;
              v89 = (UCHAR *)&v84;
              if ( &v84 )
              {
LABEL_140:
                if ( !v70 )
                {
                  SymmetricKey = -2146893810;
                  v62 = 2862;
                  v66 = 2148073486LL;
                  goto LABEL_106;
                }
                v76 = (unsigned int)v13[8];
                v92 = (UCHAR *)&v70[(unsigned int)v69];
                v77 = *(_DWORD *)(v88 + 8);
                if ( v77 < 0x301 )
                {
                  dwFlags = v69;
                  *(_QWORD *)cbSecret = v70;
                  KeyMaterial = Ssl3ComputeExportKeys(v91, v44, v76, v98);
                  SymmetricKey = KeyMaterial;
                  if ( KeyMaterial < 0 )
                  {
                    v62 = 2937;
                    goto LABEL_105;
                  }
                  v78 = (unsigned int)v13[8];
                  dwFlags = v85[0];
                  *(_QWORD *)cbSecret = v92;
                  KeyMaterial = Ssl3ComputeExportKeys(v91, Size, v78, v99);
                  SymmetricKey = KeyMaterial;
                  if ( KeyMaterial < 0 )
                  {
                    v62 = 2951;
                    goto LABEL_105;
                  }
                  v42 = v83;
                  if ( (unsigned int)v83 <= 1 )
                    goto LABEL_160;
                  dwFlags = v83;
                  *(_QWORD *)cbSecret = pbInput;
                  KeyMaterial = Ssl3ComputeExportKeys(v91, 0, 0, v98);
                  SymmetricKey = KeyMaterial;
                  if ( KeyMaterial < 0 )
                  {
                    v62 = 2967;
                    goto LABEL_105;
                  }
                  dwFlags = v83;
                  *(_QWORD *)cbSecret = Src;
                  KeyMaterial = Ssl3ComputeExportKeys(v91, 0, 0, v99);
                  SymmetricKey = KeyMaterial;
                  if ( KeyMaterial < 0 )
                  {
                    v62 = 2981;
                    goto LABEL_105;
                  }
                }
                else
                {
                  KeyMaterial = Tls1Prf(
                                  v77,
                                  *((const WCHAR **)v13 + 13),
                                  *((_QWORD *)v13 + 17),
                                  v44,
                                  v76,
                                  (__int64)"client write key",
                                  16,
                                  (__int64)v98,
                                  64,
                                  (__int64)v70,
                                  v69);
                  SymmetricKey = KeyMaterial;
                  if ( KeyMaterial < 0 )
                  {
                    v62 = 2884;
                    goto LABEL_105;
                  }
                  KeyMaterial = Tls1Prf(
                                  *(_DWORD *)(v88 + 8),
                                  *((const WCHAR **)v13 + 13),
                                  *((_QWORD *)v13 + 17),
                                  (UCHAR *)Size,
                                  v13[8],
                                  (__int64)"server write key",
                                  16,
                                  (__int64)v98,
                                  64,
                                  (__int64)v92,
                                  v85[0]);
                  SymmetricKey = KeyMaterial;
                  if ( KeyMaterial < 0 )
                  {
                    v62 = 2901;
                    goto LABEL_105;
                  }
                  v42 = v83;
                  if ( (unsigned int)v83 <= 1 )
                    goto LABEL_160;
                  KeyMaterial = Tls1Prf(
                                  *(_DWORD *)(v88 + 8),
                                  *((const WCHAR **)v13 + 13),
                                  *((_QWORD *)v13 + 17),
                                  0,
                                  0,
                                  (__int64)"IV block",
                                  8,
                                  (__int64)v98,
                                  64,
                                  (__int64)pbInput,
                                  2 * (int)v83);
                  SymmetricKey = KeyMaterial;
                  if ( KeyMaterial < 0 )
                  {
                    v62 = 2920;
                    goto LABEL_105;
                  }
                }
                v42 = v83;
LABEL_160:
                v45 = v92;
                v28 = (unsigned int)v86;
                v41 = *(_QWORD *)v85;
                v46 = pbInput;
                v43 = v95;
                v84 = v89;
                goto LABEL_37;
              }
            }
          }
          else
          {
            LODWORD(v69) = v85[0];
            v44 = v84;
            v70 = (char *)v89;
          }
        }
        if ( v71 + 8 >= v71 )
        {
          v75 = (char *)((__int64 (__fastcall *)(unsigned __int64, UCHAR *))g_pfnAllocate)(v71 + 8, v44);
          LODWORD(v69) = v85[0];
          v70 = v75;
          v44 = v84;
          v89 = (UCHAR *)v75;
          if ( v75 )
          {
            v70 = v75 + 8;
            *(_DWORD *)v75 = 1885431112;
            v89 = (UCHAR *)(v75 + 8);
          }
        }
        goto LABEL_140;
      }
      v63 = v13[9] <= 1u;
      v20 = v13 + 9;
      LODWORD(v83) = 0;
      Src = v13 + 9;
      if ( !v63 )
      {
        LODWORD(v84) = 128;
        goto LABEL_21;
      }
    }
    Src = v20;
LABEL_21:
    v5 = v88;
    goto LABEL_22;
  }
  SymmetricKey = I_GetCipherEntry(v14, *(unsigned int *)(v91 + 12), v17);
  if ( SymmetricKey >= 0 )
  {
    v15 = v91;
    goto LABEL_66;
  }
  v58 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    dwFlags = 2621;
    *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c";
    LODWORD(pbSecret) = SymmetricKey;
    goto LABEL_79;
  }
  return (unsigned int)SymmetricKey;
}

```

## disassembly

```asm
0x180006b60  push    rbp
0x180006b62  push    rbx
0x180006b63  push    rsi
0x180006b64  push    rdi
0x180006b65  push    r12
0x180006b67  push    r13
0x180006b69  push    r14
0x180006b6b  push    r15
0x180006b6d  sub     rsp, 178h
0x180006b74  lea     rbp, [rsp+60h]
0x180006b79  mov     rax, cs:__security_cookie
0x180006b80  xor     rax, rbp
0x180006b83  mov     [rbp+150h+var_50], rax
0x180006b8a  mov     r11, [rbp+150h+arg_20]
0x180006b91  mov     r14, rdx
0x180006b94  mov     [rbp+150h+var_E0], r9
0x180006b98  mov     [rbp+150h+var_E8], r8
0x180006b9c  mov     [rbp+150h+var_128], rdx
0x180006ba0  mov     [rbp+150h+var_110], rcx
0x180006ba4  test    r11, r11
0x180006ba7  jz      loc_18000719D
0x180006bad  cmp     dword ptr [r11], 0
0x180006bb1  jnz     loc_18000719D
0x180006bb7  mov     esi, [r11+4]
0x180006bbb  xor     r13d, r13d
0x180006bbe  mov     edi, r13d
0x180006bc1  mov     r15d, r13d
0x180006bc4  mov     ebx, r13d
0x180006bc7  mov     r12d, r13d
0x180006bca  mov     r8d, r13d
0x180006bcd  cmp     r8d, esi
0x180006bd0  jnb     short loc_180006C0F
0x180006bd2  mov     rax, [r11+8]
0x180006bd6  mov     edx, r8d
0x180006bd9  add     rdx, rdx
0x180006bdc  mov     r10, [rax+rdx*8+8]
0x180006be1  test    r10, r10
0x180006be4  jz      loc_180007467
0x180006bea  mov     r9d, [rax+rdx*8]
0x180006bee  test    r9d, r9d
0x180006bf1  jz      loc_180007467
0x180006bf7  mov     ecx, [rax+rdx*8+4]
0x180006bfb  sub     ecx, 14h
0x180006bfe  jnz     loc_180007108
0x180006c04  mov     rdi, r10
0x180006c07  mov     r15d, r9d
0x180006c0a  inc     r8d
0x180006c0d  jmp     short loc_180006BCD
0x180006c0f  test    rdi, rdi
0x180006c12  jz      loc_180007406
0x180006c18  cmp     r15d, 20h ; ' '
0x180006c1c  jnz     loc_180007406
0x180006c22  test    rbx, rbx
0x180006c25  jz      loc_180007406
0x180006c2b  cmp     r12d, r15d
0x180006c2e  jnz     loc_180007406
0x180006c34  movups  xmm0, xmmword ptr [rdi]
0x180006c37  movaps  [rbp+150h+var_D0], xmm0
0x180006c3e  movups  xmm1, xmmword ptr [rdi+10h]
0x180006c42  movaps  [rbp+150h+var_C0], xmm1
0x180006c49  movups  xmm0, xmmword ptr [rbx]
0x180006c4c  movaps  [rbp+150h+var_B0], xmm0
0x180006c53  movups  xmm1, xmmword ptr [rbx+10h]
0x180006c57  movaps  [rbp+150h+var_A0], xmm1
0x180006c5e  movups  xmm0, xmmword ptr [rbx]
0x180006c61  movaps  [rbp+150h+var_90], xmm0
0x180006c68  movups  xmm1, xmmword ptr [rbx+10h]
0x180006c6c  movaps  [rbp+150h+var_80], xmm1
0x180006c73  movups  xmm0, xmmword ptr [rdi]
0x180006c76  movaps  [rbp+150h+var_70], xmm0
0x180006c7d  movups  xmm1, xmmword ptr [rdi+10h]
0x180006c81  mov     rdi, [r14+10h]
0x180006c85  movaps  [rbp+150h+var_60], xmm1
0x180006c8c  test    rdi, rdi
0x180006c8f  jz      loc_18000748F
0x180006c95  mov     ecx, [rdi+28h]
0x180006c98  mov     rdx, [rbp+150h+var_110]
0x180006c9c  test    ecx, ecx
0x180006c9e  jnz     loc_18000709F
0x180006ca4  mov     ebx, r13d
0x180006ca7  mov     r12, r13
0x180006caa  mov     dword ptr [rbp+150h+var_148], ebx
0x180006cad  mov     ecx, [rdi+48h]
0x180006cb0  test    ecx, ecx
0x180006cb2  jnz     loc_1800072E0
0x180006cb8  cmp     dword ptr [r14+8], 302h
0x180006cc0  mov     esi, [rdi+44h]
0x180006cc3  mov     dword ptr [rbp+150h+var_138], esi
0x180006cc6  mov     dword ptr [rbp+150h+var_148], r13d
0x180006cca  mov     [rbp+150h+var_F8], r13d
0x180006cce  jnb     loc_18000711F
0x180006cd4  mov     esi, [rdi+24h]
0x180006cd7  lea     r14, [rdi+24h]
0x180006cdb  mov     dword ptr [rbp+150h+var_150], esi
0x180006cde  mov     [rbp+150h+Src], r14
0x180006ce2  mov     r14, [rbp+150h+var_128]
0x180006ce6  lea     eax, [rbx+70h]
0x180006ce9  mov     ecx, eax
0x180006ceb  mov     [rbp+150h+Size], rax
0x180006cef  call    SafeAllocaAllocateFromHeap
0x180006cf4  mov     r15, rax
0x180006cf7  test    rax, rax
0x180006cfa  jz      loc_1800074BF
0x180006d00  mov     r8, [rbp+150h+Size]; Size
0x180006d04  xor     edx, edx; Val
0x180006d06  mov     rcx, rax; void *
0x180006d09  mov     [rbp+150h+var_120], r13
0x180006d0d  mov     rsi, r13
0x180006d10  call    memset
0x180006d15  lea     eax, [rbx+70h]
0x180006d18  mov     dword ptr [r15+4], 73736C33h
0x180006d20  mov     [r15], eax
0x180006d23  mov     eax, [r14+8]
0x180006d27  mov     [r15+8], eax
0x180006d2b  mov     eax, dword ptr [rbp+150h+var_148]
0x180006d2e  add     eax, 70h ; 'p'
0x180006d31  mov     [r15+10h], rdi
0x180006d35  add     eax, ebx
0x180006d37  mov     dword ptr [r15+18h], 1
0x180006d3f  mov     ecx, eax
0x180006d41  mov     [rbp+150h+var_140], eax
0x180006d44  mov     [rbp+150h+Size], rax
0x180006d48  call    SafeAllocaAllocateFromHeap
0x180006d4d  mov     r14, rax
0x180006d50  test    rax, rax
0x180006d53  jz      loc_1800074E7
0x180006d59  mov     r8, [rbp+150h+Size]; Size
0x180006d5d  xor     edx, edx; Val
0x180006d5f  mov     rcx, rax; void *
0x180006d62  call    memset
0x180006d67  mov     eax, [rbp+150h+var_140]
0x180006d6a  mov     edx, dword ptr [rbp+150h+var_148]
0x180006d6d  mov     [r14], eax
0x180006d70  mov     rax, [rbp+150h+var_128]
0x180006d74  mov     dword ptr [r14+4], 73736C33h
0x180006d7c  mov     eax, [rax+8]
0x180006d7f  mov     [r14+8], eax
0x180006d83  mov     [r14+10h], rdi
0x180006d87  mov     [r14+18h], esi
0x180006d8b  test    edx, edx
0x180006d8d  jnz     loc_18000725D
0x180006d93  mov     eax, dword ptr [rbp+150h+var_150]
0x180006d96  add     eax, dword ptr [rbp+150h+var_138]
0x180006d99  add     eax, [rdi+20h]
0x180006d9c  lea     r13d, [rax+rax]
0x180006da0  lea     eax, [r13+10h]
0x180006da4  mov     ebx, eax
0x180006da6  test    eax, eax
0x180006da8  jz      loc_180007511
0x180006dae  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180006db5  ja      loc_180007511
0x180006dbb  mov     rcx, cs:g_ulAdditionalProbeSize
0x180006dc2  add     rcx, 8
0x180006dc6  add     rcx, rbx
0x180006dc9  cmp     rcx, rbx
0x180006dcc  jb      loc_180007511
0x180006dd2  call    VerifyStackAvailable
0x180006dd7  test    eax, eax
0x180006dd9  jz      loc_180007511
0x180006ddf  lea     rax, [rbx+8]
0x180006de3  mov     rdx, 0FFFFFFFFFFFFFF0h
0x180006ded  lea     rcx, [rax+0Fh]
0x180006df1  cmp     rcx, rax
0x180006df4  ja      short loc_180006DF9
0x180006df6  mov     rcx, rdx
0x180006df9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180006dfd  mov     rax, rcx
0x180006e00  call    _alloca_probe
0x180006e05  sub     rsp, rcx
0x180006e08  lea     rsi, [rsp+1B0h+var_150]
0x180006e0d  test    rsi, rsi
0x180006e10  jz      loc_180007511
0x180006e16  mov     dword ptr [rsi], 6B637453h
0x180006e1c  add     rsi, 8
0x180006e20  jz      loc_180007511
0x180006e26  test    rsi, rsi
0x180006e29  jz      loc_180006FE4
0x180006e2f  mov     rax, [rbp+150h+var_128]
0x180006e33  mov     ecx, [rax+8]
0x180006e36  lea     rdx, [rax+1Ch]
0x180006e3a  cmp     ecx, 301h
0x180006e40  jb      loc_180007545
0x180006e46  mov     r8, [rdi+88h]
0x180006e4d  lea     rax, [rbp+150h+var_90]
0x180006e54  mov     [rsp+1B0h+var_160], r13d
0x180006e59  mov     r9, rdx
0x180006e5c  mov     rdx, [rdi+68h]
0x180006e60  mov     [rsp+1B0h+var_168], rsi
0x180006e65  mov     [rsp+1B0h+var_170], 40h ; '@'
0x180006e6d  mov     [rsp+1B0h+var_178], rax
0x180006e72  lea     rax, aKeyExpansion; "key expansion"
0x180006e79  mov     [rsp+1B0h+dwFlags], 0Dh
0x180006e81  mov     qword ptr [rsp+1B0h+cbSecret], rax
0x180006e86  mov     dword ptr [rsp+1B0h+pbSecret], 30h ; '0'
0x180006e8e  call    Tls1Prf
0x180006e93  mov     ebx, eax
0x180006e95  test    eax, eax
0x180006e97  js      loc_180007439
0x180006e9d  cmp     dword ptr [rdi+80h], 0
0x180006ea4  mov     r9d, [rdi+20h]
0x180006ea8  mov     r8d, dword ptr [rbp+150h+var_138]; Size
0x180006eac  mov     ebx, dword ptr [rbp+150h+var_150]
0x180006eaf  mov     qword ptr [rbp+150h+var_140], r9
0x180006eb3  lea     r11, [r8+rsi]
0x180006eb7  lea     rdx, [r11+r8]
0x180006ebb  mov     [rbp+150h+var_F0], r11
0x180006ebf  lea     rcx, [rdx+r9]
0x180006ec3  mov     [rbp+150h+var_148], rdx
0x180006ec7  lea     r10, [rcx+r9]
0x180006ecb  mov     [rbp+150h+Size], rcx
0x180006ecf  lea     rax, [r10+rbx]
0x180006ed3  mov     [rbp+150h+pbInput], r10
0x180006ed7  mov     [rbp+150h+Src], rax
0x180006edb  jnz     loc_18000758C
0x180006ee1  mov     rax, [rbp+150h+var_128]
0x180006ee5  mov     edx, [rax+18h]
0x180006ee8  test    edx, edx
0x180006eea  jz      loc_180007156
0x180006ef0  mov     [rbp+150h+Size], rsi
0x180006ef4  mov     [rbp+150h+pbInput], r10
0x180006ef8  mov     rax, [rbp+150h+var_148]
0x180006efc  test    edx, edx
0x180006efe  cmovz   rax, rcx
0x180006f02  cmovz   rcx, [rbp+150h+var_148]
0x180006f07  mov     [rbp+150h+var_108], rcx
0x180006f0b  mov     [rbp+150h+var_F0], rax
0x180006f0f  test    r8d, r8d
0x180006f12  jnz     loc_18000716E
0x180006f18  cmp     [rbp+150h+var_F8], r8d
0x180006f1c  jz      short loc_180006F55
0x180006f1e  mov     rdx, [rbp+150h+Src]; Src
0x180006f22  lea     rcx, [r15+38h]; void *
0x180006f26  mov     r8d, ebx; Size
0x180006f29  mov     [r15+68h], ebx
0x180006f2d  call    memmove
0x180006f32  mov     rdx, [rbp+150h+pbInput]; Src
0x180006f36  lea     rcx, [r14+38h]; void *
0x180006f3a  mov     r8d, ebx; Size
0x180006f3d  mov     [r14+68h], ebx
0x180006f41  call    memmove
0x180006f46  mov     dword ptr [rbp+150h+var_150], 0
0x180006f4d  mov     r9, qword ptr [rbp+150h+var_140]
0x180006f51  mov     rcx, [rbp+150h+var_108]
0x180006f55  cmp     dword ptr [rdi+28h], 0
0x180006f59  jz      short loc_180006FCE
0x180006f5b  xor     edi, edi
0x180006f5d  lea     rdx, [r15+20h]; phKey
0x180006f61  mov     [rsp+1B0h+dwFlags], edi; dwFlags
0x180006f65  lea     r8, [r15+70h]; pbKeyObject
0x180006f69  mov     [rsp+1B0h+cbSecret], r9d; cbSecret
0x180006f6e  mov     r9d, [r12+8]; cbKeyObject
0x180006f73  mov     [rsp+1B0h+pbSecret], rcx; pbSecret
0x180006f78  mov     rcx, [r12]; hAlgorithm
0x180006f7c  call    cs:__imp_BCryptGenerateSymmetricKey
0x180006f82  mov     ebx, eax
0x180006f84  test    eax, eax
0x180006f86  js      loc_180007232
0x180006f8c  mov     rax, qword ptr [rbp+150h+var_140]
0x180006f90  lea     rdx, [r14+20h]; phKey
0x180006f94  mov     r9d, [r12+8]; cbKeyObject
0x180006f99  lea     r8, [r14+70h]; pbKeyObject
0x180006f9d  mov     rcx, [r12]; hAlgorithm
0x180006fa1  mov     [rsp+1B0h+dwFlags], edi; dwFlags
0x180006fa5  mov     [rsp+1B0h+cbSecret], eax; cbSecret
0x180006fa9  mov     rax, [rbp+150h+var_F0]
0x180006fad  mov     [rsp+1B0h+pbSecret], rax; pbSecret
0x180006fb2  call    cs:__imp_BCryptGenerateSymmetricKey
0x180006fb8  mov     ebx, eax
0x180006fba  test    eax, eax
0x180006fbc  js      loc_1800071F4
0x180006fc2  mov     edi, dword ptr [rbp+150h+var_150]
0x180006fc5  cmp     edi, 1
0x180006fc8  ja      loc_18000736B
0x180006fce  mov     rax, [rbp+150h+var_E8]
0x180006fd2  xor     ebx, ebx
0x180006fd4  mov     rdi, [rbp+150h+var_120]
0x180006fd8  mov     [rax], r15
0x180006fdb  mov     rax, [rbp+150h+var_E0]
0x180006fdf  mov     [rax], r14
0x180006fe2  jmp     short loc_180007048
0x180006fe4  mov     ebx, 8009000Eh
0x180006fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ff0  lea     rax, WPP_GLOBAL_Control
0x180006ff7  cmp     rcx, rax
0x180006ffa  jz      short loc_18000702E
0x180006ffc  test    byte ptr [rcx+1Ch], 1
0x180007000  jz      short loc_18000702E
0x180007002  mov     [rsp+1B0h+dwFlags], 0ACFh
0x18000700a  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007011  mov     qword ptr [rsp+1B0h+cbSecret], rax
0x180007016  mov     dword ptr [rsp+1B0h+pbSecret], 8009000Eh
0x18000701e  mov     rcx, [rcx+10h]
0x180007022  lea     r9, aStatus; "Status"
0x180007029  call    WPP_SF_sDsd
0x18000702e  mov     rdi, [rbp+150h+var_120]
0x180007032  mov     rcx, r15
0x180007035  call    MSCryptFree
0x18000703a  test    r14, r14
0x18000703d  jnz     loc_1800078F9
0x180007043  test    rsi, rsi
  ... truncated ...
```
