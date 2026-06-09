# CreateOneCollectionPdo

- ea: `0x180019014`
- end: `0x18001934a`
- name: `CreateOneCollectionPdo`
- size: `822`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003b69c`
- `0x18003f634`

## callees

- `0x180019014`
- `0x1800219bc`
- `0x1800226b8`
- `0x180028000`
- `0x18003fbbc`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18001919f`
- `ntoskrnl!MmBadPointer` at `0x1800192f9`
- `ntoskrnl!MmBadPointer` at `0x180019312`
- `ntoskrnl!ObfReferenceObject` at `0x180019153`
- `ntoskrnl!ObfReferenceObject` at `0x180019153`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x18001923b`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x18001923b`
- `ntoskrnl!IoCreateDevice` at `0x1800190a8`
- `ntoskrnl!IoCreateDevice` at `0x1800190a8`
- `ntoskrnl!KeInitializeSpinLock` at `0x180019253`
- `ntoskrnl!KeInitializeSpinLock` at `0x180019253`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019323`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019323`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800192c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800192c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800192a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800192a6`

## pseudocode

```c
__int64 __fastcall CreateOneCollectionPdo(__int64 a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  int v4; // esi
  __int64 v6; // r12
  ULONG v8; // esi
  __int64 v9; // r15
  PVOID ClientPDOName; // rbp
  unsigned int v12; // esi
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  bool v16; // r14
  KSPIN_LOCK *v17; // r9
  char v18; // cl
  KSPIN_LOCK *v19; // rdx
  bool v20; // al
  KSPIN_LOCK *v21; // r14
  __int64 v22; // rdx
  __int64 v23; // r15
  KIRQL v24; // al
  ULONG DeviceCharacteristics; // [rsp+20h] [rbp-88h]
  int Exclusive; // [rsp+28h] [rbp-80h]
  int DeviceObject; // [rsp+30h] [rbp-78h]
  ULONG Size; // [rsp+60h] [rbp-48h]
  PDEVICE_OBJECT v30; // [rsp+B0h] [rbp+8h] BYREF
  KSPIN_LOCK *DeviceExtension; // [rsp+B8h] [rbp+10h]
  unsigned int v32; // [rsp+C0h] [rbp+18h]

  v32 = a3;
  v4 = *(_DWORD *)(a1 + 24);
  v6 = *(_QWORD *)(a2 + 152);
  v30 = 0;
  v8 = v4 + 2328;
  v9 = 424LL * a3;
  Size = v8;
  ClientPDOName = (PVOID)MakeClientPDOName(a2 + 256, *(unsigned int *)(v9 + v6));
  if ( !ClientPDOName )
    return (unsigned int)-1073741801;
  v13 = IoCreateDevice(*(PDRIVER_OBJECT *)a1, v8, 0, 0x22u, 0x80u, 0, &v30);
  v12 = v13;
  if ( v13 < 0 )
  {
    TraceLoggingCreatePdoFailed(a2, *(unsigned int *)(v9 + v6), (unsigned int)v13);
    v16 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = v16;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qcdd(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        v15,
        *(_QWORD *)(a2 + 672),
        DeviceCharacteristics,
        Exclusive,
        DeviceObject);
    }
LABEL_16:
    if ( ClientPDOName != MmBadPointer )
      ExFreePoolWithTag(ClientPDOName, 0);
    return v12;
  }
  ObfReferenceObject(v30);
  v18 = *(_BYTE *)(*(_QWORD *)a2 + 76LL) + 1;
  DeviceExtension = (KSPIN_LOCK *)v30->DeviceExtension;
  v17 = DeviceExtension;
  v30->StackSize = v18;
  memset(v17, 0, Size);
  v19 = DeviceExtension;
  *(_OWORD *)DeviceExtension = *(_OWORD *)(a2 - 32);
  v19[2] = *(_QWORD *)(a2 - 32 + 16);
  *((_BYTE *)v19 + 24) = 1;
  *((_DWORD *)v19 + 7) = 1164207176;
  *((_DWORD *)v19 + 10) = *(_DWORD *)(v9 + v6);
  *((_DWORD *)v19 + 11) = v32;
  v19[10] = (KSPIN_LOCK)v30;
  *((_DWORD *)v19 + 9) = 1;
  v19[12] = a2 - 32;
  v19[19] = (KSPIN_LOCK)MmBadPointer;
  v19[11] = (KSPIN_LOCK)ClientPDOName;
  ClientPDOName = MmBadPointer;
  *((_DWORD *)v19 + 28) = *(_DWORD *)(a2 + 364);
  *((_DWORD *)v19 + 27) = *(_DWORD *)(a2 + 360);
  v20 = (unsigned int)(*(_DWORD *)(v9 + v6 + 12) - 1) <= 1;
  *((_BYTE *)v19 + 289) = 0;
  *((_BYTE *)v19 + 288) = v20;
  IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(v19 + 6), 0x43646948u, 0, 0, 0x20u);
  v21 = DeviceExtension;
  KeInitializeSpinLock(DeviceExtension + 15);
  v22 = v32;
  v21[16] = 0;
  v21[46] = 864000000000LL;
  v23 = (unsigned int)v22;
  *((_DWORD *)v21 + 34) = 0;
  *(_QWORD *)(*(_QWORD *)(a2 + 272) + 8 * v22 + 8) = v30;
  v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 2040));
  *(_QWORD *)(*(_QWORD *)(a2 + 288) + 8 * v23) = v21;
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 2040), v24);
  v30->Flags |= 0x2000u;
  v30->Flags |= 0x10u;
  v30->Flags &= ~0x80u;
  if ( a4 && a4 != MmBadPointer )
    *a4 = v21 + 4;
  if ( MmBadPointer )
    goto LABEL_16;
  return v12;
}

