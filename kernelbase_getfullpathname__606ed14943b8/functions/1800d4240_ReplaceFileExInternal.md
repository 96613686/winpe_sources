# ReplaceFileExInternal

- ea: `0x1800d4240`
- end: `0x1800d5ae0`
- name: `ReplaceFileExInternal`
- size: `6304`
- prototype: `__int64 __usercall@<rax>(PCWSTR DosPathName@<rcx>, PCWSTR@<rdx>, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d41e0`

## callees

- `0x18004b9d0`
- `0x18004c490`
- `0x180053330`
- `0x180053c30`
- `0x1800d3eb0`
- `0x1800d3ee8`
- `0x1800d4240`
- `0x1800d5ae8`
- `0x1800d60d8`
- `0x1800d6a90`
- `0x1800d6e60`
- `0x18011a130`
- `0x1801369c9`
- `0x1801373a0`
- `0x18013877c`
- `0x180194eb9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800d435c`
- `ntdll!RtlInitUnicodeString` at `0x1800d43fe`
- `ntdll!RtlInitUnicodeString` at `0x1800d435c`
- `ntdll!RtlInitUnicodeString` at `0x1800d43fe`
- `ntdll!NtQueryInformationFile` at `0x1800d46db`
- `ntdll!NtQueryInformationFile` at `0x1800d4aa5`
- `ntdll!NtQueryInformationFile` at `0x1800d5457`
- `ntdll!NtQueryInformationFile` at `0x1800d46db`
- `ntdll!NtQueryInformationFile` at `0x1800d4aa5`
- `ntdll!NtQueryInformationFile` at `0x1800d5457`
- `ntdll!NtOpenFile` at `0x1800d44b5`
- `ntdll!NtOpenFile` at `0x1800d4506`
- `ntdll!NtOpenFile` at `0x1800d4551`
- `ntdll!NtOpenFile` at `0x1800d4637`
- `ntdll!NtOpenFile` at `0x1800d4678`
- `ntdll!NtOpenFile` at `0x1800d4fdf`
- `ntdll!NtOpenFile` at `0x1800d54cb`
- `ntdll!NtOpenFile` at `0x1800d552e`
- `ntdll!NtOpenFile` at `0x1800d556f`
- `ntdll!NtOpenFile` at `0x1800d55bf`
- `ntdll!NtOpenFile` at `0x1800d5677`
- `ntdll!NtOpenFile` at `0x1800d56b8`
- `ntdll!NtOpenFile` at `0x1800d5707`
- `ntdll!NtOpenFile` at `0x1800d44b5`
- `ntdll!NtOpenFile` at `0x1800d4506`
- `ntdll!NtOpenFile` at `0x1800d4551`
- `ntdll!NtOpenFile` at `0x1800d4637`
- `ntdll!NtOpenFile` at `0x1800d4678`
- `ntdll!NtOpenFile` at `0x1800d4fdf`
- `ntdll!NtOpenFile` at `0x1800d54cb`
- `ntdll!NtOpenFile` at `0x1800d552e`
- `ntdll!NtOpenFile` at `0x1800d556f`
- `ntdll!NtOpenFile` at `0x1800d55bf`
- `ntdll!NtOpenFile` at `0x1800d5677`
- `ntdll!NtOpenFile` at `0x1800d56b8`
- `ntdll!NtOpenFile` at `0x1800d5707`
- `ntdll!wcslen` at `0x1800d484c`
- `ntdll!wcslen` at `0x1800d4c3c`
- `ntdll!wcslen` at `0x1800d484c`
- `ntdll!wcslen` at `0x1800d4c3c`
- `ntdll!NtSetInformationFile` at `0x1800d4af4`
- `ntdll!NtSetInformationFile` at `0x1800d4de5`
- `ntdll!NtSetInformationFile` at `0x1800d4e8d`
- `ntdll!NtSetInformationFile` at `0x1800d4f21`
- `ntdll!NtSetInformationFile` at `0x1800d505f`
- `ntdll!NtSetInformationFile` at `0x1800d5233`
- `ntdll!NtSetInformationFile` at `0x1800d5273`
- `ntdll!NtSetInformationFile` at `0x1800d52b3`
- `ntdll!NtSetInformationFile` at `0x1800d52fe`
- `ntdll!NtSetInformationFile` at `0x1800d4af4`
- `ntdll!NtSetInformationFile` at `0x1800d4de5`
- `ntdll!NtSetInformationFile` at `0x1800d4e8d`
- `ntdll!NtSetInformationFile` at `0x1800d4f21`
- `ntdll!NtSetInformationFile` at `0x1800d505f`
- `ntdll!NtSetInformationFile` at `0x1800d5233`
- `ntdll!NtSetInformationFile` at `0x1800d5273`
- `ntdll!NtSetInformationFile` at `0x1800d52b3`
- `ntdll!NtSetInformationFile` at `0x1800d52fe`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800d441b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800d457a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800d4cf5`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800d441b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800d457a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800d4cf5`
- `ntdll!wcscpy_s` at `0x1800d4907`
- `ntdll!wcscpy_s` at `0x1800d5183`
- `ntdll!wcscpy_s` at `0x1800d51a0`
- `ntdll!wcscpy_s` at `0x1800d4907`
- `ntdll!wcscpy_s` at `0x1800d5183`
- `ntdll!wcscpy_s` at `0x1800d51a0`
- `ntdll!wcscat_s` at `0x1800d4921`
- `ntdll!wcscat_s` at `0x1800d4921`
- `ntdll!swprintf_s` at `0x1800d48e5`
- `ntdll!swprintf_s` at `0x1800d5164`
- `ntdll!swprintf_s` at `0x1800d48e5`
- `ntdll!swprintf_s` at `0x1800d5164`
- `ntdll!NtFsControlFile` at `0x1800d4bf1`
- `ntdll!NtFsControlFile` at `0x1800d536f`
- `ntdll!NtFsControlFile` at `0x1800d53ef`
- `ntdll!NtFsControlFile` at `0x1800d585c`
- `ntdll!NtFsControlFile` at `0x1800d5abd`
- `ntdll!NtFsControlFile` at `0x180197a26`
- `ntdll!NtFsControlFile` at `0x180197ba9`
- `ntdll!NtFsControlFile` at `0x1800d4bf1`
- `ntdll!NtFsControlFile` at `0x1800d536f`
- `ntdll!NtFsControlFile` at `0x1800d53ef`
- `ntdll!NtFsControlFile` at `0x1800d585c`
- `ntdll!NtFsControlFile` at `0x1800d5abd`
- `ntdll!NtFsControlFile` at `0x180197a26`
- `ntdll!NtFsControlFile` at `0x180197ba9`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d4725`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800d4725`
- `ntdll!RtlSetLastWin32Error` at `0x1800d5095`
- `ntdll!RtlSetLastWin32Error` at `0x1800d50d0`
- `ntdll!RtlSetLastWin32Error` at `0x1800d511b`
- `ntdll!RtlSetLastWin32Error` at `0x1800d5411`
- `ntdll!RtlSetLastWin32Error` at `0x1800d5636`
- `ntdll!RtlSetLastWin32Error` at `0x1800d573e`
- `ntdll!RtlSetLastWin32Error` at `0x1800d57d4`
- `ntdll!RtlSetLastWin32Error` at `0x1800d59ef`
- `ntdll!RtlSetLastWin32Error` at `0x1800d5a1f`
- `ntdll!RtlSetLastWin32Error` at `0x1801979a9`
- `ntdll!RtlSetLastWin32Error` at `0x1800d5095`
- `ntdll!RtlSetLastWin32Error` at `0x1800d50d0`
- `ntdll!RtlSetLastWin32Error` at `0x1800d511b`
- `ntdll!RtlSetLastWin32Error` at `0x1800d5411`
- `ntdll!RtlSetLastWin32Error` at `0x1800d5636`
- `ntdll!RtlSetLastWin32Error` at `0x1800d573e`
- `ntdll!RtlSetLastWin32Error` at `0x1800d57d4`
- `ntdll!RtlSetLastWin32Error` at `0x1800d59ef`
- `ntdll!RtlSetLastWin32Error` at `0x1800d5a1f`
- `ntdll!RtlSetLastWin32Error` at `0x1801979a9`
- `ntdll!NtClose` at `0x1800d4f5a`
- `ntdll!NtClose` at `0x1800d5488`
- `ntdll!NtClose` at `0x1800d5806`
- `ntdll!NtClose` at `0x1800d586d`
- `ntdll!NtClose` at `0x1801979c3`
- `ntdll!NtClose` at `0x180197a36`
- `ntdll!NtClose` at `0x1800d4f5a`
- `ntdll!NtClose` at `0x1800d5488`
- `ntdll!NtClose` at `0x1800d5806`
- `ntdll!NtClose` at `0x1800d586d`
- `ntdll!NtClose` at `0x1801979c3`
- `ntdll!NtClose` at `0x180197a36`
- `ntdll!NtDuplicateObject` at `0x1800d49d4`
- `ntdll!NtDuplicateObject` at `0x1800d49d4`
- `ntdll!RtlFreeHeap` at `0x1800d5890`
- `ntdll!RtlFreeHeap` at `0x1800d58b3`
- `ntdll!RtlFreeHeap` at `0x1800d58d6`
- `ntdll!RtlFreeHeap` at `0x1800d58f4`
- `ntdll!RtlFreeHeap` at `0x1800d5912`
- `ntdll!RtlFreeHeap` at `0x1800d598c`
- `ntdll!RtlFreeHeap` at `0x180197a59`
- `ntdll!RtlFreeHeap` at `0x180197a7b`
- `ntdll!RtlFreeHeap` at `0x180197a9d`
- `ntdll!RtlFreeHeap` at `0x180197abf`
- `ntdll!RtlFreeHeap` at `0x180197ae1`
- `ntdll!RtlFreeHeap` at `0x180197be1`
- `ntdll!RtlFreeHeap` at `0x1800d5890`
- `ntdll!RtlFreeHeap` at `0x1800d58b3`
- `ntdll!RtlFreeHeap` at `0x1800d58d6`
- `ntdll!RtlFreeHeap` at `0x1800d58f4`
- `ntdll!RtlFreeHeap` at `0x1800d5912`
- `ntdll!RtlFreeHeap` at `0x1800d598c`
- `ntdll!RtlFreeHeap` at `0x180197a59`
- `ntdll!RtlFreeHeap` at `0x180197a7b`
- `ntdll!RtlFreeHeap` at `0x180197a9d`
- `ntdll!RtlFreeHeap` at `0x180197abf`
- `ntdll!RtlFreeHeap` at `0x180197ae1`
- `ntdll!RtlFreeHeap` at `0x180197be1`
- `ntdll!RtlAllocateHeap` at `0x1800d488a`
- `ntdll!RtlAllocateHeap` at `0x1800d4d29`
- `ntdll!RtlAllocateHeap` at `0x1800d4d69`
- `ntdll!RtlAllocateHeap` at `0x1800d488a`
- `ntdll!RtlAllocateHeap` at `0x1800d4d29`
- `ntdll!RtlAllocateHeap` at `0x1800d4d69`
- `ext-ms-win-kernel32-file-l1-1-0!BasepSetFileEncryptionCompression` at `0x1800d4b73`
- `ext-ms-win-kernel32-file-l1-1-0!BasepSetFileEncryptionCompression` at `0x1800d4b73`

