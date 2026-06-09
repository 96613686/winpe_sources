# ClasspInterpretGesnData

- ea: `0x140021c78`
- end: `0x140022496`
- name: `ClasspInterpretGesnData`
- size: `2078`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, unsigned __int8 *, char *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140014aa0`
- `0x14005479c`

## callees

- `0x14000f3e0`
- `0x140016d50`
- `0x140019020`
- `0x14001fc38`
- `0x14001feac`
- `0x14001fedc`
- `0x140021ba4`
- `0x140021c78`
- `0x1400225b4`
- `0x140022614`
- `0x14003e430`
- `0x14003e470`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x1400220b7`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400220b7`

## pseudocode

```c
__int64 __fastcall ClasspInterpretGesnData(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, unsigned __int8 *a2, char *a3)
{
  _MEDIA_CHANGE_DETECTION_INFO *MediaChangeDetectionInfo; // rdi
  char v5; // al
  char v8; // bl
  int EventMask; // r8d
  unsigned __int8 v10; // dl
  __int64 v11; // r9
  unsigned __int8 v13; // al
  unsigned __int8 v14; // dl
  unsigned int v15; // r12d
  int v16; // eax
  unsigned int v17; // r8d
  unsigned int v18; // ebx
  char v19; // cl
  _DEVICE_OBJECT *v20; // rcx
  _VPB *v21; // rax
  unsigned __int8 v22; // dl
  __int16 v23; // cx
  __int16 v24; // ax
  __int64 v25; // rbx
  unsigned __int8 v26; // cl
  bool v27; // zf
  int v28; // edx
  _DEVICE_OBJECT *DeviceObject; // rcx
  _VPB *Vpb; // rax
  _CLASS_DRIVER_EXTENSION *DriverExtension; // rax
  char v32; // r10
  unsigned int i; // r9d
  __int64 v34; // rcx
  __int64 v35; // rdx
  int v36; // ecx
  int v37; // ecx
  char v38; // r10
  unsigned int v39; // r8d
  __int64 v40; // rcx
  __int64 v41; // rdx
  int v42; // ecx
  int v43; // ecx
  char v44; // r10
  unsigned int v45; // r8d
  __int64 v46; // rcx
  __int64 v47; // rdx
  int v48; // ecx
  int v49; // ecx
  _QWORD *v50; // rdx
  int v51; // [rsp+20h] [rbp-E0h]
  _BYTE v52[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v53[3]; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v54[12]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 ExtraData; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-50h]
  _QWORD v57[24]; // [rsp+C0h] [rbp-40h] BYREF

  MediaChangeDetectionInfo = FdoExtension->MediaChangeDetectionInfo;
  *a3 = 0;
  v5 = a2[2];
  if ( v5 < 0 || (v5 & 7) == 0 )
    return 0;
  v8 = 1;
  if ( MediaChangeDetectionInfo->Gesn.HackEventMask )
  {
    EventMask = MediaChangeDetectionInfo->Gesn.EventMask;
    v10 = 1 << (v5 & 7);
    if ( ((unsigned __int8)EventMask & v10) == 0 )
      return 3221225862LL;
    if ( v10 == ((unsigned __int8)EventMask & (unsigned __int8)-(char)EventMask) )
    {
      if ( (a2[4] & 0xF) == 0 )
      {
        v13 = MediaChangeDetectionInfo->Gesn.NoChangeEventMask | v10;
        v14 = EventMask & ~v10;
        MediaChangeDetectionInfo->Gesn.NoChangeEventMask = v13;
        MediaChangeDetectionInfo->Gesn.EventMask = v14;
        if ( v14 )
        {
          *a3 = 1;
        }
        else
        {
          MediaChangeDetectionInfo->Gesn.EventMask = v13;
          MediaChangeDetectionInfo->Gesn.NoChangeEventMask = 0;
        }
        return 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
          v10,
          EventMask);
      }
      MediaChangeDetectionInfo->Gesn.HackEventMask = 0;
    }
  }
  v11 = (a2[1] | (*a2 << 8)) - 2;
  if ( (int)v11 < 4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
        v11,
        FdoExtension->DeviceObject);
    }
    return 3221225862LL;
  }
  if ( (a2[1] | (*a2 << 8)) != 6
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_Dq(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
      v11,
      FdoExtension->DeviceObject);
  }
  if ( (a2[4] & 0xF) == 0 )
    return 0;
  *a3 = 1;
  v15 = 0;
  switch ( a2[2] & 7 )
  {
    case 1:
      if ( (a2[4] & 0xF) == 1 )
        return v15;
      if ( MediaChangeDetectionInfo->MediaChangeRetryCount >= 4 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
            FdoExtension->DeviceObject);
        }
        v26 = MediaChangeDetectionInfo->Gesn.NoChangeEventMask | 2;
        MediaChangeDetectionInfo->Gesn.HackEventMask = 1;
        v27 = (MediaChangeDetectionInfo->Gesn.EventMask & 0xFD) == 0;
        MediaChangeDetectionInfo->Gesn.EventMask &= ~2u;
        MediaChangeDetectionInfo->Gesn.NoChangeEventMask = v26;
        if ( v27 )
        {
          MediaChangeDetectionInfo->Gesn.EventMask = v26;
          v8 = 0;
          MediaChangeDetectionInfo->Gesn.NoChangeEventMask = 0;
        }
        *a3 = v8;
        return v15;
      }
      v28 = a2[7] | (a2[6] << 8);
      if ( v28 != 1 && v28 != 2 )
        return v15;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
          FdoExtension->DeviceObject);
      }
      DeviceObject = FdoExtension->DeviceObject;
      if ( (DeviceObject->Characteristics & 1) != 0 )
      {
        Vpb = DeviceObject->Vpb;
        if ( Vpb )
        {
          if ( (Vpb->Flags & 1) != 0 )
            DeviceObject->Flags |= 2u;
        }
      }
      if ( !FdoExtension->CommonExtension.DevInfo->ClassError )
        return v15;
      memset(v54, 0, 0x58u);
      memset(v57, 0, 0xB8u);
      v53[0] = -2147483620;
      LOWORD(v56) = 0;
      DriverExtension = FdoExtension->CommonExtension.DriverExtension;
      ExtraData = 0;
      v52[0] = 0;
      LOBYTE(ExtraData) = 112;
      BYTE7(ExtraData) = 10;
      BYTE2(ExtraData) = 6;
      BYTE12(ExtraData) = 40;
      if ( (DriverExtension->SrbSupport & 2) == 0
        || (v51 = 64, v15 = InitializeStorageRequestBlock((__int64)v57), (v15 & 0x80000000) != 0) )
      {
        BYTE3(v54[0]) = -124;
        v54[4] = &ExtraData;
        v50 = v54;
        LOWORD(v54[0]) = 88;
        WORD1(v54[1]) = 4614;
        goto LABEL_145;
      }
      if ( BYTE2(v57[0]) == 40 )
      {
        if ( !HIDWORD(v57[2]) )
        {
          v32 = 0;
          for ( i = 0; i < LODWORD(v57[7]); ++i )
          {
            v34 = *((unsigned int *)&v57[15] + i);
            if ( (unsigned int)v34 >= 0x80 && (unsigned int)v34 < LODWORD(v57[2]) )
            {
              v35 = (unsigned int)v34;
              v36 = *(_DWORD *)((char *)v57 + v34) - 64;
              if ( v36 )
              {
                v37 = v36 - 1;
                if ( v37 )
                {
                  if ( v37 == 1 && v35 + 40 <= (unsigned __int64)LODWORD(v57[2]) )
                    break;
                }
                else if ( v35 + 56 <= (unsigned __int64)LODWORD(v57[2]) )
                {
                  v32 = 1;
                  *((_BYTE *)&v57[1] + v35 + 2) = 6;
                }
              }
              else if ( v35 + 40 <= (unsigned __int64)LODWORD(v57[2]) )
              {
                *((_BYTE *)&v57[1] + v35 + 2) = 6;
                break;
              }
              if ( v32 )
                break;
            }
          }
        }
      }
      else
      {
        BYTE2(v57[1]) = 6;
      }
      BYTE3(v57[0]) = -124;
      if ( BYTE2(v57[0]) == 40 )
      {
        if ( HIDWORD(v57[2]) )
          goto LABEL_143;
        v38 = 0;
        v39 = 0;
        if ( LODWORD(v57[7]) )
        {
          while ( 1 )
          {
            v40 = *((unsigned int *)&v57[15] + v39);
            if ( (unsigned int)v40 >= 0x80 && (unsigned int)v40 < LODWORD(v57[2]) )
            {
              v41 = (unsigned int)v40;
              v42 = *(_DWORD *)((char *)v57 + v40) - 64;
              if ( v42 )
              {
                v43 = v42 - 1;
                if ( v43 )
                {
                  if ( v43 == 1 && v41 + 40 <= (unsigned __int64)LODWORD(v57[2]) )
                  {
                    *(_QWORD *)((char *)&v57[3] + v41) = &ExtraData;
                    goto LABEL_127;
                  }
                }
                else if ( v41 + 56 <= (unsigned __int64)LODWORD(v57[2]) )
                {
                  v38 = 1;
                  *(_QWORD *)((char *)&v57[2] + v41) = &ExtraData;
                }
              }
              else if ( v41 + 40 <= (unsigned __int64)LODWORD(v57[2]) )
              {
                *(_QWORD *)((char *)&v57[2] + v41) = &ExtraData;
                goto LABEL_127;
              }
              if ( v38 )
                goto LABEL_127;
            }
            if ( ++v39 >= LODWORD(v57[7]) )
              goto LABEL_127;
          }
        }
      }
      else
      {
        v57[4] = &ExtraData;
LABEL_127:
        if ( BYTE2(v57[0]) != 40 )
        {
          BYTE3(v57[1]) = 18;
LABEL_143:
          v50 = v57;
LABEL_145:
          ((void (__fastcall *)(_DEVICE_OBJECT *, _QWORD *, int *, _BYTE *, int))FdoExtension->CommonExtension.DevInfo->ClassError)(
            FdoExtension->DeviceObject,
            v50,
            v53,
            v52,
            v51);
          return v15;
        }
      }
      if ( !HIDWORD(v57[2]) )
      {
        v44 = 0;
        v45 = 0;
        if ( LODWORD(v57[7]) )
        {
          while ( 1 )
          {
            v46 = *((unsigned int *)&v57[15] + v45);
            if ( (unsigned int)v46 >= 0x80 && (unsigned int)v46 < LODWORD(v57[2]) )
              break;
LABEL_137:
            if ( ++v45 >= LODWORD(v57[7]) )
              goto LABEL_143;
          }
          v47 = (unsigned int)v46;
          v48 = *(_DWORD *)((char *)v57 + v46) - 64;
          if ( !v48 )
            goto LABEL_135;
          v49 = v48 - 1;
          if ( v49 )
          {
            if ( v49 == 1 )
            {
LABEL_135:
              if ( v47 + 40 <= (unsigned __int64)LODWORD(v57[2]) )
              {
                *((_BYTE *)&v57[1] + v47 + 1) = 18;
                goto LABEL_143;
              }
            }
          }
          else if ( v47 + 56 <= (unsigned __int64)LODWORD(v57[2]) )
          {
            v44 = 1;
            *((_BYTE *)&v57[1] + v47 + 1) = 18;
          }
          if ( v44 )
            goto LABEL_143;
          goto LABEL_137;
        }
      }
      goto LABEL_143;
    case 3:
      v22 = a2[4];
      HIDWORD(ExtraData) = 0;
      if ( (v22 & 0xF) != 1 )
        return v15;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DDD(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
          v22 & 0xF,
          a2[5] & 0xF,
          a2[7] | (a2[6] << 8));
      }
      v23 = a2[6];
      v24 = a2[4] & 0xF;
      *(_QWORD *)&ExtraData = 1;
      WORD4(ExtraData) = v24;
      v25 = MEMORY[0xFFFFF78000000014];
      WORD5(ExtraData) = a2[7] | (unsigned __int16)(v23 << 8);
      v56 = v25 * KeQueryTimeIncrement();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
      }
      ClassSendNotification(FdoExtension, &GUID_IO_DEVICE_EXTERNAL_REQUEST, 0x18u, &ExtraData);
      return 0;
    case 4:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
          a2[4] & 0xF,
          a2[5]);
      }
      v19 = a2[4] & 0xF;
      if ( ((v19 - 2) & 0xFD) != 0 )
      {
        if ( v19 != 3 )
        {
          if ( v19 == 1 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
            }
            ClassSendEjectionNotification(FdoExtension);
          }
          return v15;
        }
      }
      else
      {
        v20 = FdoExtension->DeviceObject;
        if ( (v20->Characteristics & 1) != 0 )
        {
          v21 = v20->Vpb;
          if ( v21 )
          {
            if ( (v21->Flags & 1) != 0 )
              v20->Flags |= 2u;
          }
        }
        _InterlockedAdd((volatile signed __int32 *)&FdoExtension->MediaChangeCount, 1u);
      }
      ClasspSetMediaChangeStateEx(FdoExtension);
      break;
    case 6:
      *a3 = 0;
      v16 = a2[7];
      v17 = a2[5];
      LODWORD(ExtraData) = 1;
      v18 = v16 | (a2[6] << 8);
      *(_QWORD *)((char *)&ExtraData + 4) = __PAIR64__(v18, v17);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DDD(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids,
          a2[4] & 0xF,
          v17,
          v18);
      }
      if ( v18 >= 2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
        }
        ClassSendNotification(FdoExtension, &GUID_IO_DEVICE_BECOMING_READY, 0xCu, &ExtraData);
      }
      break;
  }
  return v15;
}

