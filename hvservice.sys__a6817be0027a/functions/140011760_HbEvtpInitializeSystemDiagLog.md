# HbEvtpInitializeSystemDiagLog

- ea: `0x140011760`
- end: `0x140011e12`
- name: `HbEvtpInitializeSystemDiagLog`
- size: `1714`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400115a0`

## callees

- `0x140001230`
- `0x140001600`
- `0x140002f00`
- `0x14000e61c`
- `0x140011178`
- `0x140011760`
- `0x140012abc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140011827`
- `ntoskrnl!ExAllocatePool2` at `0x140011858`
- `ntoskrnl!ExAllocatePool2` at `0x14001187c`
- `ntoskrnl!ExAllocatePool2` at `0x1400118eb`
- `ntoskrnl!ExAllocatePool2` at `0x140011a09`
- `ntoskrnl!ExAllocatePool2` at `0x140011b4f`
- `ntoskrnl!ExAllocatePool2` at `0x140011827`
- `ntoskrnl!ExAllocatePool2` at `0x140011858`
- `ntoskrnl!ExAllocatePool2` at `0x14001187c`
- `ntoskrnl!ExAllocatePool2` at `0x1400118eb`
- `ntoskrnl!ExAllocatePool2` at `0x140011a09`
- `ntoskrnl!ExAllocatePool2` at `0x140011b4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011ca6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011cc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011db8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011dd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011ca6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011cc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011d95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011db8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011dd7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011ae1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011ae1`
- `ntoskrnl!MmUnmapLockedPages` at `0x140011c5b`
- `ntoskrnl!MmUnmapLockedPages` at `0x140011d49`
- `ntoskrnl!MmUnmapLockedPages` at `0x140011c5b`
- `ntoskrnl!MmUnmapLockedPages` at `0x140011d49`
- `ntoskrnl!KeInitializeTriageDumpDataArray` at `0x140011b84`
- `ntoskrnl!KeInitializeTriageDumpDataArray` at `0x140011b84`
- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x140011b25`
- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x140011bba`
- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x140011b25`
- `ntoskrnl!KeRegisterBugCheckReasonCallback` at `0x140011bba`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400118a6`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400118a6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001178c`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14001178c`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x140011c10`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x140011c34`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x140011c10`
- `ntoskrnl!KeDeregisterBugCheckReasonCallback` at `0x140011c34`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140011d76`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140011d76`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140011dee`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140011dee`
- `winhvr!WinHvGetPartitionProperty` at `0x1400117e5`
- `winhvr!WinHvGetPartitionProperty` at `0x1400117e5`
- `winhvr!WinHvUnmapEventLogBuffer` at `0x140011d5c`
- `winhvr!WinHvUnmapEventLogBuffer` at `0x140011d5c`

## pseudocode

