# GetFileImageInfo(ushort const *,_FILE_IMAGE_INFO *)

- ea: `0x1800544e8`
- end: `0x1800548e5`
- name: `?GetFileImageInfo@@YAJPEBGPEAU_FILE_IMAGE_INFO@@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILE_IMAGE_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180015948`

## callees

- `0x180006d02`
- `0x180007014`
- `0x1800538cc`
- `0x1800544e8`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `dbghelp!ImageNtHeader` at `0x180054884`
- `dbghelp!ImageNtHeader` at `0x180054884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005454f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800547b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005454f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800547b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800548a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800548b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800548a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800548b4`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18005463d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18005463d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054539`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054539`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18005479e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18005479e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180054725`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180054725`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180054897`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180054897`

## string_xrefs

- `0x180054584`: `CreateFile failed for file [%ws] [%#x]`
- `0x18005459d`: `CreateFile failed for file [%ws] with error 0x%08x`
- `0x180054763`: `CreateFileMapping failed [%#x]`
- `0x18005477d`: `CreateFileMapping failed with 0x%08x`

## pseudocode

```c
__int64 __fastcall GetFileImageInfo(const unsigned __int16 *a1, struct _FILE_IMAGE_INFO *a2)
{
  HANDLE FileW; // rax
  void *v5; // r14
  void *v6; // rbp
  signed int LastError; // eax
  unsigned int v8; // ebx
  FILE *v9; // rax
  FILE *v10; // rax
  FILE *v11; // rax
  DWORD FileSize; // r15d
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  HANDLE FileMappingW; // rax
  signed int v17; // eax
  const char *v18; // r15
  int v19; // r13d
  void *v20; // rax
  const void *v21; // rsi
  signed int v22; // eax
  FILE *v23; // rax
  FILE *v24; // rax
  FILE *v25; // rax
  PIMAGE_NT_HEADERS v26; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-68h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-68h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-60h]

  *(_OWORD *)a2 = 0;
  *((_OWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 4) = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v6 = 0;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    dwFlagsAndAttributes[0] = v8;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(
        3,
        "GetFileImageInfo",
        1148,
        "CreateFile failed for file [%ws] [%#x]",
        a1,
        *(_QWORD *)dwFlagsAndAttributes);
    }
    else
    {
      AslLogCallPrintf(
        2,
        "GetFileImageInfo",
        1152,
        "CreateFile failed for file [%ws] with error 0x%08x",
        a1,
        *(_QWORD *)dwFlagsAndAttributes);
      if ( EnableDevInvStdErrLog )
      {
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, "Warning: %s, %u: ", "GetFileImageInfo", 1152);
        v10 = o___acrt_iob_func_0(2u);
        fprintf(v10, "CreateFile failed for file [%ws] with error 0x%08x", a1, v8);
        v11 = o___acrt_iob_func_0(2u);
        fprintf(v11, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(50331648, "CreateFile failed for file [%ws] with error 0x%08x", a1, v8);
    }
    goto LABEL_34;
  }
  FileSize = GetFileSize(FileW, 0);
  if ( !FileSize )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(1, "GetFileImageInfo", 1163, "GetFileSize failed, 0 file size");
    }
    else
    {
      AslLogCallPrintf(2, "GetFileImageInfo", 1167, "GetFileSize failed, 0 file size");
      if ( EnableDevInvStdErrLog )
      {
        v13 = o___acrt_iob_func_0(2u);
        fprintf(v13, "Error: %s, %u: ", "GetFileImageInfo", 1167);
        v14 = o___acrt_iob_func_0(2u);
        fprintf(v14, "GetFileSize failed, 0 file size");
        v15 = o___acrt_iob_func_0(2u);
        fprintf(v15, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "GetFileSize failed, 0 file size");
    }
    v8 = -2147467259;
    goto LABEL_41;
  }
  FileMappingW = CreateFileMappingW(v5, 0, 2u, 0, 0, 0);
  v6 = FileMappingW;
  if ( !FileMappingW )
  {
    v17 = GetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    dwCreationDisposition[0] = v8;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(1, "GetFileImageInfo", 1186, "CreateFileMapping failed [%#x]", *(_QWORD *)dwCreationDisposition);
      goto LABEL_34;
    }
    v18 = "CreateFileMapping failed with 0x%08x";
    v19 = 1190;
    AslLogCallPrintf(
      2,
      "GetFileImageInfo",
      1190,
      "CreateFileMapping failed with 0x%08x",
      *(_QWORD *)dwCreationDisposition);
LABEL_30:
    if ( EnableDevInvStdErrLog )
    {
      v23 = o___acrt_iob_func_0(2u);
      fprintf(v23, "Error: %s, %u: ", "GetFileImageInfo", v19);
      v24 = o___acrt_iob_func_0(2u);
      fprintf(v24, v18, v8);
      v25 = o___acrt_iob_func_0(2u);
      fprintf(v25, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v18, v8);
LABEL_34:
    if ( (v8 & 0x80000000) == 0 )
      return v8;
    goto LABEL_38;
  }
  v20 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  v21 = v20;
  if ( !v20 )
  {
    v22 = GetLastError();
    v8 = v22;
    if ( v22 > 0 )
      v8 = (unsigned __int16)v22 | 0x80070000;
    dwCreationDispositiona[0] = v8;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl'::`2'::impl) )
    {
      AslLogCallPrintf(1, "GetFileImageInfo", 1207, "MapViewOfFile failed [%#x]", *(_QWORD *)dwCreationDispositiona);
      goto LABEL_34;
    }
    v18 = "MapViewOfFile failed with 0x%08x";
    v19 = 1211;
    AslLogCallPrintf(2, "GetFileImageInfo", 1211, "MapViewOfFile failed with 0x%08x", *(_QWORD *)dwCreationDispositiona);
    goto LABEL_30;
  }
  v26 = ImageNtHeader(v20);
  if ( v26 )
  {
    *(_QWORD *)a2 = v5;
    *((_QWORD *)a2 + 1) = v6;
    *((_DWORD *)a2 + 4) = FileSize;
    *((_QWORD *)a2 + 3) = v21;
    *((_QWORD *)a2 + 4) = v26;
    return 0;
  }
  v8 = -2147024809;
  UnmapViewOfFile(v21);
