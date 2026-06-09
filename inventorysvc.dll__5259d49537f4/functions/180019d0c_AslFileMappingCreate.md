# AslFileMappingCreate

- ea: `0x180019d0c`
- end: `0x18001a005`
- name: `AslFileMappingCreate`
- size: `761`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800153e0`

## callees

- `0x180002bf0`
- `0x18000381c`
- `0x1800152d0`
- `0x180017adc`
- `0x180019d0c`
- `0x18001a00c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180019fd3`
- `ntdll!RtlFreeUnicodeString` at `0x180019fd3`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180019df4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180019df4`
- `ntdll!ZwCreateFile` at `0x180019e98`
- `ntdll!ZwCreateFile` at `0x180019e98`
- `ntdll!ZwQueryInformationFile` at `0x180019f73`
- `ntdll!ZwQueryInformationFile` at `0x180019f73`
- `ntdll!ZwClose` at `0x180019ec5`
- `ntdll!ZwClose` at `0x180019ec5`
- `ntdll!RtlAllocateHeap` at `0x180019d93`
- `ntdll!RtlAllocateHeap` at `0x180019d93`
- `ntdll!RtlInitUnicodeString` at `0x180019d76`
- `ntdll!RtlInitUnicodeString` at `0x180019d76`

## string_xrefs

