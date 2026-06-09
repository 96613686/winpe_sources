# CreateFileInternal

- ea: `0x1800533cc`
- end: `0x180053c28`
- name: `CreateFileInternal`
- size: `2140`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64, int)`
- caller_count: `11`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800123e0`
- `0x1800520d0`
- `0x180052e40`
- `0x180053330`
- `0x180053d00`
- `0x1800540a0`
- `0x1800836d0`
- `0x1800e7ec0`
- `0x1800ecc70`
- `0x1800fc530`
- `0x18018b2a0`

## callees

- `0x18004b9d0`
- `0x1800533cc`
- `0x1800f6d80`
- `0x18011a954`
- `0x18018b2c8`
- `0x18018d55c`
- `0x18018d67c`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlReleaseRelativeName` at `0x180053b45`
- `ntdll!RtlReleaseRelativeName` at `0x180053b45`
- `ntdll!NtQueryInformationFile` at `0x1800536d7`
- `ntdll!NtQueryInformationFile` at `0x1800536d7`
- `ntdll!SbSelectProcedure` at `0x180053935`
- `ntdll!SbSelectProcedure` at `0x180053935`
- `ntdll!NtSetInformationFile` at `0x180053abb`
- `ntdll!NtSetInformationFile` at `0x180053b08`
- `ntdll!NtSetInformationFile` at `0x180053abb`
- `ntdll!NtSetInformationFile` at `0x180053b08`
- `ntdll!NtCreateFile` at `0x1800539d6`
- `ntdll!NtCreateFile` at `0x180053a49`
- `ntdll!NtCreateFile` at `0x1800539d6`
- `ntdll!NtCreateFile` at `0x180053a49`
- `ntdll!RtlSetLastWin32Error` at `0x1800534a6`
- `ntdll!RtlSetLastWin32Error` at `0x180053592`
- `ntdll!RtlSetLastWin32Error` at `0x180053b1c`
- `ntdll!RtlSetLastWin32Error` at `0x180053bef`
- `ntdll!RtlSetLastWin32Error` at `0x1800534a6`
- `ntdll!RtlSetLastWin32Error` at `0x180053592`
- `ntdll!RtlSetLastWin32Error` at `0x180053b1c`
- `ntdll!RtlSetLastWin32Error` at `0x180053bef`
- `ntdll!NtQueryEaFile` at `0x18005384f`
- `ntdll!NtQueryEaFile` at `0x18005384f`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005351b`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005351b`
- `ntdll!NtClose` at `0x180053acc`
- `ntdll!NtClose` at `0x180053b32`
- `ntdll!NtClose` at `0x180053acc`
- `ntdll!NtClose` at `0x180053b32`
- `ntdll!RtlFreeHeap` at `0x180053874`
- `ntdll!RtlFreeHeap` at `0x180053b64`
- `ntdll!RtlFreeHeap` at `0x180053b87`
- `ntdll!RtlFreeHeap` at `0x180053874`
- `ntdll!RtlFreeHeap` at `0x180053b64`
- `ntdll!RtlFreeHeap` at `0x180053b87`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18005356d`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18005356d`
- `ntdll!RtlAllocateHeap` at `0x180053810`
- `ntdll!RtlAllocateHeap` at `0x180053810`

## pseudocode

```c
__int64 __fastcall CreateFileInternal(PCWSTR SourceString, int a2, ULONG a3, int a4, __int64 a5, char a6)
{
  int v7; // esi
  unsigned int v8; // edi
  ULONG v10; // r12d
  NTSTATUS inited; // eax
  HANDLE ContainingDirectory; // rax
  int v13; // r14d
  int v14; // edx
  int v15; // esi
  unsigned int v16; // ecx
  __int64 v17; // rcx
  void *EaBuffer; // rsi
  ULONG EaLength; // r13d
  char *v20; // rcx
  ULONG v21; // r14d
  int IsEnabledDeviceUsageNoInline; // eax
  ULONG v23; // r8d
  ULONG v24; // r8d
  int v25; // r15d
  PVOID Heap; // rax
  NTSTATUS v27; // r15d
  NTSTATUS v28; // ebx
  __int64 ProcessSwitchContext; // rax
  BOOL v30; // edi
  void (__fastcall *v31)(ULONG *); // rax
  ACCESS_MASK v32; // r14d
  ULONG v33; // eax
  int v34; // eax
  ULONG v35; // ecx
  ULONG v36; // ecx
  bool v37; // [rsp+60h] [rbp-A0h]
  ULONG CreateOptions; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG FileAttributes; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+74h] [rbp-8Ch] BYREF
  int v42; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  ULONG FileInformation; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+94h] [rbp-6Ch]
  ULONG ShareAccess; // [rsp+98h] [rbp-68h]
  int v47; // [rsp+9Ch] [rbp-64h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp-48h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-20h] BYREF
  PVOID P; // [rsp+110h] [rbp+10h]
  __int64 v54; // [rsp+118h] [rbp+18h] BYREF
  int v55; // [rsp+120h] [rbp+20h]
  int v56; // [rsp+198h] [rbp+98h]

  v41 = a4;
  ShareAccess = a3;
  v42 = a2;
  CreateOptions = 0;
  v49 = 0;
  FileInformation = 0;
  v54 = 0;
  v55 = 0;
  FileHandle = (HANDLE)-1LL;
  Handle = (HANDLE)-1LL;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( a5 )
  {
    if ( *(_DWORD *)a5 < 0x20u )
    {
LABEL_19:
      BaseSetLastNTError(3221225485LL);
      return -1;
    }
    v7 = *(_DWORD *)(a5 + 12);
    v8 = *(_DWORD *)(a5 + 8);
    FileAttributes = *(_DWORD *)(a5 + 4);
  }
  else
  {
    v7 = 0;
    FileAttributes = 0;
    v8 = 0;
  }
  if ( (a6 & 3) != 0 )
  {
    v37 = 0;
  }
  else
  {
    v37 = (v8 & 0x10000) != 0;
    if ( (v8 & 0x10000) != 0 )
    {
      if ( !a2 || (a3 & 4) != 0 )
      {
        RtlSetLastWin32Error(0xA0u);
        return -1;
      }
    }
    else
    {
      v37 = 0;
    }
  }
  if ( a4 == 1 )
  {
    v10 = 2;
  }
  else if ( a4 == 2 )
  {
    v10 = 5;
  }
  else
  {
    if ( a4 != 3 )
    {
      if ( a4 == 4 )
      {
        v10 = 3;
        goto LABEL_24;
      }
      if ( a4 != 5 || (a2 & 0x40000000) == 0 )
        goto LABEL_19;
    }
    v10 = 1;
  }
