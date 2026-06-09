# ConsoleCreateStandardIoObjects

- ea: `0x180107ea8`
- end: `0x1801080ab`
- name: `ConsoleCreateStandardIoObjects`
- size: `515`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180065ef0`
- `0x1800674f4`

## callees

- `0x180107ea8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180107ef8`
- `ntdll!RtlInitUnicodeString` at `0x180107fa0`
- `ntdll!RtlInitUnicodeString` at `0x180107ef8`
- `ntdll!RtlInitUnicodeString` at `0x180107fa0`
- `ntdll!NtCreateFile` at `0x180107f61`
- `ntdll!NtCreateFile` at `0x180108009`
- `ntdll!NtCreateFile` at `0x180107f61`
- `ntdll!NtCreateFile` at `0x180108009`
- `ntdll!NtClose` at `0x18010801f`
- `ntdll!NtClose` at `0x180108096`
- `ntdll!NtClose` at `0x18010801f`
- `ntdll!NtClose` at `0x180108096`
- `ntdll!NtDuplicateObject` at `0x180108060`
- `ntdll!NtDuplicateObject` at `0x180108060`

## pseudocode

```c
NTSTATUS __fastcall ConsoleCreateStandardIoObjects(__int64 a1)
{
  void *v1; // rbx
  NTSTATUS result; // eax
  void *v4; // rbx
  NTSTATUS v5; // ebx
  HANDLE v6; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+17h] BYREF
  HANDLE FileHandle; // [rsp+D0h] [rbp+67h] BYREF
  HANDLE SourceHandle; // [rsp+D8h] [rbp+6Fh] BYREF
  HANDLE TargetHandle; // [rsp+E0h] [rbp+77h] BYREF

  v1 = *(void **)(a1 + 8);
  TargetHandle = 0;
  FileHandle = 0;
  SourceHandle = 0;
  IoStatusBlock = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\Input");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v1;
  ObjectAttributes.Attributes = 66;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtCreateFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 2u, 0x20u, 0, 0);
  if ( result >= 0 )
  {
    v4 = *(void **)(a1 + 8);
    IoStatusBlock = 0;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, 44);
    RtlInitUnicodeString(&DestinationString, L"\\Output");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v4;
    ObjectAttributes.Attributes = 66;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = NtCreateFile(&SourceHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 2u, 0x20u, 0, 0);
    if ( v5 >= 0 )
    {
      v5 = NtDuplicateObject(
             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
             SourceHandle,
             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
             &TargetHandle,
             0,
             0,
             6u);
      if ( v5 >= 0 )
      {
        *(_QWORD *)(a1 + 24) = FileHandle;
        *(_QWORD *)(a1 + 32) = SourceHandle;
        *(_QWORD *)(a1 + 40) = TargetHandle;
        *(_DWORD *)a1 = 7;
        return v5;
      }
      NtClose(FileHandle);
      v6 = SourceHandle;
    }
    else
    {
      v6 = FileHandle;
    }
    NtClose(v6);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180107ea8  mov     [rsp-8+arg_18], rbx
