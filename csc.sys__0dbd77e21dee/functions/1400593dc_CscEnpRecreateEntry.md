# CscEnpRecreateEntry

- ea: `0x1400593dc`
- end: `0x140059ed3`
- name: `CscEnpRecreateEntry`
- size: `2807`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `2`
- callee_count: `34`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140024f60`
- `0x1400255bc`

## callees

- `0x140005390`
- `0x140007420`
- `0x14000b5a0`
- `0x14000be90`
- `0x14000c3dc`
- `0x14000cd00`
- `0x14000d744`
- `0x14000d960`
- `0x140010f6c`
- `0x140011dac`
- `0x140012214`
- `0x1400160f4`
- `0x140017908`
- `0x140017ebc`
- `0x140018930`
- `0x1400190ec`
- `0x14001a624`
- `0x14001ac1c`
- `0x140020028`
- `0x140025170`
- `0x1400252c4`
- `0x140025370`
- `0x1400254b8`
- `0x1400255f8`
- `0x140025790`
- `0x140029964`
- `0x140029cf0`
- `0x14002a780`
- `0x14002f010`
- `0x14002f440`
- `0x140059188`
- `0x1400593dc`
- `0x14005f838`
- `0x140082ccc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140059971`
- `ntoskrnl!ObfDereferenceObject` at `0x140059971`
- `ntoskrnl!IoFileObjectType` at `0x140059935`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005995b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005995b`

## string_xrefs

- `0x140059442`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx`
- `0x140059455`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx_1`
- `0x14005942e`: `c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Common`

## pseudocode

