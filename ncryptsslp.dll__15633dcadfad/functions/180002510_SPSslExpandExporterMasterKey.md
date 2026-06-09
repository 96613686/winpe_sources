# SPSslExpandExporterMasterKey

- ea: `0x180002510`
- end: `0x1800029d0`
- name: `SPSslExpandExporterMasterKey`
- size: `1216`
- prototype: `__int64 __fastcall(_DWORD *, __int64, BCRYPT_HASH_HANDLE *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002510`
- `0x1800037a0`
- `0x18000b594`
- `0x18000b654`
- `0x1800183d0`

## import_xrefs

- `bcrypt!BCryptDuplicateHash` at `0x180002686`
- `bcrypt!BCryptDuplicateHash` at `0x180002686`
- `bcrypt!BCryptFinishHash` at `0x1800026cb`
- `bcrypt!BCryptFinishHash` at `0x1800026cb`
- `bcrypt!BCryptDestroyHash` at `0x180002719`
- `bcrypt!BCryptDestroyHash` at `0x180002719`
- `ntdll!RtlFreeHeap` at `0x18000274f`
- `ntdll!RtlFreeHeap` at `0x180002782`
- `ntdll!RtlFreeHeap` at `0x18000274f`
- `ntdll!RtlFreeHeap` at `0x180002782`
- `ntdll!RtlAllocateHeap` at `0x18000265a`
- `ntdll!RtlAllocateHeap` at `0x1800026a8`
- `ntdll!RtlAllocateHeap` at `0x18000265a`
- `ntdll!RtlAllocateHeap` at `0x1800026a8`

## string_xrefs

