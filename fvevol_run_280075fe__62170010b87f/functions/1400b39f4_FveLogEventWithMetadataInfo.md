# FveLogEventWithMetadataInfo

- ea: `0x1400b39f4`
- end: `0x1400b3ee9`
- name: `FveLogEventWithMetadataInfo`
- size: `1269`
- prototype: ``
- caller_count: `8`
- callee_count: `8`
- tags: ``

## callers

- `0x14000e78c`
- `0x140069c0c`
- `0x1400a6ed8`
- `0x1400aa9c4`
- `0x1400afe88`
- `0x1400b09d8`
- `0x1400de284`
- `0x1400de86c`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x14000110c`
- `0x140008dc0`
- `0x140008e44`
- `0x1400218c0`
- `0x140021d00`
- `0x1400b39f4`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b3b09`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b3b09`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b3b26`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b3b26`
- `ntoskrnl!EtwWrite` at `0x1400b3c66`
- `ntoskrnl!EtwWrite` at `0x1400b3c66`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3e81`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3e81`

## pseudocode

```c
__int64 FveLogEventWithMetadataInfo(__int64 a1, const EVENT_DESCRIPTOR *a2, int a3, ...)
{
  unsigned int v5; // ebx
  __int64 v6; // rsi
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  NTSTATUS v9; // eax
  __int16 v11; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  int Id; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[7]; // [rsp+90h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+100h] [rbp+0h] BYREF
  char v24[16]; // [rsp+120h] [rbp+20h] BYREF
  int *v25; // [rsp+130h] [rbp+30h]
  __int64 v26; // [rsp+138h] [rbp+38h]
  int *p_Id; // [rsp+140h] [rbp+40h]
  __int64 v28; // [rsp+148h] [rbp+48h]
  __int64 *v29; // [rsp+150h] [rbp+50h]
  __int64 v30; // [rsp+158h] [rbp+58h]
  __int64 *v31; // [rsp+160h] [rbp+60h]
  __int64 v32; // [rsp+168h] [rbp+68h]
  __int64 *v33; // [rsp+170h] [rbp+70h]
  __int64 v34; // [rsp+178h] [rbp+78h]
  __int64 *v35; // [rsp+180h] [rbp+80h]
  __int64 v36; // [rsp+188h] [rbp+88h]
  __int64 *v37; // [rsp+190h] [rbp+90h]
  __int64 v38; // [rsp+198h] [rbp+98h]
  __int64 *v39; // [rsp+1A0h] [rbp+A0h]
  __int64 v40; // [rsp+1A8h] [rbp+A8h]
  __int64 *v41; // [rsp+1B0h] [rbp+B0h]
  __int64 v42; // [rsp+1B8h] [rbp+B8h]
  int v43; // [rsp+230h] [rbp+130h] BYREF
  __int64 v44; // [rsp+238h] [rbp+138h] BYREF
  va_list va; // [rsp+238h] [rbp+138h]
  __int64 v46; // [rsp+240h] [rbp+140h] BYREF
  va_list va1; // [rsp+240h] [rbp+140h]
  __int64 v48; // [rsp+248h] [rbp+148h] BYREF
  va_list va2; // [rsp+248h] [rbp+148h]
  __int64 v50; // [rsp+250h] [rbp+150h] BYREF
  va_list va3; // [rsp+250h] [rbp+150h]
  __int64 v52; // [rsp+258h] [rbp+158h] BYREF
  va_list va4; // [rsp+258h] [rbp+158h]
  __int64 v54; // [rsp+260h] [rbp+160h]
  __int64 v55; // [rsp+268h] [rbp+168h]
  __int64 v56; // [rsp+270h] [rbp+170h]
  va_list va5; // [rsp+278h] [rbp+178h] BYREF

  va_start(va5, a3);
  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v44 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v46 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v48 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v50 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v52 = va_arg(va5, _QWORD);
  v54 = va_arg(va5, _QWORD);
  v55 = va_arg(va5, _QWORD);
  v56 = va_arg(va5, _QWORD);
  v43 = a3;
  DosName = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids);
  }
  *(_DWORD *)&DosName.Length = 0x20000;
  v11 = 0;
  DosName.Buffer = (wchar_t *)&v11;
  memset(UserData, 0, sizeof(UserData));
  if ( a2 )
  {
    if ( a1 && (v6 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL)) != 0 && *(_QWORD *)(v6 + 88) )
    {
      v5 = 0;
      if ( !KeAreAllApcsDisabled() )
      {
        v5 = IoVolumeDeviceToDosName(*(PVOID *)(*(_QWORD *)(a1 + 64) + 120LL), &DosName);
        if ( (v5 & 0x80000000) != 0 )
        {
          *(_DWORD *)&DosName.Length = 0x20000;
          DosName.Buffer = (wchar_t *)&v11;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids, v5);
          }
        }
      }
      if ( !(_BYTE)v56 || v43 < 0 )
      {
        *(_QWORD *)&UserData[0].Size = 4;
        UserData[0].Ptr = (ULONGLONG)&v43;
        UserData[1].Ptr = (ULONGLONG)DosName.Buffer;
        UserData[1].Size = DosName.MaximumLength;
        va_copy((va_list)&UserData[2], va);
        va_copy((va_list)&UserData[3], va1);
        va_copy((va_list)&UserData[4], va2);
        va_copy((va_list)&UserData[5], va3);
        va_copy((va_list)&UserData[6], va4);
        UserData[1].Reserved = 0;
        *(_QWORD *)&UserData[2].Size = 8;
        *(_QWORD *)&UserData[3].Size = 8;
        *(_QWORD *)&UserData[4].Size = 8;
        *(_QWORD *)&UserData[5].Size = 8;
        *(_QWORD *)&UserData[6].Size = 8;
        v9 = EtwWrite(*(_QWORD *)(v6 + 88), a2, 0, 7u, UserData);
        v5 = v9;
        if ( v9 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids,
            (unsigned int)v9);
        }
        goto LABEL_35;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
