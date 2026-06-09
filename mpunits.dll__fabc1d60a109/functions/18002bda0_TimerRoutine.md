# TimerRoutine

- ea: `0x18002bda0`
- end: `0x18002c46d`
- name: `TimerRoutine`
- size: `1741`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180007800`
- `0x18000b12c`
- `0x18000b3b4`
- `0x18000b408`
- `0x18002bda0`
- `0x18002c558`
- `0x18002c6c8`
- `0x18002c868`
- `0x18002ca08`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x18002bee4`
- `msvcrt!malloc` at `0x18002bf8e`
- `msvcrt!malloc` at `0x18002bee4`
- `msvcrt!malloc` at `0x18002bf8e`
- `msvcrt!free` at `0x18002c1ff`
- `msvcrt!free` at `0x18002c208`
- `msvcrt!free` at `0x18002c40f`
- `msvcrt!free` at `0x18002c418`
- `msvcrt!free` at `0x18002c1ff`
- `msvcrt!free` at `0x18002c208`
- `msvcrt!free` at `0x18002c40f`
- `msvcrt!free` at `0x18002c418`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002be0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002be48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c382`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002be0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002be48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c382`
- `pdh!PdhGetCounterInfoW` at `0x18002becd`
- `pdh!PdhGetCounterInfoW` at `0x18002bf08`
- `pdh!PdhGetCounterInfoW` at `0x18002becd`
- `pdh!PdhGetCounterInfoW` at `0x18002bf08`
- `pdh!PdhCollectQueryDataWithTime` at `0x18002be39`
- `pdh!PdhCollectQueryDataWithTime` at `0x18002be39`
- `pdh!PdhGetFormattedCounterArrayW` at `0x18002bf77`
- `pdh!PdhGetFormattedCounterArrayW` at `0x18002bfe5`
- `pdh!PdhGetFormattedCounterArrayW` at `0x18002bf77`
- `pdh!PdhGetFormattedCounterArrayW` at `0x18002bfe5`

## pseudocode

