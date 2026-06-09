# FveBackupBootSectors

- ea: `0x1400a7898`
- end: `0x1400a7e28`
- name: `FveBackupBootSectors`
- size: `1424`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14009fb70`
- `0x1400a2f54`

## callees

- `0x140001580`
- `0x140008348`
- `0x140008e80`
- `0x140008f04`
- `0x140009cb4`
- `0x140022bf0`
- `0x140023040`
- `0x14009edc4`
- `0x1400a7898`
- `0x1400b6f14`
- `0x1400d8170`
- `0x1400dbd00`
- `0x1400e1690`
- `0x1400e859c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400a7c7c`
- `ntoskrnl!RtlCompareMemory` at `0x1400a7c7c`
- `ntoskrnl!KeBugCheckEx` at `0x1400a7d16`
- `ntoskrnl!KeBugCheckEx` at `0x1400a7d16`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7d7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7d95`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7d7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7d95`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7980`
- `ntoskrnl!ExAllocatePool2` at `0x1400a79ac`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7980`
- `ntoskrnl!ExAllocatePool2` at `0x1400a79ac`

## pseudocode

```c
__int64 __fastcall FveBackupBootSectors(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  __int64 v5; // rdx
  PDEVICE_OBJECT v6; // rcx
  int v7; // ebx
  char v8; // al
  unsigned int v9; // r13d
  void *v10; // rsi
  unsigned __int64 v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int8 *Pool2; // r12
  unsigned __int64 v15; // rax
  bool v16; // cf
  unsigned int v17; // r15d
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  bool v23; // zf
  __int64 v24; // r8
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rbx
  __int64 *v28; // rax
  __int64 v29; // rcx
  void *v31; // [rsp+28h] [rbp-D8h]
  __int128 v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v34; // [rsp+58h] [rbp-A8h]
  void *v35; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v36; // [rsp+68h] [rbp-98h]
  void *Source2; // [rsp+70h] [rbp-90h]
  unsigned __int64 v38; // [rsp+78h] [rbp-88h]
  _QWORD v39[32]; // [rsp+80h] [rbp-80h] BYREF

  v34 = a2;
  memset(v39, 0, sizeof(v39));
  v32 = 0;
  v33 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids);
  }
  v7 = 0;
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v6, v5) )
  {
    v8 = *(_BYTE *)(a1 + 4419);
    if ( (v8 & 8) != 0 && (v8 & 0x10) == 0 )
LABEL_55:
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  v35 = 0;
  v9 = 0x100000;
  v33 = 0;
  v10 = 0;
  v32 = 0;
  if ( a3 < 0x100000 )
    v9 = a3;
  v11 = v9;
  v38 = v9;
  Pool2 = (unsigned __int8 *)ExAllocatePool2(72, v9, 809850438);
  if ( !Pool2 )
  {
    v7 = -1073741670;
    goto LABEL_64;
  }
  Source2 = (void *)ExAllocatePool2(72, v9, 809850438);
  if ( !Source2 )
  {
    v7 = -1073741670;
    goto LABEL_62;
  }
  v36 = 0;
  v15 = 0;
  if ( !a3 )
    goto LABEL_62;
  while ( 1 )
  {
    v16 = a3 < v11;
    v17 = a3;
    if ( !v16 )
      v17 = v9;
    v7 = FveRawIoSynchronous(a1, *(struct _DEVICE_OBJECT **)(a1 + 112), 3u, 0, 0, v15, v17, Pool2);
    if ( v7 < 0 )
      goto LABEL_60;
    if ( *(_QWORD *)(a1 + 976) )
    {
      Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v19, v18);
      LOBYTE(v20) = 1;
      InitializeFilterData(a1, v39, v20, 0, 0, 0);
      v39[2] = v36;
      v39[11] = FveFilteredRead;
      LODWORD(v39[14]) = v17;
      v39[12] = Pool2;
      v39[13] = Pool2;
      v7 = FveParseBlockAndFilter(v39);
      DeInitializeFilterData(a1, v39);
      if ( v7 < 0 )
        goto LABEL_60;
    }
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v19, v18) )
    {
      if ( *(_QWORD *)(a1 + 976) )
        goto LABEL_25;
      v23 = (*(_BYTE *)(a1 + 4419) & 0x10) == 0;
    }
    else
    {
      v23 = *(_QWORD *)(a1 + 976) == 0;
    }
    if ( v23 )
      goto LABEL_39;
