# StorageReserveHelper::Internal::GetHandle(ushort const *,void * *)

- ea: `0x18002701c`
- end: `0x1800271bd`
- name: `?GetHandle@Internal@StorageReserveHelper@@YAJPEBGPEAPEAX@Z`
- size: `417`
- prototype: `int(StorageReserveHelper::Internal *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180026ef8`
- `0x180053d94`

## callees

- `0x18002701c`
- `0x180030ad0`
- `0x1800364c8`
- `0x18003bc70`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002708c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18002708c`
- `ntdll!RtlFreeUnicodeString` at `0x1800270c4`
- `ntdll!RtlFreeUnicodeString` at `0x180027191`
- `ntdll!RtlFreeUnicodeString` at `0x1800270c4`
- `ntdll!RtlFreeUnicodeString` at `0x180027191`
- `ntdll!NtCreateFile` at `0x180027142`
- `ntdll!NtCreateFile` at `0x180027142`

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
0x18002701c  mov     [rsp-8+arg_10], rbx
0x180027021  push    rbp
0x180027022  lea     rbp, [rsp-57h]
0x180027027  sub     rsp, 0C0h
0x18002702e  mov     rax, cs:__security_cookie
0x180027035  xor     rax, rsp
0x180027038  mov     [rbp+57h+var_10], rax
0x18002703c  xorps   xmm1, xmm1
0x18002703f  xorps   xmm0, xmm0
0x180027042  mov     rbx, rdx
0x180027045  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x180027049  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18002704d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x180027051  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x180027055  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180027059  test    rdx, rdx
0x18002705c  jnz     short loc_180027082
0x18002705e  mov     rcx, [rbp+5Fh]; this
0x180027062  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180027069  mov     ebx, 80070057h
0x18002706e  mov     edx, 5Dh ; ']'; void *
0x180027073  mov     r9d, ebx; char *
0x180027076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002707b  mov     eax, ebx
0x18002707d  jmp     loc_18002719F
0x180027082  xor     r9d, r9d; DirectoryInfo
0x180027085  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180027089  xor     r8d, r8d; NtFileNamePart
0x18002708c  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180027093  nop     dword ptr [rax+rax+00h]
0x180027098  test    al, al
0x18002709a  jnz     short loc_1800270D2
0x18002709c  mov     ebx, 80004005h
0x1800270a1  mov     edx, 6Ah ; 'j'; void *
0x1800270a6  mov     rcx, [rbp+5Fh]; this
0x1800270aa  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800270b1  mov     r9d, ebx; char *
0x1800270b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800270b9  cmp     [rbp+57h+NtPathName.Buffer], 0
0x1800270be  jz      short loc_18002707B
0x1800270c0  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x1800270c4  call    cs:__imp_RtlFreeUnicodeString
0x1800270cb  nop     dword ptr [rax+rax+00h]
0x1800270d0  jmp     short loc_18002707B
0x1800270d2  mov     [rsp+0C0h+EaLength], 0; EaLength
0x1800270da  lea     rax, [rbp+57h+NtPathName]
0x1800270de  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x1800270e7  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800270eb  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x1800270f3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800270f7  mov     [rsp+0C0h+CreateDisposition], 1; CreateDisposition
0x1800270ff  xorps   xmm0, xmm0
0x180027102  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x18002710a  mov     edx, 100180h; DesiredAccess
0x18002710f  mov     [rsp+0C0h+FileAttributes], 80h; FileAttributes
0x180027117  mov     rcx, rbx; FileHandle
0x18002711a  mov     [rsp+0C0h+AllocationSize], 0; int
0x180027123  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002712a  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180027132  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180027139  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002713d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180027142  call    cs:__imp_NtCreateFile
0x180027149  nop     dword ptr [rax+rax+00h]
0x18002714e  test    eax, eax
0x180027150  jns     short loc_180027171
0x180027152  mov     rcx, [rbp+5Fh]; this
0x180027156  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002715d  mov     r9d, eax; char *
0x180027160  mov     edx, 7Ch ; '|'; void *
0x180027165  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002716a  mov     ebx, eax
0x18002716c  jmp     loc_1800270B9
0x180027171  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180027175  jnz     short loc_180027186
0x180027177  mov     ebx, 80070006h
0x18002717c  mov     edx, 7Fh
0x180027181  jmp     loc_1800270A6
0x180027186  cmp     [rbp+57h+NtPathName.Buffer], 0
0x18002718b  jz      short loc_18002719D
0x18002718d  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x180027191  call    cs:__imp_RtlFreeUnicodeString
0x180027198  nop     dword ptr [rax+rax+00h]
0x18002719d  xor     eax, eax
0x18002719f  mov     rcx, [rbp+57h+var_10]
0x1800271a3  xor     rcx, rsp; StackCookie
0x1800271a6  call    __security_check_cookie
0x1800271ab  mov     rbx, [rsp+0C0h+arg_10]
0x1800271b3  add     rsp, 0C0h
0x1800271ba  pop     rbp
0x1800271bb  retn
```
