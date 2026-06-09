# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x14000457c`
- end: `0x14000477a`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void __fastcall(struct _ASL_LOG *, const char *, size_t)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1400050a0`

## callees

- `0x140001fe6`
- `0x14000233f`
- `0x1400042c0`
- `0x1400044b8`
- `0x14000457c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1400046b0`
- `ntdll!RtlLeaveCriticalSection` at `0x140004763`
- `ntdll!RtlLeaveCriticalSection` at `0x1400046b0`
- `ntdll!RtlLeaveCriticalSection` at `0x140004763`
- `ntdll!RtlEnterCriticalSection` at `0x1400045ab`
- `ntdll!RtlEnterCriticalSection` at `0x14000472d`
- `ntdll!RtlEnterCriticalSection` at `0x1400045ab`
- `ntdll!RtlEnterCriticalSection` at `0x14000472d`
- `ntdll!RtlReAllocateHeap` at `0x140004656`
- `ntdll!RtlReAllocateHeap` at `0x140004656`
- `ntdll!RtlAllocateHeap` at `0x140004636`
- `ntdll!RtlAllocateHeap` at `0x140004636`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400046f6`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400046f6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000471b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000471b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1400046df`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1400046df`

## pseudocode

```c
void __fastcall AslLogpWriteLog(struct _ASL_LOG *a1, const char *a2, size_t a3)
{
  DWORD v4; // r13d
  const char *v6; // rbp
  size_t v7; // rsi
  size_t v8; // rcx
  __int64 v9; // rdx
  size_t v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // r14
  unsigned __int64 v13; // rax
  void *v14; // r8
  void *v15; // rcx
  SIZE_T v16; // r14
  PVOID v17; // rax
  PVOID Heap; // r15
  size_t v19; // rax
  size_t v20; // rcx
  size_t v21; // rax
  char *StdHandle; // rax

  v4 = a3;
  v6 = a2;
  v7 = a3;
  *(_QWORD *)(*(_QWORD *)a1 + 64LL) = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  if ( *(_DWORD *)(*(_QWORD *)a1 + 76LL) )
  {
    v8 = *(unsigned int *)(*(_QWORD *)a1 + 76LL);
    if ( v7 > v8 )
    {
      v6 = &v6[v7 - v8];
      v7 = (unsigned int)v8;
    }
    v9 = *((unsigned int *)a1 + 38);
    if ( v9 + v7 > v8 )
      AslLogpRollStream((struct _RTL_MEMORY_STREAM *)((char *)a1 + 144), v7 + v9 - v8);
  }
  if ( v7 )
  {
    v10 = *((_QWORD *)a1 + 22);
    v11 = v10 + v7;
    if ( v10 + v7 >= v10 )
    {
      if ( v11 <= *((_QWORD *)a1 + 20) )
        goto LABEL_16;
      v12 = *((_QWORD *)a1 + 21) - 1LL;
      v13 = v12 + v11;
      if ( v12 + v11 >= v11 )
      {
        v14 = (void *)*((_QWORD *)a1 + 23);
        v15 = (void *)*((_QWORD *)a1 + 18);
        v16 = v13 & ~v12;
        if ( v14 )
        {
          Heap = RtlReAllocateHeap(v15, 0, v14, v16);
        }
        else
        {
          v17 = RtlAllocateHeap(v15, 0, v16);
          Heap = v17;
          if ( v17 )
            memset_0(v17, 0, v16);
        }
        if ( Heap )
        {
          *((_QWORD *)a1 + 23) = Heap;
          *((_QWORD *)a1 + 20) = v16;
LABEL_16:
          memcpy_0((void *)(*((_QWORD *)a1 + 22) + *((_QWORD *)a1 + 23)), v6, v7);
          v19 = *((_QWORD *)a1 + 22);
          v20 = v19 + v7;
          if ( v19 + v7 < v19 )
          {
            *((_QWORD *)a1 + 22) = -1;
          }
          else
          {
            *((_QWORD *)a1 + 22) = v20;
            v21 = *((_QWORD *)a1 + 19);
            if ( v21 <= v20 )
              v21 = v20;
            *((_QWORD *)a1 + 19) = v21;
          }
        }
      }
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  *(_QWORD *)(*(_QWORD *)a1 + 64LL) = *((_QWORD *)a1 + 23);
  *(_DWORD *)(*(_QWORD *)a1 + 72LL) = *((_DWORD *)a1 + 38);
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 80LL) & 1) != 0 )
    OutputDebugStringA(a2);
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 0x100) != 0 )
  {
    StdHandle = (char *)GetStdHandle(0xFFFFFFF5);
    if ( (unsigned __int64)(StdHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WriteFile(StdHandle, a2, v7, 0, 0);
  }
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 80LL) & 4) != 0 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
    AslLogpAppendLog(
      (const unsigned __int16 *)a1 + 96,
      a2,
      v4,
      (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 8) != 0,
      (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 0x20) != 0);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  }
}

```

