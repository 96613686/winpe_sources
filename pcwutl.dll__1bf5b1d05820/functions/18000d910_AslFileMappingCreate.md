# AslFileMappingCreate

- ea: `0x18000d910`
- end: `0x18000dc09`
- name: `AslFileMappingCreate`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800039c8`
- `0x18000d824`

## callees

- `0x180002688`
- `0x18000d910`
- `0x18000dc10`
- `0x18000e240`
- `0x18000eef4`
- `0x1800191f0`

## import_xrefs

- `ntdll!ZwClose` at `0x18000dac9`
- `ntdll!ZwClose` at `0x18000dac9`
- `ntdll!ZwQueryInformationFile` at `0x18000db77`
- `ntdll!ZwQueryInformationFile` at `0x18000db77`
- `ntdll!RtlFreeUnicodeString` at `0x18000dbd7`
- `ntdll!RtlFreeUnicodeString` at `0x18000dbd7`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18000d9f8`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18000d9f8`
- `ntdll!ZwCreateFile` at `0x18000da9c`
- `ntdll!ZwCreateFile` at `0x18000da9c`
- `ntdll!RtlAllocateHeap` at `0x18000d997`
- `ntdll!RtlAllocateHeap` at `0x18000d997`
- `ntdll!RtlInitUnicodeString` at `0x18000d97a`
- `ntdll!RtlInitUnicodeString` at `0x18000d97a`

## string_xrefs

- `0x18000da08`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x18000da1a`: `AslFileMappingCreate`
- `0x18000db90`: `AslFileMappingCreate`
- `0x18000db1e`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x18000db34`: `RtlFileMapInitializeByFilePath failed %S [%x]`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(_QWORD *a1, const WCHAR *a2)
{
  PVOID Heap; // rax
  PVOID v5; // rsi
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  int v10; // eax
  const char *v11; // r9
  __int64 v12; // r8
  void *v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-A1h]
  __int64 FileAttributes; // [rsp+28h] [rbp-99h]
  void *FileHandle; // [rsp+60h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK v21; // [rsp+78h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-9h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp+7h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+17h]

  v25 = 0;
  FileInformation = 0;
  DestinationString = 0;
  v21 = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v5 = Heap;
  if ( Heap )
  {
    v7 = AslStringDuplicate(Heap, a2);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = "AslStringDuplicate failed [%x]";
      v9 = 123;
LABEL_29:
      LODWORD(AllocationSize) = v7;
      AslLogCallPrintf(1, "AslFileMappingCreate", v9, v8, AllocationSize);
      goto LABEL_30;
    }
    if ( wcsnicmp_0(a2, L"\\SystemRoot\\", 0xCu)
      && (v10 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0), v6 = v10, v10 < 0) )
    {
      LODWORD(FileAttributes) = v10;
      v11 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
      v12 = 148;
    }
    else
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      IoStatusBlock = 0;
      FileHandle = 0;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v6 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 5u, 1u, 0x60u, 0, 0);
      if ( v6 < 0 )
      {
        v13 = FileHandle;
      }
      else
      {
        v13 = 0;
        *((_QWORD *)v5 + 1) = FileHandle;
        v6 = 0;
        FileHandle = 0;
        *((_BYTE *)v5 + 48) = 1;
      }
      if ( v13 )
        ZwClose(v13);
      if ( v6 >= 0 )
      {
        v25 = 0;
        v21 = 0;
        FileInformation = 0;
        v7 = ZwQueryInformationFile(*((HANDLE *)v5 + 1), &v21, &FileInformation, 0x18u, FileStandardInformation);
        v6 = v7;
        if ( v7 >= 0 )
        {
          v6 = 0;
          *((_QWORD *)v5 + 3) = *((_QWORD *)&FileInformation + 1);
          *((_DWORD *)v5 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
          *a1 = v5;
          goto LABEL_32;
        }
        v8 = "NtQueryInformationFile failed [%x]";
        v9 = 183;
        goto LABEL_29;
      }
      if ( v6 == -1073741766 || v6 == -1073741772 || v6 == -1073741620 )
        goto LABEL_30;
      v14 = (unsigned int)(v6 + 1073741805);
      if ( (unsigned int)v14 <= 0x30 && (v15 = 0x1000000008001LL, _bittest64(&v15, v14)) || v6 == -1073741638 )
      {
        LODWORD(FileAttributes) = v6;
        AslLogCallPrintf(
          3,
          "AslFileMappingCreate",
          163,
          "RtlFileMapInitializeByFilePath failed %S [%x]",
          a2,
          FileAttributes);
LABEL_30:
        AslFileMappingDelete(v5);
        goto LABEL_32;
      }
      LODWORD(FileAttributes) = v6;
      v11 = "RtlFileMapInitializeByFilePath failed %S [%x]";
      v12 = 161;
    }
    AslLogCallPrintf(1, "AslFileMappingCreate", v12, v11, a2, FileAttributes);
    goto LABEL_30;
  }
  v6 = -1073741801;
LABEL_32:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d910  mov     [rsp-8+arg_10], rbx
0x18000d915  push    rbp
0x18000d916  push    rsi
0x18000d917  push    rdi
0x18000d918  push    r12
0x18000d91a  push    r15
0x18000d91c  lea     rbp, [rsp-2Fh]
0x18000d921  sub     rsp, 0F0h
0x18000d928  mov     rax, cs:__security_cookie
0x18000d92f  xor     rax, rsp
0x18000d932  mov     [rbp+4Fh+var_30], rax
0x18000d936  xor     eax, eax
0x18000d938  xorps   xmm0, xmm0
0x18000d93b  xor     r12d, r12d
0x18000d93e  mov     [rbp+4Fh+var_38], rax
0x18000d942  xorps   xmm1, xmm1
0x18000d945  mov     rdi, rdx
0x18000d948  mov     r15, rcx
0x18000d94b  movups  [rbp+4Fh+FileInformation], xmm0
0x18000d94f  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18000d953  movups  xmmword ptr [rbp+4Fh+var_98], xmm1
0x18000d957  test    rdx, rdx
0x18000d95a  jz      loc_18000DBE1
0x18000d960  cmp     [rdx], r12w
0x18000d964  jz      loc_18000DBE1
0x18000d96a  test    rcx, rcx
0x18000d96d  jz      loc_18000DBE1
0x18000d973  mov     [rcx], r12
0x18000d976  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18000d97a  call    cs:__imp_RtlInitUnicodeString
0x18000d980  mov     rcx, gs:60h
0x18000d989  lea     edx, [r12+8]; Flags
0x18000d98e  lea     r8d, [r12+50h]; Size
0x18000d993  mov     rcx, [rcx+30h]; HeapHandle
0x18000d997  call    cs:__imp_RtlAllocateHeap
0x18000d99d  mov     rsi, rax
0x18000d9a0  test    rax, rax
0x18000d9a3  jnz     short loc_18000D9AF
0x18000d9a5  mov     ebx, 0C0000017h
0x18000d9aa  jmp     loc_18000DBCD
0x18000d9af  mov     rdx, rdi
0x18000d9b2  mov     rcx, rsi
0x18000d9b5  call    AslStringDuplicate
0x18000d9ba  mov     ebx, eax
0x18000d9bc  test    eax, eax
0x18000d9be  jns     short loc_18000D9D2
0x18000d9c0  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x18000d9c7  mov     r8d, 7Bh ; '{'
0x18000d9cd  jmp     loc_18000DB90
0x18000d9d2  mov     r8d, 0Ch; MaxCount
0x18000d9d8  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x18000d9df  mov     rcx, rdi; String1
0x18000d9e2  call    _wcsnicmp_0
0x18000d9e7  test    eax, eax
0x18000d9e9  jz      short loc_18000DA30
0x18000d9eb  xor     r9d, r9d
0x18000d9ee  lea     rdx, [rbp+4Fh+DestinationString]
0x18000d9f2  xor     r8d, r8d
0x18000d9f5  mov     rcx, rdi
0x18000d9f8  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18000d9fe  mov     ebx, eax
0x18000da00  test    eax, eax
0x18000da02  jns     short loc_18000DA30
0x18000da04  mov     dword ptr [rsp+110h+FileAttributes], eax
0x18000da08  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18000da0f  mov     r8d, 94h
0x18000da15  mov     ecx, 1
0x18000da1a  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x18000da21  mov     [rsp+110h+AllocationSize], rdi
0x18000da26  call    AslLogCallPrintf
0x18000da2b  jmp     loc_18000DBA5
0x18000da30  mov     [rsp+110h+EaLength], r12d; EaLength
0x18000da35  lea     rax, [rbp+4Fh+DestinationString]
0x18000da39  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x18000da3e  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18000da42  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x18000da4a  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18000da4e  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18000da56  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x18000da5a  xorps   xmm0, xmm0
0x18000da5d  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x18000da65  mov     dword ptr [rsp+110h+FileAttributes], 80h; FileAttributes
0x18000da6d  mov     edx, 80100080h; DesiredAccess
0x18000da72  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x18000da77  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18000da7f  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18000da87  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x18000da8b  mov     [rbp+4Fh+FileHandle], r12
0x18000da8f  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18000da93  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18000da97  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18000da9c  call    cs:__imp_ZwCreateFile
0x18000daa2  mov     ebx, eax
0x18000daa4  test    eax, eax
0x18000daa6  js      short loc_18000DAC0
0x18000daa8  mov     rax, [rbp+4Fh+FileHandle]
0x18000daac  mov     rcx, r12
0x18000daaf  mov     [rsi+8], rax
0x18000dab3  mov     ebx, r12d
0x18000dab6  mov     [rbp+4Fh+FileHandle], rcx
0x18000daba  mov     byte ptr [rsi+30h], 1
0x18000dabe  jmp     short loc_18000DAC4
0x18000dac0  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x18000dac4  test    rcx, rcx
0x18000dac7  jz      short loc_18000DACF
0x18000dac9  call    cs:__imp_ZwClose
0x18000dacf  test    ebx, ebx
0x18000dad1  jns     short loc_18000DB4B
0x18000dad3  cmp     ebx, 0C000003Ah
0x18000dad9  jz      loc_18000DBA5
0x18000dadf  cmp     ebx, 0C0000034h
0x18000dae5  jz      loc_18000DBA5
0x18000daeb  cmp     ebx, 0C00000CCh
0x18000daf1  jz      loc_18000DBA5
0x18000daf7  lea     eax, [rbx+3FFFFFEDh]
0x18000dafd  cmp     eax, 30h ; '0'
0x18000db00  ja      short loc_18000DB12
0x18000db02  mov     rcx, 1000000008001h
0x18000db0c  bt      rcx, rax
0x18000db10  jb      short loc_18000DB30
0x18000db12  cmp     ebx, 0C00000BAh
0x18000db18  jz      short loc_18000DB30
0x18000db1a  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x18000db1e  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18000db25  mov     r8d, 0A1h
0x18000db2b  jmp     loc_18000DA15
0x18000db30  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x18000db34  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18000db3b  mov     r8d, 0A3h
0x18000db41  mov     ecx, 3
0x18000db46  jmp     loc_18000DA1A
0x18000db4b  xor     eax, eax
0x18000db4d  mov     dword ptr [rsp+110h+AllocationSize], 5; FileInformationClass
0x18000db55  xorps   xmm0, xmm0
0x18000db58  mov     [rbp+4Fh+var_38], rax
0x18000db5c  xorps   xmm1, xmm1
0x18000db5f  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x18000db63  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x18000db67  lea     r9d, [rax+18h]; Length
0x18000db6b  movups  [rbp+4Fh+FileInformation], xmm1
0x18000db6f  mov     rcx, [rsi+8]; FileHandle
0x18000db73  lea     rdx, [rbp+4Fh+var_98]; IoStatusBlock
0x18000db77  call    cs:__imp_ZwQueryInformationFile
0x18000db7d  mov     ebx, eax
0x18000db7f  test    eax, eax
0x18000db81  jns     short loc_18000DBAF
0x18000db83  lea     r9, aNtqueryinforma; "NtQueryInformationFile failed [%x]"
0x18000db8a  mov     r8d, 0B7h
0x18000db90  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x18000db97  mov     dword ptr [rsp+110h+AllocationSize], eax
0x18000db9b  mov     ecx, 1
0x18000dba0  call    AslLogCallPrintf
0x18000dba5  mov     rcx, rsi; P
0x18000dba8  call    AslFileMappingDelete
0x18000dbad  jmp     short loc_18000DBCD
0x18000dbaf  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x18000dbb3  mov     ebx, r12d
0x18000dbb6  mov     [rsi+18h], rax
0x18000dbba  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x18000dbbe  neg     rax
0x18000dbc1  sbb     ecx, ecx
0x18000dbc3  neg     ecx
0x18000dbc5  inc     ecx
0x18000dbc7  mov     [rsi+38h], ecx
0x18000dbca  mov     [r15], rsi
0x18000dbcd  cmp     [rbp+4Fh+DestinationString.Buffer], rdi
0x18000dbd1  jz      short loc_18000DBDD
0x18000dbd3  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x18000dbd7  call    cs:__imp_RtlFreeUnicodeString
0x18000dbdd  mov     eax, ebx
0x18000dbdf  jmp     short loc_18000DBE6
0x18000dbe1  mov     eax, 0C000000Dh
0x18000dbe6  mov     rcx, [rbp+4Fh+var_30]
0x18000dbea  xor     rcx, rsp; StackCookie
0x18000dbed  call    __security_check_cookie
0x18000dbf2  mov     rbx, [rsp+110h+arg_10]
0x18000dbfa  add     rsp, 0F0h
0x18000dc01  pop     r15
0x18000dc03  pop     r12
0x18000dc05  pop     rdi
0x18000dc06  pop     rsi
0x18000dc07  pop     rbp
0x18000dc08  retn
```
