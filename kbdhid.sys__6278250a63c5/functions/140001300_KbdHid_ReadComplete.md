# KbdHid_ReadComplete

- ea: `0x140001300`
- end: `0x1400019f4`
- name: `KbdHid_ReadComplete`
- size: `1780`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001300`
- `0x140001a00`
- `0x140001d30`
- `0x140001ed0`
- `0x1400058d4`
- `0x140005a0c`
- `0x1400068bc`
- `0x140006a74`
- `0x140007240`
- `0x140007540`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400014b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001699`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400014b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001699`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400013a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400013a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016c7`
- `ntoskrnl!KeSetEvent` at `0x140001868`
- `ntoskrnl!KeSetEvent` at `0x140001868`
- `ntoskrnl!KeCancelTimer` at `0x140001720`
- `ntoskrnl!KeCancelTimer` at `0x140001720`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400018a6`
- `ntoskrnl!KeSetTimerEx` at `0x140001642`
- `ntoskrnl!KeSetTimerEx` at `0x1400019b6`
- `ntoskrnl!KeSetTimerEx` at `0x140001642`
- `ntoskrnl!KeSetTimerEx` at `0x1400019b6`
- `ntoskrnl!DbgBreakPointWithStatus` at `0x1400018cb`
- `ntoskrnl!DbgBreakPointWithStatus` at `0x1400018cb`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400018b6`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400018b6`
- `ntoskrnl!DbgPrint` at `0x140001972`
- `ntoskrnl!DbgPrint` at `0x140001972`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001885`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400019d6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001885`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400019d6`
- `HIDPARSE!HidP_TranslateUsageAndPagesToI8042ScanCodes` at `0x140001567`
- `HIDPARSE!HidP_TranslateUsageAndPagesToI8042ScanCodes` at `0x1400015b1`
- `HIDPARSE!HidP_TranslateUsageAndPagesToI8042ScanCodes` at `0x140001567`
- `HIDPARSE!HidP_TranslateUsageAndPagesToI8042ScanCodes` at `0x1400015b1`
- `HIDPARSE!HidP_UsageAndPageListDifference` at `0x1400014e2`
- `HIDPARSE!HidP_UsageAndPageListDifference` at `0x140001534`
- `HIDPARSE!HidP_UsageAndPageListDifference` at `0x140001786`
- `HIDPARSE!HidP_UsageAndPageListDifference` at `0x1400014e2`
- `HIDPARSE!HidP_UsageAndPageListDifference` at `0x140001534`
- `HIDPARSE!HidP_UsageAndPageListDifference` at `0x140001786`
- `HIDPARSE!HidP_GetUsagesEx` at `0x14000144c`
- `HIDPARSE!HidP_GetUsagesEx` at `0x14000144c`

## pseudocode

