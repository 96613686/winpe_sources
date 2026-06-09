# RxFastIoCheckIfPossible

- ea: `0x140069280`
- end: `0x1400694d3`
- name: `RxFastIoCheckIfPossible`
- size: `595`
- prototype: `__int64 __usercall@<rax>(PVOID FileObject@<rcx>, PLARGE_INTEGER StartingByte@<rdx>, ULONG Key, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x14001d208`
- `0x140025d00`
- `0x140069280`

## import_xrefs

- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x14006944f`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x14006944f`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x140069386`
- `ntoskrnl!FsRtlFastCheckLockForRead` at `0x140069386`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006935c`
- `ntoskrnl!IoGetCurrentProcess` at `0x140069425`
- `ntoskrnl!IoGetCurrentProcess` at `0x14006935c`
- `ntoskrnl!IoGetCurrentProcess` at `0x140069425`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400692f9`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x1400692f9`

## string_xrefs

- `0x140069333`: `notreadC`
- `0x1400693ee`: `notwriteC`
- `0x140069406`: `srvopen orphaned`
- `0x14006949c`: `readlock`
- `0x140069463`: `writelock`

## pseudocode

```c
bool __fastcall RxFastIoCheckIfPossible(
        struct _FILE_OBJECT *FileObject,
        PLARGE_INTEGER StartingByte,
        unsigned int a3,
        __int64 a4,
        ULONG Key,
        char a6)
{
  LARGE_INTEGER v6; // rbp
  char *FsContext; // rbx
  _QWORD *FsContext2; // rsi
  __int64 v11; // rsi
  int v12; // ecx
  int v13; // eax
  const char *v14; // rcx
  PEPROCESS ProcessId; // rax
  __int64 (__fastcall *v17)(_QWORD, __int64); // rax
  int v18; // eax
  int v19; // ecx
  PEPROCESS CurrentProcess; // rax
  LARGE_INTEGER Length; // [rsp+50h] [rbp+8h] BYREF

  v6.QuadPart = a3;
  Length.QuadPart = 0;
  if ( FileObject )
  {
    FsContext = (char *)FileObject->FsContext;
    FsContext2 = FileObject->FsContext2;
  }
  else
  {
    FsContext = 0;
    FsContext2 = 0;
  }
  if ( *(_WORD *)FsContext == 0xEC22 )
  {
    if ( FileObject->DeletePending )
    {
      v14 = "delpend";
    }
    else
    {
      v11 = FsContext2[4];
      v12 = *(_DWORD *)(v11 + 72);
      if ( (v12 & 0x400) != 0 )
      {
        v14 = "srvopen orphaned";
      }
      else if ( (*((_DWORD *)FsContext + 39) & 0x80u) != 0 )
      {
        v14 = "orphaned";
      }
      else if ( (v12 & 0x30) != 0 )
      {
        v14 = "ren/del";
      }
      else if ( FsRtlOplockIsFastIoPossible((POPLOCK)FsContext + 11) )
      {
        Length = v6;
        v13 = *((_DWORD *)FsContext + 41);
        if ( a6 )
        {
          if ( (v13 & 1) != 0 && (*((_DWORD *)FsContext + 40) & 0x2000000) != 0 && (*(_DWORD *)(v11 + 72) & 1) == 0 )
          {
            ProcessId = IoGetCurrentProcess();
            if ( FsRtlFastCheckLockForRead(
                   (PFILE_LOCK)(FsContext + 536),
                   StartingByte,
                   &Length,
                   Key,
                   FileObject,
                   ProcessId) )
            {
              goto LABEL_17;
            }
            v14 = "readlock";
          }
          else
          {
            v14 = "notreadC";
          }
        }
        else if ( (v13 & 2) != 0 && (*((_DWORD *)FsContext + 40) & 0x8000000) != 0 && (*(_DWORD *)(v11 + 72) & 2) == 0 )
        {
          CurrentProcess = IoGetCurrentProcess();
          if ( FsRtlFastCheckLockForWrite(
                 (PFILE_LOCK)(FsContext + 536),
                 StartingByte,
                 &Length,
                 Key,
                 FileObject,
                 CurrentProcess) )
          {
LABEL_17:
            v17 = *(__int64 (__fastcall **)(_QWORD, __int64))(*((_QWORD *)FsContext + 49) + 592LL);
            if ( !v17 )
              return 1;
            v18 = v17(0, v11);
            v19 = 0;
            if ( v18 != -1073741822 )
              v19 = v18;
            return v19 >= 0;
          }
          v14 = "writelock";
        }
        else
        {
          v14 = "notwriteC";
        }
      }
      else
      {
        v14 = "oplock";
      }
    }
  }
  else
  {
    v14 = "notfile";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qs(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)WPP_GLOBAL_Control, a3, (_DWORD)FileObject, (__int64)v14);
  }
  return 0;
}

```

