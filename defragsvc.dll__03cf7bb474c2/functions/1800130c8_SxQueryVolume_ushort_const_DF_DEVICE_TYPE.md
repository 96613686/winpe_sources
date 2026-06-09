# SxQueryVolume(ushort const *,DF_DEVICE_TYPE *)

- ea: `0x1800130c8`
- end: `0x18001351a`
- name: `?SxQueryVolume@@YAJPEBGPEAW4DF_DEVICE_TYPE@@@Z`
- size: `1106`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum DF_DEVICE_TYPE *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180012cc8`
- `0x180013020`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800130c8`
- `0x180013520`
- `0x180017e34`
- `0x18001913c`
- `0x1800193a0`
- `0x1800197a8`
- `0x18001adac`
- `0x180028f0c`
- `0x1800397a8`
- `0x18003e618`
- `0x180052e20`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180013445`
- `msvcrt!_wcsicmp` at `0x18001345a`
- `msvcrt!_wcsicmp` at `0x180013445`
- `msvcrt!_wcsicmp` at `0x18001345a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800133a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800133a8`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180013430`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180013430`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800133e0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800133e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013303`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013303`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800134b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800134bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800134b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800134bf`

## pseudocode

```c
__int64 __fastcall SxQueryVolume(const unsigned __int16 *a1, enum DF_DEVICE_TYPE *a2)
{
  DWORD v4; // esi
  struct _VOLUME_DISK_EXTENTS *v5; // rdi
  __int64 FileW; // rbx
  unsigned __int16 *v7; // r13
  _DWORD *v8; // r14
  __int16 v9; // ax
  __int64 v10; // rcx
  enum DF_DEVICE_TYPE *v11; // rax
  int DiskExts; // eax
  bool v13; // sf
  DWORD DiskNumber; // ecx
  bool v15; // zf
  unsigned int v16; // ecx
  int v17; // eax
  _DWORD *v18; // rax
  unsigned __int16 v19; // dx
  unsigned int v20; // edi
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v24; // [rsp+48h] [rbp-B8h] BYREF
  int DeviceType; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v26; // [rsp+54h] [rbp-ACh]
  __int16 v27; // [rsp+56h] [rbp-AAh]
  DWORD BytesReturned; // [rsp+88h] [rbp-78h] BYREF
  struct _VOLUME_DISK_EXTENTS *v29; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR FileSystemNameBuffer; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v33[206]; // [rsp+B2h] [rbp-4Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&DeviceType, "SxQueryVolume", 1904, 1);
  v4 = 0;
  v23 = 1;
  v29 = 0;
  v22 = 0;
  FileSystemNameBuffer = 0;
  v5 = 0;
  memset_0(v33, 0, 0xC6u);
  FileW = -1;
  BytesReturned = 0;
  lpFileName[1] = 0;
  v7 = (unsigned __int16 *)&qword_18006F470;
  lpFileName[0] = &qword_18006F470;
  v8 = 0;
  hKey = 0;
  v9 = 1921;
  v24 = 0;
  if ( !a1 )
    goto LABEL_52;
  DeviceType = 0;
  v26 = 1921;
  if ( !a2 )
  {
    v9 = 1924;
LABEL_52:
    DeviceType = -2147024809;
    goto LABEL_53;
  }
  v10 = 4;
  v11 = a2;
  do
  {
    *(_BYTE *)v11 = 0;
    v11 = (enum DF_DEVICE_TYPE *)((char *)v11 + 1);
    --v10;
  }
  while ( v10 );
  DeviceType = 0;
  v26 = 1924;
  if ( (unsigned int)SxIsRemovableFatVolume(a1) )
  {
    v22 = 2;
    goto LABEL_21;
  }
  DiskExts = SxGetDiskExts(a1, &v29);
  v5 = v29;
  v13 = DiskExts < 0;
  DeviceType = DiskExts;
  v9 = 1947;
  if ( v13 )
  {
LABEL_53:
    v27 = v9;
    goto LABEL_54;
  }
  v26 = 1947;
  DiskNumber = v29->Extents[0].DiskNumber;
  if ( DiskNumber == -1 )
  {
    DeviceType = -1996488691;
    v9 = 1952;
    goto LABEL_53;
  }
  DeviceType = SxQueryDeviceType(DiskNumber, (enum DF_DEVICE_TYPE *)&v22);
  v9 = 1955;
  if ( DeviceType < 0 )
    goto LABEL_53;
  v26 = 1955;
  if ( v5->NumberOfDiskExtents > 1 )
  {
    while ( 1 )
    {
      v15 = v4 == v5->NumberOfDiskExtents;
      if ( v4 >= v5->NumberOfDiskExtents )
        break;
      v16 = v5->Extents[v4].DiskNumber;
      if ( v16 == -1 )
      {
        DeviceType = -1996488691;
        v9 = 1969;
        goto LABEL_53;
      }
      if ( (int)SxQueryDeviceDefragAppropriate(v16, &v23) < 0 || v23 )
      {
        v15 = v4 == v5->NumberOfDiskExtents;
        break;
      }
      ++v4;
    }
    if ( v15 )
      v22 = 3;
  }
LABEL_21:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MatchingSlabandCluster>::GetImpl'::`2'::impl)
    && v22 - 9 <= 1 )
  {
    SxQueryDeviceForThinProvisionedDisk(v5->Extents[0].DiskNumber, v22, &v22);
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Dfrg", 0, 0x20019u, &hKey) )
  {
    if ( !(unsigned int)SxRegReadDWORD(hKey, L"MatchingSlabOptimization", &v24, 1) && v24 == 1 && v22 - 9 <= 1 )
      SxQueryDeviceForThinProvisionedDisk(v5->Extents[0].DiskNumber, v22, &v22);
    RegCloseKey(hKey);
  }
  v17 = v22;
  if ( v22 == 6 || v22 == 12 )
  {
    v18 = CoTaskMemAlloc(0x4000u);
    v8 = v18;
    if ( !v18 )
    {
      DeviceType = -2147024882;
      v27 = 2016;
      goto LABEL_54;
    }
    v26 = 2016;
    DeviceType = 0;
    memset_0(v18, 0, 0x4000u);
    DeviceType = CBsString::Set((CBsString *)lpFileName, a1);
    v9 = 2019;
    if ( DeviceType < 0 )
    {
      v7 = (unsigned __int16 *)lpFileName[0];
      goto LABEL_53;
    }
    v26 = 2019;
    CBsString::UnTrailing((CBsString *)lpFileName, v19);
    v7 = (unsigned __int16 *)lpFileName[0];
    FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
    if ( FileW == -1 || !DeviceIoControl((HANDLE)FileW, 0x902ECu, 0, 0, v8, 0x4000u, &BytesReturned, 0) || v8[3] <= 1u )
    {
      v17 = v22;
    }
    else
    {
      v17 = 11;
      v22 = 11;
    }
  }
  if ( v17 == 3 || v17 == 12 )
  {
    if ( !GetVolumeInformationW(a1, 0, 0, 0, 0, 0, &FileSystemNameBuffer, 0x64u)
      || _wcsicmp(&FileSystemNameBuffer, L"NTFS") && _wcsicmp(&FileSystemNameBuffer, L"REFS") )
    {
      v17 = v22;
    }
    else
    {
      v17 = 13;
      if ( v22 == 3 )
        v17 = 4;
      v22 = v17;
    }
  }
  *(_DWORD *)a2 = v17;
  v26 = 2081;
  DeviceType = 0;
LABEL_54:
  CoTaskMemFree(v5);
  CoTaskMemFree(v8);
  v20 = DeviceType;
  CBsString::_FreeData(v7);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&DeviceType);
  return v20;
}

