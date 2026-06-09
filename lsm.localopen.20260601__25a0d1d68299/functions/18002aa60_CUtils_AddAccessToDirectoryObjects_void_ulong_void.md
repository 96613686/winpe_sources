# CUtils::AddAccessToDirectoryObjects(void *,ulong,void *)

- ea: `0x18002aa60`
- end: `0x18002acbd`
- name: `?AddAccessToDirectoryObjects@CUtils@@CAJPEAXK0@Z`
- size: `605`
- prototype: `__int64 __fastcall(HANDLE DirectoryHandle, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009644`

## callees

- `0x1800077a0`
- `0x180009bf4`
- `0x18000acec`
- `0x18002aa60`
- `0x180099584`

## import_xrefs

- `ntdll!NtOpenSymbolicLinkObject` at `0x18002ab2d`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18002ab2d`
- `ntdll!NtSetSecurityObject` at `0x18002ac34`
- `ntdll!NtSetSecurityObject` at `0x18002ac34`
- `ntdll!NtQueryDirectoryObject` at `0x18002ac7f`
- `ntdll!NtQueryDirectoryObject` at `0x18002ac7f`
- `ntdll!NtQuerySecurityObject` at `0x18002ab58`
- `ntdll!NtQuerySecurityObject` at `0x18002abca`
- `ntdll!NtQuerySecurityObject` at `0x18002ab58`
- `ntdll!NtQuerySecurityObject` at `0x18002abca`
- `ntdll!NtClose` at `0x18002ab83`
- `ntdll!NtClose` at `0x18002abf2`
- `ntdll!NtClose` at `0x18002ac44`
- `ntdll!NtClose` at `0x18002ab83`
- `ntdll!NtClose` at `0x18002abf2`
- `ntdll!NtClose` at `0x18002ac44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aab6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ab99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002aab6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ab99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ac01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ac96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ac01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ac96`

## string_xrefs

- `0x18002aaee`: `SymbolicLink`
- `0x18002abdd`: `NtQuerySecurityObject status= 0x%x`
- `0x18002ab6e`: `NtQuerySecurityObject status: 0x%x`

## pseudocode

```c
__int64 __fastcall CUtils::AddAccessToDirectoryObjects(HANDLE DirectoryHandle, __int64 a2, void *a3)
{
  struct _UNICODE_STRING *v5; // rbx
  NTSTATUS i; // eax
  NTSTATUS v7; // eax
  void *v8; // rcx
  HLOCAL v9; // rax
  void *v10; // rdi
  NTSTATUS v11; // eax
  int v12; // eax
  void *v13; // rcx
  ULONG Context; // [rsp+48h] [rbp-9h] BYREF
  void *SymbolicLinkHandle; // [rsp+50h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+Fh] BYREF
  ULONG Length; // [rsp+C0h] [rbp+6Fh] BYREF
  ULONG ReturnLength; // [rsp+D0h] [rbp+7Fh] BYREF

  SymbolicLinkHandle = 0;
  ReturnLength = 0;
  Length = 0;
  Context = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v5 = (struct _UNICODE_STRING *)LocalAlloc(0, 0x1000u);
  if ( v5 )
  {
    for ( i = NtQueryDirectoryObject(DirectoryHandle, v5, 0x1000u, 1u, 1u, &Context, &ReturnLength);
          ;
          i = NtQueryDirectoryObject(DirectoryHandle, v5, 0x1000u, 1u, 0, &Context, &ReturnLength) )
    {
      if ( i < 0 )
      {
        LocalFree(v5);
        return 0;
      }
      if ( !wcscmp_0(v5[1].Buffer, L"SymbolicLink") )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = DirectoryHandle;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = v5;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes) >= 0 )
        {
          v7 = NtQuerySecurityObject(SymbolicLinkHandle, 7u, 0, 0, &Length);
          if ( v7 != -1073741789 )
          {
            _DbgPrintMessage(8, "NtQuerySecurityObject status: 0x%x", v7);
            v8 = SymbolicLinkHandle;
LABEL_7:
            NtClose(v8);
            continue;
          }
          v9 = LocalAlloc(0, Length);
          v8 = SymbolicLinkHandle;
          v10 = v9;
          SecurityDescriptor = v9;
          if ( !v9 )
            goto LABEL_7;
          v11 = NtQuerySecurityObject(SymbolicLinkHandle, 7u, v9, Length, &Length);
          if ( v11 >= 0 )
          {
            v12 = CUtils::AddAceToSecurityDescriptor(&SecurityDescriptor, -1610612736, a3, 0);
            v13 = SymbolicLinkHandle;
            if ( v12 >= 0 )
            {
              NtSetSecurityObject(SymbolicLinkHandle, 4u, SecurityDescriptor);
              v13 = SymbolicLinkHandle;
            }
            NtClose(v13);
            CUtils::CleanupSD(SecurityDescriptor);
          }
          else
          {
            _DbgPrintMessage(8, "NtQuerySecurityObject status= 0x%x", v11);
            NtClose(SymbolicLinkHandle);
            LocalFree(v10);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002aa60  mov     rax, rsp
0x18002aa63  mov     [rax+8], rbx
0x18002aa67  mov     [rax+18h], rsi
0x18002aa6b  mov     [rax+10h], edx
0x18002aa6e  push    rbp
0x18002aa6f  push    rdi
0x18002aa70  push    r14
0x18002aa72  lea     rbp, [rax-5Fh]
0x18002aa76  sub     rsp, 90h
0x18002aa7d  xorps   xmm0, xmm0
0x18002aa80  mov     [rbp+57h+SymbolicLinkHandle], 0
0x18002aa88  mov     rsi, rcx
0x18002aa8b  mov     [rbp+57h+arg_18], 0
0x18002aa92  xor     ecx, ecx; uFlags
0x18002aa94  mov     [rbp+57h+Length], 0
0x18002aa9b  mov     edx, 1000h; uBytes
0x18002aaa0  mov     [rbp+57h+var_60], 0
0x18002aaa7  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002aaab  mov     r14, r8
0x18002aaae  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002aab2  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002aab6  call    cs:__imp_LocalAlloc
0x18002aabd  nop     dword ptr [rax+rax+00h]
0x18002aac2  mov     rbx, rax
0x18002aac5  test    rax, rax
0x18002aac8  jz      loc_18002ACA2
0x18002aace  lea     rax, [rbp+57h+arg_18]
0x18002aad2  mov     [rsp+0A0h+ReturnLength], rax
0x18002aad7  lea     rax, [rbp+57h+var_60]
0x18002aadb  mov     [rsp+0A0h+Context], rax
0x18002aae0  mov     byte ptr [rsp+0A0h+LengthNeeded], 1
0x18002aae5  jmp     loc_18002AC70
0x18002aaea  mov     rcx, [rbx+18h]; String1
0x18002aaee  lea     rdx, aSymboliclink; "SymbolicLink"
0x18002aaf5  call    wcscmp_0
0x18002aafa  test    eax, eax
0x18002aafc  jnz     loc_18002AC59
0x18002ab02  xorps   xmm0, xmm0
0x18002ab05  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002ab0c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002ab10  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18002ab14  mov     edx, 0F0001h; DesiredAccess
0x18002ab19  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002ab20  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x18002ab24  mov     [rbp+57h+ObjectAttributes.ObjectName], rbx
0x18002ab28  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ab2d  call    cs:__imp_NtOpenSymbolicLinkObject
0x18002ab34  nop     dword ptr [rax+rax+00h]
0x18002ab39  test    eax, eax
0x18002ab3b  js      loc_18002AC59
0x18002ab41  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x18002ab45  lea     rax, [rbp+57h+Length]
0x18002ab49  xor     r9d, r9d; Length
0x18002ab4c  mov     [rsp+0A0h+LengthNeeded], rax; LengthNeeded
0x18002ab51  xor     r8d, r8d; SecurityDescriptor
0x18002ab54  lea     edx, [r9+7]; SecurityInformation
0x18002ab58  call    cs:__imp_NtQuerySecurityObject
0x18002ab5f  nop     dword ptr [rax+rax+00h]
0x18002ab64  cmp     eax, 0C0000023h
0x18002ab69  jz      short loc_18002AB94
0x18002ab6b  mov     r8d, eax
0x18002ab6e  lea     rdx, aNtquerysecurit_1; "NtQuerySecurityObject status: 0x%x"
0x18002ab75  mov     ecx, 8; int
0x18002ab7a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ab7f  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x18002ab83  call    cs:__imp_NtClose
0x18002ab8a  nop     dword ptr [rax+rax+00h]
0x18002ab8f  jmp     loc_18002AC59
0x18002ab94  mov     edx, [rbp+57h+Length]; uBytes
0x18002ab97  xor     ecx, ecx; uFlags
0x18002ab99  call    cs:__imp_LocalAlloc
0x18002aba0  nop     dword ptr [rax+rax+00h]
0x18002aba5  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x18002aba9  mov     rdi, rax
0x18002abac  mov     [rbp+57h+SecurityDescriptor], rax
0x18002abb0  test    rax, rax
0x18002abb3  jz      short loc_18002AB83
0x18002abb5  mov     r9d, [rbp+57h+Length]; Length
0x18002abb9  lea     rax, [rbp+57h+Length]
0x18002abbd  mov     r8, rdi; SecurityDescriptor
0x18002abc0  mov     [rsp+0A0h+LengthNeeded], rax; LengthNeeded
0x18002abc5  mov     edx, 7; SecurityInformation
0x18002abca  call    cs:__imp_NtQuerySecurityObject
0x18002abd1  nop     dword ptr [rax+rax+00h]
0x18002abd6  test    eax, eax
0x18002abd8  jns     short loc_18002AC0F
0x18002abda  mov     r8d, eax
0x18002abdd  lea     rdx, aNtquerysecurit_2; "NtQuerySecurityObject status= 0x%x"
0x18002abe4  mov     ecx, 8; int
0x18002abe9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002abee  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x18002abf2  call    cs:__imp_NtClose
0x18002abf9  nop     dword ptr [rax+rax+00h]
0x18002abfe  mov     rcx, rdi; hMem
0x18002ac01  call    cs:__imp_LocalFree
0x18002ac08  nop     dword ptr [rax+rax+00h]
0x18002ac0d  jmp     short loc_18002AC59
0x18002ac0f  xor     r9d, r9d; unsigned __int8
0x18002ac12  lea     rcx, [rbp+57h+SecurityDescriptor]; void **
0x18002ac16  mov     r8, r14; void *
0x18002ac19  mov     edx, 0A0000000h; unsigned int
0x18002ac1e  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x18002ac23  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x18002ac27  test    eax, eax
0x18002ac29  js      short loc_18002AC44
0x18002ac2b  mov     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18002ac2f  mov     edx, 4; SecurityInformation
0x18002ac34  call    cs:__imp_NtSetSecurityObject
0x18002ac3b  nop     dword ptr [rax+rax+00h]
0x18002ac40  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x18002ac44  call    cs:__imp_NtClose
0x18002ac4b  nop     dword ptr [rax+rax+00h]
0x18002ac50  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18002ac54  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x18002ac59  lea     rax, [rbp+57h+arg_18]
0x18002ac5d  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x18002ac62  lea     rax, [rbp+57h+var_60]
0x18002ac66  mov     [rsp+0A0h+Context], rax; Context
0x18002ac6b  mov     byte ptr [rsp+0A0h+LengthNeeded], 0; RestartScan
0x18002ac70  mov     r9b, 1; ReturnSingleEntry
0x18002ac73  mov     r8d, 1000h; BufferLength
0x18002ac79  mov     rdx, rbx; Buffer
0x18002ac7c  mov     rcx, rsi; DirectoryHandle
0x18002ac7f  call    cs:__imp_NtQueryDirectoryObject
0x18002ac86  nop     dword ptr [rax+rax+00h]
0x18002ac8b  test    eax, eax
0x18002ac8d  jns     loc_18002AAEA
0x18002ac93  mov     rcx, rbx; hMem
0x18002ac96  call    cs:__imp_LocalFree
0x18002ac9d  nop     dword ptr [rax+rax+00h]
0x18002aca2  lea     r11, [rsp+0A0h+var_10]
0x18002acaa  xor     eax, eax
0x18002acac  mov     rbx, [r11+20h]
0x18002acb0  mov     rsi, [r11+30h]
0x18002acb4  mov     rsp, r11
0x18002acb7  pop     r14
0x18002acb9  pop     rdi
0x18002acba  pop     rbp
0x18002acbb  retn
```
