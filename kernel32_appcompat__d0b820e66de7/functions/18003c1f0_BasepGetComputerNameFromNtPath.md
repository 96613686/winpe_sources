# BasepGetComputerNameFromNtPath

- ea: `0x18003c1f0`
- end: `0x18003c723`
- name: `BasepGetComputerNameFromNtPath`
- size: `1331`
- prototype: `__int64 __fastcall(STRING *String2, HANDLE FileHandle, void *, LPDWORD nSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003c1f0`
- `0x18003c870`
- `0x180082751`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18003c3dd`
- `ntdll!NtFsControlFile` at `0x18003c3dd`
- `ntdll!NtClose` at `0x18003c3f0`
- `ntdll!NtClose` at `0x18003c647`
- `ntdll!NtClose` at `0x18003c3f0`
- `ntdll!NtClose` at `0x18003c647`
- `ntdll!wcslen` at `0x18003c41a`
- `ntdll!wcslen` at `0x18003c41a`
- `ntdll!NtQueryInformationFile` at `0x18003c5fb`
- `ntdll!NtQueryInformationFile` at `0x18003c5fb`
- `ntdll!RtlNtStatusToDosError` at `0x18003c62f`
- `ntdll!RtlNtStatusToDosError` at `0x18003c62f`
- `ntdll!RtlPrefixString` at `0x18003c28b`
- `ntdll!RtlPrefixString` at `0x18003c4d5`
- `ntdll!RtlPrefixString` at `0x18003c28b`
- `ntdll!RtlPrefixString` at `0x18003c4d5`
- `ntdll!wcschr` at `0x18003c6b0`
- `ntdll!wcschr` at `0x18003c6b0`
- `ntdll!wcsstr` at `0x18003c536`
- `ntdll!wcsstr` at `0x18003c55a`
- `ntdll!wcsstr` at `0x18003c57e`
- `ntdll!wcsstr` at `0x18003c5a2`
- `ntdll!wcsstr` at `0x18003c5c6`
- `ntdll!wcsstr` at `0x18003c536`
- `ntdll!wcsstr` at `0x18003c55a`
- `ntdll!wcsstr` at `0x18003c57e`
- `ntdll!wcsstr` at `0x18003c5a2`
- `ntdll!wcsstr` at `0x18003c5c6`
- `ntdll!NtCreateFile` at `0x18003c381`
- `ntdll!NtCreateFile` at `0x18003c381`
- `ntdll!RtlInitUnicodeString` at `0x18003c274`
- `ntdll!RtlInitUnicodeString` at `0x18003c303`
- `ntdll!RtlInitUnicodeString` at `0x18003c274`
- `ntdll!RtlInitUnicodeString` at `0x18003c303`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18003c517`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18003c517`

## pseudocode

```c
__int64 __fastcall BasepGetComputerNameFromNtPath(STRING *String2, HANDLE FileHandle, WCHAR *a3, LPDWORD nSize)
{
  unsigned int v6; // ebx
  PCHAR Buffer; // rax
  unsigned int v10; // edi
  WCHAR *v11; // rdx
  WCHAR *v12; // rsi
  NTSTATUS v13; // eax
  NTSTATUS v14; // esi
  unsigned int v15; // edi
  WCHAR *i; // rcx
  USHORT v17; // cx
  unsigned int v18; // esi
  __int64 v19; // rsi
  PCHAR v21; // rcx
  WCHAR v22; // cx
  NTSTATUS v23; // ecx
  wchar_t *v24; // rax
  void *FileHandlea; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  STRING String1; // [rsp+78h] [rbp-88h] BYREF
  STRING v28; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v31; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR DeviceName[4]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR TargetPath[28]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t Str[236]; // [rsp+128h] [rbp+28h] BYREF
  wchar_t OutputBuffer[2]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE Src[524]; // [rsp+304h] [rbp+204h] BYREF
  unsigned int FileInformation; // [rsp+510h] [rbp+410h] BYREF
  char v38; // [rsp+516h] [rbp+416h] BYREF

  *(_QWORD *)&String1.Length = 1179664;
  *(_QWORD *)&v28.Length = 655368;
  v6 = 161;
  IoStatusBlock = 0;
  wcscpy(DeviceName, L"A:");
  String1.Buffer = (PCHAR)L"\\??\\UNC\\";
  v28.Buffer = (PCHAR)L"\\??\\";
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( RtlPrefixString(&String1, String2, 1u) )
  {
    if ( String2->Length <= String1.Length )
      return v6;
    Buffer = String2->Buffer;
    v10 = String2->Length - String1.Length;
    v11 = (WCHAR *)&Buffer[2 * ((unsigned __int64)String1.Length >> 1)];
LABEL_4:
    DestinationString.Buffer = v11;
    goto LABEL_5;
  }
  if ( !RtlPrefixString(&v28, String2, 1u) )
    return v6;
  v21 = String2->Buffer;
  if ( *((_WORD *)v21 + 5) != 58 )
    return v6;
  v22 = *((_WORD *)v21 + 4);
  DeviceName[0] = v22;
  if ( (unsigned __int16)(v22 - 97) <= 0x19u )
    DeviceName[0] = v22 - 32;
  if ( !QueryDosDeviceW(DeviceName, TargetPath, 0x105u) )
    return NtCurrentTeb()->LastErrorValue;
  if ( TargetPath != wcsstr(TargetPath, L"\\Device\\LanmanRedirector\\;")
    || DeviceName[0] != TargetPath[26]
    || TargetPath[27] != 58 )
  {
    if ( TargetPath != wcsstr(TargetPath, L"\\Device\\Harddisk")
      && TargetPath != wcsstr(TargetPath, L"\\Device\\CdRom")
      && TargetPath != wcsstr(TargetPath, L"\\Device\\Floppy") )
    {
      if ( TargetPath != wcsstr(TargetPath, L"\\Device\\WinDfs\\") )
        return v6;
      v13 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x218u, FileNameInformation);
      if ( v13 < 0 )
        goto LABEL_45;
      v10 = FileInformation;
      v11 = (WCHAR *)&v38;
      goto LABEL_4;
    }
    if ( GetComputerNameW(a3, nSize) )
      return 0;
    return NtCurrentTeb()->LastErrorValue;
  }
  v10 = 0;
  v24 = wcschr(Str, 0x5Cu);
  DestinationString.Buffer = v24;
  v11 = v24;
  if ( v24 )
  {
    v11 = v24 + 1;
    DestinationString.Buffer = v24 + 1;
    v10 = 2 * (261 - (v24 + 1 - TargetPath));
    goto LABEL_14;
  }
