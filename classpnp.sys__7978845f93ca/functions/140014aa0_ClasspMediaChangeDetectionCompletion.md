# ClasspMediaChangeDetectionCompletion

- ea: `0x140014aa0`
- end: `0x14001511a`
- name: `ClasspMediaChangeDetectionCompletion`
- size: `1658`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _BYTE *, unsigned __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008360`
- `0x140010040`
- `0x1400134a0`
- `0x140014aa0`
- `0x140015120`
- `0x140015210`
- `0x1400157d0`
- `0x140016d50`
- `0x14001f450`
- `0x14001fbf4`
- `0x14001fc38`
- `0x14001feac`
- `0x140021c78`
- `0x140022668`
- `0x1400227b4`
- `0x140038784`
- `0x140038b84`
- `0x140039818`
- `0x140039aa0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140014f9a`
- `ntoskrnl!IoQueueWorkItem` at `0x140014f9a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140014fd2`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140014fd2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400150c0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400150c0`
- `ntoskrnl!IoAllocateWorkItem` at `0x140014f5b`
- `ntoskrnl!IoAllocateWorkItem` at `0x140014f5b`

## pseudocode

```c
__int64 __fastcall ClasspMediaChangeDetectionCompletion(__int64 a1, _QWORD *a2, _BYTE *a3, unsigned __int64 a4)
{
  _BYTE *v4; // rbp
  struct _DEVICE_OBJECT *v6; // r15
  struct _FUNCTIONAL_DEVICE_EXTENSION *DeviceExtension; // r13
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // rsi
  _MEDIA_CHANGE_DETECTION_INFO *MediaChangeDetectionInfo; // r14
  char v10; // di
  unsigned int v11; // r11d
  __int64 v12; // r10
  char v13; // bl
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // ecx
  unsigned __int8 v18; // dl
  unsigned int v19; // edi
  __int64 v20; // r11
  char v21; // bl
  __int64 v22; // rcx
  unsigned __int64 v23; // r10
  int v24; // ecx
  int v25; // ecx
  char v26; // r9
  char v27; // r10
  _BYTE *v28; // rcx
  _BYTE *v29; // rax
  unsigned int v30; // eax
  char v31; // al
  char v32; // al
  _DEVICE_OBJECT *AttachedDevice; // rsi
  __int64 AdditionalSenseCodeQualifierStr; // rdi
  __int64 AdditionalSenseCodeStr; // rbx
  int SrbStatusStr; // eax
  int v37; // edx
  int v38; // r8d
  __int64 v39; // r10
  $BB685A3CEED607A01ADFB3509F1B60F2 *p_Gesn; // rbx
  __int64 v41; // r9
  PIO_WORKITEM WorkItem; // rax
  struct _IO_WORKITEM *v43; // rdi
  volatile signed __int32 **v44; // rbx
  _DWORD **v45; // r8
  signed __int32 v46; // eax
  signed __int32 v47; // ett
  _DWORD *v48; // rcx
  __int64 v50; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v51; // [rsp+88h] [rbp+10h] BYREF

  v50 = a1;
  v51 = 0;
  v4 = a3;
  LOBYTE(v50) = 0;
  v6 = *(struct _DEVICE_OBJECT **)(a2[23] + 40LL);
  DeviceExtension = (struct _FUNCTIONAL_DEVICE_EXTENSION *)v6->DeviceExtension;
  PrivateFdoData = DeviceExtension->PrivateFdoData;
  MediaChangeDetectionInfo = DeviceExtension->MediaChangeDetectionInfo;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v6, a2);
  }
  if ( (v4[3] & 0x3F) == 1 || (DeviceExtension->ScanForSpecialFlags & 0x20) == 0 )
    goto LABEL_60;
  v10 = v4[2];
  if ( v10 != 40 )
  {
    a3 = (_BYTE *)*((_QWORD *)v4 + 4);
LABEL_27:
    if ( !a3 )
      goto LABEL_60;
    if ( v10 == 40 )
    {
      v18 = 0;
      if ( !*((_DWORD *)v4 + 5) )
      {
        v19 = *((_DWORD *)v4 + 14);
        if ( v19 )
        {
          v20 = 0;
          v21 = 0;
          while ( 1 )
          {
            v22 = *(unsigned int *)&v4[4 * v20 + 120];
            if ( (unsigned int)v22 >= 0x80 )
            {
              v23 = *((unsigned int *)v4 + 4);
              if ( (unsigned int)v22 < (unsigned int)v23 )
                break;
            }
LABEL_39:
            v20 = (unsigned int)(v20 + 1);
            if ( (unsigned int)v20 >= v19 )
              goto LABEL_45;
          }
          a4 = (unsigned int)v22;
          v24 = *(_DWORD *)&v4[v22] - 64;
          if ( !v24 )
            goto LABEL_37;
          v25 = v24 - 1;
          if ( v25 )
          {
            if ( v25 == 1 )
            {
LABEL_37:
              if ( a4 + 40 <= v23 )
              {
                v18 = v4[a4 + 9];
                goto LABEL_45;
              }
            }
          }
          else if ( a4 + 56 <= v23 )
          {
            v18 = v4[a4 + 9];
            v21 = 1;
          }
          if ( v21 )
            goto LABEL_45;
          goto LABEL_39;
        }
      }
    }
    else
    {
      v18 = v4[11];
    }
LABEL_45:
    if ( !v18 )
      goto LABEL_60;
    v26 = 0;
    v27 = 0;
    v28 = &a3[v18];
    v29 = a3 + 8;
    if ( (unsigned __int8)((*a3 & 0x7F) - 114) <= 1u )
    {
      if ( v29 <= v28 )
      {
        v27 = a3[2];
        v26 = a3[1] & 0xF;
LABEL_54:
        v31 = 1;
LABEL_56:
        if ( v31 && v26 == 2 && v27 == 4 )
          v4[3] = 1;
        goto LABEL_60;
      }
    }
    else if ( v29 <= v28 )
    {
      v30 = v18;
      v26 = a3[2] & 0xF;
      if ( (unsigned int)(unsigned __int8)a3[7] + 8 <= v18 )
        v30 = (unsigned __int8)a3[7] + 8;
      if ( a3 + 13 <= &a3[v30] )
        v27 = a3[12];
      goto LABEL_54;
    }
    v31 = 0;
    goto LABEL_56;
  }
  if ( *((_DWORD *)v4 + 5) )
  {
    a3 = 0;
    goto LABEL_27;
  }
  v11 = *((_DWORD *)v4 + 14);
  if ( v11 )
  {
    a3 = 0;
    v12 = 0;
    v13 = 0;
    while ( 1 )
    {
      v14 = *(unsigned int *)&v4[4 * v12 + 120];
      if ( (unsigned int)v14 >= 0x80 )
      {
        a4 = *((unsigned int *)v4 + 4);
        if ( (unsigned int)v14 < (unsigned int)a4 )
        {
          v15 = (unsigned int)v14;
          v16 = *(_DWORD *)&v4[v14] - 64;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              if ( v17 == 1 && v15 + 40 <= a4 )
              {
                a3 = *(_BYTE **)&v4[v15 + 24];
                goto LABEL_27;
              }
            }
            else if ( v15 + 56 <= a4 )
            {
              a3 = *(_BYTE **)&v4[v15 + 16];
              v13 = 1;
            }
          }
          else if ( v15 + 40 <= a4 )
          {
            a3 = *(_BYTE **)&v4[v15 + 16];
            goto LABEL_27;
          }
          if ( v13 )
            goto LABEL_27;
        }
      }
      v12 = (unsigned int)(v12 + 1);
      if ( (unsigned int)v12 >= v11 )
        goto LABEL_27;
    }
  }
LABEL_60:
  v32 = v4[3] & 0x3F;
  v51 = 0;
  if ( v32 == 1 )
  {
    PrivateFdoData->LoggedTURFailureSinceLastIO = 0;
    p_Gesn = &MediaChangeDetectionInfo->Gesn;
    if ( MediaChangeDetectionInfo->Gesn.Supported )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
      }
      ClasspSetMediaChangeStateEx(DeviceExtension);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      AdditionalSenseCodeQualifierStr = DbgGetAdditionalSenseCodeQualifierStr(v4);
      AdditionalSenseCodeStr = DbgGetAdditionalSenseCodeStr(v4);
      DbgGetSenseCodeStr(v4);
      SrbStatusStr = DbgGetSrbStatusStr(v4);
      WPP_SF_ssss(
        (_DWORD)AttachedDevice,
        v37,
        v38,
        SrbStatusStr,
        v39,
        AdditionalSenseCodeStr,
        AdditionalSenseCodeQualifierStr);
    }
    LOBYTE(a4) = 15;
    InterpretSenseInfoWithoutHistory(v6, a2, v4, a4, 0, 0, &v51, 0);
    p_Gesn = &MediaChangeDetectionInfo->Gesn;
  }
  if ( p_Gesn->Supported )
  {
    v41 = v51;
    if ( v51 == -1073741764 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
      }
      v41 = 0;
      v51 = 0;
    }
    if ( (int)v41 >= 0 )
    {
      if ( a2[7] == 8 )
        ClasspInterpretGesnData(DeviceExtension, MediaChangeDetectionInfo->Gesn.Buffer, (char *)&v50);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v41);
    }
  }
  if ( (unsigned __int8)PORT_ALLOCATED_SENSE_EX(DeviceExtension, v4, a3) )
    FREE_PORT_ALLOCATED_SENSE_BUFFER_EX(DeviceExtension);
  *(_QWORD *)(a2[23] - 64LL) = v4;
  ClassResetMediaChangeTimer(DeviceExtension);
  if ( (_BYTE)v50 )
  {
    if ( ++MediaChangeDetectionInfo->MediaChangeRetryCount > 32 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids, v6);
      }
      WorkItem = IoAllocateWorkItem(v6);
      v43 = WorkItem;
      if ( WorkItem )
      {
        ClassAcquireRemoveLockEx(v6, WorkItem, "minkernel\\storage\\classpnp\\autorun.c", 0x4D7u);
        IoQueueWorkItem(v43, ClasspDisableGesn, DelayedWorkQueue, v43);
      }
      p_Gesn->Supported = 0;
      MediaChangeDetectionInfo->Gesn.EventMask = 0;
      MediaChangeDetectionInfo->Gesn.BufferSize = 0;
      MediaChangeDetectionInfo->MediaChangeRetryCount = 0;
      LOBYTE(v50) = 0;
    }
  }
  else
  {
    MediaChangeDetectionInfo->MediaChangeRetryCount = 0;
  }
  v44 = (volatile signed __int32 **)v6->DeviceExtension;
  if ( !ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v44[55] + 2)) )
  {
    _InterlockedIncrement(v44[55]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_a22cc05f221e30b8049471910da99059_Traceguids,
        *(unsigned int *)v44[55]);
    }
  }
  ClassReleaseRemoveLock(v6, a2);
  _InterlockedCompareExchange(&MediaChangeDetectionInfo->MediaChangeIrpInUse, 0, 1);
  if ( (_BYTE)v50 )
  {
    ClasspSendMediaStateIrp(DeviceExtension, MediaChangeDetectionInfo, 0);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
  }
  v45 = (_DWORD **)v6->DeviceExtension;
  v46 = *v45[55];
  while ( 1 )
  {
    v48 = v45[55];
    if ( !v46 )
      break;
    v47 = v46;
    v46 = _InterlockedCompareExchange(v48, v46 - 1, v46);
    if ( v47 == v46 )
      goto LABEL_117;
  }
  ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v48 + 2));
LABEL_117:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140014aa0  mov     rax, rsp
0x140014aa3  mov     [rax+18h], rbx
0x140014aa7  mov     [rax+8], rcx
0x140014aab  push    rbp
0x140014aac  push    rsi
0x140014aad  push    rdi
0x140014aae  push    r12
0x140014ab0  push    r13
0x140014ab2  push    r14
0x140014ab4  push    r15
0x140014ab6  sub     rsp, 40h
0x140014aba  mov     dword ptr [rax+10h], 0
0x140014ac1  mov     rbp, r8
0x140014ac4  mov     byte ptr [rax+8], 0
0x140014ac8  mov     r12, rdx
0x140014acb  mov     rax, [rdx+0B8h]
0x140014ad2  mov     r15, [rax+28h]
0x140014ad6  mov     r13, [r15+40h]
0x140014ada  mov     rsi, [r13+478h]
0x140014ae1  mov     r14, [r13+288h]
0x140014ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x140014aef  lea     rdi, WPP_GLOBAL_Control
0x140014af6  cmp     rcx, rdi
0x140014af9  jz      short loc_140014B27
0x140014afb  test    dword ptr [rcx+2Ch], 1000h
0x140014b02  jz      short loc_140014B27
0x140014b04  cmp     byte ptr [rcx+29h], 5
0x140014b08  jb      short loc_140014B27
0x140014b0a  mov     rcx, [rcx+18h]
0x140014b0e  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140014b15  mov     edx, 1Fh
0x140014b1a  mov     [rsp+78h+var_58], r12
0x140014b1f  mov     r9, r15
0x140014b22  call    WPP_SF_qq
0x140014b27  mov     al, [rbp+3]
0x140014b2a  and     al, 3Fh
0x140014b2c  cmp     al, 1
0x140014b2e  jz      loc_140014CEF
0x140014b34  mov     eax, [r13+36Ch]
0x140014b3b  test    al, 20h
0x140014b3d  jz      loc_140014CEF
0x140014b43  mov     dil, [rbp+2]
0x140014b47  cmp     dil, 28h ; '('
0x140014b4b  jnz     loc_140014BDB
0x140014b51  cmp     dword ptr [rbp+14h], 0
0x140014b55  jnz     short loc_140014BD6
0x140014b57  mov     r11d, [rbp+38h]
0x140014b5b  test    r11d, r11d
0x140014b5e  jz      loc_140014CE8
0x140014b64  xor     r8d, r8d
0x140014b67  xor     r10d, r10d
0x140014b6a  xor     bl, bl
0x140014b6c  mov     ecx, [rbp+r10*4+78h]
0x140014b71  cmp     ecx, 80h
0x140014b77  jb      short loc_140014BC5
0x140014b79  mov     r9d, [rbp+10h]
0x140014b7d  cmp     ecx, r9d
0x140014b80  jnb     short loc_140014BC5
0x140014b82  mov     edx, ecx
0x140014b84  mov     ecx, [rcx+rbp]
0x140014b87  sub     ecx, 40h ; '@'
0x140014b8a  jz      short loc_140014BB8
0x140014b8c  sub     ecx, 1
0x140014b8f  jz      short loc_140014BA6
0x140014b91  cmp     ecx, 1
0x140014b94  jnz     short loc_140014BC1
0x140014b96  lea     rcx, [rdx+28h]
0x140014b9a  cmp     rcx, r9
0x140014b9d  ja      short loc_140014BC1
0x140014b9f  mov     r8, [rdx+rbp+18h]
0x140014ba4  jmp     short loc_140014BDF
0x140014ba6  lea     rcx, [rdx+38h]
0x140014baa  cmp     rcx, r9
0x140014bad  ja      short loc_140014BC1
0x140014baf  mov     r8, [rdx+rbp+10h]
0x140014bb4  mov     bl, 1
0x140014bb6  jmp     short loc_140014BC1
0x140014bb8  lea     rcx, [rdx+28h]
0x140014bbc  cmp     rcx, r9
0x140014bbf  jbe     short loc_140014BCF
0x140014bc1  test    bl, bl
0x140014bc3  jnz     short loc_140014BDF
0x140014bc5  inc     r10d
0x140014bc8  cmp     r10d, r11d
0x140014bcb  jb      short loc_140014B6C
0x140014bcd  jmp     short loc_140014BDF
0x140014bcf  mov     r8, [rdx+rbp+10h]
0x140014bd4  jmp     short loc_140014BDF
0x140014bd6  xor     r8d, r8d
0x140014bd9  jmp     short loc_140014BDF
0x140014bdb  mov     r8, [rbp+20h]
0x140014bdf  test    r8, r8
0x140014be2  jz      loc_140014CE8
0x140014be8  cmp     dil, 28h ; '('
0x140014bec  jnz     short loc_140014C5D
0x140014bee  xor     dl, dl
0x140014bf0  cmp     dword ptr [rbp+14h], 0
0x140014bf4  jnz     short loc_140014C60
0x140014bf6  mov     edi, [rbp+38h]
0x140014bf9  test    edi, edi
0x140014bfb  jz      short loc_140014C60
0x140014bfd  xor     r11d, r11d
0x140014c00  xor     bl, bl
0x140014c02  mov     ecx, [rbp+r11*4+78h]
0x140014c07  cmp     ecx, 80h
0x140014c0d  jb      short loc_140014C3A
0x140014c0f  mov     r10d, [rbp+10h]
0x140014c13  cmp     ecx, r10d
0x140014c16  jnb     short loc_140014C3A
0x140014c18  mov     r9d, ecx
0x140014c1b  mov     ecx, [rcx+rbp]
0x140014c1e  sub     ecx, 40h ; '@'
0x140014c21  jz      short loc_140014C2D
0x140014c23  sub     ecx, 1
0x140014c26  jz      short loc_140014C44
0x140014c28  cmp     ecx, 1
0x140014c2b  jnz     short loc_140014C36
0x140014c2d  lea     rcx, [r9+28h]
0x140014c31  cmp     rcx, r10
0x140014c34  jbe     short loc_140014C56
0x140014c36  test    bl, bl
0x140014c38  jnz     short loc_140014C60
0x140014c3a  inc     r11d
0x140014c3d  cmp     r11d, edi
0x140014c40  jb      short loc_140014C02
0x140014c42  jmp     short loc_140014C60
0x140014c44  lea     rcx, [r9+38h]
0x140014c48  cmp     rcx, r10
0x140014c4b  ja      short loc_140014C36
0x140014c4d  mov     dl, [r9+rbp+9]
0x140014c52  mov     bl, 1
0x140014c54  jmp     short loc_140014C36
0x140014c56  mov     dl, [r9+rbp+9]
0x140014c5b  jmp     short loc_140014C60
0x140014c5d  mov     dl, [rbp+0Bh]
0x140014c60  test    dl, dl
0x140014c62  jz      loc_140014CE8
0x140014c68  mov     al, [r8]
0x140014c6b  xor     r9b, r9b
0x140014c6e  and     al, 7Fh
0x140014c70  movzx   ecx, dl
0x140014c73  sub     al, 72h ; 'r'
0x140014c75  xor     r10b, r10b
0x140014c78  add     rcx, r8
0x140014c7b  cmp     al, 1
0x140014c7d  lea     rax, [r8+8]
0x140014c81  jbe     short loc_140014CB4
0x140014c83  cmp     rax, rcx
0x140014c86  ja      short loc_140014CC9
0x140014c88  movzx   ecx, byte ptr [r8+7]
0x140014c8d  mov     r9b, [r8+2]
0x140014c91  add     ecx, 8
0x140014c94  movzx   eax, dl
0x140014c97  and     r9b, 0Fh
0x140014c9b  cmp     ecx, eax
0x140014c9d  cmovbe  eax, ecx
0x140014ca0  mov     ecx, eax
0x140014ca2  lea     rax, [r8+0Dh]
0x140014ca6  add     rcx, r8
0x140014ca9  cmp     rax, rcx
0x140014cac  ja      short loc_140014CC5
0x140014cae  mov     r10b, [r8+0Ch]
0x140014cb2  jmp     short loc_140014CC5
0x140014cb4  cmp     rax, rcx
0x140014cb7  ja      short loc_140014CC9
0x140014cb9  mov     r9b, [r8+1]
0x140014cbd  mov     r10b, [r8+2]
0x140014cc1  and     r9b, 0Fh
0x140014cc5  mov     al, 1
0x140014cc7  jmp     short loc_140014CCB
0x140014cc9  xor     al, al
0x140014ccb  test    al, al
0x140014ccd  jz      short loc_140014CE8
0x140014ccf  cmp     r9b, 2
0x140014cd3  jnz     short loc_140014CE8
0x140014cd5  lea     rdi, WPP_GLOBAL_Control
0x140014cdc  cmp     r10b, 4
0x140014ce0  jnz     short loc_140014CEF
0x140014ce2  mov     byte ptr [rbp+3], 1
0x140014ce6  jmp     short loc_140014CEF
0x140014ce8  lea     rdi, WPP_GLOBAL_Control
0x140014cef  mov     al, [rbp+3]
0x140014cf2  and     al, 3Fh
0x140014cf4  mov     [rsp+78h+arg_8], 0
0x140014cff  cmp     al, 1
0x140014d01  jz      loc_140014DB2
0x140014d07  mov     rsi, cs:WPP_GLOBAL_Control
0x140014d0e  cmp     rsi, rdi
0x140014d11  jz      short loc_140014D70
0x140014d13  test    dword ptr [rsi+2Ch], 1000h
0x140014d1a  jz      short loc_140014D70
0x140014d1c  cmp     byte ptr [rsi+29h], 3
0x140014d20  jb      short loc_140014D70
0x140014d22  mov     rsi, [rsi+18h]
0x140014d26  mov     rcx, rbp
0x140014d29  call    DbgGetAdditionalSenseCodeQualifierStr
0x140014d2e  mov     rcx, rbp
0x140014d31  mov     rdi, rax
0x140014d34  call    DbgGetAdditionalSenseCodeStr
0x140014d39  mov     rcx, rbp
0x140014d3c  mov     rbx, rax
0x140014d3f  call    DbgGetSenseCodeStr
0x140014d44  mov     rcx, rbp
0x140014d47  mov     r10, rax
0x140014d4a  call    DbgGetSrbStatusStr
0x140014d4f  mov     [rsp+78h+var_48], rdi
0x140014d54  mov     r9, rax
0x140014d57  mov     [rsp+78h+var_50], rbx
0x140014d5c  mov     rcx, rsi
0x140014d5f  mov     [rsp+78h+var_58], r10
0x140014d64  call    WPP_SF_ssss
0x140014d69  lea     rdi, WPP_GLOBAL_Control
0x140014d70  mov     [rsp+78h+var_40], 0
0x140014d79  lea     rax, [rsp+78h+arg_8]
0x140014d81  mov     [rsp+78h+var_48], rax
0x140014d86  mov     r9b, 0Fh
0x140014d89  mov     dword ptr [rsp+78h+var_50], 0
0x140014d91  mov     r8, rbp
0x140014d94  mov     rdx, r12
0x140014d97  mov     dword ptr [rsp+78h+var_58], 0
0x140014d9f  mov     rcx, r15
0x140014da2  call    InterpretSenseInfoWithoutHistory
0x140014da7  xor     esi, esi
0x140014da9  lea     rbx, [r14+48h]
0x140014dad  jmp     loc_140014E36
0x140014db2  mov     byte ptr [rsi+295h], 0
0x140014db9  lea     rbx, [r14+48h]
0x140014dbd  xor     esi, esi
0x140014dbf  cmp     [rbx], sil
0x140014dc2  jnz     short loc_140014E06
0x140014dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140014dcb  cmp     rcx, rdi
0x140014dce  jz      short loc_140014DF2
0x140014dd0  test    dword ptr [rcx+2Ch], 1000h
0x140014dd7  jz      short loc_140014DF2
0x140014dd9  cmp     byte ptr [rcx+29h], 4
0x140014ddd  jb      short loc_140014DF2
0x140014ddf  mov     rcx, [rcx+18h]
0x140014de3  lea     edx, [rsi+21h]
0x140014de6  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140014ded  call    WPP_SF_
0x140014df2  xor     r9d, r9d
0x140014df5  xor     r8d, r8d
0x140014df8  mov     rcx, r13; FdoExtension
0x140014dfb  lea     edx, [r9+1]
0x140014dff  call    ClasspSetMediaChangeStateEx
0x140014e04  jmp     short loc_140014E36
0x140014e06  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e0d  cmp     rcx, rdi
0x140014e10  jz      short loc_140014E36
0x140014e12  test    dword ptr [rcx+2Ch], 1000h
0x140014e19  jz      short loc_140014E36
0x140014e1b  cmp     byte ptr [rcx+29h], 4
0x140014e1f  jb      short loc_140014E36
0x140014e21  mov     rcx, [rcx+18h]
0x140014e25  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140014e2c  mov     edx, 22h ; '"'
0x140014e31  call    WPP_SF_
0x140014e36  cmp     [rbx], sil
0x140014e39  jz      loc_140014EDD
0x140014e3f  mov     r9d, [rsp+78h+arg_8]
0x140014e47  cmp     r9d, 0C000003Ch
0x140014e4e  jnz     short loc_140014E8A
0x140014e50  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e57  cmp     rcx, rdi
0x140014e5a  jz      short loc_140014E80
0x140014e5c  test    dword ptr [rcx+2Ch], 1000h
0x140014e63  jz      short loc_140014E80
0x140014e65  cmp     byte ptr [rcx+29h], 4
0x140014e69  jb      short loc_140014E80
0x140014e6b  mov     rcx, [rcx+18h]
0x140014e6f  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140014e76  mov     edx, 23h ; '#'
0x140014e7b  call    WPP_SF_
0x140014e80  mov     r9d, esi
0x140014e83  mov     [rsp+78h+arg_8], esi
0x140014e8a  test    r9d, r9d
0x140014e8d  jns     short loc_140014EC1
0x140014e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e96  cmp     rcx, rdi
0x140014e99  jz      short loc_140014EDD
0x140014e9b  test    dword ptr [rcx+2Ch], 1000h
0x140014ea2  jz      short loc_140014EDD
0x140014ea4  cmp     byte ptr [rcx+29h], 4
0x140014ea8  jb      short loc_140014EDD
0x140014eaa  mov     rcx, [rcx+18h]
0x140014eae  lea     r8, WPP_b6d7dd4ba2733324f803b9b140d6a6e4_Traceguids
0x140014eb5  mov     edx, 24h ; '$'
0x140014eba  call    WPP_SF_d
0x140014ebf  jmp     short loc_140014EDD
0x140014ec1  cmp     qword ptr [r12+38h], 8
0x140014ec7  jnz     short loc_140014EDD
0x140014ec9  mov     rdx, [r14+50h]
0x140014ecd  lea     r8, [rsp+78h+arg_0]
0x140014ed5  mov     rcx, r13; FdoExtension
0x140014ed8  call    ClasspInterpretGesnData
0x140014edd  mov     rdx, rbp
0x140014ee0  mov     rcx, r13
0x140014ee3  call    PORT_ALLOCATED_SENSE_EX
0x140014ee8  test    al, al
  ... truncated ...
```
