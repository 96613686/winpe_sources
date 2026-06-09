# FvePnpNotification2

- ea: `0x140062980`
- end: `0x140063139`
- name: `FvePnpNotification2`
- size: `1977`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000ba88`
- `0x14000c60c`
- `0x140061878`
- `0x140062980`
- `0x14006368c`
- `0x1400637d4`
- `0x140063848`
- `0x140063ca0`
- `0x14008b630`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140062b69`
- `ntoskrnl!RtlCompareMemory` at `0x140062b69`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1400629e1`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140062be6`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1400629e1`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140062be6`

## pseudocode

```c
__int64 __fastcall FvePnpNotification2(char *NotificationStructure, _DWORD *Context)
{
  int v4; // edx
  int v5; // r8d
  BOOLEAN v6; // r13
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rdx
  bool v11; // r12
  __int64 v13; // rax
  __int64 v14; // rcx
  bool v15; // cl
  int v16; // eax
  __int64 v17; // rax
  int v18; // esi
  __int64 v19; // rax
  __int64 v20; // rcx
  bool v21; // cl
  int v22; // eax
  __int64 v23; // rax
  int v24; // ecx
  __int64 v25; // rax
  __int64 v26; // rcx
  bool v27; // cl
  int v28; // eax
  __int64 v29; // rax
  int v30; // esi
  __int64 v31; // rax
  __int64 v32; // rcx
  bool v33; // cl
  int v34; // eax
  __int64 v35; // rax
  int v36; // ecx
  int v37; // r9d
  int v38; // r8d
  int v39; // edx
  int v40; // [rsp+20h] [rbp-48h]
  bool v41; // [rsp+B0h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      32,
      WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
      Context,
      Context[224]);
  }
  v6 = IoSetThreadHardErrorMode(0);
  if ( *(_QWORD *)(NotificationStructure + 4) == *(_QWORD *)&GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data1
    && *(_QWORD *)(NotificationStructure + 12) == *(_QWORD *)GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    if ( !Context[224] )
      FveUnregisterPnpNotifications2(Context);
    goto LABEL_43;
  }
  if ( *(_QWORD *)(NotificationStructure + 4) == *(_QWORD *)&GUID_TARGET_DEVICE_QUERY_REMOVE.Data1
    && *(_QWORD *)(NotificationStructure + 12) == *(_QWORD *)GUID_TARGET_DEVICE_QUERY_REMOVE.Data4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    if ( !Context[224] )
    {
      FveSaveFsMounted2(Context, 33);
      v40 = 33;
LABEL_78:
      LOBYTE(v8) = 1;
      LOBYTE(v7) = 1;
LABEL_115:
      FveClearFsMounted2((_DWORD)Context, v7, v8, v9, v40);
      goto LABEL_43;
    }
    goto LABEL_43;
  }
  if ( *(_QWORD *)(NotificationStructure + 4) == *(_QWORD *)&GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data1
    && *(_QWORD *)(NotificationStructure + 12) == *(_QWORD *)GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data4 )
  {
    if ( Context[224] )
      goto LABEL_43;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    v10 = 34;
    goto LABEL_124;
  }
  if ( *(_QWORD *)(NotificationStructure + 4) == *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1
    && *(_QWORD *)(NotificationStructure + 12) == *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4 )
  {
    v11 = 0;
    if ( *((_WORD *)NotificationStructure + 1) == 62
      && *((_DWORD *)NotificationStructure + 12) == 16
      && *((_DWORD *)NotificationStructure + 11) == 6 )
    {
      v11 = RtlCompareMemory(NotificationStructure + 52, L"RAW", 6u) == 6;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, v11);
    }
    if ( !Context[224] )
    {
      LOBYTE(v4) = 1;
      if ( v11 )
        v5 = 0;
      else
        LOBYTE(v5) = 1;
      FveSetFsMounted2((_DWORD)Context, v4, v5, 0, 35);
    }
    goto LABEL_43;
  }
  if ( *(_QWORD *)(NotificationStructure + 4) != *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT.Data1
    || *(_QWORD *)(NotificationStructure + 12) != *(_QWORD *)GUID_IO_VOLUME_DISMOUNT.Data4 )
  {
    if ( *(_QWORD *)(NotificationStructure + 4) == *(_QWORD *)&GUID_IO_VOLUME_DISMOUNT_FAILED.Data1
      && *(_QWORD *)(NotificationStructure + 12) == *(_QWORD *)GUID_IO_VOLUME_DISMOUNT_FAILED.Data4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v25 = *((_QWORD *)Context + 1);
        v41 = 0;
        v26 = *(_QWORD *)(v25 + 10272);
        if ( (v26 & 3) != 0 )
        {
          v27 = (v26 & 2) != 0;
        }
        else
        {
          v28 = FveFeatWcosCheck(v25, (unsigned int)&v41, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
          v27 = v41;
          if ( v28 < 0 )
            v27 = 0;
        }
        if ( !v27
          || (v29 = *((_QWORD *)Context + 128)) == 0
          || !*(_WORD *)v29
          || *(_WORD *)(v29 + 2) < 0x10u
          || (v30 = 1, (*(_DWORD *)(v29 + 8) & 0x400000) == 0) )
        {
          v30 = 0;
        }
        v31 = *((_QWORD *)Context + 1);
        v41 = 0;
        v32 = *(_QWORD *)(v31 + 10272);
        if ( (v32 & 3) != 0 )
        {
          v33 = (v32 & 2) != 0;
        }
        else
        {
          v34 = FveFeatWcosCheck(v31, (unsigned int)&v41, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
          v33 = v41;
          if ( v34 < 0 )
            v33 = 0;
        }
        if ( !v33
          || (v35 = *((_QWORD *)Context + 128)) == 0
          || !*(_WORD *)v35
          || *(_WORD *)(v35 + 2) < 0x10u
          || (v36 = 1, (*(_DWORD *)(v35 + 8) & 0x80000) == 0) )
        {
          v36 = 0;
        }
        WPP_SF_LLLL(
          WPP_GLOBAL_Control->AttachedDevice,
          38,
          WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
          (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) >> 8) & 1,
          (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) >> 22) & 1,
          v36,
          v30);
      }
      if ( Context[224] )
        goto LABEL_43;
      v10 = 37;
    }
    else
    {
      if ( *(_QWORD *)(NotificationStructure + 4) == *(_QWORD *)&GUID_IO_VOLUME_LOCK.Data1
        && *(_QWORD *)(NotificationStructure + 12) == *(_QWORD *)GUID_IO_VOLUME_LOCK.Data4 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
        }
        if ( !Context[224] )
        {
          FveSaveFsMounted2(Context, 38);
          v8 = 0;
          v40 = 38;
          v7 = 0;
          goto LABEL_115;
        }
        goto LABEL_43;
      }
      if ( *(_QWORD *)(NotificationStructure + 4) != *(_QWORD *)&GUID_IO_VOLUME_LOCK_FAILED.Data1
        || *(_QWORD *)(NotificationStructure + 12) != *(_QWORD *)GUID_IO_VOLUME_LOCK_FAILED.Data4 )
      {
        if ( *(_QWORD *)(NotificationStructure + 4) == *(_QWORD *)&GUID_IO_VOLUME_UNLOCK.Data1
          && *(_QWORD *)(NotificationStructure + 12) == *(_QWORD *)GUID_IO_VOLUME_UNLOCK.Data4 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
          }
          if ( !Context[224] )
          {
            FveRestoreFsMounted2(Context, 39);
            LOBYTE(v37) = 1;
            LOBYTE(v38) = 1;
            LOBYTE(v39) = 1;
            FveSetFsMounted2((_DWORD)Context, v39, v38, v37, 39);
          }
        }
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
      }
      if ( Context[224] )
        goto LABEL_43;
      v10 = 40;
    }
LABEL_124:
    FveRestoreFsMounted2(Context, v10);
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v13 = *((_QWORD *)Context + 1);
    v41 = 0;
    v14 = *(_QWORD *)(v13 + 10272);
    if ( (v14 & 3) != 0 )
    {
      v15 = (v14 & 2) != 0;
    }
    else
    {
      v16 = FveFeatWcosCheck(v13, (unsigned int)&v41, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      v15 = v41;
      if ( v16 < 0 )
        v15 = 0;
    }
    if ( !v15
      || (v17 = *((_QWORD *)Context + 128)) == 0
      || !*(_WORD *)v17
      || *(_WORD *)(v17 + 2) < 0x10u
      || (v18 = 1, (*(_DWORD *)(v17 + 8) & 0x400000) == 0) )
    {
      v18 = 0;
    }
    v19 = *((_QWORD *)Context + 1);
    v41 = 0;
    v20 = *(_QWORD *)(v19 + 10272);
    if ( (v20 & 3) != 0 )
    {
      v21 = (v20 & 2) != 0;
    }
    else
    {
      v22 = FveFeatWcosCheck(v19, (unsigned int)&v41, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      v21 = v41;
      if ( v22 < 0 )
        v21 = 0;
    }
    if ( !v21
      || (v23 = *((_QWORD *)Context + 128)) == 0
      || !*(_WORD *)v23
      || *(_WORD *)(v23 + 2) < 0x10u
      || (v24 = 1, (*(_DWORD *)(v23 + 8) & 0x80000) == 0) )
    {
      v24 = 0;
    }
    WPP_SF_LLLL(
      WPP_GLOBAL_Control->AttachedDevice,
      37,
      WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
      (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) >> 8) & 1,
      (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) >> 22) & 1,
      v24,
      v18);
  }
  if ( !Context[224] && (*(_DWORD *)(*((_QWORD *)Context + 15) + 48LL) & 0x400100) == 0 )
  {
    FveSaveFsMounted2(Context, 36);
    v40 = 36;
    goto LABEL_78;
  }
LABEL_43:
  IoSetThreadHardErrorMode(v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140062980  push    rbp
0x140062982  push    rbx
0x140062983  push    rsi
0x140062984  push    rdi
0x140062985  push    r12
0x140062987  push    r13
0x140062989  push    r14
0x14006298b  push    r15
0x14006298d  mov     rbp, rsp
0x140062990  sub     rsp, 68h
0x140062994  mov     rdi, rdx
0x140062997  mov     rsi, rcx
0x14006299a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400629a1  lea     r14, WPP_GLOBAL_Control
0x1400629a8  lea     r12, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400629af  cmp     rcx, r14
0x1400629b2  jz      short loc_1400629DF
0x1400629b4  mov     eax, [rcx+2Ch]
0x1400629b7  test    al, 40h
0x1400629b9  jz      short loc_1400629DF
0x1400629bb  cmp     byte ptr [rcx+29h], 5
0x1400629bf  jb      short loc_1400629DF
0x1400629c1  mov     eax, [rdi+380h]
0x1400629c7  mov     edx, 20h ; ' '
0x1400629cc  mov     rcx, [rcx+18h]
0x1400629d0  mov     r9, rdi
0x1400629d3  mov     r8, r12
0x1400629d6  mov     dword ptr [rsp+68h+var_48], eax
0x1400629da  call    WPP_SF_qd
0x1400629df  xor     ecx, ecx; EnableHardErrors
0x1400629e1  call    cs:__imp_IoSetThreadHardErrorMode
0x1400629e8  nop     dword ptr [rax+rax+00h]
0x1400629ed  mov     rcx, [rsi+4]
0x1400629f1  mov     r13b, al
0x1400629f4  cmp     rcx, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data1
0x1400629fb  jnz     short loc_140062A4F
0x1400629fd  mov     rcx, [rsi+0Ch]
0x140062a01  cmp     rcx, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data4
0x140062a08  jnz     short loc_140062A4F
0x140062a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140062a11  cmp     rcx, r14
0x140062a14  jz      short loc_140062A34
0x140062a16  mov     eax, [rcx+2Ch]
0x140062a19  test    al, 40h
0x140062a1b  jz      short loc_140062A34
0x140062a1d  cmp     byte ptr [rcx+29h], 4
0x140062a21  jb      short loc_140062A34
0x140062a23  mov     rcx, [rcx+18h]
0x140062a27  mov     edx, 21h ; '!'
0x140062a2c  mov     r8, r12
0x140062a2f  call    WPP_SF_
0x140062a34  xor     ebx, ebx
0x140062a36  cmp     [rdi+380h], ebx
0x140062a3c  jnz     loc_140062BE3
0x140062a42  mov     rcx, rdi
0x140062a45  call    FveUnregisterPnpNotifications2
0x140062a4a  jmp     loc_140062BE3
0x140062a4f  mov     rax, [rsi+4]
0x140062a53  cmp     rax, qword ptr cs:GUID_TARGET_DEVICE_QUERY_REMOVE.Data1
0x140062a5a  jnz     short loc_140062ABD
0x140062a5c  mov     rax, [rsi+0Ch]
0x140062a60  cmp     rax, qword ptr cs:GUID_TARGET_DEVICE_QUERY_REMOVE.Data4
0x140062a67  jnz     short loc_140062ABD
0x140062a69  mov     rcx, cs:WPP_GLOBAL_Control
0x140062a70  cmp     rcx, r14
0x140062a73  jz      short loc_140062A93
0x140062a75  mov     eax, [rcx+2Ch]
0x140062a78  test    al, 40h
0x140062a7a  jz      short loc_140062A93
0x140062a7c  cmp     byte ptr [rcx+29h], 4
0x140062a80  jb      short loc_140062A93
0x140062a82  mov     rcx, [rcx+18h]
0x140062a86  mov     edx, 22h ; '"'
0x140062a8b  mov     r8, r12
0x140062a8e  call    WPP_SF_
0x140062a93  xor     ebx, ebx
0x140062a95  cmp     [rdi+380h], ebx
0x140062a9b  jnz     loc_140062BE3
0x140062aa1  lea     edx, [rbx+21h]
0x140062aa4  mov     rcx, rdi
0x140062aa7  call    FveSaveFsMounted2
0x140062aac  mov     dword ptr [rsp+68h+var_48], 21h ; '!'
0x140062ab4  lea     r14d, [rbx+1]
0x140062ab8  jmp     loc_140062E16
0x140062abd  mov     rax, [rsi+4]
0x140062ac1  cmp     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data1
0x140062ac8  jnz     short loc_140062B17
0x140062aca  mov     rax, [rsi+0Ch]
0x140062ace  cmp     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data4
0x140062ad5  jnz     short loc_140062B17
0x140062ad7  xor     ebx, ebx
0x140062ad9  cmp     [rdi+380h], ebx
0x140062adf  jnz     loc_140062BE3
0x140062ae5  mov     rcx, cs:WPP_GLOBAL_Control
0x140062aec  cmp     rcx, r14
0x140062aef  jz      short loc_140062B0D
0x140062af1  mov     eax, [rcx+2Ch]
0x140062af4  test    al, 40h
0x140062af6  jz      short loc_140062B0D
0x140062af8  cmp     byte ptr [rcx+29h], 4
0x140062afc  jb      short loc_140062B0D
0x140062afe  mov     rcx, [rcx+18h]
0x140062b02  lea     edx, [rbx+23h]
0x140062b05  mov     r8, r12
0x140062b08  call    WPP_SF_
0x140062b0d  mov     edx, 22h ; '"'
0x140062b12  jmp     loc_1400630A5
0x140062b17  mov     rax, [rsi+4]
0x140062b1b  cmp     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x140062b22  jnz     loc_140062C3C
0x140062b28  mov     rax, [rsi+0Ch]
0x140062b2c  cmp     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x140062b33  jnz     loc_140062C3C
0x140062b39  xor     ebx, ebx
0x140062b3b  cmp     word ptr [rsi+2], 3Eh ; '>'
0x140062b40  movzx   r12d, bl
0x140062b44  lea     r14d, [rbx+1]
0x140062b48  jnz     short loc_140062B7D
0x140062b4a  lea     r15d, [rbx+10h]
0x140062b4e  cmp     [rsi+30h], r15d
0x140062b52  jnz     short loc_140062B7D
0x140062b54  cmp     dword ptr [rsi+2Ch], 6
0x140062b58  jnz     short loc_140062B7D
0x140062b5a  lea     rcx, [rsi+34h]; Source1
0x140062b5e  lea     r8d, [rbx+6]; Length
0x140062b62  lea     rdx, aRaw; "RAW"
0x140062b69  call    cs:__imp_RtlCompareMemory
0x140062b70  nop     dword ptr [rax+rax+00h]
0x140062b75  cmp     rax, 6
0x140062b79  cmovz   r12d, r14d
0x140062b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140062b84  lea     rax, WPP_GLOBAL_Control
0x140062b8b  cmp     rcx, rax
0x140062b8e  jz      short loc_140062BB6
0x140062b90  mov     eax, [rcx+2Ch]
0x140062b93  test    al, 40h
0x140062b95  jz      short loc_140062BB6
0x140062b97  cmp     byte ptr [rcx+29h], 4
0x140062b9b  jb      short loc_140062BB6
0x140062b9d  mov     rcx, [rcx+18h]
0x140062ba1  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140062ba8  movzx   r9d, r12b
0x140062bac  mov     edx, 24h ; '$'
0x140062bb1  call    WPP_SF_d
0x140062bb6  cmp     [rdi+380h], ebx
0x140062bbc  jnz     short loc_140062BDC
0x140062bbe  xor     r9d, r9d
0x140062bc1  mov     dword ptr [rsp+68h+var_48], 23h ; '#'
0x140062bc9  mov     dl, r14b
0x140062bcc  mov     rcx, rdi
0x140062bcf  test    r12b, r12b
0x140062bd2  jnz     short loc_140062C37
0x140062bd4  mov     r8b, r14b
0x140062bd7  call    FveSetFsMounted2
0x140062bdc  lea     r12, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140062be3  mov     cl, r13b; EnableHardErrors
0x140062be6  call    cs:__imp_IoSetThreadHardErrorMode
0x140062bed  nop     dword ptr [rax+rax+00h]
0x140062bf2  mov     rcx, cs:WPP_GLOBAL_Control
0x140062bf9  lea     rax, WPP_GLOBAL_Control
0x140062c00  cmp     rcx, rax
0x140062c03  jz      short loc_140062C23
0x140062c05  mov     eax, [rcx+2Ch]
0x140062c08  test    al, 40h
0x140062c0a  jz      short loc_140062C23
0x140062c0c  cmp     byte ptr [rcx+29h], 5
0x140062c10  jb      short loc_140062C23
0x140062c12  mov     rcx, [rcx+18h]
0x140062c16  mov     edx, 2Ah ; '*'
0x140062c1b  mov     r8, r12
0x140062c1e  call    WPP_SF_
0x140062c23  xor     eax, eax
0x140062c25  add     rsp, 68h
0x140062c29  pop     r15
0x140062c2b  pop     r14
0x140062c2d  pop     r13
0x140062c2f  pop     r12
0x140062c31  pop     rdi
0x140062c32  pop     rsi
0x140062c33  pop     rbx
0x140062c34  pop     rbp
0x140062c35  retn
0x140062c37  xor     r8d, r8d
0x140062c3a  jmp     short loc_140062BD7
0x140062c3c  mov     rax, [rsi+4]
0x140062c40  cmp     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x140062c47  jnz     loc_140062E21
0x140062c4d  mov     rax, [rsi+0Ch]
0x140062c51  cmp     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x140062c58  jnz     loc_140062E21
0x140062c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140062c65  lea     rax, WPP_GLOBAL_Control
0x140062c6c  xor     ebx, ebx
0x140062c6e  lea     r14d, [rbx+1]
0x140062c72  cmp     rcx, rax
0x140062c75  jz      loc_140062DE4
0x140062c7b  mov     eax, [rcx+2Ch]
0x140062c7e  test    al, 40h
0x140062c80  jz      loc_140062DE4
0x140062c86  cmp     byte ptr [rcx+29h], 4
0x140062c8a  jb      loc_140062DE4
0x140062c90  mov     rax, [rdi+8]
0x140062c94  mov     [rbp+arg_0], bl
0x140062c97  mov     rcx, [rax+2820h]
0x140062c9e  test    cl, 3
0x140062ca1  jz      short loc_140062CAA
0x140062ca3  shr     cl, 1
0x140062ca5  and     cl, r14b
0x140062ca8  jmp     short loc_140062CED
0x140062caa  mov     [rsp+68h+var_10], rbx
0x140062caf  lea     rdx, [rbp+arg_0]
0x140062cb3  mov     [rsp+68h+var_18], rbx
0x140062cb8  xor     r9d, r9d
0x140062cbb  mov     [rsp+68h+var_20], rbx
0x140062cc0  xor     r8d, r8d
0x140062cc3  mov     [rsp+68h+var_28], rbx
0x140062cc8  mov     rcx, rax
0x140062ccb  mov     [rsp+68h+var_30], rbx
0x140062cd0  mov     [rsp+68h+var_38], rbx
0x140062cd5  mov     [rsp+68h+var_40], rbx
0x140062cda  mov     [rsp+68h+var_48], rbx
0x140062cdf  call    FveFeatWcosCheck
0x140062ce4  movzx   ecx, [rbp+arg_0]
0x140062ce8  test    eax, eax
0x140062cea  cmovs   ecx, ebx
0x140062ced  mov     r15d, 10h
0x140062cf3  test    cl, cl
0x140062cf5  jz      short loc_140062D1D
0x140062cf7  mov     rax, [rdi+400h]
0x140062cfe  test    rax, rax
0x140062d01  jz      short loc_140062D1D
0x140062d03  cmp     [rax], r14w
0x140062d07  jb      short loc_140062D1D
0x140062d09  cmp     [rax+2], r15w
0x140062d0e  jb      short loc_140062D1D
0x140062d10  mov     eax, [rax+8]
0x140062d13  mov     esi, r14d
0x140062d16  bt      rax, 16h
0x140062d1b  jb      short loc_140062D1F
0x140062d1d  mov     esi, ebx
0x140062d1f  mov     rax, [rdi+8]
0x140062d23  mov     [rbp+arg_0], bl
0x140062d26  mov     rcx, [rax+2820h]
0x140062d2d  test    cl, 3
0x140062d30  jz      short loc_140062D39
0x140062d32  shr     cl, 1
0x140062d34  and     cl, r14b
0x140062d37  jmp     short loc_140062D7C
0x140062d39  mov     [rsp+68h+var_10], rbx
0x140062d3e  lea     rdx, [rbp+arg_0]
0x140062d42  mov     [rsp+68h+var_18], rbx
0x140062d47  xor     r9d, r9d
0x140062d4a  mov     [rsp+68h+var_20], rbx
0x140062d4f  xor     r8d, r8d
0x140062d52  mov     [rsp+68h+var_28], rbx
0x140062d57  mov     rcx, rax
0x140062d5a  mov     [rsp+68h+var_30], rbx
0x140062d5f  mov     [rsp+68h+var_38], rbx
0x140062d64  mov     [rsp+68h+var_40], rbx
0x140062d69  mov     [rsp+68h+var_48], rbx
0x140062d6e  call    FveFeatWcosCheck
0x140062d73  movzx   ecx, [rbp+arg_0]
0x140062d77  test    eax, eax
0x140062d79  cmovs   ecx, ebx
0x140062d7c  test    cl, cl
0x140062d7e  jz      short loc_140062DA6
0x140062d80  mov     rax, [rdi+400h]
0x140062d87  test    rax, rax
0x140062d8a  jz      short loc_140062DA6
0x140062d8c  cmp     [rax], r14w
0x140062d90  jb      short loc_140062DA6
0x140062d92  cmp     [rax+2], r15w
0x140062d97  jb      short loc_140062DA6
0x140062d99  mov     eax, [rax+8]
0x140062d9c  mov     ecx, r14d
0x140062d9f  bt      rax, 13h
0x140062da4  jb      short loc_140062DA8
0x140062da6  mov     ecx, ebx
0x140062da8  mov     rax, [rdi+78h]
0x140062dac  mov     edx, 25h ; '%'
0x140062db1  mov     dword ptr [rsp+68h+var_38], esi
0x140062db5  mov     r8, r12
0x140062db8  mov     dword ptr [rsp+68h+var_40], ecx
0x140062dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140062dc3  mov     r9d, [rax+30h]
0x140062dc7  mov     eax, r9d
0x140062dca  shr     eax, 16h
0x140062dcd  shr     r9d, 8
0x140062dd1  and     eax, r14d
0x140062dd4  mov     rcx, [rcx+18h]
0x140062dd8  and     r9d, r14d
0x140062ddb  mov     dword ptr [rsp+68h+var_48], eax
0x140062ddf  call    WPP_SF_LLLL
0x140062de4  cmp     [rdi+380h], ebx
0x140062dea  jnz     loc_140062BE3
0x140062df0  mov     rax, [rdi+78h]
0x140062df4  test    dword ptr [rax+30h], 400100h
0x140062dfb  jnz     loc_140062BE3
0x140062e01  mov     edx, 24h ; '$'
0x140062e06  mov     rcx, rdi
  ... truncated ...
```