## pseudocode

```c
__int64 __fastcall ReplaceFileExInternal(
        wchar_t *DosPathName,
        PCWSTR a2,
        const WCHAR *a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  int v11; // esi
  WCHAR *v12; // r14
  int v13; // ebx
  _QWORD *v14; // r12
  int v15; // r13d
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  ACCESS_MASK v18; // r15d
  NTSTATUS v19; // eax
  int v20; // edi
  DWORD v21; // r14d
  __int64 v22; // rsi
  BOOL v23; // ebx
  int v24; // r15d
  int v25; // r13d
  __int64 FileW; // r14
  unsigned int v27; // esi
  int v28; // eax
  int v29; // edi
  unsigned int v30; // r13d
  unsigned __int64 v31; // rbx
  rsize_t v32; // rbx
  wchar_t *v33; // r14
  HANDLE StandardError; // rdx
  NTSTATUS v35; // eax
  int v36; // ecx
  bool v37; // zf
  int v38; // eax
  int v39; // eax
  unsigned int v40; // edi
  wchar_t *v41; // rbx
  __int16 v42; // dx
  __int16 i; // cx
  __int64 v44; // rax
  unsigned __int16 v45; // dx
  wchar_t *v46; // rsi
  int v47; // ebx
  unsigned __int64 v48; // r13
  _DWORD *Heap; // r15
  HANDLE v50; // rbx
  NTSTATUS v51; // eax
  HANDLE v52; // rbx
  NTSTATUS v53; // eax
  HANDLE v54; // r14
  NTSTATUS v55; // eax
  NTSTATUS v56; // ebx
  HANDLE v57; // r14
  NTSTATUS v58; // eax
  ULONG v59; // ecx
  int v60; // esi
  int v61; // eax
  ULONG v62; // ecx
  __int64 v63; // rcx
  ULONG LastErrorValue; // ebx
  HANDLE v66; // rbx
  __int64 ShareAccess; // [rsp+88h] [rbp-4C8h]
  __int64 OpenOptions; // [rsp+90h] [rbp-4C0h]
  unsigned int v69; // [rsp+C8h] [rbp-488h]
  int v70; // [rsp+CCh] [rbp-484h]
  HANDLE hDevice; // [rsp+D8h] [rbp-478h] BYREF
  wchar_t *Destination; // [rsp+E0h] [rbp-470h]
  HANDLE FileHandle; // [rsp+E8h] [rbp-468h] BYREF
  PVOID v74; // [rsp+F0h] [rbp-460h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-458h] BYREF
  int v76; // [rsp+108h] [rbp-448h]
  __int16 v77; // [rsp+10Ch] [rbp-444h]
  DWORD BytesReturned; // [rsp+110h] [rbp-440h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+118h] [rbp-438h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+128h] [rbp-428h]
  int v81; // [rsp+12Ch] [rbp-424h]
  unsigned int v82; // [rsp+130h] [rbp-420h]
  int v83; // [rsp+134h] [rbp-41Ch]
  int v84; // [rsp+138h] [rbp-418h]
  HANDLE TargetHandle; // [rsp+140h] [rbp-410h] BYREF
  wchar_t *String; // [rsp+148h] [rbp-408h]
  int v87; // [rsp+150h] [rbp-400h]
  struct _UNICODE_STRING DestinationString; // [rsp+158h] [rbp-3F8h] BYREF
  int v89[2]; // [rsp+168h] [rbp-3E8h]
  PVOID P; // [rsp+170h] [rbp-3E0h]
  PVOID v91; // [rsp+178h] [rbp-3D8h]
  int v92; // [rsp+180h] [rbp-3D0h]
  int v93; // [rsp+184h] [rbp-3CCh]
  __int64 OutputBuffer; // [rsp+188h] [rbp-3C8h] BYREF
  struct _OBJECT_ATTRIBUTES v95; // [rsp+190h] [rbp-3C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1C0h] [rbp-390h] BYREF
  _QWORD *v97; // [rsp+1F0h] [rbp-360h]
  __int64 v98; // [rsp+1F8h] [rbp-358h] BYREF
  PCWSTR DosPathNamea; // [rsp+200h] [rbp-350h]
  __int128 v100; // [rsp+208h] [rbp-348h] BYREF
  __int64 v101; // [rsp+218h] [rbp-338h]
  struct _UNICODE_STRING v102; // [rsp+220h] [rbp-330h] BYREF
  const WCHAR *v103; // [rsp+230h] [rbp-320h]
  int v104; // [rsp+238h] [rbp-318h]
  __int128 InputBuffer; // [rsp+240h] [rbp-310h] BYREF
  __int64 v106; // [rsp+250h] [rbp-300h]
  __int128 v107; // [rsp+258h] [rbp-2F8h] BYREF
  __int64 v108; // [rsp+268h] [rbp-2E8h]
  _OWORD FileInformation[2]; // [rsp+270h] [rbp-2E0h] BYREF
  int v110[2]; // [rsp+290h] [rbp-2C0h]
  _OWORD v111[2]; // [rsp+298h] [rbp-2B8h] BYREF
  __int64 v112; // [rsp+2B8h] [rbp-298h]
  char FsInformation[544]; // [rsp+2C8h] [rbp-288h] BYREF
  wchar_t Buffer[8]; // [rsp+4E8h] [rbp-68h] BYREF
  PVOID hTemplateFile; // [rsp+4F8h] [rbp-58h]

  DosPathNamea = a3;
  *(_QWORD *)v89 = a2;
  String = DosPathName;
  v103 = a3;
  FileHandle = (HANDLE)-1LL;
  hDevice = (HANDLE)-1LL;
  NtPathName = 0;
  v102 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&v95, 0, 44);
  IoStatusBlock = 0;
  v11 = 0;
  v69 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  *(_QWORD *)v110 = 0;
  memset(v111, 0, sizeof(v111));
  v112 = 0;
  v12 = 0;
  Destination = 0;
  v98 = 0;
  memset_0(FsInformation, 0, 0x218u);
  RtlInitUnicodeString(&DestinationString, 0);
  if ( !DosPathName )
    goto LABEL_175;
  if ( !a2 )
    goto LABEL_175;
  if ( a7 )
    goto LABEL_175;
  if ( a8 )
    goto LABEL_175;
  P = 0;
  v91 = 0;
  v13 = 0;
  v74 = 0;
  v14 = 0;
  v97 = 0;
  BytesReturned = 0;
  v81 = 0;
  v93 = 1;
  v84 = 0;
  v87 = 0;
  if ( (a4 & 0xFFFFFFF8) != 0 )
  {
LABEL_175:
    RtlSetLastWin32Error(0x57u);
    return v69;
  }
  RtlInitUnicodeString(&NtPathName, 0);
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
    goto LABEL_120;
  P = NtPathName.Buffer;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = 18022538;
  DesiredAccess = 18022538;
  if ( NtOpenFile(&FileHandle, 0x113008Au, &ObjectAttributes, &IoStatusBlock, 7u, 0x200060u) < 0 )
  {
    v15 = 1245322;
    DesiredAccess = 1245322;
    if ( NtOpenFile(&FileHandle, 0x13008Au, &ObjectAttributes, &IoStatusBlock, 7u, 0x200060u) < 0 )
    {
      v15 = 1245320;
      DesiredAccess = 1245320;
      v16 = NtOpenFile(&FileHandle, 0x130088u, &ObjectAttributes, &IoStatusBlock, 7u, 0x200060u);
      if ( v16 < 0 )
      {
        BaseSetLastNTError((unsigned int)v16);
        goto LABEL_98;
      }
    }
  }
  if ( !RtlDosPathNameToNtPathName_U(a2, &v102, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    goto LABEL_98;
  }
  LODWORD(TargetHandle) = v15 & 2;
  v91 = v102.Buffer;
  v95.Length = 48;
  v95.RootDirectory = 0;
  v95.Attributes = 64;
  v95.ObjectName = &v102;
  *(_OWORD *)&v95.SecurityDescriptor = 0;
  if ( (v15 & 0x1000000) != 0 )
  {
    v13 = -1055064064;
    v76 = -1055064064;
    v17 = NtOpenFile(&hDevice, 0xC11D0000, &v95, &IoStatusBlock, 0, 0x60u);
    if ( v17 < 0 )
    {
      v13 = -1055588352;
      v76 = -1055588352;
      v17 = NtOpenFile(&hDevice, 0xC1150000, &v95, &IoStatusBlock, 0, 0x60u);
    }
  }
  else
  {
    v17 = -1073741790;
  }
  if ( v17 < 0 )
  {
    v13 = -1071841280;
    v76 = -1071841280;
    v17 = NtOpenFile(&hDevice, 0xC01D0000, &v95, &IoStatusBlock, 0, 0x60u);
    if ( v17 < 0 )
    {
      v13 = -1072365568;
      v76 = -1072365568;
      v17 = NtOpenFile(&hDevice, 0xC0150000, &v95, &IoStatusBlock, 0, 0x60u);
    }
  }
  if ( v17 == -1073741790 )
  {
    if ( (a4 & 6) != 0 )
    {
      v13 = -1072627712;
      v76 = -1072627712;
      v17 = NtOpenFile(&hDevice, 0xC0110000, &v95, &IoStatusBlock, 0, 0x60u);
    }
    if ( v17 == -1073741790 )
    {
      if ( (a4 & 2) != 0 )
      {
        v13 = -2145583104;
        v76 = -2145583104;
        v17 = NtOpenFile(&hDevice, 0x801D0000, &v95, &IoStatusBlock, 0, 0x60u);
        if ( v17 < 0 )
        {
          v13 = -2146107392;
          v76 = -2146107392;
          v17 = NtOpenFile(&hDevice, 0x80150000, &v95, &IoStatusBlock, 0, 0x60u);
        }
      }
      if ( v17 == -1073741790 && (a4 & 2) != 0 )
      {
        v13 = -2146369536;
        v76 = -2146369536;
        v17 = NtOpenFile(&hDevice, 0x80110000, &v95, &IoStatusBlock, 0, 0x60u);
      }
    }
  }
  if ( v17 < 0 )
    goto LABEL_62;
  if ( a6 )
  {
    InputBuffer = 0;
    v106 = 0;
    LODWORD(InputBuffer) = a6;
    v19 = NtFsControlFile(hDevice, 0, 0, 0, &IoStatusBlock, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
    if ( v19 < 0 )
      goto LABEL_117;
  }
  v18 = DesiredAccess;
  while ( 1 )
  {
    v19 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    if ( v19 < 0 )
    {
      v20 = a4 & 2;
      if ( !v20 )
        goto LABEL_117;
      v21 = 1;
      goto LABEL_23;
    }
    if ( v11 || (v110[0] & 0x400) == 0 )
    {
      if ( a5 )
      {
        v107 = 0;
        v108 = 0;
        LODWORD(v107) = a5;
        v19 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900FCu, &v107, 0x18u, 0, 0);
        if ( v19 < 0 )
          goto LABEL_117;
      }
      if ( (v110[0] & 1) != 0 )
      {
        v63 = 3221225506LL;
LABEL_145:
        BaseSetLastNTError(v63);
        goto LABEL_97;
      }
      v19 = NtQueryInformationFile(hDevice, &IoStatusBlock, v111, 0x28u, FileBasicInformation);
      v20 = a4 & 2;
      if ( v19 < 0 )
      {
        if ( !v20 )
          goto LABEL_117;
        v81 = 1;
        v104 = 1;
      }
      memset((char *)FileInformation + 8, 0, 24);
      v19 = NtSetInformationFile(hDevice, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
      if ( v19 < 0 && !v20 )
      {
LABEL_117:
        v63 = (unsigned int)v19;
        goto LABEL_145;
      }
      v21 = BytesReturned;
LABEL_23:
      v19 = NtQueryVolumeInformationFile(hDevice, &IoStatusBlock, FsInformation, 0x218u, FileFsAttributeInformation);
      if ( v19 < 0 )
      {
        if ( !v20 )
          goto LABEL_117;
        v22 = *(_QWORD *)v89;
      }
      else
      {
        BytesReturned = 0;
        v22 = *(_QWORD *)v89;
        if ( !(unsigned int)BasepCopySecurityInformation(
                              (int)String,
                              (int)FileHandle,
                              v18,
                              v89[0],
                              hDevice,
                              v13,
                              0x3Cu,
                              0,
                              FsInformation[0],
                              (__int64)&BytesReturned,
                              1) )
          goto LABEL_97;
      }
      v23 = v20 != 0;
      if ( !(unsigned int)BasepCopyAlternateDataStreams(FileHandle, ShareAccess, OpenOptions) )
        goto LABEL_97;
      if ( v21 )
      {
        v24 = -1;
      }
      else
      {
        v24 = -1;
        v37 = (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() == 0;
        v38 = v112;
        if ( v37 )
        {
          if ( v81 )
            v38 = -1;
          v39 = BasepTransferEncryption(&hDevice, &v95, v110[0], v38, v23);
        }
        else
        {
          if ( v81 )
            v38 = -1;
          v39 = BasepSetFileEncryptionCompression(FileHandle, &hDevice, &v95, String, v22, v110[0], v38, v23);
        }
        if ( !v39 )
        {
LABEL_97:
          v12 = Destination;
          goto LABEL_98;
        }
        if ( a6 )
        {
          *(_OWORD *)Buffer = 0;
          hTemplateFile = 0;
          *(_DWORD *)Buffer = a6;
          v25 = 0;
          v17 = NtFsControlFile(hDevice, 0, 0, 0, &IoStatusBlock, 0x900FCu, Buffer, 0x18u, 0, 0);
          if ( v17 < 0 )
            goto LABEL_62;
LABEL_29:
          DeviceIoControl(hDevice, 0x900A0u, 0, 0, 0, 0, &BytesReturned, 0);
          if ( (_DWORD)TargetHandle )
          {
            TargetHandle = (HANDLE)-1LL;
            StandardError = FileHandle;
            switch ( (_DWORD)FileHandle )
            {
              case 0xFFFFFFF4:
                StandardError = NtCurrentPeb()->ProcessParameters->StandardError;
                break;
              case 0xFFFFFFF5:
                StandardError = NtCurrentPeb()->ProcessParameters->StandardOutput;
                break;
              case 0xFFFFFFF6:
                StandardError = NtCurrentPeb()->ProcessParameters->StandardInput;
                break;
            }
            v35 = NtDuplicateObject(
                    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                    StandardError,
                    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                    &TargetHandle,
                    0,
                    0,
                    2u);
            if ( v35 < 0 )
            {
              BaseSetLastNTError((unsigned int)v35);
            }
            else
            {
              v70 = BasepNotifyTrackingService(&TargetHandle, &ObjectAttributes);
              v36 = v84;
              if ( v70 >= 0 )
                v36 = 1;
              v84 = v36;
              v87 = v36;
              if ( TargetHandle != (HANDLE)-1LL )
                CloseHandle(TargetHandle);
            }
          }
          if ( !DosPathNamea )
          {
            FileW = -1;
            v27 = 0;
            v82 = 0;
            v28 = wcslen(String);
            v29 = 0;
            v92 = 0;
            v30 = 2 * v28 + 32;
            v31 = v30;
            TargetHandle = (HANDLE)v30;
            Destination = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v30);
            if ( Destination )
            {
              while ( 1 )
              {
                if ( FileW != -1 )
                  goto LABEL_72;
                if ( v27 >= 0x10 )
                  break;
                swprintf_s(
                  Buffer,
                  0x10u,
                  L"~RF%4x.TMP",
                  v27 + (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24));
                v32 = v31 >> 1;
                v33 = Destination;
                wcscpy_s(Destination, v32, String);
                wcscat_s(v33, v32, Buffer);
                FileW = (__int64)CreateFileW(v33, 0x40010000u, 0, 0, 1u, 0x102u, 0);
                if ( FileW == -1 )
                {
                  if ( NtCurrentTeb()->LastErrorValue == 80 )
                    v29 = 1;
                  v92 = v29;
                }
                v82 = ++v27;
                v31 = v30;
              }
              if ( !v29 )
              {
                v40 = 0;
                v77 = 0;
                v41 = String;
                v42 = wcslen(String);
                *(_QWORD *)v89 = 0;
                for ( i = v42 - 1; ; --i )
                {
                  v77 = i;
                  v44 = i;
                  if ( i < 0 || v41[i] == 92 )
                    break;
                }
                v45 = v42 - i - 1;
                if ( v45 )
                {
                  if ( v45 < 8u )
                    v24 = (1 << (4 * v45)) - 1;
                  v46 = &Destination[v44 + 1];
                  *(_QWORD *)v89 = v46;
                  v47 = v30 - (v44 * 2 + 2);
                  v82 = 0;
                  v48 = (unsigned __int64)TargetHandle;
                  while ( FileW == -1 )
                  {
                    if ( v40 >= 0x10 )
                      goto LABEL_96;
                    swprintf_s(
                      Buffer,
                      0x10u,
                      L"%x",
                      v24 & (v40 + (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24)));
                    wcscpy_s(Destination, v48 >> 1, String);
                    wcscpy_s(v46, (unsigned __int64)v47 >> 1, Buffer);
                    FileW = (__int64)CreateFileW(Destination, 0x40010000u, 0, 0, 1u, 0x102u, 0);
                    v82 = ++v40;
                  }
LABEL_72:
                  CloseHandle((HANDLE)FileW);
                  v12 = Destination;
                  v25 = 0;
                  goto LABEL_73;
                }
              }
            }
LABEL_96:
            RtlSetLastWin32Error(0x497u);
            goto LABEL_97;
          }
          v12 = (WCHAR *)DosPathNamea;
          Destination = (wchar_t *)DosPathNamea;
LABEL_73:
          if ( RtlDosPathNameToNtPathName_U(v12, &DestinationString, 0, 0) )
          {
            Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, DestinationString.Length + 24LL);
            v74 = Heap;
            if ( Heap )
            {
              v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, NtPathName.Length + 24LL);
              v97 = v14;
              if ( v14 )
              {
                v50 = FileHandle;
                *((_QWORD *)Heap + 1) = 0;
                Heap[4] = DestinationString.Length;
                memcpy_0(Heap + 5, DestinationString.Buffer, DestinationString.Length);
                *Heap = 5;
                v51 = NtSetInformationFile(
                        v50,
                        &IoStatusBlock,
                        Heap,
                        DestinationString.Length + 24,
                        (FILE_INFORMATION_CLASS)65);
                if ( v51 == -1073741811 || v51 == -1073741637 )
                {
                  v83 = 0;
                  *(_BYTE *)Heap = 1;
                  v51 = NtSetInformationFile(
                          v50,
                          &IoStatusBlock,
                          Heap,
                          DestinationString.Length + 24,
                          FileRenameInformation);
                }
                else
                {
                  v25 = v93;
                }
                if ( v51 < 0 )
                {
                  RtlSetLastWin32Error(0x497u);
                  goto LABEL_99;
                }
                v52 = hDevice;
                v14[1] = 0;
                *((_DWORD *)v14 + 4) = NtPathName.Length;
                memcpy_0((char *)v14 + 20, NtPathName.Buffer, NtPathName.Length);
                if ( v25 )
                {
                  *(_DWORD *)v14 = 5;
                  v53 = NtSetInformationFile(
                          v52,
                          &IoStatusBlock,
                          v14,
                          NtPathName.Length + 24,
                          (FILE_INFORMATION_CLASS)65);
                  if ( v53 != -1073741811 && v53 != -1073741637 )
                  {
LABEL_83:
                    if ( v53 >= 0 )
                    {
                      v61 = 1;
                      v69 = 1;
                      Heap = v74;
                      v60 = 0;
                      goto LABEL_157;
                    }
                    v54 = FileHandle;
                    v14[1] = 0;
                    *((_DWORD *)v14 + 4) = NtPathName.Length;
                    memcpy_0((char *)v14 + 20, NtPathName.Buffer, NtPathName.Length);
                    if ( v25 )
                    {
                      *(_DWORD *)v14 = 5;
                      v55 = NtSetInformationFile(
                              v54,
                              &IoStatusBlock,
                              v14,
                              NtPathName.Length + 24,
                              (FILE_INFORMATION_CLASS)65);
                      v56 = v55;
                      if ( v55 != -1073741811 && v55 != -1073741637 )
                      {
LABEL_87:
                        if ( v56 != -1073741611 )
                          goto LABEL_92;
                        NtClose(FileHandle);
                        FileHandle = (HANDLE)-1LL;
                        ObjectAttributes.Length = 48;
                        ObjectAttributes.RootDirectory = 0;
                        ObjectAttributes.Attributes = 64;
                        ObjectAttributes.ObjectName = &DestinationString;
                        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                        if ( NtOpenFile(&FileHandle, DesiredAccess, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u) < 0 )
                          goto LABEL_92;
                        v57 = FileHandle;
                        v14[1] = 0;
                        *((_DWORD *)v14 + 4) = NtPathName.Length;
                        memcpy_0((char *)v14 + 20, NtPathName.Buffer, NtPathName.Length);
                        if ( v25 )
                        {
                          *(_DWORD *)v14 = 5;
                          v58 = NtSetInformationFile(
                                  v57,
                                  &IoStatusBlock,
                                  v14,
                                  NtPathName.Length + 24,
                                  (FILE_INFORMATION_CLASS)65);
                          v56 = v58;
                          if ( v58 != -1073741811 && v58 != -1073741637 )
                            goto LABEL_92;
                          v83 = 0;
                        }
                        *(_BYTE *)v14 = 1;
                        v56 = NtSetInformationFile(
                                v57,
                                &IoStatusBlock,
                                v14,
                                NtPathName.Length + 24,
                                FileRenameInformation);
LABEL_92:
                        v59 = 1177;
                        if ( v56 >= 0 )
                          v59 = 1176;
                        RtlSetLastWin32Error(v59);
                        v60 = 1;
                        v12 = Destination;
                        Heap = v74;
                        goto LABEL_100;
                      }
                      v25 = 0;
                      v83 = 0;
                    }
                    *(_BYTE *)v14 = 1;
                    v56 = NtSetInformationFile(v54, &IoStatusBlock, v14, NtPathName.Length + 24, FileRenameInformation);
                    goto LABEL_87;
                  }
                  v25 = 0;
                  v83 = 0;
                }
                *(_BYTE *)v14 = 1;
                v53 = NtSetInformationFile(v52, &IoStatusBlock, v14, NtPathName.Length + 24, FileRenameInformation);
                goto LABEL_83;
              }
              v62 = 1176;
            }
            else
            {
              v62 = 1175;
            }
            RtlSetLastWin32Error(v62);
            goto LABEL_99;
          }
LABEL_120:
          RtlSetLastWin32Error(3u);
          goto LABEL_98;
        }
      }
      v25 = 0;
      goto LABEL_29;
    }
    v11 = 1;
    v17 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v98, 8u, FileAttributeTagInformation);
    if ( v17 < 0 || (v98 & 0x2000000000000000LL) != 0 )
      break;
    NtClose(FileHandle);
    FileHandle = (HANDLE)-1LL;
    v19 = NtOpenFile(&FileHandle, v18, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
    if ( v19 < 0 )
      goto LABEL_117;
  }
  if ( v17 < 0 )
  {
LABEL_62:
    BaseSetLastNTError((unsigned int)v17);
    goto LABEL_63;
  }
  RtlSetLastWin32Error(0x5B8u);
LABEL_63:
  v12 = Destination;
LABEL_98:
  Heap = v74;
LABEL_99:
  v60 = 0;
LABEL_100:
  v61 = 0;
LABEL_157:
  if ( !v61 && v84 && hDevice != (HANDLE)-1LL && FileHandle != (HANDLE)-1LL )
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    BasepNotifyTrackingService(&hDevice, &v95);
    RtlSetLastWin32Error(LastErrorValue);
  }
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  if ( hDevice != (HANDLE)-1LL )
  {
    OutputBuffer = 0;
    NtFsControlFile(hDevice, 0, 0, 0, &IoStatusBlock, 0x900EFu, 0, 0, &OutputBuffer, 8u);
    NtClose(hDevice);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v91);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v12 && v12 != DosPathNamea )
  {
    if ( !v60 )
    {
      if ( a5 )
      {
        v66 = CreateFileW(v12, 0x10000u, 0, 0, 3u, 0x200080u, 0);
        if ( v66 != (HANDLE)-1LL )
        {
          v100 = 0;
          v101 = 0;
          LODWORD(v100) = a5;
          NtFsControlFile(v66, 0, 0, 0, &IoStatusBlock, 0x900FCu, &v100, 0x18u, 0, 0);
          BaseMarkFileForDelete(v66);
          CloseHandle(v66);
        }
      }
      else if ( !(unsigned int)InternalDeleteFileW(v12, 0) && NtCurrentTeb()->LastErrorValue )
      {
        IsBrokeredCreateDirectoryWPresent();
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  }
  return v69;
}

```

