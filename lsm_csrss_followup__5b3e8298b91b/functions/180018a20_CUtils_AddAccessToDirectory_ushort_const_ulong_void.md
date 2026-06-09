# CUtils::AddAccessToDirectory(ushort const *,ulong,void *)

- ea: `0x180018a20`
- end: `0x180018c56`
- name: `?AddAccessToDirectory@CUtils@@SAJPEBGKPEAX@Z`
- size: `566`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017150`

## callees

- `0x1800074c0`
- `0x180018a20`
- `0x180018f6c`
- `0x180019f28`
- `0x180028858`

## import_xrefs

- `ntdll!NtCreateDirectoryObject` at `0x180018aa0`
- `ntdll!NtCreateDirectoryObject` at `0x180018aa0`
- `ntdll!NtSetSecurityObject` at `0x180018bce`
- `ntdll!NtSetSecurityObject` at `0x180018bce`
- `ntdll!NtQuerySecurityObject` at `0x180018ad9`
- `ntdll!NtQuerySecurityObject` at `0x180018b48`
- `ntdll!NtQuerySecurityObject` at `0x180018ad9`
- `ntdll!NtQuerySecurityObject` at `0x180018b48`
- `ntdll!NtClose` at `0x180018c1d`
- `ntdll!NtClose` at `0x180018c1d`
- `ntdll!RtlInitUnicodeString` at `0x180018a6b`
- `ntdll!RtlInitUnicodeString` at `0x180018a6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018b13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018b13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c37`

## string_xrefs

- `0x180018b86`: `CUtils::AddAccessToDirectory`
- `0x180018c03`: `CUtils::AddAccessToDirectory`
- `0x180018b90`: `AddAceToSecurityDescriptor failed: 0x%x in %s`
- `0x180018aea`: `NtQuerySecurityObject failed: %x`
- `0x180018ab6`: `NtCreateDirectoryObject failed: 0x%x in %s`
- `0x180018b58`: `NtQuerySecurityObject failed: 0x%x in %s`
- `0x180018bde`: `NtSetSecurityObject failed: 0x%x in %s`
- `0x180018bfc`: `AddAccessToDirectoryObjects failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::AddAccessToDirectory(PCWSTR SourceString, __int64 a2, void *a3)
{
  int v4; // r14d
  PSECURITY_DESCRIPTOR v5; // rdi
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  NTSTATUS v8; // ebx
  NTSTATUS v9; // eax
  int v10; // eax
  NTSTATUS v11; // eax
  unsigned int v12; // edx
  int v13; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  ULONG Length; // [rsp+B8h] [rbp+38h] BYREF
  void *DirectoryHandle; // [rsp+C8h] [rbp+48h] BYREF

  DirectoryHandle = 0;
  Length = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = 0;
  v5 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 192;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtCreateDirectoryObject(&DirectoryHandle, 0xF000Fu, &ObjectAttributes);
  v7 = v6 | 0x10000000;
  if ( v6 >= 0 )
  {
    v8 = NtQuerySecurityObject(DirectoryHandle, 7u, 0, 0, &Length);
    if ( v8 == -1073741789 )
    {
      SecurityDescriptor = LocalAlloc(0, Length);
      v5 = SecurityDescriptor;
      if ( SecurityDescriptor )
      {
        v9 = NtQuerySecurityObject(DirectoryHandle, 7u, SecurityDescriptor, Length, &Length);
        v7 = v9 | 0x10000000;
        if ( v9 >= 0 )
        {
          v4 = 1;
          v10 = CUtils::AddAceToSecurityDescriptor(&SecurityDescriptor, -1610612736, a3, 1);
          v7 = v10;
          if ( v10 < 0
            || (v10 = CUtils::AddAceToSecurityDescriptor(&SecurityDescriptor, -1610612736, a3, 0), v7 = v10, v10 < 0) )
          {
            _DbgPrintMessage(8, "AddAceToSecurityDescriptor failed: 0x%x in %s", v10, "CUtils::AddAccessToDirectory");
            v5 = SecurityDescriptor;
          }
          else
          {
            v5 = SecurityDescriptor;
            v11 = NtSetSecurityObject(DirectoryHandle, 4u, SecurityDescriptor);
            v7 = v11 | 0x10000000;
            if ( v11 >= 0 )
            {
              v13 = CUtils::AddAccessToDirectoryObjects(DirectoryHandle, v12, a3);
              v7 = v13;
              if ( v13 < 0 )
                _DbgPrintMessage(
                  8,
                  "AddAccessToDirectoryObjects failed: 0x%x in %s",
                  (unsigned int)v13,
                  "CUtils::AddAccessToDirectory");
            }
            else
            {
              _DbgPrintMessage(8, "NtSetSecurityObject failed: 0x%x in %s", v7, "CUtils::AddAccessToDirectory");
            }
          }
        }
        else
        {
          _DbgPrintMessage(8, "NtQuerySecurityObject failed: 0x%x in %s", v7, "CUtils::AddAccessToDirectory");
        }
      }
      else
      {
        v7 = -2147024882;
      }
    }
    else
    {
      if ( !v8 )
        v8 = -1073741823;
      v7 = v8 | 0x10000000;
      _DbgPrintMessage(8, "NtQuerySecurityObject failed: %x", v7);
    }
  }
  else
  {
    _DbgPrintMessage(8, "NtCreateDirectoryObject failed: 0x%x in %s", v7, "CUtils::AddAccessToDirectory");
  }
  if ( DirectoryHandle )
    NtClose(DirectoryHandle);
  if ( v5 )
  {
    if ( v4 )
      CUtils::CleanupSD(v5);
    else
      LocalFree(v5);
  }
  return v7;
}

