# TlsExpandWriteKey

- ea: `0x180003050`
- end: `0x18000379a`
- name: `TlsExpandWriteKey`
- size: `1866`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009fb0`

## callees

- `0x180001de8`
- `0x180003050`
- `0x180003ef0`
- `0x18000b594`
- `0x18000b654`
- `0x18000e820`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x180003494`
- `bcrypt!BCryptSetProperty` at `0x180003494`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180003705`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180003705`
- `bcrypt!BCryptGetProperty` at `0x1800034d2`
- `bcrypt!BCryptGetProperty` at `0x18000354e`
- `bcrypt!BCryptGetProperty` at `0x1800034d2`
- `bcrypt!BCryptGetProperty` at `0x18000354e`
- `bcrypt!BCryptDestroyKey` at `0x1800035ed`
- `bcrypt!BCryptDestroyKey` at `0x1800035ed`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800033e8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000351c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180003622`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800033e8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000351c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180003622`
- `ntdll!RtlFreeHeap` at `0x1800032a1`
- `ntdll!RtlFreeHeap` at `0x1800032a1`
- `ntdll!RtlAllocateHeap` at `0x18000318e`
- `ntdll!RtlAllocateHeap` at `0x1800031e7`
- `ntdll!RtlAllocateHeap` at `0x18000318e`
- `ntdll!RtlAllocateHeap` at `0x1800031e7`

## string_xrefs

