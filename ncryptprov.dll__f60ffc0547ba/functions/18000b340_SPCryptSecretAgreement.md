# SPCryptSecretAgreement

- ea: `0x18000b340`
- end: `0x18000bdc4`
- name: `SPCryptSecretAgreement`
- size: `2692`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800086d0`
- `0x180009440`
- `0x18000af80`
- `0x18000b250`
- `0x18000b340`
- `0x18000ceb0`
- `0x180014558`
- `0x180014bec`
- `0x180014c60`
- `0x18004663c`
- `0x180052480`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000b775`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000b775`
- `ntdll!RtlReleaseResource` at `0x18000b793`
- `ntdll!RtlReleaseResource` at `0x18000b793`
- `ntdll!RtlAllocateHeap` at `0x18000b580`
- `ntdll!RtlAllocateHeap` at `0x18000b580`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b6a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b6a1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ba58`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ba58`
- `bcrypt!BCryptExportKey` at `0x18000b941`
- `bcrypt!BCryptExportKey` at `0x18000bcf3`
- `bcrypt!BCryptExportKey` at `0x18000b941`
- `bcrypt!BCryptExportKey` at `0x18000bcf3`

## string_xrefs

- `0x18000b3cb`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b449`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b49d`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b67f`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b6f7`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b71d`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b746`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b836`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b8ff`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b975`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000b9a6`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000ba09`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000ba31`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000ba64`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000bab7`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000baf9`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000bb36`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000bb85`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000bbb1`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000bca9`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000bd13`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 __fastcall SPCryptSecretAgreement(__int64 a1, const char *a2, __int64 a3, _QWORD *a4, int a5)
{
  __int64 v6; // rsi
  UCHAR *v7; // rdi
  int v8; // ebx
  __int64 v9; // r12
  _QWORD *v10; // rcx
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // r14
  __int64 v15; // r15
  _QWORD *v16; // r12
  _QWORD *v17; // rax
  int v18; // ecx
  __int64 v19; // rdx
  _DWORD *Heap; // rax
  int v22; // edx
  int v23; // r12d
  _BYTE *v24; // rax
  __int64 v25; // rax
  unsigned int v26; // eax
  int v27; // r8d
  _BYTE *v28; // rax
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  bool v32; // zf
  int v33; // eax
  __int64 v34; // r9
  int v35; // ecx
  int v36; // ecx
  unsigned __int64 v37; // rbx
  unsigned __int64 v38; // rcx
  __int64 v39; // rcx
  unsigned __int64 v40; // rcx
  void *v41; // rsp
  void *v42; // rsp
  UCHAR *v43; // rax
  NTSTATUS v44; // eax
  __int64 v45; // r9
  __int64 v46; // [rsp+0h] [rbp-40h] BYREF
  ULONG cbOutput[2]; // [rsp+20h] [rbp-20h]
  ULONG *pcbResult; // [rsp+28h] [rbp-18h]
  ULONG dwFlags; // [rsp+30h] [rbp-10h]
  int v50; // [rsp+40h] [rbp+0h] BYREF
  ULONG v51; // [rsp+44h] [rbp+4h] BYREF
  __int64 v52; // [rsp+48h] [rbp+8h] BYREF
  UCHAR *v53; // [rsp+50h] [rbp+10h]
  __int64 v54; // [rsp+58h] [rbp+18h] BYREF
  __int64 v55; // [rsp+60h] [rbp+20h] BYREF
  _QWORD *v56; // [rsp+68h] [rbp+28h]

  v56 = a4;
  v54 = 0;
  v6 = (__int64)a2;
  v55 = 0;
  v7 = 0;
  v53 = 0;
  v51 = 0;
  if ( !a2 || *(_DWORD *)a2 < 0x248u || *((_DWORD *)a2 + 1) != 1263751243 )
  {
    v52 = 0;
    v8 = -2146893786;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v8;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
      35);
    v9 = v52;
    goto LABEL_43;
  }
  v52 = (__int64)a2;
  v9 = (__int64)a2;
  if ( !a3 || *(_DWORD *)a3 < 0x248u || *(_DWORD *)(a3 + 4) != 1263751243 )
  {
    v8 = -2146893786;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v8;
    dwFlags = 5932;
    pcbResult = (ULONG *)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c";
    cbOutput[0] = -2146893786;
    goto LABEL_64;
  }
  if ( !a4 )
  {
    v8 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 5939);
    goto LABEL_43;
  }
  if ( (a5 & 0xFFFFFFBF) != 0 )
  {
    v8 = -2146893815;
    DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 5946);
    goto LABEL_43;
  }
  if ( (*(_BYTE *)(a3 + 40) & 4) == 0 || (a2[40] & 4) == 0 )
  {
    v8 = -2146893808;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v8;
    dwFlags = 5961;
    pcbResult = (ULONG *)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c";
    cbOutput[0] = -2146893808;
    goto LABEL_64;
  }
  v11 = *((_DWORD *)a2 + 107);
  v12 = 64;
  a2 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c";
  if ( (v11 & 0x10) != 0 )
  {
    v52 = v6;
    v14 = v6;
    v15 = v6;
    if ( (v11 & 0x20) == 0 || (v11 & 2) != 0 )
      goto LABEL_23;
    goto LABEL_77;
  }
  v50 = 0;
  if ( (v11 & 5) == 5 )
  {
    Sleep(0x1F4u);
    a2 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c";
    v50 = -2146893778;
  }
  v13 = *(_QWORD *)(v6 + 416);
  if ( !v13 )
    goto LABEL_21;
  v22 = *(_DWORD *)(v6 + 428);
  if ( (v22 & 2) != 0 )
  {
LABEL_51:
    a2 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c";
LABEL_21:
    *(_DWORD *)(v6 + 428) &= ~2u;
    v14 = v6;
    v15 = v6;
    goto LABEL_22;
  }
  v23 = *(_DWORD *)(v13 + 4);
  if ( (v23 & 7) == 0 && (v22 & 0x20) == 0 )
  {
    v9 = v6;
    goto LABEL_51;
  }
  v28 = (_BYTE *)(v6 + 432);
  v52 = v6;
  v29 = 64;
  v14 = v6;
  v15 = v6;
  do
  {
    *v28++ = 0;
    --v29;
  }
  while ( v29 );
  v30 = SKCacheLookup(v6);
  v31 = *(unsigned int *)(v6 + 428);
  if ( v30 >= 0 )
  {
    v9 = v6;
    *(_DWORD *)(v6 + 428) = v31 | 8;
LABEL_113:
    a2 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c";
    goto LABEL_22;
  }
  if ( (v31 & 0x20) == 0 )
  {
    v9 = v6;
    goto LABEL_105;
  }
  v32 = v23 == 0;
  v9 = v6;
  if ( !v32 || (unsigned int)OpenConsentKeyForAppContainer(v31, v6, 0) )
  {
LABEL_105:
    if ( *(_QWORD *)(v9 + 224) || *(_QWORD *)(v9 + 256) )
    {
      if ( g_dwStrongKeyCacheDuration && *(_QWORD *)(v9 + 496) && g_dwStrongKeyCacheDuration == -1 )
        goto LABEL_113;
      v34 = 542;
    }
    else
    {
      v34 = 552;
    }
    DebugTraceError(2148073518LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v34);
    goto LABEL_77;
  }
  v33 = SKCacheAdd(v6);
  a2 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c";
  if ( !v33 )
    *(_DWORD *)(v6 + 428) |= 8u;
LABEL_22:
  if ( v50 >= 0 )
    goto LABEL_23;
  if ( v50 != -2146893778 )
  {
    v8 = v50;
    DebugTraceError((unsigned int)v50, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 748);
LABEL_61:
    DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 5975);
LABEL_62:
    v7 = v53;
    goto LABEL_43;
  }
LABEL_77:
  if ( (a5 & 0x40) != 0 )
  {
    v8 = -2146893790;
    goto LABEL_61;
  }
  v8 = KspCallCredUI(v9, 1u);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        v8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        253);
LABEL_82:
    if ( v8 < 0 )
      goto LABEL_61;
    goto LABEL_27;
  }
LABEL_23:
  v16 = (_QWORD *)(v14 + 416);
  while ( 1 )
  {
    v17 = (_QWORD *)(v14 + 416);
    if ( *(_QWORD *)(v15 + 112) )
      break;
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(v6 + 304), 1u);
    v50 = KspUnprotectKey(v6);
    RtlReleaseResource((PRTL_RESOURCE)(v6 + 304));
    if ( *(_QWORD *)(v15 + 112) )
    {
      v17 = v16;
      if ( !v50 )
        break;
    }
    v16 = (_QWORD *)(v6 + 416);
    v25 = *(_QWORD *)(v6 + 416);
    if ( v25 && (*(_BYTE *)(v25 + 4) & 4) != 0 )
    {
      v8 = -2146893821;
      DebugTraceError(2148073475LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 797);
      v9 = v52;
      goto LABEL_61;
    }
    *(_DWORD *)(v6 + 428) |= 4u;
    if ( (unsigned int)KspCheckStrongKey(v6) != -2146893778 )
    {
      v8 = v50;
      goto LABEL_121;
    }
    *(_DWORD *)(v6 + 428) |= 4u;
    v26 = KspCallCredUI(v6, 1u);
    v8 = v26;
    if ( v26 )
    {
      DebugTraceError(v26, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 815);
LABEL_121:
      v9 = v52;
      goto LABEL_82;
    }
    *(_DWORD *)(v6 + 428) &= ~4u;
  }
  if ( !*v17 )
  {
    v9 = v52;
    goto LABEL_27;
  }
  v8 = 0;
  v9 = v6;
  if ( g_dwStrongKeyCacheDuration )
    GetSystemTimeAsFileTime((LPFILETIME)(v6 + 496));
  if ( (*(_DWORD *)(v6 + 428) & 8) == 0 )
  {
    v8 = SKCacheAdd(v6);
    if ( !v8 )
      *(_DWORD *)(v6 + 428) |= 8u;
  }
  v24 = (_BYTE *)(v6 + 432);
  do
  {
    *v24++ = 0;
    --v12;
  }
  while ( v12 );
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        v8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        65);
    goto LABEL_61;
  }
LABEL_27:
  v18 = *(_DWORD *)(*(_QWORD *)(v9 + 64) + 32LL);
  if ( v18 != 196618 )
  {
    v35 = v18 - 196610;
    if ( v35 )
    {
      v36 = v35 - 5;
      if ( v36 )
      {
        if ( (unsigned int)(v36 - 1) >= 2 )
        {
          v8 = -2146893816;
          goto LABEL_62;
        }
      }
    }
  }
  if ( !*(_DWORD *)(v9 + 144) )
  {
    v7 = v53;
    goto LABEL_30;
  }
  v8 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(a3 + 104), 0, L"PUBLICBLOB", 0, 0, &v51, 0);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        v27,
        (unsigned int)"Status",
        v8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        114);
      v7 = v53;
      goto LABEL_43;
    }
    goto LABEL_62;
  }
  v37 = v51;
  v7 = 0;
  if ( !v51 )
    goto LABEL_148;
  if ( v51 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_148;
  v38 = v51 + g_ulAdditionalProbeSize + 8;
  if ( v38 < v51 || !(unsigned int)VerifyStackAvailable(v38, a2) )
    goto LABEL_148;
  v39 = v37 + 23;
  if ( v37 + 23 <= v37 + 8 )
    v39 = 0xFFFFFFFFFFFFFF0LL;
  v40 = v39 & 0xFFFFFFFFFFFFFFF0uLL;
  v41 = alloca(v40);
  v42 = alloca(v40);
  v7 = (UCHAR *)&v50;
  if ( &v46 == (__int64 *)-64LL || (v50 = 1801679955, (v7 = (UCHAR *)&v52) == 0) )
  {
LABEL_148:
    if ( v37 + 8 >= v37 )
    {
      v43 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      v7 = v43;
      if ( v43 )
      {
        *(_DWORD *)v43 = 1885431112;
        v7 = v43 + 8;
      }
    }
  }
  if ( !v7 )
  {
    v8 = -2146893810;
    DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", 6010);
    goto LABEL_43;
  }
  v44 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(a3 + 104), 0, L"PUBLICBLOB", v7, v51, &v51, 0);
  v8 = v44;
  if ( v44 < 0 )
  {
    v45 = 6024;
LABEL_141:
    DebugTraceError((unsigned int)v44, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v45);
    goto LABEL_43;
  }
  v44 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, __int64 *, UCHAR *, ULONG, _DWORD))(*(_QWORD *)(v9 + 168) + 112LL))(
          *(_QWORD *)(v9 + 152),
          0,
          L"PUBLICBLOB",
          &v55,
          v7,
          v51,
          0);
  v8 = v44;
  if ( v44 < 0 )
  {
    v45 = 6038;
    goto LABEL_141;
  }
LABEL_30:
  v19 = v55;
  if ( !v55 )
    v19 = *(_QWORD *)(a3 + 104);
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, _QWORD))(*(_QWORD *)(v9 + 168) + 40LL))(
         *(_QWORD *)(v9 + 112),
         v19,
         &v54,
         0);
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      dwFlags = 6052;
      pcbResult = (ULONG *)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c";
      cbOutput[0] = v8;
LABEL_64:
      WPP_SF_sDsd(v10[2], (_DWORD)a2, a3, (unsigned int)"Status", cbOutput[0], (__int64)pcbResult, dwFlags);
    }
LABEL_43:
    if ( v54 && v8 && v8 != -2146893778 )
      KspCryptAuditCryptOperation(0, (_DWORD)a2, v9, 2486, v8);
    goto LABEL_35;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
  if ( !Heap )
  {
    v8 = -2146893810;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      dwFlags = 6063;
      pcbResult = (ULONG *)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c";
      cbOutput[0] = -2146893810;
      goto LABEL_64;
    }
    goto LABEL_43;
  }
  *Heap = 32;
  v8 = 0;
  Heap[1] = 1263751224;
  *((_QWORD *)Heap + 1) = v54;
  Heap[4] = *(_DWORD *)(v9 + 144);
  *((_QWORD *)Heap + 3) = *(_QWORD *)(v9 + 168);
  v54 = 0;
  *v56 = Heap;
LABEL_35:
  if ( v7 && *((_DWORD *)v7 - 2) == 1885431112 )
    ((void (__fastcall *)(UCHAR *))g_pfnFree)(v7 - 8);
  if ( v55 )
    (*(void (**)(void))(*(_QWORD *)(v9 + 168) + 136LL))();
  if ( v54 )
    (*(void (**)(void))(*(_QWORD *)(v9 + 168) + 56LL))();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b340  push    rbp
0x18000b342  push    rbx
0x18000b343  push    rsi
0x18000b344  push    rdi
0x18000b345  push    r12
0x18000b347  push    r13
0x18000b349  push    r14
0x18000b34b  push    r15
0x18000b34d  sub     rsp, 88h
0x18000b354  lea     rbp, [rsp+40h]
0x18000b359  mov     rax, cs:__security_cookie
0x18000b360  xor     rax, rbp
0x18000b363  mov     [rbp+80h+var_50], rax
0x18000b367  xor     ecx, ecx
0x18000b369  mov     rax, r9
0x18000b36c  mov     [rbp+80h+var_58], rax
0x18000b370  mov     r13, r8
0x18000b373  mov     [rbp+80h+var_68], rcx
0x18000b377  mov     rsi, rdx
0x18000b37a  mov     [rbp+80h+var_60], rcx
0x18000b37e  mov     edi, ecx
0x18000b380  mov     [rbp+80h+var_70], rcx
0x18000b384  mov     [rbp+80h+var_7C], ecx
0x18000b387  test    rdx, rdx
0x18000b38a  jz      short loc_18000B39D
0x18000b38c  cmp     dword ptr [rdx], 248h
0x18000b392  jb      short loc_18000B39D
0x18000b394  cmp     dword ptr [rdx+4], 4B53504Bh
0x18000b39b  jz      short loc_18000B3FC
0x18000b39d  mov     [rbp+80h+var_78], rcx
0x18000b3a1  mov     ebx, 80090026h
0x18000b3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3ad  lea     rsi, WPP_GLOBAL_Control
0x18000b3b4  cmp     rcx, rsi
0x18000b3b7  jz      loc_18000B5F8
0x18000b3bd  test    byte ptr [rcx+1Ch], 1
0x18000b3c1  jz      loc_18000B5F8
0x18000b3c7  mov     rcx, [rcx+10h]
0x18000b3cb  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b3d2  mov     [rsp+0C0h+dwFlags], 1723h
0x18000b3da  lea     r9, aStatus; "Status"
0x18000b3e1  mov     [rsp+0C0h+pcbResult], rax
0x18000b3e6  mov     [rsp+0C0h+cbOutput], 80090026h
0x18000b3ee  call    WPP_SF_sDsd
0x18000b3f3  mov     r12, [rbp+80h+var_78]
0x18000b3f7  jmp     loc_18000B62E
0x18000b3fc  mov     [rbp+80h+var_78], rsi
0x18000b400  mov     r12, rsi
0x18000b403  test    r13, r13
0x18000b406  jz      short loc_18000B41B
0x18000b408  cmp     dword ptr [r8], 248h
0x18000b40f  jb      short loc_18000B41B
0x18000b411  cmp     dword ptr [r8+4], 4B53504Bh
0x18000b419  jz      short loc_18000B462
0x18000b41b  mov     ebx, 80090026h
0x18000b420  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b427  lea     rsi, WPP_GLOBAL_Control
0x18000b42e  cmp     rcx, rsi
0x18000b431  jz      loc_18000B5F8
0x18000b437  test    byte ptr [rcx+1Ch], 1
0x18000b43b  jz      loc_18000B5F8
0x18000b441  mov     [rsp+0C0h+dwFlags], 172Ch
0x18000b449  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b450  mov     [rsp+0C0h+pcbResult], rax
0x18000b455  mov     [rsp+0C0h+cbOutput], 80090026h
0x18000b45d  jmp     loc_18000B72D
0x18000b462  test    rax, rax
0x18000b465  jz      loc_18000BA03
0x18000b46b  mov     ebx, [rbp+80h+arg_20]
0x18000b471  test    ebx, 0FFFFFFBFh
0x18000b477  jnz     loc_18000BA2B
0x18000b47d  test    byte ptr [r8+28h], 4
0x18000b482  jz      loc_18000B8D1
0x18000b488  test    byte ptr [rdx+28h], 4
0x18000b48c  jz      loc_18000B8D1
0x18000b492  mov     eax, [rdx+1ACh]
0x18000b498  mov     edi, 40h ; '@'
0x18000b49d  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b4a4  test    al, 10h
0x18000b4a6  jnz     loc_18000B84F
0x18000b4ac  and     eax, 5
0x18000b4af  mov     [rbp+80h+var_80], ecx
0x18000b4b2  cmp     al, 5
0x18000b4b4  jz      loc_18000BA53
0x18000b4ba  mov     rcx, [rsi+1A0h]
0x18000b4c1  test    rcx, rcx
0x18000b4c4  jnz     loc_18000B65A
0x18000b4ca  and     dword ptr [rsi+1ACh], 0FFFFFFFDh
0x18000b4d1  mov     r14, rsi
0x18000b4d4  mov     r15, rsi
0x18000b4d7  mov     eax, [rbp+80h+var_80]
0x18000b4da  test    eax, eax
0x18000b4dc  js      loc_18000BB42
0x18000b4e2  lea     r12, [r14+1A0h]
0x18000b4e9  cmp     qword ptr [r15+70h], 0
0x18000b4ee  lea     rax, [r14+1A0h]
0x18000b4f5  jz      loc_18000B76C
0x18000b4fb  cmp     qword ptr [rax], 0
0x18000b4ff  jnz     loc_18000B68B
0x18000b505  mov     r12, [rbp+80h+var_78]
0x18000b509  lea     rsi, WPP_GLOBAL_Control
0x18000b510  mov     rax, [r12+40h]
0x18000b515  mov     ecx, [rax+20h]
0x18000b518  cmp     ecx, 3000Ah
0x18000b51e  jnz     loc_18000BBDB
0x18000b524  cmp     dword ptr [r12+90h], 0
0x18000b52d  jnz     loc_18000B918
0x18000b533  mov     rdi, [rbp+80h+var_70]
0x18000b537  mov     rdx, [rbp+80h+var_60]
0x18000b53b  test    rdx, rdx
0x18000b53e  jnz     short loc_18000B544
0x18000b540  mov     rdx, [r13+68h]
0x18000b544  mov     rax, [r12+0A8h]
0x18000b54c  lea     r8, [rbp+80h+var_68]
0x18000b550  mov     rcx, [r12+70h]
0x18000b555  xor     r9d, r9d
0x18000b558  mov     rax, [rax+28h]
0x18000b55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b561  mov     ebx, eax
0x18000b563  test    eax, eax
0x18000b565  js      loc_18000B618
0x18000b56b  mov     rcx, gs:60h
0x18000b574  xor     edx, edx; Flags
0x18000b576  mov     r8d, 20h ; ' '; Size
0x18000b57c  mov     rcx, [rcx+30h]; HeapHandle
0x18000b580  call    cs:__imp_RtlAllocateHeap
0x18000b587  nop     dword ptr [rax+rax+00h]
0x18000b58c  mov     rcx, rax
0x18000b58f  test    rax, rax
0x18000b592  jz      loc_18000B80F
0x18000b598  mov     dword ptr [rax], 20h ; ' '
0x18000b59e  xor     ebx, ebx
0x18000b5a0  mov     dword ptr [rax+4], 4B535038h
0x18000b5a7  mov     rax, [rbp+80h+var_68]
0x18000b5ab  mov     [rcx+8], rax
0x18000b5af  mov     eax, [r12+90h]
0x18000b5b7  mov     [rcx+10h], eax
0x18000b5ba  mov     rax, [r12+0A8h]
0x18000b5c2  mov     [rcx+18h], rax
0x18000b5c6  mov     rax, [rbp+80h+var_58]
0x18000b5ca  mov     [rbp+80h+var_68], 0
0x18000b5d2  mov     [rax], rcx
0x18000b5d5  test    rdi, rdi
0x18000b5d8  jnz     loc_18000BD73
0x18000b5de  mov     rcx, [rbp+80h+var_60]
0x18000b5e2  test    rcx, rcx
0x18000b5e5  jnz     loc_18000BD95
0x18000b5eb  mov     rcx, [rbp+80h+var_68]
0x18000b5ef  test    rcx, rcx
0x18000b5f2  jnz     loc_18000BDAE
0x18000b5f8  mov     eax, ebx
0x18000b5fa  mov     rcx, [rbp+80h+var_50]
0x18000b5fe  xor     rcx, rbp; StackCookie
0x18000b601  call    __security_check_cookie
0x18000b606  lea     rsp, [rbp+48h]
0x18000b60a  pop     r15
0x18000b60c  pop     r14
0x18000b60e  pop     r13
0x18000b610  pop     r12
0x18000b612  pop     rdi
0x18000b613  pop     rsi
0x18000b614  pop     rbx
0x18000b615  pop     rbp
0x18000b616  retn
0x18000b618  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b61f  cmp     rcx, rsi
0x18000b622  jz      short loc_18000B62E
0x18000b624  test    byte ptr [rcx+1Ch], 1
0x18000b628  jnz     loc_18000B715
0x18000b62e  cmp     [rbp+80h+var_68], 0
0x18000b633  jz      short loc_18000B5D5
0x18000b635  test    ebx, ebx
0x18000b637  jz      short loc_18000B5D5
0x18000b639  cmp     ebx, 8009002Eh
0x18000b63f  jz      short loc_18000B5D5
0x18000b641  mov     r9d, 9B6h
0x18000b647  mov     [rsp+0C0h+cbOutput], ebx
0x18000b64b  mov     r8, r12
0x18000b64e  xor     ecx, ecx
0x18000b650  call    KspCryptAuditCryptOperation
0x18000b655  jmp     loc_18000B5D5
0x18000b65a  mov     edx, [rsi+1ACh]
0x18000b660  test    dl, 2
0x18000b663  jnz     short loc_18000B67F
0x18000b665  mov     r12d, [rcx+4]
0x18000b669  test    r12b, 7
0x18000b66d  jnz     loc_18000BA77
0x18000b673  test    dl, 20h
0x18000b676  jnz     loc_18000BA77
0x18000b67c  mov     r12, rsi
0x18000b67f  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b686  jmp     loc_18000B4CA
0x18000b68b  mov     eax, cs:g_dwStrongKeyCacheDuration
0x18000b691  xor     ebx, ebx
0x18000b693  mov     r12, rsi
0x18000b696  test    eax, eax
0x18000b698  jz      short loc_18000B6AD
0x18000b69a  lea     rcx, [rsi+1F0h]; lpSystemTimeAsFileTime
0x18000b6a1  call    cs:__imp_GetSystemTimeAsFileTime
0x18000b6a8  nop     dword ptr [rax+rax+00h]
0x18000b6ad  mov     eax, [rsi+1ACh]
0x18000b6b3  test    al, 8
0x18000b6b5  jz      loc_18000B8B3
0x18000b6bb  lea     rax, [r12+1B0h]
0x18000b6c3  mov     byte ptr [rax], 0
0x18000b6c6  lea     rax, [rax+1]
0x18000b6ca  sub     rdi, 1
0x18000b6ce  jnz     short loc_18000B6C3
0x18000b6d0  test    ebx, ebx
0x18000b6d2  jns     loc_18000B509
0x18000b6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6df  lea     rsi, WPP_GLOBAL_Control
0x18000b6e6  cmp     rcx, rsi
0x18000b6e9  jz      short loc_18000B6F1
0x18000b6eb  test    byte ptr [rcx+1Ch], 1
0x18000b6ef  jnz     short loc_18000B742
0x18000b6f1  mov     r9d, 1757h
0x18000b6f7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b6fe  lea     rdx, aStatus; "Status"
0x18000b705  mov     ecx, ebx
0x18000b707  call    DebugTraceError
0x18000b70c  mov     rdi, [rbp+80h+var_70]
0x18000b710  jmp     loc_18000B62E
0x18000b715  mov     [rsp+0C0h+dwFlags], 17A4h
0x18000b71d  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b724  mov     [rsp+0C0h+pcbResult], rax
0x18000b729  mov     [rsp+0C0h+cbOutput], ebx
0x18000b72d  mov     rcx, [rcx+10h]
0x18000b731  lea     r9, aStatus; "Status"
0x18000b738  call    WPP_SF_sDsd
0x18000b73d  jmp     loc_18000B62E
0x18000b742  mov     rcx, [rcx+10h]
0x18000b746  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b74d  mov     [rsp+0C0h+dwFlags], 341h
0x18000b755  lea     r9, aStatus; "Status"
0x18000b75c  mov     [rsp+0C0h+pcbResult], rax
0x18000b761  mov     [rsp+0C0h+cbOutput], ebx
0x18000b765  call    WPP_SF_sDsd
0x18000b76a  jmp     short loc_18000B6F1
0x18000b76c  mov     dl, 1; Wait
0x18000b76e  lea     rcx, [rsi+130h]; Resource
0x18000b775  call    cs:__imp_RtlAcquireResourceExclusive
0x18000b77c  nop     dword ptr [rax+rax+00h]
0x18000b781  mov     rcx, rsi
0x18000b784  call    KspUnprotectKey
0x18000b789  lea     rcx, [rsi+130h]; Resource
0x18000b790  mov     [rbp+80h+var_80], eax
0x18000b793  call    cs:__imp_RtlReleaseResource
0x18000b79a  nop     dword ptr [rax+rax+00h]
0x18000b79f  cmp     qword ptr [r15+70h], 0
0x18000b7a4  jnz     short loc_18000B801
0x18000b7a6  lea     r12, [rsi+1A0h]
0x18000b7ad  mov     rbx, rsi
0x18000b7b0  mov     rax, [r12]
0x18000b7b4  test    rax, rax
0x18000b7b7  jnz     loc_18000BB75
0x18000b7bd  or      dword ptr [rsi+1ACh], 4
0x18000b7c4  mov     rcx, rbx
0x18000b7c7  call    KspCheckStrongKey
0x18000b7cc  cmp     eax, 8009002Eh
0x18000b7d1  jnz     loc_18000BBC8
0x18000b7d7  or      dword ptr [rsi+1ACh], 4
0x18000b7de  mov     edx, 1
0x18000b7e3  mov     rcx, rbx
0x18000b7e6  call    KspCallCredUI
0x18000b7eb  mov     ebx, eax
0x18000b7ed  test    eax, eax
0x18000b7ef  jnz     loc_18000BBAB
0x18000b7f5  and     dword ptr [rsi+1ACh], 0FFFFFFFBh
0x18000b7fc  jmp     loc_18000B4E9
0x18000b801  cmp     [rbp+80h+var_80], 0
0x18000b805  mov     rax, r12
0x18000b808  jnz     short loc_18000B7A6
0x18000b80a  jmp     loc_18000B4FB
0x18000b80f  mov     ebx, 8009000Eh
0x18000b814  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b81b  cmp     rcx, rsi
0x18000b81e  jz      loc_18000B62E
0x18000b824  test    byte ptr [rcx+1Ch], 1
0x18000b828  jz      loc_18000B62E
0x18000b82e  mov     [rsp+0C0h+dwFlags], 17AFh
0x18000b836  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b83d  mov     [rsp+0C0h+pcbResult], rax
0x18000b842  mov     [rsp+0C0h+cbOutput], 8009000Eh
0x18000b84a  jmp     loc_18000B72D
0x18000b84f  mov     [rbp+80h+var_78], rsi
0x18000b853  mov     r14, rsi
0x18000b856  mov     r15, rsi
0x18000b859  test    al, 20h
0x18000b85b  jz      loc_18000B4E2
0x18000b861  test    al, 2
0x18000b863  jnz     loc_18000B4E2
0x18000b869  test    dil, bl
0x18000b86c  jnz     loc_18000BB6B
0x18000b872  mov     edx, 1
0x18000b877  mov     rcx, r12
0x18000b87a  call    KspCallCredUI
0x18000b87f  mov     ebx, eax
0x18000b881  test    eax, eax
0x18000b883  jz      loc_18000B4E2
  ... truncated ...
```
