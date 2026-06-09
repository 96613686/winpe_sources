# FveLoadWipeInfo

- ea: `0x14006bb08`
- end: `0x14006c24b`
- name: `FveLoadWipeInfo`
- size: `1859`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x14008f41c`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x14000eac0`
- `0x14000ece0`
- `0x14000ed44`
- `0x14000edac`
- `0x14000ee80`
- `0x1400218c0`
- `0x140021d00`
- `0x140064248`
- `0x14006bb08`
- `0x14006d3ac`
- `0x14008e180`
- `0x14008e6a0`
- `0x14009c2c0`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x14006bd14`
- `ntoskrnl!ZwQueryInformationFile` at `0x14006bd14`
- `ntoskrnl!ZwReadFile` at `0x14006bebc`
- `ntoskrnl!ZwReadFile` at `0x14006bebc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bf45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c1a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bf45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c1a6`
- `ntoskrnl!ZwClose` at `0x14006bd8b`
- `ntoskrnl!ZwClose` at `0x14006bdee`
- `ntoskrnl!ZwClose` at `0x14006c0a9`
- `ntoskrnl!ZwClose` at `0x14006c1c5`
- `ntoskrnl!ZwClose` at `0x14006bd8b`
- `ntoskrnl!ZwClose` at `0x14006bdee`
- `ntoskrnl!ZwClose` at `0x14006c0a9`
- `ntoskrnl!ZwClose` at `0x14006c1c5`
- `ntoskrnl!ExAllocatePool2` at `0x14006be6e`
- `ntoskrnl!ExAllocatePool2` at `0x14006be6e`

## pseudocode

```c
__int64 __fastcall FveLoadWipeInfo(__int64 a1, _BYTE *a2, _QWORD *a3, _OWORD *a4)
{
  __int64 v8; // rsi
  PDEVICE_OBJECT v9; // r8
  unsigned int v10; // ecx
  ULONG v11; // r12d
  _BYTE *v12; // r14
  unsigned int inited; // edi
  unsigned int v14; // r9d
  unsigned int v15; // ebx
  HANDLE *v16; // r13
  int v17; // eax
  HANDLE v18; // r14
  NTSTATUS Status; // r8d
  NTSTATUS v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  ULONG Length; // ebx
  HANDLE v25; // rcx
  void *Buffer; // rax
  unsigned __int8 *v27; // r14
  NTSTATUS v28; // r8d
  int v29; // eax
  int v30; // ecx
  unsigned __int16 v31; // dx
  unsigned __int16 v32; // r8
  unsigned __int16 v33; // r8
  int v34; // eax
  unsigned __int16 v35; // ax
  _QWORD *v36; // rdx
  _OWORD *v37; // r15
  _BYTE *v38; // rax
  __int64 i; // rbx
  PVOID v40; // rcx
  HANDLE v41; // rcx
  unsigned int v43; // [rsp+50h] [rbp-B0h]
  int v44; // [rsp+54h] [rbp-ACh]
  _BYTE *v45; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v46; // [rsp+60h] [rbp-A0h]
  ULONG pulResult; // [rsp+64h] [rbp-9Ch] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-98h]
  HANDLE FileHandle; // [rsp+78h] [rbp-88h]
  union _LARGE_INTEGER ByteOffset; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v51; // [rsp+88h] [rbp-78h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  HANDLE Handle[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v54; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v55; // [rsp+C0h] [rbp-40h]
  _BYTE *v56; // [rsp+C8h] [rbp-38h]
  _QWORD *v57; // [rsp+D0h] [rbp-30h]
  _OWORD *v58; // [rsp+D8h] [rbp-28h]
  _BYTE v59[144]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 FileInformation; // [rsp+170h] [rbp+70h] BYREF
  __int64 v61; // [rsp+180h] [rbp+80h]

  v57 = a3;
  v56 = a2;
  v51 = (_QWORD *)a1;
  v58 = a4;
  v55 = 0;
  v54 = 0;
  memset(v59, 0, sizeof(v59));
  v8 = 0;
  ByteOffset.QuadPart = 0;
  v61 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
  }
  v55 = 0;
  v54 = 0;
  memset(v59, 0, sizeof(v59));
  v10 = *(_DWORD *)(a1 + 1308);
  *(_OWORD *)P = 0;
  *(_OWORD *)Handle = 0;
  if ( ((v10 - 1) & v10) != 0 || !v10 )
  {
    v11 = 512;
    if ( 0x200 % v10 )
      v11 = v10 - 0x200 % v10 + 512;
  }
  else
  {
    v11 = ~(v10 - 1) & (v10 + 511);
  }
  pulResult = 0;
  v12 = v59;
  *a3 = 0;
  if ( a2 )
    v12 = a2;
  v45 = v12;
  if ( a4 )
    *a4 = 0;
  if ( v12 != v59 || (inited = FveVolumeInitInfo(a1, (__int64)v12), (inited & 0x80000000) == 0) )
  {
    v14 = 0;
    v15 = -1;
    v43 = 0;
    v44 = -1;
    v46 = 0;
    inited = -1071579134;
    while ( 1 )
    {
      if ( (unsigned int)v8 >= 2 )
      {
        if ( v14 && v15 < 2 )
        {
          _mm_lfence();
          inited = v14 < 2 ? 0x80210001 : 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_lL(WPP_GLOBAL_Control->AttachedDevice, 108, v9, v15, *((unsigned __int8 *)P[v15] + 3));
          }
          v36 = v57;
          v37 = v58;
          v38 = P[v15];
          P[v15] = 0;
          ++v38[3];
          *v36 = v38;
          if ( v37 )
          {
            *v37 = *(_OWORD *)Handle;
            *(_OWORD *)Handle = 0;
          }
        }
        else
        {
          HIDWORD(v54) = -1071579134;
          *(_QWORD *)&v54 = FVE_METADATA_CORRUPT_ERROR;
          FveLogEvent(*v51, &v54);
        }
        goto LABEL_93;
      }
      v16 = &Handle[v8];
      ByteOffset.QuadPart = 0;
      v17 = FveWipeInfoFileCreate(v51, v12, (unsigned int)v8, 0, v16);
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            100,
            WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
            (unsigned int)v8,
            v17);
        }
        goto LABEL_23;
      }
      v18 = *v16;
      FileHandle = *v16;
      Status = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            101,
            WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
            (unsigned int)v8,
            Status);
        }
        ZwClose(v18);
        goto LABEL_40;
      }
      v20 = RtlLongLongToULong(*((LONGLONG *)&FileInformation + 1), &pulResult);
      if ( v20 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_lid(
            WPP_GLOBAL_Control->AttachedDevice,
            102,
            WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
            (unsigned int)v8,
            v23,
            v20);
        }
        ZwClose(v18);
        v12 = v45;
        *v16 = 0;
        goto LABEL_23;
      }
      Length = pulResult;
      if ( pulResult < v11 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_lDd(WPP_GLOBAL_Control->AttachedDevice, 103, v22, (unsigned int)v8, pulResult, -1071579134);
        }
        v25 = v18;
        goto LABEL_39;
      }
      if ( pulResult > 0xFE00 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_lDD(WPP_GLOBAL_Control->AttachedDevice, v21, v22, (unsigned int)v8, pulResult, 65024);
        }
        Length = 65024;
        pulResult = 65024;
      }
      Buffer = (void *)ExAllocatePool2(264, Length, 809850438);
      P[v8] = Buffer;
      v27 = (unsigned __int8 *)Buffer;
      if ( !Buffer )
      {
        v12 = v45;
        inited = -1073741670;
        goto LABEL_93;
      }
      v28 = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
      if ( v28 < 0 )
        goto LABEL_73;
      v28 = IoStatusBlock.Status;
      if ( IoStatusBlock.Status < 0 || IoStatusBlock.Information != Length )
      {
        if ( IoStatusBlock.Status >= 0 )
          v28 = -1073741823;
LABEL_73:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            105,
            WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
            (unsigned int)v8,
            v28);
        }
