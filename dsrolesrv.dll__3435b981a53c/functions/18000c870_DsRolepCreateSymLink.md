# DsRolepCreateSymLink

- ea: `0x18000c870`
- end: `0x18000cad7`
- name: `DsRolepCreateSymLink`
- size: `615`
- prototype: `ULONG __fastcall(const WCHAR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000cae0`

## callees

- `0x18000c870`
- `0x180020dbc`
- `0x18002c012`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18000c969`
- `ntdll!NtCreateFile` at `0x18000c969`
- `ntdll!NtFsControlFile` at `0x18000ca45`
- `ntdll!NtFsControlFile` at `0x18000ca45`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000c8c2`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000c8dd`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000c8c2`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000c8dd`
- `ntdll!RtlFreeUnicodeString` at `0x18000ca81`
- `ntdll!RtlFreeUnicodeString` at `0x18000ca92`
- `ntdll!RtlFreeUnicodeString` at `0x18000ca81`
- `ntdll!RtlFreeUnicodeString` at `0x18000ca92`
- `ntdll!RtlAllocateHeap` at `0x18000c999`
- `ntdll!RtlAllocateHeap` at `0x18000c999`
- `ntdll!RtlNtStatusToDosError` at `0x18000cab9`
- `ntdll!RtlNtStatusToDosError` at `0x18000cab9`
- `ntdll!RtlFreeHeap` at `0x18000ca5f`
- `ntdll!RtlFreeHeap` at `0x18000ca5f`
- `ntdll!NtClose` at `0x18000ca69`
- `ntdll!NtClose` at `0x18000ca69`
- `ntdll!RtlInitUnicodeString` at `0x18000c8f2`
- `ntdll!RtlInitUnicodeString` at `0x18000c8f2`

## string_xrefs

- `0x18000caa6`: `Failed to create the link between %ws and %ws: 0x%lx\n`

## pseudocode

```c
ULONG __fastcall DsRolepCreateSymLink(const WCHAR *a1, const WCHAR *a2)
{
  int v4; // ebx
  int v5; // ebx
  char *Heap; // rax
  char *v7; // rdi
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-69h]
  int CreateDisposition; // [rsp+38h] [rbp-51h]
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-19h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+80h] [rbp-9h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+17h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+77h] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  NtPathName = 0;
  UnicodeString = 0;
  DestinationString = 0;
  if ( RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) && RtlDosPathNameToNtPathName_U(a2, &UnicodeString, 0, 0) )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &NtPathName;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = NtCreateFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x200020u, 0, 0);
    if ( v4 >= 0 )
    {
      v5 = DestinationString.Length + 12 + UnicodeString.Length;
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v5 + 8));
      v7 = Heap;
      if ( Heap )
      {
        *((_WORD *)Heap + 2) = v5;
        *(_DWORD *)(Heap + 6) = 0;
        *((_WORD *)Heap + 5) = UnicodeString.Length;
        *((_WORD *)Heap + 6) = UnicodeString.Length + 2;
        *((_WORD *)Heap + 7) = DestinationString.Length;
        memcpy_0(Heap + 16, UnicodeString.Buffer, UnicodeString.Length);
        memcpy_0(&v7[UnicodeString.Length + 18], DestinationString.Buffer, DestinationString.Length);
        CreateDisposition = *((unsigned __int16 *)v7 + 2) + 8;
        *(_DWORD *)v7 = -1610612733;
        v4 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900A4u, v7, CreateDisposition, 0, 0);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      }
      else
      {
        v4 = -1073741670;
      }
      NtClose(FileHandle);
    }
  }
  else
  {
    v4 = -1073741670;
  }
  if ( NtPathName.Buffer )
    RtlFreeUnicodeString(&NtPathName);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v4 < 0 )
  {
    LODWORD(AllocationSize) = v4;
    DsRolepLogPrintRoutine(1, "Failed to create the link between %ws and %ws: 0x%lx\n", a1, a2, AllocationSize);
  }
  return RtlNtStatusToDosError(v4);
}

