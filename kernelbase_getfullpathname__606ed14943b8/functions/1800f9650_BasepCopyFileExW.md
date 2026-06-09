# BasepCopyFileExW

- ea: `0x1800f9650`
- end: `0x1800fb78d`
- name: `BasepCopyFileExW`
- size: `8509`
- prototype: ``
- caller_count: `4`
- callee_count: `26`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f8dc0`
- `0x1800f9010`
- `0x1800f9500`
- `0x180100030`

## callees

- `0x180012670`
- `0x18004b9d0`
- `0x18004bc10`
- `0x18004be40`
- `0x18004c490`
- `0x180053330`
- `0x180053c30`
- `0x1800b918c`
- `0x1800b92b0`
- `0x1800bcab0`
- `0x1800d3694`
- `0x1800d3eb0`
- `0x1800d6840`
- `0x1800d6a90`
- `0x1800d770c`
- `0x1800f2f00`
- `0x1800f9650`
- `0x1800ff414`
- `0x180102274`
- `0x180104f90`
- `0x1801050a0`
- `0x180105e58`
- `0x18011c524`
- `0x1801369c9`
- `0x18013c428`
- `0x180194f10`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800fa085`
- `ntdll!NtQueryInformationFile` at `0x1800fa0c6`
- `ntdll!NtQueryInformationFile` at `0x1800fa15a`
- `ntdll!NtQueryInformationFile` at `0x1800fa085`
- `ntdll!NtQueryInformationFile` at `0x1800fa0c6`
- `ntdll!NtQueryInformationFile` at `0x1800fa15a`
- `ntdll!wcslen` at `0x1800f9d07`
- `ntdll!wcslen` at `0x1800f9d07`
- `ntdll!NtSetInformationFile` at `0x1800faae3`
- `ntdll!NtSetInformationFile` at `0x1800faffb`
- `ntdll!NtSetInformationFile` at `0x1800fb4c3`
- `ntdll!NtSetInformationFile` at `0x1800fb579`
- `ntdll!NtSetInformationFile` at `0x1800faae3`
- `ntdll!NtSetInformationFile` at `0x1800faffb`
- `ntdll!NtSetInformationFile` at `0x1800fb4c3`
- `ntdll!NtSetInformationFile` at `0x1800fb579`
- `ntdll!NtFsControlFile` at `0x1800fb0d2`
- `ntdll!NtFsControlFile` at `0x1800fb19a`
- `ntdll!NtFsControlFile` at `0x1800fb29d`
- `ntdll!NtFsControlFile` at `0x1800fb61b`
- `ntdll!NtFsControlFile` at `0x1800fb0d2`
- `ntdll!NtFsControlFile` at `0x1800fb19a`
- `ntdll!NtFsControlFile` at `0x1800fb29d`
- `ntdll!NtFsControlFile` at `0x1800fb61b`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fa011`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fa6d1`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fa71b`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fad8d`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fae03`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fa011`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fa6d1`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fa71b`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fad8d`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800fae03`
- `ntdll!NtCreateFile` at `0x1800f9cd0`
- `ntdll!NtCreateFile` at `0x1800fa881`
- `ntdll!NtCreateFile` at `0x1800fa8f4`
- `ntdll!NtCreateFile` at `0x1800f9cd0`
- `ntdll!NtCreateFile` at `0x1800fa881`
- `ntdll!NtCreateFile` at `0x1800fa8f4`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9976`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9d2b`
- `ntdll!RtlSetLastWin32Error` at `0x1800fb65d`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9976`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9d2b`
- `ntdll!RtlSetLastWin32Error` at `0x1800fb65d`
- `ntdll!NtWaitForSingleObject` at `0x1800faeeb`
- `ntdll!NtWaitForSingleObject` at `0x1800faf94`
- `ntdll!NtWaitForSingleObject` at `0x1800fb0f3`
- `ntdll!NtWaitForSingleObject` at `0x1800fb1bb`
- `ntdll!NtWaitForSingleObject` at `0x1800fb2be`
- `ntdll!NtWaitForSingleObject` at `0x1800faeeb`
- `ntdll!NtWaitForSingleObject` at `0x1800faf94`
- `ntdll!NtWaitForSingleObject` at `0x1800fb0f3`
- `ntdll!NtWaitForSingleObject` at `0x1800fb1bb`
- `ntdll!NtWaitForSingleObject` at `0x1800fb2be`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f9a93`
- `ntdll!RtlSetCurrentTransaction` at `0x1800fb6fc`
- `ntdll!RtlSetCurrentTransaction` at `0x180198936`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f9a93`
- `ntdll!RtlSetCurrentTransaction` at `0x1800fb6fc`
- `ntdll!RtlSetCurrentTransaction` at `0x180198936`
- `ntdll!NtCopyFileChunk` at `0x1800faec3`
- `ntdll!NtCopyFileChunk` at `0x1800faf72`
- `ntdll!NtCopyFileChunk` at `0x1800faec3`
- `ntdll!NtCopyFileChunk` at `0x1800faf72`
- `ntdll!RtlEqualUnicodeString` at `0x1800fa616`
- `ntdll!RtlEqualUnicodeString` at `0x1800fa616`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800f9be2`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800f9be2`
- `ntdll!RtlGetCurrentTransaction` at `0x1800f9960`
- `ntdll!RtlGetCurrentTransaction` at `0x1800f9960`
- `ntdll!RtlNtStatusToDosError` at `0x1800fac36`
- `ntdll!RtlNtStatusToDosError` at `0x1800fac36`
- `ntdll!NtClose` at `0x1800faaa7`
- `ntdll!NtClose` at `0x1800fab00`
- `ntdll!NtClose` at `0x1800faaa7`
- `ntdll!NtClose` at `0x1800fab00`
- `ntdll!RtlFreeHeap` at `0x1800fa18d`
- `ntdll!RtlFreeHeap` at `0x1800fa1c8`
- `ntdll!RtlFreeHeap` at `0x1800fa41f`
- `ntdll!RtlFreeHeap` at `0x1800fb71f`
- `ntdll!RtlFreeHeap` at `0x1800fb74d`
- `ntdll!RtlFreeHeap` at `0x18019895d`
- `ntdll!RtlFreeHeap` at `0x18019898a`
- `ntdll!RtlFreeHeap` at `0x1800fa18d`
- `ntdll!RtlFreeHeap` at `0x1800fa1c8`
- `ntdll!RtlFreeHeap` at `0x1800fa41f`
- `ntdll!RtlFreeHeap` at `0x1800fb71f`
- `ntdll!RtlFreeHeap` at `0x1800fb74d`
- `ntdll!RtlFreeHeap` at `0x18019895d`
- `ntdll!RtlFreeHeap` at `0x18019898a`
- `ntdll!RtlAllocateHeap` at `0x1800fa11b`
- `ntdll!RtlAllocateHeap` at `0x1800fa11b`

## pseudocode

