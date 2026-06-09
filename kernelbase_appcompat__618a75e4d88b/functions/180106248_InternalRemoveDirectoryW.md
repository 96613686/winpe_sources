# InternalRemoveDirectoryW

- ea: `0x180106248`
- end: `0x1801068e2`
- name: `InternalRemoveDirectoryW`
- size: `1690`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180106210`
- `0x18018b240`
- `0x18018b290`

## callees

- `0x18004b9d0`
- `0x18004c490`
- `0x1800fc530`
- `0x180106248`
- `0x18018d55c`
- `0x180194eb9`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1801062c0`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1801062c0`
- `ntdll!RtlReleaseRelativeName` at `0x1801063b1`
- `ntdll!RtlReleaseRelativeName` at `0x18010643e`
- `ntdll!RtlReleaseRelativeName` at `0x1801064d8`
- `ntdll!RtlReleaseRelativeName` at `0x180106659`
- `ntdll!RtlReleaseRelativeName` at `0x1801066bc`
- `ntdll!RtlReleaseRelativeName` at `0x180106896`
- `ntdll!RtlReleaseRelativeName` at `0x1801063b1`
- `ntdll!RtlReleaseRelativeName` at `0x18010643e`
- `ntdll!RtlReleaseRelativeName` at `0x1801064d8`
- `ntdll!RtlReleaseRelativeName` at `0x180106659`
- `ntdll!RtlReleaseRelativeName` at `0x1801066bc`
- `ntdll!RtlReleaseRelativeName` at `0x180106896`
- `ntdll!NtQueryInformationFile` at `0x18010641a`
- `ntdll!NtQueryInformationFile` at `0x18010641a`
- `ntdll!NtOpenFile` at `0x18010635d`
- `ntdll!NtOpenFile` at `0x180106397`
- `ntdll!NtOpenFile` at `0x1801067c8`
- `ntdll!NtOpenFile` at `0x18010635d`
- `ntdll!NtOpenFile` at `0x180106397`
- `ntdll!NtOpenFile` at `0x1801067c8`
- `ntdll!NtSetInformationFile` at `0x180106845`
- `ntdll!NtSetInformationFile` at `0x180106884`
- `ntdll!NtSetInformationFile` at `0x180106845`
- `ntdll!NtSetInformationFile` at `0x180106884`
- `ntdll!RtlSetLastWin32Error` at `0x1801062d4`
- `ntdll!RtlSetLastWin32Error` at `0x1801062d4`
- `ntdll!RtlInitUnicodeStringEx` at `0x180106643`
- `ntdll!RtlInitUnicodeStringEx` at `0x180106643`
- `ntdll!NtClose` at `0x18010646c`
- `ntdll!NtClose` at `0x180106506`
- `ntdll!NtClose` at `0x18010679f`
- `ntdll!NtClose` at `0x1801068c4`
- `ntdll!NtClose` at `0x18010646c`
- `ntdll!NtClose` at `0x180106506`
- `ntdll!NtClose` at `0x18010679f`
- `ntdll!NtClose` at `0x1801068c4`
- `ntdll!RtlFreeHeap` at `0x1801063cf`
- `ntdll!RtlFreeHeap` at `0x18010645c`
- `ntdll!RtlFreeHeap` at `0x1801064f6`
- `ntdll!RtlFreeHeap` at `0x180106677`
- `ntdll!RtlFreeHeap` at `0x1801066da`
- `ntdll!RtlFreeHeap` at `0x18010674a`
- `ntdll!RtlFreeHeap` at `0x180106768`
- `ntdll!RtlFreeHeap` at `0x1801068b4`
- `ntdll!RtlFreeHeap` at `0x1801063cf`
- `ntdll!RtlFreeHeap` at `0x18010645c`
- `ntdll!RtlFreeHeap` at `0x1801064f6`
- `ntdll!RtlFreeHeap` at `0x180106677`
- `ntdll!RtlFreeHeap` at `0x1801066da`
- `ntdll!RtlFreeHeap` at `0x18010674a`
- `ntdll!RtlFreeHeap` at `0x180106768`
- `ntdll!RtlFreeHeap` at `0x1801068b4`
- `ntdll!RtlAllocateHeap` at `0x1801064c0`
- `ntdll!RtlAllocateHeap` at `0x1801066a4`
- `ntdll!RtlAllocateHeap` at `0x1801064c0`
- `ntdll!RtlAllocateHeap` at `0x1801066a4`

## pseudocode

```c
__int64 __fastcall InternalRemoveDirectoryW(PCWSTR SourceString, char a2)
{
  ULARGE_INTEGER AppCompatFlags; // r12
  ULONG v5; // ecx
  PWSTR Buffer; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v8; // eax
  NTSTATUS inited; // ebx
  NTSTATUS v10; // eax
  NTSTATUS v12; // eax
  __int16 v13; // ax
  char v14; // dl
  unsigned __int16 *Heap; // rsi
  USHORT v16; // dx
  WCHAR *v17; // rcx
  WCHAR *v18; // rax
  WCHAR *v19; // rbx
  unsigned __int64 v20; // rcx
  NTSTATUS v21; // eax
  HANDLE FileHandle; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-61h] BYREF
  __int64 FileInformation; // [rsp+58h] [rbp-51h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+60h] [rbp-49h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+70h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-9h] BYREF
  char v29; // [rsp+118h] [rbp+6Fh] BYREF
  int v30; // [rsp+120h] [rbp+77h] BYREF
  DWORD BytesReturned; // [rsp+128h] [rbp+7Fh] BYREF

  FileHandle = 0;
  v29 = 0;
  memset(&ObjectAttributes, 0, 44);
  v30 = 0;
  NtName = 0;
  IoStatusBlock = 0;
  AppCompatFlags = NtCurrentPeb()->AppCompatFlags;
  memset(&RelativeName, 0, sizeof(RelativeName));
  FileInformation = 0;
  DestinationString = 0;
  if ( !RtlDosPathNameToRelativeNtPathName_U(SourceString, &NtName, 0, &RelativeName) )
  {
    v5 = 3;
LABEL_3:
    RtlSetLastWin32Error(v5);
    return 0;
  }
  Buffer = NtName.Buffer;
  if ( RelativeName.RelativeName.Length )
  {
    NtName = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = &NtName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenFile(&FileHandle, 0x110080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204021u);
  inited = v8;
  if ( v8 >= 0 )
  {
    v12 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
    inited = v12;
    if ( v12 < 0 && v12 != -1073741822 && v12 != -1073741811 )
    {
      RtlReleaseRelativeName(&RelativeName);
LABEL_18:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      NtClose(FileHandle);
      goto LABEL_12;
    }
    if ( v12 < 0 )
      goto LABEL_63;
    v13 = FileInformation;
    v14 = 0;
    if ( (FileInformation & 0x400) == 0 )
      goto LABEL_63;
    if ( HIDWORD(FileInformation) == -1610612733 )
    {
      Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x4000u);
      if ( !Heap )
      {
        RtlReleaseRelativeName(&RelativeName);
LABEL_24:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
        NtClose(FileHandle);
        v5 = 8;
        goto LABEL_3;
      }
      if ( DeviceIoControl(FileHandle, 0x900A8u, 0, 0, Heap, 0x4000u, &BytesReturned, 0) )
      {
        v16 = Heap[5];
        DestinationString.MaximumLength = v16;
        DestinationString.Length = v16;
        v17 = (unsigned __int16 *)((char *)Heap + Heap[4] + 16);
        DestinationString.Buffer = v17;
        if ( (v16 == 96 || v16 == 98 && v17[48] == 92)
          && *v17 == 92
          && (v17[1] == 63 || v17[1] == 92)
          && v17[2] == 63
          && v17[3] == 92
          && v17[4] == 86
          && v17[5] == 111
          && v17[6] == 108
          && v17[7] == 117
          && v17[8] == 109
          && v17[9] == 101
          && v17[10] == 123
          && v17[19] == 45
          && v17[24] == 45
          && v17[29] == 45
          && v17[34] == 45
          && v17[47] == 125 )
        {
          inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
          if ( inited < 0 )
          {
            RtlReleaseRelativeName(&RelativeName);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            goto LABEL_18;
          }
          v18 = (WCHAR *)RtlAllocateHeap(
                           NtCurrentPeb()->ProcessHeap,
                           KernelBaseGlobalData,
                           DestinationString.Length + 4LL);
          v19 = v18;
          if ( !v18 )
          {
            RtlReleaseRelativeName(&RelativeName);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            goto LABEL_24;
          }
          memcpy_0(v18, DestinationString.Buffer, DestinationString.Length);
          v19[(unsigned __int64)DestinationString.Length >> 1] = 0;
          v20 = (unsigned __int64)DestinationString.Length >> 1;
          if ( DestinationString.Buffer[v20 - 1] != 92 )
          {
            v19[v20] = 92;
            v19[((unsigned __int64)DestinationString.Length >> 1) + 1] = 0;
          }
          DeleteVolumeMountPointW(v19);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v13 = FileInformation;
    }
    else if ( HIDWORD(FileInformation) != -1610612724 && HIDWORD(FileInformation) != -1610612711 )
    {
      goto LABEL_57;
    }
    v14 = 1;
LABEL_57:
    if ( (v13 & 0x400) == 0 )
      goto LABEL_63;
    if ( v14 )
      goto LABEL_63;
    NtClose(FileHandle);
    v21 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
    inited = v21;
    if ( v21 >= 0 )
      goto LABEL_63;
    if ( ((v21 + 1073741194) & 0xFFFFFFFC) != 0 || v21 == -1073741193 )
      goto LABEL_11;
    v10 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204021u);
    goto LABEL_10;
  }
  if ( v8 != -1073741811 )
  {
LABEL_11:
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
LABEL_12:
    BaseSetLastNTError((unsigned int)inited);
    return 0;
  }
  v10 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
LABEL_10:
  inited = v10;
  if ( v10 < 0 )
    goto LABEL_11;
LABEL_63:
  if ( (a2 & 1) == 0 || (inited = BasepGetDirectoryRedirectionStatus(NtName.Buffer, FileHandle), inited >= 0) )
  {
    if ( (AppCompatFlags.QuadPart & 0x100000000LL) != 0
      || (v30 = 3,
          inited = NtSetInformationFile(FileHandle, &IoStatusBlock, &v30, 4u, (FILE_INFORMATION_CLASS)64),
          (int)(inited + 0x80000000) >= 0)
      && inited != -1073741535 )
    {
      v29 = 1;
      inited = NtSetInformationFile(FileHandle, &IoStatusBlock, &v29, 1u, FileDispositionInformation);
    }
  }
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  NtClose(FileHandle);
  if ( inited < 0 )
    goto LABEL_12;
  return 1;
}

