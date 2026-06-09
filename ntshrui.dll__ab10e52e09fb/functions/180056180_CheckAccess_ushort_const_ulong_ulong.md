# CheckAccess(ushort const *,ulong,ulong *)

- ea: `0x180056180`
- end: `0x180056253`
- name: `?CheckAccess@@YAJPEBGKPEAK@Z`
- size: `211`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180059674`
- `0x18005cba4`
- `0x18005d5ac`

## callees

- `0x180056180`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056228`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800561b5`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800561b5`
- `ntdll!NtOpenFile` at `0x180056214`
- `ntdll!NtOpenFile` at `0x180056214`
- `ntdll!RtlFreeUnicodeString` at `0x180056236`
- `ntdll!RtlFreeUnicodeString` at `0x180056236`

## pseudocode

```c
__int64 __fastcall CheckAccess(const unsigned __int16 *a1, __int64 a2, unsigned int *a3)
{
  unsigned int v4; // ebx
  NTSTATUS v5; // ebx
  _UNICODE_STRING NtPathName; // [rsp+30h] [rbp-50h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp+20h] BYREF

  *a3 = 0;
  NtPathName = 0;
  v4 = -2147024882;
  if ( RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtPathName;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    FileHandle = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    IoStatusBlock = 0;
    v5 = NtOpenFile(&FileHandle, 0x40000u, &ObjectAttributes, &IoStatusBlock, 3u, 0);
    if ( !v5 )
    {
      *a3 |= 0x40000u;
      CloseHandle(FileHandle);
    }
    v4 = v5 | 0x10000000;
    RtlFreeUnicodeString(&NtPathName);
  }
  return v4;
}

```

## disassembly

```asm
0x180056180  mov     [rsp-8+arg_0], rbx
0x180056185  mov     [rsp-8+arg_8], rdi
0x18005618a  push    rbp
0x18005618b  mov     rbp, rsp
0x18005618e  sub     rsp, 80h
0x180056195  mov     rdi, r8
0x180056198  mov     dword ptr [r8], 0
0x18005619f  xorps   xmm0, xmm0
0x1800561a2  lea     rdx, [rbp+NtPathName]; NtPathName
0x1800561a6  xor     r8d, r8d; NtFileNamePart
0x1800561a9  xor     r9d, r9d; DirectoryInfo
0x1800561ac  movups  xmmword ptr [rbp+NtPathName.Length], xmm0
0x1800561b0  mov     ebx, 8007000Eh
0x1800561b5  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800561bb  test    al, al
0x1800561bd  jz      short loc_18005623C
0x1800561bf  xorps   xmm0, xmm0
0x1800561c2  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x1800561ca  lea     rax, [rbp+NtPathName]
0x1800561ce  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800561d6  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800561da  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800561de  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800561e2  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800561ea  mov     edx, 40000h; DesiredAccess
0x1800561ef  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800561f7  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800561fb  mov     [rbp+FileHandle], 0
0x180056203  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180056208  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x180056210  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180056214  call    cs:__imp_NtOpenFile
0x18005621a  mov     ebx, eax
0x18005621c  test    eax, eax
0x18005621e  jnz     short loc_18005622E
0x180056220  bts     dword ptr [rdi], 12h
0x180056224  mov     rcx, [rbp+FileHandle]; hObject
0x180056228  call    cs:__imp_CloseHandle
0x18005622e  bts     ebx, 1Ch
0x180056232  lea     rcx, [rbp+NtPathName]; UnicodeString
0x180056236  call    cs:__imp_RtlFreeUnicodeString
0x18005623c  lea     r11, [rsp+80h+var_s0]
0x180056244  mov     eax, ebx
0x180056246  mov     rbx, [r11+10h]
0x18005624a  mov     rdi, [r11+18h]
0x18005624e  mov     rsp, r11
0x180056251  pop     rbp
0x180056252  retn
```