LABEL_24:
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited < 0 )
    goto LABEL_25;
  if ( DestinationString.Length <= 1u
    || (v47 = 1, SourceString[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92) )
  {
    v47 = 0;
  }
  CreateOptions = 0;
  inited = RtlDosPathNameToRelativeNtPathName_U_WithStatus(SourceString, &DestinationString, 0, &RelativeName);
  if ( inited < 0 )
  {
    if ( inited != -1073741801 && inited != -1073741670 )
    {
      RtlSetLastWin32Error(3u);
      return -1;
    }
LABEL_25:
    BaseSetLastNTError((unsigned int)inited);
    return -1;
  }
  P = DestinationString.Buffer;
  if ( RelativeName.RelativeName.Length )
  {
    DestinationString = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  v13 = v8 & 0x1000000;
  ObjectAttributes.Length = 48;
  v45 = v8 & 0x1000000;
  ObjectAttributes.SecurityDescriptor = 0;
  v14 = (v8 >> 6) & 0x800;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = v14 | ((v8 & 0x1000000) == 0 ? 0x40 : 0);
  if ( (v7 & 0x100000) != 0 )
  {
    v15 = v7 & 0xF0000;
    LOBYTE(v55) = (v15 & 0x40000) != 0;
    v16 = v15 & 0xFFFBFFFF;
    if ( (v15 & 0x40000) == 0 )
      v16 = v15;
    if ( (v16 & 0x80000) != 0 )
    {
      BYTE1(v55) = 1;
      v16 &= ~0x80000u;
    }
    else
    {
      BYTE1(v55) = 0;
    }
    HIDWORD(v54) = HIWORD(v16);
  }
  else
  {
    LOWORD(v55) = 257;
    HIDWORD(v54) = 2;
  }
  LODWORD(v54) = 12;
  ObjectAttributes.SecurityQualityOfService = &v54;
  if ( a5
    && (v17 = *(_QWORD *)(a5 + 16)) != 0
    && (ObjectAttributes.SecurityDescriptor = *(PVOID *)(v17 + 8), *(_DWORD *)(v17 + 16)) )
  {
    EaBuffer = 0;
    EaLength = 0;
    ObjectAttributes.Attributes = v14 | (v13 != 0 ? 2 : 66);
  }
  else
  {
    EaBuffer = 0;
    EaLength = 0;
    if ( !a5 )
      goto LABEL_54;
  }
  v20 = *(char **)(a5 + 24);
  if ( (unsigned __int64)(v20 - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || NtQueryInformationFile(v20, &IoStatusBlock, &FileInformation, 4u, FileEaInformation) < 0 )
  {
LABEL_54:
    IsEnabledDeviceUsageNoInline = Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline();
    v23 = CreateOptions;
    if ( IsEnabledDeviceUsageNoInline )
      v23 = ((v8 & 0x8000) << 14) | CreateOptions;
    v24 = ((v8 & 0x2000000) != 0 ? 0x4000 : 0)
        | ~(v8 >> 25) & 0x20
        | ((int)v8 >> 31) & 2
        | ((v8 & 0x40000
          | ((v8 & 0x800000 | ((v8 & 0x10000000 | ((v8 & 0x8000000 | (v8 >> 1) & 0x10000000) >> 8)) >> 12)) >> 3)) >> 2)
        | v23;
    CreateOptions = v24;
    if ( (NtCurrentTeb()->SameTebFlags & 0x800) != 0 )
    {
      v24 |= 0x40000u;
      CreateOptions = v24;
    }
    v25 = v8 & 0x4000000;
    if ( (v8 & 0x4000000) != 0 )
    {
      v24 |= 0x1000u;
      v42 |= 0x10000u;
      CreateOptions = v24;
    }
    if ( (v8 & 0x200000) != 0 )
    {
      v24 |= 0x200000u;
      CreateOptions = v24;
    }
    if ( (v8 & 0x100000) != 0 )
    {
      v24 |= 0x400000u;
      CreateOptions = v24;
    }
    if ( (v8 & 0x2000000) != 0 )
    {
      if ( (FileAttributes & 0x10) == 0 || !v13 || v10 != 2 )
      {
LABEL_79:
        v56 = a6 & 2;
        if ( v56 )
        {
          CreateOptions = v24 | 0x20000;
          ProcessSwitchContext = SbGetProcessSwitchContext(NtCurrentPeb()->pShimData);
          if ( ProcessSwitchContext )
            ProcessSwitchContext = *(_QWORD *)(ProcessSwitchContext + 24);
          v30 = ProcessSwitchContext == 0x6000200000000LL;
        }
        else
        {
          v30 = 0;
          v31 = (void (__fastcall *)(ULONG *))SbSelectProcedure(2880154539LL, 1, "kLsE");
          if ( v31 )
            v31(&CreateOptions);
        }
        if ( v37 && ((v41 - 1) & 0xFFFFFFFC) == 0 && v41 != 3 )
        {
          v28 = BasepOpenParentDirectoryNoRedirection(&DestinationString, &Handle);
          if ( v28 < 0 )
            goto LABEL_109;
        }
        v32 = v42 | 0x100080;
        FileAttributes &= 0xDAFFA7u;
        v28 = NtCreateFile(
                &FileHandle,
                v42 | 0x100080,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                FileAttributes,
                ShareAccess,
                v10,
                CreateOptions,
                EaBuffer,
                EaLength);
        if ( v28 == -1073741790 )
        {
          if ( !v30 && v56 )
            goto LABEL_96;
          v33 = CreateOptions;
          if ( (CreateOptions & 0x20000) == 0 || (ShareAccess & 1) != 0 )
            goto LABEL_96;
          CreateOptions &= ~0x20000u;
          v28 = NtCreateFile(
                  &FileHandle,
                  v32,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  FileAttributes,
                  ShareAccess,
                  v10,
                  v33 & 0xFFFDFFFF,
                  EaBuffer,
                  EaLength);
        }
        if ( v28 < 0 )
        {
LABEL_96:
          FileHandle = (HANDLE)-1LL;
          goto LABEL_109;
        }
        if ( v37 )
        {
          v34 = (CreateOptions & 1) != 0
              ? BasepGetDirectoryRedirectionStatus(DestinationString.Buffer, FileHandle)
              : BasepGetFileRedirectionStatus(DestinationString.Buffer, FileHandle);
          v28 = v34;
          if ( v34 < 0 )
          {
            if ( v25 )
            {
              v41 = 8;
              NtSetInformationFile(FileHandle, &IoStatusBlock, &v41, 4u, (FILE_INFORMATION_CLASS)64);
            }
            goto LABEL_104;
          }
        }
        if ( v41 == 5 )
        {
          v49 = 0;
          v28 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v49, 8u, FileAllocationInformation);
          if ( v28 < 0 )
          {
LABEL_104:
            NtClose(FileHandle);
            goto LABEL_96;
          }
        }
        else if ( v41 == 2 && IoStatusBlock.Information == 3 || v41 == 4 && IoStatusBlock.Information == 1 )
        {
          v35 = 183;
          goto LABEL_108;
        }
        v35 = 0;
LABEL_108:
        RtlSetLastWin32Error(v35);
LABEL_109:
        if ( Handle != (HANDLE)-1LL )
          NtClose(Handle);
        goto LABEL_111;
      }
      v24 |= 1u;
    }
    else
    {
      v24 |= 0x40u;
    }
    CreateOptions = v24;
    goto LABEL_79;
  }
  v21 = FileInformation;
  if ( !FileInformation )
  {
LABEL_53:
    v13 = v45;
    goto LABEL_54;
  }
  while ( 1 )
  {
    v21 *= 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v21);
    EaBuffer = Heap;
    if ( !Heap )
      break;
    v27 = NtQueryEaFile(*(HANDLE *)(a5 + 24), &IoStatusBlock, Heap, v21, 0, 0, 0, 0, 1u);
    if ( v27 >= 0 )
    {
      EaLength = IoStatusBlock.Information;
    }
    else
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
      EaBuffer = 0;
      EaLength = 0;
      IoStatusBlock.Information = 0;
    }
    if ( v27 != -2147483643 && v27 != -1073741789 )
      goto LABEL_53;
  }
  v28 = -1073741801;
