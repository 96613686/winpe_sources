# MouHid_Power

- ea: `0x140002050`
- end: `0x140002360`
- name: `MouHid_Power`
- size: `784`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001464`
- `0x140002050`
- `0x140002780`
- `0x14000292c`
- `0x140002af0`
- `0x140002e68`

## import_xrefs

- `ntoskrnl!PoCallDriver` at `0x14000216f`
- `ntoskrnl!PoCallDriver` at `0x140002297`
- `ntoskrnl!PoCallDriver` at `0x14000216f`
- `ntoskrnl!PoCallDriver` at `0x140002297`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400020f2`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140002151`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400020f2`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140002151`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400022eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400022eb`
- `ntoskrnl!IofCompleteRequest` at `0x140002106`
- `ntoskrnl!IofCompleteRequest` at `0x140002106`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002189`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140002189`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002309`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002309`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400020da`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400020da`

## pseudocode

```c
__int64 __fastcall MouHid_Power(__int64 a1, IRP *a2)
{
  int v4; // edx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  __int64 v6; // rsi
  ULONG Options; // ebp
  DWORD LowPart; // r13d
  int v9; // edx
  NTSTATUS v10; // ebx
  int v11; // r9d
  char MinorFunction; // al
  int v13; // edx
  const char *v15; // rax
  struct _IO_STACK_LOCATION *v16; // rax
  struct _IO_STACK_LOCATION *v17; // rax
  char v18; // al
  KIRQL v19; // al
  int v20; // edx
  int RemlockSize; // [rsp+20h] [rbp-78h]

  v4 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v4) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      4,
      29,
      (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids);
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v6 = *(_QWORD *)(a1 + 64);
  Options = CurrentStackLocation->Parameters.Create.Options;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v10 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v6 + 240), a2, File, 1u, 0x20u);
  if ( v10 < 0 )
  {
    PoStartNextPowerIrp(a2);
    a2->IoStatus.Status = v10;
    IofCompleteRequest(a2, 0);
    return (unsigned int)v10;
  }
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( MinorFunction == 2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = "S";
      if ( Options )
        v15 = "D";
      WPP_RECORDER_SF_qqsd(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)"D",
        0,
        v11,
        RemlockSize,
        a1,
        (char)a2,
        (__int64)v15,
        LowPart - 1);
    }
    if ( Options == 1 )
    {
      *(_DWORD *)(v6 + 44) = *(_DWORD *)(v6 + 40);
      *(_DWORD *)(v6 + 40) = LowPart;
      if ( LowPart == 1 )
      {
        v16 = a2->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&v16[-1].MajorFunction = *(_OWORD *)&v16->MajorFunction;
        *(_OWORD *)&v16[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v16->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&v16[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v16->Parameters.SetQuota + 6);
        v16[-1].FileObject = v16->FileObject;
        v16[-1].Control = 0;
        v17 = a2->Tail.Overlay.CurrentStackLocation;
        v17[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&MouHid_PowerCompletion;
        v17[-1].Context = 0;
        v17[-1].Control = -32;
        a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        PoCallDriver(*(PDEVICE_OBJECT *)(v6 + 8), a2);
        v10 = 259;
        goto LABEL_10;
      }
      v18 = _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 56), 3, 2);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qL(WPP_GLOBAL_Control->DeviceExtension, v9, 0, 31, RemlockSize, a1, v18);
      v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 64));
      *(_DWORD *)(v6 + 76) = *(_DWORD *)(v6 + 72);
      *(_DWORD *)(v6 + 84) = *(_DWORD *)(v6 + 80);
      KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 64), v19);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qdd(
          WPP_GLOBAL_Control->DeviceExtension,
          v20,
          4,
          32,
          (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
          a1,
          *(_DWORD *)(v6 + 72),
          *(_DWORD *)(v6 + 80));
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_c(WPP_GLOBAL_Control->DeviceExtension, v9, 0, v11, RemlockSize, MinorFunction);
  }
  PoStartNextPowerIrp(a2);
  ++a2->CurrentLocation;
  ++a2->Tail.Overlay.CurrentStackLocation;
  v10 = PoCallDriver(*(PDEVICE_OBJECT *)(v6 + 8), a2);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v6 + 240), a2, 0x20u);
LABEL_10:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = 0;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v13) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        4,
        34,
        (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140002050  push    rbx
0x140002052  push    rbp
0x140002053  push    rsi
0x140002054  push    rdi
0x140002055  push    r12
0x140002057  push    r13
0x140002059  push    r14
0x14000205b  push    r15
0x14000205d  sub     rsp, 58h
0x140002061  mov     rdi, rdx
0x140002064  mov     r14, rcx
0x140002067  lea     rax, WPP_RECORDER_INITIALIZED
0x14000206e  xor     edx, edx
0x140002070  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002077  lea     r8, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x14000207e  jz      short loc_1400020A5
0x140002080  mov     rcx, cs:WPP_GLOBAL_Control
0x140002087  cmp     [rcx+48h], dx
0x14000208b  jz      short loc_1400020A5
0x14000208d  mov     rcx, [rcx+40h]
0x140002091  lea     r9d, [rdx+1Dh]
0x140002095  mov     qword ptr [rsp+98h+RemlockSize], r8
0x14000209a  lea     r8d, [rdx+4]
0x14000209e  mov     dl, 5
0x1400020a0  call    WPP_RECORDER_SF_
0x1400020a5  mov     r15, [rdi+0B8h]
0x1400020ac  lea     r8, File; File
0x1400020b3  mov     rsi, [r14+40h]
0x1400020b7  mov     r9d, 1; Line
0x1400020bd  mov     rdx, rdi; Tag
0x1400020c0  mov     [rsp+98h+RemlockSize], 20h ; ' '; RemlockSize
0x1400020c8  mov     ebp, [r15+10h]
0x1400020cc  mov     r13d, [r15+18h]
0x1400020d0  lea     r12, [rsi+0F0h]
0x1400020d7  mov     rcx, r12; RemoveLock
0x1400020da  call    cs:__imp_IoAcquireRemoveLockEx
0x1400020e1  nop     dword ptr [rax+rax+00h]
0x1400020e6  xor     r8d, r8d
0x1400020e9  mov     ebx, eax
0x1400020eb  test    eax, eax
0x1400020ed  jns     short loc_140002117
0x1400020ef  mov     rcx, rdi; Irp
0x1400020f2  call    cs:__imp_PoStartNextPowerIrp
0x1400020f9  nop     dword ptr [rax+rax+00h]
0x1400020fe  xor     edx, edx; PriorityBoost
0x140002100  mov     [rdi+30h], ebx
0x140002103  mov     rcx, rdi; Irp
0x140002106  call    cs:__imp_IofCompleteRequest
0x14000210d  nop     dword ptr [rax+rax+00h]
0x140002112  jmp     loc_1400021C5
0x140002117  mov     al, [r15+1]
0x14000211b  cmp     al, 2
0x14000211d  jz      loc_1400021D9
0x140002123  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000212a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140002131  jz      short loc_140002147
0x140002133  mov     rcx, cs:WPP_GLOBAL_Control
0x14000213a  mov     byte ptr [rsp+98h+var_70], al
0x14000213e  mov     rcx, [rcx+40h]
0x140002142  call    WPP_RECORDER_SF_c
0x140002147  lea     rbp, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x14000214e  mov     rcx, rdi; Irp
0x140002151  call    cs:__imp_PoStartNextPowerIrp
0x140002158  nop     dword ptr [rax+rax+00h]
0x14000215d  inc     byte ptr [rdi+43h]
0x140002160  mov     rdx, rdi; Irp
0x140002163  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x14000216b  mov     rcx, [rsi+8]; DeviceObject
0x14000216f  call    cs:__imp_PoCallDriver
0x140002176  nop     dword ptr [rax+rax+00h]
0x14000217b  mov     r8d, 20h ; ' '; RemlockSize
0x140002181  mov     rdx, rdi; Tag
0x140002184  mov     rcx, r12; RemoveLock
0x140002187  mov     ebx, eax
0x140002189  call    cs:__imp_IoReleaseRemoveLockEx
0x140002190  nop     dword ptr [rax+rax+00h]
0x140002195  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000219c  jz      short loc_1400021C5
0x14000219e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400021a5  xor     edx, edx
0x1400021a7  cmp     [rcx+48h], dx
0x1400021ab  jz      short loc_1400021C5
0x1400021ad  mov     rcx, [rcx+40h]
0x1400021b1  lea     r9d, [rdx+22h]
0x1400021b5  lea     r8d, [rdx+4]
0x1400021b9  mov     qword ptr [rsp+98h+RemlockSize], rbp
0x1400021be  mov     dl, 5
0x1400021c0  call    WPP_RECORDER_SF_
0x1400021c5  mov     eax, ebx
0x1400021c7  add     rsp, 58h
0x1400021cb  pop     r15
0x1400021cd  pop     r14
0x1400021cf  pop     r13
0x1400021d1  pop     r12
0x1400021d3  pop     rdi
0x1400021d4  pop     rsi
0x1400021d5  pop     rbp
0x1400021d6  pop     rbx
0x1400021d7  retn
0x1400021d9  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400021e0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400021e7  jz      short loc_140002227
0x1400021e9  lea     ecx, [r13-1]
0x1400021ed  test    ebp, ebp
0x1400021ef  mov     [rsp+98h+var_58], ecx
0x1400021f3  lea     rdx, aD; "D"
0x1400021fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140002201  lea     rax, aS; "S"
0x140002208  cmovnz  rax, rdx
0x14000220c  mov     [rsp+98h+var_60], rax
0x140002211  mov     [rsp+98h+var_68], rdi
0x140002216  mov     rcx, [rcx+40h]
0x14000221a  mov     [rsp+98h+var_70], r14
0x14000221f  call    WPP_RECORDER_SF_qqsd
0x140002224  xor     r8d, r8d
0x140002227  cmp     ebp, 1
0x14000222a  jnz     loc_140002147
0x140002230  mov     eax, [rsi+28h]
0x140002233  mov     [rsi+2Ch], eax
0x140002236  mov     [rsi+28h], r13d
0x14000223a  cmp     r13d, ebp
0x14000223d  jnz     short loc_1400022B4
0x14000223f  mov     rax, [rdi+0B8h]
0x140002246  lea     rcx, MouHid_PowerCompletion
0x14000224d  mov     rdx, rdi; Irp
0x140002250  movups  xmm0, xmmword ptr [rax]
0x140002253  movups  xmmword ptr [rax-48h], xmm0
0x140002257  movups  xmm1, xmmword ptr [rax+10h]
0x14000225b  movups  xmmword ptr [rax-38h], xmm1
0x14000225f  movups  xmm0, xmmword ptr [rax+20h]
0x140002263  movups  xmmword ptr [rax-28h], xmm0
0x140002267  movsd   xmm1, qword ptr [rax+30h]
0x14000226c  movsd   qword ptr [rax-18h], xmm1
0x140002271  mov     [rax-45h], r8b
0x140002275  mov     rax, [rdi+0B8h]
0x14000227c  mov     [rax-10h], rcx
0x140002280  mov     [rax-8], r8
0x140002284  mov     byte ptr [rax-45h], 0E0h
0x140002288  mov     rax, [rdi+0B8h]
0x14000228f  or      [rax+3], bpl
0x140002293  mov     rcx, [rsi+8]; DeviceObject
0x140002297  call    cs:__imp_PoCallDriver
0x14000229e  nop     dword ptr [rax+rax+00h]
0x1400022a3  mov     ebx, 103h
0x1400022a8  lea     rbp, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x1400022af  jmp     loc_140002195
0x1400022b4  mov     ecx, 3
0x1400022b9  lea     eax, [rcx-1]
0x1400022bc  lock cmpxchg [rsi+38h], ecx
0x1400022c1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400022c8  jz      short loc_1400022E7
0x1400022ca  lea     r9d, [rcx+1Ch]
0x1400022ce  mov     dword ptr [rsp+98h+var_68], eax
0x1400022d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022d9  mov     [rsp+98h+var_70], r14
0x1400022de  mov     rcx, [rcx+40h]
0x1400022e2  call    WPP_RECORDER_SF_qL
0x1400022e7  lea     rcx, [rsi+40h]; SpinLock
0x1400022eb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400022f2  nop     dword ptr [rax+rax+00h]
0x1400022f7  mov     edx, [rsi+48h]
0x1400022fa  lea     rcx, [rsi+40h]; SpinLock
0x1400022fe  mov     [rsi+4Ch], edx
0x140002301  mov     edx, [rsi+50h]
0x140002304  mov     [rsi+54h], edx
0x140002307  mov     dl, al; NewIrql
0x140002309  call    cs:__imp_KeReleaseSpinLock
0x140002310  nop     dword ptr [rax+rax+00h]
0x140002315  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14000231c  jz      loc_140002147
0x140002322  mov     eax, [rsi+50h]
0x140002325  lea     rbp, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x14000232c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002333  mov     r9d, 20h ; ' '
0x140002339  mov     dword ptr [rsp+98h+var_60], eax
0x14000233d  mov     eax, [rsi+48h]
0x140002340  mov     dword ptr [rsp+98h+var_68], eax
0x140002344  mov     rcx, [rcx+40h]
0x140002348  lea     r8d, [r9-1Ch]
0x14000234c  mov     [rsp+98h+var_70], r14
0x140002351  mov     qword ptr [rsp+98h+RemlockSize], rbp
0x140002356  call    WPP_RECORDER_SF_qdd
0x14000235b  jmp     loc_14000214E
```