```

## disassembly

```asm
0x1800130c8  mov     [rsp-8+arg_10], rbx
0x1800130cd  push    rbp
0x1800130ce  push    rsi
0x1800130cf  push    rdi
0x1800130d0  push    r12
0x1800130d2  push    r13
0x1800130d4  push    r14
0x1800130d6  push    r15
0x1800130d8  lea     rbp, [rsp-90h]
0x1800130e0  sub     rsp, 190h
0x1800130e7  mov     rax, cs:__security_cookie
0x1800130ee  xor     rax, rsp
0x1800130f1  mov     [rbp+0C0h+var_40], rax
0x1800130f8  mov     r12, rdx
0x1800130fb  mov     r15, rcx
0x1800130fe  lea     rdx, aSxqueryvolume; "SxQueryVolume"
0x180013105  mov     r9d, 1; unsigned __int16
0x18001310b  lea     rcx, [rsp+1C0h+var_170]; this
0x180013110  mov     r8d, 770h; unsigned __int16
0x180013116  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001311b  xor     esi, esi
0x18001311d  mov     [rsp+1C0h+var_17C], 1
0x180013125  xor     edx, edx; Val
0x180013127  mov     [rbp+0C0h+var_130], rsi
0x18001312b  mov     r8d, 0C6h; Size
0x180013131  mov     [rsp+1C0h+var_180], esi
0x180013135  lea     rcx, [rbp+0C0h+var_10E]; void *
0x180013139  mov     [rbp+0C0h+FileSystemNameBuffer], si
0x18001313d  mov     edi, esi
0x18001313f  call    memset_0
0x180013144  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013148  mov     [rbp+0C0h+BytesReturned], esi
0x18001314b  mov     [rbp+0C0h+var_118], rsi
0x18001314f  lea     r13, qword_18006F470
0x180013156  mov     [rbp+0C0h+lpFileName], r13
0x18001315a  mov     r14d, esi
0x18001315d  mov     [rbp+0C0h+hKey], rsi
0x180013161  mov     eax, 781h
0x180013166  mov     [rsp+1C0h+var_178], esi
0x18001316a  test    r15, r15
0x18001316d  jz      loc_1800134A6
0x180013173  mov     [rsp+1C0h+var_170], esi
0x180013177  mov     [rsp+1C0h+var_16C], ax
0x18001317c  test    r12, r12
0x18001317f  jz      loc_1800134A1
0x180013185  lea     ecx, [rsi+4]
0x180013188  mov     rax, r12
0x18001318b  mov     [rax], sil
0x18001318e  inc     rax
0x180013191  sub     rcx, 1
0x180013195  jnz     short loc_18001318B
0x180013197  mov     eax, 784h
0x18001319c  mov     [rsp+1C0h+var_170], esi
0x1800131a0  mov     rcx, r15; lpRootPathName
0x1800131a3  mov     [rsp+1C0h+var_16C], ax
0x1800131a8  call    ?SxIsRemovableFatVolume@@YAHPEBG@Z; SxIsRemovableFatVolume(ushort const *)
0x1800131ad  test    eax, eax
0x1800131af  jz      short loc_1800131BE
0x1800131b1  mov     [rsp+1C0h+var_180], 2
0x1800131b9  jmp     loc_18001326F
0x1800131be  lea     rdx, [rbp+0C0h+var_130]; struct _VOLUME_DISK_EXTENTS **
0x1800131c2  mov     rcx, r15; unsigned __int16 *
0x1800131c5  call    ?SxGetDiskExts@@YAJPEBGPEAPEAU_VOLUME_DISK_EXTENTS@@@Z; SxGetDiskExts(ushort const *,_VOLUME_DISK_EXTENTS * *)
0x1800131ca  mov     rdi, [rbp+0C0h+var_130]
0x1800131ce  test    eax, eax
0x1800131d0  mov     [rsp+1C0h+var_170], eax
0x1800131d4  mov     eax, 79Bh
0x1800131d9  js      loc_1800134AE
0x1800131df  mov     [rsp+1C0h+var_16C], ax
0x1800131e4  mov     ecx, [rdi+8]; unsigned int
0x1800131e7  cmp     ecx, 0FFFFFFFFh
0x1800131ea  jnz     short loc_1800131FE
0x1800131ec  mov     [rsp+1C0h+var_170], 8900000Dh
0x1800131f4  mov     eax, 7A0h
0x1800131f9  jmp     loc_1800134AE
0x1800131fe  lea     rdx, [rsp+1C0h+var_180]; enum DF_DEVICE_TYPE *
0x180013203  call    ?SxQueryDeviceType@@YAJKPEAW4DF_DEVICE_TYPE@@@Z; SxQueryDeviceType(ulong,DF_DEVICE_TYPE *)
0x180013208  mov     [rsp+1C0h+var_170], eax
0x18001320c  test    eax, eax
0x18001320e  mov     eax, 7A3h
0x180013213  js      loc_1800134AE
0x180013219  mov     [rsp+1C0h+var_16C], ax
0x18001321e  cmp     dword ptr [rdi], 1
0x180013221  jbe     short loc_18001326F
0x180013223  cmp     esi, [rdi]
0x180013225  jnb     short loc_180013263
0x180013227  mov     eax, esi
0x180013229  lea     rcx, [rax+rax*2]
0x18001322d  mov     ecx, [rdi+rcx*8+8]; unsigned int
0x180013231  cmp     ecx, 0FFFFFFFFh
0x180013234  jz      short loc_18001324F
0x180013236  lea     rdx, [rsp+1C0h+var_17C]; int *
0x18001323b  call    ?SxQueryDeviceDefragAppropriate@@YAJKPEAH@Z; SxQueryDeviceDefragAppropriate(ulong,int *)
0x180013240  test    eax, eax
0x180013242  js      short loc_180013261
0x180013244  cmp     [rsp+1C0h+var_17C], r14d
0x180013249  jnz     short loc_180013261
0x18001324b  inc     esi
0x18001324d  jmp     short loc_180013223
0x18001324f  mov     [rsp+1C0h+var_170], 8900000Dh
0x180013257  mov     eax, 7B1h
0x18001325c  jmp     loc_1800134AE
0x180013261  cmp     esi, [rdi]
0x180013263  jnz     short loc_18001326D
0x180013265  mov     [rsp+1C0h+var_180], 3
0x18001326d  xor     esi, esi
0x18001326f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster> `wil::Feature<__WilFeatureTraits_Feature_MatchingSlabandCluster>::GetImpl(void)'::`2'::impl
0x180013276  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MatchingSlabandCluster@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MatchingSlabandCluster>::__private_IsEnabled(void)
0x18001327b  test    al, al
0x18001327d  jz      short loc_180013298
0x18001327f  mov     edx, [rsp+1C0h+var_180]
0x180013283  lea     eax, [rdx-9]
0x180013286  cmp     eax, 1
0x180013289  ja      short loc_180013298
0x18001328b  mov     ecx, [rdi+8]
0x18001328e  lea     r8, [rsp+1C0h+var_180]
0x180013293  call    ?SxQueryDeviceForThinProvisionedDisk@@YAJKW4DF_DEVICE_TYPE@@PEAW41@@Z; SxQueryDeviceForThinProvisionedDisk(ulong,DF_DEVICE_TYPE,DF_DEVICE_TYPE *)
0x180013298  lea     rax, [rbp+0C0h+hKey]
0x18001329c  mov     r9d, 20019h; samDesired
0x1800132a2  xor     r8d, r8d; ulOptions
0x1800132a5  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800132aa  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Dfrg"
0x1800132b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800132b8  call    cs:__imp_RegOpenKeyExW
0x1800132be  test    eax, eax
0x1800132c0  jnz     short loc_180013309
0x1800132c2  mov     rcx, [rbp+0C0h+hKey]; hKey
0x1800132c6  lea     r9d, [rax+1]; int
0x1800132ca  lea     r8, [rsp+1C0h+var_178]; unsigned int *
0x1800132cf  lea     rdx, aMatchingslabop; "MatchingSlabOptimization"
0x1800132d6  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1800132db  test    eax, eax
0x1800132dd  jnz     short loc_1800132FF
0x1800132df  cmp     [rsp+1C0h+var_178], 1
0x1800132e4  jnz     short loc_1800132FF
0x1800132e6  mov     edx, [rsp+1C0h+var_180]
0x1800132ea  lea     eax, [rdx-9]
0x1800132ed  cmp     eax, 1
0x1800132f0  ja      short loc_1800132FF
0x1800132f2  mov     ecx, [rdi+8]
0x1800132f5  lea     r8, [rsp+1C0h+var_180]
0x1800132fa  call    ?SxQueryDeviceForThinProvisionedDisk@@YAJKW4DF_DEVICE_TYPE@@PEAW41@@Z; SxQueryDeviceForThinProvisionedDisk(ulong,DF_DEVICE_TYPE,DF_DEVICE_TYPE *)
0x1800132ff  mov     rcx, [rbp+0C0h+hKey]; hKey
0x180013303  call    cs:__imp_RegCloseKey
0x180013309  mov     eax, [rsp+1C0h+var_180]
0x18001330d  cmp     eax, 6
0x180013310  jz      short loc_18001331B
0x180013312  cmp     eax, 0Ch
0x180013315  jnz     loc_180013400
0x18001331b  mov     ecx, 4000h; cb
0x180013320  call    cs:__imp_CoTaskMemAlloc
0x180013326  mov     r14, rax
0x180013329  mov     ecx, 7E0h
0x18001332e  test    rax, rax
0x180013331  jz      loc_180013492
0x180013337  mov     [rsp+1C0h+var_16C], cx
0x18001333c  xor     edx, edx; Val
0x18001333e  mov     rcx, rax; void *
0x180013341  mov     [rsp+1C0h+var_170], esi
0x180013345  mov     r8d, 4000h; Size
0x18001334b  call    memset_0
0x180013350  mov     rdx, r15; unsigned __int16 *
0x180013353  lea     rcx, [rbp+0C0h+lpFileName]; this
0x180013357  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001335c  mov     [rsp+1C0h+var_170], eax
0x180013360  test    eax, eax
0x180013362  mov     eax, 7E3h
0x180013367  jns     short loc_180013372
0x180013369  mov     r13, [rbp+0C0h+lpFileName]
0x18001336d  jmp     loc_1800134AE
0x180013372  lea     rcx, [rbp+0C0h+lpFileName]; this
0x180013376  mov     [rsp+1C0h+var_16C], ax
0x18001337b  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x180013380  mov     r13, [rbp+0C0h+lpFileName]
0x180013384  mov     eax, 3
0x180013389  mov     [rsp+1C0h+hTemplateFile], rsi; hTemplateFile
0x18001338e  mov     r8d, eax; dwShareMode
0x180013391  mov     [rsp+1C0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x180013399  xor     r9d, r9d; lpSecurityAttributes
0x18001339c  mov     edx, 0C0000000h; dwDesiredAccess
0x1800133a1  mov     dword ptr [rsp+1C0h+phkResult], eax; dwCreationDisposition
0x1800133a5  mov     rcx, r13; lpFileName
0x1800133a8  call    cs:__imp_CreateFileW
0x1800133ae  mov     rbx, rax
0x1800133b1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800133b5  jz      short loc_1800133FC
0x1800133b7  mov     [rsp+1C0h+lpOverlapped], rsi; lpOverlapped
0x1800133bc  lea     rax, [rbp+0C0h+BytesReturned]
0x1800133c0  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x1800133c5  xor     r9d, r9d; nInBufferSize
0x1800133c8  mov     [rsp+1C0h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x1800133d0  xor     r8d, r8d; lpInBuffer
0x1800133d3  mov     edx, 902ECh; dwIoControlCode
0x1800133d8  mov     [rsp+1C0h+phkResult], r14; lpOutBuffer
0x1800133dd  mov     rcx, rbx; hDevice
0x1800133e0  call    cs:__imp_DeviceIoControl
0x1800133e6  test    eax, eax
0x1800133e8  jz      short loc_1800133FC
0x1800133ea  cmp     dword ptr [r14+0Ch], 1
0x1800133ef  jbe     short loc_1800133FC
0x1800133f1  mov     eax, 0Bh
0x1800133f6  mov     [rsp+1C0h+var_180], eax
0x1800133fa  jmp     short loc_180013400
0x1800133fc  mov     eax, [rsp+1C0h+var_180]
0x180013400  cmp     eax, 3
0x180013403  jz      short loc_18001340A
0x180013405  cmp     eax, 0Ch
0x180013408  jnz     short loc_18001347E
0x18001340a  mov     dword ptr [rsp+1C0h+lpOverlapped], 64h ; 'd'; nFileSystemNameSize
0x180013412  lea     rax, [rbp+0C0h+FileSystemNameBuffer]
0x180013416  mov     [rsp+1C0h+hTemplateFile], rax; lpFileSystemNameBuffer
0x18001341b  xor     r9d, r9d; lpVolumeSerialNumber
0x18001341e  mov     qword ptr [rsp+1C0h+dwFlagsAndAttributes], rsi; lpFileSystemFlags
0x180013423  xor     r8d, r8d; nVolumeNameSize
0x180013426  xor     edx, edx; lpVolumeNameBuffer
0x180013428  mov     [rsp+1C0h+phkResult], rsi; lpMaximumComponentLength
0x18001342d  mov     rcx, r15; lpRootPathName
0x180013430  call    cs:__imp_GetVolumeInformationW
0x180013436  test    eax, eax
0x180013438  jz      short loc_18001347A
0x18001343a  lea     rdx, aNtfs; "NTFS"
0x180013441  lea     rcx, [rbp+0C0h+FileSystemNameBuffer]; String1
0x180013445  call    cs:__imp__wcsicmp
0x18001344b  test    eax, eax
0x18001344d  jz      short loc_180013464
0x18001344f  lea     rdx, aRefs; "REFS"
0x180013456  lea     rcx, [rbp+0C0h+FileSystemNameBuffer]; String1
0x18001345a  call    cs:__imp__wcsicmp
0x180013460  test    eax, eax
0x180013462  jnz     short loc_18001347A
0x180013464  cmp     [rsp+1C0h+var_180], 3
0x180013469  mov     eax, 0Dh
0x18001346e  lea     ecx, [rax-9]
0x180013471  cmovz   eax, ecx
0x180013474  mov     [rsp+1C0h+var_180], eax
0x180013478  jmp     short loc_18001347E
0x18001347a  mov     eax, [rsp+1C0h+var_180]
0x18001347e  mov     [r12], eax
0x180013482  mov     eax, 821h
0x180013487  mov     [rsp+1C0h+var_16C], ax
0x18001348c  mov     [rsp+1C0h+var_170], esi
0x180013490  jmp     short loc_1800134B3
0x180013492  mov     [rsp+1C0h+var_170], 8007000Eh
0x18001349a  mov     [rsp+1C0h+var_16A], cx
0x18001349f  jmp     short loc_1800134B3
0x1800134a1  mov     eax, 784h
0x1800134a6  mov     [rsp+1C0h+var_170], 80070057h
0x1800134ae  mov     [rsp+1C0h+var_16A], ax
0x1800134b3  mov     rcx, rdi; pv
0x1800134b6  call    cs:__imp_CoTaskMemFree
0x1800134bc  mov     rcx, r14; pv
0x1800134bf  call    cs:__imp_CoTaskMemFree
0x1800134c5  mov     edi, [rsp+1C0h+var_170]
0x1800134c9  mov     rcx, r13; unsigned __int16 *
0x1800134cc  call    ?_FreeData@CBsString@@CAXPEAGK@Z; CBsString::_FreeData(ushort *,ulong)
0x1800134d1  lea     rcx, [rbx-1]
0x1800134d5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800134d9  ja      short loc_1800134E4
0x1800134db  mov     rcx, rbx; hObject
0x1800134de  call    cs:__imp_CloseHandle
0x1800134e4  lea     rcx, [rsp+1C0h+var_170]; this
0x1800134e9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800134ee  mov     eax, edi
0x1800134f0  mov     rcx, [rbp+0C0h+var_40]
0x1800134f7  xor     rcx, rsp; StackCookie
0x1800134fa  call    __security_check_cookie
0x1800134ff  mov     rbx, [rsp+1C0h+arg_10]
0x180013507  add     rsp, 190h
0x18001350e  pop     r15
0x180013510  pop     r14
0x180013512  pop     r13
0x180013514  pop     r12
0x180013516  pop     rdi
0x180013517  pop     rsi
0x180013518  pop     rbp
0x180013519  retn
```
