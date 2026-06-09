# AslDoesDirectoryExistNtPath

- ea: `0x180058adc`
- end: `0x180058c11`
- name: `AslDoesDirectoryExistNtPath`
- size: `309`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180076fb0`

## callees

- `0x1800212e4`
- `0x180058adc`
- `0x18005c414`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180058b38`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180058b38`
- `ntdll!RtlFreeUnicodeString` at `0x180058bf4`
- `ntdll!RtlFreeUnicodeString` at `0x180058bf4`
- `ntdll!ZwClose` at `0x180058bc7`
- `ntdll!ZwClose` at `0x180058bc7`
- `ntdll!ZwOpenFile` at `0x180058bb9`
- `ntdll!ZwOpenFile` at `0x180058bb9`
- `ntdll!RtlInitUnicodeString` at `0x180058b70`
- `ntdll!RtlInitUnicodeString` at `0x180058b70`

## string_xrefs

- `0x180058b46`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x180058b58`: `AslDoesDirectoryExistNtPath`

## pseudocode

```c
__int64 __fastcall AslDoesDirectoryExistNtPath(PCWSTR SourceString)
{
  unsigned int v2; // esi
  NTSTATUS v3; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+10h] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  FileHandle = 0;
  DestinationString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  v2 = 0;
  IoStatusBlock = 0;
  if ( wcsnicmp_0(SourceString, L"\\SystemRoot\\", 0xCu) )
  {
    if ( (int)RtlDosPathNameToNtPathName_U_WithStatus(SourceString, &DestinationString, 0, 0) < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"AslDoesDirectoryExistNtPath",
        554,
        (unsigned int)"RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]");
      goto LABEL_10;
    }
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 1u);
  if ( v3 >= 0 )
  {
    ZwClose(FileHandle);
LABEL_9:
    v2 = 1;
    goto LABEL_10;
  }
  if ( v3 == -1073741790 || v3 == -1073741757 )
    goto LABEL_9;
LABEL_10:
  if ( DestinationString.Buffer != SourceString && DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  return v2;
}

```

## disassembly

```asm
0x180058adc  mov     [rsp-8+arg_8], rsi
0x180058ae1  mov     [rsp-8+arg_10], rdi
0x180058ae6  push    rbp
0x180058ae7  mov     rbp, rsp
0x180058aea  sub     rsp, 80h
0x180058af1  xor     eax, eax
0x180058af3  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x180058afa  xorps   xmm0, xmm0
0x180058afd  mov     qword ptr [rbp+DestinationString.Length], rax
0x180058b01  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180058b05  mov     rdi, rcx
0x180058b08  mov     [rbp+FileHandle], rax
0x180058b0c  lea     r8d, [rax+0Ch]; MaxCount
0x180058b10  mov     [rbp+DestinationString.Buffer], rax
0x180058b14  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180058b18  xor     esi, esi
0x180058b1a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180058b1e  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180058b22  call    _wcsnicmp_0
0x180058b27  test    eax, eax
0x180058b29  jz      short loc_180058B69
0x180058b2b  xor     r9d, r9d
0x180058b2e  lea     rdx, [rbp+DestinationString]
0x180058b32  xor     r8d, r8d
0x180058b35  mov     rcx, rdi
0x180058b38  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180058b3e  test    eax, eax
0x180058b40  jns     short loc_180058B76
0x180058b42  mov     [rsp+80h+OpenOptions], eax
0x180058b46  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180058b4d  mov     r8d, 22Ah
0x180058b53  mov     qword ptr [rsp+80h+ShareAccess], rdi
0x180058b58  lea     rdx, aAsldoesdirecto; "AslDoesDirectoryExistNtPath"
0x180058b5f  lea     ecx, [rsi+1]
0x180058b62  call    AslLogCallPrintf
0x180058b67  jmp     short loc_180058BE2
0x180058b69  mov     rdx, rdi; SourceString
0x180058b6c  lea     rcx, [rbp+DestinationString]; DestinationString
0x180058b70  call    cs:__imp_RtlInitUnicodeString
0x180058b76  lea     rax, [rbp+DestinationString]
0x180058b7a  mov     [rsp+80h+OpenOptions], 1; OpenOptions
0x180058b82  xorps   xmm0, xmm0
0x180058b85  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180058b89  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180058b8d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180058b94  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180058b98  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180058b9c  mov     edx, 100080h; DesiredAccess
0x180058ba1  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180058ba8  lea     rcx, [rbp+FileHandle]; FileHandle
0x180058bac  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x180058bb4  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180058bb9  call    cs:__imp_ZwOpenFile
0x180058bbf  test    eax, eax
0x180058bc1  js      short loc_180058BCF
0x180058bc3  mov     rcx, [rbp+FileHandle]; Handle
0x180058bc7  call    cs:__imp_ZwClose
0x180058bcd  jmp     short loc_180058BDD
0x180058bcf  cmp     eax, 0C0000022h
0x180058bd4  jz      short loc_180058BDD
0x180058bd6  cmp     eax, 0C0000043h
0x180058bdb  jnz     short loc_180058BE2
0x180058bdd  mov     esi, 1
0x180058be2  mov     rcx, [rbp+DestinationString.Buffer]
0x180058be6  cmp     rcx, rdi
0x180058be9  jz      short loc_180058BFA
0x180058beb  test    rcx, rcx
0x180058bee  jz      short loc_180058BFA
0x180058bf0  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180058bf4  call    cs:__imp_RtlFreeUnicodeString
0x180058bfa  lea     r11, [rsp+80h+var_s0]
0x180058c02  mov     eax, esi
0x180058c04  mov     rsi, [r11+18h]
0x180058c08  mov     rdi, [r11+20h]
0x180058c0c  mov     rsp, r11
0x180058c0f  pop     rbp
0x180058c10  retn
```