## disassembly

```asm
0x140069280  mov     [rsp+arg_8], rbx
0x140069285  mov     [rsp+arg_10], rbp
0x14006928a  push    rsi
0x14006928b  push    rdi
0x14006928c  push    r14
0x14006928e  sub     rsp, 30h
0x140069292  mov     ebp, r8d
0x140069295  mov     r14, rdx
0x140069298  mov     qword ptr [rsp+48h+Length], 0
0x1400692a1  mov     rdi, rcx
0x1400692a4  test    rcx, rcx
0x1400692a7  jz      loc_140069493
0x1400692ad  mov     rbx, [rcx+18h]
0x1400692b1  mov     rsi, [rcx+20h]
0x1400692b5  mov     eax, 0EC22h
0x1400692ba  cmp     [rbx], ax
0x1400692bd  jnz     loc_1400693FA
0x1400692c3  cmp     byte ptr [rcx+49h], 0
0x1400692c7  jnz     loc_14006946F
0x1400692cd  mov     rsi, [rsi+20h]
0x1400692d1  mov     ecx, [rsi+48h]
0x1400692d4  bt      ecx, 0Ah
0x1400692d8  jb      loc_140069406
0x1400692de  mov     eax, [rbx+9Ch]
0x1400692e4  test    al, al
0x1400692e6  js      loc_140069487
0x1400692ec  test    cl, 30h
0x1400692ef  jnz     loc_14006947B
0x1400692f5  lea     rcx, [rbx+58h]; Oplock
0x1400692f9  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x140069300  nop     dword ptr [rax+rax+00h]
0x140069305  test    al, al
0x140069307  jz      loc_140069412
0x14006930d  cmp     [rsp+48h+arg_28], 0
0x140069312  mov     qword ptr [rsp+48h+Length], rbp
0x140069317  mov     eax, [rbx+0A4h]
0x14006931d  jz      loc_1400693DE
0x140069323  test    al, 1
0x140069325  jz      short loc_140069333
0x140069327  test    dword ptr [rbx+0A0h], 2000000h
0x140069331  jnz     short loc_140069355
0x140069333  lea     rcx, aNotreadc; "notreadC"
0x14006933a  mov     rdx, cs:WPP_GLOBAL_Control
0x140069341  lea     rax, WPP_GLOBAL_Control
0x140069348  cmp     rdx, rax
0x14006934b  jnz     loc_1400694A8
0x140069351  xor     al, al
0x140069353  jmp     short loc_1400693C6
0x140069355  mov     eax, [rsi+48h]
0x140069358  test    al, 1
0x14006935a  jnz     short loc_140069333
0x14006935c  call    cs:__imp_IoGetCurrentProcess
0x140069363  nop     dword ptr [rax+rax+00h]
0x140069368  mov     r9d, [rsp+48h+Key]; Key
0x14006936d  lea     rcx, [rbx+218h]; FileLock
0x140069374  mov     [rsp+48h+ProcessId], rax; ProcessId
0x140069379  lea     r8, [rsp+48h+Length]; Length
0x14006937e  mov     rdx, r14; StartingByte
0x140069381  mov     [rsp+48h+FileObject], rdi; FileObject
0x140069386  call    cs:__imp_FsRtlFastCheckLockForRead
0x14006938d  nop     dword ptr [rax+rax+00h]
0x140069392  test    al, al
0x140069394  jz      loc_14006949C
0x14006939a  mov     rax, [rbx+188h]
0x1400693a1  mov     rax, [rax+250h]
0x1400693a8  test    rax, rax
0x1400693ab  jz      short loc_1400693DA
0x1400693ad  mov     rdx, rsi
0x1400693b0  xor     ecx, ecx
0x1400693b2  call    _guard_dispatch_icall
0x1400693b7  xor     ecx, ecx
0x1400693b9  cmp     eax, 0C0000002h
0x1400693be  cmovnz  ecx, eax
0x1400693c1  test    ecx, ecx
0x1400693c3  setns   al
0x1400693c6  mov     rbx, [rsp+48h+arg_8]
0x1400693cb  mov     rbp, [rsp+48h+arg_10]
0x1400693d0  add     rsp, 30h
0x1400693d4  pop     r14
0x1400693d6  pop     rdi
0x1400693d7  pop     rsi
0x1400693d8  retn
0x1400693da  mov     al, 1
0x1400693dc  jmp     short loc_1400693C6
0x1400693de  test    al, 2
0x1400693e0  jz      short loc_1400693EE
0x1400693e2  test    dword ptr [rbx+0A0h], 8000000h
0x1400693ec  jnz     short loc_14006941E
0x1400693ee  lea     rcx, aNotwritec; "notwriteC"
0x1400693f5  jmp     loc_14006933A
0x1400693fa  lea     rcx, aNotfile; "notfile"
0x140069401  jmp     loc_14006933A
0x140069406  lea     rcx, aSrvopenOrphane; "srvopen orphaned"
0x14006940d  jmp     loc_14006933A
0x140069412  lea     rcx, aOplock; "oplock"
0x140069419  jmp     loc_14006933A
0x14006941e  mov     eax, [rsi+48h]
0x140069421  test    al, 2
0x140069423  jnz     short loc_1400693EE
0x140069425  call    cs:__imp_IoGetCurrentProcess
0x14006942c  nop     dword ptr [rax+rax+00h]
0x140069431  mov     r9d, [rsp+48h+Key]; Key
0x140069436  lea     rcx, [rbx+218h]; FileLock
0x14006943d  mov     [rsp+48h+ProcessId], rax; ProcessId
0x140069442  lea     r8, [rsp+48h+Length]; Length
0x140069447  mov     rdx, r14; StartingByte
0x14006944a  mov     [rsp+48h+FileObject], rdi; FileObject
0x14006944f  call    cs:__imp_FsRtlFastCheckLockForWrite
0x140069456  nop     dword ptr [rax+rax+00h]
0x14006945b  test    al, al
0x14006945d  jnz     loc_14006939A
0x140069463  lea     rcx, aWritelock; "writelock"
0x14006946a  jmp     loc_14006933A
0x14006946f  lea     rcx, aDelpend; "delpend"
0x140069476  jmp     loc_14006933A
0x14006947b  lea     rcx, aRenDel; "ren/del"
0x140069482  jmp     loc_14006933A
0x140069487  lea     rcx, aOrphaned; "orphaned"
0x14006948e  jmp     loc_14006933A
0x140069493  xor     ebx, ebx
0x140069495  xor     esi, esi
0x140069497  jmp     loc_1400692B5
0x14006949c  lea     rcx, aReadlock; "readlock"
0x1400694a3  jmp     loc_14006933A
0x1400694a8  mov     eax, [rdx+2Ch]
0x1400694ab  test    al, 10h
0x1400694ad  jz      loc_140069351
0x1400694b3  cmp     byte ptr [rdx+29h], 2
0x1400694b7  jb      loc_140069351
0x1400694bd  mov     [rsp+48h+FileObject], rcx
0x1400694c2  mov     r9, rdi
0x1400694c5  mov     rcx, [rdx+18h]
0x1400694c9  call    WPP_SF_qs
0x1400694ce  jmp     loc_140069351
```
