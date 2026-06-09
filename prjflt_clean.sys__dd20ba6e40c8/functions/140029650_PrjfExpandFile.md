# PrjfExpandFile

- ea: `0x140029650`
- end: `0x140029d52`
- name: `PrjfExpandFile`
- size: `1794`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140029f60`

## callees

- `0x140003480`
- `0x140003e6c`
- `0x1400047cc`
- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000d128`
- `0x14000d754`
- `0x14000dab0`
- `0x140028b30`
- `0x140029650`
- `0x14003e5ac`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x140029bea`
- `ntoskrnl!KeQueryPriorityThread` at `0x140029bea`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400296b4`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400296b4`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x140029ce6`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x140029ce6`
- `ntoskrnl!ExRundownCompleted` at `0x1400296e7`
- `ntoskrnl!ExRundownCompleted` at `0x1400296e7`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400296d3`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400296d3`
- `ntoskrnl!KeClearEvent` at `0x140029b05`
- `ntoskrnl!KeClearEvent` at `0x140029b05`
- `ntoskrnl!KeSetEvent` at `0x140029b49`
- `ntoskrnl!KeSetEvent` at `0x140029ca2`
- `ntoskrnl!KeSetEvent` at `0x140029b49`
- `ntoskrnl!KeSetEvent` at `0x140029ca2`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029b19`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029b19`
- `ntoskrnl!ExAcquireFastMutex` at `0x140029ae4`
- `ntoskrnl!ExAcquireFastMutex` at `0x140029ae4`
- `ntoskrnl!ObfReferenceObject` at `0x140029bd5`
- `ntoskrnl!ObfReferenceObject` at `0x140029bd5`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14002978f`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14002978f`
- `FLTMGR!FltSetInformationFile` at `0x140029839`
- `FLTMGR!FltSetInformationFile` at `0x140029839`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140029d13`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140029d13`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140029c0c`
- `FLTMGR!FltQueueGenericWorkItem` at `0x140029c0c`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140029b25`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140029b25`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140029d28`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140029d28`

## pseudocode

