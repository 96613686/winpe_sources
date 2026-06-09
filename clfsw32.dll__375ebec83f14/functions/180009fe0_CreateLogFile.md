# CreateLogFile

- ea: `0x180009fe0`
- end: `0x18000a7d0`
- name: `CreateLogFile`
- size: `2032`
- prototype: `HANDLE __stdcall(LPCWSTR pszLogFileName, ACCESS_MASK fDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES psaLogFile, ULONG fCreateDisposition, ULONG fFlagsAndAttributes)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a9c0`
- `0x18000aec0`
- `0x18000d9b0`

## callees

- `0x1800018a4`
- `0x1800026c6`
- `0x180008674`
- `0x180009fe0`
- `0x18000dad4`
- `0x180014db6`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a36a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a71f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001537e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a36a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a71f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001537e`
- `ntdll!NtCreateFile` at `0x18000a5bd`
- `ntdll!NtCreateFile` at `0x18000a6ba`
- `ntdll!NtCreateFile` at `0x18000a5bd`
- `ntdll!NtCreateFile` at `0x18000a6ba`
- `ntdll!RtlNtStatusToDosError` at `0x18000a5cb`
- `ntdll!RtlNtStatusToDosError` at `0x18000a6c8`
- `ntdll!RtlNtStatusToDosError` at `0x18000a5cb`
- `ntdll!RtlNtStatusToDosError` at `0x18000a6c8`
- `ntdll!RtlFreeHeap` at `0x18000a746`
- `ntdll!RtlFreeHeap` at `0x1800153af`
- `ntdll!RtlFreeHeap` at `0x18000a746`
- `ntdll!RtlFreeHeap` at `0x1800153af`
- `ntdll!NtClose` at `0x18000a76e`
- `ntdll!NtClose` at `0x1800153d9`
- `ntdll!NtClose` at `0x18000a76e`
- `ntdll!NtClose` at `0x1800153d9`
- `ntdll!RtlPrefixUnicodeString` at `0x18000a236`
- `ntdll!RtlPrefixUnicodeString` at `0x18000a261`
- `ntdll!RtlPrefixUnicodeString` at `0x18000a293`
- `ntdll!RtlPrefixUnicodeString` at `0x18000a236`
- `ntdll!RtlPrefixUnicodeString` at `0x18000a261`
- `ntdll!RtlPrefixUnicodeString` at `0x18000a293`
- `ntdll!RtlInitUnicodeString` at `0x18000a140`
- `ntdll!RtlInitUnicodeString` at `0x18000a1c6`
- `ntdll!RtlInitUnicodeString` at `0x18000a1e1`
- `ntdll!RtlInitUnicodeString` at `0x18000a1fc`
- `ntdll!RtlInitUnicodeString` at `0x18000a217`
- `ntdll!RtlInitUnicodeString` at `0x18000a140`
- `ntdll!RtlInitUnicodeString` at `0x18000a1c6`
- `ntdll!RtlInitUnicodeString` at `0x18000a1e1`
- `ntdll!RtlInitUnicodeString` at `0x18000a1fc`
- `ntdll!RtlInitUnicodeString` at `0x18000a217`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18000a32e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18000a32e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000a40b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000a434`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000a40b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000a434`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a3a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a77c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a7a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a3a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a77c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a7a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153e9`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000a0b0`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000a0b0`

## pseudocode

