# BasepGetComputerNameFromNtPath

- ea: `0x180039230`
- end: `0x1800396f6`
- name: `BasepGetComputerNameFromNtPath`
- size: `1222`
- prototype: `__int64 __fastcall(STRING *String2, HANDLE FileHandle, void *, LPDWORD nSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180039230`
- `0x180039820`
- `0x18007a7d1`
- `0x18007a840`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x180039405`
- `ntdll!NtFsControlFile` at `0x180039405`
- `ntdll!NtClose` at `0x180039412`
- `ntdll!NtClose` at `0x180039626`
- `ntdll!NtClose` at `0x180039412`
- `ntdll!NtClose` at `0x180039626`
- `ntdll!wcslen` at `0x180039436`
- `ntdll!wcslen` at `0x180039436`
- `ntdll!NtQueryInformationFile` at `0x1800395e6`
- `ntdll!NtQueryInformationFile` at `0x1800395e6`
- `ntdll!RtlNtStatusToDosError` at `0x180039614`
- `ntdll!RtlNtStatusToDosError` at `0x180039614`
- `ntdll!RtlPrefixString` at `0x1800392c5`
- `ntdll!RtlPrefixString` at `0x1800394ea`
- `ntdll!RtlPrefixString` at `0x1800392c5`
- `ntdll!RtlPrefixString` at `0x1800394ea`
- `ntdll!wcschr` at `0x180039689`
- `ntdll!wcschr` at `0x180039689`
- `ntdll!wcsstr` at `0x18003953f`
- `ntdll!wcsstr` at `0x18003955d`
- `ntdll!wcsstr` at `0x18003957b`
- `ntdll!wcsstr` at `0x180039599`
- `ntdll!wcsstr` at `0x1800395b7`
- `ntdll!wcsstr` at `0x18003953f`
- `ntdll!wcsstr` at `0x18003955d`
- `ntdll!wcsstr` at `0x18003957b`
- `ntdll!wcsstr` at `0x180039599`
- `ntdll!wcsstr` at `0x1800395b7`
- `ntdll!NtCreateFile` at `0x1800393af`
- `ntdll!NtCreateFile` at `0x1800393af`
- `ntdll!RtlInitUnicodeString` at `0x1800392b4`
- `ntdll!RtlInitUnicodeString` at `0x180039337`
- `ntdll!RtlInitUnicodeString` at `0x1800392b4`
- `ntdll!RtlInitUnicodeString` at `0x180039337`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180039526`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x180039526`

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
0x180039230  push    rbp
0x180039232  push    rbx
0x180039233  push    rsi
0x180039234  push    rdi
0x180039235  push    r13
0x180039237  push    r14
0x180039239  push    r15
0x18003923b  lea     rbp, [rsp-640h]
0x180039243  sub     rsp, 740h
0x18003924a  mov     rax, cs:__security_cookie
0x180039251  xor     rax, rsp
0x180039254  mov     [rbp+670h+var_40], rax
0x18003925b  xorps   xmm0, xmm0
0x18003925e  mov     [rbp+670h+var_686], 3Ah ; ':'
0x180039265  mov     rsi, rdx
0x180039268  mov     qword ptr [rsp+770h+String1.Length], 120010h
0x180039271  mov     rdi, rcx
0x180039274  mov     qword ptr [rbp+670h+var_6E8.Length], 0A0008h
0x18003927c  mov     ebx, 0A1h
0x180039281  lea     rcx, [rsp+770h+DestinationString]; DestinationString
0x180039286  xor     edx, edx; SourceString
0x180039288  mov     r14, r9
0x18003928b  mov     r15, r8
0x18003928e  movups  xmmword ptr [rbp+670h+IoStatusBlock], xmm0
0x180039292  lea     eax, [rbx-60h]
0x180039295  mov     [rbp+670h+DeviceName], ax
0x180039299  lea     rax, aUnc; "\\??\\UNC\\"
0x1800392a0  mov     [rbp+670h+String1.Buffer], rax
0x1800392a4  lea     rax, asc_1800881F8; "\\??\\"
0x1800392ab  mov     [rbp+670h+var_6E8.Buffer], rax
0x1800392af  movups  xmmword ptr [rsp+770h+DestinationString.Length], xmm0
0x1800392b4  call    cs:__imp_RtlInitUnicodeString
0x1800392ba  mov     r8b, 1; CaseInsensitive
0x1800392bd  lea     rcx, [rsp+770h+String1]; String1
0x1800392c2  mov     rdx, rdi; String2
0x1800392c5  call    cs:__imp_RtlPrefixString
0x1800392cb  lea     r13d, [rbx-45h]
0x1800392cf  test    al, al
0x1800392d1  jz      loc_1800394E0
0x1800392d7  movzx   r8d, [rsp+770h+String1.Length]
0x1800392dd  cmp     [rdi], r8w
0x1800392e1  jbe     loc_1800394BD
0x1800392e7  mov     rax, [rdi+8]
0x1800392eb  mov     ecx, r8d
0x1800392ee  movzx   edi, word ptr [rdi]
0x1800392f1  shr     rcx, 1
0x1800392f4  sub     edi, r8d
0x1800392f7  lea     rdx, [rax+rcx*2]
0x1800392fb  mov     [rsp+770h+DestinationString.Buffer], rdx
0x180039300  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180039304  jz      loc_180039467
0x18003930a  xorps   xmm0, xmm0
0x18003930d  mov     [rsp+770h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180039316  lea     rsi, [rdx-2]
0x18003931a  xor     eax, eax
0x18003931c  movups  xmmword ptr [rbp+670h+ObjectAttributes.ObjectName], xmm0
0x180039320  lea     rdx, aDfs; "\\Dfs"
0x180039327  lea     rcx, [rbp+670h+var_698]; DestinationString
0x18003932b  movups  xmmword ptr [rbp+670h+ObjectAttributes+1Ch], xmm0
0x18003932f  movups  xmmword ptr [rbp+670h+var_698.Length], xmm0
0x180039333  movups  xmmword ptr [rbp+670h+ObjectAttributes.Length], xmm0
0x180039337  call    cs:__imp_RtlInitUnicodeString
0x18003933d  mov     [rsp+770h+EaLength], 0; EaLength
0x180039345  lea     rax, [rbp+670h+var_698]
0x180039349  mov     [rsp+770h+EaBuffer], 0; EaBuffer
0x180039352  lea     r9, [rbp+670h+IoStatusBlock]; IoStatusBlock
0x180039356  mov     [rsp+770h+CreateOptions], 0A0h; CreateOptions
0x18003935e  lea     r8, [rbp+670h+ObjectAttributes]; ObjectAttributes
0x180039362  mov     [rsp+770h+CreateDisposition], 3; CreateDisposition
0x18003936a  lea     rcx, [rsp+770h+FileHandle]; FileHandle
0x18003936f  mov     [rsp+770h+ShareAccess], 7; ShareAccess
0x180039377  xorps   xmm0, xmm0
0x18003937a  mov     [rsp+770h+FileAttributes], 80h; FileAttributes
0x180039382  mov     edx, 100000h; DesiredAccess
0x180039387  mov     [rsp+770h+AllocationSize], 0; AllocationSize
0x180039390  mov     [rbp+670h+ObjectAttributes.Length], 30h ; '0'
0x180039397  mov     [rbp+670h+ObjectAttributes.RootDirectory], 0
0x18003939f  mov     [rbp+670h+ObjectAttributes.Attributes], 40h ; '@'
0x1800393a6  mov     [rbp+670h+ObjectAttributes.ObjectName], rax
0x1800393aa  movdqu  xmmword ptr [rbp+670h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800393af  call    cs:__imp_NtCreateFile
0x1800393b5  test    eax, eax
0x1800393b7  js      loc_1800396C4
0x1800393bd  cmp     r13w, [rsi]
0x1800393c1  jnz     loc_180039621
0x1800393c7  mov     dword ptr [rsp+770h+EaBuffer], 20Ah; OutputBufferLength
0x1800393cf  lea     rcx, [rbp+670h+OutputBuffer]
0x1800393d6  mov     qword ptr [rsp+770h+CreateOptions], rcx; OutputBuffer
0x1800393db  lea     eax, [rdi+2]
0x1800393de  mov     rcx, [rsp+770h+FileHandle]; FileHandle
0x1800393e3  xor     r9d, r9d; ApcContext
0x1800393e6  mov     [rsp+770h+CreateDisposition], eax; InputBufferLength
0x1800393ea  xor     r8d, r8d; ApcRoutine
0x1800393ed  mov     qword ptr [rsp+770h+ShareAccess], rsi; InputBuffer
0x1800393f2  lea     rax, [rbp+670h+IoStatusBlock]
0x1800393f6  mov     [rsp+770h+FileAttributes], 600C0h; FsControlCode
0x1800393fe  xor     edx, edx; Event
0x180039400  mov     [rsp+770h+AllocationSize], rax; IoStatusBlock
0x180039405  call    cs:__imp_NtFsControlFile
0x18003940b  mov     rcx, [rsp+770h+FileHandle]; Handle
0x180039410  mov     esi, eax
0x180039412  call    cs:__imp_NtClose
0x180039418  test    esi, esi
0x18003941a  js      loc_180039606
0x180039420  xor     eax, eax
0x180039422  cmp     ax, [rbp+670h+OutputBuffer]
0x180039429  jz      loc_1800396CB
0x18003942f  lea     rcx, [rbp+670h+OutputBuffer]; String
0x180039436  call    cs:__imp_wcslen
0x18003943c  lea     edi, [rax+rax]
0x18003943f  cmp     edi, 6
0x180039442  jb      short loc_1800394BD
0x180039444  cmp     r13w, [rbp+670h+OutputBuffer]
0x18003944c  jnz     short loc_1800394BD
0x18003944e  cmp     r13w, [rbp+670h+var_46E]
0x180039456  jnz     short loc_1800394BD
0x180039458  lea     rdx, [rbp+670h+Src]; Src
0x18003945f  add     edi, 0FFFFFFFCh
0x180039462  mov     [rsp+770h+DestinationString.Buffer], rdx
0x180039467  mov     rcx, rdx
0x18003946a  mov     eax, ecx
0x18003946c  sub     eax, edx
0x18003946e  cmp     eax, edi
0x180039470  jb      loc_1800396D5
0x180039476  sub     cx, dx
0x180039479  movzx   esi, cx
0x18003947c  mov     [rsp+770h+DestinationString.MaximumLength], si
0x180039481  mov     [rsp+770h+DestinationString.Length], si
0x180039486  cmp     esi, edi
0x180039488  jnb     short loc_1800394BD
0x18003948a  cmp     esi, 1Eh
0x18003948d  ja      short loc_1800394BD
0x18003948f  mov     ecx, [r14]
0x180039492  lea     rax, [rsi+2]
0x180039496  add     rcx, rcx
0x180039499  mov     r8d, esi; Size
0x18003949c  cmp     rax, rcx
0x18003949f  ja      loc_180039631
0x1800394a5  mov     rcx, r15; void *
0x1800394a8  call    memcpy_0
0x1800394ad  shr     esi, 1
0x1800394af  mov     ecx, esi
0x1800394b1  xor     eax, eax
0x1800394b3  mov     [r14], ecx
0x1800394b6  mov     [r15+rsi*2], ax
0x1800394bb  xor     ebx, ebx
0x1800394bd  mov     eax, ebx
0x1800394bf  mov     rcx, [rbp+670h+var_40]
0x1800394c6  xor     rcx, rsp; StackCookie
0x1800394c9  call    __security_check_cookie
0x1800394ce  add     rsp, 740h
0x1800394d5  pop     r15
0x1800394d7  pop     r14
0x1800394d9  pop     r13
0x1800394db  pop     rdi
0x1800394dc  pop     rsi
0x1800394dd  pop     rbx
0x1800394de  pop     rbp
0x1800394df  retn
0x1800394e0  mov     r8b, 1; CaseInsensitive
0x1800394e3  lea     rcx, [rbp+670h+var_6E8]; String1
0x1800394e7  mov     rdx, rdi; String2
0x1800394ea  call    cs:__imp_RtlPrefixString
0x1800394f0  test    al, al
0x1800394f2  jz      short loc_1800394BD
0x1800394f4  mov     rcx, [rdi+8]
0x1800394f8  mov     edi, 3Ah ; ':'
0x1800394fd  cmp     [rcx+0Ah], di
0x180039501  jnz     short loc_1800394BD
0x180039503  movzx   ecx, word ptr [rcx+8]
0x180039507  mov     [rbp+670h+DeviceName], cx
0x18003950b  lea     eax, [rcx-61h]
0x18003950e  cmp     ax, 19h
0x180039512  jbe     loc_18003965B
0x180039518  mov     r8d, 105h; ucchMax
0x18003951e  lea     rdx, [rbp+670h+TargetPath]; lpTargetPath
0x180039522  lea     rcx, [rbp+670h+DeviceName]; lpDeviceName
0x180039526  call    cs:__imp_QueryDosDeviceW
0x18003952c  test    eax, eax
0x18003952e  jz      loc_18003964E
0x180039534  lea     rdx, aDeviceLanmanre; "\\Device\\LanmanRedirector\\;"
0x18003953b  lea     rcx, [rbp+670h+TargetPath]; Str
0x18003953f  call    cs:__imp_wcsstr
0x180039545  lea     rcx, [rbp+670h+TargetPath]
0x180039549  cmp     rcx, rax
0x18003954c  jz      loc_180039668
0x180039552  lea     rdx, aDeviceHarddisk; "\\Device\\Harddisk"
0x180039559  lea     rcx, [rbp+670h+TargetPath]; Str
0x18003955d  call    cs:__imp_wcsstr
0x180039563  lea     rcx, [rbp+670h+TargetPath]
0x180039567  cmp     rcx, rax
0x18003956a  jz      loc_18003963B
0x180039570  lea     rdx, aDeviceCdrom; "\\Device\\CdRom"
0x180039577  lea     rcx, [rbp+670h+TargetPath]; Str
0x18003957b  call    cs:__imp_wcsstr
0x180039581  lea     rcx, [rbp+670h+TargetPath]
0x180039585  cmp     rcx, rax
0x180039588  jz      loc_18003963B
0x18003958e  lea     rdx, aDeviceFloppy; "\\Device\\Floppy"
0x180039595  lea     rcx, [rbp+670h+TargetPath]; Str
0x180039599  call    cs:__imp_wcsstr
0x18003959f  lea     rcx, [rbp+670h+TargetPath]
0x1800395a3  cmp     rcx, rax
0x1800395a6  jz      loc_18003963B
0x1800395ac  lea     rdx, aDeviceWindfs; "\\Device\\WinDfs\\"
0x1800395b3  lea     rcx, [rbp+670h+TargetPath]; Str
0x1800395b7  call    cs:__imp_wcsstr
0x1800395bd  lea     rcx, [rbp+670h+TargetPath]
0x1800395c1  cmp     rcx, rax
0x1800395c4  jnz     loc_1800394BD
0x1800395ca  mov     r9d, 218h; Length
0x1800395d0  mov     dword ptr [rsp+770h+AllocationSize], 9; FileInformationClass
0x1800395d8  lea     r8, [rbp+670h+FileInformation]; FileInformation
0x1800395df  mov     rcx, rsi; FileHandle
0x1800395e2  lea     rdx, [rbp+670h+IoStatusBlock]; IoStatusBlock
0x1800395e6  call    cs:__imp_NtQueryInformationFile
0x1800395ec  test    eax, eax
0x1800395ee  js      loc_1800396C4
0x1800395f4  mov     edi, [rbp+670h+FileInformation]
0x1800395fa  lea     rdx, [rbp+670h+var_25A]
0x180039601  jmp     loc_1800392FB
0x180039606  cmp     esi, 0C0000034h
0x18003960c  jz      loc_1800396CB
0x180039612  mov     ecx, esi; Status
0x180039614  call    cs:__imp_RtlNtStatusToDosError
0x18003961a  mov     ebx, eax
0x18003961c  jmp     loc_1800394BD
0x180039621  mov     rcx, [rsp+770h+FileHandle]; Handle
0x180039626  call    cs:__imp_NtClose
0x18003962c  jmp     loc_1800394BD
0x180039631  mov     ebx, 6Fh ; 'o'
0x180039636  jmp     loc_1800394BD
0x18003963b  mov     rdx, r14; nSize
0x18003963e  mov     rcx, r15; lpBuffer
0x180039641  call    GetComputerNameW
0x180039646  test    eax, eax
0x180039648  jnz     loc_1800394BB
0x18003964e  mov     ebx, gs:68h
0x180039656  jmp     loc_1800394BD
0x18003965b  sub     cx, 20h ; ' '
0x18003965f  mov     [rbp+670h+DeviceName], cx
0x180039663  jmp     loc_180039518
0x180039668  movzx   eax, [rbp+670h+var_64C]
0x18003966c  cmp     [rbp+670h+DeviceName], ax
0x180039670  jnz     loc_180039552
0x180039676  cmp     di, [rbp+670h+var_64A]
0x18003967a  jnz     loc_180039552
0x180039680  mov     edx, r13d; Ch
0x180039683  lea     rcx, [rbp+670h+Str]; Str
0x180039687  xor     edi, edi
0x180039689  call    cs:__imp_wcschr
0x18003968f  mov     [rsp+770h+DestinationString.Buffer], rax
0x180039694  mov     rdx, rax
0x180039697  test    rax, rax
0x18003969a  jz      loc_180039300
0x1800396a0  add     rax, 2
0x1800396a4  lea     rcx, [rbp+670h+TargetPath]
0x1800396a8  mov     rdx, rax
0x1800396ab  mov     [rsp+770h+DestinationString.Buffer], rax
0x1800396b0  sub     rax, rcx
0x1800396b3  mov     edi, 105h
0x1800396b8  sar     rax, 1
0x1800396bb  sub     edi, eax
0x1800396bd  add     edi, edi
0x1800396bf  jmp     loc_180039467
0x1800396c4  mov     ecx, eax
0x1800396c6  jmp     loc_180039614
0x1800396cb  mov     rdx, [rsp+770h+DestinationString.Buffer]
0x1800396d0  jmp     loc_180039467
0x1800396d5  cmp     [rcx], r13w
0x1800396d9  jz      loc_180039476
0x1800396df  mov     eax, 2Eh ; '.'
0x1800396e4  cmp     ax, [rcx]
0x1800396e7  jz      loc_1800394BD
0x1800396ed  add     rcx, 2
0x1800396f1  jmp     loc_18003946A
```
