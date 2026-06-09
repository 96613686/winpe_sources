# CLogFile::ScheduleAWrite(uchar const *,ulong)

- ea: `0x18009decc`
- end: `0x18009e030`
- name: `?ScheduleAWrite@CLogFile@@AEAA_NPEBEK@Z`
- size: `356`
- prototype: `bool(CLogFile *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009dba0`
- `0x18009de10`

## callees

- `0x18009decc`
- `0x18009e038`
- `0x18009e0fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009df9b`
- `KERNEL32!GetLastError` at `0x18009df9b`
- `KERNEL32!ReleaseMutex` at `0x18009dfc4`
- `KERNEL32!ReleaseMutex` at `0x18009dfc4`
- `KERNEL32!WaitForSingleObject` at `0x18009df38`
- `KERNEL32!WaitForSingleObject` at `0x18009df38`
- `KERNEL32!LocalFree` at `0x18009dff5`
- `KERNEL32!LocalFree` at `0x18009dff5`
- `KERNEL32!SetFilePointer` at `0x18009df60`
- `KERNEL32!SetFilePointer` at `0x18009df60`
- `KERNEL32!WriteFile` at `0x18009df91`
- `KERNEL32!WriteFile` at `0x18009df91`
- `KERNEL32!VirtualFree` at `0x18009dfec`
- `KERNEL32!VirtualFree` at `0x18009e023`
- `KERNEL32!VirtualFree` at `0x18009dfec`
- `KERNEL32!VirtualFree` at `0x18009e023`

## pseudocode

```c
char __fastcall CLogFile::ScheduleAWrite(CLogFile *this, unsigned __int8 *a2, DWORD a3)
{
  char v6; // r14
  struct _OVERLAPPED *lpOverlapped; // rdi
  char v8; // bl
  DWORD v9; // eax
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF
  __int64 DistanceToMoveHigh; // [rsp+78h] [rbp+20h] BYREF

  if ( !*((_QWORD *)this + 10) || !a2 )
    return 0;
  NumberOfBytesWritten = 0;
  v6 = 0;
  DistanceToMoveHigh = 0;
  lpOverlapped = (struct _OVERLAPPED *)CLogFile::PurgeCompletedAsyncOps(this);
  if ( !lpOverlapped )
    goto LABEL_18;
  v8 = 1;
  if ( (int)qword_180309748 < 3 )
  {
    if ( WaitForSingleObject(hMutex, 0xBB8u) )
    {
      LODWORD(qword_180309748) = qword_180309748 + 1;
      HIDWORD(qword_180309748) = 1;
      goto LABEL_18;
    }
    v6 = 1;
    LODWORD(qword_180309748) = 0;
  }
  v9 = SetFilePointer(*((HANDLE *)this + 10), 0, (PLONG)&DistanceToMoveHigh + 1, 2u);
  LODWORD(DistanceToMoveHigh) = v9;
  if ( __PAIR64__(HIDWORD(DistanceToMoveHigh), v9) == 0xFFFFFFFF )
    goto LABEL_18;
  lpOverlapped->Offset = v9;
  lpOverlapped->OffsetHigh = HIDWORD(DistanceToMoveHigh);
  if ( WriteFile(*((HANDLE *)this + 10), a2, a3, &NumberOfBytesWritten, lpOverlapped) )
  {
    VirtualFree(a2, 0, 0x8000u);
LABEL_16:
    LocalFree(lpOverlapped);
    goto LABEL_11;
  }
  if ( GetLastError() != 997 )
  {
LABEL_18:
    v8 = 0;
    VirtualFree(a2, 0, 0x8000u);
    if ( !lpOverlapped )
      goto LABEL_11;
    goto LABEL_16;
  }
  lpOverlapped[1].Internal = (ULONG_PTR)a2;
  Queue<AWRITEDATA *>::Add((char *)this + 40, lpOverlapped);
LABEL_11:
  if ( v6 )
    ReleaseMutex(hMutex);
  return v8;
}

```

## disassembly