## disassembly

```asm
0x14000457c  push    rbx
0x14000457e  push    rbp
0x14000457f  push    rsi
0x140004580  push    rdi
0x140004581  push    r12
0x140004583  push    r13
0x140004585  push    r14
0x140004587  push    r15
0x140004589  sub     rsp, 38h
0x14000458d  mov     rax, [rcx]
0x140004590  mov     rdi, rcx
0x140004593  add     rcx, 68h ; 'h'; CriticalSection
0x140004597  mov     r13, r8
0x14000459a  mov     r12, rdx
0x14000459d  mov     rbp, rdx
0x1400045a0  mov     rsi, r8
0x1400045a3  mov     qword ptr [rax+40h], 0
0x1400045ab  call    cs:__imp_RtlEnterCriticalSection
0x1400045b1  mov     rax, [rdi]
0x1400045b4  lea     rbx, [rdi+90h]
0x1400045bb  cmp     dword ptr [rax+4Ch], 0
0x1400045bf  jz      short loc_1400045EB
0x1400045c1  mov     ecx, [rax+4Ch]
0x1400045c4  cmp     rsi, rcx
0x1400045c7  jbe     short loc_1400045D1
0x1400045c9  sub     rbp, rcx
0x1400045cc  add     rbp, rsi
0x1400045cf  mov     esi, ecx
0x1400045d1  mov     edx, [rbx+8]
0x1400045d4  lea     rax, [rdx+rsi]
0x1400045d8  cmp     rax, rcx
0x1400045db  jbe     short loc_1400045EB
0x1400045dd  sub     rdx, rcx
0x1400045e0  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x1400045e3  add     rdx, rsi; unsigned __int64
0x1400045e6  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x1400045eb  test    rsi, rsi
0x1400045ee  jz      loc_1400046A9
0x1400045f4  mov     rax, [rbx+20h]
0x1400045f8  lea     rcx, [rax+rsi]
0x1400045fc  cmp     rcx, rax
0x1400045ff  jb      loc_1400046A9
0x140004605  cmp     rcx, [rbx+10h]
0x140004609  jbe     short loc_14000466C
0x14000460b  mov     r14, [rbx+18h]
0x14000460f  dec     r14
0x140004612  lea     rax, [r14+rcx]
0x140004616  cmp     rax, rcx
0x140004619  jb      loc_1400046A9
0x14000461f  mov     r8, [rbx+28h]; Ptr
0x140004623  not     r14
0x140004626  mov     rcx, [rbx]; Heap
0x140004629  and     r14, rax
0x14000462c  xor     edx, edx; Flags
0x14000462e  test    r8, r8
0x140004631  jnz     short loc_140004653
0x140004633  mov     r8, r14; Size
0x140004636  call    cs:__imp_RtlAllocateHeap
0x14000463c  mov     r15, rax
0x14000463f  test    rax, rax
0x140004642  jz      short loc_14000465F
0x140004644  mov     r8, r14; Size
0x140004647  xor     edx, edx; Val
0x140004649  mov     rcx, rax; void *
0x14000464c  call    memset_0
0x140004651  jmp     short loc_14000465F
0x140004653  mov     r9, r14; Size
0x140004656  call    cs:__imp_RtlReAllocateHeap
0x14000465c  mov     r15, rax
0x14000465f  test    r15, r15
0x140004662  jz      short loc_1400046A9
0x140004664  mov     [rbx+28h], r15
0x140004668  mov     [rbx+10h], r14
0x14000466c  mov     rcx, [rbx+28h]
0x140004670  mov     r8, rsi; Size
0x140004673  add     rcx, [rbx+20h]; void *
0x140004677  mov     rdx, rbp; Src
0x14000467a  call    memcpy_0
0x14000467f  mov     rax, [rbx+20h]
0x140004683  lea     rcx, [rax+rsi]
0x140004687  cmp     rcx, rax
0x14000468a  jb      short loc_1400046A1
0x14000468c  mov     [rbx+20h], rcx
0x140004690  mov     rax, [rbx+8]
0x140004694  cmp     rax, rcx
0x140004697  cmovbe  rax, rcx
0x14000469b  mov     [rbx+8], rax
0x14000469f  jmp     short loc_1400046A9
0x1400046a1  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x1400046a9  lea     rbx, [rdi+68h]
0x1400046ad  mov     rcx, rbx; CriticalSection
0x1400046b0  call    cs:__imp_RtlLeaveCriticalSection
0x1400046b6  mov     rax, [rdi+0B8h]
0x1400046bd  mov     bpl, 1
0x1400046c0  mov     rcx, [rdi]
0x1400046c3  mov     [rcx+40h], rax
0x1400046c7  mov     eax, [rdi+98h]
0x1400046cd  mov     rcx, [rdi]
0x1400046d0  mov     [rcx+48h], eax
0x1400046d3  mov     rax, [rdi]
0x1400046d6  test    [rax+50h], bpl
0x1400046da  jz      short loc_1400046E5
0x1400046dc  mov     rcx, r12; lpOutputString
0x1400046df  call    cs:__imp_OutputDebugStringA
0x1400046e5  mov     rax, [rdi]
0x1400046e8  test    dword ptr [rax+50h], 100h
0x1400046ef  jz      short loc_140004721
0x1400046f1  mov     ecx, 0FFFFFFF5h; nStdHandle
0x1400046f6  call    cs:__imp_GetStdHandle
0x1400046fc  lea     rcx, [rax-1]
0x140004700  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140004704  ja      short loc_140004721
0x140004706  mov     r8d, esi; nNumberOfBytesToWrite
0x140004709  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x140004712  xor     r9d, r9d; lpNumberOfBytesWritten
0x140004715  mov     rdx, r12; lpBuffer
0x140004718  mov     rcx, rax; hFile
0x14000471b  call    cs:__imp_WriteFile
0x140004721  mov     rax, [rdi]
0x140004724  test    byte ptr [rax+50h], 4
0x140004728  jz      short loc_140004769
0x14000472a  mov     rcx, rbx; CriticalSection
0x14000472d  call    cs:__imp_RtlEnterCriticalSection
0x140004733  mov     rax, [rdi]
0x140004736  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x14000473d  mov     r8, r13; unsigned __int64
0x140004740  mov     rdx, r12; char *
0x140004743  mov     r9d, [rax+50h]
0x140004747  mov     eax, r9d
0x14000474a  shr     eax, 5
0x14000474d  shr     r9d, 3
0x140004751  and     al, bpl
0x140004754  and     r9b, bpl; unsigned __int8
0x140004757  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x14000475b  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x140004760  mov     rcx, rbx; CriticalSection
0x140004763  call    cs:__imp_RtlLeaveCriticalSection
0x140004769  add     rsp, 38h
0x14000476d  pop     r15
0x14000476f  pop     r14
0x140004771  pop     r13
0x140004773  pop     r12
0x140004775  pop     rdi
0x140004776  pop     rsi
0x140004777  pop     rbp
0x140004778  pop     rbx
0x140004779  retn
```
