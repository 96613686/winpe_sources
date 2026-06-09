# FvePnpNotification

- ea: `0x14008cf00`
- end: `0x14008d6c8`
- name: `FvePnpNotification`
- size: `1992`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000bc14`
- `0x14000c79c`
- `0x14006385c`
- `0x14006562c`
- `0x1400657e0`
- `0x140089928`
- `0x14008cf00`
- `0x14008d6d0`
- `0x14009113c`
- `0x140099fc8`
- `0x14009af78`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14008d0f0`
- `ntoskrnl!RtlCompareMemory` at `0x14008d0f0`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14008cf61`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14008d176`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14008cf61`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14008d176`

## pseudocode

```c
__int64 __fastcall FvePnpNotification(char *NotificationStructure, _DWORD *Context)
{
  int v4; // edx
  int v5; // r8d
  BOOLEAN v6; // r12
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // edi
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  bool v16; // r15
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  bool v21; // dl
  int v22; // eax
  __int64 v23; // rax
  int v24; // edi
  __int64 v25; // rcx
  __int64 v26; // rdx
  bool v27; // dl
  int v28; // eax
  __int64 v29; // rax
  int v30; // ecx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rdx
  bool v34; // dl
  int v35; // eax
  __int64 v36; // rax
  int v37; // edi
  __int64 v38; // rcx
  __int64 v39; // rdx
  bool v40; // dl
  int v41; // eax
  __int64 v42; // rax
  int v43; // ecx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  int v47; // r9d
  int v48; // r8d
  int v49; // edx
  bool v50; // [rsp+B0h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
      Context,
      Context[220]);
  }
  v6 = IoSetThreadHardErrorMode(0);
  v7 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data1;
  if ( !v7 )
    v7 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data4;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    if ( !Context[220] )
      FveUnregisterPnpNotifications(Context);
    goto LABEL_46;
  }
  v8 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_TARGET_DEVICE_QUERY_REMOVE.Data1;
  if ( !v8 )
    v8 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_TARGET_DEVICE_QUERY_REMOVE.Data4;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    if ( !Context[220] )
    {
      v9 = 33;
      FveSaveFsMounted(Context, 33);
LABEL_23:
      LOBYTE(v11) = 1;
      LOBYTE(v10) = 1;
LABEL_120:
      FveClearFsMounted((_DWORD)Context, v10, v11, v12, v9);
      FveFsOffline(Context, 0);
      goto LABEL_46;
    }
    goto LABEL_46;
  }
  v13 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data1;
  if ( !v13 )
    v13 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data4;
  if ( !v13 )
  {
    if ( Context[220] )
      goto LABEL_46;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    v14 = 34;
    goto LABEL_130;
  }
  v15 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1;
  if ( !v15 )
    v15 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4;
  if ( !v15 )
  {
    v16 = 0;
    if ( *((_WORD *)NotificationStructure + 1) == 62 && *(_QWORD *)(NotificationStructure + 44) == 0x1000000006LL )
      v16 = RtlCompareMemory(NotificationStructure + 52, L"RAW", 6u) == 6;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, v16);
    }
    if ( !Context[220] )
    {
      LOBYTE(v4) = 1;
      if ( v16 )
      {
        FveSetFsMounted((_DWORD)Context, v4, 0, 0, 35);
      }
      else
      {
        LOBYTE(v5) = 1;
        FveSetFsMounted((_DWORD)Context, v4, v5, 0, 35);
        FveFsOnline(Context);
      }
    }
    goto LABEL_46;
  }
  v18 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1;
  if ( !v18 )
    v18 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_VOLUME_DISMOUNT.Data4;
  if ( v18 )
  {
    v31 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT_FAILED.Data1;
    if ( !v31 )
      v31 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_VOLUME_DISMOUNT_FAILED.Data4;
    if ( v31 )
    {
      v44 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_VOLUME_LOCK.Data1;
      if ( !v44 )
        v44 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_VOLUME_LOCK.Data4;
      if ( !v44 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
        }
        if ( !Context[220] )
        {
          v9 = 38;
          FveSaveFsMounted(Context, 38);
          v11 = 0;
          v10 = 0;
          goto LABEL_120;
        }
        goto LABEL_46;
      }
      v45 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_VOLUME_LOCK_FAILED.Data1;
      if ( !v45 )
        v45 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_VOLUME_LOCK_FAILED.Data4;
      if ( v45 )
      {
        v46 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_VOLUME_UNLOCK.Data1;
        if ( !v46 )
          v46 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_VOLUME_UNLOCK.Data4;
        if ( v46 )
          goto LABEL_46;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
        }
        if ( Context[220] )
          goto LABEL_46;
        FveRestoreFsMounted(Context, 39);
        LOBYTE(v47) = 1;
        LOBYTE(v48) = 1;
        LOBYTE(v49) = 1;
        FveSetFsMounted((_DWORD)Context, v49, v48, v47, 39);
LABEL_131:
        FveFsOnline(Context);
        goto LABEL_46;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
      }
      if ( Context[220] )
        goto LABEL_46;
      v14 = 40;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v32 = *((_QWORD *)Context + 1);
        v50 = 0;
        v33 = *(_QWORD *)(v32 + 10520);
        if ( (v33 & 3) != 0 )
        {
          v34 = (v33 & 2) != 0;
        }
        else
        {
          v35 = FveFeatWcosCheck(v32, (unsigned int)&v50, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
          v34 = v50;
          if ( v35 < 0 )
            v34 = 0;
        }
        if ( !v34
          || (v36 = *((_QWORD *)Context + 128)) == 0
          || !*(_WORD *)v36
          || *(_WORD *)(v36 + 2) < 0x10u
          || (v37 = 1, (*(_DWORD *)(v36 + 8) & 0x400000) == 0) )
        {
          v37 = 0;
        }
        v38 = *((_QWORD *)Context + 1);
        v50 = 0;
        v39 = *(_QWORD *)(v38 + 10520);
        if ( (v39 & 3) != 0 )
        {
          v40 = (v39 & 2) != 0;
        }
        else
        {
          v41 = FveFeatWcosCheck(v38, (unsigned int)&v50, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
          v40 = v50;
          if ( v41 < 0 )
            v40 = 0;
        }
        if ( !v40
          || (v42 = *((_QWORD *)Context + 128)) == 0
          || !*(_WORD *)v42
          || *(_WORD *)(v42 + 2) < 0x10u
          || (v43 = 1, (*(_DWORD *)(v42 + 8) & 0x80000) == 0) )
        {
          v43 = 0;
        }
        WPP_SF_LLLL(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
          (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) >> 8) & 1,
          (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) >> 22) & 1,
          v43,
          v37);
      }
      if ( Context[220] )
        goto LABEL_46;
      v14 = 37;
    }
LABEL_130:
    FveRestoreFsMounted(Context, v14);
    goto LABEL_131;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v19 = *((_QWORD *)Context + 1);
    v50 = 0;
    v20 = *(_QWORD *)(v19 + 10520);
    if ( (v20 & 3) != 0 )
    {
      v21 = (v20 & 2) != 0;
    }
    else
    {
      v22 = FveFeatWcosCheck(v19, (unsigned int)&v50, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      v21 = v50;
      if ( v22 < 0 )
        v21 = 0;
    }
    if ( !v21
      || (v23 = *((_QWORD *)Context + 128)) == 0
      || !*(_WORD *)v23
      || *(_WORD *)(v23 + 2) < 0x10u
      || (v24 = 1, (*(_DWORD *)(v23 + 8) & 0x400000) == 0) )
    {
      v24 = 0;
    }
    v25 = *((_QWORD *)Context + 1);
    v50 = 0;
    v26 = *(_QWORD *)(v25 + 10520);
    if ( (v26 & 3) != 0 )
    {
      v27 = (v26 & 2) != 0;
    }
    else
    {
      v28 = FveFeatWcosCheck(v25, (unsigned int)&v50, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      v27 = v50;
      if ( v28 < 0 )
        v27 = 0;
    }
    if ( !v27
      || (v29 = *((_QWORD *)Context + 128)) == 0
      || !*(_WORD *)v29
      || *(_WORD *)(v29 + 2) < 0x10u
      || (v30 = 1, (*(_DWORD *)(v29 + 8) & 0x80000) == 0) )
    {
      v30 = 0;
    }
    WPP_SF_LLLL(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
      (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) >> 8) & 1,
      (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) >> 22) & 1,
      v30,
      v24);
  }
  if ( !Context[220] && (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) & 0x400100) == 0 )
  {
    v9 = 36;
    FveSaveFsMounted(Context, 36);
    goto LABEL_23;
  }
LABEL_46:
  IoSetThreadHardErrorMode(v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14008cf00  push    rbp
0x14008cf02  push    rbx
0x14008cf03  push    rsi
0x14008cf04  push    rdi
0x14008cf05  push    r12
0x14008cf07  push    r13
0x14008cf09  push    r14
0x14008cf0b  push    r15
0x14008cf0d  mov     rbp, rsp
0x14008cf10  sub     rsp, 68h
0x14008cf14  mov     rbx, rdx
0x14008cf17  mov     rdi, rcx
0x14008cf1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cf21  lea     rsi, WPP_GLOBAL_Control
0x14008cf28  lea     r15, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14008cf2f  cmp     rcx, rsi
0x14008cf32  jz      short loc_14008CF5F
0x14008cf34  mov     eax, [rcx+2Ch]
0x14008cf37  test    al, 40h
0x14008cf39  jz      short loc_14008CF5F
0x14008cf3b  cmp     byte ptr [rcx+29h], 5
0x14008cf3f  jb      short loc_14008CF5F
0x14008cf41  mov     eax, [rbx+370h]
0x14008cf47  mov     edx, 0Dh
0x14008cf4c  mov     rcx, [rcx+18h]
0x14008cf50  mov     r9, rbx
0x14008cf53  mov     r8, r15
0x14008cf56  mov     dword ptr [rsp+68h+var_48], eax
0x14008cf5a  call    WPP_SF_qd
0x14008cf5f  xor     ecx, ecx; EnableHardErrors
0x14008cf61  call    cs:__imp_IoSetThreadHardErrorMode
0x14008cf68  nop     dword ptr [rax+rax+00h]
0x14008cf6d  mov     rcx, [rdi+4]
0x14008cf71  mov     r12b, al
0x14008cf74  sub     rcx, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data1
0x14008cf7b  jnz     short loc_14008CF88
0x14008cf7d  mov     rcx, [rdi+0Ch]
0x14008cf81  sub     rcx, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data4
0x14008cf88  xor     r13d, r13d
0x14008cf8b  test    rcx, rcx
0x14008cf8e  jnz     short loc_14008CFD3
0x14008cf90  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cf97  cmp     rcx, rsi
0x14008cf9a  jz      short loc_14008CFB9
0x14008cf9c  mov     eax, [rcx+2Ch]
0x14008cf9f  test    al, 40h
0x14008cfa1  jz      short loc_14008CFB9
0x14008cfa3  cmp     byte ptr [rcx+29h], 4
0x14008cfa7  jb      short loc_14008CFB9
0x14008cfa9  mov     rcx, [rcx+18h]
0x14008cfad  lea     edx, [r13+0Eh]
0x14008cfb1  mov     r8, r15
0x14008cfb4  call    WPP_SF_
0x14008cfb9  cmp     [rbx+370h], r13d
0x14008cfc0  jnz     loc_14008D173
0x14008cfc6  mov     rcx, rbx
0x14008cfc9  call    FveUnregisterPnpNotifications
0x14008cfce  jmp     loc_14008D173
0x14008cfd3  mov     rax, [rdi+4]
0x14008cfd7  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_QUERY_REMOVE.Data1
0x14008cfde  jnz     short loc_14008CFEB
0x14008cfe0  mov     rax, [rdi+0Ch]
0x14008cfe4  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_QUERY_REMOVE.Data4
0x14008cfeb  test    rax, rax
0x14008cfee  jnz     short loc_14008D044
0x14008cff0  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cff7  cmp     rcx, rsi
0x14008cffa  jz      short loc_14008D01A
0x14008cffc  mov     eax, [rcx+2Ch]
0x14008cfff  test    al, 40h
0x14008d001  jz      short loc_14008D01A
0x14008d003  cmp     byte ptr [rcx+29h], 4
0x14008d007  jb      short loc_14008D01A
0x14008d009  mov     rcx, [rcx+18h]
0x14008d00d  mov     edx, 0Fh
0x14008d012  mov     r8, r15
0x14008d015  call    WPP_SF_
0x14008d01a  cmp     [rbx+370h], r13d
0x14008d021  jnz     loc_14008D173
0x14008d027  mov     edi, 21h ; '!'
0x14008d02c  mov     rcx, rbx
0x14008d02f  mov     edx, edi
0x14008d031  call    FveSaveFsMounted
0x14008d036  lea     esi, [rdi-20h]
0x14008d039  mov     r8b, sil
0x14008d03c  mov     dl, sil
0x14008d03f  jmp     loc_14008D5BB
0x14008d044  mov     rax, [rdi+4]
0x14008d048  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data1
0x14008d04f  jnz     short loc_14008D05C
0x14008d051  mov     rax, [rdi+0Ch]
0x14008d055  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data4
0x14008d05c  test    rax, rax
0x14008d05f  jnz     short loc_14008D0A2
0x14008d061  cmp     [rbx+370h], r13d
0x14008d068  jnz     loc_14008D173
0x14008d06e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d075  cmp     rcx, rsi
0x14008d078  jz      short loc_14008D098
0x14008d07a  mov     eax, [rcx+2Ch]
0x14008d07d  test    al, 40h
0x14008d07f  jz      short loc_14008D098
0x14008d081  cmp     byte ptr [rcx+29h], 4
0x14008d085  jb      short loc_14008D098
0x14008d087  mov     rcx, [rcx+18h]
0x14008d08b  mov     edx, 10h
0x14008d090  mov     r8, r15
0x14008d093  call    WPP_SF_
0x14008d098  mov     edx, 22h ; '"'
0x14008d09d  jmp     loc_14008D62F
0x14008d0a2  mov     rax, [rdi+4]
0x14008d0a6  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x14008d0ad  jnz     short loc_14008D0BA
0x14008d0af  mov     rax, [rdi+0Ch]
0x14008d0b3  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x14008d0ba  test    rax, rax
0x14008d0bd  jnz     loc_14008D1D1
0x14008d0c3  cmp     word ptr [rdi+2], 3Eh ; '>'
0x14008d0c8  lea     esi, [rax+1]
0x14008d0cb  movzx   r15d, r13b
0x14008d0cf  jnz     short loc_14008D104
0x14008d0d1  lea     r14d, [rax+10h]
0x14008d0d5  cmp     [rdi+30h], r14d
0x14008d0d9  jnz     short loc_14008D104
0x14008d0db  cmp     dword ptr [rdi+2Ch], 6
0x14008d0df  jnz     short loc_14008D104
0x14008d0e1  lea     rcx, [rdi+34h]; Source1
0x14008d0e5  lea     r8d, [rax+6]; Length
0x14008d0e9  lea     rdx, aRaw; "RAW"
0x14008d0f0  call    cs:__imp_RtlCompareMemory
0x14008d0f7  nop     dword ptr [rax+rax+00h]
0x14008d0fc  cmp     rax, 6
0x14008d100  cmovz   r15d, esi
0x14008d104  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d10b  lea     rax, WPP_GLOBAL_Control
0x14008d112  cmp     rcx, rax
0x14008d115  jz      short loc_14008D13D
0x14008d117  mov     eax, [rcx+2Ch]
0x14008d11a  test    al, 40h
0x14008d11c  jz      short loc_14008D13D
0x14008d11e  cmp     byte ptr [rcx+29h], 4
0x14008d122  jb      short loc_14008D13D
0x14008d124  mov     rcx, [rcx+18h]
0x14008d128  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14008d12f  movzx   r9d, r15b
0x14008d133  mov     edx, 11h
0x14008d138  call    WPP_SF_d
0x14008d13d  cmp     [rbx+370h], r13d
0x14008d144  jnz     short loc_14008D16C
0x14008d146  xor     r9d, r9d
0x14008d149  mov     dword ptr [rsp+68h+var_48], 23h ; '#'
0x14008d151  mov     dl, sil
0x14008d154  mov     rcx, rbx
0x14008d157  test    r15b, r15b
0x14008d15a  jnz     short loc_14008D1C7
0x14008d15c  mov     r8b, sil
0x14008d15f  call    FveSetFsMounted
0x14008d164  mov     rcx, rbx
0x14008d167  call    FveFsOnline
0x14008d16c  lea     r15, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14008d173  mov     cl, r12b; EnableHardErrors
0x14008d176  call    cs:__imp_IoSetThreadHardErrorMode
0x14008d17d  nop     dword ptr [rax+rax+00h]
0x14008d182  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d189  lea     rax, WPP_GLOBAL_Control
0x14008d190  cmp     rcx, rax
0x14008d193  jz      short loc_14008D1B3
0x14008d195  mov     eax, [rcx+2Ch]
0x14008d198  test    al, 40h
0x14008d19a  jz      short loc_14008D1B3
0x14008d19c  cmp     byte ptr [rcx+29h], 5
0x14008d1a0  jb      short loc_14008D1B3
0x14008d1a2  mov     rcx, [rcx+18h]
0x14008d1a6  mov     edx, 17h
0x14008d1ab  mov     r8, r15
0x14008d1ae  call    WPP_SF_
0x14008d1b3  xor     eax, eax
0x14008d1b5  add     rsp, 68h
0x14008d1b9  pop     r15
0x14008d1bb  pop     r14
0x14008d1bd  pop     r13
0x14008d1bf  pop     r12
0x14008d1c1  pop     rdi
0x14008d1c2  pop     rsi
0x14008d1c3  pop     rbx
0x14008d1c4  pop     rbp
0x14008d1c5  retn
0x14008d1c7  xor     r8d, r8d
0x14008d1ca  call    FveSetFsMounted
0x14008d1cf  jmp     short loc_14008D16C
0x14008d1d1  mov     rax, [rdi+4]
0x14008d1d5  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x14008d1dc  jnz     short loc_14008D1E9
0x14008d1de  mov     rax, [rdi+0Ch]
0x14008d1e2  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x14008d1e9  test    rax, rax
0x14008d1ec  jnz     loc_14008D3A2
0x14008d1f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d1f9  lea     esi, [rax+1]
0x14008d1fc  lea     rax, WPP_GLOBAL_Control
0x14008d203  cmp     rcx, rax
0x14008d206  jz      loc_14008D370
0x14008d20c  mov     eax, [rcx+2Ch]
0x14008d20f  test    al, 40h
0x14008d211  jz      loc_14008D370
0x14008d217  cmp     byte ptr [rcx+29h], 4
0x14008d21b  jb      loc_14008D370
0x14008d221  mov     rcx, [rbx+8]
0x14008d225  mov     [rbp+arg_0], r13b
0x14008d229  mov     rdx, [rcx+2918h]
0x14008d230  test    dl, 3
0x14008d233  jz      short loc_14008D23C
0x14008d235  shr     dl, 1
0x14008d237  and     dl, sil
0x14008d23a  jmp     short loc_14008D27D
0x14008d23c  mov     [rsp+68h+var_10], r13
0x14008d241  lea     rdx, [rbp+arg_0]
0x14008d245  mov     [rsp+68h+var_18], r13
0x14008d24a  xor     r9d, r9d
0x14008d24d  mov     [rsp+68h+var_20], r13
0x14008d252  xor     r8d, r8d
0x14008d255  mov     [rsp+68h+var_28], r13
0x14008d25a  mov     [rsp+68h+var_30], r13
0x14008d25f  mov     [rsp+68h+var_38], r13
0x14008d264  mov     [rsp+68h+var_40], r13
0x14008d269  mov     [rsp+68h+var_48], r13
0x14008d26e  call    FveFeatWcosCheck
0x14008d273  movzx   edx, [rbp+arg_0]
0x14008d277  test    eax, eax
0x14008d279  cmovs   edx, r13d
0x14008d27d  mov     r14d, 10h
0x14008d283  test    dl, dl
0x14008d285  jz      short loc_14008D2AB
0x14008d287  mov     rax, [rbx+400h]
0x14008d28e  test    rax, rax
0x14008d291  jz      short loc_14008D2AB
0x14008d293  cmp     [rax], si
0x14008d296  jb      short loc_14008D2AB
0x14008d298  cmp     [rax+2], r14w
0x14008d29d  jb      short loc_14008D2AB
0x14008d29f  mov     eax, [rax+8]
0x14008d2a2  mov     edi, esi
0x14008d2a4  bt      rax, 16h
0x14008d2a9  jb      short loc_14008D2AE
0x14008d2ab  mov     edi, r13d
0x14008d2ae  mov     rcx, [rbx+8]
0x14008d2b2  mov     [rbp+arg_0], r13b
0x14008d2b6  mov     rdx, [rcx+2918h]
0x14008d2bd  test    dl, 3
0x14008d2c0  jz      short loc_14008D2C9
0x14008d2c2  shr     dl, 1
0x14008d2c4  and     dl, sil
0x14008d2c7  jmp     short loc_14008D30A
0x14008d2c9  mov     [rsp+68h+var_10], r13
0x14008d2ce  lea     rdx, [rbp+arg_0]
0x14008d2d2  mov     [rsp+68h+var_18], r13
0x14008d2d7  xor     r9d, r9d
0x14008d2da  mov     [rsp+68h+var_20], r13
0x14008d2df  xor     r8d, r8d
0x14008d2e2  mov     [rsp+68h+var_28], r13
0x14008d2e7  mov     [rsp+68h+var_30], r13
0x14008d2ec  mov     [rsp+68h+var_38], r13
0x14008d2f1  mov     [rsp+68h+var_40], r13
0x14008d2f6  mov     [rsp+68h+var_48], r13
0x14008d2fb  call    FveFeatWcosCheck
0x14008d300  movzx   edx, [rbp+arg_0]
0x14008d304  test    eax, eax
0x14008d306  cmovs   edx, r13d
0x14008d30a  test    dl, dl
0x14008d30c  jz      short loc_14008D332
0x14008d30e  mov     rax, [rbx+400h]
0x14008d315  test    rax, rax
0x14008d318  jz      short loc_14008D332
0x14008d31a  cmp     [rax], si
0x14008d31d  jb      short loc_14008D332
0x14008d31f  cmp     [rax+2], r14w
0x14008d324  jb      short loc_14008D332
0x14008d326  mov     eax, [rax+8]
0x14008d329  mov     ecx, esi
0x14008d32b  bt      rax, 13h
0x14008d330  jb      short loc_14008D335
0x14008d332  mov     ecx, r13d
0x14008d335  mov     rax, [rbx+78h]
0x14008d339  mov     edx, 12h
0x14008d33e  mov     dword ptr [rsp+68h+var_38], edi
0x14008d342  mov     r8, r15
0x14008d345  mov     dword ptr [rsp+68h+var_40], ecx
0x14008d349  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d350  mov     r9d, [rax+30h]
0x14008d354  mov     eax, r9d
0x14008d357  shr     eax, 16h
0x14008d35a  shr     r9d, 8
0x14008d35e  and     eax, esi
0x14008d360  mov     rcx, [rcx+18h]
0x14008d364  and     r9d, esi
0x14008d367  mov     dword ptr [rsp+68h+var_48], eax
0x14008d36b  call    WPP_SF_LLLL
0x14008d370  cmp     [rbx+370h], r13d
0x14008d377  jnz     loc_14008D173
0x14008d37d  mov     rax, [rbx+78h]
  ... truncated ...
```
