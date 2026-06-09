# IsQualifiedVolume(_SCRUB_ENVIRONMENT *,_UNICODE_STRING const *,ulong,ulong *,_DISK_EXTENT *,_STORAGE_DEVICE_NUMBER_EX *,ATL::CHeapPtr<_STORAGE_DESCRIPTOR_HEADER,ATL::CCRTAllocator> &,ulong &)

- ea: `0x18000d9bc`
- end: `0x18000e2f2`
- name: `?IsQualifiedVolume@@YAJPEAU_SCRUB_ENVIRONMENT@@PEBU_UNICODE_STRING@@KPEAKPEAU_DISK_EXTENT@@PEAU_STORAGE_DEVICE_NUMBER_EX@@AEAV?$CHeapPtr@U_STORAGE_DESCRIPTOR_HEADER@@VCCRTAllocator@ATL@@@ATL@@AEAK@Z`
- size: `2358`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, __int64, _DWORD *, struct _DISK_EXTENT *, _OWORD *OutputBuffer, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013b48`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x18000891c`
- `0x18000d4f0`
- `0x18000d9bc`
- `0x18000e2f8`
- `0x18000e574`
- `0x18000e748`
- `0x18000ef90`
- `0x180010160`
- `0x180010460`
- `0x180012940`
- `0x1800129b0`
- `0x180037620`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x18000dbbf`
- `ntdll!NtQueryVolumeInformationFile` at `0x18000dbbf`
- `ntdll!RtlGetThreadErrorMode` at `0x18000daf0`
- `ntdll!RtlGetThreadErrorMode` at `0x18000daf0`
- `ntdll!NtOpenFile` at `0x18000db35`
- `ntdll!NtOpenFile` at `0x18000de63`
- `ntdll!NtOpenFile` at `0x18000db35`
- `ntdll!NtOpenFile` at `0x18000de63`

## pseudocode

```c
__int64 __fastcall IsQualifiedVolume(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        _DWORD *a4,
        struct _DISK_EXTENT *a5,
        _OWORD *OutputBuffer,
        __int64 a7,
        __int64 a8)
{
  USHORT Length; // cx
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v13; // r8
  USHORT v14; // ax
  ULONG ThreadErrorMode; // eax
  NTSTATUS v16; // eax
  unsigned int v17; // edi
  NTSTATUS v18; // eax
  NTSTATUS v19; // edi
  int v20; // eax
  PVOID *v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  NTSTATUS VolumeDiskExtent; // eax
  _QWORD *v27; // rcx
  int v28; // edx
  __int64 v29; // r12
  _QWORD *v30; // rcx
  int v31; // edx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  int DeviceNumber; // eax
  _QWORD *v37; // rcx
  int v38; // edx
  __int64 v39; // r12
  int v40; // eax
  HANDLE Handle; // [rsp+30h] [rbp-C9h] BYREF
  int v43; // [rsp+38h] [rbp-C1h]
  char v44; // [rsp+3Ch] [rbp-BDh]
  const char *v45; // [rsp+40h] [rbp-B9h] BYREF
  int v46; // [rsp+48h] [rbp-B1h]
  void *FileHandle; // [rsp+50h] [rbp-A9h] BYREF
  int v48; // [rsp+58h] [rbp-A1h]
  char v49; // [rsp+5Ch] [rbp-9Dh]
  ULONG OldMode; // [rsp+60h] [rbp-99h] BYREF
  char v51; // [rsp+64h] [rbp-95h]
  __int64 v52; // [rsp+68h] [rbp-91h]
  USHORT v53; // [rsp+70h] [rbp-89h]
  USHORT v54; // [rsp+72h] [rbp-87h]
  int v55; // [rsp+74h] [rbp-85h]
  char *v56; // [rsp+78h] [rbp-81h]
  struct _DISK_EXTENT *v57; // [rsp+80h] [rbp-79h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-71h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-61h] BYREF
  _OWORD FsInformation[3]; // [rsp+C8h] [rbp-31h] BYREF

  Length = GlobalIndentString.Length;
  v52 = a8;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v57 = a5;
  v45 = "IsQualifiedVolume";
  v13 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v13 + 16) = "IsQualifiedVolume";
  v14 = Length;
  if ( ++*(_WORD *)(v13 + 8) < Length )
  {
    v14 = *(_WORD *)(v13 + 8);
    Length = v14;
  }
  v53 = v14;
  v55 = 0;
  v56 = off_180047060;
  v54 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"IsQualifiedVolume");
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  *(_OWORD *)&a5->DiskNumber = 0;
  a5->ExtentLength.QuadPart = 0;
  *OutputBuffer = 0;
  ObjectAttributes.RootDirectory = 0;
  OutputBuffer[1] = 0;
  *((_QWORD *)OutputBuffer + 4) = 0;
  IoStatusBlock = 0;
  v51 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ThreadErrorMode = RtlGetThreadErrorMode();
  CThreadErrorMode::SetThreadErrorMode(&OldMode, ThreadErrorMode | 0x10);
  FileHandle = 0;
  v48 = 0;
  v49 = 0;
  v16 = NtOpenFile(&FileHandle, 0x1000A0u, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
  if ( v16 < 0 )
  {
    v17 = v16 | 0x10000000;
    v46 = v16 | 0x10000000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
        (_DWORD)a2,
        v16);
    }
    goto LABEL_146;
  }
  memset(FsInformation, 0, 44);
  v18 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x2Cu, FileFsAttributeInformation);
  v19 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
        (_DWORD)a2,
        v18);
    }
    v17 = v19 | 0x10000000;
    v46 = v17;
    goto LABEL_146;
  }
  if ( (FsInformation[0] & 0x80000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, a2);
    }
    v46 = 1;
    goto LABEL_24;
  }
  v20 = IsVolumeEnabledForScrub(FileHandle);
  v17 = 1;
  v46 = v20;
  if ( v20 != 1 )
  {
    if ( v20 )
    {
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
            (_DWORD)a2,
            v20);
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 && *((_BYTE *)v21 + 25) >= 3u )
        {
          v22 = 35;
          goto LABEL_43;
        }
      }
    }
    else
    {
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v22 = 33;
LABEL_43:
        WPP_SF_Z(v21[2], v22, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, a2);
      }
    }
    *a4 = 0;
    if ( *(_DWORD *)(a1 + 8) )
      goto LABEL_60;
    v23 = IsVolumeEnabledForDedup(FileHandle);
    if ( v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
          (_DWORD)a2,
          v23);
      }
