# FveBackupBootSectors

- ea: `0x1400a6940`
- end: `0x1400a6ed0`
- name: `FveBackupBootSectors`
- size: `1424`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14009ec2c`
- `0x1400a2008`

## callees

- `0x140001570`
- `0x140008288`
- `0x140008dc0`
- `0x140008e44`
- `0x140009bf4`
- `0x1400218c0`
- `0x140021d00`
- `0x14009de84`
- `0x1400a6940`
- `0x1400b5c18`
- `0x1400d8584`
- `0x1400d9620`
- `0x1400def70`
- `0x1400e5cec`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400a6d24`
- `ntoskrnl!RtlCompareMemory` at `0x1400a6d24`
- `ntoskrnl!KeBugCheckEx` at `0x1400a6dbe`
- `ntoskrnl!KeBugCheckEx` at `0x1400a6dbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a6e22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a6e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a6e22`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a6e3d`
- `ntoskrnl!ExAllocatePool2` at `0x1400a6a28`
- `ntoskrnl!ExAllocatePool2` at `0x1400a6a54`
- `ntoskrnl!ExAllocatePool2` at `0x1400a6a28`
- `ntoskrnl!ExAllocatePool2` at `0x1400a6a54`

## pseudocode

```c
__int64 __fastcall FveBackupBootSectors(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  PDEVICE_OBJECT v5; // rcx
  int v6; // ebx
  char v7; // al
  unsigned int v8; // r13d
  void *v9; // rsi
  unsigned __int64 v10; // r15
  __int64 v11; // rcx
  void *Pool2; // r12
  unsigned __int64 v13; // rax
  bool v14; // cf
  unsigned int v15; // r15d
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rcx
  bool v19; // zf
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rbx
  __int64 *v24; // rax
  __int64 v25; // rcx
  void *v27; // [rsp+28h] [rbp-D8h]
  __int128 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v30; // [rsp+58h] [rbp-A8h]
  void *v31; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v32; // [rsp+68h] [rbp-98h]
  void *Source2; // [rsp+70h] [rbp-90h]
  unsigned __int64 v34; // [rsp+78h] [rbp-88h]
  _QWORD v35[32]; // [rsp+80h] [rbp-80h] BYREF

  v30 = a2;
  memset(v35, 0, sizeof(v35));
  v28 = 0;
  v29 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids);
  }
  v6 = 0;
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v5) )
  {
    v7 = *(_BYTE *)(a1 + 4403);
    if ( (v7 & 8) != 0 && (v7 & 0x10) == 0 )
LABEL_55:
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  v31 = 0;
  v8 = 0x100000;
  v29 = 0;
  v9 = 0;
  v28 = 0;
  if ( a3 < 0x100000 )
    v8 = a3;
  v10 = v8;
  v34 = v8;
  Pool2 = (void *)ExAllocatePool2(72, v8, 809850438);
  if ( !Pool2 )
  {
    v6 = -1073741670;
    goto LABEL_64;
  }
  Source2 = (void *)ExAllocatePool2(72, v8, 809850438);
  if ( !Source2 )
  {
    v6 = -1073741670;
    goto LABEL_62;
  }
  v32 = 0;
  v13 = 0;
  if ( !a3 )
    goto LABEL_62;
  while ( 1 )
  {
    v14 = a3 < v10;
    v15 = a3;
    if ( !v14 )
      v15 = v8;
    v6 = FveRawIoSynchronous(a1, *(_QWORD *)(a1 + 112), 3, 0, 0, v13, v15, (__int64)Pool2);
    if ( v6 < 0 )
      goto LABEL_60;
    if ( *(_QWORD *)(a1 + 976) )
    {
      Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v16);
      LOBYTE(v17) = 1;
      InitializeFilterData(a1, v35, v17, 0, 0, 0);
      v35[2] = v32;
      v35[11] = FveFilteredRead;
      LODWORD(v35[14]) = v15;
      v35[12] = Pool2;
      v35[13] = Pool2;
      v6 = FveParseBlockAndFilter(v35);
      DeInitializeFilterData(a1, v35);
      if ( v6 < 0 )
        goto LABEL_60;
    }
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v16) )
    {
      if ( *(_QWORD *)(a1 + 976) )
        goto LABEL_25;
      v19 = (*(_BYTE *)(a1 + 4403) & 0x10) == 0;
    }
    else
    {
      v19 = *(_QWORD *)(a1 + 976) == 0;
    }
    if ( v19 )
      goto LABEL_39;