LABEL_57:
        ExFreePoolWithTag(v27, 0x30455646u);
        v25 = FileHandle;
        P[v8] = 0;
LABEL_39:
        ZwClose(v25);
        v15 = v44;
LABEL_40:
        *v16 = 0;
LABEL_41:
        v12 = v45;
LABEL_23:
        v14 = v43;
        goto LABEL_24;
      }
      v29 = FveValidateWipeInfo(Length, v27, *((unsigned int *)v56 + 26));
      if ( v29 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            106,
            WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
            (unsigned int)v8,
            v29);
        }
        goto LABEL_57;
      }
      v15 = v44;
      v14 = v43 + 1;
      v30 = v27[3];
      ++v43;
      if ( v44 == -1 )
        break;
      v31 = v30 - v46;
      v32 = v46 - v30;
      if ( (unsigned __int16)v30 <= v46 )
      {
        if ( v32 > (unsigned __int16)(v31 + 255) )
          break;
      }
      else
      {
        v33 = v32 + 255;
        v34 = v8;
        if ( v31 >= v33 )
          v34 = v44;
        v15 = v34;
        v44 = v34;
        v35 = v27[3];
        if ( v31 >= v33 )
          v35 = v46;
        v46 = v35;
      }
LABEL_67:
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_lL(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_GLOBAL_Control, (unsigned int)v8, v30);
        goto LABEL_41;
      }
      v12 = v45;