LABEL_60:
      Handle = 0;
      v43 = 0;
      v44 = 0;
      VolumeDiskExtent = NtOpenFile(&Handle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
      if ( VolumeDiskExtent < 0 )
      {
        v17 = VolumeDiskExtent | 0x10000000;
        v46 = VolumeDiskExtent | 0x10000000;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_66;
        }
        v28 = 39;
        goto LABEL_65;
      }
      if ( (*(_BYTE *)a4 & 4) != 0 )
      {
        DeviceNumber = StorageGetDeviceNumber(Handle, OutputBuffer);
        if ( DeviceNumber >= 0 )
        {
          v39 = v52;
          v40 = IsSpacePortDevice(OutputBuffer, Handle, a7, v52);
          if ( v40 >= 0 )
          {
            if ( v40 == 1 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, a2);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, a2);
              }
              *a4 |= 2u;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Zd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
              (_DWORD)a2,
              v40);
          }
          DeviceNumber = IsDataRedundantVolume(OutputBuffer, Handle, a7, v39);
          if ( DeviceNumber >= 0 )
          {
            if ( DeviceNumber == 1 )
            {
              v34 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
              {
                goto LABEL_140;
              }
              v35 = 52;
            }
            else
            {
              *a4 |= 1u;
              v34 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
              {
                goto LABEL_140;
              }
              v35 = 53;
            }
            goto LABEL_139;
          }
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_140;
          }
          v38 = 51;
        }
        else
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_140;
          }
          v38 = 47;
        }
        WPP_SF_Zd(v37[2], v38, (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, (_DWORD)a2, DeviceNumber);
      }
      else
      {
        VolumeDiskExtent = StorageGetDeviceNumber(Handle, OutputBuffer);
        v46 = VolumeDiskExtent;
        v17 = VolumeDiskExtent;
        if ( VolumeDiskExtent < 0 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_66;
          }
          v28 = 40;
          goto LABEL_65;
        }
        v29 = v52;
        v46 = IsSpacePortDevice(OutputBuffer, Handle, a7, v52);
        v17 = v46;
        if ( v46 < 0 )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_66;
          }
          v31 = 41;
          goto LABEL_78;
        }
        if ( v46 == 1 )
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_99;
          }
          v33 = 42;
