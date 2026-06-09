# MouHid_StartDevice

- ea: `0x14000baf0`
- end: `0x14000c107`
- name: `MouHid_StartDevice`
- size: `1559`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x14000b730`

## callees

- `0x140001364`
- `0x140001464`
- `0x140004dd0`
- `0x1400051c0`
- `0x14000b5a4`
- `0x14000baf0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000bd6b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000bd6b`
- `ntoskrnl!IoAllocateMdl` at `0x14000bd4c`
- `ntoskrnl!IoAllocateMdl` at `0x14000bd4c`
- `ntoskrnl!IoFreeMdl` at `0x14000c0c0`
- `ntoskrnl!IoFreeMdl` at `0x14000c0c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0d1`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbcb`
- `ntoskrnl!ExAllocatePool2` at `0x14000bcb1`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbcb`
- `ntoskrnl!ExAllocatePool2` at `0x14000bcb1`
- `HIDPARSE!HidP_GetCaps` at `0x14000bc1e`
- `HIDPARSE!HidP_GetCaps` at `0x14000bc1e`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bda7`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000be61`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bebf`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bf18`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bf7a`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bfeb`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000c04c`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bda7`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000be61`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bebf`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bf18`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bf7a`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000bfeb`
- `HIDPARSE!HidP_GetSpecificValueCaps` at `0x14000c04c`
- `HIDPARSE!HidP_MaxUsageListLength` at `0x14000bc70`
- `HIDPARSE!HidP_MaxUsageListLength` at `0x14000bc70`

## pseudocode

