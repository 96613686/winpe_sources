# RefsFsdDeviceControl

- ea: `0x1c0178500`
- end: `0x1c017867c`
- name: `RefsFsdDeviceControl`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1c00049a0`
- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c000f920`
- `0x1c0013f90`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c0178500`
- `0x1c0196bc8`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1c018a1f4`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c018a1f4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0178609`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c018a168`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0178609`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c018a168`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c018a184`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c018a184`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c018a28b`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c018a28b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0178637`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c018a297`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0178637`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c018a297`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c018a158`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c018a158`

## pseudocode

```c
__int64 __fastcall RefsFsdDeviceControl(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  struct _IO_STACK_LOCATION *v5; // rax
  struct _IO_STACK_LOCATION *v6; // rax
  unsigned int v7; // esi
  __int64 v9; // r8
  __int64 v10; // rdx
  PIRP v11; // rcx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v13; // rbx
  BOOLEAN IsOperationSynchronous; // [rsp+40h] [rbp-88h]
  int Status; // [rsp+44h] [rbp-84h]
  BOOL v16; // [rsp+48h] [rbp-80h] BYREF
  struct _LIST_ENTRY *v17; // [rsp+50h] [rbp-78h] BYREF
  PIRP Irp; // [rsp+58h] [rbp-70h] BYREF
  IRP *v19; // [rsp+60h] [rbp-68h] BYREF
  IRP *v20; // [rsp+68h] [rbp-60h] BYREF
  __int64 v21; // [rsp+70h] [rbp-58h] BYREF
  char v22; // [rsp+78h] [rbp-50h] BYREF
  _OWORD v23[2]; // [rsp+80h] [rbp-48h] BYREF
  __int64 v24; // [rsp+A0h] [rbp-28h]
  __int128 v25; // [rsp+A8h] [rbp-20h] BYREF

  v20 = a2;
  v25 = 0;
  v21 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 508004
    || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 5488640
    || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 5488644 )
  {
    memset(v23, 0, sizeof(v23));
    v24 = 0;
    v17 = 0;
    IsOperationSynchronous = IoIsOperationSynchronous(a2);
    KeEnterCriticalRegion();
    v16 = (int)IoPropagateActivityIdToThread(a2, &v25, &v21) >= 0;
    v19 = (IRP *)RefsInitializeTopLevelIrp(v23, 0, 0);
    Irp = v19;
    LOBYTE(v9) = 1;
    LOBYTE(v10) = IsOperationSynchronous;
    RefsInitializeIrpContext(a2, v10, v9, &v17);
    v11 = Irp;
    Flink = Irp->ThreadListEntry.Flink;
    if ( Flink )
    {
      v13 = v17;
    }
    else
    {
      *(_DWORD *)(&Irp->Size + 1) = 1397140410;
      v13 = v17;
      v11->ThreadListEntry.Flink = v17;
      LODWORD(v13->Blink) |= 0x100000u;
      IoSetTopLevelIrp(v11);
      Flink = v19->ThreadListEntry.Flink;
    }
    v13[6].Blink = Flink;
    RefsPreRequestProcessingExtend(v13);
    v7 = RefsCommonDeviceControl(v13, a2);
    if ( v16 )
      IoClearActivityIdThread(v21);
    KeLeaveCriticalRegion();
    return v7;
  }
  Irp = 0;
  v19 = 0;
  v20 = 0;
  v16 = 0;
  if ( (unsigned int)RefsDecodeFileObject(
                       0,
                       CurrentStackLocation->FileObject,
                       (unsigned int)&Irp,
                       (unsigned int)&v22,
                       (__int64)&v19,
                       (__int64)&v20,
                       0) == 4 )
  {
    v5 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v5[-1].MajorFunction = *(_OWORD *)&v5->MajorFunction;
    *(_OWORD *)&v5[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v5->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v5[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v5->Parameters.SetQuota + 6);
    v5[-1].FileObject = v5->FileObject;
    v5[-1].Control = 0;
    v6 = a2->Tail.Overlay.CurrentStackLocation;
    v6[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)DeviceControlCompletionRoutine;
    v6[-1].Context = 0;
    v6[-1].Control = -32;
    KeEnterCriticalRegion();
    Status = RefsCallStorageDriver(Irp->Tail.Overlay.OriginalFileObject, a2, 0, &v16);
    KeLeaveCriticalRegion();
    if ( Status >= 0 )
      return v16;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsExtendedCompleteRequestInternal(0, a2, (unsigned int)Status);
    return (unsigned int)Status;
  }
  else
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(0, a2, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_dc311de8764c30504d44f87d572ca6c1_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1c0178500  mov     r11, rsp
0x1c0178503  mov     [r11+8], rbx
0x1c0178507  mov     [r11+18h], rsi
0x1c017850b  mov     [r11+20h], r14
0x1c017850f  push    r15
0x1c0178511  sub     rsp, 0C0h
0x1c0178518  mov     rax, cs:__security_cookie
0x1c017851f  xor     rax, rsp
0x1c0178522  mov     [rsp+0C8h+var_10], rax
0x1c017852a  mov     r14, rdx
0x1c017852d  mov     [rsp+0C8h+var_60], rdx
0x1c0178532  xor     esi, esi
0x1c0178534  xorps   xmm0, xmm0
0x1c0178537  movups  xmmword ptr [r11-20h], xmm0
0x1c017853c  and     [r11-58h], rsi
0x1c0178540  mov     rdx, [rdx+0B8h]
0x1c0178547  mov     ecx, [rdx+18h]
0x1c017854a  sub     ecx, 7C064h
0x1c0178550  jz      loc_1C018A126
0x1c0178556  sub     ecx, 4BFF9Ch
0x1c017855c  jz      loc_1C018A126
0x1c0178562  cmp     ecx, 4
0x1c0178565  jz      loc_1C018A126
0x1c017856b  xor     al, al
0x1c017856d  lea     r15d, [rsi+1]
0x1c0178571  test    al, al
0x1c0178573  jnz     loc_1C018A134
0x1c0178579  and     [rsp+0C8h+Irp], rsi
0x1c017857e  and     [rsp+0C8h+var_68], rsi
0x1c0178583  and     [rsp+0C8h+var_60], rsi
0x1c0178588  and     [rsp+0C8h+var_80], esi
0x1c017858c  mov     [rsp+0C8h+var_98], sil
0x1c0178591  lea     rax, [rsp+0C8h+var_60]
0x1c0178596  mov     [rsp+0C8h+var_A0], rax
0x1c017859b  lea     rax, [rsp+0C8h+var_68]
0x1c01785a0  mov     [rsp+0C8h+var_A8], rax
0x1c01785a5  lea     r9, [rsp+0C8h+var_50]
0x1c01785aa  lea     r8, [rsp+0C8h+Irp]
0x1c01785af  mov     rdx, [rdx+30h]
0x1c01785b3  xor     ecx, ecx
0x1c01785b5  call    RefsDecodeFileObject
0x1c01785ba  cmp     eax, 4
0x1c01785bd  jnz     loc_1C018A2A9
0x1c01785c3  mov     rax, [r14+0B8h]
0x1c01785ca  movups  xmm0, xmmword ptr [rax]
0x1c01785cd  movups  xmmword ptr [rax-48h], xmm0
0x1c01785d1  movups  xmm1, xmmword ptr [rax+10h]
0x1c01785d5  movups  xmmword ptr [rax-38h], xmm1
0x1c01785d9  movups  xmm0, xmmword ptr [rax+20h]
0x1c01785dd  movups  xmmword ptr [rax-28h], xmm0
0x1c01785e1  movsd   xmm1, qword ptr [rax+30h]
0x1c01785e6  movsd   qword ptr [rax-18h], xmm1
0x1c01785eb  mov     [rax-45h], sil
0x1c01785ef  mov     rax, [r14+0B8h]
0x1c01785f6  lea     rcx, DeviceControlCompletionRoutine
0x1c01785fd  mov     [rax-10h], rcx
0x1c0178601  and     [rax-8], rsi
0x1c0178605  mov     byte ptr [rax-45h], 0E0h
0x1c0178609  call    cs:__imp_KeEnterCriticalRegion
0x1c0178610  nop     dword ptr [rax+rax+00h]
0x1c0178615  lea     r9, [rsp+0C8h+var_80]
0x1c017861a  xor     r8d, r8d
0x1c017861d  mov     rdx, r14
0x1c0178620  mov     rcx, [rsp+0C8h+Irp]
0x1c0178625  mov     rcx, [rcx+0C0h]
0x1c017862c  call    RefsCallStorageDriver
0x1c0178631  mov     ebx, eax
0x1c0178633  mov     [rsp+0C8h+Status], eax
0x1c0178637  call    cs:__imp_KeLeaveCriticalRegion
0x1c017863e  nop     dword ptr [rax+rax+00h]
0x1c0178643  test    ebx, ebx
0x1c0178645  js      loc_1C018A338
0x1c017864b  mov     esi, [rsp+0C8h+var_80]
0x1c017864f  mov     eax, esi
0x1c0178651  mov     rcx, [rsp+0C8h+var_10]
0x1c0178659  xor     rcx, rsp; StackCookie
0x1c017865c  call    __security_check_cookie
0x1c0178661  lea     r11, [rsp+0C8h+var_8]
0x1c0178669  mov     rbx, [r11+10h]
0x1c017866d  mov     rsi, [r11+20h]
0x1c0178671  mov     r14, [r11+28h]
0x1c0178675  mov     rsp, r11
0x1c0178678  pop     r15
0x1c017867a  retn
0x1c0180a96  push    rbp
0x1c0180a98  sub     rsp, 40h
0x1c0180a9c  mov     rbp, rdx
0x1c0180a9f  mov     rdx, rcx
0x1c0180aa2  mov     rcx, [rbp+50h]
0x1c0180aa6  call    RefsExceptionFilter
0x1c0180aab  nop
0x1c0180aac  add     rsp, 40h
0x1c0180ab0  pop     rbp
0x1c0180ab1  retn
0x1c018a126  mov     r15d, 1
0x1c018a12c  mov     al, r15b
0x1c018a12f  jmp     loc_1C0178571
0x1c018a134  xor     eax, eax
0x1c018a136  movups  [rsp+0C8h+var_48], xmm0
0x1c018a13e  movups  [rsp+0C8h+var_38], xmm0
0x1c018a146  mov     [rsp+0C8h+var_28], rax
0x1c018a14e  xor     ebx, ebx
0x1c018a150  mov     [rsp+0C8h+var_78], rbx
0x1c018a155  mov     rcx, r14; Irp
0x1c018a158  call    cs:__imp_IoIsOperationSynchronous
0x1c018a15f  nop     dword ptr [rax+rax+00h]
0x1c018a164  mov     [rsp+0C8h+var_88], al
0x1c018a168  call    cs:__imp_KeEnterCriticalRegion
0x1c018a16f  nop     dword ptr [rax+rax+00h]
0x1c018a174  lea     r8, [rsp+0C8h+var_58]
0x1c018a179  lea     rdx, [rsp+0C8h+var_20]
0x1c018a181  mov     rcx, r14
0x1c018a184  call    cs:__imp_IoPropagateActivityIdToThread
0x1c018a18b  nop     dword ptr [rax+rax+00h]
0x1c018a190  xor     ecx, ecx
0x1c018a192  test    eax, eax
0x1c018a194  cmovns  ecx, r15d
0x1c018a198  mov     [rsp+0C8h+var_80], ecx
0x1c018a19c  xor     r8d, r8d
0x1c018a19f  xor     edx, edx
0x1c018a1a1  lea     rcx, [rsp+0C8h+var_48]
0x1c018a1a9  call    RefsInitializeTopLevelIrp
0x1c018a1ae  mov     [rsp+0C8h+var_68], rax
0x1c018a1b3  mov     [rsp+0C8h+Irp], rax
0x1c018a1b8  test    rbx, rbx
0x1c018a1bb  jnz     short loc_1C018A216
0x1c018a1bd  lea     r9, [rsp+0C8h+var_78]
0x1c018a1c2  mov     r8b, r15b
0x1c018a1c5  mov     dl, [rsp+0C8h+var_88]
0x1c018a1c9  mov     rcx, r14
0x1c018a1cc  call    RefsInitializeIrpContext
0x1c018a1d1  mov     rcx, [rsp+0C8h+Irp]; Irp
0x1c018a1d6  mov     rax, [rcx+20h]
0x1c018a1da  test    rax, rax
0x1c018a1dd  jnz     short loc_1C018A20B
0x1c018a1df  mov     dword ptr [rcx+4], 5346ABBAh
0x1c018a1e6  mov     rbx, [rsp+0C8h+var_78]
0x1c018a1eb  mov     [rcx+20h], rbx
0x1c018a1ef  bts     dword ptr [rbx+8], 14h
0x1c018a1f4  call    cs:__imp_IoSetTopLevelIrp
0x1c018a1fb  nop     dword ptr [rax+rax+00h]
0x1c018a200  mov     rax, [rsp+0C8h+var_68]
0x1c018a205  mov     rax, [rax+20h]
0x1c018a209  jmp     short loc_1C018A210
0x1c018a20b  mov     rbx, [rsp+0C8h+var_78]
0x1c018a210  mov     [rbx+68h], rax
0x1c018a214  jmp     short loc_1C018A226
0x1c018a216  cmp     esi, 0C0000188h
0x1c018a21c  jnz     short loc_1C018A226
0x1c018a21e  mov     rcx, rbx
0x1c018a221  call    RefsCheckpointForLogFileFull
0x1c018a226  mov     rcx, rbx
0x1c018a229  call    RefsPreRequestProcessingExtend
0x1c018a22e  mov     rdx, r14
0x1c018a231  mov     rcx, rbx
0x1c018a234  call    RefsCommonDeviceControl
0x1c018a239  mov     esi, eax
0x1c018a23b  mov     [rsp+0C8h+Status], eax
0x1c018a23f  jmp     short loc_1C018A27F
0x1c018a241  mov     r8d, eax
0x1c018a244  mov     r14, [rsp+0C8h+var_60]
0x1c018a249  mov     rdx, r14
0x1c018a24c  mov     rbx, [rsp+0C8h+var_78]
0x1c018a251  mov     rcx, rbx
0x1c018a254  call    RefsProcessException
0x1c018a259  mov     esi, eax
0x1c018a25b  mov     [rsp+0C8h+Status], eax
0x1c018a25f  cmp     eax, 0C00000D8h
0x1c018a264  jz      short loc_1C018A274
0x1c018a266  cmp     eax, 0C00001A8h
0x1c018a26b  jz      short loc_1C018A274
0x1c018a26d  cmp     eax, 0C0000188h
0x1c018a272  jnz     short loc_1C018A27F
0x1c018a274  mov     r15d, 1
0x1c018a27a  jmp     loc_1C018A1B8
0x1c018a27f  cmp     [rsp+0C8h+var_80], 0
0x1c018a284  jz      short loc_1C018A297
0x1c018a286  mov     rcx, [rsp+0C8h+var_58]
0x1c018a28b  call    cs:__imp_IoClearActivityIdThread
0x1c018a292  nop     dword ptr [rax+rax+00h]
0x1c018a297  call    cs:__imp_KeLeaveCriticalRegion
0x1c018a29e  nop     dword ptr [rax+rax+00h]
0x1c018a2a3  nop
0x1c018a2a4  jmp     loc_1C017864F
0x1c018a2a9  mov     al, cs:RefsStatusDebugEnabled
0x1c018a2af  mov     ebx, 0C000000Dh
0x1c018a2b4  test    al, al
0x1c018a2b6  jz      short loc_1C018A2CC
0x1c018a2b8  mov     r8d, 0DDh
0x1c018a2be  lea     rdx, aDevctrlC; "DevCtrl.c"
0x1c018a2c5  mov     ecx, ebx; Status
0x1c018a2c7  call    RefsStatusDebug
0x1c018a2cc  mov     r8d, ebx
0x1c018a2cf  mov     rdx, r14
0x1c018a2d2  xor     ecx, ecx
0x1c018a2d4  call    RefsExtendedCompleteRequestInternal
0x1c018a2d9  lea     rax, WPP_GLOBAL_Control
0x1c018a2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1c018a2e7  cmp     rcx, rax
0x1c018a2ea  jz      short loc_1C018A313
0x1c018a2ec  test    dword ptr [rcx+2Ch], 100h
0x1c018a2f3  jz      short loc_1C018A313
0x1c018a2f5  cmp     byte ptr [rcx+29h], 4
0x1c018a2f9  jb      short loc_1C018A313
0x1c018a2fb  mov     edx, 0Ah
0x1c018a300  mov     r9d, ebx
0x1c018a303  lea     r8, WPP_dc311de8764c30504d44f87d572ca6c1_Traceguids
0x1c018a30a  mov     rcx, [rcx+18h]
0x1c018a30e  call    WPP_SF_D
0x1c018a313  mov     cl, cs:RefsStatusDebugEnabled
0x1c018a319  test    cl, cl
0x1c018a31b  jz      short loc_1C018A331
0x1c018a31d  mov     r8d, 0DEh
0x1c018a323  lea     rdx, aDevctrlC; "DevCtrl.c"
0x1c018a32a  mov     ecx, ebx; Status
0x1c018a32c  call    RefsStatusDebug
0x1c018a331  mov     eax, ebx
0x1c018a333  jmp     loc_1C0178651
0x1c018a338  mov     al, cs:RefsStatusDebugEnabled
0x1c018a33e  test    al, al
0x1c018a340  jz      short loc_1C018A358
0x1c018a342  mov     r8d, 113h
0x1c018a348  lea     rdx, aDevctrlC; "DevCtrl.c"
0x1c018a34f  mov     ecx, [rsp+0C8h+Status]; Status
0x1c018a353  call    RefsStatusDebug
0x1c018a358  mov     r8d, [rsp+0C8h+Status]
0x1c018a35d  mov     rdx, r14
0x1c018a360  xor     ecx, ecx
0x1c018a362  call    RefsExtendedCompleteRequestInternal
0x1c018a367  mov     eax, [rsp+0C8h+Status]
0x1c018a36b  jmp     loc_1C0178651
```