LABEL_38:
  if ( v6 )
    CloseHandle(v6);
  if ( v5 != (void *)-1LL )
LABEL_41:
    CloseHandle(v5);
  return v8;
}

```

## disassembly

```asm
0x1800544e8  push    rbx
0x1800544ea  push    rbp
0x1800544eb  push    rsi
0x1800544ec  push    rdi
0x1800544ed  push    r12
0x1800544ef  push    r13
0x1800544f1  push    r14
0x1800544f3  push    r15
0x1800544f5  sub     rsp, 48h
0x1800544f9  xor     r12d, r12d
0x1800544fc  xor     eax, eax
0x1800544fe  xorps   xmm0, xmm0
0x180054501  mov     [rsp+88h+hTemplateFile], r12; hTemplateFile
0x180054506  movups  xmmword ptr [rdx], xmm0
0x180054509  mov     rbx, rdx
0x18005450c  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180054514  movups  xmmword ptr [rdx+10h], xmm0
0x180054518  mov     [rdx+20h], rax
0x18005451c  lea     edi, [rax+3]
0x18005451f  lea     r13d, [r12+1]
0x180054524  mov     [rsp+88h+dwCreationDisposition], edi; dwCreationDisposition
0x180054528  mov     r8d, r13d; dwShareMode
0x18005452b  xor     r9d, r9d; lpSecurityAttributes
0x18005452e  mov     edx, 80000000h; dwDesiredAccess
0x180054533  mov     r15, rcx
0x180054536  mov     esi, r12d
0x180054539  call    cs:__imp_CreateFileW
0x18005453f  mov     r14, rax
0x180054542  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054546  jnz     loc_180054638
0x18005454c  mov     ebp, r12d
0x18005454f  call    cs:__imp_GetLastError
0x180054555  mov     ebx, eax
0x180054557  test    eax, eax
0x180054559  jle     short loc_180054564
0x18005455b  movzx   ebx, ax
0x18005455e  or      ebx, 80070000h
0x180054564  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x18005456b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180054570  mov     [rsp+88h+dwFlagsAndAttributes], ebx
0x180054574  lea     rdx, aGetfileimagein; "GetFileImageInfo"
0x18005457b  mov     qword ptr [rsp+88h+dwCreationDisposition], r15
0x180054580  test    al, al
0x180054582  jz      short loc_18005459D
0x180054584  lea     r9, aCreatefileFail_0; "CreateFile failed for file [%ws] [%#x]"
0x18005458b  mov     r8d, 47Ch
0x180054591  mov     ecx, edi
0x180054593  call    AslLogCallPrintf
0x180054598  jmp     loc_180054876
0x18005459d  lea     r13, aCreatefileFail; "CreateFile failed for file [%ws] with e"...
0x1800545a4  mov     edi, 2
0x1800545a9  mov     r9, r13
0x1800545ac  mov     ecx, edi
0x1800545ae  mov     r8d, 480h
0x1800545b4  call    AslLogCallPrintf
0x1800545b9  cmp     cs:EnableDevInvStdErrLog, r12d
0x1800545c0  jz      short loc_180054613
0x1800545c2  mov     ecx, edi; Ix
0x1800545c4  call    _o___acrt_iob_func_0
0x1800545c9  mov     rcx, rax; Stream
0x1800545cc  lea     r8, aGetfileimagein; "GetFileImageInfo"
0x1800545d3  mov     r9d, 480h
0x1800545d9  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x1800545e0  call    fprintf
0x1800545e5  mov     ecx, edi; Ix
0x1800545e7  call    _o___acrt_iob_func_0
0x1800545ec  mov     rcx, rax; Stream
0x1800545ef  mov     r9d, ebx
0x1800545f2  mov     r8, r15
0x1800545f5  mov     rdx, r13; Format
0x1800545f8  call    fprintf
0x1800545fd  mov     ecx, edi; Ix
0x1800545ff  call    _o___acrt_iob_func_0
0x180054604  mov     rcx, rax; Stream
0x180054607  lea     rdx, asc_18011EAD8; "\n"
0x18005460e  call    fprintf
0x180054613  cmp     cs:g_DeviceMapLogFunction, r12
0x18005461a  jz      loc_180054876
0x180054620  mov     r9d, ebx
0x180054623  mov     r8, r15
0x180054626  mov     rdx, r13
0x180054629  mov     ecx, 3000000h
0x18005462e  call    TraceMessageCallback
0x180054633  jmp     loc_180054876
0x180054638  xor     edx, edx; lpFileSizeHigh
0x18005463a  mov     rcx, r14; hFile
0x18005463d  call    cs:__imp_GetFileSize
0x180054643  mov     r15d, eax
0x180054646  test    eax, eax
0x180054648  jnz     loc_18005470C
0x18005464e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x180054655  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x18005465a  lea     r9, aGetfilesizeFai; "GetFileSize failed, 0 file size"
0x180054661  lea     rdx, aGetfileimagein; "GetFileImageInfo"
0x180054668  test    al, al
0x18005466a  jz      short loc_18005467F
0x18005466c  mov     r8d, 48Bh
0x180054672  mov     ecx, r13d
0x180054675  call    AslLogCallPrintf
0x18005467a  jmp     loc_180054702
0x18005467f  mov     ebx, 48Fh
0x180054684  mov     edi, 2
0x180054689  mov     r8d, ebx
0x18005468c  mov     ecx, edi
0x18005468e  call    AslLogCallPrintf
0x180054693  cmp     cs:EnableDevInvStdErrLog, r12d
0x18005469a  jz      short loc_1800546E8
0x18005469c  mov     ecx, edi; Ix
0x18005469e  call    _o___acrt_iob_func_0
0x1800546a3  mov     rcx, rax; Stream
0x1800546a6  lea     r8, aGetfileimagein; "GetFileImageInfo"
0x1800546ad  mov     r9d, ebx
0x1800546b0  lea     rdx, Format; "Error: %s, %u: "
0x1800546b7  call    fprintf
0x1800546bc  mov     ecx, edi; Ix
0x1800546be  call    _o___acrt_iob_func_0
0x1800546c3  mov     rcx, rax; Stream
0x1800546c6  lea     rdx, aGetfilesizeFai; "GetFileSize failed, 0 file size"
0x1800546cd  call    fprintf
0x1800546d2  mov     ecx, edi; Ix
0x1800546d4  call    _o___acrt_iob_func_0
0x1800546d9  mov     rcx, rax; Stream
0x1800546dc  lea     rdx, asc_18011EAD8; "\n"
0x1800546e3  call    fprintf
0x1800546e8  cmp     cs:g_DeviceMapLogFunction, r12
0x1800546ef  jz      short loc_180054702
0x1800546f1  lea     rdx, aGetfilesizeFai; "GetFileSize failed, 0 file size"
0x1800546f8  mov     ecx, 2000000h
0x1800546fd  call    TraceMessageCallback
0x180054702  mov     ebx, 80004005h
0x180054707  jmp     loc_1800548B1
0x18005470c  xor     r9d, r9d; dwMaximumSizeHigh
0x18005470f  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], r12; lpName
0x180054714  xor     edx, edx; lpFileMappingAttributes
0x180054716  mov     [rsp+88h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x18005471b  mov     rcx, r14; hFile
0x18005471e  lea     edi, [r9+2]
0x180054722  mov     r8d, edi; flProtect
0x180054725  call    cs:__imp_CreateFileMappingW
0x18005472b  mov     rbp, rax
0x18005472e  test    rax, rax
0x180054731  jnz     short loc_18005478C
0x180054733  call    cs:__imp_GetLastError
0x180054739  mov     ebx, eax
0x18005473b  test    eax, eax
0x18005473d  jle     short loc_180054748
0x18005473f  movzx   ebx, ax
0x180054742  or      ebx, 80070000h
0x180054748  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x18005474f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x180054754  mov     [rsp+88h+dwCreationDisposition], ebx
0x180054758  lea     rdx, aGetfileimagein; "GetFileImageInfo"
0x18005475f  test    al, al
0x180054761  jz      short loc_18005477D
0x180054763  lea     r9, aCreatefilemapp_1; "CreateFileMapping failed [%#x]"
0x18005476a  mov     r8d, 4A2h
0x180054770  mov     ecx, r13d
0x180054773  call    AslLogCallPrintf
0x180054778  jmp     loc_180054876
0x18005477d  lea     r15, aCreatefilemapp_0; "CreateFileMapping failed with 0x%08x"
0x180054784  mov     r13d, 4A6h
0x18005478a  jmp     short loc_1800547FC
0x18005478c  xor     r9d, r9d; dwFileOffsetLow
0x18005478f  mov     qword ptr [rsp+88h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x180054794  xor     r8d, r8d; dwFileOffsetHigh
0x180054797  mov     rcx, rbp; hFileMappingObject
0x18005479a  lea     edx, [r9+4]; dwDesiredAccess
0x18005479e  call    cs:__imp_MapViewOfFile
0x1800547a4  mov     rsi, rax
0x1800547a7  test    rax, rax
0x1800547aa  jnz     loc_180054881
0x1800547b0  call    cs:__imp_GetLastError
0x1800547b6  mov     ebx, eax
0x1800547b8  test    eax, eax
0x1800547ba  jle     short loc_1800547C5
0x1800547bc  movzx   ebx, ax
0x1800547bf  or      ebx, 80070000h
0x1800547c5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks> `wil::Feature<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::GetImpl(void)'::`2'::impl
0x1800547cc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DevInv_Bottlenecks@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DevInv_Bottlenecks>::__private_IsEnabled(void)
0x1800547d1  mov     [rsp+88h+dwCreationDisposition], ebx
0x1800547d5  lea     rdx, aGetfileimagein; "GetFileImageInfo"
0x1800547dc  test    al, al
0x1800547de  jz      short loc_1800547EF
0x1800547e0  lea     r9, aMapviewoffileF; "MapViewOfFile failed [%#x]"
0x1800547e7  mov     r8d, 4B7h
0x1800547ed  jmp     short loc_180054770
0x1800547ef  lea     r15, aMapviewoffileF_0; "MapViewOfFile failed with 0x%08x"
0x1800547f6  mov     r13d, 4BBh
0x1800547fc  mov     r9, r15
0x1800547ff  mov     r8, r13
0x180054802  mov     ecx, edi
0x180054804  call    AslLogCallPrintf
0x180054809  cmp     cs:EnableDevInvStdErrLog, r12d
0x180054810  jz      short loc_18005485D
0x180054812  mov     ecx, edi; Ix
0x180054814  call    _o___acrt_iob_func_0
0x180054819  mov     r9d, r13d
0x18005481c  lea     r8, aGetfileimagein; "GetFileImageInfo"
0x180054823  lea     rdx, Format; "Error: %s, %u: "
0x18005482a  mov     rcx, rax; Stream
0x18005482d  call    fprintf
0x180054832  mov     ecx, edi; Ix
0x180054834  call    _o___acrt_iob_func_0
0x180054839  mov     r8d, ebx
0x18005483c  mov     rdx, r15; Format
0x18005483f  mov     rcx, rax; Stream
0x180054842  call    fprintf
0x180054847  mov     ecx, edi; Ix
0x180054849  call    _o___acrt_iob_func_0
0x18005484e  lea     rdx, asc_18011EAD8; "\n"
0x180054855  mov     rcx, rax; Stream
0x180054858  call    fprintf
0x18005485d  cmp     cs:g_DeviceMapLogFunction, r12
0x180054864  jz      short loc_180054876
0x180054866  mov     r8d, ebx
0x180054869  mov     rdx, r15
0x18005486c  mov     ecx, 2000000h
0x180054871  call    TraceMessageCallback
0x180054876  test    ebx, ebx
0x180054878  jns     short loc_1800548D2
0x18005487a  test    rsi, rsi
0x18005487d  jz      short loc_18005489D
0x18005487f  jmp     short loc_180054894
0x180054881  mov     rcx, rsi; Base
0x180054884  call    cs:__imp_ImageNtHeader
0x18005488a  test    rax, rax
0x18005488d  jnz     short loc_1800548BC
0x18005488f  mov     ebx, 80070057h
0x180054894  mov     rcx, rsi; lpBaseAddress
0x180054897  call    cs:__imp_UnmapViewOfFile
0x18005489d  test    rbp, rbp
0x1800548a0  jz      short loc_1800548AB
0x1800548a2  mov     rcx, rbp; hObject
0x1800548a5  call    cs:__imp_CloseHandle
0x1800548ab  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800548af  jz      short loc_1800548D2
0x1800548b1  mov     rcx, r14; hObject
0x1800548b4  call    cs:__imp_CloseHandle
0x1800548ba  jmp     short loc_1800548D2
0x1800548bc  mov     [rbx], r14
0x1800548bf  mov     [rbx+8], rbp
0x1800548c3  mov     [rbx+10h], r15d
0x1800548c7  mov     [rbx+18h], rsi
0x1800548cb  mov     [rbx+20h], rax
0x1800548cf  mov     ebx, r12d
0x1800548d2  mov     eax, ebx
0x1800548d4  add     rsp, 48h
0x1800548d8  pop     r15
0x1800548da  pop     r14
0x1800548dc  pop     r13
0x1800548de  pop     r12
0x1800548e0  pop     rdi
0x1800548e1  pop     rsi
0x1800548e2  pop     rbp
0x1800548e3  pop     rbx
0x1800548e4  retn
```