LABEL_25:
    if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v18) )
    {
      v27 = 0;
      goto LABEL_38;
    }
    v21 = *(_QWORD *)(a1 + 4736);
    if ( v21 )
    {
      if ( *(_DWORD *)(v21 + 88) && !v9 )
        break;
    }
LABEL_37:
    v27 = v9;
LABEL_38:
    LOBYTE(v20) = 1;
    InitializeFilterData(a1, v35, v20, 0, 0, v27);
    v35[2] = v30;
    v35[11] = FveFilteredWrite;
    LODWORD(v35[14]) = v15;
    v35[12] = Pool2;
    v35[13] = Pool2;
    v6 = FveParseBlockAndFilter(v35);
    DeInitializeFilterData(a1, v35);
    if ( v6 < 0 )
      goto LABEL_72;
LABEL_39:
    v6 = FveRawIoSynchronous(a1, *(_QWORD *)(a1 + 112), 4, 0, 0, v30, v15, (__int64)Pool2);
    if ( v6 < 0 )
    {
LABEL_72:
      v24 = FVE_METADATA_FAILED_COMMIT;
      goto LABEL_61;
    }
    v22 = FveRawIoSynchronous(a1, *(_QWORD *)(a1 + 112), 9, 0, 0, 0, 0, 0);
    v6 = v22;
    if ( v22 != -1073741822 && v22 != -1073741808 && v22 != -1073741637 && v22 < 0 )
    {
      v24 = FVE_METADATA_DISK_FAILED_FLUSH_ERROR;
      goto LABEL_61;
    }
    v6 = FveRawIoSynchronous(a1, *(_QWORD *)(a1 + 112), 3, 0, 0, v30, v15, (__int64)Source2);
    if ( v6 < 0 )
      goto LABEL_60;
    v23 = v15;
    if ( RtlCompareMemory(Pool2, Source2, v15) != v15 )
    {
      v6 = -1073741823;
LABEL_60:
      v24 = FVE_METADATA_DISK_FAILED_READBACK_ERROR;
LABEL_61:
      v25 = *(_QWORD *)a1;
      *(_QWORD *)&v28 = v24;
      DWORD2(v28) = -1;
      HIDWORD(v28) = v6;
      v29 = 0;
      FveLogEventEx(v25, (const EVENT_DESCRIPTOR **)&v28, 0, 1);
      goto LABEL_62;
    }
    if ( v15 + v30 < v30 || (v13 = v15 + v32, v13 < v32) )
    {
      v6 = -1073741675;
      goto LABEL_62;
    }
    a3 -= v15;
    if ( !a3 )
    {
      v6 = 0;
      goto LABEL_62;
    }
    v10 = v34;
    v32 += v23;
    v30 += v23;
  }
  if ( *(_QWORD *)(a1 + 1008) )
    goto LABEL_55;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids);
  }
  v6 = ExtractFvek(*(_QWORD *)(a1 + 976) + 64LL, *(_QWORD *)(a1 + 1016), *(unsigned int *)(a1 + 1308), &v31);
  if ( v6 >= 0 )
  {
    v9 = v31;
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, (unsigned int)v6);
  }
  v9 = v31;
LABEL_62:
  ExFreePoolWithTag(Pool2, 0x30455646u);
  if ( Source2 )
    ExFreePoolWithTag(Source2, 0x30455646u);
LABEL_64:
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v11) && v9 )
    DeleteKey(v9);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400a6940  mov     [rsp-8+arg_18], rbx