## disassembly

```asm
0x1800d4240  mov     r11, rsp
0x1800d4243  push    rbx
0x1800d4244  push    rsi
0x1800d4245  push    rdi
0x1800d4246  push    r12
0x1800d4248  push    r13
0x1800d424a  push    r14
0x1800d424c  push    r15
0x1800d424e  sub     rsp, 4B0h
0x1800d4255  mov     rax, cs:__security_cookie
0x1800d425c  xor     rax, rsp
0x1800d425f  mov     [rsp+4E8h+var_48], rax
0x1800d4267  mov     edi, r9d
0x1800d426a  mov     rax, r8
0x1800d426d  mov     [rsp+4E8h+DosPathName], rax
0x1800d4275  mov     r15, rdx
0x1800d4278  mov     qword ptr [rsp+4E8h+var_3E8], rdx
0x1800d4280  mov     r13, rcx
0x1800d4283  mov     [rsp+4E8h+String], rcx
0x1800d428b  mov     [rsp+4E8h+var_320], rax
0x1800d4293  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d4297  mov     [r11-468h], rax
0x1800d429e  mov     [rsp+4E8h+hDevice], rax
0x1800d42a3  xorps   xmm0, xmm0
0x1800d42a6  movups  xmmword ptr [rsp+4E8h+NtPathName.Length], xmm0
0x1800d42ae  xorps   xmm1, xmm1
0x1800d42b1  movups  xmmword ptr [rsp+4E8h+var_330.Length], xmm1
0x1800d42b9  movups  xmmword ptr [rsp+4E8h+DestinationString.Length], xmm0
0x1800d42c1  xor     eax, eax
0x1800d42c3  movups  xmmword ptr [rsp+4E8h+ObjectAttributes.Length], xmm0
0x1800d42cb  movups  xmmword ptr [rsp+4E8h+ObjectAttributes.ObjectName], xmm0
0x1800d42d3  movups  xmmword ptr [rsp+4E8h+ObjectAttributes+1Ch], xmm0
0x1800d42db  movups  xmmword ptr [rsp+4E8h+var_3C0.Length], xmm0
0x1800d42e3  movups  xmmword ptr [rsp+4E8h+var_3C0.ObjectName], xmm0
0x1800d42eb  movups  xmmword ptr [rsp+4E8h+var_3C0+1Ch], xmm0
0x1800d42f3  movups  xmmword ptr [rsp+4E8h+IoStatusBlock], xmm0
0x1800d42fb  xor     esi, esi
0x1800d42fd  mov     [rsp+4E8h+var_488], esi
0x1800d4301  movups  [rsp+4E8h+FileInformation], xmm0
0x1800d4309  movups  [rsp+4E8h+var_2D0], xmm0
0x1800d4311  mov     [r11-2C0h], rax
0x1800d4318  movups  [rsp+4E8h+var_2B8], xmm1
0x1800d4320  movups  [rsp+4E8h+var_2A8], xmm1
0x1800d4328  mov     [r11-298h], rax
0x1800d432f  mov     r14d, esi
0x1800d4332  mov     [rsp+4E8h+Destination], rsi
0x1800d4337  mov     [r11-358h], rsi
0x1800d433e  xor     edx, edx; Val
0x1800d4340  mov     r8d, 218h; Size
0x1800d4346  lea     rcx, [r11-288h]; void *
0x1800d434d  call    memset_0
0x1800d4352  xor     edx, edx; SourceString
0x1800d4354  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x1800d435c  call    cs:__imp_RtlInitUnicodeString
0x1800d4363  nop     dword ptr [rax+rax+00h]
0x1800d4368  test    r13, r13
0x1800d436b  jz      loc_1800D5A1A
0x1800d4371  test    r15, r15
0x1800d4374  jz      loc_1800D5A1A
0x1800d437a  cmp     [rsp+4E8h+arg_30], rsi
0x1800d4382  jnz     loc_1800D5A1A
0x1800d4388  cmp     [rsp+4E8h+arg_38], rsi
0x1800d4390  jnz     loc_1800D5A1A
0x1800d4396  mov     [rsp+4E8h+P], rsi
0x1800d439e  mov     [rsp+4E8h+var_3D8], rsi
0x1800d43a6  mov     ebx, esi
0x1800d43a8  mov     [rsp+4E8h+var_460], rsi
0x1800d43b0  mov     r12d, esi
0x1800d43b3  mov     [rsp+4E8h+var_360], rsi
0x1800d43bb  mov     [rsp+4E8h+BytesReturned], esi
0x1800d43c2  mov     [rsp+4E8h+var_424], esi
0x1800d43c9  mov     [rsp+4E8h+var_3CC], 1
0x1800d43d4  xor     eax, eax
0x1800d43d6  mov     [rsp+4E8h+var_480], eax
0x1800d43da  mov     [rsp+4E8h+var_418], eax
0x1800d43e1  mov     [rsp+4E8h+var_400], eax
0x1800d43e8  test    edi, 0FFFFFFF8h
0x1800d43ee  jnz     loc_1800D5A1A
0x1800d43f4  xor     edx, edx; SourceString
0x1800d43f6  lea     rcx, [rsp+4E8h+NtPathName]; DestinationString
0x1800d43fe  call    cs:__imp_RtlInitUnicodeString
0x1800d4405  nop     dword ptr [rax+rax+00h]
0x1800d440a  xor     r9d, r9d; DirectoryInfo
0x1800d440d  xor     r8d, r8d; NtFileNamePart
0x1800d4410  lea     rdx, [rsp+4E8h+NtPathName]; NtPathName
0x1800d4418  mov     rcx, r13; DosPathName
0x1800d441b  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800d4422  nop     dword ptr [rax+rax+00h]
0x1800d4427  xor     r13d, r13d
0x1800d442a  test    al, al
0x1800d442c  jz      loc_1800D540C
0x1800d4432  mov     rax, [rsp+4E8h+NtPathName.Buffer]
0x1800d443a  mov     [rsp+4E8h+P], rax
0x1800d4442  mov     [rsp+4E8h+ObjectAttributes.Length], 30h ; '0'
0x1800d444d  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], r13
0x1800d4455  mov     [rsp+4E8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800d4460  lea     rax, [rsp+4E8h+NtPathName]
0x1800d4468  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x1800d4470  xorps   xmm0, xmm0
0x1800d4473  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d447c  mov     r13d, 113008Ah
0x1800d4482  mov     [rsp+4E8h+DesiredAccess], r13d
0x1800d448a  mov     dword ptr [rsp+4E8h+OpenOptions], 200060h; OpenOptions
0x1800d4492  mov     [rsp+4E8h+ShareAccess], 7; ShareAccess
0x1800d449a  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800d44a2  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x1800d44aa  mov     edx, r13d; DesiredAccess
0x1800d44ad  lea     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800d44b5  call    cs:__imp_NtOpenFile
0x1800d44bc  nop     dword ptr [rax+rax+00h]
0x1800d44c1  mov     [rsp+4E8h+var_484], eax
0x1800d44c5  test    eax, eax
0x1800d44c7  jns     loc_1800D4569
0x1800d44cd  mov     r13d, 13008Ah
0x1800d44d3  mov     [rsp+4E8h+DesiredAccess], r13d
0x1800d44db  mov     dword ptr [rsp+4E8h+OpenOptions], 200060h; OpenOptions
0x1800d44e3  mov     [rsp+4E8h+ShareAccess], 7; ShareAccess
0x1800d44eb  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800d44f3  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x1800d44fb  mov     edx, r13d; DesiredAccess
0x1800d44fe  lea     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800d4506  call    cs:__imp_NtOpenFile
0x1800d450d  nop     dword ptr [rax+rax+00h]
0x1800d4512  mov     [rsp+4E8h+var_484], eax
0x1800d4516  test    eax, eax
0x1800d4518  jns     short loc_1800D4569
0x1800d451a  and     r13d, 0FFFFFFFDh
0x1800d451e  mov     [rsp+4E8h+DesiredAccess], r13d
0x1800d4526  mov     dword ptr [rsp+4E8h+OpenOptions], 200060h; OpenOptions
0x1800d452e  mov     [rsp+4E8h+ShareAccess], 7; ShareAccess
0x1800d4536  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800d453e  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x1800d4546  mov     edx, r13d; DesiredAccess
0x1800d4549  lea     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800d4551  call    cs:__imp_NtOpenFile
0x1800d4558  nop     dword ptr [rax+rax+00h]
0x1800d455d  mov     [rsp+4E8h+var_484], eax
0x1800d4561  test    eax, eax
0x1800d4563  js      loc_1800D52C6
0x1800d4569  xor     r9d, r9d; DirectoryInfo
0x1800d456c  xor     r8d, r8d; NtFileNamePart
0x1800d456f  lea     rdx, [rsp+4E8h+var_330]; NtPathName
0x1800d4577  mov     rcx, r15; DosPathName
0x1800d457a  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800d4581  nop     dword ptr [rax+rax+00h]
0x1800d4586  xor     ecx, ecx
0x1800d4588  test    al, al
0x1800d458a  jz      loc_1800D5631
0x1800d4590  mov     eax, r13d
0x1800d4593  and     eax, 2
0x1800d4596  mov     dword ptr [rsp+4E8h+TargetHandle], eax
0x1800d459d  mov     rax, [rsp+4E8h+var_330.Buffer]
0x1800d45a5  mov     [rsp+4E8h+var_3D8], rax
0x1800d45ad  mov     [rsp+4E8h+var_3C0.Length], 30h ; '0'
0x1800d45b8  mov     [rsp+4E8h+var_3C0.RootDirectory], rcx
0x1800d45c0  mov     [rsp+4E8h+var_3C0.Attributes], 40h ; '@'
0x1800d45cb  lea     rax, [rsp+4E8h+var_330]
0x1800d45d3  mov     [rsp+4E8h+var_3C0.ObjectName], rax
0x1800d45db  xorps   xmm0, xmm0
0x1800d45de  movdqu  xmmword ptr [rsp+4E8h+var_3C0.SecurityDescriptor], xmm0
0x1800d45e7  lea     r15d, [rcx+60h]
0x1800d45eb  bt      r13d, 18h
0x1800d45f0  jb      loc_1800D5647
0x1800d45f6  mov     r14d, 0C0000022h
0x1800d45fc  mov     eax, r14d
0x1800d45ff  xor     r13d, r13d
0x1800d4602  mov     [rsp+4E8h+var_484], eax
0x1800d4606  test    eax, eax
0x1800d4608  jns     short loc_1800D4688
0x1800d460a  mov     ebx, 0C01D0000h
0x1800d460f  mov     [rsp+4E8h+var_448], ebx
0x1800d4616  mov     dword ptr [rsp+4E8h+OpenOptions], r15d; OpenOptions
0x1800d461b  mov     [rsp+4E8h+ShareAccess], r13d; ShareAccess
0x1800d4620  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800d4628  lea     r8, [rsp+4E8h+var_3C0]; ObjectAttributes
0x1800d4630  mov     edx, ebx; DesiredAccess
0x1800d4632  lea     rcx, [rsp+4E8h+hDevice]; FileHandle
0x1800d4637  call    cs:__imp_NtOpenFile
0x1800d463e  nop     dword ptr [rax+rax+00h]
0x1800d4643  mov     [rsp+4E8h+var_484], eax
0x1800d4647  test    eax, eax
0x1800d4649  jns     short loc_1800D4688
0x1800d464b  mov     ebx, 0C0150000h
0x1800d4650  mov     [rsp+4E8h+var_448], ebx
0x1800d4657  mov     dword ptr [rsp+4E8h+OpenOptions], r15d; OpenOptions
0x1800d465c  mov     [rsp+4E8h+ShareAccess], r13d; ShareAccess
0x1800d4661  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800d4669  lea     r8, [rsp+4E8h+var_3C0]; ObjectAttributes
0x1800d4671  mov     edx, ebx; DesiredAccess
0x1800d4673  lea     rcx, [rsp+4E8h+hDevice]; FileHandle
0x1800d4678  call    cs:__imp_NtOpenFile
0x1800d467f  nop     dword ptr [rax+rax+00h]
0x1800d4684  mov     [rsp+4E8h+var_484], eax
0x1800d4688  cmp     eax, r14d
0x1800d468b  jz      loc_1800D54E8
0x1800d4691  test    eax, eax
0x1800d4693  js      loc_1800D4C09
0x1800d4699  mov     r13d, [rsp+4E8h+arg_28]
0x1800d46a1  xor     r15d, r15d
0x1800d46a4  test    r13d, r13d
0x1800d46a7  jnz     loc_1800D5311
0x1800d46ad  mov     r15d, [rsp+4E8h+DesiredAccess]
0x1800d46b5  mov     [rsp+4E8h+ShareAccess], 4; FileInformationClass
0x1800d46bd  mov     r9d, 28h ; '('; Length
0x1800d46c3  lea     r8, [rsp+4E8h+FileInformation]; FileInformation
0x1800d46cb  lea     rdx, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800d46d3  mov     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800d46db  call    cs:__imp_NtQueryInformationFile
0x1800d46e2  nop     dword ptr [rax+rax+00h]
0x1800d46e7  mov     [rsp+4E8h+var_484], eax
0x1800d46eb  test    eax, eax
0x1800d46ed  jns     loc_1800D4A4D
0x1800d46f3  and     edi, 2
0x1800d46f6  jz      loc_1800D5387
0x1800d46fc  xor     esi, esi
0x1800d46fe  lea     r14d, [rsi+1]
0x1800d4702  mov     [rsp+4E8h+ShareAccess], 5; FsInformationClass
0x1800d470a  mov     r9d, 218h; Length
0x1800d4710  lea     r8, [rsp+4E8h+FsInformation]; FsInformation
0x1800d4718  lea     rdx, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800d4720  mov     rcx, [rsp+4E8h+hDevice]; FileHandle
0x1800d4725  call    cs:__imp_NtQueryVolumeInformationFile
0x1800d472c  nop     dword ptr [rax+rax+00h]
0x1800d4731  mov     [rsp+4E8h+var_484], eax
0x1800d4735  test    eax, eax
0x1800d4737  js      loc_1800D576F
0x1800d473d  mov     [rsp+4E8h+BytesReturned], esi
0x1800d4744  mov     [rsp+4E8h+var_498], 1; int
0x1800d474c  lea     rax, [rsp+4E8h+BytesReturned]
0x1800d4754  mov     qword ptr [rsp+4E8h+OutputBufferLength], rax; __int64
0x1800d4759  mov     eax, dword ptr [rsp+4E8h+FsInformation]
0x1800d4760  mov     dword ptr [rsp+4E8h+OutputBuffer], eax; char
0x1800d4764  mov     [rsp+4E8h+lpOverlapped], rsi; __int64
0x1800d4769  mov     dword ptr [rsp+4E8h+lpBytesReturned], 3Ch ; '<'; SecurityInfo
0x1800d4771  mov     dword ptr [rsp+4E8h+OpenOptions], ebx; __int64
0x1800d4775  mov     rax, [rsp+4E8h+hDevice]
0x1800d477a  mov     qword ptr [rsp+4E8h+ShareAccess], rax; __int64
0x1800d477f  mov     rsi, qword ptr [rsp+4E8h+var_3E8]
0x1800d4787  mov     r9, rsi; int
0x1800d478a  mov     r8d, r15d; int
0x1800d478d  mov     rdx, [rsp+4E8h+FileHandle]; int
0x1800d4795  mov     rcx, [rsp+4E8h+String]; int
0x1800d479d  call    BasepCopySecurityInformation
0x1800d47a2  test    eax, eax
0x1800d47a4  jz      loc_1800D50DC
0x1800d47aa  xor     eax, eax
0x1800d47ac  mov     ebx, eax
0x1800d47ae  test    edi, edi
0x1800d47b0  setnz   bl
0x1800d47b3  mov     r8d, ebx
0x1800d47b6  mov     rdx, [rsp+4E8h+hDevice]
0x1800d47bb  mov     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800d47c3  call    BasepCopyAlternateDataStreams
0x1800d47c8  xor     edi, edi
0x1800d47ca  test    eax, eax
0x1800d47cc  jz      loc_1800D50DC
0x1800d47d2  test    r14d, r14d
0x1800d47d5  jz      loc_1800D4B19
0x1800d47db  or      r15d, 0FFFFFFFFh
0x1800d47df  xor     r13d, r13d
0x1800d47e2  mov     [rsp+4E8h+lpOverlapped], r13; lpOverlapped
0x1800d47e7  lea     rax, [rsp+4E8h+BytesReturned]
0x1800d47ef  mov     [rsp+4E8h+lpBytesReturned], rax; lpBytesReturned
0x1800d47f4  mov     dword ptr [rsp+4E8h+OpenOptions], r13d; nOutBufferSize
0x1800d47f9  mov     qword ptr [rsp+4E8h+ShareAccess], r13; lpOutBuffer
0x1800d47fe  xor     r9d, r9d; nInBufferSize
0x1800d4801  xor     r8d, r8d; lpInBuffer
0x1800d4804  mov     edx, 900A0h; dwIoControlCode
0x1800d4809  mov     rcx, [rsp+4E8h+hDevice]; hDevice
0x1800d480e  call    DeviceIoControl
0x1800d4813  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800d4817  cmp     dword ptr [rsp+4E8h+TargetHandle], r13d
0x1800d481f  jnz     loc_1800D4989
0x1800d4825  mov     rax, [rsp+4E8h+DosPathName]
0x1800d482d  test    rax, rax
0x1800d4830  jnz     loc_1800D4C1A
0x1800d4836  mov     r14, rbx
0x1800d4839  mov     esi, r13d
0x1800d483c  mov     [rsp+4E8h+var_420], r13d
0x1800d4844  mov     rcx, [rsp+4E8h+String]; String
0x1800d484c  call    cs:__imp_wcslen
0x1800d4853  nop     dword ptr [rax+rax+00h]
0x1800d4858  add     eax, eax
0x1800d485a  mov     edi, r13d
0x1800d485d  mov     [rsp+4E8h+var_3D0], r13d
0x1800d4865  lea     r13d, [rax+20h]
0x1800d4869  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800d486f  mov     ebx, r13d
0x1800d4872  mov     [rsp+4E8h+TargetHandle], rbx
0x1800d487a  mov     rcx, gs:60h
0x1800d4883  mov     r8d, r13d; Size
0x1800d4886  mov     rcx, [rcx+30h]; HeapHandle
0x1800d488a  call    cs:__imp_RtlAllocateHeap
0x1800d4891  nop     dword ptr [rax+rax+00h]
0x1800d4896  mov     [rsp+4E8h+Destination], rax
0x1800d489b  test    rax, rax
0x1800d489e  jz      loc_1800D50CB
0x1800d48a4  mov     eax, 7FFE0320h
0x1800d48a9  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800d48ad  jnz     loc_1800D4CD4
  ... truncated ...
```