```c
__int64 __fastcall MouHid_StartDevice(__int64 *a1)
{
  int v2; // edx
  NTSTATUS Caps; // esi
  void *PreparsedData; // r14
  _WORD *v5; // rbx
  unsigned __int16 v6; // r12
  unsigned int v7; // esi
  __int64 v8; // r15
  __int64 Pool2; // rax
  void *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  struct _MDL *Mdl; // rax
  __int64 v14; // rcx
  char BitSize; // cl
  LONG PhysicalMax; // eax
  char v17; // cl
  LONG v18; // eax
  USAGE v19; // r9
  USAGE v20; // r9
  struct _MDL *v21; // rcx
  USHORT ValueCapsLength; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+50h] [rbp-B0h]
  _HIDP_CAPS Capabilities; // [rsp+60h] [rbp-A0h] BYREF
  struct _HIDP_VALUE_CAPS ValueCaps; // [rsp+A0h] [rbp-60h] BYREF

  memset(&Capabilities, 0, sizeof(Capabilities));
  v24 = 0;
  v25 = 0;
  ValueCapsLength = 0;
  memset(&ValueCaps, 0, sizeof(ValueCaps));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      5,
      20,
      (__int64)WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids);
  }
  Caps = MouHid_CallHidClass(a1, 721320, 0, 0, &v24, 12);
  if ( Caps < 0 )
    return (unsigned int)Caps;
  PreparsedData = (void *)ExAllocatePool2(64, (unsigned int)v24, 1215655757);
  if ( !PreparsedData )
    return (unsigned int)-1073741670;
  v5 = 0;
  Caps = MouHid_CallHidClass(a1, 721299, 0, 0, PreparsedData, v24);
  if ( Caps < 0 || (Caps = HidP_GetCaps((PHIDP_PREPARSED_DATA)PreparsedData, &Capabilities), Caps < 0) )
  {
LABEL_53:
    ExFreePoolWithTag(PreparsedData, 0);
    if ( v5 )
    {
      v21 = (struct _MDL *)*((_QWORD *)v5 + 18);
      if ( v21 )
        IoFreeMdl(v21);
      ExFreePoolWithTag(v5, 0);
      a1[27] = 0;
    }
    return (unsigned int)Caps;
  }
  if ( Capabilities.UsagePage != 1
    || Capabilities.Usage != 2 && (Capabilities.Usage != 1 || BYTE2(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels)) )
  {
    Caps = -1073741823;
    goto LABEL_53;
  }
  v6 = HidP_MaxUsageListLength(HidP_Input, 9u, (PHIDP_PREPARSED_DATA)PreparsedData);
  v7 = (Capabilities.InputReportByteLength + 7) & 0xFFFFFFF8;
  v8 = (2 * v6 + 7) & 0xFFFFFFF8;
  Pool2 = ExAllocatePool2(64, v7 + 152 + 4 * (_DWORD)v8, 1215655757);
  a1[27] = Pool2;
  v5 = (_WORD *)Pool2;
  if ( !Pool2 )
    goto LABEL_14;
  *(_QWORD *)(Pool2 + 32) = PreparsedData;
  v10 = (void *)(Pool2 + 152);
  *(_HIDP_CAPS *)(Pool2 + 40) = Capabilities;
  v11 = Pool2 + 152 + v7;
  *(_WORD *)(Pool2 + 28) = v6;
  *((_WORD *)a1 + 189) = v6;
  *(_QWORD *)(Pool2 + 104) = Pool2 + 152;
  *(_QWORD *)(Pool2 + 120) = v11;
  *(_QWORD *)(Pool2 + 112) = v11 + v8;
  v12 = (unsigned int)v8 + v11 + v8;
  *((_QWORD *)v5 + 16) = v12;
  *((_QWORD *)v5 + 17) = (unsigned int)v8 + v12;
  Mdl = IoAllocateMdl(v10, Capabilities.InputReportByteLength, 0, 0, 0);
  *((_QWORD *)v5 + 18) = Mdl;
  if ( !Mdl )
  {
LABEL_14:
    Caps = -1073741670;
    goto LABEL_53;
  }
  MmBuildMdlForNonPagedPool(Mdl);
  ValueCapsLength = 1;
  Caps = HidP_GetSpecificValueCaps(
           HidP_Input,
           1u,
           0,
           0x30u,
           &ValueCaps,
           &ValueCapsLength,
           (PHIDP_PREPARSED_DATA)PreparsedData);
  if ( Caps < 0 )
    goto LABEL_53;
  if ( ValueCaps.IsAbsolute )
  {
    if ( Capabilities.Usage == 1 && BYTE1(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels)
      || !LOBYTE(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels) )
    {
      *((_WORD *)a1 + 177) = 1;
      *((_BYTE *)v5 + 16) = 1;
    }
    else
    {
      *((_WORD *)a1 + 177) = 0;
      *((_BYTE *)v5 + 16) = 0;
      v14 = *a1;
      *((_DWORD *)a1 + 30) |= 1u;
      MouHid_LogError(*(void **)(v14 + 8), -2147155966);
    }
  }
  else
  {
    *((_WORD *)a1 + 177) = 0;
    *((_BYTE *)v5 + 16) = 0;
  }
  BitSize = ValueCaps.BitSize;
  *v5 = ValueCaps.BitSize;
  PhysicalMax = ValueCaps.PhysicalMax;
  if ( !ValueCaps.PhysicalMax )
    PhysicalMax = (1 << (BitSize - 1)) - 1;
  *((_DWORD *)v5 + 2) = PhysicalMax;
  ValueCapsLength = 1;
  Caps = HidP_GetSpecificValueCaps(
           HidP_Input,
           1u,
           0,
           0x31u,
           &ValueCaps,
           &ValueCapsLength,
           (PHIDP_PREPARSED_DATA)PreparsedData);
  if ( Caps < 0 )
    goto LABEL_53;
  v17 = ValueCaps.BitSize;
  v5[1] = ValueCaps.BitSize;
  v18 = ValueCaps.PhysicalMax;
  if ( !ValueCaps.PhysicalMax )
    v18 = (1 << (v17 - 1)) - 1;
  *((_DWORD *)v5 + 3) = v18;
  v19 = *((_WORD *)a1 + 46);
  if ( !v19 )
  {
    ValueCapsLength = 1;
    if ( HidP_GetSpecificValueCaps(
           HidP_Input,
           1u,
           0,
           0x38u,
           &ValueCaps,
           &ValueCapsLength,
           (PHIDP_PREPARSED_DATA)PreparsedData) >= 0
      && ValueCapsLength == 1 )
    {
      v5[2] = ValueCaps.BitSize;
      *((_WORD *)a1 + 188) = 256;
      *((_BYTE *)v5 + 17) = 0;
      *(_DWORD *)(v5 + 9) = 3670017;
      goto LABEL_40;
    }
    ValueCapsLength = 1;
    if ( HidP_GetSpecificValueCaps(
           HidP_Input,
           1u,
           0,
           0x32u,
           &ValueCaps,
           &ValueCapsLength,
           (PHIDP_PREPARSED_DATA)PreparsedData) >= 0
      && ValueCapsLength == 1 )
    {
      v5[2] = ValueCaps.BitSize;
      *((_WORD *)a1 + 188) = 256;
      *((_BYTE *)v5 + 17) = 0;
      *(_DWORD *)(v5 + 9) = 3276801;
      goto LABEL_40;
    }
LABEL_39:
    v5[2] = 0;
    *((_BYTE *)v5 + 17) = 1;
    goto LABEL_40;
  }
  if ( HidP_GetSpecificValueCaps(
         HidP_Input,
         *((_WORD *)a1 + 45),
         0,
         v19,
         &ValueCaps,
         &ValueCapsLength,
         (PHIDP_PREPARSED_DATA)PreparsedData) < 0
    || ValueCapsLength != 1 )
  {
    goto LABEL_39;
  }
  v5[2] = ValueCaps.BitSize;
  *((_WORD *)a1 + 188) = 256;
  *((_BYTE *)v5 + 17) = 0;
  v5[9] = *((_WORD *)a1 + 45);
  v5[10] = *((_WORD *)a1 + 46);
LABEL_40:
  v20 = *((_WORD *)a1 + 49);
  ValueCapsLength = 1;
  if ( v20 )
  {
    if ( HidP_GetSpecificValueCaps(
           HidP_Input,
           *((_WORD *)a1 + 48),
           0,
           v20,
           &ValueCaps,
           &ValueCapsLength,
           (PHIDP_PREPARSED_DATA)PreparsedData) >= 0
      && ValueCapsLength == 1 )
    {
      v5[3] = ValueCaps.BitSize;
      if ( *(&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 1) == 5 )
        *((_WORD *)a1 + 188) |= 0x8000u;
      *((_BYTE *)v5 + 22) = 0;
      v5[12] = *((_WORD *)a1 + 48);
      v5[13] = *((_WORD *)a1 + 49);
      return (unsigned int)Caps;
    }
LABEL_51:
    v5[3] = 0;
    *((_BYTE *)v5 + 22) = 1;
    return (unsigned int)Caps;
  }
  if ( HidP_GetSpecificValueCaps(
         HidP_Input,
         0xCu,
         0,
         0x238u,
         &ValueCaps,
         &ValueCapsLength,
         (PHIDP_PREPARSED_DATA)PreparsedData) < 0
    || ValueCapsLength != 1 )
  {
    goto LABEL_51;
  }
  v5[3] = ValueCaps.BitSize;
  if ( *(&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 1) == 5 )
    *((_WORD *)a1 + 188) |= 0x8000u;
  *((_BYTE *)v5 + 22) = 0;
  *((_DWORD *)v5 + 6) = 37224460;
  return (unsigned int)Caps;
}

```

