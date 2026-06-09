# CdFastIoCheckIfPossible

- ea: `0x14000bf70`
- end: `0x14000c009`
- name: `CdFastIoCheckIfPossible`
- size: `153`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, PLARGE_INTEGER StartingByte@<rdx>, ULONG Key, char, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14000bf70`

## import_xrefs

- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x14000bfd8`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x14000bfd8`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000bfb2`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000bfb2`

## pseudocode

```c
bool __fastcall CdFastIoCheckIfPossible(
        PFILE_OBJECT FileObject,
        PLARGE_INTEGER StartingByte,
        unsigned int a3,
        __int64 a4,
        ULONG Key,
        char a6,
        _DWORD *a7)
{
  PVOID FsContext; // rbx
  FILE_LOCK *v10; // rbx
  PEPROCESS ProcessId; // rax
  union _LARGE_INTEGER Length; // [rsp+40h] [rbp+8h] BYREF

  if ( ((__int64)FileObject->FsContext2 & 7) == 4 && a6 )
  {
    FsContext = FileObject->FsContext;
    Length.QuadPart = a3;
    if ( *((_QWORD *)FsContext + 59) )
    {
      v10 = (FILE_LOCK *)*((_QWORD *)FsContext + 59);
      ProcessId = IoGetCurrentProcess();
      return FsRtlFastCheckLockForRead(v10, StartingByte, &Length, Key, FileObject, ProcessId) != 0;
    }
  }
  else
  {
    *a7 = -1073741811;
  }
  return 1;
}

```

## disassembly

```asm
0x14000bf70  mov     [rsp+arg_8], rbx
0x14000bf75  mov     [rsp+arg_10], rsi
0x14000bf7a  push    rdi
0x14000bf7b  sub     rsp, 30h
0x14000bf7f  mov     eax, [rcx+20h]
0x14000bf82  mov     rsi, rdx
0x14000bf85  and     al, 7
0x14000bf87  mov     rdi, rcx
0x14000bf8a  cmp     al, 4
0x14000bf8c  jnz     short loc_14000BFEB
0x14000bf8e  cmp     [rsp+38h+arg_28], 0
0x14000bf93  jz      short loc_14000BFEB
0x14000bf95  mov     rbx, [rcx+18h]
0x14000bf99  mov     eax, r8d
0x14000bf9c  mov     qword ptr [rsp+38h+Length], rax
0x14000bfa1  cmp     qword ptr [rbx+1D8h], 0
0x14000bfa9  jz      short loc_14000BFF6
0x14000bfab  mov     rbx, [rbx+1D8h]
0x14000bfb2  call    cs:__imp_IoGetCurrentProcess
0x14000bfb9  nop     dword ptr [rax+rax+00h]
0x14000bfbe  mov     r9d, [rsp+38h+Key]; Key
0x14000bfc3  lea     r8, [rsp+38h+Length]; Length
0x14000bfc8  mov     [rsp+38h+ProcessId], rax; ProcessId
0x14000bfcd  mov     rdx, rsi; StartingByte
0x14000bfd0  mov     rcx, rbx; FileLock
0x14000bfd3  mov     [rsp+38h+FileObject], rdi; FileObject
0x14000bfd8  call    cs:__imp_FsRtlFastCheckLockForRead
0x14000bfdf  nop     dword ptr [rax+rax+00h]
0x14000bfe4  test    al, al
0x14000bfe6  setnz   al
0x14000bfe9  jmp     short loc_14000BFF8
0x14000bfeb  mov     rax, [rsp+38h+arg_30]
0x14000bff0  mov     dword ptr [rax], 0C000000Dh
0x14000bff6  mov     al, 1
0x14000bff8  mov     rbx, [rsp+38h+arg_8]
0x14000bffd  mov     rsi, [rsp+38h+arg_10]
0x14000c002  add     rsp, 30h
0x14000c006  pop     rdi
0x14000c007  retn
```
