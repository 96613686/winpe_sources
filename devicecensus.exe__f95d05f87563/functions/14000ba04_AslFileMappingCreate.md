# AslFileMappingCreate

- ea: `0x14000ba04`
- end: `0x14000bcfe`
- name: `AslFileMappingCreate`
- size: `762`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140007184`

## callees

- `0x140007074`
- `0x1400097d4`
- `0x14000ba04`
- `0x14000bd04`
- `0x1400115f0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14000bad6`
- `msvcrt!_wcsnicmp` at `0x14000bad6`
- `ntdll!ZwQueryInformationFile` at `0x14000bc6c`
- `ntdll!ZwQueryInformationFile` at `0x14000bc6c`
- `ntdll!ZwCreateFile` at `0x14000bb91`
- `ntdll!ZwCreateFile` at `0x14000bb91`
- `ntdll!RtlFreeUnicodeString` at `0x14000bccc`
- `ntdll!RtlFreeUnicodeString` at `0x14000bccc`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14000baed`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14000baed`
- `ntdll!ZwClose` at `0x14000bbbe`
- `ntdll!ZwClose` at `0x14000bbbe`
- `ntdll!RtlAllocateHeap` at `0x14000ba8b`
- `ntdll!RtlAllocateHeap` at `0x14000ba8b`
- `ntdll!RtlInitUnicodeString` at `0x14000ba6e`
- `ntdll!RtlInitUnicodeString` at `0x14000ba6e`

## string_xrefs

- `0x14000bafd`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x14000bb0f`: `AslFileMappingCreate`
- `0x14000bc85`: `AslFileMappingCreate`
- `0x14000bc13`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x14000bc29`: `RtlFileMapInitializeByFilePath failed %S [%x]`

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
    if ( _wcsnicmp(a2, L"\\SystemRoot\\", 0xCu)
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
0x14000ba04  mov     [rsp-8+arg_10], rbx
0x14000ba09  push    rbp
0x14000ba0a  push    rsi
0x14000ba0b  push    rdi
0x14000ba0c  push    r12
0x14000ba0e  push    r15
0x14000ba10  lea     rbp, [rsp-2Fh]
0x14000ba15  sub     rsp, 0F0h
0x14000ba1c  mov     rax, cs:__security_cookie
0x14000ba23  xor     rax, rsp
0x14000ba26  mov     [rbp+4Fh+var_30], rax
0x14000ba2a  xor     eax, eax
0x14000ba2c  xorps   xmm0, xmm0
0x14000ba2f  xor     r12d, r12d
0x14000ba32  mov     [rbp+4Fh+var_38], rax
0x14000ba36  xorps   xmm1, xmm1
0x14000ba39  mov     rdi, rdx
0x14000ba3c  mov     r15, rcx
0x14000ba3f  movups  [rbp+4Fh+FileInformation], xmm0
0x14000ba43  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14000ba47  movups  xmmword ptr [rbp+4Fh+var_98], xmm1
0x14000ba4b  test    rdx, rdx
0x14000ba4e  jz      loc_14000BCD6
0x14000ba54  cmp     [rdx], r12w
0x14000ba58  jz      loc_14000BCD6
0x14000ba5e  test    rcx, rcx
0x14000ba61  jz      loc_14000BCD6
0x14000ba67  mov     [rcx], r12
0x14000ba6a  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14000ba6e  call    cs:__imp_RtlInitUnicodeString
0x14000ba74  mov     rcx, gs:60h
0x14000ba7d  lea     edx, [r12+8]; Flags
0x14000ba82  lea     r8d, [r12+50h]; Size
0x14000ba87  mov     rcx, [rcx+30h]; HeapHandle
0x14000ba8b  call    cs:__imp_RtlAllocateHeap
0x14000ba91  mov     rsi, rax
0x14000ba94  test    rax, rax
0x14000ba97  jnz     short loc_14000BAA3
0x14000ba99  mov     ebx, 0C0000017h
0x14000ba9e  jmp     loc_14000BCC2
0x14000baa3  mov     rdx, rdi
0x14000baa6  mov     rcx, rsi
0x14000baa9  call    AslStringDuplicate
0x14000baae  mov     ebx, eax
0x14000bab0  test    eax, eax
0x14000bab2  jns     short loc_14000BAC6
0x14000bab4  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x14000babb  mov     r8d, 7Bh ; '{'
0x14000bac1  jmp     loc_14000BC85
0x14000bac6  mov     r8d, 0Ch; MaxCount
0x14000bacc  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x14000bad3  mov     rcx, rdi; String1
0x14000bad6  call    cs:__imp__wcsnicmp
0x14000badc  test    eax, eax
0x14000bade  jz      short loc_14000BB25
0x14000bae0  xor     r9d, r9d
0x14000bae3  lea     rdx, [rbp+4Fh+DestinationString]
0x14000bae7  xor     r8d, r8d
0x14000baea  mov     rcx, rdi
0x14000baed  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14000baf3  mov     ebx, eax
0x14000baf5  test    eax, eax
0x14000baf7  jns     short loc_14000BB25
0x14000baf9  mov     dword ptr [rsp+110h+FileAttributes], eax
0x14000bafd  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x14000bb04  mov     r8d, 94h
0x14000bb0a  mov     ecx, 1
0x14000bb0f  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x14000bb16  mov     [rsp+110h+AllocationSize], rdi
0x14000bb1b  call    AslLogCallPrintf
0x14000bb20  jmp     loc_14000BC9A
0x14000bb25  mov     [rsp+110h+EaLength], r12d; EaLength
0x14000bb2a  lea     rax, [rbp+4Fh+DestinationString]
0x14000bb2e  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x14000bb33  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x14000bb37  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x14000bb3f  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14000bb43  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x14000bb4b  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14000bb4f  xorps   xmm0, xmm0
0x14000bb52  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x14000bb5a  mov     dword ptr [rsp+110h+FileAttributes], 80h; FileAttributes
0x14000bb62  mov     edx, 80100080h; DesiredAccess
0x14000bb67  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x14000bb6c  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14000bb74  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x14000bb7c  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x14000bb80  mov     [rbp+4Fh+FileHandle], r12
0x14000bb84  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x14000bb88  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14000bb8c  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000bb91  call    cs:__imp_ZwCreateFile
0x14000bb97  mov     ebx, eax
0x14000bb99  test    eax, eax
0x14000bb9b  js      short loc_14000BBB5
0x14000bb9d  mov     rax, [rbp+4Fh+FileHandle]
0x14000bba1  mov     rcx, r12
0x14000bba4  mov     [rsi+8], rax
0x14000bba8  mov     ebx, r12d
0x14000bbab  mov     [rbp+4Fh+FileHandle], rcx
0x14000bbaf  mov     byte ptr [rsi+30h], 1
0x14000bbb3  jmp     short loc_14000BBB9
0x14000bbb5  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x14000bbb9  test    rcx, rcx
0x14000bbbc  jz      short loc_14000BBC4
0x14000bbbe  call    cs:__imp_ZwClose
0x14000bbc4  test    ebx, ebx
0x14000bbc6  jns     short loc_14000BC40
0x14000bbc8  cmp     ebx, 0C000003Ah
0x14000bbce  jz      loc_14000BC9A
0x14000bbd4  cmp     ebx, 0C0000034h
0x14000bbda  jz      loc_14000BC9A
0x14000bbe0  cmp     ebx, 0C00000CCh
0x14000bbe6  jz      loc_14000BC9A
0x14000bbec  lea     eax, [rbx+3FFFFFEDh]
0x14000bbf2  cmp     eax, 30h ; '0'
0x14000bbf5  ja      short loc_14000BC07
0x14000bbf7  mov     rcx, 1000000008001h
0x14000bc01  bt      rcx, rax
0x14000bc05  jb      short loc_14000BC25
0x14000bc07  cmp     ebx, 0C00000BAh
0x14000bc0d  jz      short loc_14000BC25
0x14000bc0f  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x14000bc13  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x14000bc1a  mov     r8d, 0A1h
0x14000bc20  jmp     loc_14000BB0A
0x14000bc25  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x14000bc29  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x14000bc30  mov     r8d, 0A3h
0x14000bc36  mov     ecx, 3
0x14000bc3b  jmp     loc_14000BB0F
0x14000bc40  xor     eax, eax
0x14000bc42  mov     dword ptr [rsp+110h+AllocationSize], 5; FileInformationClass
0x14000bc4a  xorps   xmm0, xmm0
0x14000bc4d  mov     [rbp+4Fh+var_38], rax
0x14000bc51  xorps   xmm1, xmm1
0x14000bc54  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x14000bc58  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x14000bc5c  lea     r9d, [rax+18h]; Length
0x14000bc60  movups  [rbp+4Fh+FileInformation], xmm1
0x14000bc64  mov     rcx, [rsi+8]; FileHandle
0x14000bc68  lea     rdx, [rbp+4Fh+var_98]; IoStatusBlock
0x14000bc6c  call    cs:__imp_ZwQueryInformationFile
0x14000bc72  mov     ebx, eax
0x14000bc74  test    eax, eax
0x14000bc76  jns     short loc_14000BCA4
0x14000bc78  lea     r9, aNtqueryinforma; "NtQueryInformationFile failed [%x]"
0x14000bc7f  mov     r8d, 0B7h
0x14000bc85  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x14000bc8c  mov     dword ptr [rsp+110h+AllocationSize], eax
0x14000bc90  mov     ecx, 1
0x14000bc95  call    AslLogCallPrintf
0x14000bc9a  mov     rcx, rsi; P
0x14000bc9d  call    AslFileMappingDelete
0x14000bca2  jmp     short loc_14000BCC2
0x14000bca4  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x14000bca8  mov     ebx, r12d
0x14000bcab  mov     [rsi+18h], rax
0x14000bcaf  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x14000bcb3  neg     rax
0x14000bcb6  sbb     ecx, ecx
0x14000bcb8  neg     ecx
0x14000bcba  inc     ecx
0x14000bcbc  mov     [rsi+38h], ecx
0x14000bcbf  mov     [r15], rsi
0x14000bcc2  cmp     [rbp+4Fh+DestinationString.Buffer], rdi
0x14000bcc6  jz      short loc_14000BCD2
0x14000bcc8  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x14000bccc  call    cs:__imp_RtlFreeUnicodeString
0x14000bcd2  mov     eax, ebx
0x14000bcd4  jmp     short loc_14000BCDB
0x14000bcd6  mov     eax, 0C000000Dh
0x14000bcdb  mov     rcx, [rbp+4Fh+var_30]
0x14000bcdf  xor     rcx, rsp; StackCookie
0x14000bce2  call    __security_check_cookie
0x14000bce7  mov     rbx, [rsp+110h+arg_10]
0x14000bcef  add     rsp, 0F0h
0x14000bcf6  pop     r15
0x14000bcf8  pop     r12
0x14000bcfa  pop     rdi
0x14000bcfb  pop     rsi
0x14000bcfc  pop     rbp
0x14000bcfd  retn
```
