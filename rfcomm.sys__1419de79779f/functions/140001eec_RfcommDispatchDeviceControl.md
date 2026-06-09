# RfcommDispatchDeviceControl

- ea: `0x140001eec`
- end: `0x140002564`
- name: `RfcommDispatchDeviceControl`
- size: `1656`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140005cfc`

## callees

- `0x140001eec`
- `0x140003970`
- `0x140003bf4`
- `0x140003cb4`
- `0x140005c38`
- `0x140014c64`
- `0x14001513c`
- `0x1400152ec`
- `0x14001ea34`
- `0x14001ec2c`
- `0x14001ed50`
- `0x140033edc`
- `0x140034048`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400022ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002327`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400024a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400022ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002327`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400024a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400024d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400024d1`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14000224c`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14000224c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400022d2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400022d2`

## string_xrefs

- `0x1400024eb`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`
- `0x140002512`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`

## pseudocode

```c
__int64 __fastcall RfcommDispatchDeviceControl(__int64 a1, IRP *a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // ebx
  _IRP *MasterIrp; // rsi
  __int64 v7; // rax
  unsigned __int32 v8; // edx
  __int64 v9; // r15
  PEPROCESS v10; // r14
  NTSTATUS v11; // edi
  unsigned __int32 v12; // r8d
  unsigned __int32 v13; // r9d
  unsigned __int32 v14; // eax
  bool v15; // cc
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  int v18; // r9d
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  unsigned int v22; // ebx
  void *v23; // rcx
  int v24; // edx
  char v25; // bl
  char v26; // r13
  __int64 v27; // rsi
  void *v28; // rcx
  KSPIN_LOCK *v29; // rcx
  KIRQL v30; // dl
  __int64 v31; // rbx
  __int64 v32; // rbx
  int v33; // edx
  int v34; // eax
  __int64 v35; // rbx
  __int64 v36; // rdx
  int v38; // [rsp+20h] [rbp-28h]
  int v39; // [rsp+30h] [rbp-18h]
  __int64 v40; // [rsp+38h] [rbp-10h]
  __int64 v41; // [rsp+90h] [rbp+48h] BYREF
  __int64 v42; // [rsp+98h] [rbp+50h] BYREF
  PEPROCESS Process; // [rsp+A0h] [rbp+58h] BYREF
  _QWORD *v44; // [rsp+A8h] [rbp+60h]

  v44 = (_QWORD *)a4;
  v5 = *(_DWORD *)(a3 + 24);
  v40 = *(_QWORD *)(a1 + 64);
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  v42 = 0;
  v41 = 0;
  Process = 0;
  v7 = RfcommValidateIoctl((unsigned int)&Process, a3, (unsigned int)&v41, (unsigned int)&v42, (__int64)&Process, a4);
  v9 = v41;
  v10 = Process;
  if ( !v7 )
    goto LABEL_2;
  v11 = 0;
  if ( v5 > 0x120090 )
  {
    v19 = v5 - 1179796;
    if ( !v19 )
    {
      *(_DWORD *)&MasterIrp->Type = 0;
      v35 = *((_QWORD *)v10 + 7);
      *(_BYTE *)(v35 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v35 + 56));
      if ( (*(_DWORD *)(*((_QWORD *)v10 + 7) + 296LL) & 2) != 0 )
        *(_DWORD *)&MasterIrp->Type = 1;
      goto LABEL_104;
    }
    v20 = v19 - 4;
    if ( !v20 )
    {
      _InterlockedExchange((volatile __int32 *)(v41 + 216), *(_DWORD *)&MasterIrp->Type != 0);
      goto LABEL_106;
    }
    v21 = v20 - 288;
    if ( v21 )
    {
      v22 = v21 - 4;
      if ( v22 )
      {
        if ( v22 != 360 )
        {
LABEL_61:
          v11 = -1073741822;
          goto LABEL_106;
        }
        if ( !(unsigned __int8)IsCallingProcess(`IsCallingProcessBthservEx'::`2'::s_sdBthserv) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v8,
              3,
              93,
              (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
          v11 = -1073741790;
          goto LABEL_106;
        }
        v23 = (void *)*(unsigned int *)&MasterIrp->Type;
        v39 = *(_DWORD *)&MasterIrp->Type;
        Process = 0;
        v11 = PsLookupProcessByProcessId(v23, &Process);
        if ( v11 < 0 )
        {
LABEL_106:
          if ( v10 )
            RefObj_ReleaseEx(
              (char *)v10 + 24,
              1145981254,
              2157,
              "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
          goto LABEL_108;
        }
        LOBYTE(v41) = 0;
        v25 = 1;
        if ( (int)QueryIsAppContainer(Process, &v41) >= 0 )
        {
          v26 = v41;
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v24,
              3,
              94,
              (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
          v26 = 1;
        }
        v27 = v42;
        *(_BYTE *)(v27 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v42 + 48));
        v28 = *(void **)(v27 + 88);
        if ( v28 )
        {
          ObfDereferenceObject(v28);
          *(_QWORD *)(v27 + 88) = 0;
        }
        *(_DWORD *)(v27 + 824) = v39;
        *(_QWORD *)(v27 + 88) = Process;
        if ( *(_BYTE *)(*(_QWORD *)(v40 + 80) + 48LL) || !v26 )
          v25 = 0;
        *(_BYTE *)(v27 + 828) = v25;
        v29 = (KSPIN_LOCK *)(v27 + 48);
        v30 = *(_BYTE *)(v27 + 56);
LABEL_105:
        KeReleaseSpinLock(v29, v30);
        goto LABEL_106;
      }
      v31 = *((_QWORD *)Process + 7);
      *(_BYTE *)(v31 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v31 + 56));
      if ( _InterlockedExchange((volatile __int32 *)v10 + 51, 0) )
      {
        *(_DWORD *)&MasterIrp->Type = 1;
        *(&MasterIrp->Size + 1) = *((_WORD *)v10 + 104);
      }
      else if ( _InterlockedExchange((volatile __int32 *)v10 + 49, 0) )
      {
        *(_DWORD *)&MasterIrp->Type = 2;
        *((_BYTE *)&MasterIrp->Size + 2) = *((_BYTE *)v10 + 200);
      }
      else
      {
        v11 = IrpList_EnqueueEx(v42 + 736, a2);
      }