```

## disassembly

```asm
0x18000c870  mov     [rsp-8+arg_0], rbx
0x18000c875  mov     [rsp-8+arg_8], rsi
0x18000c87a  push    rbp
0x18000c87b  push    rdi
0x18000c87c  push    r14
0x18000c87e  lea     rbp, [rsp-47h]
0x18000c883  sub     rsp, 0D0h
0x18000c88a  xorps   xmm0, xmm0
0x18000c88d  xorps   xmm1, xmm1
0x18000c890  mov     rsi, rdx
0x18000c893  xor     eax, eax
0x18000c895  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000c899  xor     r9d, r9d; DirectoryInfo
0x18000c89c  mov     [rbp+57h+FileHandle], rax
0x18000c8a0  xor     r8d, r8d; NtFileNamePart
0x18000c8a3  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18000c8a7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000c8ab  mov     r14, rcx
0x18000c8ae  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000c8b2  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000c8b6  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm1
0x18000c8ba  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x18000c8be  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18000c8c2  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000c8c8  test    al, al
0x18000c8ca  jz      loc_18000CA71
0x18000c8d0  xor     r9d, r9d; DirectoryInfo
0x18000c8d3  lea     rdx, [rbp+57h+UnicodeString]; NtPathName
0x18000c8d7  xor     r8d, r8d; NtFileNamePart
0x18000c8da  mov     rcx, rsi; DosPathName
0x18000c8dd  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000c8e3  test    al, al
0x18000c8e5  jz      loc_18000CA71
0x18000c8eb  mov     rdx, rsi; SourceString
0x18000c8ee  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000c8f2  call    cs:__imp_RtlInitUnicodeString
0x18000c8f8  mov     [rsp+0E0h+EaLength], 0; EaLength
0x18000c900  lea     rax, [rbp+57h+NtPathName]
0x18000c904  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x18000c90d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000c911  mov     [rsp+0E0h+CreateOptions], 200020h; CreateOptions
0x18000c919  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000c91d  mov     [rsp+0E0h+CreateDisposition], 1; CreateDisposition
0x18000c925  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000c929  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x18000c931  xorps   xmm0, xmm0
0x18000c934  mov     [rsp+0E0h+FileAttributes], 80h; FileAttributes
0x18000c93c  mov     edx, 100002h; DesiredAccess
0x18000c941  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x18000c94a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000c951  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000c959  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000c960  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000c964  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c969  call    cs:__imp_NtCreateFile
0x18000c96f  mov     ebx, eax
0x18000c971  test    eax, eax
0x18000c973  js      loc_18000CA76
0x18000c979  movzx   ecx, [rbp+57h+DestinationString.Length]
0x18000c97d  xor     edx, edx; Flags
0x18000c97f  movzx   ebx, [rbp+57h+UnicodeString.Length]
0x18000c983  add     ecx, 0Ch
0x18000c986  add     ebx, ecx
0x18000c988  mov     rcx, gs:60h
0x18000c991  mov     rcx, [rcx+30h]; HeapHandle
0x18000c995  lea     r8d, [rbx+8]; Size
0x18000c999  call    cs:__imp_RtlAllocateHeap
0x18000c99f  mov     rdi, rax
0x18000c9a2  test    rax, rax
0x18000c9a5  jnz     short loc_18000C9B1
0x18000c9a7  mov     ebx, 0C000009Ah
0x18000c9ac  jmp     loc_18000CA65
0x18000c9b1  mov     [rax+4], bx
0x18000c9b5  lea     rcx, [rdi+10h]; void *
0x18000c9b9  xor     eax, eax
0x18000c9bb  mov     [rdi+6], eax
0x18000c9be  movzx   eax, [rbp+57h+UnicodeString.Length]
0x18000c9c2  mov     [rdi+0Ah], ax
0x18000c9c6  movzx   eax, [rbp+57h+UnicodeString.Length]
0x18000c9ca  add     ax, 2
0x18000c9ce  mov     [rdi+0Ch], ax
0x18000c9d2  movzx   eax, [rbp+57h+DestinationString.Length]
0x18000c9d6  mov     [rdi+0Eh], ax
0x18000c9da  movzx   r8d, [rbp+57h+UnicodeString.Length]; Size
0x18000c9df  mov     rdx, [rbp+57h+UnicodeString.Buffer]; Src
0x18000c9e3  call    memcpy_0
0x18000c9e8  movzx   ecx, [rbp+57h+UnicodeString.Length]
0x18000c9ec  movzx   r8d, [rbp+57h+DestinationString.Length]; Size
0x18000c9f1  add     rcx, 12h
0x18000c9f5  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x18000c9f9  add     rcx, rdi; void *
0x18000c9fc  call    memcpy_0
0x18000ca01  movzx   eax, word ptr [rdi+4]
0x18000ca05  xor     r9d, r9d; ApcContext
0x18000ca08  mov     dword ptr [rsp+0E0h+EaBuffer], 0; OutputBufferLength
0x18000ca10  add     eax, 8
0x18000ca13  mov     qword ptr [rsp+0E0h+CreateOptions], 0; OutputBuffer
0x18000ca1c  xor     r8d, r8d; ApcRoutine
0x18000ca1f  mov     [rsp+0E0h+CreateDisposition], eax; InputBufferLength
0x18000ca23  xor     edx, edx; Event
0x18000ca25  mov     qword ptr [rsp+0E0h+ShareAccess], rdi; InputBuffer
0x18000ca2a  lea     rax, [rbp+57h+IoStatusBlock]
0x18000ca2e  mov     dword ptr [rdi], 0A0000003h
0x18000ca34  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000ca38  mov     [rsp+0E0h+FileAttributes], 900A4h; FsControlCode
0x18000ca40  mov     [rsp+0E0h+AllocationSize], rax; IoStatusBlock
0x18000ca45  call    cs:__imp_NtFsControlFile
0x18000ca4b  mov     rcx, gs:60h
0x18000ca54  mov     r8, rdi; P
0x18000ca57  xor     edx, edx; Flags
0x18000ca59  mov     ebx, eax
0x18000ca5b  mov     rcx, [rcx+30h]; HeapHandle
0x18000ca5f  call    cs:__imp_RtlFreeHeap
0x18000ca65  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18000ca69  call    cs:__imp_NtClose
0x18000ca6f  jmp     short loc_18000CA76
0x18000ca71  mov     ebx, 0C000009Ah
0x18000ca76  cmp     [rbp+57h+NtPathName.Buffer], 0
0x18000ca7b  jz      short loc_18000CA87
0x18000ca7d  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18000ca81  call    cs:__imp_RtlFreeUnicodeString
0x18000ca87  cmp     [rbp+57h+UnicodeString.Buffer], 0
0x18000ca8c  jz      short loc_18000CA98
0x18000ca8e  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18000ca92  call    cs:__imp_RtlFreeUnicodeString
0x18000ca98  test    ebx, ebx
0x18000ca9a  jns     short loc_18000CAB7
0x18000ca9c  mov     r9, rsi
0x18000ca9f  mov     dword ptr [rsp+0E0h+AllocationSize], ebx
0x18000caa3  mov     r8, r14
0x18000caa6  lea     rdx, aFailedToCreate_6; "Failed to create the link between %ws a"...
0x18000caad  mov     ecx, 1
0x18000cab2  call    DsRolepLogPrintRoutine
0x18000cab7  mov     ecx, ebx; Status
0x18000cab9  call    cs:__imp_RtlNtStatusToDosError
0x18000cabf  lea     r11, [rsp+0E0h+var_10]
0x18000cac7  mov     rbx, [r11+20h]
0x18000cacb  mov     rsi, [r11+28h]
0x18000cacf  mov     rsp, r11
0x18000cad2  pop     r14
0x18000cad4  pop     rdi
0x18000cad5  pop     rbp
0x18000cad6  retn
```