LABEL_25:
    if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v22, v21) )
    {
      v31 = 0;
      goto LABEL_38;
    }
    v25 = *(_QWORD *)(a1 + 4752);
    if ( v25 )
    {
      if ( *(_DWORD *)(v25 + 88) && !v10 )
        break;
    }
LABEL_37:
    v31 = v10;
LABEL_38:
    LOBYTE(v24) = 1;
    InitializeFilterData(a1, v39, v24, 0, 0, v31);
    v39[2] = v34;
    v39[11] = FveFilteredWrite;
    LODWORD(v39[14]) = v17;
    v39[12] = Pool2;
    v39[13] = Pool2;
    v7 = FveParseBlockAndFilter(v39);
    DeInitializeFilterData(a1, v39);
    if ( v7 < 0 )
      goto LABEL_72;
LABEL_39:
    v7 = FveRawIoSynchronous(a1, *(struct _DEVICE_OBJECT **)(a1 + 112), 4u, 0, 0, v34, v17, Pool2);
    if ( v7 < 0 )
    {
LABEL_72:
      v28 = FVE_METADATA_FAILED_COMMIT;
      goto LABEL_61;
    }
    v26 = FveRawIoSynchronous(a1, *(struct _DEVICE_OBJECT **)(a1 + 112), 9u, 0, 0, 0, 0, 0);
    v7 = v26;
    if ( v26 != -1073741822 && v26 != -1073741808 && v26 != -1073741637 && v26 < 0 )
    {
      v28 = FVE_METADATA_DISK_FAILED_FLUSH_ERROR;
      goto LABEL_61;
    }
    v7 = FveRawIoSynchronous(a1, *(struct _DEVICE_OBJECT **)(a1 + 112), 3u, 0, 0, v34, v17, (unsigned __int8 *)Source2);
    if ( v7 < 0 )
      goto LABEL_60;
    v27 = v17;
    if ( RtlCompareMemory(Pool2, Source2, v17) != v17 )
    {
      v7 = -1073741823;
LABEL_60:
      v28 = FVE_METADATA_DISK_FAILED_READBACK_ERROR;
LABEL_61:
      v29 = *(_QWORD *)a1;
      *(_QWORD *)&v32 = v28;
      DWORD2(v32) = -1;
      HIDWORD(v32) = v7;
      v33 = 0;
      FveLogEventEx(v29, (const EVENT_DESCRIPTOR **)&v32, 0, 1);
      goto LABEL_62;
    }
    if ( v17 + v34 < v34 || (v15 = v17 + v36, v15 < v36) )
    {
      v7 = -1073741675;
      goto LABEL_62;
    }
    a3 -= v17;
    if ( !a3 )
    {
      v7 = 0;
      goto LABEL_62;
    }
    v11 = v38;
    v36 += v27;
    v34 += v27;
  }
  if ( *(_QWORD *)(a1 + 1008) )
    goto LABEL_55;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids);
  }
  v7 = ExtractFvek(*(_QWORD *)(a1 + 976) + 64LL, *(_QWORD *)(a1 + 1016), *(unsigned int *)(a1 + 1308), &v35);
  if ( v7 >= 0 )
  {
    v10 = v35;
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, (unsigned int)v7);
  }
  v10 = v35;
LABEL_62:
  ExFreePoolWithTag(Pool2, 0x30455646u);
  if ( Source2 )
    ExFreePoolWithTag(Source2, 0x30455646u);
LABEL_64:
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v13, v12) && v10 )
    DeleteKey(v10);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400a7898  mov     [rsp-8+arg_18], rbx
