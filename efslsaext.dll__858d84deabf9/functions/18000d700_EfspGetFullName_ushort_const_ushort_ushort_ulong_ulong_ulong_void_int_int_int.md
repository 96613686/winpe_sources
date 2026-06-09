# EfspGetFullName(ushort const *,ushort * *,ushort * *,ulong,ulong *,ulong,void *,int,int *,int *)

- ea: `0x18000d700`
- end: `0x18000ddc7`
- name: `?EfspGetFullName@@YAKPEBGPEAPEAG1KPEAKKPEAXHPEAH4@Z`
- size: `1735`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, char, unsigned int *, unsigned int, void *, int, int *, int *)`
- caller_count: `8`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000af80`
- `0x18000b1e0`
- `0x18000b424`
- `0x18000b808`
- `0x18000ba38`
- `0x18000bd78`
- `0x18000bfc0`
- `0x18000c21c`

## callees

- `0x180007e6c`
- `0x18000d300`
- `0x18000d41c`
- `0x18000d700`
- `0x18000ddd0`
- `0x18000dee0`
- `0x18001200e`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d83a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d83a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dca7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dc36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dca7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd95`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000dacd`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000dacd`
- `ntdll!RtlInitUnicodeString` at `0x18000d7b0`
- `ntdll!RtlInitUnicodeString` at `0x18000d7b0`
- `ntdll!NtQueryInformationFile` at `0x18000dbb1`
- `ntdll!NtQueryInformationFile` at `0x18000dbb1`
- `ntdll!NtCreateFile` at `0x18000db5b`
- `ntdll!NtCreateFile` at `0x18000db5b`
- `ntdll!RtlFreeHeap` at `0x18000d868`
- `ntdll!RtlFreeHeap` at `0x18000dbe2`
- `ntdll!RtlFreeHeap` at `0x18000dcd3`
- `ntdll!RtlFreeHeap` at `0x18000dcf5`
- `ntdll!RtlFreeHeap` at `0x18000dd1b`
- `ntdll!RtlFreeHeap` at `0x18000dd39`
- `ntdll!RtlFreeHeap` at `0x18000dd5e`
- `ntdll!RtlFreeHeap` at `0x18000dd82`
- `ntdll!RtlFreeHeap` at `0x18000d868`
- `ntdll!RtlFreeHeap` at `0x18000dbe2`
- `ntdll!RtlFreeHeap` at `0x18000dcd3`
- `ntdll!RtlFreeHeap` at `0x18000dcf5`
- `ntdll!RtlFreeHeap` at `0x18000dd1b`
- `ntdll!RtlFreeHeap` at `0x18000dd39`
- `ntdll!RtlFreeHeap` at `0x18000dd5e`
- `ntdll!RtlFreeHeap` at `0x18000dd82`
- `ntdll!RtlAllocateHeap` at `0x18000d811`
- `ntdll!RtlAllocateHeap` at `0x18000d92d`
- `ntdll!RtlAllocateHeap` at `0x18000dbfd`
- `ntdll!RtlAllocateHeap` at `0x18000d811`
- `ntdll!RtlAllocateHeap` at `0x18000d92d`
- `ntdll!RtlAllocateHeap` at `0x18000dbfd`
- `ntdll!RtlNtStatusToDosError` at `0x18000db67`
- `ntdll!RtlNtStatusToDosError` at `0x18000db67`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d9f5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d9f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d8ec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d9d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d8ec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d9d8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000d908`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000d951`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000d908`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000d951`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18000d84c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18000d84c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000d830`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18000d830`

## pseudocode

```c
__int64 __fastcall EfspGetFullName(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3,
        char a4,
        unsigned int *a5,
        unsigned int a6,
        void *a7,
        int a8,
        int *a9,
        int *a10)
{
  const WCHAR *v10; // r13
  const WCHAR *v11; // r12
  _WORD *v12; // rsi
  __int64 v14; // rax
  unsigned int v15; // ebx
  WCHAR *Heap; // rax
  DWORD LastError; // eax
  unsigned int FullNameLocal; // ebx
  UINT DriveTypeW; // ebx
  __int64 v20; // rdx
  DWORD v21; // edi
  HANDLE FileW; // rax
  DWORD FinalPathNameByHandleW; // eax
  DWORD v24; // ebx
  PVOID v25; // rax
  unsigned int v26; // ebx
  DWORD FileAttributesW; // eax
  DWORD v28; // r13d
  ULONG CreateOptions; // edi
  ULONG CreateDisposition; // r15d
  int v31; // r14d
  ULONG v32; // ebx
  NTSTATUS v33; // eax
  NTSTATUS v34; // ecx
  ULONG v35; // edi
  NTSTATUS v36; // eax
  int v37; // ebx
  _WORD *v38; // rax
  unsigned __int16 **v39; // r14
  unsigned __int16 **v40; // rdi
  unsigned int v41; // r9d
  unsigned __int16 **v42; // rdi
  unsigned __int16 **v43; // rdi
  HANDLE hFile; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v46; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR DosPathName; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpRootPathName; // [rsp+78h] [rbp-88h]
  unsigned __int16 **v49; // [rsp+80h] [rbp-80h]
  unsigned __int16 **v50; // [rsp+88h] [rbp-78h]
  unsigned int v51[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v52[2]; // [rsp+98h] [rbp-68h]
  PVOID P; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  void *v55; // [rsp+B8h] [rbp-48h]
  int *v56; // [rsp+C0h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE FileInformation[528]; // [rsp+110h] [rbp+10h] BYREF

  v10 = 0;
  v11 = a1;
  v49 = a3;
  v12 = 0;
  v50 = a2;
  DosPathName = a1;
  v55 = a7;
  v56 = a9;
  hFile = 0;
  v51[0] = 0;
  v46 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  DestinationString = 0;
  memset_0(FileInformation, 0, sizeof(FileInformation));
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  *v50 = 0;
  *v49 = 0;
  if ( a10 )
    *a10 = 1;
  if ( a9 )
    *a9 = 0;
  v14 = -1;
  do
    ++v14;
  while ( v11[v14] );
  *(_QWORD *)v52 = v14;
  if ( (unsigned int)(v14 + 1) > 0x104 )
    v15 = 2 * (v14 + 1);
  else
    v15 = 522;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  lpRootPathName = Heap;
  if ( !Heap )
    goto LABEL_78;
  if ( !GetVolumePathNameW(v11, Heap, v15 >> 1) )
  {
LABEL_12:
    LastError = GetLastError();
LABEL_13:
    FullNameLocal = LastError;
    goto LABEL_79;
  }
  DriveTypeW = GetDriveTypeW(lpRootPathName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)lpRootPathName);
  lpRootPathName = 0;
  if ( DriveTypeW != 4 )
  {
    v46 = 1966080;
    DosPathName = 0;
    *(_QWORD *)v51 = 0;
    v21 = 0;
    if ( (int)AppModelPolicy_GetPolicy_Internal(-6, v20, &v46, v51, &DosPathName) < 0
      || v46 != 1966081
      || (FileW = CreateFileW(v11, 0x80u, 1u, 0, 3u, 0x2000000u, 0), hFile = FileW, FileW == (HANDLE)-1LL) )
    {
LABEL_22:
      if ( v10 )
        v11 = v10;
      else
        v21 = v52[0];
      FullNameLocal = EfspGetFullNameLocal(v11, v21, v50, v49);
      if ( a10 )
        *a10 = 0;
      goto LABEL_79;
    }
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
    v24 = FinalPathNameByHandleW;
    if ( !FinalPathNameByHandleW )
      goto LABEL_12;
    v25 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * FinalPathNameByHandleW);
    P = v25;
    v10 = (const WCHAR *)v25;
    if ( v25 )
    {
      v21 = GetFinalPathNameByHandleW(hFile, (LPWSTR)v25, v24, 0);
      if ( !v21 )
        goto LABEL_12;
      CloseHandle(hFile);
      hFile = 0;
      goto LABEL_22;
    }
LABEL_78:
    FullNameLocal = 8;
    goto LABEL_79;
  }
  v26 = a6;
  if ( (a4 & 1) != 0 || a6 )
  {
    FileAttributesW = GetFileAttributesW(v11);
    v28 = FileAttributesW;
    if ( a6 )
    {
      if ( FileAttributesW == -1 )
      {
        CreateDisposition = 2;
        if ( a5 && *a5 == 1 )
          *a5 = 2;
        if ( (a4 & 2) != 0 )
        {
          CreateOptions = 1;
          v26 = a6 | 0x10;
        }
        else
        {
          CreateOptions = 0x8000;
        }
      }
      else
      {
        if ( a5 && *a5 == 1 )
        {
          FullNameLocal = 80;
          goto LABEL_79;
        }
        CreateOptions = 0;
        if ( (FileAttributesW & 0x10) != 0 )
        {
          if ( (a4 & 2) == 0 )
          {
            FullNameLocal = 8540;
            goto LABEL_79;
          }
          CreateOptions = 1;
        }
        CreateDisposition = 1;
      }
    }
    else
    {
      v31 = a4 & 2;
      if ( FileAttributesW == -1 )
      {
        CreateDisposition = 2;
        CreateOptions = v31 != 0 ? 16385 : 49152;
        v26 = v31 != 0 ? 144 : 128;
      }
      else
      {
        CreateDisposition = 1;
        if ( v31 )
        {
          CreateOptions = 16385;
          v26 = 144;
        }
        else
        {
          v26 = 128;
          CreateOptions = 0x4000;
        }
      }
    }
    if ( !RtlDosPathNameToNtPathName_U(DosPathName, &DestinationString, 0, 0) )
    {
      FullNameLocal = 3;
      goto LABEL_79;
    }
    v32 = v26 & 0xFFFFBFFE;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = a8 != 0 ? 66 : 64;
    ObjectAttributes.ObjectName = &DestinationString;
    if ( v55 )
      ObjectAttributes.SecurityDescriptor = (PVOID)*((_QWORD *)v55 + 1);
    else
      ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.SecurityQualityOfService = 0;
    v33 = NtCreateFile(
            &hFile,
            0x100100u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            v32,
            0,
            CreateDisposition,
            CreateOptions,
            0,
            0);
    if ( v33 < 0 )
    {
      v34 = v33;
LABEL_59:
      LastError = RtlNtStatusToDosError(v34);
      goto LABEL_13;
    }
    v11 = DosPathName;
    if ( v28 == -1 && v56 )
      *v56 = 1;
  }
  else
  {
    hFile = CreateFileW(v11, 0x80u, 1u, 0, 3u, 0x2000000u, 0);
    if ( hFile == (HANDLE)-1LL )
      goto LABEL_12;
  }
  v12 = FileInformation;
  v35 = 528;
  do
  {
    v36 = NtQueryInformationFile(hFile, &IoStatusBlock, v12, v35, FileNetworkPhysicalNameInformation);
    v37 = v36;
    if ( v36 != -2147483643 && v36 != -1073741789 )
      break;
    v35 *= 2;
    if ( v12 != (_WORD *)FileInformation )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    v38 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v35);
    v12 = v38;
    if ( !v38 )
    {
      CloseHandle(hFile);
      hFile = 0;
      goto LABEL_78;
    }
    memset_0(v38, 0, v35);
  }
  while ( v37 == -2147483643 || v37 == -1073741789 );
  CloseHandle(hFile);
  hFile = 0;
  if ( v37 < 0 )
  {
    v34 = v37;
    goto LABEL_59;
  }
  if ( v12[2] != 92 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v39 = v49;
  v40 = v50;
  FullNameLocal = EfspGetUNCName((struct _FILE_NETWORK_PHYSICAL_NAME_INFORMATION *)v12, v50, v51, v49, &v46);
  if ( !FullNameLocal )
  {
    LastError = EfspAttemptToGetWebDavPath(v11, v52[0], v40, v41, v39, v46);
    goto LABEL_13;
  }
LABEL_79:
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  if ( lpRootPathName )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)lpRootPathName);
  if ( v12 && v12 != (_WORD *)FileInformation )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( FullNameLocal )
  {
    v42 = v49;
    if ( *v49 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v49);
      *v42 = 0;
    }
    v43 = v50;
    if ( *v50 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *v50);
      *v43 = 0;
    }
  }
  if ( hFile )
    CloseHandle(hFile);
  return FullNameLocal;
}