```c
__int64 __fastcall KbdHid_ReadComplete(PDEVICE_OBJECT DeviceObject, IRP *Irp, char *Context, int a4)
{
  IRP *v5; // r14
  KIRQL v6; // r13
  char v7; // r12
  NTSTATUS Status; // ecx
  __int64 v9; // rsi
  int v10; // r8d
  bool v11; // di
  ULONG *v12; // r14
  PUSAGE_AND_PAGE *v14; // rcx
  ULONG v15; // eax
  _DWORD *v16; // rcx
  NTSTATUS v17; // eax
  struct _USAGE_AND_PAGE *v18; // rdi
  KIRQL v19; // al
  __int64 i; // rdx
  struct _USAGE_AND_PAGE *v21; // r9
  int PreparsedData; // [rsp+20h] [rbp-88h]
  ULONG UsageLength; // [rsp+44h] [rbp-64h] BYREF
  PUSAGE_AND_PAGE *v24; // [rsp+48h] [rbp-60h]
  IRP *v25; // [rsp+50h] [rbp-58h]
  __int64 v26; // [rsp+58h] [rbp-50h]
  __int64 v27; // [rsp+60h] [rbp-48h]
  char v28; // [rsp+B0h] [rbp+8h]
  bool v29; // [rsp+B8h] [rbp+10h]
  CSHORT Type; // [rsp+C0h] [rbp+18h]
  ULONG v31; // [rsp+C8h] [rbp+20h]

  v28 = (char)DeviceObject;
  v5 = Irp;
  LODWORD(Irp) = 0;
  UsageLength = 0;
  v6 = 0;
  v7 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(Irp) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      2,
      10,
      (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
    LODWORD(Irp) = 0;
  }
  Status = v5->IoStatus.Status;
  v9 = *((_QWORD *)Context + 14);
  v25 = (IRP *)v9;
  v10 = 3;
  v11 = _InterlockedCompareExchange((volatile signed __int32 *)Context + 8, 3, 1) != 1;
  v29 = v11;
  if ( !*((_DWORD *)Context + 7) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qql(WPP_GLOBAL_Control->DeviceExtension, 0, 3, a4, PreparsedData, *(_QWORD *)Context, (char)v5, 0);
LABEL_57:
    if ( v11 )
    {
      KeSetEvent((PRKEVENT)(Context + 40), 0, 0);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 152), *((PVOID *)Context + 13), 0x20u);
      v11 = 0;
    }
    goto LABEL_5;
  }
  if ( Status )
  {
    if ( Status != -1073741738 && Status != -1073741727 && Status != -1073741667 && Status != -1073741536 )
      goto LABEL_5;
    goto LABEL_57;
  }
  v12 = (ULONG *)(v9 + 72);
  v27 = v9 + 72;
  if ( *(_DWORD *)(v9 + 72) )
  {
    UsageLength = *(_DWORD *)(v9 + 72);
    v24 = (PUSAGE_AND_PAGE *)(v9 + 88);
    if ( HidP_GetUsagesEx(
           HidP_Input,
           0,
           *(PUSAGE_AND_PAGE *)(v9 + 88),
           &UsageLength,
           *(PHIDP_PREPARSED_DATA *)v9,
           *(PCHAR *)(v9 + 80),
           *(unsigned __int16 *)(v9 + 12)) >= 0 )
    {
      v14 = (PUSAGE_AND_PAGE *)(v9 + 88);
      v26 = v9 + 88;
      if ( UsageLength == 1
        && (*v14)->UsagePage == 7
        && (*v14)->Usage == 70
        && BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceContext)
        && (_BYTE)KdDebuggerEnabled )
      {
        if ( !KdRefreshDebuggerNotPresent() )
          DbgBreakPointWithStatus(2u);
        v14 = (PUSAGE_AND_PAGE *)(v9 + 88);
      }
      v15 = 0;
      for ( Irp = (IRP *)*v14; ; Irp = (IRP *)((char *)Irp + 4) )
      {
        v25 = Irp;
        v31 = v15;
        if ( v15 >= *v12 )
          break;
        if ( (*v14)->UsagePage == 7 )
        {
          Type = Irp->Type;
          v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 93);
          for ( i = *((_QWORD *)Context + 92); i; i = *(_QWORD *)(i + 8) )
          {
            if ( *(_WORD *)i == Type )
            {
              Type = *(_WORD *)(i + 2);
              break;
            }
          }
          KeReleaseSpinLock((PKSPIN_LOCK)Context + 93, v19);
          Irp = v25;
          v25->Type = Type;
          if ( Type == 1 )
            goto LABEL_5;
          if ( !Type )
            break;
          v14 = v24;
        }
        v15 = v31 + 1;
      }
      v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 136));
      v7 = 1;
      if ( HidP_UsageAndPageListDifference(
             *(PUSAGE_AND_PAGE *)(v9 + 120),
             *v24,
             *(PUSAGE_AND_PAGE *)(v9 + 112),
             *(PUSAGE_AND_PAGE *)(v9 + 104),
             *v12) >= 0 )
      {
        v16 = *(_DWORD **)(v9 + 104);
        if ( *v16 || **(_DWORD **)(v9 + 112) )
        {
          memmove(v16, *(const void **)(v9 + 128), 4LL * *v12);
          if ( HidP_UsageAndPageListDifference(
                 *(PUSAGE_AND_PAGE *)(v9 + 120),
                 *v24,
                 *(PUSAGE_AND_PAGE *)(v9 + 96),
                 *(PUSAGE_AND_PAGE *)(v9 + 128),
                 *v12) >= 0
            && HidP_TranslateUsageAndPagesToI8042ScanCodes(
                 *(PUSAGE_AND_PAGE *)(v9 + 96),
                 *v12,
                 HidP_Keyboard_Break,
                 (PHIDP_KEYBOARD_MODIFIER_STATE)(v9 + 76),
                 KbdHid_InsertCodesIntoQueue,
                 Context) >= 0 )
          {
            if ( !*(_DWORD *)*v24 || (v21 = *(struct _USAGE_AND_PAGE **)(v9 + 128), *(_DWORD *)v21) )
              v17 = HidP_TranslateUsageAndPagesToI8042ScanCodes(
                      *(PUSAGE_AND_PAGE *)(v9 + 128),
                      *v12,
                      HidP_Keyboard_Make,
                      (PHIDP_KEYBOARD_MODIFIER_STATE)(v9 + 76),
                      KbdHid_InsertCodesIntoQueue,
                      Context);
            else
              v17 = HidP_UsageAndPageListDifference(
                      *(PUSAGE_AND_PAGE *)(v9 + 96),
                      *(PUSAGE_AND_PAGE *)(v9 + 104),
                      *(PUSAGE_AND_PAGE *)(v9 + 112),
                      v21,
                      *v12);
            if ( v17 >= 0 )
            {
              v18 = *(struct _USAGE_AND_PAGE **)(v9 + 120);
              *(_QWORD *)(v9 + 120) = *v24;
              memset(v18, 0, 4LL * *v12);
              *v24 = v18;
              LODWORD(Irp) = UsageLength;
              if ( !UsageLength )
              {
                if ( !*((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 6) )
                {
                  KeCancelTimer((PKTIMER)(Context + 432));
                  KbdHid_S0IdleStateUpdate(Context);
                }
                goto LABEL_30;
              }
              if ( **(_WORD **)(v9 + 96) || **(_WORD **)(v9 + 128) )
              {
                if ( !*((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 6) )
                  KeSetTimerEx(
                    (PKTIMER)(Context + 432),
                    *(LARGE_INTEGER *)(Context + 496),
                    *((_DWORD *)Context + 126),
                    (PKDPC)(Context + 368));
LABEL_30:
                v11 = v29;
                goto LABEL_5;
              }
              if ( !Context[648] )
              {
                Context[648] = 1;
                DbgPrint(
                  "*****\n"
                  "***** CHATTERY   KEYBOARD : Keyboard is sending useless reports.  Tell 'em to fix it.\n"
                  "*****\n");
                *((_DWORD *)Context + 30) |= 1u;
                KbdHid_LogError(*(_QWORD *)(*(_QWORD *)Context + 8LL));
              }
              if ( !Context[89] && v29 )
                KeSetTimerEx((PKTIMER)Context + 9, *(LARGE_INTEGER *)(Context + 640), 0, (PKDPC)Context + 8);
              v11 = 0;
              IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 152), *((PVOID *)Context + 13), 0x20u);
              KbdHid_CancelAutoRepeatTimer(Context);
            }
          }
        }
      }
    }
  }
LABEL_5:
  if ( v7 )
    KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 136), v6);
  if ( v11 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(Irp) = 5;
      WPP_RECORDER_SF_q(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)Irp, v10, 12, PreparsedData, v28);
    }
    KbdHid_StartRead(Context);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(Irp) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)Irp,
      2,
      13,
      (__int64)WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140001300  mov     [rsp+arg_10], r8
0x140001305  mov     [rsp+arg_0], rcx
0x14000130a  push    rbx
0x14000130b  push    rsi
0x14000130c  push    rdi
0x14000130d  push    r12
0x14000130f  push    r13
0x140001311  push    r14
0x140001313  push    r15
0x140001315  sub     rsp, 70h
0x140001319  mov     rbx, r8
0x14000131c  mov     r14, rdx
0x14000131f  xor     edx, edx
0x140001321  mov     [rsp+0A8h+UsageLength], edx
0x140001325  xor     r13b, r13b
0x140001328  mov     byte ptr [rsp+0A8h+arg_18], r13b
0x140001330  xor     r12b, r12b
0x140001333  lea     r15, WPP_RECORDER_INITIALIZED
0x14000133a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140001341  jnz     loc_1400013DF
0x140001347  mov     ecx, [r14+30h]
0x14000134b  mov     rsi, [rbx+70h]
0x14000134f  mov     [rsp+0A8h+var_58], rsi
0x140001354  mov     eax, 1
0x140001359  mov     r8d, 3
0x14000135f  lock cmpxchg [rbx+20h], r8d
0x140001365  setnz   dil
0x140001369  mov     [rsp+0A8h+arg_8], dil
0x140001371  cmp     dword ptr [rbx+1Ch], 0
0x140001375  jz      loc_140001806
0x14000137b  test    ecx, ecx
0x14000137d  jnz     loc_140001832
0x140001383  lea     r14, [rsi+48h]
0x140001387  mov     [rsp+0A8h+var_48], r14
0x14000138c  mov     eax, [r14]
0x14000138f  test    eax, eax
0x140001391  jnz     loc_14000141A
0x140001397  test    r12b, r12b
0x14000139a  jz      short loc_1400013B3
0x14000139c  lea     rcx, [rsi+88h]; SpinLock
0x1400013a3  movzx   edx, r13b; NewIrql
0x1400013a7  call    cs:__imp_KeReleaseSpinLock
0x1400013ae  nop     dword ptr [rax+rax+00h]
0x1400013b3  test    dil, dil
0x1400013b6  jnz     loc_14000165B
0x1400013bc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400013c3  jnz     loc_1400017CC
0x1400013c9  mov     eax, 0C0000016h
0x1400013ce  add     rsp, 70h
0x1400013d2  pop     r15
0x1400013d4  pop     r14
0x1400013d6  pop     r13
0x1400013d8  pop     r12
0x1400013da  pop     rdi
0x1400013db  pop     rsi
0x1400013dc  pop     rbx
0x1400013dd  retn
0x1400013df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400013e6  cmp     [rcx+48h], dx
0x1400013ea  jz      loc_140001347
0x1400013f0  mov     r9d, 0Ah
0x1400013f6  lea     rax, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x1400013fd  mov     [rsp+0A8h+PreparsedData], rax
0x140001402  mov     r8d, 2
0x140001408  mov     dl, 5
0x14000140a  mov     rcx, [rcx+40h]
0x14000140e  call    WPP_RECORDER_SF_
0x140001413  xor     edx, edx
0x140001415  jmp     loc_140001347
0x14000141a  mov     [rsp+0A8h+UsageLength], eax
0x14000141e  lea     rcx, [rsi+58h]
0x140001422  mov     [rsp+0A8h+var_60], rcx
0x140001427  movzx   eax, word ptr [rsi+0Ch]
0x14000142b  xor     edx, edx; LinkCollection
0x14000142d  mov     [rsp+0A8h+ReportLength], eax; ReportLength
0x140001431  mov     rax, [rsi+50h]
0x140001435  mov     [rsp+0A8h+Report], rax; Report
0x14000143a  mov     rax, [rsi]
0x14000143d  mov     [rsp+0A8h+PreparsedData], rax; PreparsedData
0x140001442  lea     r9, [rsp+0A8h+UsageLength]; UsageLength
0x140001447  mov     r8, [rcx]; ButtonList
0x14000144a  xor     ecx, ecx; ReportType
0x14000144c  call    cs:__imp_HidP_GetUsagesEx
0x140001453  nop     dword ptr [rax+rax+00h]
0x140001458  test    eax, eax
0x14000145a  js      loc_140001397
0x140001460  lea     rcx, [rsi+58h]
0x140001464  mov     [rsp+0A8h+var_50], rcx
0x140001469  mov     r8d, 7
0x14000146f  cmp     [rsp+0A8h+UsageLength], 1
0x140001474  jz      loc_140001741
0x14000147a  xor     eax, eax
0x14000147c  mov     rdx, [rcx]
0x14000147f  mov     [rsp+0A8h+var_58], rdx
0x140001484  mov     [rsp+0A8h+arg_18], eax
0x14000148b  cmp     eax, [r14]
0x14000148e  jnb     short loc_1400014AD
0x140001490  mov     rax, [rcx]
0x140001493  cmp     r8w, [rax+2]
0x140001498  jz      loc_140001687
0x14000149e  mov     eax, [rsp+0A8h+arg_18]
0x1400014a5  inc     eax
0x1400014a7  add     rdx, 4
0x1400014ab  jmp     short loc_14000147F
0x1400014ad  lea     rcx, [rsi+88h]; SpinLock
0x1400014b4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400014bb  nop     dword ptr [rax+rax+00h]
0x1400014c0  movzx   r13d, al
0x1400014c4  mov     r12b, 1
0x1400014c7  mov     ecx, [r14]
0x1400014ca  mov     dword ptr [rsp+0A8h+PreparsedData], ecx; UsageListLength
0x1400014ce  mov     r9, [rsi+68h]; MakeUsageList
0x1400014d2  mov     r8, [rsi+70h]; BreakUsageList
0x1400014d6  mov     rax, [rsp+0A8h+var_60]
0x1400014db  mov     rdx, [rax]; CurrentUsageList
0x1400014de  mov     rcx, [rsi+78h]; PreviousUsageList
0x1400014e2  call    cs:__imp_HidP_UsageAndPageListDifference
0x1400014e9  nop     dword ptr [rax+rax+00h]
0x1400014ee  test    eax, eax
0x1400014f0  js      loc_140001397
0x1400014f6  mov     rcx, [rsi+68h]; void *
0x1400014fa  cmp     dword ptr [rcx], 0
0x1400014fd  jz      loc_140001675
0x140001503  mov     r8d, [r14]
0x140001506  shl     r8, 2; Size
0x14000150a  mov     rdx, [rsi+80h]; Src
0x140001511  call    memmove
0x140001516  mov     eax, [r14]
0x140001519  mov     dword ptr [rsp+0A8h+PreparsedData], eax; UsageListLength
0x14000151d  mov     r9, [rsi+80h]; MakeUsageList
0x140001524  mov     r8, [rsi+60h]; BreakUsageList
0x140001528  mov     rax, [rsp+0A8h+var_60]
0x14000152d  mov     rdx, [rax]; CurrentUsageList
0x140001530  mov     rcx, [rsi+78h]; PreviousUsageList
0x140001534  call    cs:__imp_HidP_UsageAndPageListDifference
0x14000153b  nop     dword ptr [rax+rax+00h]
0x140001540  test    eax, eax
0x140001542  js      loc_140001397
0x140001548  lea     r9, [rsi+4Ch]; ModifierState
0x14000154c  mov     [rsp+0A8h+Report], rbx; InsertCodesContext
0x140001551  lea     rcx, KbdHid_InsertCodesIntoQueue
0x140001558  mov     [rsp+0A8h+PreparsedData], rcx; InsertCodesProcedure
0x14000155d  xor     r8d, r8d; KeyAction
0x140001560  mov     edx, [r14]; UsageListLength
0x140001563  mov     rcx, [rsi+60h]; ChangedUsageList
0x140001567  call    cs:__imp_HidP_TranslateUsageAndPagesToI8042ScanCodes
0x14000156e  nop     dword ptr [rax+rax+00h]
0x140001573  test    eax, eax
0x140001575  js      loc_140001397
0x14000157b  mov     rax, [rsp+0A8h+var_60]
0x140001580  mov     rax, [rax]
0x140001583  cmp     dword ptr [rax], 0
0x140001586  jnz     loc_140001762
0x14000158c  mov     [rsp+0A8h+Report], rbx; InsertCodesContext
0x140001591  lea     rax, KbdHid_InsertCodesIntoQueue
0x140001598  mov     [rsp+0A8h+PreparsedData], rax; InsertCodesProcedure
0x14000159d  lea     r9, [rsi+4Ch]; ModifierState
0x1400015a1  mov     r8d, 1; KeyAction
0x1400015a7  mov     edx, [r14]; UsageListLength
0x1400015aa  mov     rcx, [rsi+80h]; ChangedUsageList
0x1400015b1  call    cs:__imp_HidP_TranslateUsageAndPagesToI8042ScanCodes
0x1400015b8  nop     dword ptr [rax+rax+00h]
0x1400015bd  test    eax, eax
0x1400015bf  js      loc_140001397
0x1400015c5  mov     rdi, [rsi+78h]
0x1400015c9  mov     rax, [rsp+0A8h+var_60]
0x1400015ce  mov     rax, [rax]
0x1400015d1  mov     [rsi+78h], rax
0x1400015d5  mov     r8d, [r14]
0x1400015d8  shl     r8, 2; Size
0x1400015dc  xor     edx, edx; Val
0x1400015de  mov     rcx, rdi; void *
0x1400015e1  call    memset
0x1400015e6  mov     rax, [rsp+0A8h+var_60]
0x1400015eb  mov     [rax], rdi
0x1400015ee  mov     edx, [rsp+0A8h+UsageLength]
0x1400015f2  test    edx, edx
0x1400015f4  jz      loc_14000170C
0x1400015fa  mov     rax, [rsi+60h]
0x1400015fe  xor     ecx, ecx
0x140001600  cmp     cx, [rax]
0x140001603  jnz     short loc_140001615
0x140001605  mov     rax, [rsi+80h]
0x14000160c  cmp     cx, [rax]
0x14000160f  jz      loc_14000195C
0x140001615  test    edx, edx
0x140001617  jz      loc_14000170C
0x14000161d  cmp     byte ptr cs:WPP_MAIN_CB.Queue+2Eh, 0
0x140001624  jnz     short loc_14000164E
0x140001626  lea     r9, [rbx+170h]; Dpc
0x14000162d  lea     rcx, [rbx+1B0h]; Timer
0x140001634  mov     r8d, [rbx+1F8h]; Period
0x14000163b  mov     rdx, [rbx+1F0h]; DueTime
0x140001642  call    cs:__imp_KeSetTimerEx
0x140001649  nop     dword ptr [rax+rax+00h]
0x14000164e  movzx   edi, [rsp+0A8h+arg_8]
0x140001656  jmp     loc_140001397
0x14000165b  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140001662  jnz     loc_140001797
0x140001668  mov     rcx, rbx; Context
0x14000166b  call    KbdHid_StartRead
0x140001670  jmp     loc_1400013BC
0x140001675  mov     rax, [rsi+70h]
0x140001679  cmp     dword ptr [rax], 0
0x14000167c  jnz     loc_140001503
0x140001682  jmp     loc_140001397
0x140001687  movzx   eax, word ptr [rdx]
0x14000168a  mov     word ptr [rsp+0A8h+arg_10], ax
0x140001692  lea     rcx, [rbx+2E8h]; SpinLock
0x140001699  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400016a0  nop     dword ptr [rax+rax+00h]
0x1400016a5  mov     rdx, [rbx+2E0h]
0x1400016ac  movzx   ecx, word ptr [rsp+0A8h+arg_10]
0x1400016b4  test    rdx, rdx
0x1400016b7  jnz     loc_14000193D
0x1400016bd  movzx   edx, al; NewIrql
0x1400016c0  lea     rcx, [rbx+2E8h]; SpinLock
0x1400016c7  call    cs:__imp_KeReleaseSpinLock
0x1400016ce  nop     dword ptr [rax+rax+00h]
0x1400016d3  mov     rdx, [rsp+0A8h+var_58]
0x1400016d8  movzx   ecx, word ptr [rsp+0A8h+arg_10]
0x1400016e0  mov     [rdx], cx
0x1400016e3  mov     eax, 1
0x1400016e8  cmp     ax, cx
0x1400016eb  jz      loc_140001397
0x1400016f1  xor     eax, eax
0x1400016f3  cmp     ax, cx
0x1400016f6  jz      loc_1400014AD
0x1400016fc  mov     rcx, [rsp+0A8h+var_60]
0x140001701  mov     r8d, 7
0x140001707  jmp     loc_14000149E
0x14000170c  cmp     byte ptr cs:WPP_MAIN_CB.Queue+2Eh, 0
0x140001713  jnz     loc_14000164E
0x140001719  lea     rcx, [rbx+1B0h]; PKTIMER
0x140001720  call    cs:__imp_KeCancelTimer
0x140001727  nop     dword ptr [rax+rax+00h]
0x14000172c  xor     edx, edx
0x14000172e  mov     r8d, 1
0x140001734  mov     rcx, rbx; Context
0x140001737  call    KbdHid_S0IdleStateUpdate
0x14000173c  jmp     loc_14000164E
0x140001741  mov     rax, [rcx]
0x140001744  cmp     r8w, [rax+2]
0x140001749  jnz     loc_14000147A
0x14000174f  mov     edx, 46h ; 'F'
0x140001754  cmp     dx, [rax]
0x140001757  jnz     loc_14000147A
0x14000175d  jmp     loc_140001899
0x140001762  mov     r9, [rsi+80h]; MakeUsageList
0x140001769  cmp     dword ptr [r9], 0
0x14000176d  jnz     loc_14000158C
0x140001773  mov     eax, [r14]
0x140001776  mov     dword ptr [rsp+0A8h+PreparsedData], eax; UsageListLength
0x14000177a  mov     r8, [rsi+70h]; BreakUsageList
0x14000177e  mov     rdx, [rsi+68h]; CurrentUsageList
0x140001782  mov     rcx, [rsi+60h]; PreviousUsageList
0x140001786  call    cs:__imp_HidP_UsageAndPageListDifference
0x14000178d  nop     dword ptr [rax+rax+00h]
0x140001792  jmp     loc_1400015BD
0x140001797  mov     rcx, cs:WPP_GLOBAL_Control
0x14000179e  cmp     word ptr [rcx+48h], 0
0x1400017a3  jz      loc_140001668
0x1400017a9  mov     r9d, 0Ch
0x1400017af  mov     rax, [rsp+0A8h+arg_0]
0x1400017b7  mov     [rsp+0A8h+Report], rax
0x1400017bc  mov     dl, 5
0x1400017be  mov     rcx, [rcx+40h]
0x1400017c2  call    WPP_RECORDER_SF_q
0x1400017c7  jmp     loc_140001668
0x1400017cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400017d3  cmp     word ptr [rcx+48h], 0
0x1400017d8  jz      loc_1400013C9
0x1400017de  mov     r9d, 0Dh
0x1400017e4  lea     rax, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x1400017eb  mov     [rsp+0A8h+PreparsedData], rax
0x1400017f0  mov     r8d, 2
0x1400017f6  mov     dl, 5
0x1400017f8  mov     rcx, [rcx+40h]
0x1400017fc  call    WPP_RECORDER_SF_
0x140001801  jmp     loc_1400013C9
0x140001806  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000180d  jz      short loc_140001856
0x14000180f  mov     [rsp+0A8h+var_70], edx
0x140001813  mov     qword ptr [rsp+0A8h+ReportLength], r14
0x140001818  mov     rax, [rbx]
0x14000181b  mov     [rsp+0A8h+Report], rax
0x140001820  mov     rcx, cs:WPP_GLOBAL_Control
0x140001827  mov     rcx, [rcx+40h]
0x14000182b  call    WPP_RECORDER_SF_qql
0x140001830  jmp     short loc_140001856
0x140001832  cmp     ecx, 0C0000056h
0x140001838  jz      short loc_140001856
0x14000183a  cmp     ecx, 0C0000061h
0x140001840  jz      short loc_140001856
0x140001842  cmp     ecx, 0C000009Dh
0x140001848  jz      short loc_140001856
0x14000184a  cmp     ecx, 0C0000120h
0x140001850  jnz     loc_140001397
0x140001856  test    dil, dil
0x140001859  jz      loc_140001397
  ... truncated ...
```