```c
__int64 __fastcall TimerRoutine(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  unsigned int CounterInfoW; // edi
  struct _PDH_COUNTER_INFO_W *v5; // r13
  struct _PDH_FMT_COUNTERVALUE_ITEM_W *ItemBuffer; // rsi
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r12
  __int64 v13; // rcx
  struct _PDH_COUNTER_INFO_W *v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 szCounterName; // rax
  int v20; // edx
  int v21; // edx
  int v22; // edx
  DWORD v23; // edx
  __int64 v24; // rcx
  DWORD v25; // edx
  __int64 v26; // rax
  DWORD v27; // r9d
  DWORD v28; // r8d
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r12
  int ResultCallback; // eax
  __int64 i; // rdi
  int v38; // eax
  int v39; // eax
  DWORD pdwBufferSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwItemCount; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v43; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR szObjectName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v45; // [rsp+48h] [rbp-B8h]
  int v46; // [rsp+4Ch] [rbp-B4h]
  LONGLONG pllTimeStamp; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h]
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  const char *v51; // [rsp+78h] [rbp-88h]
  int v52; // [rsp+80h] [rbp-80h]
  int v53; // [rsp+84h] [rbp-7Ch]
  __int64 *v54; // [rsp+90h] [rbp-70h]
  __int64 v55; // [rsp+98h] [rbp-68h] BYREF
  __int128 v56; // [rsp+A0h] [rbp-60h]
  __int128 v57; // [rsp+B0h] [rbp-50h]
  int v58; // [rsp+C0h] [rbp-40h]
  _BYTE v59[12]; // [rsp+C4h] [rbp-3Ch]
  _OWORD v60[2]; // [rsp+D0h] [rbp-30h] BYREF

  pllTimeStamp = 0;
  dwItemCount = 0;
  pdwBufferSize = 0;
  memset(v60, 0, sizeof(v60));
  v43 = 0;
  ExecutionContext_SaveThread((LPGUID)v60);
  if ( *(_QWORD *)(a1 + 104) != GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(a1 + 64) )
    _Pump_BeginDeferring(a1 + 64);
  v2 = PdhCollectQueryDataWithTime(*(PDH_HQUERY *)(a1 + 8), &pllTimeStamp);
  CounterInfoW = v2;
  if ( v2 == -2147481643 )
  {
    if ( *(_QWORD *)(a1 + 104) != GetCurrentThreadId() && (unsigned int)_Pump_EndDeferringHelper(a1 + 64) )
      _Pump_EndDeferring(a1 + 64);
    return ExecutionContext_RestoreThread((LPGUID)v60);
  }
  v5 = 0;
  ItemBuffer = 0;
  if ( v2 )
  {
    v7 = 512;
    v8 = v2;
LABEL_10:
    trace_PDH(v8, v3, v7);
    v9 = 1;
    goto LABEL_66;
  }
  v10 = 0;
  v9 = 0;
  v46 = 0;
  if ( !*(_DWORD *)(a1 + 32) )
    goto LABEL_75;
  while ( 1 )
  {
    v11 = *(_QWORD *)(a1 + 48);
    pdwBufferSize = 0;
    v12 = (unsigned int)v10;
    CounterInfoW = PdhGetCounterInfoW(*(PDH_HCOUNTER *)(v11 + 8 * v10), 0, &pdwBufferSize, 0);
    if ( CounterInfoW != -2147481646 )
    {
      trace_EH_Check(v13, 518);
      v5 = 0;
LABEL_64:
      ItemBuffer = 0;
      goto LABEL_65;
    }
    v14 = (struct _PDH_COUNTER_INFO_W *)malloc(pdwBufferSize);
    v5 = v14;
    if ( !v14 )
    {
      v34 = 521;
LABEL_60:
      trace_EH_Check(v15, v34);
      goto LABEL_64;
    }
    v16 = PdhGetCounterInfoW(*(PDH_HCOUNTER *)(*(_QWORD *)(a1 + 48) + 8 * v12), 0, &pdwBufferSize, v14);
    CounterInfoW = v16;
    if ( v16 )
    {
      trace_PDH(v16, v17, 524);
      ItemBuffer = 0;
      v9 = 1;
      goto LABEL_66;
    }
    v18 = *(_QWORD *)(a1 + 40);
    szObjectName = v5->CounterPath.szObjectName;
    szCounterName = (__int64)v5->CounterPath.szCounterName;
    pdwBufferSize = 0;
    v20 = *(_DWORD *)(v18 + 4 * v12);
    v49 = szCounterName;
    v21 = v20 - 2;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        if ( v22 == 1 )
          v23 = 33280;
        else
          v23 = 0;
      }
      else
      {
        v23 = 33792;
      }
    }
    else
    {
      v23 = 33024;
    }
    CounterInfoW = PdhGetFormattedCounterArrayW(
                     *(PDH_HCOUNTER *)(*(_QWORD *)(a1 + 48) + 8 * v12),
                     v23,
                     &pdwBufferSize,
                     &dwItemCount,
                     0);
    if ( CounterInfoW != -2147481646 )
    {
      v34 = 532;
      goto LABEL_60;
    }
    ItemBuffer = (struct _PDH_FMT_COUNTERVALUE_ITEM_W *)malloc(pdwBufferSize);
    if ( !ItemBuffer )
    {
      trace_EH_Check(v24, 535);
LABEL_65:
      v9 = 4;
      goto LABEL_66;
    }
    switch ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 4 * v12) )
    {
      case 2:
        v25 = 33024;
        break;
      case 3:
        v25 = 33792;
        break;
      case 4:
        v25 = 33280;
        break;
      default:
        v25 = 0;
        break;
    }
    CounterInfoW = PdhGetFormattedCounterArrayW(
                     *(PDH_HCOUNTER *)(*(_QWORD *)(a1 + 48) + 8 * v12),
                     v25,
                     &pdwBufferSize,
                     &dwItemCount,
                     ItemBuffer);
    if ( CounterInfoW + 2147481643 <= 3 || CounterInfoW == -1073738810 || CounterInfoW == -1073738822 )
      goto LABEL_53;
    if ( CounterInfoW )
    {
      v7 = 558;
      v8 = CounterInfoW;
      goto LABEL_10;
    }
    v26 = *(_QWORD *)(a1 + 56);
    v48 = v26;
LABEL_52:
    if ( v26 )
      break;
LABEL_53:
    free(ItemBuffer);
    free(v5);
    v5 = 0;
    v10 = (unsigned int)(v46 + 1);
    v46 = v10;
    if ( (unsigned int)v10 >= *(_DWORD *)(a1 + 32) )
    {
      ItemBuffer = 0;
      if ( v9 )
        goto LABEL_66;
      goto LABEL_75;
    }
  }
  v54 = (__int64 *)(v26 + 32);
  ((void (__fastcall *)(_QWORD))ObserverProtocol_AddRef)(*(_QWORD *)(v26 + 32));
  v27 = dwItemCount;
  v28 = 0;
  v45 = 0;
  if ( !dwItemCount )
  {
LABEL_51:
    v33 = *v54;
    v48 = *(_QWORD *)(v48 + 16);
    ((void (__fastcall *)(__int64))ObserverProtocol_Release)(v33);
    v26 = v48;
    goto LABEL_52;
  }
  while ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 4 * v12) != 2 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 4 * v12) == 3 )
    {
      v29 = WrapUint64(pllTimeStamp, (unsigned int)ItemBuffer + 24 * v28, (unsigned int)&v43, (_DWORD)szObjectName, v49);
      v9 = v29;
      if ( v29 )
      {
        v31 = 589;
        goto LABEL_42;
      }
      goto LABEL_46;
    }
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 4 * v12) == 4 )
    {
      v29 = WrapReal64(pllTimeStamp, (unsigned int)ItemBuffer + 24 * v28, (unsigned int)&v43, (_DWORD)szObjectName, v49);
      v9 = v29;
      if ( v29 )
      {
        v31 = 579;
        goto LABEL_42;
      }
      goto LABEL_46;
    }
LABEL_50:
    v45 = ++v28;
    if ( v28 >= v27 )
      goto LABEL_51;
  }
  v29 = WrapUint32(pllTimeStamp, (unsigned int)ItemBuffer + 24 * v28, (unsigned int)&v43, (_DWORD)szObjectName, v49);
  v9 = v29;
  if ( !v29 )
  {
LABEL_46:
    ExecutionContext_SetContext(*(LPVOID *)(v48 + 48));
    v55 = v43;
    v58 = 15;
    *(_QWORD *)&v59[4] = 0;
    v32 = *v54;
    *(_QWORD *)v59 = v43 == 0 ? 0x20000000 : 0;
    v56 = 0;
    v57 = 0;
    ((void (__fastcall *)(__int64, __int64 *))ObserverProtocol_PostNext)(v32, &v55);
    if ( v43 && *(_QWORD *)v43 )
      (*(void (**)(void))(*(_QWORD *)v43 + 16LL))();
    v27 = dwItemCount;
    v28 = v45;
    v43 = 0;
    goto LABEL_50;
  }
  v31 = 584;
LABEL_42:
  trace_MI(v29, v30, v31);
LABEL_66:
  szObjectName = 0;
  v35 = EnableErrorDetails();
  if ( CounterInfoW )
  {
    TryCreatePdhErrorDetails(CounterInfoW);
    if ( NITS_PRESENCE_STUB != 1 )
    {
      ResultCallback = JobQueryResultCallback();
      v50 = 0;
      v52 = 627;
      v53 = -1;
      v51 = "admin\\wmi\\winomi\\mp\\perf\\formattedprobe.c";
      AssertW_Checked(
        ResultCallback == 0,
        (int)"!((NITS_PRESENCE_STUB != NitsStubbedOut) ? NITS_STUB.DidFault() : NitsFalse)",
        (int)L"Ignoring error deliberately",
        (int)&v50,
        0);
    }
  }
  CatchErrorDetails(v35, &szObjectName);
  for ( i = *(_QWORD *)(a1 + 56); i; i = *(_QWORD *)(i + 16) )
  {
    ExecutionContext_SetContext(*(LPVOID *)(i + 48));
    ((void (__fastcall *)(_QWORD, _QWORD, LPWSTR))ObserverProtocol_PostErrorAndDispose)(
      *(_QWORD *)(i + 32),
      v9,
      szObjectName);
  }
  if ( szObjectName && *(_QWORD *)szObjectName )
    (*(void (**)(void))(*(_QWORD *)szObjectName + 16LL))();
LABEL_75:
  if ( *(_QWORD *)(a1 + 104) != GetCurrentThreadId() )
  {
    v38 = (unsigned int)_Pump_EndDeferringHelper(a1 + 64) ? _Pump_EndDeferring(a1 + 64) : 0;
    if ( v38 && NITS_PRESENCE_STUB != 1 )
    {
      v39 = JobQueryResultCallback();
      v50 = 0;
      v51 = "admin\\wmi\\winomi\\mp\\perf\\formattedprobe.c";
      v52 = 646;
      v53 = -1;
      AssertW_Checked(
        v39 == 0,
        (int)"!((NITS_PRESENCE_STUB != NitsStubbedOut) ? NITS_STUB.DidFault() : NitsFalse)",
        (int)L"Ignoring error deliberately",
        (int)&v50,
        0);
    }
  }
  free(v5);
  free(ItemBuffer);
  if ( v43 && *(_QWORD *)v43 )
    (*(void (**)(void))(*(_QWORD *)v43 + 16LL))();
  return ExecutionContext_RestoreThread((LPGUID)v60);
}

```