```c
HANDLE __stdcall CreateLogFile(
        LPCWSTR pszLogFileName,
        ACCESS_MASK fDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES psaLogFile,
        ULONG fCreateDisposition,
        ULONG fFlagsAndAttributes)
{
  void *lpSecurityDescriptor; // rcx
  DWORD v9; // ecx
  DWORD v10; // edi
  char v11; // r14
  WCHAR *v12; // r12
  ULONG v13; // esi
  int v14; // r13d
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  size_t v18; // rbx
  unsigned __int64 v19; // rax
  size_t v20; // rbx
  int v21; // eax
  unsigned __int64 v22; // r13
  unsigned __int64 v23; // rax
  WCHAR *v24; // rax
  UNICODE_STRING *p_Source; // rdx
  ULONG v27; // eax
  ACCESS_MASK v28; // edx
  ULONG v29; // ebx
  ACCESS_MASK v30; // edx
  NTSTATUS v31; // eax
  int v32; // esi
  int v33; // ecx
  NTSTATUS v34; // eax
  __int64 v35; // [rsp+0h] [rbp-198h] BYREF
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-178h]
  ULONG FileAttributes[2]; // [rsp+28h] [rbp-170h]
  ULONG ShareAccess; // [rsp+30h] [rbp-168h]
  ULONG CreateDisposition; // [rsp+38h] [rbp-160h]
  ULONG CreateOptions; // [rsp+40h] [rbp-158h]
  PVOID EaBuffer; // [rsp+48h] [rbp-150h]
  ULONG EaLength; // [rsp+50h] [rbp-148h]
  int v43; // [rsp+60h] [rbp-138h]
  int v44; // [rsp+64h] [rbp-134h]
  ULONG v45; // [rsp+68h] [rbp-130h]
  ACCESS_MASK v46; // [rsp+6Ch] [rbp-12Ch]
  struct _UNICODE_STRING NtName; // [rsp+70h] [rbp-128h] BYREF
  void *FileHandle; // [rsp+80h] [rbp-118h] BYREF
  void *v49; // [rsp+88h] [rbp-110h] BYREF
  WCHAR *v50; // [rsp+90h] [rbp-108h]
  UNICODE_STRING String2; // [rsp+98h] [rbp-100h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+A8h] [rbp-F0h] BYREF
  struct _UNICODE_STRING v53; // [rsp+B8h] [rbp-E0h] BYREF
  void *v54; // [rsp+C8h] [rbp-D0h]
  UNICODE_STRING v55; // [rsp+D0h] [rbp-C8h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-B8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+120h] [rbp-78h] BYREF
  UNICODE_STRING String1; // [rsp+130h] [rbp-68h] BYREF
  UNICODE_STRING v60; // [rsp+140h] [rbp-58h] BYREF
  UNICODE_STRING Source; // [rsp+150h] [rbp-48h] BYREF
  __int64 *v62; // [rsp+160h] [rbp-38h]
  char v63; // [rsp+1A0h] [rbp+8h]

  v62 = &v35;
  v46 = fDesiredAccess;
  IoStatusBlock.Pointer = 0;
  IoStatusBlock.Information = 0;
  v49 = (void *)-1LL;
  FileHandle = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  *(_QWORD *)&NtName.Length = 0;
  NtName.Buffer = 0;
  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  *(_QWORD *)&v53.Length = 0;
  v53.Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !pszLogFileName )
    goto LABEL_80;
  v54 = 0;
  if ( !psaLogFile )
    goto LABEL_7;
  if ( psaLogFile->nLength < 0x18
    || (lpSecurityDescriptor = psaLogFile->lpSecurityDescriptor) != 0
    && !IsValidSecurityDescriptor(lpSecurityDescriptor) )
  {
LABEL_80:
    v9 = 87;
    goto LABEL_81;
  }
  v54 = psaLogFile->lpSecurityDescriptor;
LABEL_7:
  switch ( fCreateDisposition )
  {
    case 1u:
      v45 = 2;
      v10 = 3;
      break;
    case 3u:
      v11 = 1;
      v45 = 1;
      v10 = 3;
      goto LABEL_15;
    case 4u:
      v10 = 3;
      v45 = 3;
      break;
    default:
      v9 = 50;
LABEL_81:
      SetLastError(v9);
      return (HANDLE)-1LL;
  }
  v11 = 1;
LABEL_15:
  v43 = 0;
  v12 = 0;
  v50 = 0;
  v13 = 32772;
  RtlInitUnicodeString(&DestinationString, pszLogFileName);
  if ( !ClfsTokenizeStreamNames(&DestinationString, &String2, &v53) )
  {
    v9 = 1921;
    goto LABEL_81;
  }
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = 0;
  *(_QWORD *)&v55.Length = 0;
  v55.Buffer = 0;
  *(_QWORD *)&v60.Length = 0;
  v60.Buffer = 0;
  *(_QWORD *)&Source.Length = 0;
  Source.Buffer = 0;
  RtlInitUnicodeString(&String1, L"\\??\\LOG:");
  RtlInitUnicodeString(&v55, L"\\CLFS");
  RtlInitUnicodeString(&v60, L"LOG:");
  RtlInitUnicodeString(&Source, L"\\GLOBAL??\\LOG:");
  if ( RtlPrefixUnicodeString(&String1, &String2, 1u) )
  {
    v14 = 8;
  }
  else
  {
    if ( RtlPrefixUnicodeString(&v55, &String2, 1u) )
    {
      v63 = 0;
      v14 = 5;
      goto LABEL_24;
    }
    if ( !RtlPrefixUnicodeString(&v60, &String2, 1u) )
    {
      v10 = 1921;
      v43 = 1921;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_slSl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          v16,
          v17,
          (_DWORD)AllocationSize,
          (__int64)pszLogFileName,
          129);
      }
      goto LABEL_70;
    }
    v14 = 4;
  }
  v63 = 1;
LABEL_24:
  v18 = (String2.Length >> 1) - v14;
  v19 = 2LL * (unsigned int)(v18 + 1);
  if ( !is_mul_ok((unsigned int)(v18 + 1), 2u) )
    v19 = -1;
  v12 = (WCHAR *)operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
  v50 = v12;
  if ( v12 )
  {
    v20 = v18;
    memcpy_0(v12, &String2.Buffer[v14], v20 * 2);
    v12[v20] = 0;
    if ( RtlDosPathNameToRelativeNtPathName_U(v12, &NtName, 0, 0) )
    {
      v21 = NtName.Length >> 1;
      if ( v63 )
        v22 = (unsigned int)(v21 + 15);
      else
        v22 = (unsigned int)(v21 + v14 + 1);
      operator delete[](v12);
      v23 = 2 * v22;
      if ( !is_mul_ok(v22, 2u) )
        v23 = -1;
      v24 = (WCHAR *)operator new[](v23, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v24;
      v50 = v24;
      if ( !v24 )
      {
        SetLastError(0xEu);
        local_unwind_0(v62, &loc_18000A3C7);
        return (HANDLE)-1LL;
      }
      Destination.Buffer = v24;
      Destination.Length = 0;
      Destination.MaximumLength = 2 * v22;
      p_Source = &v55;
      if ( v63 )
        p_Source = &Source;
      if ( !RtlAppendUnicodeStringToString(&Destination, p_Source)
        && !RtlAppendUnicodeStringToString(&Destination, &NtName) )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = &Destination;
        ObjectAttributes.SecurityDescriptor = v54;
        ObjectAttributes.SecurityQualityOfService = 0;
        if ( v53.Length )
        {
          if ( (fFlagsAndAttributes & 0x20000000) != 0 )
            v13 = 32780;
          v44 = v13;
          v29 = v45;
          if ( v45 == 1 )
          {
            EaLength = 0;
            EaBuffer = 0;
            CreateOptions = v13;
            CreateDisposition = 1;
            v30 = 0x80000000;
          }
          else
          {
            if ( v45 - 2 >= 2 )
            {
              v10 = 50;
              goto LABEL_28;
            }
            EaLength = 0;
            EaBuffer = 0;
            CreateOptions = v13;
            CreateDisposition = 3;
            v30 = -1073741824;
          }
          v31 = NtCreateFile(
                  &FileHandle,
                  v30,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  fFlagsAndAttributes & 0x20 | 0x80,
                  7u,
                  CreateDisposition,
                  CreateOptions,
                  EaBuffer,
                  EaLength);
          v10 = RtlNtStatusToDosError(v31);
          v43 = v10;
          if ( v10 )
            goto LABEL_70;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = FileHandle;
          ObjectAttributes.Attributes = 66;
          ObjectAttributes.ObjectName = &v53;
          ObjectAttributes.SecurityDescriptor = v54;
          ObjectAttributes.SecurityQualityOfService = 0;
          v32 = v13 | 0x40;
          v44 = v32;
          if ( (fFlagsAndAttributes & 0x20000000) != 0 )
          {
            v32 |= 8u;
            v44 = v32;
          }
          if ( (fFlagsAndAttributes & 0x40000000) != 0 )
          {
            v33 = v46;
          }
          else
          {
            v32 |= 0x20u;
            v44 = v32;
            v33 = v46 | 0x100000;
          }
          EaLength = 0;
          EaBuffer = 0;
          CreateOptions = v32 | 0x40;
          CreateDisposition = v29;
          ShareAccess = dwShareMode;
          FileAttributes[0] = fFlagsAndAttributes & 0x9FFFFEFF | 0x100;
          v28 = v33;
        }
        else
        {
          v27 = 32836;
          v44 = 32836;
          if ( (fFlagsAndAttributes & 0x40000000) != 0 )
          {
            v11 = 0;
          }
          else
          {
            v27 = 32868;
            v44 = 32868;
          }
          v28 = v46 | 0x100000;
          if ( !v11 )
            v28 = v46;
          if ( (fFlagsAndAttributes & 0x20000000) != 0 )
          {
            v27 |= 8u;
            v44 = v27;
          }
          EaLength = 0;
          EaBuffer = 0;
          CreateOptions = v27;
          CreateDisposition = v45;
          ShareAccess = dwShareMode;
          FileAttributes[0] = fFlagsAndAttributes & 0x9FFFFEFF | 0x100;
        }
        v34 = NtCreateFile(
                &v49,
                v28,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                FileAttributes[0],
                ShareAccess,
                CreateDisposition,
                CreateOptions,
                EaBuffer,
                EaLength);
        v10 = RtlNtStatusToDosError(v34);
        v43 = v10;
        goto LABEL_70;
      }
      v10 = 1359;
    }
    v43 = v10;
    goto LABEL_70;
  }
  v10 = 14;
LABEL_28:
  v43 = v10;
LABEL_70:
  if ( v12 )
    operator delete[](v12);
  if ( NtName.Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtName.Buffer);
    NtName.Buffer = 0;
  }
  if ( FileHandle && v53.Length )
    NtClose(FileHandle);
  SetLastError(v10);
  if ( v10 )
    return (HANDLE)-1LL;
  return v49;
}

```

