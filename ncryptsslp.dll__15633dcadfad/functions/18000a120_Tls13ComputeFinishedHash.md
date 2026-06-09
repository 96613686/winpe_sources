# Tls13ComputeFinishedHash

- ea: `0x18000a120`
- end: `0x18000a954`
- name: `Tls13ComputeFinishedHash`
- size: `2100`
- prototype: `__int64 __fastcall(__int64, __int64, void *, ULONG, UCHAR *pbOutput, ULONG)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800091e0`

## callees

- `0x180001acc`
- `0x18000a120`
- `0x18000b594`
- `0x18000b654`
- `0x1800183d0`
- `0x180020cb4`
- `0x180024fb0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000a67c`
- `bcrypt!BCryptHashData` at `0x18000a67c`
- `bcrypt!BCryptKeyDerivation` at `0x18000a367`
- `bcrypt!BCryptKeyDerivation` at `0x18000a367`
- `bcrypt!BCryptCreateHash` at `0x18000a65d`
- `bcrypt!BCryptCreateHash` at `0x18000a65d`
- `bcrypt!BCryptFinishHash` at `0x18000a584`
- `bcrypt!BCryptFinishHash` at `0x18000a6a5`
- `bcrypt!BCryptFinishHash` at `0x18000a584`
- `bcrypt!BCryptFinishHash` at `0x18000a6a5`
- `bcrypt!BCryptDestroyHash` at `0x18000a4dc`
- `bcrypt!BCryptDestroyHash` at `0x18000a4dc`
- `ntdll!RtlFreeHeap` at `0x18000a4af`
- `ntdll!RtlFreeHeap` at `0x18000a4cc`
- `ntdll!RtlFreeHeap` at `0x18000a4f9`
- `ntdll!RtlFreeHeap` at `0x18000a540`
- `ntdll!RtlFreeHeap` at `0x18000a4af`
- `ntdll!RtlFreeHeap` at `0x18000a4cc`
- `ntdll!RtlFreeHeap` at `0x18000a4f9`
- `ntdll!RtlFreeHeap` at `0x18000a540`
- `ntdll!RtlAllocateHeap` at `0x18000a22a`
- `ntdll!RtlAllocateHeap` at `0x18000a2de`
- `ntdll!RtlAllocateHeap` at `0x18000a561`
- `ntdll!RtlAllocateHeap` at `0x18000a61b`
- `ntdll!RtlAllocateHeap` at `0x18000a22a`
- `ntdll!RtlAllocateHeap` at `0x18000a2de`
- `ntdll!RtlAllocateHeap` at `0x18000a561`
- `ntdll!RtlAllocateHeap` at `0x18000a61b`

## string_xrefs