```

## disassembly

```asm
0x180106248  mov     [rsp-8+arg_0], rbx
0x18010624d  push    rbp
0x18010624e  push    rsi
0x18010624f  push    rdi
0x180106250  push    r12
0x180106252  push    r13
0x180106254  push    r14
0x180106256  push    r15
0x180106258  lea     rbp, [rsp-27h]
0x18010625d  sub     rsp, 0D0h
0x180106264  xorps   xmm0, xmm0
0x180106267  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x18010626b  xor     r13d, r13d
0x18010626e  xorps   xmm1, xmm1
0x180106271  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180106275  mov     [rbp+57h+FileHandle], r13
0x180106279  xor     eax, eax
0x18010627b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18010627f  mov     [rbp+57h+arg_8], r13b
0x180106283  mov     r15d, edx
0x180106286  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18010628a  mov     [rbp+57h+arg_10], r13d
0x18010628e  xor     r8d, r8d; PartName
0x180106291  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x180106295  lea     rdx, [rbp+57h+NtName]; NtName
0x180106299  mov     r14, rcx
0x18010629c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1801062a0  mov     rax, gs:60h
0x1801062a9  mov     r12, [rax+2C8h]
0x1801062b0  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1801062b4  mov     [rbp+57h+FileInformation], r13
0x1801062b8  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1801062bc  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1801062c0  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1801062c7  nop     dword ptr [rax+rax+00h]
0x1801062cc  test    al, al
0x1801062ce  jnz     short loc_1801062E5
0x1801062d0  lea     ecx, [r13+3]; LastError
0x1801062d4  call    cs:__imp_RtlSetLastWin32Error
0x1801062db  nop     dword ptr [rax+rax+00h]
0x1801062e0  jmp     loc_1801063E2
0x1801062e5  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1801062e9  mov     rdi, [rbp+57h+NtName.Buffer]
0x1801062ed  test    ax, ax
0x1801062f0  jz      short loc_180106312
0x1801062f2  mov     [rbp+57h+NtName.Length], ax
0x1801062f6  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1801062f9  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1801062fc  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x180106300  mov     word ptr [rbp+57h+NtName+6], ax
0x180106304  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x180106308  mov     [rbp+57h+NtName.Buffer], rax
0x18010630c  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x180106310  jmp     short loc_180106319
0x180106312  mov     rax, r13
0x180106315  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x180106319  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18010631d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180106321  lea     rax, [rbp+57h+NtName]
0x180106325  mov     [rsp+100h+OpenOptions], 204021h; OpenOptions
0x18010632d  xorps   xmm0, xmm0
0x180106330  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180106334  mov     esi, 7
0x180106339  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180106340  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180106344  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18010634b  mov     edx, 110080h; DesiredAccess
0x180106350  mov     [rsp+100h+ShareAccess], esi; ShareAccess
0x180106354  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180106358  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18010635d  call    cs:__imp_NtOpenFile
0x180106364  nop     dword ptr [rax+rax+00h]
0x180106369  mov     ebx, eax
0x18010636b  test    eax, eax
0x18010636d  jns     loc_180106400
0x180106373  cmp     eax, 0C000000Dh
0x180106378  jnz     short loc_1801063AD
0x18010637a  mov     [rsp+100h+OpenOptions], 4021h; OpenOptions
0x180106382  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180106386  mov     [rsp+100h+ShareAccess], esi; ShareAccess
0x18010638a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18010638e  mov     edx, 110000h; DesiredAccess
0x180106393  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180106397  call    cs:__imp_NtOpenFile
0x18010639e  nop     dword ptr [rax+rax+00h]
0x1801063a3  mov     ebx, eax
0x1801063a5  test    eax, eax
0x1801063a7  jns     loc_180106804
0x1801063ad  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1801063b1  call    cs:__imp_RtlReleaseRelativeName
0x1801063b8  nop     dword ptr [rax+rax+00h]
0x1801063bd  mov     rcx, gs:60h
0x1801063c6  mov     r8, rdi; P
0x1801063c9  xor     edx, edx; Flags
0x1801063cb  mov     rcx, [rcx+30h]; HeapHandle
0x1801063cf  call    cs:__imp_RtlFreeHeap
0x1801063d6  nop     dword ptr [rax+rax+00h]
0x1801063db  mov     ecx, ebx
0x1801063dd  call    BaseSetLastNTError
0x1801063e2  xor     eax, eax
0x1801063e4  mov     rbx, [rsp+100h+arg_0]
0x1801063ec  add     rsp, 0D0h
0x1801063f3  pop     r15
0x1801063f5  pop     r14
0x1801063f7  pop     r13
0x1801063f9  pop     r12
0x1801063fb  pop     rdi
0x1801063fc  pop     rsi
0x1801063fd  pop     rbp
0x1801063fe  retn
0x180106400  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180106404  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180106408  mov     r9d, 8; Length
0x18010640e  mov     [rsp+100h+ShareAccess], 23h ; '#'; FileInformationClass
0x180106416  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18010641a  call    cs:__imp_NtQueryInformationFile
0x180106421  nop     dword ptr [rax+rax+00h]
0x180106426  mov     ebx, eax
0x180106428  test    eax, eax
0x18010642a  jns     short loc_18010647D
0x18010642c  cmp     eax, 0C0000002h
0x180106431  jz      short loc_18010647D
0x180106433  cmp     eax, 0C000000Dh
0x180106438  jz      short loc_18010647D
0x18010643a  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18010643e  call    cs:__imp_RtlReleaseRelativeName
0x180106445  nop     dword ptr [rax+rax+00h]
0x18010644a  mov     rcx, gs:60h
0x180106453  mov     r8, rdi; P
0x180106456  xor     edx, edx; Flags
0x180106458  mov     rcx, [rcx+30h]; HeapHandle
0x18010645c  call    cs:__imp_RtlFreeHeap
0x180106463  nop     dword ptr [rax+rax+00h]
0x180106468  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18010646c  call    cs:__imp_NtClose
0x180106473  nop     dword ptr [rax+rax+00h]
0x180106478  jmp     loc_1801063DB
0x18010647d  test    ebx, ebx
0x18010647f  js      loc_180106804
0x180106485  mov     rax, [rbp+57h+FileInformation]
0x180106489  mov     dl, r13b
0x18010648c  bt      eax, 0Ah
0x180106490  jnb     loc_180106804
0x180106496  mov     ecx, dword ptr [rbp+57h+FileInformation+4]
0x180106499  cmp     ecx, 0A0000003h
0x18010649f  jnz     loc_18010677F
0x1801064a5  mov     rcx, gs:60h
0x1801064ae  mov     ebx, 4000h
0x1801064b3  mov     edx, cs:KernelBaseGlobalData; Flags
0x1801064b9  mov     r8d, ebx; Size
0x1801064bc  mov     rcx, [rcx+30h]; HeapHandle
0x1801064c0  call    cs:__imp_RtlAllocateHeap
0x1801064c7  nop     dword ptr [rax+rax+00h]
0x1801064cc  mov     rsi, rax
0x1801064cf  test    rax, rax
0x1801064d2  jnz     short loc_18010651C
0x1801064d4  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1801064d8  call    cs:__imp_RtlReleaseRelativeName
0x1801064df  nop     dword ptr [rax+rax+00h]
0x1801064e4  mov     rcx, gs:60h
0x1801064ed  mov     r8, rdi; P
0x1801064f0  xor     edx, edx; Flags
0x1801064f2  mov     rcx, [rcx+30h]; HeapHandle
0x1801064f6  call    cs:__imp_RtlFreeHeap
0x1801064fd  nop     dword ptr [rax+rax+00h]
0x180106502  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180106506  call    cs:__imp_NtClose
0x18010650d  nop     dword ptr [rax+rax+00h]
0x180106512  mov     ecx, 8
0x180106517  jmp     loc_1801062D4
0x18010651c  mov     rcx, [rbp+57h+FileHandle]; hDevice
0x180106520  lea     rax, [rbp+57h+BytesReturned]
0x180106524  mov     [rsp+100h+lpOverlapped], r13; lpOverlapped
0x180106529  xor     r9d, r9d; nInBufferSize
0x18010652c  mov     [rsp+100h+lpBytesReturned], rax; lpBytesReturned
0x180106531  xor     r8d, r8d; lpInBuffer
0x180106534  mov     [rsp+100h+OpenOptions], ebx; nOutBufferSize
0x180106538  mov     edx, 900A8h; dwIoControlCode
0x18010653d  mov     qword ptr [rsp+100h+ShareAccess], rsi; lpOutBuffer
0x180106542  call    DeviceIoControl
0x180106547  test    eax, eax
0x180106549  jz      loc_180106756
0x18010654f  movzx   edx, word ptr [rsi+0Ah]
0x180106553  mov     eax, 5Ch ; '\'
0x180106558  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x18010655c  mov     [rbp+57h+DestinationString.Length], dx
0x180106560  movzx   ecx, word ptr [rsi+8]
0x180106564  add     rcx, 10h
0x180106568  add     rcx, rsi
0x18010656b  mov     [rbp+57h+DestinationString.Buffer], rcx
0x18010656f  cmp     dx, 60h ; '`'
0x180106573  jz      short loc_180106589
0x180106575  cmp     dx, 62h ; 'b'
0x180106579  jnz     loc_180106756
0x18010657f  cmp     [rcx+60h], ax
0x180106583  jnz     loc_180106756
0x180106589  cmp     [rcx], ax
0x18010658c  jnz     loc_180106756
0x180106592  cmp     word ptr [rcx+2], 3Fh ; '?'
0x180106597  jz      short loc_1801065A3
0x180106599  cmp     [rcx+2], ax
0x18010659d  jnz     loc_180106756
0x1801065a3  cmp     word ptr [rcx+4], 3Fh ; '?'
0x1801065a8  jnz     loc_180106756
0x1801065ae  cmp     [rcx+6], ax
0x1801065b2  jnz     loc_180106756
0x1801065b8  cmp     word ptr [rcx+8], 56h ; 'V'
0x1801065bd  jnz     loc_180106756
0x1801065c3  cmp     word ptr [rcx+0Ah], 6Fh ; 'o'
0x1801065c8  jnz     loc_180106756
0x1801065ce  cmp     word ptr [rcx+0Ch], 6Ch ; 'l'
0x1801065d3  jnz     loc_180106756
0x1801065d9  cmp     word ptr [rcx+0Eh], 75h ; 'u'
0x1801065de  jnz     loc_180106756
0x1801065e4  cmp     word ptr [rcx+10h], 6Dh ; 'm'
0x1801065e9  jnz     loc_180106756
0x1801065ef  cmp     word ptr [rcx+12h], 65h ; 'e'
0x1801065f4  jnz     loc_180106756
0x1801065fa  cmp     word ptr [rcx+14h], 7Bh ; '{'
0x1801065ff  jnz     loc_180106756
0x180106605  mov     ax, 2Dh ; '-'
0x180106609  cmp     [rcx+26h], ax
0x18010660d  jnz     loc_180106756
0x180106613  cmp     [rcx+30h], ax
0x180106617  jnz     loc_180106756
0x18010661d  cmp     [rcx+3Ah], ax
0x180106621  jnz     loc_180106756
0x180106627  cmp     [rcx+44h], ax
0x18010662b  jnz     loc_180106756
0x180106631  cmp     word ptr [rcx+5Eh], 7Dh ; '}'
0x180106636  jnz     loc_180106756
0x18010663c  mov     rdx, r14; SourceString
0x18010663f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180106643  call    cs:__imp_RtlInitUnicodeStringEx
0x18010664a  nop     dword ptr [rax+rax+00h]
0x18010664f  mov     ebx, eax
0x180106651  test    eax, eax
0x180106653  jns     short loc_180106688
0x180106655  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x180106659  call    cs:__imp_RtlReleaseRelativeName
0x180106660  nop     dword ptr [rax+rax+00h]
0x180106665  mov     rcx, gs:60h
0x18010666e  mov     r8, rsi; P
0x180106671  xor     edx, edx; Flags
0x180106673  mov     rcx, [rcx+30h]; HeapHandle
0x180106677  call    cs:__imp_RtlFreeHeap
0x18010667e  nop     dword ptr [rax+rax+00h]
0x180106683  jmp     loc_18010644A
0x180106688  mov     rcx, gs:60h
0x180106691  movzx   r8d, [rbp+57h+DestinationString.Length]
0x180106696  mov     edx, cs:KernelBaseGlobalData; Flags
0x18010669c  add     r8, 4; Size
0x1801066a0  mov     rcx, [rcx+30h]; HeapHandle
0x1801066a4  call    cs:__imp_RtlAllocateHeap
0x1801066ab  nop     dword ptr [rax+rax+00h]
0x1801066b0  mov     rbx, rax
0x1801066b3  test    rax, rax
0x1801066b6  jnz     short loc_1801066EB
0x1801066b8  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1801066bc  call    cs:__imp_RtlReleaseRelativeName
0x1801066c3  nop     dword ptr [rax+rax+00h]
0x1801066c8  mov     rcx, gs:60h
0x1801066d1  mov     r8, rsi; P
0x1801066d4  xor     edx, edx; Flags
0x1801066d6  mov     rcx, [rcx+30h]; HeapHandle
0x1801066da  call    cs:__imp_RtlFreeHeap
0x1801066e1  nop     dword ptr [rax+rax+00h]
0x1801066e6  jmp     loc_1801064E4
0x1801066eb  movzx   r8d, [rbp+57h+DestinationString.Length]; Size
0x1801066f0  mov     rcx, rbx; void *
0x1801066f3  mov     rdx, [rbp+57h+DestinationString.Buffer]; Src
0x1801066f7  call    memcpy_0
0x1801066fc  movzx   ecx, [rbp+57h+DestinationString.Length]
0x180106700  mov     edx, 5Ch ; '\'
0x180106705  shr     rcx, 1
0x180106708  mov     [rbx+rcx*2], r13w
0x18010670d  movzx   ecx, [rbp+57h+DestinationString.Length]
0x180106711  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180106715  shr     rcx, 1
0x180106718  cmp     [rax+rcx*2-2], dx
0x18010671d  jz      short loc_180106730
0x18010671f  mov     [rbx+rcx*2], dx
0x180106723  movzx   ecx, [rbp+57h+DestinationString.Length]
0x180106727  shr     rcx, 1
0x18010672a  mov     [rbx+rcx*2+2], r13w
0x180106730  mov     rcx, rbx; lpszVolumeMountPoint
0x180106733  call    DeleteVolumeMountPointW
0x180106738  mov     rcx, gs:60h
0x180106741  mov     r8, rbx; P
0x180106744  xor     edx, edx; Flags
0x180106746  mov     rcx, [rcx+30h]; HeapHandle
0x18010674a  call    cs:__imp_RtlFreeHeap
0x180106751  nop     dword ptr [rax+rax+00h]
0x180106756  mov     rcx, gs:60h
0x18010675f  mov     r8, rsi; P
0x180106762  xor     edx, edx; Flags
0x180106764  mov     rcx, [rcx+30h]; HeapHandle
0x180106768  call    cs:__imp_RtlFreeHeap
0x18010676f  nop     dword ptr [rax+rax+00h]
0x180106774  mov     rax, [rbp+57h+FileInformation]
  ... truncated ...
```