0x1400a6945  push    rbp
0x1400a6946  push    rsi
0x1400a6947  push    rdi
0x1400a6948  push    r12
0x1400a694a  push    r13
0x1400a694c  push    r14
0x1400a694e  push    r15
0x1400a6950  lea     rbp, [rsp-90h]
0x1400a6958  sub     rsp, 190h
0x1400a695f  mov     rax, cs:__security_cookie
0x1400a6966  xor     rax, rsp
0x1400a6969  mov     [rbp+0C0h+var_40], rax
0x1400a6970  mov     r14, r8
0x1400a6973  mov     [rsp+1C0h+var_168], rdx
0x1400a6978  mov     rdi, rcx
0x1400a697b  xor     edx, edx; Val
0x1400a697d  mov     r8d, 100h; Size
0x1400a6983  lea     rcx, [rbp+0C0h+var_140]; void *
0x1400a6987  call    memset
0x1400a698c  xorps   xmm0, xmm0
0x1400a698f  xor     eax, eax
0x1400a6991  movups  [rsp+1C0h+var_180], xmm0
0x1400a6996  mov     [rsp+1C0h+var_170], rax
0x1400a699b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a69a2  lea     rax, WPP_GLOBAL_Control
0x1400a69a9  cmp     rcx, rax
0x1400a69ac  jz      short loc_1400A69D0
0x1400a69ae  mov     eax, [rcx+2Ch]
0x1400a69b1  test    al, 4
0x1400a69b3  jz      short loc_1400A69D0
0x1400a69b5  cmp     byte ptr [rcx+29h], 5
0x1400a69b9  jb      short loc_1400A69D0
0x1400a69bb  mov     rcx, [rcx+18h]
0x1400a69bf  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400a69c6  mov     edx, 5Fh ; '_'
0x1400a69cb  call    WPP_SF_
0x1400a69d0  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400a69d5  xor     ebx, ebx
0x1400a69d7  test    eax, eax
0x1400a69d9  jz      short loc_1400A69ED
0x1400a69db  mov     al, [rdi+1133h]
0x1400a69e1  test    al, 8
0x1400a69e3  jz      short loc_1400A69ED
0x1400a69e5  test    al, 10h
0x1400a69e7  jz      loc_1400A6DAA
0x1400a69ed  xor     eax, eax
0x1400a69ef  mov     [rsp+1C0h+var_160], rbx
0x1400a69f4  mov     r13d, 100000h
0x1400a69fa  mov     [rsp+1C0h+var_170], rax
0x1400a69ff  xorps   xmm0, xmm0
0x1400a6a02  mov     rsi, rbx
0x1400a6a05  movups  [rsp+1C0h+var_180], xmm0
0x1400a6a0a  cmp     r14, r13
0x1400a6a0d  jnb     short loc_1400A6A12
0x1400a6a0f  mov     r13d, r14d
0x1400a6a12  mov     r15d, r13d
0x1400a6a15  mov     r8d, 30455646h
0x1400a6a1b  mov     edx, r13d
0x1400a6a1e  mov     ecx, 48h ; 'H'
0x1400a6a23  mov     [rsp+1C0h+var_148], r15
0x1400a6a28  call    cs:__imp_ExAllocatePool2
0x1400a6a2f  nop     dword ptr [rax+rax+00h]
0x1400a6a34  mov     r12, rax
0x1400a6a37  test    rax, rax
0x1400a6a3a  jnz     short loc_1400A6A46
0x1400a6a3c  mov     ebx, 0C000009Ah
0x1400a6a41  jmp     loc_1400A6E49
0x1400a6a46  mov     r8d, 30455646h
0x1400a6a4c  mov     rdx, r15
0x1400a6a4f  mov     ecx, 48h ; 'H'
0x1400a6a54  call    cs:__imp_ExAllocatePool2
0x1400a6a5b  nop     dword ptr [rax+rax+00h]
0x1400a6a60  mov     [rsp+1C0h+Source2], rax
0x1400a6a65  test    rax, rax
0x1400a6a68  jnz     short loc_1400A6A74
0x1400a6a6a  mov     ebx, 0C000009Ah
0x1400a6a6f  jmp     loc_1400A6E18
0x1400a6a74  mov     [rsp+1C0h+var_158], rbx
0x1400a6a79  mov     rax, rbx
0x1400a6a7c  test    r14, r14
0x1400a6a7f  jz      loc_1400A6E18
0x1400a6a85  cmp     r14, r15
0x1400a6a88  mov     r15d, r14d
0x1400a6a8b  jb      short loc_1400A6A90
0x1400a6a8d  mov     r15d, r13d
0x1400a6a90  mov     rdx, [rdi+70h]
0x1400a6a94  xor     r9d, r9d
0x1400a6a97  mov     [rsp+1C0h+var_188], r12
0x1400a6a9c  mov     rcx, rdi
0x1400a6a9f  mov     [rsp+1C0h+var_190], r15d
0x1400a6aa4  mov     [rsp+1C0h+var_198], rax
0x1400a6aa9  lea     r8d, [r9+3]
0x1400a6aad  mov     [rsp+1C0h+BugCheckParameter4], 0
0x1400a6ab6  call    FveRawIoSynchronous
0x1400a6abb  mov     ebx, eax
0x1400a6abd  test    eax, eax
0x1400a6abf  js      loc_1400A6DE4
0x1400a6ac5  xor     ebx, ebx
0x1400a6ac7  cmp     [rdi+3D0h], rbx
0x1400a6ace  jz      short loc_1400A6B32
0x1400a6ad0  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400a6ad5  xor     r9d, r9d
0x1400a6ad8  mov     [rsp+1C0h+var_198], rbx
0x1400a6add  mov     r8b, 1
0x1400a6ae0  mov     [rsp+1C0h+BugCheckParameter4], rbx
0x1400a6ae5  lea     rdx, [rbp+0C0h+var_140]
0x1400a6ae9  mov     rcx, rdi
0x1400a6aec  call    InitializeFilterData
0x1400a6af1  mov     rax, [rsp+1C0h+var_158]
0x1400a6af6  lea     rcx, [rbp+0C0h+var_140]
0x1400a6afa  mov     [rbp+0C0h+var_130], rax
0x1400a6afe  lea     rax, FveFilteredRead
0x1400a6b05  mov     [rbp+0C0h+var_E8], rax
0x1400a6b09  mov     [rbp+0C0h+var_D0], r15d
0x1400a6b0d  mov     [rbp+0C0h+var_E0], r12
0x1400a6b11  mov     [rbp+0C0h+var_D8], r12
0x1400a6b15  call    FveParseBlockAndFilter
0x1400a6b1a  lea     rdx, [rbp+0C0h+var_140]
0x1400a6b1e  mov     rcx, rdi
0x1400a6b21  mov     ebx, eax
0x1400a6b23  call    DeInitializeFilterData
0x1400a6b28  test    ebx, ebx
0x1400a6b2a  js      loc_1400A6DE4
0x1400a6b30  xor     ebx, ebx
0x1400a6b32  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400a6b37  test    eax, eax
0x1400a6b39  jnz     short loc_1400A6B44
0x1400a6b3b  cmp     [rdi+3D0h], rbx
0x1400a6b42  jmp     short loc_1400A6B54
0x1400a6b44  cmp     [rdi+3D0h], rbx
0x1400a6b4b  jnz     short loc_1400A6B5A
0x1400a6b4d  test    byte ptr [rdi+1133h], 10h
0x1400a6b54  jz      loc_1400A6C5A
0x1400a6b5a  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400a6b5f  test    eax, eax
0x1400a6b61  jnz     short loc_1400A6B6D
0x1400a6b63  mov     [rsp+1C0h+var_198], rbx
0x1400a6b68  jmp     loc_1400A6C02
0x1400a6b6d  mov     rax, [rdi+1280h]
0x1400a6b74  test    rax, rax
0x1400a6b77  jz      loc_1400A6BFD
0x1400a6b7d  cmp     [rax+58h], ebx
0x1400a6b80  jz      short loc_1400A6BFD
0x1400a6b82  test    rsi, rsi
0x1400a6b85  jnz     short loc_1400A6BFD
0x1400a6b87  cmp     [rdi+3F0h], rbx
0x1400a6b8e  jnz     loc_1400A6DAA
0x1400a6b94  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6b9b  lea     rsi, WPP_GLOBAL_Control
0x1400a6ba2  cmp     rcx, rsi
0x1400a6ba5  jz      short loc_1400A6BC9
0x1400a6ba7  mov     eax, [rcx+2Ch]
0x1400a6baa  test    al, 4
0x1400a6bac  jz      short loc_1400A6BC9
0x1400a6bae  cmp     byte ptr [rcx+29h], 5
0x1400a6bb2  jb      short loc_1400A6BC9
0x1400a6bb4  mov     rcx, [rcx+18h]
0x1400a6bb8  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400a6bbf  mov     edx, 60h ; '`'
0x1400a6bc4  call    WPP_SF_
0x1400a6bc9  mov     rcx, [rdi+3D0h]
0x1400a6bd0  lea     r9, [rsp+1C0h+var_160]
0x1400a6bd5  mov     r8d, [rdi+51Ch]
0x1400a6bdc  add     rcx, 40h ; '@'
0x1400a6be0  mov     rdx, [rdi+3F8h]
0x1400a6be7  call    ExtractFvek
0x1400a6bec  mov     ebx, eax
0x1400a6bee  test    eax, eax
0x1400a6bf0  js      loc_1400A6D72
0x1400a6bf6  mov     rsi, [rsp+1C0h+var_160]
0x1400a6bfb  xor     ebx, ebx
0x1400a6bfd  mov     [rsp+1C0h+var_198], rsi
0x1400a6c02  xor     r9d, r9d
0x1400a6c05  mov     [rsp+1C0h+BugCheckParameter4], rbx
0x1400a6c0a  mov     r8b, 1
0x1400a6c0d  lea     rdx, [rbp+0C0h+var_140]
0x1400a6c11  mov     rcx, rdi
0x1400a6c14  call    InitializeFilterData
0x1400a6c19  mov     rax, [rsp+1C0h+var_168]
0x1400a6c1e  lea     rcx, [rbp+0C0h+var_140]
0x1400a6c22  mov     [rbp+0C0h+var_130], rax
0x1400a6c26  lea     rax, FveFilteredWrite
0x1400a6c2d  mov     [rbp+0C0h+var_E8], rax
0x1400a6c31  mov     [rbp+0C0h+var_D0], r15d
0x1400a6c35  mov     [rbp+0C0h+var_E0], r12
0x1400a6c39  mov     [rbp+0C0h+var_D8], r12
0x1400a6c3d  call    FveParseBlockAndFilter
0x1400a6c42  lea     rdx, [rbp+0C0h+var_140]
0x1400a6c46  mov     rcx, rdi
0x1400a6c49  mov     ebx, eax
0x1400a6c4b  call    DeInitializeFilterData
0x1400a6c50  test    ebx, ebx
0x1400a6c52  js      loc_1400A6EC4
0x1400a6c58  xor     ebx, ebx
0x1400a6c5a  mov     rax, [rsp+1C0h+var_168]
0x1400a6c5f  xor     r9d, r9d
0x1400a6c62  mov     rdx, [rdi+70h]
0x1400a6c66  mov     rcx, rdi
0x1400a6c69  mov     [rsp+1C0h+var_188], r12
0x1400a6c6e  mov     [rsp+1C0h+var_190], r15d
0x1400a6c73  mov     [rsp+1C0h+var_198], rax
0x1400a6c78  lea     r8d, [r9+4]
0x1400a6c7c  mov     [rsp+1C0h+BugCheckParameter4], rbx
0x1400a6c81  call    FveRawIoSynchronous
0x1400a6c86  mov     ebx, eax
0x1400a6c88  xor     eax, eax
0x1400a6c8a  test    ebx, ebx
0x1400a6c8c  js      loc_1400A6EC4
0x1400a6c92  mov     rdx, [rdi+70h]
0x1400a6c96  lea     r8d, [rax+9]
0x1400a6c9a  mov     [rsp+1C0h+var_188], rax
0x1400a6c9f  xor     r9d, r9d
0x1400a6ca2  mov     [rsp+1C0h+var_190], eax
0x1400a6ca6  mov     rcx, rdi
0x1400a6ca9  mov     [rsp+1C0h+var_198], rax
0x1400a6cae  mov     [rsp+1C0h+BugCheckParameter4], rax
0x1400a6cb3  call    FveRawIoSynchronous
0x1400a6cb8  mov     ebx, eax
0x1400a6cba  cmp     eax, 0C0000002h
0x1400a6cbf  jz      short loc_1400A6CD7
0x1400a6cc1  cmp     eax, 0C0000010h
0x1400a6cc6  jz      short loc_1400A6CD7
0x1400a6cc8  cmp     eax, 0C00000BBh
0x1400a6ccd  jz      short loc_1400A6CD7
0x1400a6ccf  test    eax, eax
0x1400a6cd1  js      loc_1400A6DCB
0x1400a6cd7  mov     rax, [rsp+1C0h+Source2]
0x1400a6cdc  xor     r9d, r9d
0x1400a6cdf  mov     rdx, [rdi+70h]
0x1400a6ce3  mov     rcx, rdi
0x1400a6ce6  mov     [rsp+1C0h+var_188], rax
0x1400a6ceb  mov     rax, [rsp+1C0h+var_168]
0x1400a6cf0  mov     [rsp+1C0h+var_190], r15d
0x1400a6cf5  lea     r8d, [r9+3]
0x1400a6cf9  mov     [rsp+1C0h+var_198], rax
0x1400a6cfe  mov     [rsp+1C0h+BugCheckParameter4], 0
0x1400a6d07  call    FveRawIoSynchronous
0x1400a6d0c  mov     ebx, eax
0x1400a6d0e  test    eax, eax
0x1400a6d10  js      loc_1400A6DE4
0x1400a6d16  mov     rdx, [rsp+1C0h+Source2]; Source2
0x1400a6d1b  mov     rcx, r12; Source1
0x1400a6d1e  mov     r8d, r15d; Length
0x1400a6d21  mov     ebx, r15d
0x1400a6d24  call    cs:__imp_RtlCompareMemory
0x1400a6d2b  nop     dword ptr [rax+rax+00h]
0x1400a6d30  cmp     rax, rbx
0x1400a6d33  jnz     loc_1400A6DDF
0x1400a6d39  mov     rax, [rsp+1C0h+var_168]
0x1400a6d3e  lea     rcx, [rbx+rax]
0x1400a6d42  cmp     rcx, rax
0x1400a6d45  jb      loc_1400A6DD8
0x1400a6d4b  mov     rdx, [rsp+1C0h+var_158]
0x1400a6d50  lea     rax, [rbx+rdx]
0x1400a6d54  cmp     rax, rdx
0x1400a6d57  jb      short loc_1400A6DD8
0x1400a6d59  sub     r14, rbx
0x1400a6d5c  jz      short loc_1400A6DD4
0x1400a6d5e  mov     r15, [rsp+1C0h+var_148]
0x1400a6d63  mov     [rsp+1C0h+var_158], rax
0x1400a6d68  mov     [rsp+1C0h+var_168], rcx
0x1400a6d6d  jmp     loc_1400A6A85
0x1400a6d72  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6d79  cmp     rcx, rsi
0x1400a6d7c  jz      short loc_1400A6DA3
0x1400a6d7e  mov     eax, [rcx+2Ch]
0x1400a6d81  test    al, 4
0x1400a6d83  jz      short loc_1400A6DA3
0x1400a6d85  cmp     byte ptr [rcx+29h], 2
0x1400a6d89  jb      short loc_1400A6DA3
0x1400a6d8b  mov     rcx, [rcx+18h]
0x1400a6d8f  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400a6d96  mov     edx, 61h ; 'a'
0x1400a6d9b  mov     r9d, ebx
0x1400a6d9e  call    WPP_SF_d
0x1400a6da3  mov     rsi, [rsp+1C0h+var_160]
0x1400a6da8  jmp     short loc_1400A6E18
0x1400a6daa  xor     r9d, r9d; BugCheckParameter3
0x1400a6dad  mov     [rsp+1C0h+BugCheckParameter4], rbx; BugCheckParameter4
0x1400a6db2  xor     r8d, r8d; BugCheckParameter2
0x1400a6db5  mov     ecx, 120h; BugCheckCode
0x1400a6dba  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400a6dbe  call    cs:__imp_KeBugCheckEx
0x1400a6dcb  lea     rax, FVE_METADATA_DISK_FAILED_FLUSH_ERROR
0x1400a6dd2  jmp     short loc_1400A6DEB
0x1400a6dd4  xor     ebx, ebx
0x1400a6dd6  jmp     short loc_1400A6E18
0x1400a6dd8  mov     ebx, 0C0000095h
0x1400a6ddd  jmp     short loc_1400A6E18
0x1400a6ddf  mov     ebx, 0C0000001h
0x1400a6de4  lea     rax, FVE_METADATA_DISK_FAILED_READBACK_ERROR
0x1400a6deb  mov     rcx, [rdi]
0x1400a6dee  lea     rdx, [rsp+1C0h+var_180]
0x1400a6df3  mov     r9b, 1
0x1400a6df6  mov     qword ptr [rsp+1C0h+var_180], rax
0x1400a6dfb  xor     r8d, r8d
0x1400a6dfe  mov     dword ptr [rsp+1C0h+var_180+8], 0FFFFFFFFh
0x1400a6e06  mov     dword ptr [rsp+1C0h+var_180+0Ch], ebx
0x1400a6e0a  mov     [rsp+1C0h+var_170], 0
  ... truncated ...
```
