# RefsFastIoCheckIfPossibleInternal

- ea: `0x1c01c1b80`
- end: `0x1c01c1df2`
- name: `RefsFastIoCheckIfPossibleInternal`
- size: `626`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1c01bdb10`
- `0x1c01bdf74`
- `0x1c01be5a0`
- `0x1c01c1aa0`

## callees

- `0x1c0091864`
- `0x1c00a097c`
- `0x1c00b37c0`
- `0x1c01c1b80`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1c01c1cbb`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01c1cbb`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01c1ced`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01c1ced`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c01c1bf2`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c01c1c6a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c01c1bf2`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c01c1c6a`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x1c01c1c9f`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x1c01c1c9f`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x1c01c1c22`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x1c01c1c22`

## pseudocode

```c
char __fastcall RefsFastIoCheckIfPossibleInternal(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        union _LARGE_INTEGER *a3,
        unsigned int a4,
        ULONG Key,
        char a6)
{
  char v8; // bl
  _BYTE *FsContext2; // rax
  char *FsContext; // rdi
  __int64 v12; // r13
  PEPROCESS ProcessId; // rax
  BOOLEAN v14; // al
  int v15; // esi
  union _LARGE_INTEGER v16; // r12
  union _LARGE_INTEGER v17; // r14
  PEPROCESS CurrentProcess; // rax
  int v19; // r15d
  __int64 v20; // rax
  bool v21; // zf
  int v22; // eax
  LONGLONG v23; // [rsp+38h] [rbp-40h]
  union _LARGE_INTEGER Length; // [rsp+88h] [rbp+10h] BYREF
  PLARGE_INTEGER StartingByte; // [rsp+90h] [rbp+18h]
  unsigned int v27; // [rsp+98h] [rbp+20h]

  v27 = a4;
  StartingByte = a3;
  v8 = 0;
  FsContext2 = a2->FsContext2;
  if ( FsContext2 && FsContext2[80] == 2 )
    FsContext = (char *)a2->FsContext;
  else
    FsContext = 0;
  if ( !FsContext )
    return 0;
  v12 = *((_QWORD *)FsContext + 15);
  Length.QuadPart = a4;
  if ( a6 )
  {
    if ( *((_QWORD *)FsContext + 42) )
    {
      ProcessId = IoGetCurrentProcess();
      v14 = FsRtlFastCheckLockForRead(*((PFILE_LOCK *)FsContext + 42), a3, &Length, Key, a2, ProcessId);
      goto LABEL_32;
    }
    return 1;
  }
  LOBYTE(v15) = 0;
  if ( (*(_DWORD *)(v12 + 4) & 0x20) != 0 )
    return v8;
  if ( (*((_DWORD *)FsContext + 76) & 0x10000) != 0 )
    return v8;
  v16 = *a3;
  v17 = *(union _LARGE_INTEGER *)(FsContext + 32);
  v23 = a3->QuadPart + a4;
  if ( *((_QWORD *)FsContext + 42) )
  {
    CurrentProcess = IoGetCurrentProcess();
    if ( !FsRtlFastCheckLockForWrite(*((PFILE_LOCK *)FsContext + 42), StartingByte, &Length, Key, a2, CurrentProcess) )
      return v8;
  }
  ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v12 + 96) + 8LL));
  v19 = *(_DWORD *)(*(_QWORD *)(v12 + 88) + 4LL) & 0x80000;
  v20 = *(_QWORD *)(v12 + 216);
  if ( v20 )
    v15 = *(_DWORD *)(v20 + 104);
  ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(v12 + 96) + 8LL));
  if ( v19 )
  {
    if ( *((_WORD *)FsContext + 104) )
    {
      if ( v16.QuadPart < v17.QuadPart && (v15 & 0x10) == 0 )
        goto LABEL_27;
      if ( v23 <= v17.QuadPart )
      {
LABEL_28:
        v22 = 1;
LABEL_29:
        if ( !v22 )
          return v8;
        goto LABEL_30;
      }
      v21 = (v15 & 0x20) == 0;
    }
    else
    {
      if ( v16.QuadPart < v17.QuadPart && (v15 & 1) == 0 )
        goto LABEL_27;
      if ( v23 <= v17.QuadPart )
        goto LABEL_28;
      v21 = (v15 & 2) == 0;
    }
    if ( v21 )
    {
LABEL_27:
      v22 = 0;
      goto LABEL_29;
    }
    goto LABEL_28;
  }
LABEL_30:
  if ( !*((_DWORD *)FsContext + 62) )
    return 1;
  v14 = RefsReserveClusters(a1, FsContext, StartingByte->QuadPart, v27);
LABEL_32:
  if ( v14 )
    return 1;
  return v8;
}

```

## disassembly

