# NlpEnumerateDomainTrusts(_DOMAIN_INFO *,ulong,ulong *,_DS_DOMAIN_TRUSTSW * *)

- ea: `0x18006ad08`
- end: `0x18006b1cb`
- name: `?NlpEnumerateDomainTrusts@@YAKPEAU_DOMAIN_INFO@@KPEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z`
- size: `1219`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *, unsigned int, unsigned int *, struct _DS_DOMAIN_TRUSTSW **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18006b2e0`

## callees

- `0x180003200`
- `0x180003670`
- `0x180007278`
- `0x18001606c`
- `0x1800160a0`
- `0x18006ad08`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006ad91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006ad91`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006ad73`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006ad73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006aee8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006aee8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b195`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b195`
- `ntdll!RtlLeaveCriticalSection` at `0x18006adb0`
- `ntdll!RtlLeaveCriticalSection` at `0x18006aec0`
- `ntdll!RtlLeaveCriticalSection` at `0x18006af02`
- `ntdll!RtlLeaveCriticalSection` at `0x18006b187`
- `ntdll!RtlLeaveCriticalSection` at `0x18006b1c3`
- `ntdll!RtlLeaveCriticalSection` at `0x18006adb0`
- `ntdll!RtlLeaveCriticalSection` at `0x18006aec0`
- `ntdll!RtlLeaveCriticalSection` at `0x18006af02`
- `ntdll!RtlLeaveCriticalSection` at `0x18006b187`
- `ntdll!RtlLeaveCriticalSection` at `0x18006b1c3`
- `ntdll!RtlEnterCriticalSection` at `0x18006ad7e`
- `ntdll!RtlEnterCriticalSection` at `0x18006ad7e`
- `ntdll!RtlLengthSid` at `0x18006ae5a`
- `ntdll!RtlLengthSid` at `0x18006b018`
- `ntdll!RtlLengthSid` at `0x18006ae5a`
- `ntdll!RtlLengthSid` at `0x18006b018`
- `SAMSRV!SamIMixedDomain` at `0x18006afe3`
- `SAMSRV!SamIMixedDomain` at `0x18006afe3`

## string_xrefs

- `0x18006adb8`: `NlpEnumerateDomainTrusts: Can't get updated Domain List from cache.\n`

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
          && !(unsigned __int8)SamIMixedDomain(*((_QWORD *)a1 + 46)) )
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
        NetpULongPtrRoundUp((unsigned __int64)v29, 4, &v47);
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
0x18006ad08  mov     [rsp-40h+arg_18], r9
0x18006ad0d  mov     [rsp-40h+arg_10], r8
0x18006ad12  mov     [rsp-40h+arg_8], edx
0x18006ad16  push    rbp
0x18006ad17  push    rbx
0x18006ad18  push    rsi
0x18006ad19  push    rdi
0x18006ad1a  push    r12
0x18006ad1c  push    r13
0x18006ad1e  push    r14
0x18006ad20  push    r15
0x18006ad22  mov     rbp, rsp
0x18006ad25  sub     rsp, 78h
0x18006ad29  mov     rax, cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA; void * NlGlobalTrustInfoUpToDateEvent
0x18006ad30  lea     r13, [rcx+190h]
0x18006ad37  xor     r12d, r12d
0x18006ad3a  mov     [rbp+Handles], rax
0x18006ad3e  mov     rax, cs:?NlGlobalTerminateEvent@@3PEAXEA; void * NlGlobalTerminateEvent
0x18006ad45  mov     rsi, rcx
0x18006ad48  mov     [rbp+var_18], rax
0x18006ad4c  mov     edi, r12d
0x18006ad4f  mov     r14d, r12d
0x18006ad52  mov     [rbp+var_40], r12
0x18006ad56  mov     r15d, r12d
0x18006ad59  mov     [rbp+CriticalSection], r13
0x18006ad5d  xor     r8d, r8d; bWaitAll
0x18006ad60  mov     [rsp+78h+bAlertable], r12d; bAlertable
0x18006ad65  mov     r9d, 4E20h; dwMilliseconds
0x18006ad6b  lea     rdx, [rbp+Handles]; lpHandles
0x18006ad6f  lea     ecx, [r8+2]; nCount
0x18006ad73  call    cs:__imp_WaitForMultipleObjectsEx
0x18006ad79  mov     rcx, r13; CriticalSection
0x18006ad7c  mov     ebx, eax
0x18006ad7e  call    cs:__imp_RtlEnterCriticalSection
0x18006ad84  test    ebx, ebx
0x18006ad86  jnz     short loc_18006ADB8
0x18006ad88  mov     rcx, cs:?NlGlobalTrustInfoUpToDateEvent@@3PEAXEA; hHandle
0x18006ad8f  xor     edx, edx; dwMilliseconds
0x18006ad91  call    cs:__imp_WaitForSingleObject
0x18006ad97  dec     eax
0x18006ad99  cmp     eax, 0FFFFFFFDh
0x18006ad9c  ja      short loc_18006ADC9
0x18006ad9e  lea     rdx, aNlpenumeratedo_0; "NlpEnumerateDomainTrusts: NlGlobalTrust"...
0x18006ada5  lea     ecx, [rbx+2]; unsigned int
0x18006ada8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006adad  mov     rcx, r13; CriticalSection
0x18006adb0  call    cs:__imp_RtlLeaveCriticalSection
0x18006adb6  jmp     short loc_18006AD5D
0x18006adb8  lea     rdx, aNlpenumeratedo; "NlpEnumerateDomainTrusts: Can't get upd"...
0x18006adbf  mov     ecx, 2; unsigned int
0x18006adc4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006adc9  cmp     [rsi+1E0h], r12d
0x18006add0  jz      loc_18006B184
0x18006add6  mov     r9d, [rsi+1E4h]
0x18006addd  test    r9d, r9d
0x18006ade0  jz      loc_18006B1C0
0x18006ade6  mov     r13d, [rbp+arg_8]
0x18006adea  mov     rdx, [rsi+1D8h]
0x18006adf1  mov     eax, r15d
0x18006adf4  imul    rcx, rax, 38h ; '8'
0x18006adf8  test    [rcx+rdx+10h], r13d
0x18006adfd  jz      loc_18006AE8A
0x18006ae03  mov     r8, [rcx+rdx+8]
0x18006ae08  mov     eax, edi
0x18006ae0a  mov     [rbp+arg_0], eax
0x18006ae0d  mov     ebx, edi
0x18006ae0f  test    r8, r8
0x18006ae12  jz      short loc_18006AE2E
0x18006ae14  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006ae18  inc     rax
0x18006ae1b  cmp     [r8+rax*2], di
0x18006ae20  jnz     short loc_18006AE18
0x18006ae22  lea     eax, ds:2[rax*2]
0x18006ae29  mov     [rbp+arg_0], eax
0x18006ae2c  mov     ebx, eax
0x18006ae2e  mov     r8, [rcx+rdx]
0x18006ae32  test    r8, r8
0x18006ae35  jz      short loc_18006AE50
0x18006ae37  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006ae3b  inc     rax
0x18006ae3e  cmp     [r8+rax*2], di
0x18006ae43  jnz     short loc_18006AE3B
0x18006ae45  add     ebx, 2
0x18006ae48  lea     eax, [rbx+rax*2]
0x18006ae4b  mov     [rbp+arg_0], eax
0x18006ae4e  mov     ebx, eax
0x18006ae50  mov     rcx, [rcx+rdx+20h]; Sid
0x18006ae55  test    rcx, rcx
0x18006ae58  jz      short loc_18006AE6C
0x18006ae5a  call    cs:__imp_RtlLengthSid
0x18006ae60  mov     r9d, [rsi+1E4h]
0x18006ae67  add     eax, ebx
0x18006ae69  mov     [rbp+arg_0], eax
0x18006ae6c  lea     r8, [rbp+arg_0]; unsigned int *
0x18006ae70  mov     edx, 4; unsigned int
0x18006ae75  mov     ecx, eax; unsigned int
0x18006ae77  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x18006ae7c  mov     r8d, [rbp+arg_0]
0x18006ae80  add     r8d, 38h ; '8'
0x18006ae84  add     r12d, r8d
0x18006ae87  inc     r14d
0x18006ae8a  inc     r15d
0x18006ae8d  cmp     r15d, r9d
0x18006ae90  jb      loc_18006ADEA
0x18006ae96  lea     r13, [rsi+190h]
0x18006ae9d  test    r12d, r12d
0x18006aea0  jz      loc_18006B1BD
0x18006aea6  mov     ecx, r12d
0x18006aea9  call    NetpMemoryAllocate
0x18006aeae  xor     r12d, r12d
0x18006aeb1  mov     rdi, rax
0x18006aeb4  test    rax, rax
0x18006aeb7  jnz     short loc_18006AEC8
0x18006aeb9  mov     rcx, r13; CriticalSection
0x18006aebc  lea     r12d, [rax+8]
0x18006aec0  call    cs:__imp_RtlLeaveCriticalSection
0x18006aec6  jmp     short loc_18006AF10
0x18006aec8  mov     r8d, [rbp+arg_8]
0x18006aecc  mov     r13d, r8d
0x18006aecf  and     r13d, 1
0x18006aed3  mov     [rbp+var_48], r13d
0x18006aed7  jz      short loc_18006AF1C
0x18006aed9  mov     edx, [rsi+1E4h]
0x18006aedf  mov     ecx, 40h ; '@'; uFlags
0x18006aee4  shl     rdx, 2; uBytes
0x18006aee8  call    cs:__imp_LocalAlloc
0x18006aeee  mov     [rbp+var_40], rax
0x18006aef2  mov     rdx, rax
0x18006aef5  test    rax, rax
0x18006aef8  jnz     short loc_18006AF21
0x18006aefa  mov     rcx, [rbp+CriticalSection]; CriticalSection
0x18006aefe  lea     r12d, [rax+8]
0x18006af02  call    cs:__imp_RtlLeaveCriticalSection
0x18006af08  mov     rcx, rdi
0x18006af0b  call    NetpMemoryFree
0x18006af10  xor     eax, eax
0x18006af12  mov     edi, eax
0x18006af14  mov     r14d, eax
0x18006af17  jmp     loc_18006B19B
0x18006af1c  mov     rdx, r12
0x18006af1f  jmp     short loc_18006AF25
0x18006af21  mov     r8d, [rbp+arg_8]
0x18006af25  mov     eax, r14d
0x18006af28  mov     r14d, r12d
0x18006af2b  imul    r15, rax, 38h ; '8'
0x18006af2f  mov     eax, r12d
0x18006af32  add     r15, rdi
0x18006af35  mov     [rbp+arg_0], eax
0x18006af38  mov     [rbp+var_38], r15
0x18006af3c  cmp     [rsi+1E4h], r12d
0x18006af43  jbe     loc_18006B128
0x18006af49  mov     r12d, 8
0x18006af4f  mov     ecx, eax
0x18006af51  mov     rax, [rsi+1D8h]
0x18006af58  imul    rbx, rcx, 38h ; '8'
0x18006af5c  mov     [rbp+var_28], rbx
0x18006af60  test    [rbx+rax+10h], r8d
0x18006af65  jz      loc_18006B10D
0x18006af6b  test    r13d, r13d
0x18006af6e  jz      short loc_18006AF74
0x18006af70  mov     [rdx+rcx*4], r14d
0x18006af74  mov     eax, r14d
0x18006af77  imul    r13, rax, 38h ; '8'
0x18006af7b  mov     rax, [rsi+1D8h]
0x18006af82  mov     ecx, [rbx+rax+10h]
0x18006af86  mov     [rdi+r13+10h], ecx
0x18006af8b  mov     rax, [rsi+1D8h]
0x18006af92  mov     ecx, [rbx+rax+14h]
0x18006af96  mov     [rdi+r13+14h], ecx
0x18006af9b  mov     rax, [rsi+1D8h]
0x18006afa2  mov     ecx, [rbx+rax+18h]
0x18006afa6  mov     [rdi+r13+18h], ecx
0x18006afab  mov     rax, [rsi+1D8h]
0x18006afb2  mov     ecx, [rbx+rax+1Ch]
0x18006afb6  mov     [rdi+r13+1Ch], ecx
0x18006afbb  mov     rax, [rsi+1D8h]
0x18006afc2  movups  xmm0, xmmword ptr [rbx+rax+28h]
0x18006afc7  movdqu  xmmword ptr [rdi+r13+28h], xmm0
0x18006afce  mov     rax, [rsi+1D8h]
0x18006afd5  test    [rbx+rax+10h], r12b
0x18006afda  jz      short loc_18006AFF7
0x18006afdc  mov     rcx, [rsi+170h]
0x18006afe3  call    cs:__imp_SamIMixedDomain
0x18006afe9  xor     ecx, ecx
0x18006afeb  test    al, al
0x18006afed  jnz     short loc_18006AFF9
0x18006afef  or      dword ptr [rdi+r13+10h], 10h
0x18006aff5  jmp     short loc_18006AFF9
0x18006aff7  xor     ecx, ecx
0x18006aff9  mov     rax, [rsi+1D8h]
0x18006b000  cmp     [rbx+rax+20h], rcx
0x18006b005  jz      short loc_18006B04A
0x18006b007  mov     [rdi+r13+20h], r15
0x18006b00c  mov     rcx, [rsi+1D8h]
0x18006b013  mov     rcx, [rbx+rcx+20h]; Sid
0x18006b018  call    cs:__imp_RtlLengthSid
0x18006b01e  mov     rdx, [rsi+1D8h]
0x18006b025  mov     rcx, r15; void *
0x18006b028  mov     ebx, eax
0x18006b02a  mov     r8d, eax; Size
0x18006b02d  mov     rax, [rbp+var_28]
0x18006b031  mov     rdx, [rax+rdx+20h]; Src
0x18006b036  call    memcpy_0
0x18006b03b  add     r15, rbx
0x18006b03e  mov     rbx, [rbp+var_28]
0x18006b042  mov     [rbp+var_38], r15
0x18006b046  xor     ecx, ecx
0x18006b048  jmp     short loc_18006B04F
0x18006b04a  mov     [rdi+r13+20h], rcx
0x18006b04f  mov     rax, [rsi+1D8h]
0x18006b056  cmp     [rbx+rax], rcx
0x18006b05a  jz      short loc_18006B09B
0x18006b05c  mov     [rdi+r13], r15
0x18006b060  mov     rax, [rsi+1D8h]
0x18006b067  mov     rdx, [rbx+rax]; Src
0x18006b06b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006b06f  inc     rax
0x18006b072  cmp     [rdx+rax*2], cx
0x18006b076  jnz     short loc_18006B06F
0x18006b078  lea     eax, ds:2[rax*2]
0x18006b07f  mov     rcx, r15; void *
0x18006b082  mov     r8d, eax; Size
0x18006b085  mov     ebx, eax
0x18006b087  call    memcpy_0
0x18006b08c  add     r15, rbx
0x18006b08f  mov     rbx, [rbp+var_28]
0x18006b093  mov     [rbp+var_38], r15
0x18006b097  xor     ecx, ecx
0x18006b099  jmp     short loc_18006B09F
0x18006b09b  mov     [rdi+r13], rcx
0x18006b09f  mov     rax, [rsi+1D8h]
0x18006b0a6  cmp     [rbx+rax+8], rcx
0x18006b0ab  jz      short loc_18006B0E8
0x18006b0ad  mov     [rdi+r13+8], r15
0x18006b0b2  mov     rax, [rsi+1D8h]
0x18006b0b9  mov     rdx, [rbx+rax+8]; Src
0x18006b0be  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006b0c2  inc     rax
0x18006b0c5  cmp     [rdx+rax*2], cx
0x18006b0c9  jnz     short loc_18006B0C2
0x18006b0cb  lea     eax, ds:2[rax*2]
0x18006b0d2  mov     rcx, r15; void *
0x18006b0d5  mov     r8d, eax; Size
0x18006b0d8  mov     ebx, eax
0x18006b0da  call    memcpy_0
0x18006b0df  add     r15, rbx
0x18006b0e2  mov     [rbp+var_38], r15
0x18006b0e6  jmp     short loc_18006B0ED
0x18006b0e8  mov     [rdi+r13+8], rcx
0x18006b0ed  lea     r8, [rbp+var_38]; unsigned __int64 *
0x18006b0f1  mov     edx, 4; unsigned __int64
0x18006b0f6  mov     rcx, r15; unsigned __int64
0x18006b0f9  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006b0fe  mov     r15, [rbp+var_38]
0x18006b102  inc     r14d
0x18006b105  mov     r13d, [rbp+var_48]
0x18006b109  mov     r8d, [rbp+arg_8]
0x18006b10d  mov     eax, [rbp+arg_0]
0x18006b110  mov     rdx, [rbp+var_40]
0x18006b114  inc     eax
0x18006b116  mov     [rbp+arg_0], eax
0x18006b119  cmp     eax, [rsi+1E4h]
0x18006b11f  jb      loc_18006AF4F
0x18006b125  xor     r12d, r12d
0x18006b128  mov     edx, r12d
0x18006b12b  test    r13d, r13d
0x18006b12e  jz      short loc_18006B165
0x18006b130  mov     r15, [rbp+var_40]
0x18006b134  test    r14d, r14d
0x18006b137  jz      short loc_18006B180
0x18006b139  mov     r8, r12
0x18006b13c  imul    r9, r8, 38h ; '8'
0x18006b140  mov     eax, [r9+rdi+10h]
0x18006b145  and     al, 5
0x18006b147  cmp     al, 1
0x18006b149  jnz     short loc_18006B159
0x18006b14b  mov     eax, [r9+rdi+14h]
0x18006b150  mov     ecx, [r15+rax*4]
0x18006b154  mov     [r9+rdi+14h], ecx
0x18006b159  inc     edx
0x18006b15b  inc     r8
0x18006b15e  cmp     edx, r14d
0x18006b161  jb      short loc_18006B13C
0x18006b163  jmp     short loc_18006B180
0x18006b165  test    r14d, r14d
0x18006b168  jz      short loc_18006B17C
0x18006b16a  mov     eax, edx
0x18006b16c  inc     edx
0x18006b16e  imul    rcx, rax, 38h ; '8'
0x18006b172  mov     [rcx+rdi+14h], r12d
0x18006b177  cmp     edx, r14d
0x18006b17a  jb      short loc_18006B16A
0x18006b17c  mov     r15, [rbp+var_40]
0x18006b180  mov     r13, [rbp+CriticalSection]
0x18006b184  mov     rcx, r13; CriticalSection
0x18006b187  call    cs:__imp_RtlLeaveCriticalSection
0x18006b18d  test    r15, r15
0x18006b190  jz      short loc_18006B19B
0x18006b192  mov     rcx, r15; hMem
0x18006b195  call    cs:__imp_LocalFree
  ... truncated ...
```
