# SxQueryVolume(ushort const *,DF_DEVICE_TYPE *)

- ea: `0x1801ae820`
- end: `0x1801aeccd`
- name: `?SxQueryVolume@@YAJPEBGPEAW4DF_DEVICE_TYPE@@@Z`
- size: `1197`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum DF_DEVICE_TYPE *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180132234`

## callees

- `0x180006350`
- `0x180006dd4`
- `0x1801adb3c`
- `0x1801ae638`
- `0x1801ae820`
- `0x1801aee80`
- `0x1801af550`
- `0x1801afa54`
- `0x1801aff14`
- `0x1801b06bc`
- `0x1801b0b88`
- `0x1801b0c38`
- `0x1801b0e90`
- `0x1801b0ec0`
- `0x1801b0fc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801aebd7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801aebf2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801aebd7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801aebf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801aec8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801aec8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801ae9b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801ae9b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ae966`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801ae966`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aec55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aec64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aec55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801aec64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae9d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ae9d8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801aea9a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801aea9a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801aea5c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801aea5c`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801aebbc`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1801aebbc`

## pseudocode

```c
__int64 __fastcall SxQueryVolume(const unsigned __int16 *a1, enum DF_DEVICE_TYPE *a2)
{
  struct _VOLUME_DISK_EXTENTS *v4; // rdi
  __int64 FileW; // rbx
  __int16 v6; // ax
  _DWORD *v7; // r14
  __int64 v8; // rcx
  enum DF_DEVICE_TYPE *v9; // rax
  int v10; // r9d
  int v11; // eax
  _DWORD *v12; // rax
  unsigned __int16 v13; // dx
  int DiskExts; // eax
  bool v15; // sf
  DWORD DiskNumber; // ecx
  DWORD v17; // esi
  unsigned int v18; // ecx
  unsigned int v19; // edi
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v23; // [rsp+48h] [rbp-B8h] BYREF
  int DeviceType; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v25; // [rsp+54h] [rbp-ACh]
  __int16 v26; // [rsp+56h] [rbp-AAh]
  DWORD BytesReturned; // [rsp+88h] [rbp-78h] BYREF
  struct _VOLUME_DISK_EXTENTS *v28; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR FileSystemNameBuffer; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[206]; // [rsp+B2h] [rbp-4Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&DeviceType, "SxQueryVolume", 0x770u, 1u);
  v22 = 1;
  v28 = 0;
  v21 = 0;
  FileSystemNameBuffer = 0;
  v4 = 0;
  memset_0(v32, 0, 0xC6u);
  BytesReturned = 0;
  FileW = -1;
  lpFileName[0] = (LPCWSTR)qword_1802E5D80;
  lpFileName[1] = 0;
  v6 = 1921;
  hKey = 0;
  v7 = 0;
  v23 = 0;
  if ( !a1 )
    goto LABEL_50;
  DeviceType = 0;
  v25 = 1921;
  if ( !a2 )
  {
    v6 = 1924;
LABEL_50:
    DeviceType = -2147024809;
    goto LABEL_51;
  }
  v8 = 4;
  v9 = a2;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (enum DF_DEVICE_TYPE *)((char *)v9 + 1);
    --v8;
  }
  while ( v8 );
  DeviceType = 0;
  v25 = 1924;
  if ( (unsigned int)SxIsRemovableFatVolume(a1) )
  {
    v21 = 2;
  }
  else
  {
    DiskExts = SxGetDiskExts(a1, &v28);
    v4 = v28;
    v15 = DiskExts < 0;
    DeviceType = DiskExts;
    v6 = 1947;
    if ( v15 )
      goto LABEL_51;
    v25 = 1947;
    DiskNumber = v28->Extents[0].DiskNumber;
    if ( DiskNumber == -1 )
    {
      DeviceType = -1996488691;
      v6 = 1952;
      goto LABEL_51;
    }
    DeviceType = SxQueryDeviceType(DiskNumber, (enum DF_DEVICE_TYPE *)&v21);
    v6 = 1955;
    if ( DeviceType < 0 )
      goto LABEL_51;
    v25 = 1955;
    if ( v4->NumberOfDiskExtents > 1 )
    {
      v17 = 0;
      do
      {
        v18 = v4->Extents[v17].DiskNumber;
        if ( v18 == -1 )
        {
          DeviceType = -1996488691;
          v6 = 1969;
          goto LABEL_51;
        }
        if ( (int)SxQueryDeviceDefragAppropriate(v18, &v22) < 0 )
          break;
        if ( v22 )
          break;
        ++v17;
      }
      while ( v17 < v4->NumberOfDiskExtents );
      if ( v17 == v4->NumberOfDiskExtents )
        v21 = 3;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MatchingSlabandCluster>::GetImpl'::`2'::impl)
    && v21 - 9 <= 1 )
  {
    SxQueryDeviceForThinProvisionedDisk(v4->Extents[0].DiskNumber, v21, &v21);
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Dfrg", 0, 0x20019u, &hKey) )
  {
    if ( !(unsigned int)SxRegReadDWORD(hKey, L"MatchingSlabOptimization", &v23, v10) && v23 == 1 && v21 - 9 <= 1 )
      SxQueryDeviceForThinProvisionedDisk(v4->Extents[0].DiskNumber, v21, &v21);
    RegCloseKey(hKey);
  }
  v11 = v21;
  if ( v21 != 6 && v21 != 12 )
    goto LABEL_38;
  v12 = CoTaskMemAlloc(0x4000u);
  v7 = v12;
  if ( !v12 )
  {
    DeviceType = -2147024882;
    v26 = 2016;
    goto LABEL_52;
  }
  v25 = 2016;
  DeviceType = 0;
  memset_0(v12, 0, 0x4000u);
  DeviceType = CBsString::Set((CBsString *)lpFileName, a1);
  v6 = 2019;
  if ( DeviceType < 0 )
  {
LABEL_51:
    v26 = v6;
    goto LABEL_52;
  }
  v25 = 2019;
  CBsString::UnTrailing((CBsString *)lpFileName, v13);
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
  if ( FileW == -1 || !DeviceIoControl((HANDLE)FileW, 0x902ECu, 0, 0, v7, 0x4000u, &BytesReturned, 0) || v7[3] <= 1u )
  {
    v11 = v21;
  }
  else
  {
    v11 = 11;
    v21 = 11;
  }
LABEL_38:
  if ( v11 == 3 || v11 == 12 )
  {
    if ( !GetVolumeInformationW(a1, 0, 0, 0, 0, 0, &FileSystemNameBuffer, 0x64u)
      || (unsigned int)_o__wcsicmp(&FileSystemNameBuffer, L"NTFS")
      && (unsigned int)_o__wcsicmp(&FileSystemNameBuffer, L"REFS") )
    {
      v11 = v21;
    }
    else
    {
      v11 = 13;
      if ( v21 == 3 )
        v11 = 4;
      v21 = v11;
    }
  }
  *(_DWORD *)a2 = v11;
  v25 = 2081;
  DeviceType = 0;
LABEL_52:
  CoTaskMemFree(v4);
  CoTaskMemFree(v7);
  v19 = DeviceType;
  CBsString::_Release((CBsString *)lpFileName);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&DeviceType);
  return v19;
}

