# HidpPdoRemoveDevice

- ea: `0x18001a1cc`
- end: `0x18001a550`
- name: `HidpPdoRemoveDevice`
- size: `900`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003e5b0`

## callees

- `0x180009a78`
- `0x1800125c4`
- `0x18001a1cc`
- `0x18001e8ec`
- `0x180023924`
- `0x180027c80`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x18001a23e`
- `ntoskrnl!IoWMIRegistrationControl` at `0x18001a23e`
- `ntoskrnl!MmBadPointer` at `0x18001a203`
- `ntoskrnl!MmBadPointer` at `0x18001a26d`
- `ntoskrnl!MmBadPointer` at `0x18001a344`
- `ntoskrnl!MmBadPointer` at `0x18001a36e`
- `ntoskrnl!MmBadPointer` at `0x18001a392`
- `ntoskrnl!MmBadPointer` at `0x18001a45e`
- `ntoskrnl!MmBadPointer` at `0x18001a488`
- `ntoskrnl!ObfDereferenceObject` at `0x18001a49a`
- `ntoskrnl!ObfDereferenceObject` at `0x18001a49a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001a350`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001a46a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001a350`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18001a46a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001a362`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001a47c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001a362`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001a47c`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001a3b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001a3b0`
- `ntoskrnl!IoCancelIrp` at `0x18001a255`
- `ntoskrnl!IoCancelIrp` at `0x18001a255`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001a386`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001a386`
- `ntoskrnl!IoDeleteDevice` at `0x18001a4aa`
- `ntoskrnl!IoDeleteDevice` at `0x18001a4aa`

## pseudocode

```c
void __fastcall HidpPdoRemoveDevice(__int64 a1, __int64 a2, __int64 a3)
{
  char v5; // bl
  __int64 v6; // r8
  void (__fastcall *v7)(_QWORD, __int64); // rax
  IRP *v8; // rcx
  char *v9; // rdx
  char *v10; // rcx
  struct _UNICODE_STRING *v11; // rcx
  KIRQL v12; // al
  __int64 v13; // rdx
  __int64 v14; // rax
  struct _UNICODE_STRING *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax

  v5 = 1;
  v6 = (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(a1, a2, a3) != 0 ? 7 : 1;
  *(_DWORD *)(a2 + 4) = v6;
  v7 = *(void (__fastcall **)(_QWORD, __int64))(a2 + 120);
  if ( v7 && v7 != MmBadPointer )
    v7(*(_QWORD *)(a2 + 128), 2);
  if ( !*(_BYTE *)(a2 + 256) && *(int *)(a1 + 344) > 1 && *(int *)(a1 + 340) > 1 )
    IoWMIRegistrationControl(*(PDEVICE_OBJECT *)(a2 + 48), 2u);
  v8 = (IRP *)_InterlockedExchange64((volatile __int64 *)(a2 + 96), 0);
  if ( v8 )
    IoCancelIrp(v8);
  v9 = *(char **)(a1 + 152);
  if ( v9 && v9 != MmBadPointer )
  {
    v10 = &v9[424 * *(unsigned int *)(a2 + 12)];
    if ( v10[292] )
    {
      LOBYTE(v9) = 1;
      StopPollingLoop(v10, v9);
    }
    if ( !*(_BYTE *)(a2 + 73) )
      CompleteAllPendingReadsForPdo(a2, v9, v6);
  }
  if ( !*(_BYTE *)(a1 + 588) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v5 = 0;
    }
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = v5;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdq(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v9,
        v6,
        *(_QWORD *)(a1 + 672),
        4,
        2,
        38,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL),
        *(_DWORD *)(a2 + 8),
        *(_QWORD *)(a2 + 48));
    }
    v11 = *(struct _UNICODE_STRING **)(a2 + 56);
    if ( v11 )
    {
      if ( v11 != MmBadPointer )
      {
        RtlFreeUnicodeString(v11);
        ExFreePoolWithTag(*(PVOID *)(a2 + 56), 0);
        *(_QWORD *)(a2 + 56) = MmBadPointer;
      }
    }
    v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2040));
    *(_QWORD *)(*(_QWORD *)(a1 + 288) + 8LL * *(unsigned int *)(a2 + 12)) = MmBadPointer;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 2040), v12);