LABEL_5:
  if ( FileHandle != (HANDLE)-1LL )
  {
    FileHandlea = (void *)-1LL;
    v12 = v11 - 1;
    v31 = 0;
    memset(&ObjectAttributes, 0, 44);
    RtlInitUnicodeString(&v31, L"\\Dfs");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &v31;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v13 = NtCreateFile(&FileHandlea, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 3u, 0xA0u, 0, 0);
    if ( v13 >= 0 )
    {
      if ( *v12 != 92 )
      {
        NtClose(FileHandlea);
        return v6;
      }
      v14 = NtFsControlFile(FileHandlea, 0, 0, 0, &IoStatusBlock, 0x600C0u, v12, v10 + 2, OutputBuffer, 0x20Au);
      NtClose(FileHandlea);
      if ( v14 >= 0 )
      {
        if ( OutputBuffer[0] )
        {
          v15 = 2 * wcslen(OutputBuffer);
          if ( v15 < 6 || OutputBuffer[0] != 92 || OutputBuffer[1] != 92 )
            return v6;
          v11 = (WCHAR *)Src;
          v10 = v15 - 4;
          DestinationString.Buffer = (PWSTR)Src;
          goto LABEL_14;
        }
        goto LABEL_46;
      }
      if ( v14 == -1073741772 )
      {
LABEL_46:
        v11 = DestinationString.Buffer;
        goto LABEL_14;
      }
      v23 = v14;
      return RtlNtStatusToDosError(v23);
    }
LABEL_45:
    v23 = v13;
    return RtlNtStatusToDosError(v23);
  }
