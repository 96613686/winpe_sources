# CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180004a60`
- end: `0x180005214`
- name: `?GetDiskDevicePnpPathFromVolumePath@CEnhancedStorageActEnumerator@@AEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1972`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x180005960`

## callees

- `0x180003924`
- `0x180003bdc`
- `0x180003c54`
- `0x180003c94`
- `0x180003ce0`
- `0x180003df0`
- `0x180003ed0`
- `0x180004a60`
- `0x1800060e8`
- `0x180006148`
- `0x18000c4f0`

## import_xrefs

- `msvcrt!free` at `0x180005109`
- `msvcrt!free` at `0x180005175`
- `msvcrt!free` at `0x180005109`
- `msvcrt!free` at `0x180005175`
- `msvcrt!malloc` at `0x180004c3d`
- `msvcrt!malloc` at `0x180004ea2`
- `msvcrt!malloc` at `0x180004c3d`
- `msvcrt!malloc` at `0x180004ea2`
- `KERNEL32!CreateFileW` at `0x180004b39`
- `KERNEL32!CreateFileW` at `0x180004fa4`
- `KERNEL32!CreateFileW` at `0x180004b39`
- `KERNEL32!CreateFileW` at `0x180004fa4`
- `KERNEL32!GetLastError` at `0x180004b50`
- `KERNEL32!GetLastError` at `0x180004be1`
- `KERNEL32!GetLastError` at `0x180004cc8`
- `KERNEL32!GetLastError` at `0x180004d79`
- `KERNEL32!GetLastError` at `0x180004e19`
- `KERNEL32!GetLastError` at `0x180004e87`
- `KERNEL32!GetLastError` at `0x180004f2e`
- `KERNEL32!GetLastError` at `0x180004fb2`
- `KERNEL32!GetLastError` at `0x18000503f`
- `KERNEL32!GetLastError` at `0x180004b50`
- `KERNEL32!GetLastError` at `0x180004be1`
- `KERNEL32!GetLastError` at `0x180004cc8`
- `KERNEL32!GetLastError` at `0x180004d79`
- `KERNEL32!GetLastError` at `0x180004e19`
- `KERNEL32!GetLastError` at `0x180004e87`
- `KERNEL32!GetLastError` at `0x180004f2e`
- `KERNEL32!GetLastError` at `0x180004fb2`
- `KERNEL32!GetLastError` at `0x18000503f`
- `KERNEL32!DeviceIoControl` at `0x180004bd3`
- `KERNEL32!DeviceIoControl` at `0x180004cbe`
- `KERNEL32!DeviceIoControl` at `0x180005035`
- `KERNEL32!DeviceIoControl` at `0x180004bd3`
- `KERNEL32!DeviceIoControl` at `0x180004cbe`
- `KERNEL32!DeviceIoControl` at `0x180005035`
- `KERNEL32!CloseHandle` at `0x18000507c`
- `KERNEL32!CloseHandle` at `0x180005180`
- `KERNEL32!CloseHandle` at `0x18000518e`
- `KERNEL32!CloseHandle` at `0x18000507c`
- `KERNEL32!CloseHandle` at `0x180005180`
- `KERNEL32!CloseHandle` at `0x18000518e`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180004e0f`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180004e0f`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180004e7f`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180004f24`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180004e7f`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180004f24`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180005167`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180005167`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180004d67`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180004d67`

## string_xrefs

- `0x180004aff`: `CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  const WCHAR *v3; // r13
  HANDLE FileW; // rcx
  signed int LastError; // eax
  PVOID *v6; // rcx
  __int64 v7; // r14
  DWORD v8; // eax
  DWORD v9; // r12d
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  signed int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  HDEVINFO ClassDevsW; // rax
  WCHAR *v17; // rbx
  signed int v18; // eax
  HDEVINFO v19; // rcx
  DWORD v20; // r13d
  signed int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  HDEVINFO v25; // r14
  BOOL DeviceInterfaceDetailW; // ebx
  DWORD v27; // eax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v28; // rax
  signed int v29; // eax
  signed int v30; // eax
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // ebx
  int v35; // [rsp+40h] [rbp-2D8h] BYREF
  const WCHAR *v36; // [rsp+48h] [rbp-2D0h]
  DWORD BytesReturned; // [rsp+50h] [rbp-2C8h] BYREF
  DWORD RequiredSize; // [rsp+54h] [rbp-2C4h] BYREF
  DWORD nOutBufferSize; // [rsp+58h] [rbp-2C0h] BYREF
  HDEVINFO DeviceInfoSet; // [rsp+60h] [rbp-2B8h]
  int v41; // [rsp+68h] [rbp-2B0h]
  HANDLE hDevice; // [rsp+70h] [rbp-2A8h]
  int v43; // [rsp+78h] [rbp-2A0h] BYREF
  __int64 v44; // [rsp+80h] [rbp-298h]
  __int64 v45; // [rsp+88h] [rbp-290h]
  void *Block; // [rsp+90h] [rbp-288h]
  const WCHAR *v47; // [rsp+98h] [rbp-280h]
  __int64 v48; // [rsp+A0h] [rbp-278h] BYREF
  int v49; // [rsp+A8h] [rbp-270h]
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+B0h] [rbp-268h] BYREF
  _BYTE v51[272]; // [rsp+D0h] [rbp-248h] BYREF
  _BYTE OutBuffer[256]; // [rsp+1E0h] [rbp-138h] BYREF

  v44 = a3;
  v3 = a2;
  v36 = a2;
  v47 = a2;
  v35 = -2147023728;
  BytesReturned = 0;
  v48 = 0;
  v49 = 0;
  nOutBufferSize = 256;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, a3, (_DWORD)a2, a3);
  CESTTrackFn::CESTTrackFn(
    (CESTTrackFn *)v51,
    "CEnhancedStorageActEnumerator::GetDiskDevicePnpPathFromVolumePath",
    &v35);
  FileW = CreateFileW(v3, 0, 1u, 0, 3u, 0, 0);
  hDevice = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v35 = LastError;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
        (unsigned int)LastError);
      goto LABEL_92;
    }
    goto LABEL_93;
  }
  v7 = -1;
  if ( DeviceIoControl(FileW, 0x560000u, 0, 0, OutBuffer, nOutBufferSize, &BytesReturned, 0) )
  {
    v11 = OutBuffer;
  }
  else
  {
    v8 = GetLastError();
    if ( v8 != 234 )
    {
      v35 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
          v8,
          -2147418113);
      goto LABEL_90;
    }
    v9 = BytesReturned;
    v10 = malloc(BytesReturned);
    v11 = v10;
    if ( !v10 )
    {
      v35 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
          "lpVolumeDiskExtents");
      goto LABEL_90;
    }
    nOutBufferSize = v9;
    if ( !DeviceIoControl(hDevice, 0x560000u, 0, 0, v10, v9, &BytesReturned, 0) )
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v35 = v12;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_90;
      v14 = 38;
      v15 = (unsigned int)v12;