```

## disassembly

```asm
0x180018a20  mov     [rsp-28h+arg_0], rbx
0x180018a25  mov     [rsp-28h+Length], edx
0x180018a29  push    rbp
0x180018a2a  push    rsi
0x180018a2b  push    rdi
0x180018a2c  push    r12
0x180018a2e  push    r14
0x180018a30  mov     rbp, rsp
0x180018a33  sub     rsp, 80h
0x180018a3a  xorps   xmm0, xmm0
0x180018a3d  mov     [rbp+DirectoryHandle], 0
0x180018a45  mov     rdx, rcx; SourceString
0x180018a48  mov     [rbp+Length], 0
0x180018a4f  lea     rcx, [rbp+DestinationString]; DestinationString
0x180018a53  mov     rsi, r8
0x180018a56  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180018a5a  xor     r14d, r14d
0x180018a5d  xor     edi, edi
0x180018a5f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180018a63  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180018a67  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180018a6b  call    cs:__imp_RtlInitUnicodeString
0x180018a71  lea     rax, [rbp+DestinationString]
0x180018a75  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180018a7c  xorps   xmm0, xmm0
0x180018a7f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180018a83  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180018a87  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x180018a8b  mov     edx, 0F000Fh; DesiredAccess
0x180018a90  mov     [rbp+ObjectAttributes.Attributes], 0C0h
0x180018a97  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x180018a9b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180018aa0  call    cs:__imp_NtCreateDirectoryObject
0x180018aa6  mov     ebx, eax
0x180018aa8  mov     r12d, 10000000h
0x180018aae  or      ebx, r12d
0x180018ab1  jge     short loc_180018AC2
0x180018ab3  mov     r8d, ebx
0x180018ab6  lea     rdx, aNtcreatedirect; "NtCreateDirectoryObject failed: 0x%x in"...
0x180018abd  jmp     loc_180018C03
0x180018ac2  mov     rcx, [rbp+DirectoryHandle]; Handle
0x180018ac6  lea     rax, [rbp+Length]
0x180018aca  xor     r9d, r9d; Length
0x180018acd  mov     [rsp+80h+LengthNeeded], rax; LengthNeeded
0x180018ad2  xor     r8d, r8d; SecurityDescriptor
0x180018ad5  lea     edx, [r9+7]; SecurityInformation
0x180018ad9  call    cs:__imp_NtQuerySecurityObject
0x180018adf  mov     ebx, eax
0x180018ae1  cmp     eax, 0C0000023h
0x180018ae6  jz      short loc_180018B0E
0x180018ae8  test    ebx, ebx
0x180018aea  lea     rdx, aNtquerysecurit_0; "NtQuerySecurityObject failed: %x"
0x180018af1  mov     eax, 0C0000001h
0x180018af6  mov     ecx, 8; int
0x180018afb  cmovz   ebx, eax
0x180018afe  or      ebx, r12d
0x180018b01  mov     r8d, ebx
0x180018b04  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018b09  jmp     loc_180018C14
0x180018b0e  mov     edx, [rbp+Length]; uBytes
0x180018b11  xor     ecx, ecx; uFlags
0x180018b13  call    cs:__imp_LocalAlloc
0x180018b19  mov     [rbp+SecurityDescriptor], rax
0x180018b1d  mov     rdi, rax
0x180018b20  test    rax, rax
0x180018b23  jnz     short loc_180018B2F
0x180018b25  mov     ebx, 8007000Eh
0x180018b2a  jmp     loc_180018C14
0x180018b2f  mov     r9d, [rbp+Length]; Length
0x180018b33  lea     rax, [rbp+Length]
0x180018b37  mov     rcx, [rbp+DirectoryHandle]; Handle
0x180018b3b  mov     r8, rdi; SecurityDescriptor
0x180018b3e  mov     edx, 7; SecurityInformation
0x180018b43  mov     [rsp+80h+LengthNeeded], rax; LengthNeeded
0x180018b48  call    cs:__imp_NtQuerySecurityObject
0x180018b4e  mov     ebx, eax
0x180018b50  or      ebx, r12d
0x180018b53  jge     short loc_180018B64
0x180018b55  mov     r8d, ebx
0x180018b58  lea     rdx, aNtquerysecurit; "NtQuerySecurityObject failed: 0x%x in %"...
0x180018b5f  jmp     loc_180018C03
0x180018b64  mov     r14d, 1
0x180018b6a  lea     rcx, [rbp+SecurityDescriptor]; void **
0x180018b6e  mov     edi, 0A0000000h
0x180018b73  mov     r9b, r14b; unsigned __int8
0x180018b76  mov     edx, edi; unsigned int
0x180018b78  mov     r8, rsi; void *
0x180018b7b  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x180018b80  mov     ebx, eax
0x180018b82  test    eax, eax
0x180018b84  jns     short loc_180018BA7
0x180018b86  lea     r9, aCutilsAddacces; "CUtils::AddAccessToDirectory"
0x180018b8d  mov     r8d, eax
0x180018b90  lea     rdx, aAddacetosecuri; "AddAceToSecurityDescriptor failed: 0x%x"...
0x180018b97  mov     ecx, 8; int
0x180018b9c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018ba1  mov     rdi, [rbp+SecurityDescriptor]
0x180018ba5  jmp     short loc_180018C14
0x180018ba7  xor     r9d, r9d; unsigned __int8
0x180018baa  lea     rcx, [rbp+SecurityDescriptor]; void **
0x180018bae  mov     r8, rsi; void *
0x180018bb1  mov     edx, edi; unsigned int
0x180018bb3  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x180018bb8  mov     ebx, eax
0x180018bba  test    eax, eax
0x180018bbc  js      short loc_180018B86
0x180018bbe  mov     rdi, [rbp+SecurityDescriptor]
0x180018bc2  mov     edx, 4; SecurityInformation
0x180018bc7  mov     rcx, [rbp+DirectoryHandle]; Handle
0x180018bcb  mov     r8, rdi; SecurityDescriptor
0x180018bce  call    cs:__imp_NtSetSecurityObject
0x180018bd4  mov     ebx, eax
0x180018bd6  or      ebx, r12d
0x180018bd9  jge     short loc_180018BE7
0x180018bdb  mov     r8d, ebx
0x180018bde  lea     rdx, aNtsetsecurityo; "NtSetSecurityObject failed: 0x%x in %s"
0x180018be5  jmp     short loc_180018C03
0x180018be7  mov     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x180018beb  mov     r8, rsi; void *
0x180018bee  call    ?AddAccessToDirectoryObjects@CUtils@@CAJPEAXK0@Z; CUtils::AddAccessToDirectoryObjects(void *,ulong,void *)
0x180018bf3  mov     ebx, eax
0x180018bf5  test    eax, eax
0x180018bf7  jns     short loc_180018C14
0x180018bf9  mov     r8d, eax
0x180018bfc  lea     rdx, aAddaccesstodir_0; "AddAccessToDirectoryObjects failed: 0x%"...
0x180018c03  lea     r9, aCutilsAddacces; "CUtils::AddAccessToDirectory"
0x180018c0a  mov     ecx, 8; int
0x180018c0f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018c14  mov     rcx, [rbp+DirectoryHandle]; Handle
0x180018c18  test    rcx, rcx
0x180018c1b  jz      short loc_180018C23
0x180018c1d  call    cs:__imp_NtClose
0x180018c23  test    rdi, rdi
0x180018c26  jz      short loc_180018C3D
0x180018c28  mov     rcx, rdi; hMem
0x180018c2b  test    r14d, r14d
0x180018c2e  jz      short loc_180018C37
0x180018c30  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180018c35  jmp     short loc_180018C3D
0x180018c37  call    cs:__imp_LocalFree
0x180018c3d  mov     eax, ebx
0x180018c3f  mov     rbx, [rsp+80h+arg_0]
0x180018c47  add     rsp, 80h
0x180018c4e  pop     r14
0x180018c50  pop     r12
0x180018c52  pop     rdi
0x180018c53  pop     rsi
0x180018c54  pop     rbp
0x180018c55  retn
```