```c
__int64 __fastcall BasepCopyFileExW(
        wchar_t *a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        HANDLE *a10,
        HANDLE *a11,
        __int64 a12,
        DWORD a13,
        int a14,
        unsigned int a15,
        __int128 *a16)
{
  __int128 *v17; // rsi
  unsigned int v18; // edi
  int v19; // ecx
  DWORD v20; // ebx
  BOOL v21; // eax
  DWORD v22; // edx
  int v23; // edx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 result; // rax
  int v28; // ebx
  int *v29; // rax
  int v30; // r8d
  int v31; // eax
  unsigned int v32; // r13d
  ULONG CreateOptions; // r14d
  int v34; // r12d
  NTSTATUS v35; // eax
  ULONG v36; // ecx
  __int64 v37; // rcx
  PVOID v38; // rsi
  DWORD v39; // r15d
  ULONG v40; // ebx
  NTSTATUS v41; // eax
  NTSTATUS v42; // esi
  wchar_t *v43; // rsi
  size_t v44; // rax
  ULONG v45; // ecx
  NTSTATUS LastStatusValue; // esi
  HANDLE EventW; // rax
  void *v48; // rsi
  char v49; // r12
  unsigned int v50; // ebx
  PVOID Heap; // rax
  unsigned int *v52; // r8
  int v53; // ebx
  unsigned int v54; // eax
  int v55; // r12d
  __int64 v56; // rdx
  unsigned int *v57; // rcx
  int i; // eax
  unsigned int v59; // r12d
  char v60; // bl
  char v61; // r13
  __int64 *v62; // r14
  unsigned int v63; // edx
  __int64 v64; // rcx
  __int64 v65; // rax
  int v66; // eax
  ULONG v67; // ebx
  unsigned __int64 v68; // rdx
  __int16 v69; // bx
  HANDLE v70; // rcx
  int v71; // r15d
  int v72; // r14d
  HANDLE EventA; // rbx
  __int64 v74; // rbx
  struct _TEB *v75; // rsi
  int v76; // r13d
  unsigned int v77; // esi
  int v78; // eax
  NTSTATUS v79; // r12d
  int v80; // ecx
  NTSTATUS v81; // esi
  int v82; // eax
  NTSTATUS Status; // eax
  __int64 v84; // rax
  int v85; // eax
  HANDLE FileW; // rax
  ULONG LastErrorValue; // esi
  NTSTATUS v88; // ebx
  ULONG v89; // edx
  int AllocationSize; // [rsp+20h] [rbp-6C8h]
  int FileAttributes; // [rsp+28h] [rbp-6C0h]
  int ShareAccess; // [rsp+30h] [rbp-6B8h]
  int v93; // [rsp+B0h] [rbp-638h]
  HANDLE hObject; // [rsp+B8h] [rbp-630h] BYREF
  HANDLE FileHandle; // [rsp+C0h] [rbp-628h] BYREF
  PVOID P; // [rsp+C8h] [rbp-620h]
  int v97; // [rsp+D0h] [rbp-618h]
  char v98; // [rsp+D4h] [rbp-614h]
  __int64 v99; // [rsp+D8h] [rbp-610h] BYREF
  DWORD BytesReturned; // [rsp+E0h] [rbp-608h] BYREF
  char v101; // [rsp+E4h] [rbp-604h]
  __int64 v102; // [rsp+E8h] [rbp-600h] BYREF
  __int64 v103; // [rsp+F0h] [rbp-5F8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-5F0h] BYREF
  unsigned int v105; // [rsp+108h] [rbp-5E0h]
  __int64 v106; // [rsp+10Ch] [rbp-5DCh] BYREF
  wchar_t *String; // [rsp+118h] [rbp-5D0h] BYREF
  __int64 v108; // [rsp+120h] [rbp-5C8h]
  __int64 v109; // [rsp+128h] [rbp-5C0h] BYREF
  ULONG v110; // [rsp+130h] [rbp-5B8h]
  int v111; // [rsp+134h] [rbp-5B4h]
  SECURITY_INFORMATION SecurityInfo[2]; // [rsp+138h] [rbp-5B0h] BYREF
  int v113; // [rsp+140h] [rbp-5A8h] BYREF
  unsigned int v114; // [rsp+144h] [rbp-5A4h]
  int v115; // [rsp+148h] [rbp-5A0h]
  PVOID j; // [rsp+150h] [rbp-598h]
  __int64 v117; // [rsp+158h] [rbp-590h] BYREF
  HANDLE v118; // [rsp+160h] [rbp-588h] BYREF
  LPCWSTR lpFileName; // [rsp+168h] [rbp-580h]
  HANDLE Handle; // [rsp+170h] [rbp-578h] BYREF
  int v121[4]; // [rsp+178h] [rbp-570h] BYREF
  int v122; // [rsp+188h] [rbp-560h]
  int v123; // [rsp+18Ch] [rbp-55Ch]
  int v124; // [rsp+190h] [rbp-558h]
  unsigned int v125; // [rsp+194h] [rbp-554h]
  int v126; // [rsp+198h] [rbp-550h]
  __int64 FsInformation; // [rsp+1A0h] [rbp-548h] BYREF
  int v128[2]; // [rsp+1A8h] [rbp-540h] BYREF
  int v129; // [rsp+1B0h] [rbp-538h]
  int v130; // [rsp+1B4h] [rbp-534h] BYREF
  PVOID v131[2]; // [rsp+1B8h] [rbp-530h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1C8h] [rbp-520h] BYREF
  __int128 EaBuffer; // [rsp+1F8h] [rbp-4F0h] BYREF
  __int128 v134; // [rsp+208h] [rbp-4E0h]
  struct _OVERLAPPED Overlapped; // [rsp+218h] [rbp-4D0h] BYREF
  HANDLE *v136; // [rsp+238h] [rbp-4B0h]
  HANDLE *v137; // [rsp+240h] [rbp-4A8h]
  __int64 v138; // [rsp+248h] [rbp-4A0h]
  __int64 v139; // [rsp+250h] [rbp-498h]
  __int64 v140; // [rsp+258h] [rbp-490h]
  _QWORD v141[2]; // [rsp+260h] [rbp-488h] BYREF
  int v142; // [rsp+270h] [rbp-478h]
  int v143; // [rsp+290h] [rbp-458h]
  int *v144; // [rsp+2D0h] [rbp-418h]
  __int64 v145; // [rsp+2D8h] [rbp-410h]
  __int64 v146; // [rsp+2E0h] [rbp-408h]
  __int64 v147; // [rsp+2E8h] [rbp-400h]
  __int64 v148; // [rsp+2F0h] [rbp-3F8h]
  __int64 v149; // [rsp+2F8h] [rbp-3F0h]
  __int128 OutputBuffer; // [rsp+310h] [rbp-3D8h] BYREF
  UNICODE_STRING String2; // [rsp+320h] [rbp-3C8h] BYREF
  __int128 FileInformation; // [rsp+330h] [rbp-3B8h] BYREF
  __int64 v153; // [rsp+340h] [rbp-3A8h]
  __int128 InBuffer; // [rsp+348h] [rbp-3A0h] BYREF
  __int64 v155; // [rsp+358h] [rbp-390h]
  __int64 v156[2]; // [rsp+360h] [rbp-388h] BYREF
  __int128 v157; // [rsp+370h] [rbp-378h]
  __int128 v158; // [rsp+380h] [rbp-368h]
  __int64 v159; // [rsp+390h] [rbp-358h]
  _QWORD InputBuffer[2]; // [rsp+398h] [rbp-350h] BYREF
  __int128 v161; // [rsp+3A8h] [rbp-340h] BYREF
  __int128 v162; // [rsp+3B8h] [rbp-330h]
  __int64 v163; // [rsp+3C8h] [rbp-320h]
  __int128 v164; // [rsp+3D0h] [rbp-318h] BYREF
  __int128 v165; // [rsp+3E0h] [rbp-308h] BYREF
  __int128 v166; // [rsp+3F0h] [rbp-2F8h]
  _BYTE v167[4]; // [rsp+400h] [rbp-2E8h] BYREF
  int v168; // [rsp+404h] [rbp-2E4h]
  _DWORD v169[136]; // [rsp+480h] [rbp-268h] BYREF

  *(_QWORD *)&OutputBuffer = a3;
  lpFileName = a2;
  String = a1;
  v17 = a16;
  v136 = a10;
  v138 = (__int64)a10;
  v137 = a11;
  v139 = (__int64)a11;
  v109 = a12;
  FileHandle = (HANDLE)-1LL;
  hObject = (HANDLE)-1LL;
  v18 = 0;
  v106 = 0;
  v103 = 0x100000000LL;
  v113 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  v153 = 0;
  v161 = 0;
  v162 = 0;
  v163 = 0;
  FsInformation = 0;
  *(_OWORD *)v121 = 0;
  *(_OWORD *)v131 = 0;
  v118 = 0;
  Handle = 0;
  v130 = 0;
  memset_0(v141, 0, 0xA8u);
  v99 = 0;
  *(_OWORD *)v156 = 0;
  v157 = 0;
  v158 = 0;
  v159 = 0;
  SecurityInfo[0] = 0;
  LODWORD(v117) = -1;
  *(_QWORD *)v128 = 0;
  EaBuffer = 0;
  v134 = 0;
  v165 = 0;
  v166 = 0;
  v102 = 0;
  v19 = a8;
  if ( (a8 & 0x411B0770) != 0 )
    goto LABEL_272;
  if ( (a9 & 0xFEC4780F) != 0 )
    goto LABEL_272;
  v20 = a13;
  if ( (a13 & 0xFFFFFFFC) != 0 )
    goto LABEL_272;
  if ( Feature_BlockCloningInCopy_Enabled == -1 )
  {
    v108 = (unsigned int)Feature_BlockCloningInCopy__private_featureState;
    if ( (Feature_BlockCloningInCopy__private_featureState & 0x10) == 0 )
    {
      LODWORD(v108) = Feature_BlockCloningInCopy__private_featureState | 1;
      wil_details_FeatureReporting_ReportUsageToService(Feature_BlockCloningInCopy__private_descriptor, v108, 3, 1);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
        v108,
        3,
        Feature_BlockCloningInCopy__private_descriptor);
      v18 = 0;
    }
    Feature_BlockCloningInCopy_Enabled = 1;
    v21 = 1;
    v19 = a8;
  }
  else
  {
    v21 = Feature_BlockCloningInCopy_Enabled == 1;
  }
  v22 = v20 | 2;
  if ( v21 )
    v22 = v20;
  if ( (BytesReturned = v22, a15 - 1 <= 0x1FE)
    || a14 && (unsigned int)(a14 - 4096) > 0x3FFFF000
    || (v19 & 0x4002) == 0x4002 )
  {
LABEL_272:
    BaseSetLastNTError(3221225485LL);
    return 0;
  }
  LODWORD(a8) = a9 | v19;
  if ( RtlGetCurrentTransaction() )
  {
    RtlSetLastWin32Error(0x1A45u);
    return 0;
  }
  result = BasepCloudFileCopy(v24, v23, v25, v26);
  if ( !(_DWORD)result )
    return result;
  v28 = 0;
  P = 0;
  LODWORD(v134) = 0;
  EaBuffer = 1u;
  if ( v17 )
  {
    v165 = *v17;
    v166 = v17[1];
    *((_QWORD *)&v134 + 1) = &v165;
  }
  if ( (_QWORD)OutputBuffer || a5 || a6 )
  {
    v141[1] = 0;
    v142 = 0;
    v29 = &v130;
    if ( a5 )
      v29 = a5;
    v144 = v29;
    v145 = a4;
    v146 = a6;
    v147 = a7;
    if ( (_QWORD)OutputBuffer )
    {
      v148 = *(_QWORD *)OutputBuffer;
      v149 = *(_QWORD *)(OutputBuffer + 8);
    }
    v99 = (__int64)v141;
  }
  RtlSetCurrentTransaction(v109);
  v143 = 1;
  v30 = a8;
  if ( (a8 & 0x1000) == 0 )
  {
    v31 = BasepCopyCheckNoBuffering();
    v30 = a8;
    if ( v31 )
    {
      v30 = a8 | 0x1000;
      LODWORD(a8) = a8 | 0x1000;
    }
  }
  if ( (v30 & 2) != 0 )
  {
    v30 &= 0xFFFEEFFF;
    LODWORD(a8) = v30;
  }
  if ( (v30 & 0x1000) != 0 )
    v28 = 1;
  HIDWORD(v103) = v28;
  v123 = v28;
  LODWORD(v109) = v30 & 0x180;
  LODWORD(v108) = (_DWORD)v109 != 0 ? 0x4000 : 0;
  v32 = ((v30 & 0xFC | 0xFFFFFFF8) << 28) | ((v30 & 0x2020) != 0 ? 0x1000000 : 0);
  CreateOptions = v108 | 0x10200004 | (v28 != 0 ? 8 : 0) | ((_DWORD)v109 == 0 ? 0x40 : 0);
  v97 = CreateOptions;
  v111 = 0;
  v122 = 5;
  v34 = 5;
  if ( (v30 & 0x20000) != 0 )
    v34 = 7;
  v124 = v34;
  v122 = v34;
  v35 = RtlDosPathNameToNtPathName_U_WithStatus(String, v131, 0, 0);
  if ( v35 < 0 )
  {
    if ( v35 != -1073741801 && v35 != -1073741670 )
    {
      v36 = 3;
      goto LABEL_260;
    }
LABEL_41:
    v37 = (unsigned int)v35;
    goto LABEL_42;
  }
  while ( 2 )
  {
    v39 = v32;
    v105 = v32;
    v40 = v34;
    v110 = v34;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v131;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v41 = NtCreateFile(
                &FileHandle,
                v39 | 0x100080,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                0,
                v40,
                1u,
                CreateOptions,
                &EaBuffer,
                0x20u);
        v42 = v41;
        if ( v41 >= 0 )
          break;
        BaseSetLastNTError((unsigned int)v41);
        if ( v42 == -1073741638 )
        {
          v43 = String;
          v44 = wcslen(String);
          if ( v44 <= 1 || (v45 = 3, v43[v44 - 1] != 92) )
            v45 = 5;
          RtlSetLastWin32Error(v45);
        }
        FileHandle = (HANDLE)-1LL;
        if ( (NtCurrentTeb()->LastErrorValue == 1314 || NtCurrentTeb()->LastErrorValue == 5) && (v39 & 0x1000000) != 0 )
        {
          v39 &= ~0x1000000u;
          goto LABEL_60;
        }
        if ( (NtCurrentTeb()->LastErrorValue == 5 || NtCurrentTeb()->LastErrorValue == 32) && (v39 & 0x40000000) != 0 )
        {
          v39 &= ~0x40000000u;
          v105 = v39;
          if ( (v32 & 0x1000000) != 0 )
          {
            v39 |= 0x1000000u;
LABEL_60:
            v105 = v39;
          }
        }
        else
        {
          if ( (v40 & 2) != 0 )
          {
            if ( (CreateOptions & 0x200000) == 0 )
              goto LABEL_43;
            CreateOptions &= ~0x200000u;
            v97 = CreateOptions;
            v105 = v32;
            v40 = v34;
            v110 = v34;
          }
          else
          {
            v40 |= 2u;
            v110 = v40;
            v105 = v32;
            CreateOptions &= ~8u;
            v97 = CreateOptions;
            LODWORD(a8) = a8 & 0xFFFFEFFF;
            HIDWORD(v103) = 0;
            v123 = 0;
          }
          v39 = v32;
        }
      }
      if ( v111 )
        break;
      v143 = 6;
      v111 = 1;
      LastStatusValue = BasepProcessNameGrafting(FileHandle, v128, (__int64)&v117, a8, BytesReturned);
      if ( LastStatusValue < 0 )
      {
        CloseHandle(FileHandle);
        FileHandle = (HANDLE)-1LL;
        goto LABEL_70;
      }
      if ( (_DWORD)v103 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        v48 = EventW;
        if ( EventW )
        {
          v93 = CopyNameGraftNow(
                  FileHandle,
                  (__int64)String,
                  (__int64)lpFileName,
                  (a8 & 0x80u) != 0LL ? 0x4001 : 0,
                  AllocationSize,
                  FileAttributes,
                  ShareAccess,
                  &a8,
                  EventW);
          CloseHandle(v48);
          CloseHandle(FileHandle);
          FileHandle = (HANDLE)-1LL;
          v18 = v93 != 0;
        }
        else
        {
          CloseHandle(FileHandle);
          FileHandle = (HANDLE)-1LL;
        }
        goto LABEL_43;
      }
      if ( HIDWORD(v106) )
        break;
      CreateOptions &= ~0x200000u;
      v97 = CreateOptions;
      CloseHandle(FileHandle);
      FileHandle = (HANDLE)-1LL;
    }
    SecurityInfo[1] = BasepGetSecurityToPrefetchSource(v39, (unsigned int)a8);
    if ( (CreateOptions & 8) != 0 || (a8 & 2) != 0 )
      goto LABEL_82;
    v35 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
    if ( v35 < 0 )
      goto LABEL_41;
    if ( (FsInformation & 0x1000000000LL) != 0 && (FsInformation & 0x100000000000LL) == 0 )
    {
      BasepDisableLocalFileBuffering(FileHandle);
      BasepRemotePrefetchSource(FileHandle);
    }
LABEL_82:
    v35 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v35 < 0 )
      goto LABEL_41;
    v35 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v161, 0x28u, FileBasicInformation);
    if ( v35 < 0 )
      goto LABEL_41;
    v49 = v163;
    v141[0] = *((_QWORD *)&FileInformation + 1);
    v50 = 4096;
    v129 = 4096;
    while ( 2 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v50);
      v38 = Heap;
      P = Heap;
      if ( !Heap )
      {
        BaseSetLastNTError(3221225495LL);
        goto LABEL_262;
      }
      LastStatusValue = NtQueryInformationFile(FileHandle, &IoStatusBlock, Heap, v50 - 2, FileStreamInformation);
      v52 = (unsigned int *)P;
      if ( LastStatusValue < 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        P = 0;
        v50 *= 2;
        v129 = v50;
        goto LABEL_90;
      }
      if ( !IoStatusBlock.Information )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        P = 0;
LABEL_90:
        v52 = 0;
      }
      if ( LastStatusValue == -2147483643 || LastStatusValue == -1073741789 )
        continue;
      break;
    }
    if ( (_QWORD)OutputBuffer || (a8 & 0x4002) != 0 )
    {
      LOWORD(v156[0]) = (a8 & 2) != 0 ? 31387 : 19139;
      WORD1(v156[0]) = 56;
      v156[1] = v161;
      *(_QWORD *)&v157 = v162;
      *((_QWORD *)&v157 + 1) = *((_QWORD *)&FileInformation + 1);
      v158 = *((unsigned __int64 *)&FileInformation + 1);
      HIDWORD(v156[0]) = 0;
      LODWORD(v159) = 0;
      if ( v52 )
      {
        v56 = 0;
        v140 = 0;
        v57 = v52;
        j = v52;
        for ( i = 0; ; ++i )
        {
          v56 += *((_QWORD *)v57 + 1);
          v140 = v56;
          HIDWORD(v156[0]) = i + 1;
          if ( !*v57 )
            break;
          v57 = (unsigned int *)((char *)v57 + *v57);
          j = v57;
        }
        v141[0] = v56;
        *(_QWORD *)&v158 = v56;
        HIDWORD(v156[0]) = i;
      }
    }
    v161 = 0;
    LODWORD(v163) = 0;
    if ( (a8 & 2) != 0 && ((__int64)v158 < 0x80000 || (v49 & 0x10) != 0) )
    {
      LODWORD(a8) = a8 & 0xFFFFFFFD;
      LOWORD(v156[0]) = 19139;
    }
    v53 = HIDWORD(v102);
    v54 = BaseCopyStream(
            String,
            &FileHandle,
            v39,
            lpFileName,
            0,
            0,
            (__int64 *)&FileInformation + 1,
            (int *)&a8,
            &hObject,
            (int *)&v106,
            &v113,
            &v99,
            v156,
            SHIDWORD(v102),
            v128[1],
            SecurityInfo[1],
            (__int64)SecurityInfo,
            BytesReturned,
            a14,
            a15,
            SHIDWORD(v103),
            &v102);
    v18 = v54;
    if ( !v53 )
      goto LABEL_117;
    if ( !v54 )
    {
      if ( NtCurrentTeb()->LastErrorValue != 80 || (a8 & 1) == 0 )
      {
        v55 = v49 & 1;
        if ( !v55 )
          BaseMarkFileForDelete(hObject);
        if ( hObject != (HANDLE)-1LL )
        {
          CloseHandle(hObject);
          hObject = (HANDLE)-1LL;
        }
        if ( v55 )
        {
          SetFileAttributesW(lpFileName, 0x80u);
          DeleteFileW(lpFileName);
        }
        if ( FileHandle != (HANDLE)-1LL )
        {
          CloseHandle(FileHandle);
          FileHandle = (HANDLE)-1LL;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        P = 0;
        CreateOptions &= ~0x200000u;
        v97 = CreateOptions;
        HIDWORD(v102) = 0;
        v34 = v124;
        continue;
      }
LABEL_117:
      if ( !v54 )
        goto LABEL_165;
    }
    break;
  }
  if ( (a8 & 0x8000) != 0 )
    goto LABEL_165;
  v143 = 1;
  if ( !P )
    goto LABEL_165;
  v59 = 0;
  v125 = 0;
  v60 = 0;
  v98 = 0;
  v61 = 0;
  v101 = 0;
  v62 = (__int64 *)P;
  for ( j = P; ; j = v62 )
  {
LABEL_121:
    while ( 1 )
    {
      LastStatusValue = 0;
      v143 = 1;
      v63 = *((_DWORD *)v62 + 1);
      if ( v63 > 2 && *((_WORD *)v62 + 13) != 58 )
        break;
      if ( !*(_DWORD *)v62 )
        goto LABEL_165;
      v62 = (__int64 *)((char *)v62 + *(unsigned int *)v62);
      j = v62;
    }
    *(_DWORD *)(&String2.MaximumLength + 1) = 0;
    *(_DWORD *)&String2.Length = 786444;
    String2.Buffer = (PWSTR)((char *)v62 + v63 + 12);
    if ( v63 <= 0xC || RtlEqualUnicodeString(&DataStreamTypeName, &String2, 1u) )
      break;
    if ( !*(_DWORD *)v62 )
      goto LABEL_165;
    v62 = (__int64 *)((char *)v62 + *(unsigned int *)v62);
  }
  v125 = ++v59;
  if ( v18 == 2 )
  {
    v64 = v99;
    if ( v99 )
    {
      if ( v59 >= (unsigned int)v159 )
      {
        v64 = v99;
        v65 = *((_QWORD *)&v158 + 1);
      }
      else
      {
        v65 = v62[1];
      }
      *(_QWORD *)(v64 + 8) += v65;
    }
  }
  if ( !v60 )
  {
    memset_0(v169, 0, 0x218u);
    v98 = 1;
    v66 = NtQueryVolumeInformationFile(hObject, &IoStatusBlock, v169, 0x218u, FileFsAttributeInformation);
    if ( v66 >= 0 )
    {
      if ( (v169[0] & 0x40000) != 0 )
        v66 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, v169, 0x218u, FileFsAttributeInformation);
      if ( v66 >= 0 && (v169[0] & 0x40000) != 0 )
      {
        v61 = 1;
        v101 = 1;
        goto LABEL_140;
      }
    }
    if ( v66 >= 0 )
      v66 = -1073741637;
    if ( (a8 & 0x13B87F0) != 0 )
    {
      if ( v99 )
      {
        *(_DWORD *)(v99 + 20) = 1;
        v74 = v99;
        *(_DWORD *)(v74 + 24) = RtlNtStatusToDosError(v66);
        *(_QWORD *)(v99 + 64) = 0;
        *(_QWORD *)(v99 + 32) = FileHandle;
        *(_QWORD *)(v99 + 40) = hObject;
      }
      if ( !(unsigned int)BasepCopyFileCallback(8) )
      {
        v75 = NtCurrentTeb();
        if ( v75 )
          LastStatusValue = v75->LastStatusValue;
        else
          LastStatusValue = -1073741811;
        v18 = 0;
        goto LABEL_157;
      }
    }
LABEL_140:
    LastStatusValue = 0;
  }
  if ( v18 != 1 && (v18 != 2 || (_DWORD)v159 != v59) )
    goto LABEL_157;
  if ( v18 != 2 )
  {
    LODWORD(v159) = v59;
    *((_QWORD *)&v158 + 1) = 0;
  }
  *(_QWORD *)&v121[2] = v62 + 3;
  LOWORD(v121[0]) = *((_WORD *)v62 + 2);
  HIWORD(v121[0]) = v121[0];
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = FileHandle;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v121;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v67 = 268435460;
  v97 = 268435460;
  if ( (_DWORD)v109 )
    v67 = 268451844;
  v97 = v67;
  if ( HIDWORD(v102) )
  {
    v67 |= 0x200000u;
    v97 = v67;
  }
  LastStatusValue = NtCreateFile(
                      &Handle,
                      0x80100000,
                      &ObjectAttributes,
                      &IoStatusBlock,
                      0,
                      0,
                      5u,
                      1u,
                      v67,
                      &EaBuffer,
                      0x20u);
  if ( LastStatusValue == -1073741757 )
    LastStatusValue = NtCreateFile(
                        &Handle,
                        0x80100000,
                        &ObjectAttributes,
                        &IoStatusBlock,
                        0,
                        0,
                        7u,
                        1u,
                        v67,
                        &EaBuffer,
                        0x20u);
  if ( LastStatusValue < 0 )
    goto LABEL_158;
  LODWORD(v103) = 0;
  HIDWORD(v106) = 0;
  v68 = (unsigned __int64)LOWORD(v121[0]) >> 1;
  v69 = *(_WORD *)(*(_QWORD *)&v121[2] + 2 * v68);
  *(_WORD *)(*(_QWORD *)&v121[2] + 2 * v68) = 0;
  v118 = (HANDLE)-1LL;
  LODWORD(v103) = a8 & 0xFFFEEFFE;
  HIDWORD(v106) = v102;
  v18 = BaseCopyStream(
          String,
          &Handle,
          v39,
          *(const WCHAR **)&v121[2],
          hObject,
          v106,
          v62 + 1,
          (int *)&v103,
          &v118,
          0,
          &v113,
          &v99,
          v156,
          SHIDWORD(v102),
          v128[1],
          SecurityInfo[1],
          (__int64)SecurityInfo,
          BytesReturned | 2,
          a14,
          a15,
          0,
          (_DWORD *)&v106 + 1);
  *(_WORD *)(*(_QWORD *)&v121[2] + 2 * ((unsigned __int64)LOWORD(v121[0]) >> 1)) = v69;
  NtClose(Handle);
  v70 = v118;
  if ( v118 != (HANDLE)-1LL )
  {
    if ( v18 )
    {
      LastStatusValue = NtSetInformationFile(v118, &IoStatusBlock, &v161, 0x28u, FileBasicInformation);
      v70 = v118;
    }
    NtClose(v70);
  }
LABEL_157:
  if ( LastStatusValue < 0 )
  {
LABEL_158:
    v18 = 0;
    BaseSetLastNTError((unsigned int)LastStatusValue);
  }
  if ( v18 )
  {
LABEL_183:
    if ( !*(_DWORD *)v62 )
      goto LABEL_165;
    v62 = (__int64 *)((char *)v62 + *(unsigned int *)v62);
    j = v62;
    v60 = v98;
    goto LABEL_121;
  }
  if ( !v61 )
  {
    LastStatusValue = 0;
    v18 = 1;
    goto LABEL_183;
  }
  if ( (!v99 || !*(_DWORD *)(v99 + 104)) && (a8 & 2) == 0 )
    BaseMarkFileForDelete(hObject);
LABEL_165:
  if ( !v18 || (a8 & 0x4002) == 0 )
    goto LABEL_239;
  v115 = 56;
  v114 = 0;
  v71 = 0;
  v126 = 0;
  v109 = 0;
  String = 0;
  v72 = 56;
  if ( *((_QWORD *)&FileInformation + 1) < 0x38u )
    v72 = DWORD2(FileInformation);
  v115 = v72;
  if ( !v72 )
    goto LABEL_239;
  EventA = CreateEventA(0, 1, 0, 0);
  if ( !EventA )
  {
    v18 = 0;
    goto LABEL_70;
  }
  v143 = 4;
  v76 = HIDWORD(v103);
  if ( !HIDWORD(v103) && !(_DWORD)v106 && (v102 & 1) == 0 )
  {
LABEL_201:
    v80 = v72;
    if ( (v102 & 1) != 0 )
      v80 = v71;
    v81 = NtCopyFileChunk(FileHandle, hObject, EventA, &IoStatusBlock, v80, &v109, &String, 0, 0, v102);
    if ( v81 == 259 )
      v81 = NtWaitForSingleObject(EventA, 0, 0);
    if ( v81 >= 0 )
      goto LABEL_276;
    v82 = v102;
    if ( (v102 & 1) != 0 )
    {
      LODWORD(v102) = v102 & 0xFFFFFFFE;
      v81 = NtCopyFileChunk(FileHandle, hObject, EventA, &IoStatusBlock, v72, &v109, &String, 0, 0, v82 & 0xFFFFFFFE);
      if ( v81 == 259 )
        v81 = NtWaitForSingleObject(EventA, 0, 0);
    }
    if ( v81 < 0 )
    {
      BaseMarkFileForDelete(hObject);
      v18 = 0;
      BaseSetLastNTError((unsigned int)v81);
    }
    else
    {
LABEL_276:
      if ( *((_QWORD *)&FileInformation + 1) < 0x38u )
      {
        *(_QWORD *)&OutputBuffer = *((_QWORD *)&FileInformation + 1);
        if ( NtSetInformationFile(hObject, &IoStatusBlock, &OutputBuffer, 8u, FileEndOfFileInformation) < 0 )
          BaseMarkFileForDelete(hObject);
      }
      v18 = 1;
      if ( (a8 & 0x20000000) != 0 )
      {
        String2 = 0;
        OutputBuffer = 0;
        InputBuffer[0] = 0;
        InputBuffer[1] = *((_QWORD *)&FileInformation + 1);
        Status = NtFsControlFile(
                   hObject,
                   EventA,
                   0,
                   0,
                   &IoStatusBlock,
                   0x940CFu,
                   InputBuffer,
                   0x10u,
                   &OutputBuffer,
                   0x10u);
        if ( Status == 259 )
        {
          Status = NtWaitForSingleObject(EventA, 1u, 0);
          if ( Status >= 0 )
            Status = IoStatusBlock.Status;
        }
        if ( Status < 0 && Status != -1073741789 && Status != -2147483643 )
          goto LABEL_220;
        Status = NtFsControlFile(
                   FileHandle,
                   EventA,
                   0,
                   0,
                   &IoStatusBlock,
                   0x940CFu,
                   InputBuffer,
                   0x10u,
                   &String2,
                   0x10u);
        if ( Status == 259 )
        {
          Status = NtWaitForSingleObject(EventA, 1u, 0);
          if ( Status >= 0 )
            Status = IoStatusBlock.Status;
        }
        if ( Status < 0 )
        {
          if ( Status != -1073741789 && Status != -2147483643 )
          {
LABEL_220:
            BaseSetLastNTError((unsigned int)Status);
            v18 = 0;
            BaseMarkFileForDelete(hObject);
            goto LABEL_43;
          }
          v18 = 1;
        }
        if ( *(_QWORD *)&String2.Length != (_QWORD)OutputBuffer || !IoStatusBlock.Information )
        {
          v164 = 0;
          v84 = *((_QWORD *)&FileInformation + 1);
          if ( IoStatusBlock.Information )
            v84 = *(_QWORD *)&String2.Length;
          *((_QWORD *)&v164 + 1) = v84;
          Status = NtFsControlFile(hObject, EventA, 0, 0, &IoStatusBlock, 0x980C8u, &v164, 0x10u, 0, 0);
          if ( Status == 259 )
          {
            Status = NtWaitForSingleObject(EventA, 1u, 0);
            if ( Status >= 0 )
              Status = IoStatusBlock.Status;
          }
          if ( Status < 0 )
            goto LABEL_220;
        }
      }
    }
    CloseHandle(EventA);
LABEL_239:
    if ( !v18 )
      goto LABEL_43;
    if ( (_DWORD)v117 != -1 )
    {
      memset(&Overlapped, 0, sizeof(Overlapped));
      BytesReturned = 0;
      InBuffer = 0;
      Overlapped.hEvent = CreateEventA(0, 1, 0, 0);
      if ( Overlapped.hEvent )
      {
        if ( !DeviceIoControl(hObject, 0x900C4u, 0, 0, 0, 0, &BytesReturned, &Overlapped)
          && NtCurrentTeb()->LastErrorValue == 997 )
        {
          GetOverlappedResult(hObject, &Overlapped, &BytesReturned, 1);
        }
        ResetEvent(&Overlapped.hEvent);
        *((_QWORD *)&InBuffer + 1) = *((_QWORD *)&FileInformation + 1);
        if ( !DeviceIoControl(hObject, 0x980C8u, &InBuffer, 0x10u, 0, 0, &BytesReturned, &Overlapped)
          && NtCurrentTeb()->LastErrorValue == 997 )
        {
          GetOverlappedResult(hObject, &Overlapped, &BytesReturned, 1);
        }
        CloseHandle(Overlapped.hEvent);
      }
    }
    v143 = 4;
    if ( NtSetInformationFile(hObject, &IoStatusBlock, &v161, 0x28u, FileBasicInformation) == -1073741757 )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
      v85 = 128;
      v97 = 128;
      if ( HIDWORD(v102) )
        v85 = 2097280;
      v97 = v85;
      FileW = CreateFileW(lpFileName, 0x100u, 0, 0, 3u, v85 | (unsigned int)v108, 0);
      hObject = FileW;
      if ( FileW != (HANDLE)-1LL )
        NtSetInformationFile(FileW, &IoStatusBlock, &v161, 0x28u, FileBasicInformation);
    }
    memset_0(v167, 0, 0x74u);
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    if ( GetFileInformationByHandleEx(hObject, FileRemoteProtocolInfo, v167, 0x74u) )
    {
      if ( v168 == 3014656 )
      {
        v88 = NtFsControlFile(hObject, 0, 0, 0, &IoStatusBlock, 0x400007Fu, 0, 0, 0, 0);
        if ( v88 < 0 )
        {
          BaseMarkFileForDelete(hObject);
          v18 = 0;
          BaseSetLastNTError((unsigned int)v88);
        }
      }
    }
    if ( !v18 )
      goto LABEL_43;
    v36 = LastErrorValue;
LABEL_260:
    RtlSetLastWin32Error(v36);
    goto LABEL_43;
  }
  InBuffer = 0;
  v155 = 0;
  v18 = 0;
  LastStatusValue = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &InBuffer, 0x18u, FileFsSizeInformation);
  if ( LastStatusValue >= 0 )
  {
    v77 = HIDWORD(v155);
    v114 = HIDWORD(v155);
    v71 = HIDWORD(v155) * v155;
    v126 = HIDWORD(v155) * v155;
    v78 = v106;
    if ( (_DWORD)v106 )
    {
      v79 = NtQueryVolumeInformationFile(hObject, &IoStatusBlock, &InBuffer, 0x18u, FileFsSizeInformation);
      if ( v79 < 0 )
      {
        CloseHandle(EventA);
        v37 = (unsigned int)v79;
        goto LABEL_42;
      }
      if ( HIDWORD(v155) > v77 )
        v77 = HIDWORD(v155);
      v114 = v77;
      v78 = v106;
    }
    if ( v76 || v78 )
    {
      v72 = v77;
      v115 = v77;
    }
    goto LABEL_201;
  }
  CloseHandle(EventA);
LABEL_70:
  v37 = (unsigned int)LastStatusValue;
LABEL_42:
  BaseSetLastNTError(v37);
LABEL_43:
  v38 = P;
LABEL_262:
  if ( !v18 && v99 && NtCurrentTeb()->LastErrorValue != 1235 && NtCurrentTeb()->LastErrorValue != 3050 )
  {
    v89 = NtCurrentTeb()->LastErrorValue;
    *(_DWORD *)(v99 + 92) = v89;
    *(_DWORD *)(v99 + 24) = v89;
    BasepCopyFileCallback(6);
  }
  *v136 = FileHandle;
  *v137 = hObject;
  RtlSetCurrentTransaction(0);
  if ( v38 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v38);
  if ( v131[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v131[1]);
  return v18;
}

```

