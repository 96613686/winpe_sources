# AslDoesDirectoryExistNtPath

- ea: `0x1800c01f8`
- end: `0x1800c032d`
- name: `AslDoesDirectoryExistNtPath`
- size: `309`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a9020`

## callees

- `0x18004281c`
- `0x180076e9c`
- `0x1800c01f8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800c028c`
- `ntdll!RtlInitUnicodeString` at `0x1800c028c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800c0254`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800c0254`
- `ntdll!ZwClose` at `0x1800c02e3`
- `ntdll!ZwClose` at `0x1800c02e3`
- `ntdll!RtlFreeUnicodeString` at `0x1800c0310`
- `ntdll!RtlFreeUnicodeString` at `0x1800c0310`
- `ntdll!ZwOpenFile` at `0x1800c02d5`
- `ntdll!ZwOpenFile` at `0x1800c02d5`

## string_xrefs

- `0x1800c0262`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x1800c0274`: `AslDoesDirectoryExistNtPath`

## pseudocode

```c
__int64 __fastcall AslDoesDirectoryExistNtPath(PCWSTR SourceString)
{
  unsigned int v2; // esi
  int v3; // eax
  NTSTATUS v4; // eax
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
  if ( wcsnicmp(SourceString, L"\\SystemRoot\\", 0xCu) )
  {
    v3 = RtlDosPathNameToNtPathName_U_WithStatus(SourceString, &DestinationString, 0, 0);
    if ( v3 < 0 )
    {
      AslLogCallPrintf(
        1,
        "AslDoesDirectoryExistNtPath",
        554,
        "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]",
        SourceString,
        v3);
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
  v4 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 1u);
  if ( v4 >= 0 )
  {
    ZwClose(FileHandle);
LABEL_9:
    v2 = 1;
    goto LABEL_10;
  }
  if ( v4 == -1073741790 || v4 == -1073741757 )
    goto LABEL_9;
LABEL_10:
  if ( DestinationString.Buffer != SourceString && DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  return v2;
}

```

## disassembly

```asm
0x1800c01f8  mov     [rsp-8+arg_8], rsi
0x1800c01fd  mov     [rsp-8+arg_10], rdi
0x1800c0202  push    rbp
0x1800c0203  mov     rbp, rsp
0x1800c0206  sub     rsp, 80h
0x1800c020d  xor     eax, eax
0x1800c020f  lea     rdx, aSystemroot_0; "\\SystemRoot\\"
0x1800c0216  xorps   xmm0, xmm0
0x1800c0219  mov     qword ptr [rbp+DestinationString.Length], rax
0x1800c021d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800c0221  mov     rdi, rcx
0x1800c0224  mov     [rbp+FileHandle], rax
0x1800c0228  lea     r8d, [rax+0Ch]; MaxCount
0x1800c022c  mov     [rbp+DestinationString.Buffer], rax
0x1800c0230  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800c0234  xor     esi, esi
0x1800c0236  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800c023a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800c023e  call    _wcsnicmp
0x1800c0243  test    eax, eax
0x1800c0245  jz      short loc_1800C0285
0x1800c0247  xor     r9d, r9d
0x1800c024a  lea     rdx, [rbp+DestinationString]
0x1800c024e  xor     r8d, r8d
0x1800c0251  mov     rcx, rdi
0x1800c0254  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800c025a  test    eax, eax
0x1800c025c  jns     short loc_1800C0292
0x1800c025e  mov     [rsp+80h+OpenOptions], eax
0x1800c0262  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x1800c0269  mov     r8d, 22Ah
0x1800c026f  mov     qword ptr [rsp+80h+ShareAccess], rdi
0x1800c0274  lea     rdx, aAsldoesdirecto; "AslDoesDirectoryExistNtPath"
0x1800c027b  lea     ecx, [rsi+1]
0x1800c027e  call    AslLogCallPrintf
0x1800c0283  jmp     short loc_1800C02FE
0x1800c0285  mov     rdx, rdi; SourceString
0x1800c0288  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800c028c  call    cs:__imp_RtlInitUnicodeString
0x1800c0292  lea     rax, [rbp+DestinationString]
0x1800c0296  mov     [rsp+80h+OpenOptions], 1; OpenOptions
0x1800c029e  xorps   xmm0, xmm0
0x1800c02a1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800c02a5  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800c02a9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800c02b0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800c02b4  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1800c02b8  mov     edx, 100080h; DesiredAccess
0x1800c02bd  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800c02c4  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800c02c8  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x1800c02d0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c02d5  call    cs:__imp_ZwOpenFile
0x1800c02db  test    eax, eax
0x1800c02dd  js      short loc_1800C02EB
0x1800c02df  mov     rcx, [rbp+FileHandle]; Handle
0x1800c02e3  call    cs:__imp_ZwClose
0x1800c02e9  jmp     short loc_1800C02F9
0x1800c02eb  cmp     eax, 0C0000022h
0x1800c02f0  jz      short loc_1800C02F9
0x1800c02f2  cmp     eax, 0C0000043h
0x1800c02f7  jnz     short loc_1800C02FE
0x1800c02f9  mov     esi, 1
0x1800c02fe  mov     rcx, [rbp+DestinationString.Buffer]
0x1800c0302  cmp     rcx, rdi
0x1800c0305  jz      short loc_1800C0316
0x1800c0307  test    rcx, rcx
0x1800c030a  jz      short loc_1800C0316
0x1800c030c  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1800c0310  call    cs:__imp_RtlFreeUnicodeString
0x1800c0316  lea     r11, [rsp+80h+var_s0]
0x1800c031e  mov     eax, esi
0x1800c0320  mov     rsi, [r11+18h]
0x1800c0324  mov     rdi, [r11+20h]
0x1800c0328  mov     rsp, r11
0x1800c032b  pop     rbp
0x1800c032c  retn
```
