# RefsCommonPnp

- ea: `0x1c0174fcc`
- end: `0x1c0175736`
- name: `RefsCommonPnp`
- size: `1898`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1c0174d50`

## callees

- `0x1c000f770`
- `0x1c000f920`
- `0x1c0013f90`
- `0x1c003cac4`
- `0x1c0068168`
- `0x1c015527c`
- `0x1c016d3c4`
- `0x1c0174be4`
- `0x1c0174fcc`
- `0x1c017cb78`
- `0x1c017d30c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c0175338`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0175338`
- `ntoskrnl!KeInitializeEvent` at `0x1c017505d`
- `ntoskrnl!KeInitializeEvent` at `0x1c017505d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0175617`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c01756ed`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0175617`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c01756ed`
- `ntoskrnl!KeClearEvent` at `0x1c0175628`
- `ntoskrnl!KeClearEvent` at `0x1c0175628`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x1c0175344`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x1c0175344`

## pseudocode

```c
__int64 __fastcall RefsCommonPnp(__int64 a1, IRP **a2, _BYTE *a3, __int64 a4)
{
  _BYTE *v4; // rdi
  bool v7; // r12
  PDEVICE_OBJECT DeviceObject; // rbx
  struct _DEVICE_OBJECT *v9; // rbx
  int v10; // eax
  int v11; // ecx
  int v12; // edi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v14; // rcx
  __int64 v15; // r9
  char v16; // al
  __int64 v17; // r8
  __int64 v18; // r9
  BOOL v19; // eax
  int Status; // [rsp+30h] [rbp-68h]
  _QWORD v22[11]; // [rsp+40h] [rbp-58h] BYREF
  char v23; // [rsp+A8h] [rbp+10h]
  _BYTE *v24; // [rsp+B0h] [rbp+18h]
  NTSTATUS v25; // [rsp+B8h] [rbp+20h] BYREF

  v24 = a3;
  v4 = a3;
  Status = 0;
  v25 = 0;
  memset(v22, 0, 32);
  v23 = 0;
  v7 = 0;
  if ( !*a2 )
  {
    v9 = *(struct _DEVICE_OBJECT **)(a1 + 64);
LABEL_7:
    v11 = *(unsigned __int8 *)(a1 + 41);
    if ( (_BYTE)v11 == 23 )
      v7 = BYTE1(v9[11].Queue.Wcb.NumberOfMapRegisters) != 0;
    if ( (v11 == 1 || v11 == 23) && !v7 )
    {
      KeWaitForSingleObject(&v9[10].Queue, Executive, 0, 0, 0);
      LOBYTE(v11) = *(_BYTE *)(a1 + 41);
    }
    if ( (_BYTE)v11 && ((_BYTE)v11 == 23 || (unsigned __int8)v11 <= 3u) && !v7 )
    {
      LOBYTE(a3) = 1;
      RefsAcquireExclusiveVcb(a1, v9, a3, a4);
      v23 = 1;
    }
    if ( !*a2 )
      goto LABEL_28;
    if ( *(_BYTE *)(a1 + 41) != 1 )
    {
      if ( *(_BYTE *)(a1 + 41) != 2 )
      {
        if ( *(_BYTE *)(a1 + 41) != 3 )
        {
          if ( *(_BYTE *)(a1 + 41) != 23 )
          {
            v12 = 0;
LABEL_20:
            Status = v12;
            goto LABEL_21;
          }
          v9->ReferenceCount |= 0x8000000u;
          v9->ReferenceCount &= ~0x10000u;
        }
LABEL_23:
        CurrentStackLocation = (*a2)->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
        *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                   + 6);
        CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
        CurrentStackLocation[-1].Control = 0;
        v22[0] = a1;
        v14 = (*a2)->Tail.Overlay.CurrentStackLocation;
        v14[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)RefsPnpCompletionRoutine;
        v14[-1].Context = v22;
        v14[-1].Control = 0;
        v14[-1].Control = 64;
        v14[-1].Control = -64;
        v14[-1].Control = -32;
        Status = RefsCallStorageDriver(*(_QWORD *)&v9->DeviceQueue.1, *a2, 0, &v25);
        if ( Status < 0 )
        {
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(Status);
          RefsExtendedCompleteRequestInternal(0, *a2, Status, v15);
          goto LABEL_26;
        }
        a4 = (unsigned int)v25;
        if ( !v25 )
        {
          Status = 0;
LABEL_26:
          *(_QWORD *)(a1 + 72) = 0;
          *a2 = 0;
          if ( Status == 259 )
          {
            KeWaitForSingleObject(&v22[1], Executive, 0, 0, 0);
            KeClearEvent((PRKEVENT)&v22[1]);
          }
LABEL_28:
          v16 = *(_BYTE *)(a1 + 41);
          if ( v16 == 3 )
          {
            v9->ReferenceCount &= ~0x8000000u;
            if ( (v9->ReferenceCount & 0x8000) != 0 )
            {
              if ( !*v4 )
              {
                *(_DWORD *)(a1 + 8) |= 0x10000u;
                _InterlockedAdd((volatile signed __int32 *)&v9->Dpc.ProcessorHistory + 1, 1u);
                *v4 = 1;
              }
              RefsUnlockVolumeInternal(a1, v9);
            }
          }
          else if ( v16 == 23 && !v7 && (v9->ReferenceCount & 1) != 0 )
          {
            if ( !*v4 )
            {
              *(_DWORD *)(a1 + 8) |= 0x10000u;
              _InterlockedAdd((volatile signed __int32 *)&v9->Dpc.ProcessorHistory + 1, 1u);
              *v4 = 1;
            }
            RefsPerformSurpriseRemoval(a1, v9);
          }
LABEL_103:
          if ( v23 )
            RefsReleaseVcbCheckDelete(a1, v9);
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(Status);
          RefsExtendedCompleteRequestInternal(a1, 0, Status, a4);
          return (unsigned int)Status;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          if ( v25 < 0 )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
LABEL_95:
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                16,
                WPP_e32f88d1ac52326e267dd435382f9434_Traceguids,
                (unsigned int)v25);
              goto LABEL_96;
            }
            v19 = 0;
          }
          else
          {
            v19 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
          }
          if ( v19 )
            goto LABEL_95;
        }
