# CUtils::AddAccessToDirectoryObjects(void *,ulong,void *)

- ea: `0x180028858`
- end: `0x180028a6c`
- name: `?AddAccessToDirectoryObjects@CUtils@@CAJPEAXK0@Z`
- size: `532`
- prototype: `__int64 __fastcall(HANDLE DirectoryHandle, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018a20`

## callees

- `0x1800074c0`
- `0x180018f6c`
- `0x180019f28`
- `0x180028858`
- `0x180094034`

## import_xrefs

- `ntdll!NtOpenSymbolicLinkObject` at `0x18002891f`
- `ntdll!NtOpenSymbolicLinkObject` at `0x18002891f`
- `ntdll!NtSetSecurityObject` at `0x1800289fc`
- `ntdll!NtSetSecurityObject` at `0x1800289fc`
- `ntdll!NtQueryDirectoryObject` at `0x180028a3b`
- `ntdll!NtQueryDirectoryObject` at `0x180028a3b`
- `ntdll!NtQuerySecurityObject` at `0x180028944`
- `ntdll!NtQuerySecurityObject` at `0x1800289a4`
- `ntdll!NtQuerySecurityObject` at `0x180028944`
- `ntdll!NtQuerySecurityObject` at `0x1800289a4`
- `ntdll!NtClose` at `0x180028969`
- `ntdll!NtClose` at `0x1800289c6`
- `ntdll!NtClose` at `0x180028a06`
- `ntdll!NtClose` at `0x180028969`
- `ntdll!NtClose` at `0x1800289c6`
- `ntdll!NtClose` at `0x180028a06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800288ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028979`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800288ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800289cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028a4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800289cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028a4c`

## string_xrefs

- `0x1800288e0`: `SymbolicLink`
- `0x180028954`: `NtQuerySecurityObject status: 0x%x`
- `0x1800289b1`: `NtQuerySecurityObject status= 0x%x`

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
0x180028858  mov     rax, rsp
0x18002885b  mov     [rax+8], rbx
0x18002885f  mov     [rax+18h], rsi
0x180028863  mov     [rax+10h], edx
0x180028866  push    rbp
0x180028867  push    rdi
0x180028868  push    r14
0x18002886a  lea     rbp, [rax-5Fh]
0x18002886e  sub     rsp, 90h
0x180028875  xorps   xmm0, xmm0
0x180028878  mov     [rbp+57h+SymbolicLinkHandle], 0
0x180028880  mov     rsi, rcx
0x180028883  mov     [rbp+57h+arg_18], 0
0x18002888a  xor     ecx, ecx; uFlags
0x18002888c  mov     [rbp+57h+Length], 0
0x180028893  mov     edx, 1000h; uBytes
0x180028898  mov     [rbp+57h+var_60], 0
0x18002889f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800288a3  mov     r14, r8
0x1800288a6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800288aa  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800288ae  call    cs:__imp_LocalAlloc
0x1800288b4  mov     rbx, rax
0x1800288b7  test    rax, rax
0x1800288ba  jz      loc_180028A52
0x1800288c0  lea     rax, [rbp+57h+arg_18]
0x1800288c4  mov     [rsp+0A0h+ReturnLength], rax
0x1800288c9  lea     rax, [rbp+57h+var_60]
0x1800288cd  mov     [rsp+0A0h+Context], rax
0x1800288d2  mov     byte ptr [rsp+0A0h+LengthNeeded], 1
0x1800288d7  jmp     loc_180028A2C
0x1800288dc  mov     rcx, [rbx+18h]; String1
0x1800288e0  lea     rdx, aSymboliclink; "SymbolicLink"
0x1800288e7  call    wcscmp_0
0x1800288ec  test    eax, eax
0x1800288ee  jnz     loc_180028A15
0x1800288f4  xorps   xmm0, xmm0
0x1800288f7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800288fe  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180028902  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x180028906  mov     edx, 0F0001h; DesiredAccess
0x18002890b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180028912  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180028916  mov     [rbp+57h+ObjectAttributes.ObjectName], rbx
0x18002891a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002891f  call    cs:__imp_NtOpenSymbolicLinkObject
0x180028925  test    eax, eax
0x180028927  js      loc_180028A15
0x18002892d  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x180028931  lea     rax, [rbp+57h+Length]
0x180028935  xor     r9d, r9d; Length
0x180028938  mov     [rsp+0A0h+LengthNeeded], rax; LengthNeeded
0x18002893d  xor     r8d, r8d; SecurityDescriptor
0x180028940  lea     edx, [r9+7]; SecurityInformation
0x180028944  call    cs:__imp_NtQuerySecurityObject
0x18002894a  cmp     eax, 0C0000023h
0x18002894f  jz      short loc_180028974
0x180028951  mov     r8d, eax
0x180028954  lea     rdx, aNtquerysecurit_1; "NtQuerySecurityObject status: 0x%x"
0x18002895b  mov     ecx, 8; int
0x180028960  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180028965  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x180028969  call    cs:__imp_NtClose
0x18002896f  jmp     loc_180028A15
0x180028974  mov     edx, [rbp+57h+Length]; uBytes
0x180028977  xor     ecx, ecx; uFlags
0x180028979  call    cs:__imp_LocalAlloc
0x18002897f  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x180028983  mov     rdi, rax
0x180028986  mov     [rbp+57h+SecurityDescriptor], rax
0x18002898a  test    rax, rax
0x18002898d  jz      short loc_180028969
0x18002898f  mov     r9d, [rbp+57h+Length]; Length
0x180028993  lea     rax, [rbp+57h+Length]
0x180028997  mov     r8, rdi; SecurityDescriptor
0x18002899a  mov     [rsp+0A0h+LengthNeeded], rax; LengthNeeded
0x18002899f  mov     edx, 7; SecurityInformation
0x1800289a4  call    cs:__imp_NtQuerySecurityObject
0x1800289aa  test    eax, eax
0x1800289ac  jns     short loc_1800289D7
0x1800289ae  mov     r8d, eax
0x1800289b1  lea     rdx, aNtquerysecurit_2; "NtQuerySecurityObject status= 0x%x"
0x1800289b8  mov     ecx, 8; int
0x1800289bd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800289c2  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x1800289c6  call    cs:__imp_NtClose
0x1800289cc  mov     rcx, rdi; hMem
0x1800289cf  call    cs:__imp_LocalFree
0x1800289d5  jmp     short loc_180028A15
0x1800289d7  xor     r9d, r9d; unsigned __int8
0x1800289da  lea     rcx, [rbp+57h+SecurityDescriptor]; void **
0x1800289de  mov     r8, r14; void *
0x1800289e1  mov     edx, 0A0000000h; unsigned int
0x1800289e6  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x1800289eb  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x1800289ef  test    eax, eax
0x1800289f1  js      short loc_180028A06
0x1800289f3  mov     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800289f7  mov     edx, 4; SecurityInformation
0x1800289fc  call    cs:__imp_NtSetSecurityObject
0x180028a02  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x180028a06  call    cs:__imp_NtClose
0x180028a0c  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180028a10  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180028a15  lea     rax, [rbp+57h+arg_18]
0x180028a19  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x180028a1e  lea     rax, [rbp+57h+var_60]
0x180028a22  mov     [rsp+0A0h+Context], rax; Context
0x180028a27  mov     byte ptr [rsp+0A0h+LengthNeeded], 0; RestartScan
0x180028a2c  mov     r9b, 1; ReturnSingleEntry
0x180028a2f  mov     r8d, 1000h; BufferLength
0x180028a35  mov     rdx, rbx; Buffer
0x180028a38  mov     rcx, rsi; DirectoryHandle
0x180028a3b  call    cs:__imp_NtQueryDirectoryObject
0x180028a41  test    eax, eax
0x180028a43  jns     loc_1800288DC
0x180028a49  mov     rcx, rbx; hMem
0x180028a4c  call    cs:__imp_LocalFree
0x180028a52  lea     r11, [rsp+0A0h+var_10]
0x180028a5a  xor     eax, eax
0x180028a5c  mov     rbx, [r11+20h]
0x180028a60  mov     rsi, [r11+30h]
0x180028a64  mov     rsp, r11
0x180028a67  pop     r14
0x180028a69  pop     rdi
0x180028a6a  pop     rbp
0x180028a6b  retn
```