```c
__int64 __fastcall CscEnpRecreateEntry(__int64 a1, unsigned int *a2)
{
  __int64 v4; // rdx
  int v5; // r8d
  int v6; // ecx
  unsigned __int16 *v7; // r13
  int v8; // ecx
  int PrincipalForCurrentThread; // ebx
  int v10; // esi
  __int64 v11; // r8
  void *v12; // rdx
  __int64 v13; // rsi
  __m128i v14; // xmm2
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  _OWORD *v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // eax
  bool v25; // zf
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // eax
  int HandleInformation; // [rsp+28h] [rbp-D8h]
  char v33; // [rsp+60h] [rbp-A0h]
  char v34; // [rsp+61h] [rbp-9Fh]
  char v35; // [rsp+62h] [rbp-9Eh]
  unsigned __int16 v36[2]; // [rsp+64h] [rbp-9Ch] BYREF
  char v37; // [rsp+68h] [rbp-98h]
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  _OWORD *v40; // [rsp+80h] [rbp-80h] BYREF
  void *v41; // [rsp+88h] [rbp-78h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  PVOID Object; // [rsp+98h] [rbp-68h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING UnicodeString; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v46[2]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v47[2]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v48[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v49[2]; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v50[2]; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v51[2]; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v52[2]; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v53[2]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v54[20]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v55; // [rsp+220h] [rbp+120h] BYREF
  __int128 v56; // [rsp+230h] [rbp+130h]
  __int64 v57; // [rsp+240h] [rbp+140h]
  _OWORD v58[5]; // [rsp+250h] [rbp+150h] BYREF

  v46[0] = 3145775;
  v38 = 0;
  v42 = 0;
  v57 = 0;
  v36[0] = 0;
  v46[1] = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Common";
  v35 = 0;
  v47[1] = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx";
  v34 = 0;
  v48[1] = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.CommonEx_1";
  v47[0] = 3276849;
  v49[1] = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.User";
  v48[0] = 3407923;
  v55 = 0;
  v49[0] = 3014701;
  v56 = 0;
  v41 = 0;
  UnicodeString = 0;
  LODWORD(v40) = 0;
  memset(v50, 0, sizeof(v50));
  v37 = 0;
  memset(v51, 0, sizeof(v51));
  memset(v52, 0, sizeof(v52));
  memset(v53, 0, sizeof(v53));
  memset(v58, 0, sizeof(v58));
  memset(v54, 0, sizeof(v54));
  v5 = *a2;
  v6 = *a2;
  v44 = *(_QWORD *)(a1 + 144);
  LOBYTE(v7) = 0;
  v33 = 0;
  Handle = 0;
  Object = 0;
  v8 = v6 - 1;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      LOBYTE(HandleInformation) = *((_BYTE *)a2 + 8);
      WPP_SF_qDc(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids, a1, v5);
    }
LABEL_13:
    if ( (*(_DWORD *)(a1 + 336) & 0x10) != 0 )
    {
      PrincipalForCurrentThread = -1073741811;
      v10 = 915;
      goto LABEL_103;
    }
    v4 = *a2;
    v7 = 0;
    if ( (_DWORD)v4 == 2 )
    {
      if ( (*(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL) & 0x1000) == 0 )
      {
        PrincipalForCurrentThread = -1073741811;
        v10 = 927;
        goto LABEL_103;
      }
      if ( *(_WORD *)(a1 + 402) )
      {
        PrincipalForCurrentThread = CscEnpQueryPrincipalForCurrentThread(a1, v36);
        if ( PrincipalForCurrentThread < 0 )
        {
          v10 = 938;
          goto LABEL_103;
        }
        if ( *(_WORD *)(a1 + 402) != v36[0] )
        {
          PrincipalForCurrentThread = -1073741811;
          v10 = 947;
          goto LABEL_103;
        }
        v4 = *a2;
      }
      v7 = v36;
    }
    if ( (_DWORD)v4 == 1 )
    {
      PrincipalForCurrentThread = CscDiffTransferRemoveState(a1);
      if ( PrincipalForCurrentThread < 0 )
      {
        v10 = 962;
        goto LABEL_102;
      }
      PrincipalForCurrentThread = CscDiffTransferCloseHandle(a1);
      if ( PrincipalForCurrentThread < 0 )
      {
        v10 = 966;
        goto LABEL_102;
      }
    }
    else if ( *(_DWORD *)(a1 + 164) )
    {
      PrincipalForCurrentThread = -1073741790;
      v10 = 978;
      goto LABEL_102;
    }
    if ( *a2 == 1 )
    {
      if ( *((_BYTE *)a2 + 8) )
      {
        PrincipalForCurrentThread = CscEnpQueryPrincipalForCurrentThread(a1, v36);
        if ( PrincipalForCurrentThread < 0 )
        {
          v10 = 992;
          goto LABEL_102;
        }
      }
      v7 = v36;
    }
    v55 = *(_OWORD *)(a1 + 288);
    v56 = *(_OWORD *)(a1 + 304);
    LODWORD(v55) = *(_DWORD *)(a1 + 128);
    LODWORD(v57) = 0;
    CscEaInitializeNameEntry(v50, v46, 0);
    CscEaInitializeNameEntry(v51, v47, v50);
    CscEaInitializeNameEntry(v52, v48, v50);
    CscEaInitializeNameEntry(v53, v49, v50);
    PrincipalForCurrentThread = CscEaReadEaList(*(_QWORD *)(a1 + 144), (__int64 **)v50, (__int64 *)&v41, &v40);
    if ( PrincipalForCurrentThread < 0 )
    {
      v10 = 1031;
      goto LABEL_102;
    }
    if ( *a2 == 1 )
    {
      PrincipalForCurrentThread = CscStOrphanerCreateTemporaryFile(
                                    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 64LL),
                                    (unsigned int)&UnicodeString,
                                    (unsigned int)&v38,
                                    1245592,
                                    *((_BYTE *)a2 + 8) != 0 ? 0x4000 : 0,
                                    HandleInformation);
      if ( PrincipalForCurrentThread < 0 )
      {
        v10 = 1054;
        goto LABEL_102;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids,
          &UnicodeString);
      }
    }
    else
    {
      if ( *a2 != 2 )
      {
        PrincipalForCurrentThread = -1073740768;
        v10 = 1090;
        goto LABEL_102;
      }
      v11 = (unsigned int)v40;
      v12 = v41;
      v38 = *(_QWORD *)(a1 + 152);
      *(_QWORD *)(a1 + 152) = 0;
      *(_WORD *)(a1 + 402) = 0;
      *(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL) &= ~0x1000u;
      PrincipalForCurrentThread = CscStorepLowIoSetEaFilePoster(v38, v12, v11);
      if ( PrincipalForCurrentThread < 0 )
      {
        v10 = 1082;
        goto LABEL_102;
      }
    }
    CscEaFreeFullEaBuffer(&v41);
    CscStUtFreeUniqueName(&UnicodeString);
    PrincipalForCurrentThread = CscStorepLowIoQueryFileId(v38, &v42);
    if ( PrincipalForCurrentThread < 0 )
    {
      v10 = 1105;
      goto LABEL_102;
    }
    if ( *a2 == 1 )
    {
      v13 = v42;
      if ( *(_QWORD *)(a1 + 168) )
      {
        PrincipalForCurrentThread = CscStorepLowIoOpenFileByFileIdPoster(
                                      (unsigned int)&Handle,
                                      v38,
                                      v42,
                                      2032127,
                                      7,
                                      40);
        if ( PrincipalForCurrentThread < 0 )
        {
          v10 = 1117;
          goto LABEL_102;
        }
        PrincipalForCurrentThread = CscStorepLowIoDisableImplicitTimeUpdates(Handle);
        if ( PrincipalForCurrentThread < 0 )
        {
          v10 = 1120;
          goto LABEL_102;
        }
        PrincipalForCurrentThread = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
        if ( PrincipalForCurrentThread < 0 )
        {
          v10 = 1127;
          goto LABEL_102;
        }
        ObfDereferenceObject(Object);
      }
    }
    else
    {
      v13 = v42;
    }
    if ( (*(_DWORD *)(a1 + 192) & 0x10000) != 0 )
    {
      v14 = *(__m128i *)(a1 + 192);
      v15 = *(_OWORD *)(a1 + 224);
      v58[1] = *(_OWORD *)(a1 + 208);
      v16 = *(_OWORD *)(a1 + 240);
      v58[2] = v15;
      v17 = *(_OWORD *)(a1 + 256);
      v58[0] = v14;
      LODWORD(v58[0]) = _mm_cvtsi128_si32(v14) & 0xFFFEFFFF;
      v18 = v58;
      v40 = v58;
      v58[3] = v16;
      v58[4] = v17;
    }
    else
    {
      LODWORD(v18) = 0;
      v40 = 0;
      if ( !v7 )
      {
LABEL_66:
        if ( *a2 == 1
          && (PrincipalForCurrentThread = CscEnpCopyData(
                                            *(_QWORD *)(a1 + 144),
                                            *(_QWORD *)(a1 + 136),
                                            v38,
                                            v13,
                                            *(_QWORD *)(a1 + 328)),
              PrincipalForCurrentThread < 0) )
        {
          v10 = 1180;
        }
        else
        {
          PrincipalForCurrentThread = CscStorepLowIoSetInformationFilePoster(v38, &v55, 40);
          if ( PrincipalForCurrentThread >= 0 )
          {
            if ( *a2 == 2 )
            {
              PrincipalForCurrentThread = CscEnpEnableUndoableEntry(a1, v54, v38);
              if ( PrincipalForCurrentThread < 0 )
              {
                v10 = 1208;
                goto LABEL_102;
              }
              v33 = 1;
              PrincipalForCurrentThread = CscEnpUpdateSuspendedInformationEntry(
                                            a1,
                                            *((_QWORD *)a2 + 2),
                                            *((_QWORD *)a2 + 3),
                                            a2[8]);
              if ( PrincipalForCurrentThread < 0 )
              {
                v10 = 1220;
                goto LABEL_102;
              }
            }
            CscEnpMainAcquireExclusive(*(_QWORD *)(a1 + 24));
            v19 = *(_QWORD *)(a1 + 8);
            v37 = 1;
            PrincipalForCurrentThread = CscStOrphanerAddTemporaryFile(*(_QWORD *)(v19 + 64), v44);
            if ( PrincipalForCurrentThread >= 0 )
            {
              v35 = 1;
              PrincipalForCurrentThread = CscStorepLowIoRenameFilePoster(
                                            v38,
                                            *(_QWORD *)(*(_QWORD *)(a1 + 24) + 144LL),
                                            a1 + 48,
                                            0);
              if ( PrincipalForCurrentThread >= 0 )
              {
                if ( v33 )
                {
                  v20 = CscEnpEnablePqUpdateOnUndoableEntry(a1, v54);
                  if ( v20 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        27,
                        WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids,
                        v20);
                    }
                  }
                }
                PrincipalForCurrentThread = CscEnpWriteAttributesInternal(
                                              a1,
                                              0,
                                              v13,
                                              (_DWORD)v40,
                                              0,
                                              0,
                                              0,
                                              (__int64)v7,
                                              0,
                                              0);
                if ( PrincipalForCurrentThread >= 0 )
                {
                  LOBYTE(v4) = 1;
                  v10 = 0;
                  v21 = CscStorepLowIoSetDeleteDisposition(v44, v4);
                  if ( v21
                    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      28,
                      WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids,
                      v21);
                  }
                  CscStorepLowIoClosePoster(v44, v22);
                  if ( v33 )
                  {
                    LOBYTE(v23) = 1;
                    v24 = CscEnpDisableUndoableEntry(a1, v54, v23);
                    if ( v24
                      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        29,
                        WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids,
                        v24);
                    }
                    v33 = 0;
                  }
                  *(_QWORD *)(a1 + 144) = v38;
                  *(_QWORD *)(a1 + 136) = v42;
                  if ( v7 )
                    *(_WORD *)(a1 + 400) = v36[0];
                  *(_DWORD *)(a1 + 192) &= ~0x10000u;
                  v25 = *a2 == 1;
                  v38 = 0;
                  v34 = 0;
                  v35 = 0;
                  if ( v25 && Handle )
                  {
                    CscStorepLowIoClosePoster(*(_QWORD *)(a1 + 168), v4);
                    *(_QWORD *)(a1 + 168) = Handle;
                    *(_QWORD *)(a1 + 176) = Object;
                    Handle = 0;
                    Object = 0;
                  }
                }
                else
                {
                  v34 = 1;
                  v10 = 1278;
                }
              }
              else
              {
                v10 = 1249;
              }
            }
            else
            {
              v10 = 1241;
            }
            goto LABEL_102;
          }
          v10 = 1194;
        }
LABEL_102:
        LOBYTE(v7) = v33;
        goto LABEL_103;
      }
    }
    PrincipalForCurrentThread = CscEnpWriteAttributesInternal(a1, v38, 0, (_DWORD)v18, 0, 0, 0, (__int64)v7, 0, 0);
    if ( PrincipalForCurrentThread < 0 )
    {
      v10 = 1155;
      goto LABEL_102;
    }
    goto LABEL_66;
  }
  if ( v8 == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      WPP_SF_qDqd(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        (unsigned int)WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids,
        a1,
        v5,
        *((_QWORD *)a2 + 1),
        a2[8]);
    }
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids, a1, v5);
  PrincipalForCurrentThread = -1073741811;
  v10 = 906;
LABEL_103:
  if ( *a2 == 1 && Handle )
    CscStorepLowIoClosePoster(Handle, v4);
  if ( v41 )
    CscEaFreeFullEaBuffer(&v41);
  if ( UnicodeString.Buffer )
    CscStUtFreeUniqueName(&UnicodeString);
  if ( (_BYTE)v7 )
  {
    v26 = CscEnpDisableUndoableEntry(a1, v54, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids, v26);
    }
  }
  if ( v34 )
  {
    v27 = CscStOrphanerAddTemporaryFile(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 64LL), v38);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids, v27);
    }
  }
  if ( v38 )
  {
    LOBYTE(v4) = 1;
    v28 = CscStorepLowIoSetDeleteDisposition(v38, v4);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids, v28);
    }
    CscStorepLowIoClosePoster(v38, v29);
  }
  if ( v35 )
  {
    v30 = CscStorepLowIoRenameFilePoster(*(_QWORD *)(a1 + 144), *(_QWORD *)(*(_QWORD *)(a1 + 24) + 144LL), a1 + 48, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids, v30);
    }
  }
  if ( v37 )
    CscEnpMainRelease(*(_QWORD *)(a1 + 24));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids,
      (unsigned int)PrincipalForCurrentThread,
      v10);
  return (unsigned int)PrincipalForCurrentThread;
}

```