## disassembly

```asm
0x180009fe0  mov     rax, rsp
0x180009fe3  mov     [rax+10h], rbx
0x180009fe7  mov     [rax+20h], rsi
0x180009feb  mov     [rax+18h], r8d
0x180009fef  push    rdi
0x180009ff0  push    r12
0x180009ff2  push    r13
0x180009ff4  push    r14
0x180009ff6  push    r15
0x180009ff8  sub     rsp, 170h
0x180009fff  mov     [rsp+198h+var_38], rsp
0x18000a007  mov     rbx, r9
0x18000a00a  mov     [rsp+198h+var_12C], edx
0x18000a00e  mov     r13, rcx
0x18000a011  xor     edi, edi
0x18000a013  mov     [rax-0B8h], rdi
0x18000a01a  mov     [rax-0B0h], rdi
0x18000a021  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000a025  mov     [rax-110h], r15
0x18000a02c  mov     [rax-118h], rdi
0x18000a033  mov     [rax-78h], rdi
0x18000a037  mov     [rax-70h], rdi
0x18000a03b  mov     [rax-100h], rdi
0x18000a042  mov     [rax-0F8h], rdi
0x18000a049  mov     qword ptr [rsp+198h+NtName.Length], rdi
0x18000a04e  mov     [rsp+198h+NtName.Buffer], rdi
0x18000a053  mov     [rax-0F0h], rdi
0x18000a05a  mov     [rax-0E8h], rdi
0x18000a061  mov     [rax-0E0h], rdi
0x18000a068  mov     [rax-0D8h], rdi
0x18000a06f  xorps   xmm0, xmm0
0x18000a072  movups  xmmword ptr [rax-0A8h], xmm0
0x18000a079  movups  xmmword ptr [rax-98h], xmm0
0x18000a080  movups  xmmword ptr [rax-88h], xmm0
0x18000a087  test    rcx, rcx
0x18000a08a  jz      loc_18000A79E
0x18000a090  mov     [rsp+198h+var_D0], rdi
0x18000a098  test    rbx, rbx
0x18000a09b  jz      short loc_18000A0D0
0x18000a09d  cmp     dword ptr [r9], 18h
0x18000a0a1  jb      loc_18000A79E
0x18000a0a7  mov     rcx, [r9+8]; pSecurityDescriptor
0x18000a0ab  test    rcx, rcx
0x18000a0ae  jz      short loc_18000A0C4
0x18000a0b0  call    cs:__imp_IsValidSecurityDescriptor
0x18000a0b7  nop     dword ptr [rax+rax+00h]
0x18000a0bc  test    eax, eax
0x18000a0be  jz      loc_18000A79E
0x18000a0c4  mov     rax, [rbx+8]
0x18000a0c8  mov     [rsp+198h+var_D0], rax
0x18000a0d0  mov     ecx, [rsp+198h+fCreateDisposition]
0x18000a0d7  sub     ecx, 1
0x18000a0da  jz      short loc_18000A10C
0x18000a0dc  sub     ecx, 2
0x18000a0df  jz      short loc_18000A0FB
0x18000a0e1  cmp     ecx, 1
0x18000a0e4  jz      short loc_18000A0F0
0x18000a0e6  mov     ecx, 32h ; '2'
0x18000a0eb  jmp     loc_18000A7A3
0x18000a0f0  mov     edi, 3
0x18000a0f5  mov     [rsp+198h+var_130], edi
0x18000a0f9  jmp     short loc_18000A119
0x18000a0fb  mov     r14d, 1
0x18000a101  mov     [rsp+198h+var_130], r14d
0x18000a106  lea     edi, [r14+2]
0x18000a10a  jmp     short loc_18000A11F
0x18000a10c  mov     [rsp+198h+var_130], 2
0x18000a114  mov     edi, 3
0x18000a119  mov     r14d, 1
0x18000a11f  xor     ebx, ebx
0x18000a121  mov     [rsp+198h+var_138], ebx
0x18000a125  mov     r12d, ebx
0x18000a128  mov     [rsp+198h+var_108], rbx
0x18000a130  mov     esi, 8004h
0x18000a135  mov     rdx, r13; SourceString
0x18000a138  lea     rcx, [rsp+198h+DestinationString]; DestinationString
0x18000a140  call    cs:__imp_RtlInitUnicodeString
0x18000a147  nop     dword ptr [rax+rax+00h]
0x18000a14c  lea     r8, [rsp+198h+var_E0]; PUNICODE_STRING
0x18000a154  lea     rdx, [rsp+198h+String2]; DestinationString
0x18000a15c  lea     rcx, [rsp+198h+DestinationString]; struct _UNICODE_STRING *
0x18000a164  call    ?ClfsTokenizeStreamNames@@YAEAEBU_UNICODE_STRING@@AEAU1@1@Z; ClfsTokenizeStreamNames(_UNICODE_STRING const &,_UNICODE_STRING &,_UNICODE_STRING &)
0x18000a169  test    al, al
0x18000a16b  jnz     short loc_18000A177
0x18000a16d  mov     ecx, 781h
0x18000a172  jmp     loc_18000A7A3
0x18000a177  mov     qword ptr [rsp+198h+String1.Length], rbx
0x18000a17f  mov     [rsp+198h+String1.Buffer], rbx
0x18000a187  mov     qword ptr [rsp+198h+var_C8.Length], rbx
0x18000a18f  mov     [rsp+198h+var_C8.Buffer], rbx
0x18000a197  mov     qword ptr [rsp+198h+var_58.Length], rbx
0x18000a19f  mov     [rsp+198h+var_58.Buffer], rbx
0x18000a1a7  mov     qword ptr [rsp+198h+Source.Length], rbx
0x18000a1af  mov     [rsp+198h+Source.Buffer], rbx
0x18000a1b7  lea     rdx, aLog; "\\??\\LOG:"
0x18000a1be  lea     rcx, [rsp+198h+String1]; DestinationString
0x18000a1c6  call    cs:__imp_RtlInitUnicodeString
0x18000a1cd  nop     dword ptr [rax+rax+00h]
0x18000a1d2  lea     rdx, aClfs; "\\CLFS"
0x18000a1d9  lea     rcx, [rsp+198h+var_C8]; DestinationString
0x18000a1e1  call    cs:__imp_RtlInitUnicodeString
0x18000a1e8  nop     dword ptr [rax+rax+00h]
0x18000a1ed  lea     rdx, aLog_0; "LOG:"
0x18000a1f4  lea     rcx, [rsp+198h+var_58]; DestinationString
0x18000a1fc  call    cs:__imp_RtlInitUnicodeString
0x18000a203  nop     dword ptr [rax+rax+00h]
0x18000a208  lea     rdx, aGlobalLog; "\\GLOBAL??\\LOG:"
0x18000a20f  lea     rcx, [rsp+198h+Source]; DestinationString
0x18000a217  call    cs:__imp_RtlInitUnicodeString
0x18000a21e  nop     dword ptr [rax+rax+00h]
0x18000a223  mov     r8b, r14b; CaseInsensitive
0x18000a226  lea     rdx, [rsp+198h+String2]; String2
0x18000a22e  lea     rcx, [rsp+198h+String1]; String1
0x18000a236  call    cs:__imp_RtlPrefixUnicodeString
0x18000a23d  nop     dword ptr [rax+rax+00h]
0x18000a242  test    al, al
0x18000a244  jz      short loc_18000A24E
0x18000a246  mov     r13d, 8
0x18000a24c  jmp     short loc_18000A2AD
0x18000a24e  mov     r8b, r14b; CaseInsensitive
0x18000a251  lea     rdx, [rsp+198h+String2]; String2
0x18000a259  lea     rcx, [rsp+198h+var_C8]; String1
0x18000a261  call    cs:__imp_RtlPrefixUnicodeString
0x18000a268  nop     dword ptr [rax+rax+00h]
0x18000a26d  test    al, al
0x18000a26f  jz      short loc_18000A280
0x18000a271  mov     byte ptr [rsp+198h+arg_0], bl
0x18000a278  mov     r13d, 5
0x18000a27e  jmp     short loc_18000A2B5
0x18000a280  mov     r8b, r14b; CaseInsensitive
0x18000a283  lea     rdx, [rsp+198h+String2]; String2
0x18000a28b  lea     rcx, [rsp+198h+var_58]; String1
0x18000a293  call    cs:__imp_RtlPrefixUnicodeString
0x18000a29a  nop     dword ptr [rax+rax+00h]
0x18000a29f  test    al, al
0x18000a2a1  jz      loc_18000A6DC
0x18000a2a7  mov     r13d, 4
0x18000a2ad  mov     byte ptr [rsp+198h+arg_0], r14b
0x18000a2b5  movzx   ebx, [rsp+198h+String2.Length]
0x18000a2bd  shr     ebx, 1
0x18000a2bf  sub     ebx, r13d
0x18000a2c2  lea     ecx, [rbx+1]
0x18000a2c5  mov     eax, 2
0x18000a2ca  mul     rcx
0x18000a2cd  cmovb   rax, r15
0x18000a2d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a2d8  mov     rcx, rax; unsigned __int64
0x18000a2db  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a2e0  mov     r12, rax
0x18000a2e3  mov     [rsp+198h+var_108], rax
0x18000a2eb  test    rax, rax
0x18000a2ee  jnz     short loc_18000A2FC
0x18000a2f0  lea     edi, [rax+0Eh]
0x18000a2f3  mov     [rsp+198h+var_138], edi
0x18000a2f7  jmp     loc_18000A715
0x18000a2fc  add     rbx, rbx
0x18000a2ff  mov     ecx, r13d
0x18000a302  mov     rax, [rsp+198h+String2.Buffer]
0x18000a30a  lea     rdx, [rax+rcx*2]; Src
0x18000a30e  mov     r8, rbx; Size
0x18000a311  mov     rcx, r12; void *
0x18000a314  call    memcpy_0
0x18000a319  xor     eax, eax
0x18000a31b  mov     [rbx+r12], ax
0x18000a320  xor     r9d, r9d; RelativeName
0x18000a323  xor     r8d, r8d; PartName
0x18000a326  lea     rdx, [rsp+198h+NtName]; NtName
0x18000a32b  mov     rcx, r12; DosName
0x18000a32e  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18000a335  nop     dword ptr [rax+rax+00h]
0x18000a33a  xor     ebx, ebx
0x18000a33c  test    al, al
0x18000a33e  jnz     short loc_18000A349
0x18000a340  mov     [rsp+198h+var_138], edi
0x18000a344  jmp     loc_18000A717
0x18000a349  movzx   eax, [rsp+198h+NtName.Length]
0x18000a34e  shr     eax, 1
0x18000a350  mov     bl, byte ptr [rsp+198h+arg_0]
0x18000a357  test    bl, bl
0x18000a359  jnz     short loc_18000A363
0x18000a35b  inc     r13d
0x18000a35e  add     r13d, eax
0x18000a361  jmp     short loc_18000A367
0x18000a363  lea     r13d, [rax+0Fh]
0x18000a367  mov     rcx, r12
0x18000a36a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a371  nop     dword ptr [rax+rax+00h]
0x18000a376  mov     eax, 2
0x18000a37b  mul     r13
0x18000a37e  cmovb   rax, r15
0x18000a382  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a389  mov     rcx, rax; unsigned __int64
0x18000a38c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000a391  mov     r12, rax
0x18000a394  mov     [rsp+198h+var_108], rax
0x18000a39c  xor     ecx, ecx
0x18000a39e  test    rax, rax
0x18000a3a1  jnz     short loc_18000A3D0
0x18000a3a3  lea     ecx, [rax+0Eh]; dwErrCode
0x18000a3a6  call    cs:__imp_SetLastError
0x18000a3ad  nop     dword ptr [rax+rax+00h]
0x18000a3b2  lea     rdx, loc_18000A3C7
0x18000a3b9  mov     rcx, [rsp+198h+var_38]
0x18000a3c1  call    _local_unwind_0
0x18000a3c6  nop
0x18000a3c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a3cb  jmp     loc_18000A7B2
0x18000a3d0  mov     [rsp+198h+Destination.Buffer], rax
0x18000a3d8  mov     [rsp+198h+Destination.Length], cx
0x18000a3e0  add     r13w, r13w
0x18000a3e4  mov     [rsp+198h+Destination.MaximumLength], r13w
0x18000a3ed  lea     rdx, [rsp+198h+var_C8]
0x18000a3f5  lea     rax, [rsp+198h+Source]
0x18000a3fd  test    bl, bl
0x18000a3ff  cmovnz  rdx, rax; Source
0x18000a403  lea     rcx, [rsp+198h+Destination]; Destination
0x18000a40b  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000a412  nop     dword ptr [rax+rax+00h]
0x18000a417  xor     ebx, ebx
0x18000a419  test    eax, eax
0x18000a41b  jz      short loc_18000A427
0x18000a41d  mov     edi, 54Fh
0x18000a422  jmp     loc_18000A340
0x18000a427  lea     rdx, [rsp+198h+NtName]; Source
0x18000a42c  lea     rcx, [rsp+198h+Destination]; Destination
0x18000a434  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000a43b  nop     dword ptr [rax+rax+00h]
0x18000a440  test    eax, eax
0x18000a442  jnz     short loc_18000A41D
0x18000a444  mov     [rsp+198h+ObjectAttributes.Length], 30h ; '0'
0x18000a44f  mov     [rsp+198h+ObjectAttributes.RootDirectory], rbx
0x18000a457  mov     [rsp+198h+ObjectAttributes.Attributes], 40h ; '@'
0x18000a462  lea     rax, [rsp+198h+Destination]
0x18000a46a  mov     [rsp+198h+ObjectAttributes.ObjectName], rax
0x18000a472  mov     rax, [rsp+198h+var_D0]
0x18000a47a  mov     [rsp+198h+ObjectAttributes.SecurityDescriptor], rax
0x18000a482  mov     [rsp+198h+ObjectAttributes.SecurityQualityOfService], rbx
0x18000a48a  cmp     [rsp+198h+var_E0.Length], bx
0x18000a492  jnz     short loc_18000A510
0x18000a494  mov     eax, 8044h
0x18000a499  mov     [rsp+198h+var_134], eax
0x18000a49d  mov     r8d, [rsp+198h+fFlagsAndAttributes]
0x18000a4a5  bt      r8d, 1Eh
0x18000a4aa  jb      short loc_18000A4B7
0x18000a4ac  mov     eax, 8064h
0x18000a4b1  mov     [rsp+198h+var_134], eax
0x18000a4b5  jmp     short loc_18000A4BA
0x18000a4b7  mov     r14b, bl
0x18000a4ba  mov     edx, [rsp+198h+var_12C]
0x18000a4be  bts     edx, 14h
0x18000a4c2  test    r14b, r14b
0x18000a4c5  cmovz   edx, [rsp+198h+var_12C]
0x18000a4ca  mov     ecx, r8d
0x18000a4cd  and     ecx, 9FFFFFFFh
0x18000a4d3  bts     ecx, 8
0x18000a4d7  bt      r8d, 1Dh
0x18000a4dc  jnb     short loc_18000A4E5
0x18000a4de  or      eax, 8
0x18000a4e1  mov     [rsp+198h+var_134], eax
0x18000a4e5  mov     [rsp+198h+EaLength], ebx
0x18000a4e9  mov     [rsp+198h+EaBuffer], rbx
0x18000a4ee  mov     [rsp+198h+CreateOptions], eax
0x18000a4f2  mov     ebx, [rsp+198h+var_130]
0x18000a4f6  mov     [rsp+198h+CreateDisposition], ebx
0x18000a4fa  mov     r8d, [rsp+198h+arg_10]
0x18000a502  mov     [rsp+198h+ShareAccess], r8d
0x18000a507  mov     [rsp+198h+FileAttributes], ecx
0x18000a50b  jmp     loc_18000A69B
0x18000a510  mov     r13d, [rsp+198h+fFlagsAndAttributes]
0x18000a518  mov     ecx, r13d
0x18000a51b  and     ecx, 20h
0x18000a51e  bts     ecx, 7
0x18000a522  mov     eax, r13d
0x18000a525  and     eax, 20000000h
0x18000a52a  mov     [rsp+198h+arg_0], eax
0x18000a531  mov     eax, 800Ch
0x18000a536  cmovnz  esi, eax
0x18000a539  mov     [rsp+198h+var_134], esi
0x18000a53d  mov     ebx, [rsp+198h+var_130]
0x18000a541  mov     eax, ebx
0x18000a543  sub     eax, 1
0x18000a546  jz      short loc_18000A578
0x18000a548  sub     eax, 1
0x18000a54b  jz      short loc_18000A55C
0x18000a54d  sub     eax, 1
0x18000a550  jz      short loc_18000A55C
0x18000a552  mov     edi, 32h ; '2'
0x18000a557  jmp     loc_18000A2F3
0x18000a55c  xor     r14d, r14d
0x18000a55f  mov     [rsp+198h+EaLength], r14d
0x18000a564  mov     [rsp+198h+EaBuffer], r14
0x18000a569  mov     [rsp+198h+CreateOptions], esi
0x18000a56d  mov     [rsp+198h+CreateDisposition], edi
0x18000a571  mov     edx, 0C0000000h
0x18000a576  jmp     short loc_18000A594
0x18000a578  xor     eax, eax
0x18000a57a  mov     [rsp+198h+EaLength], eax; EaLength
0x18000a57e  mov     [rsp+198h+EaBuffer], rax; EaBuffer
0x18000a583  mov     [rsp+198h+CreateOptions], esi; CreateOptions
0x18000a587  mov     [rsp+198h+CreateDisposition], r14d; CreateDisposition
  ... truncated ...
```