LABEL_96:
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(v25);
        Status = v25;
        goto LABEL_26;
      }
      if ( (v9->ReferenceCount & 0x8000) == 0 )
      {
        v12 = 0;
        goto LABEL_20;
      }
      v12 = RefsUnlockVolumeInternal(a1, v9);
      Status = v12;
LABEL_21:
      if ( v12 >= 0 )
      {
        v4 = v24;
        goto LABEL_23;
      }
LABEL_48:
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(Status);
      RefsExtendedCompleteRequestInternal(0, *a2, Status, a4);
      goto LABEL_103;
    }
    if ( (v9->ReferenceCount & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_e32f88d1ac52326e267dd435382f9434_Traceguids, 3221226094LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_47;
      goto LABEL_46;
    }
    if ( LODWORD(v9->Dpc.ProcessorHistory) || LODWORD(v9->Dpc.DeferredContext) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v12 = -1073741823;
      }
      else
      {
        v12 = -1073741823;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_e32f88d1ac52326e267dd435382f9434_Traceguids,
            3221225473LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741823);
      goto LABEL_20;
    }
    RefsFlushVolume(a1, v9, 15);
    _InterlockedAdd((volatile signed __int32 *)&v9->Dpc.ProcessorHistory + 1, 1u);
    ExReleaseResourceLite((PERESOURCE)&v9[4].Queue);
    CcWaitForCurrentLazyWriterActivity();
    LOBYTE(v17) = 1;
    RefsAcquireExclusiveVcb(a1, v9, v17, v18);
    _InterlockedDecrement((volatile signed __int32 *)&v9->Dpc.ProcessorHistory + 1);
    if ( (v9->ReferenceCount & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_e32f88d1ac52326e267dd435382f9434_Traceguids, 3221226094LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_47;
LABEL_46:
      RefsStatusDebug(-1073741202);
LABEL_47:
      Status = -1073741202;
      goto LABEL_48;
    }
    if ( LODWORD(v9->Dpc.ProcessorHistory) || LODWORD(v9->Dpc.DeferredContext) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_e32f88d1ac52326e267dd435382f9434_Traceguids, 3221225473LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_69;
    }
    else
    {
      if ( HIDWORD(v9->Dpc.ProcessorHistory) - HIDWORD(v9[7].Dpc.SystemArgument2) == HIDWORD(v9->Dpc.DeferredRoutine) )
      {
        v12 = RefsLockVolumeInternal(a1, (_DWORD)v9, 0, a4, 0);
        Status = v12;
        if ( v12 >= 0 )
          v9->ReferenceCount |= 0x8000000u;
        goto LABEL_21;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e32f88d1ac52326e267dd435382f9434_Traceguids, 3221225473LL);
      }
      if ( !RefsStatusDebugEnabled )
      {
LABEL_69:
        Status = -1073741823;
        goto LABEL_48;
      }
    }
    RefsStatusDebug(-1073741823);
    goto LABEL_69;
  }
  DeviceObject = (*a2)->Tail.Overlay.CurrentStackLocation->DeviceObject;
  if ( DeviceObject->Size == 8592 )
  {
    v9 = DeviceObject + 1;
    v10 = v9 ? (unsigned __int16)v9->Type : 0;
    if ( v10 == 2049 )
    {
      KeInitializeEvent((PRKEVENT)&v22[1], NotificationEvent, 0);
      goto LABEL_7;
    }
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741811);
  RefsExtendedCompleteRequestInternal(a1, *a2, -1073741811, a4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_e32f88d1ac52326e267dd435382f9434_Traceguids, 3221225485LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741811);
  return 3221225485LL;
}