```c
__int64 __fastcall PrjfExpandFile(struct _FLT_INSTANCE *a1, struct _FILE_OBJECT *a2, __int64 a3, __int64 *a4)
{
  __int64 v4; // rax
  int *v8; // r10
  int v9; // esi
  int v10; // r12d
  int v11; // r15d
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // r13
  __int64 v13; // r8
  int FileNameInformationUnsafe; // ebx
  PFLT_FILE_NAME_INFORMATION v15; // r8
  PVOID v16; // r9
  int v17; // esi
  struct _FLT_INSTANCE *v18; // rsi
  __int64 v19; // rdx
  __int64 v21; // rdx
  unsigned int v22; // esi
  __int64 v23; // r15
  __int128 v24; // xmm0
  bool v25; // zf
  int v26; // edx
  int v27; // edx
  KPRIORITY PriorityThread; // eax
  int v29; // edx
  __int64 v30; // rcx
  char *v31; // rcx
  __int64 v32; // rdx
  int v33; // [rsp+30h] [rbp-61h]
  __int16 v34; // [rsp+38h] [rbp-59h]
  char v35; // [rsp+50h] [rbp-41h]
  char v36; // [rsp+58h] [rbp-39h]
  __int64 p_FileName; // [rsp+60h] [rbp-31h]
  bool v38; // [rsp+68h] [rbp-29h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+70h] [rbp-21h] BYREF
  PVOID P; // [rsp+78h] [rbp-19h]
  __int64 FileInformation; // [rsp+80h] [rbp-11h] BYREF
  __int64 v42; // [rsp+88h] [rbp-9h]
  __int128 v43; // [rsp+98h] [rbp+7h] BYREF
  __int128 v44[4]; // [rsp+A8h] [rbp+17h] BYREF
  USHORT SectorSize; // [rsp+108h] [rbp+77h]

  v4 = *(_QWORD *)(a3 + 8);
  FileInformation = 0;
  FileNameInformation = 0;
  v8 = *(int **)(v4 + 88);
  v9 = *(_DWORD *)(v4 + 64);
  v10 = v8[1];
  v11 = *v8;
  if ( v9 <= v10 )
  {
    if ( v9 == v10 )
      return 0;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  }
  GenericWorkItem = 0;
  SectorSize = IoGetRelatedDeviceObject(a2)->SectorSize;
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(*(_QWORD *)(a3 + 8) + 80LL));
  ExRundownCompleted((PEX_RUNDOWN_REF)(*(_QWORD *)(a3 + 8) + 80LL));
  LOBYTE(v13) = 1;
  FileNameInformationUnsafe = PrjfSuppressTimestamps(a1, a2, v13);
  v38 = FileNameInformationUnsafe >= 0;
  v43 = *(_OWORD *)(*(_QWORD *)(a3 + 8) + 96LL);
  P = (PVOID)PrjfGetUnionContext(a1, &v43);
  v16 = P;
  if ( P )
  {
    v42 = 0;
    v17 = v9 - 1;
    if ( v17 )
    {
      if ( v17 == 1 )
      {
        v18 = a1;
        if ( (v11 & 2) != 0 )
        {
          FileInformation = 0;
          FileNameInformationUnsafe = FltSetInformationFile(a1, a2, &FileInformation, 8u, FileEndOfFileInformation);
          if ( FileNameInformationUnsafe < 0 )
            goto LABEL_55;
        }
LABEL_8:
        if ( v10 == 3 && (*(_DWORD *)(a3 + 40) & 0x1000) != 0 )
        {
          v43 = 0;
          FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(a2, v18, 0x101u, &FileNameInformation);
          if ( FileNameInformationUnsafe < 0 )
          {
            LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            LOBYTE(v19) = BYTE1(xmmword_14001A3D0) & 4;
            if ( (BYTE1(xmmword_14001A3D0) & 4) == 0
              && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              goto LABEL_55;
            }
            p_FileName = (__int64)&a2->FileName;
            v36 = FileNameInformationUnsafe;
            v35 = 93;
            v34 = 23;
            goto LABEL_34;
          }
          v16 = P;
          v15 = FileNameInformation;
          v19 = *((unsigned __int16 *)P + 20);
          if ( FileNameInformation->Name.Length <= (unsigned __int16)v19 )
          {
            FileNameInformationUnsafe = -1073741773;
            LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            LOBYTE(v19) = BYTE1(xmmword_14001A3D0) & 4;
            if ( (BYTE1(xmmword_14001A3D0) & 4) == 0
              && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              goto LABEL_55;
            }
            p_FileName = (__int64)&a2->FileName;
            v36 = 51;
            v35 = 109;
            v34 = 24;
            goto LABEL_34;
          }
          v24 = *(_OWORD *)P;
          *((_QWORD *)&v43 + 1) = (char *)FileNameInformation->Name.Buffer + v19 + 2;
          v25 = *(_DWORD *)a3 == 1;
          LOWORD(v43) = FileNameInformation->Name.Length - v19 - 2;
          WORD1(v43) = v43;
          LOBYTE(v33) = v25;
          v44[0] = v24;
          FileNameInformationUnsafe = PrjfSendNotifyOperationCommand(0, v18, a2, v44, &v43, v33, 4096, 0, 0, 0, 0);
          if ( FileNameInformationUnsafe < 0 )
          {
            LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            if ( (BYTE1(xmmword_14001A3D0) & 4) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v26) = BYTE1(xmmword_14001A3D0) & 4;
              WPP_RECORDER_AND_TRACE_SF_sDdZ(
                522,
                v26,
                (_DWORD)v15,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                10,
                25,
                (__int64)&WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
                137,
                FileNameInformationUnsafe,
                (__int64)&FileNameInformation->Name);
            }
            goto LABEL_55;
          }
        }
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 8) + 8LL));
        *(_DWORD *)(*(_QWORD *)(a3 + 8) + 64LL) = v10;
        KeClearEvent((PRKEVENT)(*(_QWORD *)(a3 + 8) + 344LL));
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a3 + 8) + 8LL));
        GenericWorkItem = FltAllocateGenericWorkItem();
        if ( GenericWorkItem )
        {
          ObfReferenceObject(a2);
          PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
          FileNameInformationUnsafe = FltQueueGenericWorkItem(
                                        GenericWorkItem,
                                        v18,
                                        PrjfFlushAndUpdateDiskStateWorker,
                                        (WORK_QUEUE_TYPE)(PriorityThread + 32),
                                        a2);
          if ( FileNameInformationUnsafe >= 0 )
          {
            GenericWorkItem = 0;
            if ( a4 )
              *a4 = v42;
          }
          else
          {
            if ( (BYTE1(xmmword_14001A3D0) & 4) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v29) = BYTE1(xmmword_14001A3D0) & 4;
              LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDqd(
                522,
                v29,
                (_DWORD)v15,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                10,
                27,
                (__int64)&WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
                193,
                (char)a2,
                FileNameInformationUnsafe);
            }
            KeSetEvent((PRKEVENT)(*(_QWORD *)(a3 + 8) + 344LL), 0, 0);
          }
        }
        else
        {
          KeSetEvent((PRKEVENT)(*(_QWORD *)(a3 + 8) + 344LL), 0, 0);
          FileNameInformationUnsafe = -1073741670;
          LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v27) = BYTE1(xmmword_14001A3D0) & 4;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              522,
              v27,
              (_DWORD)v15,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              10,
              26,
              (__int64)&WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
              171,
              154);
          }
        }
        goto LABEL_55;
      }
      MicrosoftTelemetryAssertTriggeredMsgKM("Unexpected target state!");
    }
    else if ( (v11 & 2) == 0 && (v11 & 8) == 0 )
    {
      v21 = *(_QWORD *)(a3 + 16);
      v42 = v21;
      *(_QWORD *)&v43 = (unsigned int)-SectorSize;
      v22 = v21 <= (__int64)v43 ? *(_DWORD *)(a3 + 16) : -SectorSize;
      v23 = 0;
      if ( v21 > 0 )
      {
        while ( 1 )
        {
          v44[0] = *(_OWORD *)(a3 + 24);
          FileNameInformationUnsafe = PrjfCopyStreamData(a1, v23, v22, a2, (__int64)v16, v44);
          if ( FileNameInformationUnsafe < 0 )
            break;
          v23 += v22;
          if ( *(_QWORD *)(a3 + 16) - v23 <= (__int64)v43 )
            v22 = *(_DWORD *)(a3 + 16) - v23;
          else
            v22 = -SectorSize;
          v16 = P;
          if ( v23 >= *(_QWORD *)(a3 + 16) )
            goto LABEL_7;
        }
        LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v19) = BYTE1(xmmword_14001A3D0) & 4;
        if ( (BYTE1(xmmword_14001A3D0) & 4) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_55;
        p_FileName = (__int64)&a2->FileName;
        v36 = FileNameInformationUnsafe;
        v35 = 15;
        v34 = 22;
LABEL_34:
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          522,
          v19,
          (_DWORD)v15,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          10,
          v34,
          (__int64)&WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
          v35,
          v36,
          p_FileName);
        goto LABEL_55;
      }
    }
LABEL_7:
    v18 = a1;
    goto LABEL_8;
  }
LABEL_55:
  if ( v38 )
    PrjfSuppressTimestamps(a1, a2, 0);
  v30 = *(_QWORD *)(a3 + 8);
  if ( *(int *)(v30 + 64) < 3 )
    ExReInitializeRundownProtection((PEX_RUNDOWN_REF)(v30 + 80));
  v31 = (char *)P;
  v32 = *(_QWORD *)(*(_QWORD *)(a3 + 8) + 88LL);
  *(_DWORD *)(v32 + 8) = FileNameInformationUnsafe;
  if ( v31 )
    PrjfReleaseUnionContext(v31, v32, (__int64)v15, (__int64)v16);
  if ( GenericWorkItem )
    FltFreeGenericWorkItem(GenericWorkItem);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)FileNameInformationUnsafe;
}

```