- `0x18000321c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800032f9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000334a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003393`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800035cc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003631`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800036cc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180003776`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800033bf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180003567`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000359d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000360a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000365e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall TlsExpandWriteKey(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  SIZE_T v6; // r13
  PVOID v7; // r14
  __int64 v8; // rbp
  __int64 v9; // rcx
  __int64 v10; // rsi
  int v11; // r9d
  __int64 *v12; // r14
  __int64 *v13; // r14
  LPCWSTR *v14; // rcx
  _QWORD *v15; // rcx
  ULONG v16; // ebp
  char *Heap; // rax
  int v18; // edx
  char *v19; // rsi
  SIZE_T v20; // rbx
  PVOID v21; // rax
  int v22; // edx
  UCHAR *v23; // r15
  _BYTE *v24; // rdx
  unsigned int v25; // edi
  __int64 v26; // rax
  UCHAR *v27; // rax
  _QWORD *v29; // rcx
  int v30; // eax
  int v31; // r8d
  bool v32; // zf
  BCRYPT_ALG_HANDLE v33; // rbp
  int v34; // r8d
  NTSTATUS SymmetricKey; // eax
  __int64 v36; // r9
  void *v37; // rdi
  int v38; // eax
  int cbSecret; // [rsp+28h] [rbp-70h]
  int cbSecreta; // [rsp+28h] [rbp-70h]
  ULONG pcbResult; // [rsp+40h] [rbp-58h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+48h] [rbp-50h]
  PVOID P; // [rsp+50h] [rbp-48h]
  int hObject; // [rsp+A0h] [rbp+8h]
  NTSTATUS hObjecta; // [rsp+A0h] [rbp+8h]
  BCRYPT_HANDLE hObjectb; // [rsp+A0h] [rbp+8h]
  ULONG pbOutput; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a2;
  if ( !a1 || !a2 || (v5 = *(_QWORD *)(a2 + 16)) == 0 || !a3 )
  {
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4228);
    return (unsigned int)-2146893785;
  }
  v6 = *(unsigned int *)(v5 + 32);
  if ( (unsigned int)v6 > 0xFFFF || (v7 = *(PVOID *)(a2 + 32), (P = v7) == 0) )
  {
    v25 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        141);
    return v25;
  }
  v8 = *(unsigned int *)(v5 + 40);
  v9 = 16LL * (unsigned int)v8;
  v10 = v9 + a1;
  if ( *(_DWORD *)(v9 + a1 + 28) )
    goto LABEL_15;
  v11 = *(_DWORD *)(a1 + 12);
  hAlgorithm = 0;
  pbOutput = 0;
  if ( (v11 & 1) != 0 )
    v12 = l_NonPagedCipherEntryCache;
  else
    v12 = l_PagedCipherEntryCache;
  v13 = &v12[(unsigned __int64)v9 / 8];
  if ( (unsigned int)v8 < g_dwCipherInfoTotalCount )
  {
    _mm_lfence();
    v14 = (LPCWSTR *)g_pCipherInfo[v8];
    if ( v14 )
    {
      if ( *((_DWORD *)v13 + 3) )
      {
LABEL_50:
        *(_QWORD *)(v10 + 16) = *v13;
        v30 = *((_DWORD *)v13 + 2);
        v7 = P;
        *(_DWORD *)(v10 + 24) = v30;
LABEL_15:
        v15 = WPP_GLOBAL_Control;
        goto LABEL_16;
      }
      hObjecta = GetAlgorithmHandle(*v14);
      LODWORD(a2) = hObjecta;
      if ( hObjecta < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return (unsigned int)hObjecta;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_45:
          if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 )
            WPP_SF_sDsd(
              v29[2],
              a2,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              (unsigned int)"Status",
              a2,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              154);
          return (unsigned int)hObjecta;
        }
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          hObjecta,
          v31,
          (unsigned int)"Status",
          hObjecta,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          131);
      }
      else
      {
        v32 = (_DWORD)v8 == 5;
        v33 = hAlgorithm;
        if ( !v32 )
          goto LABEL_55;
        pcbResult = 0;
        hObjecta = BCryptSetProperty(hAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0);
        if ( hObjecta < 0 )
        {
          DebugTraceError(
            (unsigned int)hObjecta,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            4754);
          BCryptCloseAlgorithmProvider(hAlgorithm, 0);
        }
        else
        {
          hObjecta = BCryptGetProperty(hAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
          LODWORD(a2) = hObjecta;
          if ( hObjecta >= 0 )
          {
LABEL_55:
            hObjectb = (BCRYPT_HANDLE)_InterlockedCompareExchange64(v13, (signed __int64)v33, 0);
            if ( !hObjectb
              || (pcbResult = 0,
                  BCryptCloseAlgorithmProvider(v33, 0),
                  hObjecta = BCryptGetProperty(hObjectb, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0),
                  hObjecta >= 0) )
            {
              *((_DWORD *)v13 + 2) = pbOutput;
              *((_DWORD *)v13 + 3) = 1;
              goto LABEL_50;
            }
            DebugTraceError(
              (unsigned int)hObjecta,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              4794);
            goto LABEL_44;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              hObjecta,
              v34,
              (unsigned int)"Status",
              hObjecta,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              160);
          BCryptCloseAlgorithmProvider(v33, 0);
        }
      }
LABEL_44:
      LODWORD(a2) = hObjecta;
      v29 = WPP_GLOBAL_Control;
      goto LABEL_45;
    }
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      144,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      117);
    v7 = P;
    goto LABEL_15;
  }
  v7 = P;
LABEL_16:
  v16 = *(_DWORD *)(v10 + 24);
  if ( !v16 || (hAlgorithm = *(BCRYPT_ALG_HANDLE *)(v10 + 16)) == 0 )
  {
    v25 = -2146893783;
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v15[2],
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        162);
    return v25;
  }
  pbOutput = v16 + 112;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16 + 112);
  v19 = Heap;
  if ( !Heap )
  {
    v25 = -2146893810;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        172);
    return v25;
  }
  memset(Heap, 0, v16 + 112);
  *((_DWORD *)v19 + 1) = 1936944179;
  *(_DWORD *)v19 = v16 + 112;
  *((_DWORD *)v19 + 2) = *(_DWORD *)(v3 + 8);
  v20 = v6;
  *((_QWORD *)v19 + 2) = v5;
  *((_DWORD *)v19 + 27) = 5;
  *((_DWORD *)v19 + 26) = 12;
  v21 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  P = v21;
  if ( v21 )
  {
    LOWORD(cbSecret) = v6;
    v23 = (UCHAR *)v21;
    SymmetricKey = TlsExpandLabel(v7, "key", 0, 0, v21, cbSecret);
    hObject = SymmetricKey;
    if ( SymmetricKey >= 0 )
    {
      SymmetricKey = BCryptGenerateSymmetricKey(
                       hAlgorithm,
                       (BCRYPT_KEY_HANDLE *)v19 + 4,
                       (PUCHAR)v19 + 112,
                       v16,
                       v23,
                       v6,
                       0);
      hObject = SymmetricKey;
      if ( SymmetricKey >= 0 )
      {
        v37 = (void *)*((_QWORD *)v19 + 4);
        LOWORD(cbSecreta) = 12;
        v38 = TlsExpandLabel(v7, "iv", 0, 0, v19 + 56, cbSecreta);
        hObject = v38;
        if ( v38 >= 0 )
        {
          v25 = v38;
          *a3 = v19;
LABEL_27:
          v27 = v23;
          if ( (_DWORD)v6 )
          {
            do
            {
              *v27++ = 0;
              --v20;
            }
            while ( v20 );
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
          return v25;
        }
        DebugTraceError(
          (unsigned int)v38,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          4327);
        if ( v37 )
          BCryptDestroyKey(v37);
        goto LABEL_24;
      }
      v36 = 4312;
    }
    else
    {
      v36 = 4297;
    }
    DebugTraceError(
      (unsigned int)SymmetricKey,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      v36);
  }
  else
  {
    hObject = -2146893810;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        189);
    v23 = (UCHAR *)P;
  }
LABEL_24:
  v24 = v19;
  v25 = hObject;
  v26 = pbOutput;
  if ( pbOutput )
  {
    do
    {
      *v24++ = 0;
      --v26;
    }
    while ( v26 );
  }
  MSCryptFree(v19);
  if ( v23 )
    goto LABEL_27;
  return v25;
}

```