```

## disassembly

```asm
0x1c0174fcc  mov     rax, rsp
0x1c0174fcf  mov     [rax+18h], r8
0x1c0174fd3  mov     [rax+8], rcx
0x1c0174fd7  push    rbx
0x1c0174fd8  push    rsi
0x1c0174fd9  push    rdi
0x1c0174fda  push    r12
0x1c0174fdc  push    r13
0x1c0174fde  push    r14
0x1c0174fe0  push    r15
0x1c0174fe2  sub     rsp, 60h
0x1c0174fe6  mov     rdi, r8
0x1c0174fe9  mov     r13, rdx
0x1c0174fec  mov     r14, rcx
0x1c0174fef  and     dword ptr [rax-68h], 0
0x1c0174ff3  and     dword ptr [rax+20h], 0
0x1c0174ff7  xorps   xmm0, xmm0
0x1c0174ffa  movups  xmmword ptr [rax-58h], xmm0
0x1c0174ffe  movups  xmmword ptr [rax-48h], xmm0
0x1c0175002  mov     [rsp+98h+arg_8], 0
0x1c017500a  xor     r12b, r12b
0x1c017500d  mov     rax, [rdx]
0x1c0175010  test    rax, rax
0x1c0175013  jz      loc_1C0188E80
0x1c0175019  mov     rax, [rax+0B8h]
0x1c0175020  mov     rbx, [rax+28h]
0x1c0175024  mov     eax, 2190h
0x1c0175029  cmp     [rbx+2], ax
0x1c017502d  jnz     loc_1C0188DEF
0x1c0175033  add     rbx, 150h
0x1c017503a  jz      loc_1C0188DE8
0x1c0175040  movzx   eax, word ptr [rbx]
0x1c0175043  cmp     eax, 801h
0x1c0175048  jnz     loc_1C0188DEF
0x1c017504e  mov     [rsp+98h+var_60], rbx
0x1c0175053  xor     r8d, r8d; State
0x1c0175056  xor     edx, edx; Type
0x1c0175058  lea     rcx, [rsp+98h+Event]; Event
0x1c017505d  call    cs:__imp_KeInitializeEvent
0x1c0175064  nop     dword ptr [rax+rax+00h]
0x1c0175069  movzx   ecx, byte ptr [r14+29h]
0x1c017506e  mov     r15d, 1
0x1c0175074  cmp     cl, 17h
0x1c0175077  jz      loc_1C01756BB
0x1c017507d  mov     edx, ecx
0x1c017507f  sub     edx, 1
0x1c0175082  jz      loc_1C01756CF
0x1c0175088  cmp     edx, 16h
0x1c017508b  jz      loc_1C01756CF
0x1c0175091  test    cl, cl
0x1c0175093  jz      short loc_1C01750A7
0x1c0175095  cmp     cl, 17h
0x1c0175098  jz      loc_1C0175702
0x1c017509e  cmp     cl, 3
0x1c01750a1  jbe     loc_1C0175702
0x1c01750a7  cmp     qword ptr [r13+0], 0
0x1c01750ac  jz      loc_1C01751B1
0x1c01750b2  movzx   ecx, byte ptr [r14+29h]
0x1c01750b7  sub     ecx, 1
0x1c01750ba  jz      loc_1C017524D
0x1c01750c0  sub     ecx, 1
0x1c01750c3  jz      loc_1C0175219
0x1c01750c9  sub     ecx, 1
0x1c01750cc  lea     rsi, WPP_GLOBAL_Control
0x1c01750d3  jz      loc_1C017520F
0x1c01750d9  cmp     ecx, 14h
0x1c01750dc  jz      loc_1C0175200
0x1c01750e2  xor     edi, edi
0x1c01750e4  mov     [rsp+98h+Status], edi
0x1c01750e8  test    edi, edi
0x1c01750ea  js      loc_1C01752C7
0x1c01750f0  mov     rdi, [rsp+98h+arg_10]
0x1c01750f8  mov     rax, [r13+0]
0x1c01750fc  mov     rcx, [rax+0B8h]
0x1c0175103  movups  xmm0, xmmword ptr [rcx]
0x1c0175106  movups  xmmword ptr [rcx-48h], xmm0
0x1c017510a  movups  xmm1, xmmword ptr [rcx+10h]
0x1c017510e  movups  xmmword ptr [rcx-38h], xmm1
0x1c0175112  movups  xmm0, xmmword ptr [rcx+20h]
0x1c0175116  movups  xmmword ptr [rcx-28h], xmm0
0x1c017511a  movsd   xmm1, qword ptr [rcx+30h]
0x1c017511f  movsd   qword ptr [rcx-18h], xmm1
0x1c0175124  mov     byte ptr [rcx-45h], 0
0x1c0175128  mov     [rsp+98h+var_58], r14
0x1c017512d  mov     rax, [r13+0]
0x1c0175131  mov     rcx, [rax+0B8h]
0x1c0175138  lea     rax, RefsPnpCompletionRoutine
0x1c017513f  mov     [rcx-10h], rax
0x1c0175143  lea     rax, [rsp+98h+var_58]
0x1c0175148  mov     [rcx-8], rax
0x1c017514c  mov     byte ptr [rcx-45h], 0
0x1c0175150  mov     byte ptr [rcx-45h], 40h ; '@'
0x1c0175154  mov     byte ptr [rcx-45h], 0C0h
0x1c0175158  mov     byte ptr [rcx-45h], 0E0h
0x1c017515c  lea     r9, [rsp+98h+arg_18]
0x1c0175164  xor     r8d, r8d
0x1c0175167  mov     rdx, [r13+0]
0x1c017516b  mov     rcx, [rbx+0C0h]
0x1c0175172  call    RefsCallStorageDriver
0x1c0175177  mov     [rsp+98h+Status], eax
0x1c017517b  test    eax, eax
0x1c017517d  js      loc_1C0175556
0x1c0175183  mov     r9d, [rsp+98h+arg_18]
0x1c017518b  test    r9d, r9d
0x1c017518e  jnz     loc_1C017558B
0x1c0175194  and     [rsp+98h+Status], r9d
0x1c0175199  and     qword ptr [r14+48h], 0
0x1c017519e  and     qword ptr [r13+0], 0
0x1c01751a3  cmp     [rsp+98h+Status], 103h
0x1c01751ab  jz      loc_1C0175604
0x1c01751b1  mov     al, [r14+29h]
0x1c01751b5  cmp     al, 3
0x1c01751b7  jz      loc_1C0175639
0x1c01751bd  cmp     al, 17h
0x1c01751bf  jnz     loc_1C0175669
0x1c01751c5  test    r12b, r12b
0x1c01751c8  jnz     loc_1C0175669
0x1c01751ce  mov     eax, [rbx+4]
0x1c01751d1  test    r15b, al
0x1c01751d4  jz      loc_1C0175669
0x1c01751da  cmp     [rdi], r12b
0x1c01751dd  jnz     short loc_1C01751F0
0x1c01751df  bts     dword ptr [r14+8], 10h
0x1c01751e5  lock add [rbx+0DCh], r15d
0x1c01751ed  mov     [rdi], r15b
0x1c01751f0  mov     rdx, rbx
0x1c01751f3  mov     rcx, r14
0x1c01751f6  call    RefsPerformSurpriseRemoval
0x1c01751fb  jmp     loc_1C0175669
0x1c0175200  bts     dword ptr [rbx+4], 1Bh
0x1c0175205  mov     eax, [rbx+4]
0x1c0175208  btr     eax, 10h
0x1c017520c  mov     [rbx+4], eax
0x1c017520f  and     [rsp+98h+Status], 0
0x1c0175214  jmp     loc_1C01750F8
0x1c0175219  mov     eax, [rbx+4]
0x1c017521c  bt      eax, 0Fh
0x1c0175220  jnb     short loc_1C017523F
0x1c0175222  mov     rdx, rbx
0x1c0175225  mov     rcx, r14
0x1c0175228  call    RefsUnlockVolumeInternal
0x1c017522d  mov     edi, eax
0x1c017522f  mov     [rsp+98h+Status], eax
0x1c0175233  lea     rsi, WPP_GLOBAL_Control
0x1c017523a  jmp     loc_1C01750E8
0x1c017523f  xor     edi, edi
0x1c0175241  lea     rsi, WPP_GLOBAL_Control
0x1c0175248  jmp     loc_1C01750E4
0x1c017524d  mov     eax, [rbx+4]
0x1c0175250  test    r15b, al
0x1c0175253  jnz     loc_1C01752FC
0x1c0175259  lea     rsi, WPP_GLOBAL_Control
0x1c0175260  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0175267  cmp     rcx, rsi
0x1c017526a  jz      short loc_1C0175296
0x1c017526c  mov     eax, [rcx+2Ch]
0x1c017526f  bt      eax, 8
0x1c0175273  jnb     short loc_1C0175296
0x1c0175275  cmp     byte ptr [rcx+29h], 4
0x1c0175279  jb      short loc_1C0175296
0x1c017527b  mov     edx, 0Bh
0x1c0175280  mov     r9d, 0C000026Eh
0x1c0175286  lea     r8, WPP_e32f88d1ac52326e267dd435382f9434_Traceguids
0x1c017528d  mov     rcx, [rcx+18h]
0x1c0175291  call    WPP_SF_D
0x1c0175296  mov     al, cs:RefsStatusDebugEnabled
0x1c017529c  test    al, al
0x1c017529e  jz      short loc_1C01752BF
0x1c01752a0  mov     r8d, 181h
0x1c01752a6  jmp     short loc_1C01752AE
0x1c01752a8  mov     r8d, 1C1h
0x1c01752ae  lea     rdx, aPnpC; "Pnp.c"
0x1c01752b5  mov     ecx, 0C000026Eh; Status
0x1c01752ba  call    RefsStatusDebug
0x1c01752bf  mov     [rsp+98h+Status], 0C000026Eh
0x1c01752c7  mov     al, cs:RefsStatusDebugEnabled
0x1c01752cd  test    al, al
0x1c01752cf  jz      short loc_1C01752E7
0x1c01752d1  mov     r8d, 239h
0x1c01752d7  lea     rdx, aPnpC; "Pnp.c"
0x1c01752de  mov     ecx, [rsp+98h+Status]; Status
0x1c01752e2  call    RefsStatusDebug
0x1c01752e7  mov     r8d, [rsp+98h+Status]
0x1c01752ec  mov     rdx, [r13+0]
0x1c01752f0  xor     ecx, ecx
0x1c01752f2  call    RefsExtendedCompleteRequestInternal
0x1c01752f7  jmp     loc_1C0175669
0x1c01752fc  cmp     dword ptr [rbx+0D8h], 0
0x1c0175303  ja      loc_1C01754E9
0x1c0175309  cmp     dword ptr [rbx+0E8h], 0
0x1c0175310  jnz     loc_1C01754E9
0x1c0175316  mov     edi, 0Fh
0x1c017531b  mov     r8d, edi
0x1c017531e  mov     rdx, rbx
0x1c0175321  mov     rcx, r14
0x1c0175324  call    RefsFlushVolume
0x1c0175329  lock add [rbx+0DCh], r15d
0x1c0175331  lea     rcx, [rbx+590h]; Resource
0x1c0175338  call    cs:__imp_ExReleaseResourceLite
0x1c017533f  nop     dword ptr [rax+rax+00h]
0x1c0175344  call    cs:__imp_CcWaitForCurrentLazyWriterActivity
0x1c017534b  nop     dword ptr [rax+rax+00h]
0x1c0175350  mov     r8b, r15b
0x1c0175353  mov     rdx, rbx
0x1c0175356  mov     rcx, r14
0x1c0175359  call    RefsAcquireExclusiveVcb
0x1c017535e  lock dec dword ptr [rbx+0DCh]
0x1c0175365  mov     eax, [rbx+4]
0x1c0175368  test    r15b, al
0x1c017536b  jnz     short loc_1C01753BB
0x1c017536d  lea     rsi, WPP_GLOBAL_Control
0x1c0175374  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017537b  cmp     rcx, rsi
0x1c017537e  jz      short loc_1C01753A8
0x1c0175380  mov     eax, [rcx+2Ch]
0x1c0175383  bt      eax, 8
0x1c0175387  jnb     short loc_1C01753A8
0x1c0175389  cmp     byte ptr [rcx+29h], 4
0x1c017538d  jb      short loc_1C01753A8
0x1c017538f  lea     edx, [rdi-2]
0x1c0175392  mov     r9d, 0C000026Eh
0x1c0175398  lea     r8, WPP_e32f88d1ac52326e267dd435382f9434_Traceguids
0x1c017539f  mov     rcx, [rcx+18h]
0x1c01753a3  call    WPP_SF_D
0x1c01753a8  mov     al, cs:RefsStatusDebugEnabled
0x1c01753ae  test    al, al
0x1c01753b0  jz      loc_1C01752BF
0x1c01753b6  jmp     loc_1C01752A8
0x1c01753bb  cmp     dword ptr [rbx+0D8h], 0
0x1c01753c2  ja      loc_1C0175490
0x1c01753c8  cmp     dword ptr [rbx+0E8h], 0
0x1c01753cf  jnz     loc_1C0175490
0x1c01753d5  mov     eax, [rbx+0A2Ch]
0x1c01753db  mov     ecx, [rbx+0DCh]
0x1c01753e1  sub     ecx, eax
0x1c01753e3  cmp     ecx, [rbx+0E4h]
0x1c01753e9  jz      short loc_1C017545D
0x1c01753eb  lea     rsi, WPP_GLOBAL_Control
0x1c01753f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01753f9  cmp     rcx, rsi
0x1c01753fc  jz      short loc_1C0175429
0x1c01753fe  mov     eax, [rcx+2Ch]
0x1c0175401  bt      eax, 8
0x1c0175405  jnb     short loc_1C0175429
0x1c0175407  cmp     byte ptr [rcx+29h], 4
0x1c017540b  jb      short loc_1C0175429
0x1c017540d  mov     edx, edi
0x1c017540f  mov     edi, 0C0000001h
0x1c0175414  mov     r9d, edi
0x1c0175417  lea     r8, WPP_e32f88d1ac52326e267dd435382f9434_Traceguids
0x1c017541e  mov     rcx, [rcx+18h]
0x1c0175422  call    WPP_SF_D
0x1c0175427  jmp     short loc_1C017542E
0x1c0175429  mov     edi, 0C0000001h
0x1c017542e  mov     al, cs:RefsStatusDebugEnabled
0x1c0175434  test    al, al
0x1c0175436  jz      short loc_1C0175454
0x1c0175438  mov     r8d, 1DCh
0x1c017543e  jmp     short loc_1C0175446
0x1c0175440  mov     r8d, 1D1h
0x1c0175446  lea     rdx, aPnpC; "Pnp.c"
0x1c017544d  mov     ecx, edi; Status
0x1c017544f  call    RefsStatusDebug
0x1c0175454  mov     [rsp+98h+Status], edi
0x1c0175458  jmp     loc_1C01752C7
0x1c017545d  and     [rsp+98h+var_78], 0
0x1c0175463  xor     r8d, r8d
0x1c0175466  mov     rdx, rbx
0x1c0175469  mov     rcx, r14
0x1c017546c  call    RefsLockVolumeInternal
0x1c0175471  mov     edi, eax
0x1c0175473  mov     [rsp+98h+Status], eax
0x1c0175477  lea     rsi, WPP_GLOBAL_Control
0x1c017547e  test    eax, eax
0x1c0175480  js      loc_1C01750E8
0x1c0175486  bts     dword ptr [rbx+4], 1Bh
0x1c017548b  jmp     loc_1C01750E8
0x1c0175490  lea     rsi, WPP_GLOBAL_Control
0x1c0175497  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017549e  cmp     rcx, rsi
0x1c01754a1  jz      short loc_1C01754D1
0x1c01754a3  mov     eax, [rcx+2Ch]
0x1c01754a6  bt      eax, 8
0x1c01754aa  jnb     short loc_1C01754D1
0x1c01754ac  cmp     byte ptr [rcx+29h], 4
0x1c01754b0  jb      short loc_1C01754D1
0x1c01754b2  mov     edx, 0Eh
0x1c01754b7  mov     edi, 0C0000001h
0x1c01754bc  mov     r9d, edi
0x1c01754bf  lea     r8, WPP_e32f88d1ac52326e267dd435382f9434_Traceguids
0x1c01754c6  mov     rcx, [rcx+18h]
0x1c01754ca  call    WPP_SF_D
0x1c01754cf  jmp     short loc_1C01754D6
0x1c01754d1  mov     edi, 0C0000001h
0x1c01754d6  mov     al, cs:RefsStatusDebugEnabled
0x1c01754dc  test    al, al
0x1c01754de  jz      loc_1C0175454
0x1c01754e4  jmp     loc_1C0175440
0x1c01754e9  lea     rsi, WPP_GLOBAL_Control
0x1c01754f0  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
