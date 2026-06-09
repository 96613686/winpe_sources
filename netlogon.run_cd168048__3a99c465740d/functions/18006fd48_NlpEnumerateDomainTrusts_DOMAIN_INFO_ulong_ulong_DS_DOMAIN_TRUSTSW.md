# NlpEnumerateDomainTrusts(_DOMAIN_INFO *,ulong,ulong *,_DS_DOMAIN_TRUSTSW * *)

- ea: `0x18006fd48`
- end: `0x18007025a`
- name: `?NlpEnumerateDomainTrusts@@YAKPEAU_DOMAIN_INFO@@KPEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z`
- size: `1298`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, unsigned int, unsigned int *, struct _DS_DOMAIN_TRUSTSW **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180070380`

## callees

- `0x180003320`
- `0x1800037f0`
- `0x180007518`
- `0x180016a70`
- `0x180016aa4`
- `0x18006fd48`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006fddd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006fddd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006fdb3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006fdb3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ff4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ff4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070217`
- `ntdll!RtlLeaveCriticalSection` at `0x18006fe02`
- `ntdll!RtlLeaveCriticalSection` at `0x18006ff1e`
- `ntdll!RtlLeaveCriticalSection` at `0x18006ff6c`
- `ntdll!RtlLeaveCriticalSection` at `0x180070203`
- `ntdll!RtlLeaveCriticalSection` at `0x18007024c`
- `ntdll!RtlLeaveCriticalSection` at `0x18006fe02`
- `ntdll!RtlLeaveCriticalSection` at `0x18006ff1e`
- `ntdll!RtlLeaveCriticalSection` at `0x18006ff6c`
- `ntdll!RtlLeaveCriticalSection` at `0x180070203`
- `ntdll!RtlLeaveCriticalSection` at `0x18007024c`
- `ntdll!RtlEnterCriticalSection` at `0x18006fdc4`
- `ntdll!RtlEnterCriticalSection` at `0x18006fdc4`
- `ntdll!RtlLengthSid` at `0x18006feb2`
- `ntdll!RtlLengthSid` at `0x18007008e`
- `ntdll!RtlLengthSid` at `0x18006feb2`
- `ntdll!RtlLengthSid` at `0x18007008e`
- `SAMSRV!SamIMixedDomain` at `0x180070053`
- `SAMSRV!SamIMixedDomain` at `0x180070053`

## string_xrefs

- `0x18006fe10`: `NlpEnumerateDomainTrusts: Can't get updated Domain List from cache.\n`

## pseudocode

