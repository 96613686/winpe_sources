# TpiDispatchFastIoDeviceControl

- ea: `0x140012290`
- end: `0x140012dd9`
- name: `TpiDispatchFastIoDeviceControl`
- size: `2889`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400015b0`
- `0x1400018b0`
- `0x140002030`
- `0x140002aa0`
- `0x140002bd8`
- `0x140002c08`
- `0x140002f88`
- `0x140002fc4`
- `0x140005e10`
- `0x140006240`
- `0x14000e06c`
- `0x140011b00`
- `0x140012290`
- `0x1400133f0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400123ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001249f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001257f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012648`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400126d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012a0d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012ac7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012ba5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012cad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400123ca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001249f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001257f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012648`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400126d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012a0d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012ac7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012ba5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012cad`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400123a1`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14001267f`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140012988`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140012b78`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140012c86`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400123a1`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14001267f`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140012988`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140012b78`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140012c86`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001248a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012609`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012633`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001266c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001271a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a51`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012ab2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012bdf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012cf9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012d3b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001248a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012609`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012633`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001266c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001271a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012a51`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012ab2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012bdf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012cf9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012d3b`
- `NDIS!NdisCmRegisterSapComplete` at `0x140012d24`
- `NDIS!NdisCmRegisterSapComplete` at `0x140012d24`
- `NDIS!NdisCmDeregisterSapComplete` at `0x140012c07`
- `NDIS!NdisCmDeregisterSapComplete` at `0x140012c07`
- `NETIO!HfSuspendHandle32` at `0x14001246d`
- `NETIO!HfSuspendHandle32` at `0x14001246d`
- `NETIO!HfGetPointerFromHandle32` at `0x1400123ee`
- `NETIO!HfGetPointerFromHandle32` at `0x1400125a4`
- `NETIO!HfGetPointerFromHandle32` at `0x140012a31`
- `NETIO!HfGetPointerFromHandle32` at `0x1400123ee`
- `NETIO!HfGetPointerFromHandle32` at `0x1400125a4`
- `NETIO!HfGetPointerFromHandle32` at `0x140012a31`

## pseudocode

