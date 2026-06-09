# UnprotectLegacyPrivateKey

- ea: `0x1800155f4`
- end: `0x180015eb4`
- name: `UnprotectLegacyPrivateKey`
- size: `2240`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014bec`
- `0x180033a10`

## callees

- `0x1800086d0`
- `0x18000af80`
- `0x18000b250`
- `0x1800155f4`
- `0x180015ebc`
- `0x18001652c`
- `0x180038970`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800157c2`
- `ntdll!RtlFreeHeap` at `0x1800157c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015824`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015861`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015861`
- `bcrypt!BCryptImportKeyPair` at `0x180015767`
- `bcrypt!BCryptImportKeyPair` at `0x180015767`
- `bcrypt!BCryptExportKey` at `0x180015bb1`
- `bcrypt!BCryptExportKey` at `0x180015c9e`
- `bcrypt!BCryptExportKey` at `0x180015d20`
- `bcrypt!BCryptExportKey` at `0x180015e11`
- `bcrypt!BCryptExportKey` at `0x180015bb1`
- `bcrypt!BCryptExportKey` at `0x180015c9e`
- `bcrypt!BCryptExportKey` at `0x180015d20`
- `bcrypt!BCryptExportKey` at `0x180015e11`
- `DPAPI!CryptUnprotectDataNoUI` at `0x1800156fa`
- `DPAPI!CryptUnprotectDataNoUI` at `0x1800156fa`

## string_xrefs

- `0x1800156be`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180015e84`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x1800157fb`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180015937`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180015a66`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180015a91`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180015e68`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`

## pseudocode

```c
__int64 __fastcall UnprotectLegacyPrivateKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ebx
  int PasswordHashAlg; // eax
  unsigned int v9; // edi
  unsigned int v10; // edx
  __int64 v11; // r8
  int v12; // ecx
  unsigned int v13; // r15d
  DWORD i; // r13d
  PVOID *v15; // rdx
  const WCHAR *v16; // r13
  __int64 v17; // rcx
  ULONG *pbInput; // rdi
  int v19; // r8d
  unsigned __int64 cbInput; // rsi
  ULONG v21; // ecx
  int v22; // edx
  unsigned int v23; // ebx
  int v24; // r8d
  _BYTE *v25; // rax
  __int64 v26; // rcx
  DWORD LastError; // eax
  int v29; // r8d
  unsigned int v30; // r15d
  unsigned int v31; // ecx
  unsigned __int64 v32; // rax
  __int64 v33; // rdx
  unsigned __int64 v34; // rcx
  __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  void *v37; // rsp
  void *v38; // rsp
  ULONG *v39; // rax
  __int64 v40; // r9
  _DWORD *v41; // rdx
  ULONG v42; // eax
  __int64 v43; // rbx
  __int64 v44; // r9
  __int64 v45; // r10
  __int64 v46; // rcx
  __int64 v47; // r11
  __int64 v48; // r9
  __int64 v49; // r8
  PVOID v50; // rdx
  __int64 v51; // rcx
  char *v52; // rcx
  __int64 v53; // r9
  __int64 v54; // rcx
  unsigned int v55; // eax
  __int64 v56; // rdx
  unsigned __int64 v57; // rcx
  __int64 v58; // rcx
  unsigned __int64 v59; // rcx
  void *v60; // rsp
  void *v61; // rsp
  ULONG *v62; // rax
  unsigned int v63; // r15d
  unsigned int v64; // r15d
  __int64 v65; // rdx
  size_t v66; // rbx
  unsigned __int64 v67; // rcx
  __int64 v68; // rcx
  unsigned __int64 v69; // rcx
  void *v70; // rsp
  void *v71; // rsp
  ULONG *v72; // rax
  _BYTE v73[32]; // [rsp+0h] [rbp-50h] BYREF
  ULONG dwFlags[2]; // [rsp+30h] [rbp-20h]
  ULONG pcbResult; // [rsp+50h] [rbp+0h] BYREF
  __int64 v76; // [rsp+58h] [rbp+8h] BYREF
  PVOID P[2]; // [rsp+60h] [rbp+10h] BYREF
  _DWORD *v78; // [rsp+70h] [rbp+20h]
  __int64 v79; // [rsp+78h] [rbp+28h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+80h] [rbp+30h] BYREF
  _DWORD v81[2]; // [rsp+88h] [rbp+38h] BYREF
  __int64 v82; // [rsp+90h] [rbp+40h]
  __int128 v83; // [rsp+98h] [rbp+48h] BYREF
  __int64 v84; // [rsp+A8h] [rbp+58h]

  v84 = 0;
  v81[1] = 0;
  v5 = *(_QWORD *)(a1 + 256);
  phKey = 0;
  pcbResult = 0;
  v83 = 0;
  *(_OWORD *)P = 0;
  if ( v5 )
  {
    v6 = *(_DWORD *)(a1 + 264);
    v7 = 1;
    v82 = v5;
    LODWORD(v83) = 24;
    v81[0] = v6;
    PasswordHashAlg = MyCryptProtectGetPasswordHashAlg(a1, a2, a3, a4);
    v9 = 64;
    v10 = 0;
    v11 = a1 + 432;
    if ( PasswordHashAlg != 32782 )
      v9 = 20;
    v76 = a1 + 432;
    while ( v7 )
    {
      v12 = 0;
      if ( !*(_BYTE *)(v10 + v11) )
        v12 = v7;
      ++v10;
      v7 = v12;
      if ( v10 >= v9 )
      {
        if ( v12 )
        {
          v11 = 0;
          v76 = 0;
          v9 = 0;
        }
        break;
      }
    }
    v13 = 0;
    for ( i = 10; ; i *= 2 )
    {
      if ( (unsigned int)CryptUnprotectDataNoUI(v81, 0, 0, 0, &v83, -2147483647, v11, v9, P) )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        v16 = 0;
        goto LABEL_14;
      }
      LastError = GetLastError();
      v23 = LastError;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)WPP_GLOBAL_Control,
          v29,
          (unsigned int)"dwSts",
          LastError,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          21);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v23 != 1723 || v13 >= 5 )
        break;
      Sleep(i);
      v11 = v76;
      ++v13;
    }
    v16 = 0;
    if ( v23 )
    {
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          (unsigned int)v15[2],
          (_DWORD)v15,
          v29,
          (unsigned int)"Status",
          v23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
          250);
      return v23;
    }