## disassembly

```asm
0x180003050  mov     r11, rsp
0x180003053  mov     [r11+18h], r8
0x180003057  push    rbx
0x180003058  push    rdi
0x180003059  sub     rsp, 88h
0x180003060  mov     rbx, rdx
0x180003063  mov     rax, rcx
0x180003066  test    rcx, rcx
0x180003069  jz      loc_180003765
0x18000306f  test    rdx, rdx
0x180003072  jz      loc_180003765
0x180003078  mov     rdi, [rdx+10h]
0x18000307c  test    rdi, rdi
0x18000307f  jz      loc_180003765
0x180003085  test    r8, r8
0x180003088  jz      loc_180003765
0x18000308e  mov     [r11-28h], r13
0x180003092  mov     r13d, [rdi+20h]
0x180003096  mov     [r11-30h], r14
0x18000309a  mov     [r11-38h], r15
0x18000309e  cmp     r13d, 0FFFFh
0x1800030a5  ja      loc_1800032D7
0x1800030ab  mov     r14, [rdx+20h]
0x1800030af  mov     [rsp+98h+P], r14
0x1800030b4  test    r14, r14
0x1800030b7  jz      loc_1800032D7
0x1800030bd  mov     [r11+10h], rbp
0x1800030c1  mov     ebp, [rdi+28h]
0x1800030c4  mov     [r11-18h], rsi
0x1800030c8  mov     ecx, ebp
0x1800030ca  shl     rcx, 4
0x1800030ce  mov     [r11-20h], r12
0x1800030d2  xor     r12d, r12d
0x1800030d5  cmp     [rcx+rax+1Ch], r12d
0x1800030da  lea     rsi, [rcx+rax]
0x1800030de  jnz     short loc_180003147
0x1800030e0  mov     r9d, [rax+0Ch]
0x1800030e4  lea     rax, __ImageBase
0x1800030eb  mov     [r11-50h], r12
0x1800030ef  mov     [r11+20h], r12d
0x1800030f3  test    r9b, 1
0x1800030f7  jnz     loc_1800035F8
0x1800030fd  lea     r14, rva l_PagedCipherEntryCache[rax]
0x180003104  add     r14, rcx
0x180003107  cmp     ebp, cs:g_dwCipherInfoTotalCount
0x18000310d  jnb     short loc_180003123
0x18000310f  lfence
0x180003112  mov     rcx, rva g_pCipherInfo[rax+rbp*8]
0x18000311a  test    rcx, rcx
0x18000311d  jnz     loc_180003417
0x180003123  mov     rcx, cs:WPP_GLOBAL_Control
0x18000312a  lea     r15, WPP_GLOBAL_Control
0x180003131  cmp     rcx, r15
0x180003134  jz      short loc_180003140
0x180003136  test    byte ptr [rcx+1Ch], 1
0x18000313a  jnz     loc_18000365A
0x180003140  mov     r14, [rsp+98h+P]
0x180003145  jmp     short loc_180003155
0x180003147  lea     r15, WPP_GLOBAL_Control
0x18000314e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003155  mov     ebp, [rsi+18h]
0x180003158  test    ebp, ebp
0x18000315a  jz      loc_180003373
0x180003160  mov     rax, [rsi+10h]
0x180003164  mov     [rsp+98h+hAlgorithm], rax
0x180003169  test    rax, rax
0x18000316c  jz      loc_180003373
0x180003172  mov     rcx, gs:60h
0x18000317b  lea     eax, [rbp+70h]
0x18000317e  mov     r8d, eax; Size
0x180003181  xor     edx, edx; Flags
0x180003183  mov     [rsp+98h+pbOutput], eax
0x18000318a  mov     rcx, [rcx+30h]; HeapHandle
0x18000318e  call    cs:__imp_RtlAllocateHeap
0x180003194  mov     rsi, rax
0x180003197  test    rax, rax
0x18000319a  jz      loc_180003323
0x1800031a0  lea     r8d, [rbp+70h]; Size
0x1800031a4  xor     edx, edx; Val
0x1800031a6  mov     rcx, rax; void *
0x1800031a9  call    memset
0x1800031ae  mov     dword ptr [rsi+4], 73736C33h
0x1800031b5  lea     eax, [rbp+70h]
0x1800031b8  mov     [rsi], eax
0x1800031ba  mov     r8, r13; Size
0x1800031bd  mov     eax, [rbx+8]
0x1800031c0  xor     edx, edx; Flags
0x1800031c2  mov     [rsi+8], eax
0x1800031c5  mov     rbx, r13
0x1800031c8  mov     [rsi+10h], rdi
0x1800031cc  mov     dword ptr [rsi+6Ch], 5
0x1800031d3  mov     dword ptr [rsi+68h], 0Ch
0x1800031da  mov     rcx, gs:60h
0x1800031e3  mov     rcx, [rcx+30h]; HeapHandle
0x1800031e7  call    cs:__imp_RtlAllocateHeap
0x1800031ed  mov     [rsp+98h+P], rax
0x1800031f2  test    rax, rax
0x1800031f5  jnz     loc_180003690
0x1800031fb  mov     dword ptr [rsp+98h+hObject], 8009000Eh
0x180003206  mov     rcx, cs:WPP_GLOBAL_Control
0x18000320d  cmp     rcx, r15
0x180003210  jz      short loc_180003244
0x180003212  test    byte ptr [rcx+1Ch], 1
0x180003216  jz      short loc_180003244
0x180003218  mov     rcx, [rcx+10h]
0x18000321c  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003223  mov     [rsp+98h+var_68], 10BDh
0x18000322b  lea     r9, aStatus; "Status"
0x180003232  mov     qword ptr [rsp+98h+cbSecret], r8
0x180003237  mov     [rsp+98h+dwFlags], 8009000Eh
0x18000323f  call    WPP_SF_sDsd
0x180003244  mov     r15, [rsp+98h+P]
0x180003249  mov     ecx, [rsp+98h+pbOutput]
0x180003250  mov     rdx, rsi
0x180003253  mov     edi, dword ptr [rsp+98h+hObject]
0x18000325a  mov     eax, ecx
0x18000325c  test    ecx, ecx
0x18000325e  jz      short loc_18000326D
0x180003260  mov     byte ptr [rdx], 0
0x180003263  lea     rdx, [rdx+1]
0x180003267  sub     rax, 1
0x18000326b  jnz     short loc_180003260
0x18000326d  mov     rcx, rsi
0x180003270  call    MSCryptFree
0x180003275  test    r15, r15
0x180003278  jz      short loc_1800032A7
0x18000327a  mov     rax, r15
0x18000327d  test    r13d, r13d
0x180003280  jz      short loc_18000328F
0x180003282  mov     byte ptr [rax], 0
0x180003285  lea     rax, [rax+1]
0x180003289  sub     rbx, 1
0x18000328d  jnz     short loc_180003282
0x18000328f  mov     rcx, gs:60h
0x180003298  mov     r8, r15; P
0x18000329b  xor     edx, edx; Flags
0x18000329d  mov     rcx, [rcx+30h]; HeapHandle
0x1800032a1  call    cs:__imp_RtlFreeHeap
0x1800032a7  mov     r12, [rsp+98h+var_20]
0x1800032ac  mov     rbp, [rsp+98h+arg_8]
0x1800032b4  mov     rsi, [rsp+98h+var_18]
0x1800032bc  mov     r14, [rsp+98h+var_30]
0x1800032c1  mov     r15, [rsp+98h+var_38]
0x1800032c6  mov     r13, [rsp+98h+var_28]
0x1800032cb  mov     eax, edi
0x1800032cd  add     rsp, 88h
0x1800032d4  pop     rdi
0x1800032d5  pop     rbx
0x1800032d6  retn
0x1800032d7  mov     edi, 80090027h
0x1800032dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032e3  lea     r15, WPP_GLOBAL_Control
0x1800032ea  cmp     rcx, r15
0x1800032ed  jz      short loc_1800032BC
0x1800032ef  test    byte ptr [rcx+1Ch], 1
0x1800032f3  jz      short loc_1800032BC
0x1800032f5  mov     rcx, [rcx+10h]
0x1800032f9  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003300  mov     [rsp+98h+var_68], 108Dh
0x180003308  lea     r9, aStatus; "Status"
0x18000330f  mov     qword ptr [rsp+98h+cbSecret], r8
0x180003314  mov     [rsp+98h+dwFlags], 80090027h
0x18000331c  call    WPP_SF_sDsd
0x180003321  jmp     short loc_1800032BC
0x180003323  mov     edi, 8009000Eh
0x180003328  mov     rcx, cs:WPP_GLOBAL_Control
0x18000332f  cmp     rcx, r15
0x180003332  jz      loc_1800032A7
0x180003338  test    byte ptr [rcx+1Ch], 1
0x18000333c  jz      loc_1800032A7
0x180003342  mov     [rsp+98h+var_68], 10ACh
0x18000334a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003351  mov     qword ptr [rsp+98h+cbSecret], r8
0x180003356  mov     [rsp+98h+dwFlags], 8009000Eh
0x18000335e  mov     rcx, [rcx+10h]
0x180003362  lea     r9, aStatus; "Status"
0x180003369  call    WPP_SF_sDsd
0x18000336e  jmp     loc_1800032A7
0x180003373  mov     edi, 80090029h
0x180003378  cmp     rcx, r15
0x18000337b  jz      loc_1800032A7
0x180003381  test    byte ptr [rcx+1Ch], 1
0x180003385  jz      loc_1800032A7
0x18000338b  mov     [rsp+98h+var_68], 10A2h
0x180003393  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000339a  mov     qword ptr [rsp+98h+cbSecret], r8
0x18000339f  mov     [rsp+98h+dwFlags], 80090029h
0x1800033a7  jmp     short loc_18000335E
0x1800033a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033b0  cmp     rcx, r15
0x1800033b3  jz      short loc_1800033E3
0x1800033b5  test    byte ptr [rcx+1Ch], 1
0x1800033b9  jz      short loc_1800033E3
0x1800033bb  mov     rcx, [rcx+10h]
0x1800033bf  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800033c6  mov     [rsp+98h+var_68], 12A0h
0x1800033ce  lea     r9, aStatus; "Status"
0x1800033d5  mov     qword ptr [rsp+98h+cbSecret], rax
0x1800033da  mov     [rsp+98h+dwFlags], edx
0x1800033de  call    WPP_SF_sDsd
0x1800033e3  xor     edx, edx; dwFlags
0x1800033e5  mov     rcx, rbp; hAlgorithm
0x1800033e8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800033ee  mov     edx, dword ptr [rsp+98h+hObject]
0x1800033f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033fc  cmp     rcx, r15
0x1800033ff  jz      short loc_18000340B
0x180003401  test    byte ptr [rcx+1Ch], 1
0x180003405  jnz     loc_18000362D
0x18000340b  mov     edi, dword ptr [rsp+98h+hObject]
0x180003412  jmp     loc_1800032A7
0x180003417  cmp     [r14+0Ch], r12d
0x18000341b  jz      short loc_18000343C
0x18000341d  lea     r15, WPP_GLOBAL_Control
0x180003424  mov     rax, [r14]
0x180003427  mov     [rsi+10h], rax
0x18000342b  mov     eax, [r14+8]
0x18000342f  mov     r14, [rsp+98h+P]
0x180003434  mov     [rsi+18h], eax
0x180003437  jmp     loc_18000314E
0x18000343c  mov     rcx, [rcx]; pszAlgId
0x18000343f  lea     r8, [rsp+98h+pbOutput]
0x180003447  lea     rdx, [rsp+98h+hAlgorithm]
0x18000344c  call    GetAlgorithmHandle
0x180003451  mov     dword ptr [rsp+98h+hObject], eax
0x180003458  mov     edx, eax
0x18000345a  lea     r15, WPP_GLOBAL_Control
0x180003461  test    eax, eax
0x180003463  js      loc_18000357F
0x180003469  cmp     ebp, 5
0x18000346c  mov     rbp, [rsp+98h+hAlgorithm]
0x180003471  jnz     short loc_1800034E9
0x180003473  mov     r9d, 20h ; ' '; cbInput
0x180003479  mov     [rsp+98h+pcbResult], r12d
0x18000347e  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x180003485  mov     [rsp+98h+dwFlags], r12d; dwFlags
0x18000348a  lea     rdx, pszProperty; "ChainingMode"
0x180003491  mov     rcx, rbp; hObject
0x180003494  call    cs:__imp_BCryptSetProperty
0x18000349a  mov     dword ptr [rsp+98h+hObject], eax
0x1800034a1  mov     ecx, eax
0x1800034a3  test    eax, eax
0x1800034a5  js      loc_180003604
0x1800034ab  lea     rax, [rsp+98h+pcbResult]
0x1800034b0  mov     [rsp+98h+cbSecret], r12d; dwFlags
0x1800034b5  mov     r9d, 4; cbOutput
0x1800034bb  mov     qword ptr [rsp+98h+dwFlags], rax; pcbResult
0x1800034c0  lea     r8, [rsp+98h+pbOutput]; pbOutput
0x1800034c8  mov     rcx, rbp; hObject
0x1800034cb  lea     rdx, aObjectlength; "ObjectLength"
0x1800034d2  call    cs:__imp_BCryptGetProperty
0x1800034d8  mov     dword ptr [rsp+98h+hObject], eax
0x1800034df  mov     edx, eax
0x1800034e1  test    eax, eax
0x1800034e3  js      loc_1800033A9
0x1800034e9  xor     eax, eax
0x1800034eb  lock cmpxchg [r14], rbp
0x1800034f0  mov     [rsp+98h+hObject], rax
0x1800034f8  jnz     short loc_180003512
0x1800034fa  mov     eax, [rsp+98h+pbOutput]
0x180003501  mov     [r14+8], eax
0x180003505  mov     dword ptr [r14+0Ch], 1
0x18000350d  jmp     loc_180003424
0x180003512  xor     edx, edx; dwFlags
0x180003514  mov     [rsp+98h+pcbResult], r12d
0x180003519  mov     rcx, rbp; hAlgorithm
0x18000351c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180003522  mov     rcx, [rsp+98h+hObject]; hObject
0x18000352a  lea     rax, [rsp+98h+pcbResult]
0x18000352f  mov     [rsp+98h+cbSecret], r12d; dwFlags
0x180003534  lea     r8, [rsp+98h+pbOutput]; pbOutput
0x18000353c  mov     r9d, 4; cbOutput
0x180003542  mov     qword ptr [rsp+98h+dwFlags], rax; pcbResult
0x180003547  lea     rdx, aObjectlength; "ObjectLength"
0x18000354e  call    cs:__imp_BCryptGetProperty
0x180003554  mov     dword ptr [rsp+98h+hObject], eax
0x18000355b  mov     ecx, eax
0x18000355d  test    eax, eax
0x18000355f  jns     short loc_1800034FA
0x180003561  mov     r9d, 12BAh
0x180003567  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000356e  lea     rdx, aStatus; "Status"
0x180003575  call    DebugTraceError
0x18000357a  jmp     loc_1800033EE
0x18000357f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003586  cmp     rcx, r15
0x180003589  jz      loc_18000340B
0x18000358f  test    byte ptr [rcx+1Ch], 1
0x180003593  jz      loc_1800033FC
0x180003599  mov     rcx, [rcx+10h]
0x18000359d  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800035a4  mov     [rsp+98h+var_68], 1283h
0x1800035ac  lea     r9, aStatus; "Status"
0x1800035b3  mov     qword ptr [rsp+98h+cbSecret], rax
0x1800035b8  mov     [rsp+98h+dwFlags], edx
0x1800035bc  call    WPP_SF_sDsd
0x1800035c1  jmp     loc_1800033EE
0x1800035c6  mov     r9d, 10E7h
0x1800035cc  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800035d3  lea     rdx, aStatus; "Status"
  ... truncated ...
```