```asm
0x18009decc  mov     [rsp+arg_8], rbx
0x18009ded1  push    rbp
0x18009ded2  push    rsi
0x18009ded3  push    rdi
0x18009ded4  push    r14
0x18009ded6  push    r15
0x18009ded8  sub     rsp, 30h
0x18009dedc  cmp     qword ptr [rcx+50h], 0
0x18009dee1  mov     r15d, r8d
0x18009dee4  mov     rsi, rdx
0x18009dee7  mov     rbp, rcx
0x18009deea  jz      loc_18009DFDD
0x18009def0  test    rdx, rdx
0x18009def3  jz      loc_18009DFDD
0x18009def9  mov     [rsp+58h+NumberOfBytesWritten], 0
0x18009df01  xor     r14b, r14b
0x18009df04  mov     [rsp+58h+DistanceToMoveHigh], 0
0x18009df0d  call    ?PurgeCompletedAsyncOps@CLogFile@@AEAAPEAUAWRITEDATA@@XZ; CLogFile::PurgeCompletedAsyncOps(void)
0x18009df12  mov     rdi, rax
0x18009df15  test    rax, rax
0x18009df18  jz      loc_18009E016
0x18009df1e  cmp     dword ptr cs:qword_180309748, 3
0x18009df25  mov     ebx, 1
0x18009df2a  jge     short loc_18009DF4F
0x18009df2c  mov     rcx, cs:hMutex; hHandle
0x18009df33  mov     edx, 0BB8h; dwMilliseconds
0x18009df38  call    cs:__imp_WaitForSingleObject
0x18009df3e  test    eax, eax
0x18009df40  jnz     loc_18009DFFD
0x18009df46  mov     r14b, bl
0x18009df49  mov     dword ptr cs:qword_180309748, eax
0x18009df4f  mov     rcx, [rbp+50h]; hFile
0x18009df53  lea     r8, [rsp+58h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18009df58  mov     r9d, 2; dwMoveMethod
0x18009df5e  xor     edx, edx; lDistanceToMove
0x18009df60  call    cs:__imp_SetFilePointer
0x18009df66  mov     dword ptr [rsp+58h+DistanceToMoveHigh], eax
0x18009df6a  cmp     eax, 0FFFFFFFFh
0x18009df6d  jz      loc_18009E00B
0x18009df73  mov     [rdi+10h], eax
0x18009df76  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18009df7b  mov     eax, dword ptr [rsp+58h+DistanceToMoveHigh+4]
0x18009df7f  mov     r8d, r15d; nNumberOfBytesToWrite
0x18009df82  mov     [rdi+14h], eax
0x18009df85  mov     rdx, rsi; lpBuffer
0x18009df88  mov     rcx, [rbp+50h]; hFile
0x18009df8c  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x18009df91  call    cs:__imp_WriteFile
0x18009df97  test    eax, eax
0x18009df99  jnz     short loc_18009DFE1
0x18009df9b  call    cs:__imp_GetLastError
0x18009dfa1  cmp     eax, 3E5h
0x18009dfa6  jnz     short loc_18009E016
0x18009dfa8  lea     rcx, [rbp+28h]
0x18009dfac  mov     [rdi+20h], rsi
0x18009dfb0  mov     rdx, rdi
0x18009dfb3  call    ?Add@?$Queue@PEAUAWRITEDATA@@@@QEAA_NPEAUAWRITEDATA@@@Z; Queue<AWRITEDATA *>::Add(AWRITEDATA *)
0x18009dfb8  test    r14b, r14b
0x18009dfbb  jz      short loc_18009DFCA
0x18009dfbd  mov     rcx, cs:hMutex; hMutex
0x18009dfc4  call    cs:__imp_ReleaseMutex
0x18009dfca  mov     al, bl
0x18009dfcc  mov     rbx, [rsp+58h+arg_8]
0x18009dfd1  add     rsp, 30h
0x18009dfd5  pop     r15
0x18009dfd7  pop     r14
0x18009dfd9  pop     rdi
0x18009dfda  pop     rsi
0x18009dfdb  pop     rbp
0x18009dfdc  retn
0x18009dfdd  xor     al, al
0x18009dfdf  jmp     short loc_18009DFCC
0x18009dfe1  xor     edx, edx; dwSize
0x18009dfe3  mov     r8d, 8000h; dwFreeType
0x18009dfe9  mov     rcx, rsi; lpAddress
0x18009dfec  call    cs:__imp_VirtualFree
0x18009dff2  mov     rcx, rdi; hMem
0x18009dff5  call    cs:__imp_LocalFree
0x18009dffb  jmp     short loc_18009DFB8
0x18009dffd  add     dword ptr cs:qword_180309748, ebx
0x18009e003  mov     dword ptr cs:qword_180309748+4, ebx
0x18009e009  jmp     short loc_18009E016
0x18009e00b  cmp     dword ptr [rsp+58h+DistanceToMoveHigh+4], 0
0x18009e010  jnz     loc_18009DF73
0x18009e016  xor     edx, edx; dwSize
0x18009e018  mov     r8d, 8000h; dwFreeType
0x18009e01e  mov     rcx, rsi; lpAddress
0x18009e021  xor     bl, bl
0x18009e023  call    cs:__imp_VirtualFree
0x18009e029  test    rdi, rdi
0x18009e02c  jz      short loc_18009DFB8
0x18009e02e  jmp     short loc_18009DFF2
```
