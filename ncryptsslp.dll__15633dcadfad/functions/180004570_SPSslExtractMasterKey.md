# SPSslExtractMasterKey

- ea: `0x180004570`
- end: `0x18000522b`
- name: `SPSslExtractMasterKey`
- size: `3259`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001acc`
- `0x180003ef0`
- `0x180004570`
- `0x180005860`
- `0x18000b594`
- `0x18000b654`
- `0x1800183d0`
- `0x180020cb4`
- `0x180024fb0`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x180004d77`
- `bcrypt!BCryptSetProperty` at `0x180004d9b`
- `bcrypt!BCryptSetProperty` at `0x180004d77`
- `bcrypt!BCryptSetProperty` at `0x180004d9b`
- `bcrypt!BCryptHashData` at `0x1800047a7`
- `bcrypt!BCryptHashData` at `0x1800047a7`
- `bcrypt!BCryptKeyDerivation` at `0x1800049e7`
- `bcrypt!BCryptKeyDerivation` at `0x1800049e7`
- `bcrypt!BCryptCreateHash` at `0x18000478a`
- `bcrypt!BCryptCreateHash` at `0x18000478a`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180004d35`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180004d35`
- `bcrypt!BCryptFinishHash` at `0x1800047ce`
- `bcrypt!BCryptFinishHash` at `0x1800047ce`
- `bcrypt!BCryptDestroyKey` at `0x1800051fc`
- `bcrypt!BCryptDestroyKey` at `0x1800051fc`
- `bcrypt!BCryptDestroyHash` at `0x180004851`
- `bcrypt!BCryptDestroyHash` at `0x180004851`
- `ntdll!RtlFreeHeap` at `0x18000486e`
- `ntdll!RtlFreeHeap` at `0x180004b3f`
- `ntdll!RtlFreeHeap` at `0x180004c7a`
- `ntdll!RtlFreeHeap` at `0x180004caf`
- `ntdll!RtlFreeHeap` at `0x180004ccc`
- `ntdll!RtlFreeHeap` at `0x180005070`
- `ntdll!RtlFreeHeap` at `0x1800051ea`
- `ntdll!RtlFreeHeap` at `0x18000486e`
- `ntdll!RtlFreeHeap` at `0x180004b3f`
- `ntdll!RtlFreeHeap` at `0x180004c7a`
- `ntdll!RtlFreeHeap` at `0x180004caf`
- `ntdll!RtlFreeHeap` at `0x180004ccc`
- `ntdll!RtlFreeHeap` at `0x180005070`
- `ntdll!RtlFreeHeap` at `0x1800051ea`
- `ntdll!RtlAllocateHeap` at `0x1800046b0`
- `ntdll!RtlAllocateHeap` at `0x180004758`
- `ntdll!RtlAllocateHeap` at `0x18000488f`
- `ntdll!RtlAllocateHeap` at `0x18000494c`
- `ntdll!RtlAllocateHeap` at `0x180004b60`
- `ntdll!RtlAllocateHeap` at `0x180004b96`
- `ntdll!RtlAllocateHeap` at `0x1800046b0`
- `ntdll!RtlAllocateHeap` at `0x180004758`
- `ntdll!RtlAllocateHeap` at `0x18000488f`
- `ntdll!RtlAllocateHeap` at `0x18000494c`
- `ntdll!RtlAllocateHeap` at `0x180004b60`
- `ntdll!RtlAllocateHeap` at `0x180004b96`

## string_xrefs