- `0x1800025d5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800027b7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000280a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180002865`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800028df`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800029bf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExpandExporterMasterKey(_DWORD *a1, __int64 a2, BCRYPT_HASH_HANDLE *a3, __int64 a4)
{
  BCRYPT_HASH_HANDLE *v5; // rsi
  __int64 v6; // rdi
  ULONG v7; // ebp
  UCHAR *v8; // r14
  UCHAR *v9; // r13
  ULONG v10; // r15d
  __int64 v11; // rax
  NTSTATUS v12; // esi
  const char *v13; // rbx
  UCHAR *Heap; // rax
  int v15; // edx
  int v16; // r8d
  int v17; // edx
  int v18; // r8d
  UCHAR *v19; // rax
  NTSTATUS v20; // eax
  __int64 v21; // rcx
  UCHAR *v22; // rax
  __int64 v23; // rcx
  UCHAR *v24; // rax
  _QWORD *v26; // rcx
  const wchar_t *v27; // rbp
  __int64 i; // rbx
  __int64 *v29; // rax
  __int64 *v30; // r14
  __int64 v31; // r9
  __int64 v32; // rcx
  char v33; // [rsp+30h] [rbp-48h]
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+90h] [rbp+18h] BYREF

  v5 = a3;
  v6 = a2;
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
    a1 = 0;
  if ( !a2 || *(_DWORD *)a2 < 0x70u || *(_DWORD *)(a2 + 4) != 1936944179 )
    v6 = 0;
  if ( !a3 || *(_DWORD *)a3 < 0x30u || *((_DWORD *)a3 + 1) != 1936944178 )
    v5 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  phNewHash = 0;
  if ( a1 )
  {
    if ( v6 )
    {
      v11 = *(_QWORD *)(v6 + 16);
      if ( v11 )
      {
        if ( v5 )
        {
          v27 = *(const wchar_t **)(v11 + 136);
          if ( !v27 || !*v27 )
            v27 = L"SHA256";
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)i >= g_dwHashInfoTotalCount )
              goto LABEL_20;
            v29 = (__int64 *)g_pHashInfo[i];
            v30 = &g_pHashInfo[i];
            if ( v29 )
            {
              a2 = *v29;
              if ( *v29 )
              {
                if ( !wcsnicmp(v27, (const wchar_t *)a2, 0x40u) )
                  break;
              }
            }
          }
          _mm_lfence();
          if ( *v30 )
          {
            v7 = *(_DWORD *)(*v30 + 8);
            if ( v7 > 0xFF )
              goto LABEL_58;
          }
          else
          {
LABEL_20:
            v7 = 0;
          }
          if ( v7 == *((_DWORD *)v5 + 7) && a4 )
          {
            if ( *(_DWORD *)(v6 + 8) == 772 )
            {
              if ( *(_DWORD *)(v6 + 108) == 1 )
              {
                v13 = "e exp master";
LABEL_27:
                v10 = *((_DWORD *)v5 + 6);
                Heap = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
                v9 = Heap;
                if ( Heap )
                {
                  v12 = BCryptDuplicateHash(v5[2], &phNewHash, Heap, v10, 0);
                  if ( v12 >= 0 )
                  {
                    v19 = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
                    v8 = v19;
                    if ( v19 )
                    {
                      v20 = BCryptFinishHash(phNewHash, v19, v7, 0);
                      v12 = v20;
                      if ( v20 < 0 )
                      {
                        v31 = 6463;
                      }
                      else
                      {
                        v20 = TlsDeriveSecret(v6, v13, v8, (unsigned __int8)v7, 6, a4);
                        v12 = v20;
                        if ( v20 >= 0 )
                          goto LABEL_32;
                        v31 = 6480;
                      }
                      v32 = (unsigned int)v20;
                    }
                    else
                    {
                      v12 = -1073741801;
                      v31 = 6453;
                      v32 = 3221225495LL;
                    }
                    DebugTraceError(
                      v32,
                      "Status",
                      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                      v31);
                    goto LABEL_32;
                  }
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v17,
                      v18,
                      (unsigned int)"Status",
                      v12,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                      46);
                  }
                }
                else
                {
                  v12 = -1073741801;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v15,
                      v16,
                      (unsigned int)"Status",
                      23,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
                      35);
                    v8 = 0;
                    goto LABEL_32;
                  }
                }
                v8 = 0;
                goto LABEL_32;
              }
              if ( *(_DWORD *)(v6 + 108) == 3 )
              {
                v13 = "exp master";
                goto LABEL_27;
              }
              v12 = -2146893783;
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
LABEL_54:
                v8 = 0;
                goto LABEL_32;
              }
              v33 = 22;
            }
            else
            {
              v12 = -2146893783;
              v26 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_54;
              }
              v33 = 8;
            }
            WPP_SF_sDsd(
              v26[2],
              a2,
              (_DWORD)a3,
              (unsigned int)"Status",
              41,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              v33);
            goto LABEL_54;
          }
LABEL_58:
          v12 = -2146893785;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              a2,
              (_DWORD)a3,
              (unsigned int)"Status",
              39,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              1);
          goto LABEL_54;
        }
      }
    }
  }
  v12 = -2146893786;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)v12;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    a2,
    (_DWORD)a3,
    (unsigned int)"Status",
    38,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
    244);
LABEL_32:
  if ( phNewHash )
    BCryptDestroyHash(phNewHash);
  if ( v9 )
  {
    v21 = v10;
    v22 = v9;
    if ( v10 )
    {
      do
      {
        *v22++ = 0;
        --v21;
      }
      while ( v21 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  }
  if ( v8 )
  {
    v23 = v7;
    v24 = v8;
    if ( v7 )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180002510  push    rbp
0x180002512  push    rsi
0x180002513  push    rdi
0x180002514  push    r12
0x180002516  push    r13
0x180002518  push    r14
0x18000251a  push    r15
0x18000251c  sub     rsp, 40h
0x180002520  mov     r12, r9
0x180002523  mov     rsi, r8
0x180002526  mov     rdi, rdx
0x180002529  test    rcx, rcx
0x18000252c  jz      short loc_18000253F
0x18000252e  cmp     dword ptr [rcx], 310h
0x180002534  jb      short loc_18000253F
0x180002536  cmp     dword ptr [rcx+4], 73736C31h
0x18000253d  jz      short loc_180002541
0x18000253f  xor     ecx, ecx
0x180002541  test    rdx, rdx
0x180002544  jz      short loc_180002554
0x180002546  cmp     dword ptr [rdx], 70h ; 'p'
0x180002549  jb      short loc_180002554
0x18000254b  cmp     dword ptr [rdx+4], 73736C33h
0x180002552  jz      short loc_180002556
0x180002554  xor     edi, edi
0x180002556  test    r8, r8
0x180002559  jz      short loc_18000256B
0x18000255b  cmp     dword ptr [r8], 30h ; '0'
0x18000255f  jb      short loc_18000256B
0x180002561  cmp     dword ptr [r8+4], 73736C32h
0x180002569  jz      short loc_18000256D
0x18000256b  xor     esi, esi
0x18000256d  xor     ebp, ebp
0x18000256f  xor     r14d, r14d
0x180002572  xor     r13d, r13d
0x180002575  mov     dword ptr [rsp+78h+Size], ebp
0x18000257c  xor     r15d, r15d
0x18000257f  mov     [rsp+78h+phNewHash], rbp
0x180002587  mov     [rsp+78h+arg_8], r14
0x18000258f  test    rcx, rcx
0x180002592  jz      short loc_1800025AB
0x180002594  test    rdi, rdi
0x180002597  jz      short loc_1800025AB
0x180002599  mov     rax, [rdi+10h]
0x18000259d  test    rax, rax
0x1800025a0  jz      short loc_1800025AB
0x1800025a2  test    rsi, rsi
0x1800025a5  jnz     loc_1800028F5
0x1800025ab  mov     esi, 80090026h
0x1800025b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025b7  lea     rax, WPP_GLOBAL_Control
0x1800025be  cmp     rcx, rax
0x1800025c1  jz      loc_180002788
0x1800025c7  test    byte ptr [rcx+1Ch], 1
0x1800025cb  jz      loc_180002788
0x1800025d1  mov     rcx, [rcx+10h]
0x1800025d5  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800025dc  mov     dword ptr [rsp+78h+var_48], 18F4h
0x1800025e4  lea     r9, aStatus; "Status"
0x1800025eb  mov     [rsp+78h+var_50], rax
0x1800025f0  mov     [rsp+78h+dwFlags], 80090026h
0x1800025f8  call    WPP_SF_sDsd
0x1800025fd  jmp     loc_18000270C
0x180002602  mov     ebp, dword ptr [rsp+78h+Size]
0x180002609  cmp     ebp, [rsi+1Ch]
0x18000260c  jnz     loc_1800028B9
0x180002612  test    r12, r12
0x180002615  jz      loc_1800028B9
0x18000261b  cmp     dword ptr [rdi+8], 304h
0x180002622  jnz     loc_18000283F
0x180002628  mov     ecx, [rdi+6Ch]
0x18000262b  sub     ecx, 1
0x18000262e  jz      loc_18000298A
0x180002634  cmp     ecx, 2
0x180002637  jnz     loc_180002891
0x18000263d  lea     rbx, aExpMaster; "exp master"
0x180002644  mov     rcx, gs:60h
0x18000264d  xor     edx, edx; Flags
0x18000264f  mov     r15d, [rsi+18h]
0x180002653  mov     r8d, r15d; Size
0x180002656  mov     rcx, [rcx+30h]; HeapHandle
0x18000265a  call    cs:__imp_RtlAllocateHeap
0x180002660  mov     r13, rax
0x180002663  test    rax, rax
0x180002666  jz      loc_1800027E8
0x18000266c  mov     rcx, [rsi+10h]; hHash
0x180002670  lea     rdx, [rsp+78h+phNewHash]; phNewHash
0x180002678  mov     r9d, r15d; cbHashObject
0x18000267b  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180002683  mov     r8, rax; pbHashObject
0x180002686  call    cs:__imp_BCryptDuplicateHash
0x18000268c  mov     esi, eax
0x18000268e  test    eax, eax
0x180002690  js      loc_18000279A
0x180002696  mov     rcx, gs:60h
0x18000269f  xor     edx, edx; Flags
0x1800026a1  mov     r8d, ebp; Size
0x1800026a4  mov     rcx, [rcx+30h]; HeapHandle
0x1800026a8  call    cs:__imp_RtlAllocateHeap
0x1800026ae  mov     r14, rax
0x1800026b1  test    rax, rax
0x1800026b4  jz      loc_180002996
0x1800026ba  mov     rcx, [rsp+78h+phNewHash]; hHash
0x1800026c2  xor     r9d, r9d; dwFlags
0x1800026c5  mov     r8d, ebp; cbOutput
0x1800026c8  mov     rdx, rax; pbOutput
0x1800026cb  call    cs:__imp_BCryptFinishHash
0x1800026d1  mov     esi, eax
0x1800026d3  test    eax, eax
0x1800026d5  js      loc_1800029A8
0x1800026db  movzx   r9d, bpl
0x1800026df  mov     [rsp+78h+var_50], r12
0x1800026e4  mov     r8, r14
0x1800026e7  mov     [rsp+78h+dwFlags], 6
0x1800026ef  mov     rdx, rbx
0x1800026f2  mov     rcx, rdi
0x1800026f5  call    TlsDeriveSecret
0x1800026fa  mov     esi, eax
0x1800026fc  test    eax, eax
0x1800026fe  js      loc_1800029B0
0x180002704  mov     rbx, [rsp+78h+arg_18]
0x18000270c  mov     rcx, [rsp+78h+phNewHash]; hHash
0x180002714  test    rcx, rcx
0x180002717  jz      short loc_18000271F
0x180002719  call    cs:__imp_BCryptDestroyHash
0x18000271f  test    r13, r13
0x180002722  jz      short loc_180002755
0x180002724  mov     ecx, r15d
0x180002727  mov     rax, r13
0x18000272a  test    r15d, r15d
0x18000272d  jz      short loc_18000273D
0x18000272f  nop
0x180002730  mov     byte ptr [rax], 0
0x180002733  lea     rax, [rax+1]
0x180002737  sub     rcx, 1
0x18000273b  jnz     short loc_180002730
0x18000273d  mov     rcx, gs:60h
0x180002746  mov     r8, r13; P
0x180002749  xor     edx, edx; Flags
0x18000274b  mov     rcx, [rcx+30h]; HeapHandle
0x18000274f  call    cs:__imp_RtlFreeHeap
0x180002755  test    r14, r14
0x180002758  jz      short loc_180002788
0x18000275a  mov     ecx, ebp
0x18000275c  mov     rax, r14
0x18000275f  test    ebp, ebp
0x180002761  jz      short loc_180002770
0x180002763  mov     byte ptr [rax], 0
0x180002766  lea     rax, [rax+1]
0x18000276a  sub     rcx, 1
0x18000276e  jnz     short loc_180002763
0x180002770  mov     rcx, gs:60h
0x180002779  mov     r8, r14; P
0x18000277c  xor     edx, edx; Flags
0x18000277e  mov     rcx, [rcx+30h]; HeapHandle
0x180002782  call    cs:__imp_RtlFreeHeap
0x180002788  mov     eax, esi
0x18000278a  add     rsp, 40h
0x18000278e  pop     r15
0x180002790  pop     r14
0x180002792  pop     r13
0x180002794  pop     r12
0x180002796  pop     rdi
0x180002797  pop     rsi
0x180002798  pop     rbp
0x180002799  retn
0x18000279a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027a1  lea     rax, WPP_GLOBAL_Control
0x1800027a8  cmp     rcx, rax
0x1800027ab  jz      short loc_1800027DB
0x1800027ad  test    byte ptr [rcx+1Ch], 1
0x1800027b1  jz      short loc_1800027DB
0x1800027b3  mov     rcx, [rcx+10h]
0x1800027b7  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800027be  mov     dword ptr [rsp+78h+var_48], 192Eh
0x1800027c6  lea     r9, aStatus; "Status"
0x1800027cd  mov     [rsp+78h+var_50], rax
0x1800027d2  mov     [rsp+78h+dwFlags], esi
0x1800027d6  call    WPP_SF_sDsd
0x1800027db  mov     r14, [rsp+78h+arg_8]
0x1800027e3  jmp     loc_180002704
0x1800027e8  mov     esi, 0C0000017h
0x1800027ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027f4  lea     rax, WPP_GLOBAL_Control
0x1800027fb  cmp     rcx, rax
0x1800027fe  jz      short loc_1800027DB
0x180002800  test    byte ptr [rcx+1Ch], 1
0x180002804  jz      short loc_1800027DB
0x180002806  mov     rcx, [rcx+10h]
0x18000280a  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002811  mov     dword ptr [rsp+78h+var_48], 1923h
0x180002819  lea     r9, aStatus; "Status"
0x180002820  mov     [rsp+78h+var_50], rax
0x180002825  mov     [rsp+78h+dwFlags], 0C0000017h
0x18000282d  call    WPP_SF_sDsd
0x180002832  mov     r14, [rsp+78h+arg_8]
0x18000283a  jmp     loc_180002704
0x18000283f  mov     esi, 80090029h
0x180002844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000284b  lea     rax, WPP_GLOBAL_Control
0x180002852  cmp     rcx, rax
0x180002855  jz      short loc_180002889
0x180002857  test    byte ptr [rcx+1Ch], 1
0x18000285b  jz      short loc_180002889
0x18000285d  mov     dword ptr [rsp+78h+var_48], 1908h
0x180002865  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000286c  mov     [rsp+78h+var_50], rax
0x180002871  mov     [rsp+78h+dwFlags], 80090029h
0x180002879  mov     rcx, [rcx+10h]
0x18000287d  lea     r9, aStatus; "Status"
0x180002884  call    WPP_SF_sDsd
0x180002889  mov     r14, r13
0x18000288c  jmp     loc_180002704
0x180002891  mov     esi, 80090029h
0x180002896  mov     rcx, cs:WPP_GLOBAL_Control
0x18000289d  lea     rax, WPP_GLOBAL_Control
0x1800028a4  cmp     rcx, rax
0x1800028a7  jz      short loc_180002889
0x1800028a9  test    byte ptr [rcx+1Ch], 1
0x1800028ad  jz      short loc_180002889
0x1800028af  mov     dword ptr [rsp+78h+var_48], 1916h
0x1800028b7  jmp     short loc_180002865
0x1800028b9  mov     esi, 80090027h
0x1800028be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028c5  lea     rax, WPP_GLOBAL_Control
0x1800028cc  cmp     rcx, rax
0x1800028cf  jz      short loc_180002889
0x1800028d1  test    byte ptr [rcx+1Ch], 1
0x1800028d5  jz      short loc_180002889
0x1800028d7  mov     dword ptr [rsp+78h+var_48], 1901h
0x1800028df  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800028e6  mov     [rsp+78h+var_50], rax
0x1800028eb  mov     [rsp+78h+dwFlags], 80090027h
0x1800028f3  jmp     short loc_180002879
0x1800028f5  mov     rbp, [rax+88h]
0x1800028fc  mov     [rsp+78h+arg_18], rbx
0x180002904  test    rbp, rbp
0x180002907  jz      short loc_180002981
0x180002909  cmp     [rbp+0], r13w
0x18000290e  jz      short loc_180002981
0x180002910  xor     ebx, ebx
0x180002912  lea     rcx, g_pHashInfo
0x180002919  nop     dword ptr [rax+00000000h]
0x180002920  cmp     ebx, cs:g_dwHashInfoTotalCount
0x180002926  jnb     loc_180002602
0x18000292c  mov     rax, [rcx+rbx*8]
0x180002930  lea     r14, [rcx+rbx*8]
0x180002934  test    rax, rax
0x180002937  jz      short loc_18000295A
0x180002939  mov     rdx, [rax]; String2
0x18000293c  test    rdx, rdx
0x18000293f  jz      short loc_18000295A
0x180002941  mov     r8d, 40h ; '@'; MaxCount
0x180002947  mov     rcx, rbp; String1
0x18000294a  call    _wcsnicmp
0x18000294f  test    eax, eax
0x180002951  jz      short loc_18000295E
0x180002953  lea     rcx, g_pHashInfo
0x18000295a  inc     ebx
0x18000295c  jmp     short loc_180002920
0x18000295e  lfence
0x180002961  mov     rax, [r14]
0x180002964  test    rax, rax
0x180002967  jz      loc_180002602
0x18000296d  mov     ebp, [rax+8]
0x180002970  cmp     ebp, 0FFh
0x180002976  ja      loc_1800028B9
0x18000297c  jmp     loc_180002609
0x180002981  lea     rbp, aSha256; "SHA256"
0x180002988  jmp     short loc_180002910
0x18000298a  lea     rbx, aEExpMaster; "e exp master"
0x180002991  jmp     loc_180002644
0x180002996  mov     esi, 0C0000017h
0x18000299b  mov     r9d, 1935h
0x1800029a1  mov     ecx, 0C0000017h
0x1800029a6  jmp     short loc_1800029B8
0x1800029a8  mov     r9d, 193Fh
0x1800029ae  jmp     short loc_1800029B6
0x1800029b0  mov     r9d, 1950h
0x1800029b6  mov     ecx, eax
0x1800029b8  lea     rdx, aStatus; "Status"
0x1800029bf  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800029c6  call    DebugTraceError
0x1800029cb  jmp     loc_180002704
```