LABEL_24:
      v8 = (unsigned int)(v8 + 1);
    }
    v15 = v8;
    v46 = v27[3];
    v44 = v8;
    goto LABEL_67;
  }
LABEL_93:
  for ( i = 0; i != 2; ++i )
  {
    v40 = P[i];
    if ( v40 )
    {
      ExFreePoolWithTag(v40, 0x30455646u);
      P[i] = 0;
    }
    v41 = Handle[i];
    if ( v41 )
    {
      ZwClose(v41);
      Handle[i] = 0;
    }
  }
  if ( v12 == v59 )
    FveVolumeCleanupInfo(v12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids, inited);
  }
  return inited;
}

```

## disassembly

```asm
0x14006bb08  push    rbp
0x14006bb0a  push    rbx
0x14006bb0b  push    rsi
0x14006bb0c  push    rdi
0x14006bb0d  push    r12
0x14006bb0f  push    r13
0x14006bb11  push    r14
0x14006bb13  push    r15
0x14006bb15  lea     rbp, [rsp-98h]
0x14006bb1d  sub     rsp, 198h
0x14006bb24  mov     rax, cs:__security_cookie
0x14006bb2b  xor     rax, rsp
0x14006bb2e  mov     [rbp+0D0h+var_48], rax
0x14006bb35  mov     rdi, r8
0x14006bb38  mov     [rbp+0D0h+var_100], r8
0x14006bb3c  mov     rbx, rdx
0x14006bb3f  mov     [rbp+0D0h+var_108], rdx
0x14006bb43  mov     r13, rcx
0x14006bb46  mov     [rbp+0D0h+var_148], rcx
0x14006bb4a  xorps   xmm0, xmm0
0x14006bb4d  mov     [rbp+0D0h+var_F8], r9
0x14006bb51  xor     eax, eax
0x14006bb53  lea     rcx, [rbp+0D0h+var_F0]; void *
0x14006bb57  mov     r14d, 90h
0x14006bb5d  mov     [rbp+0D0h+var_110], rax
0x14006bb61  mov     r8d, r14d; Size
0x14006bb64  xor     edx, edx; Val
0x14006bb66  mov     r15, r9
0x14006bb69  movups  [rbp+0D0h+var_120], xmm0
0x14006bb6d  call    memset
0x14006bb72  xor     esi, esi
0x14006bb74  xorps   xmm0, xmm0
0x14006bb77  xor     eax, eax
0x14006bb79  mov     qword ptr [rbp+0D0h+var_150], rsi
0x14006bb7d  mov     [rbp+0D0h+var_50], rax
0x14006bb84  movups  xmmword ptr [rbp+0D0h+IoStatusBlock], xmm0
0x14006bb88  movups  [rbp+0D0h+FileInformation], xmm0
0x14006bb8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bb93  lea     rax, WPP_GLOBAL_Control
0x14006bb9a  cmp     rcx, rax
0x14006bb9d  jz      short loc_14006BBBF
0x14006bb9f  mov     eax, [rcx+2Ch]
0x14006bba2  test    al, 20h
0x14006bba4  jz      short loc_14006BBBF
0x14006bba6  cmp     byte ptr [rcx+29h], 5
0x14006bbaa  jb      short loc_14006BBBF
0x14006bbac  mov     rcx, [rcx+18h]
0x14006bbb0  lea     edx, [rsi+63h]
0x14006bbb3  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006bbba  call    WPP_SF_
0x14006bbbf  xorps   xmm0, xmm0
0x14006bbc2  lea     rcx, [rbp+0D0h+var_F0]; void *
0x14006bbc6  xor     eax, eax
0x14006bbc8  mov     r8, r14; Size
0x14006bbcb  xor     edx, edx; Val
0x14006bbcd  mov     [rbp+0D0h+var_110], rax
0x14006bbd1  movups  [rbp+0D0h+var_120], xmm0
0x14006bbd5  call    memset
0x14006bbda  mov     ecx, [r13+51Ch]
0x14006bbe1  xorps   xmm0, xmm0
0x14006bbe4  xorps   xmm1, xmm1
0x14006bbe7  movups  xmmword ptr [rsp+1D0h+P], xmm0
0x14006bbec  lea     eax, [rcx-1]
0x14006bbef  movups  xmmword ptr [rbp+0D0h+Handle], xmm1
0x14006bbf3  test    ecx, eax
0x14006bbf5  jnz     short loc_14006BC09
0x14006bbf7  test    ecx, ecx
0x14006bbf9  jz      short loc_14006BC09
0x14006bbfb  lea     r12d, [rcx+1FFh]
0x14006bc02  not     eax
0x14006bc04  and     r12d, eax
0x14006bc07  jmp     short loc_14006BC1F
0x14006bc09  xor     edx, edx
0x14006bc0b  mov     r12d, 200h
0x14006bc11  mov     eax, r12d
0x14006bc14  div     ecx
0x14006bc16  test    edx, edx
0x14006bc18  jz      short loc_14006BC1F
0x14006bc1a  sub     ecx, edx
0x14006bc1c  add     r12d, ecx
0x14006bc1f  test    rbx, rbx
0x14006bc22  mov     [rsp+1D0h+pulResult], esi
0x14006bc26  lea     r14, [rbp+0D0h+var_F0]
0x14006bc2a  mov     [rdi], rsi
0x14006bc2d  cmovnz  r14, rbx
0x14006bc31  mov     [rsp+1D0h+var_178], r14
0x14006bc36  test    r15, r15
0x14006bc39  jz      short loc_14006BC3F
0x14006bc3b  movups  xmmword ptr [r15], xmm0
0x14006bc3f  lea     rax, [rbp+0D0h+var_F0]
0x14006bc43  cmp     r14, rax
0x14006bc46  jnz     short loc_14006BC5D
0x14006bc48  mov     rdx, r14
0x14006bc4b  mov     rcx, r13
0x14006bc4e  call    FveVolumeInitInfo
0x14006bc53  mov     edi, eax
0x14006bc55  test    eax, eax
0x14006bc57  js      loc_14006C18E
0x14006bc5d  xor     r9d, r9d
0x14006bc60  lea     r15, WPP_GLOBAL_Control
0x14006bc67  or      ebx, 0FFFFFFFFh
0x14006bc6a  mov     [rsp+1D0h+var_180], r9d
0x14006bc6f  xor     eax, eax
0x14006bc71  mov     [rsp+1D0h+var_17C], ebx
0x14006bc75  mov     [rsp+1D0h+var_170], eax
0x14006bc79  mov     edi, 0C0210002h
0x14006bc7e  cmp     esi, 2
0x14006bc81  jnb     loc_14006C0DA
0x14006bc87  mov     rcx, [rbp+0D0h+var_148]
0x14006bc8b  lea     r13, [rbp+0D0h+Handle]
0x14006bc8f  lea     r13, [r13+rsi*8+0]
0x14006bc94  mov     qword ptr [rbp+0D0h+var_150], 0
0x14006bc9c  xor     r9d, r9d
0x14006bc9f  mov     qword ptr [rsp+1D0h+FileInformationClass], r13
0x14006bca4  mov     r8d, esi
0x14006bca7  mov     rdx, r14
0x14006bcaa  call    FveWipeInfoFileCreate
0x14006bcaf  test    eax, eax
0x14006bcb1  jns     short loc_14006BCF2
0x14006bcb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bcba  cmp     rcx, r15
0x14006bcbd  jz      short loc_14006BCE9
0x14006bcbf  mov     edx, [rcx+2Ch]
0x14006bcc2  test    dl, 20h
0x14006bcc5  jz      short loc_14006BCE9
0x14006bcc7  cmp     byte ptr [rcx+29h], 2
0x14006bccb  jb      short loc_14006BCE9
0x14006bccd  mov     rcx, [rcx+18h]
0x14006bcd1  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006bcd8  mov     edx, 64h ; 'd'
0x14006bcdd  mov     [rsp+1D0h+FileInformationClass], eax
0x14006bce1  mov     r9d, esi
0x14006bce4  call    WPP_SF_Dd
0x14006bce9  mov     r9d, [rsp+1D0h+var_180]
0x14006bcee  inc     esi
0x14006bcf0  jmp     short loc_14006BC7E
0x14006bcf2  mov     r14, [r13+0]
0x14006bcf6  lea     r8, [rbp+0D0h+FileInformation]; FileInformation
0x14006bcfa  mov     rcx, r14; FileHandle
0x14006bcfd  mov     [rsp+1D0h+FileHandle], r14
0x14006bd02  mov     r9d, 18h; Length
0x14006bd08  mov     [rsp+1D0h+FileInformationClass], 5; FileInformationClass
0x14006bd10  lea     rdx, [rbp+0D0h+IoStatusBlock]; IoStatusBlock
0x14006bd14  call    cs:__imp_ZwQueryInformationFile
0x14006bd1b  nop     dword ptr [rax+rax+00h]
0x14006bd20  mov     r8d, eax
0x14006bd23  test    eax, eax
0x14006bd25  js      loc_14006C069
0x14006bd2b  mov     r8d, dword ptr [rbp+0D0h+IoStatusBlock]
0x14006bd2f  test    r8d, r8d
0x14006bd32  js      loc_14006C069
0x14006bd38  mov     r9, qword ptr [rbp+0D0h+FileInformation+8]
0x14006bd3c  lea     rdx, [rsp+1D0h+pulResult]; pulResult
0x14006bd41  mov     rcx, r9; llOperand
0x14006bd44  call    RtlLongLongToULong
0x14006bd49  test    eax, eax
0x14006bd4b  jns     short loc_14006BDA9
0x14006bd4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bd54  cmp     rcx, r15
0x14006bd57  jz      short loc_14006BD88
0x14006bd59  mov     edx, [rcx+2Ch]
0x14006bd5c  test    dl, 20h
0x14006bd5f  jz      short loc_14006BD88
0x14006bd61  cmp     byte ptr [rcx+29h], 2
0x14006bd65  jb      short loc_14006BD88
0x14006bd67  mov     rcx, [rcx+18h]
0x14006bd6b  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006bd72  mov     dword ptr [rsp+1D0h+Buffer], eax
0x14006bd76  mov     edx, 66h ; 'f'
0x14006bd7b  mov     qword ptr [rsp+1D0h+FileInformationClass], r9
0x14006bd80  mov     r9d, esi
0x14006bd83  call    WPP_SF_lid
0x14006bd88  mov     rcx, r14; Handle
0x14006bd8b  call    cs:__imp_ZwClose
0x14006bd92  nop     dword ptr [rax+rax+00h]
0x14006bd97  mov     r14, [rsp+1D0h+var_178]
0x14006bd9c  mov     qword ptr [r13+0], 0
0x14006bda4  jmp     loc_14006BCE9
0x14006bda9  mov     ebx, [rsp+1D0h+pulResult]
0x14006bdad  cmp     ebx, r12d
0x14006bdb0  jnb     short loc_14006BE17
0x14006bdb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bdb9  lea     rax, WPP_GLOBAL_Control
0x14006bdc0  cmp     rcx, rax
0x14006bdc3  jz      short loc_14006BDEB
0x14006bdc5  mov     eax, [rcx+2Ch]
0x14006bdc8  test    al, 20h
0x14006bdca  jz      short loc_14006BDEB
0x14006bdcc  cmp     byte ptr [rcx+29h], 2
0x14006bdd0  jb      short loc_14006BDEB
0x14006bdd2  mov     rcx, [rcx+18h]
0x14006bdd6  mov     edx, 67h ; 'g'
0x14006bddb  mov     dword ptr [rsp+1D0h+Buffer], edi
0x14006bddf  mov     r9d, esi
0x14006bde2  mov     [rsp+1D0h+FileInformationClass], ebx
0x14006bde6  call    WPP_SF_lDd
0x14006bdeb  mov     rcx, r14; Handle
0x14006bdee  call    cs:__imp_ZwClose
0x14006bdf5  nop     dword ptr [rax+rax+00h]
0x14006bdfa  mov     ebx, [rsp+1D0h+var_17C]
0x14006bdfe  mov     qword ptr [r13+0], 0
0x14006be06  mov     r14, [rsp+1D0h+var_178]
0x14006be0b  lea     r15, WPP_GLOBAL_Control
0x14006be12  jmp     loc_14006BCE9
0x14006be17  mov     r14d, 0FE00h
0x14006be1d  cmp     ebx, r14d
0x14006be20  jbe     short loc_14006BE5E
0x14006be22  mov     rcx, cs:WPP_GLOBAL_Control
0x14006be29  lea     rax, WPP_GLOBAL_Control
0x14006be30  cmp     rcx, rax
0x14006be33  jz      short loc_14006BE57
0x14006be35  mov     eax, [rcx+2Ch]
0x14006be38  test    al, 20h
0x14006be3a  jz      short loc_14006BE57
0x14006be3c  cmp     byte ptr [rcx+29h], 3
0x14006be40  jb      short loc_14006BE57
0x14006be42  mov     rcx, [rcx+18h]
0x14006be46  mov     r9d, esi
0x14006be49  mov     dword ptr [rsp+1D0h+Buffer], r14d
0x14006be4e  mov     [rsp+1D0h+FileInformationClass], ebx
0x14006be52  call    WPP_SF_lDD
0x14006be57  mov     ebx, r14d
0x14006be5a  mov     [rsp+1D0h+pulResult], ebx
0x14006be5e  mov     r8d, 30455646h
0x14006be64  mov     edx, ebx
0x14006be66  mov     ecx, 108h
0x14006be6b  mov     r15d, ebx
0x14006be6e  call    cs:__imp_ExAllocatePool2
0x14006be75  nop     dword ptr [rax+rax+00h]
0x14006be7a  mov     [rsp+rsi*8+1D0h+P], rax
0x14006be7f  mov     r14, rax
0x14006be82  test    rax, rax
0x14006be85  jz      loc_14006C0CB
0x14006be8b  mov     rcx, [rsp+1D0h+FileHandle]; FileHandle
0x14006be90  lea     rax, [rbp+0D0h+var_150]
0x14006be94  mov     [rsp+1D0h+Key], 0; Key
0x14006be9d  xor     r9d, r9d; ApcContext
0x14006bea0  mov     [rsp+1D0h+ByteOffset], rax; ByteOffset
0x14006bea5  xor     r8d, r8d; ApcRoutine
0x14006bea8  mov     [rsp+1D0h+Length], ebx; Length
0x14006beac  lea     rax, [rbp+0D0h+IoStatusBlock]
0x14006beb0  mov     [rsp+1D0h+Buffer], r14; Buffer
0x14006beb5  xor     edx, edx; Event
0x14006beb7  mov     qword ptr [rsp+1D0h+FileInformationClass], rax; IoStatusBlock
0x14006bebc  call    cs:__imp_ZwReadFile
0x14006bec3  nop     dword ptr [rax+rax+00h]
0x14006bec8  mov     r8d, eax
0x14006becb  test    eax, eax
0x14006becd  js      loc_14006C02E
0x14006bed3  mov     r8d, dword ptr [rbp+0D0h+IoStatusBlock]
0x14006bed7  test    r8d, r8d
0x14006beda  js      loc_14006C022
0x14006bee0  cmp     [rbp+0D0h+IoStatusBlock.Information], r15
0x14006bee4  jnz     loc_14006C022
0x14006beea  mov     rax, [rbp+0D0h+var_108]
0x14006beee  mov     rdx, r14
0x14006bef1  mov     ecx, ebx
0x14006bef3  mov     r8d, [rax+68h]
0x14006bef7  call    FveValidateWipeInfo
0x14006befc  test    eax, eax
0x14006befe  jns     short loc_14006BF64
0x14006bf00  mov     rcx, cs:WPP_GLOBAL_Control
0x14006bf07  lea     rdx, WPP_GLOBAL_Control
0x14006bf0e  cmp     rcx, rdx
0x14006bf11  jz      short loc_14006BF3D
0x14006bf13  mov     edx, [rcx+2Ch]
0x14006bf16  test    dl, 20h
0x14006bf19  jz      short loc_14006BF3D
0x14006bf1b  cmp     byte ptr [rcx+29h], 2
0x14006bf1f  jb      short loc_14006BF3D
0x14006bf21  mov     edx, 6Ah ; 'j'
0x14006bf26  mov     [rsp+1D0h+FileInformationClass], eax
0x14006bf2a  mov     rcx, [rcx+18h]
0x14006bf2e  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006bf35  mov     r9d, esi
0x14006bf38  call    WPP_SF_Dd
0x14006bf3d  mov     edx, 30455646h; Tag
0x14006bf42  mov     rcx, r14; P
0x14006bf45  call    cs:__imp_ExFreePoolWithTag
0x14006bf4c  nop     dword ptr [rax+rax+00h]
0x14006bf51  mov     rcx, [rsp+1D0h+FileHandle]
0x14006bf56  mov     [rsp+rsi*8+1D0h+P], 0
0x14006bf5f  jmp     loc_14006BDEE
0x14006bf64  mov     r9d, [rsp+1D0h+var_180]
0x14006bf69  mov     ebx, [rsp+1D0h+var_17C]
0x14006bf6d  inc     r9d
0x14006bf70  movzx   ecx, byte ptr [r14+3]
0x14006bf75  mov     [rsp+1D0h+var_180], r9d
0x14006bf7a  cmp     ebx, 0FFFFFFFFh
0x14006bf7d  jz      short loc_14006BFCD
0x14006bf7f  mov     r15d, [rsp+1D0h+var_170]
0x14006bf84  movzx   edx, cx
0x14006bf87  movzx   r8d, r15w
0x14006bf8b  sub     dx, r15w
0x14006bf8f  sub     r8w, cx
0x14006bf93  mov     eax, 0FFh
0x14006bf98  cmp     cx, r15w
0x14006bf9c  jbe     short loc_14006BFC4
0x14006bf9e  add     r8w, ax
0x14006bfa2  mov     eax, esi
  ... truncated ...
```