## disassembly

```asm
0x1400593dc  mov     [rsp-8+arg_10], rbx
0x1400593e1  push    rbp
0x1400593e2  push    rsi
0x1400593e3  push    rdi
0x1400593e4  push    r12
0x1400593e6  push    r13
0x1400593e8  push    r14
0x1400593ea  push    r15
0x1400593ec  lea     rbp, [rsp-1B0h]
0x1400593f4  sub     rsp, 2B0h
0x1400593fb  mov     rax, cs:__security_cookie
0x140059402  xor     rax, rsp
0x140059405  mov     [rbp+1E0h+var_40], rax
0x14005940c  xor     esi, esi
0x14005940e  mov     [rbp+1E0h+var_228], 30002Fh
0x140059416  xorps   xmm0, xmm0
0x140059419  mov     [rsp+2E0h+var_270], rsi
0x14005941e  xor     eax, eax
0x140059420  mov     [rbp+1E0h+var_250], rsi
0x140059424  mov     [rbp+1E0h+var_A0], rax
0x14005942b  xorps   xmm1, xmm1
0x14005942e  lea     rax, aC8a05bc03fa849; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x140059435  mov     [rsp+2E0h+var_27C], si
0x14005943a  mov     [rbp+1E0h+var_220], rax
0x14005943e  lea     r8d, [rsi+50h]; Size
0x140059442  lea     rax, aC8a05bc03fa849_3; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x140059449  mov     [rsp+2E0h+var_27E], sil
0x14005944e  mov     [rbp+1E0h+var_210], rax
0x140059452  mov     r14, rdx
0x140059455  lea     rax, aC8a05bc03fa849_4; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x14005945c  mov     [rsp+2E0h+var_27F], sil
0x140059461  mov     [rbp+1E0h+var_200], rax
0x140059465  mov     rdi, rcx
0x140059468  lea     rax, aC8a05bc03fa849_5; "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Cs"...
0x14005946f  mov     [rbp+1E0h+var_218], 320031h
0x140059477  xor     edx, edx; Val
0x140059479  mov     [rbp+1E0h+var_1F0], rax
0x14005947d  lea     rcx, [rbp+1E0h+var_90]; void *
0x140059484  mov     [rbp+1E0h+var_208], 340033h
0x14005948c  movups  [rbp+1E0h+var_C0], xmm0
0x140059493  mov     [rbp+1E0h+var_1F8], 2E002Dh
0x14005949b  movups  [rbp+1E0h+var_B0], xmm0
0x1400594a2  mov     [rbp+1E0h+var_258], rsi
0x1400594a6  movups  xmmword ptr [rbp+1E0h+UnicodeString.Length], xmm0
0x1400594aa  mov     dword ptr [rbp+1E0h+var_260], esi
0x1400594ad  movups  [rbp+1E0h+var_1E8], xmm0
0x1400594b1  mov     [rsp+2E0h+var_278], sil
0x1400594b6  movups  [rbp+1E0h+var_1D8], xmm0
0x1400594ba  movups  [rbp+1E0h+var_1C8], xmm1
0x1400594be  movups  [rbp+1E0h+var_1B8], xmm1
0x1400594c2  movups  [rbp+1E0h+var_1A8], xmm0
0x1400594c6  movups  [rbp+1E0h+var_198], xmm0
0x1400594ca  movups  [rbp+1E0h+var_188], xmm1
0x1400594ce  movups  [rbp+1E0h+var_178], xmm1
0x1400594d2  call    memset
0x1400594d7  xor     edx, edx; Val
0x1400594d9  lea     rcx, [rbp+1E0h+var_160]; void *
0x1400594e0  mov     r8d, 0A0h; Size
0x1400594e6  call    memset
0x1400594eb  mov     r8d, [r14]
0x1400594ee  lea     r12, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids
0x1400594f5  mov     rax, [rdi+90h]
0x1400594fc  mov     ecx, r8d
0x1400594ff  mov     [rbp+1E0h+var_240], rax
0x140059503  mov     r13b, sil
0x140059506  mov     [rsp+2E0h+var_280], sil
0x14005950b  mov     [rsp+2E0h+Handle], rsi
0x140059510  mov     [rbp+1E0h+var_248], rsi
0x140059514  sub     ecx, 1
0x140059517  jz      loc_1400595B3
0x14005951d  cmp     ecx, 1
0x140059520  jz      short loc_14005956B
0x140059522  mov     rcx, cs:WPP_GLOBAL_Control
0x140059529  lea     r15, WPP_GLOBAL_Control
0x140059530  lea     r12, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids
0x140059537  cmp     rcx, r15
0x14005953a  jz      short loc_14005955C
0x14005953c  test    dword ptr [rcx+2Ch], 20000h
0x140059543  jz      short loc_14005955C
0x140059545  mov     rcx, [rcx+18h]
0x140059549  lea     edx, [rsi+19h]
0x14005954c  mov     dword ptr [rsp+2E0h+Object], r8d
0x140059551  mov     r9, rdi
0x140059554  mov     r8, r12
0x140059557  call    WPP_SF_qD
0x14005955c  mov     ebx, 0C000000Dh
0x140059561  mov     esi, 38Ah
0x140059566  jmp     loc_140059D1C
0x14005956b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059572  lea     r15, WPP_GLOBAL_Control
0x140059579  cmp     rcx, r15
0x14005957c  jz      short loc_1400595F0
0x14005957e  test    dword ptr [rcx+2Ch], 20000h
0x140059585  jz      short loc_1400595F0
0x140059587  mov     eax, [r14+20h]
0x14005958b  mov     edx, 18h
0x140059590  mov     rcx, [rcx+18h]
0x140059594  mov     r9, rdi
0x140059597  mov     dword ptr [rsp+2E0h+var_2B0], eax
0x14005959b  mov     rax, [r14+8]
0x14005959f  mov     [rsp+2E0h+HandleInformation], rax
0x1400595a4  mov     dword ptr [rsp+2E0h+Object], r8d
0x1400595a9  mov     r8, r12
0x1400595ac  call    WPP_SF_qDqd
0x1400595b1  jmp     short loc_1400595F0
0x1400595b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400595ba  lea     r15, WPP_GLOBAL_Control
0x1400595c1  cmp     rcx, r15
0x1400595c4  jz      short loc_1400595F0
0x1400595c6  test    dword ptr [rcx+2Ch], 20000h
0x1400595cd  jz      short loc_1400595F0
0x1400595cf  mov     al, [r14+8]
0x1400595d3  mov     edx, 17h
0x1400595d8  mov     rcx, [rcx+18h]
0x1400595dc  mov     r9, rdi
0x1400595df  mov     byte ptr [rsp+2E0h+HandleInformation], al
0x1400595e3  mov     dword ptr [rsp+2E0h+Object], r8d
0x1400595e8  mov     r8, r12
0x1400595eb  call    WPP_SF_qDc
0x1400595f0  mov     eax, [rdi+150h]
0x1400595f6  test    al, 10h
0x1400595f8  jz      short loc_140059609
0x1400595fa  mov     ebx, 0C000000Dh
0x1400595ff  mov     esi, 393h
0x140059604  jmp     loc_140059D1C
0x140059609  mov     edx, [r14]
0x14005960c  mov     r13, rsi
0x14005960f  cmp     edx, 2
0x140059612  jnz     short loc_14005966C
0x140059614  mov     rax, [r14+8]
0x140059618  test    dword ptr [rax+10h], 1000h
0x14005961f  jnz     short loc_140059630
0x140059621  mov     ebx, 0C000000Dh
0x140059626  mov     esi, 39Fh
0x14005962b  jmp     loc_140059D1C
0x140059630  cmp     [rdi+192h], si
0x140059637  jz      short loc_140059667
0x140059639  lea     rdx, [rsp+2E0h+var_27C]
0x14005963e  mov     rcx, rdi
0x140059641  call    CscEnpQueryPrincipalForCurrentThread
0x140059646  mov     ebx, eax
0x140059648  test    eax, eax
0x14005964a  jns     short loc_140059656
0x14005964c  mov     esi, 3AAh
0x140059651  jmp     loc_140059D1C
0x140059656  movzx   eax, [rsp+2E0h+var_27C]
0x14005965b  cmp     [rdi+192h], ax
0x140059662  jnz     short loc_140059689
0x140059664  mov     edx, [r14]
0x140059667  lea     r13, [rsp+2E0h+var_27C]
0x14005966c  cmp     edx, 1
0x14005966f  jnz     short loc_1400596B0
0x140059671  mov     rcx, rdi
0x140059674  call    CscDiffTransferRemoveState
0x140059679  mov     ebx, eax
0x14005967b  test    eax, eax
0x14005967d  jns     short loc_140059698
0x14005967f  mov     esi, 3C2h
0x140059684  jmp     loc_140059D17
0x140059689  mov     ebx, 0C000000Dh
0x14005968e  mov     esi, 3B3h
0x140059693  jmp     loc_140059D1C
0x140059698  mov     rcx, rdi
0x14005969b  call    CscDiffTransferCloseHandle
0x1400596a0  mov     ebx, eax
0x1400596a2  test    eax, eax
0x1400596a4  jns     short loc_1400596C7
0x1400596a6  mov     esi, 3C6h
0x1400596ab  jmp     loc_140059D17
0x1400596b0  cmp     [rdi+0A4h], esi
0x1400596b6  jz      short loc_1400596C7
0x1400596b8  mov     ebx, 0C0000022h
0x1400596bd  mov     esi, 3D2h
0x1400596c2  jmp     loc_140059D17
0x1400596c7  cmp     dword ptr [r14], 1
0x1400596cb  jnz     short loc_1400596F5
0x1400596cd  cmp     [r14+8], sil
0x1400596d1  jz      short loc_1400596F0
0x1400596d3  lea     rdx, [rsp+2E0h+var_27C]
0x1400596d8  mov     rcx, rdi
0x1400596db  call    CscEnpQueryPrincipalForCurrentThread
0x1400596e0  mov     ebx, eax
0x1400596e2  test    eax, eax
0x1400596e4  jns     short loc_1400596F0
0x1400596e6  mov     esi, 3E0h
0x1400596eb  jmp     loc_140059D17
0x1400596f0  lea     r13, [rsp+2E0h+var_27C]
0x1400596f5  mov     rax, [rdi+120h]
0x1400596fc  lea     rdx, [rbp+1E0h+var_228]
0x140059700  mov     qword ptr [rbp+1E0h+var_C0], rax
0x140059707  lea     rcx, [rbp+1E0h+var_1E8]
0x14005970b  mov     rax, [rdi+128h]
0x140059712  xor     r8d, r8d
0x140059715  mov     qword ptr [rbp+1E0h+var_C0+8], rax
0x14005971c  mov     rax, [rdi+130h]
0x140059723  mov     qword ptr [rbp+1E0h+var_B0], rax
0x14005972a  mov     rax, [rdi+138h]
0x140059731  mov     qword ptr [rbp+1E0h+var_B0+8], rax
0x140059738  mov     eax, [rdi+80h]
0x14005973e  mov     dword ptr [rbp+1E0h+var_C0], eax
0x140059744  mov     dword ptr [rbp+1E0h+var_A0], esi
0x14005974a  call    CscEaInitializeNameEntry
0x14005974f  lea     rcx, [rbp+1E0h+var_1C8]
0x140059753  lea     r8, [rbp+1E0h+var_1E8]
0x140059757  lea     rdx, [rbp+1E0h+var_218]
0x14005975b  call    CscEaInitializeNameEntry
0x140059760  lea     rcx, [rbp+1E0h+var_1A8]
0x140059764  lea     r8, [rbp+1E0h+var_1E8]
0x140059768  lea     rdx, [rbp+1E0h+var_208]
0x14005976c  call    CscEaInitializeNameEntry
0x140059771  lea     rcx, [rbp+1E0h+var_188]
0x140059775  lea     r8, [rbp+1E0h+var_1E8]
0x140059779  lea     rdx, [rbp+1E0h+var_1F8]
0x14005977d  call    CscEaInitializeNameEntry
0x140059782  mov     rcx, [rdi+90h]
0x140059789  lea     r9, [rbp+1E0h+var_260]
0x14005978d  lea     r8, [rbp+1E0h+var_258]
0x140059791  lea     rdx, [rbp+1E0h+var_1E8]
0x140059795  call    CscEaReadEaList
0x14005979a  mov     ebx, eax
0x14005979c  test    eax, eax
0x14005979e  jns     short loc_1400597AA
0x1400597a0  mov     esi, 407h
0x1400597a5  jmp     loc_140059D17
0x1400597aa  mov     ecx, [r14]
0x1400597ad  sub     ecx, 1
0x1400597b0  jz      short loc_14005980F
0x1400597b2  cmp     ecx, 1
0x1400597b5  jz      short loc_1400597C6
0x1400597b7  mov     ebx, 0C0000420h
0x1400597bc  mov     esi, 442h
0x1400597c1  jmp     loc_140059D17
0x1400597c6  mov     rax, [rdi+98h]
0x1400597cd  mov     r8d, dword ptr [rbp+1E0h+var_260]
0x1400597d1  mov     rdx, [rbp+1E0h+var_258]
0x1400597d5  mov     [rsp+2E0h+var_270], rax
0x1400597da  mov     [rdi+98h], rsi
0x1400597e1  mov     [rdi+192h], si
0x1400597e8  mov     rax, [r14+8]
0x1400597ec  btr     dword ptr [rax+10h], 0Ch
0x1400597f1  mov     rcx, [rsp+2E0h+var_270]
0x1400597f6  call    CscStorepLowIoSetEaFilePoster
0x1400597fb  mov     ebx, eax
0x1400597fd  test    eax, eax
0x1400597ff  jns     loc_140059898
0x140059805  mov     esi, 43Ah
0x14005980a  jmp     loc_140059D17
0x14005980f  mov     r10, [rdi+8]
0x140059813  lea     r8, [rsp+2E0h+var_270]
0x140059818  mov     al, [r14+8]
0x14005981c  lea     rdx, [rbp+1E0h+UnicodeString]
0x140059820  neg     al
0x140059822  mov     r9d, 130198h
0x140059828  mov     rax, [r10+18h]
0x14005982c  sbb     ecx, ecx
0x14005982e  mov     [rsp+2E0h+var_290], rax
0x140059833  and     ecx, 4000h
0x140059839  mov     eax, dword ptr [rbp+1E0h+var_260]
0x14005983c  mov     dword ptr [rsp+2E0h+var_298], eax
0x140059840  mov     rax, [rbp+1E0h+var_258]
0x140059844  mov     [rsp+2E0h+var_2A0], rax
0x140059849  mov     dword ptr [rsp+2E0h+var_2A8], 60h ; '`'
0x140059851  mov     dword ptr [rsp+2E0h+Object], ecx
0x140059855  mov     rcx, [r10+40h]
0x140059859  call    CscStOrphanerCreateTemporaryFile
0x14005985e  mov     ebx, eax
0x140059860  test    eax, eax
0x140059862  jns     short loc_14005986E
0x140059864  mov     esi, 41Eh
0x140059869  jmp     loc_140059D17
0x14005986e  mov     rcx, cs:WPP_GLOBAL_Control
0x140059875  cmp     rcx, r15
0x140059878  jz      short loc_140059898
0x14005987a  test    dword ptr [rcx+2Ch], 40000h
0x140059881  jz      short loc_140059898
0x140059883  mov     rcx, [rcx+18h]
0x140059887  lea     r9, [rbp+1E0h+UnicodeString]
0x14005988b  mov     edx, 1Ah
0x140059890  mov     r8, r12
0x140059893  call    WPP_SF_Z
0x140059898  lea     rcx, [rbp+1E0h+var_258]
0x14005989c  call    CscEaFreeFullEaBuffer
0x1400598a1  lea     rcx, [rbp+1E0h+UnicodeString]; UnicodeString
0x1400598a5  call    CscStUtFreeUniqueName
0x1400598aa  mov     rcx, [rsp+2E0h+var_270]
0x1400598af  lea     rdx, [rbp+1E0h+var_250]
0x1400598b3  call    CscStorepLowIoQueryFileId
0x1400598b8  mov     ebx, eax
0x1400598ba  test    eax, eax
0x1400598bc  jns     short loc_1400598C8
0x1400598be  mov     esi, 451h
0x1400598c3  jmp     loc_140059D17
0x1400598c8  cmp     dword ptr [r14], 1
0x1400598cc  jnz     loc_140059989
0x1400598d2  cmp     [rdi+0A8h], rsi
0x1400598d9  mov     rsi, [rbp+1E0h+var_250]
0x1400598dd  jz      loc_14005998D
0x1400598e3  mov     rdx, [rsp+2E0h+var_270]
0x1400598e8  lea     rcx, [rsp+2E0h+Handle]
0x1400598ed  mov     dword ptr [rsp+2E0h+HandleInformation], 28h ; '('
  ... truncated ...
```
