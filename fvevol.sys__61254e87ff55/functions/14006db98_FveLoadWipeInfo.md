# FveLoadWipeInfo

- ea: `0x14006db98`
- end: `0x14006e2db`
- name: `FveLoadWipeInfo`
- size: `1859`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1400914cc`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x14000eca8`
- `0x14000eec8`
- `0x14000ef2c`
- `0x14000ef94`
- `0x14000f068`
- `0x140022bf0`
- `0x140023040`
- `0x1400662d0`
- `0x14006db98`
- `0x14006f43c`
- `0x140090230`
- `0x140090750`
- `0x14009e2c0`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x14006dda4`
- `ntoskrnl!ZwQueryInformationFile` at `0x14006dda4`
- `ntoskrnl!ZwReadFile` at `0x14006df4c`
- `ntoskrnl!ZwReadFile` at `0x14006df4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dfd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e236`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dfd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e236`
- `ntoskrnl!ZwClose` at `0x14006de1b`
- `ntoskrnl!ZwClose` at `0x14006de7e`
- `ntoskrnl!ZwClose` at `0x14006e139`
- `ntoskrnl!ZwClose` at `0x14006e255`
- `ntoskrnl!ZwClose` at `0x14006de1b`
- `ntoskrnl!ZwClose` at `0x14006de7e`
- `ntoskrnl!ZwClose` at `0x14006e139`
- `ntoskrnl!ZwClose` at `0x14006e255`
- `ntoskrnl!ExAllocatePool2` at `0x14006defe`
- `ntoskrnl!ExAllocatePool2` at `0x14006defe`

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
0x14006db98  push    rbp
0x14006db9a  push    rbx
0x14006db9b  push    rsi
0x14006db9c  push    rdi
0x14006db9d  push    r12
0x14006db9f  push    r13
0x14006dba1  push    r14
0x14006dba3  push    r15
0x14006dba5  lea     rbp, [rsp-98h]
0x14006dbad  sub     rsp, 198h
0x14006dbb4  mov     rax, cs:__security_cookie
0x14006dbbb  xor     rax, rsp
0x14006dbbe  mov     [rbp+0D0h+var_48], rax
0x14006dbc5  mov     rdi, r8
0x14006dbc8  mov     [rbp+0D0h+var_100], r8
0x14006dbcc  mov     rbx, rdx
0x14006dbcf  mov     [rbp+0D0h+var_108], rdx
0x14006dbd3  mov     r13, rcx
0x14006dbd6  mov     [rbp+0D0h+var_148], rcx
0x14006dbda  xorps   xmm0, xmm0
0x14006dbdd  mov     [rbp+0D0h+var_F8], r9
0x14006dbe1  xor     eax, eax
0x14006dbe3  lea     rcx, [rbp+0D0h+var_F0]; void *
0x14006dbe7  mov     r14d, 90h
0x14006dbed  mov     [rbp+0D0h+var_110], rax
0x14006dbf1  mov     r8d, r14d; Size
0x14006dbf4  xor     edx, edx; Val
0x14006dbf6  mov     r15, r9
0x14006dbf9  movups  [rbp+0D0h+var_120], xmm0
0x14006dbfd  call    memset
0x14006dc02  xor     esi, esi
0x14006dc04  xorps   xmm0, xmm0
0x14006dc07  xor     eax, eax
0x14006dc09  mov     qword ptr [rbp+0D0h+var_150], rsi
0x14006dc0d  mov     [rbp+0D0h+var_50], rax
0x14006dc14  movups  xmmword ptr [rbp+0D0h+IoStatusBlock], xmm0
0x14006dc18  movups  [rbp+0D0h+FileInformation], xmm0
0x14006dc1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dc23  lea     rax, WPP_GLOBAL_Control
0x14006dc2a  cmp     rcx, rax
0x14006dc2d  jz      short loc_14006DC4F
0x14006dc2f  mov     eax, [rcx+2Ch]
0x14006dc32  test    al, 20h
0x14006dc34  jz      short loc_14006DC4F
0x14006dc36  cmp     byte ptr [rcx+29h], 5
0x14006dc3a  jb      short loc_14006DC4F
0x14006dc3c  mov     rcx, [rcx+18h]
0x14006dc40  lea     edx, [rsi+63h]
0x14006dc43  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006dc4a  call    WPP_SF_
0x14006dc4f  xorps   xmm0, xmm0
0x14006dc52  lea     rcx, [rbp+0D0h+var_F0]; void *
0x14006dc56  xor     eax, eax
0x14006dc58  mov     r8, r14; Size
0x14006dc5b  xor     edx, edx; Val
0x14006dc5d  mov     [rbp+0D0h+var_110], rax
0x14006dc61  movups  [rbp+0D0h+var_120], xmm0
0x14006dc65  call    memset
0x14006dc6a  mov     ecx, [r13+51Ch]
0x14006dc71  xorps   xmm0, xmm0
0x14006dc74  xorps   xmm1, xmm1
0x14006dc77  movups  xmmword ptr [rsp+1D0h+P], xmm0
0x14006dc7c  lea     eax, [rcx-1]
0x14006dc7f  movups  xmmword ptr [rbp+0D0h+Handle], xmm1
0x14006dc83  test    ecx, eax
0x14006dc85  jnz     short loc_14006DC99
0x14006dc87  test    ecx, ecx
0x14006dc89  jz      short loc_14006DC99
0x14006dc8b  lea     r12d, [rcx+1FFh]
0x14006dc92  not     eax
0x14006dc94  and     r12d, eax
0x14006dc97  jmp     short loc_14006DCAF
0x14006dc99  xor     edx, edx
0x14006dc9b  mov     r12d, 200h
0x14006dca1  mov     eax, r12d
0x14006dca4  div     ecx
0x14006dca6  test    edx, edx
0x14006dca8  jz      short loc_14006DCAF
0x14006dcaa  sub     ecx, edx
0x14006dcac  add     r12d, ecx
0x14006dcaf  test    rbx, rbx
0x14006dcb2  mov     [rsp+1D0h+pulResult], esi
0x14006dcb6  lea     r14, [rbp+0D0h+var_F0]
0x14006dcba  mov     [rdi], rsi
0x14006dcbd  cmovnz  r14, rbx
0x14006dcc1  mov     [rsp+1D0h+var_178], r14
0x14006dcc6  test    r15, r15
0x14006dcc9  jz      short loc_14006DCCF
0x14006dccb  movups  xmmword ptr [r15], xmm0
0x14006dccf  lea     rax, [rbp+0D0h+var_F0]
0x14006dcd3  cmp     r14, rax
0x14006dcd6  jnz     short loc_14006DCED
0x14006dcd8  mov     rdx, r14
0x14006dcdb  mov     rcx, r13
0x14006dcde  call    FveVolumeInitInfo
0x14006dce3  mov     edi, eax
0x14006dce5  test    eax, eax
0x14006dce7  js      loc_14006E21E
0x14006dced  xor     r9d, r9d
0x14006dcf0  lea     r15, WPP_GLOBAL_Control
0x14006dcf7  or      ebx, 0FFFFFFFFh
0x14006dcfa  mov     [rsp+1D0h+var_180], r9d
0x14006dcff  xor     eax, eax
0x14006dd01  mov     [rsp+1D0h+var_17C], ebx
0x14006dd05  mov     [rsp+1D0h+var_170], eax
0x14006dd09  mov     edi, 0C0210002h
0x14006dd0e  cmp     esi, 2
0x14006dd11  jnb     loc_14006E16A
0x14006dd17  mov     rcx, [rbp+0D0h+var_148]
0x14006dd1b  lea     r13, [rbp+0D0h+Handle]
0x14006dd1f  lea     r13, [r13+rsi*8+0]
0x14006dd24  mov     qword ptr [rbp+0D0h+var_150], 0
0x14006dd2c  xor     r9d, r9d
0x14006dd2f  mov     qword ptr [rsp+1D0h+FileInformationClass], r13
0x14006dd34  mov     r8d, esi
0x14006dd37  mov     rdx, r14
0x14006dd3a  call    FveWipeInfoFileCreate
0x14006dd3f  test    eax, eax
0x14006dd41  jns     short loc_14006DD82
0x14006dd43  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dd4a  cmp     rcx, r15
0x14006dd4d  jz      short loc_14006DD79
0x14006dd4f  mov     edx, [rcx+2Ch]
0x14006dd52  test    dl, 20h
0x14006dd55  jz      short loc_14006DD79
0x14006dd57  cmp     byte ptr [rcx+29h], 2
0x14006dd5b  jb      short loc_14006DD79
0x14006dd5d  mov     rcx, [rcx+18h]
0x14006dd61  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006dd68  mov     edx, 64h ; 'd'
0x14006dd6d  mov     [rsp+1D0h+FileInformationClass], eax
0x14006dd71  mov     r9d, esi
0x14006dd74  call    WPP_SF_Dd
0x14006dd79  mov     r9d, [rsp+1D0h+var_180]
0x14006dd7e  inc     esi
0x14006dd80  jmp     short loc_14006DD0E
0x14006dd82  mov     r14, [r13+0]
0x14006dd86  lea     r8, [rbp+0D0h+FileInformation]; FileInformation
0x14006dd8a  mov     rcx, r14; FileHandle
0x14006dd8d  mov     [rsp+1D0h+FileHandle], r14
0x14006dd92  mov     r9d, 18h; Length
0x14006dd98  mov     [rsp+1D0h+FileInformationClass], 5; FileInformationClass
0x14006dda0  lea     rdx, [rbp+0D0h+IoStatusBlock]; IoStatusBlock
0x14006dda4  call    cs:__imp_ZwQueryInformationFile
0x14006ddab  nop     dword ptr [rax+rax+00h]
0x14006ddb0  mov     r8d, eax
0x14006ddb3  test    eax, eax
0x14006ddb5  js      loc_14006E0F9
0x14006ddbb  mov     r8d, dword ptr [rbp+0D0h+IoStatusBlock]
0x14006ddbf  test    r8d, r8d
0x14006ddc2  js      loc_14006E0F9
0x14006ddc8  mov     r9, qword ptr [rbp+0D0h+FileInformation+8]
0x14006ddcc  lea     rdx, [rsp+1D0h+pulResult]; pulResult
0x14006ddd1  mov     rcx, r9; llOperand
0x14006ddd4  call    RtlLongLongToULong
0x14006ddd9  test    eax, eax
0x14006dddb  jns     short loc_14006DE39
0x14006dddd  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dde4  cmp     rcx, r15
0x14006dde7  jz      short loc_14006DE18
0x14006dde9  mov     edx, [rcx+2Ch]
0x14006ddec  test    dl, 20h
0x14006ddef  jz      short loc_14006DE18
0x14006ddf1  cmp     byte ptr [rcx+29h], 2
0x14006ddf5  jb      short loc_14006DE18
0x14006ddf7  mov     rcx, [rcx+18h]
0x14006ddfb  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006de02  mov     dword ptr [rsp+1D0h+Buffer], eax
0x14006de06  mov     edx, 66h ; 'f'
0x14006de0b  mov     qword ptr [rsp+1D0h+FileInformationClass], r9
0x14006de10  mov     r9d, esi
0x14006de13  call    WPP_SF_lid
0x14006de18  mov     rcx, r14; Handle
0x14006de1b  call    cs:__imp_ZwClose
0x14006de22  nop     dword ptr [rax+rax+00h]
0x14006de27  mov     r14, [rsp+1D0h+var_178]
0x14006de2c  mov     qword ptr [r13+0], 0
0x14006de34  jmp     loc_14006DD79
0x14006de39  mov     ebx, [rsp+1D0h+pulResult]
0x14006de3d  cmp     ebx, r12d
0x14006de40  jnb     short loc_14006DEA7
0x14006de42  mov     rcx, cs:WPP_GLOBAL_Control
0x14006de49  lea     rax, WPP_GLOBAL_Control
0x14006de50  cmp     rcx, rax
0x14006de53  jz      short loc_14006DE7B
0x14006de55  mov     eax, [rcx+2Ch]
0x14006de58  test    al, 20h
0x14006de5a  jz      short loc_14006DE7B
0x14006de5c  cmp     byte ptr [rcx+29h], 2
0x14006de60  jb      short loc_14006DE7B
0x14006de62  mov     rcx, [rcx+18h]
0x14006de66  mov     edx, 67h ; 'g'
0x14006de6b  mov     dword ptr [rsp+1D0h+Buffer], edi
0x14006de6f  mov     r9d, esi
0x14006de72  mov     [rsp+1D0h+FileInformationClass], ebx
0x14006de76  call    WPP_SF_lDd
0x14006de7b  mov     rcx, r14; Handle
0x14006de7e  call    cs:__imp_ZwClose
0x14006de85  nop     dword ptr [rax+rax+00h]
0x14006de8a  mov     ebx, [rsp+1D0h+var_17C]
0x14006de8e  mov     qword ptr [r13+0], 0
0x14006de96  mov     r14, [rsp+1D0h+var_178]
0x14006de9b  lea     r15, WPP_GLOBAL_Control
0x14006dea2  jmp     loc_14006DD79
0x14006dea7  mov     r14d, 0FE00h
0x14006dead  cmp     ebx, r14d
0x14006deb0  jbe     short loc_14006DEEE
0x14006deb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006deb9  lea     rax, WPP_GLOBAL_Control
0x14006dec0  cmp     rcx, rax
0x14006dec3  jz      short loc_14006DEE7
0x14006dec5  mov     eax, [rcx+2Ch]
0x14006dec8  test    al, 20h
0x14006deca  jz      short loc_14006DEE7
0x14006decc  cmp     byte ptr [rcx+29h], 3
0x14006ded0  jb      short loc_14006DEE7
0x14006ded2  mov     rcx, [rcx+18h]
0x14006ded6  mov     r9d, esi
0x14006ded9  mov     dword ptr [rsp+1D0h+Buffer], r14d
0x14006dede  mov     [rsp+1D0h+FileInformationClass], ebx
0x14006dee2  call    WPP_SF_lDD
0x14006dee7  mov     ebx, r14d
0x14006deea  mov     [rsp+1D0h+pulResult], ebx
0x14006deee  mov     r8d, 30455646h
0x14006def4  mov     edx, ebx
0x14006def6  mov     ecx, 108h
0x14006defb  mov     r15d, ebx
0x14006defe  call    cs:__imp_ExAllocatePool2
0x14006df05  nop     dword ptr [rax+rax+00h]
0x14006df0a  mov     [rsp+rsi*8+1D0h+P], rax
0x14006df0f  mov     r14, rax
0x14006df12  test    rax, rax
0x14006df15  jz      loc_14006E15B
0x14006df1b  mov     rcx, [rsp+1D0h+FileHandle]; FileHandle
0x14006df20  lea     rax, [rbp+0D0h+var_150]
0x14006df24  mov     [rsp+1D0h+Key], 0; Key
0x14006df2d  xor     r9d, r9d; ApcContext
0x14006df30  mov     [rsp+1D0h+ByteOffset], rax; ByteOffset
0x14006df35  xor     r8d, r8d; ApcRoutine
0x14006df38  mov     [rsp+1D0h+Length], ebx; Length
0x14006df3c  lea     rax, [rbp+0D0h+IoStatusBlock]
0x14006df40  mov     [rsp+1D0h+Buffer], r14; Buffer
0x14006df45  xor     edx, edx; Event
0x14006df47  mov     qword ptr [rsp+1D0h+FileInformationClass], rax; IoStatusBlock
0x14006df4c  call    cs:__imp_ZwReadFile
0x14006df53  nop     dword ptr [rax+rax+00h]
0x14006df58  mov     r8d, eax
0x14006df5b  test    eax, eax
0x14006df5d  js      loc_14006E0BE
0x14006df63  mov     r8d, dword ptr [rbp+0D0h+IoStatusBlock]
0x14006df67  test    r8d, r8d
0x14006df6a  js      loc_14006E0B2
0x14006df70  cmp     [rbp+0D0h+IoStatusBlock.Information], r15
0x14006df74  jnz     loc_14006E0B2
0x14006df7a  mov     rax, [rbp+0D0h+var_108]
0x14006df7e  mov     rdx, r14
0x14006df81  mov     ecx, ebx
0x14006df83  mov     r8d, [rax+68h]
0x14006df87  call    FveValidateWipeInfo
0x14006df8c  test    eax, eax
0x14006df8e  jns     short loc_14006DFF4
0x14006df90  mov     rcx, cs:WPP_GLOBAL_Control
0x14006df97  lea     rdx, WPP_GLOBAL_Control
0x14006df9e  cmp     rcx, rdx
0x14006dfa1  jz      short loc_14006DFCD
0x14006dfa3  mov     edx, [rcx+2Ch]
0x14006dfa6  test    dl, 20h
0x14006dfa9  jz      short loc_14006DFCD
0x14006dfab  cmp     byte ptr [rcx+29h], 2
0x14006dfaf  jb      short loc_14006DFCD
0x14006dfb1  mov     edx, 6Ah ; 'j'
0x14006dfb6  mov     [rsp+1D0h+FileInformationClass], eax
0x14006dfba  mov     rcx, [rcx+18h]
0x14006dfbe  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x14006dfc5  mov     r9d, esi
0x14006dfc8  call    WPP_SF_Dd
0x14006dfcd  mov     edx, 30455646h; Tag
0x14006dfd2  mov     rcx, r14; P
0x14006dfd5  call    cs:__imp_ExFreePoolWithTag
0x14006dfdc  nop     dword ptr [rax+rax+00h]
0x14006dfe1  mov     rcx, [rsp+1D0h+FileHandle]
0x14006dfe6  mov     [rsp+rsi*8+1D0h+P], 0
0x14006dfef  jmp     loc_14006DE7E
0x14006dff4  mov     r9d, [rsp+1D0h+var_180]
0x14006dff9  mov     ebx, [rsp+1D0h+var_17C]
0x14006dffd  inc     r9d
0x14006e000  movzx   ecx, byte ptr [r14+3]
0x14006e005  mov     [rsp+1D0h+var_180], r9d
0x14006e00a  cmp     ebx, 0FFFFFFFFh
0x14006e00d  jz      short loc_14006E05D
0x14006e00f  mov     r15d, [rsp+1D0h+var_170]
0x14006e014  movzx   edx, cx
0x14006e017  movzx   r8d, r15w
0x14006e01b  sub     dx, r15w
0x14006e01f  sub     r8w, cx
0x14006e023  mov     eax, 0FFh
0x14006e028  cmp     cx, r15w
0x14006e02c  jbe     short loc_14006E054
0x14006e02e  add     r8w, ax
0x14006e032  mov     eax, esi
  ... truncated ...
```