```

## disassembly

```asm
0x1801ae820  mov     [rsp-8+arg_10], rbx
0x1801ae825  push    rbp
0x1801ae826  push    rsi
0x1801ae827  push    rdi
0x1801ae828  push    r12
0x1801ae82a  push    r13
0x1801ae82c  push    r14
0x1801ae82e  push    r15
0x1801ae830  lea     rbp, [rsp-90h]
0x1801ae838  sub     rsp, 190h
0x1801ae83f  mov     rax, cs:__security_cookie
0x1801ae846  xor     rax, rsp
0x1801ae849  mov     [rbp+0C0h+var_40], rax
0x1801ae850  mov     r12, rdx
0x1801ae853  mov     r15, rcx
0x1801ae856  lea     rdx, aSxqueryvolume; "SxQueryVolume"
0x1801ae85d  mov     r9d, 1; unsigned __int16
0x1801ae863  lea     rcx, [rsp+1C0h+var_170]; this
0x1801ae868  mov     r8d, 770h; unsigned __int16
0x1801ae86e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1801ae873  xor     r13d, r13d
0x1801ae876  mov     [rsp+1C0h+var_17C], 1
0x1801ae87e  xor     edx, edx; Val
0x1801ae880  mov     [rbp+0C0h+var_130], r13
0x1801ae884  mov     r8d, 0C6h; Size
0x1801ae88a  mov     [rsp+1C0h+var_180], r13d
0x1801ae88f  lea     rcx, [rbp+0C0h+var_10E]; void *
0x1801ae893  mov     [rbp+0C0h+FileSystemNameBuffer], r13w
0x1801ae898  mov     edi, r13d
0x1801ae89b  call    memset_0
0x1801ae8a0  lea     rax, qword_1802E5D80
0x1801ae8a7  mov     [rbp+0C0h+BytesReturned], r13d
0x1801ae8ab  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801ae8af  mov     [rbp+0C0h+lpFileName], rax
0x1801ae8b3  mov     [rbp+0C0h+var_118], r13
0x1801ae8b7  mov     eax, 781h
0x1801ae8bc  mov     [rbp+0C0h+hKey], r13
0x1801ae8c0  mov     r14d, r13d
0x1801ae8c3  mov     [rsp+1C0h+var_178], r13d
0x1801ae8c8  test    r15, r15
0x1801ae8cb  jz      loc_1801AEC45
0x1801ae8d1  mov     [rsp+1C0h+var_170], r13d
0x1801ae8d6  mov     [rsp+1C0h+var_16C], ax
0x1801ae8db  test    r12, r12
0x1801ae8de  jz      loc_1801AEC40
0x1801ae8e4  lea     ecx, [rbx+5]
0x1801ae8e7  mov     rax, r12
0x1801ae8ea  mov     [rax], r13b
0x1801ae8ed  inc     rax
0x1801ae8f0  sub     rcx, 1
0x1801ae8f4  jnz     short loc_1801AE8EA
0x1801ae8f6  mov     eax, 784h
0x1801ae8fb  mov     [rsp+1C0h+var_170], r13d
0x1801ae900  mov     rcx, r15; lpRootPathName
0x1801ae903  mov     [rsp+1C0h+var_16C], ax
0x1801ae908  call    ?SxIsRemovableFatVolume@@YAHPEBG@Z; SxIsRemovableFatVolume(ushort const *)
0x1801ae90d  test    eax, eax
0x1801ae90f  jz      loc_1801AEAC7
0x1801ae915  mov     [rsp+1C0h+var_180], 2
0x1801ae91d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster> `wil::Feature<__WilFeatureTraits_Feature_MatchingSlabandCluster>::GetImpl(void)'::`2'::impl
0x1801ae924  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster>::__private_IsEnabled(void)
0x1801ae929  test    al, al
0x1801ae92b  jz      short loc_1801AE946
0x1801ae92d  mov     edx, [rsp+1C0h+var_180]
0x1801ae931  lea     eax, [rdx-9]
0x1801ae934  cmp     eax, 1
0x1801ae937  ja      short loc_1801AE946
0x1801ae939  mov     ecx, [rdi+8]
0x1801ae93c  lea     r8, [rsp+1C0h+var_180]
0x1801ae941  call    ?SxQueryDeviceForThinProvisionedDisk@@YAJKW4DF_DEVICE_TYPE@@PEAW41@@Z; SxQueryDeviceForThinProvisionedDisk(ulong,DF_DEVICE_TYPE,DF_DEVICE_TYPE *)
0x1801ae946  lea     rax, [rbp+0C0h+hKey]
0x1801ae94a  mov     r9d, 20019h; samDesired
0x1801ae950  xor     r8d, r8d; ulOptions
0x1801ae953  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1801ae958  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Dfrg"
0x1801ae95f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801ae966  call    cs:__imp_RegOpenKeyExW
0x1801ae96d  nop     dword ptr [rax+rax+00h]
0x1801ae972  test    eax, eax
0x1801ae974  jnz     short loc_1801AE9BF
0x1801ae976  mov     rcx, [rbp+0C0h+hKey]; hKey
0x1801ae97a  lea     r8, [rsp+1C0h+var_178]; unsigned int *
0x1801ae97f  lea     rdx, aMatchingslabop; "MatchingSlabOptimization"
0x1801ae986  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1801ae98b  test    eax, eax
0x1801ae98d  jnz     short loc_1801AE9AF
0x1801ae98f  cmp     [rsp+1C0h+var_178], 1
0x1801ae994  jnz     short loc_1801AE9AF
0x1801ae996  mov     edx, [rsp+1C0h+var_180]
0x1801ae99a  lea     eax, [rdx-9]
0x1801ae99d  cmp     eax, 1
0x1801ae9a0  ja      short loc_1801AE9AF
0x1801ae9a2  mov     ecx, [rdi+8]
0x1801ae9a5  lea     r8, [rsp+1C0h+var_180]
0x1801ae9aa  call    ?SxQueryDeviceForThinProvisionedDisk@@YAJKW4DF_DEVICE_TYPE@@PEAW41@@Z; SxQueryDeviceForThinProvisionedDisk(ulong,DF_DEVICE_TYPE,DF_DEVICE_TYPE *)
0x1801ae9af  mov     rcx, [rbp+0C0h+hKey]; hKey
0x1801ae9b3  call    cs:__imp_RegCloseKey
0x1801ae9ba  nop     dword ptr [rax+rax+00h]
0x1801ae9bf  mov     eax, [rsp+1C0h+var_180]
0x1801ae9c3  cmp     eax, 6
0x1801ae9c6  jz      short loc_1801AE9D1
0x1801ae9c8  cmp     eax, 0Ch
0x1801ae9cb  jnz     loc_1801AEB88
0x1801ae9d1  mov     esi, 4000h
0x1801ae9d6  mov     ecx, esi; cb
0x1801ae9d8  call    cs:__imp_CoTaskMemAlloc
0x1801ae9df  nop     dword ptr [rax+rax+00h]
0x1801ae9e4  mov     r14, rax
0x1801ae9e7  mov     ecx, 7E0h
0x1801ae9ec  test    rax, rax
0x1801ae9ef  jz      loc_1801AEC31
0x1801ae9f5  mov     [rsp+1C0h+var_16C], cx
0x1801ae9fa  mov     r8d, esi; Size
0x1801ae9fd  mov     rcx, rax; void *
0x1801aea00  mov     [rsp+1C0h+var_170], r13d
0x1801aea05  xor     edx, edx; Val
0x1801aea07  call    memset_0
0x1801aea0c  mov     rdx, r15; unsigned __int16 *
0x1801aea0f  lea     rcx, [rbp+0C0h+lpFileName]; this
0x1801aea13  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1801aea18  mov     [rsp+1C0h+var_170], eax
0x1801aea1c  test    eax, eax
0x1801aea1e  mov     eax, 7E3h
0x1801aea23  js      loc_1801AEC4D
0x1801aea29  lea     rcx, [rbp+0C0h+lpFileName]; this
0x1801aea2d  mov     [rsp+1C0h+var_16C], ax
0x1801aea32  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1801aea37  mov     rcx, [rbp+0C0h+lpFileName]; lpFileName
0x1801aea3b  mov     eax, 3
0x1801aea40  mov     [rsp+1C0h+hTemplateFile], r13; hTemplateFile
0x1801aea45  mov     r8d, eax; dwShareMode
0x1801aea48  mov     [rsp+1C0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x1801aea50  xor     r9d, r9d; lpSecurityAttributes
0x1801aea53  mov     edx, 0C0000000h; dwDesiredAccess
0x1801aea58  mov     dword ptr [rsp+1C0h+phkResult], eax; dwCreationDisposition
0x1801aea5c  call    cs:__imp_CreateFileW
0x1801aea63  nop     dword ptr [rax+rax+00h]
0x1801aea68  mov     rbx, rax
0x1801aea6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801aea6f  jz      loc_1801AEB84
0x1801aea75  mov     [rsp+1C0h+lpOverlapped], r13; lpOverlapped
0x1801aea7a  lea     rax, [rbp+0C0h+BytesReturned]
0x1801aea7e  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x1801aea83  xor     r9d, r9d; nInBufferSize
0x1801aea86  mov     [rsp+1C0h+dwFlagsAndAttributes], esi; nOutBufferSize
0x1801aea8a  xor     r8d, r8d; lpInBuffer
0x1801aea8d  mov     edx, 902ECh; dwIoControlCode
0x1801aea92  mov     [rsp+1C0h+phkResult], r14; lpOutBuffer
0x1801aea97  mov     rcx, rbx; hDevice
0x1801aea9a  call    cs:__imp_DeviceIoControl
0x1801aeaa1  nop     dword ptr [rax+rax+00h]
0x1801aeaa6  test    eax, eax
0x1801aeaa8  jz      loc_1801AEB84
0x1801aeaae  cmp     dword ptr [r14+0Ch], 1
0x1801aeab3  jbe     loc_1801AEB84
0x1801aeab9  mov     eax, 0Bh
0x1801aeabe  mov     [rsp+1C0h+var_180], eax
0x1801aeac2  jmp     loc_1801AEB88
0x1801aeac7  lea     rdx, [rbp+0C0h+var_130]; struct _VOLUME_DISK_EXTENTS **
0x1801aeacb  mov     rcx, r15; unsigned __int16 *
0x1801aeace  call    ?SxGetDiskExts@@YAJPEBGPEAPEAU_VOLUME_DISK_EXTENTS@@@Z; SxGetDiskExts(ushort const *,_VOLUME_DISK_EXTENTS * *)
0x1801aead3  mov     rdi, [rbp+0C0h+var_130]
0x1801aead7  test    eax, eax
0x1801aead9  mov     [rsp+1C0h+var_170], eax
0x1801aeadd  mov     eax, 79Bh
0x1801aeae2  js      loc_1801AEC4D
0x1801aeae8  mov     [rsp+1C0h+var_16C], ax
0x1801aeaed  mov     ecx, [rdi+8]; unsigned int
0x1801aeaf0  cmp     ecx, 0FFFFFFFFh
0x1801aeaf3  jnz     short loc_1801AEB07
0x1801aeaf5  mov     [rsp+1C0h+var_170], 8900000Dh
0x1801aeafd  mov     eax, 7A0h
0x1801aeb02  jmp     loc_1801AEC4D
0x1801aeb07  lea     rdx, [rsp+1C0h+var_180]; enum DF_DEVICE_TYPE *
0x1801aeb0c  call    ?SxQueryDeviceType@@YAJKPEAW4DF_DEVICE_TYPE@@@Z; SxQueryDeviceType(ulong,DF_DEVICE_TYPE *)
0x1801aeb11  mov     [rsp+1C0h+var_170], eax
0x1801aeb15  test    eax, eax
0x1801aeb17  mov     eax, 7A3h
0x1801aeb1c  js      loc_1801AEC4D
0x1801aeb22  mov     [rsp+1C0h+var_16C], ax
0x1801aeb27  cmp     dword ptr [rdi], 1
0x1801aeb2a  jbe     loc_1801AE91D
0x1801aeb30  mov     esi, r13d
0x1801aeb33  mov     eax, esi
0x1801aeb35  lea     rcx, [rax+rax*2]
0x1801aeb39  mov     ecx, [rdi+rcx*8+8]; unsigned int
0x1801aeb3d  cmp     ecx, 0FFFFFFFFh
0x1801aeb40  jz      short loc_1801AEB72
0x1801aeb42  lea     rdx, [rsp+1C0h+var_17C]; int *
0x1801aeb47  call    ?SxQueryDeviceDefragAppropriate@@YAJKPEAH@Z; SxQueryDeviceDefragAppropriate(ulong,int *)
0x1801aeb4c  test    eax, eax
0x1801aeb4e  js      short loc_1801AEB5D
0x1801aeb50  cmp     [rsp+1C0h+var_17C], r13d
0x1801aeb55  jnz     short loc_1801AEB5D
0x1801aeb57  inc     esi
0x1801aeb59  cmp     esi, [rdi]
0x1801aeb5b  jb      short loc_1801AEB33
0x1801aeb5d  cmp     esi, [rdi]
0x1801aeb5f  jnz     loc_1801AE91D
0x1801aeb65  mov     [rsp+1C0h+var_180], 3
0x1801aeb6d  jmp     loc_1801AE91D
0x1801aeb72  mov     [rsp+1C0h+var_170], 8900000Dh
0x1801aeb7a  mov     eax, 7B1h
0x1801aeb7f  jmp     loc_1801AEC4D
0x1801aeb84  mov     eax, [rsp+1C0h+var_180]
0x1801aeb88  cmp     eax, 3
0x1801aeb8b  jz      short loc_1801AEB96
0x1801aeb8d  cmp     eax, 0Ch
0x1801aeb90  jnz     loc_1801AEC1C
0x1801aeb96  mov     dword ptr [rsp+1C0h+lpOverlapped], 64h ; 'd'; nFileSystemNameSize
0x1801aeb9e  lea     rax, [rbp+0C0h+FileSystemNameBuffer]
0x1801aeba2  mov     [rsp+1C0h+hTemplateFile], rax; lpFileSystemNameBuffer
0x1801aeba7  xor     r9d, r9d; lpVolumeSerialNumber
0x1801aebaa  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], r13; lpFileSystemFlags
0x1801aebaf  xor     r8d, r8d; nVolumeNameSize
0x1801aebb2  xor     edx, edx; lpVolumeNameBuffer
0x1801aebb4  mov     [rsp+1C0h+phkResult], r13; lpMaximumComponentLength
0x1801aebb9  mov     rcx, r15; lpRootPathName
0x1801aebbc  call    cs:__imp_GetVolumeInformationW
0x1801aebc3  nop     dword ptr [rax+rax+00h]
0x1801aebc8  test    eax, eax
0x1801aebca  jz      short loc_1801AEC18
0x1801aebcc  lea     rdx, aNtfs_0; "NTFS"
0x1801aebd3  lea     rcx, [rbp+0C0h+FileSystemNameBuffer]
0x1801aebd7  call    cs:__imp__o__wcsicmp
0x1801aebde  nop     dword ptr [rax+rax+00h]
0x1801aebe3  test    eax, eax
0x1801aebe5  jz      short loc_1801AEC02
0x1801aebe7  lea     rdx, aRefs; "REFS"
0x1801aebee  lea     rcx, [rbp+0C0h+FileSystemNameBuffer]
0x1801aebf2  call    cs:__imp__o__wcsicmp
0x1801aebf9  nop     dword ptr [rax+rax+00h]
0x1801aebfe  test    eax, eax
0x1801aec00  jnz     short loc_1801AEC18
0x1801aec02  cmp     [rsp+1C0h+var_180], 3
0x1801aec07  mov     eax, 0Dh
0x1801aec0c  lea     ecx, [rax-9]
0x1801aec0f  cmovz   eax, ecx
0x1801aec12  mov     [rsp+1C0h+var_180], eax
0x1801aec16  jmp     short loc_1801AEC1C
0x1801aec18  mov     eax, [rsp+1C0h+var_180]
0x1801aec1c  mov     [r12], eax
0x1801aec20  mov     eax, 821h
0x1801aec25  mov     [rsp+1C0h+var_16C], ax
0x1801aec2a  mov     [rsp+1C0h+var_170], r13d
0x1801aec2f  jmp     short loc_1801AEC52
0x1801aec31  mov     [rsp+1C0h+var_170], 8007000Eh
0x1801aec39  mov     [rsp+1C0h+var_16A], cx
0x1801aec3e  jmp     short loc_1801AEC52
0x1801aec40  mov     eax, 784h
0x1801aec45  mov     [rsp+1C0h+var_170], 80070057h
0x1801aec4d  mov     [rsp+1C0h+var_16A], ax
0x1801aec52  mov     rcx, rdi; pv
0x1801aec55  call    cs:__imp_CoTaskMemFree
0x1801aec5c  nop     dword ptr [rax+rax+00h]
0x1801aec61  mov     rcx, r14; pv
0x1801aec64  call    cs:__imp_CoTaskMemFree
0x1801aec6b  nop     dword ptr [rax+rax+00h]
0x1801aec70  mov     edi, [rsp+1C0h+var_170]
0x1801aec74  lea     rcx, [rbp+0C0h+lpFileName]; this
0x1801aec78  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1801aec7d  lea     rcx, [rbx-1]
0x1801aec81  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801aec85  ja      short loc_1801AEC96
0x1801aec87  mov     rcx, rbx; hObject
0x1801aec8a  call    cs:__imp_CloseHandle
0x1801aec91  nop     dword ptr [rax+rax+00h]
0x1801aec96  lea     rcx, [rsp+1C0h+var_170]; this
0x1801aec9b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1801aeca0  mov     eax, edi
0x1801aeca2  mov     rcx, [rbp+0C0h+var_40]
0x1801aeca9  xor     rcx, rsp; StackCookie
0x1801aecac  call    __security_check_cookie
0x1801aecb1  mov     rbx, [rsp+1C0h+arg_10]
0x1801aecb9  add     rsp, 190h
0x1801aecc0  pop     r15
0x1801aecc2  pop     r14
0x1801aecc4  pop     r13
0x1801aecc6  pop     r12
0x1801aecc8  pop     rdi
0x1801aecc9  pop     rsi
0x1801aecca  pop     rbp
0x1801aeccb  retn
```
