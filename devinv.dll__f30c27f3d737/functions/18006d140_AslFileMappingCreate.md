# AslFileMappingCreate

- ea: `0x18006d140`
- end: `0x18006d439`
- name: `AslFileMappingCreate`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180066d20`
- `0x1800740bc`

## callees

- `0x180005e40`
- `0x180006e1c`
- `0x180066c10`
- `0x1800680ac`
- `0x18006d140`
- `0x18006d440`

## import_xrefs

- `ntdll!ZwQueryInformationFile` at `0x18006d3a7`
- `ntdll!ZwQueryInformationFile` at `0x18006d3a7`
- `ntdll!ZwCreateFile` at `0x18006d2cc`
- `ntdll!ZwCreateFile` at `0x18006d2cc`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006d228`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006d228`
- `ntdll!ZwClose` at `0x18006d2f9`
- `ntdll!ZwClose` at `0x18006d2f9`
- `ntdll!RtlAllocateHeap` at `0x18006d1c7`
- `ntdll!RtlAllocateHeap` at `0x18006d1c7`
- `ntdll!RtlInitUnicodeString` at `0x18006d1aa`
- `ntdll!RtlInitUnicodeString` at `0x18006d1aa`
- `ntdll!RtlFreeUnicodeString` at `0x18006d407`
- `ntdll!RtlFreeUnicodeString` at `0x18006d407`

## string_xrefs

- `0x18006d238`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x18006d24a`: `AslFileMappingCreate`
- `0x18006d3c0`: `AslFileMappingCreate`
- `0x18006d34e`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x18006d364`: `RtlFileMapInitializeByFilePath failed %S [%x]`

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
0x18006d140  mov     [rsp-8+arg_10], rbx
0x18006d145  push    rbp
0x18006d146  push    rsi
0x18006d147  push    rdi
0x18006d148  push    r12
0x18006d14a  push    r15
0x18006d14c  lea     rbp, [rsp-2Fh]
0x18006d151  sub     rsp, 0F0h
0x18006d158  mov     rax, cs:__security_cookie
0x18006d15f  xor     rax, rsp
0x18006d162  mov     [rbp+4Fh+var_30], rax
0x18006d166  xor     eax, eax
0x18006d168  xorps   xmm0, xmm0
0x18006d16b  xor     r12d, r12d
0x18006d16e  mov     [rbp+4Fh+var_38], rax
0x18006d172  xorps   xmm1, xmm1
0x18006d175  mov     rdi, rdx
0x18006d178  mov     r15, rcx
0x18006d17b  movups  [rbp+4Fh+FileInformation], xmm0
0x18006d17f  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18006d183  movups  xmmword ptr [rbp+4Fh+var_98], xmm1
0x18006d187  test    rdx, rdx
0x18006d18a  jz      loc_18006D411
0x18006d190  cmp     [rdx], r12w
0x18006d194  jz      loc_18006D411
0x18006d19a  test    rcx, rcx
0x18006d19d  jz      loc_18006D411
0x18006d1a3  mov     [rcx], r12
0x18006d1a6  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18006d1aa  call    cs:__imp_RtlInitUnicodeString
0x18006d1b0  mov     rcx, gs:60h
0x18006d1b9  lea     edx, [r12+8]; Flags
0x18006d1be  lea     r8d, [r12+50h]; Size
0x18006d1c3  mov     rcx, [rcx+30h]; HeapHandle
0x18006d1c7  call    cs:__imp_RtlAllocateHeap
0x18006d1cd  mov     rsi, rax
0x18006d1d0  test    rax, rax
0x18006d1d3  jnz     short loc_18006D1DF
0x18006d1d5  mov     ebx, 0C0000017h
0x18006d1da  jmp     loc_18006D3FD
0x18006d1df  mov     rdx, rdi
0x18006d1e2  mov     rcx, rsi
0x18006d1e5  call    AslStringDuplicate
0x18006d1ea  mov     ebx, eax
0x18006d1ec  test    eax, eax
0x18006d1ee  jns     short loc_18006D202
0x18006d1f0  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x18006d1f7  mov     r8d, 7Bh ; '{'
0x18006d1fd  jmp     loc_18006D3C0
0x18006d202  mov     r8d, 0Ch; MaxCount
0x18006d208  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x18006d20f  mov     rcx, rdi; String1
0x18006d212  call    _wcsnicmp
0x18006d217  test    eax, eax
0x18006d219  jz      short loc_18006D260
0x18006d21b  xor     r9d, r9d
0x18006d21e  lea     rdx, [rbp+4Fh+DestinationString]
0x18006d222  xor     r8d, r8d
0x18006d225  mov     rcx, rdi
0x18006d228  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18006d22e  mov     ebx, eax
0x18006d230  test    eax, eax
0x18006d232  jns     short loc_18006D260
0x18006d234  mov     dword ptr [rsp+110h+FileAttributes], eax
0x18006d238  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18006d23f  mov     r8d, 94h
0x18006d245  mov     ecx, 1
0x18006d24a  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x18006d251  mov     [rsp+110h+AllocationSize], rdi
0x18006d256  call    AslLogCallPrintf
0x18006d25b  jmp     loc_18006D3D5
0x18006d260  mov     [rsp+110h+EaLength], r12d; EaLength
0x18006d265  lea     rax, [rbp+4Fh+DestinationString]
0x18006d269  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x18006d26e  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x18006d272  mov     [rsp+110h+CreateOptions], 60h ; '`'; CreateOptions
0x18006d27a  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18006d27e  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18006d286  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x18006d28a  xorps   xmm0, xmm0
0x18006d28d  mov     [rsp+110h+ShareAccess], 5; ShareAccess
0x18006d295  mov     dword ptr [rsp+110h+FileAttributes], 80h; FileAttributes
0x18006d29d  mov     edx, 80100080h; DesiredAccess
0x18006d2a2  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x18006d2a7  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18006d2af  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18006d2b7  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x18006d2bb  mov     [rbp+4Fh+FileHandle], r12
0x18006d2bf  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x18006d2c3  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18006d2c7  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d2cc  call    cs:__imp_ZwCreateFile
0x18006d2d2  mov     ebx, eax
0x18006d2d4  test    eax, eax
0x18006d2d6  js      short loc_18006D2F0
0x18006d2d8  mov     rax, [rbp+4Fh+FileHandle]
0x18006d2dc  mov     rcx, r12
0x18006d2df  mov     [rsi+8], rax
0x18006d2e3  mov     ebx, r12d
0x18006d2e6  mov     [rbp+4Fh+FileHandle], rcx
0x18006d2ea  mov     byte ptr [rsi+30h], 1
0x18006d2ee  jmp     short loc_18006D2F4
0x18006d2f0  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x18006d2f4  test    rcx, rcx
0x18006d2f7  jz      short loc_18006D2FF
0x18006d2f9  call    cs:__imp_ZwClose
0x18006d2ff  test    ebx, ebx
0x18006d301  jns     short loc_18006D37B
0x18006d303  cmp     ebx, 0C000003Ah
0x18006d309  jz      loc_18006D3D5
0x18006d30f  cmp     ebx, 0C0000034h
0x18006d315  jz      loc_18006D3D5
0x18006d31b  cmp     ebx, 0C00000CCh
0x18006d321  jz      loc_18006D3D5
0x18006d327  lea     eax, [rbx+3FFFFFEDh]
0x18006d32d  cmp     eax, 30h ; '0'
0x18006d330  ja      short loc_18006D342
0x18006d332  mov     rcx, 1000000008001h
0x18006d33c  bt      rcx, rax
0x18006d340  jb      short loc_18006D360
0x18006d342  cmp     ebx, 0C00000BAh
0x18006d348  jz      short loc_18006D360
0x18006d34a  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x18006d34e  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18006d355  mov     r8d, 0A1h
0x18006d35b  jmp     loc_18006D245
0x18006d360  mov     dword ptr [rsp+110h+FileAttributes], ebx
0x18006d364  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18006d36b  mov     r8d, 0A3h
0x18006d371  mov     ecx, 3
0x18006d376  jmp     loc_18006D24A
0x18006d37b  xor     eax, eax
0x18006d37d  mov     dword ptr [rsp+110h+AllocationSize], 5; FileInformationClass
0x18006d385  xorps   xmm0, xmm0
0x18006d388  mov     [rbp+4Fh+var_38], rax
0x18006d38c  xorps   xmm1, xmm1
0x18006d38f  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x18006d393  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x18006d397  lea     r9d, [rax+18h]; Length
0x18006d39b  movups  [rbp+4Fh+FileInformation], xmm1
0x18006d39f  mov     rcx, [rsi+8]; FileHandle
0x18006d3a3  lea     rdx, [rbp+4Fh+var_98]; IoStatusBlock
0x18006d3a7  call    cs:__imp_ZwQueryInformationFile
0x18006d3ad  mov     ebx, eax
0x18006d3af  test    eax, eax
0x18006d3b1  jns     short loc_18006D3DF
0x18006d3b3  lea     r9, aNtqueryinforma; "NtQueryInformationFile failed [%x]"
0x18006d3ba  mov     r8d, 0B7h
0x18006d3c0  lea     rdx, aAslfilemapping_13; "AslFileMappingCreate"
0x18006d3c7  mov     dword ptr [rsp+110h+AllocationSize], eax
0x18006d3cb  mov     ecx, 1
0x18006d3d0  call    AslLogCallPrintf
0x18006d3d5  mov     rcx, rsi; P
0x18006d3d8  call    AslFileMappingDelete
0x18006d3dd  jmp     short loc_18006D3FD
0x18006d3df  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x18006d3e3  mov     ebx, r12d
0x18006d3e6  mov     [rsi+18h], rax
0x18006d3ea  mov     rax, qword ptr [rbp+4Fh+FileInformation+8]
0x18006d3ee  neg     rax
0x18006d3f1  sbb     ecx, ecx
0x18006d3f3  neg     ecx
0x18006d3f5  inc     ecx
0x18006d3f7  mov     [rsi+38h], ecx
0x18006d3fa  mov     [r15], rsi
0x18006d3fd  cmp     [rbp+4Fh+DestinationString.Buffer], rdi
0x18006d401  jz      short loc_18006D40D
0x18006d403  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x18006d407  call    cs:__imp_RtlFreeUnicodeString
0x18006d40d  mov     eax, ebx
0x18006d40f  jmp     short loc_18006D416
0x18006d411  mov     eax, 0C000000Dh
0x18006d416  mov     rcx, [rbp+4Fh+var_30]
0x18006d41a  xor     rcx, rsp; StackCookie
0x18006d41d  call    __security_check_cookie
0x18006d422  mov     rbx, [rsp+110h+arg_10]
0x18006d42a  add     rsp, 0F0h
0x18006d431  pop     r15
0x18006d433  pop     r12
0x18006d435  pop     rdi
0x18006d436  pop     rsi
0x18006d437  pop     rbp
0x18006d438  retn
```
