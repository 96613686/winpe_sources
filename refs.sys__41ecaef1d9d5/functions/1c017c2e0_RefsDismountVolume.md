# RefsDismountVolume

- ea: `0x1c017c2e0`
- end: `0x1c017c7ec`
- name: `RefsDismountVolume`
- size: `1292`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1c015c128`

## callees

- `0x1c00049a0`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c0063db0`
- `0x1c0066e38`
- `0x1c0068168`
- `0x1c015527c`
- `0x1c016d3c4`
- `0x1c0173a9c`
- `0x1c017c2e0`
- `0x1c017c7f4`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c017c651`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017c787`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0180d99`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017c651`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c017c787`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0180d99`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c017c3fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c017c3fc`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c017c40e`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c0180df0`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c018bf6d`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c017c40e`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c0180df0`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x1c018bf6d`
- `ntoskrnl!FsRtlDismountComplete` at `0x1c017c741`
- `ntoskrnl!FsRtlDismountComplete` at `0x1c0180d52`
- `ntoskrnl!FsRtlDismountComplete` at `0x1c017c741`
- `ntoskrnl!FsRtlDismountComplete` at `0x1c0180d52`

## pseudocode

```c
__int64 __fastcall RefsDismountVolume(__int64 a1, __int64 a2)
{
  char v4; // r14
  struct _FILE_OBJECT *v5; // r13
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdi
  char i; // bl
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // ecx
  __int64 v13; // rbx
  unsigned int Status; // [rsp+44h] [rbp-74h]
  char v16; // [rsp+48h] [rbp-70h]
  __int64 v17; // [rsp+50h] [rbp-68h] BYREF
  __int64 v18; // [rsp+58h] [rbp-60h] BYREF
  __int64 v19; // [rsp+60h] [rbp-58h] BYREF
  _QWORD v20[2]; // [rsp+68h] [rbp-50h] BYREF
  char v21; // [rsp+78h] [rbp-40h] BYREF
  __int64 v23; // [rsp+D8h] [rbp+20h] BYREF

  v16 = 0;
  v23 = 0;
  v20[0] = 0;
  v19 = 0;
  v4 = 1;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225473LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741823);
  *(_DWORD *)(a1 + 8) &= ~8u;
  v5 = *(struct _FILE_OBJECT **)(*(_QWORD *)(a2 + 184) + 48LL);
  v20[1] = v5;
  RefsDecodeFileObject(a1, (_DWORD)v5, (unsigned int)&v23, (unsigned int)&v21, (__int64)v20, (__int64)&v19, 1);
  if ( !v19 || (*(_WORD *)(v19 + 88) & 0x200) == 0 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790);
    RefsExtendedCompleteRequestInternal(a1, a2, 3221225506LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225506LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790);
    return 3221225506LL;
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x40000) == 0 )
  {
    KeWaitForSingleObject((PVOID)(v23 + 3440), Executive, 0, 0, 0);
    FsRtlNotifyVolumeEvent(v5, 1u);
  }
  v18 = MEMORY[0xFFFFF78000000320];
  v8 = v23;
  for ( i = 1; ; i = 0 )
  {
    LOBYTE(v6) = 1;
    RefsAcquireExclusiveVcb(a1, v8, v6, v7);
    if ( *(_DWORD *)(v8 + 232) )
    {
      if ( (*(_DWORD *)(v8 + 4) & 2) != 0 )
      {
        if ( *(_DWORD *)(v8 + 224) == *(_DWORD *)(v8 + 220) - *(_DWORD *)(v8 + 228) - 1 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 0);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(0);
          v11 = 0;
          Status = 0;
          v4 = v16;
          v8 = v23;
          goto LABEL_14;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v11 = -1073741790;
        }
        else
        {
          v11 = -1073741790;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            44,
            WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
            3221225506LL);
        }
        if ( !RefsStatusDebugEnabled )
        {
LABEL_25:
          Status = v11;
          v8 = v23;
          goto LABEL_59;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v11 = -1073741790;
        }
        else
        {
          v11 = -1073741790;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            42,
            WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
            3221225506LL);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_25;
      }
      RefsStatusDebug(-1073741790);
      goto LABEL_25;
    }
    v16 = 1;
    v10 = *(_DWORD *)(v8 + 4);
    if ( (v10 & 1) == 0 )
    {
      if ( (v10 & 0x800000) == 0 )
        goto LABEL_13;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221226094LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741202);
      v11 = -1073741202;
      goto LABEL_25;
    }
    if ( !i )
      break;
    ExReleaseResourceLite((PERESOURCE)(v8 + 1424));
  }
  v12 = *(_DWORD *)(a1 + 8);
  if ( (v12 & 0x40000) == 0 && (v10 & 0x2000000) == 0 )
  {
    *(_DWORD *)(a1 + 224) = 8;
    *(_DWORD *)(a1 + 8) = v12 | 0x40000;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225864LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741432);
    RefsRaiseStatusInternal(a1, 3221225864LL);
  }
  RefsFlushVolume(a1, v8, 95);
  RefsPerformDismountOnVcb(a1, v8, 0, 0, 0);
  *(_DWORD *)(v8 + 4) |= 2u;
  *(_QWORD *)(v8 + 832) = (char *)&v5->Type + 1;
  RefsSetDirectWritesAllowed(*(_QWORD *)(v8 + 208));