```c
char __fastcall TpiDispatchFastIoDeviceControl(
        __int64 a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        __int64 a8)
{
  char v9; // si
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  KIRQL v13; // r14
  KSPIN_LOCK *v14; // rcx
  KIRQL v15; // dl
  KIRQL v16; // al
  __int64 v17; // r8
  KIRQL v18; // r15
  int PointerFromHandle32; // r14d
  KIRQL v20; // al
  KIRQL v21; // dl
  __int64 v22; // r8
  int v23; // edx
  int v24; // r14d
  unsigned int v25; // r15d
  KIRQL v26; // bl
  KIRQL v27; // al
  char *v28; // rcx
  KIRQL v29; // al
  volatile signed __int32 *v31[2]; // [rsp+38h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+48h] [rbp-B0h]
  unsigned int v33; // [rsp+4Ch] [rbp-ACh]
  unsigned int ULongFromUser; // [rsp+50h] [rbp-A8h]
  _QWORD v35[14]; // [rsp+60h] [rbp-98h] BYREF

  v31[1] = (volatile signed __int32 *)a8;
  v9 = 1;
  if ( a1 == *((_QWORD *)SstpGlobals + 3) )
  {
    TpiNonSstpFastIoDeviceControl(a3);
    return v9;
  }
  if ( a1 != *((_QWORD *)SstpGlobals + 2) )
  {
    *(_DWORD *)a8 = -1073741637;
    *(_QWORD *)(a8 + 8) = 0;
    return v9;
  }
  if ( a7 == 1212420 )
  {
    if ( a4 < 4 )
      goto LABEL_57;
    LODWORD(v31[0]) = 0;
    if ( ((unsigned __int8)a3 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    LODWORD(v31[0]) = RtlReadULongFromUser(a3);
    v29 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 55);
    v28 = (char *)SstpGlobals;
    if ( *((_DWORD *)SstpGlobals + 112) == 1 )
    {
      *(_DWORD *)a8 = 0;
      *((_DWORD *)SstpGlobals + 112) = LODWORD(v31[0]) == 0 ? 3 : 0;
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 55, v29);
      NdisCmRegisterSapComplete(LODWORD(v31[0]) != 0 ? 0xC0000001 : 0, *((NDIS_HANDLE *)SstpGlobals + 57), 0);
      return v9;
    }
    v15 = v29;
LABEL_90:
    v14 = (KSPIN_LOCK *)(v28 + 440);
    goto LABEL_91;
  }
  if ( a7 == 1212428 )
  {
    if ( a4 < 4 )
      goto LABEL_57;
    LODWORD(v31[0]) = 0;
    if ( ((unsigned __int8)a3 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    LODWORD(v31[0]) = RtlReadULongFromUser(a3);
    *(_DWORD *)a8 = 0;
    v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 55);
    v28 = (char *)SstpGlobals;
    v15 = v27;
    if ( *((_DWORD *)SstpGlobals + 112) == 2 )
    {
      *((_DWORD *)SstpGlobals + 112) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 55, v27);
      NdisCmDeregisterSapComplete(LODWORD(v31[0]) != 0 ? 0xC0000001 : 0, *((NDIS_HANDLE *)SstpGlobals + 57));
      return v9;
    }
    goto LABEL_90;
  }
  if ( a7 != 1212440 )
  {
    if ( a7 == 1212454 )
    {
      if ( a4 == 4 )
      {
        ULongFromUser = RtlReadULongFromUser(a3);
        return RetrieveSendPackets(a8, ULongFromUser, a5, a6);
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_57;
      }
      v11 = 123;
LABEL_56:
      WPP_SF_(v10->AttachedDevice, v11, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
LABEL_57:
      *(_DWORD *)a8 = -1073741811;
      *(_QWORD *)(a8 + 8) = 4;
      return v9;
    }
    if ( a7 != 1212469 )
    {
      if ( a7 != 1212480 )
        return 0;
      *(_DWORD *)a8 = 0;
      if ( a4 < 4 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_57;
        }
        v11 = 115;
        goto LABEL_56;
      }
      v31[0] = 0;
      if ( ((unsigned __int8)a3 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      v12 = RtlReadULongFromUser(a3);
      v32 = v12;
      v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 62);
      if ( (int)HfGetPointerFromHandle32(*((_QWORD *)SstpGlobals + 63), v12, v31) < 0 )
      {
        v14 = (KSPIN_LOCK *)((char *)SstpGlobals + 496);
        v15 = v13;
LABEL_91:
        KeReleaseSpinLock(v14, v15);
        return v9;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF__guid_(
          WPP_GLOBAL_Control->AttachedDevice,
          117,
          WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
          v31[0] + 121);
      }
      _InterlockedIncrement(v31[0]);
      HfSuspendHandle32(*((_QWORD *)SstpGlobals + 63), v12);
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v13);
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v31[0] + 4);
LABEL_78:
      LOBYTE(v17) = v16;
      InitiateSstpContextCleanup((__int64)v31[0], 0, v17);
      DereferenceRefCount(v31[0]);
      return v9;
    }
    v31[0] = 0;
    if ( a4 != 16392 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
      }
      *(_DWORD *)a8 = -1073741811;
      *(_QWORD *)(a8 + 8) = 16392;
      return v9;
    }
    v33 = RtlReadULongFromUser(a3);
    v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 62);
    PointerFromHandle32 = HfGetPointerFromHandle32(*((_QWORD *)SstpGlobals + 63), v33, v31);
    if ( PointerFromHandle32 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF__guid_(
          WPP_GLOBAL_Control->AttachedDevice,
          120,
          WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
          v31[0] + 121);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v18);
      goto LABEL_46;
    }
    _InterlockedIncrement(v31[0]);
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v18);
    v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v31[0] + 4);
    *((_DWORD *)v31[0] + 5272) |= 0x10000u;
    KeReleaseSpinLock((PKSPIN_LOCK)v31[0] + 4, v20);
    if ( ((unsigned __int8)a3 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser((void *)(v31[0] + 1163), a3, 0x4008u);
    *((_DWORD *)v31[0] + 1163) = 0;
    PointerFromHandle32 = DelineateSSTPFrame(v31[0] + 134);
    v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v31[0] + 4);
    *((_DWORD *)v31[0] + 5272) &= ~0x10000u;
    if ( PointerFromHandle32 >= 0 )
    {
      if ( !*((_BYTE *)v31[0] + 21092) )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)v31[0] + 4, v21);
        goto LABEL_45;
      }
      LOBYTE(v22) = v21;
      v23 = 4;
    }
    else
    {
      LOBYTE(v22) = v21;
      v23 = 0;
    }
    InitiateSstpContextCleanup((__int64)v31[0], v23, v22);
LABEL_45:
    DereferenceRefCount(v31[0]);
LABEL_46:
    *(_DWORD *)a8 = PointerFromHandle32;
    *(_QWORD *)(a8 + 8) = 0;
    if ( PointerFromHandle32 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF__guid_D(
        WPP_GLOBAL_Control->AttachedDevice,
        122,
        WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
        v31[0] + 121,
        PointerFromHandle32);
    }
    return v9;
  }
  v31[0] = 0;
  if ( a4 == 104 )
  {
    memset(v35, 0, 0x68u);
    if ( ((unsigned __int8)a3 & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(v35, a3, 0x68u);
    v24 = v35[3];
    if ( !LODWORD(v35[3]) )
      return 0;
    v25 = v35[0];
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 127, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    }
    *(_DWORD *)a8 = 0;
    *(_QWORD *)(a8 + 8) = 0;
    v9 = 1;
    v26 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)SstpGlobals + 62);
    if ( !(unsigned int)HfGetPointerFromHandle32(*((_QWORD *)SstpGlobals + 63), v25, v31) )
    {
      _InterlockedIncrement(v31[0]);
      KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v26);
      v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v31[0] + 4);
      *((_DWORD *)v31[0] + 5274) = v24;
      *((_DWORD *)v31[0] + 5272) &= ~0x2000u;
      goto LABEL_78;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)SstpGlobals + 62, v26);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 128, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
    }
    *(_DWORD *)a8 = -1073741811;
    *(_QWORD *)(a8 + 8) = 104;
    return 1;
  }
  return v9;
}

```

