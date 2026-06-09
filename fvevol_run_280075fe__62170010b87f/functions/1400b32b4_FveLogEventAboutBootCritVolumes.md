# FveLogEventAboutBootCritVolumes

- ea: `0x1400b32b4`
- end: `0x1400b3699`
- name: `FveLogEventAboutBootCritVolumes`
- size: `997`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14006f4e0`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x14000110c`
- `0x140008dc0`
- `0x140008e44`
- `0x1400218c0`
- `0x140021d00`
- `0x1400b32b4`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b3380`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x1400b3380`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b339d`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1400b339d`
- `ntoskrnl!EtwWrite` at `0x1400b347a`
- `ntoskrnl!EtwWrite` at `0x1400b347a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b362e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b362e`

## pseudocode

```c
__int64 __fastcall FveLogEventAboutBootCritVolumes(__int64 a1, __int64 a2, int a3, int a4, int a5, int a6, int a7)
{
  __int64 v8; // rdi
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  __int16 DosName; // [rsp+38h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DosName_8; // [rsp+40h] [rbp-C8h] BYREF
  int v15; // [rsp+50h] [rbp-B8h] BYREF
  int v16; // [rsp+54h] [rbp-B4h] BYREF
  __int64 v17; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+70h] [rbp-98h] BYREF
  __int64 v21; // [rsp+78h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[6]; // [rsp+88h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+E8h] [rbp-20h] BYREF
  char v24[16]; // [rsp+108h] [rbp+0h] BYREF
  int *v25; // [rsp+118h] [rbp+10h]
  __int64 v26; // [rsp+120h] [rbp+18h]
  int *v27; // [rsp+128h] [rbp+20h]
  __int64 v28; // [rsp+130h] [rbp+28h]
  __int64 *v29; // [rsp+138h] [rbp+30h]
  __int64 v30; // [rsp+140h] [rbp+38h]
  __int64 *v31; // [rsp+148h] [rbp+40h]
  __int64 v32; // [rsp+150h] [rbp+48h]
  __int64 *v33; // [rsp+158h] [rbp+50h]
  __int64 v34; // [rsp+160h] [rbp+58h]
  __int64 *v35; // [rsp+168h] [rbp+60h]
  __int64 v36; // [rsp+170h] [rbp+68h]
  __int64 *v37; // [rsp+178h] [rbp+70h]
  __int64 v38; // [rsp+180h] [rbp+78h]
  int v39; // [rsp+1E8h] [rbp+E0h] BYREF
  int v40; // [rsp+1F0h] [rbp+E8h] BYREF

  v40 = a4;
  v39 = a3;
  DosName_8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids);
  }
  *(_DWORD *)&DosName_8.Length = 0x20000;
  DosName = 0;
  DosName_8.Buffer = (wchar_t *)&DosName;
  memset(UserData, 0, sizeof(UserData));
  if ( a1 && (v8 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL)) != 0 && *(_QWORD *)(v8 + 88) )
  {
    if ( !KeAreAllApcsDisabled() )
    {
      v9 = IoVolumeDeviceToDosName(*(PVOID *)(*(_QWORD *)(a1 + 64) + 120LL), &DosName_8);
      if ( v9 < 0 )
      {
        *(_DWORD *)&DosName_8.Length = 0x20000;
        DosName_8.Buffer = (wchar_t *)&DosName;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids,
            (unsigned int)v9);
        }
      }
    }
    *(_QWORD *)&UserData[0].Size = 4;
    UserData[0].Ptr = (ULONGLONG)&v39;
    UserData[1].Ptr = (ULONGLONG)DosName_8.Buffer;
    UserData[1].Size = DosName_8.MaximumLength;
    UserData[2].Ptr = (ULONGLONG)&v40;
    UserData[3].Ptr = (ULONGLONG)&a5;
    UserData[4].Ptr = (ULONGLONG)&a6;
    UserData[5].Ptr = (ULONGLONG)&a7;
    UserData[1].Reserved = 0;
    *(_QWORD *)&UserData[2].Size = 4;
    *(_QWORD *)&UserData[3].Size = 4;
    *(_QWORD *)&UserData[4].Size = 4;
    *(_QWORD *)&UserData[5].Size = 4;
    v10 = EtwWrite(*(_QWORD *)(v8 + 88), &FVE_BOOT_CRIT_DEVICE_UNEXPECTED_BEHAVIOR, 0, 6u, UserData);
    v11 = v10;
    if ( v10 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids,
        (unsigned int)v10);
    }
  }
  else
  {
    v11 = -1073741436;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids);
    }
  }
  if ( v39 < 0 && (unsigned int)dword_140045040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
  {
    tlgCreate1Sz_wchar_t(v24, DosName_8.Buffer);
    v25 = &v15;
    v15 = v39;
    v27 = &v16;
    v17 = v40;
    v26 = 4;
    v29 = &v17;
    v18 = a5;
    v31 = &v18;
    v19 = a6;
    v33 = &v19;
    v20 = a7;
    v35 = &v20;
    v37 = &v21;
    v16 = 24714;
    v28 = 4;
    v30 = 8;
    v32 = 8;
    v34 = 8;
    v36 = 8;
    v21 = 0x1000000;
    v38 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140045040, (unsigned __int8 *)&unk_14003BD18, 0, 0, 0xAu, &v23);
  }
  if ( (__int16 *)DosName_8.Buffer != &DosName )
  {
    ExFreePoolWithTag(DosName_8.Buffer, 0);
    DosName_8.Buffer = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x11u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1400b32b4  mov     rax, rsp
0x1400b32b7  mov     [rax+10h], rbx
0x1400b32bb  mov     [rax+20h], r9d
0x1400b32bf  mov     [rax+18h], r8d
0x1400b32c3  push    rbp
0x1400b32c4  push    rsi
0x1400b32c5  push    rdi
0x1400b32c6  push    r12
0x1400b32c8  push    r13
0x1400b32ca  push    r14
0x1400b32cc  push    r15
0x1400b32ce  lea     rbp, [rax-0C8h]
0x1400b32d5  sub     rsp, 190h
0x1400b32dc  mov     rax, cs:__security_cookie
0x1400b32e3  xor     rax, rsp
0x1400b32e6  mov     [rbp+0C0h+var_40], rax
0x1400b32ed  xorps   xmm0, xmm0
0x1400b32f0  mov     rbx, rcx
0x1400b32f3  movups  xmmword ptr [rsp+1C0h+DosName.Buffer], xmm0
0x1400b32f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b32ff  lea     r13, WPP_GLOBAL_Control
0x1400b3306  lea     r12, WPP_7dbdcd8ecbed33ea741e2ac5e04a7ff4_Traceguids
0x1400b330d  cmp     rcx, r13
0x1400b3310  jz      short loc_1400B3330
0x1400b3312  bt      dword ptr [rcx+2Ch], 11h
0x1400b3317  jnb     short loc_1400B3330
0x1400b3319  cmp     byte ptr [rcx+29h], 5
0x1400b331d  jb      short loc_1400B3330
0x1400b331f  mov     rcx, [rcx+18h]
0x1400b3323  mov     edx, 21h ; '!'
0x1400b3328  mov     r8, r12
0x1400b332b  call    WPP_SF_
0x1400b3330  xor     esi, esi
0x1400b3332  mov     dword ptr [rsp+1C0h+DosName.Buffer], 20000h
0x1400b333a  lea     rax, [rsp+1C0h+DosName]
0x1400b333f  mov     [rsp+1C0h+DosName.Length], si
0x1400b3344  xor     edx, edx; Val
0x1400b3346  mov     [rsp+1C0h+P], rax
0x1400b334b  lea     rcx, [rbp+0C0h+var_140]; void *
0x1400b334f  lea     r8d, [rsi+60h]; Size
0x1400b3353  lea     r14d, [rsi+2]
0x1400b3357  call    memset
0x1400b335c  test    rbx, rbx
0x1400b335f  jz      loc_1400B34BB
0x1400b3365  mov     rax, [rbx+40h]
0x1400b3369  mov     rdi, [rax+8]
0x1400b336d  test    rdi, rdi
0x1400b3370  jz      loc_1400B34BB
0x1400b3376  cmp     [rdi+58h], rsi
0x1400b337a  jz      loc_1400B34BB
0x1400b3380  call    cs:__imp_KeAreAllApcsDisabled
0x1400b3387  nop     dword ptr [rax+rax+00h]
0x1400b338c  test    al, al
0x1400b338e  jnz     short loc_1400B33EA
0x1400b3390  mov     rcx, [rbx+40h]
0x1400b3394  lea     rdx, [rsp+1C0h+DosName.Buffer]; DosName
0x1400b3399  mov     rcx, [rcx+78h]; VolumeDeviceObject
0x1400b339d  call    cs:__imp_IoVolumeDeviceToDosName
0x1400b33a4  nop     dword ptr [rax+rax+00h]
0x1400b33a9  mov     r9d, eax
0x1400b33ac  test    eax, eax
0x1400b33ae  jns     short loc_1400B33EA
0x1400b33b0  lea     rax, [rsp+1C0h+DosName]
0x1400b33b5  mov     dword ptr [rsp+1C0h+DosName.Buffer], 20000h
0x1400b33bd  mov     [rsp+1C0h+P], rax
0x1400b33c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b33c9  cmp     rcx, r13
0x1400b33cc  jz      short loc_1400B33EA
0x1400b33ce  bt      dword ptr [rcx+2Ch], 11h
0x1400b33d3  jnb     short loc_1400B33EA
0x1400b33d5  cmp     [rcx+29h], r14b
0x1400b33d9  jb      short loc_1400B33EA
0x1400b33db  mov     rcx, [rcx+18h]
0x1400b33df  lea     edx, [rsi+24h]
0x1400b33e2  mov     r8, r12
0x1400b33e5  call    WPP_SF_d
0x1400b33ea  lea     rax, [rbp+0C0h+arg_10]
0x1400b33f1  mov     qword ptr [rbp+0C0h+var_140.Size], 4
0x1400b33f9  mov     [rbp+0C0h+var_140.Ptr], rax
0x1400b33fd  lea     rdx, FVE_BOOT_CRIT_DEVICE_UNEXPECTED_BEHAVIOR; EventDescriptor
0x1400b3404  mov     rax, [rsp+1C0h+P]
0x1400b3409  mov     r9d, 6; UserDataCount
0x1400b340f  mov     [rbp+0C0h+var_130], rax
0x1400b3413  xor     r8d, r8d; ActivityId
0x1400b3416  movzx   eax, word ptr [rsp+1C0h+DosName.Buffer+2]
0x1400b341b  mov     [rbp+0C0h+var_128], eax
0x1400b341e  lea     rax, [rbp+0C0h+arg_18]
0x1400b3425  mov     [rbp+0C0h+var_120], rax
0x1400b3429  lea     rax, [rbp+0C0h+arg_20]
0x1400b3430  mov     [rbp+0C0h+var_110], rax
0x1400b3434  lea     rax, [rbp+0C0h+arg_28]
0x1400b343b  mov     [rbp+0C0h+var_100], rax
0x1400b343f  lea     rax, [rbp+0C0h+arg_30]
0x1400b3446  mov     [rbp+0C0h+var_F0], rax
0x1400b344a  lea     rax, [rbp+0C0h+var_140]
0x1400b344e  mov     [rbp+0C0h+var_124], esi
0x1400b3451  mov     [rbp+0C0h+var_118], 4
0x1400b3459  mov     [rbp+0C0h+var_108], 4
0x1400b3461  mov     [rbp+0C0h+var_F8], 4
0x1400b3469  mov     [rbp+0C0h+var_E8], 4
0x1400b3471  mov     rcx, [rdi+58h]; RegHandle
0x1400b3475  mov     [rsp+1C0h+UserData], rax; UserData
0x1400b347a  call    cs:__imp_EtwWrite
0x1400b3481  nop     dword ptr [rax+rax+00h]
0x1400b3486  mov     ebx, eax
0x1400b3488  test    eax, eax
0x1400b348a  jns     short loc_1400B34EA
0x1400b348c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3493  cmp     rcx, r13
0x1400b3496  jz      short loc_1400B34EA
0x1400b3498  bt      dword ptr [rcx+2Ch], 11h
0x1400b349d  jnb     short loc_1400B34EA
0x1400b349f  cmp     [rcx+29h], r14b
0x1400b34a3  jb      short loc_1400B34EA
0x1400b34a5  mov     rcx, [rcx+18h]
0x1400b34a9  mov     edx, 25h ; '%'
0x1400b34ae  mov     r9d, eax
0x1400b34b1  mov     r8, r12
0x1400b34b4  call    WPP_SF_d
0x1400b34b9  jmp     short loc_1400B34EA
0x1400b34bb  mov     ebx, 0C0000184h
0x1400b34c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b34c7  cmp     rcx, r13
0x1400b34ca  jz      short loc_1400B34EA
0x1400b34cc  bt      dword ptr [rcx+2Ch], 11h
0x1400b34d1  jnb     short loc_1400B34EA
0x1400b34d3  cmp     [rcx+29h], r14b
0x1400b34d7  jb      short loc_1400B34EA
0x1400b34d9  mov     rcx, [rcx+18h]
0x1400b34dd  mov     edx, 23h ; '#'
0x1400b34e2  mov     r8, r12
0x1400b34e5  call    WPP_SF_
0x1400b34ea  cmp     [rbp+0C0h+arg_10], esi
0x1400b34f0  jge     loc_1400B361D
0x1400b34f6  mov     eax, cs:dword_140045040
0x1400b34fc  cmp     eax, 4
0x1400b34ff  jbe     loc_1400B361D
0x1400b3505  mov     rdx, 400000000000h
0x1400b350f  lea     rcx, dword_140045040
0x1400b3516  call    _tlgKeywordOn
0x1400b351b  test    al, al
0x1400b351d  jz      loc_1400B361D
0x1400b3523  mov     rdx, [rsp+1C0h+P]
0x1400b3528  lea     rcx, [rbp+0C0h+var_C0]
0x1400b352c  call    _tlgCreate1Sz_wchar_t
0x1400b3531  mov     ecx, [rbp+0C0h+arg_10]
0x1400b3537  lea     rax, [rsp+1C0h+var_178]
0x1400b353c  mov     [rbp+0C0h+var_B0], rax
0x1400b3540  lea     rdx, unk_14003BD18
0x1400b3547  lea     rax, [rsp+1C0h+var_178+4]
0x1400b354c  mov     dword ptr [rsp+1C0h+var_178], ecx
0x1400b3550  mov     [rbp+0C0h+var_A0], rax
0x1400b3554  lea     rcx, dword_140045040
0x1400b355b  movsxd  rax, [rbp+0C0h+arg_18]
0x1400b3562  xor     r9d, r9d
0x1400b3565  mov     [rsp+1C0h+var_170], rax
0x1400b356a  xor     r8d, r8d
0x1400b356d  lea     rax, [rsp+1C0h+var_170]
0x1400b3572  mov     [rbp+0C0h+var_A8], 4
0x1400b357a  mov     [rbp+0C0h+var_90], rax
0x1400b357e  movsxd  rax, [rbp+0C0h+arg_20]
0x1400b3585  mov     [rsp+1C0h+var_168], rax
0x1400b358a  lea     rax, [rsp+1C0h+var_168]
0x1400b358f  mov     [rbp+0C0h+var_80], rax
0x1400b3593  movsxd  rax, [rbp+0C0h+arg_28]
0x1400b359a  mov     [rsp+1C0h+var_160], rax
0x1400b359f  lea     rax, [rsp+1C0h+var_160]
0x1400b35a4  mov     [rbp+0C0h+var_70], rax
0x1400b35a8  movsxd  rax, [rbp+0C0h+arg_30]
0x1400b35af  mov     [rsp+1C0h+var_158], rax
0x1400b35b4  lea     rax, [rsp+1C0h+var_158]
0x1400b35b9  mov     [rbp+0C0h+var_60], rax
0x1400b35bd  lea     rax, [rsp+1C0h+var_150]
0x1400b35c2  mov     [rbp+0C0h+var_50], rax
0x1400b35c6  lea     rax, [rbp+0C0h+var_E0]
0x1400b35ca  mov     qword ptr [rsp+1C0h+var_198], rax
0x1400b35cf  mov     dword ptr [rsp+1C0h+UserData], 0Ah
0x1400b35d7  mov     dword ptr [rsp+1C0h+var_178+4], 608Ah
0x1400b35df  mov     [rbp+0C0h+var_98], 4
0x1400b35e7  mov     [rbp+0C0h+var_88], 8
0x1400b35ef  mov     [rbp+0C0h+var_78], 8
0x1400b35f7  mov     [rbp+0C0h+var_68], 8
0x1400b35ff  mov     [rbp+0C0h+var_58], 8
0x1400b3607  mov     [rsp+1C0h+var_150], 1000000h
0x1400b3610  mov     [rbp+0C0h+var_48], 8
0x1400b3618  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b361d  mov     rcx, [rsp+1C0h+P]; P
0x1400b3622  lea     rax, [rsp+1C0h+DosName]
0x1400b3627  cmp     rcx, rax
0x1400b362a  jz      short loc_1400B363F
0x1400b362c  xor     edx, edx; Tag
0x1400b362e  call    cs:__imp_ExFreePoolWithTag
0x1400b3635  nop     dword ptr [rax+rax+00h]
0x1400b363a  mov     [rsp+1C0h+P], rsi
0x1400b363f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3646  cmp     rcx, r13
0x1400b3649  jz      short loc_1400B366C
0x1400b364b  bt      dword ptr [rcx+2Ch], 11h
0x1400b3650  jnb     short loc_1400B366C
0x1400b3652  cmp     byte ptr [rcx+29h], 5
0x1400b3656  jb      short loc_1400B366C
0x1400b3658  mov     rcx, [rcx+18h]
0x1400b365c  mov     edx, 26h ; '&'
0x1400b3661  mov     r9d, ebx
0x1400b3664  mov     r8, r12
0x1400b3667  call    WPP_SF_d
0x1400b366c  mov     eax, ebx
0x1400b366e  mov     rcx, [rbp+0C0h+var_40]
0x1400b3675  xor     rcx, rsp; StackCookie
0x1400b3678  call    __security_check_cookie
0x1400b367d  mov     rbx, [rsp+1C0h+arg_8]
0x1400b3685  add     rsp, 190h
0x1400b368c  pop     r15
0x1400b368e  pop     r14
0x1400b3690  pop     r13
0x1400b3692  pop     r12
0x1400b3694  pop     rdi
0x1400b3695  pop     rsi
0x1400b3696  pop     rbp
0x1400b3697  retn
```