## disassembly

```asm
0x1800f9650  mov     r11, rsp
0x1800f9653  push    rbx
0x1800f9654  push    rsi
0x1800f9655  push    rdi
0x1800f9656  push    r12
0x1800f9658  push    r13
0x1800f965a  push    r14
0x1800f965c  push    r15
0x1800f965e  sub     rsp, 6B0h
0x1800f9665  mov     rax, cs:__security_cookie
0x1800f966c  xor     rax, rsp
0x1800f966f  mov     [rsp+6E8h+var_48], rax
0x1800f9677  mov     r12, r9
0x1800f967a  mov     qword ptr [rsp+6E8h+OutputBuffer], r8
0x1800f9682  mov     [rsp+6E8h+lpFileName], rdx
0x1800f968a  mov     [rsp+6E8h+String], rcx
0x1800f9692  mov     rsi, [rsp+6E8h+arg_78]
0x1800f969a  mov     r14, [rsp+6E8h+arg_20]
0x1800f96a2  mov     r15, [rsp+6E8h+arg_28]
0x1800f96aa  mov     r13, [rsp+6E8h+arg_30]
0x1800f96b2  mov     rax, [rsp+6E8h+arg_48]
0x1800f96ba  mov     [rsp+6E8h+var_4B0], rax
0x1800f96c2  mov     [rsp+6E8h+var_4A0], rax
0x1800f96ca  mov     rax, [rsp+6E8h+arg_50]
0x1800f96d2  mov     [rsp+6E8h+var_4A8], rax
0x1800f96da  mov     [rsp+6E8h+var_498], rax
0x1800f96e2  mov     rax, [rsp+6E8h+arg_58]
0x1800f96ea  mov     [rsp+6E8h+var_5C0], rax
0x1800f96f2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f96f6  mov     [r11-628h], rax
0x1800f96fd  mov     [r11-630h], rax
0x1800f9704  xor     edi, edi
0x1800f9706  mov     dword ptr [rsp+6E8h+var_5DC], edi
0x1800f970d  mov     dword ptr [rsp+6E8h+var_5F8], edi
0x1800f9714  mov     dword ptr [rsp+6E8h+var_5DC+4], edi
0x1800f971b  mov     dword ptr [rsp+6E8h+var_600+4], edi
0x1800f9722  mov     dword ptr [rsp+6E8h+var_5A8], edi
0x1800f9729  xor     eax, eax
0x1800f972b  xorps   xmm0, xmm0
0x1800f972e  movups  xmmword ptr [rsp+6E8h+ObjectAttributes.Length], xmm0
0x1800f9736  movups  xmmword ptr [rsp+6E8h+ObjectAttributes.ObjectName], xmm0
0x1800f973e  movups  xmmword ptr [rsp+6E8h+ObjectAttributes+1Ch], xmm0
0x1800f9746  movups  xmmword ptr [rsp+6E8h+IoStatusBlock], xmm0
0x1800f974e  xorps   xmm1, xmm1
0x1800f9751  movups  [rsp+6E8h+FileInformation], xmm1
0x1800f9759  mov     [r11-3A8h], rax
0x1800f9760  movups  [rsp+6E8h+var_340], xmm0
0x1800f9768  movups  [rsp+6E8h+var_330], xmm0
0x1800f9770  mov     [r11-320h], rax
0x1800f9777  mov     [r11-548h], rdi
0x1800f977e  movups  xmmword ptr [rsp+6E8h+var_570], xmm0
0x1800f9786  movups  xmmword ptr [rsp+6E8h+var_530], xmm1
0x1800f978e  mov     [r11-588h], rdi
0x1800f9795  mov     [r11-578h], rdi
0x1800f979c  mov     [rsp+6E8h+var_534], edi
0x1800f97a3  xor     edx, edx; Val
0x1800f97a5  mov     r8d, 0A8h; Size
0x1800f97ab  lea     rcx, [r11-488h]; void *
0x1800f97b2  call    memset_0
0x1800f97b7  mov     [rsp+6E8h+var_610], rdi
0x1800f97bf  xorps   xmm0, xmm0
0x1800f97c2  xor     eax, eax
0x1800f97c4  movups  xmmword ptr [rsp+6E8h+var_388], xmm0
0x1800f97cc  movups  [rsp+6E8h+var_378], xmm0
0x1800f97d4  movups  [rsp+6E8h+var_368], xmm0
0x1800f97dc  mov     [rsp+6E8h+var_358], rax
0x1800f97e4  mov     [rsp+6E8h+var_5B0], edi
0x1800f97eb  or      eax, 0FFFFFFFFh
0x1800f97ee  mov     dword ptr [rsp+6E8h+var_590], eax
0x1800f97f5  mov     qword ptr [rsp+6E8h+var_540], rdi
0x1800f97fd  lea     r8d, [rdi+1]
0x1800f9801  mov     dword ptr [rsp+6E8h+var_5F8+4], r8d
0x1800f9809  movups  [rsp+6E8h+var_4F0], xmm0
0x1800f9811  movups  [rsp+6E8h+var_4E0], xmm0
0x1800f9819  xorps   xmm1, xmm1
0x1800f981c  movups  [rsp+6E8h+var_308], xmm1
0x1800f9824  movups  [rsp+6E8h+var_2F8], xmm1
0x1800f982c  mov     dword ptr [rsp+6E8h+var_600], edi
0x1800f9833  mov     ecx, dword ptr [rsp+6E8h+arg_38]
0x1800f983a  test    ecx, 411B0770h
0x1800f9840  jnz     loc_1800FB75D
0x1800f9846  test    [rsp+6E8h+arg_40], 0FEC4780Fh
0x1800f9851  jnz     loc_1800FB75D
0x1800f9857  mov     ebx, [rsp+6E8h+arg_60]
0x1800f985e  test    ebx, 0FFFFFFFCh
0x1800f9864  jnz     loc_1800FB75D
0x1800f986a  mov     edx, cs:Feature_BlockCloningInCopy_Enabled
0x1800f9870  cmp     edx, eax
0x1800f9872  jnz     loc_1800F98F9
0x1800f9878  mov     [rsp+6E8h+var_5C8], rdi
0x1800f9880  mov     ecx, cs:Feature_BlockCloningInCopy__private_featureState
0x1800f9886  mov     dword ptr [rsp+6E8h+var_5C8], ecx
0x1800f988d  test    cl, 10h
0x1800f9890  jnz     short loc_1800F98E6
0x1800f9892  mov     rax, [rsp+6E8h+var_5C8]
0x1800f989a  mov     [rsp+6E8h+var_5C8], rax
0x1800f98a2  or      ecx, r8d
0x1800f98a5  mov     dword ptr [rsp+6E8h+var_5C8], ecx
0x1800f98ac  mov     r9d, r8d
0x1800f98af  lea     edi, [r8+2]
0x1800f98b3  mov     r8d, edi
0x1800f98b6  mov     rdx, [rsp+6E8h+var_5C8]
0x1800f98be  lea     rcx, Feature_BlockCloningInCopy__private_descriptor
0x1800f98c5  call    wil_details_FeatureReporting_ReportUsageToService
0x1800f98ca  lea     r8, Feature_BlockCloningInCopy__private_descriptor
0x1800f98d1  mov     edx, edi
0x1800f98d3  mov     rcx, [rsp+6E8h+var_5C8]
0x1800f98db  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1800f98e0  xor     edi, edi
0x1800f98e2  lea     r8d, [rdi+1]
0x1800f98e6  mov     cs:Feature_BlockCloningInCopy_Enabled, r8d
0x1800f98ed  mov     eax, r8d
0x1800f98f0  mov     ecx, dword ptr [rsp+6E8h+arg_38]
0x1800f98f7  jmp     short loc_1800F9901
0x1800f98f9  mov     eax, edi
0x1800f98fb  cmp     edx, r8d
0x1800f98fe  setz    al
0x1800f9901  mov     edx, ebx
0x1800f9903  or      edx, 2
0x1800f9906  test    eax, eax
0x1800f9908  cmovnz  edx, ebx
0x1800f990b  mov     [rsp+6E8h+BytesReturned], edx
0x1800f9912  mov     eax, [rsp+6E8h+arg_70]
0x1800f9919  dec     eax
0x1800f991b  cmp     eax, 1FEh
0x1800f9920  jbe     loc_1800FB75D
0x1800f9926  mov     eax, [rsp+6E8h+arg_68]
0x1800f992d  test    eax, eax
0x1800f992f  jz      short loc_1800F9941
0x1800f9931  add     eax, 0FFFFF000h
0x1800f9936  cmp     eax, 3FFFF000h
0x1800f993b  ja      loc_1800FB75D
0x1800f9941  mov     eax, ecx
0x1800f9943  mov     edx, 4002h
0x1800f9948  and     eax, edx
0x1800f994a  cmp     eax, edx
0x1800f994c  jz      loc_1800FB75D
0x1800f9952  or      ecx, [rsp+6E8h+arg_40]
0x1800f9959  mov     dword ptr [rsp+6E8h+arg_38], ecx
0x1800f9960  call    cs:__imp_RtlGetCurrentTransaction
0x1800f9967  nop     dword ptr [rax+rax+00h]
0x1800f996c  test    rax, rax
0x1800f996f  jz      short loc_1800F9987
0x1800f9971  mov     ecx, 1A45h; LastError
0x1800f9976  call    cs:__imp_RtlSetLastWin32Error
0x1800f997d  nop     dword ptr [rax+rax+00h]
0x1800f9982  jmp     loc_1800FB767
0x1800f9987  lea     rax, [rsp+6E8h+var_5F8+4]
0x1800f998f  mov     qword ptr [rsp+6E8h+CreateOptions], rax
0x1800f9994  call    BasepCloudFileCopy
0x1800f9999  test    eax, eax
0x1800f999b  jz      loc_1800FB769
0x1800f99a1  cmp     dword ptr [rsp+6E8h+var_5F8+4], edi
0x1800f99a8  jz      loc_1800FB769
0x1800f99ae  mov     ebx, edi
0x1800f99b0  mov     [rsp+6E8h+var_634], edi
0x1800f99b7  xor     edx, edx
0x1800f99b9  mov     [rsp+6E8h+P], rdx
0x1800f99c1  mov     qword ptr [rsp+6E8h+var_4F0+8], rdx
0x1800f99c9  mov     dword ptr [rsp+6E8h+var_4E0], edx
0x1800f99d0  mov     qword ptr [rsp+6E8h+var_4F0], 1
0x1800f99dc  test    rsi, rsi
0x1800f99df  jz      short loc_1800F9A0A
0x1800f99e1  movups  xmm0, xmmword ptr [rsi]
0x1800f99e4  movdqu  [rsp+6E8h+var_308], xmm0
0x1800f99ed  movups  xmm1, xmmword ptr [rsi+10h]
0x1800f99f1  movdqu  [rsp+6E8h+var_2F8], xmm1
0x1800f99fa  lea     rax, [rsp+6E8h+var_308]
0x1800f9a02  mov     qword ptr [rsp+6E8h+var_4E0+8], rax
0x1800f9a0a  mov     rcx, qword ptr [rsp+6E8h+OutputBuffer]
0x1800f9a12  test    rcx, rcx
0x1800f9a15  jnz     short loc_1800F9A21
0x1800f9a17  test    r14, r14
0x1800f9a1a  jnz     short loc_1800F9A21
0x1800f9a1c  test    r15, r15
0x1800f9a1f  jz      short loc_1800F9A8B
0x1800f9a21  mov     [rsp+6E8h+var_480], rdx
0x1800f9a29  mov     [rsp+6E8h+var_478], edx
0x1800f9a30  lea     rax, [rsp+6E8h+var_534]
0x1800f9a38  test    r14, r14
0x1800f9a3b  cmovnz  rax, r14
0x1800f9a3f  mov     [rsp+6E8h+var_418], rax
0x1800f9a47  mov     [rsp+6E8h+var_410], r12
0x1800f9a4f  mov     [rsp+6E8h+var_408], r15
0x1800f9a57  mov     [rsp+6E8h+var_400], r13
0x1800f9a5f  test    rcx, rcx
0x1800f9a62  jz      short loc_1800F9A7B
0x1800f9a64  mov     rax, [rcx]
0x1800f9a67  mov     [rsp+6E8h+var_3F8], rax
0x1800f9a6f  mov     rax, [rcx+8]
0x1800f9a73  mov     [rsp+6E8h+var_3F0], rax
0x1800f9a7b  lea     rax, [rsp+6E8h+var_488]
0x1800f9a83  mov     [rsp+6E8h+var_610], rax
0x1800f9a8b  mov     rcx, [rsp+6E8h+var_5C0]
0x1800f9a93  call    cs:__imp_RtlSetCurrentTransaction
0x1800f9a9a  nop     dword ptr [rax+rax+00h]
0x1800f9a9f  mov     eax, 1
0x1800f9aa4  mov     [rsp+6E8h+var_458], eax
0x1800f9aab  mov     r8d, dword ptr [rsp+6E8h+arg_38]
0x1800f9ab3  mov     esi, 1000h
0x1800f9ab8  test    esi, r8d
0x1800f9abb  jnz     short loc_1800F9ADE
0x1800f9abd  call    BasepCopyCheckNoBuffering
0x1800f9ac2  mov     r8d, dword ptr [rsp+6E8h+arg_38]
0x1800f9aca  test    eax, eax
0x1800f9acc  mov     eax, 1
0x1800f9ad1  jz      short loc_1800F9ADE
0x1800f9ad3  or      r8d, esi
0x1800f9ad6  mov     dword ptr [rsp+6E8h+arg_38], r8d
0x1800f9ade  test    r8b, 2
0x1800f9ae2  jz      short loc_1800F9AF3
0x1800f9ae4  and     r8d, 0FFFEEFFFh
0x1800f9aeb  mov     dword ptr [rsp+6E8h+arg_38], r8d
0x1800f9af3  test    esi, r8d
0x1800f9af6  cmovnz  ebx, eax
0x1800f9af9  mov     dword ptr [rsp+6E8h+var_5F8+4], ebx
0x1800f9b00  mov     [rsp+6E8h+var_55C], ebx
0x1800f9b07  mov     r9d, r8d
0x1800f9b0a  and     r9d, 180h
0x1800f9b11  mov     dword ptr [rsp+6E8h+var_5C0], r9d
0x1800f9b19  mov     eax, r9d
0x1800f9b1c  neg     eax
0x1800f9b1e  sbb     ecx, ecx
0x1800f9b20  and     ecx, 4000h
0x1800f9b26  mov     dword ptr [rsp+6E8h+var_5C8], ecx
0x1800f9b2d  mov     eax, r8d
0x1800f9b30  and     eax, 2020h
0x1800f9b35  neg     eax
0x1800f9b37  sbb     r13d, r13d
0x1800f9b3a  and     r13d, 1000000h
0x1800f9b41  mov     eax, r8d
0x1800f9b44  and     eax, 0FFFFFFFCh
0x1800f9b47  or      eax, 0FFFFFFF8h
0x1800f9b4a  shl     eax, 1Ch
0x1800f9b4d  or      r13d, eax
0x1800f9b50  mov     [rsp+6E8h+var_618], 10000000h
0x1800f9b5b  or      ecx, 10200004h
0x1800f9b61  mov     [rsp+6E8h+var_618], ecx
0x1800f9b68  mov     eax, ebx
0x1800f9b6a  neg     eax
0x1800f9b6c  sbb     edx, edx
0x1800f9b6e  and     edx, 8
0x1800f9b71  or      edx, ecx
0x1800f9b73  mov     [rsp+6E8h+var_618], edx
0x1800f9b7a  mov     eax, r9d
0x1800f9b7d  neg     eax
0x1800f9b7f  sbb     r14d, r14d
0x1800f9b82  not     r14d
0x1800f9b85  and     r14d, 40h
0x1800f9b89  or      r14d, edx
0x1800f9b8c  mov     [rsp+6E8h+var_618], r14d
0x1800f9b94  mov     [rsp+6E8h+var_5B4], 0
0x1800f9b9f  mov     eax, 5
0x1800f9ba4  mov     [rsp+6E8h+var_560], eax
0x1800f9bab  bt      r8d, 11h
0x1800f9bb0  mov     r12d, eax
0x1800f9bb3  lea     eax, [r12+2]
0x1800f9bb8  cmovb   r12d, eax
0x1800f9bbc  mov     [rsp+6E8h+var_558], r12d
0x1800f9bc4  mov     [rsp+6E8h+var_560], r12d
0x1800f9bcc  xor     r9d, r9d
0x1800f9bcf  xor     r8d, r8d
0x1800f9bd2  lea     rdx, [rsp+6E8h+var_530]
0x1800f9bda  mov     rcx, [rsp+6E8h+String]
0x1800f9be2  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800f9be9  nop     dword ptr [rax+rax+00h]
0x1800f9bee  mov     [rsp+6E8h+var_638], eax
0x1800f9bf5  test    eax, eax
0x1800f9bf7  jns     short loc_1800F9C25
0x1800f9bf9  cmp     eax, 0C0000017h
0x1800f9bfe  jz      short loc_1800F9C11
0x1800f9c00  cmp     eax, 0C000009Ah
0x1800f9c05  jz      short loc_1800F9C11
0x1800f9c07  mov     ecx, 3
0x1800f9c0c  jmp     loc_1800FB65D
0x1800f9c11  mov     ecx, eax
0x1800f9c13  call    BaseSetLastNTError
0x1800f9c18  mov     rsi, [rsp+6E8h+P]
0x1800f9c20  jmp     loc_1800FB679
0x1800f9c25  mov     r15d, r13d
0x1800f9c28  mov     [rsp+6E8h+var_5E0], r13d
0x1800f9c30  mov     ebx, r12d
0x1800f9c33  mov     [rsp+6E8h+var_5B8], ebx
0x1800f9c3a  mov     [rsp+6E8h+ObjectAttributes.Length], 30h ; '0'
0x1800f9c45  mov     [rsp+6E8h+ObjectAttributes.RootDirectory], 0
0x1800f9c51  mov     [rsp+6E8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f9c5c  lea     rax, [rsp+6E8h+var_530]
0x1800f9c64  mov     [rsp+6E8h+ObjectAttributes.ObjectName], rax
0x1800f9c6c  xorps   xmm0, xmm0
0x1800f9c6f  movdqu  xmmword ptr [rsp+6E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f9c78  mov     edx, r15d
0x1800f9c7b  or      edx, 100080h; DesiredAccess
0x1800f9c81  mov     [rsp+6E8h+EaLength], 20h ; ' '; EaLength
0x1800f9c89  lea     rax, [rsp+6E8h+var_4F0]
0x1800f9c91  mov     [rsp+6E8h+EaBuffer], rax; EaBuffer
0x1800f9c96  mov     [rsp+6E8h+CreateOptions], r14d; CreateOptions
0x1800f9c9b  mov     [rsp+6E8h+CreateDisposition], 1; CreateDisposition
0x1800f9ca3  mov     [rsp+6E8h+ShareAccess], ebx; ShareAccess
0x1800f9ca7  mov     [rsp+6E8h+FileAttributes], 0; FileAttributes
0x1800f9caf  mov     [rsp+6E8h+AllocationSize], 0; AllocationSize
  ... truncated ...
```
