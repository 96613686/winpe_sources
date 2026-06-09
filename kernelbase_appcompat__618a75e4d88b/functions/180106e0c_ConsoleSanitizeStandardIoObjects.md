# ConsoleSanitizeStandardIoObjects

- ea: `0x180106e0c`
- end: `0x180107188`
- name: `ConsoleSanitizeStandardIoObjects`
- size: `892`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180065ef0`
- `0x180066708`
- `0x1800674f4`

## callees

- `0x180106e0c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180106e8f`
- `ntdll!RtlInitUnicodeString` at `0x180106f9c`
- `ntdll!RtlInitUnicodeString` at `0x180107073`
- `ntdll!RtlInitUnicodeString` at `0x180106e8f`
- `ntdll!RtlInitUnicodeString` at `0x180106f9c`
- `ntdll!RtlInitUnicodeString` at `0x180107073`
- `ntdll!NtCreateFile` at `0x180106efa`
- `ntdll!NtCreateFile` at `0x180107007`
- `ntdll!NtCreateFile` at `0x1801070de`
- `ntdll!NtCreateFile` at `0x180106efa`
- `ntdll!NtCreateFile` at `0x180107007`
- `ntdll!NtCreateFile` at `0x1801070de`
- `ntdll!NtClose` at `0x18010702a`
- `ntdll!NtClose` at `0x180107107`
- `ntdll!NtClose` at `0x18010702a`
- `ntdll!NtClose` at `0x180107107`
- `ntdll!NtDuplicateObject` at `0x180107139`
- `ntdll!NtDuplicateObject` at `0x180107139`

## pseudocode

```c
NTSTATUS __fastcall ConsoleSanitizeStandardIoObjects(__int64 a1)
{
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // r14
  NTSTATUS v3; // ebx
  int v4; // edi
  void *v5; // rbx
  NTSTATUS result; // eax
  void *v7; // rbx
  HANDLE v8; // rcx
  void *v9; // rbx
  NTSTATUS v10; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  HANDLE FileHandle; // [rsp+F8h] [rbp+6Fh] BYREF
  HANDLE SourceHandle; // [rsp+100h] [rbp+77h] BYREF
  HANDLE TargetHandle; // [rsp+108h] [rbp+7Fh] BYREF

  FileHandle = 0;
  TargetHandle = 0;
  SourceHandle = 0;
  ProcessParameters = NtCurrentPeb()->ProcessParameters;
  if ( ProcessParameters->StandardInput )
  {
    v3 = 0;
    v4 = 0;
    if ( ((__int64)ProcessParameters->StandardInput & 0x10000003) != 3 )
    {
LABEL_5:
      if ( !ProcessParameters->StandardOutput || ((__int64)ProcessParameters->StandardOutput & 0x10000003) == 3 )
      {
        v7 = *(void **)(a1 + 8);
        IoStatusBlock = 0;
        DestinationString = 0;
        memset(&ObjectAttributes, 0, 44);
        RtlInitUnicodeString(&DestinationString, L"\\Output");
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = v7;
        ObjectAttributes.Attributes = 66;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v3 = NtCreateFile(&SourceHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 2u, 0x20u, 0, 0);
        if ( v3 < 0 )
        {
          v8 = FileHandle;
          goto LABEL_19;
        }
        v3 = 0;
        v4 |= 2u;
      }
      if ( ProcessParameters->StandardError && ((__int64)ProcessParameters->StandardError & 0x10000003) != 3 )
        goto LABEL_9;
      if ( SourceHandle )
      {
        v3 = NtDuplicateObject(
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               SourceHandle,
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               &TargetHandle,
               0,
               0,
               6u);
      }
      else
      {
        v9 = *(void **)(a1 + 8);
        IoStatusBlock = 0;
        DestinationString = 0;
        memset(&ObjectAttributes, 0, 44);
        RtlInitUnicodeString(&DestinationString, L"\\Output");
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = v9;
        ObjectAttributes.Attributes = 66;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v10 = NtCreateFile(&TargetHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 2u, 0x20u, 0, 0);
        v3 = 0;
        if ( v10 < 0 )
          v3 = v10;
      }
      if ( v3 >= 0 )
      {
        v4 |= 4u;
LABEL_9:
        if ( (v4 & 1) != 0 )
          *(_QWORD *)(a1 + 24) = FileHandle;
        if ( (v4 & 2) != 0 )
          *(_QWORD *)(a1 + 32) = SourceHandle;
        if ( (v4 & 4) != 0 )
          *(_QWORD *)(a1 + 40) = TargetHandle;
        *(_DWORD *)a1 = v4;
        return v3;
      }
      if ( FileHandle )
        NtClose(FileHandle);
      v8 = SourceHandle;
LABEL_19:
      if ( v8 )
        NtClose(v8);
      return v3;
    }
  }
  v5 = *(void **)(a1 + 8);
  IoStatusBlock = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\Input");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v5;
  ObjectAttributes.Attributes = 66;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 2u, 0x20u, 0, 0);
  if ( result >= 0 )
  {
    v3 = 0;
    v4 = 1;
    goto LABEL_5;
  }
  return result;
}

