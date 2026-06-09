# FatFastIoCheckIfPossible

- ea: `0x140038f30`
- end: `0x140039062`
- name: `FatFastIoCheckIfPossible`
- size: `306`
- prototype: `__int64 __usercall@<rax>(PVOID FileObject@<rcx>, PLARGE_INTEGER StartingByte@<rdx>, ULONG Key, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140001d4c`
- `0x140038f30`
- `0x14003d880`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x140038f8d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140039019`
- `ntoskrnl!IoGetCurrentProcess` at `0x140038f8d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140039019`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x140038fb9`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x140038fb9`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x140039041`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x140039041`

## pseudocode

```c
bool __fastcall FatFastIoCheckIfPossible(
        struct _FILE_OBJECT *FileObject,
        PLARGE_INTEGER StartingByte,
        unsigned int a3,
        __int64 a4,
        ULONG Key,
        char a6)
{
  PEPROCESS ProcessId; // rax
  __int64 v11; // rbx
  PEPROCESS CurrentProcess; // rax
  __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  union _LARGE_INTEGER Length; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+48h] [rbp-8h] BYREF

  v15 = 0;
  v13 = 0;
  v16 = 0;
  Length.QuadPart = 0;
  if ( (unsigned int)FatDecodeFileObject(FileObject, &v15, &v13, &v16) == 2 )
  {
    Length.QuadPart = a3;
    if ( a6 )
    {
      ProcessId = IoGetCurrentProcess();
      if ( FsRtlFastCheckLockForRead((PFILE_LOCK)(v13 + 320), StartingByte, &Length, Key, FileObject, ProcessId) )
        return 1;
    }
    else
    {
      v11 = v13;
      if ( ((*(_DWORD *)(v13 + 192) & 0x8000) == 0
         || *(_QWORD *)(v13 + 24) >= a3 + StartingByte->QuadPart + *(unsigned int *)(v13 + 132)
         && (unsigned __int8)FatIsIoRangeValid(a3, StartingByte->QuadPart, a3, *(unsigned int *)(v13 + 132)))
        && (*(_DWORD *)(v15 + 200) & 0x4000) == 0 )
      {
        CurrentProcess = IoGetCurrentProcess();
        return FsRtlFastCheckLockForWrite(
                 (PFILE_LOCK)(v11 + 320),
                 StartingByte,
                 &Length,
                 Key,
                 FileObject,
                 CurrentProcess) != 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140038f30  push    rbp
0x140038f32  push    rbx
0x140038f33  push    rsi
0x140038f34  push    rdi
0x140038f35  push    r14
0x140038f37  mov     rbp, rsp
0x140038f3a  sub     rsp, 50h
0x140038f3e  mov     esi, r8d
0x140038f41  lea     r9, [rbp+var_8]
0x140038f45  mov     rdi, rdx
0x140038f48  mov     [rbp+var_10], 0
0x140038f50  lea     r8, [rbp+var_20]
0x140038f54  mov     [rbp+var_20], 0
0x140038f5c  lea     rdx, [rbp+var_10]
0x140038f60  mov     [rbp+var_8], 0
0x140038f68  mov     r14, rcx
0x140038f6b  mov     qword ptr [rbp+Length], 0
0x140038f73  call    FatDecodeFileObject
0x140038f78  cmp     eax, 2
0x140038f7b  jnz     loc_140039054
0x140038f81  cmp     [rbp+arg_28], 0
0x140038f85  mov     ecx, esi
0x140038f87  mov     qword ptr [rbp+Length], rcx
0x140038f8b  jz      short loc_140038FD4
0x140038f8d  call    cs:__imp_IoGetCurrentProcess
0x140038f94  nop     dword ptr [rax+rax+00h]
0x140038f99  mov     rcx, [rbp+var_20]
0x140038f9d  lea     r8, [rbp+Length]; Length
0x140038fa1  mov     r9d, [rbp+Key]; Key
0x140038fa5  add     rcx, 140h; FileLock
0x140038fac  mov     [rsp+50h+ProcessId], rax; ProcessId
0x140038fb1  mov     rdx, rdi; StartingByte
0x140038fb4  mov     [rsp+50h+FileObject], r14; FileObject
0x140038fb9  call    cs:__imp_FsRtlFastCheckLockForRead
0x140038fc0  nop     dword ptr [rax+rax+00h]
0x140038fc5  test    al, al
0x140038fc7  jz      loc_140039054
0x140038fcd  mov     al, 1
0x140038fcf  jmp     loc_140039056
0x140038fd4  mov     rbx, [rbp+var_20]
0x140038fd8  test    dword ptr [rbx+0C0h], 8000h
0x140038fe2  jz      short loc_140039009
0x140038fe4  mov     r9d, [rbx+84h]
0x140038feb  mov     eax, r9d
0x140038fee  add     rax, [rdi]
0x140038ff1  add     rax, rcx
0x140038ff4  cmp     [rbx+18h], rax
0x140038ff8  jl      short loc_140039054
0x140038ffa  mov     rdx, [rdi]
0x140038ffd  mov     r8d, esi
0x140039000  call    FatIsIoRangeValid
0x140039005  test    al, al
0x140039007  jz      short loc_140039054
0x140039009  mov     rax, [rbp+var_10]
0x14003900d  mov     ecx, [rax+0C8h]
0x140039013  bt      ecx, 0Eh
0x140039017  jb      short loc_140039054
0x140039019  call    cs:__imp_IoGetCurrentProcess
0x140039020  nop     dword ptr [rax+rax+00h]
0x140039025  mov     r9d, [rbp+Key]; Key
0x140039029  lea     rcx, [rbx+140h]; FileLock
0x140039030  mov     [rsp+50h+ProcessId], rax; ProcessId
0x140039035  lea     r8, [rbp+Length]; Length
0x140039039  mov     rdx, rdi; StartingByte
0x14003903c  mov     [rsp+50h+FileObject], r14; FileObject
0x140039041  call    cs:__imp_FsRtlFastCheckLockForWrite
0x140039048  nop     dword ptr [rax+rax+00h]
0x14003904d  test    al, al
0x14003904f  setnz   al
0x140039052  jmp     short loc_140039056
0x140039054  xor     al, al
0x140039056  add     rsp, 50h
0x14003905a  pop     r14
0x14003905c  pop     rdi
0x14003905d  pop     rsi
0x14003905e  pop     rbx
0x14003905f  pop     rbp
0x140039060  retn
```