0x1400a789d  push    rbp
0x1400a789e  push    rsi
0x1400a789f  push    rdi
0x1400a78a0  push    r12
0x1400a78a2  push    r13
0x1400a78a4  push    r14
0x1400a78a6  push    r15
0x1400a78a8  lea     rbp, [rsp-90h]
0x1400a78b0  sub     rsp, 190h
0x1400a78b7  mov     rax, cs:__security_cookie
0x1400a78be  xor     rax, rsp
0x1400a78c1  mov     [rbp+0C0h+var_40], rax
0x1400a78c8  mov     r14, r8
0x1400a78cb  mov     [rsp+1C0h+var_168], rdx
0x1400a78d0  mov     rdi, rcx
0x1400a78d3  xor     edx, edx; Val
0x1400a78d5  mov     r8d, 100h; Size
0x1400a78db  lea     rcx, [rbp+0C0h+var_140]; void *
0x1400a78df  call    memset
0x1400a78e4  xorps   xmm0, xmm0
0x1400a78e7  xor     eax, eax
0x1400a78e9  movups  [rsp+1C0h+var_180], xmm0
0x1400a78ee  mov     [rsp+1C0h+var_170], rax
0x1400a78f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a78fa  lea     rax, WPP_GLOBAL_Control
0x1400a7901  cmp     rcx, rax
0x1400a7904  jz      short loc_1400A7928
0x1400a7906  mov     eax, [rcx+2Ch]
0x1400a7909  test    al, 4
0x1400a790b  jz      short loc_1400A7928
0x1400a790d  cmp     byte ptr [rcx+29h], 5
0x1400a7911  jb      short loc_1400A7928
0x1400a7913  mov     rcx, [rcx+18h]
0x1400a7917  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400a791e  mov     edx, 5Fh ; '_'
0x1400a7923  call    WPP_SF_
0x1400a7928  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400a792d  xor     ebx, ebx
0x1400a792f  test    eax, eax
0x1400a7931  jz      short loc_1400A7945
0x1400a7933  mov     al, [rdi+1143h]
0x1400a7939  test    al, 8
0x1400a793b  jz      short loc_1400A7945
0x1400a793d  test    al, 10h
0x1400a793f  jz      loc_1400A7D02
0x1400a7945  xor     eax, eax
0x1400a7947  mov     [rsp+1C0h+var_160], rbx
0x1400a794c  mov     r13d, 100000h
0x1400a7952  mov     [rsp+1C0h+var_170], rax
0x1400a7957  xorps   xmm0, xmm0
0x1400a795a  mov     rsi, rbx
0x1400a795d  movups  [rsp+1C0h+var_180], xmm0
0x1400a7962  cmp     r14, r13
0x1400a7965  jnb     short loc_1400A796A
0x1400a7967  mov     r13d, r14d
0x1400a796a  mov     r15d, r13d
0x1400a796d  mov     r8d, 30455646h
0x1400a7973  mov     edx, r13d
0x1400a7976  mov     ecx, 48h ; 'H'
0x1400a797b  mov     [rsp+1C0h+var_148], r15
0x1400a7980  call    cs:__imp_ExAllocatePool2
0x1400a7987  nop     dword ptr [rax+rax+00h]
0x1400a798c  mov     r12, rax
0x1400a798f  test    rax, rax
0x1400a7992  jnz     short loc_1400A799E
0x1400a7994  mov     ebx, 0C000009Ah
0x1400a7999  jmp     loc_1400A7DA1
0x1400a799e  mov     r8d, 30455646h
0x1400a79a4  mov     rdx, r15
0x1400a79a7  mov     ecx, 48h ; 'H'
0x1400a79ac  call    cs:__imp_ExAllocatePool2
0x1400a79b3  nop     dword ptr [rax+rax+00h]
0x1400a79b8  mov     [rsp+1C0h+Source2], rax
0x1400a79bd  test    rax, rax
0x1400a79c0  jnz     short loc_1400A79CC
0x1400a79c2  mov     ebx, 0C000009Ah
0x1400a79c7  jmp     loc_1400A7D70
0x1400a79cc  mov     [rsp+1C0h+var_158], rbx
0x1400a79d1  mov     rax, rbx
0x1400a79d4  test    r14, r14
0x1400a79d7  jz      loc_1400A7D70
0x1400a79dd  cmp     r14, r15
0x1400a79e0  mov     r15d, r14d
0x1400a79e3  jb      short loc_1400A79E8
0x1400a79e5  mov     r15d, r13d
0x1400a79e8  mov     rdx, [rdi+70h]
0x1400a79ec  xor     r9d, r9d
0x1400a79ef  mov     [rsp+1C0h+var_188], r12
0x1400a79f4  mov     rcx, rdi
0x1400a79f7  mov     [rsp+1C0h+var_190], r15d
0x1400a79fc  mov     [rsp+1C0h+var_198], rax
0x1400a7a01  lea     r8d, [r9+3]
0x1400a7a05  mov     [rsp+1C0h+BugCheckParameter4], 0
0x1400a7a0e  call    FveRawIoSynchronous
0x1400a7a13  mov     ebx, eax
0x1400a7a15  test    eax, eax
0x1400a7a17  js      loc_1400A7D3C
0x1400a7a1d  xor     ebx, ebx
0x1400a7a1f  cmp     [rdi+3D0h], rbx
0x1400a7a26  jz      short loc_1400A7A8A
0x1400a7a28  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400a7a2d  xor     r9d, r9d
0x1400a7a30  mov     [rsp+1C0h+var_198], rbx
0x1400a7a35  mov     r8b, 1
0x1400a7a38  mov     [rsp+1C0h+BugCheckParameter4], rbx
0x1400a7a3d  lea     rdx, [rbp+0C0h+var_140]
0x1400a7a41  mov     rcx, rdi
0x1400a7a44  call    InitializeFilterData
0x1400a7a49  mov     rax, [rsp+1C0h+var_158]
0x1400a7a4e  lea     rcx, [rbp+0C0h+var_140]
0x1400a7a52  mov     [rbp+0C0h+var_130], rax
0x1400a7a56  lea     rax, FveFilteredRead
0x1400a7a5d  mov     [rbp+0C0h+var_E8], rax
0x1400a7a61  mov     [rbp+0C0h+var_D0], r15d
0x1400a7a65  mov     [rbp+0C0h+var_E0], r12
0x1400a7a69  mov     [rbp+0C0h+var_D8], r12
0x1400a7a6d  call    FveParseBlockAndFilter
0x1400a7a72  lea     rdx, [rbp+0C0h+var_140]
0x1400a7a76  mov     rcx, rdi
0x1400a7a79  mov     ebx, eax
0x1400a7a7b  call    DeInitializeFilterData
0x1400a7a80  test    ebx, ebx
0x1400a7a82  js      loc_1400A7D3C
0x1400a7a88  xor     ebx, ebx
0x1400a7a8a  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400a7a8f  test    eax, eax
0x1400a7a91  jnz     short loc_1400A7A9C
0x1400a7a93  cmp     [rdi+3D0h], rbx
0x1400a7a9a  jmp     short loc_1400A7AAC
0x1400a7a9c  cmp     [rdi+3D0h], rbx
0x1400a7aa3  jnz     short loc_1400A7AB2
0x1400a7aa5  test    byte ptr [rdi+1143h], 10h
0x1400a7aac  jz      loc_1400A7BB2
0x1400a7ab2  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400a7ab7  test    eax, eax
0x1400a7ab9  jnz     short loc_1400A7AC5
0x1400a7abb  mov     [rsp+1C0h+var_198], rbx
0x1400a7ac0  jmp     loc_1400A7B5A
0x1400a7ac5  mov     rax, [rdi+1290h]
0x1400a7acc  test    rax, rax
0x1400a7acf  jz      loc_1400A7B55
0x1400a7ad5  cmp     [rax+58h], ebx
0x1400a7ad8  jz      short loc_1400A7B55
0x1400a7ada  test    rsi, rsi
0x1400a7add  jnz     short loc_1400A7B55
0x1400a7adf  cmp     [rdi+3F0h], rbx
0x1400a7ae6  jnz     loc_1400A7D02
0x1400a7aec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7af3  lea     rsi, WPP_GLOBAL_Control
0x1400a7afa  cmp     rcx, rsi
0x1400a7afd  jz      short loc_1400A7B21
0x1400a7aff  mov     eax, [rcx+2Ch]
0x1400a7b02  test    al, 4
0x1400a7b04  jz      short loc_1400A7B21
0x1400a7b06  cmp     byte ptr [rcx+29h], 5
0x1400a7b0a  jb      short loc_1400A7B21
0x1400a7b0c  mov     rcx, [rcx+18h]
0x1400a7b10  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400a7b17  mov     edx, 60h ; '`'
0x1400a7b1c  call    WPP_SF_
0x1400a7b21  mov     rcx, [rdi+3D0h]
0x1400a7b28  lea     r9, [rsp+1C0h+var_160]
0x1400a7b2d  mov     r8d, [rdi+51Ch]
0x1400a7b34  add     rcx, 40h ; '@'
0x1400a7b38  mov     rdx, [rdi+3F8h]
0x1400a7b3f  call    ExtractFvek
0x1400a7b44  mov     ebx, eax
0x1400a7b46  test    eax, eax
0x1400a7b48  js      loc_1400A7CCA
0x1400a7b4e  mov     rsi, [rsp+1C0h+var_160]
0x1400a7b53  xor     ebx, ebx
0x1400a7b55  mov     [rsp+1C0h+var_198], rsi
0x1400a7b5a  xor     r9d, r9d
0x1400a7b5d  mov     [rsp+1C0h+BugCheckParameter4], rbx
0x1400a7b62  mov     r8b, 1
0x1400a7b65  lea     rdx, [rbp+0C0h+var_140]
0x1400a7b69  mov     rcx, rdi
0x1400a7b6c  call    InitializeFilterData
0x1400a7b71  mov     rax, [rsp+1C0h+var_168]
0x1400a7b76  lea     rcx, [rbp+0C0h+var_140]
0x1400a7b7a  mov     [rbp+0C0h+var_130], rax
0x1400a7b7e  lea     rax, FveFilteredWrite
0x1400a7b85  mov     [rbp+0C0h+var_E8], rax
0x1400a7b89  mov     [rbp+0C0h+var_D0], r15d
0x1400a7b8d  mov     [rbp+0C0h+var_E0], r12
0x1400a7b91  mov     [rbp+0C0h+var_D8], r12
0x1400a7b95  call    FveParseBlockAndFilter
0x1400a7b9a  lea     rdx, [rbp+0C0h+var_140]
0x1400a7b9e  mov     rcx, rdi
0x1400a7ba1  mov     ebx, eax
0x1400a7ba3  call    DeInitializeFilterData
0x1400a7ba8  test    ebx, ebx
0x1400a7baa  js      loc_1400A7E1C
0x1400a7bb0  xor     ebx, ebx
0x1400a7bb2  mov     rax, [rsp+1C0h+var_168]
0x1400a7bb7  xor     r9d, r9d
0x1400a7bba  mov     rdx, [rdi+70h]
0x1400a7bbe  mov     rcx, rdi
0x1400a7bc1  mov     [rsp+1C0h+var_188], r12
0x1400a7bc6  mov     [rsp+1C0h+var_190], r15d
0x1400a7bcb  mov     [rsp+1C0h+var_198], rax
0x1400a7bd0  lea     r8d, [r9+4]
0x1400a7bd4  mov     [rsp+1C0h+BugCheckParameter4], rbx
0x1400a7bd9  call    FveRawIoSynchronous
0x1400a7bde  mov     ebx, eax
0x1400a7be0  xor     eax, eax
0x1400a7be2  test    ebx, ebx
0x1400a7be4  js      loc_1400A7E1C
0x1400a7bea  mov     rdx, [rdi+70h]
0x1400a7bee  lea     r8d, [rax+9]
0x1400a7bf2  mov     [rsp+1C0h+var_188], rax
0x1400a7bf7  xor     r9d, r9d
0x1400a7bfa  mov     [rsp+1C0h+var_190], eax
0x1400a7bfe  mov     rcx, rdi
0x1400a7c01  mov     [rsp+1C0h+var_198], rax
0x1400a7c06  mov     [rsp+1C0h+BugCheckParameter4], rax
0x1400a7c0b  call    FveRawIoSynchronous
0x1400a7c10  mov     ebx, eax
0x1400a7c12  cmp     eax, 0C0000002h
0x1400a7c17  jz      short loc_1400A7C2F
0x1400a7c19  cmp     eax, 0C0000010h
0x1400a7c1e  jz      short loc_1400A7C2F
0x1400a7c20  cmp     eax, 0C00000BBh
0x1400a7c25  jz      short loc_1400A7C2F
0x1400a7c27  test    eax, eax
0x1400a7c29  js      loc_1400A7D23
0x1400a7c2f  mov     rax, [rsp+1C0h+Source2]
0x1400a7c34  xor     r9d, r9d
0x1400a7c37  mov     rdx, [rdi+70h]
0x1400a7c3b  mov     rcx, rdi
0x1400a7c3e  mov     [rsp+1C0h+var_188], rax
0x1400a7c43  mov     rax, [rsp+1C0h+var_168]
0x1400a7c48  mov     [rsp+1C0h+var_190], r15d
0x1400a7c4d  lea     r8d, [r9+3]
0x1400a7c51  mov     [rsp+1C0h+var_198], rax
0x1400a7c56  mov     [rsp+1C0h+BugCheckParameter4], 0
0x1400a7c5f  call    FveRawIoSynchronous
0x1400a7c64  mov     ebx, eax
0x1400a7c66  test    eax, eax
0x1400a7c68  js      loc_1400A7D3C
0x1400a7c6e  mov     rdx, [rsp+1C0h+Source2]; Source2
0x1400a7c73  mov     rcx, r12; Source1
0x1400a7c76  mov     r8d, r15d; Length
0x1400a7c79  mov     ebx, r15d
0x1400a7c7c  call    cs:__imp_RtlCompareMemory
0x1400a7c83  nop     dword ptr [rax+rax+00h]
0x1400a7c88  cmp     rax, rbx
0x1400a7c8b  jnz     loc_1400A7D37
0x1400a7c91  mov     rax, [rsp+1C0h+var_168]
0x1400a7c96  lea     rcx, [rbx+rax]
0x1400a7c9a  cmp     rcx, rax
0x1400a7c9d  jb      loc_1400A7D30
0x1400a7ca3  mov     rdx, [rsp+1C0h+var_158]
0x1400a7ca8  lea     rax, [rbx+rdx]
0x1400a7cac  cmp     rax, rdx
0x1400a7caf  jb      short loc_1400A7D30
0x1400a7cb1  sub     r14, rbx
0x1400a7cb4  jz      short loc_1400A7D2C
0x1400a7cb6  mov     r15, [rsp+1C0h+var_148]
0x1400a7cbb  mov     [rsp+1C0h+var_158], rax
0x1400a7cc0  mov     [rsp+1C0h+var_168], rcx
0x1400a7cc5  jmp     loc_1400A79DD
0x1400a7cca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7cd1  cmp     rcx, rsi
0x1400a7cd4  jz      short loc_1400A7CFB
0x1400a7cd6  mov     eax, [rcx+2Ch]
0x1400a7cd9  test    al, 4
0x1400a7cdb  jz      short loc_1400A7CFB
0x1400a7cdd  cmp     byte ptr [rcx+29h], 2
0x1400a7ce1  jb      short loc_1400A7CFB
0x1400a7ce3  mov     rcx, [rcx+18h]
0x1400a7ce7  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400a7cee  mov     edx, 61h ; 'a'
0x1400a7cf3  mov     r9d, ebx
0x1400a7cf6  call    WPP_SF_d
0x1400a7cfb  mov     rsi, [rsp+1C0h+var_160]
0x1400a7d00  jmp     short loc_1400A7D70
0x1400a7d02  xor     r9d, r9d; BugCheckParameter3
0x1400a7d05  mov     [rsp+1C0h+BugCheckParameter4], rbx; BugCheckParameter4
0x1400a7d0a  xor     r8d, r8d; BugCheckParameter2
0x1400a7d0d  mov     ecx, 120h; BugCheckCode
0x1400a7d12  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400a7d16  call    cs:__imp_KeBugCheckEx
0x1400a7d23  lea     rax, FVE_METADATA_DISK_FAILED_FLUSH_ERROR
0x1400a7d2a  jmp     short loc_1400A7D43
0x1400a7d2c  xor     ebx, ebx
0x1400a7d2e  jmp     short loc_1400A7D70
0x1400a7d30  mov     ebx, 0C0000095h
0x1400a7d35  jmp     short loc_1400A7D70
0x1400a7d37  mov     ebx, 0C0000001h
0x1400a7d3c  lea     rax, FVE_METADATA_DISK_FAILED_READBACK_ERROR
0x1400a7d43  mov     rcx, [rdi]
0x1400a7d46  lea     rdx, [rsp+1C0h+var_180]
0x1400a7d4b  mov     r9b, 1
0x1400a7d4e  mov     qword ptr [rsp+1C0h+var_180], rax
0x1400a7d53  xor     r8d, r8d
0x1400a7d56  mov     dword ptr [rsp+1C0h+var_180+8], 0FFFFFFFFh
0x1400a7d5e  mov     dword ptr [rsp+1C0h+var_180+0Ch], ebx
0x1400a7d62  mov     [rsp+1C0h+var_170], 0
  ... truncated ...
```
