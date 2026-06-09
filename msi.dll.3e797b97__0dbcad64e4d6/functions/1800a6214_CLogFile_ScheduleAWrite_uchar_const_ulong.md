# CLogFile::ScheduleAWrite(uchar const *,ulong)

- ea: `0x1800a6214`
- end: `0x1800a63b1`
- name: `?ScheduleAWrite@CLogFile@@AEAA_NPEBEK@Z`
- size: `413`
- prototype: `bool(CLogFile *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800a5f38`
- `0x1800a614c`

## callees

- `0x1800a6214`
- `0x1800a63b8`
- `0x1800a6490`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800a62f5`
- `KERNEL32!GetLastError` at `0x1800a62f5`
- `KERNEL32!ReleaseMutex` at `0x1800a6328`
- `KERNEL32!ReleaseMutex` at `0x1800a6328`
- `KERNEL32!WaitForSingleObject` at `0x1800a6280`
- `KERNEL32!WaitForSingleObject` at `0x1800a6280`
- `KERNEL32!LocalFree` at `0x1800a6366`
- `KERNEL32!LocalFree` at `0x1800a6366`
- `KERNEL32!SetFilePointer` at `0x1800a62ae`
- `KERNEL32!SetFilePointer` at `0x1800a62ae`
- `KERNEL32!WriteFile` at `0x1800a62e5`
- `KERNEL32!WriteFile` at `0x1800a62e5`
- `KERNEL32!VirtualFree` at `0x1800a6357`
- `KERNEL32!VirtualFree` at `0x1800a639a`
- `KERNEL32!VirtualFree` at `0x1800a6357`
- `KERNEL32!VirtualFree` at `0x1800a639a`

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
  if ( (int)qword_1803136F8 < 3 )
  {
    if ( WaitForSingleObject(hMutex, 0xBB8u) )
    {
      LODWORD(qword_1803136F8) = qword_1803136F8 + 1;
      HIDWORD(qword_1803136F8) = 1;
      goto LABEL_18;
    }
    v6 = 1;
    LODWORD(qword_1803136F8) = 0;
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
0x1800a6214  mov     [rsp+arg_8], rbx
0x1800a6219  push    rbp
0x1800a621a  push    rsi
0x1800a621b  push    rdi
0x1800a621c  push    r14
0x1800a621e  push    r15
0x1800a6220  sub     rsp, 30h
0x1800a6224  cmp     qword ptr [rcx+50h], 0
0x1800a6229  mov     r15d, r8d
0x1800a622c  mov     rsi, rdx
0x1800a622f  mov     rbp, rcx
0x1800a6232  jz      loc_1800A6348
0x1800a6238  test    rdx, rdx
0x1800a623b  jz      loc_1800A6348
0x1800a6241  mov     [rsp+58h+NumberOfBytesWritten], 0
0x1800a6249  xor     r14b, r14b
0x1800a624c  mov     [rsp+58h+DistanceToMoveHigh], 0
0x1800a6255  call    ?PurgeCompletedAsyncOps@CLogFile@@AEAAPEAUAWRITEDATA@@XZ; CLogFile::PurgeCompletedAsyncOps(void)
0x1800a625a  mov     rdi, rax
0x1800a625d  test    rax, rax
0x1800a6260  jz      loc_1800A638D
0x1800a6266  cmp     dword ptr cs:qword_1803136F8, 3
0x1800a626d  mov     ebx, 1
0x1800a6272  jge     short loc_1800A629D
0x1800a6274  mov     rcx, cs:hMutex; hHandle
0x1800a627b  mov     edx, 0BB8h; dwMilliseconds
0x1800a6280  call    cs:__imp_WaitForSingleObject
0x1800a6287  nop     dword ptr [rax+rax+00h]
0x1800a628c  test    eax, eax
0x1800a628e  jnz     loc_1800A6374
0x1800a6294  mov     r14b, bl
0x1800a6297  mov     dword ptr cs:qword_1803136F8, eax
0x1800a629d  mov     rcx, [rbp+50h]; hFile
0x1800a62a1  lea     r8, [rsp+58h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x1800a62a6  mov     r9d, 2; dwMoveMethod
0x1800a62ac  xor     edx, edx; lDistanceToMove
0x1800a62ae  call    cs:__imp_SetFilePointer
0x1800a62b5  nop     dword ptr [rax+rax+00h]
0x1800a62ba  mov     dword ptr [rsp+58h+DistanceToMoveHigh], eax
0x1800a62be  cmp     eax, 0FFFFFFFFh
0x1800a62c1  jz      loc_1800A6382
0x1800a62c7  mov     [rdi+10h], eax
0x1800a62ca  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a62cf  mov     eax, dword ptr [rsp+58h+DistanceToMoveHigh+4]
0x1800a62d3  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800a62d6  mov     [rdi+14h], eax
0x1800a62d9  mov     rdx, rsi; lpBuffer
0x1800a62dc  mov     rcx, [rbp+50h]; hFile
0x1800a62e0  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x1800a62e5  call    cs:__imp_WriteFile
0x1800a62ec  nop     dword ptr [rax+rax+00h]
0x1800a62f1  test    eax, eax
0x1800a62f3  jnz     short loc_1800A634C
0x1800a62f5  call    cs:__imp_GetLastError
0x1800a62fc  nop     dword ptr [rax+rax+00h]
0x1800a6301  cmp     eax, 3E5h
0x1800a6306  jnz     loc_1800A638D
0x1800a630c  lea     rcx, [rbp+28h]
0x1800a6310  mov     [rdi+20h], rsi
0x1800a6314  mov     rdx, rdi
0x1800a6317  call    ?Add@?$Queue@PEAUAWRITEDATA@@@@QEAA_NPEAUAWRITEDATA@@@Z; Queue<AWRITEDATA *>::Add(AWRITEDATA *)
0x1800a631c  test    r14b, r14b
0x1800a631f  jz      short loc_1800A6334
0x1800a6321  mov     rcx, cs:hMutex; hMutex
0x1800a6328  call    cs:__imp_ReleaseMutex
0x1800a632f  nop     dword ptr [rax+rax+00h]
0x1800a6334  mov     al, bl
0x1800a6336  mov     rbx, [rsp+58h+arg_8]
0x1800a633b  add     rsp, 30h
0x1800a633f  pop     r15
0x1800a6341  pop     r14
0x1800a6343  pop     rdi
0x1800a6344  pop     rsi
0x1800a6345  pop     rbp
0x1800a6346  retn
0x1800a6348  xor     al, al
0x1800a634a  jmp     short loc_1800A6336
0x1800a634c  xor     edx, edx; dwSize
0x1800a634e  mov     r8d, 8000h; dwFreeType
0x1800a6354  mov     rcx, rsi; lpAddress
0x1800a6357  call    cs:__imp_VirtualFree
0x1800a635e  nop     dword ptr [rax+rax+00h]
0x1800a6363  mov     rcx, rdi; hMem
0x1800a6366  call    cs:__imp_LocalFree
0x1800a636d  nop     dword ptr [rax+rax+00h]
0x1800a6372  jmp     short loc_1800A631C
0x1800a6374  add     dword ptr cs:qword_1803136F8, ebx
0x1800a637a  mov     dword ptr cs:qword_1803136F8+4, ebx
0x1800a6380  jmp     short loc_1800A638D
0x1800a6382  cmp     dword ptr [rsp+58h+DistanceToMoveHigh+4], 0
0x1800a6387  jnz     loc_1800A62C7
0x1800a638d  xor     edx, edx; dwSize
0x1800a638f  mov     r8d, 8000h; dwFreeType
0x1800a6395  mov     rcx, rsi; lpAddress
0x1800a6398  xor     bl, bl
0x1800a639a  call    cs:__imp_VirtualFree
0x1800a63a1  nop     dword ptr [rax+rax+00h]
0x1800a63a6  test    rdi, rdi
0x1800a63a9  jz      loc_1800A631C
0x1800a63af  jmp     short loc_1800A6363
```