- `0x18000a36d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000a405`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000a7ef`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000a843`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000a8a4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000a8d4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000a92c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls13ComputeFinishedHash(__int64 a1, __int64 a2, void *a3, ULONG a4, UCHAR *pbOutput, ULONG a6)
{
  PUCHAR v6; // rbx
  SIZE_T v7; // r13
  __int64 v9; // rsi
  wchar_t *v10; // rsi
  unsigned int v11; // r14d
  const wchar_t **v12; // rax
  __int64 *v13; // rdi
  SIZE_T v14; // rsi
  size_t v15; // rdx
  __int64 v16; // r15
  int v17; // edx
  int v18; // r8d
  unsigned __int8 v19; // r14
  SIZE_T v20; // rbp
  _BYTE *Heap; // rax
  int v22; // edx
  int v23; // r8d
  _BYTE *v24; // r13
  PVOID v25; // r8
  NTSTATUS v26; // eax
  int v27; // edx
  int v28; // r8d
  NTSTATUS HashEntry; // r14d
  UCHAR *v30; // rbp
  PVOID v31; // rdx
  _BYTE *j; // rax
  _BYTE *v34; // rax
  UCHAR *v35; // rax
  NTSTATUS v36; // eax
  const wchar_t *v37; // rdx
  int v38; // r8d
  wchar_t *v39; // rcx
  __int64 i; // rbx
  const wchar_t **v41; // rax
  __int64 v42; // rdi
  ULONG v43; // ebx
  int v44; // edx
  int v45; // r8d
  ULONG v46; // r9d
  int v47; // edx
  int v48; // r8d
  int v49; // edx
  int v50; // r8d
  int v51; // edx
  int v52; // r8d
  int v53; // edx
  int v54; // r8d
  __int64 v55; // r9
  __int64 v56; // rcx
  int v57; // [rsp+40h] [rbp-88h] BYREF
  char v58; // [rsp+46h] [rbp-82h]
  PUCHAR pbHashObject; // [rsp+48h] [rbp-80h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+50h] [rbp-78h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-70h]
  PVOID P; // [rsp+60h] [rbp-68h]
  _DWORD v63[2]; // [rsp+68h] [rbp-60h] BYREF
  _BYTE *v64; // [rsp+70h] [rbp-58h]
  _DWORD v65[2]; // [rsp+78h] [rbp-50h] BYREF
  _DWORD *v66; // [rsp+80h] [rbp-48h]

  v6 = 0;
  v7 = a4;
  pbHashObject = 0;
  hHash = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v9 = *(_QWORD *)(a2 + 16);
      if ( v9 )
      {
        if ( a3 && pbOutput && a6 == a4 )
        {
          v10 = *(wchar_t **)(v9 + 136);
          v11 = 0;
          String1 = 0;
          if ( !v10 || !*v10 )
            v10 = L"SHA256";
          while ( 1 )
          {
            if ( (unsigned int)v6 >= g_dwHashInfoTotalCount )
              goto LABEL_15;
            v12 = (const wchar_t **)g_pHashInfo[(_QWORD)v6];
            v13 = &g_pHashInfo[(_QWORD)v6];
            if ( v12 )
            {
              if ( *v12 && !wcsnicmp(v10, *v12, 0x40u) )
                break;
            }
            v6 = (PUCHAR)(unsigned int)((_DWORD)v6 + 1);
          }
          _mm_lfence();
          if ( *v13 )
          {
            v11 = *(_DWORD *)(*v13 + 8);
            if ( v11 > 0xFF )
              goto LABEL_90;
            String1 = v10;
          }
LABEL_15:
          if ( v11 == (_DWORD)v7 )
          {
            v14 = v7;
            P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
            if ( !P )
            {
              HashEntry = -1073741801;
              DebugTraceError(
                3221225495LL,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                4619);
              v6 = pbHashObject;
              goto LABEL_39;
            }
            v16 = *(_QWORD *)(a2 + 32);
            v58 = aTls13[6];
            v63[1] = 20;
            v63[0] = 0;
            v19 = strnlen_s("finished", v15);
            v64 = 0;
            v66 = v63;
            v65[0] = 0;
            v65[1] = 1;
            v57 = 0;
            if ( v16 && v19 != 0xF9 && (_WORD)v7 )
            {
              v20 = (unsigned __int16)((unsigned __int8)(v19 + 6) + 4);
              Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
              v24 = Heap;
              if ( Heap )
              {
                Heap[2] = v19 + 6;
                Heap[1] = a4;
                *Heap = BYTE1(a4);
                qmemcpy(Heap + 3, "tls13 ", 6);
                memmove(Heap + 9, "finished", v19);
                v25 = P;
                v24[v19 + 9] = 0;
                v63[0] = v20;
                v64 = v24;
                v26 = BCryptKeyDerivation(v16, v65, v25, (unsigned __int16)a4, &v57, 0);
                HashEntry = v26;
                if ( (v26 || v57 != (unsigned __int16)a4)
                  && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v27,
                    v28,
                    (unsigned int)"Status",
                    v26,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                    195);
                }
                v34 = v24;
                do
                {
                  *v34++ = 0;
                  --v20;
                }
                while ( v20 );
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
                if ( HashEntry >= 0 )
                {
                  v35 = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
                  v30 = v35;
                  if ( v35 )
                  {
                    v36 = BCryptFinishHash(a3, v35, a4, 0);
                    HashEntry = v36;
                    if ( v36 >= 0 )
                    {
                      v39 = String1;
                      if ( String1 )
                      {
                        for ( i = 0; (unsigned int)i < g_dwHashInfoTotalCount; i = (unsigned int)(i + 1) )
                        {
                          v41 = (const wchar_t **)g_pHashInfo[i];
                          if ( v41 )
                          {
                            v37 = *v41;
                            if ( *v41 )
                            {
                              if ( !wcsnicmp(v39, v37, 0x40u) )
                              {
                                v42 = a1 + 32LL * (unsigned int)i;
                                if ( !*(_DWORD *)(v42 + 300) )
                                {
                                  HashEntry = I_GetHashEntry((unsigned int)i, *(unsigned int *)(a1 + 12), v42 + 272);
                                  if ( HashEntry < 0 )
                                  {
                                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                    {
                                      WPP_SF_sDsd(
                                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                                        v53,
                                        v54,
                                        (unsigned int)"Status",
                                        HashEntry,
                                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                                        69);
                                    }
                                    goto LABEL_34;
                                  }
                                }
                                v43 = *(_DWORD *)(v42 + 292);
                                pbHashObject = (PUCHAR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v43);
                                if ( pbHashObject )
                                {
                                  v46 = v43;
                                  v6 = pbHashObject;
                                  HashEntry = BCryptCreateHash(
                                                *(BCRYPT_ALG_HANDLE *)(v42 + 280),
                                                &hHash,
                                                pbHashObject,
                                                v46,
                                                (PUCHAR)P,
                                                a4,
                                                0);
                                  if ( HashEntry < 0 )
                                  {
                                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                    {
                                      WPP_SF_sDsd(
                                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                                        v47,
                                        v48,
                                        (unsigned int)"Status",
                                        HashEntry,
                                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                                        96);
                                    }
                                  }
                                  else
                                  {
                                    HashEntry = BCryptHashData(hHash, v30, a4, 0);
                                    if ( HashEntry < 0 )
                                    {
                                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                      {
                                        WPP_SF_sDsd(
                                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                                          v49,
                                          v50,
                                          (unsigned int)"Status",
                                          HashEntry,
                                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                                          107);
                                      }
                                    }
                                    else
                                    {
                                      HashEntry = BCryptFinishHash(hHash, pbOutput, a6, 0);
                                      if ( HashEntry < 0
                                        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                      {
                                        WPP_SF_sDsd(
                                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                                          v51,
                                          v52,
                                          (unsigned int)"Status",
                                          HashEntry,
                                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                                          117);
                                      }
                                    }
                                  }
                                  goto LABEL_35;
                                }
                                HashEntry = -2146893810;
                                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                                {
                                  WPP_SF_sDsd(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    v44,
                                    v45,
                                    (unsigned int)"Status",
                                    14,
                                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                                    83);
                                }
                                goto LABEL_34;
                              }
                              v39 = String1;
                            }
                          }
                        }
                      }
                      HashEntry = -2146893783;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          (_DWORD)v37,
                          v38,
                          (unsigned int)"Status",
                          41,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                          60);
                      }
                      goto LABEL_34;
                    }
                    v55 = 4657;
                    v56 = (unsigned int)v36;
                  }
                  else
                  {
                    HashEntry = -1073741801;
                    v55 = 4647;
                    v56 = 3221225495LL;
                  }
                  DebugTraceError(v56, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v55);
LABEL_34:
                  v6 = pbHashObject;
                  goto LABEL_35;
                }
              }
              else
              {
                HashEntry = -1073741801;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v22,
                    v23,
                    (unsigned int)"Status",
                    23,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                    169);
                }
              }
            }
            else
            {
              HashEntry = -1073741811;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v17,
                  v18,
                  (unsigned int)"Status",
                  13,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                  150);
              }
            }
            v30 = 0;
            DebugTraceError(
              (unsigned int)HashEntry,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              4631);
            v6 = 0;