```

## disassembly

```asm
0x140021c78  mov     [rsp-8+arg_18], rbx
0x140021c7d  push    rbp
0x140021c7e  push    rsi
0x140021c7f  push    rdi
0x140021c80  push    r12
0x140021c82  push    r13
0x140021c84  push    r14
0x140021c86  push    r15
0x140021c88  lea     rbp, [rsp-90h]
0x140021c90  sub     rsp, 190h
0x140021c97  mov     rax, cs:__security_cookie
0x140021c9e  xor     rax, rsp
0x140021ca1  mov     [rbp+0C0h+var_40], rax
0x140021ca8  mov     rdi, [rcx+288h]
0x140021caf  xor     r13d, r13d
0x140021cb2  mov     [r8], r13b
0x140021cb5  mov     r15, r8
0x140021cb8  movzx   eax, byte ptr [rdx+2]
0x140021cbc  mov     rsi, rdx
0x140021cbf  mov     r14, rcx
0x140021cc2  test    al, al
0x140021cc4  js      loc_140021DCD
0x140021cca  test    al, 7
0x140021ccc  jz      loc_140021DCD
0x140021cd2  lea     r11, WPP_GLOBAL_Control
0x140021cd9  mov     r10d, 1000h
0x140021cdf  lea     r12, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140021ce6  lea     ebx, [r13+1]
0x140021cea  cmp     [rdi+49h], r13b
0x140021cee  jz      short loc_140021D58
0x140021cf0  movzx   r8d, byte ptr [rdi+4Ah]
0x140021cf5  mov     ecx, eax
0x140021cf7  and     ecx, 7
0x140021cfa  mov     edx, ebx
0x140021cfc  shl     dl, cl
0x140021cfe  test    dl, r8b
0x140021d01  jz      loc_140021DA7
0x140021d07  mov     al, r8b
0x140021d0a  neg     al
0x140021d0c  and     al, r8b
0x140021d0f  cmp     dl, al
0x140021d11  jz      loc_140021DAE
0x140021d17  mov     rcx, cs:WPP_GLOBAL_Control
0x140021d1e  cmp     rcx, r11
0x140021d21  jz      short loc_140021D54
0x140021d23  test    [rcx+2Ch], r10d
0x140021d27  jz      short loc_140021D54
0x140021d29  cmp     byte ptr [rcx+29h], 4
0x140021d2d  jb      short loc_140021D54
0x140021d2f  mov     rcx, [rcx+18h]
0x140021d33  movzx   r9d, dl
0x140021d37  lea     edx, [rbx+0Bh]
0x140021d3a  mov     dword ptr [rsp+1C0h+var_1A0], r8d
0x140021d3f  mov     r8, r12
0x140021d42  call    WPP_SF_DD
0x140021d47  mov     r10d, 1000h
0x140021d4d  lea     r11, WPP_GLOBAL_Control
0x140021d54  mov     [rdi+49h], r13b
0x140021d58  movzx   r9d, byte ptr [rsi]
0x140021d5c  movzx   eax, byte ptr [rsi+1]
0x140021d60  shl     r9d, 8
0x140021d64  or      r9d, eax
0x140021d67  add     r9d, 0FFFFFFFEh
0x140021d6b  cmp     r9d, 4
0x140021d6f  jge     loc_140021DFF
0x140021d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140021d7c  cmp     rcx, r11
0x140021d7f  jz      short loc_140021DA7
0x140021d81  test    [rcx+2Ch], r10d
0x140021d85  jz      short loc_140021DA7
0x140021d87  cmp     byte ptr [rcx+29h], 3
0x140021d8b  jb      short loc_140021DA7
0x140021d8d  mov     rax, [r14+8]
0x140021d91  mov     edx, 0Dh
0x140021d96  mov     rcx, [rcx+18h]
0x140021d9a  mov     r8, r12
0x140021d9d  mov     [rsp+1C0h+var_1A0], rax
0x140021da2  call    WPP_SF_Dq
0x140021da7  mov     eax, 0C0000186h
0x140021dac  jmp     short loc_140021DCF
0x140021dae  test    byte ptr [rsi+4], 0Fh
0x140021db2  jnz     short loc_140021D58
0x140021db4  mov     al, dl
0x140021db6  not     dl
0x140021db8  or      al, [rdi+4Bh]
0x140021dbb  and     dl, r8b
0x140021dbe  mov     [rdi+4Bh], al
0x140021dc1  mov     [rdi+4Ah], dl
0x140021dc4  jnz     short loc_140021DFA
0x140021dc6  mov     [rdi+4Ah], al
0x140021dc9  mov     [rdi+4Bh], r13b
0x140021dcd  xor     eax, eax
0x140021dcf  mov     rcx, [rbp+0C0h+var_40]
0x140021dd6  xor     rcx, rsp; StackCookie
0x140021dd9  call    __security_check_cookie
0x140021dde  mov     rbx, [rsp+1C0h+arg_18]
0x140021de6  add     rsp, 190h
0x140021ded  pop     r15
0x140021def  pop     r14
0x140021df1  pop     r13
0x140021df3  pop     r12
0x140021df5  pop     rdi
0x140021df6  pop     rsi
0x140021df7  pop     rbp
0x140021df8  retn
0x140021dfa  mov     [r15], bl
0x140021dfd  jmp     short loc_140021DCD
0x140021dff  jz      short loc_140021E33
0x140021e01  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e08  cmp     rcx, r11
0x140021e0b  jz      short loc_140021E33
0x140021e0d  test    [rcx+2Ch], r10d
0x140021e11  jz      short loc_140021E33
0x140021e13  cmp     byte ptr [rcx+29h], 3
0x140021e17  jb      short loc_140021E33
0x140021e19  mov     rax, [r14+8]
0x140021e1d  mov     edx, 0Eh
0x140021e22  mov     rcx, [rcx+18h]
0x140021e26  mov     r8, r12
0x140021e29  mov     [rsp+1C0h+var_1A0], rax
0x140021e2e  call    WPP_SF_Dq
0x140021e33  test    byte ptr [rsi+4], 0Fh
0x140021e37  jz      short loc_140021DCD
0x140021e39  mov     [r15], bl
0x140021e3c  mov     r12d, r13d
0x140021e3f  movzx   ecx, byte ptr [rsi+2]
0x140021e43  and     ecx, 7
0x140021e46  sub     ecx, ebx
0x140021e48  jz      loc_14002211B
0x140021e4e  sub     ecx, 2
0x140021e51  jz      loc_140022015
0x140021e57  sub     ecx, ebx
0x140021e59  jz      loc_140021F2E
0x140021e5f  cmp     ecx, 2
0x140021e62  jnz     loc_14002248E
0x140021e68  mov     [r15], r13b
0x140021e6b  movzx   eax, byte ptr [rsi+7]
0x140021e6f  movzx   r8d, byte ptr [rsi+5]
0x140021e74  mov     dword ptr [rbp+0C0h+ExtraData], ebx
0x140021e77  movzx   ebx, byte ptr [rsi+6]
0x140021e7b  shl     ebx, 8
0x140021e7e  or      ebx, eax
0x140021e80  mov     dword ptr [rbp+0C0h+ExtraData+4], r8d
0x140021e84  mov     dword ptr [rbp+0C0h+ExtraData+8], ebx
0x140021e87  mov     rcx, cs:WPP_GLOBAL_Control
0x140021e8e  lea     rax, WPP_GLOBAL_Control
0x140021e95  cmp     rcx, rax
0x140021e98  jz      short loc_140021ED7
0x140021e9a  test    dword ptr [rcx+2Ch], 1000h
0x140021ea1  jz      short loc_140021ED0
0x140021ea3  cmp     byte ptr [rcx+29h], 4
0x140021ea7  jb      short loc_140021ED0
0x140021ea9  movzx   r9d, byte ptr [rsi+4]
0x140021eae  mov     edx, 15h
0x140021eb3  mov     rcx, [rcx+18h]
0x140021eb7  and     r9d, 0Fh
0x140021ebb  mov     [rsp+1C0h+var_198], ebx
0x140021ebf  mov     dword ptr [rsp+1C0h+var_1A0], r8d
0x140021ec4  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140021ecb  call    WPP_SF_DDD
0x140021ed0  lea     rax, WPP_GLOBAL_Control
0x140021ed7  cmp     ebx, 2
0x140021eda  jb      loc_14002248E
0x140021ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x140021ee7  cmp     rcx, rax
0x140021eea  jz      short loc_140021F10
0x140021eec  test    dword ptr [rcx+2Ch], 1000h
0x140021ef3  jz      short loc_140021F10
0x140021ef5  cmp     byte ptr [rcx+29h], 4
0x140021ef9  jb      short loc_140021F10
0x140021efb  mov     rcx, [rcx+18h]
0x140021eff  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140021f06  mov     edx, 16h
0x140021f0b  call    WPP_SF_
0x140021f10  lea     r9, [rbp+0C0h+ExtraData]; ExtraData
0x140021f14  mov     r8d, 0Ch; ExtraDataSize
0x140021f1a  lea     rdx, GUID_IO_DEVICE_BECOMING_READY; Guid
0x140021f21  mov     rcx, r14; FdoExtension
0x140021f24  call    ClassSendNotification
0x140021f29  jmp     loc_14002248E
0x140021f2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f35  lea     rdx, WPP_GLOBAL_Control
0x140021f3c  cmp     rcx, rdx
0x140021f3f  jz      short loc_140021F7D
0x140021f41  test    dword ptr [rcx+2Ch], 1000h
0x140021f48  jz      short loc_140021F7D
0x140021f4a  cmp     byte ptr [rcx+29h], 4
0x140021f4e  jb      short loc_140021F7D
0x140021f50  movzx   r9d, byte ptr [rsi+4]
0x140021f55  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140021f5c  movzx   eax, byte ptr [rsi+5]
0x140021f60  and     r9d, 0Fh
0x140021f64  mov     rcx, [rcx+18h]
0x140021f68  mov     edx, 13h
0x140021f6d  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x140021f71  call    WPP_SF_DD
0x140021f76  lea     rdx, WPP_GLOBAL_Control
0x140021f7d  mov     cl, [rsi+4]
0x140021f80  and     cl, 0Fh
0x140021f83  lea     eax, [rcx-2]
0x140021f86  test    al, 0FDh
0x140021f88  jz      short loc_140021FDB
0x140021f8a  cmp     cl, 3
0x140021f8d  jnz     short loc_140021F96
0x140021f8f  mov     edx, 2
0x140021f94  jmp     short loc_140022002
0x140021f96  cmp     cl, bl
0x140021f98  jnz     loc_14002248E
0x140021f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021fa5  cmp     rcx, rdx
0x140021fa8  jz      short loc_140021FCE
0x140021faa  test    dword ptr [rcx+2Ch], 1000h
0x140021fb1  jz      short loc_140021FCE
0x140021fb3  cmp     byte ptr [rcx+29h], 4
0x140021fb7  jb      short loc_140021FCE
0x140021fb9  mov     rcx, [rcx+18h]
0x140021fbd  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140021fc4  mov     edx, 14h
0x140021fc9  call    WPP_SF_
0x140021fce  mov     rcx, r14; FdoExtension
0x140021fd1  call    ClassSendEjectionNotification
0x140021fd6  jmp     loc_14002248E
0x140021fdb  mov     rcx, [r14+8]
0x140021fdf  mov     eax, [rcx+34h]
0x140021fe2  test    bl, al
0x140021fe4  jz      short loc_140021FF8
0x140021fe6  mov     rax, [rcx+38h]
0x140021fea  test    rax, rax
0x140021fed  jz      short loc_140021FF8
0x140021fef  test    [rax+4], bl
0x140021ff2  jz      short loc_140021FF8
0x140021ff4  or      dword ptr [rcx+30h], 2
0x140021ff8  lock add [r14+2B8h], ebx
0x140022000  mov     edx, ebx
0x140022002  xor     r8d, r8d
0x140022005  mov     r9b, bl
0x140022008  mov     rcx, r14; FdoExtension
0x14002200b  call    ClasspSetMediaChangeStateEx
0x140022010  jmp     loc_14002248E
0x140022015  movzx   edx, byte ptr [rsi+4]
0x140022019  mov     al, dl
0x14002201b  mov     dword ptr [rbp+0C0h+ExtraData+0Ch], r13d
0x14002201f  and     al, 0Fh
0x140022021  cmp     al, bl
0x140022023  jnz     loc_14002248E
0x140022029  mov     rcx, cs:WPP_GLOBAL_Control
0x140022030  lea     rdi, WPP_GLOBAL_Control
0x140022037  cmp     rcx, rdi
0x14002203a  jz      short loc_140022087
0x14002203c  test    dword ptr [rcx+2Ch], 1000h
0x140022043  jz      short loc_140022087
0x140022045  cmp     byte ptr [rcx+29h], 4
0x140022049  jb      short loc_140022087
0x14002204b  movzx   r8d, byte ptr [rsi+6]
0x140022050  mov     r9d, edx
0x140022053  movzx   eax, byte ptr [rsi+7]
0x140022057  and     r9d, 0Fh
0x14002205b  mov     rcx, [rcx+18h]
0x14002205f  mov     edx, 11h
0x140022064  shl     r8d, 8
0x140022068  or      r8d, eax
0x14002206b  movzx   eax, byte ptr [rsi+5]
0x14002206f  mov     [rsp+1C0h+var_198], r8d
0x140022074  and     eax, 0Fh
0x140022077  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x14002207e  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x140022082  call    WPP_SF_DDD
0x140022087  mov     al, [rsi+4]
0x14002208a  movzx   ecx, byte ptr [rsi+6]
0x14002208e  and     al, 0Fh
0x140022090  movzx   eax, al
0x140022093  mov     qword ptr [rbp+0C0h+ExtraData], rbx
0x140022097  mov     rbx, 0FFFFF78000000014h
0x1400220a1  mov     word ptr [rbp+0C0h+ExtraData+8], ax
0x1400220a5  movzx   eax, byte ptr [rsi+7]
0x1400220a9  shl     cx, 8
0x1400220ad  mov     rbx, [rbx]
0x1400220b0  or      cx, ax
0x1400220b3  mov     word ptr [rbp+0C0h+ExtraData+0Ah], cx
0x1400220b7  call    cs:__imp_KeQueryTimeIncrement
0x1400220be  nop     dword ptr [rax+rax+00h]
0x1400220c3  mov     eax, eax
0x1400220c5  imul    rax, rbx
0x1400220c9  mov     [rbp+0C0h+var_110], rax
0x1400220cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400220d4  cmp     rcx, rdi
0x1400220d7  jz      short loc_1400220FD
0x1400220d9  test    dword ptr [rcx+2Ch], 1000h
0x1400220e0  jz      short loc_1400220FD
0x1400220e2  cmp     byte ptr [rcx+29h], 4
0x1400220e6  jb      short loc_1400220FD
0x1400220e8  mov     rcx, [rcx+18h]
0x1400220ec  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x1400220f3  mov     edx, 12h
0x1400220f8  call    WPP_SF_
0x1400220fd  lea     r9, [rbp+0C0h+ExtraData]; ExtraData
0x140022101  mov     r8d, 18h; ExtraDataSize
0x140022107  lea     rdx, GUID_IO_DEVICE_EXTERNAL_REQUEST; Guid
0x14002210e  mov     rcx, r14; FdoExtension
0x140022111  call    ClassSendNotification
  ... truncated ...
```