```c
__int64 __fastcall HbEvtpInitializeSystemDiagLog(__int64 a1)
{
  int LogConfiguration; // eax
  __int64 *v4; // rdi
  int PartitionProperty; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // eax
  unsigned int i; // esi
  __int64 v10; // rcx
  void *Pool2; // rax
  _QWORD *v12; // rbx
  unsigned int v13; // esi
  bool v14; // zf
  __int64 v15; // rax
  PVOID v16; // r11
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // r14
  __int64 v20; // rbx
  unsigned int v21; // eax
  int v22; // esi
  unsigned int j; // edx
  unsigned __int64 v24; // r8
  __int64 v25; // r10
  __int64 v26; // r9
  __int64 v27; // rax
  char *v28; // rax
  char *v29; // rdx
  void *v30; // rax
  PKTRIAGE_DUMP_DATA_ARRAY *v31; // rbx
  char *v32; // rcx
  char *v33; // rdx
  void *v34; // rcx
  PVOID *v35; // rcx
  unsigned int k; // esi
  __int64 v37; // r15
  __int64 v38; // r14
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  __int64 v42; // [rsp+78h] [rbp+48h] BYREF
  __int64 *v43; // [rsp+80h] [rbp+50h] BYREF

  v42 = 0;
  v43 = 0;
  if ( !ExAcquireRundownProtection(&stru_140009408) )
    return 3221225635LL;
  LogConfiguration = HbEvtpGetLogConfiguration(2, &v43);
  v4 = v43;
  PartitionProperty = LogConfiguration;
  if ( LogConfiguration < 0 )
    goto LABEL_57;
  if ( *((_DWORD *)v43 + 2) )
    goto LABEL_56;
  PartitionProperty = WinHvGetPartitionProperty(-1, 327718, &v42);
  if ( PartitionProperty < 0 )
    goto LABEL_57;
  if ( (_DWORD)v42 )
  {
    if ( (unsigned int)(HIDWORD(v42) - 1) <= 0x1FF )
    {
      P = (PVOID)ExAllocatePool2(258, (unsigned int)(HIDWORD(v42) << 12), 1967284808);
      if ( P
        && (v6 = ExAllocatePool2(256, 112LL * (unsigned int)v42, 1967284808), (v4[4] = v6) != 0)
        && (v7 = ExAllocatePool2(64, 8LL * (unsigned int)v42, 1967284808), (v4[5] = v7) != 0) )
      {
        v8 = v42;
        for ( i = 0; i < (unsigned int)v42; v8 = v42 )
        {
          ExInitializeRundownProtection((PEX_RUNDOWN_REF)(v4[5] + 8LL * i));
          v10 = 112LL * i;
          *(_DWORD *)(v4[4] + v10 + 80) = 2;
          *(_DWORD *)(v4[4] + v10 + 84) = i++;
        }
        if ( HbpIsCpuManagementPartition )
        {
          Pool2 = (void *)ExAllocatePool2(64, 176, 1967284808);
          HbEvtpCrashdumpContext = Pool2;
          v12 = Pool2;
          if ( Pool2 )
          {
            memset(Pool2, 0, 0xB0u);
            v12[3] = HIDWORD(v42);
            v12[4] = (unsigned int)(HIDWORD(v42) << 12);
          }
          v8 = v42;
        }
        v13 = 0;
        if ( v8 )
        {
          while ( 1 )
          {
            PartitionProperty = HbEvtpMapSystemDiagLogBuffer(v4[4] + 112LL * v13, HIDWORD(v42));
            if ( PartitionProperty < 0 )
              break;
            if ( HbEvtpCrashdumpContext )
              *(__m128i *)((char *)HbEvtpCrashdumpContext + 40) = _mm_add_epi64(
                                                                    _mm_loadu_si128((const __m128i *)((char *)HbEvtpCrashdumpContext + 24)),
                                                                    _mm_loadu_si128((const __m128i *)((char *)HbEvtpCrashdumpContext + 40)));
            v8 = v42;
            if ( ++v13 >= (unsigned int)v42 )
              goto LABEL_24;
          }
        }
        else
        {
LABEL_24:
          *((_DWORD *)v4 + 2) = v8;
          *(_DWORD *)v4 = HIDWORD(v42);
          v14 = HbpIsCpuManagementPartition == 0;
          *((_DWORD *)v4 + 1) = HIDWORD(v42) << 12;
          *((_DWORD *)v4 + 3) = 0;
          *((_DWORD *)v4 + 4) = 2;
          *((_DWORD *)v4 + 12) = 1;
          dword_14000948C = -1;
          qword_140009480 = 0;
          dword_140009488 = 0;
          if ( v14 || (PartitionProperty = HbEvtpGetTlMetadataFromHvBinary(a1), PartitionProperty >= 0) )
          {
            byte_140009049 = 1;
            TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140009050);
            if ( !HbEvtpCrashdumpContext )
              goto LABEL_41;
            v15 = ExAllocatePool2(64, 16 * (*((_QWORD *)HbEvtpCrashdumpContext + 5) + 3LL), 1967284808);
            v16 = HbEvtpCrashdumpContext;
            v17 = v15;
            *((_QWORD *)HbEvtpCrashdumpContext + 2) = v15;
            if ( !v15 )
              goto LABEL_41;
            v18 = *((_QWORD *)v16 + 6);
            v19 = 0;
            *(_QWORD *)v17 = 0;
            v20 = 2;
            *(_WORD *)(v17 + 10) = 0;
            *(_QWORD *)(v17 + 32) = 0;
            *(_DWORD *)(v17 + 44) = 0;
            *(_DWORD *)(v17 + 40) = 2 * v18;
            *(_WORD *)(v17 + 8) = 8 * (((unsigned __int64)(2 * v18 + 4095) >> 12) + 6);
            *(_WORD *)(*((_QWORD *)v16 + 2) + 10LL) |= 0x2002u;
            v21 = v42;
            v22 = HIDWORD(v42);
            do
            {
              for ( j = 0; j < v21; ++j )
              {
                v24 = 0;
                v25 = v4[4] + 112LL * j;
                if ( v22 )
                {
                  v26 = v19 + 6;
                  do
                  {
                    ++v19;
                    v27 = *(_QWORD *)(*(_QWORD *)(v25 + 8) + 8 * v24++ + 48);
                    *(_QWORD *)(*((_QWORD *)v16 + 2) + 8 * v26++) = v27;
                    v22 = HIDWORD(v42);
                  }
                  while ( v24 < HIDWORD(v42) );
                  v21 = v42;
                }
              }
              --v20;
            }
            while ( v20 );
            v28 = (char *)MmMapLockedPagesSpecifyCache(*((PMDL *)v16 + 2), 0, MmCached, 0, 0, 0x40000020u);
            v29 = (char *)HbEvtpCrashdumpContext;
            *((_QWORD *)HbEvtpCrashdumpContext + 1) = v28;
            if ( !v28 )
              goto LABEL_41;
            *(_QWORD *)v29 = &v28[*((_QWORD *)v29 + 6)];
            v29[100] = 0;
            if ( !KeRegisterBugCheckReasonCallback(
                    (PKBUGCHECK_REASON_CALLBACK_RECORD)(v29 + 56),
                    HbEvtpSystemDiagLogCrashdumpCallback,
                    KbCallbackSecondaryDumpData,
                    (PUCHAR)"HbEvtpSystemDiagLogCrashdump") )
              goto LABEL_41;
            *((_BYTE *)HbEvtpCrashdumpContext + 104) = 1;
            v30 = (void *)ExAllocatePool2(64, 96, 1967284808);
            v31 = (PKTRIAGE_DUMP_DATA_ARRAY *)HbEvtpCrashdumpContext;
            *((_QWORD *)HbEvtpCrashdumpContext + 21) = v30;
            if ( !v30 )
              goto LABEL_41;
            memset(v30, 0, 0x60u);
            PartitionProperty = KeInitializeTriageDumpDataArray(v31[21], 0x60u);
            if ( PartitionProperty >= 0
              && (v32 = (char *)HbEvtpCrashdumpContext,
                  *((_BYTE *)HbEvtpCrashdumpContext + 156) = 0,
                  KeRegisterBugCheckReasonCallback(
                    (PKBUGCHECK_REASON_CALLBACK_RECORD)(v32 + 112),
                    HbEvtpTriageDumpDataCrashdumpCallback,
                    KbCallbackTriageDumpData,
                    (PUCHAR)"HbEvtpTriageDumpDataCrashdump")) )
            {
              *((_BYTE *)HbEvtpCrashdumpContext + 160) = 1;
            }
            else
            {
LABEL_41:
              PartitionProperty = 0;
              if ( HbpIsCpuManagementPartition )
                HbpTraceEvent(
                  1,
                  "HbEvtpInitializeSystemDiagLog",
                  5806,
                  "Failed to initialize unencrypted crashdump support for the hypervisor's event log");
              v33 = (char *)HbEvtpCrashdumpContext;
              if ( HbEvtpCrashdumpContext )
              {
                if ( *((_BYTE *)HbEvtpCrashdumpContext + 104) )
                {
                  KeDeregisterBugCheckReasonCallback((PKBUGCHECK_REASON_CALLBACK_RECORD)((char *)HbEvtpCrashdumpContext
                                                                                       + 56));
                  v33 = (char *)HbEvtpCrashdumpContext;
                  *((_BYTE *)HbEvtpCrashdumpContext + 104) = 0;
                }
                if ( v33[160] )
                {
                  KeDeregisterBugCheckReasonCallback((PKBUGCHECK_REASON_CALLBACK_RECORD)(v33 + 112));
                  v33 = (char *)HbEvtpCrashdumpContext;
                  *((_BYTE *)HbEvtpCrashdumpContext + 160) = 0;
                }
                v34 = (void *)*((_QWORD *)v33 + 1);
                if ( v34 )
                  MmUnmapLockedPages(v34, *((PMDL *)v33 + 2));
                v35 = (PVOID *)HbEvtpCrashdumpContext;
                if ( *((_QWORD *)HbEvtpCrashdumpContext + 2) )
                {
                  ExFreePoolWithTag(*((PVOID *)HbEvtpCrashdumpContext + 2), 0x75426248u);
                  v35 = (PVOID *)HbEvtpCrashdumpContext;
                  *((_QWORD *)HbEvtpCrashdumpContext + 2) = 0;
                }
                if ( v35[21] )
                {
                  ExFreePoolWithTag(v35[21], 0x75426248u);
                  v35 = (PVOID *)HbEvtpCrashdumpContext;
                  *((_QWORD *)HbEvtpCrashdumpContext + 21) = 0;
                }
                ExFreePoolWithTag(v35, 0x75426248u);
                HbEvtpCrashdumpContext = 0;
              }
            }
            goto LABEL_73;
          }
        }
      }
      else
      {
        PartitionProperty = -1073741670;
      }
LABEL_57:
      if ( HbEvtpCrashdumpContext )
      {
        ExFreePoolWithTag(HbEvtpCrashdumpContext, 0x75426248u);
        HbEvtpCrashdumpContext = 0;
      }
      if ( v4 && v4[4] )
      {
        for ( k = 0; k < (unsigned int)v42; ++k )
        {
          v37 = v4[4];
          v38 = 112LL * k;
          v39 = *(void **)(v38 + v37);
          if ( !v39 )
            break;
          MmUnmapLockedPages(v39, *(PMDL *)(v38 + v37 + 8));
          WinHvUnmapEventLogBuffer(2, k);
          if ( !HbpIsCpuManagementPartition )
            MmFreePagesFromMdl(*(PMDL *)(v38 + v37 + 8));
        }
        v40 = (void *)v4[4];
        if ( v40 )
        {
          ExFreePoolWithTag(v40, 0x75426248u);
          v4[4] = 0;
        }
        *((_DWORD *)v4 + 2) = 0;
      }
      if ( P )
      {
        ExFreePoolWithTag(P, 0x75426248u);
        P = 0;
      }
      v41 = (void *)v4[5];
      if ( v41 )
      {
        ExFreePoolWithTag(v41, 0x75426248u);
        v4[5] = 0;
      }
      goto LABEL_73;
    }
LABEL_56:
    PartitionProperty = -1073741811;
    goto LABEL_57;
  }
  PartitionProperty = 0;
LABEL_73:
  ExReleaseRundownProtection(&stru_140009408);
  return (unsigned int)PartitionProperty;
}

```

