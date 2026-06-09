# CfpCreateFile

- ea: `0x1800046bc`
- end: `0x1800047fc`
- name: `CfpCreateFile`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003d50`
- `0x180004dd0`
- `0x1800064e0`
- `0x1800078d0`
- `0x180007f30`
- `0x18000e250`
- `0x18001035c`
- `0x1800112c0`

## callees

- `0x1800046bc`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800047ab`
- `ntdll!NtCreateFile` at `0x1800047ab`
- `ntdll!RtlFreeUnicodeString` at `0x1800047d2`
- `ntdll!RtlFreeUnicodeString` at `0x1800047d2`
- `ntdll!RtlDosLongPathNameToNtPathName_U_WithStatus` at `0x180004710`
- `ntdll!RtlDosLongPathNameToNtPathName_U_WithStatus` at `0x180004710`
- `ntdll!RtlNtStatusToDosError` at `0x180004720`
- `ntdll!RtlNtStatusToDosError` at `0x1800047bb`
- `ntdll!RtlNtStatusToDosError` at `0x180004720`
- `ntdll!RtlNtStatusToDosError` at `0x1800047bb`

## pseudocode

```c
__int64 __fastcall CfpCreateFile(
        __int64 a1,
        __int64 a2,
        ACCESS_MASK a3,
        ULONG a4,
        __int64 a5,
        ULONG CreateOptions,
        __int64 a7,
        void **FileHandle)
{
  ACCESS_MASK v9; // edi
  int v10; // ebx
  signed int v11; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-51h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-41h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-31h] BYREF

  v9 = a3;
  IoStatusBlock = 0;
  UnicodeString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a3 || (CreateOptions & 0x30) != 0 )
    v9 = a3 | 0x100000;
  v10 = RtlDosLongPathNameToNtPathName_U_WithStatus(a1, &UnicodeString, 0, 0);
  v11 = RtlNtStatusToDosError(v10);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  if ( v11 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &UnicodeString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = NtCreateFile(FileHandle, v9, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, a4, 1u, CreateOptions, 0, 0);
    RtlNtStatusToDosError(v10);
  }
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v10 < 0 )
    *FileHandle = (void *)-1LL;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800046bc  push    rbp
0x1800046be  push    rbx
0x1800046bf  push    rsi
0x1800046c0  push    rdi
0x1800046c1  push    r14
0x1800046c3  push    r15
0x1800046c5  lea     rbp, [rsp-7]
0x1800046ca  sub     rsp, 0B8h
0x1800046d1  mov     r14d, [rbp+2Fh+arg_28]
0x1800046d5  xorps   xmm0, xmm0
0x1800046d8  xor     eax, eax
0x1800046da  xorps   xmm1, xmm1
0x1800046dd  mov     r15d, r9d
0x1800046e0  mov     edi, r8d
0x1800046e3  movups  xmmword ptr [rbp+2Fh+ObjectAttributes.ObjectName], xmm0
0x1800046e7  movups  xmmword ptr [rbp+2Fh+ObjectAttributes+1Ch], xmm0
0x1800046eb  movups  xmmword ptr [rbp+2Fh+IoStatusBlock], xmm0
0x1800046ef  movups  xmmword ptr [rbp+2Fh+UnicodeString.Length], xmm1
0x1800046f3  movups  xmmword ptr [rbp+2Fh+ObjectAttributes.Length], xmm0
0x1800046f7  test    r8d, r8d
0x1800046fa  jz      short loc_180004702
0x1800046fc  test    r14b, 30h
0x180004700  jz      short loc_180004706
0x180004702  bts     edi, 14h
0x180004706  xor     r9d, r9d
0x180004709  lea     rdx, [rbp+2Fh+UnicodeString]
0x18000470d  xor     r8d, r8d
0x180004710  call    cs:__imp_RtlDosLongPathNameToNtPathName_U_WithStatus
0x180004717  nop     dword ptr [rax+rax+00h]
0x18000471c  mov     ecx, eax; Status
0x18000471e  mov     ebx, eax
0x180004720  call    cs:__imp_RtlNtStatusToDosError
0x180004727  nop     dword ptr [rax+rax+00h]
0x18000472c  test    eax, eax
0x18000472e  jle     short loc_180004738
0x180004730  movzx   eax, ax
0x180004733  or      eax, 80070000h
0x180004738  mov     rsi, [rbp+2Fh+FileHandle]
0x18000473c  test    eax, eax
0x18000473e  js      loc_1800047C7
0x180004744  mov     [rsp+0E0h+EaLength], 0; EaLength
0x18000474c  lea     rax, [rbp+2Fh+UnicodeString]
0x180004750  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x180004759  lea     r9, [rbp+2Fh+IoStatusBlock]; IoStatusBlock
0x18000475d  mov     [rsp+0E0h+CreateOptions], r14d; CreateOptions
0x180004762  lea     r8, [rbp+2Fh+ObjectAttributes]; ObjectAttributes
0x180004766  mov     [rsp+0E0h+CreateDisposition], 1; CreateDisposition
0x18000476e  xorps   xmm0, xmm0
0x180004771  mov     [rsp+0E0h+ShareAccess], r15d; ShareAccess
0x180004776  mov     edx, edi; DesiredAccess
0x180004778  mov     [rsp+0E0h+FileAttributes], 80h; FileAttributes
0x180004780  mov     rcx, rsi; FileHandle
0x180004783  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x18000478c  mov     [rbp+2Fh+ObjectAttributes.Length], 30h ; '0'
0x180004793  mov     [rbp+2Fh+ObjectAttributes.RootDirectory], 0
0x18000479b  mov     [rbp+2Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1800047a2  mov     [rbp+2Fh+ObjectAttributes.ObjectName], rax
0x1800047a6  movdqu  xmmword ptr [rbp+2Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800047ab  call    cs:__imp_NtCreateFile
0x1800047b2  nop     dword ptr [rax+rax+00h]
0x1800047b7  mov     ecx, eax; Status
0x1800047b9  mov     ebx, eax
0x1800047bb  call    cs:__imp_RtlNtStatusToDosError
0x1800047c2  nop     dword ptr [rax+rax+00h]
0x1800047c7  cmp     [rbp+2Fh+UnicodeString.Buffer], 0
0x1800047cc  jz      short loc_1800047DE
0x1800047ce  lea     rcx, [rbp+2Fh+UnicodeString]; UnicodeString
0x1800047d2  call    cs:__imp_RtlFreeUnicodeString
0x1800047d9  nop     dword ptr [rax+rax+00h]
0x1800047de  test    ebx, ebx
0x1800047e0  jns     short loc_1800047E9
0x1800047e2  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800047e9  mov     eax, ebx
0x1800047eb  add     rsp, 0B8h
0x1800047f2  pop     r15
0x1800047f4  pop     r14
0x1800047f6  pop     rdi
0x1800047f7  pop     rsi
0x1800047f8  pop     rbx
0x1800047f9  pop     rbp
0x1800047fa  retn
```