## disassembly

```asm
0x140012290  mov     [rsp+arg_0], rbx
0x140012295  mov     [rsp+arg_8], rsi
0x14001229a  push    rdi
0x14001229b  push    r14
0x14001229d  push    r15
0x14001229f  sub     rsp, 0E0h
0x1400122a6  mov     rax, cs:__security_cookie
0x1400122ad  xor     rax, rsp
0x1400122b0  mov     [rsp+0F8h+var_28], rax
0x1400122b8  mov     r10d, r9d
0x1400122bb  mov     rdi, r8
0x1400122be  mov     rbx, [rsp+0F8h+arg_38]
0x1400122c6  mov     r14, [rsp+0F8h+arg_20]
0x1400122ce  mov     [rsp+0F8h+var_B8], rbx
0x1400122d3  mov     sil, 1
0x1400122d6  mov     [rsp+0F8h+var_C8], sil
0x1400122db  mov     rax, cs:SstpGlobals
0x1400122e2  cmp     rcx, [rax+18h]
0x1400122e6  jnz     short loc_140012303
0x1400122e8  mov     r9, rbx
0x1400122eb  mov     r8d, [rsp+0F8h+arg_30]
0x1400122f3  mov     edx, r10d
0x1400122f6  mov     rcx, rdi; Src
0x1400122f9  call    TpiNonSstpFastIoDeviceControl
0x1400122fe  jmp     loc_140012DAC
0x140012303  cmp     rcx, [rax+10h]
0x140012307  jnz     loc_140012D9E
0x14001230d  mov     eax, [rsp+0F8h+arg_30]
0x140012314  sub     eax, 128004h
0x140012319  jz      loc_140012C70
0x14001231f  sub     eax, 8
0x140012322  jz      loc_140012B62
0x140012328  sub     eax, 0Ch
0x14001232b  jz      loc_14001291A
0x140012331  sub     eax, 0Eh
0x140012334  jz      loc_14001284B
0x14001233a  sub     eax, 0Fh
0x14001233d  jz      loc_140012508
0x140012343  cmp     eax, 0Bh
0x140012346  jz      short loc_140012350
0x140012348  xor     sil, sil
0x14001234b  jmp     loc_140012DAC
0x140012350  mov     dword ptr [rbx], 0
0x140012356  cmp     r10d, 4
0x14001235a  jnb     short loc_140012392
0x14001235c  lea     rdi, WPP_GLOBAL_Control
0x140012363  mov     rcx, cs:WPP_GLOBAL_Control
0x14001236a  cmp     rcx, rdi
0x14001236d  jz      loc_140012886
0x140012373  mov     eax, [rcx+2Ch]
0x140012376  test    al, 2
0x140012378  jz      loc_140012886
0x14001237e  cmp     [rcx+29h], sil
0x140012382  jb      loc_140012886
0x140012388  mov     edx, 73h ; 's'
0x14001238d  jmp     loc_140012876
0x140012392  mov     [rsp+0F8h+var_C0], 0
0x14001239b  test    dil, 3
0x14001239f  jz      short loc_1400123AE
0x1400123a1  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400123a8  nop     dword ptr [rax+rax+00h]
0x1400123ad  int     3; Trap to Debugger
0x1400123ae  mov     rcx, rdi
0x1400123b1  call    RtlReadULongFromUser
0x1400123b6  mov     ebx, eax
0x1400123b8  mov     [rsp+0F8h+var_B0], eax
0x1400123bc  mov     rcx, cs:SstpGlobals
0x1400123c3  add     rcx, 1F0h; SpinLock
0x1400123ca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400123d1  nop     dword ptr [rax+rax+00h]
0x1400123d6  mov     r14b, al
0x1400123d9  lea     r8, [rsp+0F8h+var_C0]
0x1400123de  mov     edx, ebx
0x1400123e0  mov     rcx, cs:SstpGlobals
0x1400123e7  mov     rcx, [rcx+1F8h]
0x1400123ee  call    cs:__imp_HfGetPointerFromHandle32
0x1400123f5  nop     dword ptr [rax+rax+00h]
0x1400123fa  test    eax, eax
0x1400123fc  jns     short loc_140012414
0x1400123fe  mov     rcx, cs:SstpGlobals
0x140012405  add     rcx, 1F0h
0x14001240c  mov     dl, r14b
0x14001240f  jmp     loc_140012D3B
0x140012414  lea     rdi, WPP_GLOBAL_Control
0x14001241b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012422  cmp     rcx, rdi
0x140012425  jz      short loc_140012455
0x140012427  mov     eax, [rcx+2Ch]
0x14001242a  test    al, 2
0x14001242c  jz      short loc_140012455
0x14001242e  cmp     byte ptr [rcx+29h], 3
0x140012432  jb      short loc_140012455
0x140012434  mov     r9, [rsp+0F8h+var_C0]
0x140012439  add     r9, 1E4h
0x140012440  mov     edx, 75h ; 'u'
0x140012445  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001244c  mov     rcx, [rcx+18h]
0x140012450  call    WPP_SF__guid_
0x140012455  mov     rax, [rsp+0F8h+var_C0]
0x14001245a  lock inc dword ptr [rax]
0x14001245d  mov     edx, ebx
0x14001245f  mov     rcx, cs:SstpGlobals
0x140012466  mov     rcx, [rcx+1F8h]
0x14001246d  call    cs:__imp_HfSuspendHandle32
0x140012474  nop     dword ptr [rax+rax+00h]
0x140012479  mov     rcx, cs:SstpGlobals
0x140012480  add     rcx, 1F0h; SpinLock
0x140012487  mov     dl, r14b; NewIrql
0x14001248a  call    cs:__imp_KeReleaseSpinLock
0x140012491  nop     dword ptr [rax+rax+00h]
0x140012496  mov     rcx, [rsp+0F8h+var_C0]
0x14001249b  add     rcx, 20h ; ' '; SpinLock
0x14001249f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400124a6  nop     dword ptr [rax+rax+00h]
0x1400124ab  jmp     loc_140012AEC
0x1400124b0  lea     rax, WPP_GLOBAL_Control
0x1400124b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400124be  cmp     rcx, rax
0x1400124c1  jz      short loc_1400124EB
0x1400124c3  mov     eax, [rcx+2Ch]
0x1400124c6  test    al, 2
0x1400124c8  jz      short loc_1400124EB
0x1400124ca  cmp     byte ptr [rcx+29h], 1
0x1400124ce  jb      short loc_1400124EB
0x1400124d0  mov     edx, 74h ; 't'
0x1400124d5  mov     r9d, 128040h
0x1400124db  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400124e2  mov     rcx, [rcx+18h]
0x1400124e6  call    WPP_SF_d
0x1400124eb  mov     rax, [rsp+0F8h+var_B8]
0x1400124f0  mov     dword ptr [rax], 0C000000Dh
0x1400124f6  mov     qword ptr [rax+8], 0
0x1400124fe  mov     sil, [rsp+0F8h+var_C8]
0x140012503  jmp     loc_140012DAC
0x140012508  mov     [rsp+0F8h+var_C0], 0
0x140012511  cmp     r10d, 4008h
0x140012518  jz      short loc_140012562
0x14001251a  lea     rdi, WPP_GLOBAL_Control
0x140012521  mov     rcx, cs:WPP_GLOBAL_Control
0x140012528  cmp     rcx, rdi
0x14001252b  jz      short loc_14001254F
0x14001252d  mov     eax, [rcx+2Ch]
0x140012530  test    al, 2
0x140012532  jz      short loc_14001254F
0x140012534  cmp     [rcx+29h], sil
0x140012538  jb      short loc_14001254F
0x14001253a  mov     edx, 76h ; 'v'
0x14001253f  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140012546  mov     rcx, [rcx+18h]
0x14001254a  call    WPP_SF_
0x14001254f  mov     dword ptr [rbx], 0C000000Dh
0x140012555  mov     qword ptr [rbx+8], 4008h
0x14001255d  jmp     loc_140012DAC
0x140012562  mov     rcx, rdi
0x140012565  call    RtlReadULongFromUser
0x14001256a  mov     r14d, eax
0x14001256d  mov     [rsp+0F8h+var_AC], eax
0x140012571  mov     rcx, cs:SstpGlobals
0x140012578  add     rcx, 1F0h; SpinLock
0x14001257f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012586  nop     dword ptr [rax+rax+00h]
0x14001258b  mov     r15b, al
0x14001258e  lea     r8, [rsp+0F8h+var_C0]
0x140012593  mov     edx, r14d
0x140012596  mov     rcx, cs:SstpGlobals
0x14001259d  mov     rcx, [rcx+1F8h]
0x1400125a4  call    cs:__imp_HfGetPointerFromHandle32
0x1400125ab  nop     dword ptr [rax+rax+00h]
0x1400125b0  mov     r14d, eax
0x1400125b3  test    eax, eax
0x1400125b5  jz      short loc_14001261A
0x1400125b7  lea     rdi, WPP_GLOBAL_Control
0x1400125be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400125c5  cmp     rcx, rdi
0x1400125c8  jz      short loc_1400125F8
0x1400125ca  mov     eax, [rcx+2Ch]
0x1400125cd  test    al, 2
0x1400125cf  jz      short loc_1400125F8
0x1400125d1  cmp     byte ptr [rcx+29h], 1
0x1400125d5  jb      short loc_1400125F8
0x1400125d7  mov     r9, [rsp+0F8h+var_C0]
0x1400125dc  add     r9, 1E4h
0x1400125e3  mov     edx, 78h ; 'x'
0x1400125e8  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400125ef  mov     rcx, [rcx+18h]
0x1400125f3  call    WPP_SF__guid_
0x1400125f8  mov     rcx, cs:SstpGlobals
0x1400125ff  add     rcx, 1F0h; SpinLock
0x140012606  mov     dl, r15b; NewIrql
0x140012609  call    cs:__imp_KeReleaseSpinLock
0x140012610  nop     dword ptr [rax+rax+00h]
0x140012615  jmp     loc_140012737
0x14001261a  mov     rax, [rsp+0F8h+var_C0]
0x14001261f  lock inc dword ptr [rax]
0x140012622  mov     rcx, cs:SstpGlobals
0x140012629  add     rcx, 1F0h; SpinLock
0x140012630  mov     dl, r15b; NewIrql
0x140012633  call    cs:__imp_KeReleaseSpinLock
0x14001263a  nop     dword ptr [rax+rax+00h]
0x14001263f  mov     rcx, [rsp+0F8h+var_C0]
0x140012644  add     rcx, 20h ; ' '; SpinLock
0x140012648  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001264f  nop     dword ptr [rax+rax+00h]
0x140012654  mov     dl, al; NewIrql
0x140012656  mov     rax, [rsp+0F8h+var_C0]
0x14001265b  bts     dword ptr [rax+5260h], 10h
0x140012663  mov     rcx, [rsp+0F8h+var_C0]
0x140012668  add     rcx, 20h ; ' '; SpinLock
0x14001266c  call    cs:__imp_KeReleaseSpinLock
0x140012673  nop     dword ptr [rax+rax+00h]
0x140012678  nop
0x140012679  test    dil, 3
0x14001267d  jz      short loc_14001268C
0x14001267f  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140012686  nop     dword ptr [rax+rax+00h]
0x14001268b  int     3; Trap to Debugger
0x14001268c  mov     rcx, [rsp+0F8h+var_C0]
0x140012691  add     rcx, 122Ch; void *
0x140012698  mov     r8d, 4008h; Size
0x14001269e  mov     rdx, rdi; Src
0x1400126a1  call    RtlCopyFromUser
0x1400126a6  mov     rax, [rsp+0F8h+var_C0]
0x1400126ab  mov     dword ptr [rax+122Ch], 0
0x1400126b5  mov     rdx, [rsp+0F8h+var_C0]
0x1400126ba  lea     rcx, [rdx+218h]
0x1400126c1  call    DelineateSSTPFrame
0x1400126c6  mov     r14d, eax
0x1400126c9  mov     rcx, [rsp+0F8h+var_C0]
0x1400126ce  add     rcx, 20h ; ' '; SpinLock
0x1400126d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400126d9  nop     dword ptr [rax+rax+00h]
0x1400126de  mov     dl, al; NewIrql
0x1400126e0  mov     rax, [rsp+0F8h+var_C0]
0x1400126e5  btr     dword ptr [rax+5260h], 10h
0x1400126ed  mov     rcx, [rsp+0F8h+var_C0]
0x1400126f2  test    r14d, r14d
0x1400126f5  jns     short loc_1400126FE
0x1400126f7  mov     r8b, dl
0x1400126fa  xor     edx, edx
0x1400126fc  jmp     short loc_14001270F
0x1400126fe  cmp     byte ptr [rcx+5264h], 0
0x140012705  jz      short loc_140012716
0x140012707  mov     r8b, dl
0x14001270a  mov     edx, 4
0x14001270f  call    InitiateSstpContextCleanup
0x140012714  jmp     short loc_140012726
0x140012716  add     rcx, 20h ; ' '; SpinLock
0x14001271a  call    cs:__imp_KeReleaseSpinLock
0x140012721  nop     dword ptr [rax+rax+00h]
0x140012726  mov     rcx, [rsp+0F8h+var_C0]
0x14001272b  call    DereferenceRefCount
0x140012730  lea     rdi, WPP_GLOBAL_Control
0x140012737  mov     [rbx], r14d
0x14001273a  mov     qword ptr [rbx+8], 0
0x140012742  test    r14d, r14d
0x140012745  jns     loc_140012DAC
0x14001274b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012752  cmp     rcx, rdi
0x140012755  jz      loc_140012DAC
0x14001275b  mov     eax, [rcx+2Ch]
0x14001275e  test    al, 2
0x140012760  jz      loc_140012DAC
0x140012766  cmp     byte ptr [rcx+29h], 1
0x14001276a  jb      loc_140012DAC
0x140012770  mov     r9, [rsp+0F8h+var_C0]
0x140012775  add     r9, 1E4h
0x14001277c  mov     edx, 7Ah ; 'z'
0x140012781  mov     [rsp+0F8h+var_D8], r14d
0x140012786  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001278d  mov     rcx, [rcx+18h]
0x140012791  call    WPP_SF__guid_D
0x140012796  jmp     loc_140012DAC
0x14001279b  lea     rax, WPP_GLOBAL_Control
0x1400127a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400127a9  cmp     rcx, rax
0x1400127ac  jz      short loc_1400127D6
0x1400127ae  mov     eax, [rcx+2Ch]
0x1400127b1  test    al, 2
0x1400127b3  jz      short loc_1400127D6
0x1400127b5  cmp     byte ptr [rcx+29h], 1
0x1400127b9  jb      short loc_1400127D6
0x1400127bb  mov     edx, 79h ; 'y'
0x1400127c0  mov     r9d, 128035h
0x1400127c6  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400127cd  mov     rcx, [rcx+18h]
0x1400127d1  call    WPP_SF_d
0x1400127d6  mov     rax, [rsp+0F8h+var_B8]
0x1400127db  mov     dword ptr [rax], 0C000000Dh
0x1400127e1  mov     qword ptr [rax+8], 0
0x1400127e9  mov     sil, [rsp+0F8h+var_C8]
0x1400127ee  jmp     loc_140012DAC
0x1400127f3  lea     rax, WPP_GLOBAL_Control
0x1400127fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140012801  cmp     rcx, rax
0x140012804  jz      short loc_14001282E
0x140012806  mov     eax, [rcx+2Ch]
0x140012809  test    al, 2
0x14001280b  jz      short loc_14001282E
0x14001280d  cmp     byte ptr [rcx+29h], 1
0x140012811  jb      short loc_14001282E
  ... truncated ...
```