LABEL_35:
            v31 = P;
            for ( j = P; v14; --v14 )
              *j++ = 0;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v31);
            if ( v30 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
            goto LABEL_39;
          }
LABEL_90:
          HashEntry = -2146893785;
          DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4579);
          v6 = pbHashObject;
          goto LABEL_39;
        }
      }
    }
  }
  HashEntry = -2146893785;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)HashEntry;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    a2,
    (_DWORD)a3,
    (unsigned int)"Status",
    39,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
    214);
LABEL_39:
  if ( hHash )
    BCryptDestroyHash(hHash);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return (unsigned int)HashEntry;
}

```

## disassembly

```asm
0x18000a120  mov     [rsp+cbOutput], r9d
0x18000a125  mov     [rsp+arg_10], r8
0x18000a12a  mov     [rsp+arg_0], rcx
0x18000a12f  push    rbx
0x18000a130  push    rbp
0x18000a131  push    rsi
0x18000a132  push    rdi
0x18000a133  push    r13
0x18000a135  push    r14
0x18000a137  push    r15
0x18000a139  sub     rsp, 90h
0x18000a140  xor     ebx, ebx
0x18000a142  mov     r13d, r9d
0x18000a145  mov     [rsp+0C8h+pbHashObject], rbx
0x18000a14a  mov     rax, r8
0x18000a14d  mov     [rsp+0C8h+hHash], rbx
0x18000a152  mov     rbp, rdx
0x18000a155  test    rcx, rcx
0x18000a158  jz      loc_18000A818
0x18000a15e  test    rdx, rdx
0x18000a161  jz      loc_18000A818
0x18000a167  mov     rsi, [rdx+10h]
0x18000a16b  test    rsi, rsi
0x18000a16e  jz      loc_18000A818
0x18000a174  test    rax, rax
0x18000a177  jz      loc_18000A818
0x18000a17d  cmp     [rsp+0C8h+pbOutput], rbx
0x18000a185  jz      loc_18000A818
0x18000a18b  cmp     [rsp+0C8h+arg_28], r13d
0x18000a193  jnz     loc_18000A818
0x18000a199  mov     rsi, [rsi+88h]
0x18000a1a0  xor     eax, eax
0x18000a1a2  xor     r14d, r14d
0x18000a1a5  mov     [rsp+0C8h+String1], rax
0x18000a1aa  test    rsi, rsi
0x18000a1ad  jz      loc_18000A76A
0x18000a1b3  cmp     [rsi], ax
0x18000a1b6  jz      loc_18000A76A
0x18000a1bc  lea     rcx, g_pHashInfo
0x18000a1c3  cmp     ebx, cs:g_dwHashInfoTotalCount
0x18000a1c9  jnb     short loc_18000A20C
0x18000a1cb  mov     rax, [rcx+rbx*8]
0x18000a1cf  lea     rdi, [rcx+rbx*8]
0x18000a1d3  test    rax, rax
0x18000a1d6  jz      short loc_18000A1F9
0x18000a1d8  mov     rdx, [rax]; String2
0x18000a1db  test    rdx, rdx
0x18000a1de  jz      short loc_18000A1F9
0x18000a1e0  mov     r8d, 40h ; '@'; MaxCount
0x18000a1e6  mov     rcx, rsi; String1
0x18000a1e9  call    _wcsnicmp
0x18000a1ee  test    eax, eax
0x18000a1f0  jz      short loc_18000A1FD
0x18000a1f2  lea     rcx, g_pHashInfo
0x18000a1f9  inc     ebx
0x18000a1fb  jmp     short loc_18000A1C3
0x18000a1fd  lfence
0x18000a200  mov     rax, [rdi]
0x18000a203  test    rax, rax
0x18000a206  jnz     loc_18000A3C7
0x18000a20c  cmp     r14d, r13d
0x18000a20f  jnz     loc_18000A926
0x18000a215  mov     rcx, gs:60h
0x18000a21e  mov     r8, r13; Size
0x18000a221  xor     edx, edx; Flags
0x18000a223  mov     rsi, r13
0x18000a226  mov     rcx, [rcx+30h]; HeapHandle
0x18000a22a  call    cs:__imp_RtlAllocateHeap
0x18000a230  mov     [rsp+0C8h+P], rax
0x18000a235  test    rax, rax
0x18000a238  jz      loc_18000A89E
0x18000a23e  movzx   eax, byte ptr cs:aTls13+6; ""
0x18000a245  lea     rcx, aFinished; "finished"
0x18000a24c  mov     r15, [rbp+20h]
0x18000a250  mov     edi, dword ptr cs:aTls13; "tls13 "
0x18000a256  mov     [rsp+0C8h+arg_8], r12
0x18000a25e  movzx   r12d, word ptr cs:aTls13+4; "3 "
0x18000a266  mov     [rsp+0C8h+var_82], al
0x18000a26a  call    strnlen_s
0x18000a26f  xor     ecx, ecx
0x18000a271  mov     [rsp+0C8h+var_5C], 14h
0x18000a279  mov     [rsp+0C8h+var_60], ecx
0x18000a27d  mov     r14, rax
0x18000a280  mov     [rsp+0C8h+var_58], rcx
0x18000a285  lea     rax, [rsp+0C8h+var_60]
0x18000a28a  mov     [rsp+0C8h+var_48], rax
0x18000a292  mov     [rsp+0C8h+var_50], ecx
0x18000a296  mov     [rsp+0C8h+var_4C], 1
0x18000a29e  mov     [rsp+0C8h+var_88], ecx
0x18000a2a2  test    r15, r15
0x18000a2a5  jz      loc_18000A7C0
0x18000a2ab  lea     ebx, [r14+6]
0x18000a2af  cmp     bl, 0FFh
0x18000a2b2  jnb     loc_18000A7C0
0x18000a2b8  test    r13w, r13w
0x18000a2bc  jz      loc_18000A7C0
0x18000a2c2  mov     rcx, gs:60h
0x18000a2cb  xor     edx, edx; Flags
0x18000a2cd  movzx   eax, bl
0x18000a2d0  add     ax, 4
0x18000a2d4  movzx   ebp, ax
0x18000a2d7  mov     rcx, [rcx+30h]; HeapHandle
0x18000a2db  mov     r8d, ebp; Size
0x18000a2de  call    cs:__imp_RtlAllocateHeap
0x18000a2e4  mov     r13, rax
0x18000a2e7  test    rax, rax
0x18000a2ea  jz      loc_18000A3E2
0x18000a2f0  mov     ecx, [rsp+0C8h+cbOutput]
0x18000a2f7  lea     rdx, aFinished; "finished"
0x18000a2fe  mov     [r13+2], bl
0x18000a302  movzx   eax, cx
0x18000a305  mov     [r13+1], cl
0x18000a309  lea     rcx, [r13+9]; void *
0x18000a30d  shr     ax, 8
0x18000a311  mov     [r13+0], al
0x18000a315  mov     [r13+3], edi
0x18000a319  movzx   ebx, r14b
0x18000a31d  mov     r8d, ebx; Size
0x18000a320  mov     [r13+7], r12w
0x18000a325  call    memmove
0x18000a32a  mov     r12d, [rsp+0C8h+cbOutput]
0x18000a332  lea     rax, [rsp+0C8h+var_88]
0x18000a337  mov     r8, [rsp+0C8h+P]
0x18000a33c  lea     rdx, [rsp+0C8h+var_50]
0x18000a341  mov     byte ptr [rbx+r13+9], 0
0x18000a347  mov     rcx, r15
0x18000a34a  movzx   ebx, r12w
0x18000a34e  mov     r9d, ebx
0x18000a351  mov     [rsp+0C8h+cbSecret], 0
0x18000a359  mov     [rsp+0C8h+var_60], ebp
0x18000a35d  mov     [rsp+0C8h+var_58], r13
0x18000a362  mov     [rsp+0C8h+pbSecret], rax
0x18000a367  call    cs:__imp_BCryptKeyDerivation
0x18000a36d  lea     r15, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a374  mov     r14d, eax
0x18000a377  lea     rdi, WPP_GLOBAL_Control
0x18000a37e  test    eax, eax
0x18000a380  jz      loc_18000A514
0x18000a386  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a38d  cmp     rcx, rdi
0x18000a390  jz      loc_18000A51E
0x18000a396  test    byte ptr [rcx+1Ch], 1
0x18000a39a  jz      loc_18000A51E
0x18000a3a0  mov     rcx, [rcx+10h]
0x18000a3a4  lea     r9, aStatus; "Status"
0x18000a3ab  mov     [rsp+0C8h+dwFlags], 0FC3h
0x18000a3b3  mov     qword ptr [rsp+0C8h+cbSecret], r15
0x18000a3b8  mov     dword ptr [rsp+0C8h+pbSecret], r14d
0x18000a3bd  call    WPP_SF_sDsd
0x18000a3c2  jmp     loc_18000A51E
0x18000a3c7  mov     r14d, [rax+8]
0x18000a3cb  cmp     r14d, 0FFh
0x18000a3d2  ja      loc_18000A926
0x18000a3d8  mov     [rsp+0C8h+String1], rsi
0x18000a3dd  jmp     loc_18000A20C
0x18000a3e2  mov     r14d, 0C0000017h
0x18000a3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3ef  lea     rax, WPP_GLOBAL_Control
0x18000a3f6  cmp     rcx, rax
0x18000a3f9  jz      short loc_18000A405
0x18000a3fb  test    byte ptr [rcx+1Ch], 1
0x18000a3ff  jnz     loc_18000A8CC
0x18000a405  lea     r15, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a40c  xor     ebp, ebp
0x18000a40e  lea     rdx, aStatus; "Status"
0x18000a415  mov     r9d, 1217h
0x18000a41b  mov     r8, r15
0x18000a41e  mov     ecx, r14d
0x18000a421  call    DebugTraceError
0x18000a426  mov     ebx, ebp
0x18000a428  jmp     short loc_18000A470
0x18000a42a  lea     rdi, WPP_GLOBAL_Control
0x18000a431  mov     r14d, 80090029h
0x18000a437  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a43e  cmp     rcx, rdi
0x18000a441  jz      short loc_18000A46B
0x18000a443  test    byte ptr [rcx+1Ch], 1
0x18000a447  jz      short loc_18000A46B
0x18000a449  mov     [rsp+0C8h+dwFlags], 123Ch
0x18000a451  mov     qword ptr [rsp+0C8h+cbSecret], r15
0x18000a456  mov     dword ptr [rsp+0C8h+pbSecret], r14d
0x18000a45b  mov     rcx, [rcx+10h]
0x18000a45f  lea     r9, aStatus; "Status"
0x18000a466  call    WPP_SF_sDsd
0x18000a46b  mov     rbx, [rsp+0C8h+pbHashObject]
0x18000a470  mov     rdx, [rsp+0C8h+P]
0x18000a475  mov     r12, [rsp+0C8h+arg_8]
0x18000a47d  mov     rax, rdx
0x18000a480  test    rsi, rsi
0x18000a483  jz      short loc_18000A49D
0x18000a485  nop     word ptr [rax+rax+00000000h]
0x18000a490  mov     byte ptr [rax], 0
0x18000a493  lea     rax, [rax+1]
0x18000a497  sub     rsi, 1
0x18000a49b  jnz     short loc_18000A490
0x18000a49d  mov     rcx, gs:60h
0x18000a4a6  mov     r8, rdx; P
0x18000a4a9  xor     edx, edx; Flags
0x18000a4ab  mov     rcx, [rcx+30h]; HeapHandle
0x18000a4af  call    cs:__imp_RtlFreeHeap
0x18000a4b5  test    rbp, rbp
0x18000a4b8  jz      short loc_18000A4D2
0x18000a4ba  mov     rcx, gs:60h
0x18000a4c3  mov     r8, rbp; P
0x18000a4c6  xor     edx, edx; Flags
0x18000a4c8  mov     rcx, [rcx+30h]; HeapHandle
0x18000a4cc  call    cs:__imp_RtlFreeHeap
0x18000a4d2  mov     rcx, [rsp+0C8h+hHash]; hHash
0x18000a4d7  test    rcx, rcx
0x18000a4da  jz      short loc_18000A4E2
0x18000a4dc  call    cs:__imp_BCryptDestroyHash
0x18000a4e2  test    rbx, rbx
0x18000a4e5  jz      short loc_18000A4FF
0x18000a4e7  mov     rcx, gs:60h
0x18000a4f0  mov     r8, rbx; P
0x18000a4f3  xor     edx, edx; Flags
0x18000a4f5  mov     rcx, [rcx+30h]; HeapHandle
0x18000a4f9  call    cs:__imp_RtlFreeHeap
0x18000a4ff  mov     eax, r14d
0x18000a502  add     rsp, 90h
0x18000a509  pop     r15
0x18000a50b  pop     r14
0x18000a50d  pop     r13
0x18000a50f  pop     rdi
0x18000a510  pop     rsi
0x18000a511  pop     rbp
0x18000a512  pop     rbx
0x18000a513  retn
0x18000a514  cmp     [rsp+0C8h+var_88], ebx
0x18000a518  jnz     loc_18000A386
0x18000a51e  mov     rax, r13
0x18000a521  mov     byte ptr [rax], 0
0x18000a524  lea     rax, [rax+1]
0x18000a528  sub     rbp, 1
0x18000a52c  jnz     short loc_18000A521
0x18000a52e  mov     rcx, gs:60h
0x18000a537  mov     r8, r13; P
0x18000a53a  xor     edx, edx; Flags
0x18000a53c  mov     rcx, [rcx+30h]; HeapHandle
0x18000a540  call    cs:__imp_RtlFreeHeap
0x18000a546  test    r14d, r14d
0x18000a549  js      loc_18000A40C
0x18000a54f  mov     rcx, gs:60h
0x18000a558  mov     r8, rsi; Size
0x18000a55b  xor     edx, edx; Flags
0x18000a55d  mov     rcx, [rcx+30h]; HeapHandle
0x18000a561  call    cs:__imp_RtlAllocateHeap
0x18000a567  mov     rbp, rax
0x18000a56a  test    rax, rax
0x18000a56d  jz      loc_18000A8ED
0x18000a573  mov     rcx, [rsp+0C8h+arg_10]; hHash
0x18000a57b  xor     r9d, r9d; dwFlags
0x18000a57e  mov     r8d, r12d; cbOutput
0x18000a581  mov     rdx, rax; pbOutput
0x18000a584  call    cs:__imp_BCryptFinishHash
0x18000a58a  mov     r14d, eax
0x18000a58d  test    eax, eax
0x18000a58f  js      loc_18000A90A
0x18000a595  mov     rcx, [rsp+0C8h+String1]; String1
0x18000a59a  test    rcx, rcx
0x18000a59d  jz      loc_18000A431
0x18000a5a3  xor     ebx, ebx
0x18000a5a5  lea     r14, g_pHashInfo
0x18000a5ac  nop     dword ptr [rax+00h]
0x18000a5b0  cmp     ebx, cs:g_dwHashInfoTotalCount
0x18000a5b6  jnb     loc_18000A42A
0x18000a5bc  mov     rax, [r14+rbx*8]
0x18000a5c0  mov     edi, ebx
0x18000a5c2  test    rax, rax
0x18000a5c5  jz      short loc_18000A5E3
0x18000a5c7  mov     rdx, [rax]; String2
0x18000a5ca  test    rdx, rdx
0x18000a5cd  jz      short loc_18000A5E3
0x18000a5cf  mov     r8d, 40h ; '@'; MaxCount
0x18000a5d5  call    _wcsnicmp
0x18000a5da  test    eax, eax
0x18000a5dc  jz      short loc_18000A5E7
0x18000a5de  mov     rcx, [rsp+0C8h+String1]
0x18000a5e3  inc     ebx
0x18000a5e5  jmp     short loc_18000A5B0
0x18000a5e7  mov     rdx, [rsp+0C8h+arg_0]
0x18000a5ef  shl     rdi, 5
0x18000a5f3  add     rdi, rdx
0x18000a5f6  cmp     dword ptr [rdi+12Ch], 0
0x18000a5fd  jz      loc_18000A776
0x18000a603  mov     rcx, gs:60h
0x18000a60c  xor     edx, edx; Flags
0x18000a60e  mov     ebx, [rdi+124h]
0x18000a614  mov     r8d, ebx; Size
0x18000a617  mov     rcx, [rcx+30h]; HeapHandle
0x18000a61b  call    cs:__imp_RtlAllocateHeap
0x18000a621  mov     [rsp+0C8h+pbHashObject], rax
0x18000a626  test    rax, rax
0x18000a629  jz      loc_18000A6E1
0x18000a62f  mov     rax, [rsp+0C8h+P]
0x18000a634  lea     rdx, [rsp+0C8h+hHash]; phHash
0x18000a639  mov     rcx, [rdi+118h]; hAlgorithm
0x18000a640  mov     r9d, ebx; cbHashObject
0x18000a643  mov     rbx, [rsp+0C8h+pbHashObject]
0x18000a648  mov     [rsp+0C8h+dwFlags], 0; dwFlags
  ... truncated ...
```
