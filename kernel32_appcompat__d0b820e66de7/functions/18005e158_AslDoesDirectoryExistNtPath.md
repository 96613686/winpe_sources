# AslDoesDirectoryExistNtPath

- ea: `0x18005e158`
- end: `0x18005e2af`
- name: `AslDoesDirectoryExistNtPath`
- size: `343`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007edb0`

## callees

- `0x18001f138`
- `0x18005e158`
- `0x180061df4`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005e1b4`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005e1b4`
- `ntdll!RtlFreeUnicodeString` at `0x18005e28b`
- `ntdll!RtlFreeUnicodeString` at `0x18005e28b`
- `ntdll!ZwClose` at `0x18005e258`
- `ntdll!ZwClose` at `0x18005e258`
- `ntdll!ZwOpenFile` at `0x18005e244`
- `ntdll!ZwOpenFile` at `0x18005e244`
- `ntdll!RtlInitUnicodeString` at `0x18005e1f5`
- `ntdll!RtlInitUnicodeString` at `0x18005e1f5`

## string_xrefs

- `0x18005e1c8`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x18005e1da`: `AslDoesDirectoryExistNtPath`

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
0x18005e158  mov     [rsp-8+arg_8], rsi
0x18005e15d  mov     [rsp-8+arg_10], rdi
0x18005e162  push    rbp
0x18005e163  mov     rbp, rsp
0x18005e166  sub     rsp, 80h
0x18005e16d  xor     eax, eax
0x18005e16f  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x18005e176  xorps   xmm0, xmm0
0x18005e179  mov     qword ptr [rbp+DestinationString.Length], rax
0x18005e17d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18005e181  mov     rdi, rcx
0x18005e184  mov     [rbp+FileHandle], rax
0x18005e188  lea     r8d, [rax+0Ch]; MaxCount
0x18005e18c  mov     [rbp+DestinationString.Buffer], rax
0x18005e190  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18005e194  xor     esi, esi
0x18005e196  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18005e19a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18005e19e  call    _wcsnicmp_0
0x18005e1a3  test    eax, eax
0x18005e1a5  jz      short loc_18005E1EE
0x18005e1a7  xor     r9d, r9d
0x18005e1aa  lea     rdx, [rbp+DestinationString]
0x18005e1ae  xor     r8d, r8d
0x18005e1b1  mov     rcx, rdi
0x18005e1b4  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18005e1bb  nop     dword ptr [rax+rax+00h]
0x18005e1c0  test    eax, eax
0x18005e1c2  jns     short loc_18005E201
0x18005e1c4  mov     [rsp+80h+OpenOptions], eax
0x18005e1c8  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18005e1cf  mov     r8d, 22Ah
0x18005e1d5  mov     qword ptr [rsp+80h+ShareAccess], rdi
0x18005e1da  lea     rdx, aAsldoesdirecto; "AslDoesDirectoryExistNtPath"
0x18005e1e1  lea     ecx, [rsi+1]
0x18005e1e4  call    AslLogCallPrintf
0x18005e1e9  jmp     loc_18005E279
0x18005e1ee  mov     rdx, rdi; SourceString
0x18005e1f1  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005e1f5  call    cs:__imp_RtlInitUnicodeString
0x18005e1fc  nop     dword ptr [rax+rax+00h]
0x18005e201  lea     rax, [rbp+DestinationString]
0x18005e205  mov     [rsp+80h+OpenOptions], 1; OpenOptions
0x18005e20d  xorps   xmm0, xmm0
0x18005e210  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18005e214  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18005e218  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005e21f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005e223  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18005e227  mov     edx, 100080h; DesiredAccess
0x18005e22c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18005e233  lea     rcx, [rbp+FileHandle]; FileHandle
0x18005e237  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x18005e23f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e244  call    cs:__imp_ZwOpenFile
0x18005e24b  nop     dword ptr [rax+rax+00h]
0x18005e250  test    eax, eax
0x18005e252  js      short loc_18005E266
0x18005e254  mov     rcx, [rbp+FileHandle]; Handle
0x18005e258  call    cs:__imp_ZwClose
0x18005e25f  nop     dword ptr [rax+rax+00h]
0x18005e264  jmp     short loc_18005E274
0x18005e266  cmp     eax, 0C0000022h
0x18005e26b  jz      short loc_18005E274
0x18005e26d  cmp     eax, 0C0000043h
0x18005e272  jnz     short loc_18005E279
0x18005e274  mov     esi, 1
0x18005e279  mov     rcx, [rbp+DestinationString.Buffer]
0x18005e27d  cmp     rcx, rdi
0x18005e280  jz      short loc_18005E297
0x18005e282  test    rcx, rcx
0x18005e285  jz      short loc_18005E297
0x18005e287  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18005e28b  call    cs:__imp_RtlFreeUnicodeString
0x18005e292  nop     dword ptr [rax+rax+00h]
0x18005e297  lea     r11, [rsp+80h+var_s0]
0x18005e29f  mov     eax, esi
0x18005e2a1  mov     rsi, [r11+18h]
0x18005e2a5  mov     rdi, [r11+20h]
0x18005e2a9  mov     rsp, r11
0x18005e2ac  pop     rbp
0x18005e2ad  retn
```