LABEL_39:
    ObfDereferenceObject(*(PVOID *)(a2 + 48));
    IoDeleteDevice(*(PDEVICE_OBJECT *)(a2 + 48));
    return;
  }
  if ( *(_BYTE *)(a2 + 73) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v5 = 0;
    }
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = *(_QWORD *)(a2 + 64);
      v14 = *(_QWORD *)(v13 + 32);
      LOBYTE(v13) = v5;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdq(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        v6,
        *(_QWORD *)(a1 + 672),
        4,
        2,
        39,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        v14,
        *(_DWORD *)(a2 + 8),
        *(_QWORD *)(a2 + 48));
    }
    v15 = *(struct _UNICODE_STRING **)(a2 + 56);
    if ( v15 && v15 != MmBadPointer )
    {
      RtlFreeUnicodeString(v15);
      ExFreePoolWithTag(*(PVOID *)(a2 + 56), 0);
      *(_QWORD *)(a2 + 56) = MmBadPointer;
    }
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v5 = 0;
  }
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v16 = *(_QWORD *)(a2 + 64);
    v17 = *(_QWORD *)(v16 + 32);
    LOBYTE(v16) = v5;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qdq(
      WPP_GLOBAL_Control->AttachedDevice,
      v16,
      v6,
      *(_QWORD *)(a1 + 672),
      4,
      2,
      40,
      (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
      v17,
      *(_DWORD *)(a2 + 8),
      *(_QWORD *)(a2 + 48));
  }
}

