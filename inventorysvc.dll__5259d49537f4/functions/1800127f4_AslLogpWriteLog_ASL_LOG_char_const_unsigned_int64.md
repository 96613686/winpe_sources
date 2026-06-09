# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x1800127f4`
- end: `0x1800129f2`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void __fastcall(struct _ASL_LOG *, const char *, size_t)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180013314`

## callees

- `0x1800038b8`
- `0x180005477`
- `0x180012538`
- `0x180012730`
- `0x1800127f4`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180012928`
- `ntdll!RtlLeaveCriticalSection` at `0x1800129db`
- `ntdll!RtlLeaveCriticalSection` at `0x180012928`
- `ntdll!RtlLeaveCriticalSection` at `0x1800129db`
- `ntdll!RtlEnterCriticalSection` at `0x180012823`
- `ntdll!RtlEnterCriticalSection` at `0x1800129a5`
- `ntdll!RtlEnterCriticalSection` at `0x180012823`
- `ntdll!RtlEnterCriticalSection` at `0x1800129a5`
- `ntdll!RtlReAllocateHeap` at `0x1800128ce`
- `ntdll!RtlReAllocateHeap` at `0x1800128ce`
- `ntdll!RtlAllocateHeap` at `0x1800128ae`
- `ntdll!RtlAllocateHeap` at `0x1800128ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180012957`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180012957`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18001296e`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18001296e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012993`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180012993`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800127f4  push    rbx
0x1800127f6  push    rbp
0x1800127f7  push    rsi
0x1800127f8  push    rdi
0x1800127f9  push    r12
0x1800127fb  push    r13
0x1800127fd  push    r14
0x1800127ff  push    r15
0x180012801  sub     rsp, 38h
0x180012805  mov     rax, [rcx]
0x180012808  mov     rdi, rcx
0x18001280b  add     rcx, 68h ; 'h'; CriticalSection
0x18001280f  mov     r13, r8
0x180012812  mov     r12, rdx
0x180012815  mov     rbp, rdx
0x180012818  mov     rsi, r8
0x18001281b  mov     qword ptr [rax+40h], 0
0x180012823  call    cs:__imp_RtlEnterCriticalSection
0x180012829  mov     rax, [rdi]
0x18001282c  lea     rbx, [rdi+90h]
0x180012833  cmp     dword ptr [rax+4Ch], 0
0x180012837  jz      short loc_180012863
0x180012839  mov     ecx, [rax+4Ch]
0x18001283c  cmp     rsi, rcx
0x18001283f  jbe     short loc_180012849
0x180012841  sub     rbp, rcx
0x180012844  add     rbp, rsi
0x180012847  mov     esi, ecx
0x180012849  mov     edx, [rbx+8]
0x18001284c  lea     rax, [rdx+rsi]
0x180012850  cmp     rax, rcx
0x180012853  jbe     short loc_180012863
0x180012855  sub     rdx, rcx
0x180012858  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x18001285b  add     rdx, rsi; unsigned __int64
0x18001285e  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x180012863  test    rsi, rsi
0x180012866  jz      loc_180012921
0x18001286c  mov     rax, [rbx+20h]
0x180012870  lea     rcx, [rax+rsi]
0x180012874  cmp     rcx, rax
0x180012877  jb      loc_180012921
0x18001287d  cmp     rcx, [rbx+10h]
0x180012881  jbe     short loc_1800128E4
0x180012883  mov     r14, [rbx+18h]
0x180012887  dec     r14
0x18001288a  lea     rax, [r14+rcx]
0x18001288e  cmp     rax, rcx
0x180012891  jb      loc_180012921
0x180012897  mov     r8, [rbx+28h]; Ptr
0x18001289b  not     r14
0x18001289e  mov     rcx, [rbx]; Heap
0x1800128a1  and     r14, rax
0x1800128a4  xor     edx, edx; Flags
0x1800128a6  test    r8, r8
0x1800128a9  jnz     short loc_1800128CB
0x1800128ab  mov     r8, r14; Size
0x1800128ae  call    cs:__imp_RtlAllocateHeap
0x1800128b4  mov     r15, rax
0x1800128b7  test    rax, rax
0x1800128ba  jz      short loc_1800128D7
0x1800128bc  mov     r8, r14; Size
0x1800128bf  xor     edx, edx; Val
0x1800128c1  mov     rcx, rax; void *
0x1800128c4  call    memset_0
0x1800128c9  jmp     short loc_1800128D7
0x1800128cb  mov     r9, r14; Size
0x1800128ce  call    cs:__imp_RtlReAllocateHeap
0x1800128d4  mov     r15, rax
0x1800128d7  test    r15, r15
0x1800128da  jz      short loc_180012921
0x1800128dc  mov     [rbx+28h], r15
0x1800128e0  mov     [rbx+10h], r14
0x1800128e4  mov     rcx, [rbx+28h]
0x1800128e8  mov     r8, rsi; Size
0x1800128eb  add     rcx, [rbx+20h]; void *
0x1800128ef  mov     rdx, rbp; Src
0x1800128f2  call    memcpy_0
0x1800128f7  mov     rax, [rbx+20h]
0x1800128fb  lea     rcx, [rax+rsi]
0x1800128ff  cmp     rcx, rax
0x180012902  jb      short loc_180012919
0x180012904  mov     [rbx+20h], rcx
0x180012908  mov     rax, [rbx+8]
0x18001290c  cmp     rax, rcx
0x18001290f  cmovbe  rax, rcx
0x180012913  mov     [rbx+8], rax
0x180012917  jmp     short loc_180012921
0x180012919  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x180012921  lea     rbx, [rdi+68h]
0x180012925  mov     rcx, rbx; CriticalSection
0x180012928  call    cs:__imp_RtlLeaveCriticalSection
0x18001292e  mov     rax, [rdi+0B8h]
0x180012935  mov     bpl, 1
0x180012938  mov     rcx, [rdi]
0x18001293b  mov     [rcx+40h], rax
0x18001293f  mov     eax, [rdi+98h]
0x180012945  mov     rcx, [rdi]
0x180012948  mov     [rcx+48h], eax
0x18001294b  mov     rax, [rdi]
0x18001294e  test    [rax+50h], bpl
0x180012952  jz      short loc_18001295D
0x180012954  mov     rcx, r12; lpOutputString
0x180012957  call    cs:__imp_OutputDebugStringA
0x18001295d  mov     rax, [rdi]
0x180012960  test    dword ptr [rax+50h], 100h
0x180012967  jz      short loc_180012999
0x180012969  mov     ecx, 0FFFFFFF5h; nStdHandle
0x18001296e  call    cs:__imp_GetStdHandle
0x180012974  lea     rcx, [rax-1]
0x180012978  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001297c  ja      short loc_180012999
0x18001297e  mov     r8d, esi; nNumberOfBytesToWrite
0x180012981  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18001298a  xor     r9d, r9d; lpNumberOfBytesWritten
0x18001298d  mov     rdx, r12; lpBuffer
0x180012990  mov     rcx, rax; hFile
0x180012993  call    cs:__imp_WriteFile
0x180012999  mov     rax, [rdi]
0x18001299c  test    byte ptr [rax+50h], 4
0x1800129a0  jz      short loc_1800129E1
0x1800129a2  mov     rcx, rbx; CriticalSection
0x1800129a5  call    cs:__imp_RtlEnterCriticalSection
0x1800129ab  mov     rax, [rdi]
0x1800129ae  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x1800129b5  mov     r8, r13; unsigned __int64
0x1800129b8  mov     rdx, r12; char *
0x1800129bb  mov     r9d, [rax+50h]
0x1800129bf  mov     eax, r9d
0x1800129c2  shr     eax, 5
0x1800129c5  shr     r9d, 3
0x1800129c9  and     al, bpl
0x1800129cc  and     r9b, bpl; unsigned __int8
0x1800129cf  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x1800129d3  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x1800129d8  mov     rcx, rbx; CriticalSection
0x1800129db  call    cs:__imp_RtlLeaveCriticalSection
0x1800129e1  add     rsp, 38h
0x1800129e5  pop     r15
0x1800129e7  pop     r14
0x1800129e9  pop     r13
0x1800129eb  pop     r12
0x1800129ed  pop     rdi
0x1800129ee  pop     rsi
0x1800129ef  pop     rbp
0x1800129f0  pop     rbx
0x1800129f1  retn
```