```asm
0x1c01c1b80  mov     rax, rsp
0x1c01c1b83  mov     [rax+20h], r9d
0x1c01c1b87  mov     [rax+18h], r8
0x1c01c1b8b  mov     [rax+8], rcx
0x1c01c1b8f  push    rbx
0x1c01c1b90  push    rsi
0x1c01c1b91  push    rdi
0x1c01c1b92  push    r12
0x1c01c1b94  push    r13
0x1c01c1b96  push    r14
0x1c01c1b98  push    r15
0x1c01c1b9a  sub     rsp, 40h
0x1c01c1b9e  mov     r14, r8
0x1c01c1ba1  mov     r15, rdx
0x1c01c1ba4  xor     ebx, ebx
0x1c01c1ba6  mov     [rax-48h], bl
0x1c01c1ba9  mov     rax, [rdx+20h]
0x1c01c1bad  test    rax, rax
0x1c01c1bb0  jz      short loc_1C01C1BBE
0x1c01c1bb2  cmp     byte ptr [rax+50h], 2
0x1c01c1bb6  jnz     short loc_1C01C1BBE
0x1c01c1bb8  mov     rdi, [rdx+18h]
0x1c01c1bbc  jmp     short loc_1C01C1BC1
0x1c01c1bbe  mov     rdi, rbx
0x1c01c1bc1  test    rdi, rdi
0x1c01c1bc4  jnz     short loc_1C01C1BCD
0x1c01c1bc6  xor     al, al
0x1c01c1bc8  jmp     loc_1C01C1DE1
0x1c01c1bcd  mov     r13, [rdi+78h]
0x1c01c1bd1  mov     ecx, r9d
0x1c01c1bd4  mov     qword ptr [rsp+78h+Length], rcx
0x1c01c1bdc  cmp     [rsp+78h+arg_28], bl
0x1c01c1be3  jz      short loc_1C01C1C33
0x1c01c1be5  cmp     [rdi+150h], rbx
0x1c01c1bec  jz      loc_1C01C1D73
0x1c01c1bf2  call    cs:__imp_IoGetCurrentProcess
0x1c01c1bf9  nop     dword ptr [rax+rax+00h]
0x1c01c1bfe  mov     [rsp+78h+ProcessId], rax; ProcessId
0x1c01c1c03  mov     [rsp+78h+FileObject], r15; FileObject
0x1c01c1c08  mov     r9d, [rsp+78h+Key]; Key
0x1c01c1c10  lea     r8, [rsp+78h+Length]; Length
0x1c01c1c18  mov     rdx, r14; StartingByte
0x1c01c1c1b  mov     rcx, [rdi+150h]; FileLock
0x1c01c1c22  call    cs:__imp_FsRtlFastCheckLockForRead
0x1c01c1c29  nop     dword ptr [rax+rax+00h]
0x1c01c1c2e  jmp     loc_1C01C1D6F
0x1c01c1c33  mov     esi, ebx
0x1c01c1c35  mov     eax, [r13+4]
0x1c01c1c39  test    al, 20h
0x1c01c1c3b  jnz     loc_1C01C1D79
0x1c01c1c41  test    dword ptr [rdi+130h], 10000h
0x1c01c1c4b  jnz     loc_1C01C1D79
0x1c01c1c51  mov     r12, [r8]
0x1c01c1c54  mov     r14, [rdi+20h]
0x1c01c1c58  lea     rax, [r12+rcx]
0x1c01c1c5c  mov     [rsp+78h+var_40], rax
0x1c01c1c61  cmp     [rdi+150h], rbx
0x1c01c1c68  jz      short loc_1C01C1CB3
0x1c01c1c6a  call    cs:__imp_IoGetCurrentProcess
0x1c01c1c71  nop     dword ptr [rax+rax+00h]
0x1c01c1c76  mov     [rsp+78h+ProcessId], rax; ProcessId
0x1c01c1c7b  mov     [rsp+78h+FileObject], r15; FileObject
0x1c01c1c80  mov     r9d, [rsp+78h+Key]; Key
0x1c01c1c88  lea     r8, [rsp+78h+Length]; Length
0x1c01c1c90  mov     rdx, [rsp+78h+StartingByte]; StartingByte
0x1c01c1c98  mov     rcx, [rdi+150h]; FileLock
0x1c01c1c9f  call    cs:__imp_FsRtlFastCheckLockForWrite
0x1c01c1ca6  nop     dword ptr [rax+rax+00h]
0x1c01c1cab  test    al, al
0x1c01c1cad  jz      loc_1C01C1D79
0x1c01c1cb3  mov     rcx, [r13+60h]
0x1c01c1cb7  add     rcx, 8; FastMutex
0x1c01c1cbb  call    cs:__imp_ExAcquireFastMutex
0x1c01c1cc2  nop     dword ptr [rax+rax+00h]
0x1c01c1cc7  mov     rax, [r13+58h]
0x1c01c1ccb  mov     r15d, [rax+4]
0x1c01c1ccf  and     r15d, 80000h
0x1c01c1cd6  mov     rax, [r13+0D8h]
0x1c01c1cdd  test    rax, rax
0x1c01c1ce0  jz      short loc_1C01C1CE5
0x1c01c1ce2  mov     esi, [rax+68h]
0x1c01c1ce5  mov     rcx, [r13+60h]
0x1c01c1ce9  add     rcx, 8; FastMutex
0x1c01c1ced  call    cs:__imp_ExReleaseFastMutex
0x1c01c1cf4  nop     dword ptr [rax+rax+00h]
0x1c01c1cf9  test    r15d, r15d
0x1c01c1cfc  jz      short loc_1C01C1D44
0x1c01c1cfe  cmp     [rdi+0D0h], bx
0x1c01c1d05  jz      short loc_1C01C1D1F
0x1c01c1d07  cmp     r12, r14
0x1c01c1d0a  jge     short loc_1C01C1D12
0x1c01c1d0c  test    sil, 10h
0x1c01c1d10  jz      short loc_1C01C1D37
0x1c01c1d12  cmp     [rsp+78h+var_40], r14
0x1c01c1d17  jle     short loc_1C01C1D3B
0x1c01c1d19  test    sil, 20h
0x1c01c1d1d  jmp     short loc_1C01C1D35
0x1c01c1d1f  cmp     r12, r14
0x1c01c1d22  jge     short loc_1C01C1D2A
0x1c01c1d24  test    sil, 1
0x1c01c1d28  jz      short loc_1C01C1D37
0x1c01c1d2a  cmp     [rsp+78h+var_40], r14
0x1c01c1d2f  jle     short loc_1C01C1D3B
0x1c01c1d31  test    sil, 2
0x1c01c1d35  jnz     short loc_1C01C1D3B
0x1c01c1d37  mov     eax, ebx
0x1c01c1d39  jmp     short loc_1C01C1D40
0x1c01c1d3b  mov     eax, 1
0x1c01c1d40  test    eax, eax
0x1c01c1d42  jz      short loc_1C01C1D79
0x1c01c1d44  cmp     [rdi+0F8h], ebx
0x1c01c1d4a  jz      short loc_1C01C1D73
0x1c01c1d4c  mov     r9d, [rsp+78h+arg_18]
0x1c01c1d54  mov     rax, [rsp+78h+StartingByte]
0x1c01c1d5c  mov     r8, [rax]
0x1c01c1d5f  mov     rdx, rdi
0x1c01c1d62  mov     rcx, [rsp+78h+arg_0]
0x1c01c1d6a  call    RefsReserveClusters
0x1c01c1d6f  test    al, al
0x1c01c1d71  jz      short loc_1C01C1D79
0x1c01c1d73  mov     bl, 1
0x1c01c1d75  mov     [rsp+78h+var_48], bl
0x1c01c1d79  jmp     short loc_1C01C1DDF
0x1c01c1d7b  mov     rbx, [rsp+78h+arg_0]
0x1c01c1d83  test    rbx, rbx
0x1c01c1d86  jz      short loc_1C01C1D8D
0x1c01c1d88  btr     dword ptr [rbx+4], 8
0x1c01c1d8d  cmp     eax, 0C00001A8h
0x1c01c1d92  jnz     short loc_1C01C1DD7
0x1c01c1d94  mov     rcx, [rbx+18h]
0x1c01c1d98  test    rcx, rcx
0x1c01c1d9b  jz      short loc_1C01C1DBE
0x1c01c1d9d  and     [rsp+78h+var_40], 0
0x1c01c1da3  lea     rdx, [rsp+78h+var_40]
0x1c01c1da8  call    MsTriageGetContext
0x1c01c1dad  mov     rdx, [rsp+78h+var_40]
0x1c01c1db2  test    rdx, rdx
0x1c01c1db5  jz      short loc_1C01C1DD7
0x1c01c1db7  call    RefsDeleteTriageContextInternal
0x1c01c1dbc  jmp     short loc_1C01C1DD7
0x1c01c1dbe  mov     rdx, [rbx+0A0h]
0x1c01c1dc5  test    rdx, rdx
0x1c01c1dc8  jz      short loc_1C01C1DD7
0x1c01c1dca  call    RefsDeleteTriageContextInternal
0x1c01c1dcf  and     qword ptr [rbx+0A0h], 0
0x1c01c1dd7  and     dword ptr [rbx+10h], 0
0x1c01c1ddb  mov     bl, [rsp+78h+var_48]
0x1c01c1ddf  mov     al, bl
0x1c01c1de1  add     rsp, 40h
0x1c01c1de5  pop     r15
0x1c01c1de7  pop     r14
0x1c01c1de9  pop     r13
0x1c01c1deb  pop     r12
0x1c01c1ded  pop     rdi
0x1c01c1dee  pop     rsi
0x1c01c1def  pop     rbx
0x1c01c1df0  retn
```