## disassembly

```asm
0x140011760  mov     [rsp-38h+arg_0], rbx
0x140011765  push    rbp
0x140011766  push    rsi
0x140011767  push    rdi
0x140011768  push    r12
0x14001176a  push    r13
0x14001176c  push    r14
0x14001176e  push    r15
0x140011770  mov     rbp, rsp
0x140011773  sub     rsp, 30h
0x140011777  mov     r14, rcx
0x14001177a  xor     r12d, r12d
0x14001177d  lea     rcx, stru_140009408; RunRef
0x140011784  mov     [rbp+arg_8], r12
0x140011788  mov     [rbp+arg_10], r12
0x14001178c  call    cs:__imp_ExAcquireRundownProtection
0x140011793  nop     dword ptr [rax+rax+00h]
0x140011798  test    al, al
0x14001179a  jnz     short loc_1400117A6
0x14001179c  mov     eax, 0C00000A3h
0x1400117a1  jmp     loc_140011DFC
0x1400117a6  lea     rdx, [rbp+arg_10]
0x1400117aa  mov     ecx, 2
0x1400117af  call    HbEvtpGetLogConfiguration
0x1400117b4  mov     rdi, [rbp+arg_10]
0x1400117b8  mov     ebx, eax
0x1400117ba  mov     r13d, 75426248h
0x1400117c0  mov     r15d, 1
0x1400117c6  test    eax, eax
0x1400117c8  js      loc_140011CF3
0x1400117ce  cmp     [rdi+8], r12d
0x1400117d2  ja      loc_140011CEE
0x1400117d8  lea     r8, [rbp+arg_8]
0x1400117dc  mov     edx, 50026h
0x1400117e1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400117e5  call    cs:__imp_WinHvGetPartitionProperty
0x1400117ec  nop     dword ptr [rax+rax+00h]
0x1400117f1  mov     ebx, eax
0x1400117f3  test    eax, eax
0x1400117f5  js      loc_140011CF3
0x1400117fb  cmp     dword ptr [rbp+arg_8], r12d
0x1400117ff  jnz     short loc_140011809
0x140011801  mov     ebx, r12d
0x140011804  jmp     loc_140011DE7
0x140011809  mov     ecx, dword ptr [rbp+arg_8+4]
0x14001180c  lea     eax, [rcx-1]
0x14001180f  cmp     eax, 1FFh
0x140011814  ja      loc_140011CEE
0x14001181a  shl     ecx, 0Ch
0x14001181d  mov     r8d, r13d
0x140011820  mov     edx, ecx
0x140011822  mov     ecx, 102h
0x140011827  call    cs:__imp_ExAllocatePool2
0x14001182e  nop     dword ptr [rax+rax+00h]
0x140011833  mov     cs:P, rax
0x14001183a  test    rax, rax
0x14001183d  jnz     short loc_140011849
0x14001183f  mov     ebx, 0C000009Ah
0x140011844  jmp     loc_140011CF3
0x140011849  mov     eax, dword ptr [rbp+arg_8]
0x14001184c  mov     r8d, r13d
0x14001184f  imul    rdx, rax, 70h ; 'p'
0x140011853  mov     ecx, 100h
0x140011858  call    cs:__imp_ExAllocatePool2
0x14001185f  nop     dword ptr [rax+rax+00h]
0x140011864  mov     [rdi+20h], rax
0x140011868  test    rax, rax
0x14001186b  jz      short loc_14001183F
0x14001186d  mov     edx, dword ptr [rbp+arg_8]
0x140011870  mov     r8d, r13d
0x140011873  shl     rdx, 3
0x140011877  mov     ecx, 40h ; '@'
0x14001187c  call    cs:__imp_ExAllocatePool2
0x140011883  nop     dword ptr [rax+rax+00h]
0x140011888  mov     [rdi+28h], rax
0x14001188c  test    rax, rax
0x14001188f  jz      short loc_14001183F
0x140011891  mov     rax, [rbp+arg_8]
0x140011895  mov     esi, r12d
0x140011898  test    eax, eax
0x14001189a  jz      short loc_1400118D5
0x14001189c  mov     rax, [rdi+28h]
0x1400118a0  mov     ebx, esi
0x1400118a2  lea     rcx, [rax+rbx*8]; RunRef
0x1400118a6  call    cs:__imp_ExInitializeRundownProtection
0x1400118ad  nop     dword ptr [rax+rax+00h]
0x1400118b2  mov     rax, [rdi+20h]
0x1400118b6  imul    rcx, rbx, 70h ; 'p'
0x1400118ba  mov     dword ptr [rax+rcx+50h], 2
0x1400118c2  mov     rax, [rdi+20h]
0x1400118c6  mov     [rax+rcx+54h], esi
0x1400118ca  add     esi, r15d
0x1400118cd  mov     rax, [rbp+arg_8]
0x1400118d1  cmp     esi, eax
0x1400118d3  jb      short loc_14001189C
0x1400118d5  cmp     cs:HbpIsCpuManagementPartition, r12b
0x1400118dc  jz      short loc_140011928
0x1400118de  mov     esi, 0B0h
0x1400118e3  mov     r8d, r13d
0x1400118e6  mov     edx, esi
0x1400118e8  lea     ecx, [rsi-70h]
0x1400118eb  call    cs:__imp_ExAllocatePool2
0x1400118f2  nop     dword ptr [rax+rax+00h]
0x1400118f7  mov     cs:HbEvtpCrashdumpContext, rax
0x1400118fe  mov     rbx, rax
0x140011901  test    rax, rax
0x140011904  jz      short loc_140011924
0x140011906  mov     r8d, esi; Size
0x140011909  xor     edx, edx; Val
0x14001190b  mov     rcx, rax; void *
0x14001190e  call    memset
0x140011913  mov     ecx, dword ptr [rbp+arg_8+4]
0x140011916  mov     [rbx+18h], rcx
0x14001191a  mov     ecx, dword ptr [rbp+arg_8+4]
0x14001191d  shl     ecx, 0Ch
0x140011920  mov     [rbx+20h], rcx
0x140011924  mov     rax, [rbp+arg_8]
0x140011928  mov     esi, r12d
0x14001192b  test    eax, eax
0x14001192d  jz      short loc_140011975
0x14001192f  mov     edx, dword ptr [rbp+arg_8+4]
0x140011932  mov     eax, esi
0x140011934  imul    rcx, rax, 70h ; 'p'
0x140011938  add     rcx, [rdi+20h]
0x14001193c  call    HbEvtpMapSystemDiagLogBuffer
0x140011941  mov     ebx, eax
0x140011943  test    eax, eax
0x140011945  js      loc_140011CF3
0x14001194b  mov     rax, cs:HbEvtpCrashdumpContext
0x140011952  test    rax, rax
0x140011955  jz      short loc_14001196A
0x140011957  movdqu  xmm0, xmmword ptr [rax+28h]
0x14001195c  movdqu  xmm1, xmmword ptr [rax+18h]
0x140011961  paddq   xmm1, xmm0
0x140011965  movdqu  xmmword ptr [rax+28h], xmm1
0x14001196a  mov     rax, [rbp+arg_8]
0x14001196e  add     esi, r15d
0x140011971  cmp     esi, eax
0x140011973  jb      short loc_14001192F
0x140011975  mov     [rdi+8], eax
0x140011978  mov     eax, dword ptr [rbp+arg_8+4]
0x14001197b  mov     [rdi], eax
0x14001197d  mov     eax, dword ptr [rbp+arg_8+4]
0x140011980  shl     eax, 0Ch
0x140011983  cmp     cs:HbpIsCpuManagementPartition, r12b
0x14001198a  mov     [rdi+4], eax
0x14001198d  mov     [rdi+0Ch], r12d
0x140011991  mov     dword ptr [rdi+10h], 2
0x140011998  mov     [rdi+30h], r15d
0x14001199c  mov     cs:dword_14000948C, 0FFFFFFFFh
0x1400119a6  mov     cs:qword_140009480, r12
0x1400119ad  mov     cs:dword_140009488, r12d
0x1400119b4  jz      short loc_1400119C8
0x1400119b6  mov     rcx, r14
0x1400119b9  call    HbEvtpGetTlMetadataFromHvBinary
0x1400119be  mov     ebx, eax
0x1400119c0  test    eax, eax
0x1400119c2  js      loc_140011CF3
0x1400119c8  mov     r8, r14
0x1400119cb  mov     cs:byte_140009049, r15b
0x1400119d2  lea     rdx, HbEvtpSystemDiagLogTraceLoggingCallback
0x1400119d9  lea     rcx, dword_140009050; CallbackContext
0x1400119e0  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400119e5  mov     rdx, cs:HbEvtpCrashdumpContext
0x1400119ec  test    rdx, rdx
0x1400119ef  jz      loc_140011BCE
0x1400119f5  mov     rdx, [rdx+28h]
0x1400119f9  mov     r8d, r13d
0x1400119fc  add     rdx, 3
0x140011a00  mov     ecx, 40h ; '@'
0x140011a05  shl     rdx, 4
0x140011a09  call    cs:__imp_ExAllocatePool2
0x140011a10  nop     dword ptr [rax+rax+00h]
0x140011a15  mov     r11, cs:HbEvtpCrashdumpContext
0x140011a1c  mov     rdx, rax
0x140011a1f  mov     [r11+10h], rax
0x140011a23  test    rax, rax
0x140011a26  jz      loc_140011BCE
0x140011a2c  mov     rax, [r11+30h]
0x140011a30  mov     r14, r12
0x140011a33  mov     [rdx], r12
0x140011a36  mov     ebx, 2
0x140011a3b  mov     [rdx+0Ah], r12w
0x140011a40  mov     [rdx+20h], r12
0x140011a44  lea     rcx, [rax+rax]
0x140011a48  mov     [rdx+2Ch], r12d
0x140011a4c  mov     [rdx+28h], ecx
0x140011a4f  lea     rax, [rcx+0FFFh]
0x140011a56  shr     rax, 0Ch
0x140011a5a  mov     ecx, 2002h
0x140011a5f  add     ax, 6
0x140011a63  shl     ax, 3
0x140011a67  mov     [rdx+8], ax
0x140011a6b  mov     rax, [r11+10h]
0x140011a6f  or      [rax+0Ah], cx
0x140011a73  mov     rax, [rbp+arg_8]
0x140011a77  mov     esi, dword ptr [rbp+arg_8+4]
0x140011a7a  mov     edx, r12d
0x140011a7d  test    eax, eax
0x140011a7f  jz      short loc_140011AC3
0x140011a81  mov     ecx, edx
0x140011a83  mov     r8, r12
0x140011a86  imul    r10, rcx, 70h ; 'p'
0x140011a8a  add     r10, [rdi+20h]
0x140011a8e  test    esi, esi
0x140011a90  jz      short loc_140011ABC
0x140011a92  lea     r9, [r14+6]
0x140011a96  mov     rax, [r10+8]
0x140011a9a  add     r14, r15
0x140011a9d  mov     rcx, [r11+10h]
0x140011aa1  mov     rax, [rax+r8*8+30h]
0x140011aa6  add     r8, r15
0x140011aa9  mov     [rcx+r9*8], rax
0x140011aad  add     r9, r15
0x140011ab0  mov     esi, dword ptr [rbp+arg_8+4]
0x140011ab3  cmp     r8, rsi
0x140011ab6  jb      short loc_140011A96
0x140011ab8  mov     rax, [rbp+arg_8]
0x140011abc  add     edx, r15d
0x140011abf  cmp     edx, eax
0x140011ac1  jb      short loc_140011A81
0x140011ac3  sub     rbx, r15
0x140011ac6  jnz     short loc_140011A7A
0x140011ac8  mov     rcx, [r11+10h]; MemoryDescriptorList
0x140011acc  xor     r9d, r9d; RequestedAddress
0x140011acf  mov     [rsp+30h+Priority], 40000020h; Priority
0x140011ad7  mov     r8d, r15d; CacheType
0x140011ada  xor     edx, edx; AccessMode
0x140011adc  mov     [rsp+30h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140011ae1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140011ae8  nop     dword ptr [rax+rax+00h]
0x140011aed  mov     rdx, cs:HbEvtpCrashdumpContext
0x140011af4  mov     rcx, rax
0x140011af7  mov     [rdx+8], rax
0x140011afb  test    rax, rax
0x140011afe  jz      loc_140011BCE
0x140011b04  add     rcx, [rdx+30h]
0x140011b08  lea     r9, Component; "HbEvtpSystemDiagLogCrashdump"
0x140011b0f  mov     [rdx], rcx
0x140011b12  lea     r8d, [rbx+2]; Reason
0x140011b16  lea     rcx, [rdx+38h]; CallbackRecord
0x140011b1a  mov     [rdx+64h], r12b
0x140011b1e  lea     rdx, HbEvtpSystemDiagLogCrashdumpCallback; CallbackRoutine
0x140011b25  call    cs:__imp_KeRegisterBugCheckReasonCallback
0x140011b2c  nop     dword ptr [rax+rax+00h]
0x140011b31  test    al, al
0x140011b33  jz      loc_140011BCE
0x140011b39  mov     rax, cs:HbEvtpCrashdumpContext
0x140011b40  lea     edi, [rbx+60h]
0x140011b43  mov     r8d, r13d
0x140011b46  lea     ecx, [rbx+40h]
0x140011b49  mov     edx, edi
0x140011b4b  mov     [rax+68h], r15b
0x140011b4f  call    cs:__imp_ExAllocatePool2
0x140011b56  nop     dword ptr [rax+rax+00h]
0x140011b5b  mov     rbx, cs:HbEvtpCrashdumpContext
0x140011b62  mov     [rbx+0A8h], rax
0x140011b69  test    rax, rax
0x140011b6c  jz      short loc_140011BCE
0x140011b6e  mov     r8d, edi; Size
0x140011b71  xor     edx, edx; Val
0x140011b73  mov     rcx, rax; void *
0x140011b76  call    memset
0x140011b7b  mov     rcx, [rbx+0A8h]; KtriageDumpDataArray
0x140011b82  mov     edx, edi; Size
0x140011b84  call    cs:__imp_KeInitializeTriageDumpDataArray
0x140011b8b  nop     dword ptr [rax+rax+00h]
0x140011b90  mov     ebx, eax
0x140011b92  test    eax, eax
0x140011b94  js      short loc_140011BCE
0x140011b96  mov     rcx, cs:HbEvtpCrashdumpContext
0x140011b9d  lea     r9, aHbevtptriagedu; "HbEvtpTriageDumpDataCrashdump"
0x140011ba4  lea     r8d, [rdi-59h]; Reason
0x140011ba8  lea     rdx, HbEvtpTriageDumpDataCrashdumpCallback; CallbackRoutine
0x140011baf  mov     [rcx+9Ch], r12b
0x140011bb6  add     rcx, 70h ; 'p'; CallbackRecord
0x140011bba  call    cs:__imp_KeRegisterBugCheckReasonCallback
0x140011bc1  nop     dword ptr [rax+rax+00h]
0x140011bc6  test    al, al
0x140011bc8  jnz     loc_140011CDB
0x140011bce  cmp     cs:HbpIsCpuManagementPartition, r12b
0x140011bd5  mov     ebx, r12d
0x140011bd8  jz      short loc_140011BF6
0x140011bda  lea     r9, aFailedToInitia; "Failed to initialize unencrypted crashd"...
0x140011be1  mov     r8d, 16AEh
0x140011be7  lea     rdx, aHbevtpinitiali; "HbEvtpInitializeSystemDiagLog"
0x140011bee  mov     ecx, r15d
0x140011bf1  call    HbpTraceEvent
0x140011bf6  mov     rdx, cs:HbEvtpCrashdumpContext
0x140011bfd  test    rdx, rdx
0x140011c00  jz      loc_140011DE7
0x140011c06  cmp     [rdx+68h], r12b
0x140011c0a  jz      short loc_140011C27
0x140011c0c  lea     rcx, [rdx+38h]; CallbackRecord
0x140011c10  call    cs:__imp_KeDeregisterBugCheckReasonCallback
0x140011c17  nop     dword ptr [rax+rax+00h]
0x140011c1c  mov     rdx, cs:HbEvtpCrashdumpContext
0x140011c23  mov     [rdx+68h], r12b
0x140011c27  cmp     [rdx+0A0h], r12b
0x140011c2e  jz      short loc_140011C4E
  ... truncated ...
```