## disassembly

```asm
0x18002bda0  push    rbp
0x18002bda2  push    rbx
0x18002bda3  push    rsi
0x18002bda4  push    rdi
0x18002bda5  push    r12
0x18002bda7  push    r13
0x18002bda9  push    r14
0x18002bdab  push    r15
0x18002bdad  lea     rbp, [rsp-8]
0x18002bdb2  sub     rsp, 108h
0x18002bdb9  mov     rax, cs:__security_cookie
0x18002bdc0  xor     rax, rsp
0x18002bdc3  mov     [rbp+40h+var_50], rax
0x18002bdc7  mov     rax, cs:off_180047C30
0x18002bdce  xorps   xmm0, xmm0
0x18002bdd1  mov     r14, rcx
0x18002bdd4  mov     [rsp+140h+pllTimeStamp], 0
0x18002bddd  mov     [rsp+140h+dwItemCount], 0
0x18002bde5  lea     rcx, [rbp+40h+var_70]
0x18002bde9  mov     [rsp+140h+pdwBufferSize], 0
0x18002bdf1  movups  [rbp+40h+var_70], xmm0
0x18002bdf5  mov     [rsp+140h+var_108], 0
0x18002bdfe  movups  [rbp+40h+var_60], xmm0
0x18002be02  mov     rax, [rax]
0x18002be05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be0a  lea     r15, [r14+40h]
0x18002be0e  call    cs:__imp_GetCurrentThreadId
0x18002be14  mov     eax, eax
0x18002be16  cmp     [r15+28h], rax
0x18002be1a  jz      short loc_18002BE30
0x18002be1c  mov     rcx, r15
0x18002be1f  call    __Pump_BeginDeferringHelper
0x18002be24  test    eax, eax
0x18002be26  jz      short loc_18002BE30
0x18002be28  mov     rcx, r15
0x18002be2b  call    __Pump_BeginDeferring
0x18002be30  mov     rcx, [r14+8]; hQuery
0x18002be34  lea     rdx, [rsp+140h+pllTimeStamp]; pllTimeStamp
0x18002be39  call    cs:__imp_PdhCollectQueryDataWithTime
0x18002be3f  mov     edi, eax
0x18002be41  cmp     eax, 800007D5h
0x18002be46  jnz     short loc_18002BE77
0x18002be48  call    cs:__imp_GetCurrentThreadId
0x18002be4e  mov     eax, eax
0x18002be50  cmp     [r15+28h], rax
0x18002be54  jz      loc_18002C439
0x18002be5a  mov     rcx, r15
0x18002be5d  call    __Pump_EndDeferringHelper
0x18002be62  test    eax, eax
0x18002be64  jz      loc_18002C439
0x18002be6a  mov     rcx, r15
0x18002be6d  call    __Pump_EndDeferring
0x18002be72  jmp     loc_18002C439
0x18002be77  xor     r13d, r13d
0x18002be7a  lea     r12, aAdminWmiWinomi_15; "admin\\wmi\\winomi\\mp\\perf\\formatted"...
0x18002be81  xor     esi, esi
0x18002be83  test    eax, eax
0x18002be85  jz      short loc_18002BE9E
0x18002be87  mov     r8d, 200h
0x18002be8d  mov     ecx, eax
0x18002be8f  call    trace_PDH
0x18002be94  mov     ebx, 1
0x18002be99  jmp     loc_18002C292
0x18002be9e  xor     eax, eax
0x18002bea0  xor     ebx, ebx
0x18002bea2  mov     [rsp+140h+var_F4], eax
0x18002bea6  cmp     [r14+20h], eax
0x18002beaa  jbe     loc_18002C382
0x18002beb0  mov     rcx, [r14+30h]
0x18002beb4  lea     r8, [rsp+140h+pdwBufferSize]; pdwBufferSize
0x18002beb9  mov     [rsp+140h+pdwBufferSize], 0
0x18002bec1  xor     r9d, r9d; lpBuffer
0x18002bec4  xor     edx, edx; bRetrieveExplainText
0x18002bec6  mov     r12d, eax
0x18002bec9  mov     rcx, [rcx+rax*8]; hCounter
0x18002becd  call    cs:__imp_PdhGetCounterInfoW
0x18002bed3  mov     edi, eax
0x18002bed5  cmp     eax, 800007D2h
0x18002beda  jnz     loc_18002C27E
0x18002bee0  mov     ecx, [rsp+140h+pdwBufferSize]; Size
0x18002bee4  call    cs:__imp_malloc
0x18002beea  mov     r13, rax
0x18002beed  test    rax, rax
0x18002bef0  jz      loc_18002C277
0x18002bef6  mov     rcx, [r14+30h]
0x18002befa  lea     r8, [rsp+140h+pdwBufferSize]; pdwBufferSize
0x18002beff  mov     r9, rax; lpBuffer
0x18002bf02  xor     edx, edx; bRetrieveExplainText
0x18002bf04  mov     rcx, [rcx+r12*8]; hCounter
0x18002bf08  call    cs:__imp_PdhGetCounterInfoW
0x18002bf0e  mov     edi, eax
0x18002bf10  test    eax, eax
0x18002bf12  jnz     loc_18002C261
0x18002bf18  mov     rax, [r13+38h]
0x18002bf1c  mov     rcx, [r14+28h]
0x18002bf20  mov     [rsp+140h+var_100], rax
0x18002bf25  mov     rax, [r13+58h]
0x18002bf29  mov     [rsp+140h+pdwBufferSize], edi
0x18002bf2d  mov     edx, [rcx+r12*4]
0x18002bf31  mov     [rsp+140h+var_E0], rax
0x18002bf36  sub     edx, 2
0x18002bf39  jz      short loc_18002BF57
0x18002bf3b  sub     edx, 1
0x18002bf3e  jz      short loc_18002BF50
0x18002bf40  cmp     edx, 1
0x18002bf43  jz      short loc_18002BF49
0x18002bf45  xor     edx, edx
0x18002bf47  jmp     short loc_18002BF5C
0x18002bf49  mov     edx, 8200h
0x18002bf4e  jmp     short loc_18002BF5C
0x18002bf50  mov     edx, 8400h
0x18002bf55  jmp     short loc_18002BF5C
0x18002bf57  mov     edx, 8100h; dwFormat
0x18002bf5c  mov     rcx, [r14+30h]
0x18002bf60  lea     r9, [rsp+140h+dwItemCount]; lpdwItemCount
0x18002bf65  lea     r8, [rsp+140h+pdwBufferSize]; lpdwBufferSize
0x18002bf6a  mov     [rsp+140h+ItemBuffer], 0; ItemBuffer
0x18002bf73  mov     rcx, [rcx+r12*8]; hCounter
0x18002bf77  call    cs:__imp_PdhGetFormattedCounterArrayW
0x18002bf7d  mov     edi, eax
0x18002bf7f  cmp     eax, 800007D2h
0x18002bf84  jnz     loc_18002C255
0x18002bf8a  mov     ecx, [rsp+140h+pdwBufferSize]; Size
0x18002bf8e  call    cs:__imp_malloc
0x18002bf94  mov     rsi, rax
0x18002bf97  test    rax, rax
0x18002bf9a  jz      loc_18002C249
0x18002bfa0  mov     rdx, [r14+28h]
0x18002bfa4  mov     eax, [rdx+r12*4]
0x18002bfa8  sub     eax, 2
0x18002bfab  jz      short loc_18002BFC9
0x18002bfad  sub     eax, 1
0x18002bfb0  jz      short loc_18002BFC2
0x18002bfb2  cmp     eax, 1
0x18002bfb5  jz      short loc_18002BFBB
0x18002bfb7  xor     edx, edx
0x18002bfb9  jmp     short loc_18002BFCE
0x18002bfbb  mov     edx, 8200h
0x18002bfc0  jmp     short loc_18002BFCE
0x18002bfc2  mov     edx, 8400h
0x18002bfc7  jmp     short loc_18002BFCE
0x18002bfc9  mov     edx, 8100h; dwFormat
0x18002bfce  mov     rcx, [r14+30h]
0x18002bfd2  lea     r9, [rsp+140h+dwItemCount]; lpdwItemCount
0x18002bfd7  lea     r8, [rsp+140h+pdwBufferSize]; lpdwBufferSize
0x18002bfdc  mov     [rsp+140h+ItemBuffer], rsi; ItemBuffer
0x18002bfe1  mov     rcx, [rcx+r12*8]; hCounter
0x18002bfe5  call    cs:__imp_PdhGetFormattedCounterArrayW
0x18002bfeb  mov     edi, eax
0x18002bfed  add     eax, 7FFFF82Bh
0x18002bff2  cmp     eax, 3
0x18002bff5  jbe     loc_18002C1FC
0x18002bffb  cmp     edi, 0C0000BC6h
0x18002c001  jz      loc_18002C1FC
0x18002c007  cmp     edi, 0C0000BBAh
0x18002c00d  jz      loc_18002C1FC
0x18002c013  test    edi, edi
0x18002c015  jnz     loc_18002C23C
0x18002c01b  mov     rax, [r14+38h]
0x18002c01f  mov     [rsp+140h+var_E8], rax
0x18002c024  jmp     loc_18002C1F3
0x18002c029  lea     rcx, [rax+20h]
0x18002c02d  mov     rax, cs:off_180047BB0
0x18002c034  mov     [rbp+40h+var_B0], rcx
0x18002c038  mov     rcx, [rcx]
0x18002c03b  mov     rax, [rax+8]
0x18002c03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c044  mov     r9d, [rsp+140h+dwItemCount]
0x18002c049  xor     r8d, r8d
0x18002c04c  mov     [rsp+140h+var_F8], r8d
0x18002c051  test    r9d, r9d
0x18002c054  jz      loc_18002C1C9
0x18002c05a  mov     rcx, [r14+28h]
0x18002c05e  mov     edx, [rcx+r12*4]
0x18002c062  sub     edx, 2
0x18002c065  jz      loc_18002C0EB
0x18002c06b  sub     edx, 1
0x18002c06e  jz      short loc_18002C0B7
0x18002c070  cmp     edx, 1
0x18002c073  jnz     loc_18002C1B8
0x18002c079  mov     rax, [rsp+140h+var_E0]
0x18002c07e  lea     rcx, [r8+r8*2]
0x18002c082  mov     r9, [rsp+140h+var_100]
0x18002c087  lea     rdx, [rsi+rcx*8]
0x18002c08b  mov     rcx, [rsp+140h+pllTimeStamp]
0x18002c090  lea     r8, [rsp+140h+var_108]
0x18002c095  mov     [rsp+140h+ItemBuffer], rax
0x18002c09a  call    WrapReal64
0x18002c09f  mov     ebx, eax
0x18002c0a1  test    eax, eax
0x18002c0a3  jz      short loc_18002C11B
0x18002c0a5  mov     r8d, 243h
0x18002c0ab  mov     ecx, eax
0x18002c0ad  call    trace_MI
0x18002c0b2  jmp     loc_18002C292
0x18002c0b7  mov     rax, [rsp+140h+var_E0]
0x18002c0bc  lea     rcx, [r8+r8*2]
0x18002c0c0  mov     r9, [rsp+140h+var_100]
0x18002c0c5  lea     rdx, [rsi+rcx*8]
0x18002c0c9  mov     rcx, [rsp+140h+pllTimeStamp]
0x18002c0ce  lea     r8, [rsp+140h+var_108]
0x18002c0d3  mov     [rsp+140h+ItemBuffer], rax
0x18002c0d8  call    WrapUint64
0x18002c0dd  mov     ebx, eax
0x18002c0df  test    eax, eax
0x18002c0e1  jz      short loc_18002C11B
0x18002c0e3  mov     r8d, 24Dh
0x18002c0e9  jmp     short loc_18002C0AB
0x18002c0eb  mov     rax, [rsp+140h+var_E0]
0x18002c0f0  lea     rcx, [r8+r8*2]
0x18002c0f4  mov     r9, [rsp+140h+var_100]
0x18002c0f9  lea     rdx, [rsi+rcx*8]
0x18002c0fd  mov     rcx, [rsp+140h+pllTimeStamp]
0x18002c102  lea     r8, [rsp+140h+var_108]
0x18002c107  mov     [rsp+140h+ItemBuffer], rax
0x18002c10c  call    WrapUint32
0x18002c111  mov     ebx, eax
0x18002c113  test    eax, eax
0x18002c115  jnz     loc_18002C231
0x18002c11b  mov     rax, cs:off_180047C30
0x18002c122  mov     rcx, [rsp+140h+var_E8]
0x18002c127  mov     rax, [rax+10h]
0x18002c12b  mov     rcx, [rcx+30h]
0x18002c12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c134  mov     rcx, [rsp+140h+var_108]
0x18002c139  xorps   xmm0, xmm0
0x18002c13c  mov     rax, rcx
0x18002c13f  mov     [rbp+40h+var_A8], rcx
0x18002c143  mov     rcx, [rbp+40h+var_B0]
0x18002c147  neg     rax
0x18002c14a  mov     rax, cs:off_180047BB0
0x18002c151  xorps   xmm1, xmm1
0x18002c154  sbb     edx, edx
0x18002c156  mov     [rbp+40h+var_80], 0Fh
0x18002c15d  not     edx
0x18002c15f  mov     [rbp+40h+var_78], 0
0x18002c167  mov     rcx, [rcx]
0x18002c16a  and     edx, 20000000h
0x18002c170  mov     [rbp+40h+var_7C], edx
0x18002c173  lea     rdx, [rbp+40h+var_A8]
0x18002c177  movdqu  [rbp+40h+var_A0], xmm0
0x18002c17c  movdqu  [rbp+40h+var_90], xmm1
0x18002c181  mov     rax, [rax+20h]
0x18002c185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c18a  mov     rcx, [rsp+140h+var_108]
0x18002c18f  test    rcx, rcx
0x18002c192  jz      short loc_18002C1A5
0x18002c194  mov     rax, [rcx]
0x18002c197  test    rax, rax
0x18002c19a  jz      short loc_18002C1A5
0x18002c19c  mov     rax, [rax+10h]
0x18002c1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1a5  mov     r9d, [rsp+140h+dwItemCount]
0x18002c1aa  mov     r8d, [rsp+140h+var_F8]
0x18002c1af  mov     [rsp+140h+var_108], 0
0x18002c1b8  inc     r8d
0x18002c1bb  mov     [rsp+140h+var_F8], r8d
0x18002c1c0  cmp     r8d, r9d
0x18002c1c3  jb      loc_18002C05A
0x18002c1c9  mov     rax, [rsp+140h+var_E8]
0x18002c1ce  mov     rcx, [rbp+40h+var_B0]
0x18002c1d2  mov     rax, [rax+10h]
0x18002c1d6  mov     rcx, [rcx]
0x18002c1d9  mov     [rsp+140h+var_E8], rax
0x18002c1de  mov     rax, cs:off_180047BB0
0x18002c1e5  mov     rax, [rax+10h]
0x18002c1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1ee  mov     rax, [rsp+140h+var_E8]
0x18002c1f3  test    rax, rax
0x18002c1f6  jnz     loc_18002C029
0x18002c1fc  mov     rcx, rsi; Block
0x18002c1ff  call    cs:__imp_free
0x18002c205  mov     rcx, r13; Block
0x18002c208  call    cs:__imp_free
0x18002c20e  mov     eax, [rsp+140h+var_F4]
0x18002c212  xor     r13d, r13d
0x18002c215  inc     eax
0x18002c217  mov     [rsp+140h+var_F4], eax
0x18002c21b  cmp     eax, [r14+20h]
0x18002c21f  jb      loc_18002BEB0
0x18002c225  xor     esi, esi
0x18002c227  test    ebx, ebx
0x18002c229  jz      loc_18002C37B
0x18002c22f  jmp     short loc_18002C292
0x18002c231  mov     r8d, 248h
0x18002c237  jmp     loc_18002C0AB
0x18002c23c  mov     r8d, 22Eh
0x18002c242  mov     ecx, edi
0x18002c244  jmp     loc_18002BE8F
0x18002c249  mov     edx, 217h
0x18002c24e  call    trace_EH_Check
0x18002c253  jmp     short loc_18002C28D
0x18002c255  mov     edx, 214h
0x18002c25a  call    trace_EH_Check
0x18002c25f  jmp     short loc_18002C28B
0x18002c261  mov     r8d, 20Ch
0x18002c267  mov     ecx, eax
0x18002c269  call    trace_PDH
0x18002c26e  xor     esi, esi
0x18002c270  mov     ebx, 1
  ... truncated ...
```