LABEL_104:
      v36 = *((_QWORD *)v10 + 7);
      v29 = (KSPIN_LOCK *)(v36 + 56);
      v30 = *(_BYTE *)(v36 + 64);
      goto LABEL_105;
    }
    v32 = v42;
    v41 = v42 + 680;
    v11 = IrpList_EnqueueEx(v42 + 680, a2);
    if ( v11 < 0 )
      goto LABEL_106;
    switch ( *(_DWORD *)&MasterIrp->Type )
    {
      case 1:
        v33 = v42;
        LOBYTE(v38) = 1;
        break;
      case 2:
        v34 = RfcommSendMsgRLS(v10, v32, a2, &MasterIrp->Size + 1);
        goto LABEL_98;
      case 3:
      case 4:
      case 5:
        v34 = RfcommSendMsgRPN(v10, v32, a2, MasterIrp);
        goto LABEL_98;
      case 6:
        LOBYTE(v38) = 0;
        v33 = v32;
        break;
      default:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            3,
            89,
            (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
            *(_DWORD *)&MasterIrp->Type);
        goto LABEL_99;
    }
    v34 = RfcommSendMsgMSC((_DWORD)v10, v33, (_DWORD)a2, (int)MasterIrp + 4, v38);
LABEL_98:
    if ( v34 >= 0 )
      goto LABEL_106;