- `0x1800046d4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800047e1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000481f`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180004a1d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180004aea`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180004c22`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180004de6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180004f1c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800050aa`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180005162`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000519a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180004e2e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180004e83`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180004ec8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180004fa9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005052`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005110`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800051b9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExtractMasterKey(_DWORD *a1, _DWORD *a2, _QWORD *a3)
{
  _DWORD *v3; // r15
  _DWORD *v4; // r14
  __int64 v5; // rsi
  const wchar_t *v6; // rsi
  const wchar_t *v7; // r13
  __int64 i; // rbx
  const wchar_t **v9; // rax
  __int64 *v10; // rdi
  unsigned int v11; // edi
  SIZE_T v12; // rsi
  int v13; // r8d
  UCHAR *v14; // rbx
  UCHAR *Heap; // r12
  const wchar_t *v16; // rdx
  __int64 j; // rbx
  const wchar_t **v18; // rax
  BCRYPT_ALG_HANDLE *v19; // rdi
  ULONG v20; // ebx
  int v21; // edx
  int v22; // r8d
  int v23; // edx
  int v24; // r8d
  NTSTATUS v25; // r13d
  NTSTATUS HashEntry; // eax
  __int16 v27; // r14
  NTSTATUS v28; // eax
  size_t v29; // rdx
  __int64 v30; // r13
  char *v31; // rdi
  int v32; // edx
  int v33; // r8d
  unsigned __int8 v34; // r12
  __int64 v35; // r14
  _BYTE *v36; // rax
  char v37; // ch
  _BYTE *v38; // rdi
  __int64 v39; // rbx
  ULONG cbSecret; // r12d
  size_t v41; // r8
  _BYTE *v42; // rdi
  int v43; // edx
  int v44; // r8d
  _BYTE *v45; // rcx
  void *pbSecret; // r14
  _BYTE *v47; // rax
  PVOID v48; // rax
  char *v49; // rax
  int v50; // edx
  int v51; // r8d
  __int64 v52; // rbx
  wchar_t *v53; // rbx
  __int64 HashInfoFromAlgorithmName; // rax
  PVOID v55; // rdx
  _BYTE *k; // rax
  __int64 v58; // r9
  __int64 v60; // r9
  __int64 v61; // rcx
  _BYTE *v62; // rax
  __int64 v63; // rcx
  __int64 v64; // r9
  __int64 v65; // rcx
  __int64 v66; // r9
  char dwFlags; // [rsp+30h] [rbp-41h]
  char dwFlagsa; // [rsp+30h] [rbp-41h]
  UCHAR *pbOutput; // [rsp+40h] [rbp-31h]
  int v70; // [rsp+48h] [rbp-29h] BYREF
  char v71; // [rsp+4Eh] [rbp-23h]
  int v72; // [rsp+50h] [rbp-21h]
  PVOID v73; // [rsp+58h] [rbp-19h]
  char *v74; // [rsp+60h] [rbp-11h]
  _DWORD v75[2]; // [rsp+68h] [rbp-9h] BYREF
  PVOID v76; // [rsp+70h] [rbp-1h]
  PVOID P; // [rsp+78h] [rbp+7h]
  _DWORD v78[2]; // [rsp+80h] [rbp+Fh] BYREF
  _DWORD *v79; // [rsp+88h] [rbp+17h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+D0h] [rbp+5Fh] BYREF
  SIZE_T Size; // [rsp+D8h] [rbp+67h]
  _QWORD *v82; // [rsp+E0h] [rbp+6Fh]

  v82 = a3;
  v3 = a2;
  v4 = a1;
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
    v4 = 0;
  if ( !a2 || *a2 < 0x70u || a2[1] != 1936944179 )
    v3 = 0;
  if ( v4 && v3 )
  {
    if ( !a3 )
    {
      v64 = 5919;
      goto LABEL_143;
    }
    if ( v3[2] == 772 && v3[27] == 2 )
    {
      v5 = *((_QWORD *)v3 + 2);
      if ( v5 )
      {
        v6 = *(const wchar_t **)(v5 + 136);
        v7 = 0;
        LODWORD(Size) = 0;
        if ( !v6 || !*v6 )
          v6 = L"SHA256";
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= g_dwHashInfoTotalCount )
            goto LABEL_24;
          v9 = (const wchar_t **)g_pHashInfo[i];
          v10 = &g_pHashInfo[i];
          if ( v9 )
          {
            if ( *v9 && !wcsnicmp(v6, *v9, 0x40u) )
              break;
          }
        }
        _mm_lfence();
        if ( !*v10 )
        {
LABEL_24:
          v11 = Size;
LABEL_25:
          v12 = v11;
          pbOutput = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
          v14 = pbOutput;
          if ( pbOutput )
          {
            Heap = 0;
            phHash = 0;
            v16 = (const wchar_t *)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c";
            if ( v7 && (_BYTE)v11 )
            {
              for ( j = 0; (unsigned int)j < g_dwHashInfoTotalCount; j = (unsigned int)(j + 1) )
              {
                v18 = (const wchar_t **)g_pHashInfo[j];
                if ( v18 )
                {
                  v16 = *v18;
                  if ( *v18 )
                  {
                    if ( !wcsnicmp(v7, v16, 0x40u) )
                    {
                      v19 = (BCRYPT_ALG_HANDLE *)&v4[8 * (unsigned int)j];
                      if ( !*((_DWORD *)v19 + 75) )
                      {
                        HashEntry = I_GetHashEntry((unsigned int)j, (unsigned int)v4[3], v19 + 34);
                        v25 = HashEntry;
                        if ( HashEntry < 0 )
                        {
                          v66 = 3902;
                          goto LABEL_151;
                        }
                      }
                      v20 = *((_DWORD *)v19 + 72);
                      Heap = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
                      if ( Heap )
                      {
                        v25 = BCryptCreateHash(v19[34], &phHash, Heap, v20, 0, 0, 0);
                        if ( v25 < 0 )
                        {
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                          {
                            WPP_SF_sDsd(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              v23,
                              v24,
                              (unsigned int)"Status",
                              v25,
                              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                              86);
                          }
                        }
                        else
                        {
                          HashEntry = BCryptHashData(phHash, 0, 0, 0);
                          v25 = HashEntry;
                          if ( HashEntry >= 0 )
                          {
                            v14 = pbOutput;
                            v27 = Size;
                            v28 = BCryptFinishHash(phHash, pbOutput, (unsigned __int8)Size, 0);
                            v25 = v28;
                            if ( v28 < 0 )
                              DebugTraceError(
                                (unsigned int)v28,
                                "Status",
                                "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                                3944);
                            goto LABEL_45;
                          }
                          v66 = 3934;
LABEL_151:
                          DebugTraceError(
                            (unsigned int)HashEntry,
                            "Status",
                            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                            v66);
                        }
                      }
                      else
                      {
                        v25 = -2146893810;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          WPP_SF_sDsd(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            v21,
                            v22,
                            (unsigned int)"Status",
                            14,
                            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                            73);
                        }
                      }
LABEL_43:
                      v14 = pbOutput;
                      goto LABEL_44;
                    }
                  }
                }
              }
              v25 = -2146893783;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  (_DWORD)v16,
                  v13,
                  (unsigned int)"Status",
                  41,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                  53);
              }
              goto LABEL_43;
            }
            v25 = -2146893785;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_134;
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              v13,
              (unsigned int)"Status",
              39,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              45);
LABEL_44:
            v27 = Size;
LABEL_45:
            if ( phHash )
              BCryptDestroyHash(phHash);
            if ( Heap )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            if ( v25 < 0 )
            {
LABEL_134:
              v60 = 5964;
              v61 = (unsigned int)v25;
            }
            else
            {
              v73 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
              if ( v73 )
              {
                v30 = *((_QWORD *)v3 + 4);
                v72 = *(_DWORD *)"tls13 ";
                v31 = 0;
                LOWORD(phHash) = *(_WORD *)"3 ";
                v71 = aTls13[6];
                v74 = 0;
                v75[0] = 0;
                v34 = strnlen_s("derived", v29);
                v75[1] = 20;
                v79 = v75;
                v76 = 0;
                v78[0] = 0;
                v78[1] = 1;
                v70 = 0;
                if ( v30 && v34 != 0xF9 && (_BYTE)v27 && v27 )
                {
                  v35 = (unsigned __int16)((unsigned __int8)(v34 + 6) + 4 + (unsigned __int8)v27);
                  v36 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v35);
                  P = v36;
                  v32 = (int)v36;
                  if ( v36 )
                  {
                    v37 = BYTE1(Size);
                    v38 = v36 + 9;
                    v36[1] = Size;
                    v36[2] = v34 + 6;
                    *v36 = v37;
                    *(_DWORD *)(v36 + 3) = v72;
                    *(_WORD *)(v36 + 7) = (_WORD)phHash;
                    v39 = v34;
                    memmove(v36 + 9, "derived", v34);
                    cbSecret = Size;
                    v41 = (unsigned __int8)Size;
                    v38[v39] = Size;
                    memmove(&v38[v39 + 1], pbOutput, v41);
                    v42 = P;
                    v75[0] = v35;
                    v76 = P;
                    v25 = BCryptKeyDerivation(v30, v78, v73, (unsigned __int16)cbSecret, &v70, 0);
                    if ( (v25 || v70 != (unsigned __int16)cbSecret)
                      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v43,
                        v44,
                        (unsigned int)"Status",
                        v25,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                        195);
                    }
                    v47 = v42;
                    do
                    {
                      *v47++ = 0;
                      --v35;
                    }
                    while ( v35 );
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v42);
                    if ( v25 >= 0 )
                    {
                      v48 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
                      pbSecret = v48;
                      if ( !v48 )
                      {
                        v25 = -2146893810;
                        DebugTraceError(
                          2148073486LL,
                          "Status",
                          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                          6000);
                        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pbOutput);
                        v31 = v74;
                        goto LABEL_90;
                      }
                      memset(v48, 0, v12);
                      v49 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x70u);
                      v31 = v49;
                      if ( !v49 )
                      {
                        v25 = -2146893810;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          WPP_SF_sDsd(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            v50,
                            v51,
                            (unsigned int)"Status",
                            14,
                            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                            125);
                        }
                        goto LABEL_89;
                      }
                      memset(v49 + 8, 0, 0x68u);
                      *(_DWORD *)v31 = 112;
                      *((_DWORD *)v31 + 1) = 1936944179;
                      *((_DWORD *)v31 + 2) = v3[2];
                      v52 = *((_QWORD *)v3 + 2);
                      *((_QWORD *)v31 + 2) = v52;
                      *((_DWORD *)v31 + 27) = 3;
                      phHash = 0;
                      if ( !cbSecret || !v52 )
                      {
                        v25 = -1073741811;
                        v45 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        {
LABEL_87:
                          if ( v25 >= 0 )
                          {
LABEL_88:
                            *v82 = v31;
                            v31 = 0;
LABEL_89:
                            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pbOutput);
LABEL_90:
                            v55 = v73;
                            for ( k = v73; v12; --v12 )
                              *k++ = 0;
                            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v55);
                            if ( pbSecret )
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pbSecret);
                            if ( v31 )
                            {
                              v62 = v31;
                              v63 = 112;
                              do
                              {
                                *v62++ = 0;
                                --v63;
                              }
                              while ( v63 );
                              MSCryptFree(v31);
                            }
                            return (unsigned int)v25;
                          }
                          if ( v45 == (_BYTE *)&WPP_GLOBAL_Control || (v45[28] & 1) == 0 )
                            goto LABEL_89;
                          dwFlags = -109;
LABEL_110:
                          WPP_SF_sDsd(
                            *((_QWORD *)v45 + 2),
                            v32,
                            v33,
                            (unsigned int)"Status",
                            v25,
                            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                            dwFlags);
                          goto LABEL_89;
                        }
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v32,
                          v33,
                          (unsigned int)"Status",
                          13,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                          210);
                        goto LABEL_84;
                      }
                      v53 = *(wchar_t **)(v52 + 136);
                      if ( !v53 || !*v53 )
                        v53 = L"SHA256";
                      HashInfoFromAlgorithmName = I_GetHashInfoFromAlgorithmName(v53);
                      if ( !HashInfoFromAlgorithmName || cbSecret != *(_DWORD *)(HashInfoFromAlgorithmName + 8) )
                      {
                        v25 = -1073741811;
                        DebugTraceError(
                          3221225485LL,
                          "Status",
                          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                          3807);
LABEL_84:
                        v45 = WPP_GLOBAL_Control;
                        goto LABEL_85;
                      }
                      v25 = BCryptGenerateSymmetricKey(
                              (BCRYPT_ALG_HANDLE)0x391,
                              &phHash,
                              0,
                              0,
                              (PUCHAR)pbSecret,
                              cbSecret,
                              0);
                      if ( v25 )
                      {
                        v45 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          dwFlagsa = -19;
                          goto LABEL_106;
                        }
                      }
                      else
                      {
                        v58 = -1;
                        while ( v53[++v58] != 0 )
                          ;
                        v25 = BCryptSetProperty(phHash, L"HkdfHashAlgorithm", (PUCHAR)v53, 2 * v58 + 2, 0);
                        if ( !v25 )
                        {
                          v25 = BCryptSetProperty(phHash, L"HkdfSaltAndFinalize", (PUCHAR)v73, cbSecret, 0);
                          if ( !v25 )
                          {
                            *((_QWORD *)v31 + 4) = phHash;
                            phHash = 0;
                            goto LABEL_88;
                          }
                          v45 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                          {
                            goto LABEL_85;
                          }
                          dwFlagsa = 7;
                          goto LABEL_106;
                        }
                        v45 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          dwFlagsa = -6;
LABEL_106:
                          WPP_SF_sDsd(
                            *((_QWORD *)v45 + 2),
                            v32,
                            v33,
                            (unsigned int)"Status",
                            v25,
                            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                            dwFlagsa);
                          goto LABEL_84;
                        }
                      }
LABEL_85:
                      if ( phHash )
                      {
                        BCryptDestroyKey(phHash);
                        v45 = WPP_GLOBAL_Control;
                      }
                      goto LABEL_87;
                    }
                    v31 = v74;
                  }
                  else
                  {
                    v25 = -1073741801;
                    v45 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    {
                      goto LABEL_62;
                    }
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      0,
                      v33,
                      (unsigned int)"Status",
                      23,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                      169);
                  }
                }
                else
                {
                  v25 = -1073741811;
                  v45 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  {
                    goto LABEL_62;
                  }
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v32,
                    v33,
                    (unsigned int)"Status",
                    13,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                    150);
                }
                v45 = WPP_GLOBAL_Control;
LABEL_62:
                pbSecret = 0;
                if ( v45 == (_BYTE *)&WPP_GLOBAL_Control || (v45[28] & 1) == 0 )
                  goto LABEL_89;
                dwFlags = 100;
                goto LABEL_110;
              }
              v25 = -2146893810;
              v60 = 5976;
              v61 = 2148073486LL;
            }
            DebugTraceError(v61, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v60);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
            return (unsigned int)v25;
          }
          v25 = -2146893810;
          v64 = 5958;
          v65 = 2148073486LL;
LABEL_145:
          DebugTraceError(v65, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v64);
          return (unsigned int)v25;
        }
        v11 = *(_DWORD *)(*v10 + 8);
        LODWORD(Size) = v11;
        if ( v11 <= 0xFF )
        {
          v7 = v6;
          goto LABEL_25;
        }
        v64 = 5942;
LABEL_143:
        v25 = -2146893785;
        v65 = 2148073511LL;
        goto LABEL_145;
      }
    }
    v25 = -2146893783;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        41);
  }
  else
  {
    v25 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        24);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x180004570  mov     [rsp-8+arg_10], r8
0x180004575  push    rbp
0x180004576  push    r13
0x180004578  push    r14
0x18000457a  push    r15
0x18000457c  lea     rbp, [rsp-37h]
0x180004581  sub     rsp, 0A8h
0x180004588  mov     rax, r8
0x18000458b  mov     r15, rdx
0x18000458e  mov     r14, rcx
0x180004591  test    rcx, rcx
0x180004594  jz      short loc_1800045A7
0x180004596  cmp     dword ptr [rcx], 310h
0x18000459c  jb      short loc_1800045A7
0x18000459e  cmp     dword ptr [rcx+4], 73736C31h
0x1800045a5  jz      short loc_1800045AA
0x1800045a7  xor     r14d, r14d
0x1800045aa  test    rdx, rdx
0x1800045ad  jz      short loc_1800045BD
0x1800045af  cmp     dword ptr [rdx], 70h ; 'p'
0x1800045b2  jb      short loc_1800045BD
0x1800045b4  cmp     dword ptr [rdx+4], 73736C33h
0x1800045bb  jz      short loc_1800045C0
0x1800045bd  xor     r15d, r15d
0x1800045c0  mov     [rsp+0C0h+arg_18], rbx
0x1800045c8  mov     [rsp+0C0h+var_20], rsi
0x1800045d0  mov     [rsp+0C0h+var_28], rdi
0x1800045d8  mov     [rsp+0C0h+var_30], r12
0x1800045e0  test    r14, r14
0x1800045e3  jz      loc_180004F7A
0x1800045e9  test    r15, r15
0x1800045ec  jz      loc_180004F7A
0x1800045f2  test    rax, rax
0x1800045f5  jz      loc_1800050DD
0x1800045fb  cmp     dword ptr [r15+8], 304h
0x180004603  jnz     loc_180004E99
0x180004609  cmp     dword ptr [r15+6Ch], 2
0x18000460e  jnz     loc_180004E99
0x180004614  mov     rsi, [r15+10h]
0x180004618  test    rsi, rsi
0x18000461b  jz      loc_180004E99
0x180004621  mov     rsi, [rsi+88h]
0x180004628  xor     edi, edi
0x18000462a  xor     r13d, r13d
0x18000462d  mov     dword ptr [rbp+4Fh+Size], edi
0x180004630  test    rsi, rsi
0x180004633  jz      loc_180004B03
0x180004639  cmp     [rsi], di
0x18000463c  jz      loc_180004B03
0x180004642  xor     ebx, ebx
0x180004644  lea     rcx, g_pHashInfo
0x18000464b  nop     dword ptr [rax+rax+00h]
0x180004650  cmp     ebx, cs:g_dwHashInfoTotalCount
0x180004656  jnb     short loc_180004699
0x180004658  mov     rax, [rcx+rbx*8]
0x18000465c  lea     rdi, [rcx+rbx*8]
0x180004660  test    rax, rax
0x180004663  jz      short loc_180004686
0x180004665  mov     rdx, [rax]; String2
0x180004668  test    rdx, rdx
0x18000466b  jz      short loc_180004686
0x18000466d  mov     r8d, 40h ; '@'; MaxCount
0x180004673  mov     rcx, rsi; String1
0x180004676  call    _wcsnicmp
0x18000467b  test    eax, eax
0x18000467d  jz      short loc_18000468A
0x18000467f  lea     rcx, g_pHashInfo
0x180004686  inc     ebx
0x180004688  jmp     short loc_180004650
0x18000468a  lfence
0x18000468d  mov     rax, [rdi]
0x180004690  test    rax, rax
0x180004693  jnz     loc_180005121
0x180004699  mov     edi, dword ptr [rbp+4Fh+Size]
0x18000469c  mov     rcx, gs:60h
0x1800046a5  xor     edx, edx; Flags
0x1800046a7  mov     r8d, edi; Size
0x1800046aa  mov     esi, edi
0x1800046ac  mov     rcx, [rcx+30h]; HeapHandle
0x1800046b0  call    cs:__imp_RtlAllocateHeap
0x1800046b6  mov     [rbp+4Fh+pbOutput], rax
0x1800046ba  mov     rbx, rax
0x1800046bd  test    rax, rax
0x1800046c0  jz      loc_1800050F8
0x1800046c6  xor     r12d, r12d
0x1800046c9  lea     rax, WPP_GLOBAL_Control
0x1800046d0  mov     [rbp+4Fh+phHash], r12
0x1800046d4  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800046db  test    r13, r13
0x1800046de  jz      loc_180005000
0x1800046e4  test    dil, dil
0x1800046e7  jz      loc_180005000
0x1800046ed  xor     ebx, ebx
0x1800046ef  nop
0x1800046f0  cmp     ebx, cs:g_dwHashInfoTotalCount
0x1800046f6  jnb     loc_1800047F8
0x1800046fc  lea     rax, g_pHashInfo
0x180004703  mov     edi, ebx
0x180004705  mov     rax, [rax+rbx*8]
0x180004709  test    rax, rax
0x18000470c  jz      short loc_180004728
0x18000470e  mov     rdx, [rax]; String2
0x180004711  test    rdx, rdx
0x180004714  jz      short loc_180004728
0x180004716  mov     r8d, 40h ; '@'; MaxCount
0x18000471c  mov     rcx, r13; String1
0x18000471f  call    _wcsnicmp
0x180004724  test    eax, eax
0x180004726  jz      short loc_18000472C
0x180004728  inc     ebx
0x18000472a  jmp     short loc_1800046F0
0x18000472c  shl     rdi, 5
0x180004730  add     rdi, r14
0x180004733  cmp     [rdi+12Ch], r12d
0x18000473a  jz      loc_180005137
0x180004740  mov     rcx, gs:60h
0x180004749  xor     edx, edx; Flags
0x18000474b  mov     ebx, [rdi+120h]
0x180004751  mov     r8d, ebx; Size
0x180004754  mov     rcx, [rcx+30h]; HeapHandle
0x180004758  call    cs:__imp_RtlAllocateHeap
0x18000475e  mov     r12, rax
0x180004761  test    rax, rax
0x180004764  jz      loc_180004ABB
0x18000476a  mov     rcx, [rdi+110h]; hAlgorithm
0x180004771  lea     rdx, [rbp+4Fh+phHash]; phHash
0x180004775  xor     eax, eax
0x180004777  mov     r9d, ebx; cbHashObject
0x18000477a  mov     dword ptr [rsp+0C0h+dwFlags], eax; dwFlags
0x18000477e  mov     r8, r12; pbHashObject
0x180004781  mov     [rsp+0C0h+cbSecret], eax; cbSecret
0x180004785  mov     [rsp+0C0h+pbSecret], rax; pbSecret
0x18000478a  call    cs:__imp_BCryptCreateHash
0x180004790  mov     r13d, eax
0x180004793  test    eax, eax
0x180004795  js      loc_180004A8D
0x18000479b  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18000479f  xor     r9d, r9d; dwFlags
0x1800047a2  xor     r8d, r8d; cbInput
0x1800047a5  xor     edx, edx; pbInput
0x1800047a7  call    cs:__imp_BCryptHashData
0x1800047ad  mov     r13d, eax
0x1800047b0  test    eax, eax
0x1800047b2  js      loc_18000515C
0x1800047b8  mov     rbx, [rbp+4Fh+pbOutput]
0x1800047bc  xor     r9d, r9d; dwFlags
0x1800047bf  mov     r14d, dword ptr [rbp+4Fh+Size]
0x1800047c3  mov     rdx, rbx; pbOutput
0x1800047c6  mov     rcx, [rbp+4Fh+phHash]; hHash
0x1800047ca  movzx   r8d, r14b; cbOutput
0x1800047ce  call    cs:__imp_BCryptFinishHash
0x1800047d4  mov     r13d, eax
0x1800047d7  test    eax, eax
0x1800047d9  jns     short loc_180004848
0x1800047db  mov     r9d, 0F68h
0x1800047e1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800047e8  lea     rdx, aStatus; "Status"
0x1800047ef  mov     ecx, eax
0x1800047f1  call    DebugTraceError
0x1800047f6  jmp     short loc_180004848
0x1800047f8  mov     r13d, 80090029h
0x1800047fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180004805  lea     rax, WPP_GLOBAL_Control
0x18000480c  cmp     rcx, rax
0x18000480f  jz      short loc_180004840
0x180004811  test    byte ptr [rcx+1Ch], 1
0x180004815  jz      short loc_180004840
0x180004817  mov     dword ptr [rsp+0C0h+dwFlags], 0F35h
0x18000481f  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004826  mov     qword ptr [rsp+0C0h+cbSecret], rax
0x18000482b  mov     dword ptr [rsp+0C0h+pbSecret], r13d
0x180004830  mov     rcx, [rcx+10h]
0x180004834  lea     r9, aStatus; "Status"
0x18000483b  call    WPP_SF_sDsd
0x180004840  mov     rbx, [rbp+4Fh+pbOutput]
0x180004844  mov     r14d, dword ptr [rbp+4Fh+Size]
0x180004848  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18000484c  test    rcx, rcx
0x18000484f  jz      short loc_180004857
0x180004851  call    cs:__imp_BCryptDestroyHash
0x180004857  test    r12, r12
0x18000485a  jz      short loc_180004874
0x18000485c  mov     rcx, gs:60h
0x180004865  mov     r8, r12; P
0x180004868  xor     edx, edx; Flags
0x18000486a  mov     rcx, [rcx+30h]; HeapHandle
0x18000486e  call    cs:__imp_RtlFreeHeap
0x180004874  test    r13d, r13d
0x180004877  js      loc_180005042
0x18000487d  mov     rcx, gs:60h
0x180004886  mov     r8, rsi; Size
0x180004889  xor     edx, edx; Flags
0x18000488b  mov     rcx, [rcx+30h]; HeapHandle
0x18000488f  call    cs:__imp_RtlAllocateHeap
0x180004895  mov     [rbp+4Fh+var_68], rax
0x180004899  test    rax, rax
0x18000489c  jz      loc_18000517C
0x1800048a2  mov     eax, dword ptr cs:aTls13; "tls13 "
0x1800048a8  lea     rcx, Src; "derived"
0x1800048af  mov     r13, [r15+20h]
0x1800048b3  xor     ebx, ebx
0x1800048b5  mov     [rbp+4Fh+var_70], eax
0x1800048b8  mov     edi, ebx
0x1800048ba  movzx   eax, word ptr cs:aTls13+4; "3 "
0x1800048c1  mov     word ptr [rbp+4Fh+phHash], ax
0x1800048c5  movzx   eax, byte ptr cs:aTls13+6; ""
0x1800048cc  mov     [rbp+4Fh+var_72], al
0x1800048cf  mov     [rbp+4Fh+var_60], rbx
0x1800048d3  call    strnlen_s
0x1800048d8  mov     [rbp+4Fh+var_58], ebx
0x1800048db  mov     r12, rax
0x1800048de  mov     [rbp+4Fh+var_54], 14h
0x1800048e5  lea     rax, [rbp+4Fh+var_58]
0x1800048e9  mov     [rbp+4Fh+var_38], rax
0x1800048ed  mov     [rbp+4Fh+var_50], rbx
0x1800048f1  mov     [rbp+4Fh+var_40], ebx
0x1800048f4  mov     [rbp+4Fh+var_3C], 1
0x1800048fb  mov     [rbp+4Fh+var_78], ebx
0x1800048fe  test    r13, r13
0x180004901  jz      loc_180004EED
0x180004907  lea     ebx, [r12+6]
0x18000490c  cmp     bl, 0FFh
0x18000490f  jnb     loc_180004EED
0x180004915  test    r14b, r14b
0x180004918  jz      loc_180004EED
0x18000491e  test    r14w, r14w
0x180004922  jz      loc_180004EED
0x180004928  movzx   ecx, r14b
0x18000492c  xor     edx, edx; Flags
0x18000492e  movzx   eax, bl
0x180004931  add     ax, 4
0x180004935  add     cx, ax
0x180004938  movzx   r14d, cx
0x18000493c  mov     rcx, gs:60h
0x180004945  mov     r8d, r14d; Size
0x180004948  mov     rcx, [rcx+30h]; HeapHandle
0x18000494c  call    cs:__imp_RtlAllocateHeap
0x180004952  mov     [rbp+4Fh+P], rax
0x180004956  mov     rdx, rax
0x180004959  test    rax, rax
0x18000495c  jz      loc_180004A47
0x180004962  mov     ecx, dword ptr [rbp+4Fh+Size]
0x180004965  lea     rdi, [rdx+9]
0x180004969  mov     [rdx+1], cl
0x18000496c  movzx   eax, cx
0x18000496f  mov     [rdx+2], bl
0x180004972  mov     rcx, rdi; void *
0x180004975  shr     ax, 8
0x180004979  mov     [rdx], al
0x18000497b  mov     eax, [rbp+4Fh+var_70]
0x18000497e  mov     [rdx+3], eax
0x180004981  movzx   eax, word ptr [rbp+4Fh+phHash]
0x180004985  mov     [rdx+7], ax
0x180004989  lea     rdx, Src; "derived"
0x180004990  movzx   ebx, r12b
0x180004994  mov     r8d, ebx; Size
0x180004997  call    memmove
0x18000499c  mov     r12d, dword ptr [rbp+4Fh+Size]
0x1800049a0  lea     rcx, [rbx+1]
0x1800049a4  mov     rdx, [rbp+4Fh+pbOutput]; Src
0x1800049a8  add     rcx, rdi; void *
0x1800049ab  movzx   r8d, r12b; Size
0x1800049af  mov     [rdi+rbx], r12b
0x1800049b3  call    memmove
0x1800049b8  mov     rdi, [rbp+4Fh+P]
0x1800049bc  lea     rax, [rbp+4Fh+var_78]
0x1800049c0  mov     r8, [rbp+4Fh+var_68]
0x1800049c4  lea     rdx, [rbp+4Fh+var_40]
0x1800049c8  movzx   ebx, r12w
0x1800049cc  mov     rcx, r13
0x1800049cf  mov     r9d, ebx
0x1800049d2  mov     [rsp+0C0h+cbSecret], 0
0x1800049da  mov     [rsp+0C0h+pbSecret], rax
0x1800049df  mov     [rbp+4Fh+var_58], r14d
0x1800049e3  mov     [rbp+4Fh+var_50], rdi
0x1800049e7  call    cs:__imp_BCryptKeyDerivation
0x1800049ed  mov     r13d, eax
0x1800049f0  test    eax, eax
0x1800049f2  jz      loc_180004B0F
0x1800049f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049ff  lea     rax, WPP_GLOBAL_Control
0x180004a06  cmp     rcx, rax
0x180004a09  jz      loc_180004B18
0x180004a0f  test    byte ptr [rcx+1Ch], 1
0x180004a13  jz      loc_180004B18
0x180004a19  mov     rcx, [rcx+10h]
0x180004a1d  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004a24  mov     dword ptr [rsp+0C0h+dwFlags], 0FC3h
0x180004a2c  lea     r9, aStatus; "Status"
0x180004a33  mov     qword ptr [rsp+0C0h+cbSecret], rax
0x180004a38  mov     dword ptr [rsp+0C0h+pbSecret], r13d
0x180004a3d  call    WPP_SF_sDsd
0x180004a42  jmp     loc_180004B18
0x180004a47  mov     r13d, 0C0000017h
0x180004a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a54  lea     rbx, WPP_GLOBAL_Control
0x180004a5b  cmp     rcx, rbx
0x180004a5e  jz      short loc_180004A6A
0x180004a60  test    byte ptr [rcx+1Ch], 1
0x180004a64  jnz     loc_180005192
  ... truncated ...
```