LABEL_14:
    v17 = *(_QWORD *)(a1 + 64);
    pbInput = 0;
    LODWORD(v76) = 0;
    v19 = *(_DWORD *)(v17 + 32) - 196609;
    if ( *(_DWORD *)(v17 + 32) != 196609 )
    {
      if ( *(_DWORD *)(v17 + 32) != 196610 )
      {
        if ( *(_DWORD *)(v17 + 32) != 196611 )
        {
          LODWORD(cbInput) = 0;
          v21 = 0;
          goto LABEL_18;
        }
        if ( LODWORD(P[0]) != 20 )
        {
          v53 = 1881;
LABEL_73:
          v23 = -2146893821;
          v54 = 2148073475LL;
LABEL_115:
          DebugTraceError(v54, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v53);
LABEL_22:
          v25 = P[1];
          if ( P[1] )
          {
            v26 = LODWORD(P[0]);
            if ( LODWORD(P[0]) )
            {
              do
              {
                *v25++ = 0;
                --v26;
              }
              while ( v26 );
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
          }
          if ( pbInput )
          {
            if ( *(pbInput - 2) == 1885431112 )
              ((void (*)(void))g_pfnFree)();
          }
          return v23;
        }
        v55 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(a1 + 104), 0, L"DSAPUBLICBLOB", 0, 0, &pcbResult, 0);
        v23 = v55;
        if ( v55 )
        {
          v53 = 1896;
LABEL_77:
          v54 = v55;
          goto LABEL_115;
        }
        cbInput = pcbResult + 20;
        if ( pcbResult == -20 )
          goto LABEL_118;
        if ( (unsigned int)cbInput > (unsigned __int64)g_ulMaxStackAllocSize )
          goto LABEL_118;
        v57 = (unsigned int)cbInput + g_ulAdditionalProbeSize + 8;
        if ( v57 < (unsigned int)cbInput || !(unsigned int)VerifyStackAvailable(v57, v56) )
          goto LABEL_118;
        v58 = cbInput + 23;
        if ( cbInput + 23 <= cbInput + 8 )
          v58 = 0xFFFFFFFFFFFFFF0LL;
        v59 = v58 & 0xFFFFFFFFFFFFFFF0uLL;
        v60 = alloca(v59);
        v61 = alloca(v59);
        pbInput = &pcbResult;
        if ( v73 == (_BYTE *)-80LL || (pcbResult = 1801679955, (pbInput = (ULONG *)&v76) == 0) )
        {
LABEL_118:
          if ( cbInput + 8 >= (unsigned int)cbInput )
          {
            v62 = (ULONG *)((__int64 (*)(void))g_pfnAllocate)();
            pbInput = v62;
            if ( v62 )
            {
              *v62 = 1885431112;
              pbInput = v62 + 2;
            }
          }
        }
        if ( !pbInput )
        {
          v53 = 1906;
LABEL_114:
          v23 = -2146893810;
          v54 = 2148073486LL;
          goto LABEL_115;
        }
        v55 = BCryptExportKey(
                *(BCRYPT_KEY_HANDLE *)(a1 + 104),
                0,
                L"DSAPUBLICBLOB",
                (PUCHAR)pbInput,
                cbInput,
                &pcbResult,
                0);
        v23 = v55;
        if ( v55 )
        {
          v53 = 1920;
          goto LABEL_77;
        }
        *pbInput = 1448104772;
        v16 = L"DSAPRIVATEBLOB";
        ReverseMemCopy((char *)pbInput + pcbResult, P[1], 20);
        v21 = 8;
LABEL_18:
        v23 = BCryptImportKeyPair(*(BCRYPT_ALG_HANDLE *)(a1 + 88), 0, v16, &phKey, (PUCHAR)pbInput, cbInput, v21);
        if ( v23 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v22,
              v24,
              (unsigned int)"Status",
              v23,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
              221);
        }
        else
        {
          *(_QWORD *)(a1 + 112) = phKey;
        }
        goto LABEL_22;
      }
      v63 = *(_DWORD *)(a1 + 28) >> 3;
      if ( LODWORD(P[0]) > v63 )
      {
        v53 = 1942;
        goto LABEL_73;
      }
      v64 = v63 - LODWORD(P[0]);
      v55 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(a1 + 104), 0, L"DHPUBLICBLOB", 0, 0, &pcbResult, 0);
      v23 = v55;
      if ( v55 )
      {
        v53 = 1958;
        goto LABEL_77;
      }
      cbInput = pcbResult + (*(_DWORD *)(a1 + 28) >> 3);
      if ( !(_DWORD)cbInput )
        goto LABEL_105;
      v66 = (unsigned int)cbInput;
      if ( (unsigned int)cbInput > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_105;
      v67 = (unsigned int)cbInput + g_ulAdditionalProbeSize + 8;
      if ( v67 < (unsigned int)cbInput || !(unsigned int)VerifyStackAvailable(v67, v65) )
        goto LABEL_105;
      v68 = cbInput + 23;
      if ( cbInput + 23 <= cbInput + 8 )
        v68 = 0xFFFFFFFFFFFFFF0LL;
      v69 = v68 & 0xFFFFFFFFFFFFFFF0uLL;
      v70 = alloca(v69);
      v71 = alloca(v69);
      pbInput = &pcbResult;
      if ( v73 == (_BYTE *)-80LL || (pcbResult = 1801679955, (pbInput = (ULONG *)&v76) == 0) )
      {
LABEL_105:
        v66 = (unsigned int)cbInput;
        if ( cbInput + 8 >= (unsigned int)cbInput )
        {
          v72 = (ULONG *)((__int64 (*)(void))g_pfnAllocate)();
          pbInput = v72;
          if ( v72 )
          {
            *v72 = 1885431112;
            pbInput = v72 + 2;
          }
        }
      }
      if ( !pbInput )
      {
        v53 = 1968;
        goto LABEL_114;
      }
      memset_0(pbInput, 0, v66);
      v55 = BCryptExportKey(
              *(BCRYPT_KEY_HANDLE *)(a1 + 104),
              0,
              L"DHPUBLICBLOB",
              (PUCHAR)pbInput,
              cbInput,
              &pcbResult,
              0);
      v23 = v55;
      if ( v55 )
      {
        v53 = 1983;
        goto LABEL_77;
      }
      *pbInput = 1448101956;
      v16 = L"DHPRIVATEBLOB";
      v49 = LODWORD(P[0]);
      v50 = P[1];
      v52 = (char *)pbInput + v64 + pcbResult;
LABEL_68:
      ReverseMemCopy(v52, v50, v49);
      v21 = v76;
      goto LABEL_18;
    }
    if ( LODWORD(P[0]) >= 0x14 )
    {
      v19 = -1;
      v78 = P[1];
      v30 = (unsigned int)(*((_DWORD *)P[1] + 2) + 7) >> 3;
      v31 = (v30 + 1) >> 1;
      v79 = v31;
      v32 = 9LL * v31;
      if ( v32 <= 0xFFFFFFFF )
      {
        v33 = (unsigned int)(v32 + 20);
        if ( (unsigned int)v33 < (unsigned int)v32 )
        {
          v40 = 1819;
        }
        else
        {
          if ( LODWORD(P[0]) >= (unsigned int)v33 )
          {
            cbInput = v30 + 28 + 2 * v31;
            if ( cbInput > g_ulMaxStackAllocSize )
              goto LABEL_119;
            v34 = cbInput + g_ulAdditionalProbeSize + 8;
            if ( v34 < cbInput || !(unsigned int)VerifyStackAvailable(v34, v33) )
              goto LABEL_119;
            v35 = cbInput + 23;
            if ( cbInput + 23 <= cbInput + 8 )
              v35 = 0xFFFFFFFFFFFFFF0LL;
            v36 = v35 & 0xFFFFFFFFFFFFFFF0uLL;
            v37 = alloca(v36);
            v38 = alloca(v36);
            pbInput = &pcbResult;
            if ( !&pcbResult || (pcbResult = 1801679955, (pbInput = (ULONG *)&v76) == 0) )
            {
LABEL_119:
              if ( cbInput + 8 >= cbInput )
              {
                v39 = (ULONG *)((__int64 (*)(void))g_pfnAllocate)();
                pbInput = v39;
                if ( v39 )
                {
                  *v39 = 1885431112;
                  pbInput = v39 + 2;
                }
              }
            }
            if ( !pbInput )
            {
              v53 = 1845;
              goto LABEL_114;
            }
            v41 = v78;
            *pbInput = 843141970;
            v16 = L"RSAPRIVATEBLOB";
            pbInput[1] = v41[2];
            v42 = v79;
            v43 = (__int64)v41 + v30 + 28;
            pbInput[4] = v79;
            pbInput[5] = v42;
            pbInput[2] = 4;
            pbInput[3] = v30;
            ReverseMemCopy(pbInput + 6, v41 + 4, 4);
            ReverseMemCopy(v44 + pbInput[2], v45, v30);
            ReverseMemCopy(v47 + v46, v43, (unsigned int)v79);
            v49 = (unsigned int)v48;
            v50 = (PVOID)(v43 + v48 + 4);
            v52 = (char *)(v48 + v51);
            goto LABEL_68;
          }
          v40 = 1826;
        }
        DebugTraceError(2148073475LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", v40);
        return 2148073475LL;
      }
      if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 1) == 0 )
        return 2148073475LL;
      dwFlags[0] = 1812;
    }
    else
    {
      if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 1) == 0 )
        return 2148073475LL;
      dwFlags[0] = 1800;
    }
    WPP_SF_sDsd(
      (unsigned int)v15[2],
      (_DWORD)v15,
      v19,
      (unsigned int)"Status",
      3,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
      dwFlags[0]);
    return 2148073475LL;
  }
  return 2148073485LL;
}

