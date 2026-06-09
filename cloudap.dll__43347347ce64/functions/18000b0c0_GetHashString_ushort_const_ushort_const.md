# GetHashString(ushort const *,ushort * const)

- ea: `0x18000b0c0`
- end: `0x18000b83e`
- name: `?GetHashString@@YAJPEBGQEAG@Z`
- size: `1918`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr, unsigned __int16 *const)`
- caller_count: `17`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180004e80`
- `0x18000db68`
- `0x180029650`
- `0x18002d71c`
- `0x18002ea68`
- `0x180032998`
- `0x18003fcdc`
- `0x180040fe4`
- `0x180047c70`
- `0x180048e60`
- `0x18004d294`
- `0x18004e7b0`
- `0x18004f600`
- `0x180052978`
- `0x18005d774`
- `0x18005e654`
- `0x18005ea48`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x1800156f0`
- `0x180042410`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b77b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b77b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7d5`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18000b24b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18000b2ac`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18000b24b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18000b2ac`
- `bcrypt!BCryptDestroyHash` at `0x18000b1e6`
- `bcrypt!BCryptDestroyHash` at `0x18000b1e6`
- `bcrypt!BCryptFinishHash` at `0x18000b31f`
- `bcrypt!BCryptFinishHash` at `0x18000b31f`
- `bcrypt!BCryptCreateHash` at `0x18000b2de`
- `bcrypt!BCryptCreateHash` at `0x18000b2de`
- `bcrypt!BCryptHashData` at `0x18000b2fc`
- `bcrypt!BCryptHashData` at `0x18000b2fc`

## string_xrefs