```c
__int64 __fastcall NlpEnumerateDomainTrusts(
        struct _DOMAIN_INFO *a1,
        int a2,
        unsigned int *a3,
        struct _DS_DOMAIN_TRUSTSW **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r13
  unsigned int v5; // r12d
  struct _DS_DOMAIN_TRUSTSW *v7; // rdi
  unsigned int v8; // r14d
  void *v9; // r15
  DWORD v10; // ebx
  unsigned int v11; // r9d
  int v12; // r13d
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rax
  void *v21; // rcx
  __int64 v22; // rax
  int v23; // r8d
  int v24; // r13d
  _DWORD *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // r15
  unsigned int v28; // eax
  struct _DS_DOMAIN_TRUSTSW *v29; // r15
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rbx
  __int64 v33; // r13
  size_t v34; // rbx
  _WORD *v35; // rdx
  __int64 v36; // rax
  size_t v37; // rbx
  _WORD *v38; // rdx
  __int64 v39; // rax
  size_t v40; // rbx
  unsigned int v41; // edx
  __int64 v42; // r8
  __int64 v43; // rax
  int v45; // [rsp+30h] [rbp-48h]
  _DWORD *v46; // [rsp+38h] [rbp-40h]
  unsigned __int64 v47; // [rsp+40h] [rbp-38h] BYREF
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+48h] [rbp-30h]
  __int64 v49; // [rsp+50h] [rbp-28h]
  HANDLE Handles[4]; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v51; // [rsp+C0h] [rbp+48h] BYREF
  int v52; // [rsp+C8h] [rbp+50h]
  unsigned int *v53; // [rsp+D0h] [rbp+58h]
  struct _DS_DOMAIN_TRUSTSW **v54; // [rsp+D8h] [rbp+60h]

  v54 = a4;
  v53 = a3;
  v52 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 400);
  v5 = 0;
  Handles[0] = NlGlobalTrustInfoUpToDateEvent;
  Handles[1] = NlGlobalTerminateEvent;
  v7 = 0;
  v8 = 0;
  v46 = 0;
  v9 = 0;
  CriticalSection = (PRTL_CRITICAL_SECTION)((char *)a1 + 400);
  while ( 1 )
  {
    v10 = WaitForMultipleObjectsEx(2u, Handles, 0, 0x4E20u, 0);
    RtlEnterCriticalSection(v4);
    if ( v10 )
      break;
    if ( WaitForSingleObject(NlGlobalTrustInfoUpToDateEvent, 0) - 1 > 0xFFFFFFFD )
      goto LABEL_6;
    NlPrintRoutine(2u, L"NlpEnumerateDomainTrusts: NlGlobalTrustInfoUpToDateEvent has been reset.\n");
    RtlLeaveCriticalSection(v4);
  }
  NlPrintRoutine(2u, L"NlpEnumerateDomainTrusts: Can't get updated Domain List from cache.\n");
LABEL_6:
  if ( !*((_DWORD *)a1 + 120) )
    goto LABEL_65;
  v11 = *((_DWORD *)a1 + 121);
  if ( !v11 )
  {
LABEL_69:
    RtlLeaveCriticalSection(v4);
    goto LABEL_67;
  }
  v12 = v52;
  do
  {
    v13 = *((_QWORD *)a1 + 59);
    v14 = 56LL * (unsigned int)v9;
    if ( (v12 & *(_DWORD *)(v14 + v13 + 16)) != 0 )
    {
      v15 = *(_QWORD *)(v14 + v13 + 8);
      v16 = 0;
      v51 = 0;
      v17 = 0;
      if ( v15 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(v15 + 2 * v18) );
        v16 = 2 * v18 + 2;
        v51 = v16;
        v17 = v16;
      }
      v19 = *(_QWORD *)(v14 + v13);
      if ( v19 )
      {
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)(v19 + 2 * v20) );
        v16 = v17 + 2 + 2 * v20;
        v51 = v16;
        v17 = v16;
      }
      v21 = *(void **)(v14 + v13 + 32);
      if ( v21 )
      {
        v16 = v17 + RtlLengthSid(v21);
        v51 = v16;
      }
      NetpULongRoundUp(v16, 4u, &v51);
      v5 += v51 + 56;
      ++v8;
    }
    LODWORD(v9) = (_DWORD)v9 + 1;
  }
  while ( (unsigned int)v9 < v11 );
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 400);
  if ( !v5 )
  {
    v5 = 0;
    goto LABEL_69;
  }
  v22 = NetpMemoryAllocate(v5);
  v5 = 0;
  v7 = (struct _DS_DOMAIN_TRUSTSW *)v22;
  if ( !v22 )
  {
    v5 = 8;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 10);
LABEL_28:
    v7 = 0;
    v8 = 0;
    goto LABEL_67;
  }
  v23 = v52;
  v24 = v52 & 1;
  v45 = v24;
  if ( (v52 & 1) != 0 )
  {
    v46 = LocalAlloc(0x40u, 4LL * *((unsigned int *)a1 + 121));
    v25 = v46;
    if ( !v46 )
    {
      v5 = 8;
      RtlLeaveCriticalSection(CriticalSection);
      NetpMemoryFree(v7);
      goto LABEL_28;
    }
    v23 = v52;
  }
  else
  {
    v25 = 0;
  }
  v26 = v8;
  v8 = 0;
  v27 = v26;
  v28 = 0;
  v29 = &v7[v27];
  v51 = 0;
  v47 = (unsigned __int64)v29;
  if ( *((_DWORD *)a1 + 121) )
  {
    do
    {
      v30 = v28;
      v31 = *((_QWORD *)a1 + 59);
      v32 = 56 * v30;
      v49 = 56 * v30;
      if ( (v23 & *(_DWORD *)(56 * v30 + v31 + 16)) != 0 )
      {
        if ( v24 )
          v25[v30] = v8;
        v33 = v8;
        v7[v33].Flags = *(_DWORD *)(v32 + *((_QWORD *)a1 + 59) + 16);
        v7[v33].ParentIndex = *(_DWORD *)(v32 + *((_QWORD *)a1 + 59) + 20);
        v7[v33].TrustType = *(_DWORD *)(v32 + *((_QWORD *)a1 + 59) + 24);
        v7[v33].TrustAttributes = *(_DWORD *)(v32 + *((_QWORD *)a1 + 59) + 28);
        v7[v33].DomainGuid = *(GUID *)(v32 + *((_QWORD *)a1 + 59) + 40);
        if ( (*(_BYTE *)(v32 + *((_QWORD *)a1 + 59) + 16) & 8) != 0
          && !(unsigned __int8)SamIMixedDomain(*((_QWORD *)a1 + 46), v25) )
        {
          v7[v33].Flags |= 0x10u;
        }
        if ( *(_QWORD *)(v32 + *((_QWORD *)a1 + 59) + 32) )
        {
          v7[v33].DomainSid = v29;
          v34 = RtlLengthSid(*(PSID *)(v32 + *((_QWORD *)a1 + 59) + 32));
          memcpy_0(v29, *(const void **)(v49 + *((_QWORD *)a1 + 59) + 32), v34);
          v29 = (struct _DS_DOMAIN_TRUSTSW *)((char *)v29 + v34);
          v32 = v49;
          v47 = (unsigned __int64)v29;
        }
        else
        {
          v7[v33].DomainSid = 0;
        }
        if ( *(_QWORD *)(v32 + *((_QWORD *)a1 + 59)) )
        {
          v7[v8].NetbiosDomainName = (LPWSTR)v29;
          v35 = *(_WORD **)(v32 + *((_QWORD *)a1 + 59));
          v36 = -1;
          do
            ++v36;
          while ( v35[v36] );
          v37 = (unsigned int)(2 * v36 + 2);
          memcpy_0(v29, v35, v37);
          v29 = (struct _DS_DOMAIN_TRUSTSW *)((char *)v29 + v37);
          v32 = v49;
          v47 = (unsigned __int64)v29;
        }
        else
        {
          v7[v8].NetbiosDomainName = 0;
        }
        if ( *(_QWORD *)(v32 + *((_QWORD *)a1 + 59) + 8) )
        {
          v7[v33].DnsDomainName = (LPWSTR)v29;
          v38 = *(_WORD **)(v32 + *((_QWORD *)a1 + 59) + 8);
          v39 = -1;
          do
            ++v39;
          while ( v38[v39] );
          v40 = (unsigned int)(2 * v39 + 2);
          memcpy_0(v29, v38, v40);
          v29 = (struct _DS_DOMAIN_TRUSTSW *)((char *)v29 + v40);
          v47 = (unsigned __int64)v29;
        }
        else
        {
          v7[v33].DnsDomainName = 0;
        }
        NetpULongPtrRoundUp((unsigned __int64)v29, 4u, &v47);
        v29 = (struct _DS_DOMAIN_TRUSTSW *)v47;
        ++v8;
        v24 = v45;
        v23 = v52;
      }
      v25 = v46;
      v28 = v51 + 1;
      v51 = v28;
    }
    while ( v28 < *((_DWORD *)a1 + 121) );
    v5 = 0;
  }
  v41 = 0;
  if ( v24 )
  {
    v9 = v46;
    if ( v8 )
    {
      v42 = 0;
      do
      {
        if ( (v7[v42].Flags & 5) == 1 )
          v7[v42].ParentIndex = v46[v7[v42].ParentIndex];
        ++v41;
        ++v42;
      }
      while ( v41 < v8 );
    }
  }
  else
  {
    if ( v8 )
    {
      do
      {
        v43 = v41++;
        v7[v43].ParentIndex = 0;
      }
      while ( v41 < v8 );
    }
    v9 = v46;
  }
  v4 = CriticalSection;
LABEL_65:
  RtlLeaveCriticalSection(v4);
  if ( v9 )
    LocalFree(v9);
LABEL_67:
  *v53 = v8;
  *v54 = v7;
  return v5;
}

```