LABEL_98:
          WPP_SF_Z(v32[2], v33, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, a2);
LABEL_99:
          CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&Handle);
LABEL_24:
          v17 = 1;
          goto LABEL_146;
        }
        *a4 |= 2u;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, a2);
        }
        v46 = IsDataRedundantVolume(OutputBuffer, Handle, a7, v29);
        v17 = v46;
        if ( v46 < 0 )
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_66;
          }
          v31 = 44;
LABEL_78:
          WPP_SF_Zd(v30[2], v31, (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, (_DWORD)a2, v17);
          goto LABEL_66;
        }
        if ( v46 == 1 )
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_99;
          }
          v33 = 45;
          goto LABEL_98;
        }
        *a4 |= 1u;
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v35 = 46;
LABEL_139:
          WPP_SF_Z(v34[2], v35, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, a2);
        }
      }
LABEL_140:
      VolumeDiskExtent = QueryVolumeDiskExtent(Handle, v57);
      v46 = VolumeDiskExtent;
      v17 = VolumeDiskExtent;
      if ( VolumeDiskExtent >= 0 )
      {
        v46 = 0;
        CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&Handle);
        v17 = 0;
        goto LABEL_146;
      }
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v28 = 54;
LABEL_65:
      WPP_SF_Zd(
        v27[2],
        v28,
        (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
        (_DWORD)a2,
        VolumeDiskExtent);
LABEL_66:
      CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&Handle);
      goto LABEL_146;
    }
    if ( v23 == 1 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_60;
      }
      v25 = 37;
    }
    else
    {
      *a4 |= 4u;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_60;
      }
      v25 = 38;
    }
    WPP_SF_Z(v24[2], v25, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, a2);
    goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, a2);
  }
LABEL_146:
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  CThreadErrorMode::~CThreadErrorMode((CThreadErrorMode *)&OldMode);
  CHResultImp::~CHResultImp((CHResultImp *)&v45);
  return v17;
}