LABEL_99:
    if ( (unsigned __int8)IrpList_DequeueIrp(v41, a2) )
      RfcommCompleteTdiIrp(a2);
    goto LABEL_106;
  }
  switch ( v5 )
  {
    case 0x120090u:
      if ( *(_DWORD *)&MasterIrp->Type == 1 )
      {
        *(_DWORD *)(v41 + 204) |= 2u;
        goto LABEL_106;
      }
LABEL_2:
      v11 = -1073741808;
      goto LABEL_106;
    case 0x120030u:
      if ( *(_DWORD *)&MasterIrp->Type )
      {
        *(_DWORD *)(v41 + 212) |= 0x20000u;
        goto LABEL_106;
      }
      goto LABEL_2;
    case 0x120034u:
      if ( *(_DWORD *)&MasterIrp->Type )
      {
        *(_DWORD *)(v41 + 212) |= 0x40000u;
        goto LABEL_106;
      }
      goto LABEL_2;
    case 0x12006Cu:
      *(_DWORD *)&MasterIrp->Type = *((unsigned __int16 *)Process + 116);
      *v44 = 4;
      goto LABEL_106;
  }
  if ( v5 != 1179760 && v5 != 1179764 && v5 != 1179768 )
    goto LABEL_61;
  if ( Process )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        3,
        84,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
    goto LABEL_2;
  }
  v9 = v41;
  v12 = _InterlockedCompareExchange((volatile signed __int32 *)(v41 + 192), 0, 0);
  v13 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 196), 0, 0);
  v14 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 200), 0, 0);
  v8 = *(_DWORD *)&MasterIrp->Type;
  if ( (*(_DWORD *)(v9 + 204) & 2) != 0 )
    v15 = v8 <= 0x3F0;
  else
    v15 = v8 <= 0x3F3;
  if ( v15 && v8 >= 0x17 )
  {
    v16 = v5 - 1179760;
    if ( !v16 )
    {
      if ( (!v12 || v8 <= v12) && (!v13 || v8 >= v13) )
      {
        v8 = _InterlockedExchange((volatile __int32 *)(v9 + 200), v8);
        goto LABEL_45;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_36;
      v18 = 88;
      goto LABEL_35;
    }
    v17 = v16 - 4;
    if ( v17 )
    {
      if ( v17 == 4 )
      {
        if ( v12 && v8 > v12 || v14 && v8 > v14 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
LABEL_36:
            v11 = -1073741808;
            goto LABEL_45;
          }
          v18 = 87;
LABEL_35:
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            3,
            v18,
            (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
          goto LABEL_36;
        }
        v8 = _InterlockedExchange((volatile __int32 *)(v9 + 196), v8);
      }
LABEL_45:
      *v44 = 0;
      goto LABEL_108;
    }
    if ( (!v14 || v8 >= v14) && (!v13 || v8 >= v13) )
    {
      v8 = _InterlockedExchange((volatile __int32 *)(v9 + 192), v8);
      goto LABEL_45;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_36;
    v18 = 86;
    goto LABEL_35;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      3,
      85,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
  v11 = -1073741808;
LABEL_108:
  if ( v9 )
    RefObj_ReleaseEx(v9 + 24, 1145981254, 2162, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      3,
      95,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140001eec  mov     [rsp-40h+arg_18], r9
0x140001ef1  push    rbp
0x140001ef2  push    rbx
0x140001ef3  push    rsi
0x140001ef4  push    rdi
0x140001ef5  push    r12
0x140001ef7  push    r13
0x140001ef9  push    r14
0x140001efb  push    r15
0x140001efd  mov     rbp, rsp
0x140001f00  sub     rsp, 48h
0x140001f04  mov     rcx, [rcx+40h]
0x140001f08  mov     r13, rdx
0x140001f0b  mov     ebx, [r8+18h]
0x140001f0f  xor     edx, edx
0x140001f11  mov     rax, r8
0x140001f14  mov     [rsp+48h+var_20], r9
0x140001f19  mov     [rbp+var_10], rcx
0x140001f1d  lea     r9, [rbp+arg_8]
0x140001f21  mov     rsi, [r13+18h]
0x140001f25  lea     rcx, [rbp+Process]
0x140001f29  mov     [rbp+arg_8], rdx
0x140001f2d  lea     r8, [rbp+arg_0]
0x140001f31  mov     [rbp+arg_0], rdx
0x140001f35  mov     [rbp+Process], rdx
0x140001f39  mov     rdx, rax
0x140001f3c  mov     [rsp+48h+var_28], rcx
0x140001f41  call    RfcommValidateIoctl
0x140001f46  mov     r15, [rbp+arg_0]
0x140001f4a  lea     r12, WPP_RECORDER_INITIALIZED
0x140001f51  mov     r14, [rbp+Process]
0x140001f55  lea     rcx, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140001f5c  test    rax, rax
0x140001f5f  jnz     short loc_140001F6B
0x140001f61  mov     edi, 0C0000010h
0x140001f66  jmp     loc_1400024DD
0x140001f6b  xor     edi, edi
0x140001f6d  mov     eax, 120090h
0x140001f72  cmp     ebx, eax
0x140001f74  ja      loc_1400021B5
0x140001f7a  jz      loc_14000219B
0x140001f80  mov     eax, ebx
0x140001f82  sub     eax, 120030h
0x140001f87  jz      loc_140002185
0x140001f8d  sub     eax, 4
0x140001f90  jz      loc_14000216F
0x140001f96  sub     eax, 38h ; '8'
0x140001f99  jz      loc_140002155
0x140001f9f  sub     eax, 4
0x140001fa2  jz      short loc_140001FB2
0x140001fa4  sub     eax, 4
0x140001fa7  jz      short loc_140001FB2
0x140001fa9  cmp     eax, 4
0x140001fac  jnz     loc_1400021E7
0x140001fb2  test    r14, r14
0x140001fb5  jz      short loc_140001FE1
0x140001fb7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140001fbe  jz      short loc_140001F61
0x140001fc0  mov     [rsp+48h+var_28], rcx
0x140001fc5  mov     r9d, 54h ; 'T'
0x140001fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140001fd2  lea     r8d, [r9-51h]
0x140001fd6  mov     rcx, [rcx+40h]
0x140001fda  call    WPP_RECORDER_SF_
0x140001fdf  jmp     short loc_140001F61
0x140001fe1  mov     r15, [rbp+arg_0]
0x140001fe5  xor     ecx, ecx
0x140001fe7  xor     eax, eax
0x140001fe9  lock cmpxchg [r15+0C0h], ecx
0x140001ff2  mov     r8d, eax
0x140001ff5  xor     eax, eax
0x140001ff7  lock cmpxchg [r15+0C4h], ecx
0x140002000  mov     r9d, eax
0x140002003  xor     eax, eax
0x140002005  lock cmpxchg [r15+0C8h], ecx
0x14000200e  mov     ecx, [r15+0CCh]
0x140002015  mov     edx, [rsi]
0x140002017  test    cl, 2
0x14000201a  jz      short loc_140002024
0x14000201c  cmp     edx, 3F0h
0x140002022  jmp     short loc_14000202A
0x140002024  cmp     edx, 3F3h
0x14000202a  ja      loc_140002115
0x140002030  cmp     edx, 17h
0x140002033  jb      loc_140002115
0x140002039  lea     r12, WPP_RECORDER_INITIALIZED
0x140002040  lea     rsi, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140002047  sub     ebx, 120070h
0x14000204d  jz      loc_1400020D9
0x140002053  sub     ebx, 4
0x140002056  jz      short loc_14000208D
0x140002058  cmp     ebx, 4
0x14000205b  jnz     loc_140002105
0x140002061  test    r8d, r8d
0x140002064  jz      short loc_14000206B
0x140002066  cmp     edx, r8d
0x140002069  ja      short loc_140002073
0x14000206b  test    eax, eax
0x14000206d  jz      short loc_140002084
0x14000206f  cmp     edx, eax
0x140002071  jbe     short loc_140002084
0x140002073  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000207a  jz      short loc_1400020C9
0x14000207c  mov     r9d, 57h ; 'W'
0x140002082  jmp     short loc_1400020AE
0x140002084  xchg    edx, [r15+0C4h]
0x14000208b  jmp     short loc_140002105
0x14000208d  test    eax, eax
0x14000208f  jz      short loc_140002095
0x140002091  cmp     edx, eax
0x140002093  jb      short loc_14000209F
0x140002095  test    r9d, r9d
0x140002098  jz      short loc_1400020D0
0x14000209a  cmp     edx, r9d
0x14000209d  jnb     short loc_1400020D0
0x14000209f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400020a6  jz      short loc_1400020C9
0x1400020a8  mov     r9d, 56h ; 'V'
0x1400020ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020b5  mov     r8d, 3
0x1400020bb  mov     [rsp+48h+var_28], rsi
0x1400020c0  mov     rcx, [rcx+40h]
0x1400020c4  call    WPP_RECORDER_SF_
0x1400020c9  mov     edi, 0C0000010h
0x1400020ce  jmp     short loc_140002105
0x1400020d0  xchg    edx, [r15+0C0h]
0x1400020d7  jmp     short loc_140002105
0x1400020d9  test    r8d, r8d
0x1400020dc  jz      short loc_1400020E3
0x1400020de  cmp     edx, r8d
0x1400020e1  ja      short loc_1400020ED
0x1400020e3  test    r9d, r9d
0x1400020e6  jz      short loc_1400020FE
0x1400020e8  cmp     edx, r9d
0x1400020eb  jnb     short loc_1400020FE
0x1400020ed  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400020f4  jz      short loc_1400020C9
0x1400020f6  mov     r9d, 58h ; 'X'
0x1400020fc  jmp     short loc_1400020AE
0x1400020fe  xchg    edx, [r15+0C8h]
0x140002105  mov     rax, [rbp+arg_18]
0x140002109  mov     qword ptr [rax], 0
0x140002110  jmp     loc_140002504
0x140002115  lea     r12, WPP_RECORDER_INITIALIZED
0x14000211c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002123  lea     rsi, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14000212a  jz      short loc_14000214B
0x14000212c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002133  mov     r9d, 55h ; 'U'
0x140002139  mov     [rsp+48h+var_28], rsi
0x14000213e  mov     rcx, [rcx+40h]
0x140002142  lea     r8d, [r9-52h]
0x140002146  call    WPP_RECORDER_SF_
0x14000214b  mov     edi, 0C0000010h
0x140002150  jmp     loc_140002504
0x140002155  movzx   eax, word ptr [r14+0E8h]
0x14000215d  mov     [rsi], eax
0x14000215f  mov     rax, [rbp+arg_18]
0x140002163  mov     qword ptr [rax], 4
0x14000216a  jmp     loc_1400024DD
0x14000216f  cmp     [rsi], edi
0x140002171  jz      loc_140001F61
0x140002177  bts     dword ptr [r15+0D4h], 12h
0x140002180  jmp     loc_1400024DD
0x140002185  cmp     [rsi], edi
0x140002187  jz      loc_140001F61
0x14000218d  bts     dword ptr [r15+0D4h], 11h
0x140002196  jmp     loc_1400024DD
0x14000219b  mov     ebx, 1
0x1400021a0  cmp     [rsi], ebx
0x1400021a2  jnz     loc_140001F61
0x1400021a8  or      dword ptr [r15+0CCh], 2
0x1400021b0  jmp     loc_1400024DD
0x1400021b5  sub     ebx, 120094h
0x1400021bb  jz      loc_140002498
0x1400021c1  sub     ebx, 4
0x1400021c4  jz      loc_140002488
0x1400021ca  sub     ebx, 120h
0x1400021d0  jz      loc_140002396
0x1400021d6  sub     ebx, 4
0x1400021d9  jz      loc_14000231F
0x1400021df  cmp     ebx, 168h
0x1400021e5  jz      short loc_1400021F1
0x1400021e7  mov     edi, 0C0000002h
0x1400021ec  jmp     loc_1400024DD
0x1400021f1  xor     edx, edx
0x1400021f3  lea     rcx, ?s_sdBthserv@?1??IsCallingProcessBthservEx@@9@9; SecurityDescriptor
0x1400021fa  call    IsCallingProcess
0x1400021ff  test    al, al
0x140002201  jnz     short loc_14000223C
0x140002203  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000220a  jz      short loc_140002232
0x14000220c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002213  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14000221a  mov     r9d, 5Dh ; ']'
0x140002220  mov     [rsp+48h+var_28], rax
0x140002225  mov     rcx, [rcx+40h]
0x140002229  lea     r8d, [r9-5Ah]
0x14000222d  call    WPP_RECORDER_SF_
0x140002232  mov     edi, 0C0000022h
0x140002237  jmp     loc_1400024DD
0x14000223c  mov     eax, [rsi]
0x14000223e  lea     rdx, [rbp+Process]; Process
0x140002242  mov     ecx, eax; ProcessId
0x140002244  mov     [rbp+var_18], rax
0x140002248  mov     [rbp+Process], rdi
0x14000224c  call    cs:__imp_PsLookupProcessByProcessId
0x140002253  nop     dword ptr [rax+rax+00h]
0x140002258  mov     edi, eax
0x14000225a  test    eax, eax
0x14000225c  js      loc_1400024DD
0x140002262  mov     rcx, [rbp+Process]
0x140002266  lea     rdx, [rbp+arg_0]
0x14000226a  mov     byte ptr [rbp+arg_0], 0
0x14000226e  call    QueryIsAppContainer
0x140002273  mov     ebx, 1
0x140002278  test    eax, eax
0x14000227a  jns     short loc_1400022AE
0x14000227c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140002283  jz      short loc_1400022A9
0x140002285  mov     rcx, cs:WPP_GLOBAL_Control
0x14000228c  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140002293  lea     r9d, [rbx+5Dh]
0x140002297  mov     [rsp+48h+var_28], rax
0x14000229c  lea     r8d, [rbx+2]
0x1400022a0  mov     rcx, [rcx+40h]
0x1400022a4  call    WPP_RECORDER_SF_
0x1400022a9  mov     r13b, bl
0x1400022ac  jmp     short loc_1400022B2
0x1400022ae  mov     r13b, byte ptr [rbp+arg_0]
0x1400022b2  mov     rsi, [rbp+arg_8]
0x1400022b6  lea     rcx, [rsi+30h]; SpinLock
0x1400022ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400022c1  nop     dword ptr [rax+rax+00h]
0x1400022c6  mov     [rsi+38h], al
0x1400022c9  mov     rcx, [rsi+58h]; Object
0x1400022cd  test    rcx, rcx
0x1400022d0  jz      short loc_1400022E6
0x1400022d2  call    cs:__imp_ObfDereferenceObject
0x1400022d9  nop     dword ptr [rax+rax+00h]
0x1400022de  mov     qword ptr [rsi+58h], 0
0x1400022e6  mov     rax, [rbp+var_18]
0x1400022ea  mov     [rsi+338h], eax
0x1400022f0  mov     rax, [rbp+Process]
0x1400022f4  mov     [rsi+58h], rax
0x1400022f8  mov     rax, [rbp+var_10]
0x1400022fc  mov     rax, [rax+50h]
0x140002300  cmp     byte ptr [rax+30h], 0
0x140002304  jnz     short loc_14000230B
0x140002306  test    r13b, r13b
0x140002309  jnz     short loc_14000230D
0x14000230b  xor     bl, bl
0x14000230d  mov     [rsi+33Ch], bl
0x140002313  lea     rcx, [rsi+30h]
0x140002317  mov     dl, [rsi+38h]
0x14000231a  jmp     loc_1400024D1
0x14000231f  mov     rbx, [r14+38h]
0x140002323  lea     rcx, [rbx+38h]; SpinLock
0x140002327  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000232e  nop     dword ptr [rax+rax+00h]
0x140002333  mov     [rbx+40h], al
0x140002336  xor     eax, eax
0x140002338  xchg    eax, [r14+0CCh]
0x14000233f  test    eax, eax
0x140002341  jz      short loc_14000235A
0x140002343  mov     dword ptr [rsi], 1
0x140002349  movzx   eax, word ptr [r14+0D0h]
0x140002351  mov     [rsi+4], ax
0x140002355  jmp     loc_1400024C6
0x14000235a  xor     eax, eax
0x14000235c  xchg    eax, [r14+0C4h]
0x140002363  test    eax, eax
0x140002365  jz      short loc_14000237C
0x140002367  mov     dword ptr [rsi], 2
0x14000236d  mov     al, [r14+0C8h]
0x140002374  mov     [rsi+4], al
0x140002377  jmp     loc_1400024C6
0x14000237c  mov     rcx, [rbp+arg_8]
0x140002380  mov     rdx, r13
0x140002383  add     rcx, 2E0h
0x14000238a  call    IrpList_EnqueueEx
0x14000238f  mov     edi, eax
0x140002391  jmp     loc_1400024C6
0x140002396  mov     rbx, [rbp+arg_8]
0x14000239a  mov     rdx, r13
0x14000239d  lea     rax, [rbx+2A8h]
0x1400023a4  mov     rcx, rax
0x1400023a7  mov     [rbp+arg_0], rax
0x1400023ab  call    IrpList_EnqueueEx
0x1400023b0  mov     edi, eax
0x1400023b2  test    eax, eax
0x1400023b4  js      loc_1400024DD
0x1400023ba  mov     ecx, [rsi]
0x1400023bc  mov     eax, ecx
0x1400023be  sub     eax, 1
0x1400023c1  jz      loc_14000244B
0x1400023c7  sub     eax, 1
0x1400023ca  jz      short loc_140002437
0x1400023cc  sub     eax, 1
0x1400023cf  jz      short loc_140002424
  ... truncated ...
```
