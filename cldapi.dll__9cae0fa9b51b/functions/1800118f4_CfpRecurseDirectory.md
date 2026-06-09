# CfpRecurseDirectory

- ea: `0x1800118f4`
- end: `0x180011cc3`
- name: `CfpRecurseDirectory`
- size: `975`
- prototype: `__int64 __fastcall(int, int, int, int, int, HANDLE FileHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007f30`
- `0x1800118f4`

## callees

- `0x18000b960`
- `0x18000f100`
- `0x1800118f4`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180011b52`
- `ntdll!NtCreateFile` at `0x180011b52`
- `ntdll!RtlIsPartialPlaceholder` at `0x18001196f`
- `ntdll!RtlIsPartialPlaceholder` at `0x18001196f`
- `ntdll!RtlEqualUnicodeString` at `0x180011ab3`
- `ntdll!RtlEqualUnicodeString` at `0x180011ad2`
- `ntdll!RtlEqualUnicodeString` at `0x180011ab3`
- `ntdll!RtlEqualUnicodeString` at `0x180011ad2`
- `ntdll!RtlNtStatusToDosError` at `0x180011a4c`
- `ntdll!RtlNtStatusToDosError` at `0x180011b72`
- `ntdll!RtlNtStatusToDosError` at `0x180011bd7`
- `ntdll!RtlNtStatusToDosError` at `0x180011a4c`
- `ntdll!RtlNtStatusToDosError` at `0x180011b72`
- `ntdll!RtlNtStatusToDosError` at `0x180011bd7`
- `ntdll!NtClose` at `0x180011c10`
- `ntdll!NtClose` at `0x180011ca2`
- `ntdll!NtClose` at `0x180011c10`
- `ntdll!NtClose` at `0x180011ca2`
- `ntdll!NtQueryDirectoryFile` at `0x180011a30`
- `ntdll!NtQueryDirectoryFile` at `0x180011a30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800119b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800119b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800119ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800119ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011c8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011c8c`

## pseudocode

```c
__int64 __fastcall CfpRecurseDirectory(
        void *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 FileHandle)
{
  void *v6; // r15
  signed int v7; // ebx
  unsigned int *FileInformation; // rdi
  BOOLEAN v9; // r14
  HANDLE ProcessHeap; // rax
  NTSTATUS v11; // eax
  signed int v12; // eax
  unsigned int *v13; // rsi
  NTSTATUS v14; // r15d
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  HANDLE v18; // rax
  UNICODE_STRING String1; // [rsp+68h] [rbp-61h] BYREF
  UNICODE_STRING String2; // [rsp+78h] [rbp-51h] BYREF
  UNICODE_STRING v22; // [rsp+88h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-21h] BYREF

  *(_QWORD *)&String2.Length = 262146;
  *(_QWORD *)&v22.Length = 393220;
  v6 = a1;
  FileHandle = -1;
  String2.Buffer = L".";
  v22.Buffer = L"..";
  v7 = 0;
  FileInformation = 0;
  if ( (a3 & 0x10) == 0 )
    goto LABEL_30;
  v9 = 1;
  if ( (unsigned __int8)RtlIsPartialPlaceholder(a3, a4) )
    CfUpdatePlaceholder((int)v6, 0, 0, 0, 0, 0, 16, 0, 0);
LABEL_4:
  while ( 1 )
  {
    IoStatusBlock = 0;
    if ( !FileInformation )
    {
      ProcessHeap = GetProcessHeap();
      FileInformation = (unsigned int *)HeapAlloc(ProcessHeap, 0, 0x400u);
      v7 = FileInformation == 0 ? 8 : 0;
      if ( !FileInformation )
        v7 |= 0x80070000;
      if ( v7 < 0 )
        break;
    }
    v11 = NtQueryDirectoryFile(
            v6,
            0,
            0,
            0,
            &IoStatusBlock,
            FileInformation,
            0x400u,
            FileFullDirectoryInformation,
            0,
            0,
            v9);
    v9 = 0;
    if ( v11 == -2147483642 )
      break;
    v12 = RtlNtStatusToDosError(v11);
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 < 0 )
      break;
    v13 = FileInformation;
    if ( FileInformation )
    {
      while ( 1 )
      {
        *(_QWORD *)&String1.Length = 0;
        String1.Buffer = (PWSTR)(v13 + 17);
        memset(&ObjectAttributes, 0, 44);
        String1.Length = *((_WORD *)v13 + 30);
        String1.MaximumLength = *((_WORD *)v13 + 30);
        if ( !RtlEqualUnicodeString(&String1, &String2, 0) && !RtlEqualUnicodeString(&String1, &v22, 0) )
        {
          ObjectAttributes.ObjectName = &String1;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = v6;
          ObjectAttributes.Attributes = 64;
          v14 = NtCreateFile(
                  (PHANDLE)&FileHandle,
                  (v13[14] & 0x10 | 0x1101800) >> 4,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0x80u,
                  7u,
                  1u,
                  0x200020u,
                  0,
                  0);
          v15 = RtlNtStatusToDosError((a5 & 1) != 0 ? v14 : 0);
          v7 = v15;
          if ( v15 > 0 )
            v7 = (unsigned __int16)v15 | 0x80070000;
          if ( v7 < 0 )
          {
            v6 = a1;
            goto LABEL_30;
          }
          if ( v14 < 0 )
          {
            v6 = a1;
          }
          else
          {
            CfpRecurseDirectory(FileHandle, 65920, v13[14], v13[16], a5 & 0xFFFFFFFD, CfpProcessUnregistration);
            v16 = RtlNtStatusToDosError((a5 & 1) != 0 ? v14 : 0);
            v7 = v16;
            if ( v16 > 0 )
              v7 = (unsigned __int16)v16 | 0x80070000;
            v6 = a1;
            if ( v7 < 0 )
              goto LABEL_30;
          }
        }
        if ( FileHandle != -1 )
        {
          NtClose((HANDLE)FileHandle);
          FileHandle = -1;
        }
        if ( *v13 )
        {
          v13 = (unsigned int *)((char *)v13 + *v13);
          if ( v13 )
            continue;
        }
        goto LABEL_4;
      }
    }
  }
