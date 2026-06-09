# FvePnpNotification

- ea: `0x14008ae60`
- end: `0x14008b628`
- name: `FvePnpNotification`
- size: `1992`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000ba88`
- `0x14000c60c`
- `0x1400617dc`
- `0x1400635ac`
- `0x140063760`
- `0x140087888`
- `0x14008ae60`
- `0x14008b630`
- `0x14008f08c`
- `0x140097f18`
- `0x140098ec8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14008b050`
- `ntoskrnl!RtlCompareMemory` at `0x14008b050`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14008aec1`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14008b0d6`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14008aec1`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14008b0d6`

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
        v33 = *(_QWORD *)(v32 + 10272);
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
        v39 = *(_QWORD *)(v38 + 10272);
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
    v20 = *(_QWORD *)(v19 + 10272);
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
    v26 = *(_QWORD *)(v25 + 10272);
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
0x14008ae60  push    rbp
0x14008ae62  push    rbx
0x14008ae63  push    rsi
0x14008ae64  push    rdi
0x14008ae65  push    r12
0x14008ae67  push    r13
0x14008ae69  push    r14
0x14008ae6b  push    r15
0x14008ae6d  mov     rbp, rsp
0x14008ae70  sub     rsp, 68h
0x14008ae74  mov     rbx, rdx
0x14008ae77  mov     rdi, rcx
0x14008ae7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ae81  lea     rsi, WPP_GLOBAL_Control
0x14008ae88  lea     r15, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14008ae8f  cmp     rcx, rsi
0x14008ae92  jz      short loc_14008AEBF
0x14008ae94  mov     eax, [rcx+2Ch]
0x14008ae97  test    al, 40h
0x14008ae99  jz      short loc_14008AEBF
0x14008ae9b  cmp     byte ptr [rcx+29h], 5
0x14008ae9f  jb      short loc_14008AEBF
0x14008aea1  mov     eax, [rbx+370h]
0x14008aea7  mov     edx, 0Dh
0x14008aeac  mov     rcx, [rcx+18h]
0x14008aeb0  mov     r9, rbx
0x14008aeb3  mov     r8, r15
0x14008aeb6  mov     dword ptr [rsp+68h+var_48], eax
0x14008aeba  call    WPP_SF_qd
0x14008aebf  xor     ecx, ecx; EnableHardErrors
0x14008aec1  call    cs:__imp_IoSetThreadHardErrorMode
0x14008aec8  nop     dword ptr [rax+rax+00h]
0x14008aecd  mov     rcx, [rdi+4]
0x14008aed1  mov     r12b, al
0x14008aed4  sub     rcx, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data1
0x14008aedb  jnz     short loc_14008AEE8
0x14008aedd  mov     rcx, [rdi+0Ch]
0x14008aee1  sub     rcx, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_COMPLETE.Data4
0x14008aee8  xor     r13d, r13d
0x14008aeeb  test    rcx, rcx
0x14008aeee  jnz     short loc_14008AF33
0x14008aef0  mov     rcx, cs:WPP_GLOBAL_Control
0x14008aef7  cmp     rcx, rsi
0x14008aefa  jz      short loc_14008AF19
0x14008aefc  mov     eax, [rcx+2Ch]
0x14008aeff  test    al, 40h
0x14008af01  jz      short loc_14008AF19
0x14008af03  cmp     byte ptr [rcx+29h], 4
0x14008af07  jb      short loc_14008AF19
0x14008af09  mov     rcx, [rcx+18h]
0x14008af0d  lea     edx, [r13+0Eh]
0x14008af11  mov     r8, r15
0x14008af14  call    WPP_SF_
0x14008af19  cmp     [rbx+370h], r13d
0x14008af20  jnz     loc_14008B0D3
0x14008af26  mov     rcx, rbx
0x14008af29  call    FveUnregisterPnpNotifications
0x14008af2e  jmp     loc_14008B0D3
0x14008af33  mov     rax, [rdi+4]
0x14008af37  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_QUERY_REMOVE.Data1
0x14008af3e  jnz     short loc_14008AF4B
0x14008af40  mov     rax, [rdi+0Ch]
0x14008af44  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_QUERY_REMOVE.Data4
0x14008af4b  test    rax, rax
0x14008af4e  jnz     short loc_14008AFA4
0x14008af50  mov     rcx, cs:WPP_GLOBAL_Control
0x14008af57  cmp     rcx, rsi
0x14008af5a  jz      short loc_14008AF7A
0x14008af5c  mov     eax, [rcx+2Ch]
0x14008af5f  test    al, 40h
0x14008af61  jz      short loc_14008AF7A
0x14008af63  cmp     byte ptr [rcx+29h], 4
0x14008af67  jb      short loc_14008AF7A
0x14008af69  mov     rcx, [rcx+18h]
0x14008af6d  mov     edx, 0Fh
0x14008af72  mov     r8, r15
0x14008af75  call    WPP_SF_
0x14008af7a  cmp     [rbx+370h], r13d
0x14008af81  jnz     loc_14008B0D3
0x14008af87  mov     edi, 21h ; '!'
0x14008af8c  mov     rcx, rbx
0x14008af8f  mov     edx, edi
0x14008af91  call    FveSaveFsMounted
0x14008af96  lea     esi, [rdi-20h]
0x14008af99  mov     r8b, sil
0x14008af9c  mov     dl, sil
0x14008af9f  jmp     loc_14008B51B
0x14008afa4  mov     rax, [rdi+4]
0x14008afa8  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data1
0x14008afaf  jnz     short loc_14008AFBC
0x14008afb1  mov     rax, [rdi+0Ch]
0x14008afb5  sub     rax, qword ptr cs:GUID_TARGET_DEVICE_REMOVE_CANCELLED.Data4
0x14008afbc  test    rax, rax
0x14008afbf  jnz     short loc_14008B002
0x14008afc1  cmp     [rbx+370h], r13d
0x14008afc8  jnz     loc_14008B0D3
0x14008afce  mov     rcx, cs:WPP_GLOBAL_Control
0x14008afd5  cmp     rcx, rsi
0x14008afd8  jz      short loc_14008AFF8
0x14008afda  mov     eax, [rcx+2Ch]
0x14008afdd  test    al, 40h
0x14008afdf  jz      short loc_14008AFF8
0x14008afe1  cmp     byte ptr [rcx+29h], 4
0x14008afe5  jb      short loc_14008AFF8
0x14008afe7  mov     rcx, [rcx+18h]
0x14008afeb  mov     edx, 10h
0x14008aff0  mov     r8, r15
0x14008aff3  call    WPP_SF_
0x14008aff8  mov     edx, 22h ; '"'
0x14008affd  jmp     loc_14008B58F
0x14008b002  mov     rax, [rdi+4]
0x14008b006  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x14008b00d  jnz     short loc_14008B01A
0x14008b00f  mov     rax, [rdi+0Ch]
0x14008b013  sub     rax, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x14008b01a  test    rax, rax
0x14008b01d  jnz     loc_14008B131
0x14008b023  cmp     word ptr [rdi+2], 3Eh ; '>'
0x14008b028  lea     esi, [rax+1]
0x14008b02b  movzx   r15d, r13b
0x14008b02f  jnz     short loc_14008B064
0x14008b031  lea     r14d, [rax+10h]
0x14008b035  cmp     [rdi+30h], r14d
0x14008b039  jnz     short loc_14008B064
0x14008b03b  cmp     dword ptr [rdi+2Ch], 6
0x14008b03f  jnz     short loc_14008B064
0x14008b041  lea     rcx, [rdi+34h]; Source1
0x14008b045  lea     r8d, [rax+6]; Length
0x14008b049  lea     rdx, aRaw; "RAW"
0x14008b050  call    cs:__imp_RtlCompareMemory
0x14008b057  nop     dword ptr [rax+rax+00h]
0x14008b05c  cmp     rax, 6
0x14008b060  cmovz   r15d, esi
0x14008b064  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b06b  lea     rax, WPP_GLOBAL_Control
0x14008b072  cmp     rcx, rax
0x14008b075  jz      short loc_14008B09D
0x14008b077  mov     eax, [rcx+2Ch]
0x14008b07a  test    al, 40h
0x14008b07c  jz      short loc_14008B09D
0x14008b07e  cmp     byte ptr [rcx+29h], 4
0x14008b082  jb      short loc_14008B09D
0x14008b084  mov     rcx, [rcx+18h]
0x14008b088  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14008b08f  movzx   r9d, r15b
0x14008b093  mov     edx, 11h
0x14008b098  call    WPP_SF_d
0x14008b09d  cmp     [rbx+370h], r13d
0x14008b0a4  jnz     short loc_14008B0CC
0x14008b0a6  xor     r9d, r9d
0x14008b0a9  mov     dword ptr [rsp+68h+var_48], 23h ; '#'
0x14008b0b1  mov     dl, sil
0x14008b0b4  mov     rcx, rbx
0x14008b0b7  test    r15b, r15b
0x14008b0ba  jnz     short loc_14008B127
0x14008b0bc  mov     r8b, sil
0x14008b0bf  call    FveSetFsMounted
0x14008b0c4  mov     rcx, rbx
0x14008b0c7  call    FveFsOnline
0x14008b0cc  lea     r15, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14008b0d3  mov     cl, r12b; EnableHardErrors
0x14008b0d6  call    cs:__imp_IoSetThreadHardErrorMode
0x14008b0dd  nop     dword ptr [rax+rax+00h]
0x14008b0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b0e9  lea     rax, WPP_GLOBAL_Control
0x14008b0f0  cmp     rcx, rax
0x14008b0f3  jz      short loc_14008B113
0x14008b0f5  mov     eax, [rcx+2Ch]
0x14008b0f8  test    al, 40h
0x14008b0fa  jz      short loc_14008B113
0x14008b0fc  cmp     byte ptr [rcx+29h], 5
0x14008b100  jb      short loc_14008B113
0x14008b102  mov     rcx, [rcx+18h]
0x14008b106  mov     edx, 17h
0x14008b10b  mov     r8, r15
0x14008b10e  call    WPP_SF_
0x14008b113  xor     eax, eax
0x14008b115  add     rsp, 68h
0x14008b119  pop     r15
0x14008b11b  pop     r14
0x14008b11d  pop     r13
0x14008b11f  pop     r12
0x14008b121  pop     rdi
0x14008b122  pop     rsi
0x14008b123  pop     rbx
0x14008b124  pop     rbp
0x14008b125  retn
0x14008b127  xor     r8d, r8d
0x14008b12a  call    FveSetFsMounted
0x14008b12f  jmp     short loc_14008B0CC
0x14008b131  mov     rax, [rdi+4]
0x14008b135  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data1
0x14008b13c  jnz     short loc_14008B149
0x14008b13e  mov     rax, [rdi+0Ch]
0x14008b142  sub     rax, qword ptr cs:GUID_IO_VOLUME_DISMOUNT.Data4
0x14008b149  test    rax, rax
0x14008b14c  jnz     loc_14008B302
0x14008b152  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b159  lea     esi, [rax+1]
0x14008b15c  lea     rax, WPP_GLOBAL_Control
0x14008b163  cmp     rcx, rax
0x14008b166  jz      loc_14008B2D0
0x14008b16c  mov     eax, [rcx+2Ch]
0x14008b16f  test    al, 40h
0x14008b171  jz      loc_14008B2D0
0x14008b177  cmp     byte ptr [rcx+29h], 4
0x14008b17b  jb      loc_14008B2D0
0x14008b181  mov     rcx, [rbx+8]
0x14008b185  mov     [rbp+arg_0], r13b
0x14008b189  mov     rdx, [rcx+2820h]
0x14008b190  test    dl, 3
0x14008b193  jz      short loc_14008B19C
0x14008b195  shr     dl, 1
0x14008b197  and     dl, sil
0x14008b19a  jmp     short loc_14008B1DD
0x14008b19c  mov     [rsp+68h+var_10], r13
0x14008b1a1  lea     rdx, [rbp+arg_0]
0x14008b1a5  mov     [rsp+68h+var_18], r13
0x14008b1aa  xor     r9d, r9d
0x14008b1ad  mov     [rsp+68h+var_20], r13
0x14008b1b2  xor     r8d, r8d
0x14008b1b5  mov     [rsp+68h+var_28], r13
0x14008b1ba  mov     [rsp+68h+var_30], r13
0x14008b1bf  mov     [rsp+68h+var_38], r13
0x14008b1c4  mov     [rsp+68h+var_40], r13
0x14008b1c9  mov     [rsp+68h+var_48], r13
0x14008b1ce  call    FveFeatWcosCheck
0x14008b1d3  movzx   edx, [rbp+arg_0]
0x14008b1d7  test    eax, eax
0x14008b1d9  cmovs   edx, r13d
0x14008b1dd  mov     r14d, 10h
0x14008b1e3  test    dl, dl
0x14008b1e5  jz      short loc_14008B20B
0x14008b1e7  mov     rax, [rbx+400h]
0x14008b1ee  test    rax, rax
0x14008b1f1  jz      short loc_14008B20B
0x14008b1f3  cmp     [rax], si
0x14008b1f6  jb      short loc_14008B20B
0x14008b1f8  cmp     [rax+2], r14w
0x14008b1fd  jb      short loc_14008B20B
0x14008b1ff  mov     eax, [rax+8]
0x14008b202  mov     edi, esi
0x14008b204  bt      rax, 16h
0x14008b209  jb      short loc_14008B20E
0x14008b20b  mov     edi, r13d
0x14008b20e  mov     rcx, [rbx+8]
0x14008b212  mov     [rbp+arg_0], r13b
0x14008b216  mov     rdx, [rcx+2820h]
0x14008b21d  test    dl, 3
0x14008b220  jz      short loc_14008B229
0x14008b222  shr     dl, 1
0x14008b224  and     dl, sil
0x14008b227  jmp     short loc_14008B26A
0x14008b229  mov     [rsp+68h+var_10], r13
0x14008b22e  lea     rdx, [rbp+arg_0]
0x14008b232  mov     [rsp+68h+var_18], r13
0x14008b237  xor     r9d, r9d
0x14008b23a  mov     [rsp+68h+var_20], r13
0x14008b23f  xor     r8d, r8d
0x14008b242  mov     [rsp+68h+var_28], r13
0x14008b247  mov     [rsp+68h+var_30], r13
0x14008b24c  mov     [rsp+68h+var_38], r13
0x14008b251  mov     [rsp+68h+var_40], r13
0x14008b256  mov     [rsp+68h+var_48], r13
0x14008b25b  call    FveFeatWcosCheck
0x14008b260  movzx   edx, [rbp+arg_0]
0x14008b264  test    eax, eax
0x14008b266  cmovs   edx, r13d
0x14008b26a  test    dl, dl
0x14008b26c  jz      short loc_14008B292
0x14008b26e  mov     rax, [rbx+400h]
0x14008b275  test    rax, rax
0x14008b278  jz      short loc_14008B292
0x14008b27a  cmp     [rax], si
0x14008b27d  jb      short loc_14008B292
0x14008b27f  cmp     [rax+2], r14w
0x14008b284  jb      short loc_14008B292
0x14008b286  mov     eax, [rax+8]
0x14008b289  mov     ecx, esi
0x14008b28b  bt      rax, 13h
0x14008b290  jb      short loc_14008B295
0x14008b292  mov     ecx, r13d
0x14008b295  mov     rax, [rbx+78h]
0x14008b299  mov     edx, 12h
0x14008b29e  mov     dword ptr [rsp+68h+var_38], edi
0x14008b2a2  mov     r8, r15
0x14008b2a5  mov     dword ptr [rsp+68h+var_40], ecx
0x14008b2a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b2b0  mov     r9d, [rax+30h]
0x14008b2b4  mov     eax, r9d
0x14008b2b7  shr     eax, 16h
0x14008b2ba  shr     r9d, 8
0x14008b2be  and     eax, esi
0x14008b2c0  mov     rcx, [rcx+18h]
0x14008b2c4  and     r9d, esi
0x14008b2c7  mov     dword ptr [rsp+68h+var_48], eax
0x14008b2cb  call    WPP_SF_LLLL
0x14008b2d0  cmp     [rbx+370h], r13d
0x14008b2d7  jnz     loc_14008B0D3
0x14008b2dd  mov     rax, [rbx+78h]
  ... truncated ...
```