```

## disassembly

```asm
0x18001a1cc  push    rbx
0x18001a1ce  push    rsi
0x18001a1cf  push    rdi
0x18001a1d0  push    r14
0x18001a1d2  sub     rsp, 68h
0x18001a1d6  mov     rdi, rdx
0x18001a1d9  mov     rsi, rcx
0x18001a1dc  call    Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline
0x18001a1e1  neg     eax
0x18001a1e3  mov     ebx, 1
0x18001a1e8  sbb     r8d, r8d
0x18001a1eb  and     r8d, 6
0x18001a1ef  add     r8d, ebx
0x18001a1f2  lea     r14d, [rbx+1]
0x18001a1f6  mov     [rdi+4], r8d
0x18001a1fa  mov     rax, [rdi+78h]
0x18001a1fe  test    rax, rax
0x18001a201  jz      short loc_18001A21E
0x18001a203  mov     rcx, cs:MmBadPointer
0x18001a20a  cmp     rax, [rcx]
0x18001a20d  jz      short loc_18001A21E
0x18001a20f  mov     rcx, [rdi+80h]
0x18001a216  mov     edx, r14d
0x18001a219  call    _guard_dispatch_icall
0x18001a21e  cmp     byte ptr [rdi+100h], 0
0x18001a225  jnz     short loc_18001A24A
0x18001a227  cmp     [rsi+158h], ebx
0x18001a22d  jle     short loc_18001A24A
0x18001a22f  cmp     [rsi+154h], ebx
0x18001a235  jle     short loc_18001A24A
0x18001a237  mov     rcx, [rdi+30h]; DeviceObject
0x18001a23b  mov     edx, r14d; Action
0x18001a23e  call    cs:__imp_IoWMIRegistrationControl
0x18001a245  nop     dword ptr [rax+rax+00h]
0x18001a24a  xor     ecx, ecx
0x18001a24c  xchg    rcx, [rdi+60h]; Irp
0x18001a250  test    rcx, rcx
0x18001a253  jz      short loc_18001A261
0x18001a255  call    cs:__imp_IoCancelIrp
0x18001a25c  nop     dword ptr [rax+rax+00h]
0x18001a261  mov     rdx, [rsi+98h]
0x18001a268  test    rdx, rdx
0x18001a26b  jz      short loc_18001A2A4
0x18001a26d  mov     rax, cs:MmBadPointer
0x18001a274  cmp     rdx, [rax]
0x18001a277  jz      short loc_18001A2A4
0x18001a279  mov     eax, [rdi+0Ch]
0x18001a27c  imul    rcx, rax, 1A8h
0x18001a283  add     rcx, rdx
0x18001a286  cmp     byte ptr [rcx+124h], 0
0x18001a28d  jz      short loc_18001A296
0x18001a28f  mov     dl, bl
0x18001a291  call    StopPollingLoop
0x18001a296  cmp     byte ptr [rdi+49h], 0
0x18001a29a  jnz     short loc_18001A2A4
0x18001a29c  mov     rcx, rdi
0x18001a29f  call    CompleteAllPendingReadsForPdo
0x18001a2a4  cmp     byte ptr [rsi+24Ch], 0
0x18001a2ab  jnz     loc_18001A3C1
0x18001a2b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2b8  lea     rax, WPP_GLOBAL_Control
0x18001a2bf  cmp     rcx, rax
0x18001a2c2  jz      short loc_18001A2D2
0x18001a2c4  mov     eax, [rcx+2Ch]
0x18001a2c7  test    r14b, al
0x18001a2ca  jz      short loc_18001A2D2
0x18001a2cc  cmp     byte ptr [rcx+29h], 4
0x18001a2d0  jnb     short loc_18001A2D4
0x18001a2d2  xor     bl, bl
0x18001a2d4  lea     rax, WPP_RECORDER_INITIALIZED
0x18001a2db  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001a2e2  setnz   r8b
0x18001a2e6  test    bl, bl
0x18001a2e8  jnz     short loc_18001A2EF
0x18001a2ea  test    r8b, r8b
0x18001a2ed  jz      short loc_18001A33B
0x18001a2ef  mov     rax, [rdi+30h]
0x18001a2f3  mov     dl, bl
0x18001a2f5  mov     r9, [rdi+40h]
0x18001a2f9  mov     rcx, [rcx+18h]
0x18001a2fd  mov     [rsp+88h+var_38], rax
0x18001a302  mov     eax, [rdi+8]
0x18001a305  mov     [rsp+88h+var_40], eax
0x18001a309  mov     rax, [r9+20h]
0x18001a30d  mov     r9, [rsi+2A0h]
0x18001a314  mov     [rsp+88h+var_48], rax
0x18001a319  lea     rax, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18001a320  mov     [rsp+88h+var_50], rax
0x18001a325  mov     [rsp+88h+var_58], 26h ; '&'
0x18001a32c  mov     [rsp+88h+var_60], r14d
0x18001a331  mov     [rsp+88h+var_68], 4
0x18001a336  call    WPP_RECORDER_AND_TRACE_SF_qdq
0x18001a33b  mov     rcx, [rdi+38h]; UnicodeString
0x18001a33f  test    rcx, rcx
0x18001a342  jz      short loc_18001A37C
0x18001a344  mov     rax, cs:MmBadPointer
0x18001a34b  cmp     rcx, [rax]
0x18001a34e  jz      short loc_18001A37C
0x18001a350  call    cs:__imp_RtlFreeUnicodeString
0x18001a357  nop     dword ptr [rax+rax+00h]
0x18001a35c  mov     rcx, [rdi+38h]; P
0x18001a360  xor     edx, edx; Tag
0x18001a362  call    cs:__imp_ExFreePoolWithTag
0x18001a369  nop     dword ptr [rax+rax+00h]
0x18001a36e  mov     rax, cs:MmBadPointer
0x18001a375  mov     rcx, [rax]
0x18001a378  mov     [rdi+38h], rcx
0x18001a37c  lea     rbx, [rsi+7F8h]
0x18001a383  mov     rcx, rbx; SpinLock
0x18001a386  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001a38d  nop     dword ptr [rax+rax+00h]
0x18001a392  mov     rdx, cs:MmBadPointer
0x18001a399  mov     rcx, rbx; SpinLock
0x18001a39c  mov     r10d, [rdi+0Ch]
0x18001a3a0  mov     r9, [rsi+120h]
0x18001a3a7  mov     r8, [rdx]
0x18001a3aa  mov     dl, al; NewIrql
0x18001a3ac  mov     [r9+r10*8], r8
0x18001a3b0  call    cs:__imp_KeReleaseSpinLock
0x18001a3b7  nop     dword ptr [rax+rax+00h]
0x18001a3bc  jmp     loc_18001A496
0x18001a3c1  cmp     byte ptr [rdi+49h], 0
0x18001a3c5  jz      loc_18001A4BB
0x18001a3cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3d2  lea     rax, WPP_GLOBAL_Control
0x18001a3d9  cmp     rcx, rax
0x18001a3dc  jz      short loc_18001A3EC
0x18001a3de  mov     eax, [rcx+2Ch]
0x18001a3e1  test    r14b, al
0x18001a3e4  jz      short loc_18001A3EC
0x18001a3e6  cmp     byte ptr [rcx+29h], 4
0x18001a3ea  jnb     short loc_18001A3EE
0x18001a3ec  xor     bl, bl
0x18001a3ee  lea     rax, WPP_RECORDER_INITIALIZED
0x18001a3f5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001a3fc  setnz   r8b
0x18001a400  test    bl, bl
0x18001a402  jnz     short loc_18001A409
0x18001a404  test    r8b, r8b
0x18001a407  jz      short loc_18001A455
0x18001a409  mov     rax, [rdi+30h]
0x18001a40d  mov     rdx, [rdi+40h]
0x18001a411  mov     r9, [rsi+2A0h]
0x18001a418  mov     rcx, [rcx+18h]
0x18001a41c  mov     [rsp+88h+var_38], rax
0x18001a421  mov     eax, [rdi+8]
0x18001a424  mov     [rsp+88h+var_40], eax
0x18001a428  mov     rax, [rdx+20h]
0x18001a42c  mov     dl, bl
0x18001a42e  mov     [rsp+88h+var_48], rax
0x18001a433  lea     rax, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18001a43a  mov     [rsp+88h+var_50], rax
0x18001a43f  mov     [rsp+88h+var_58], 27h ; '''
0x18001a446  mov     [rsp+88h+var_60], r14d
0x18001a44b  mov     [rsp+88h+var_68], 4
0x18001a450  call    WPP_RECORDER_AND_TRACE_SF_qdq
0x18001a455  mov     rcx, [rdi+38h]; UnicodeString
0x18001a459  test    rcx, rcx
0x18001a45c  jz      short loc_18001A496
0x18001a45e  mov     rax, cs:MmBadPointer
0x18001a465  cmp     rcx, [rax]
0x18001a468  jz      short loc_18001A496
0x18001a46a  call    cs:__imp_RtlFreeUnicodeString
0x18001a471  nop     dword ptr [rax+rax+00h]
0x18001a476  mov     rcx, [rdi+38h]; P
0x18001a47a  xor     edx, edx; Tag
0x18001a47c  call    cs:__imp_ExFreePoolWithTag
0x18001a483  nop     dword ptr [rax+rax+00h]
0x18001a488  mov     rax, cs:MmBadPointer
0x18001a48f  mov     rcx, [rax]
0x18001a492  mov     [rdi+38h], rcx
0x18001a496  mov     rcx, [rdi+30h]; Object
0x18001a49a  call    cs:__imp_ObfDereferenceObject
0x18001a4a1  nop     dword ptr [rax+rax+00h]
0x18001a4a6  mov     rcx, [rdi+30h]; DeviceObject
0x18001a4aa  call    cs:__imp_IoDeleteDevice
0x18001a4b1  nop     dword ptr [rax+rax+00h]
0x18001a4b6  jmp     loc_18001A545
0x18001a4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4c2  lea     rax, WPP_GLOBAL_Control
0x18001a4c9  cmp     rcx, rax
0x18001a4cc  jz      short loc_18001A4DC
0x18001a4ce  mov     eax, [rcx+2Ch]
0x18001a4d1  test    r14b, al
0x18001a4d4  jz      short loc_18001A4DC
0x18001a4d6  cmp     byte ptr [rcx+29h], 4
0x18001a4da  jnb     short loc_18001A4DE
0x18001a4dc  xor     bl, bl
0x18001a4de  lea     rax, WPP_RECORDER_INITIALIZED
0x18001a4e5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001a4ec  setnz   r8b
0x18001a4f0  test    bl, bl
0x18001a4f2  jnz     short loc_18001A4F9
0x18001a4f4  test    r8b, r8b
0x18001a4f7  jz      short loc_18001A545
0x18001a4f9  mov     rax, [rdi+30h]
0x18001a4fd  mov     rdx, [rdi+40h]
0x18001a501  mov     r9, [rsi+2A0h]
0x18001a508  mov     rcx, [rcx+18h]
0x18001a50c  mov     [rsp+88h+var_38], rax
0x18001a511  mov     eax, [rdi+8]
0x18001a514  mov     [rsp+88h+var_40], eax
0x18001a518  mov     rax, [rdx+20h]
0x18001a51c  mov     dl, bl
0x18001a51e  mov     [rsp+88h+var_48], rax
0x18001a523  lea     rax, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18001a52a  mov     [rsp+88h+var_50], rax
0x18001a52f  mov     [rsp+88h+var_58], 28h ; '('
0x18001a536  mov     [rsp+88h+var_60], r14d
0x18001a53b  mov     [rsp+88h+var_68], 4
0x18001a540  call    WPP_RECORDER_AND_TRACE_SF_qdq
0x18001a545  add     rsp, 68h
0x18001a549  pop     r14
0x18001a54b  pop     rdi
0x18001a54c  pop     rsi
0x18001a54d  pop     rbx
0x18001a54e  retn
```