- `0x18000b162`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000b620`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000b659`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000b69b`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000b6e2`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000b72c`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000b794`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000b7e4`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000b811`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000b67b`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall GetHashString(UCHAR *lpSrcStr, unsigned __int16 *const a2)
{
  UCHAR *v4; // rsi
  __int64 v5; // rax
  int v6; // r14d
  unsigned int HashStringPreRS2; // ebx
  const UCHAR *v8; // r9
  char v9; // al
  const UCHAR *v10; // rdx
  bool v11; // zf
  unsigned int v13; // eax
  unsigned int v14; // r15d
  WCHAR *v15; // rax
  ULONG v16; // r14d
  unsigned int i; // r10d
  __int64 v18; // r9
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // r8
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r8
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // r8
  unsigned __int64 v30; // r8
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // r8
  unsigned __int64 v33; // r8
  unsigned int v34; // ecx
  unsigned __int64 v35; // r8
  const char *v36; // r9
  char v37; // al
  char v38; // al
  char v39; // al
  const char *v40; // rax
  const char *v41; // r9
  const char *v42; // r9
  const char *v43; // r9
  LPWSTR lpDestStr; // [rsp+20h] [rbp-88h]
  LPWSTR lpDestStra; // [rsp+20h] [rbp-88h]
  const char *cchDest; // [rsp+28h] [rbp-80h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+50h] [rbp-58h] BYREF
  UCHAR pbOutput[32]; // [rsp+58h] [rbp-50h] BYREF

  *(_OWORD *)a2 = 0;
  *((_OWORD *)a2 + 1) = 0;
  *((_OWORD *)a2 + 2) = 0;
  *((_OWORD *)a2 + 3) = 0;
  hHash = 0;
  *((_OWORD *)a2 + 4) = 0;
  v4 = 0;
  *((_OWORD *)a2 + 5) = 0;
  *((_OWORD *)a2 + 6) = 0;
  *((_OWORD *)a2 + 7) = 0;
  a2[64] = 0;
  if ( (g_ulTestFlags & 2) != 0 )
  {
    HashStringPreRS2 = GetHashStringPreRS2(lpSrcStr, a2);
    if ( HashStringPreRS2 )
    {
      v40 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v40, 1042, "GetHashStringPreRS2", &Class);
    }
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&lpSrcStr[2 * v5] );
    v6 = v5 + 1;
    if ( (int)v5 + 1 >= (unsigned int)v5 )
    {
      v13 = LCMapStringEx(&Class, 0x31403u, (LPCWSTR)lpSrcStr, v6, 0, 0, 0, 0, 0);
      if ( !v13 )
      {
        if ( (int)GetLastError() > 0 )
          HashStringPreRS2 = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          HashStringPreRS2 = GetLastError();
        v41 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(lpDestStr) = 1079;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v41, lpDestStr, "LCMapStringEx", &Class);
        goto LABEL_13;
      }
      v14 = v13 + 1;
      if ( v13 + 1 < v13 )
      {
        HashStringPreRS2 = -1073741675;
        v36 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(lpDestStr) = 1084;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v36, lpDestStr, "RtlDWordAdd", &Class);
        goto LABEL_13;
      }
      v15 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v14);
      v4 = (UCHAR *)v15;
      if ( v15 )
      {
        v16 = LCMapStringEx(&Class, 0x31403u, (LPCWSTR)lpSrcStr, v6, v15, v14, 0, 0, 0);
        if ( !v16 )
        {
          if ( (int)GetLastError() > 0 )
            HashStringPreRS2 = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            HashStringPreRS2 = GetLastError();
          v42 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(lpDestStra) = 1111;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v42, lpDestStra, "LCMapStringEx", &Class);
          goto LABEL_13;
        }
        HashStringPreRS2 = BCryptCreateHash(g_hSHA256, &hHash, 0, 0, 0, 0, 0);
        if ( HashStringPreRS2 )
        {
          v8 = "";
          while ( 1 )
          {
            v37 = *(v8 - 1);
            v10 = v8--;
            v11 = v37 == 92;
            if ( v37 == 92 )
              break;
            if ( v8 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
            {
              v11 = v37 == 92;
              break;
            }
          }
          cchDest = "BCryptCreateHash";
          LODWORD(lpDestStr) = 1121;
        }
        else
        {
          HashStringPreRS2 = BCryptHashData(hHash, v4, v16, 0);
          if ( HashStringPreRS2 )
          {
            v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
            LODWORD(lpDestStr) = 1130;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v43, lpDestStr, "BCryptHashData", &Class);
            goto LABEL_13;
          }
          HashStringPreRS2 = BCryptFinishHash(hHash, pbOutput, 0x20u, 0);
          if ( !HashStringPreRS2 )
          {
            for ( i = 0; i < 0x20; i += 16 )
            {
              v18 = 2 * i;
              v19 = (unsigned __int64)pbOutput[i] >> 4;
              a2[v18] = a0123456789abcd[pbOutput[i] & 0xF];
              a2[(unsigned int)(v18 + 1)] = a0123456789abcd[v19];
              v20 = (unsigned __int64)pbOutput[i + 1] >> 4;
              a2[(unsigned int)(v18 + 2)] = a0123456789abcd[pbOutput[i + 1] & 0xF];
              a2[(unsigned int)(v18 + 3)] = a0123456789abcd[v20];
              v21 = (unsigned __int64)pbOutput[i + 2] >> 4;
              a2[2 * i + 4] = a0123456789abcd[pbOutput[i + 2] & 0xF];
              a2[(unsigned int)(v18 + 5)] = a0123456789abcd[v21];
              v22 = (unsigned __int64)pbOutput[i + 3] >> 4;
              a2[2 * i + 6] = a0123456789abcd[pbOutput[i + 3] & 0xF];
              a2[(unsigned int)(v18 + 7)] = a0123456789abcd[v22];
              v23 = (unsigned __int64)pbOutput[i + 4] >> 4;
              a2[2 * i + 8] = a0123456789abcd[pbOutput[i + 4] & 0xF];
              a2[(unsigned int)(v18 + 9)] = a0123456789abcd[v23];
              v24 = (unsigned __int64)pbOutput[i + 5] >> 4;
              a2[2 * i + 10] = a0123456789abcd[pbOutput[i + 5] & 0xF];
              a2[(unsigned int)(v18 + 11)] = a0123456789abcd[v24];
              v25 = (unsigned __int64)pbOutput[i + 6] >> 4;
              a2[2 * i + 12] = a0123456789abcd[pbOutput[i + 6] & 0xF];
              a2[(unsigned int)(v18 + 13)] = a0123456789abcd[v25];
              v26 = (unsigned __int64)pbOutput[i + 7] >> 4;
              a2[2 * i + 14] = a0123456789abcd[pbOutput[i + 7] & 0xF];
              a2[(unsigned int)(v18 + 15)] = a0123456789abcd[v26];
              v27 = (unsigned __int64)pbOutput[i + 8] >> 4;
              a2[2 * i + 16] = a0123456789abcd[pbOutput[i + 8] & 0xF];
              a2[(unsigned int)(v18 + 17)] = a0123456789abcd[v27];
              v28 = (unsigned __int64)pbOutput[i + 9] >> 4;
              a2[2 * i + 18] = a0123456789abcd[pbOutput[i + 9] & 0xF];
              a2[(unsigned int)(v18 + 19)] = a0123456789abcd[v28];
              v29 = (unsigned __int64)pbOutput[i + 10] >> 4;
              a2[2 * i + 20] = a0123456789abcd[pbOutput[i + 10] & 0xF];
              a2[(unsigned int)(v18 + 21)] = a0123456789abcd[v29];
              v30 = (unsigned __int64)pbOutput[i + 11] >> 4;
              a2[2 * i + 22] = a0123456789abcd[pbOutput[i + 11] & 0xF];
              a2[(unsigned int)(v18 + 23)] = a0123456789abcd[v30];
              v31 = (unsigned __int64)pbOutput[i + 12] >> 4;
              a2[2 * i + 24] = a0123456789abcd[pbOutput[i + 12] & 0xF];
              a2[(unsigned int)(v18 + 25)] = a0123456789abcd[v31];
              v32 = (unsigned __int64)pbOutput[i + 13] >> 4;
              a2[2 * i + 26] = a0123456789abcd[pbOutput[i + 13] & 0xF];
              a2[(unsigned int)(v18 + 27)] = a0123456789abcd[v32];
              v33 = (unsigned __int64)pbOutput[i + 14] >> 4;
              a2[2 * i + 28] = a0123456789abcd[pbOutput[i + 14] & 0xF];
              a2[(unsigned int)(v18 + 29)] = a0123456789abcd[v33];
              v34 = i + 15;
              v35 = pbOutput[i + 15];
              a2[2 * v34] = a0123456789abcd[v35 & 0xF];
              a2[(unsigned int)(v18 + 31)] = a0123456789abcd[v35 >> 4];
            }
            a2[64] = 0;
            HashStringPreRS2 = 0;
            goto LABEL_13;
          }
          v8 = "";
          while ( 1 )
          {
            v38 = *(v8 - 1);
            v10 = v8--;
            v11 = v38 == 92;
            if ( v38 == 92 )
              break;
            if ( v8 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
            {
              v11 = v38 == 92;
              break;
            }
          }
          cchDest = "BCryptFinishHash";
          LODWORD(lpDestStr) = 1139;
        }
      }
      else
      {
        HashStringPreRS2 = -1073741801;
        v8 = "";
        while ( 1 )
        {
          v39 = *(v8 - 1);
          v10 = v8--;
          v11 = v39 == 92;
          if ( v39 == 92 )
            break;
          if ( v8 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
          {
            v11 = v39 == 92;
            break;
          }
        }
        cchDest = "AllocateLsaHeap";
        LODWORD(lpDestStr) = 1090;
      }
    }
    else
    {
      HashStringPreRS2 = -1073741675;
      v8 = "";
      while ( 1 )
      {
        v9 = *(v8 - 1);
        v10 = v8--;
        v11 = v9 == 92;
        if ( v9 == 92 )
          break;
        if ( v8 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
        {
          v11 = v9 == 92;
          break;
        }
      }
      cchDest = "RtlDWordAdd";
      LODWORD(lpDestStr) = 1049;
    }
    if ( v11 )
      v8 = v10;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashStringPreRS2, v8, lpDestStr, cchDest, &Class);
  }
LABEL_13:
  if ( hHash )
    BCryptDestroyHash(hHash);
  if ( v4 )
    ((void (__fastcall *)(UCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v4);
  return HashStringPreRS2;
}

```