```

## disassembly

```asm
0x180019014  mov     rax, rsp
0x180019017  mov     [rax+20h], rbx
0x18001901b  mov     [rax+18h], r8d
0x18001901f  push    rbp
0x180019020  push    rsi
0x180019021  push    rdi
0x180019022  push    r12
0x180019024  push    r13
0x180019026  push    r14
0x180019028  push    r15
0x18001902a  sub     rsp, 70h
0x18001902e  mov     esi, [rcx+18h]
0x180019031  mov     rbx, rcx
0x180019034  mov     r12, [rdx+98h]
0x18001903b  lea     rcx, [rdx+100h]
0x180019042  mov     qword ptr [rax+8], 0
0x18001904a  mov     rdi, rdx
0x18001904d  mov     eax, r8d
0x180019050  add     esi, 918h
0x180019056  imul    r15, rax, 1A8h
0x18001905d  mov     r13, r9
0x180019060  mov     qword ptr [rsp+0A8h+Size], rsi
0x180019065  mov     edx, [r15+r12]
0x180019069  call    MakeClientPDOName
0x18001906e  mov     rbp, rax
0x180019071  test    rax, rax
0x180019074  jnz     short loc_180019080
0x180019076  mov     esi, 0C0000017h
0x18001907b  jmp     loc_18001932F
0x180019080  mov     rcx, [rbx]; DriverObject
0x180019083  lea     rax, [rsp+0A8h+arg_0]
0x18001908b  mov     qword ptr [rsp+0A8h+DeviceObject], rax; DeviceObject
0x180019090  mov     r9d, 22h ; '"'; DeviceType
0x180019096  mov     [rsp+0A8h+Exclusive], 0; Exclusive
0x18001909b  xor     r8d, r8d; DeviceName
0x18001909e  mov     edx, esi; DeviceExtensionSize
0x1800190a0  mov     [rsp+0A8h+DeviceCharacteristics], 80h; DeviceCharacteristics
0x1800190a8  call    cs:__imp_IoCreateDevice
0x1800190af  nop     dword ptr [rax+rax+00h]
0x1800190b4  mov     esi, eax
0x1800190b6  test    eax, eax
0x1800190b8  jns     loc_180019147
0x1800190be  mov     edx, [r15+r12]
0x1800190c2  mov     r8d, eax
0x1800190c5  mov     rcx, rdi
0x1800190c8  call    TraceLoggingCreatePdoFailed
0x1800190cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800190d4  lea     rax, WPP_GLOBAL_Control
0x1800190db  cmp     r10, rax
0x1800190de  jz      short loc_1800190F8
0x1800190e0  mov     ecx, [r10+2Ch]
0x1800190e4  test    cl, 8
0x1800190e7  jz      short loc_1800190F8
0x1800190e9  cmp     byte ptr [r10+29h], 3
0x1800190ee  jb      short loc_1800190F8
0x1800190f0  mov     r14d, 1
0x1800190f6  jmp     short loc_1800190FB
0x1800190f8  xor     r14b, r14b
0x1800190fb  lea     rax, WPP_RECORDER_INITIALIZED
0x180019102  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180019109  setnz   r8b
0x18001910d  test    r14b, r14b
0x180019110  jnz     short loc_18001911B
0x180019112  test    r8b, r8b
0x180019115  jz      loc_180019312
0x18001911b  mov     eax, [r15+r12]
0x18001911f  mov     dl, r14b
0x180019122  mov     r9, [rdi+2A0h]
0x180019129  mov     rcx, [r10+18h]
0x18001912d  mov     [rsp+0A8h+var_50], esi
0x180019131  mov     [rsp+0A8h+var_58], eax
0x180019135  mov     rax, [rdi]
0x180019138  mov     [rsp+0A8h+var_68], rax
0x18001913d  call    WPP_RECORDER_AND_TRACE_SF_qcdd
0x180019142  jmp     loc_180019312
0x180019147  mov     rcx, [rsp+0A8h+arg_0]; Object
0x18001914f  lea     rbx, [rdi-20h]
0x180019153  call    cs:__imp_ObfReferenceObject
0x18001915a  nop     dword ptr [rax+rax+00h]
0x18001915f  mov     rdx, [rsp+0A8h+arg_0]
0x180019167  mov     r14d, 1
0x18001916d  mov     rax, [rdi]
0x180019170  mov     r8d, [rsp+0A8h+Size]; Size
0x180019175  mov     r9, [rdx+40h]
0x180019179  mov     cl, [rax+4Ch]
0x18001917c  add     cl, r14b
0x18001917f  mov     [rsp+0A8h+arg_8], r9
0x180019187  mov     [rdx+4Ch], cl
0x18001918a  xor     edx, edx; Val
0x18001918c  mov     rcx, r9; void *
0x18001918f  call    memset
0x180019194  mov     rdx, [rsp+0A8h+arg_8]
0x18001919c  movups  xmm0, xmmword ptr [rbx]
0x18001919f  mov     rcx, cs:MmBadPointer
0x1800191a6  mov     [rsp+0A8h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x1800191ae  movups  xmmword ptr [rdx], xmm0
0x1800191b1  movsd   xmm1, qword ptr [rbx+10h]
0x1800191b6  movsd   qword ptr [rdx+10h], xmm1
0x1800191bb  mov     [rdx+18h], r14b
0x1800191bf  mov     dword ptr [rdx+1Ch], 45646448h
0x1800191c6  mov     eax, [r15+r12]
0x1800191ca  mov     [rdx+28h], eax
0x1800191cd  mov     eax, [rsp+0A8h+arg_10]
0x1800191d4  mov     [rdx+2Ch], eax
0x1800191d7  mov     rax, [rsp+0A8h+arg_0]
0x1800191df  mov     [rdx+50h], rax
0x1800191e3  mov     [rdx+24h], r14d
0x1800191e7  mov     [rdx+60h], rbx
0x1800191eb  mov     rax, [rcx]
0x1800191ee  mov     [rdx+98h], rax
0x1800191f5  mov     [rdx+58h], rbp
0x1800191f9  mov     rbp, [rcx]
0x1800191fc  lea     rcx, [rdx+30h]; Lock
0x180019200  mov     eax, [rdi+16Ch]
0x180019206  mov     [rdx+70h], eax
0x180019209  mov     eax, [rdi+168h]
0x18001920f  mov     [rdx+6Ch], eax
0x180019212  mov     eax, [r15+r12+0Ch]
0x180019217  sub     eax, r14d
0x18001921a  cmp     eax, r14d
0x18001921d  setbe   al
0x180019220  xor     r12d, r12d
0x180019223  mov     [rdx+121h], r12b
0x18001922a  xor     r9d, r9d; HighWatermark
0x18001922d  mov     [rdx+120h], al
0x180019233  xor     r8d, r8d; MaxLockedMinutes
0x180019236  mov     edx, 43646948h; AllocateTag
0x18001923b  call    cs:__imp_IoInitializeRemoveLockEx
0x180019242  nop     dword ptr [rax+rax+00h]
0x180019247  mov     r14, [rsp+0A8h+arg_8]
0x18001924f  lea     rcx, [r14+78h]; SpinLock
0x180019253  call    cs:__imp_KeInitializeSpinLock
0x18001925a  nop     dword ptr [rax+rax+00h]
0x18001925f  mov     edx, [rsp+0A8h+arg_10]
0x180019266  lea     rbx, [rdi+7F8h]
0x18001926d  mov     [r14+80h], r12
0x180019274  mov     rax, 0C92A69C000h
0x18001927e  mov     [r14+170h], rax
0x180019285  mov     r15d, edx
0x180019288  mov     [r14+88h], r12d
0x18001928f  mov     rcx, [rdi+110h]
0x180019296  mov     rax, [rsp+0A8h+arg_0]
0x18001929e  mov     [rcx+rdx*8+8], rax
0x1800192a3  mov     rcx, rbx; SpinLock
0x1800192a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1800192ad  nop     dword ptr [rax+rax+00h]
0x1800192b2  mov     rdx, [rdi+120h]
0x1800192b9  mov     rcx, rbx; SpinLock
0x1800192bc  mov     [rdx+r15*8], r14
0x1800192c0  mov     dl, al; NewIrql
0x1800192c2  call    cs:__imp_KeReleaseSpinLock
0x1800192c9  nop     dword ptr [rax+rax+00h]
0x1800192ce  mov     rax, [rsp+0A8h+arg_0]
0x1800192d6  bts     dword ptr [rax+30h], 0Dh
0x1800192db  mov     rax, [rsp+0A8h+arg_0]
0x1800192e3  or      dword ptr [rax+30h], 10h
0x1800192e7  mov     rax, [rsp+0A8h+arg_0]
0x1800192ef  btr     dword ptr [rax+30h], 7
0x1800192f4  test    r13, r13
0x1800192f7  jz      short loc_18001930D
0x1800192f9  mov     rax, cs:MmBadPointer
0x180019300  cmp     r13, [rax]
0x180019303  jz      short loc_18001930D
0x180019305  lea     rax, [r14+20h]
0x180019309  mov     [r13+0], rax
0x18001930d  test    rbp, rbp
0x180019310  jz      short loc_18001932F
0x180019312  mov     rax, cs:MmBadPointer
0x180019319  cmp     rbp, [rax]
0x18001931c  jz      short loc_18001932F
0x18001931e  xor     edx, edx; Tag
0x180019320  mov     rcx, rbp; P
0x180019323  call    cs:__imp_ExFreePoolWithTag
0x18001932a  nop     dword ptr [rax+rax+00h]
0x18001932f  mov     rbx, [rsp+0A8h+arg_18]
0x180019337  mov     eax, esi
0x180019339  add     rsp, 70h
0x18001933d  pop     r15
0x18001933f  pop     r14
0x180019341  pop     r13
0x180019343  pop     r12
0x180019345  pop     rdi
0x180019346  pop     rsi
0x180019347  pop     rbp
0x180019348  retn
```