## disassembly

```asm
0x140029650  mov     rax, rsp
0x140029653  mov     [rax+10h], rbx
0x140029657  mov     [rax+20h], r9
0x14002965b  mov     [rax+8], rcx
0x14002965f  push    rbp
0x140029660  push    rsi
0x140029661  push    rdi
0x140029662  push    r12
0x140029664  push    r13
0x140029666  push    r14
0x140029668  push    r15
0x14002966a  lea     rbp, [rax-5Fh]
0x14002966e  sub     rsp, 0B0h
0x140029675  mov     rax, [r8+8]
0x140029679  mov     rdi, r8
0x14002967c  mov     [rbp+57h+FileInformation], 0
0x140029684  mov     r14, rdx
0x140029687  mov     [rbp+57h+FileNameInformation], 0
0x14002968f  mov     rbx, rcx
0x140029692  mov     r10, [rax+58h]
0x140029696  mov     esi, [rax+40h]
0x140029699  mov     r12d, [r10+4]
0x14002969d  mov     r15d, [r10]
0x1400296a0  cmp     esi, r12d
0x1400296a3  jle     loc_140029804
0x1400296a9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400296ae  mov     rcx, r14; FileObject
0x1400296b1  xor     r13d, r13d
0x1400296b4  call    cs:__imp_IoGetRelatedDeviceObject
0x1400296bb  nop     dword ptr [rax+rax+00h]
0x1400296c0  mov     rcx, [rdi+8]
0x1400296c4  add     rcx, 50h ; 'P'; RunRef
0x1400296c8  movzx   eax, word ptr [rax+130h]
0x1400296cf  mov     word ptr [rbp+57h+arg_10], ax
0x1400296d3  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400296da  nop     dword ptr [rax+rax+00h]
0x1400296df  mov     rcx, [rdi+8]
0x1400296e3  add     rcx, 50h ; 'P'; RunRef
0x1400296e7  call    cs:__imp_ExRundownCompleted
0x1400296ee  nop     dword ptr [rax+rax+00h]
0x1400296f3  mov     r8b, 1
0x1400296f6  mov     rdx, r14
0x1400296f9  mov     rcx, rbx
0x1400296fc  call    PrjfSuppressTimestamps
0x140029701  mov     rcx, [rbp+57h+Instance]
0x140029705  lea     rdx, [rbp+57h+var_50]
0x140029709  mov     ebx, eax
0x14002970b  shr     eax, 1Fh
0x14002970e  xor     al, 1
0x140029710  mov     dword ptr [rbp+57h+var_80], eax
0x140029713  mov     rax, [rdi+8]
0x140029717  movups  xmm0, xmmword ptr [rax+60h]
0x14002971b  movdqu  [rbp+57h+var_50], xmm0
0x140029720  call    PrjfGetUnionContext
0x140029725  mov     [rbp+57h+P], rax
0x140029729  mov     r9, rax
0x14002972c  test    rax, rax
0x14002972f  jz      loc_140029CC3
0x140029735  mov     ecx, r15d
0x140029738  mov     [rbp+57h+var_60], r13
0x14002973c  and     ecx, 2
0x14002973f  sub     esi, 1
0x140029742  jz      loc_140029854
0x140029748  cmp     esi, 1
0x14002974b  jz      loc_140029811
0x140029751  lea     rcx, aUnexpectedTarg; "Unexpected target state!"
0x140029758  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002975d  mov     rsi, [rbp+57h+Instance]
0x140029761  cmp     r12d, 3
0x140029765  jnz     loc_140029ADC
0x14002976b  test    dword ptr [rdi+28h], 1000h
0x140029772  jz      loc_140029ADC
0x140029778  xorps   xmm0, xmm0
0x14002977b  lea     r9, [rbp+57h+FileNameInformation]; FileNameInformation
0x14002977f  mov     r8d, 101h; NameOptions
0x140029785  mov     rdx, rsi; Instance
0x140029788  mov     rcx, r14; FileObject
0x14002978b  movups  [rbp+57h+var_50], xmm0
0x14002978f  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140029796  nop     dword ptr [rax+rax+00h]
0x14002979b  mov     ebx, eax
0x14002979d  test    eax, eax
0x14002979f  jns     loc_14002997C
0x1400297a5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400297ab  lea     rax, WPP_RECORDER_INITIALIZED
0x1400297b2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400297b9  setnz   r8b
0x1400297bd  and     dl, 4
0x1400297c0  jnz     short loc_1400297CB
0x1400297c2  test    r8b, r8b
0x1400297c5  jz      loc_140029CC3
0x1400297cb  lea     rax, [r14+58h]
0x1400297cf  mov     [rsp+58h], rax
0x1400297d4  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400297db  mov     dword ptr [rsp+0E0h+var_90], ebx
0x1400297df  mov     dword ptr [rsp+0E0h+var_98], 55Dh
0x1400297e7  mov     qword ptr [rsp+0E0h+var_A0], rax
0x1400297ec  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x1400297f3  mov     [rsp+0E0h+var_A8], rax
0x1400297f8  mov     word ptr [rsp+0E0h+var_B0], 17h
0x1400297ff  jmp     loc_140029955
0x140029804  jnz     loc_1400296AE
0x14002980a  xor     eax, eax
0x14002980c  jmp     loc_140029D36
0x140029811  mov     rsi, [rbp+57h+Instance]
0x140029815  test    ecx, ecx
0x140029817  jz      loc_140029761
0x14002981d  mov     r9d, 8; Length
0x140029823  mov     [rbp+57h+FileInformation], r13
0x140029827  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14002982b  mov     [rsp+0E0h+FileInformationClass], 14h; FileInformationClass
0x140029833  mov     rdx, r14; FileObject
0x140029836  mov     rcx, rsi; Instance
0x140029839  call    cs:__imp_FltSetInformationFile
0x140029840  nop     dword ptr [rax+rax+00h]
0x140029845  mov     ebx, eax
0x140029847  test    eax, eax
0x140029849  js      loc_140029CC3
0x14002984f  jmp     loc_140029761
0x140029854  test    ecx, ecx
0x140029856  jnz     loc_14002975D
0x14002985c  test    r15b, 8
0x140029860  jnz     loc_14002975D
0x140029866  movzx   ecx, word ptr [rbp+57h+arg_10]
0x14002986a  mov     rdx, [rdi+10h]
0x14002986e  mov     r8d, ecx
0x140029871  neg     r8
0x140029874  mov     [rbp+57h+var_60], rdx
0x140029878  mov     r8d, r8d
0x14002987b  mov     qword ptr [rbp+57h+var_50], r8
0x14002987f  mov     [rbp+57h+arg_10], ecx
0x140029882  cmp     rdx, r8
0x140029885  jle     short loc_14002988D
0x140029887  mov     esi, ecx
0x140029889  neg     esi
0x14002988b  jmp     short loc_140029890
0x14002988d  mov     esi, [rdi+10h]
0x140029890  xor     r15d, r15d
0x140029893  test    rdx, rdx
0x140029896  jle     loc_14002975D
0x14002989c  movups  xmm0, xmmword ptr [rdi+18h]
0x1400298a0  mov     rcx, [rbp+57h+Instance]
0x1400298a4  lea     rax, [rbp+57h+var_40]
0x1400298a8  mov     qword ptr [rsp+0E0h+var_B8], rax
0x1400298ad  mov     r8d, esi
0x1400298b0  mov     qword ptr [rsp+0E0h+FileInformationClass], r9
0x1400298b5  mov     rdx, r15
0x1400298b8  mov     r9, r14
0x1400298bb  movdqu  [rbp+57h+var_40], xmm0
0x1400298c0  call    PrjfCopyStreamData
0x1400298c5  mov     ebx, eax
0x1400298c7  test    eax, eax
0x1400298c9  js      short loc_1400298FB
0x1400298cb  mov     rcx, [rdi+10h]
0x1400298cf  mov     eax, esi
0x1400298d1  add     r15, rax
0x1400298d4  mov     rax, rcx
0x1400298d7  sub     rax, r15
0x1400298da  cmp     rax, qword ptr [rbp+57h+var_50]
0x1400298de  jle     short loc_1400298E7
0x1400298e0  mov     esi, [rbp+57h+arg_10]
0x1400298e3  neg     esi
0x1400298e5  jmp     short loc_1400298ED
0x1400298e7  mov     esi, [rdi+10h]
0x1400298ea  sub     esi, r15d
0x1400298ed  mov     r9, [rbp+57h+P]
0x1400298f1  cmp     r15, rcx
0x1400298f4  jl      short loc_14002989C
0x1400298f6  jmp     loc_14002975D
0x1400298fb  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140029901  lea     rax, WPP_RECORDER_INITIALIZED
0x140029908  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002990f  setnz   r8b
0x140029913  and     dl, 4
0x140029916  jnz     short loc_140029921
0x140029918  test    r8b, r8b
0x14002991b  jz      loc_140029CC3
0x140029921  lea     rax, [r14+58h]
0x140029925  mov     [rsp+58h], rax
0x14002992a  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140029931  mov     dword ptr [rsp+0E0h+var_90], ebx
0x140029935  mov     dword ptr [rsp+0E0h+var_98], 50Fh
0x14002993d  mov     qword ptr [rsp+0E0h+var_A0], rax
0x140029942  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x140029949  mov     [rsp+0E0h+var_A8], rax
0x14002994e  mov     word ptr [rsp+0E0h+var_B0], 16h
0x140029955  mov     [rsp+0E0h+var_B8], 0Ah
0x14002995d  mov     byte ptr [rsp+0E0h+FileInformationClass], 2
0x140029962  mov     r9, cs:WPP_GLOBAL_Control
0x140029969  mov     ecx, 20Ah
0x14002996e  mov     r9, [r9+40h]
0x140029972  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140029977  jmp     loc_140029CC3
0x14002997c  mov     r9, [rbp+57h+P]
0x140029980  mov     r8, [rbp+57h+FileNameInformation]
0x140029984  movzx   edx, word ptr [r9+28h]
0x140029989  cmp     [r8+8], dx
0x14002998e  ja      short loc_1400299F4
0x140029990  mov     ebx, 0C0000033h
0x140029995  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002999b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400299a2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400299a9  setnz   r8b
0x1400299ad  and     dl, 4
0x1400299b0  jnz     short loc_1400299BB
0x1400299b2  test    r8b, r8b
0x1400299b5  jz      loc_140029CC3
0x1400299bb  lea     rax, [r14+58h]
0x1400299bf  mov     [rsp+58h], rax
0x1400299c4  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400299cb  mov     dword ptr [rsp+0E0h+var_90], ebx
0x1400299cf  mov     dword ptr [rsp+0E0h+var_98], 56Dh
0x1400299d7  mov     qword ptr [rsp+0E0h+var_A0], rax
0x1400299dc  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x1400299e3  mov     [rsp+0E0h+var_A8], rax
0x1400299e8  mov     word ptr [rsp+0E0h+var_B0], 18h
0x1400299ef  jmp     loc_140029955
0x1400299f4  mov     rcx, [r8+10h]
0x1400299f8  mov     r15d, 2
0x1400299fe  movups  xmm0, xmmword ptr [r9]
0x140029a02  mov     [rsp+0E0h+var_90], r13
0x140029a07  lea     r9, [rbp+57h+var_40]
0x140029a0b  mov     byte ptr [rsp+0E0h+var_98], r13b
0x140029a10  add     rcx, 2
0x140029a14  add     rcx, rdx
0x140029a17  mov     qword ptr [rsp+0E0h+var_A0], r13
0x140029a1c  mov     qword ptr [rbp+57h+var_50+8], rcx
0x140029a20  movzx   eax, word ptr [r8+8]
0x140029a25  mov     r8, r14
0x140029a28  sub     ax, dx
0x140029a2b  mov     [rsp+0E0h+var_A8], r13
0x140029a30  sub     ax, r15w
0x140029a34  mov     dword ptr [rsp+0E0h+var_B0], 1000h
0x140029a3c  cmp     dword ptr [rdi], 1
0x140029a3f  mov     rdx, rsi
0x140029a42  mov     word ptr [rbp+57h+var_50], ax
0x140029a46  mov     word ptr [rbp+57h+var_50+2], ax
0x140029a4a  setz    al
0x140029a4d  mov     byte ptr [rsp+0E0h+var_B8], al
0x140029a51  xor     ecx, ecx
0x140029a53  lea     rax, [rbp+57h+var_50]
0x140029a57  mov     qword ptr [rsp+0E0h+FileInformationClass], rax
0x140029a5c  movdqu  [rbp+57h+var_40], xmm0
0x140029a61  call    PrjfSendNotifyOperationCommand
0x140029a66  mov     ebx, eax
0x140029a68  test    eax, eax
0x140029a6a  jns     short loc_140029ADC
0x140029a6c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140029a72  lea     rax, WPP_RECORDER_INITIALIZED
0x140029a79  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029a80  setnz   r8b
0x140029a84  and     dl, 4
0x140029a87  jnz     short loc_140029A92
0x140029a89  test    r8b, r8b
0x140029a8c  jz      loc_140029CC3
0x140029a92  mov     rax, [rbp+57h+FileNameInformation]
0x140029a96  add     rax, 8
0x140029a9a  mov     [rsp+58h], rax
0x140029a9f  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140029aa6  mov     dword ptr [rsp+0E0h+var_90], ebx
0x140029aaa  mov     dword ptr [rsp+0E0h+var_98], 589h
0x140029ab2  mov     qword ptr [rsp+0E0h+var_A0], rax
0x140029ab7  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x140029abe  mov     [rsp+0E0h+var_A8], rax
0x140029ac3  mov     word ptr [rsp+0E0h+var_B0], 19h
0x140029aca  mov     [rsp+0E0h+var_B8], 0Ah
0x140029ad2  mov     byte ptr [rsp+0E0h+FileInformationClass], r15b
0x140029ad7  jmp     loc_140029962
0x140029adc  mov     rcx, [rdi+8]
0x140029ae0  add     rcx, 8; FastMutex
0x140029ae4  call    cs:__imp_ExAcquireFastMutex
0x140029aeb  nop     dword ptr [rax+rax+00h]
0x140029af0  mov     rax, [rdi+8]
0x140029af4  mov     r15d, 158h
0x140029afa  mov     [rax+40h], r12d
0x140029afe  mov     rcx, [rdi+8]
0x140029b02  add     rcx, r15; Event
0x140029b05  call    cs:__imp_KeClearEvent
0x140029b0c  nop     dword ptr [rax+rax+00h]
0x140029b11  mov     rcx, [rdi+8]
0x140029b15  add     rcx, 8; FastMutex
0x140029b19  call    cs:__imp_ExReleaseFastMutex
0x140029b20  nop     dword ptr [rax+rax+00h]
0x140029b25  call    cs:__imp_FltAllocateGenericWorkItem
0x140029b2c  nop     dword ptr [rax+rax+00h]
0x140029b31  mov     r13, rax
0x140029b34  test    rax, rax
0x140029b37  jnz     loc_140029BD2
0x140029b3d  mov     rcx, [rdi+8]
0x140029b41  xor     r8d, r8d; Wait
0x140029b44  add     rcx, r15; Event
0x140029b47  xor     edx, edx; Increment
0x140029b49  call    cs:__imp_KeSetEvent
0x140029b50  nop     dword ptr [rax+rax+00h]
0x140029b55  mov     ebx, 0C000009Ah
0x140029b5a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140029b60  lea     rax, WPP_RECORDER_INITIALIZED
0x140029b67  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140029b6e  setnz   r8b
0x140029b72  and     dl, 4
  ... truncated ...
```
