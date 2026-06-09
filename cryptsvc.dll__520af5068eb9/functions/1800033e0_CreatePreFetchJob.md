# CreatePreFetchJob

- ea: `0x1800033e0`
- end: `0x18000374e`
- name: `CreatePreFetchJob`
- size: `878`
- prototype: `char *__fastcall(_WORD *Src, struct _CRYPTNET_URL_CACHE_PRE_FETCH_INFO *, int, _WORD *, __int64, FILETIME *lpFileTime1, __int128 *, FILETIME *lpFileTime2)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800028f0`

## callees

- `0x1800033e0`
- `0x180003760`
- `0x1800068b0`
- `0x1800174fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003734`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003734`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003450`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003450`
- `CRYPT32!I_CryptCreateLruEntry` at `0x180003538`
- `CRYPT32!I_CryptCreateLruEntry` at `0x180003538`
- `CRYPT32!I_CryptInsertLruEntry` at `0x180003551`
- `CRYPT32!I_CryptInsertLruEntry` at `0x180003551`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000355b`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x18000355b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800035e0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003613`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003637`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003650`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800036bf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800035e0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003613`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003637`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003650`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800036bf`

## pseudocode

```c
char *__fastcall CreatePreFetchJob(
        _WORD *Src,
        struct _CRYPTNET_URL_CACHE_PRE_FETCH_INFO *a2,
        int a3,
        _WORD *a4,
        __int64 a5,
        FILETIME *lpFileTime1,
        __int128 *a7,
        FILETIME *lpFileTime2)
{
  __int64 v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // edi
  __int64 v14; // rax
  unsigned __int64 v15; // rbp
  char *v16; // rax
  char *v17; // rsi
  unsigned int v18; // r12d
  __int128 v19; // xmm0
  unsigned int v22; // edx
  int v23; // ecx
  FILETIME ThisUpdateTime; // rax
  void *v25; // rcx
  __int128 v26; // [rsp+30h] [rbp-38h] BYREF

  v11 = -1;
  v26 = 0;
  if ( Src )
  {
    v12 = -1;
    do
      ++v12;
    while ( Src[v12] );
  }
  else
  {
    LODWORD(v12) = 0;
  }
  if ( a4 )
  {
    while ( a4[++v11] != 0 )
      ;
    v13 = 2 * v11 + 2;
  }
  else
  {
    v13 = 0;
  }
  v14 = (unsigned int)(2 * v12 + 2);
  v15 = (unsigned int)v14;
  v16 = (char *)LocalAlloc(0x40u, v13 + v14 + 256);
  v17 = v16;
  if ( !v16 )
  {
    SetLastError(0x8007000E);
    return v17;
  }
  v18 = 0;
  *((_QWORD *)v16 + 9) = v16 + 256;
  memcpy_0(v16 + 256, Src, (unsigned int)v15);
  if ( v13 )
  {
    v25 = (void *)(*((_QWORD *)v17 + 9) + 2 * (v15 >> 1));
    *((_QWORD *)v17 + 10) = v25;
    memcpy_0(v25, a4, v13);
  }
  *(_OWORD *)(v17 + 136) = *(_OWORD *)&a2->cbSize;
  *(_OWORD *)(v17 + 152) = *(_OWORD *)&a2->ThisUpdateTime.dwLowDateTime;
  *((_QWORD *)v17 + 21) = a2->PublishTime;
  v19 = *a7;
  *((_DWORD *)v17 + 28) = a3;
  *(_OWORD *)(v17 + 88) = v19;
  *((_DWORD *)v17 + 29) = 0;
  *(FILETIME *)(v17 + 60) = *lpFileTime1;
  if ( a5 )
  {
    v18 = *(_DWORD *)(a5 + 32);
    if ( *(__int16 *)(a5 + 6) >= 0 )
    {
      *((_DWORD *)v17 + 45) = 0;
    }
    else
    {
      v22 = *(_DWORD *)(a5 + 16);
      if ( v22 )
      {
        if ( *(_DWORD *)(a5 + 8) || *(_DWORD *)(a5 + 12) || *(_QWORD *)(a5 + 24) )
        {
          v23 = dword_18002027C;
          if ( v22 >= dword_18002027C )
          {
            v23 = *(_DWORD *)(a5 + 16);
            if ( v22 > dword_180020280 )
              v23 = dword_180020280;
          }
          *((_DWORD *)v17 + 45) = v23;
          if ( v23 )
          {
            if ( CompareFileTime(lpFileTime1, &a2->ThisUpdateTime) >= 0 )
            {
              if ( CompareFileTime(lpFileTime1, lpFileTime2) > 0 )
                ThisUpdateTime = *lpFileTime2;
              else
                ThisUpdateTime = *lpFileTime1;
            }
            else
            {
              ThisUpdateTime = a2->ThisUpdateTime;
            }
            *((_QWORD *)v17 + 23) = *(_QWORD *)&ThisUpdateTime + 10000000LL * *((unsigned int *)v17 + 45);
            if ( CompareFileTime((const FILETIME *)v17 + 23, lpFileTime2) < 0 )
              *((FILETIME *)v17 + 23) = *lpFileTime2;
            *((_DWORD *)v17 + 44) = (!a2->PublishTime.dwLowDateTime && !a2->PublishTime.dwHighDateTime
                                  || CompareFileTime((const FILETIME *)v17 + 23, &a2->PublishTime) < 0)
                                 && CompareFileTime((const FILETIME *)v17 + 23, &a2->NextUpdateTime) < 0;
          }
        }
        else
        {
          *((_DWORD *)v17 + 45) = 0;
        }
      }
      else
      {
        *((_DWORD *)v17 + 45) = 0;
      }
    }
  }
  SetRandomPreFetchTimes(a2, lpFileTime2, v18, (unsigned int *)v17 + 52, (struct _FILETIME *const)v17 + 24);
  LODWORD(v26) = 16;
  *((_QWORD *)&v26 + 1) = v17 + 88;
  if ( (unsigned int)I_CryptCreateLruEntry(hPreFetchJobLruCache, &v26, v17, v17 + 104) )
  {
    I_CryptInsertLruEntry(*((_QWORD *)v17 + 13), 0);
    I_CryptReleaseLruEntry(*((_QWORD *)v17 + 13));
    return v17;
  }
  PkiFree(v17);
  return 0;
}