```

## disassembly

```asm
0x18000d9bc  mov     [rsp-8+arg_0], rbx
0x18000d9c1  push    rbp
0x18000d9c2  push    rsi
0x18000d9c3  push    rdi
0x18000d9c4  push    r12
0x18000d9c6  push    r13
0x18000d9c8  push    r14
0x18000d9ca  push    r15
0x18000d9cc  lea     rbp, [rsp-7]
0x18000d9d1  sub     rsp, 100h
0x18000d9d8  mov     rax, cs:__security_cookie
0x18000d9df  xor     rax, rsp
0x18000d9e2  mov     [rbp+37h+var_38], rax
0x18000d9e6  mov     rax, [rbp+37h+arg_38]
0x18000d9ea  lea     r10, aIsqualifiedvol; "IsQualifiedVolume"
0x18000d9f1  mov     rbx, [rbp+37h+arg_20]
0x18000d9f5  mov     rsi, rdx
0x18000d9f8  mov     edx, cs:_tls_index
0x18000d9fe  mov     r12, rcx
0x18000da01  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18000da08  mov     r14, r9
0x18000da0b  mov     r15, [rbp+37h+OutputBuffer]
0x18000da0f  mov     r9d, 1
0x18000da15  mov     r13, [rbp+37h+arg_30]
0x18000da19  mov     [rsp+130h+var_C8], rax
0x18000da1e  mov     rax, gs:58h
0x18000da27  mov     [rbp+37h+var_B0], rbx
0x18000da2b  mov     [rsp+130h+var_F0], r10
0x18000da30  mov     r8, [rax+rdx*8]
0x18000da34  mov     eax, 10h
0x18000da39  mov     edx, 8
0x18000da3e  mov     [rax+r8], r10
0x18000da42  movzx   eax, cx
0x18000da45  add     [rdx+r8], r9w
0x18000da4a  movzx   edx, word ptr [rdx+r8]
0x18000da4f  cmp     dx, cx
0x18000da52  cmovb   ax, dx
0x18000da56  cmovb   cx, dx
0x18000da5a  mov     [rsp+130h+var_C0], ax
0x18000da5f  xor     eax, eax
0x18000da61  mov     [rsp+130h+var_BC], eax
0x18000da65  mov     rax, cs:off_180047060; "                                       "...
0x18000da6c  mov     [rsp+130h+var_B8], rax
0x18000da71  mov     [rsp+130h+var_BE], cx
0x18000da76  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da7d  lea     rax, WPP_GLOBAL_Control
0x18000da84  cmp     rcx, rax
0x18000da87  jz      short loc_18000DAAC
0x18000da89  test    [rcx+1Ch], r9b
0x18000da8d  jz      short loc_18000DAAC
0x18000da8f  cmp     byte ptr [rcx+19h], 5
0x18000da93  jb      short loc_18000DAAC
0x18000da95  mov     rcx, [rcx+10h]; LoggerHandle
0x18000da99  lea     edx, [r9+0Ch]
0x18000da9d  lea     r9, [rsp+130h+var_C0]
0x18000daa2  mov     qword ptr [rsp+130h+ShareAccess], r10; __int64
0x18000daa7  call    WPP_SF_aZs
0x18000daac  xorps   xmm0, xmm0
0x18000daaf  mov     qword ptr [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x18000dab7  xor     eax, eax
0x18000dab9  mov     [rbp+37h+ObjectAttributes.ObjectName], rsi
0x18000dabd  xorps   xmm1, xmm1
0x18000dac0  mov     qword ptr [rbp+37h+ObjectAttributes.Attributes], 0C0h
0x18000dac8  movups  xmmword ptr [rbx], xmm1
0x18000dacb  mov     [rbx+10h], rax
0x18000dacf  xor     edi, edi
0x18000dad1  movups  xmmword ptr [r15], xmm0
0x18000dad5  mov     [rbp+37h+ObjectAttributes.RootDirectory], rdi
0x18000dad9  movups  xmmword ptr [r15+10h], xmm0
0x18000dade  mov     [r15+20h], rax
0x18000dae2  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x18000dae6  mov     [rsp+130h+var_CC], dil
0x18000daeb  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000daf0  call    cs:__imp_RtlGetThreadErrorMode
0x18000daf6  or      eax, 10h
0x18000daf9  lea     rcx, [rsp+130h+OldMode]; OldMode
0x18000dafe  mov     edx, eax; NewMode
0x18000db00  call    ?SetThreadErrorMode@CThreadErrorMode@@QEAAJK@Z; CThreadErrorMode::SetThreadErrorMode(ulong)
0x18000db05  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x18000db09  mov     [rsp+130h+OpenOptions], 60h ; '`'; OpenOptions
0x18000db11  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18000db15  mov     [rsp+130h+FileHandle], rdi
0x18000db1a  mov     edx, 1000A0h; DesiredAccess
0x18000db1f  mov     [rsp+130h+var_D8], edi
0x18000db23  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x18000db28  mov     [rsp+130h+var_D4], dil
0x18000db2d  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x18000db35  call    cs:__imp_NtOpenFile
0x18000db3b  test    eax, eax
0x18000db3d  jns     short loc_18000DB95
0x18000db3f  mov     edi, eax
0x18000db41  bts     edi, 1Ch
0x18000db45  mov     [rsp+130h+var_E8], edi
0x18000db49  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db50  lea     rdx, WPP_GLOBAL_Control
0x18000db57  cmp     rcx, rdx
0x18000db5a  jz      loc_18000E2AB
0x18000db60  test    byte ptr [rcx+1Ch], 1
0x18000db64  jz      loc_18000E2AB
0x18000db6a  cmp     byte ptr [rcx+19h], 2
0x18000db6e  jb      loc_18000E2AB
0x18000db74  mov     rcx, [rcx+10h]
0x18000db78  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000db7f  mov     edx, 1Dh
0x18000db84  mov     [rsp+130h+ShareAccess], eax
0x18000db88  mov     r9, rsi
0x18000db8b  call    WPP_SF_Zd
0x18000db90  jmp     loc_18000E2AB
0x18000db95  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x18000db9a  lea     r8, [rbp+37h+FsInformation]; FsInformation
0x18000db9e  xorps   xmm0, xmm0
0x18000dba1  mov     [rsp+130h+ShareAccess], 5; FsInformationClass
0x18000dba9  movups  xmmword ptr [rbp+37h+var_58], xmm0
0x18000dbad  mov     r9d, 2Ch ; ','; Length
0x18000dbb3  lea     rdx, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x18000dbb7  movups  xmmword ptr [rbp+37h+var_58+0Ch], xmm0
0x18000dbbb  movups  [rbp+37h+FsInformation], xmm0
0x18000dbbf  call    cs:__imp_NtQueryVolumeInformationFile
0x18000dbc5  mov     edi, eax
0x18000dbc7  test    eax, eax
0x18000dbc9  jns     short loc_18000DC13
0x18000dbcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbd2  lea     rdx, WPP_GLOBAL_Control
0x18000dbd9  cmp     rcx, rdx
0x18000dbdc  jz      short loc_18000DC06
0x18000dbde  test    byte ptr [rcx+1Ch], 1
0x18000dbe2  jz      short loc_18000DC06
0x18000dbe4  cmp     byte ptr [rcx+19h], 2
0x18000dbe8  jb      short loc_18000DC06
0x18000dbea  mov     rcx, [rcx+10h]
0x18000dbee  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000dbf5  mov     edx, 1Eh
0x18000dbfa  mov     [rsp+130h+ShareAccess], eax
0x18000dbfe  mov     r9, rsi
0x18000dc01  call    WPP_SF_Zd
0x18000dc06  bts     edi, 1Ch
0x18000dc0a  mov     [rsp+130h+var_E8], edi
0x18000dc0e  jmp     loc_18000E2AB
0x18000dc13  test    dword ptr [rbp+37h+FsInformation], 80000h
0x18000dc1a  jz      short loc_18000DC65
0x18000dc1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc23  lea     rdx, WPP_GLOBAL_Control
0x18000dc2a  cmp     rcx, rdx
0x18000dc2d  jz      short loc_18000DC53
0x18000dc2f  test    byte ptr [rcx+1Ch], 1
0x18000dc33  jz      short loc_18000DC53
0x18000dc35  cmp     byte ptr [rcx+19h], 4
0x18000dc39  jb      short loc_18000DC53
0x18000dc3b  mov     rcx, [rcx+10h]
0x18000dc3f  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000dc46  mov     edx, 1Fh
0x18000dc4b  mov     r9, rsi
0x18000dc4e  call    WPP_SF_Z
0x18000dc53  mov     [rsp+130h+var_E8], 1
0x18000dc5b  mov     edi, 1
0x18000dc60  jmp     loc_18000E2AB
0x18000dc65  mov     rcx, [rsp+130h+FileHandle]; Handle
0x18000dc6a  call    ?IsVolumeEnabledForScrub@@YAJPEAX@Z; IsVolumeEnabledForScrub(void *)
0x18000dc6f  mov     edi, 1
0x18000dc74  mov     [rsp+130h+var_E8], eax
0x18000dc78  cmp     eax, edi
0x18000dc7a  jnz     short loc_18000DCC2
0x18000dc7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc83  lea     rdx, WPP_GLOBAL_Control
0x18000dc8a  cmp     rcx, rdx
0x18000dc8d  jz      loc_18000E2AB
0x18000dc93  test    [rcx+1Ch], dil
0x18000dc97  jz      loc_18000E2AB
0x18000dc9d  cmp     byte ptr [rcx+19h], 4
0x18000dca1  jb      loc_18000E2AB
0x18000dca7  mov     rcx, [rcx+10h]
0x18000dcab  lea     edx, [rdi+1Fh]
0x18000dcae  mov     r9, rsi
0x18000dcb1  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000dcb8  call    WPP_SF_Z
0x18000dcbd  jmp     loc_18000E2AB
0x18000dcc2  lea     rbx, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000dcc9  test    eax, eax
0x18000dccb  jnz     short loc_18000DCF1
0x18000dccd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcd4  lea     rdx, WPP_GLOBAL_Control
0x18000dcdb  cmp     rcx, rdx
0x18000dcde  jz      short loc_18000DD5B
0x18000dce0  test    [rcx+1Ch], dil
0x18000dce4  jz      short loc_18000DD5B
0x18000dce6  cmp     byte ptr [rcx+19h], 4
0x18000dcea  jb      short loc_18000DD5B
0x18000dcec  lea     edx, [rax+21h]
0x18000dcef  jmp     short loc_18000DD4C
0x18000dcf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcf8  lea     rdx, WPP_GLOBAL_Control
0x18000dcff  cmp     rcx, rdx
0x18000dd02  jz      short loc_18000DD5B
0x18000dd04  test    [rcx+1Ch], dil
0x18000dd08  jz      short loc_18000DD2F
0x18000dd0a  cmp     byte ptr [rcx+19h], 2
0x18000dd0e  jb      short loc_18000DD2F
0x18000dd10  mov     rcx, [rcx+10h]
0x18000dd14  mov     edx, 22h ; '"'
0x18000dd19  mov     r9, rsi
0x18000dd1c  mov     [rsp+130h+ShareAccess], eax
0x18000dd20  mov     r8, rbx
0x18000dd23  call    WPP_SF_Zd
0x18000dd28  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd2f  lea     rax, WPP_GLOBAL_Control
0x18000dd36  cmp     rcx, rax
0x18000dd39  jz      short loc_18000DD5B
0x18000dd3b  test    [rcx+1Ch], dil
0x18000dd3f  jz      short loc_18000DD5B
0x18000dd41  cmp     byte ptr [rcx+19h], 3
0x18000dd45  jb      short loc_18000DD5B
0x18000dd47  mov     edx, 23h ; '#'
0x18000dd4c  mov     rcx, [rcx+10h]
0x18000dd50  mov     r9, rsi
0x18000dd53  mov     r8, rbx
0x18000dd56  call    WPP_SF_Z
0x18000dd5b  mov     dword ptr [r14], 0
0x18000dd62  cmp     dword ptr [r12+8], 0
0x18000dd68  jnz     loc_18000DE24
0x18000dd6e  mov     rcx, [rsp+130h+FileHandle]; Handle
0x18000dd73  call    ?IsVolumeEnabledForDedup@@YAJPEAX@Z; IsVolumeEnabledForDedup(void *)
0x18000dd78  test    eax, eax
0x18000dd7a  jns     short loc_18000DDC1
0x18000dd7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd83  lea     r12, WPP_GLOBAL_Control
0x18000dd8a  cmp     rcx, r12
0x18000dd8d  jz      loc_18000DE2B
0x18000dd93  test    [rcx+1Ch], dil
0x18000dd97  jz      loc_18000DE2B
0x18000dd9d  cmp     byte ptr [rcx+19h], 2
0x18000dda1  jb      loc_18000DE2B
0x18000dda7  mov     rcx, [rcx+10h]
0x18000ddab  mov     edx, 24h ; '$'
0x18000ddb0  mov     r9, rsi
0x18000ddb3  mov     [rsp+130h+ShareAccess], eax
0x18000ddb7  mov     r8, rbx
0x18000ddba  call    WPP_SF_Zd
0x18000ddbf  jmp     short loc_18000DE2B
0x18000ddc1  cmp     eax, edi
0x18000ddc3  jnz     short loc_18000DDFA
0x18000ddc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddcc  lea     r12, WPP_GLOBAL_Control
0x18000ddd3  cmp     rcx, r12
0x18000ddd6  jz      short loc_18000DE2B
0x18000ddd8  test    [rcx+1Ch], dil
0x18000dddc  jz      short loc_18000DE2B
0x18000ddde  cmp     byte ptr [rcx+19h], 4
0x18000dde2  jb      short loc_18000DE2B
0x18000dde4  mov     edx, 25h ; '%'
0x18000dde9  mov     rcx, [rcx+10h]
0x18000dded  mov     r9, rsi
0x18000ddf0  mov     r8, rbx
0x18000ddf3  call    WPP_SF_Z
0x18000ddf8  jmp     short loc_18000DE2B
0x18000ddfa  or      dword ptr [r14], 4
0x18000ddfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de05  lea     r12, WPP_GLOBAL_Control
0x18000de0c  cmp     rcx, r12
0x18000de0f  jz      short loc_18000DE2B
0x18000de11  test    [rcx+1Ch], dil
0x18000de15  jz      short loc_18000DE2B
0x18000de17  cmp     byte ptr [rcx+19h], 4
0x18000de1b  jb      short loc_18000DE2B
0x18000de1d  mov     edx, 26h ; '&'
0x18000de22  jmp     short loc_18000DDE9
0x18000de24  lea     r12, WPP_GLOBAL_Control
0x18000de2b  mov     [rsp+130h+OpenOptions], 60h ; '`'; OpenOptions
0x18000de33  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x18000de37  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18000de3b  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x18000de43  mov     edx, 100080h; DesiredAccess
0x18000de48  mov     [rsp+130h+Handle], 0
0x18000de51  lea     rcx, [rsp+130h+Handle]; FileHandle
0x18000de56  mov     [rsp+130h+var_F8], 0
0x18000de5e  mov     [rsp+130h+var_F4], 0
0x18000de63  call    cs:__imp_NtOpenFile
0x18000de69  test    eax, eax
0x18000de6b  jns     short loc_18000DEB6
0x18000de6d  mov     edi, eax
0x18000de6f  bts     edi, 1Ch
0x18000de73  mov     [rsp+130h+var_E8], edi
0x18000de77  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de7e  cmp     rcx, r12
0x18000de81  jz      short loc_18000DEA7
0x18000de83  test    byte ptr [rcx+1Ch], 1
0x18000de87  jz      short loc_18000DEA7
0x18000de89  cmp     byte ptr [rcx+19h], 2
0x18000de8d  jb      short loc_18000DEA7
0x18000de8f  mov     edx, 27h ; '''
0x18000de94  mov     [rsp+130h+ShareAccess], eax
0x18000de98  mov     rcx, [rcx+10h]
0x18000de9c  mov     r9, rsi
0x18000de9f  mov     r8, rbx
0x18000dea2  call    WPP_SF_Zd
0x18000dea7  lea     rcx, [rsp+130h+Handle]
0x18000deac  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x18000deb1  jmp     loc_18000E2AB
0x18000deb6  test    byte ptr [r14], 4
0x18000deba  mov     rdx, r15; OutputBuffer
0x18000debd  mov     rcx, [rsp+130h+Handle]; Handle
  ... truncated ...
```
