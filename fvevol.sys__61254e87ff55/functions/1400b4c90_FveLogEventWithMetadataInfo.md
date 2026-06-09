# FveLogEventWithMetadataInfo

- ea: `0x1400b4c90`
- end: `0x1400b5185`
- name: `FveLogEventWithMetadataInfo`
- size: `1269`
- prototype: ``
- caller_count: `8`
- callee_count: `8`
- tags: ``

## callers

- `0x14000e974`
- `0x14006bc9c`
- `0x1400a7e30`
- `0x1400ab924`
- `0x1400b1110`
- `0x1400b1c60`
- `0x1400e09a4`
- `0x1400e0f8c`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140001114`
- `0x140008e80`
- `0x140008f04`
- `0x140022bf0`
- `0x140023040`
- `0x1400b4c90`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b4da5`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b4da5`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b4dc2`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b4dc2`
- `ntoskrnl!EtwWrite` at `0x1400b4f02`
- `ntoskrnl!EtwWrite` at `0x1400b4f02`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b511d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b511d`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids);
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
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids, v5);
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
            WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids,
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
          && (unsigned int)dword_140046040 > 4
          && (unsigned __int8)tlgKeywordOn(&dword_140046040, 0x400000000000LL) )
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
            (__int64)&dword_140046040,
            (unsigned __int8 *)&dword_14003D1EC,
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
    WPP_SF_(v7->AttachedDevice, v8, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids);
    goto LABEL_35;
  }
  v5 = -1073741811;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v5;
  if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u) && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids);
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1400b4c90  mov     [rsp-8+arg_18], r9
0x1400b4c95  mov     [rsp-8+arg_10], r8d
0x1400b4c9a  push    rbp
0x1400b4c9b  push    rbx
0x1400b4c9c  push    rsi
0x1400b4c9d  push    rdi
0x1400b4c9e  push    r12
0x1400b4ca0  push    r13
0x1400b4ca2  push    r14
0x1400b4ca4  push    r15
0x1400b4ca6  lea     rbp, [rsp-0D8h]
0x1400b4cae  sub     rsp, 1D8h
0x1400b4cb5  mov     rax, cs:__security_cookie
0x1400b4cbc  xor     rax, rsp
0x1400b4cbf  mov     [rbp+110h+var_50], rax
0x1400b4cc6  xorps   xmm0, xmm0
0x1400b4cc9  mov     r14, rdx
0x1400b4ccc  movups  xmmword ptr [rsp+210h+DosName.Length], xmm0
0x1400b4cd1  mov     rdi, rcx
0x1400b4cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4cdb  lea     r13, WPP_GLOBAL_Control
0x1400b4ce2  cmp     rcx, r13
0x1400b4ce5  jz      short loc_1400B4D09
0x1400b4ce7  bt      dword ptr [rcx+2Ch], 11h
0x1400b4cec  jnb     short loc_1400B4D09
0x1400b4cee  cmp     byte ptr [rcx+29h], 5
0x1400b4cf2  jb      short loc_1400B4D09
0x1400b4cf4  mov     rcx, [rcx+18h]
0x1400b4cf8  lea     r8, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids
0x1400b4cff  mov     edx, 0Ah
0x1400b4d04  call    WPP_SF_
0x1400b4d09  xor     r15d, r15d
0x1400b4d0c  mov     dword ptr [rsp+210h+DosName.Length], 20000h
0x1400b4d14  lea     rax, [rsp+210h+var_1E0]
0x1400b4d19  mov     [rsp+210h+var_1E0], r15w
0x1400b4d1f  xor     edx, edx; Val
0x1400b4d21  mov     [rsp+210h+DosName.Buffer], rax
0x1400b4d26  lea     rcx, [rbp+110h+var_180]; void *
0x1400b4d2a  lea     r8d, [r15+70h]; Size
0x1400b4d2e  lea     esi, [r15+2]
0x1400b4d32  call    memset
0x1400b4d37  test    r14, r14
0x1400b4d3a  jnz     short loc_1400B4D7E
0x1400b4d3c  mov     ebx, 0C000000Dh
0x1400b4d41  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4d48  cmp     rcx, r13
0x1400b4d4b  jz      loc_1400B515F
0x1400b4d51  bt      dword ptr [rcx+2Ch], 11h
0x1400b4d56  jnb     loc_1400B512E
0x1400b4d5c  cmp     [rcx+29h], sil
0x1400b4d60  jb      loc_1400B512E
0x1400b4d66  mov     rcx, [rcx+18h]
0x1400b4d6a  lea     edx, [rsi+9]
0x1400b4d6d  lea     r8, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids
0x1400b4d74  call    WPP_SF_
0x1400b4d79  jmp     loc_1400B510C
0x1400b4d7e  test    rdi, rdi
0x1400b4d81  jz      loc_1400B4F4C
0x1400b4d87  mov     rax, [rdi+40h]
0x1400b4d8b  mov     rsi, [rax+8]
0x1400b4d8f  test    rsi, rsi
0x1400b4d92  jz      loc_1400B4F47
0x1400b4d98  cmp     [rsi+58h], r15
0x1400b4d9c  jz      loc_1400B4F47
0x1400b4da2  mov     ebx, r15d
0x1400b4da5  call    cs:__imp_KeAreAllApcsDisabled
0x1400b4dac  nop     dword ptr [rax+rax+00h]
0x1400b4db1  test    al, al
0x1400b4db3  jnz     short loc_1400B4E1C
0x1400b4db5  mov     rcx, [rdi+40h]
0x1400b4db9  lea     rdx, [rsp+210h+DosName]; DosName
0x1400b4dbe  mov     rcx, [rcx+78h]; VolumeDeviceObject
0x1400b4dc2  call    cs:__imp_IoVolumeDeviceToDosName
0x1400b4dc9  nop     dword ptr [rax+rax+00h]
0x1400b4dce  mov     ebx, eax
0x1400b4dd0  mov     edi, 2
0x1400b4dd5  test    eax, eax
0x1400b4dd7  jns     short loc_1400B4E21
0x1400b4dd9  lea     rax, [rsp+210h+var_1E0]
0x1400b4dde  mov     dword ptr [rsp+210h+DosName.Length], 20000h
0x1400b4de6  mov     [rsp+210h+DosName.Buffer], rax
0x1400b4deb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4df2  cmp     rcx, r13
0x1400b4df5  jz      short loc_1400B4E21
0x1400b4df7  bt      dword ptr [rcx+2Ch], 11h
0x1400b4dfc  jnb     short loc_1400B4E21
0x1400b4dfe  cmp     [rcx+29h], dil
0x1400b4e02  jb      short loc_1400B4E21
0x1400b4e04  mov     rcx, [rcx+18h]
0x1400b4e08  lea     edx, [rdi+0Bh]
0x1400b4e0b  mov     r9d, ebx
0x1400b4e0e  lea     r8, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids
0x1400b4e15  call    WPP_SF_d
0x1400b4e1a  jmp     short loc_1400B4E21
0x1400b4e1c  mov     edi, 2
0x1400b4e21  cmp     byte ptr [rbp+110h+arg_50], r15b
0x1400b4e28  jz      short loc_1400B4E62
0x1400b4e2a  cmp     [rbp+110h+arg_10], r15d
0x1400b4e31  jl      short loc_1400B4E62
0x1400b4e33  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4e3a  cmp     rcx, r13
0x1400b4e3d  jz      loc_1400B4F7F
0x1400b4e43  bt      dword ptr [rcx+2Ch], 11h
0x1400b4e48  jnb     loc_1400B4F7F
0x1400b4e4e  cmp     byte ptr [rcx+29h], 5
0x1400b4e52  jb      loc_1400B4F7F
0x1400b4e58  mov     edx, 0Eh
0x1400b4e5d  jmp     loc_1400B4F6F
0x1400b4e62  lea     rax, [rbp+110h+arg_10]
0x1400b4e69  mov     qword ptr [rbp+110h+var_180.Size], 4
0x1400b4e71  mov     [rbp+110h+var_180.Ptr], rax
0x1400b4e75  mov     r9d, 7; UserDataCount
0x1400b4e7b  mov     rax, [rsp+210h+DosName.Buffer]
0x1400b4e80  xor     r8d, r8d; ActivityId
0x1400b4e83  mov     [rbp+110h+var_170], rax
0x1400b4e87  mov     rdx, r14; EventDescriptor
0x1400b4e8a  movzx   eax, [rsp+210h+DosName.MaximumLength]
0x1400b4e8f  mov     [rbp+110h+var_168], eax
0x1400b4e92  lea     rax, [rbp+110h+arg_18]
0x1400b4e99  mov     [rbp+110h+var_160], rax
0x1400b4e9d  lea     rax, [rbp+110h+arg_20]
0x1400b4ea4  mov     [rbp+110h+var_150], rax
0x1400b4ea8  lea     rax, [rbp+110h+arg_28]
0x1400b4eaf  mov     [rbp+110h+var_140], rax
0x1400b4eb3  lea     rax, [rbp+110h+arg_30]
0x1400b4eba  mov     [rbp+110h+var_130], rax
0x1400b4ebe  lea     rax, [rbp+110h+arg_38]
0x1400b4ec5  mov     [rbp+110h+var_120], rax
0x1400b4ec9  lea     rax, [rbp+110h+var_180]
0x1400b4ecd  mov     [rbp+110h+var_164], r15d
0x1400b4ed1  mov     [rbp+110h+var_158], 8
0x1400b4ed9  mov     [rbp+110h+var_148], 8
0x1400b4ee1  mov     [rbp+110h+var_138], 8
0x1400b4ee9  mov     [rbp+110h+var_128], 8
0x1400b4ef1  mov     [rbp+110h+var_118], 8
0x1400b4ef9  mov     rcx, [rsi+58h]; RegHandle
0x1400b4efd  mov     [rsp+210h+UserData], rax; UserData
0x1400b4f02  call    cs:__imp_EtwWrite
0x1400b4f09  nop     dword ptr [rax+rax+00h]
0x1400b4f0e  mov     ebx, eax
0x1400b4f10  test    eax, eax
0x1400b4f12  jns     short loc_1400B4F7F
0x1400b4f14  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4f1b  cmp     rcx, r13
0x1400b4f1e  jz      short loc_1400B4F7F
0x1400b4f20  bt      dword ptr [rcx+2Ch], 11h
0x1400b4f25  jnb     short loc_1400B4F7F
0x1400b4f27  cmp     [rcx+29h], dil
0x1400b4f2b  jb      short loc_1400B4F7F
0x1400b4f2d  mov     rcx, [rcx+18h]
0x1400b4f31  lea     r8, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids
0x1400b4f38  mov     edx, 0Fh
0x1400b4f3d  mov     r9d, eax
0x1400b4f40  call    WPP_SF_d
0x1400b4f45  jmp     short loc_1400B4F7F
0x1400b4f47  mov     esi, 2
0x1400b4f4c  mov     ebx, 0C0000184h
0x1400b4f51  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4f58  cmp     rcx, r13
0x1400b4f5b  jz      short loc_1400B4F7F
0x1400b4f5d  bt      dword ptr [rcx+2Ch], 11h
0x1400b4f62  jnb     short loc_1400B4F7F
0x1400b4f64  cmp     [rcx+29h], sil
0x1400b4f68  jb      short loc_1400B4F7F
0x1400b4f6a  mov     edx, 0Ch
0x1400b4f6f  mov     rcx, [rcx+18h]
0x1400b4f73  lea     r8, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids
0x1400b4f7a  call    WPP_SF_
0x1400b4f7f  cmp     byte ptr [rbp+110h+arg_48], 1
0x1400b4f86  jz      short loc_1400B4F95
0x1400b4f88  cmp     [rbp+110h+arg_10], r15d
0x1400b4f8f  jge     loc_1400B510C
0x1400b4f95  mov     eax, cs:dword_140046040
0x1400b4f9b  cmp     eax, 4
0x1400b4f9e  jbe     loc_1400B510C
0x1400b4fa4  mov     rdx, 400000000000h
0x1400b4fae  lea     rcx, dword_140046040
0x1400b4fb5  call    _tlgKeywordOn
0x1400b4fba  test    al, al
0x1400b4fbc  jz      loc_1400B510C
0x1400b4fc2  mov     rdx, [rsp+210h+DosName.Buffer]
0x1400b4fc7  lea     rcx, [rbp+110h+var_F0]
0x1400b4fcb  call    _tlgCreate1Sz_wchar_t
0x1400b4fd0  mov     ecx, [rbp+110h+arg_10]
0x1400b4fd6  lea     rax, [rsp+210h+var_1C8]
0x1400b4fdb  mov     [rbp+110h+var_E0], rax
0x1400b4fdf  lea     rdx, dword_14003D1EC
0x1400b4fe6  movzx   eax, word ptr [r14]
0x1400b4fea  xor     r9d, r9d
0x1400b4fed  mov     [rsp+210h+var_1C4], eax
0x1400b4ff1  xor     r8d, r8d
0x1400b4ff4  lea     rax, [rsp+210h+var_1C4]
0x1400b4ff9  mov     [rsp+210h+var_1C8], ecx
0x1400b4ffd  mov     [rbp+110h+var_D0], rax
0x1400b5001  lea     rcx, dword_140046040
0x1400b5008  mov     rax, [rbp+110h+arg_18]
0x1400b500f  mov     [rsp+210h+var_1C0], rax
0x1400b5014  lea     rax, [rsp+210h+var_1C0]
0x1400b5019  mov     [rbp+110h+var_C0], rax
0x1400b501d  mov     rax, [rbp+110h+arg_20]
0x1400b5024  mov     [rsp+210h+var_1B8], rax
0x1400b5029  lea     rax, [rsp+210h+var_1B8]
0x1400b502e  mov     [rbp+110h+var_B0], rax
0x1400b5032  mov     rax, [rbp+110h+arg_28]
0x1400b5039  mov     [rsp+210h+var_1B0], rax
0x1400b503e  lea     rax, [rsp+210h+var_1B0]
0x1400b5043  mov     [rbp+110h+var_A0], rax
0x1400b5047  mov     rax, [rbp+110h+arg_30]
0x1400b504e  mov     [rsp+210h+var_1A8], rax
0x1400b5053  lea     rax, [rsp+210h+var_1A8]
0x1400b5058  mov     [rbp+110h+var_90], rax
0x1400b505f  mov     rax, [rbp+110h+arg_38]
0x1400b5066  mov     [rsp+210h+var_1A0], rax
0x1400b506b  lea     rax, [rsp+210h+var_1A0]
0x1400b5070  mov     [rbp+110h+var_80], rax
0x1400b5077  mov     rax, [rbp+110h+arg_40]
0x1400b507e  mov     [rsp+210h+var_198], rax
0x1400b5083  lea     rax, [rsp+210h+var_198]
0x1400b5088  mov     [rbp+110h+var_70], rax
0x1400b508f  lea     rax, [rbp+110h+var_190]
0x1400b5093  mov     [rbp+110h+var_60], rax
0x1400b509a  lea     rax, [rbp+110h+var_110]
0x1400b509e  mov     [rsp+210h+var_1E8], rax
0x1400b50a3  mov     dword ptr [rsp+210h+UserData], 0Ch
0x1400b50ab  mov     [rbp+110h+var_D8], 4
0x1400b50b3  mov     [rbp+110h+var_C8], 4
0x1400b50bb  mov     [rbp+110h+var_B8], 8
0x1400b50c3  mov     [rbp+110h+var_A8], 8
0x1400b50cb  mov     [rbp+110h+var_98], 8
0x1400b50d3  mov     [rbp+110h+var_88], 8
0x1400b50de  mov     [rbp+110h+var_78], 8
0x1400b50e9  mov     [rbp+110h+var_68], 8
0x1400b50f4  mov     [rbp+110h+var_190], 1000000h
0x1400b50fc  mov     [rbp+110h+var_58], 8
0x1400b5107  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b510c  mov     rcx, [rsp+210h+DosName.Buffer]; P
0x1400b5111  lea     rax, [rsp+210h+var_1E0]
0x1400b5116  cmp     rcx, rax
0x1400b5119  jz      short loc_1400B512E
0x1400b511b  xor     edx, edx; Tag
0x1400b511d  call    cs:__imp_ExFreePoolWithTag
0x1400b5124  nop     dword ptr [rax+rax+00h]
0x1400b5129  mov     [rsp+210h+DosName.Buffer], r15
0x1400b512e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5135  cmp     rcx, r13
0x1400b5138  jz      short loc_1400B515F
0x1400b513a  bt      dword ptr [rcx+2Ch], 11h
0x1400b513f  jnb     short loc_1400B515F
0x1400b5141  cmp     byte ptr [rcx+29h], 5
0x1400b5145  jb      short loc_1400B515F
0x1400b5147  mov     rcx, [rcx+18h]
0x1400b514b  lea     r8, WPP_303a4b105747300cb5f16433e0e95a1e_Traceguids
0x1400b5152  mov     edx, 10h
0x1400b5157  mov     r9d, ebx
0x1400b515a  call    WPP_SF_d
0x1400b515f  mov     eax, ebx
0x1400b5161  mov     rcx, [rbp+110h+var_50]
0x1400b5168  xor     rcx, rsp; StackCookie
0x1400b516b  call    __security_check_cookie
0x1400b5170  add     rsp, 1D8h
0x1400b5177  pop     r15
0x1400b5179  pop     r14
0x1400b517b  pop     r13
0x1400b517d  pop     r12
0x1400b517f  pop     rdi
0x1400b5180  pop     rsi
0x1400b5181  pop     rbx
0x1400b5182  pop     rbp
0x1400b5183  retn
```