```

## disassembly

```asm
0x1800033e0  mov     [rsp+arg_8], rbx
0x1800033e5  mov     [rsp+arg_18], rbp
0x1800033ea  mov     [rsp+arg_10], r8d
0x1800033ef  push    rsi
0x1800033f0  push    rdi
0x1800033f1  push    r13
0x1800033f3  push    r14
0x1800033f5  push    r15
0x1800033f7  sub     rsp, 40h
0x1800033fb  mov     rbx, rcx
0x1800033fe  xorps   xmm0, xmm0
0x180003401  mov     r15, r9
0x180003404  mov     r13, rdx
0x180003407  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000340e  movups  [rsp+68h+var_38], xmm0
0x180003413  test    rbx, rbx
0x180003416  jz      loc_180003728
0x18000341c  mov     rax, rcx
0x18000341f  nop
0x180003420  inc     rax
0x180003423  cmp     word ptr [rbx+rax*2], 0
0x180003428  jnz     short loc_180003420
0x18000342a  test    r15, r15
0x18000342d  jnz     loc_180003580
0x180003433  xor     edi, edi
0x180003435  lea     eax, ds:2[rax*2]
0x18000343c  mov     r14d, edi
0x18000343f  lea     rdx, [rax+100h]
0x180003446  mov     ebp, eax
0x180003448  add     rdx, r14; uBytes
0x18000344b  mov     ecx, 40h ; '@'; uFlags
0x180003450  call    cs:__imp_LocalAlloc
0x180003456  mov     rsi, rax
0x180003459  test    rax, rax
0x18000345c  jz      loc_18000372F
0x180003462  mov     [rsp+68h+arg_0], r12
0x180003467  xor     r12d, r12d
0x18000346a  lea     rcx, [rax+100h]; void *
0x180003471  mov     r8d, ebp; Size
0x180003474  mov     rdx, rbx; Src
0x180003477  mov     [rax+48h], rcx
0x18000347b  call    memcpy_0
0x180003480  test    edi, edi
0x180003482  jnz     loc_180003677
0x180003488  movups  xmm0, xmmword ptr [r13+0]
0x18000348d  mov     rax, [rsp+68h+arg_30]
0x180003495  lea     rbp, [rsi+58h]
0x180003499  mov     rdi, [rsp+68h+lpFileTime1]
0x1800034a1  mov     r14, [rsp+68h+lpFileTime2]
0x1800034a9  movups  xmmword ptr [rsi+88h], xmm0
0x1800034b0  movups  xmm1, xmmword ptr [r13+10h]
0x1800034b5  movups  xmmword ptr [rsi+98h], xmm1
0x1800034bc  movsd   xmm0, qword ptr [r13+20h]
0x1800034c2  movsd   qword ptr [rsi+0A8h], xmm0
0x1800034ca  movups  xmm0, xmmword ptr [rax]
0x1800034cd  mov     eax, [rsp+68h+arg_10]
0x1800034d4  mov     [rsi+70h], eax
0x1800034d7  movups  xmmword ptr [rbp+0], xmm0
0x1800034db  mov     [rsi+74h], r12d
0x1800034df  mov     rax, [rdi]
0x1800034e2  mov     [rsi+3Ch], rax
0x1800034e6  mov     rax, [rsp+68h+arg_20]
0x1800034ee  test    rax, rax
0x1800034f1  jnz     loc_180003599
0x1800034f7  lea     rax, [rsi+0C0h]
0x1800034fe  mov     r8d, r12d; unsigned int
0x180003501  lea     r9, [rsi+0D0h]; unsigned int *
0x180003508  mov     [rsp+68h+var_48], rax; struct _FILETIME *
0x18000350d  mov     rdx, r14; struct _FILETIME *
0x180003510  mov     rcx, r13; struct _CRYPTNET_URL_CACHE_PRE_FETCH_INFO *
0x180003513  call    ?SetRandomPreFetchTimes@@YAXPEAU_CRYPTNET_URL_CACHE_PRE_FETCH_INFO@@PEAU_FILETIME@@KPEAKQEAU2@@Z; SetRandomPreFetchTimes(_CRYPTNET_URL_CACHE_PRE_FETCH_INFO *,_FILETIME *,ulong,ulong *,_FILETIME * const)
0x180003518  mov     rcx, cs:?hPreFetchJobLruCache@@3PEAXEA; void * hPreFetchJobLruCache
0x18000351f  lea     r9, [rsi+68h]
0x180003523  mov     r8, rsi
0x180003526  mov     dword ptr [rsp+68h+var_38], 10h
0x18000352e  lea     rdx, [rsp+68h+var_38]
0x180003533  mov     qword ptr [rsp+68h+var_38+8], rbp
0x180003538  call    cs:__imp_I_CryptCreateLruEntry
0x18000353e  mov     r12, [rsp+68h+arg_0]
0x180003543  test    eax, eax
0x180003545  jz      loc_180003668
0x18000354b  mov     rcx, [rsi+68h]
0x18000354f  xor     edx, edx
0x180003551  call    cs:__imp_I_CryptInsertLruEntry
0x180003557  mov     rcx, [rsi+68h]
0x18000355b  call    cs:__imp_I_CryptReleaseLruEntry
0x180003561  mov     rax, rsi
0x180003564  mov     rbx, [rsp+68h+arg_8]
0x180003569  mov     rbp, [rsp+68h+arg_18]
0x180003571  add     rsp, 40h
0x180003575  pop     r15
0x180003577  pop     r14
0x180003579  pop     r13
0x18000357b  pop     rdi
0x18000357c  pop     rsi
0x18000357d  retn
0x180003580  cmp     word ptr [r9+rcx*2+2], 0
0x180003587  lea     rcx, [rcx+1]
0x18000358b  jnz     short loc_180003580
0x18000358d  lea     edi, ds:2[rcx*2]
0x180003594  jmp     loc_180003435
0x180003599  cmp     word ptr [rax+6], 0
0x18000359e  mov     r12d, [rax+20h]
0x1800035a2  jge     loc_18000373F
0x1800035a8  mov     edx, [rax+10h]
0x1800035ab  test    edx, edx
0x1800035ad  jz      loc_180003711
0x1800035b3  cmp     dword ptr [rax+8], 0
0x1800035b7  jz      loc_1800036E0
0x1800035bd  mov     ecx, cs:dword_18002027C
0x1800035c3  cmp     edx, ecx
0x1800035c5  jnb     loc_180003696
0x1800035cb  mov     [rsi+0B4h], ecx
0x1800035d1  test    ecx, ecx
0x1800035d3  jz      loc_1800034F7
0x1800035d9  lea     rdx, [r13+10h]; lpFileTime2
0x1800035dd  mov     rcx, rdi; lpFileTime1
0x1800035e0  call    cs:__imp_CompareFileTime
0x1800035e6  test    eax, eax
0x1800035e8  jns     loc_1800036B9
0x1800035ee  mov     rax, [r13+10h]
0x1800035f2  mov     ecx, [rsi+0B4h]
0x1800035f8  imul    rdx, rcx, 989680h
0x1800035ff  lea     rcx, [rsi+0B8h]; lpFileTime1
0x180003606  add     rdx, rax
0x180003609  mov     [rsi+0B8h], rdx
0x180003610  mov     rdx, r14; lpFileTime2
0x180003613  call    cs:__imp_CompareFileTime
0x180003619  test    eax, eax
0x18000361b  js      loc_1800036AA
0x180003621  cmp     dword ptr [r13+20h], 0
0x180003626  lea     rdx, [r13+20h]; lpFileTime2
0x18000362a  jz      loc_1800036D1
0x180003630  lea     rcx, [rsi+0B8h]; lpFileTime1
0x180003637  call    cs:__imp_CompareFileTime
0x18000363d  test    eax, eax
0x18000363f  jns     loc_180003704
0x180003645  lea     rdx, [r13+18h]; lpFileTime2
0x180003649  lea     rcx, [rsi+0B8h]; lpFileTime1
0x180003650  call    cs:__imp_CompareFileTime
0x180003656  xor     ecx, ecx
0x180003658  test    eax, eax
0x18000365a  sets    cl
0x18000365d  mov     [rsi+0B0h], ecx
0x180003663  jmp     loc_1800034F7
0x180003668  mov     rcx, rsi; hMem
0x18000366b  call    PkiFree
0x180003670  xor     eax, eax
0x180003672  jmp     loc_180003564
0x180003677  mov     rax, [rsi+48h]
0x18000367b  mov     r8, r14; Size
0x18000367e  shr     rbp, 1
0x180003681  mov     rdx, r15; Src
0x180003684  lea     rcx, [rax+rbp*2]; void *
0x180003688  mov     [rsi+50h], rcx
0x18000368c  call    memcpy_0
0x180003691  jmp     loc_180003488
0x180003696  cmp     edx, cs:dword_180020280
0x18000369c  mov     ecx, edx
0x18000369e  cmova   ecx, cs:dword_180020280
0x1800036a5  jmp     loc_1800035CB
0x1800036aa  mov     rax, [r14]
0x1800036ad  mov     [rsi+0B8h], rax
0x1800036b4  jmp     loc_180003621
0x1800036b9  mov     rdx, r14; lpFileTime2
0x1800036bc  mov     rcx, rdi; lpFileTime1
0x1800036bf  call    cs:__imp_CompareFileTime
0x1800036c5  test    eax, eax
0x1800036c7  jg      short loc_180003720
0x1800036c9  mov     rax, [rdi]
0x1800036cc  jmp     loc_1800035F2
0x1800036d1  cmp     dword ptr [rdx+4], 0
0x1800036d5  jz      loc_180003645
0x1800036db  jmp     loc_180003630
0x1800036e0  cmp     dword ptr [rax+0Ch], 0
0x1800036e4  jnz     loc_1800035BD
0x1800036ea  cmp     qword ptr [rax+18h], 0
0x1800036ef  jnz     loc_1800035BD
0x1800036f5  mov     dword ptr [rsi+0B4h], 0
0x1800036ff  jmp     loc_1800034F7
0x180003704  xor     ecx, ecx
0x180003706  mov     [rsi+0B0h], ecx
0x18000370c  jmp     loc_1800034F7
0x180003711  mov     dword ptr [rsi+0B4h], 0
0x18000371b  jmp     loc_1800034F7
0x180003720  mov     rax, [r14]
0x180003723  jmp     loc_1800035F2
0x180003728  xor     eax, eax
0x18000372a  jmp     loc_18000342A
0x18000372f  mov     ecx, 8007000Eh; dwErrCode
0x180003734  call    cs:__imp_SetLastError
0x18000373a  jmp     loc_180003561
0x18000373f  mov     dword ptr [rsi+0B4h], 0
0x180003749  jmp     loc_1800034F7
```
