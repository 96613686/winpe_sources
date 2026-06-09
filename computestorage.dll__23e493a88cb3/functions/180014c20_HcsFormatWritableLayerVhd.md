# HcsFormatWritableLayerVhd

- ea: `0x180014c20`
- end: `0x180014e78`
- name: `HcsFormatWritableLayerVhd`
- size: `600`
- prototype: `HRESULT __stdcall(HANDLE vhdHandle)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x1800084c0`
- `0x180008ce8`
- `0x180008fac`
- `0x18000a964`
- `0x18000f118`
- `0x18000ffd4`
- `0x180012818`
- `0x180014c20`
- `0x18001c5d4`
- `0x180028640`
- `0x180028830`
- `0x180028a04`
- `0x180029b08`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014dca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014dca`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180014d2f`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180014d2f`
- `VirtDisk!GetVirtualDiskInformation` at `0x180014cbe`
- `VirtDisk!GetVirtualDiskInformation` at `0x180014cbe`
- `VirtDisk!DetachVirtualDisk` at `0x180014de8`
- `VirtDisk!DetachVirtualDisk` at `0x180014de8`

## string_xrefs

- `0x180014c55`: `ComputeStorage_FormatDisk`
- `0x180014e50`: `onecore\vm\compute\dll\storage\src\layer.cpp`
- `0x180014e65`: `onecore\vm\compute\dll\storage\src\layer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __stdcall HcsFormatWritableLayerVhd(HANDLE vhdHandle)
{
  DWORD VirtualDiskInformation; // eax
  DWORD VirtualDiskPhysicalPath; // eax
  __int64 v3; // r8
  const unsigned __int16 *v4; // rdx
  const WCHAR *v5; // rcx
  DWORD v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  HRESULT result; // eax
  unsigned int v11[4]; // [rsp+20h] [rbp-408h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+30h] [rbp-3F8h] BYREF
  char v13; // [rsp+38h] [rbp-3F0h] BYREF
  ULONG DiskPathSizeInBytes; // [rsp+3Ch] [rbp-3ECh] BYREF
  ULONG SizeUsed; // [rsp+40h] [rbp-3E8h] BYREF
  ULONG VirtualDiskInfoSize; // [rsp+44h] [rbp-3E4h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-3E0h] BYREF
  _GET_VIRTUAL_DISK_INFO VirtualDiskInfo; // [rsp+50h] [rbp-3D8h] BYREF
  PCWSTR pszPathIn[8]; // [rsp+70h] [rbp-3B8h] BYREF
  _QWORD v20[42]; // [rsp+B0h] [rbp-378h] BYREF
  WCHAR DiskPath[264]; // [rsp+200h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+428h] [rbp+0h]

  VirtualDiskHandle = vhdHandle;
  memset_0(v20, 0, sizeof(v20));
  wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v20,
    (__int64)"ComputeStorage_FormatDisk");
  v20[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk::`vftable';
  ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk::StartActivity((ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk *)v20);
  *(_QWORD *)&VirtualDiskInfo.Version = 13;
  memset(&VirtualDiskInfo.Size, 0, sizeof(VirtualDiskInfo.Size));
  SizeUsed = 0;
  VirtualDiskInfoSize = 32;
  VirtualDiskInformation = GetVirtualDiskInformation(
                             VirtualDiskHandle,
                             &VirtualDiskInfoSize,
                             &VirtualDiskInfo,
                             &SizeUsed);
  try
  {
    if ( VirtualDiskInformation )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1AC,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        (const char *)VirtualDiskInformation,
        v11[0]);
    if ( VirtualDiskInfo.Identifier.Data1 )
    {
      v13 = 1;
    }
    else
    {
      v13 = 0;
      MountVhd(
        VirtualDiskHandle,
        ATTACH_VIRTUAL_DISK_FLAG_BYPASS_DEFAULT_ENCRYPTION_POLICY|ATTACH_VIRTUAL_DISK_FLAG_NO_DRIVE_LETTER);
    }
    *(_QWORD *)&VirtualDiskInfo.Version = &VirtualDiskHandle;
    VirtualDiskInfo.Size.VirtualSize = (ULONGLONG)&v13;
    VirtualDiskInfo.Identifier.Data4[0] = 1;
    DiskPathSizeInBytes = 520;
    VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, DiskPath);
    if ( VirtualDiskPhysicalPath )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
        (const char *)VirtualDiskPhysicalPath,
        v11[0]);
    hObject = 0;
    OpenDisk(&hObject, DiskPath);
    *(GUID *)v11 = GUID_00000000_0000_0000_0000_000000000000;
    FormatDisk(pszPathIn, hObject, v3, (UUID *)v11);
    v5 = (const WCHAR *)pszPathIn;
    if ( pszPathIn[3] > (PCWSTR)7 )
      v5 = pszPathIn[0];
    OsImageUtilities::Helpers::CreateSandboxStateDirectory(v5, v4);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20);
    std::wstring::~wstring((char **)pszPathIn);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( !v13 )
    {
      v6 = DetachVirtualDisk(VirtualDiskHandle, DETACH_VIRTUAL_DISK_FLAG_NONE, 0);
      if ( v6 )
        wil::details::in1diag3::_Log_Win32(retaddr, v7, v8, (const char *)v6, v11[0]);
    }
    v20[0] = &ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk::`vftable';
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
    wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v20);
    result = 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x1CA,
             (unsigned int)"onecore\\vm\\compute\\dll\\storage\\src\\layer.cpp",
             v9);
  }
  return result;
}