LABEL_35:
        if ( ((_BYTE)v55 == 1 || v43 < 0)
          && (unsigned int)dword_140045040 > 4
          && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
        {
          tlgCreate1Sz_wchar_t(v24, DosName.Buffer);
          v25 = &v13;
          Id = a2->Id;
          v13 = v43;
          p_Id = &Id;
          v15 = v44;
          v29 = &v15;
          v16 = v46;
          v31 = &v16;
          v17 = v48;
          v33 = &v17;
          v18 = v50;
          v35 = &v18;
          v19 = v52;
          v37 = &v19;
          v20 = v54;
          v39 = &v20;
          v41 = &v21;
          v26 = 4;
          v28 = 4;
          v30 = 8;
          v32 = 8;
          v34 = 8;
          v36 = 8;
          v38 = 8;
          v40 = 8;
          v21 = 0x1000000;
          v42 = 8;
          tlgWriteTransfer_EtwWriteTransfer(
            (__int64)&dword_140045040,
            (unsigned __int8 *)&dword_14003C16C,
            0,
            0,
            0xCu,
            &v23);
        }
        goto LABEL_40;
      }
      v8 = 14;
    }
    else
    {
      v5 = -1073741436;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_35;
      }
      v8 = 12;
    }
    WPP_SF_(v7->AttachedDevice, v8, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids);
    goto LABEL_35;
  }
  v5 = -1073741811;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v5;
  if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u) && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids);