LABEL_25:
      WPP_SF_d(v13[2], v14, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, v15);
      goto LABEL_90;
    }
  }
  if ( *v11 != 1 )
  {
    v15 = 2147942450LL;
    v35 = -2147024846;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_90;
    v14 = 39;
    goto LABEL_25;
  }
  v41 = v11[2];
  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_DISK, 0, 0, 0x12u);
  DeviceInfoSet = ClassDevsW;
  if ( !ClassDevsW )
  {
    v17 = 0;
    v18 = GetLastError();
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    v35 = v18;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
        (unsigned int)v18);
    v19 = DeviceInfoSet;
    goto LABEL_87;
  }
  v20 = 0;
  while ( 1 )
  {
    RequiredSize = 0;
    memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
    DeviceInterfaceData.cbSize = 32;
    if ( !SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &GUID_DEVINTERFACE_DISK, v20, &DeviceInterfaceData) )
    {
      v21 = GetLastError();
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      v35 = v21;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v23 = 41;
        v24 = (unsigned int)v21;
        goto LABEL_82;
      }
      goto LABEL_83;
    }
    v25 = DeviceInfoSet;
    DeviceInterfaceDetailW = SetupDiGetDeviceInterfaceDetailW(
                               DeviceInfoSet,
                               &DeviceInterfaceData,
                               0,
                               0,
                               &RequiredSize,
                               0);
    v27 = GetLastError();
    if ( DeviceInterfaceDetailW || v27 != 122 )
    {
      v24 = 2147549183LL;
      v35 = -2147418113;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v23 = 42;
LABEL_82:
        WPP_SF_d(v22[2], v23, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, v24);
      }