0x180107ead  push    rbp
0x180107eae  push    rsi
0x180107eaf  push    rdi
0x180107eb0  lea     rbp, [rsp-47h]
0x180107eb5  sub     rsp, 0B0h
0x180107ebc  mov     rbx, [rcx+8]
0x180107ec0  lea     rdx, aInput; "\\Input"
0x180107ec7  xorps   xmm0, xmm0
0x180107eca  xor     esi, esi
0x180107ecc  mov     rdi, rcx
0x180107ecf  mov     [rbp+57h+TargetHandle], rsi
0x180107ed3  xorps   xmm1, xmm1
0x180107ed6  mov     [rbp+57h+FileHandle], rsi
0x180107eda  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180107ede  xor     eax, eax
0x180107ee0  mov     [rbp+57h+SourceHandle], rsi
0x180107ee4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180107ee8  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180107eec  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180107ef0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180107ef4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180107ef8  call    cs:__imp_RtlInitUnicodeString
0x180107eff  nop     dword ptr [rax+rax+00h]
0x180107f04  mov     [rsp+0C0h+EaLength], esi; EaLength
0x180107f08  lea     rax, [rbp+57h+DestinationString]
0x180107f0c  mov     [rsp+0C0h+EaBuffer], rsi; EaBuffer
0x180107f11  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180107f15  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x180107f1d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180107f21  mov     [rsp+0C0h+CreateDisposition], 2; CreateDisposition
0x180107f29  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180107f2d  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x180107f35  xorps   xmm0, xmm0
0x180107f38  mov     [rsp+0C0h+FileAttributes], esi; FileAttributes
0x180107f3c  mov     edx, 12019Fh; DesiredAccess
0x180107f41  mov     [rsp+0C0h+AllocationSize], rsi; AllocationSize
0x180107f46  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180107f4d  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180107f51  mov     [rbp+57h+ObjectAttributes.Attributes], 42h ; 'B'
0x180107f58  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180107f5c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180107f61  call    cs:__imp_NtCreateFile
0x180107f68  nop     dword ptr [rax+rax+00h]
0x180107f6d  test    eax, eax
0x180107f6f  js      loc_18010802D
0x180107f75  mov     rbx, [rdi+8]
0x180107f79  lea     rdx, aOutput; "\\Output"
0x180107f80  xorps   xmm0, xmm0
0x180107f83  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180107f87  xorps   xmm1, xmm1
0x180107f8a  xor     eax, eax
0x180107f8c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180107f90  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180107f94  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180107f98  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180107f9c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180107fa0  call    cs:__imp_RtlInitUnicodeString
0x180107fa7  nop     dword ptr [rax+rax+00h]
0x180107fac  mov     [rsp+0C0h+EaLength], esi; EaLength
0x180107fb0  lea     rax, [rbp+57h+DestinationString]
0x180107fb4  mov     [rsp+0C0h+EaBuffer], rsi; EaBuffer
0x180107fb9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180107fbd  mov     [rsp+0C0h+CreateOptions], 20h ; ' '; CreateOptions
0x180107fc5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180107fc9  mov     [rsp+0C0h+CreateDisposition], 2; CreateDisposition
0x180107fd1  lea     rcx, [rbp+57h+SourceHandle]; FileHandle
0x180107fd5  mov     [rsp+0C0h+ShareAccess], 7; ShareAccess
0x180107fdd  xorps   xmm0, xmm0
0x180107fe0  mov     [rsp+0C0h+FileAttributes], esi; FileAttributes
0x180107fe4  mov     edx, 12019Fh; DesiredAccess
0x180107fe9  mov     [rsp+0C0h+AllocationSize], rsi; AllocationSize
0x180107fee  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180107ff5  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180107ff9  mov     [rbp+57h+ObjectAttributes.Attributes], 42h ; 'B'
0x180108000  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180108004  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180108009  call    cs:__imp_NtCreateFile
0x180108010  nop     dword ptr [rax+rax+00h]
0x180108015  mov     ebx, eax
0x180108017  test    eax, eax
0x180108019  jns     short loc_180108041
0x18010801b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18010801f  call    cs:__imp_NtClose
0x180108026  nop     dword ptr [rax+rax+00h]
0x18010802b  mov     eax, ebx
0x18010802d  mov     rbx, [rsp+0C0h+arg_18]
0x180108035  add     rsp, 0B0h
0x18010803c  pop     rdi
0x18010803d  pop     rsi
0x18010803e  pop     rbp
0x18010803f  retn
0x180108041  mov     rdx, [rbp+57h+SourceHandle]; SourceHandle
0x180108045  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x180108049  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x18010804d  mov     [rsp+0C0h+ShareAccess], 6; Options
0x180108055  mov     r8, rcx; TargetProcessHandle
0x180108058  mov     [rsp+0C0h+FileAttributes], esi; HandleAttributes
0x18010805c  mov     dword ptr [rsp+0C0h+AllocationSize], esi; DesiredAccess
0x180108060  call    cs:__imp_NtDuplicateObject
0x180108067  nop     dword ptr [rax+rax+00h]
0x18010806c  mov     ebx, eax
0x18010806e  test    eax, eax
0x180108070  js      short loc_180108092
0x180108072  mov     rax, [rbp+57h+FileHandle]
0x180108076  mov     [rdi+18h], rax
0x18010807a  mov     rax, [rbp+57h+SourceHandle]
0x18010807e  mov     [rdi+20h], rax
0x180108082  mov     rax, [rbp+57h+TargetHandle]
0x180108086  mov     [rdi+28h], rax
0x18010808a  mov     dword ptr [rdi], 7
0x180108090  jmp     short loc_18010802B
0x180108092  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180108096  call    cs:__imp_NtClose
0x18010809d  nop     dword ptr [rax+rax+00h]
0x1801080a2  mov     rcx, [rbp+57h+SourceHandle]
0x1801080a6  jmp     loc_18010801F
```