LABEL_111:
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( EaBuffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
  if ( v28 >= 0 )
    return (__int64)FileHandle;
  BaseSetLastNTError((unsigned int)v28);
  if ( v28 == -1073741771 )
  {
    v36 = 80;
LABEL_124:
    RtlSetLastWin32Error(v36);
    return (__int64)FileHandle;
  }
  if ( v28 == -1073741638 )
  {
    v36 = 3;
    if ( !v47 )
      v36 = 5;
    goto LABEL_124;
  }
  return (__int64)FileHandle;
}

```

## disassembly

```asm
0x1800533cc  mov     [rsp-8+arg_18], rbx
0x1800533d1  push    rbp
0x1800533d2  push    rsi
0x1800533d3  push    rdi
0x1800533d4  push    r12
0x1800533d6  push    r13
0x1800533d8  push    r14
0x1800533da  push    r15
0x1800533dc  lea     rbp, [rsp-30h]
0x1800533e1  sub     rsp, 130h
0x1800533e8  mov     rax, cs:__security_cookie
0x1800533ef  xor     rax, rsp
0x1800533f2  mov     [rbp+60h+var_38], rax
0x1800533f6  mov     rbx, [rbp+60h+arg_20]
0x1800533fd  xorps   xmm0, xmm0
0x180053400  xor     r15d, r15d
0x180053403  mov     [rsp+160h+var_EC], r9d
0x180053408  xor     eax, eax
0x18005340a  mov     [rbp+60h+ShareAccess], r8d
0x18005340e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180053412  mov     [rsp+160h+var_E8], edx
0x180053416  mov     [rsp+160h+CreateOptions], r15d
0x18005341b  xorps   xmm1, xmm1
0x18005341e  mov     [rbp+60h+var_B0], r15
0x180053422  mov     r14, rcx
0x180053425  mov     [rbp+60h+FileInformation], r15d
0x180053429  mov     [rbp+60h+var_48], rax
0x18005342d  mov     [rbp+60h+var_40], eax
0x180053430  mov     [rsp+160h+FileHandle], r12
0x180053435  mov     [rbp+60h+Handle], r12
0x180053439  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x18005343d  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x180053441  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x180053445  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x180053449  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm1
0x18005344d  movups  xmmword ptr [rbp+60h+RelativeName.RelativeName.Length], xmm0
0x180053451  movups  xmmword ptr [rbp+60h+RelativeName.ContainingDirectory], xmm0
0x180053455  test    rbx, rbx
0x180053458  jz      short loc_180053472
0x18005345a  cmp     dword ptr [rbx], 20h ; ' '
0x18005345d  jb      loc_1800534ED
0x180053463  mov     eax, [rbx+4]
0x180053466  mov     esi, [rbx+0Ch]
0x180053469  mov     edi, [rbx+8]
0x18005346c  mov     [rsp+160h+FileAttributes], eax
0x180053470  jmp     short loc_18005347D
0x180053472  mov     esi, r15d
0x180053475  mov     [rsp+160h+FileAttributes], r15d
0x18005347a  mov     edi, r15d
0x18005347d  test    byte ptr [rbp+60h+arg_28], 3
0x180053484  jnz     short loc_1800534C0
0x180053486  bt      edi, 10h
0x18005348a  setb    cl
0x18005348d  mov     [rsp+160h+var_100], cl
0x180053491  bt      edi, 10h
0x180053495  jnb     short loc_1800534BA
0x180053497  test    edx, edx
0x180053499  jz      short loc_1800534A1
0x18005349b  test    r8b, 4
0x18005349f  jz      short loc_1800534C5
0x1800534a1  mov     ecx, 0A0h; LastError
0x1800534a6  call    cs:__imp_RtlSetLastWin32Error
0x1800534ad  nop     dword ptr [rax+rax+00h]
0x1800534b2  mov     rax, r12
0x1800534b5  jmp     loc_180053C00
0x1800534ba  mov     [rsp+160h+var_100], cl
0x1800534be  jmp     short loc_1800534C5
0x1800534c0  mov     [rsp+160h+var_100], r15b
0x1800534c5  mov     eax, r9d
0x1800534c8  mov     r13d, 1
0x1800534ce  sub     eax, r13d
0x1800534d1  jz      short loc_18005350E
0x1800534d3  sub     eax, r13d
0x1800534d6  jz      short loc_180053506
0x1800534d8  sub     eax, r13d
0x1800534db  jz      short loc_180053501
0x1800534dd  sub     eax, r13d
0x1800534e0  jz      short loc_1800534F9
0x1800534e2  cmp     eax, r13d
0x1800534e5  jnz     short loc_1800534ED
0x1800534e7  bt      edx, 1Eh
0x1800534eb  jb      short loc_180053501
0x1800534ed  mov     ecx, 0C000000Dh
0x1800534f2  call    BaseSetLastNTError
0x1800534f7  jmp     short loc_1800534B2
0x1800534f9  mov     r12d, 3
0x1800534ff  jmp     short loc_180053514
0x180053501  mov     r12d, r13d
0x180053504  jmp     short loc_180053514
0x180053506  mov     r12d, 5
0x18005350c  jmp     short loc_180053514
0x18005350e  mov     r12d, 2
0x180053514  mov     rdx, r14; SourceString
0x180053517  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x18005351b  call    cs:__imp_RtlInitUnicodeStringEx
0x180053522  nop     dword ptr [rax+rax+00h]
0x180053527  test    eax, eax
0x180053529  jns     short loc_18005353B
0x18005352b  mov     ecx, eax
0x18005352d  call    BaseSetLastNTError
0x180053532  or      rax, 0FFFFFFFFFFFFFFFFh
0x180053536  jmp     loc_180053C00
0x18005353b  cmp     [rbp+60h+DestinationString.Length], r13w
0x180053540  jbe     short loc_180053556
0x180053542  movzx   eax, [rbp+60h+DestinationString.Length]
0x180053546  shr     rax, 1
0x180053549  mov     [rbp+60h+var_C4], r13d
0x18005354d  cmp     word ptr [r14+rax*2-2], 5Ch ; '\'
0x180053554  jz      short loc_18005355A
0x180053556  mov     [rbp+60h+var_C4], r15d
0x18005355a  lea     r9, [rbp+60h+RelativeName]
0x18005355e  mov     [rsp+160h+CreateOptions], r15d
0x180053563  xor     r8d, r8d
0x180053566  lea     rdx, [rbp+60h+DestinationString]
0x18005356a  mov     rcx, r14
0x18005356d  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x180053574  nop     dword ptr [rax+rax+00h]
0x180053579  test    eax, eax
0x18005357b  jns     short loc_1800535A0
0x18005357d  mov     ebx, 0C0000017h
0x180053582  cmp     eax, ebx
0x180053584  jz      short loc_18005352B
0x180053586  cmp     eax, 0C000009Ah
0x18005358b  jz      short loc_18005352B
0x18005358d  mov     ecx, 3; LastError
0x180053592  call    cs:__imp_RtlSetLastWin32Error
0x180053599  nop     dword ptr [rax+rax+00h]
0x18005359e  jmp     short loc_180053532
0x1800535a0  mov     rax, [rbp+60h+DestinationString.Buffer]
0x1800535a4  mov     [rbp+60h+P], rax
0x1800535a8  movzx   eax, [rbp+60h+RelativeName.RelativeName.Length]
0x1800535ac  test    ax, ax
0x1800535af  jz      short loc_1800535D1
0x1800535b1  mov     [rbp+60h+DestinationString.Length], ax
0x1800535b5  mov     eax, dword ptr [rbp+60h+RelativeName.RelativeName.MaximumLength]
0x1800535b8  mov     dword ptr [rbp+60h+DestinationString.MaximumLength], eax
0x1800535bb  movzx   eax, word ptr [rbp+60h+RelativeName.RelativeName+6]
0x1800535bf  mov     word ptr [rbp+60h+DestinationString+6], ax
0x1800535c3  mov     rax, [rbp+60h+RelativeName.RelativeName.Buffer]
0x1800535c7  mov     [rbp+60h+DestinationString.Buffer], rax
0x1800535cb  mov     rax, [rbp+60h+RelativeName.ContainingDirectory]
0x1800535cf  jmp     short loc_1800535D8
0x1800535d1  mov     rax, r15
0x1800535d4  mov     [rbp+60h+RelativeName.ContainingDirectory], rax
0x1800535d8  mov     [rbp+60h+ObjectAttributes.RootDirectory], rax
0x1800535dc  mov     r14d, edi
0x1800535df  and     r14d, 1000000h
0x1800535e6  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1800535ed  mov     eax, r14d
0x1800535f0  mov     [rbp+60h+var_CC], r14d
0x1800535f4  mov     edx, edi
0x1800535f6  mov     [rbp+60h+ObjectAttributes.SecurityDescriptor], r15
0x1800535fa  shr     edx, 6
0x1800535fd  and     edx, 800h
0x180053603  neg     eax
0x180053605  lea     rax, [rbp+60h+DestinationString]
0x180053609  sbb     ecx, ecx
0x18005360b  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x18005360f  not     ecx
0x180053611  and     ecx, 40h
0x180053614  or      ecx, edx
0x180053616  mov     [rbp+60h+ObjectAttributes.Attributes], ecx
0x180053619  bt      esi, 14h
0x18005361d  jnb     short loc_180053656
0x18005361f  and     esi, 0F0000h
0x180053625  bt      esi, 12h
0x180053629  mov     ecx, esi
0x18005362b  setb    byte ptr [rbp+60h+var_40]
0x18005362f  btr     ecx, 12h
0x180053633  bt      esi, 12h
0x180053637  cmovnb  ecx, esi
0x18005363a  bt      ecx, 13h
0x18005363e  jnb     short loc_18005364A
0x180053640  mov     byte ptr [rbp+60h+var_40+1], r13b
0x180053644  btr     ecx, 13h
0x180053648  jmp     short loc_18005364E
0x18005364a  mov     byte ptr [rbp+60h+var_40+1], r15b
0x18005364e  shr     ecx, 10h
0x180053651  mov     dword ptr [rbp+60h+var_48+4], ecx
0x180053654  jmp     short loc_180053663
0x180053656  mov     word ptr [rbp+60h+var_40], 101h
0x18005365c  mov     dword ptr [rbp+60h+var_48+4], 2
0x180053663  mov     dword ptr [rbp+60h+var_48], 0Ch
0x18005366a  lea     rax, [rbp+60h+var_48]
0x18005366e  mov     [rbp+60h+ObjectAttributes.SecurityQualityOfService], rax
0x180053672  test    rbx, rbx
0x180053675  jz      short loc_1800536A8
0x180053677  mov     rcx, [rbx+10h]
0x18005367b  test    rcx, rcx
0x18005367e  jz      short loc_1800536A8
0x180053680  mov     rax, [rcx+8]
0x180053684  mov     [rbp+60h+ObjectAttributes.SecurityDescriptor], rax
0x180053688  cmp     [rcx+10h], r15d
0x18005368c  jz      short loc_1800536A8
0x18005368e  mov     eax, r14d
0x180053691  mov     rsi, r15
0x180053694  neg     eax
0x180053696  mov     r13d, r15d
0x180053699  sbb     ecx, ecx
0x18005369b  and     ecx, 0FFFFFFC0h
0x18005369e  add     ecx, 42h ; 'B'
0x1800536a1  or      ecx, edx
0x1800536a3  mov     [rbp+60h+ObjectAttributes.Attributes], ecx
0x1800536a6  jmp     short loc_1800536B3
0x1800536a8  mov     rsi, r15
0x1800536ab  mov     r13d, r15d
0x1800536ae  test    rbx, rbx
0x1800536b1  jz      short loc_1800536F8
0x1800536b3  mov     rcx, [rbx+18h]; FileHandle
0x1800536b7  lea     rax, [rcx-1]
0x1800536bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800536bf  ja      short loc_1800536F8
0x1800536c1  mov     r9d, 4; Length
0x1800536c7  mov     [rsp+160h+FileInformationClass], 7; FileInformationClass
0x1800536cf  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x1800536d3  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x1800536d7  call    cs:__imp_NtQueryInformationFile
0x1800536de  nop     dword ptr [rax+rax+00h]
0x1800536e3  test    eax, eax
0x1800536e5  js      short loc_1800536F8
0x1800536e7  mov     r14d, [rbp+60h+FileInformation]
0x1800536eb  test    r14d, r14d
0x1800536ee  jnz     loc_1800537F7
0x1800536f4  mov     r14d, [rbp+60h+var_CC]
0x1800536f8  call    Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline
0x1800536fd  mov     r8d, [rsp+160h+CreateOptions]
0x180053702  test    eax, eax
0x180053704  jz      short loc_180053713
0x180053706  mov     eax, edi
0x180053708  and     eax, 8000h
0x18005370d  shl     eax, 0Eh
0x180053710  or      r8d, eax
0x180053713  mov     ecx, 10000000h
0x180053718  mov     eax, edi
0x18005371a  and     eax, 8000000h
0x18005371f  mov     edx, edi
0x180053721  shr     edx, 1
0x180053723  mov     r10d, 40000h
0x180053729  and     edx, ecx
0x18005372b  mov     r9d, edi
0x18005372e  or      edx, eax
0x180053730  and     r9d, 2000000h
0x180053737  shr     edx, 8
0x18005373a  mov     eax, edi
0x18005373c  and     eax, ecx
0x18005373e  or      edx, eax
0x180053740  mov     eax, edi
0x180053742  and     eax, 800000h
0x180053747  shr     edx, 0Ch
0x18005374a  or      edx, eax
0x18005374c  mov     eax, edi
0x18005374e  and     eax, r10d
0x180053751  shr     edx, 3
0x180053754  or      edx, eax
0x180053756  mov     eax, edi
0x180053758  sar     eax, 1Fh
0x18005375b  and     eax, 2
0x18005375e  shr     edx, 2
0x180053761  or      edx, eax
0x180053763  mov     eax, edi
0x180053765  shr     eax, 19h
0x180053768  not     eax
0x18005376a  and     eax, 20h
0x18005376d  or      edx, eax
0x18005376f  mov     eax, r9d
0x180053772  neg     eax
0x180053774  sbb     ecx, ecx
0x180053776  and     ecx, 4000h
0x18005377c  or      edx, ecx
0x18005377e  mov     ecx, 800h
0x180053783  or      r8d, edx
0x180053786  mov     [rsp+160h+CreateOptions], r8d
0x18005378b  mov     rax, gs:30h
0x180053794  test    [rax+17EEh], cx
0x18005379b  jz      short loc_1800537A5
0x18005379d  or      r8d, r10d
0x1800537a0  mov     [rsp+160h+CreateOptions], r8d
0x1800537a5  mov     r15d, edi
0x1800537a8  and     r15d, 4000000h
0x1800537af  jz      short loc_1800537C1
0x1800537b1  bts     r8d, 0Ch
0x1800537b6  bts     [rsp+160h+var_E8], 10h
0x1800537bc  mov     [rsp+160h+CreateOptions], r8d
0x1800537c1  mov     eax, 200000h
0x1800537c6  test    eax, edi
0x1800537c8  jz      short loc_1800537D2
0x1800537ca  or      r8d, eax
0x1800537cd  mov     [rsp+160h+CreateOptions], r8d
0x1800537d2  bt      edi, 14h
0x1800537d6  jnb     short loc_1800537E2
0x1800537d8  bts     r8d, 16h
0x1800537dd  mov     [rsp+160h+CreateOptions], r8d
0x1800537e2  test    r9d, r9d
0x1800537e5  jnz     loc_1800538BE
0x1800537eb  or      r8d, 40h
0x1800537ef  jmp     loc_1800538D5
0x1800537f4  xor     r15d, r15d
0x1800537f7  mov     rcx, gs:60h
0x180053800  add     r14d, r14d
0x180053803  mov     edx, cs:KernelBaseGlobalData; Flags
  ... truncated ...
```