LABEL_83:
      v17 = 0;
      goto LABEL_84;
    }
    v28 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)malloc(RequiredSize);
    v17 = (WCHAR *)v28;
    Block = v28;
    if ( !v28 )
    {
      v35 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
          "pDiDetailData");
LABEL_84:
      v7 = -1;
      goto LABEL_85;
    }
    v28->cbSize = 8;
    if ( !SetupDiGetDeviceInterfaceDetailW(v25, &DeviceInterfaceData, v28, RequiredSize, 0, 0) )
    {
      v29 = GetLastError();
      if ( v29 > 0 )
        v29 = (unsigned __int16)v29 | 0x80070000;
      v35 = v29;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
          (unsigned int)v29);
      goto LABEL_84;
    }
    v7 = (__int64)CreateFileW(v17 + 2, 0, 1u, 0, 3u, 0, 0);
    if ( v7 == -1 )
    {
      v30 = GetLastError();
      if ( v30 > 0 )
        v30 = (unsigned __int16)v30 | 0x80070000;
      v35 = v30;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_85;
      v32 = 45;
      goto LABEL_64;
    }
    if ( !DeviceIoControl((HANDLE)v7, 0x2D1080u, 0, 0, &v48, 0xCu, &nOutBufferSize, 0) )
    {
      v30 = GetLastError();
      if ( v30 > 0 )
        v30 = (unsigned __int16)v30 | 0x80070000;
      v35 = v30;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_85;
      v32 = 46;
LABEL_64:
      WPP_SF_d(v31[2], v32, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, (unsigned int)v30);
      goto LABEL_85;
    }
    CloseHandle((HANDLE)v7);
    v7 = -1;
    v45 = -1;
    if ( HIDWORD(v48) == v41 )
      break;
    ++v20;
    free(v17);
    v17 = 0;
    if ( v35 == -2147024637 )
      goto LABEL_85;
    ClassDevsW = DeviceInfoSet;
  }
  try
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(v44, v17 + 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, v17 + 2);
    v35 = 0;
  }
  catch ( ATL::CAtlException v43 )
  {
    v35 = v43;
    if ( v43 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
        (unsigned int)v43);
    v7 = v45;
    v17 = (WCHAR *)Block;
    LODWORD(v3) = (_DWORD)v47;
    goto LABEL_86;
  }
LABEL_85:
  LODWORD(v3) = (_DWORD)v36;
LABEL_86:
  v19 = DeviceInfoSet;
  if ( DeviceInfoSet != (HDEVINFO)-1LL )
LABEL_87:
    SetupDiDestroyDeviceInfoList(v19);
  if ( v17 )
    free(v17);
LABEL_90:
  CloseHandle(hDevice);
  if ( v7 != -1 )
    CloseHandle((HANDLE)v7);
LABEL_92:
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_93:
  if ( v35 == -2147024637 )
  {
    v35 = -2147023728;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
      WPP_SF_Sd(
        (unsigned int)v6[2],
        49,
        (unsigned int)&WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
        (_DWORD)v3,
        144);
  }
  v33 = v35;
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v51);
  return v33;
}

