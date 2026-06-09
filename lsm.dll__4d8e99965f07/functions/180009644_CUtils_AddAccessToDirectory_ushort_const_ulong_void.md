# CUtils::AddAccessToDirectory(ushort const *,ulong,void *)

- ea: `0x180009644`
- end: `0x1800098ab`
- name: `?AddAccessToDirectory@CUtils@@SAJPEBGKPEAX@Z`
- size: `615`
- prototype: `__int64 __fastcall(PCWSTR SourceString, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000afd0`

## callees

- `0x1800077a0`
- `0x180009644`
- `0x180009bf4`
- `0x18000acec`
- `0x18002aa60`

## import_xrefs

- `ntdll!NtCreateDirectoryObject` at `0x1800096ca`
- `ntdll!NtCreateDirectoryObject` at `0x1800096ca`
- `ntdll!NtSetSecurityObject` at `0x180009810`
- `ntdll!NtSetSecurityObject` at `0x180009810`
- `ntdll!NtQuerySecurityObject` at `0x180009709`
- `ntdll!NtQuerySecurityObject` at `0x180009784`
- `ntdll!NtQuerySecurityObject` at `0x180009709`
- `ntdll!NtQuerySecurityObject` at `0x180009784`
- `ntdll!NtClose` at `0x180009865`
- `ntdll!NtClose` at `0x180009865`
- `ntdll!RtlInitUnicodeString` at `0x18000968f`
- `ntdll!RtlInitUnicodeString` at `0x18000968f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009749`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009749`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009885`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009885`

## string_xrefs

- `0x1800097c8`: `CUtils::AddAccessToDirectory`
- `0x18000984b`: `CUtils::AddAccessToDirectory`
- `0x1800097d2`: `AddAceToSecurityDescriptor failed: 0x%x in %s`
- `0x180009720`: `NtQuerySecurityObject failed: %x`
- `0x1800096e6`: `NtCreateDirectoryObject failed: 0x%x in %s`
- `0x18000979a`: `NtQuerySecurityObject failed: 0x%x in %s`
- `0x180009844`: `AddAccessToDirectoryObjects failed: 0x%x in %s`
- `0x180009826`: `NtSetSecurityObject failed: 0x%x in %s`

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
0x180009644  mov     [rsp-28h+arg_0], rbx
0x180009649  mov     [rsp-28h+Length], edx
0x18000964d  push    rbp
0x18000964e  push    rsi
0x18000964f  push    rdi
0x180009650  push    r12
0x180009652  push    r14
0x180009654  mov     rbp, rsp
0x180009657  sub     rsp, 80h
0x18000965e  xorps   xmm0, xmm0
0x180009661  mov     [rbp+DirectoryHandle], 0
0x180009669  mov     rdx, rcx; SourceString
0x18000966c  mov     [rbp+Length], 0
0x180009673  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009677  mov     rsi, r8
0x18000967a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000967e  xor     r14d, r14d
0x180009681  xor     edi, edi
0x180009683  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180009687  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000968b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000968f  call    cs:__imp_RtlInitUnicodeString
0x180009696  nop     dword ptr [rax+rax+00h]
0x18000969b  lea     rax, [rbp+DestinationString]
0x18000969f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800096a6  xorps   xmm0, xmm0
0x1800096a9  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800096ad  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800096b1  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x1800096b5  mov     edx, 0F000Fh; DesiredAccess
0x1800096ba  mov     [rbp+ObjectAttributes.Attributes], 0C0h
0x1800096c1  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x1800096c5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800096ca  call    cs:__imp_NtCreateDirectoryObject
0x1800096d1  nop     dword ptr [rax+rax+00h]
0x1800096d6  mov     ebx, eax
0x1800096d8  mov     r12d, 10000000h
0x1800096de  or      ebx, r12d
0x1800096e1  jge     short loc_1800096F2
0x1800096e3  mov     r8d, ebx
0x1800096e6  lea     rdx, aNtcreatedirect; "NtCreateDirectoryObject failed: 0x%x in"...
0x1800096ed  jmp     loc_18000984B
0x1800096f2  mov     rcx, [rbp+DirectoryHandle]; Handle
0x1800096f6  lea     rax, [rbp+Length]
0x1800096fa  xor     r9d, r9d; Length
0x1800096fd  mov     [rsp+80h+LengthNeeded], rax; LengthNeeded
0x180009702  xor     r8d, r8d; SecurityDescriptor
0x180009705  lea     edx, [r9+7]; SecurityInformation
0x180009709  call    cs:__imp_NtQuerySecurityObject
0x180009710  nop     dword ptr [rax+rax+00h]
0x180009715  mov     ebx, eax
0x180009717  cmp     eax, 0C0000023h
0x18000971c  jz      short loc_180009744
0x18000971e  test    ebx, ebx
0x180009720  lea     rdx, aNtquerysecurit_0; "NtQuerySecurityObject failed: %x"
0x180009727  mov     eax, 0C0000001h
0x18000972c  mov     ecx, 8; int
0x180009731  cmovz   ebx, eax
0x180009734  or      ebx, r12d
0x180009737  mov     r8d, ebx
0x18000973a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000973f  jmp     loc_18000985C
0x180009744  mov     edx, [rbp+Length]; uBytes
0x180009747  xor     ecx, ecx; uFlags
0x180009749  call    cs:__imp_LocalAlloc
0x180009750  nop     dword ptr [rax+rax+00h]
0x180009755  mov     [rbp+SecurityDescriptor], rax
0x180009759  mov     rdi, rax
0x18000975c  test    rax, rax
0x18000975f  jnz     short loc_18000976B
0x180009761  mov     ebx, 8007000Eh
0x180009766  jmp     loc_18000985C
0x18000976b  mov     r9d, [rbp+Length]; Length
0x18000976f  lea     rax, [rbp+Length]
0x180009773  mov     rcx, [rbp+DirectoryHandle]; Handle
0x180009777  mov     r8, rdi; SecurityDescriptor
0x18000977a  mov     edx, 7; SecurityInformation
0x18000977f  mov     [rsp+80h+LengthNeeded], rax; LengthNeeded
0x180009784  call    cs:__imp_NtQuerySecurityObject
0x18000978b  nop     dword ptr [rax+rax+00h]
0x180009790  mov     ebx, eax
0x180009792  or      ebx, r12d
0x180009795  jge     short loc_1800097A6
0x180009797  mov     r8d, ebx
0x18000979a  lea     rdx, aNtquerysecurit; "NtQuerySecurityObject failed: 0x%x in %"...
0x1800097a1  jmp     loc_18000984B
0x1800097a6  mov     r14d, 1
0x1800097ac  lea     rcx, [rbp+SecurityDescriptor]; void **
0x1800097b0  mov     edi, 0A0000000h
0x1800097b5  mov     r9b, r14b; unsigned __int8
0x1800097b8  mov     edx, edi; unsigned int
0x1800097ba  mov     r8, rsi; void *
0x1800097bd  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x1800097c2  mov     ebx, eax
0x1800097c4  test    eax, eax
0x1800097c6  jns     short loc_1800097E9
0x1800097c8  lea     r9, aCutilsAddacces; "CUtils::AddAccessToDirectory"
0x1800097cf  mov     r8d, eax
0x1800097d2  lea     rdx, aAddacetosecuri; "AddAceToSecurityDescriptor failed: 0x%x"...
0x1800097d9  mov     ecx, 8; int
0x1800097de  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800097e3  mov     rdi, [rbp+SecurityDescriptor]
0x1800097e7  jmp     short loc_18000985C
0x1800097e9  xor     r9d, r9d; unsigned __int8
0x1800097ec  lea     rcx, [rbp+SecurityDescriptor]; void **
0x1800097f0  mov     r8, rsi; void *
0x1800097f3  mov     edx, edi; unsigned int
0x1800097f5  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x1800097fa  mov     ebx, eax
0x1800097fc  test    eax, eax
0x1800097fe  js      short loc_1800097C8
0x180009800  mov     rdi, [rbp+SecurityDescriptor]
0x180009804  mov     edx, 4; SecurityInformation
0x180009809  mov     rcx, [rbp+DirectoryHandle]; Handle
0x18000980d  mov     r8, rdi; SecurityDescriptor
0x180009810  call    cs:__imp_NtSetSecurityObject
0x180009817  nop     dword ptr [rax+rax+00h]
0x18000981c  mov     ebx, eax
0x18000981e  or      ebx, r12d
0x180009821  jge     short loc_18000982F
0x180009823  mov     r8d, ebx
0x180009826  lea     rdx, aNtsetsecurityo; "NtSetSecurityObject failed: 0x%x in %s"
0x18000982d  jmp     short loc_18000984B
0x18000982f  mov     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x180009833  mov     r8, rsi; void *
0x180009836  call    ?AddAccessToDirectoryObjects@CUtils@@CAJPEAXK0@Z; CUtils::AddAccessToDirectoryObjects(void *,ulong,void *)
0x18000983b  mov     ebx, eax
0x18000983d  test    eax, eax
0x18000983f  jns     short loc_18000985C
0x180009841  mov     r8d, eax
0x180009844  lea     rdx, aAddaccesstodir_0; "AddAccessToDirectoryObjects failed: 0x%"...
0x18000984b  lea     r9, aCutilsAddacces; "CUtils::AddAccessToDirectory"
0x180009852  mov     ecx, 8; int
0x180009857  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000985c  mov     rcx, [rbp+DirectoryHandle]; Handle
0x180009860  test    rcx, rcx
0x180009863  jz      short loc_180009871
0x180009865  call    cs:__imp_NtClose
0x18000986c  nop     dword ptr [rax+rax+00h]
0x180009871  test    rdi, rdi
0x180009874  jz      short loc_180009891
0x180009876  mov     rcx, rdi; hMem
0x180009879  test    r14d, r14d
0x18000987c  jz      short loc_180009885
0x18000987e  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180009883  jmp     short loc_180009891
0x180009885  call    cs:__imp_LocalFree
0x18000988c  nop     dword ptr [rax+rax+00h]
0x180009891  mov     eax, ebx
0x180009893  mov     rbx, [rsp+80h+arg_0]
0x18000989b  add     rsp, 80h
0x1800098a2  pop     r14
0x1800098a4  pop     r12
0x1800098a6  pop     rdi
0x1800098a7  pop     rsi
0x1800098a8  pop     rbp
0x1800098a9  retn
```