```

## disassembly

```asm
0x18000d700  mov     [rsp-8+arg_18], rbx
0x18000d705  push    rbp
0x18000d706  push    rsi
0x18000d707  push    rdi
0x18000d708  push    r12
0x18000d70a  push    r13
0x18000d70c  push    r14
0x18000d70e  push    r15
0x18000d710  lea     rbp, [rsp-230h]
0x18000d718  sub     rsp, 330h
0x18000d71f  mov     rax, cs:__security_cookie
0x18000d726  xor     rax, rsp
0x18000d729  mov     [rbp+260h+var_40], rax
0x18000d730  mov     rax, [rbp+260h+arg_30]
0x18000d737  xorps   xmm0, xmm0
0x18000d73a  mov     rbx, [rbp+260h+arg_40]
0x18000d741  xor     r13d, r13d
0x18000d744  mov     rdi, [rbp+260h+arg_20]
0x18000d74b  mov     r12, rcx
0x18000d74e  mov     r15, [rbp+260h+arg_48]
0x18000d755  xorps   xmm1, xmm1
0x18000d758  mov     [rbp+260h+var_2E0], r8
0x18000d75c  mov     esi, r13d
0x18000d75f  mov     [rbp+260h+var_2D8], rdx
0x18000d763  mov     r8d, 210h; Size
0x18000d769  mov     [rsp+360h+DosPathName], rcx
0x18000d76e  xor     edx, edx; Val
0x18000d770  lea     rcx, [rbp+260h+FileInformation]; void *
0x18000d774  mov     [rbp+260h+var_2A8], rax
0x18000d778  mov     [rbp+260h+var_2A0], rbx
0x18000d77c  mov     r14d, r9d
0x18000d77f  mov     [rsp+360h+hFile], r13
0x18000d784  mov     [rbp+260h+var_2D0], r13d
0x18000d788  mov     [rsp+360h+var_2F8], r13d
0x18000d78d  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x18000d791  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm0
0x18000d795  movups  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d799  movups  xmmword ptr [rbp+260h+IoStatusBlock], xmm0
0x18000d79d  movups  xmmword ptr [rbp+260h+DestinationString.Length], xmm1
0x18000d7a1  call    memset_0
0x18000d7a6  xor     edx, edx; SourceString
0x18000d7a8  mov     [rbp+260h+P], r13
0x18000d7ac  lea     rcx, [rbp+260h+DestinationString]; DestinationString
0x18000d7b0  call    cs:__imp_RtlInitUnicodeString
0x18000d7b6  mov     rax, [rbp+260h+var_2D8]
0x18000d7ba  xor     ecx, ecx
0x18000d7bc  mov     [rax], rcx
0x18000d7bf  mov     rax, [rbp+260h+var_2E0]
0x18000d7c3  mov     [rax], rcx
0x18000d7c6  test    r15, r15
0x18000d7c9  jz      short loc_18000D7D2
0x18000d7cb  mov     dword ptr [r15], 1
0x18000d7d2  test    rbx, rbx
0x18000d7d5  jz      short loc_18000D7D9
0x18000d7d7  mov     [rbx], ecx
0x18000d7d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d7dd  inc     rax
0x18000d7e0  cmp     [r12+rax*2], cx
0x18000d7e5  jnz     short loc_18000D7DD
0x18000d7e7  lea     ebx, [rax+1]
0x18000d7ea  mov     qword ptr [rbp+260h+var_2C8], rax
0x18000d7ee  cmp     ebx, 104h
0x18000d7f4  ja      short loc_18000D7FD
0x18000d7f6  mov     ebx, 20Ah
0x18000d7fb  jmp     short loc_18000D7FF
0x18000d7fd  add     ebx, ebx
0x18000d7ff  mov     rcx, gs:60h
0x18000d808  xor     edx, edx; Flags
0x18000d80a  mov     r8d, ebx; Size
0x18000d80d  mov     rcx, [rcx+30h]; HeapHandle
0x18000d811  call    cs:__imp_RtlAllocateHeap
0x18000d817  mov     [rsp+360h+lpRootPathName], rax
0x18000d81c  test    rax, rax
0x18000d81f  jz      loc_18000DCB2
0x18000d825  shr     ebx, 1
0x18000d827  mov     rdx, rax; lpszVolumePathName
0x18000d82a  mov     r8d, ebx; cchBufferLength
0x18000d82d  mov     rcx, r12; lpszFileName
0x18000d830  call    cs:__imp_GetVolumePathNameW
0x18000d836  test    eax, eax
0x18000d838  jnz     short loc_18000D847
0x18000d83a  call    cs:__imp_GetLastError
0x18000d840  mov     ebx, eax
0x18000d842  jmp     loc_18000DCB7
0x18000d847  mov     rcx, [rsp+360h+lpRootPathName]; lpRootPathName
0x18000d84c  call    cs:__imp_GetDriveTypeW
0x18000d852  mov     rcx, gs:60h
0x18000d85b  xor     edx, edx; Flags
0x18000d85d  mov     r8, [rsp+360h+lpRootPathName]; P
0x18000d862  mov     ebx, eax
0x18000d864  mov     rcx, [rcx+30h]; HeapHandle
0x18000d868  call    cs:__imp_RtlFreeHeap
0x18000d86e  mov     [rsp+360h+lpRootPathName], rsi
0x18000d873  cmp     ebx, 4
0x18000d876  jz      loc_18000D9A1
0x18000d87c  xor     r14d, r14d
0x18000d87f  mov     [rsp+360h+var_2F8], 1E0000h
0x18000d887  lea     rax, [rsp+360h+DosPathName]
0x18000d88c  mov     [rsp+360h+DosPathName], r14
0x18000d891  lea     r9, [rbp+260h+var_2D0]
0x18000d895  mov     qword ptr [rbp+260h+var_2D0], r14
0x18000d899  lea     r8, [rsp+360h+var_2F8]
0x18000d89e  mov     qword ptr [rsp+360h+dwCreationDisposition], rax
0x18000d8a3  lea     rcx, [r14-6]
0x18000d8a7  mov     edi, r14d
0x18000d8aa  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z
0x18000d8af  or      eax, 10000000h
0x18000d8b4  jl      loc_18000D971
0x18000d8ba  cmp     [rsp+360h+var_2F8], 1E0001h
0x18000d8c2  jnz     loc_18000D971
0x18000d8c8  mov     [rsp+360h+hTemplateFile], r14; hTemplateFile
0x18000d8cd  lea     r8d, [r14+1]; dwShareMode
0x18000d8d1  mov     [rsp+360h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000d8d9  xor     r9d, r9d; lpSecurityAttributes
0x18000d8dc  mov     edx, 80h; dwDesiredAccess
0x18000d8e1  mov     [rsp+360h+dwCreationDisposition], 3; dwCreationDisposition
0x18000d8e9  mov     rcx, r12; lpFileName
0x18000d8ec  call    cs:__imp_CreateFileW
0x18000d8f2  mov     [rsp+360h+hFile], rax
0x18000d8f7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d8fb  jz      short loc_18000D971
0x18000d8fd  xor     r9d, r9d; dwFlags
0x18000d900  xor     r8d, r8d; cchFilePath
0x18000d903  xor     edx, edx; lpszFilePath
0x18000d905  mov     rcx, rax; hFile
0x18000d908  call    cs:__imp_GetFinalPathNameByHandleW
0x18000d90e  mov     ebx, eax
0x18000d910  test    eax, eax
0x18000d912  jz      loc_18000D83A
0x18000d918  mov     rcx, gs:60h
0x18000d921  mov     r8d, ebx
0x18000d924  add     r8, r8; Size
0x18000d927  xor     edx, edx; Flags
0x18000d929  mov     rcx, [rcx+30h]; HeapHandle
0x18000d92d  call    cs:__imp_RtlAllocateHeap
0x18000d933  mov     [rbp+260h+P], rax
0x18000d937  mov     r13, rax
0x18000d93a  test    rax, rax
0x18000d93d  jz      loc_18000DCB2
0x18000d943  mov     rcx, [rsp+360h+hFile]; hFile
0x18000d948  xor     r9d, r9d; dwFlags
0x18000d94b  mov     r8d, ebx; cchFilePath
0x18000d94e  mov     rdx, rax; lpszFilePath
0x18000d951  call    cs:__imp_GetFinalPathNameByHandleW
0x18000d957  mov     edi, eax
0x18000d959  test    eax, eax
0x18000d95b  jz      loc_18000D83A
0x18000d961  mov     rcx, [rsp+360h+hFile]; hObject
0x18000d966  call    cs:__imp_CloseHandle
0x18000d96c  mov     [rsp+360h+hFile], r14
0x18000d971  mov     r9, [rbp+260h+var_2E0]; unsigned __int16 **
0x18000d975  test    r13, r13
0x18000d978  mov     r8, [rbp+260h+var_2D8]; unsigned __int16 **
0x18000d97c  cmovz   edi, [rbp+260h+var_2C8]
0x18000d980  cmovnz  r12, r13
0x18000d984  mov     edx, edi; unsigned int
0x18000d986  mov     rcx, r12; unsigned __int16 *
0x18000d989  call    ?EfspGetFullNameLocal@@YAKPEBGKPEAPEAG1@Z
0x18000d98e  mov     ebx, eax
0x18000d990  test    r15, r15
0x18000d993  jz      loc_18000DCB7
0x18000d999  mov     [r15], r14d
0x18000d99c  jmp     loc_18000DCB7
0x18000d9a1  mov     ebx, [rbp+260h+arg_28]
0x18000d9a7  xor     r15d, r15d
0x18000d9aa  test    r14b, 1
0x18000d9ae  jnz     short loc_18000D9F2
0x18000d9b0  test    ebx, ebx
0x18000d9b2  jnz     short loc_18000D9F2
0x18000d9b4  mov     [rsp+360h+hTemplateFile], r15; hTemplateFile
0x18000d9b9  lea     r8d, [rbx+1]; dwShareMode
0x18000d9bd  mov     [rsp+360h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000d9c5  xor     r9d, r9d; lpSecurityAttributes
0x18000d9c8  mov     edx, 80h; dwDesiredAccess
0x18000d9cd  mov     [rsp+360h+dwCreationDisposition], 3; dwCreationDisposition
0x18000d9d5  mov     rcx, r12; lpFileName
0x18000d9d8  call    cs:__imp_CreateFileW
0x18000d9de  mov     [rsp+360h+hFile], rax
0x18000d9e3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d9e7  jnz     loc_18000DB8B
0x18000d9ed  jmp     loc_18000D83A
0x18000d9f2  mov     rcx, r12; lpFileName
0x18000d9f5  call    cs:__imp_GetFileAttributesW
0x18000d9fb  or      r12d, 0FFFFFFFFh
0x18000d9ff  mov     r13d, eax
0x18000da02  test    ebx, ebx
0x18000da04  jz      short loc_18000DA6E
0x18000da06  cmp     eax, r12d
0x18000da09  jz      short loc_18000DA45
0x18000da0b  test    rdi, rdi
0x18000da0e  jz      short loc_18000DA1F
0x18000da10  cmp     dword ptr [rdi], 1
0x18000da13  jnz     short loc_18000DA1F
0x18000da15  mov     ebx, 50h ; 'P'
0x18000da1a  jmp     loc_18000DCB7
0x18000da1f  mov     edi, r15d
0x18000da22  test    r13b, 10h
0x18000da26  jz      short loc_18000DA3D
0x18000da28  test    r14b, 2
0x18000da2c  jnz     short loc_18000DA38
0x18000da2e  mov     ebx, 215Ch
0x18000da33  jmp     loc_18000DCB7
0x18000da38  mov     edi, 1
0x18000da3d  mov     r15d, 1
0x18000da43  jmp     short loc_18000DABE
0x18000da45  mov     r15d, 2
0x18000da4b  test    rdi, rdi
0x18000da4e  jz      short loc_18000DA58
0x18000da50  cmp     dword ptr [rdi], 1
0x18000da53  jnz     short loc_18000DA58
0x18000da55  mov     [rdi], r15d
0x18000da58  test    r15b, r14b
0x18000da5b  jz      short loc_18000DA67
0x18000da5d  mov     edi, 1
0x18000da62  or      ebx, 10h
0x18000da65  jmp     short loc_18000DABE
0x18000da67  mov     edi, 8000h
0x18000da6c  jmp     short loc_18000DABE
0x18000da6e  and     r14d, 2
0x18000da72  cmp     r13d, r12d
0x18000da75  jnz     short loc_18000DA9D
0x18000da77  mov     eax, r14d
0x18000da7a  mov     r15d, 2
0x18000da80  neg     eax
0x18000da82  sbb     edi, edi
0x18000da84  and     edi, 0FFFF8001h
0x18000da8a  add     edi, 0C000h
0x18000da90  neg     r14d
0x18000da93  sbb     ebx, ebx
0x18000da95  and     ebx, 10h
0x18000da98  sub     ebx, 0FFFFFF80h
0x18000da9b  jmp     short loc_18000DABE
0x18000da9d  mov     r15d, 1
0x18000daa3  test    r14d, r14d
0x18000daa6  jz      short loc_18000DAB4
0x18000daa8  mov     edi, 4001h
0x18000daad  mov     ebx, 90h
0x18000dab2  jmp     short loc_18000DABE
0x18000dab4  mov     ebx, 80h
0x18000dab9  mov     edi, 4000h
0x18000dabe  mov     rcx, [rsp+360h+DosPathName]; DosPathName
0x18000dac3  lea     rdx, [rbp+260h+DestinationString]; NtPathName
0x18000dac7  xor     r9d, r9d; DirectoryInfo
0x18000daca  xor     r8d, r8d; NtFileNamePart
0x18000dacd  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000dad3  xor     ecx, ecx
0x18000dad5  test    al, al
0x18000dad7  jnz     short loc_18000DAE1
0x18000dad9  lea     ebx, [rcx+3]
0x18000dadc  jmp     loc_18000DCB7
0x18000dae1  and     ebx, 0FFFFBFFEh
0x18000dae7  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x18000daee  neg     [rbp+260h+arg_38]
0x18000daf4  mov     [rbp+260h+ObjectAttributes.RootDirectory], rcx
0x18000daf8  sbb     eax, eax
0x18000dafa  and     eax, 2
0x18000dafd  add     eax, 40h ; '@'
0x18000db00  mov     [rbp+260h+ObjectAttributes.Attributes], eax
0x18000db03  lea     rax, [rbp+260h+DestinationString]
0x18000db07  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x18000db0b  mov     rax, [rbp+260h+var_2A8]
0x18000db0f  test    rax, rax
0x18000db12  jz      short loc_18000DB1E
0x18000db14  mov     rax, [rax+8]
0x18000db18  mov     [rbp+260h+ObjectAttributes.SecurityDescriptor], rax
0x18000db1c  jmp     short loc_18000DB22
0x18000db1e  mov     [rbp+260h+ObjectAttributes.SecurityDescriptor], rcx
0x18000db22  mov     [rsp+360h+EaLength], ecx; EaLength
0x18000db26  lea     r9, [rbp+260h+IoStatusBlock]; IoStatusBlock
0x18000db2a  mov     [rsp+360h+EaBuffer], rcx; EaBuffer
0x18000db2f  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x18000db33  mov     [rsp+360h+CreateOptions], edi; CreateOptions
0x18000db37  mov     edx, 100100h; DesiredAccess
0x18000db3c  mov     [rsp+360h+CreateDisposition], r15d; CreateDisposition
0x18000db41  xor     r15d, r15d
0x18000db44  mov     dword ptr [rsp+360h+hTemplateFile], r15d; ShareAccess
0x18000db49  mov     [rbp+260h+ObjectAttributes.SecurityQualityOfService], rcx
0x18000db4d  lea     rcx, [rsp+360h+hFile]; FileHandle
0x18000db52  mov     [rsp+360h+dwFlagsAndAttributes], ebx; FileAttributes
0x18000db56  mov     qword ptr [rsp+360h+dwCreationDisposition], r15; AllocationSize
0x18000db5b  call    cs:__imp_NtCreateFile
0x18000db61  test    eax, eax
0x18000db63  jns     short loc_18000DB72
0x18000db65  mov     ecx, eax; Status
0x18000db67  call    cs:__imp_RtlNtStatusToDosError
0x18000db6d  jmp     loc_18000D840
0x18000db72  cmp     r13d, r12d
0x18000db75  mov     r12, [rsp+360h+DosPathName]
0x18000db7a  jnz     short loc_18000DB8B
0x18000db7c  mov     rax, [rbp+260h+var_2A0]
0x18000db80  test    rax, rax
0x18000db83  jz      short loc_18000DB8B
0x18000db85  mov     dword ptr [rax], 1
0x18000db8b  lea     rsi, [rbp+260h+FileInformation]
0x18000db8f  mov     edi, 210h
0x18000db94  mov     r13d, 0C0000023h
0x18000db9a  mov     rcx, [rsp+360h+hFile]; FileHandle
0x18000db9f  lea     rdx, [rbp+260h+IoStatusBlock]; IoStatusBlock
0x18000dba3  mov     r9d, edi; Length
0x18000dba6  mov     [rsp+360h+dwCreationDisposition], 31h ; '1'; FileInformationClass
  ... truncated ...
```