## disassembly

```asm
0x14000baf0  push    rbp
0x14000baf2  push    rbx
0x14000baf3  push    rsi
0x14000baf4  push    rdi
0x14000baf5  push    r12
0x14000baf7  push    r13
0x14000baf9  push    r14
0x14000bafb  push    r15
0x14000bafd  lea     rbp, [rsp-8]
0x14000bb02  sub     rsp, 108h
0x14000bb09  mov     rax, cs:__security_cookie
0x14000bb10  xor     rax, rsp
0x14000bb13  mov     [rbp+40h+var_50], rax
0x14000bb17  mov     rdi, rcx
0x14000bb1a  mov     ebx, 40h ; '@'
0x14000bb1f  mov     r8d, ebx; Size
0x14000bb22  lea     rcx, [rsp+140h+Capabilities]; void *
0x14000bb27  xor     edx, edx; Val
0x14000bb29  call    memset
0x14000bb2e  xor     eax, eax
0x14000bb30  lea     r8d, [rbx+8]; Size
0x14000bb34  xor     r13d, r13d
0x14000bb37  mov     [rsp+140h+var_F8], rax
0x14000bb3c  xor     edx, edx; Val
0x14000bb3e  mov     [rsp+140h+var_F0], eax
0x14000bb42  lea     rcx, [rbp+40h+ValueCaps]; void *
0x14000bb46  mov     [rsp+140h+var_100], r13w
0x14000bb4c  call    memset
0x14000bb51  lea     rax, WPP_RECORDER_INITIALIZED
0x14000bb58  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000bb5f  jz      short loc_14000BB8F
0x14000bb61  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bb68  cmp     [rcx+48h], r13w
0x14000bb6d  jz      short loc_14000BB8F
0x14000bb6f  mov     rcx, [rcx+40h]
0x14000bb73  lea     r8d, [rbx-3Bh]
0x14000bb77  lea     rax, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x14000bb7e  mov     dl, r8b
0x14000bb81  lea     r9d, [rbx-2Ch]
0x14000bb85  mov     [rsp+140h+Irp], rax
0x14000bb8a  call    WPP_RECORDER_SF_
0x14000bb8f  lea     rax, [rsp+140h+var_F8]
0x14000bb94  mov     dword ptr [rsp+140h+ValueCapsLength], 0Ch
0x14000bb9c  xor     r9d, r9d
0x14000bb9f  mov     [rsp+140h+Irp], rax
0x14000bba4  xor     r8d, r8d
0x14000bba7  mov     edx, 0B01A8h
0x14000bbac  mov     rcx, rdi
0x14000bbaf  call    MouHid_CallHidClass
0x14000bbb4  mov     esi, eax
0x14000bbb6  test    eax, eax
0x14000bbb8  js      loc_14000C0E4
0x14000bbbe  mov     edx, dword ptr [rsp+140h+var_F8]
0x14000bbc2  mov     r8d, 48756F4Dh
0x14000bbc8  mov     rcx, rbx
0x14000bbcb  call    cs:__imp_ExAllocatePool2
0x14000bbd2  nop     dword ptr [rax+rax+00h]
0x14000bbd7  mov     r14, rax
0x14000bbda  test    rax, rax
0x14000bbdd  jnz     short loc_14000BBE9
0x14000bbdf  mov     esi, 0C000009Ah
0x14000bbe4  jmp     loc_14000C0E4
0x14000bbe9  mov     eax, dword ptr [rsp+140h+var_F8]
0x14000bbed  xor     r9d, r9d
0x14000bbf0  mov     dword ptr [rsp+140h+ValueCapsLength], eax
0x14000bbf4  xor     r8d, r8d
0x14000bbf7  mov     edx, 0B0193h
0x14000bbfc  mov     [rsp+140h+Irp], r14
0x14000bc01  mov     rcx, rdi
0x14000bc04  mov     rbx, r13
0x14000bc07  call    MouHid_CallHidClass
0x14000bc0c  mov     esi, eax
0x14000bc0e  test    eax, eax
0x14000bc10  js      loc_14000C09E
0x14000bc16  lea     rdx, [rsp+140h+Capabilities]; Capabilities
0x14000bc1b  mov     rcx, r14; PreparsedData
0x14000bc1e  call    cs:__imp_HidP_GetCaps
0x14000bc25  nop     dword ptr [rax+rax+00h]
0x14000bc2a  mov     esi, eax
0x14000bc2c  test    eax, eax
0x14000bc2e  js      loc_14000C09E
0x14000bc34  mov     ecx, 1
0x14000bc39  cmp     cx, [rsp+140h+Capabilities.UsagePage]
0x14000bc3e  jnz     loc_14000C099
0x14000bc44  lea     eax, [rcx+1]
0x14000bc47  cmp     ax, [rsp+140h+Capabilities.Usage]
0x14000bc4c  jz      short loc_14000BC66
0x14000bc4e  cmp     cx, [rsp+140h+Capabilities.Usage]
0x14000bc53  jnz     loc_14000C099
0x14000bc59  cmp     byte ptr cs:WPP_MAIN_CB.Queue+12h, r13b
0x14000bc60  jnz     loc_14000C099
0x14000bc66  mov     edx, 9; UsagePage
0x14000bc6b  mov     r8, r14; PreparsedData
0x14000bc6e  xor     ecx, ecx; ReportType
0x14000bc70  call    cs:__imp_HidP_MaxUsageListLength
0x14000bc77  nop     dword ptr [rax+rax+00h]
0x14000bc7c  movzx   esi, [rsp+140h+Capabilities.InputReportByteLength]
0x14000bc81  mov     ecx, 40h ; '@'
0x14000bc86  movzx   edx, ax
0x14000bc89  mov     r12d, eax
0x14000bc8c  mov     eax, 0FFFFFFF8h
0x14000bc91  add     esi, 7
0x14000bc94  and     esi, eax
0x14000bc96  mov     r8d, 48756F4Dh
0x14000bc9c  lea     r15d, ds:7[rdx*2]
0x14000bca4  and     r15d, eax
0x14000bca7  lea     edx, [rsi+98h]
0x14000bcad  lea     edx, [rdx+r15*4]
0x14000bcb1  call    cs:__imp_ExAllocatePool2
0x14000bcb8  nop     dword ptr [rax+rax+00h]
0x14000bcbd  mov     [rdi+0D8h], rax
0x14000bcc4  mov     rbx, rax
0x14000bcc7  test    rax, rax
0x14000bcca  jnz     short loc_14000BCD6
0x14000bccc  mov     esi, 0C000009Ah
0x14000bcd1  jmp     loc_14000C09E
0x14000bcd6  mov     [rax+20h], r14
0x14000bcda  lea     rcx, [rax+98h]; VirtualAddress
0x14000bce1  movaps  xmm0, xmmword ptr [rsp+140h+Capabilities.Usage]
0x14000bce6  xor     r9d, r9d; ChargeQuota
0x14000bce9  movups  xmmword ptr [rax+28h], xmm0
0x14000bced  mov     r8d, r15d
0x14000bcf0  movaps  xmm1, xmmword ptr [rsp+140h+Capabilities.Reserved+6]
0x14000bcf5  movups  xmmword ptr [rax+38h], xmm1
0x14000bcf9  mov     edx, esi
0x14000bcfb  movaps  xmm0, xmmword ptr [rbp+40h+Capabilities.Reserved+16h]
0x14000bcff  add     rdx, rcx
0x14000bd02  movups  xmmword ptr [rax+48h], xmm0
0x14000bd06  mov     [rsp+140h+Irp], r13; Irp
0x14000bd0b  movaps  xmm1, xmmword ptr [rbp+40h+Capabilities.NumberInputValueCaps]
0x14000bd0f  movups  xmmword ptr [rax+58h], xmm1
0x14000bd13  mov     [rax+1Ch], r12w
0x14000bd18  mov     [rdi+17Ah], r12w
0x14000bd20  mov     [rax+68h], rcx
0x14000bd24  mov     [rax+78h], rdx
0x14000bd28  lea     rax, [rdx+r15]
0x14000bd2c  mov     [rbx+70h], rax
0x14000bd30  add     rax, r8
0x14000bd33  mov     [rbx+80h], rax
0x14000bd3a  add     rax, r8
0x14000bd3d  mov     [rbx+88h], rax
0x14000bd44  xor     r8d, r8d; SecondaryBuffer
0x14000bd47  movzx   edx, [rsp+140h+Capabilities.InputReportByteLength]; Length
0x14000bd4c  call    cs:__imp_IoAllocateMdl
0x14000bd53  nop     dword ptr [rax+rax+00h]
0x14000bd58  mov     [rbx+90h], rax
0x14000bd5f  test    rax, rax
0x14000bd62  jz      loc_14000BCCC
0x14000bd68  mov     rcx, rax; MemoryDescriptorList
0x14000bd6b  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000bd72  nop     dword ptr [rax+rax+00h]
0x14000bd77  mov     r15d, 1
0x14000bd7d  mov     [rsp+140h+PreparsedData], r14; PreparsedData
0x14000bd82  lea     rax, [rsp+140h+var_100]
0x14000bd87  mov     [rsp+140h+var_100], r15w
0x14000bd8d  mov     [rsp+140h+ValueCapsLength], rax; ValueCapsLength
0x14000bd92  xor     r8d, r8d; LinkCollection
0x14000bd95  lea     rax, [rbp+40h+ValueCaps]
0x14000bd99  mov     edx, r15d; UsagePage
0x14000bd9c  lea     r9d, [r15+2Fh]; Usage
0x14000bda0  mov     [rsp+140h+Irp], rax; ValueCaps
0x14000bda5  xor     ecx, ecx; ReportType
0x14000bda7  call    cs:__imp_HidP_GetSpecificValueCaps
0x14000bdae  nop     dword ptr [rax+rax+00h]
0x14000bdb3  mov     esi, eax
0x14000bdb5  test    eax, eax
0x14000bdb7  js      loc_14000C09E
0x14000bdbd  cmp     [rbp+40h+ValueCaps.IsAbsolute], r13b
0x14000bdc1  jz      short loc_14000BE0E
0x14000bdc3  cmp     r15w, [rsp+140h+Capabilities.Usage]
0x14000bdc9  jnz     short loc_14000BDD4
0x14000bdcb  cmp     byte ptr cs:WPP_MAIN_CB.Queue+11h, r13b
0x14000bdd2  jnz     short loc_14000BE00
0x14000bdd4  cmp     byte ptr cs:WPP_MAIN_CB.Queue+10h, r13b
0x14000bddb  jz      short loc_14000BE00
0x14000bddd  mov     [rdi+162h], r13w
0x14000bde5  mov     edx, 80050002h
0x14000bdea  mov     [rbx+10h], r13b
0x14000bdee  mov     rcx, [rdi]
0x14000bdf1  or      [rdi+78h], r15d
0x14000bdf5  mov     rcx, [rcx+8]
0x14000bdf9  call    MouHid_LogError
0x14000bdfe  jmp     short loc_14000BE1A
0x14000be00  mov     [rdi+162h], r15w
0x14000be08  mov     [rbx+10h], r15b
0x14000be0c  jmp     short loc_14000BE1A
0x14000be0e  mov     [rdi+162h], r13w
0x14000be16  mov     [rbx+10h], r13b
0x14000be1a  movzx   ecx, [rbp+40h+ValueCaps.BitSize]
0x14000be1e  mov     [rbx], cx
0x14000be21  mov     eax, [rbp+40h+ValueCaps.PhysicalMax]
0x14000be24  test    eax, eax
0x14000be26  jnz     short loc_14000BE32
0x14000be28  dec     ecx
0x14000be2a  mov     eax, r15d
0x14000be2d  shl     eax, cl
0x14000be2f  sub     eax, r15d
0x14000be32  mov     [rbx+8], eax
0x14000be35  mov     r9d, 31h ; '1'; Usage
0x14000be3b  lea     rax, [rsp+140h+var_100]
0x14000be40  mov     [rsp+140h+PreparsedData], r14; PreparsedData
0x14000be45  mov     [rsp+140h+ValueCapsLength], rax; ValueCapsLength
0x14000be4a  xor     r8d, r8d; LinkCollection
0x14000be4d  lea     rax, [rbp+40h+ValueCaps]
0x14000be51  mov     [rsp+140h+var_100], r15w
0x14000be57  mov     edx, r15d; UsagePage
0x14000be5a  mov     [rsp+140h+Irp], rax; ValueCaps
0x14000be5f  xor     ecx, ecx; ReportType
0x14000be61  call    cs:__imp_HidP_GetSpecificValueCaps
0x14000be68  nop     dword ptr [rax+rax+00h]
0x14000be6d  mov     esi, eax
0x14000be6f  test    eax, eax
0x14000be71  js      loc_14000C09E
0x14000be77  movzx   ecx, [rbp+40h+ValueCaps.BitSize]
0x14000be7b  mov     [rbx+2], cx
0x14000be7f  mov     eax, [rbp+40h+ValueCaps.PhysicalMax]
0x14000be82  test    eax, eax
0x14000be84  jnz     short loc_14000BE90
0x14000be86  dec     ecx
0x14000be88  mov     eax, r15d
0x14000be8b  shl     eax, cl
0x14000be8d  sub     eax, r15d
0x14000be90  mov     [rbx+0Ch], eax
0x14000be93  xor     r8d, r8d; LinkCollection
0x14000be96  movzx   r9d, word ptr [rdi+5Ch]; Usage
0x14000be9b  lea     rax, [rsp+140h+var_100]
0x14000bea0  mov     [rsp+140h+PreparsedData], r14; PreparsedData
0x14000bea5  xor     ecx, ecx; ReportType
0x14000bea7  mov     [rsp+140h+ValueCapsLength], rax; ValueCapsLength
0x14000beac  lea     rax, [rbp+40h+ValueCaps]
0x14000beb0  mov     [rsp+140h+Irp], rax; ValueCaps
0x14000beb5  cmp     r13w, r9w
0x14000beb9  jz      short loc_14000BF09
0x14000bebb  movzx   edx, word ptr [rdi+5Ah]; UsagePage
0x14000bebf  call    cs:__imp_HidP_GetSpecificValueCaps
0x14000bec6  nop     dword ptr [rax+rax+00h]
0x14000becb  test    eax, eax
0x14000becd  js      loc_14000BFB0
0x14000bed3  cmp     [rsp+140h+var_100], r15w
0x14000bed9  jnz     loc_14000BFB0
0x14000bedf  movzx   eax, [rbp+40h+ValueCaps.BitSize]
0x14000bee3  mov     [rbx+4], ax
0x14000bee7  mov     word ptr [rdi+178h], 100h
0x14000bef0  mov     [rbx+11h], r13b
0x14000bef4  movzx   eax, word ptr [rdi+5Ah]
0x14000bef8  mov     [rbx+12h], ax
0x14000befc  movzx   eax, word ptr [rdi+5Ch]
0x14000bf00  mov     [rbx+14h], ax
0x14000bf04  jmp     loc_14000BFB9
0x14000bf09  mov     r9d, 38h ; '8'; Usage
0x14000bf0f  mov     [rsp+140h+var_100], r15w
0x14000bf15  mov     edx, r15d; UsagePage
0x14000bf18  call    cs:__imp_HidP_GetSpecificValueCaps
0x14000bf1f  nop     dword ptr [rax+rax+00h]
0x14000bf24  test    eax, eax
0x14000bf26  js      short loc_14000BF4E
0x14000bf28  cmp     [rsp+140h+var_100], r15w
0x14000bf2e  jnz     short loc_14000BF4E
0x14000bf30  movzx   eax, [rbp+40h+ValueCaps.BitSize]
0x14000bf34  mov     [rbx+4], ax
0x14000bf38  mov     word ptr [rdi+178h], 100h
0x14000bf41  mov     [rbx+11h], r13b
0x14000bf45  mov     dword ptr [rbx+12h], 380001h
0x14000bf4c  jmp     short loc_14000BFB9
0x14000bf4e  lea     rax, [rsp+140h+var_100]
0x14000bf53  mov     [rsp+140h+PreparsedData], r14; PreparsedData
0x14000bf58  mov     [rsp+140h+ValueCapsLength], rax; ValueCapsLength
0x14000bf5d  mov     r9d, 32h ; '2'; Usage
0x14000bf63  lea     rax, [rbp+40h+ValueCaps]
0x14000bf67  mov     [rsp+140h+var_100], r15w
0x14000bf6d  xor     r8d, r8d; LinkCollection
0x14000bf70  mov     [rsp+140h+Irp], rax; ValueCaps
0x14000bf75  mov     edx, r15d; UsagePage
0x14000bf78  xor     ecx, ecx; ReportType
0x14000bf7a  call    cs:__imp_HidP_GetSpecificValueCaps
0x14000bf81  nop     dword ptr [rax+rax+00h]
0x14000bf86  test    eax, eax
0x14000bf88  js      short loc_14000BFB0
0x14000bf8a  cmp     [rsp+140h+var_100], r15w
0x14000bf90  jnz     short loc_14000BFB0
0x14000bf92  movzx   eax, [rbp+40h+ValueCaps.BitSize]
0x14000bf96  mov     [rbx+4], ax
0x14000bf9a  mov     word ptr [rdi+178h], 100h
0x14000bfa3  mov     [rbx+11h], r13b
0x14000bfa7  mov     dword ptr [rbx+12h], 320001h
0x14000bfae  jmp     short loc_14000BFB9
0x14000bfb0  mov     [rbx+4], r13w
0x14000bfb5  mov     [rbx+11h], r15b
0x14000bfb9  movzx   r9d, word ptr [rdi+62h]; Usage
0x14000bfbe  lea     rax, [rsp+140h+var_100]
0x14000bfc3  mov     [rsp+140h+PreparsedData], r14; PreparsedData
0x14000bfc8  xor     r8d, r8d; LinkCollection
0x14000bfcb  mov     [rsp+140h+ValueCapsLength], rax; ValueCapsLength
0x14000bfd0  xor     ecx, ecx; ReportType
0x14000bfd2  mov     [rsp+140h+var_100], r15w
0x14000bfd8  lea     rax, [rbp+40h+ValueCaps]
0x14000bfdc  mov     [rsp+140h+Irp], rax; ValueCaps
0x14000bfe1  cmp     r13w, r9w
0x14000bfe5  jz      short loc_14000C041
0x14000bfe7  movzx   edx, word ptr [rdi+60h]; UsagePage
  ... truncated ...
```