```

## disassembly

```asm
0x1800155f4  push    rbp
0x1800155f6  push    rbx
0x1800155f7  push    rsi
0x1800155f8  push    rdi
0x1800155f9  push    r12
0x1800155fb  push    r13
0x1800155fd  push    r14
0x1800155ff  push    r15
0x180015601  sub     rsp, 0C8h
0x180015608  lea     rbp, [rsp+50h]
0x18001560d  mov     rax, cs:__security_cookie
0x180015614  xor     rax, rbp
0x180015617  mov     [rbp+0B0h+var_48], rax
0x18001561b  xor     esi, esi
0x18001561d  xor     eax, eax
0x18001561f  xorps   xmm0, xmm0
0x180015622  mov     [rbp+0B0h+var_58], rax
0x180015626  mov     r14, rcx
0x180015629  mov     [rbp+0B0h+var_74], esi
0x18001562c  mov     rcx, [rcx+100h]
0x180015633  mov     [rbp+0B0h+phKey], rsi
0x180015637  mov     [rbp+0B0h+pcbResult], esi
0x18001563a  movups  [rbp+0B0h+var_68], xmm0
0x18001563e  movups  xmmword ptr [rbp+0B0h+P], xmm0
0x180015642  test    rcx, rcx
0x180015645  jz      loc_180015B61
0x18001564b  mov     eax, [r14+108h]
0x180015652  lea     ebx, [rsi+1]
0x180015655  mov     [rbp+0B0h+var_70], rcx
0x180015659  mov     rcx, r14
0x18001565c  mov     dword ptr [rbp+0B0h+var_68], 18h
0x180015663  mov     [rbp+0B0h+var_78], eax
0x180015666  call    MyCryptProtectGetPasswordHashAlg
0x18001566b  cmp     eax, 800Eh
0x180015670  lea     edi, [rsi+40h]
0x180015673  lea     ecx, [rsi+14h]
0x180015676  mov     edx, esi
0x180015678  lea     r8, [r14+1B0h]
0x18001567f  cmovnz  edi, ecx
0x180015682  mov     [rbp+0B0h+var_A8], r8
0x180015686  test    ebx, ebx
0x180015688  jz      short loc_1800156AA
0x18001568a  mov     eax, edx
0x18001568c  mov     ecx, esi
0x18001568e  cmp     [rax+r8], sil
0x180015692  cmovz   ecx, ebx
0x180015695  inc     edx
0x180015697  mov     ebx, ecx
0x180015699  cmp     edx, edi
0x18001569b  jb      short loc_180015686
0x18001569d  test    ecx, ecx
0x18001569f  jz      short loc_1800156AA
0x1800156a1  mov     r8, rsi
0x1800156a4  mov     [rbp+0B0h+var_A8], rsi
0x1800156a8  mov     edi, esi
0x1800156aa  cmp     [rbp+0B0h+var_70], rsi
0x1800156ae  jz      loc_1800158FA
0x1800156b4  mov     r15d, esi
0x1800156b7  lea     r12, WPP_GLOBAL_Control
0x1800156be  lea     rsi, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800156c5  mov     r13d, 0Ah
0x1800156cb  lea     rax, [rbp+0B0h+P]
0x1800156cf  xor     r9d, r9d
0x1800156d2  mov     [rsp+100h+var_C0], rax
0x1800156d7  lea     rcx, [rbp+0B0h+var_78]
0x1800156db  mov     [rsp+100h+var_C8], edi
0x1800156df  lea     rax, [rbp+0B0h+var_68]
0x1800156e3  mov     qword ptr [rsp+100h+dwFlags], r8
0x1800156e8  xor     edx, edx
0x1800156ea  mov     [rsp+100h+cbInput], 80000001h
0x1800156f2  xor     r8d, r8d
0x1800156f5  mov     [rsp+100h+pbInput], rax
0x1800156fa  call    cs:__imp_CryptUnprotectDataNoUI
0x180015701  nop     dword ptr [rax+rax+00h]
0x180015706  test    eax, eax
0x180015708  jz      loc_180015824
0x18001570e  mov     rdx, cs:WPP_GLOBAL_Control
0x180015715  xor     r13d, r13d
0x180015718  mov     rcx, [r14+40h]
0x18001571c  mov     rdi, r13
0x18001571f  mov     dword ptr [rbp+0B0h+var_A8], r13d
0x180015723  mov     r8d, [rcx+20h]
0x180015727  sub     r8d, 30001h
0x18001572e  jz      loc_1800158AA
0x180015734  sub     r8d, 1
0x180015738  jz      loc_180015CE7
0x18001573e  cmp     r8d, 1
0x180015742  jz      loc_180015B6B
0x180015748  xor     esi, esi
0x18001574a  mov     ecx, r13d
0x18001574d  mov     [rsp+100h+dwFlags], ecx; dwFlags
0x180015751  lea     r9, [rbp+0B0h+phKey]; phKey
0x180015755  mov     rcx, [r14+58h]; hAlgorithm
0x180015759  mov     r8, r13; pszBlobType
0x18001575c  mov     [rsp+100h+cbInput], esi; cbInput
0x180015760  xor     edx, edx; hImportKey
0x180015762  mov     [rsp+100h+pbInput], rdi; pbInput
0x180015767  call    cs:__imp_BCryptImportKeyPair
0x18001576e  nop     dword ptr [rax+rax+00h]
0x180015773  xor     r13d, r13d
0x180015776  mov     ebx, eax
0x180015778  test    eax, eax
0x18001577a  jz      loc_18001589D
0x180015780  mov     rcx, cs:WPP_GLOBAL_Control
0x180015787  cmp     rcx, r12
0x18001578a  jz      short loc_180015792
0x18001578c  test    byte ptr [rcx+1Ch], 1
0x180015790  jnz     short loc_1800157F7
0x180015792  mov     rax, [rbp+0B0h+P+8]
0x180015796  test    rax, rax
0x180015799  jz      short loc_1800157CE
0x18001579b  mov     ecx, dword ptr [rbp+0B0h+P]
0x18001579e  test    rcx, rcx
0x1800157a1  jz      short loc_1800157AF
0x1800157a3  mov     [rax], r13b
0x1800157a6  inc     rax
0x1800157a9  sub     rcx, 1
0x1800157ad  jnz     short loc_1800157A3
0x1800157af  mov     rcx, gs:60h
0x1800157b8  xor     edx, edx; Flags
0x1800157ba  mov     r8, [rbp+0B0h+P+8]; P
0x1800157be  mov     rcx, [rcx+30h]; HeapHandle
0x1800157c2  call    cs:__imp_RtlFreeHeap
0x1800157c9  nop     dword ptr [rax+rax+00h]
0x1800157ce  test    rdi, rdi
0x1800157d1  jnz     loc_18001587C
0x1800157d7  mov     eax, ebx
0x1800157d9  mov     rcx, [rbp+0B0h+var_48]
0x1800157dd  xor     rcx, rbp; StackCookie
0x1800157e0  call    __security_check_cookie
0x1800157e5  lea     rsp, [rbp+78h]
0x1800157e9  pop     r15
0x1800157eb  pop     r14
0x1800157ed  pop     r13
0x1800157ef  pop     r12
0x1800157f1  pop     rdi
0x1800157f2  pop     rsi
0x1800157f3  pop     rbx
0x1800157f4  pop     rbp
0x1800157f5  retn
0x1800157f7  mov     rcx, [rcx+10h]
0x1800157fb  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015802  mov     [rsp+100h+dwFlags], 7DDh
0x18001580a  lea     r9, aStatus; "Status"
0x180015811  mov     qword ptr [rsp+100h+cbInput], rax
0x180015816  mov     dword ptr [rsp+100h+pbInput], ebx
0x18001581a  call    WPP_SF_sDsd
0x18001581f  jmp     loc_180015792
0x180015824  call    cs:__imp_GetLastError
0x18001582b  nop     dword ptr [rax+rax+00h]
0x180015830  mov     ebx, eax
0x180015832  mov     rdx, cs:WPP_GLOBAL_Control
0x180015839  cmp     rdx, r12
0x18001583c  jz      short loc_180015848
0x18001583e  test    byte ptr [rdx+1Ch], 1
0x180015842  jnz     loc_1800158CD
0x180015848  cmp     ebx, 6BBh
0x18001584e  jnz     loc_180015AAE
0x180015854  cmp     r15d, 5
0x180015858  jnb     loc_180015AAE
0x18001585e  mov     ecx, r13d; dwMilliseconds
0x180015861  call    cs:__imp_Sleep
0x180015868  nop     dword ptr [rax+rax+00h]
0x18001586d  mov     r8, [rbp+0B0h+var_A8]
0x180015871  add     r13d, r13d
0x180015874  inc     r15d
0x180015877  jmp     loc_1800156CB
0x18001587c  lea     rcx, [rdi-8]
0x180015880  cmp     dword ptr [rcx], 70616548h
0x180015886  jnz     loc_1800157D7
0x18001588c  mov     rax, cs:g_pfnFree
0x180015893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015898  jmp     loc_1800157D7
0x18001589d  mov     rax, [rbp+0B0h+phKey]
0x1800158a1  mov     [r14+70h], rax
0x1800158a5  jmp     loc_180015792
0x1800158aa  cmp     dword ptr [rbp+0B0h+P], 14h
0x1800158ae  jnb     loc_180015960
0x1800158b4  cmp     rdx, r12
0x1800158b7  jz      short loc_1800158C3
0x1800158b9  test    byte ptr [rdx+1Ch], 1
0x1800158bd  jnz     loc_180015A5A
0x1800158c3  mov     eax, 80090003h
0x1800158c8  jmp     loc_1800157D9
0x1800158cd  mov     rcx, [rdx+10h]
0x1800158d1  lea     r9, aDwsts; "dwSts"
0x1800158d8  mov     [rsp+100h+dwFlags], 215h
0x1800158e0  mov     qword ptr [rsp+100h+cbInput], rsi
0x1800158e5  mov     dword ptr [rsp+100h+pbInput], ebx
0x1800158e9  call    WPP_SF_sDsd
0x1800158ee  mov     rdx, cs:WPP_GLOBAL_Control
0x1800158f5  jmp     loc_180015848
0x1800158fa  mov     ebx, 57h ; 'W'
0x1800158ff  mov     rdx, cs:WPP_GLOBAL_Control
0x180015906  lea     r12, WPP_GLOBAL_Control
0x18001590d  cmp     rdx, r12
0x180015910  jz      loc_1800157D7
0x180015916  test    byte ptr [rdx+1Ch], 1
0x18001591a  jnz     loc_180015E80
0x180015920  cmp     rdx, r12
0x180015923  jz      loc_1800157D7
0x180015929  test    byte ptr [rdx+1Ch], 1
0x18001592d  jz      loc_1800157D7
0x180015933  mov     rcx, [rdx+10h]
0x180015937  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001593e  mov     [rsp+100h+dwFlags], 6FAh
0x180015946  lea     r9, aStatus; "Status"
0x18001594d  mov     qword ptr [rsp+100h+cbInput], rax
0x180015952  mov     dword ptr [rsp+100h+pbInput], ebx
0x180015956  call    WPP_SF_sDsd
0x18001595b  jmp     loc_1800157D7
0x180015960  mov     rax, [rbp+0B0h+P+8]
0x180015964  mov     r8d, 0FFFFFFFFh
0x18001596a  mov     [rbp+0B0h+var_90], rax
0x18001596e  mov     r15d, [rax+8]
0x180015972  add     r15d, 7
0x180015976  shr     r15d, 3
0x18001597a  lea     eax, [r15+1]
0x18001597e  shr     eax, 1
0x180015980  mov     ecx, eax
0x180015982  mov     [rbp+0B0h+var_88], rcx
0x180015986  lea     rax, [rax+rax*8]
0x18001598a  cmp     rax, r8
0x18001598d  ja      loc_180015A3D
0x180015993  lea     edx, [rax+14h]
0x180015996  cmp     edx, eax
0x180015998  jb      loc_180015A8B
0x18001599e  cmp     dword ptr [rbp+0B0h+P], edx
0x1800159a1  jb      loc_180015E4D
0x1800159a7  lea     esi, [r15+1Ch]
0x1800159ab  lea     esi, [rsi+rcx*2]
0x1800159ae  mov     ebx, esi
0x1800159b0  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800159b7  ja      short loc_180015A09
0x1800159b9  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800159c0  add     rcx, 8
0x1800159c4  add     rcx, rbx
0x1800159c7  cmp     rcx, rbx
0x1800159ca  jb      short loc_180015A09
0x1800159cc  call    VerifyStackAvailable
0x1800159d1  test    eax, eax
0x1800159d3  jz      short loc_180015A09
0x1800159d5  lea     rax, [rsi+8]
0x1800159d9  lea     rcx, [rax+0Fh]
0x1800159dd  cmp     rcx, rax
0x1800159e0  ja      short loc_1800159EC
0x1800159e2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800159ec  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800159f0  mov     rax, rcx
0x1800159f3  call    _alloca_probe
0x1800159f8  sub     rsp, rcx
0x1800159fb  lea     rdi, [rsp+100h+pcbResult]
0x180015a00  test    rdi, rdi
0x180015a03  jnz     loc_180015ABE
0x180015a09  lea     rcx, [rsi+8]
0x180015a0d  cmp     rcx, rbx
0x180015a10  jb      loc_180015ACE
0x180015a16  mov     rax, cs:g_pfnAllocate
0x180015a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a22  mov     rdi, rax
0x180015a25  test    rax, rax
0x180015a28  jz      loc_180015ACE
0x180015a2e  mov     dword ptr [rax], 70616548h
0x180015a34  add     rdi, 8
0x180015a38  jmp     loc_180015ACE
0x180015a3d  cmp     rdx, r12
0x180015a40  jz      loc_1800158C3
0x180015a46  test    byte ptr [rdx+1Ch], 1
0x180015a4a  jz      loc_1800158C3
0x180015a50  mov     [rsp+100h+dwFlags], 714h
0x180015a58  jmp     short loc_180015A62
0x180015a5a  mov     [rsp+100h+dwFlags], 708h
0x180015a62  mov     rcx, [rdx+10h]
0x180015a66  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015a6d  mov     qword ptr [rsp+100h+cbInput], rax
0x180015a72  lea     r9, aStatus; "Status"
0x180015a79  mov     dword ptr [rsp+100h+pbInput], 80090003h
0x180015a81  call    WPP_SF_sDsd
0x180015a86  jmp     loc_1800158C3
0x180015a8b  mov     r9d, 71Bh
0x180015a91  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015a98  mov     ecx, 80090003h
0x180015a9d  lea     rdx, aStatus; "Status"
0x180015aa4  call    DebugTraceError
0x180015aa9  jmp     loc_1800158C3
0x180015aae  xor     r13d, r13d
0x180015ab1  test    ebx, ebx
0x180015ab3  jz      loc_180015718
0x180015ab9  jmp     loc_180015920
0x180015abe  mov     dword ptr [rdi], 6B637453h
0x180015ac4  add     rdi, 8
0x180015ac8  jz      loc_180015A09
0x180015ace  test    rdi, rdi
0x180015ad1  jz      loc_180015E58
0x180015ad7  mov     rdx, [rbp+0B0h+var_90]
0x180015adb  lea     r9, [rdi+18h]
0x180015adf  mov     dword ptr [rdi], 32415352h
0x180015ae5  lea     r13, aRsaprivateblob; "RSAPRIVATEBLOB"
0x180015aec  mov     r8d, 4
0x180015af2  mov     r11d, r15d
  ... truncated ...
```