LABEL_13:
  v11 = 0;
  Status = 0;
LABEL_14:
  if ( v4 )
    *(_DWORD *)(v8 + 4) |= 0x800000u;
LABEL_59:
  FsRtlDismountComplete(*(_QWORD *)(v8 + 192), v11);
  v17 = MEMORY[0xFFFFF78000000320];
  v13 = v23;
  RefsTelemetryDismountTimeTracker(&v18, &v17, v23, Status);
  ExReleaseResourceLite((PERESOURCE)(v13 + 1424));
  if ( (int)(Status + 0x80000000) >= 0 && Status != -1073741202 )
    FsRtlNotifyVolumeEvent(v5, 2u);
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Status);
  RefsExtendedCompleteRequestInternal(a1, a2, Status);
  return Status;
}

```

## disassembly

```asm
0x1c017c2e0  mov     rax, rsp
0x1c017c2e3  mov     [rax+10h], rdx
0x1c017c2e7  mov     [rax+8], rcx
0x1c017c2eb  push    rbx
0x1c017c2ec  push    rsi
0x1c017c2ed  push    rdi
0x1c017c2ee  push    r12
0x1c017c2f0  push    r13
0x1c017c2f2  push    r14
0x1c017c2f4  push    r15
0x1c017c2f6  sub     rsp, 80h
0x1c017c2fd  mov     rdi, rdx
0x1c017c300  mov     r15, rcx
0x1c017c303  xor     ebx, ebx
0x1c017c305  mov     [rax-78h], bl
0x1c017c308  mov     [rax-70h], bl
0x1c017c30b  mov     [rax+20h], rbx
0x1c017c30f  mov     [rax-50h], rbx
0x1c017c313  mov     [rax-58h], rbx
0x1c017c317  lea     r14d, [rbx+1]
0x1c017c31b  mov     [rax+18h], r14b
0x1c017c31f  mov     [rax-60h], rbx
0x1c017c323  lea     rax, WPP_GLOBAL_Control
0x1c017c32a  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017c331  mov     esi, 100h
0x1c017c336  cmp     rcx, rax
0x1c017c339  jz      short loc_1C017C344
0x1c017c33b  test    [rcx+2Ch], esi
0x1c017c33e  jnz     loc_1C018BF2E
0x1c017c344  mov     al, cs:RefsStatusDebugEnabled
0x1c017c34a  lea     r12, aFsctrlC; "FsCtrl.c"
0x1c017c351  test    al, al
0x1c017c353  jz      short loc_1C017C368
0x1c017c355  mov     r8d, 0C3Bh
0x1c017c35b  mov     rdx, r12
0x1c017c35e  mov     ecx, 0C0000001h; Status
0x1c017c363  call    RefsStatusDebug
0x1c017c368  mov     [rsp+0B8h+Status], 0C0000001h
0x1c017c370  and     dword ptr [r15+8], 0FFFFFFF7h
0x1c017c375  mov     rax, [rdi+0B8h]
0x1c017c37c  mov     r13, [rax+30h]
0x1c017c380  mov     [rsp+0B8h+var_48], r13
0x1c017c385  mov     [rsp+0B8h+var_88], r14b
0x1c017c38a  lea     rax, [rsp+0B8h+var_58]
0x1c017c38f  mov     [rsp+0B8h+var_90], rax
0x1c017c394  lea     rax, [rsp+0B8h+var_50]
0x1c017c399  mov     [rsp+0B8h+Timeout], rax
0x1c017c39e  lea     r9, [rsp+0B8h+var_40]
0x1c017c3a3  lea     r8, [rsp+0B8h+arg_18]
0x1c017c3ab  mov     rdx, r13
0x1c017c3ae  mov     rcx, r15
0x1c017c3b1  call    RefsDecodeFileObject
0x1c017c3b6  mov     rax, [rsp+0B8h+var_58]
0x1c017c3bb  test    rax, rax
0x1c017c3be  jz      loc_1C018BF7F
0x1c017c3c4  movzx   eax, word ptr [rax+58h]
0x1c017c3c8  mov     ecx, 200h
0x1c017c3cd  test    cx, ax
0x1c017c3d0  jz      loc_1C018BF7F
0x1c017c3d6  test    dword ptr [r15+8], 40000h
0x1c017c3de  jnz     short loc_1C017C41B
0x1c017c3e0  mov     rcx, [rsp+0B8h+arg_18]
0x1c017c3e8  add     rcx, 0D70h; Object
0x1c017c3ef  mov     [rsp+0B8h+Timeout], rbx; Timeout
0x1c017c3f4  xor     r9d, r9d; Alertable
0x1c017c3f7  xor     r8d, r8d; WaitMode
0x1c017c3fa  xor     edx, edx; WaitReason
0x1c017c3fc  call    cs:__imp_KeWaitForSingleObject
0x1c017c403  nop     dword ptr [rax+rax+00h]
0x1c017c408  mov     edx, r14d; EventCode
0x1c017c40b  mov     rcx, r13; FileObject
0x1c017c40e  call    cs:__imp_FsRtlNotifyVolumeEvent
0x1c017c415  nop     dword ptr [rax+rax+00h]
0x1c017c41a  nop
0x1c017c41b  mov     rax, 0FFFFF78000000320h
0x1c017c425  mov     rax, [rax]
0x1c017c428  mov     [rsp+0B8h+var_60], rax
0x1c017c42d  mov     rdi, [rsp+0B8h+arg_18]
0x1c017c435  mov     bl, [rsp+0B8h+arg_10]
0x1c017c43c  mov     r8b, r14b
0x1c017c43f  mov     rdx, rdi
0x1c017c442  mov     rcx, r15
0x1c017c445  call    RefsAcquireExclusiveVcb
0x1c017c44a  mov     [rsp+0B8h+var_78], r14b
0x1c017c44f  cmp     dword ptr [rdi+0E8h], 0
0x1c017c456  jnz     short loc_1C017C48C
0x1c017c458  mov     [rsp+0B8h+var_70], r14b
0x1c017c45d  mov     eax, [rdi+4]
0x1c017c460  test    r14b, al
0x1c017c463  jnz     loc_1C017C646
0x1c017c469  bt      eax, 17h
0x1c017c46d  jb      loc_1C017C5FA
0x1c017c473  xor     ebx, ebx
0x1c017c475  mov     [rsp+0B8h+Status], ebx
0x1c017c479  test    r14b, r14b
0x1c017c47c  jz      loc_1C017C738
0x1c017c482  bts     dword ptr [rdi+4], 17h
0x1c017c487  jmp     loc_1C017C738
0x1c017c48c  mov     eax, [rdi+4]
0x1c017c48f  test    al, 2
0x1c017c491  jnz     loc_1C017C526
0x1c017c497  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017c49e  lea     rax, WPP_GLOBAL_Control
0x1c017c4a5  cmp     rcx, rax
0x1c017c4a8  jz      short loc_1C017C4D4
0x1c017c4aa  test    [rcx+2Ch], esi
0x1c017c4ad  jz      short loc_1C017C4D4
0x1c017c4af  cmp     byte ptr [rcx+29h], 4
0x1c017c4b3  jb      short loc_1C017C4D4
0x1c017c4b5  mov     edx, 2Ah ; '*'
0x1c017c4ba  mov     ebx, 0C0000022h
0x1c017c4bf  mov     r9d, ebx
0x1c017c4c2  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c017c4c9  mov     rcx, [rcx+18h]
0x1c017c4cd  call    WPP_SF_D
0x1c017c4d2  jmp     short loc_1C017C4D9
0x1c017c4d4  mov     ebx, 0C0000022h
0x1c017c4d9  mov     al, cs:RefsStatusDebugEnabled
0x1c017c4df  test    al, al
0x1c017c4e1  jz      short loc_1C017C515
0x1c017c4e3  mov     r8d, 0C7Dh
0x1c017c4e9  jmp     short loc_1C017C4F1
0x1c017c4eb  mov     r8d, 0C8Eh
0x1c017c4f1  mov     rdx, r12
0x1c017c4f4  mov     ecx, ebx; Status
0x1c017c4f6  call    RefsStatusDebug
0x1c017c4fb  jmp     short loc_1C017C515
0x1c017c4fd  mov     r8d, 0CA8h
0x1c017c503  mov     rdx, r12
0x1c017c506  mov     ecx, 0C000026Eh; Status
0x1c017c50b  call    RefsStatusDebug
0x1c017c510  mov     ebx, 0C000026Eh
0x1c017c515  mov     [rsp+0B8h+Status], ebx
0x1c017c519  mov     rdi, [rsp+0B8h+arg_18]
0x1c017c521  jmp     loc_1C017C738
0x1c017c526  mov     ecx, [rdi+0DCh]
0x1c017c52c  sub     ecx, [rdi+0E4h]
0x1c017c532  sub     ecx, r14d
0x1c017c535  cmp     [rdi+0E0h], ecx
0x1c017c53b  jnz     short loc_1C017C5A5
0x1c017c53d  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017c544  lea     rax, WPP_GLOBAL_Control
0x1c017c54b  cmp     rcx, rax
0x1c017c54e  jz      short loc_1C017C573
0x1c017c550  test    [rcx+2Ch], esi
0x1c017c553  jz      short loc_1C017C573
0x1c017c555  cmp     byte ptr [rcx+29h], 5
0x1c017c559  jb      short loc_1C017C573
0x1c017c55b  mov     edx, 2Bh ; '+'
0x1c017c560  xor     r9d, r9d
0x1c017c563  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c017c56a  mov     rcx, [rcx+18h]
0x1c017c56e  call    WPP_SF_D
0x1c017c573  mov     al, cs:RefsStatusDebugEnabled
0x1c017c579  test    al, al
0x1c017c57b  jz      short loc_1C017C58D
0x1c017c57d  mov     r8d, 0C86h
0x1c017c583  mov     rdx, r12
0x1c017c586  xor     ecx, ecx; Status
0x1c017c588  call    RefsStatusDebug
0x1c017c58d  xor     ebx, ebx
0x1c017c58f  mov     [rsp+0B8h+Status], ebx
0x1c017c593  mov     r14b, [rsp+0B8h+var_70]
0x1c017c598  mov     rdi, [rsp+0B8h+arg_18]
0x1c017c5a0  jmp     loc_1C017C479
0x1c017c5a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017c5ac  lea     rax, WPP_GLOBAL_Control
0x1c017c5b3  cmp     rcx, rax
0x1c017c5b6  jz      short loc_1C017C5E2
0x1c017c5b8  test    [rcx+2Ch], esi
0x1c017c5bb  jz      short loc_1C017C5E2
0x1c017c5bd  cmp     byte ptr [rcx+29h], 4
0x1c017c5c1  jb      short loc_1C017C5E2
0x1c017c5c3  mov     edx, 2Ch ; ','
0x1c017c5c8  mov     ebx, 0C0000022h
0x1c017c5cd  mov     r9d, ebx
0x1c017c5d0  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c017c5d7  mov     rcx, [rcx+18h]
0x1c017c5db  call    WPP_SF_D
0x1c017c5e0  jmp     short loc_1C017C5E7
0x1c017c5e2  mov     ebx, 0C0000022h
0x1c017c5e7  mov     al, cs:RefsStatusDebugEnabled
0x1c017c5ed  test    al, al
0x1c017c5ef  jz      loc_1C017C515
0x1c017c5f5  jmp     loc_1C017C4EB
0x1c017c5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017c601  lea     rax, WPP_GLOBAL_Control
0x1c017c608  cmp     rcx, rax
0x1c017c60b  jz      short loc_1C017C633
0x1c017c60d  test    [rcx+2Ch], esi
0x1c017c610  jz      short loc_1C017C633
0x1c017c612  cmp     byte ptr [rcx+29h], 4
0x1c017c616  jb      short loc_1C017C633
0x1c017c618  mov     edx, 2Dh ; '-'
0x1c017c61d  mov     r9d, 0C000026Eh
0x1c017c623  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c017c62a  mov     rcx, [rcx+18h]
0x1c017c62e  call    WPP_SF_D
0x1c017c633  mov     al, cs:RefsStatusDebugEnabled
0x1c017c639  test    al, al
0x1c017c63b  jz      loc_1C017C510
0x1c017c641  jmp     loc_1C017C4FD
0x1c017c646  test    bl, bl
0x1c017c648  jz      short loc_1C017C669
0x1c017c64a  lea     rcx, [rdi+590h]; Resource
0x1c017c651  call    cs:__imp_ExReleaseResourceLite
0x1c017c658  nop     dword ptr [rax+rax+00h]
0x1c017c65d  mov     [rsp+0B8h+var_78], 0
0x1c017c662  xor     bl, bl
0x1c017c664  jmp     loc_1C017C43C
0x1c017c669  mov     ecx, [r15+8]
0x1c017c66d  mov     edx, 40000h
0x1c017c672  test    edx, ecx
0x1c017c674  jnz     short loc_1C017C6F0
0x1c017c676  bt      eax, 19h
0x1c017c67a  jb      short loc_1C017C6F0
0x1c017c67c  mov     dword ptr [r15+0E0h], 8
0x1c017c687  or      ecx, edx
0x1c017c689  mov     [r15+8], ecx
0x1c017c68d  mov     rcx, cs:WPP_GLOBAL_Control
0x1c017c694  lea     rax, WPP_GLOBAL_Control
0x1c017c69b  cmp     rcx, rax
0x1c017c69e  jz      short loc_1C017C6C6
0x1c017c6a0  test    [rcx+2Ch], esi
0x1c017c6a3  jz      short loc_1C017C6C6
0x1c017c6a5  cmp     byte ptr [rcx+29h], 4
0x1c017c6a9  jb      short loc_1C017C6C6
0x1c017c6ab  mov     edx, 2Eh ; '.'
0x1c017c6b0  mov     r9d, 0C0000188h
0x1c017c6b6  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c017c6bd  mov     rcx, [rcx+18h]
0x1c017c6c1  call    WPP_SF_D
0x1c017c6c6  mov     al, cs:RefsStatusDebugEnabled
0x1c017c6cc  test    al, al
0x1c017c6ce  jz      short loc_1C017C6E3
0x1c017c6d0  mov     r8d, 0CCAh
0x1c017c6d6  mov     rdx, r12
0x1c017c6d9  mov     ecx, 0C0000188h; Status
0x1c017c6de  call    RefsStatusDebug
0x1c017c6e3  mov     edx, 0C0000188h
0x1c017c6e8  mov     rcx, r15
0x1c017c6eb  call    RefsRaiseStatusInternal
0x1c017c6f0  mov     r8d, 5Fh ; '_'
0x1c017c6f6  mov     rdx, rdi
0x1c017c6f9  mov     rcx, r15
0x1c017c6fc  call    RefsFlushVolume
0x1c017c701  and     [rsp+0B8h+Timeout], 0
0x1c017c707  xor     r9d, r9d
0x1c017c70a  xor     r8d, r8d
0x1c017c70d  mov     rdx, rdi
0x1c017c710  mov     rcx, r15
0x1c017c713  call    RefsPerformDismountOnVcb
0x1c017c718  or      dword ptr [rdi+4], 2
0x1c017c71c  lea     rax, [r13+1]
0x1c017c720  mov     [rdi+340h], rax
0x1c017c727  mov     rcx, [rdi+0D0h]
0x1c017c72e  call    RefsSetDirectWritesAllowed
0x1c017c733  jmp     loc_1C017C473
0x1c017c738  mov     edx, ebx
0x1c017c73a  mov     rcx, [rdi+0C0h]
0x1c017c741  call    cs:__imp_FsRtlDismountComplete
0x1c017c748  nop     dword ptr [rax+rax+00h]
0x1c017c74d  mov     rax, 0FFFFF78000000320h
0x1c017c757  mov     rax, [rax]
0x1c017c75a  mov     [rsp+0B8h+var_68], rax
0x1c017c75f  mov     edi, [rsp+0B8h+Status]
0x1c017c763  mov     r9d, edi
0x1c017c766  mov     rbx, [rsp+0B8h+arg_18]
0x1c017c76e  mov     r8, rbx
0x1c017c771  lea     rdx, [rsp+0B8h+var_68]
0x1c017c776  lea     rcx, [rsp+0B8h+var_60]
0x1c017c77b  call    RefsTelemetryDismountTimeTracker
0x1c017c780  lea     rcx, [rbx+590h]; Resource
0x1c017c787  call    cs:__imp_ExReleaseResourceLite
0x1c017c78e  nop     dword ptr [rax+rax+00h]
0x1c017c793  mov     ecx, 80000000h
0x1c017c798  lea     eax, [rdi+rcx]
0x1c017c79b  test    ecx, eax
0x1c017c79d  jz      loc_1C018BF59
0x1c017c7a3  mov     al, cs:RefsStatusDebugEnabled
0x1c017c7a9  test    al, al
0x1c017c7ab  jz      short loc_1C017C7BF
0x1c017c7ad  mov     r8d, 0D24h
0x1c017c7b3  mov     rdx, r12
0x1c017c7b6  mov     ecx, [rsp+0B8h+Status]; Status
0x1c017c7ba  call    RefsStatusDebug
0x1c017c7bf  mov     r8d, [rsp+0B8h+Status]
0x1c017c7c4  mov     rdx, [rsp+0B8h+arg_8]
0x1c017c7cc  mov     rcx, r15
0x1c017c7cf  call    RefsExtendedCompleteRequestInternal
0x1c017c7d4  mov     eax, [rsp+0B8h+Status]
0x1c017c7d8  add     rsp, 80h
0x1c017c7df  pop     r15
0x1c017c7e1  pop     r14
0x1c017c7e3  pop     r13
0x1c017c7e5  pop     r12
0x1c017c7e7  pop     rdi
0x1c017c7e8  pop     rsi
0x1c017c7e9  pop     rbx
0x1c017c7ea  retn
  ... truncated ...
```
