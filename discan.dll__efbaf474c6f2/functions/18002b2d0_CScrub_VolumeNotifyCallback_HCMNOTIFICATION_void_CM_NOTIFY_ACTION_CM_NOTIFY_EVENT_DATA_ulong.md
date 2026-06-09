# CScrub::_VolumeNotifyCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x18002b2d0`
- end: `0x18002b5b0`
- name: `?_VolumeNotifyCallback@CScrub@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `736`
- prototype: `__int64 __fastcall(__int64, CScrub *, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800064d8`
- `0x18002b1c0`
- `0x18002b2d0`
- `0x18002d870`

## string_xrefs

- `0x18002b36b`: `Dismount`
- `0x18002b383`: `DismountFailed`
- `0x18002b39b`: `Mount`
- `0x18002b464`: `InfoMakeCompat`
- `0x18002b4a6`: `PhysicalConfigurationChange`

## pseudocode

```c
__int64 __fastcall CScrub::_VolumeNotifyCallback(__int64 a1, CScrub *a2, unsigned int a3, __int64 a4)
{
  PVOID *v7; // rcx
  bool v8; // zf
  _QWORD *v9; // r9
  unsigned int i; // edx
  _QWORD *v11; // r11
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD v16[44]; // [rsp+30h] [rbp-D0h]

  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      176,
      &WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
      a3,
      *(_DWORD *)a4);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 == 6 && *(_DWORD *)a4 == 1 )
  {
    v8 = (*((_BYTE *)v7 + 28) & 1) == 0;
    v16[0] = &GUID_IO_VOLUME_CHANGE;
    v16[1] = "VolumeChange";
    v16[2] = &GUID_IO_VOLUME_DISMOUNT;
    v16[3] = "Dismount";
    v16[4] = &GUID_IO_VOLUME_DISMOUNT_FAILED;
    v16[5] = "DismountFailed";
    v16[6] = &GUID_IO_VOLUME_MOUNT;
    v16[7] = "Mount";
    v16[8] = &GUID_IO_VOLUME_LOCK;
    v16[9] = "Lock";
    v16[10] = &GUID_IO_VOLUME_LOCK_FAILED;
    v16[11] = "LockFailed";
    v16[12] = &GUID_IO_VOLUME_UNLOCK;
    v16[13] = "Unlock";
    v16[14] = &GUID_IO_VOLUME_NAME_CHANGE;
    v16[15] = "NameChange";
    v16[16] = &GUID_IO_VOLUME_NEED_CHKDSK;
    v16[17] = "NeedChkdsk";
    v16[18] = &GUID_IO_VOLUME_WORM_NEAR_FULL;
    v16[19] = "WormNearFull";
    v16[20] = &GUID_IO_VOLUME_WEARING_OUT;
    v16[21] = "WearingOut";
    v16[22] = &GUID_IO_VOLUME_FORCE_CLOSED;
    v16[23] = "ForceClosed";
    v16[24] = &GUID_IO_VOLUME_INFO_MAKE_COMPAT;
    v16[25] = "InfoMakeCompat";
    v16[26] = &GUID_IO_VOLUME_PREPARING_EJECT;
    v16[27] = "PreparingEject";
    v16[28] = &GUID_IO_VOLUME_BACKGROUND_FORMAT;
    v16[29] = "BackgroundFormat";
    v16[30] = &GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE;
    v16[31] = "PhysicalConfigurationChange";
    v16[32] = &GUID_IO_VOLUME_UNIQUE_ID_CHANGE;
    v16[33] = "UniqueIdChange";
    v16[34] = &GUID_IO_VOLUME_FVE_STATUS_CHANGE;
    v16[35] = "FveStatusChange";
    v16[36] = &GUID_IO_VOLUME_DEVICE_INTERFACE;
    v16[37] = "DeviceInterface";
    v16[38] = &GUID_IO_VOLUME_CHANGE_SIZE;
    v16[39] = "ChangeSize";
    if ( !v8 && *((_BYTE *)v7 + 25) >= 4u )
    {
      v9 = (_QWORD *)(a4 + 8);
      for ( i = 0; i < 0x14; ++i )
      {
        v11 = (_QWORD *)v16[2 * i];
        v12 = *v9 - *v11;
        if ( *v9 == *v11 )
          v12 = *(_QWORD *)(a4 + 16) - v11[1];
        if ( !v12 )
          break;
      }
      if ( v7 != &WPP_GLOBAL_Control )
        WPP_SF_s_guid_((TRACEHANDLE)v7[2], a4 + 8);
    }
    v13 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_IO_VOLUME_LOCK.Data1;
    if ( !v13 )
      v13 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_IO_VOLUME_LOCK.Data4;
    if ( !v13 )
      goto LABEL_23;
    v14 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1;
    if ( !v14 )
      v14 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_IO_VOLUME_DISMOUNT.Data4;
    if ( !v14 )
LABEL_23:
      CScrub::_VolumeLockNotify(a2);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b2d0  push    rbp
0x18002b2d2  push    rbx
0x18002b2d3  push    rsi
0x18002b2d4  push    rdi
0x18002b2d5  push    r14
0x18002b2d7  lea     rbp, [rsp-70h]
0x18002b2dc  sub     rsp, 170h
0x18002b2e3  mov     rbx, r9
0x18002b2e6  mov     edi, r8d
0x18002b2e9  mov     rsi, rdx
0x18002b2ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2f3  lea     r14, WPP_GLOBAL_Control
0x18002b2fa  cmp     rcx, r14
0x18002b2fd  jz      short loc_18002B331
0x18002b2ff  test    byte ptr [rcx+1Ch], 1
0x18002b303  jz      short loc_18002B331
0x18002b305  cmp     byte ptr [rcx+19h], 4
0x18002b309  jb      short loc_18002B331
0x18002b30b  mov     eax, [r9]
0x18002b30e  mov     edx, 0B0h
0x18002b313  mov     rcx, [rcx+10h]
0x18002b317  mov     r9d, r8d
0x18002b31a  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x18002b321  mov     dword ptr [rsp+190h+var_170], eax
0x18002b325  call    WPP_SF_Dd
0x18002b32a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b331  cmp     edi, 6
0x18002b334  jnz     loc_18002B5A0
0x18002b33a  cmp     dword ptr [rbx], 1
0x18002b33d  jnz     loc_18002B5A0
0x18002b343  test    byte ptr [rcx+1Ch], 1
0x18002b347  lea     rax, GUID_IO_VOLUME_CHANGE
0x18002b34e  mov     [rsp+190h+var_160], rax
0x18002b353  lea     rax, aVolumechange; "VolumeChange"
0x18002b35a  mov     [rsp+190h+var_158], rax
0x18002b35f  lea     rax, GUID_IO_VOLUME_DISMOUNT
0x18002b366  mov     [rsp+190h+var_150], rax
0x18002b36b  lea     rax, aDismount; "Dismount"
0x18002b372  mov     [rsp+190h+var_148], rax
0x18002b377  lea     rax, GUID_IO_VOLUME_DISMOUNT_FAILED
0x18002b37e  mov     [rsp+190h+var_140], rax
0x18002b383  lea     rax, aDismountfailed; "DismountFailed"
0x18002b38a  mov     [rsp+190h+var_138], rax
0x18002b38f  lea     rax, GUID_IO_VOLUME_MOUNT
0x18002b396  mov     [rsp+190h+var_130], rax
0x18002b39b  lea     rax, aMount; "Mount"
0x18002b3a2  mov     [rsp+190h+var_128], rax
0x18002b3a7  lea     rax, GUID_IO_VOLUME_LOCK
0x18002b3ae  mov     [rsp+190h+var_120], rax
0x18002b3b3  lea     rax, aLock; "Lock"
0x18002b3ba  mov     [rsp+190h+var_118], rax
0x18002b3bf  lea     rax, GUID_IO_VOLUME_LOCK_FAILED
0x18002b3c6  mov     [rbp+90h+var_110], rax
0x18002b3ca  lea     rax, aLockfailed; "LockFailed"
0x18002b3d1  mov     [rbp+90h+var_108], rax
0x18002b3d5  lea     rax, GUID_IO_VOLUME_UNLOCK
0x18002b3dc  mov     [rbp+90h+var_100], rax
0x18002b3e0  lea     rax, aUnlock; "Unlock"
0x18002b3e7  mov     [rbp+90h+var_F8], rax
0x18002b3eb  lea     rax, GUID_IO_VOLUME_NAME_CHANGE
0x18002b3f2  mov     [rbp+90h+var_F0], rax
0x18002b3f6  lea     rax, aNamechange; "NameChange"
0x18002b3fd  mov     [rbp+90h+var_E8], rax
0x18002b401  lea     rax, GUID_IO_VOLUME_NEED_CHKDSK
0x18002b408  mov     [rbp+90h+var_E0], rax
0x18002b40c  lea     rax, aNeedchkdsk; "NeedChkdsk"
0x18002b413  mov     [rbp+90h+var_D8], rax
0x18002b417  lea     rax, GUID_IO_VOLUME_WORM_NEAR_FULL
0x18002b41e  mov     [rbp+90h+var_D0], rax
0x18002b422  lea     rax, aWormnearfull; "WormNearFull"
0x18002b429  mov     [rbp+90h+var_C8], rax
0x18002b42d  lea     rax, GUID_IO_VOLUME_WEARING_OUT
0x18002b434  mov     [rbp+90h+var_C0], rax
0x18002b438  lea     rax, aWearingout; "WearingOut"
0x18002b43f  mov     [rbp+90h+var_B8], rax
0x18002b443  lea     rax, GUID_IO_VOLUME_FORCE_CLOSED
0x18002b44a  mov     [rbp+90h+var_B0], rax
0x18002b44e  lea     rax, aForceclosed; "ForceClosed"
0x18002b455  mov     [rbp+90h+var_A8], rax
0x18002b459  lea     rax, GUID_IO_VOLUME_INFO_MAKE_COMPAT
0x18002b460  mov     [rbp+90h+var_A0], rax
0x18002b464  lea     rax, aInfomakecompat; "InfoMakeCompat"
0x18002b46b  mov     [rbp+90h+var_98], rax
0x18002b46f  lea     rax, GUID_IO_VOLUME_PREPARING_EJECT
0x18002b476  mov     [rbp+90h+var_90], rax
0x18002b47a  lea     rax, aPreparingeject; "PreparingEject"
0x18002b481  mov     [rbp+90h+var_88], rax
0x18002b485  lea     rax, GUID_IO_VOLUME_BACKGROUND_FORMAT
0x18002b48c  mov     [rbp+90h+var_80], rax
0x18002b490  lea     rax, aBackgroundform; "BackgroundFormat"
0x18002b497  mov     [rbp+90h+var_78], rax
0x18002b49b  lea     rax, GUID_IO_VOLUME_PHYSICAL_CONFIGURATION_CHANGE
0x18002b4a2  mov     [rbp+90h+var_70], rax
0x18002b4a6  lea     rax, aPhysicalconfig; "PhysicalConfigurationChange"
0x18002b4ad  mov     [rbp+90h+var_68], rax
0x18002b4b1  lea     rax, GUID_IO_VOLUME_UNIQUE_ID_CHANGE
0x18002b4b8  mov     [rbp+90h+var_60], rax
0x18002b4bc  lea     rax, aUniqueidchange; "UniqueIdChange"
0x18002b4c3  mov     [rbp+90h+var_58], rax
0x18002b4c7  lea     rax, GUID_IO_VOLUME_FVE_STATUS_CHANGE
0x18002b4ce  mov     [rbp+90h+var_50], rax
0x18002b4d2  lea     rax, aFvestatuschang; "FveStatusChange"
0x18002b4d9  mov     [rbp+90h+var_48], rax
0x18002b4dd  lea     rax, GUID_IO_VOLUME_DEVICE_INTERFACE
0x18002b4e4  mov     [rbp+90h+var_40], rax
0x18002b4e8  lea     rax, aDeviceinterfac; "DeviceInterface"
0x18002b4ef  mov     [rbp+90h+var_38], rax
0x18002b4f3  lea     rax, GUID_IO_VOLUME_CHANGE_SIZE
0x18002b4fa  mov     [rbp+90h+var_30], rax
0x18002b4fe  lea     rax, aChangesize; "ChangeSize"
0x18002b505  mov     [rbp+90h+var_28], rax
0x18002b509  jz      short loc_18002B55E
0x18002b50b  cmp     byte ptr [rcx+19h], 4
0x18002b50f  jb      short loc_18002B55E
0x18002b511  xor     r10d, r10d
0x18002b514  lea     r9, [rbx+8]
0x18002b518  xor     edx, edx
0x18002b51a  cmp     edx, 14h
0x18002b51d  jnb     short loc_18002B548
0x18002b51f  mov     rax, [r9]
0x18002b522  mov     r8d, edx
0x18002b525  add     r8, r8
0x18002b528  mov     r11, [rsp+r8*8+190h+var_160]
0x18002b52d  sub     rax, [r11]
0x18002b530  jnz     short loc_18002B53A
0x18002b532  mov     rax, [r9+8]
0x18002b536  sub     rax, [r11+8]
0x18002b53a  test    rax, rax
0x18002b53d  jz      short loc_18002B543
0x18002b53f  inc     edx
0x18002b541  jmp     short loc_18002B51A
0x18002b543  mov     r10, [rsp+r8*8+190h+var_158]
0x18002b548  cmp     rcx, r14
0x18002b54b  jz      short loc_18002B55E
0x18002b54d  mov     rcx, [rcx+10h]; LoggerHandle
0x18002b551  mov     [rsp+190h+var_170], r9; __int64
0x18002b556  mov     r9, r10
0x18002b559  call    WPP_SF_s_guid_
0x18002b55e  mov     rax, [rbx+8]
0x18002b562  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data1
0x18002b569  jnz     short loc_18002B576
0x18002b56b  mov     rax, [rbx+10h]
0x18002b56f  sub     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data4
0x18002b576  test    rax, rax
0x18002b579  jz      short loc_18002B598
0x18002b57b  mov     rax, [rbx+8]
0x18002b57f  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x18002b586  jnz     short loc_18002B593
0x18002b588  mov     rax, [rbx+10h]
0x18002b58c  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x18002b593  test    rax, rax
0x18002b596  jnz     short loc_18002B5A0
0x18002b598  mov     rcx, rsi; this
0x18002b59b  call    ?_VolumeLockNotify@CScrub@@AEAAXXZ; CScrub::_VolumeLockNotify(void)
0x18002b5a0  xor     eax, eax
0x18002b5a2  add     rsp, 170h
0x18002b5a9  pop     r14
0x18002b5ab  pop     rdi
0x18002b5ac  pop     rsi
0x18002b5ad  pop     rbx
0x18002b5ae  pop     rbp
0x18002b5af  retn
```