LABEL_14:
  for ( i = v11; (int)i - (int)v11 < v10 && *i != 92; ++i )
  {
    if ( *i == 46 )
      return v6;
  }
  v17 = (_WORD)i - (_WORD)v11;
  v18 = v17;
  DestinationString.MaximumLength = v17;
  DestinationString.Length = v17;
  if ( v17 < v10 && v17 <= 0x1Eu )
  {
    if ( (unsigned __int64)v17 + 2 > 2 * (unsigned __int64)*nSize )
      return 111;
    memcpy_0(a3, v11, v17);
    v19 = v18 >> 1;
    *nSize = v19;
    a3[v19] = 0;
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x18003c1f0  push    rbp
0x18003c1f2  push    rbx
0x18003c1f3  push    rsi
0x18003c1f4  push    rdi
0x18003c1f5  push    r13
0x18003c1f7  push    r14
0x18003c1f9  push    r15
0x18003c1fb  lea     rbp, [rsp-640h]
0x18003c203  sub     rsp, 740h
0x18003c20a  mov     rax, cs:__security_cookie
0x18003c211  xor     rax, rsp
0x18003c214  mov     [rbp+670h+var_40], rax
0x18003c21b  xorps   xmm0, xmm0
0x18003c21e  mov     [rbp+670h+var_686], 3Ah ; ':'
0x18003c225  mov     rsi, rdx
0x18003c228  mov     qword ptr [rsp+770h+String1.Length], 120010h
0x18003c231  mov     rdi, rcx
0x18003c234  mov     qword ptr [rbp+670h+var_6E8.Length], 0A0008h
0x18003c23c  mov     ebx, 0A1h
0x18003c241  lea     rcx, [rsp+770h+DestinationString]; DestinationString
0x18003c246  xor     edx, edx; SourceString
0x18003c248  mov     r14, r9
0x18003c24b  mov     r15, r8
0x18003c24e  movups  xmmword ptr [rbp+670h+IoStatusBlock], xmm0
0x18003c252  lea     eax, [rbx-60h]
0x18003c255  mov     [rbp+670h+DeviceName], ax
0x18003c259  lea     rax, aUnc; "\\??\\UNC\\"
0x18003c260  mov     [rbp+670h+String1.Buffer], rax
0x18003c264  lea     rax, asc_180090038; "\\??\\"
0x18003c26b  mov     [rbp+670h+var_6E8.Buffer], rax
0x18003c26f  movups  xmmword ptr [rsp+770h+DestinationString.Length], xmm0
0x18003c274  call    cs:__imp_RtlInitUnicodeString
0x18003c27b  nop     dword ptr [rax+rax+00h]
0x18003c280  mov     r8b, 1; CaseInsensitive
0x18003c283  lea     rcx, [rsp+770h+String1]; String1
0x18003c288  mov     rdx, rdi; String2
0x18003c28b  call    cs:__imp_RtlPrefixString
0x18003c292  nop     dword ptr [rax+rax+00h]
0x18003c297  lea     r13d, [rbx-45h]
0x18003c29b  test    al, al
0x18003c29d  jz      loc_18003C4CB
0x18003c2a3  movzx   r8d, [rsp+770h+String1.Length]
0x18003c2a9  cmp     [rdi], r8w
0x18003c2ad  jbe     loc_18003C4A7
0x18003c2b3  mov     rax, [rdi+8]
0x18003c2b7  mov     ecx, r8d
0x18003c2ba  movzx   edi, word ptr [rdi]
0x18003c2bd  shr     rcx, 1
0x18003c2c0  sub     edi, r8d
0x18003c2c3  lea     rdx, [rax+rcx*2]
0x18003c2c7  mov     [rsp+770h+DestinationString.Buffer], rdx
0x18003c2cc  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18003c2d0  jz      loc_18003C451
0x18003c2d6  xorps   xmm0, xmm0
0x18003c2d9  mov     [rsp+770h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18003c2e2  lea     rsi, [rdx-2]
0x18003c2e6  xor     eax, eax
0x18003c2e8  movups  xmmword ptr [rbp+670h+ObjectAttributes.ObjectName], xmm0
0x18003c2ec  lea     rdx, aDfs; "\\Dfs"
0x18003c2f3  lea     rcx, [rbp+670h+var_698]; DestinationString
0x18003c2f7  movups  xmmword ptr [rbp+670h+ObjectAttributes+1Ch], xmm0
0x18003c2fb  movups  xmmword ptr [rbp+670h+var_698.Length], xmm0
0x18003c2ff  movups  xmmword ptr [rbp+670h+ObjectAttributes.Length], xmm0
0x18003c303  call    cs:__imp_RtlInitUnicodeString
0x18003c30a  nop     dword ptr [rax+rax+00h]
0x18003c30f  mov     [rsp+770h+EaLength], 0; EaLength
0x18003c317  lea     rax, [rbp+670h+var_698]
0x18003c31b  mov     [rsp+770h+EaBuffer], 0; EaBuffer
0x18003c324  lea     r9, [rbp+670h+IoStatusBlock]; IoStatusBlock
0x18003c328  mov     [rsp+770h+CreateOptions], 0A0h; CreateOptions
0x18003c330  lea     r8, [rbp+670h+ObjectAttributes]; ObjectAttributes
0x18003c334  mov     [rsp+770h+CreateDisposition], 3; CreateDisposition
0x18003c33c  lea     rcx, [rsp+770h+FileHandle]; FileHandle
0x18003c341  mov     [rsp+770h+ShareAccess], 7; ShareAccess
0x18003c349  xorps   xmm0, xmm0
0x18003c34c  mov     [rsp+770h+FileAttributes], 80h; FileAttributes
0x18003c354  mov     edx, 100000h; DesiredAccess
0x18003c359  mov     [rsp+770h+AllocationSize], 0; AllocationSize
0x18003c362  mov     [rbp+670h+ObjectAttributes.Length], 30h ; '0'
0x18003c369  mov     [rbp+670h+ObjectAttributes.RootDirectory], 0
0x18003c371  mov     [rbp+670h+ObjectAttributes.Attributes], 40h ; '@'
0x18003c378  mov     [rbp+670h+ObjectAttributes.ObjectName], rax
0x18003c37c  movdqu  xmmword ptr [rbp+670h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003c381  call    cs:__imp_NtCreateFile
0x18003c388  nop     dword ptr [rax+rax+00h]
0x18003c38d  test    eax, eax
0x18003c38f  js      loc_18003C6F1
0x18003c395  cmp     r13w, [rsi]
0x18003c399  jnz     loc_18003C642
0x18003c39f  mov     dword ptr [rsp+770h+EaBuffer], 20Ah; OutputBufferLength
0x18003c3a7  lea     rcx, [rbp+670h+OutputBuffer]
0x18003c3ae  mov     qword ptr [rsp+770h+CreateOptions], rcx; OutputBuffer
0x18003c3b3  lea     eax, [rdi+2]
0x18003c3b6  mov     rcx, [rsp+770h+FileHandle]; FileHandle
0x18003c3bb  xor     r9d, r9d; ApcContext
0x18003c3be  mov     [rsp+770h+CreateDisposition], eax; InputBufferLength
0x18003c3c2  xor     r8d, r8d; ApcRoutine
0x18003c3c5  mov     qword ptr [rsp+770h+ShareAccess], rsi; InputBuffer
0x18003c3ca  lea     rax, [rbp+670h+IoStatusBlock]
0x18003c3ce  mov     [rsp+770h+FileAttributes], 600C0h; FsControlCode
0x18003c3d6  xor     edx, edx; Event
0x18003c3d8  mov     [rsp+770h+AllocationSize], rax; IoStatusBlock
0x18003c3dd  call    cs:__imp_NtFsControlFile
0x18003c3e4  nop     dword ptr [rax+rax+00h]
0x18003c3e9  mov     rcx, [rsp+770h+FileHandle]; Handle
0x18003c3ee  mov     esi, eax
0x18003c3f0  call    cs:__imp_NtClose
0x18003c3f7  nop     dword ptr [rax+rax+00h]
0x18003c3fc  test    esi, esi
0x18003c3fe  js      loc_18003C621
0x18003c404  xor     eax, eax
0x18003c406  cmp     ax, [rbp+670h+OutputBuffer]
0x18003c40d  jz      loc_18003C6F8
0x18003c413  lea     rcx, [rbp+670h+OutputBuffer]; String
0x18003c41a  call    cs:__imp_wcslen
0x18003c421  nop     dword ptr [rax+rax+00h]
0x18003c426  lea     edi, [rax+rax]
0x18003c429  cmp     edi, 6
0x18003c42c  jb      short loc_18003C4A7
0x18003c42e  cmp     r13w, [rbp+670h+OutputBuffer]
0x18003c436  jnz     short loc_18003C4A7
0x18003c438  cmp     r13w, [rbp+670h+var_46E]
0x18003c440  jnz     short loc_18003C4A7
0x18003c442  lea     rdx, [rbp+670h+Src]; Src
0x18003c449  add     edi, 0FFFFFFFCh
0x18003c44c  mov     [rsp+770h+DestinationString.Buffer], rdx
0x18003c451  mov     rcx, rdx
0x18003c454  mov     eax, ecx
0x18003c456  sub     eax, edx
0x18003c458  cmp     eax, edi
0x18003c45a  jb      loc_18003C702
0x18003c460  sub     cx, dx
0x18003c463  movzx   esi, cx
0x18003c466  mov     [rsp+770h+DestinationString.MaximumLength], si
0x18003c46b  mov     [rsp+770h+DestinationString.Length], si
0x18003c470  cmp     esi, edi
0x18003c472  jnb     short loc_18003C4A7
0x18003c474  cmp     esi, 1Eh
0x18003c477  ja      short loc_18003C4A7
0x18003c479  mov     ecx, [r14]
0x18003c47c  lea     rax, [rsi+2]
0x18003c480  add     rcx, rcx
0x18003c483  mov     r8d, esi; Size
0x18003c486  cmp     rax, rcx
0x18003c489  ja      loc_18003C658
0x18003c48f  mov     rcx, r15; void *
0x18003c492  call    memcpy_0
0x18003c497  shr     esi, 1
0x18003c499  mov     ecx, esi
0x18003c49b  xor     eax, eax
0x18003c49d  mov     [r14], ecx
0x18003c4a0  mov     [r15+rsi*2], ax
0x18003c4a5  xor     ebx, ebx
0x18003c4a7  mov     eax, ebx
0x18003c4a9  mov     rcx, [rbp+670h+var_40]
0x18003c4b0  xor     rcx, rsp; StackCookie
0x18003c4b3  call    __security_check_cookie
0x18003c4b8  add     rsp, 740h
0x18003c4bf  pop     r15
0x18003c4c1  pop     r14
0x18003c4c3  pop     r13
0x18003c4c5  pop     rdi
0x18003c4c6  pop     rsi
0x18003c4c7  pop     rbx
0x18003c4c8  pop     rbp
0x18003c4c9  retn
0x18003c4cb  mov     r8b, 1; CaseInsensitive
0x18003c4ce  lea     rcx, [rbp+670h+var_6E8]; String1
0x18003c4d2  mov     rdx, rdi; String2
0x18003c4d5  call    cs:__imp_RtlPrefixString
0x18003c4dc  nop     dword ptr [rax+rax+00h]
0x18003c4e1  test    al, al
0x18003c4e3  jz      short loc_18003C4A7
0x18003c4e5  mov     rcx, [rdi+8]
0x18003c4e9  mov     edi, 3Ah ; ':'
0x18003c4ee  cmp     [rcx+0Ah], di
0x18003c4f2  jnz     short loc_18003C4A7
0x18003c4f4  movzx   ecx, word ptr [rcx+8]
0x18003c4f8  mov     [rbp+670h+DeviceName], cx
0x18003c4fc  lea     eax, [rcx-61h]
0x18003c4ff  cmp     ax, 19h
0x18003c503  jbe     loc_18003C682
0x18003c509  mov     r8d, 105h; ucchMax
0x18003c50f  lea     rdx, [rbp+670h+TargetPath]; lpTargetPath
0x18003c513  lea     rcx, [rbp+670h+DeviceName]; lpDeviceName
0x18003c517  call    cs:__imp_QueryDosDeviceW
0x18003c51e  nop     dword ptr [rax+rax+00h]
0x18003c523  test    eax, eax
0x18003c525  jz      loc_18003C675
0x18003c52b  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\;"
0x18003c532  lea     rcx, [rbp+670h+TargetPath]; Str
0x18003c536  call    cs:__imp_wcsstr
0x18003c53d  nop     dword ptr [rax+rax+00h]
0x18003c542  lea     rcx, [rbp+670h+TargetPath]
0x18003c546  cmp     rcx, rax
0x18003c549  jz      loc_18003C68F
0x18003c54f  lea     rdx, aDeviceHarddisk; "\\Device\\Harddisk"
0x18003c556  lea     rcx, [rbp+670h+TargetPath]; Str
0x18003c55a  call    cs:__imp_wcsstr
0x18003c561  nop     dword ptr [rax+rax+00h]
0x18003c566  lea     rcx, [rbp+670h+TargetPath]
0x18003c56a  cmp     rcx, rax
0x18003c56d  jz      loc_18003C662
0x18003c573  lea     rdx, aDeviceCdrom; "\\Device\\CdRom"
0x18003c57a  lea     rcx, [rbp+670h+TargetPath]; Str
0x18003c57e  call    cs:__imp_wcsstr
0x18003c585  nop     dword ptr [rax+rax+00h]
0x18003c58a  lea     rcx, [rbp+670h+TargetPath]
0x18003c58e  cmp     rcx, rax
0x18003c591  jz      loc_18003C662
0x18003c597  lea     rdx, aDeviceFloppy; "\\Device\\Floppy"
0x18003c59e  lea     rcx, [rbp+670h+TargetPath]; Str
0x18003c5a2  call    cs:__imp_wcsstr
0x18003c5a9  nop     dword ptr [rax+rax+00h]
0x18003c5ae  lea     rcx, [rbp+670h+TargetPath]
0x18003c5b2  cmp     rcx, rax
0x18003c5b5  jz      loc_18003C662
0x18003c5bb  lea     rdx, aDeviceWindfs; "\\Device\\WinDfs\\"
0x18003c5c2  lea     rcx, [rbp+670h+TargetPath]; Str
0x18003c5c6  call    cs:__imp_wcsstr
0x18003c5cd  nop     dword ptr [rax+rax+00h]
0x18003c5d2  lea     rcx, [rbp+670h+TargetPath]
0x18003c5d6  cmp     rcx, rax
0x18003c5d9  jnz     loc_18003C4A7
0x18003c5df  mov     r9d, 218h; Length
0x18003c5e5  mov     dword ptr [rsp+770h+AllocationSize], 9; FileInformationClass
0x18003c5ed  lea     r8, [rbp+670h+FileInformation]; FileInformation
0x18003c5f4  mov     rcx, rsi; FileHandle
0x18003c5f7  lea     rdx, [rbp+670h+IoStatusBlock]; IoStatusBlock
0x18003c5fb  call    cs:__imp_NtQueryInformationFile
0x18003c602  nop     dword ptr [rax+rax+00h]
0x18003c607  test    eax, eax
0x18003c609  js      loc_18003C6F1
0x18003c60f  mov     edi, [rbp+670h+FileInformation]
0x18003c615  lea     rdx, [rbp+670h+var_25A]
0x18003c61c  jmp     loc_18003C2C7
0x18003c621  cmp     esi, 0C0000034h
0x18003c627  jz      loc_18003C6F8
0x18003c62d  mov     ecx, esi; Status
0x18003c62f  call    cs:__imp_RtlNtStatusToDosError
0x18003c636  nop     dword ptr [rax+rax+00h]
0x18003c63b  mov     ebx, eax
0x18003c63d  jmp     loc_18003C4A7
0x18003c642  mov     rcx, [rsp+770h+FileHandle]; Handle
0x18003c647  call    cs:__imp_NtClose
0x18003c64e  nop     dword ptr [rax+rax+00h]
0x18003c653  jmp     loc_18003C4A7
0x18003c658  mov     ebx, 6Fh ; 'o'
0x18003c65d  jmp     loc_18003C4A7
0x18003c662  mov     rdx, r14; nSize
0x18003c665  mov     rcx, r15; lpBuffer
0x18003c668  call    GetComputerNameW
0x18003c66d  test    eax, eax
0x18003c66f  jnz     loc_18003C4A5
0x18003c675  mov     ebx, gs:68h
0x18003c67d  jmp     loc_18003C4A7
0x18003c682  sub     cx, 20h ; ' '
0x18003c686  mov     [rbp+670h+DeviceName], cx
0x18003c68a  jmp     loc_18003C509
0x18003c68f  movzx   eax, [rbp+670h+var_64C]
0x18003c693  cmp     [rbp+670h+DeviceName], ax
0x18003c697  jnz     loc_18003C54F
0x18003c69d  cmp     di, [rbp+670h+var_64A]
0x18003c6a1  jnz     loc_18003C54F
0x18003c6a7  mov     edx, r13d; Ch
0x18003c6aa  lea     rcx, [rbp+670h+Str]; Str
0x18003c6ae  xor     edi, edi
0x18003c6b0  call    cs:__imp_wcschr
0x18003c6b7  nop     dword ptr [rax+rax+00h]
0x18003c6bc  mov     [rsp+770h+DestinationString.Buffer], rax
0x18003c6c1  mov     rdx, rax
0x18003c6c4  test    rax, rax
0x18003c6c7  jz      loc_18003C2CC
0x18003c6cd  add     rax, 2
0x18003c6d1  lea     rcx, [rbp+670h+TargetPath]
0x18003c6d5  mov     rdx, rax
0x18003c6d8  mov     [rsp+770h+DestinationString.Buffer], rax
0x18003c6dd  sub     rax, rcx
0x18003c6e0  mov     edi, 105h
0x18003c6e5  sar     rax, 1
0x18003c6e8  sub     edi, eax
0x18003c6ea  add     edi, edi
0x18003c6ec  jmp     loc_18003C451
0x18003c6f1  mov     ecx, eax
0x18003c6f3  jmp     loc_18003C62F
0x18003c6f8  mov     rdx, [rsp+770h+DestinationString.Buffer]
0x18003c6fd  jmp     loc_18003C451
0x18003c702  cmp     [rcx], r13w
0x18003c706  jz      loc_18003C460
0x18003c70c  mov     eax, 2Eh ; '.'
0x18003c711  cmp     ax, [rcx]
0x18003c714  jz      loc_18003C4A7
0x18003c71a  add     rcx, 2
0x18003c71e  jmp     loc_18003C454
```