```

## disassembly

```asm
0x180106e0c  push    rbp
0x180106e0e  push    rbx
0x180106e0f  push    rsi
0x180106e10  push    rdi
0x180106e11  push    r13
0x180106e13  push    r14
0x180106e15  push    r15
0x180106e17  lea     rbp, [rsp-27h]
0x180106e1c  sub     rsp, 0B0h
0x180106e23  xor     r15d, r15d
0x180106e26  mov     rsi, rcx
0x180106e29  mov     [rbp+57h+FileHandle], r15
0x180106e2d  mov     r13d, 10000003h
0x180106e33  mov     [rbp+57h+TargetHandle], r15
0x180106e37  mov     [rbp+57h+SourceHandle], r15
0x180106e3b  mov     rax, gs:60h
0x180106e44  mov     r14, [rax+20h]
0x180106e48  mov     rax, [r14+20h]
0x180106e4c  test    rax, rax
0x180106e4f  jz      short loc_180106E64
0x180106e51  and     rax, r13
0x180106e54  mov     ebx, r15d
0x180106e57  mov     edi, r15d
0x180106e5a  cmp     rax, 3
0x180106e5e  jnz     loc_180106F21
0x180106e64  mov     rbx, [rcx+8]
0x180106e68  lea     rdx, aInput; "\\Input"
0x180106e6f  xorps   xmm0, xmm0
0x180106e72  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180106e76  xorps   xmm1, xmm1
0x180106e79  xor     eax, eax
0x180106e7b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180106e7f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180106e83  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180106e87  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180106e8b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180106e8f  call    cs:__imp_RtlInitUnicodeString
0x180106e96  nop     dword ptr [rax+rax+00h]
0x180106e9b  mov     [rsp+0E0h+EaLength], r15d; EaLength
0x180106ea0  lea     rax, [rbp+57h+DestinationString]
0x180106ea4  mov     [rsp+0E0h+EaBuffer], r15; EaBuffer
0x180106ea9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180106ead  mov     [rsp+0E0h+CreateOptions], 20h ; ' '; CreateOptions
0x180106eb5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180106eb9  mov     [rsp+0E0h+CreateDisposition], 2; CreateDisposition
0x180106ec1  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180106ec5  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180106ecd  xorps   xmm0, xmm0
0x180106ed0  mov     [rsp+0E0h+FileAttributes], r15d; FileAttributes
0x180106ed5  mov     edx, 12019Fh; DesiredAccess
0x180106eda  mov     [rsp+0E0h+AllocationSize], r15; AllocationSize
0x180106edf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180106ee6  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180106eea  mov     [rbp+57h+ObjectAttributes.Attributes], 42h ; 'B'
0x180106ef1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180106ef5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180106efa  call    cs:__imp_NtCreateFile
0x180106f01  nop     dword ptr [rax+rax+00h]
0x180106f06  test    eax, eax
0x180106f08  jns     loc_180107149
0x180106f0e  add     rsp, 0B0h
0x180106f15  pop     r15
0x180106f17  pop     r14
0x180106f19  pop     r13
0x180106f1b  pop     rdi
0x180106f1c  pop     rsi
0x180106f1d  pop     rbx
0x180106f1e  pop     rbp
0x180106f1f  retn
0x180106f21  mov     rax, [r14+28h]
0x180106f25  test    rax, rax
0x180106f28  jz      short loc_180106F71
0x180106f2a  and     rax, r13
0x180106f2d  cmp     rax, 3
0x180106f31  jz      short loc_180106F71
0x180106f33  mov     rax, [r14+30h]
0x180106f37  test    rax, rax
0x180106f3a  jz      loc_18010703B
0x180106f40  and     rax, r13
0x180106f43  cmp     rax, 3
0x180106f47  jz      loc_18010703B
0x180106f4d  test    dil, 1
0x180106f51  jnz     loc_180107161
0x180106f57  test    dil, 2
0x180106f5b  jnz     loc_18010716E
0x180106f61  test    dil, 4
0x180106f65  jnz     loc_18010717B
0x180106f6b  mov     [rsi], edi
0x180106f6d  mov     eax, ebx
0x180106f6f  jmp     short loc_180106F0E
0x180106f71  mov     rbx, [rsi+8]
0x180106f75  lea     rdx, aOutput; "\\Output"
0x180106f7c  xorps   xmm0, xmm0
0x180106f7f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180106f83  xorps   xmm1, xmm1
0x180106f86  xor     eax, eax
0x180106f88  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180106f8c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180106f90  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180106f94  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180106f98  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180106f9c  call    cs:__imp_RtlInitUnicodeString
0x180106fa3  nop     dword ptr [rax+rax+00h]
0x180106fa8  mov     [rsp+0E0h+EaLength], r15d; EaLength
0x180106fad  lea     rax, [rbp+57h+DestinationString]
0x180106fb1  mov     [rsp+0E0h+EaBuffer], r15; EaBuffer
0x180106fb6  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180106fba  mov     [rsp+0E0h+CreateOptions], 20h ; ' '; CreateOptions
0x180106fc2  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180106fc6  mov     [rsp+0E0h+CreateDisposition], 2; CreateDisposition
0x180106fce  lea     rcx, [rbp+57h+SourceHandle]; FileHandle
0x180106fd2  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180106fda  xorps   xmm0, xmm0
0x180106fdd  mov     [rsp+0E0h+FileAttributes], r15d; FileAttributes
0x180106fe2  mov     edx, 12019Fh; DesiredAccess
0x180106fe7  mov     [rsp+0E0h+AllocationSize], r15; AllocationSize
0x180106fec  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180106ff3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180106ff7  mov     [rbp+57h+ObjectAttributes.Attributes], 42h ; 'B'
0x180106ffe  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180107002  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180107007  call    cs:__imp_NtCreateFile
0x18010700e  nop     dword ptr [rax+rax+00h]
0x180107013  mov     ebx, eax
0x180107015  test    eax, eax
0x180107017  jns     loc_180107156
0x18010701d  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180107021  test    rcx, rcx
0x180107024  jz      loc_180106F6D
0x18010702a  call    cs:__imp_NtClose
0x180107031  nop     dword ptr [rax+rax+00h]
0x180107036  jmp     loc_180106F6D
0x18010703b  mov     rdx, [rbp+57h+SourceHandle]; SourceHandle
0x18010703f  test    rdx, rdx
0x180107042  jnz     loc_18010711C
0x180107048  mov     rbx, [rsi+8]
0x18010704c  lea     rdx, aOutput; "\\Output"
0x180107053  xorps   xmm0, xmm0
0x180107056  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18010705a  xorps   xmm1, xmm1
0x18010705d  xor     eax, eax
0x18010705f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180107063  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180107067  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18010706b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18010706f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180107073  call    cs:__imp_RtlInitUnicodeString
0x18010707a  nop     dword ptr [rax+rax+00h]
0x18010707f  mov     [rsp+0E0h+EaLength], r15d; EaLength
0x180107084  lea     rax, [rbp+57h+DestinationString]
0x180107088  mov     [rsp+0E0h+EaBuffer], r15; EaBuffer
0x18010708d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180107091  mov     [rsp+0E0h+CreateOptions], 20h ; ' '; CreateOptions
0x180107099  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18010709d  mov     [rsp+0E0h+CreateDisposition], 2; CreateDisposition
0x1801070a5  lea     rcx, [rbp+57h+TargetHandle]; FileHandle
0x1801070a9  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x1801070b1  xorps   xmm0, xmm0
0x1801070b4  mov     [rsp+0E0h+FileAttributes], r15d; FileAttributes
0x1801070b9  mov     edx, 12019Fh; DesiredAccess
0x1801070be  mov     [rsp+0E0h+AllocationSize], r15; AllocationSize
0x1801070c3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1801070ca  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1801070ce  mov     [rbp+57h+ObjectAttributes.Attributes], 42h ; 'B'
0x1801070d5  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1801070d9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801070de  call    cs:__imp_NtCreateFile
0x1801070e5  nop     dword ptr [rax+rax+00h]
0x1801070ea  test    eax, eax
0x1801070ec  mov     ebx, r15d
0x1801070ef  cmovs   ebx, eax
0x1801070f2  test    ebx, ebx
0x1801070f4  js      short loc_1801070FE
0x1801070f6  or      edi, 4
0x1801070f9  jmp     loc_180106F4D
0x1801070fe  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180107102  test    rcx, rcx
0x180107105  jz      short loc_180107113
0x180107107  call    cs:__imp_NtClose
0x18010710e  nop     dword ptr [rax+rax+00h]
0x180107113  mov     rcx, [rbp+57h+SourceHandle]
0x180107117  jmp     loc_180107021
0x18010711c  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180107120  mov     [rsp+0E0h+ShareAccess], 6; Options
0x180107128  mov     r8, rcx; TargetProcessHandle
0x18010712b  mov     [rsp+0E0h+FileAttributes], r15d; HandleAttributes
0x180107130  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x180107134  mov     dword ptr [rsp+0E0h+AllocationSize], r15d; DesiredAccess
0x180107139  call    cs:__imp_NtDuplicateObject
0x180107140  nop     dword ptr [rax+rax+00h]
0x180107145  mov     ebx, eax
0x180107147  jmp     short loc_1801070F2
0x180107149  mov     ebx, r15d
0x18010714c  mov     edi, 1
0x180107151  jmp     loc_180106F21
0x180107156  mov     ebx, r15d
0x180107159  or      edi, 2
0x18010715c  jmp     loc_180106F33
0x180107161  mov     rax, [rbp+57h+FileHandle]
0x180107165  mov     [rsi+18h], rax
0x180107169  jmp     loc_180106F57
0x18010716e  mov     rax, [rbp+57h+SourceHandle]
0x180107172  mov     [rsi+20h], rax
0x180107176  jmp     loc_180106F61
0x18010717b  mov     rax, [rbp+57h+TargetHandle]
0x18010717f  mov     [rsi+28h], rax
0x180107183  jmp     loc_180106F6B
```