LABEL_30:
  if ( (a5 & 2) == 0 && (v7 >= 0 || (a5 & 1) == 0) )
  {
    v17 = CfpProcessUnregistration(v6);
    if ( v7 >= 0 )
      v7 = v17;
  }
  if ( FileInformation )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, FileInformation);
  }
  if ( FileHandle != -1 )
    NtClose((HANDLE)FileHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800118f4  mov     rax, rsp
0x1800118f7  mov     [rax+20h], r9d
0x1800118fb  mov     [rax+18h], r8d
0x1800118ff  mov     [rax+8], rcx
0x180011903  push    rbp
0x180011904  push    rbx
0x180011905  push    rsi
0x180011906  push    rdi
0x180011907  push    r12
0x180011909  push    r14
0x18001190b  push    r15
0x18001190d  lea     rbp, [rax-47h]
0x180011911  sub     rsp, 0D0h
0x180011918  xor     r12d, r12d
0x18001191b  mov     qword ptr [rbp+3Fh+String2.Length], 40002h
0x180011923  mov     qword ptr [rbp+3Fh+var_80.Length], 60004h
0x18001192b  mov     r15, rcx
0x18001192e  mov     [rbp+3Fh+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180011936  lea     rcx, asc_180022950; "."
0x18001193d  mov     [rbp+3Fh+String2.Buffer], rcx
0x180011941  lea     rcx, asc_180022948; ".."
0x180011948  mov     [rbp+3Fh+var_80.Buffer], rcx
0x18001194c  mov     r10d, r9d
0x18001194f  mov     eax, r8d
0x180011952  mov     esi, 2
0x180011957  mov     ebx, r12d
0x18001195a  mov     edi, r12d
0x18001195d  test    r8b, 10h
0x180011961  jz      loc_180011C4E
0x180011967  mov     edx, r9d
0x18001196a  mov     ecx, eax
0x18001196c  mov     r14b, 1
0x18001196f  call    cs:__imp_RtlIsPartialPlaceholder
0x180011976  nop     dword ptr [rax+rax+00h]
0x18001197b  test    al, al
0x18001197d  jz      short loc_1800119AB
0x18001197f  mov     qword ptr [rsp+100h+ReturnSingleEntry], r12; __int64
0x180011984  xor     r9d, r9d; int
0x180011987  mov     qword ptr [rsp+100h+FileInformationClass], r12; __int64
0x18001198c  xor     r8d, r8d; int
0x18001198f  mov     [rsp+100h+Length], 10h; int
0x180011997  xor     edx, edx; int
0x180011999  mov     dword ptr [rsp+100h+FileInformation], r12d; int
0x18001199e  mov     rcx, r15; int
0x1800119a1  mov     [rsp+100h+IoStatusBlock], r12; Src
0x1800119a6  call    CfUpdatePlaceholder
0x1800119ab  xorps   xmm0, xmm0
0x1800119ae  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x1800119b2  test    rdi, rdi
0x1800119b5  jnz     short loc_1800119FC
0x1800119b7  call    cs:__imp_GetProcessHeap
0x1800119be  nop     dword ptr [rax+rax+00h]
0x1800119c3  xor     edx, edx; dwFlags
0x1800119c5  mov     r8d, 400h; dwBytes
0x1800119cb  mov     rcx, rax; hHeap
0x1800119ce  call    cs:__imp_HeapAlloc
0x1800119d5  nop     dword ptr [rax+rax+00h]
0x1800119da  mov     rdi, rax
0x1800119dd  neg     rax
0x1800119e0  sbb     ebx, ebx
0x1800119e2  not     ebx
0x1800119e4  and     ebx, 8
0x1800119e7  mov     eax, ebx
0x1800119e9  or      eax, 80070000h
0x1800119ee  test    rdi, rdi
0x1800119f1  cmovz   ebx, eax
0x1800119f4  test    ebx, ebx
0x1800119f6  js      loc_180011C47
0x1800119fc  mov     [rsp+50h], r14b; RestartScan
0x180011a01  lea     rax, [rbp+3Fh+var_70]
0x180011a05  mov     [rsp+100h+FileName], r12; FileName
0x180011a0a  xor     r9d, r9d; ApcContext
0x180011a0d  mov     [rsp+100h+ReturnSingleEntry], r12b; ReturnSingleEntry
0x180011a12  xor     r8d, r8d; ApcRoutine
0x180011a15  mov     [rsp+100h+FileInformationClass], esi; FileInformationClass
0x180011a19  xor     edx, edx; Event
0x180011a1b  mov     [rsp+100h+Length], 400h; Length
0x180011a23  mov     rcx, r15; FileHandle
0x180011a26  mov     [rsp+100h+FileInformation], rdi; FileInformation
0x180011a2b  mov     [rsp+100h+IoStatusBlock], rax; IoStatusBlock
0x180011a30  call    cs:__imp_NtQueryDirectoryFile
0x180011a37  nop     dword ptr [rax+rax+00h]
0x180011a3c  mov     r14b, r12b
0x180011a3f  cmp     eax, 80000006h
0x180011a44  jz      loc_180011C47
0x180011a4a  mov     ecx, eax; Status
0x180011a4c  call    cs:__imp_RtlNtStatusToDosError
0x180011a53  nop     dword ptr [rax+rax+00h]
0x180011a58  mov     ebx, eax
0x180011a5a  test    eax, eax
0x180011a5c  jle     short loc_180011A67
0x180011a5e  movzx   ebx, ax
0x180011a61  or      ebx, 80070000h
0x180011a67  test    ebx, ebx
0x180011a69  js      loc_180011C47
0x180011a6f  mov     rsi, rdi
0x180011a72  test    rdi, rdi
0x180011a75  jz      loc_180011C34
0x180011a7b  mov     qword ptr [rbp+3Fh+String1.Length], r12
0x180011a7f  lea     rdx, [rbp+3Fh+String2]; String2
0x180011a83  xor     eax, eax
0x180011a85  lea     rcx, [rbp+3Fh+String1]; String1
0x180011a89  xorps   xmm0, xmm0
0x180011a8c  lea     rax, [rsi+44h]
0x180011a90  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x180011a94  mov     [rbp+3Fh+String1.Buffer], rax
0x180011a98  xor     r8d, r8d; CaseInsensitive
0x180011a9b  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x180011a9f  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x180011aa3  movzx   eax, word ptr [rsi+3Ch]
0x180011aa7  mov     [rbp+3Fh+String1.Length], ax
0x180011aab  movzx   eax, word ptr [rsi+3Ch]
0x180011aaf  mov     [rbp+3Fh+String1.MaximumLength], ax
0x180011ab3  call    cs:__imp_RtlEqualUnicodeString
0x180011aba  nop     dword ptr [rax+rax+00h]
0x180011abf  test    al, al
0x180011ac1  jnz     loc_180011C06
0x180011ac7  xor     r8d, r8d; CaseInsensitive
0x180011aca  lea     rdx, [rbp+3Fh+var_80]; String2
0x180011ace  lea     rcx, [rbp+3Fh+String1]; String1
0x180011ad2  call    cs:__imp_RtlEqualUnicodeString
0x180011ad9  nop     dword ptr [rax+rax+00h]
0x180011ade  test    al, al
0x180011ae0  jnz     loc_180011C06
0x180011ae6  mov     [rsp+50h], r12d; EaLength
0x180011aeb  lea     rax, [rbp+3Fh+String1]
0x180011aef  mov     [rsp+100h+FileName], r12; EaBuffer
0x180011af4  lea     r9, [rbp+3Fh+var_70]; IoStatusBlock
0x180011af8  mov     dword ptr [rsp+100h+ReturnSingleEntry], 200020h; CreateOptions
0x180011b00  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180011b04  mov     [rsp+100h+FileInformationClass], 1; CreateDisposition
0x180011b0c  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x180011b10  xorps   xmm0, xmm0
0x180011b13  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x180011b17  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180011b1c  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x180011b23  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r15
0x180011b27  mov     [rbp+3Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180011b2e  mov     edx, [rsi+38h]
0x180011b31  and     edx, 10h
0x180011b34  mov     [rsp+100h+Length], 7; ShareAccess
0x180011b3c  or      edx, 1101800h
0x180011b42  mov     dword ptr [rsp+100h+FileInformation], 80h; FileAttributes
0x180011b4a  shr     edx, 4; DesiredAccess
0x180011b4d  mov     [rsp+100h+IoStatusBlock], r12; AllocationSize
0x180011b52  call    cs:__imp_NtCreateFile
0x180011b59  nop     dword ptr [rax+rax+00h]
0x180011b5e  mov     r12d, [rbp+3Fh+arg_20]
0x180011b62  mov     r15d, eax
0x180011b65  and     r12d, 1
0x180011b69  mov     ecx, r12d
0x180011b6c  neg     ecx
0x180011b6e  sbb     ecx, ecx
0x180011b70  and     ecx, eax; Status
0x180011b72  call    cs:__imp_RtlNtStatusToDosError
0x180011b79  nop     dword ptr [rax+rax+00h]
0x180011b7e  mov     ebx, eax
0x180011b80  test    eax, eax
0x180011b82  jle     short loc_180011B8D
0x180011b84  movzx   ebx, ax
0x180011b87  or      ebx, 80070000h
0x180011b8d  test    ebx, ebx
0x180011b8f  js      loc_180011C3E
0x180011b95  test    r15d, r15d
0x180011b98  js      short loc_180011BFF
0x180011b9a  mov     eax, [rbp+3Fh+arg_20]
0x180011b9d  lea     rcx, CfpProcessUnregistration
0x180011ba4  mov     r9d, [rsi+40h]; int
0x180011ba8  and     eax, 0FFFFFFFDh
0x180011bab  mov     r8d, [rsi+38h]; int
0x180011baf  mov     edx, 10180h; int
0x180011bb4  mov     qword ptr [rsp+100h+Length], 0
0x180011bbd  mov     [rsp+100h+FileInformation], rcx; FileHandle
0x180011bc2  mov     rcx, [rbp+3Fh+FileHandle]; int
0x180011bc6  mov     dword ptr [rsp+100h+IoStatusBlock], eax; int
0x180011bca  call    CfpRecurseDirectory
0x180011bcf  neg     r12d
0x180011bd2  sbb     ecx, ecx
0x180011bd4  and     ecx, r15d; Status
0x180011bd7  call    cs:__imp_RtlNtStatusToDosError
0x180011bde  nop     dword ptr [rax+rax+00h]
0x180011be3  xor     r12d, r12d
0x180011be6  mov     ebx, eax
0x180011be8  test    eax, eax
0x180011bea  jle     short loc_180011BF5
0x180011bec  movzx   ebx, ax
0x180011bef  or      ebx, 80070000h
0x180011bf5  mov     r15, [rbp+3Fh+arg_0]
0x180011bf9  test    ebx, ebx
0x180011bfb  js      short loc_180011C42
0x180011bfd  jmp     short loc_180011C06
0x180011bff  mov     r15, [rbp+3Fh+arg_0]
0x180011c03  xor     r12d, r12d
0x180011c06  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x180011c0a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011c0e  jz      short loc_180011C24
0x180011c10  call    cs:__imp_NtClose
0x180011c17  nop     dword ptr [rax+rax+00h]
0x180011c1c  mov     [rbp+3Fh+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180011c24  cmp     [rsi], r12d
0x180011c27  jz      short loc_180011C34
0x180011c29  mov     eax, [rsi]
0x180011c2b  add     rsi, rax
0x180011c2e  jnz     loc_180011A7B
0x180011c34  mov     esi, 2
0x180011c39  jmp     loc_1800119AB
0x180011c3e  mov     r15, [rbp+3Fh+arg_0]
0x180011c42  mov     esi, 2
0x180011c47  mov     eax, [rbp+3Fh+arg_10]
0x180011c4a  mov     r10d, [rbp+3Fh+arg_18]
0x180011c4e  test    byte ptr [rbp+3Fh+arg_20], sil
0x180011c52  jnz     short loc_180011C73
0x180011c54  test    ebx, ebx
0x180011c56  jns     short loc_180011C5E
0x180011c58  test    byte ptr [rbp+3Fh+arg_20], 1
0x180011c5c  jnz     short loc_180011C73
0x180011c5e  xor     r9d, r9d
0x180011c61  mov     r8d, r10d
0x180011c64  mov     edx, eax
0x180011c66  mov     rcx, r15; hFile
0x180011c69  call    CfpProcessUnregistration
0x180011c6e  test    ebx, ebx
0x180011c70  cmovns  ebx, eax
0x180011c73  test    rdi, rdi
0x180011c76  jz      short loc_180011C98
0x180011c78  call    cs:__imp_GetProcessHeap
0x180011c7f  nop     dword ptr [rax+rax+00h]
0x180011c84  mov     r8, rdi; lpMem
0x180011c87  xor     edx, edx; dwFlags
0x180011c89  mov     rcx, rax; hHeap
0x180011c8c  call    cs:__imp_HeapFree
0x180011c93  nop     dword ptr [rax+rax+00h]
0x180011c98  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x180011c9c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011ca0  jz      short loc_180011CAE
0x180011ca2  call    cs:__imp_NtClose
0x180011ca9  nop     dword ptr [rax+rax+00h]
0x180011cae  mov     eax, ebx
0x180011cb0  add     rsp, 0D0h
0x180011cb7  pop     r15
0x180011cb9  pop     r14
0x180011cbb  pop     r12
0x180011cbd  pop     rdi
0x180011cbe  pop     rsi
0x180011cbf  pop     rbx
0x180011cc0  pop     rbp
0x180011cc1  retn
```