```

## disassembly

```asm
0x180014c20  push    rdi
0x180014c22  sub     rsp, 420h
0x180014c29  mov     rax, cs:__security_cookie
0x180014c30  xor     rax, rsp
0x180014c33  mov     [rsp+428h+var_18], rax
0x180014c3b  mov     [rsp+428h+VirtualDiskHandle], rcx
0x180014c40  xor     edx, edx; Val
0x180014c42  mov     r8d, 150h; Size
0x180014c48  lea     rcx, [rsp+428h+var_378]; void *
0x180014c50  call    memset_0
0x180014c55  lea     rdx, aComputestorage_6; "ComputeStorage_FormatDisk"
0x180014c5c  lea     rcx, [rsp+428h+var_378]
0x180014c64  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014c69  lea     rdi, ??_7ComputeStorage_FormatDisk@TraceProvider@Diagnostics@ComputeStorage@@6B@; const ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk::`vftable'
0x180014c70  mov     [rsp+428h+var_378], rdi
0x180014c78  lea     rcx, [rsp+428h+var_378]; this
0x180014c80  call    ?StartActivity@ComputeStorage_FormatDisk@TraceProvider@Diagnostics@ComputeStorage@@QEAAXXZ; ComputeStorage::Diagnostics::TraceProvider::ComputeStorage_FormatDisk::StartActivity(void)
0x180014c85  nop
0x180014c86  mov     qword ptr [rsp+428h+VirtualDiskInfo.Version], 0Dh
0x180014c8f  xorps   xmm0, xmm0
0x180014c92  xor     eax, eax
0x180014c94  movups  xmmword ptr [rsp+428h+VirtualDiskInfo.8], xmm0
0x180014c99  mov     qword ptr [rsp+428h+VirtualDiskInfo.8+10h], rax
0x180014c9e  mov     [rsp+428h+SizeUsed], eax
0x180014ca2  mov     [rsp+428h+VirtualDiskInfoSize], 20h ; ' '
0x180014caa  lea     r9, [rsp+428h+SizeUsed]; SizeUsed
0x180014caf  lea     r8, [rsp+428h+VirtualDiskInfo]; VirtualDiskInfo
0x180014cb4  lea     rdx, [rsp+428h+VirtualDiskInfoSize]; VirtualDiskInfoSize
0x180014cb9  mov     rcx, [rsp+428h+VirtualDiskHandle]; VirtualDiskHandle
0x180014cbe  call    cs:__imp_GetVirtualDiskInformation
0x180014cc5  nop     dword ptr [rax+rax+00h]
0x180014cca  mov     rcx, [rsp+428h]; this
0x180014cd2  test    eax, eax
0x180014cd4  jnz     loc_180014E4D
0x180014cda  cmp     dword ptr [rsp+428h+VirtualDiskInfo.8], 0
0x180014cdf  jz      short loc_180014CE8
0x180014ce1  mov     [rsp+428h+var_3F0], 1
0x180014ce6  jmp     short loc_180014CFC
0x180014ce8  mov     [rsp+428h+var_3F0], 0
0x180014ced  mov     edx, 22h ; '"'; enum _ATTACH_VIRTUAL_DISK_FLAG
0x180014cf2  mov     rcx, [rsp+428h+VirtualDiskHandle]; void *
0x180014cf7  call    ?MountVhd@@YAXPEAXW4_ATTACH_VIRTUAL_DISK_FLAG@@G@Z; MountVhd(void *,_ATTACH_VIRTUAL_DISK_FLAG,ushort)
0x180014cfc  lea     rax, [rsp+428h+VirtualDiskHandle]
0x180014d01  mov     qword ptr [rsp+428h+VirtualDiskInfo.Version], rax
0x180014d06  lea     rax, [rsp+428h+var_3F0]
0x180014d0b  mov     qword ptr [rsp+428h+VirtualDiskInfo.8], rax
0x180014d10  mov     byte ptr [rsp+428h+VirtualDiskInfo.8+8], 1
0x180014d15  mov     [rsp+428h+DiskPathSizeInBytes], 208h
0x180014d1d  lea     r8, [rsp+428h+DiskPath]; DiskPath
0x180014d25  lea     rdx, [rsp+428h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x180014d2a  mov     rcx, [rsp+428h+VirtualDiskHandle]; VirtualDiskHandle
0x180014d2f  call    cs:__imp_GetVirtualDiskPhysicalPath
0x180014d36  nop     dword ptr [rax+rax+00h]
0x180014d3b  mov     rcx, [rsp+428h]; this
0x180014d43  test    eax, eax
0x180014d45  jnz     loc_180014E62
0x180014d4b  mov     [rsp+428h+hObject], 0
0x180014d54  lea     rdx, [rsp+428h+DiskPath]
0x180014d5c  lea     rcx, [rsp+428h+hObject]
0x180014d61  call    ?OpenDisk@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGK@Z; OpenDisk(ushort const *,ulong)
0x180014d66  nop
0x180014d67  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180014d6e  movdqu  xmmword ptr [rsp+428h+var_408], xmm0; unsigned int
0x180014d74  lea     r9, [rsp+428h+var_408]
0x180014d79  mov     rdx, [rsp+428h+hObject]
0x180014d7e  lea     rcx, [rsp+428h+pszPathIn]
0x180014d83  call    ?FormatDisk@@YA?AUPartitionInfo@@PEAXPEBGU_GUID@@@Z; FormatDisk(void *,ushort const *,_GUID)
0x180014d88  nop
0x180014d89  lea     rcx, [rsp+428h+pszPathIn]
0x180014d8e  cmp     [rsp+428h+var_3A0], 7
0x180014d97  cmova   rcx, [rsp+428h+pszPathIn]; pszPathIn
0x180014d9d  call    ?CreateSandboxStateDirectory@Helpers@OsImageUtilities@@YAXPEBG@Z; OsImageUtilities::Helpers::CreateSandboxStateDirectory(ushort const *)
0x180014da2  lea     rcx, [rsp+428h+var_378]
0x180014daa  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180014daf  nop
0x180014db0  lea     rcx, [rsp+428h+pszPathIn]
0x180014db5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014dba  nop
0x180014dbb  mov     rcx, [rsp+428h+hObject]; hObject
0x180014dc0  lea     rax, [rcx-1]
0x180014dc4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014dc8  ja      short loc_180014DD7
0x180014dca  call    cs:__imp_CloseHandle
0x180014dd1  nop     dword ptr [rax+rax+00h]
0x180014dd6  nop
0x180014dd7  cmp     [rsp+428h+var_3F0], 0
0x180014ddc  jnz     short loc_180014E09
0x180014dde  xor     r8d, r8d; ProviderSpecificFlags
0x180014de1  xor     edx, edx; Flags
0x180014de3  mov     rcx, [rsp+428h+VirtualDiskHandle]; VirtualDiskHandle
0x180014de8  call    cs:__imp_DetachVirtualDisk
0x180014def  nop     dword ptr [rax+rax+00h]
0x180014df4  mov     rcx, [rsp+428h]; this
0x180014dfc  test    eax, eax
0x180014dfe  jz      short loc_180014E09
0x180014e00  mov     r9d, eax; char *
0x180014e03  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180014e08  nop
0x180014e09  mov     [rsp+428h+var_378], rdi
0x180014e11  lea     rcx, [rsp+428h+var_378]
0x180014e19  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014e1e  lea     rcx, [rsp+428h+var_378]
0x180014e26  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeStorage@@$0A@$0CAAEA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeStorage::Diagnostics::TraceProvider,0,131136,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180014e2b  xor     eax, eax
0x180014e2d  jmp     short loc_180014E33
0x180014e2f  mov     eax, [rsp+428h+DiskPathSizeInBytes]
0x180014e33  mov     rcx, [rsp+428h+var_18]
0x180014e3b  xor     rcx, rsp; StackCookie
0x180014e3e  call    __security_check_cookie
0x180014e43  add     rsp, 420h
0x180014e4a  pop     rdi
0x180014e4b  retn
0x180014e4d  mov     r9d, eax; char *
0x180014e50  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x180014e57  mov     edx, 1ACh; void *
0x180014e5c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180014e62  mov     r9d, eax; char *
0x180014e65  lea     r8, aOnecoreVmCompu_1; "onecore\\vm\\compute\\dll\\storage\\src"...
0x180014e6c  mov     edx, 1C1h; void *
0x180014e71  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