## disassembly

```asm
0x18006fd48  mov     [rsp-40h+arg_18], r9
0x18006fd4d  mov     [rsp-40h+arg_10], r8
0x18006fd52  mov     [rsp-40h+arg_8], edx
0x18006fd56  push    rbp
0x18006fd57  push    rbx
0x18006fd58  push    rsi
0x18006fd59  push    rdi
0x18006fd5a  push    r12
0x18006fd5c  push    r13
0x18006fd5e  push    r14
0x18006fd60  push    r15
0x18006fd62  mov     rbp, rsp
0x18006fd65  sub     rsp, 78h
0x18006fd69  mov     rax, cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA; void * NlGlobalTrustInfoUpToDateEvent
0x18006fd70  lea     r13, [rcx+190h]
0x18006fd77  xor     r12d, r12d
0x18006fd7a  mov     [rbp+Handles], rax
0x18006fd7e  mov     rax, cs:?NlGlobalTerminateEvent@@3PEAXEA; void * NlGlobalTerminateEvent
0x18006fd85  mov     rsi, rcx
0x18006fd88  mov     [rbp+var_18], rax
0x18006fd8c  mov     edi, r12d
0x18006fd8f  mov     r14d, r12d
0x18006fd92  mov     [rbp+var_40], r12
0x18006fd96  mov     r15d, r12d
0x18006fd99  mov     [rbp+CriticalSection], r13
0x18006fd9d  xor     r8d, r8d; bWaitAll
0x18006fda0  mov     [rsp+78h+bAlertable], r12d; bAlertable
0x18006fda5  mov     r9d, 4E20h; dwMilliseconds
0x18006fdab  lea     rdx, [rbp+Handles]; lpHandles
0x18006fdaf  lea     ecx, [r8+2]; nCount
0x18006fdb3  call    cs:__imp_WaitForMultipleObjectsEx
0x18006fdba  nop     dword ptr [rax+rax+00h]
0x18006fdbf  mov     rcx, r13; CriticalSection
0x18006fdc2  mov     ebx, eax
0x18006fdc4  call    cs:__imp_RtlEnterCriticalSection
0x18006fdcb  nop     dword ptr [rax+rax+00h]
0x18006fdd0  test    ebx, ebx
0x18006fdd2  jnz     short loc_18006FE10
0x18006fdd4  mov     rcx, cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA; hHandle
0x18006fddb  xor     edx, edx; dwMilliseconds
0x18006fddd  call    cs:__imp_WaitForSingleObject
0x18006fde4  nop     dword ptr [rax+rax+00h]
0x18006fde9  dec     eax
0x18006fdeb  cmp     eax, 0FFFFFFFDh
0x18006fdee  ja      short loc_18006FE21
0x18006fdf0  lea     rdx, aNlpenumeratedo_0; "NlpEnumerateDomainTrusts: NlGlobalTrust"...
0x18006fdf7  lea     ecx, [rbx+2]; unsigned int
0x18006fdfa  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006fdff  mov     rcx, r13; CriticalSection
0x18006fe02  call    cs:__imp_RtlLeaveCriticalSection
0x18006fe09  nop     dword ptr [rax+rax+00h]
0x18006fe0e  jmp     short loc_18006FD9D
0x18006fe10  lea     rdx, aNlpenumeratedo; "NlpEnumerateDomainTrusts: Can't get upd"...
0x18006fe17  mov     ecx, 2; unsigned int
0x18006fe1c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006fe21  cmp     [rsi+1E0h], r12d
0x18006fe28  jz      loc_180070200
0x18006fe2e  mov     r9d, [rsi+1E4h]
0x18006fe35  test    r9d, r9d
0x18006fe38  jz      loc_180070249
0x18006fe3e  mov     r13d, [rbp+arg_8]
0x18006fe42  mov     rdx, [rsi+1D8h]
0x18006fe49  mov     eax, r15d
0x18006fe4c  imul    rcx, rax, 38h ; '8'
0x18006fe50  test    [rcx+rdx+10h], r13d
0x18006fe55  jz      loc_18006FEE8
0x18006fe5b  mov     r8, [rcx+rdx+8]
0x18006fe60  mov     eax, edi
0x18006fe62  mov     [rbp+arg_0], eax
0x18006fe65  mov     ebx, edi
0x18006fe67  test    r8, r8
0x18006fe6a  jz      short loc_18006FE86
0x18006fe6c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006fe70  inc     rax
0x18006fe73  cmp     [r8+rax*2], di
0x18006fe78  jnz     short loc_18006FE70
0x18006fe7a  lea     eax, ds:2[rax*2]
0x18006fe81  mov     [rbp+arg_0], eax
0x18006fe84  mov     ebx, eax
0x18006fe86  mov     r8, [rcx+rdx]
0x18006fe8a  test    r8, r8
0x18006fe8d  jz      short loc_18006FEA8
0x18006fe8f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006fe93  inc     rax
0x18006fe96  cmp     [r8+rax*2], di
0x18006fe9b  jnz     short loc_18006FE93
0x18006fe9d  add     ebx, 2
0x18006fea0  lea     eax, [rbx+rax*2]
0x18006fea3  mov     [rbp+arg_0], eax
0x18006fea6  mov     ebx, eax
0x18006fea8  mov     rcx, [rcx+rdx+20h]; Sid
0x18006fead  test    rcx, rcx
0x18006feb0  jz      short loc_18006FECA
0x18006feb2  call    cs:__imp_RtlLengthSid
0x18006feb9  nop     dword ptr [rax+rax+00h]
0x18006febe  mov     r9d, [rsi+1E4h]
0x18006fec5  add     eax, ebx
0x18006fec7  mov     [rbp+arg_0], eax
0x18006feca  lea     r8, [rbp+arg_0]; unsigned int *
0x18006fece  mov     edx, 4; unsigned int
0x18006fed3  mov     ecx, eax; unsigned int
0x18006fed5  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x18006feda  mov     r8d, [rbp+arg_0]
0x18006fede  add     r8d, 38h ; '8'
0x18006fee2  add     r12d, r8d
0x18006fee5  inc     r14d
0x18006fee8  inc     r15d
0x18006feeb  cmp     r15d, r9d
0x18006feee  jb      loc_18006FE42
0x18006fef4  lea     r13, [rsi+190h]
0x18006fefb  test    r12d, r12d
0x18006fefe  jz      loc_180070246
0x18006ff04  mov     ecx, r12d
0x18006ff07  call    NetpMemoryAllocate
0x18006ff0c  xor     r12d, r12d
0x18006ff0f  mov     rdi, rax
0x18006ff12  test    rax, rax
0x18006ff15  jnz     short loc_18006FF2C
0x18006ff17  mov     rcx, r13; CriticalSection
0x18006ff1a  lea     r12d, [rax+8]
0x18006ff1e  call    cs:__imp_RtlLeaveCriticalSection
0x18006ff25  nop     dword ptr [rax+rax+00h]
0x18006ff2a  jmp     short loc_18006FF80
0x18006ff2c  mov     r8d, [rbp+arg_8]
0x18006ff30  mov     r13d, r8d
0x18006ff33  and     r13d, 1
0x18006ff37  mov     [rbp+var_48], r13d
0x18006ff3b  jz      short loc_18006FF8C
0x18006ff3d  mov     edx, [rsi+1E4h]
0x18006ff43  mov     ecx, 40h ; '@'; uFlags
0x18006ff48  shl     rdx, 2; uBytes
0x18006ff4c  call    cs:__imp_LocalAlloc
0x18006ff53  nop     dword ptr [rax+rax+00h]
0x18006ff58  mov     [rbp+var_40], rax
0x18006ff5c  mov     rdx, rax
0x18006ff5f  test    rax, rax
0x18006ff62  jnz     short loc_18006FF91
0x18006ff64  mov     rcx, [rbp+CriticalSection]; CriticalSection
0x18006ff68  lea     r12d, [rax+8]
0x18006ff6c  call    cs:__imp_RtlLeaveCriticalSection
0x18006ff73  nop     dword ptr [rax+rax+00h]
0x18006ff78  mov     rcx, rdi
0x18006ff7b  call    NetpMemoryFree
0x18006ff80  xor     eax, eax
0x18006ff82  mov     edi, eax
0x18006ff84  mov     r14d, eax
0x18006ff87  jmp     loc_180070223
0x18006ff8c  mov     rdx, r12
0x18006ff8f  jmp     short loc_18006FF95
0x18006ff91  mov     r8d, [rbp+arg_8]
0x18006ff95  mov     eax, r14d
0x18006ff98  mov     r14d, r12d
0x18006ff9b  imul    r15, rax, 38h ; '8'
0x18006ff9f  mov     eax, r12d
0x18006ffa2  add     r15, rdi
0x18006ffa5  mov     [rbp+arg_0], eax
0x18006ffa8  mov     [rbp+var_38], r15
0x18006ffac  cmp     [rsi+1E4h], r12d
0x18006ffb3  jbe     loc_1800701A4
0x18006ffb9  mov     r12d, 8
0x18006ffbf  mov     ecx, eax
0x18006ffc1  mov     rax, [rsi+1D8h]
0x18006ffc8  imul    rbx, rcx, 38h ; '8'
0x18006ffcc  mov     [rbp+var_28], rbx
0x18006ffd0  test    [rbx+rax+10h], r8d
0x18006ffd5  jz      loc_180070189
0x18006ffdb  test    r13d, r13d
0x18006ffde  jz      short loc_18006FFE4
0x18006ffe0  mov     [rdx+rcx*4], r14d
0x18006ffe4  mov     eax, r14d
0x18006ffe7  imul    r13, rax, 38h ; '8'
0x18006ffeb  mov     rax, [rsi+1D8h]
0x18006fff2  mov     ecx, [rbx+rax+10h]
0x18006fff6  mov     [rdi+r13+10h], ecx
0x18006fffb  mov     rax, [rsi+1D8h]
0x180070002  mov     ecx, [rbx+rax+14h]
0x180070006  mov     [rdi+r13+14h], ecx
0x18007000b  mov     rax, [rsi+1D8h]
0x180070012  mov     ecx, [rbx+rax+18h]
0x180070016  mov     [rdi+r13+18h], ecx
0x18007001b  mov     rax, [rsi+1D8h]
0x180070022  mov     ecx, [rbx+rax+1Ch]
0x180070026  mov     [rdi+r13+1Ch], ecx
0x18007002b  mov     rax, [rsi+1D8h]
0x180070032  movups  xmm0, xmmword ptr [rbx+rax+28h]
0x180070037  movdqu  xmmword ptr [rdi+r13+28h], xmm0
0x18007003e  mov     rax, [rsi+1D8h]
0x180070045  test    [rbx+rax+10h], r12b
0x18007004a  jz      short loc_18007006D
0x18007004c  mov     rcx, [rsi+170h]
0x180070053  call    cs:__imp_SamIMixedDomain
0x18007005a  nop     dword ptr [rax+rax+00h]
0x18007005f  xor     ecx, ecx
0x180070061  test    al, al
0x180070063  jnz     short loc_18007006F
0x180070065  or      dword ptr [rdi+r13+10h], 10h
0x18007006b  jmp     short loc_18007006F
0x18007006d  xor     ecx, ecx
0x18007006f  mov     rax, [rsi+1D8h]
0x180070076  cmp     [rbx+rax+20h], rcx
0x18007007b  jz      short loc_1800700C6
0x18007007d  mov     [rdi+r13+20h], r15
0x180070082  mov     rcx, [rsi+1D8h]
0x180070089  mov     rcx, [rbx+rcx+20h]; Sid
0x18007008e  call    cs:__imp_RtlLengthSid
0x180070095  nop     dword ptr [rax+rax+00h]
0x18007009a  mov     rdx, [rsi+1D8h]
0x1800700a1  mov     rcx, r15; void *
0x1800700a4  mov     ebx, eax
0x1800700a6  mov     r8d, eax; Size
0x1800700a9  mov     rax, [rbp+var_28]
0x1800700ad  mov     rdx, [rax+rdx+20h]; Src
0x1800700b2  call    memcpy_0
0x1800700b7  add     r15, rbx
0x1800700ba  mov     rbx, [rbp+var_28]
0x1800700be  mov     [rbp+var_38], r15
0x1800700c2  xor     ecx, ecx
0x1800700c4  jmp     short loc_1800700CB
0x1800700c6  mov     [rdi+r13+20h], rcx
0x1800700cb  mov     rax, [rsi+1D8h]
0x1800700d2  cmp     [rbx+rax], rcx
0x1800700d6  jz      short loc_180070117
0x1800700d8  mov     [rdi+r13], r15
0x1800700dc  mov     rax, [rsi+1D8h]
0x1800700e3  mov     rdx, [rbx+rax]; Src
0x1800700e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800700eb  inc     rax
0x1800700ee  cmp     [rdx+rax*2], cx
0x1800700f2  jnz     short loc_1800700EB
0x1800700f4  lea     eax, ds:2[rax*2]
0x1800700fb  mov     rcx, r15; void *
0x1800700fe  mov     r8d, eax; Size
0x180070101  mov     ebx, eax
0x180070103  call    memcpy_0
0x180070108  add     r15, rbx
0x18007010b  mov     rbx, [rbp+var_28]
0x18007010f  mov     [rbp+var_38], r15
0x180070113  xor     ecx, ecx
0x180070115  jmp     short loc_18007011B
0x180070117  mov     [rdi+r13], rcx
0x18007011b  mov     rax, [rsi+1D8h]
0x180070122  cmp     [rbx+rax+8], rcx
0x180070127  jz      short loc_180070164
0x180070129  mov     [rdi+r13+8], r15
0x18007012e  mov     rax, [rsi+1D8h]
0x180070135  mov     rdx, [rbx+rax+8]; Src
0x18007013a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007013e  inc     rax
0x180070141  cmp     [rdx+rax*2], cx
0x180070145  jnz     short loc_18007013E
0x180070147  lea     eax, ds:2[rax*2]
0x18007014e  mov     rcx, r15; void *
0x180070151  mov     r8d, eax; Size
0x180070154  mov     ebx, eax
0x180070156  call    memcpy_0
0x18007015b  add     r15, rbx
0x18007015e  mov     [rbp+var_38], r15
0x180070162  jmp     short loc_180070169
0x180070164  mov     [rdi+r13+8], rcx
0x180070169  lea     r8, [rbp+var_38]; unsigned __int64 *
0x18007016d  mov     edx, 4; unsigned __int64
0x180070172  mov     rcx, r15; unsigned __int64
0x180070175  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007017a  mov     r15, [rbp+var_38]
0x18007017e  inc     r14d
0x180070181  mov     r13d, [rbp+var_48]
0x180070185  mov     r8d, [rbp+arg_8]
0x180070189  mov     eax, [rbp+arg_0]
0x18007018c  mov     rdx, [rbp+var_40]
0x180070190  inc     eax
0x180070192  mov     [rbp+arg_0], eax
0x180070195  cmp     eax, [rsi+1E4h]
0x18007019b  jb      loc_18006FFBF
0x1800701a1  xor     r12d, r12d
0x1800701a4  mov     edx, r12d
0x1800701a7  test    r13d, r13d
0x1800701aa  jz      short loc_1800701E1
0x1800701ac  mov     r15, [rbp+var_40]
0x1800701b0  test    r14d, r14d
0x1800701b3  jz      short loc_1800701FC
0x1800701b5  mov     r8, r12
0x1800701b8  imul    r9, r8, 38h ; '8'
0x1800701bc  mov     eax, [r9+rdi+10h]
0x1800701c1  and     al, 5
0x1800701c3  cmp     al, 1
0x1800701c5  jnz     short loc_1800701D5
0x1800701c7  mov     eax, [r9+rdi+14h]
0x1800701cc  mov     ecx, [r15+rax*4]
0x1800701d0  mov     [r9+rdi+14h], ecx
0x1800701d5  inc     edx
0x1800701d7  inc     r8
0x1800701da  cmp     edx, r14d
0x1800701dd  jb      short loc_1800701B8
0x1800701df  jmp     short loc_1800701FC
0x1800701e1  test    r14d, r14d
0x1800701e4  jz      short loc_1800701F8
0x1800701e6  mov     eax, edx
0x1800701e8  inc     edx
0x1800701ea  imul    rcx, rax, 38h ; '8'
0x1800701ee  mov     [rcx+rdi+14h], r12d
  ... truncated ...
```