LABEL_40:
    if ( (__int16 *)DosName.Buffer != &v11 )
    {
      ExFreePoolWithTag(DosName.Buffer, 0);
      DosName.Buffer = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1400b39f4  mov     [rsp-8+arg_18], r9
0x1400b39f9  mov     [rsp-8+arg_10], r8d
0x1400b39fe  push    rbp
0x1400b39ff  push    rbx
0x1400b3a00  push    rsi
0x1400b3a01  push    rdi
0x1400b3a02  push    r12
0x1400b3a04  push    r13
0x1400b3a06  push    r14
0x1400b3a08  push    r15
0x1400b3a0a  lea     rbp, [rsp-0D8h]
0x1400b3a12  sub     rsp, 1D8h
0x1400b3a19  mov     rax, cs:__security_cookie
0x1400b3a20  xor     rax, rsp
0x1400b3a23  mov     [rbp+110h+var_50], rax
0x1400b3a2a  xorps   xmm0, xmm0
0x1400b3a2d  mov     r14, rdx
0x1400b3a30  movups  xmmword ptr [rsp+210h+DosName.Length], xmm0
0x1400b3a35  mov     rdi, rcx
0x1400b3a38  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3a3f  lea     r13, WPP_GLOBAL_Control
0x1400b3a46  cmp     rcx, r13
0x1400b3a49  jz      short loc_1400B3A6D
0x1400b3a4b  bt      dword ptr [rcx+2Ch], 11h
0x1400b3a50  jnb     short loc_1400B3A6D
0x1400b3a52  cmp     byte ptr [rcx+29h], 5
0x1400b3a56  jb      short loc_1400B3A6D
0x1400b3a58  mov     rcx, [rcx+18h]
0x1400b3a5c  lea     r8, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids
0x1400b3a63  mov     edx, 0Ah
0x1400b3a68  call    WPP_SF_
0x1400b3a6d  xor     r15d, r15d
0x1400b3a70  mov     dword ptr [rsp+210h+DosName.Length], 20000h
0x1400b3a78  lea     rax, [rsp+210h+var_1E0]
0x1400b3a7d  mov     [rsp+210h+var_1E0], r15w
0x1400b3a83  xor     edx, edx; Val
0x1400b3a85  mov     [rsp+210h+DosName.Buffer], rax
0x1400b3a8a  lea     rcx, [rbp+110h+var_180]; void *
0x1400b3a8e  lea     r8d, [r15+70h]; Size
0x1400b3a92  lea     esi, [r15+2]
0x1400b3a96  call    memset
0x1400b3a9b  test    r14, r14
0x1400b3a9e  jnz     short loc_1400B3AE2
0x1400b3aa0  mov     ebx, 0C000000Dh
0x1400b3aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3aac  cmp     rcx, r13
0x1400b3aaf  jz      loc_1400B3EC3
0x1400b3ab5  bt      dword ptr [rcx+2Ch], 11h
0x1400b3aba  jnb     loc_1400B3E92
0x1400b3ac0  cmp     [rcx+29h], sil
0x1400b3ac4  jb      loc_1400B3E92
0x1400b3aca  mov     rcx, [rcx+18h]
0x1400b3ace  lea     edx, [rsi+9]
0x1400b3ad1  lea     r8, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids
0x1400b3ad8  call    WPP_SF_
0x1400b3add  jmp     loc_1400B3E70
0x1400b3ae2  test    rdi, rdi
0x1400b3ae5  jz      loc_1400B3CB0
0x1400b3aeb  mov     rax, [rdi+40h]
0x1400b3aef  mov     rsi, [rax+8]
0x1400b3af3  test    rsi, rsi
0x1400b3af6  jz      loc_1400B3CAB
0x1400b3afc  cmp     [rsi+58h], r15
0x1400b3b00  jz      loc_1400B3CAB
0x1400b3b06  mov     ebx, r15d
0x1400b3b09  call    cs:__imp_KeAreAllApcsDisabled
0x1400b3b10  nop     dword ptr [rax+rax+00h]
0x1400b3b15  test    al, al
0x1400b3b17  jnz     short loc_1400B3B80
0x1400b3b19  mov     rcx, [rdi+40h]
0x1400b3b1d  lea     rdx, [rsp+210h+DosName]; DosName
0x1400b3b22  mov     rcx, [rcx+78h]; VolumeDeviceObject
0x1400b3b26  call    cs:__imp_IoVolumeDeviceToDosName
0x1400b3b2d  nop     dword ptr [rax+rax+00h]
0x1400b3b32  mov     ebx, eax
0x1400b3b34  mov     edi, 2
0x1400b3b39  test    eax, eax
0x1400b3b3b  jns     short loc_1400B3B85
0x1400b3b3d  lea     rax, [rsp+210h+var_1E0]
0x1400b3b42  mov     dword ptr [rsp+210h+DosName.Length], 20000h
0x1400b3b4a  mov     [rsp+210h+DosName.Buffer], rax
0x1400b3b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3b56  cmp     rcx, r13
0x1400b3b59  jz      short loc_1400B3B85
0x1400b3b5b  bt      dword ptr [rcx+2Ch], 11h
0x1400b3b60  jnb     short loc_1400B3B85
0x1400b3b62  cmp     [rcx+29h], dil
0x1400b3b66  jb      short loc_1400B3B85
0x1400b3b68  mov     rcx, [rcx+18h]
0x1400b3b6c  lea     edx, [rdi+0Bh]
0x1400b3b6f  mov     r9d, ebx
0x1400b3b72  lea     r8, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids
0x1400b3b79  call    WPP_SF_d
0x1400b3b7e  jmp     short loc_1400B3B85
0x1400b3b80  mov     edi, 2
0x1400b3b85  cmp     byte ptr [rbp+110h+arg_50], r15b
0x1400b3b8c  jz      short loc_1400B3BC6
0x1400b3b8e  cmp     [rbp+110h+arg_10], r15d
0x1400b3b95  jl      short loc_1400B3BC6
0x1400b3b97  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3b9e  cmp     rcx, r13
0x1400b3ba1  jz      loc_1400B3CE3
0x1400b3ba7  bt      dword ptr [rcx+2Ch], 11h
0x1400b3bac  jnb     loc_1400B3CE3
0x1400b3bb2  cmp     byte ptr [rcx+29h], 5
0x1400b3bb6  jb      loc_1400B3CE3
0x1400b3bbc  mov     edx, 0Eh
0x1400b3bc1  jmp     loc_1400B3CD3
0x1400b3bc6  lea     rax, [rbp+110h+arg_10]
0x1400b3bcd  mov     qword ptr [rbp+110h+var_180.Size], 4
0x1400b3bd5  mov     [rbp+110h+var_180.Ptr], rax
0x1400b3bd9  mov     r9d, 7; UserDataCount
0x1400b3bdf  mov     rax, [rsp+210h+DosName.Buffer]
0x1400b3be4  xor     r8d, r8d; ActivityId
0x1400b3be7  mov     [rbp+110h+var_170], rax
0x1400b3beb  mov     rdx, r14; EventDescriptor
0x1400b3bee  movzx   eax, [rsp+210h+DosName.MaximumLength]
0x1400b3bf3  mov     [rbp+110h+var_168], eax
0x1400b3bf6  lea     rax, [rbp+110h+arg_18]
0x1400b3bfd  mov     [rbp+110h+var_160], rax
0x1400b3c01  lea     rax, [rbp+110h+arg_20]
0x1400b3c08  mov     [rbp+110h+var_150], rax
0x1400b3c0c  lea     rax, [rbp+110h+arg_28]
0x1400b3c13  mov     [rbp+110h+var_140], rax
0x1400b3c17  lea     rax, [rbp+110h+arg_30]
0x1400b3c1e  mov     [rbp+110h+var_130], rax
0x1400b3c22  lea     rax, [rbp+110h+arg_38]
0x1400b3c29  mov     [rbp+110h+var_120], rax
0x1400b3c2d  lea     rax, [rbp+110h+var_180]
0x1400b3c31  mov     [rbp+110h+var_164], r15d
0x1400b3c35  mov     [rbp+110h+var_158], 8
0x1400b3c3d  mov     [rbp+110h+var_148], 8
0x1400b3c45  mov     [rbp+110h+var_138], 8
0x1400b3c4d  mov     [rbp+110h+var_128], 8
0x1400b3c55  mov     [rbp+110h+var_118], 8
0x1400b3c5d  mov     rcx, [rsi+58h]; RegHandle
0x1400b3c61  mov     [rsp+210h+UserData], rax; UserData
0x1400b3c66  call    cs:__imp_EtwWrite
0x1400b3c6d  nop     dword ptr [rax+rax+00h]
0x1400b3c72  mov     ebx, eax
0x1400b3c74  test    eax, eax
0x1400b3c76  jns     short loc_1400B3CE3
0x1400b3c78  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3c7f  cmp     rcx, r13
0x1400b3c82  jz      short loc_1400B3CE3
0x1400b3c84  bt      dword ptr [rcx+2Ch], 11h
0x1400b3c89  jnb     short loc_1400B3CE3
0x1400b3c8b  cmp     [rcx+29h], dil
0x1400b3c8f  jb      short loc_1400B3CE3
0x1400b3c91  mov     rcx, [rcx+18h]
0x1400b3c95  lea     r8, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids
0x1400b3c9c  mov     edx, 0Fh
0x1400b3ca1  mov     r9d, eax
0x1400b3ca4  call    WPP_SF_d
0x1400b3ca9  jmp     short loc_1400B3CE3
0x1400b3cab  mov     esi, 2
0x1400b3cb0  mov     ebx, 0C0000184h
0x1400b3cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3cbc  cmp     rcx, r13
0x1400b3cbf  jz      short loc_1400B3CE3
0x1400b3cc1  bt      dword ptr [rcx+2Ch], 11h
0x1400b3cc6  jnb     short loc_1400B3CE3
0x1400b3cc8  cmp     [rcx+29h], sil
0x1400b3ccc  jb      short loc_1400B3CE3
0x1400b3cce  mov     edx, 0Ch
0x1400b3cd3  mov     rcx, [rcx+18h]
0x1400b3cd7  lea     r8, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids
0x1400b3cde  call    WPP_SF_
0x1400b3ce3  cmp     byte ptr [rbp+110h+arg_48], 1
0x1400b3cea  jz      short loc_1400B3CF9
0x1400b3cec  cmp     [rbp+110h+arg_10], r15d
0x1400b3cf3  jge     loc_1400B3E70
0x1400b3cf9  mov     eax, cs:dword_140045040
0x1400b3cff  cmp     eax, 4
0x1400b3d02  jbe     loc_1400B3E70
0x1400b3d08  mov     rdx, 400000000000h
0x1400b3d12  lea     rcx, dword_140045040
0x1400b3d19  call    _tlgKeywordOn
0x1400b3d1e  test    al, al
0x1400b3d20  jz      loc_1400B3E70
0x1400b3d26  mov     rdx, [rsp+210h+DosName.Buffer]
0x1400b3d2b  lea     rcx, [rbp+110h+var_F0]
0x1400b3d2f  call    _tlgCreate1Sz_wchar_t
0x1400b3d34  mov     ecx, [rbp+110h+arg_10]
0x1400b3d3a  lea     rax, [rsp+210h+var_1C8]
0x1400b3d3f  mov     [rbp+110h+var_E0], rax
0x1400b3d43  lea     rdx, dword_14003C16C
0x1400b3d4a  movzx   eax, word ptr [r14]
0x1400b3d4e  xor     r9d, r9d
0x1400b3d51  mov     [rsp+210h+var_1C4], eax
0x1400b3d55  xor     r8d, r8d
0x1400b3d58  lea     rax, [rsp+210h+var_1C4]
0x1400b3d5d  mov     [rsp+210h+var_1C8], ecx
0x1400b3d61  mov     [rbp+110h+var_D0], rax
0x1400b3d65  lea     rcx, dword_140045040
0x1400b3d6c  mov     rax, [rbp+110h+arg_18]
0x1400b3d73  mov     [rsp+210h+var_1C0], rax
0x1400b3d78  lea     rax, [rsp+210h+var_1C0]
0x1400b3d7d  mov     [rbp+110h+var_C0], rax
0x1400b3d81  mov     rax, [rbp+110h+arg_20]
0x1400b3d88  mov     [rsp+210h+var_1B8], rax
0x1400b3d8d  lea     rax, [rsp+210h+var_1B8]
0x1400b3d92  mov     [rbp+110h+var_B0], rax
0x1400b3d96  mov     rax, [rbp+110h+arg_28]
0x1400b3d9d  mov     [rsp+210h+var_1B0], rax
0x1400b3da2  lea     rax, [rsp+210h+var_1B0]
0x1400b3da7  mov     [rbp+110h+var_A0], rax
0x1400b3dab  mov     rax, [rbp+110h+arg_30]
0x1400b3db2  mov     [rsp+210h+var_1A8], rax
0x1400b3db7  lea     rax, [rsp+210h+var_1A8]
0x1400b3dbc  mov     [rbp+110h+var_90], rax
0x1400b3dc3  mov     rax, [rbp+110h+arg_38]
0x1400b3dca  mov     [rsp+210h+var_1A0], rax
0x1400b3dcf  lea     rax, [rsp+210h+var_1A0]
0x1400b3dd4  mov     [rbp+110h+var_80], rax
0x1400b3ddb  mov     rax, [rbp+110h+arg_40]
0x1400b3de2  mov     [rsp+210h+var_198], rax
0x1400b3de7  lea     rax, [rsp+210h+var_198]
0x1400b3dec  mov     [rbp+110h+var_70], rax
0x1400b3df3  lea     rax, [rbp+110h+var_190]
0x1400b3df7  mov     [rbp+110h+var_60], rax
0x1400b3dfe  lea     rax, [rbp+110h+var_110]
0x1400b3e02  mov     [rsp+210h+var_1E8], rax
0x1400b3e07  mov     dword ptr [rsp+210h+UserData], 0Ch
0x1400b3e0f  mov     [rbp+110h+var_D8], 4
0x1400b3e17  mov     [rbp+110h+var_C8], 4
0x1400b3e1f  mov     [rbp+110h+var_B8], 8
0x1400b3e27  mov     [rbp+110h+var_A8], 8
0x1400b3e2f  mov     [rbp+110h+var_98], 8
0x1400b3e37  mov     [rbp+110h+var_88], 8
0x1400b3e42  mov     [rbp+110h+var_78], 8
0x1400b3e4d  mov     [rbp+110h+var_68], 8
0x1400b3e58  mov     [rbp+110h+var_190], 1000000h
0x1400b3e60  mov     [rbp+110h+var_58], 8
0x1400b3e6b  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b3e70  mov     rcx, [rsp+210h+DosName.Buffer]; P
0x1400b3e75  lea     rax, [rsp+210h+var_1E0]
0x1400b3e7a  cmp     rcx, rax
0x1400b3e7d  jz      short loc_1400B3E92
0x1400b3e7f  xor     edx, edx; Tag
0x1400b3e81  call    cs:__imp_ExFreePoolWithTag
0x1400b3e88  nop     dword ptr [rax+rax+00h]
0x1400b3e8d  mov     [rsp+210h+DosName.Buffer], r15
0x1400b3e92  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3e99  cmp     rcx, r13
0x1400b3e9c  jz      short loc_1400B3EC3
0x1400b3e9e  bt      dword ptr [rcx+2Ch], 11h
0x1400b3ea3  jnb     short loc_1400B3EC3
0x1400b3ea5  cmp     byte ptr [rcx+29h], 5
0x1400b3ea9  jb      short loc_1400B3EC3
0x1400b3eab  mov     rcx, [rcx+18h]
0x1400b3eaf  lea     r8, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids
0x1400b3eb6  mov     edx, 10h
0x1400b3ebb  mov     r9d, ebx
0x1400b3ebe  call    WPP_SF_d
0x1400b3ec3  mov     eax, ebx
0x1400b3ec5  mov     rcx, [rbp+110h+var_50]
0x1400b3ecc  xor     rcx, rsp; StackCookie
0x1400b3ecf  call    __security_check_cookie
0x1400b3ed4  add     rsp, 1D8h
0x1400b3edb  pop     r15
0x1400b3edd  pop     r14
0x1400b3edf  pop     r13
0x1400b3ee1  pop     r12
0x1400b3ee3  pop     rdi
0x1400b3ee4  pop     rsi
0x1400b3ee5  pop     rbx
0x1400b3ee6  pop     rbp
0x1400b3ee7  retn
```
