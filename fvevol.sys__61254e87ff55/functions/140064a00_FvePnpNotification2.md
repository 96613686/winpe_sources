# FvePnpNotification2

- ea: `0x140064a00`
- end: `0x1400651b9`
- name: `FvePnpNotification2`
- size: `1977`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000bc14`
- `0x14000c79c`
- `0x1400638f8`
- `0x140064a00`
- `0x14006570c`
- `0x140065854`
- `0x1400658c8`
- `0x140065d20`
- `0x14008d6d0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140064be9`
- `ntoskrnl!RtlCompareMemory` at `0x140064be9`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140064a61`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140064c66`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140064a61`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x140064c66`

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
        v26 = *(_QWORD *)(v25 + 10520);
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
        v32 = *(_QWORD *)(v31 + 10520);
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
    v14 = *(_QWORD *)(v13 + 10520);
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
    v20 = *(_QWORD *)(v19 + 10520);
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
0x140064a00  push    rbp
0x140064a02  push    rbx
0x140064a03  push    rsi
0x140064a04  push    rdi
0x140064a05  push    r12
0x140064a07  push    r13
0x140064a09  push    r14
0x140064a0b  push    r15
0x140064a0d  mov     rbp, rsp
0x140064a10  sub     rsp, 68h
0x140064a14  mov     rdi, rdx
0x140064a17  mov     rsi, rcx
0x140064a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140064a21  lea     r14, WPP_GLOBAL_Control
0x140064a28  lea     r12, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140064a2f  cmp     rcx, r14
0x140064a32  jz      short loc_140064A5F
0x140064a34  mov     eax, [rcx+2Ch]
0x140064a37  test    al, 40h
0x140064a39  jz      short loc_140064A5F
0x140064a3b  cmp     byte ptr [rcx+29h], 5
0x140064a3f  jb      short loc_140064A5F
0x140064a41  mov     eax, [rdi+380h]
0x140064a47  mov     edx, 20h ; ' '
0x140064a4c  mov     rcx, [rcx+18h]
0x140064a50  mov     r9, rdi
0x140064a53  mov     r8, r12
0x140064a56  mov     dword ptr [rsp+68h+var_48], eax
0x140064a5a  call    WPP_SF_qd
0x140064a5f  xor     ecx, ecx; EnableHardErrors
0x140064a61  call    cs:__imp_IoSetThreadHardErrorMode
0x140064a68  nop     dword ptr [rax+rax+00h]
0x140064a6d  mov     rcx, [rsi+4]
0x140064a71  mov     r13b, al
0x140064a74  cmp     rcx, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data1
0x140064a7b  jnz     short loc_140064ACF
0x140064a7d  mov     rcx, [rsi+0Ch]
0x140064a81  cmp     rcx, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data4
0x140064a88  jnz     short loc_140064ACF
0x140064a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140064a91  cmp     rcx, r14
0x140064a94  jz      short loc_140064AB4
0x140064a96  mov     eax, [rcx+2Ch]
0x140064a99  test    al, 40h
0x140064a9b  jz      short loc_140064AB4
0x140064a9d  cmp     byte ptr [rcx+29h], 4
0x140064aa1  jb      short loc_140064AB4
0x140064aa3  mov     rcx, [rcx+18h]
0x140064aa7  mov     edx, 21h ; '!'
0x140064aac  mov     r8, r12
0x140064aaf  call    WPP_SF_
0x140064ab4  xor     ebx, ebx
0x140064ab6  cmp     [rdi+380h], ebx
0x140064abc  jnz     loc_140064C63
0x140064ac2  mov     rcx, rdi
0x140064ac5  call    FveUnregisterPnpNotifications2
0x140064aca  jmp     loc_140064C63
0x140064acf  mov     rax, [rsi+4]
0x140064ad3  cmp     rax, qword ptr cs:GUID_TARGET_DEVICE_QUERY_REMOVE.Data1
0x140064ada  jnz     short loc_140064B3D
0x140064adc  mov     rax, [rsi+0Ch]
0x140064ae0  cmp     rax, qword ptr cs:GUID_TARGET_DEVICE_QUERY_REMOVE.Data4
0x140064ae7  jnz     short loc_140064B3D
0x140064ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x140064af0  cmp     rcx, r14
0x140064af3  jz      short loc_140064B13
0x140064af5  mov     eax, [rcx+2Ch]
0x140064af8  test    al, 40h
0x140064afa  jz      short loc_140064B13
0x140064afc  cmp     byte ptr [rcx+29h], 4
0x140064b00  jb      short loc_140064B13
0x140064b02  mov     rcx, [rcx+18h]
0x140064b06  mov     edx, 22h ; '"'
0x140064b0b  mov     r8, r12
0x140064b0e  call    WPP_SF_
0x140064b13  xor     ebx, ebx
0x140064b15  cmp     [rdi+380h], ebx
0x140064b1b  jnz     loc_140064C63
0x140064b21  lea     edx, [rbx+21h]
0x140064b24  mov     rcx, rdi
0x140064b27  call    FveSaveFsMounted2
0x140064b2c  mov     dword ptr [rsp+68h+var_48], 21h ; '!'
0x140064b34  lea     r14d, [rbx+1]
0x140064b38  jmp     loc_140064E96
0x140064b3d  mov     rax, [rsi+4]
0x140064b41  cmp     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data1
0x140064b48  jnz     short loc_140064B97
0x140064b4a  mov     rax, [rsi+0Ch]
0x140064b4e  cmp     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data4
0x140064b55  jnz     short loc_140064B97
0x140064b57  xor     ebx, ebx
0x140064b59  cmp     [rdi+380h], ebx
0x140064b5f  jnz     loc_140064C63
0x140064b65  mov     rcx, cs:WPP_GLOBAL_Control
0x140064b6c  cmp     rcx, r14
0x140064b6f  jz      short loc_140064B8D
0x140064b71  mov     eax, [rcx+2Ch]
0x140064b74  test    al, 40h
0x140064b76  jz      short loc_140064B8D
0x140064b78  cmp     byte ptr [rcx+29h], 4
0x140064b7c  jb      short loc_140064B8D
0x140064b7e  mov     rcx, [rcx+18h]
0x140064b82  lea     edx, [rbx+23h]
0x140064b85  mov     r8, r12
0x140064b88  call    WPP_SF_
0x140064b8d  mov     edx, 22h ; '"'
0x140064b92  jmp     loc_140065125
0x140064b97  mov     rax, [rsi+4]
0x140064b9b  cmp     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x140064ba2  jnz     loc_140064CBC
0x140064ba8  mov     rax, [rsi+0Ch]
0x140064bac  cmp     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x140064bb3  jnz     loc_140064CBC
0x140064bb9  xor     ebx, ebx
0x140064bbb  cmp     word ptr [rsi+2], 3Eh ; '>'
0x140064bc0  movzx   r12d, bl
0x140064bc4  lea     r14d, [rbx+1]
0x140064bc8  jnz     short loc_140064BFD
0x140064bca  lea     r15d, [rbx+10h]
0x140064bce  cmp     [rsi+30h], r15d
0x140064bd2  jnz     short loc_140064BFD
0x140064bd4  cmp     dword ptr [rsi+2Ch], 6
0x140064bd8  jnz     short loc_140064BFD
0x140064bda  lea     rcx, [rsi+34h]; Source1
0x140064bde  lea     r8d, [rbx+6]; Length
0x140064be2  lea     rdx, aRaw; "RAW"
0x140064be9  call    cs:__imp_RtlCompareMemory
0x140064bf0  nop     dword ptr [rax+rax+00h]
0x140064bf5  cmp     rax, 6
0x140064bf9  cmovz   r12d, r14d
0x140064bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140064c04  lea     rax, WPP_GLOBAL_Control
0x140064c0b  cmp     rcx, rax
0x140064c0e  jz      short loc_140064C36
0x140064c10  mov     eax, [rcx+2Ch]
0x140064c13  test    al, 40h
0x140064c15  jz      short loc_140064C36
0x140064c17  cmp     byte ptr [rcx+29h], 4
0x140064c1b  jb      short loc_140064C36
0x140064c1d  mov     rcx, [rcx+18h]
0x140064c21  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140064c28  movzx   r9d, r12b
0x140064c2c  mov     edx, 24h ; '$'
0x140064c31  call    WPP_SF_d
0x140064c36  cmp     [rdi+380h], ebx
0x140064c3c  jnz     short loc_140064C5C
0x140064c3e  xor     r9d, r9d
0x140064c41  mov     dword ptr [rsp+68h+var_48], 23h ; '#'
0x140064c49  mov     dl, r14b
0x140064c4c  mov     rcx, rdi
0x140064c4f  test    r12b, r12b
0x140064c52  jnz     short loc_140064CB7
0x140064c54  mov     r8b, r14b
0x140064c57  call    FveSetFsMounted2
0x140064c5c  lea     r12, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140064c63  mov     cl, r13b; EnableHardErrors
0x140064c66  call    cs:__imp_IoSetThreadHardErrorMode
0x140064c6d  nop     dword ptr [rax+rax+00h]
0x140064c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140064c79  lea     rax, WPP_GLOBAL_Control
0x140064c80  cmp     rcx, rax
0x140064c83  jz      short loc_140064CA3
0x140064c85  mov     eax, [rcx+2Ch]
0x140064c88  test    al, 40h
0x140064c8a  jz      short loc_140064CA3
0x140064c8c  cmp     byte ptr [rcx+29h], 5
0x140064c90  jb      short loc_140064CA3
0x140064c92  mov     rcx, [rcx+18h]
0x140064c96  mov     edx, 2Ah ; '*'
0x140064c9b  mov     r8, r12
0x140064c9e  call    WPP_SF_
0x140064ca3  xor     eax, eax
0x140064ca5  add     rsp, 68h
0x140064ca9  pop     r15
0x140064cab  pop     r14
0x140064cad  pop     r13
0x140064caf  pop     r12
0x140064cb1  pop     rdi
0x140064cb2  pop     rsi
0x140064cb3  pop     rbx
0x140064cb4  pop     rbp
0x140064cb5  retn
0x140064cb7  xor     r8d, r8d
0x140064cba  jmp     short loc_140064C57
0x140064cbc  mov     rax, [rsi+4]
0x140064cc0  cmp     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x140064cc7  jnz     loc_140064EA1
0x140064ccd  mov     rax, [rsi+0Ch]
0x140064cd1  cmp     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x140064cd8  jnz     loc_140064EA1
0x140064cde  mov     rcx, cs:WPP_GLOBAL_Control
0x140064ce5  lea     rax, WPP_GLOBAL_Control
0x140064cec  xor     ebx, ebx
0x140064cee  lea     r14d, [rbx+1]
0x140064cf2  cmp     rcx, rax
0x140064cf5  jz      loc_140064E64
0x140064cfb  mov     eax, [rcx+2Ch]
0x140064cfe  test    al, 40h
0x140064d00  jz      loc_140064E64
0x140064d06  cmp     byte ptr [rcx+29h], 4
0x140064d0a  jb      loc_140064E64
0x140064d10  mov     rax, [rdi+8]
0x140064d14  mov     [rbp+arg_0], bl
0x140064d17  mov     rcx, [rax+2918h]
0x140064d1e  test    cl, 3
0x140064d21  jz      short loc_140064D2A
0x140064d23  shr     cl, 1
0x140064d25  and     cl, r14b
0x140064d28  jmp     short loc_140064D6D
0x140064d2a  mov     [rsp+68h+var_10], rbx
0x140064d2f  lea     rdx, [rbp+arg_0]
0x140064d33  mov     [rsp+68h+var_18], rbx
0x140064d38  xor     r9d, r9d
0x140064d3b  mov     [rsp+68h+var_20], rbx
0x140064d40  xor     r8d, r8d
0x140064d43  mov     [rsp+68h+var_28], rbx
0x140064d48  mov     rcx, rax
0x140064d4b  mov     [rsp+68h+var_30], rbx
0x140064d50  mov     [rsp+68h+var_38], rbx
0x140064d55  mov     [rsp+68h+var_40], rbx
0x140064d5a  mov     [rsp+68h+var_48], rbx
0x140064d5f  call    FveFeatWcosCheck
0x140064d64  movzx   ecx, [rbp+arg_0]
0x140064d68  test    eax, eax
0x140064d6a  cmovs   ecx, ebx
0x140064d6d  mov     r15d, 10h
0x140064d73  test    cl, cl
0x140064d75  jz      short loc_140064D9D
0x140064d77  mov     rax, [rdi+400h]
0x140064d7e  test    rax, rax
0x140064d81  jz      short loc_140064D9D
0x140064d83  cmp     [rax], r14w
0x140064d87  jb      short loc_140064D9D
0x140064d89  cmp     [rax+2], r15w
0x140064d8e  jb      short loc_140064D9D
0x140064d90  mov     eax, [rax+8]
0x140064d93  mov     esi, r14d
0x140064d96  bt      rax, 16h
0x140064d9b  jb      short loc_140064D9F
0x140064d9d  mov     esi, ebx
0x140064d9f  mov     rax, [rdi+8]
0x140064da3  mov     [rbp+arg_0], bl
0x140064da6  mov     rcx, [rax+2918h]
0x140064dad  test    cl, 3
0x140064db0  jz      short loc_140064DB9
0x140064db2  shr     cl, 1
0x140064db4  and     cl, r14b
0x140064db7  jmp     short loc_140064DFC
0x140064db9  mov     [rsp+68h+var_10], rbx
0x140064dbe  lea     rdx, [rbp+arg_0]
0x140064dc2  mov     [rsp+68h+var_18], rbx
0x140064dc7  xor     r9d, r9d
0x140064dca  mov     [rsp+68h+var_20], rbx
0x140064dcf  xor     r8d, r8d
0x140064dd2  mov     [rsp+68h+var_28], rbx
0x140064dd7  mov     rcx, rax
0x140064dda  mov     [rsp+68h+var_30], rbx
0x140064ddf  mov     [rsp+68h+var_38], rbx
0x140064de4  mov     [rsp+68h+var_40], rbx
0x140064de9  mov     [rsp+68h+var_48], rbx
0x140064dee  call    FveFeatWcosCheck
0x140064df3  movzx   ecx, [rbp+arg_0]
0x140064df7  test    eax, eax
0x140064df9  cmovs   ecx, ebx
0x140064dfc  test    cl, cl
0x140064dfe  jz      short loc_140064E26
0x140064e00  mov     rax, [rdi+400h]
0x140064e07  test    rax, rax
0x140064e0a  jz      short loc_140064E26
0x140064e0c  cmp     [rax], r14w
0x140064e10  jb      short loc_140064E26
0x140064e12  cmp     [rax+2], r15w
0x140064e17  jb      short loc_140064E26
0x140064e19  mov     eax, [rax+8]
0x140064e1c  mov     ecx, r14d
0x140064e1f  bt      rax, 13h
0x140064e24  jb      short loc_140064E28
0x140064e26  mov     ecx, ebx
0x140064e28  mov     rax, [rdi+78h]
0x140064e2c  mov     edx, 25h ; '%'
0x140064e31  mov     dword ptr [rsp+68h+var_38], esi
0x140064e35  mov     r8, r12
0x140064e38  mov     dword ptr [rsp+68h+var_40], ecx
0x140064e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140064e43  mov     r9d, [rax+30h]
0x140064e47  mov     eax, r9d
0x140064e4a  shr     eax, 16h
0x140064e4d  shr     r9d, 8
0x140064e51  and     eax, r14d
0x140064e54  mov     rcx, [rcx+18h]
0x140064e58  and     r9d, r14d
0x140064e5b  mov     dword ptr [rsp+68h+var_48], eax
0x140064e5f  call    WPP_SF_LLLL
0x140064e64  cmp     [rdi+380h], ebx
0x140064e6a  jnz     loc_140064C63
0x140064e70  mov     rax, [rdi+78h]
0x140064e74  test    dword ptr [rax+30h], 400100h
0x140064e7b  jnz     loc_140064C63
0x140064e81  mov     edx, 24h ; '$'
0x140064e86  mov     rcx, rdi
  ... truncated ...
```