## disassembly

```asm
0x18000b0c0  mov     r11, rsp
0x18000b0c3  push    rbx
0x18000b0c4  push    rsi
0x18000b0c5  sub     rsp, 98h
0x18000b0cc  mov     rax, cs:__security_cookie
0x18000b0d3  xor     rax, rsp
0x18000b0d6  mov     [rsp+0A8h+var_30], rax
0x18000b0db  xorps   xmm0, xmm0
0x18000b0de  mov     [r11+18h], rbp
0x18000b0e2  movups  xmmword ptr [rdx], xmm0
0x18000b0e5  mov     [r11+20h], rdi
0x18000b0e9  xor     eax, eax
0x18000b0eb  movups  xmmword ptr [rdx+10h], xmm0
0x18000b0ef  mov     [r11-18h], r12
0x18000b0f3  xor     r12d, r12d
0x18000b0f6  movups  xmmword ptr [rdx+20h], xmm0
0x18000b0fa  mov     [r11-28h], r15
0x18000b0fe  mov     rdi, rdx
0x18000b101  movups  xmmword ptr [rdx+30h], xmm0
0x18000b105  mov     rbx, rcx
0x18000b108  mov     [r11-58h], r12
0x18000b10c  movups  xmmword ptr [rdx+40h], xmm0
0x18000b110  mov     esi, r12d
0x18000b113  movups  xmmword ptr [rdx+50h], xmm0
0x18000b117  movups  xmmword ptr [rdx+60h], xmm0
0x18000b11b  movups  xmmword ptr [rdx+70h], xmm0
0x18000b11f  mov     [rdx+80h], ax
0x18000b126  mov     eax, cs:?g_ulTestFlags@@3KA; ulong g_ulTestFlags
0x18000b12c  test    al, 2
0x18000b12e  jnz     loc_18000B71D
0x18000b134  mov     [r11-20h], r14
0x18000b138  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b13f  nop
0x18000b140  inc     rax
0x18000b143  cmp     [rcx+rax*2], si
0x18000b147  jnz     short loc_18000B140
0x18000b149  lea     r14d, [rax+1]
0x18000b14d  cmp     r14d, eax
0x18000b150  jnb     loc_18000B21D
0x18000b156  mov     ebx, 0C0000095h
0x18000b15b  lea     r9, pbInput+24h; ""
0x18000b162  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000b169  movzx   eax, byte ptr [r9-1]
0x18000b16e  mov     rdx, r9
0x18000b171  dec     r9
0x18000b174  cmp     al, 5Ch ; '\'
0x18000b176  jz      short loc_18000B17F
0x18000b178  cmp     r9, rcx
0x18000b17b  ja      short loc_18000B169
0x18000b17d  cmp     al, 5Ch ; '\'
0x18000b17f  lea     rbp, Class
0x18000b186  mov     [rsp+0A8h+lpVersionInformation], rbp
0x18000b18b  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x18000b192  mov     qword ptr [rsp+0A8h+cchDest], rax
0x18000b197  mov     dword ptr [rsp+0A8h+lpDestStr], 419h
0x18000b19f  cmovz   r9, rdx
0x18000b1a3  mov     r8d, ebx
0x18000b1a6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000b1ad  xor     ecx, ecx
0x18000b1af  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000b1b4  mov     r14, [rsp+0A8h+var_20]
0x18000b1bc  mov     rcx, [rsp+0A8h+hHash]; hHash
0x18000b1c1  mov     r15, [rsp+0A8h+var_28]
0x18000b1c9  mov     r12, [rsp+0A8h+var_18]
0x18000b1d1  mov     rdi, [rsp+0A8h+arg_18]
0x18000b1d9  mov     rbp, [rsp+0A8h+arg_10]
0x18000b1e1  test    rcx, rcx
0x18000b1e4  jz      short loc_18000B1EC
0x18000b1e6  call    cs:__imp_BCryptDestroyHash
0x18000b1ec  test    rsi, rsi
0x18000b1ef  jz      short loc_18000B204
0x18000b1f1  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000b1f8  mov     rcx, rsi
0x18000b1fb  mov     rax, [rax+30h]
0x18000b1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b204  mov     eax, ebx
0x18000b206  mov     rcx, [rsp+0A8h+var_30]
0x18000b20b  xor     rcx, rsp; StackCookie
0x18000b20e  call    __security_check_cookie
0x18000b213  add     rsp, 98h
0x18000b21a  pop     rsi
0x18000b21b  pop     rbx
0x18000b21c  retn
0x18000b21d  mov     [rsp+0A8h+sortHandle], r12; sortHandle
0x18000b222  lea     rbp, Class
0x18000b229  mov     [rsp+0A8h+lpReserved], r12; lpReserved
0x18000b22e  mov     r9d, r14d; cchSrc
0x18000b231  mov     [rsp+0A8h+lpVersionInformation], r12; lpVersionInformation
0x18000b236  mov     r8, rbx; lpSrcStr
0x18000b239  mov     [rsp+0A8h+cchDest], r12d; cchDest
0x18000b23e  mov     edx, 31403h; dwMapFlags
0x18000b243  mov     rcx, rbp; lpLocaleName
0x18000b246  mov     [rsp+0A8h+lpDestStr], r12; lpDestStr
0x18000b24b  call    cs:__imp_LCMapStringEx
0x18000b251  test    eax, eax
0x18000b253  jz      loc_18000B771
0x18000b259  lea     r15d, [rax+1]
0x18000b25d  cmp     r15d, eax
0x18000b260  jb      loc_18000B620
0x18000b266  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000b26d  mov     ecx, r15d
0x18000b270  mov     rax, [rax+28h]
0x18000b274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b279  mov     rsi, rax
0x18000b27c  test    rax, rax
0x18000b27f  jz      loc_18000B6D6
0x18000b285  mov     [rsp+0A8h+sortHandle], r12; sortHandle
0x18000b28a  mov     r9d, r14d; cchSrc
0x18000b28d  mov     [rsp+0A8h+lpReserved], r12; lpReserved
0x18000b292  mov     r8, rbx; lpSrcStr
0x18000b295  mov     [rsp+0A8h+lpVersionInformation], r12; lpVersionInformation
0x18000b29a  mov     edx, 31403h; dwMapFlags
0x18000b29f  mov     [rsp+0A8h+cchDest], r15d; cchDest
0x18000b2a4  mov     rcx, rbp; lpLocaleName
0x18000b2a7  mov     [rsp+0A8h+lpDestStr], rax; lpDestStr
0x18000b2ac  call    cs:__imp_LCMapStringEx
0x18000b2b2  mov     r14d, eax
0x18000b2b5  test    eax, eax
0x18000b2b7  jz      loc_18000B7C1
0x18000b2bd  mov     rcx, cs:?g_hSHA256@@3PEAXEA; hAlgorithm
0x18000b2c4  lea     rdx, [rsp+0A8h+hHash]; phHash
0x18000b2c9  mov     dword ptr [rsp+0A8h+lpVersionInformation], r12d; dwFlags
0x18000b2ce  xor     r9d, r9d; cbHashObject
0x18000b2d1  mov     [rsp+0A8h+cchDest], r12d; cbSecret
0x18000b2d6  xor     r8d, r8d; pbHashObject
0x18000b2d9  mov     [rsp+0A8h+lpDestStr], r12; pbSecret
0x18000b2de  call    cs:__imp_BCryptCreateHash
0x18000b2e4  mov     ebx, eax
0x18000b2e6  test    eax, eax
0x18000b2e8  jnz     loc_18000B652
0x18000b2ee  mov     rcx, [rsp+0A8h+hHash]; hHash
0x18000b2f3  xor     r9d, r9d; dwFlags
0x18000b2f6  mov     r8d, r14d; cbInput
0x18000b2f9  mov     rdx, rsi; pbInput
0x18000b2fc  call    cs:__imp_BCryptHashData
0x18000b302  mov     ebx, eax
0x18000b304  test    eax, eax
0x18000b306  jnz     loc_18000B811
0x18000b30c  mov     rcx, [rsp+0A8h+hHash]; hHash
0x18000b311  lea     rdx, [rsp+0A8h+pbOutput]; pbOutput
0x18000b316  xor     r9d, r9d; dwFlags
0x18000b319  mov     r8d, 20h ; ' '; cbOutput
0x18000b31f  call    cs:__imp_BCryptFinishHash
0x18000b325  mov     ebx, eax
0x18000b327  test    eax, eax
0x18000b329  jnz     loc_18000B694
0x18000b32f  mov     r10d, r12d
0x18000b332  lea     r11, a0123456789abcd; "0123456789abcdef"
0x18000b339  nop     dword ptr [rax+00000000h]
0x18000b340  lea     r9d, [r10+r10]
0x18000b344  mov     eax, r10d
0x18000b347  lea     ecx, [r9+1]
0x18000b34b  movzx   edx, [rsp+rax+0A8h+pbOutput]
0x18000b350  mov     eax, edx
0x18000b352  shr     rdx, 4
0x18000b356  and     eax, 0Fh
0x18000b359  movzx   eax, word ptr [r11+rax*2]
0x18000b35e  mov     [rdi+r9*2], ax
0x18000b363  movzx   eax, word ptr [r11+rdx*2]
0x18000b368  mov     [rdi+rcx*2], ax
0x18000b36c  lea     ecx, [r9+2]
0x18000b370  lea     eax, [r10+1]
0x18000b374  movzx   r8d, [rsp+rax+0A8h+pbOutput]
0x18000b37a  mov     edx, r8d
0x18000b37d  shr     r8, 4
0x18000b381  and     edx, 0Fh
0x18000b384  movzx   eax, word ptr [r11+rdx*2]
0x18000b389  mov     [rdi+rcx*2], ax
0x18000b38d  lea     ecx, [r9+3]
0x18000b391  movzx   eax, word ptr [r11+r8*2]
0x18000b396  mov     [rdi+rcx*2], ax
0x18000b39a  lea     ecx, [r10+2]
0x18000b39e  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b3a4  add     ecx, ecx
0x18000b3a6  mov     edx, r8d
0x18000b3a9  shr     r8, 4
0x18000b3ad  and     edx, 0Fh
0x18000b3b0  movzx   eax, word ptr [r11+rdx*2]
0x18000b3b5  mov     [rdi+rcx*2], ax
0x18000b3b9  lea     ecx, [r9+5]
0x18000b3bd  movzx   eax, word ptr [r11+r8*2]
0x18000b3c2  mov     [rdi+rcx*2], ax
0x18000b3c6  lea     ecx, [r10+3]
0x18000b3ca  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b3d0  add     ecx, ecx
0x18000b3d2  mov     edx, r8d
0x18000b3d5  shr     r8, 4
0x18000b3d9  and     edx, 0Fh
0x18000b3dc  movzx   eax, word ptr [r11+rdx*2]
0x18000b3e1  mov     [rdi+rcx*2], ax
0x18000b3e5  lea     ecx, [r9+7]
0x18000b3e9  movzx   eax, word ptr [r11+r8*2]
0x18000b3ee  mov     [rdi+rcx*2], ax
0x18000b3f2  lea     ecx, [r10+4]
0x18000b3f6  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b3fc  add     ecx, ecx
0x18000b3fe  mov     edx, r8d
0x18000b401  shr     r8, 4
0x18000b405  and     edx, 0Fh
0x18000b408  movzx   eax, word ptr [r11+rdx*2]
0x18000b40d  mov     [rdi+rcx*2], ax
0x18000b411  lea     ecx, [r9+9]
0x18000b415  movzx   eax, word ptr [r11+r8*2]
0x18000b41a  mov     [rdi+rcx*2], ax
0x18000b41e  lea     ecx, [r10+5]
0x18000b422  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b428  add     ecx, ecx
0x18000b42a  mov     edx, r8d
0x18000b42d  shr     r8, 4
0x18000b431  and     edx, 0Fh
0x18000b434  movzx   eax, word ptr [r11+rdx*2]
0x18000b439  mov     [rdi+rcx*2], ax
0x18000b43d  lea     ecx, [r9+0Bh]
0x18000b441  movzx   eax, word ptr [r11+r8*2]
0x18000b446  mov     [rdi+rcx*2], ax
0x18000b44a  lea     ecx, [r10+6]
0x18000b44e  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b454  add     ecx, ecx
0x18000b456  mov     edx, r8d
0x18000b459  shr     r8, 4
0x18000b45d  and     edx, 0Fh
0x18000b460  movzx   eax, word ptr [r11+rdx*2]
0x18000b465  mov     [rdi+rcx*2], ax
0x18000b469  lea     ecx, [r9+0Dh]
0x18000b46d  movzx   eax, word ptr [r11+r8*2]
0x18000b472  mov     [rdi+rcx*2], ax
0x18000b476  lea     ecx, [r10+7]
0x18000b47a  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b480  mov     edx, r8d
0x18000b483  and     edx, 0Fh
0x18000b486  movzx   eax, word ptr [r11+rdx*2]
0x18000b48b  add     ecx, ecx
0x18000b48d  shr     r8, 4
0x18000b491  mov     [rdi+rcx*2], ax
0x18000b495  lea     ecx, [r9+0Fh]
0x18000b499  movzx   eax, word ptr [r11+r8*2]
0x18000b49e  mov     [rdi+rcx*2], ax
0x18000b4a2  lea     ecx, [r10+8]
0x18000b4a6  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b4ac  add     ecx, ecx
0x18000b4ae  mov     edx, r8d
0x18000b4b1  shr     r8, 4
0x18000b4b5  and     edx, 0Fh
0x18000b4b8  movzx   eax, word ptr [r11+rdx*2]
0x18000b4bd  mov     [rdi+rcx*2], ax
0x18000b4c1  lea     ecx, [r9+11h]
0x18000b4c5  movzx   eax, word ptr [r11+r8*2]
0x18000b4ca  mov     [rdi+rcx*2], ax
0x18000b4ce  lea     ecx, [r10+9]
0x18000b4d2  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b4d8  add     ecx, ecx
0x18000b4da  mov     edx, r8d
0x18000b4dd  shr     r8, 4
0x18000b4e1  and     edx, 0Fh
0x18000b4e4  movzx   eax, word ptr [r11+rdx*2]
0x18000b4e9  mov     [rdi+rcx*2], ax
0x18000b4ed  lea     ecx, [r9+13h]
0x18000b4f1  movzx   eax, word ptr [r11+r8*2]
0x18000b4f6  mov     [rdi+rcx*2], ax
0x18000b4fa  lea     ecx, [r10+0Ah]
0x18000b4fe  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b504  add     ecx, ecx
0x18000b506  mov     edx, r8d
0x18000b509  shr     r8, 4
0x18000b50d  and     edx, 0Fh
0x18000b510  movzx   eax, word ptr [r11+rdx*2]
0x18000b515  mov     [rdi+rcx*2], ax
0x18000b519  lea     ecx, [r9+15h]
0x18000b51d  movzx   eax, word ptr [r11+r8*2]
0x18000b522  mov     [rdi+rcx*2], ax
0x18000b526  lea     ecx, [r10+0Bh]
0x18000b52a  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b530  add     ecx, ecx
0x18000b532  mov     edx, r8d
0x18000b535  shr     r8, 4
0x18000b539  and     edx, 0Fh
0x18000b53c  movzx   eax, word ptr [r11+rdx*2]
0x18000b541  mov     [rdi+rcx*2], ax
0x18000b545  lea     ecx, [r9+17h]
0x18000b549  movzx   eax, word ptr [r11+r8*2]
0x18000b54e  mov     [rdi+rcx*2], ax
0x18000b552  lea     ecx, [r10+0Ch]
0x18000b556  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b55c  add     ecx, ecx
0x18000b55e  mov     edx, r8d
0x18000b561  shr     r8, 4
0x18000b565  and     edx, 0Fh
0x18000b568  movzx   eax, word ptr [r11+rdx*2]
0x18000b56d  mov     [rdi+rcx*2], ax
0x18000b571  lea     ecx, [r9+19h]
0x18000b575  movzx   eax, word ptr [r11+r8*2]
0x18000b57a  mov     [rdi+rcx*2], ax
0x18000b57e  lea     ecx, [r10+0Dh]
0x18000b582  movzx   r8d, [rsp+rcx+0A8h+pbOutput]
0x18000b588  add     ecx, ecx
0x18000b58a  mov     edx, r8d
0x18000b58d  shr     r8, 4
0x18000b591  and     edx, 0Fh
0x18000b594  movzx   eax, word ptr [r11+rdx*2]
0x18000b599  mov     [rdi+rcx*2], ax
  ... truncated ...
```