- `0x180019e04`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x180019e16`: `AslFileMappingCreate`
- `0x180019f8c`: `AslFileMappingCreate`
- `0x180019f1a`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180019f30`: `RtlFileMapInitializeByFilePath failed %S [%x]`

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
    if ( wcsnicmp(a2, L"\\SystemRoot\\", 0xCu)
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
0x180019d0c  mov     [rsp-8+arg_10], rbx
0x180019d11  push    rbp
0x180019d12  push    rsi
0x180019d13  push    rdi
0x180019d14  push    r12
0x180019d16  push    r15
0x180019d18  lea     rbp, [rsp-2Fh]
0x180019d1d  sub     rsp, 0F0h
0x180019d24  mov     rax, cs:__security_cookie
0x180019d2b  xor     rax, rsp
0x180019d2e  mov     [rbp+4Fh+var_30], rax
0x180019d32  xor     eax, eax
0x180019d34  xorps   xmm0, xmm0
0x180019d37  xor     r12d, r12d
0x180019d3a  mov     [rbp+4Fh+var_38], rax
0x180019d3e  xorps   xmm1, xmm1
0x180019d41  mov     rdi, rdx
0x180019d44  mov     r15, rcx
0x180019d47  movups  [rbp+4Fh+FileInformation], xmm0
0x180019d4b  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x180019d4f  movups  xmmword ptr [rbp+4Fh+var_98], xmm1
0x180019d53  test    rdx, rdx
0x180019d56  jz      loc_180019FDD
0x180019d5c  cmp     [rdx], r12w
0x180019d60  jz      loc_180019FDD
0x180019d66  test    rcx, rcx
0x180019d69  jz      loc_180019FDD
0x180019d6f  mov     [rcx], r12
0x180019d72  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x180019d76  call    cs:__imp_RtlInitUnicodeString
0x180019d7c  mov     rcx, gs:60h
0x180019d85  lea     edx, [r12+8]; Flags
0x180019d8a  lea     r8d, [r12+50h]; Size
0x180019d8f  mov     rcx, [rcx+30h]; HeapHandle
0x180019d93  call    cs:__imp_RtlAllocateHeap
0x180019d99  mov     rsi, rax
0x180019d9c  test    rax, rax
0x180019d9f  jnz     short loc_180019DAB
0x180019da1  mov     ebx, 0C0000017h
0x180019da6  jmp     loc_180019FC9
0x180019dab  mov     rdx, rdi
0x180019dae  mov     rcx, rsi
0x180019db1  call    AslStringDuplicate
0x180019db6  mov     ebx, eax
0x180019db8  test    eax, eax
0x180019dba  jns     short loc_180019DCE
0x180019dbc  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x180019dc3  mov     r8d, 7Bh ; '{'
0x180019dc9  jmp     loc_180019F8C
0x180019dce  mov     r8d, 0Ch; MaxCount
0x180019dd4  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x180019ddb  mov     rcx, rdi; String1
0x180019dde  call    _wcsnicmp
0x180019de3  test    eax, eax
0x180019de5  jz      short loc_180019E2C
0x180019de7  xor     r9d, r9d
0x180019dea  lea     rdx, [rbp+4Fh+DestinationString]
0x180019dee  xor     r8d, r8d
0x180019df1  mov     rcx, rdi
0x180019df4  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180019dfa  mov     ebx, eax
0x180019dfc  test    eax, eax
0x180019dfe  jns     short loc_180019E2C
0x180019e00  mov     dword ptr [rsp+110h+FileAttributes], eax
0x180019e04  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180019e0b  mov     r8d, 94h
0x180019e11  mov     ecx, 1
0x180019e16  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x180019e1d  mov     [rsp+110h+AllocationSize], rdi
0x180019e22  call    AslLogCallPrintf
0x180019e27  jmp     loc_180019FA1
0x180019e2c  mov     [rsp+110h+EaLength], r12d; EaLength
0x180019e31  lea     rax, [rbp+4Fh+DestinationString]
0x180019e35  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x180019e3a  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180019e3e  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x180019e46  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180019e4a  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x180019e52  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180019e56  xorps   xmm0, xmm0
0x180019e59  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x180019e61  mov     dword ptr [rsp+110h+FileAttributes], 80h; FileAttributes
0x180019e69  mov     edx, 80100080h; DesiredAccess
0x180019e6e  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x180019e73  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180019e7b  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180019e83  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x180019e87  mov     [rbp+4Fh+FileHandle], r12
0x180019e8b  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x180019e8f  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x180019e93  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180019e98  call    cs:__imp_ZwCreateFile
0x180019e9e  mov     ebx, eax
0x180019ea0  test    eax, eax
0x180019ea2  js      short loc_180019EBC
0x180019ea4  mov     rax, [rbp+4Fh+FileHandle]
0x180019ea8  mov     rcx, r12
0x180019eab  mov     [rsi+8], rax
0x180019eaf  mov     ebx, r12d
0x180019eb2  mov     [rbp+4Fh+FileHandle], rcx
0x180019eb6  mov     byte ptr [rsi+30h], 1
0x180019eba  jmp     short loc_180019EC0
0x180019ebc  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180019ec0  test    rcx, rcx
0x180019ec3  jz      short loc_180019ECB
0x180019ec5  call    cs:__imp_ZwClose
0x180019ecb  test    ebx, ebx
0x180019ecd  jns     short loc_180019F47
0x180019ecf  cmp     ebx, 0C000003Ah
0x180019ed5  jz      loc_180019FA1
0x180019edb  cmp     ebx, 0C0000034h
0x180019ee1  jz      loc_180019FA1
0x180019ee7  cmp     ebx, 0C00000CCh
0x180019eed  jz      loc_180019FA1
0x180019ef3  lea     eax, [rbx+3FFFFFEDh]
0x180019ef9  cmp     eax, 30h ; '0'
0x180019efc  ja      short loc_180019F0E
0x180019efe  mov     rcx, 1000000008001h
0x180019f08  bt      rcx, rax
0x180019f0c  jb      short loc_180019F2C
0x180019f0e  cmp     ebx, 0C00000BAh
0x180019f14  jz      short loc_180019F2C
0x180019f16  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x180019f1a  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180019f21  mov     r8d, 0A1h
0x180019f27  jmp     loc_180019E11
0x180019f2c  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x180019f30  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180019f37  mov     r8d, 0A3h
0x180019f3d  mov     ecx, 3
0x180019f42  jmp     loc_180019E16
0x180019f47  xor     eax, eax
0x180019f49  mov     dword ptr [rsp+110h+AllocationSize], 5; FileInformationClass
0x180019f51  xorps   xmm0, xmm0
0x180019f54  mov     [rbp+4Fh+var_38], rax
0x180019f58  xorps   xmm1, xmm1
0x180019f5b  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x180019f5f  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x180019f63  lea     r9d, [rax+18h]; Length
0x180019f67  movups  [rbp+4Fh+FileInformation], xmm1
0x180019f6b  mov     rcx, [rsi+8]; FileHandle
0x180019f6f  lea     rdx, [rbp+4Fh+var_98]; IoStatusBlock
0x180019f73  call    cs:__imp_ZwQueryInformationFile
0x180019f79  mov     ebx, eax
0x180019f7b  test    eax, eax
0x180019f7d  jns     short loc_180019FAB
0x180019f7f  lea     r9, aNtqueryinforma; "NtQueryInformationFile failed [%x]"
0x180019f86  mov     r8d, 0B7h
0x180019f8c  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x180019f93  mov     dword ptr [rsp+110h+AllocationSize], eax
0x180019f97  mov     ecx, 1
0x180019f9c  call    AslLogCallPrintf
0x180019fa1  mov     rcx, rsi; P
0x180019fa4  call    AslFileMappingDelete
0x180019fa9  jmp     short loc_180019FC9
0x180019fab  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x180019faf  mov     ebx, r12d
0x180019fb2  mov     [rsi+18h], rax
0x180019fb6  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x180019fba  neg     rax
0x180019fbd  sbb     ecx, ecx
0x180019fbf  neg     ecx
0x180019fc1  inc     ecx
0x180019fc3  mov     [rsi+38h], ecx
0x180019fc6  mov     [r15], rsi
0x180019fc9  cmp     [rbp+4Fh+DestinationString.Buffer], rdi
0x180019fcd  jz      short loc_180019FD9
0x180019fcf  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x180019fd3  call    cs:__imp_RtlFreeUnicodeString
0x180019fd9  mov     eax, ebx
0x180019fdb  jmp     short loc_180019FE2
0x180019fdd  mov     eax, 0C000000Dh
0x180019fe2  mov     rcx, [rbp+4Fh+var_30]
0x180019fe6  xor     rcx, rsp; StackCookie
0x180019fe9  call    __security_check_cookie
0x180019fee  mov     rbx, [rsp+110h+arg_10]
0x180019ff6  add     rsp, 0F0h
0x180019ffd  pop     r15
0x180019fff  pop     r12
0x18001a001  pop     rdi
0x18001a002  pop     rsi
0x18001a003  pop     rbp
0x18001a004  retn
```