```

## disassembly

```asm
0x180004a60  mov     [rsp+arg_0], rbx
0x180004a65  push    rsi
0x180004a66  push    r12
0x180004a68  push    r13
0x180004a6a  push    r14
0x180004a6c  push    r15
0x180004a6e  sub     rsp, 2F0h
0x180004a75  mov     rax, cs:__security_cookie
0x180004a7c  xor     rax, rsp
0x180004a7f  mov     [rsp+318h+var_38], rax
0x180004a87  mov     rax, r8
0x180004a8a  mov     [rsp+318h+var_298], rax
0x180004a92  mov     r13, rdx
0x180004a95  mov     [rsp+318h+var_2D0], rdx
0x180004a9a  mov     [rsp+318h+var_280], rdx
0x180004aa2  mov     [rsp+318h+var_2D8], 80070490h
0x180004aaa  mov     [rsp+318h+BytesReturned], 0
0x180004ab2  xor     ecx, ecx
0x180004ab4  mov     [rsp+318h+var_278], rcx
0x180004abc  mov     [rsp+318h+var_270], ecx
0x180004ac3  mov     [rsp+318h+nOutBufferSize], 100h
0x180004acb  lea     rsi, WPP_GLOBAL_Control
0x180004ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ad9  cmp     rcx, rsi
0x180004adc  jz      short loc_180004AFA
0x180004ade  test    byte ptr [rcx+1Ch], 10h
0x180004ae2  jz      short loc_180004AFA
0x180004ae4  mov     edx, 22h ; '"'
0x180004ae9  mov     qword ptr [rsp+318h+dwCreationDisposition], rax
0x180004aee  mov     r9, r13
0x180004af1  mov     rcx, [rcx+10h]
0x180004af5  call    WPP_SF_Sq
0x180004afa  lea     r8, [rsp+318h+var_2D8]; int *
0x180004aff  lea     rdx, aCenhancedstora_5; "CEnhancedStorageActEnumerator::GetDiskD"...
0x180004b06  lea     rcx, [rsp+318h+var_248]; this
0x180004b0e  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x180004b13  nop
0x180004b14  mov     [rsp+318h+hTemplateFile], 0; hTemplateFile
0x180004b1d  mov     [rsp+318h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180004b25  mov     [rsp+318h+dwCreationDisposition], 3; dwCreationDisposition
0x180004b2d  xor     r9d, r9d; lpSecurityAttributes
0x180004b30  xor     edx, edx; dwDesiredAccess
0x180004b32  lea     r8d, [r9+1]; dwShareMode
0x180004b36  mov     rcx, r13; lpFileName
0x180004b39  call    cs:__imp_CreateFileW
0x180004b3f  mov     rcx, rax; hDevice
0x180004b42  mov     [rsp+318h+hDevice], rax
0x180004b47  or      r15, 0FFFFFFFFFFFFFFFFh
0x180004b4b  cmp     rax, r15
0x180004b4e  jnz     short loc_180004B9D
0x180004b50  call    cs:__imp_GetLastError
0x180004b56  test    eax, eax
0x180004b58  jle     short loc_180004B62
0x180004b5a  movzx   eax, ax
0x180004b5d  or      eax, 80070000h
0x180004b62  mov     [rsp+318h+var_2D8], eax
0x180004b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b6d  cmp     rcx, rsi
0x180004b70  jz      loc_18000519B
0x180004b76  test    byte ptr [rcx+1Ch], 2
0x180004b7a  jz      loc_18000519B
0x180004b80  mov     edx, 23h ; '#'
0x180004b85  mov     r9d, eax
0x180004b88  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004b8f  mov     rcx, [rcx+10h]
0x180004b93  call    WPP_SF_d
0x180004b98  jmp     loc_180005194
0x180004b9d  mov     r14, r15
0x180004ba0  mov     [rsp+318h+lpOverlapped], 0; lpOverlapped
0x180004ba9  lea     rax, [rsp+318h+BytesReturned]
0x180004bae  mov     [rsp+318h+hTemplateFile], rax; lpBytesReturned
0x180004bb3  mov     eax, [rsp+318h+nOutBufferSize]
0x180004bb7  mov     [rsp+318h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180004bbb  lea     rax, [rsp+318h+OutBuffer]
0x180004bc3  mov     qword ptr [rsp+318h+dwCreationDisposition], rax; lpOutBuffer
0x180004bc8  xor     r9d, r9d; nInBufferSize
0x180004bcb  xor     r8d, r8d; lpInBuffer
0x180004bce  mov     edx, 560000h; dwIoControlCode
0x180004bd3  call    cs:__imp_DeviceIoControl
0x180004bd9  test    eax, eax
0x180004bdb  jnz     loc_180004D15
0x180004be1  call    cs:__imp_GetLastError
0x180004be7  cmp     eax, 0EAh
0x180004bec  jz      short loc_180004C35
0x180004bee  mov     r9d, 8000FFFFh
0x180004bf4  mov     [rsp+318h+var_2D8], r9d
0x180004bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c00  cmp     rcx, rsi
0x180004c03  jz      loc_18000517B
0x180004c09  test    byte ptr [rcx+1Ch], 2
0x180004c0d  jz      loc_18000517B
0x180004c13  mov     edx, 24h ; '$'
0x180004c18  mov     [rsp+318h+dwCreationDisposition], r9d
0x180004c1d  mov     r9d, eax
0x180004c20  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004c27  mov     rcx, [rcx+10h]
0x180004c2b  call    WPP_SF_dd
0x180004c30  jmp     loc_18000517B
0x180004c35  mov     r12d, [rsp+318h+BytesReturned]
0x180004c3a  mov     ecx, r12d; Size
0x180004c3d  call    cs:__imp_malloc
0x180004c43  mov     rbx, rax
0x180004c46  test    rax, rax
0x180004c49  jnz     short loc_180004C8C
0x180004c4b  mov     [rsp+318h+var_2D8], 8007000Eh
0x180004c53  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c5a  cmp     rcx, rsi
0x180004c5d  jz      loc_18000517B
0x180004c63  test    byte ptr [rcx+1Ch], 2
0x180004c67  jz      loc_18000517B
0x180004c6d  lea     edx, [rax+25h]
0x180004c70  lea     r9, aLpvolumediskex; "lpVolumeDiskExtents"
0x180004c77  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004c7e  mov     rcx, [rcx+10h]
0x180004c82  call    WPP_SF_s
0x180004c87  jmp     loc_18000517B
0x180004c8c  mov     [rsp+318h+nOutBufferSize], r12d
0x180004c91  mov     [rsp+318h+lpOverlapped], 0; lpOverlapped
0x180004c9a  lea     rax, [rsp+318h+BytesReturned]
0x180004c9f  mov     [rsp+318h+hTemplateFile], rax; lpBytesReturned
0x180004ca4  mov     [rsp+318h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x180004ca9  mov     qword ptr [rsp+318h+dwCreationDisposition], rbx; lpOutBuffer
0x180004cae  xor     r9d, r9d; nInBufferSize
0x180004cb1  xor     r8d, r8d; lpInBuffer
0x180004cb4  mov     edx, 560000h; dwIoControlCode
0x180004cb9  mov     rcx, [rsp+318h+hDevice]; hDevice
0x180004cbe  call    cs:__imp_DeviceIoControl
0x180004cc4  test    eax, eax
0x180004cc6  jnz     short loc_180004D1D
0x180004cc8  call    cs:__imp_GetLastError
0x180004cce  test    eax, eax
0x180004cd0  jle     short loc_180004CDA
0x180004cd2  movzx   eax, ax
0x180004cd5  or      eax, 80070000h
0x180004cda  mov     [rsp+318h+var_2D8], eax
0x180004cde  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ce5  cmp     rcx, rsi
0x180004ce8  jz      loc_18000517B
0x180004cee  test    byte ptr [rcx+1Ch], 2
0x180004cf2  jz      loc_18000517B
0x180004cf8  mov     edx, 26h ; '&'
0x180004cfd  mov     r9d, eax
0x180004d00  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004d07  mov     rcx, [rcx+10h]
0x180004d0b  call    WPP_SF_d
0x180004d10  jmp     loc_18000517B
0x180004d15  lea     rbx, [rsp+318h+OutBuffer]
0x180004d1d  cmp     dword ptr [rbx], 1
0x180004d20  jz      short loc_180004D4E
0x180004d22  mov     r9d, 80070032h
0x180004d28  mov     [rsp+318h+var_2D8], r9d
0x180004d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d34  cmp     rcx, rsi
0x180004d37  jz      loc_18000517B
0x180004d3d  test    byte ptr [rcx+1Ch], 2
0x180004d41  jz      loc_18000517B
0x180004d47  mov     edx, 27h ; '''
0x180004d4c  jmp     short loc_180004D00
0x180004d4e  mov     eax, [rbx+8]
0x180004d51  mov     [rsp+318h+var_2B0], eax
0x180004d55  mov     r9d, 12h; Flags
0x180004d5b  xor     r8d, r8d; hwndParent
0x180004d5e  xor     edx, edx; Enumerator
0x180004d60  lea     rcx, GUID_DEVINTERFACE_DISK; ClassGuid
0x180004d67  call    cs:__imp_SetupDiGetClassDevsW
0x180004d6d  mov     [rsp+318h+DeviceInfoSet], rax
0x180004d72  test    rax, rax
0x180004d75  jnz     short loc_180004DC3
0x180004d77  xor     ebx, ebx
0x180004d79  call    cs:__imp_GetLastError
0x180004d7f  test    eax, eax
0x180004d81  jle     short loc_180004D8B
0x180004d83  movzx   eax, ax
0x180004d86  or      eax, 80070000h
0x180004d8b  mov     [rsp+318h+var_2D8], eax
0x180004d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d96  cmp     rcx, rsi
0x180004d99  jz      short loc_180004DB9
0x180004d9b  test    byte ptr [rcx+1Ch], 2
0x180004d9f  jz      short loc_180004DB9
0x180004da1  mov     edx, 28h ; '('
0x180004da6  mov     r9d, eax
0x180004da9  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004db0  mov     rcx, [rcx+10h]
0x180004db4  call    WPP_SF_d
0x180004db9  mov     rcx, [rsp+318h+DeviceInfoSet]
0x180004dbe  jmp     loc_180005167
0x180004dc3  xor     r13d, r13d
0x180004dc6  jmp     short loc_180004DCD
0x180004dc8  mov     rax, [rsp+318h+DeviceInfoSet]
0x180004dcd  mov     [rsp+318h+RequiredSize], 0
0x180004dd5  xorps   xmm0, xmm0
0x180004dd8  movups  xmmword ptr [rsp+318h+DeviceInterfaceData.cbSize], xmm0
0x180004de0  movups  xmmword ptr [rsp+318h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x180004de8  mov     [rsp+318h+DeviceInterfaceData.cbSize], 20h ; ' '
0x180004df3  lea     rcx, [rsp+318h+DeviceInterfaceData]
0x180004dfb  mov     qword ptr [rsp+318h+dwCreationDisposition], rcx; DeviceInterfaceData
0x180004e00  mov     r9d, r13d; MemberIndex
0x180004e03  lea     r8, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x180004e0a  xor     edx, edx; DeviceInfoData
0x180004e0c  mov     rcx, rax; DeviceInfoSet
0x180004e0f  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x180004e15  test    eax, eax
0x180004e17  jnz     short loc_180004E56
0x180004e19  call    cs:__imp_GetLastError
0x180004e1f  test    eax, eax
0x180004e21  jle     short loc_180004E2B
0x180004e23  movzx   eax, ax
0x180004e26  or      eax, 80070000h
0x180004e2b  mov     [rsp+318h+var_2D8], eax
0x180004e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e36  cmp     rcx, rsi
0x180004e39  jz      loc_180005153
0x180004e3f  test    byte ptr [rcx+1Ch], 2
0x180004e43  jz      loc_180005153
0x180004e49  mov     edx, 29h ; ')'
0x180004e4e  mov     r9d, eax
0x180004e51  jmp     loc_180005143
0x180004e56  mov     qword ptr [rsp+318h+dwFlagsAndAttributes], 0; DeviceInfoData
0x180004e5f  lea     rax, [rsp+318h+RequiredSize]
0x180004e64  mov     qword ptr [rsp+318h+dwCreationDisposition], rax; RequiredSize
0x180004e69  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x180004e6c  xor     r8d, r8d; DeviceInterfaceDetailData
0x180004e6f  lea     rdx, [rsp+318h+DeviceInterfaceData]; DeviceInterfaceData
0x180004e77  mov     r14, [rsp+318h+DeviceInfoSet]
0x180004e7c  mov     rcx, r14; DeviceInfoSet
0x180004e7f  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180004e85  mov     ebx, eax
0x180004e87  call    cs:__imp_GetLastError
0x180004e8d  test    ebx, ebx
0x180004e8f  jnz     loc_180005121
0x180004e95  cmp     eax, 7Ah ; 'z'
0x180004e98  jnz     loc_180005121
0x180004e9e  mov     ecx, [rsp+318h+RequiredSize]; Size
0x180004ea2  call    cs:__imp_malloc
0x180004ea8  mov     rbx, rax
0x180004eab  mov     [rsp+318h+Block], rax
0x180004eb3  test    rax, rax
0x180004eb6  jnz     short loc_180004EF9
0x180004eb8  mov     [rsp+318h+var_2D8], 8007000Eh
0x180004ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ec7  cmp     rcx, rsi
0x180004eca  jz      loc_180005155
0x180004ed0  test    byte ptr [rcx+1Ch], 2
0x180004ed4  jz      loc_180005155
0x180004eda  lea     edx, [rax+2Bh]
0x180004edd  lea     r9, aPdidetaildata; "pDiDetailData"
0x180004ee4  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004eeb  mov     rcx, [rcx+10h]
0x180004eef  call    WPP_SF_s
0x180004ef4  jmp     loc_180005155
0x180004ef9  mov     dword ptr [rax], 8
0x180004eff  mov     qword ptr [rsp+318h+dwFlagsAndAttributes], 0; DeviceInfoData
0x180004f08  mov     qword ptr [rsp+318h+dwCreationDisposition], 0; RequiredSize
0x180004f11  mov     r9d, [rsp+318h+RequiredSize]; DeviceInterfaceDetailDataSize
0x180004f16  mov     r8, rbx; DeviceInterfaceDetailData
0x180004f19  lea     rdx, [rsp+318h+DeviceInterfaceData]; DeviceInterfaceData
0x180004f21  mov     rcx, r14; DeviceInfoSet
0x180004f24  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180004f2a  test    eax, eax
0x180004f2c  jnz     short loc_180004F7B
0x180004f2e  call    cs:__imp_GetLastError
0x180004f34  test    eax, eax
0x180004f36  jle     short loc_180004F40
0x180004f38  movzx   eax, ax
0x180004f3b  or      eax, 80070000h
0x180004f40  mov     [rsp+318h+var_2D8], eax
0x180004f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f4b  cmp     rcx, rsi
0x180004f4e  jz      loc_180005155
0x180004f54  test    byte ptr [rcx+1Ch], 2
0x180004f58  jz      loc_180005155
0x180004f5e  mov     edx, 2Ch ; ','
0x180004f63  mov     r9d, eax
0x180004f66  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004f6d  mov     rcx, [rcx+10h]
0x180004f71  call    WPP_SF_d
0x180004f76  jmp     loc_180005155
0x180004f7b  lea     r12, [rbx+4]
0x180004f7f  mov     [rsp+318h+hTemplateFile], 0; hTemplateFile
0x180004f88  mov     [rsp+318h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180004f90  mov     [rsp+318h+dwCreationDisposition], 3; dwCreationDisposition
0x180004f98  xor     r9d, r9d; lpSecurityAttributes
0x180004f9b  xor     edx, edx; dwDesiredAccess
0x180004f9d  lea     r8d, [r9+1]; dwShareMode
0x180004fa1  mov     rcx, r12; lpFileName
0x180004fa4  call    cs:__imp_CreateFileW
0x180004faa  mov     r14, rax
0x180004fad  cmp     rax, r15
0x180004fb0  jnz     short loc_180004FFF
0x180004fb2  call    cs:__imp_GetLastError
0x180004fb8  test    eax, eax
0x180004fba  jle     short loc_180004FC4
0x180004fbc  movzx   eax, ax
0x180004fbf  or      eax, 80070000h
0x180004fc4  mov     [rsp+318h+var_2D8], eax
0x180004fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fcf  cmp     rcx, rsi
0x180004fd2  jz      loc_180005158
0x180004fd8  test    byte ptr [rcx+1Ch], 2
  ... truncated ...
```
