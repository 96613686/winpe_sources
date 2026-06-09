# StorageReserveHelper::Internal::GetHandle(ushort const *,void * *)

- ea: `0x180024708`
- end: `0x180024890`
- name: `?GetHandle@Internal@StorageReserveHelper@@YAJPEBGPEAPEAX@Z`
- size: `392`
- prototype: `int(StorageReserveHelper::Internal *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800245fc`
- `0x180050d70`

## callees

- `0x180024708`
- `0x18002aef0`
- `0x18002d2d8`
- `0x18003a730`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180024778`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180024778`
- `ntdll!RtlFreeUnicodeString` at `0x1800247aa`
- `ntdll!RtlFreeUnicodeString` at `0x18002486b`
- `ntdll!RtlFreeUnicodeString` at `0x1800247aa`
- `ntdll!RtlFreeUnicodeString` at `0x18002486b`
- `ntdll!NtCreateFile` at `0x180024822`
- `ntdll!NtCreateFile` at `0x180024822`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::Internal::GetHandle(const WCHAR *this, void **a2, void **a3)
{
  unsigned int v4; // ebx
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  int AllocationSize; // [rsp+20h] [rbp-49h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+90h] [rbp+27h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  NtPathName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)0x80070057LL,
      AllocationSize);
    return v4;
  }
  if ( !RtlDosPathNameToNtPathName_U(this, &NtPathName, 0, 0) )
  {
    v4 = -2147467259;
    v6 = 106;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)v4,
      AllocationSize);
    goto LABEL_7;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtCreateFile(a2, 0x100180u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x20u, 0, 0);
  if ( v7 < 0 )
  {
    v4 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x7C,
           (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
           (const char *)(unsigned int)v7,
           AllocationSize);
LABEL_7:
    if ( NtPathName.Buffer )
      RtlFreeUnicodeString(&NtPathName);
    return v4;
  }
  if ( *a2 == (void *)-1LL )
  {
    v4 = -2147024890;
    v6 = 127;
    goto LABEL_6;
  }
  if ( NtPathName.Buffer )
    RtlFreeUnicodeString(&NtPathName);
  return 0;
}

```

## disassembly

```asm
0x180024708  mov     [rsp-8+arg_10], rbx
0x18002470d  push    rbp
0x18002470e  lea     rbp, [rsp-57h]
0x180024713  sub     rsp, 0C0h
0x18002471a  mov     rax, cs:__security_cookie
0x180024721  xor     rax, rsp
0x180024724  mov     [rbp+57h+var_10], rax
0x180024728  xorps   xmm1, xmm1
0x18002472b  xorps   xmm0, xmm0
0x18002472e  mov     rbx, rdx
0x180024731  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x180024735  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x180024739  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18002473d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180024741  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180024745  test    rdx, rdx
0x180024748  jnz     short loc_18002476E
0x18002474a  mov     rcx, [rbp+5Fh]; this
0x18002474e  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180024755  mov     ebx, 80070057h
0x18002475a  mov     edx, 5Dh ; ']'; void *
0x18002475f  mov     r9d, ebx; char *
0x180024762  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024767  mov     eax, ebx
0x180024769  jmp     loc_180024873
0x18002476e  xor     r9d, r9d; DirectoryInfo
0x180024771  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180024775  xor     r8d, r8d; NtFileNamePart
0x180024778  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18002477e  test    al, al
0x180024780  jnz     short loc_1800247B2
0x180024782  mov     ebx, 80004005h
0x180024787  mov     edx, 6Ah ; 'j'; void *
0x18002478c  mov     rcx, [rbp+5Fh]; this
0x180024790  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180024797  mov     r9d, ebx; char *
0x18002479a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002479f  cmp     [rbp+57h+NtPathName.Buffer], 0
0x1800247a4  jz      short loc_180024767
0x1800247a6  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x1800247aa  call    cs:__imp_RtlFreeUnicodeString
0x1800247b0  jmp     short loc_180024767
0x1800247b2  mov     [rsp+0C0h+EaLength], 0; EaLength
0x1800247ba  lea     rax, [rbp+57h+NtPathName]
0x1800247be  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x1800247c7  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800247cb  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x1800247d3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800247d7  mov     [rsp+0C0h+CreateDisposition], 1; CreateDisposition
0x1800247df  xorps   xmm0, xmm0
0x1800247e2  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x1800247ea  mov     edx, 100180h; DesiredAccess
0x1800247ef  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x1800247f7  mov     rcx, rbx; FileHandle
0x1800247fa  mov     [rsp+0C0h+AllocationSize], 0; int
0x180024803  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002480a  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180024812  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180024819  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002481d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180024822  call    cs:__imp_NtCreateFile
0x180024828  test    eax, eax
0x18002482a  jns     short loc_18002484B
0x18002482c  mov     rcx, [rbp+5Fh]; this
0x180024830  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180024837  mov     r9d, eax; char *
0x18002483a  mov     edx, 7Ch ; '|'; void *
0x18002483f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180024844  mov     ebx, eax
0x180024846  jmp     loc_18002479F
0x18002484b  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18002484f  jnz     short loc_180024860
0x180024851  mov     ebx, 80070006h
0x180024856  mov     edx, 7Fh
0x18002485b  jmp     loc_18002478C
0x180024860  cmp     [rbp+57h+NtPathName.Buffer], 0
0x180024865  jz      short loc_180024871
0x180024867  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x18002486b  call    cs:__imp_RtlFreeUnicodeString
0x180024871  xor     eax, eax
0x180024873  mov     rcx, [rbp+57h+var_10]
0x180024877  xor     rcx, rsp; StackCookie
0x18002487a  call    __security_check_cookie
0x18002487f  mov     rbx, [rsp+0C0h+arg_10]
0x180024887  add     rsp, 0C0h
0x18002488e  pop     rbp
0x18002488f  retn
```
