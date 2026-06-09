# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x18006a070`
- end: `0x18006a26e`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18006a9e4`

## callees

- `0x180006eac`
- `0x180006ec4`
- `0x180069db4`
- `0x180069fac`
- `0x18006a070`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18006a1a4`
- `ntdll!RtlLeaveCriticalSection` at `0x18006a257`
- `ntdll!RtlLeaveCriticalSection` at `0x18006a1a4`
- `ntdll!RtlLeaveCriticalSection` at `0x18006a257`
- `ntdll!RtlEnterCriticalSection` at `0x18006a09f`
- `ntdll!RtlEnterCriticalSection` at `0x18006a221`
- `ntdll!RtlEnterCriticalSection` at `0x18006a09f`
- `ntdll!RtlEnterCriticalSection` at `0x18006a221`
- `ntdll!RtlReAllocateHeap` at `0x18006a14a`
- `ntdll!RtlReAllocateHeap` at `0x18006a14a`
- `ntdll!RtlAllocateHeap` at `0x18006a12a`
- `ntdll!RtlAllocateHeap` at `0x18006a12a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18006a1d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18006a1d3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006a20f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006a20f`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18006a1ea`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18006a1ea`

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
0x18006a070  push    rbx
0x18006a072  push    rbp
0x18006a073  push    rsi
0x18006a074  push    rdi
0x18006a075  push    r12
0x18006a077  push    r13
0x18006a079  push    r14
0x18006a07b  push    r15
0x18006a07d  sub     rsp, 38h
0x18006a081  mov     rax, [rcx]
0x18006a084  mov     rdi, rcx
0x18006a087  add     rcx, 68h ; 'h'; CriticalSection
0x18006a08b  mov     r13, r8
0x18006a08e  mov     r12, rdx
0x18006a091  mov     rbp, rdx
0x18006a094  mov     rsi, r8
0x18006a097  mov     qword ptr [rax+40h], 0
0x18006a09f  call    cs:__imp_RtlEnterCriticalSection
0x18006a0a5  mov     rax, [rdi]
0x18006a0a8  lea     rbx, [rdi+90h]
0x18006a0af  cmp     dword ptr [rax+4Ch], 0
0x18006a0b3  jz      short loc_18006A0DF
0x18006a0b5  mov     ecx, [rax+4Ch]
0x18006a0b8  cmp     rsi, rcx
0x18006a0bb  jbe     short loc_18006A0C5
0x18006a0bd  sub     rbp, rcx
0x18006a0c0  add     rbp, rsi
0x18006a0c3  mov     esi, ecx
0x18006a0c5  mov     edx, [rbx+8]
0x18006a0c8  lea     rax, [rdx+rsi]
0x18006a0cc  cmp     rax, rcx
0x18006a0cf  jbe     short loc_18006A0DF
0x18006a0d1  sub     rdx, rcx
0x18006a0d4  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x18006a0d7  add     rdx, rsi; unsigned __int64
0x18006a0da  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x18006a0df  test    rsi, rsi
0x18006a0e2  jz      loc_18006A19D
0x18006a0e8  mov     rax, [rbx+20h]
0x18006a0ec  lea     rcx, [rax+rsi]
0x18006a0f0  cmp     rcx, rax
0x18006a0f3  jb      loc_18006A19D
0x18006a0f9  cmp     rcx, [rbx+10h]
0x18006a0fd  jbe     short loc_18006A160
0x18006a0ff  mov     r14, [rbx+18h]
0x18006a103  dec     r14
0x18006a106  lea     rax, [r14+rcx]
0x18006a10a  cmp     rax, rcx
0x18006a10d  jb      loc_18006A19D
0x18006a113  mov     r8, [rbx+28h]; Ptr
0x18006a117  not     r14
0x18006a11a  mov     rcx, [rbx]; Heap
0x18006a11d  and     r14, rax
0x18006a120  xor     edx, edx; Flags
0x18006a122  test    r8, r8
0x18006a125  jnz     short loc_18006A147
0x18006a127  mov     r8, r14; Size
0x18006a12a  call    cs:__imp_RtlAllocateHeap
0x18006a130  mov     r15, rax
0x18006a133  test    rax, rax
0x18006a136  jz      short loc_18006A153
0x18006a138  mov     r8, r14; Size
0x18006a13b  xor     edx, edx; Val
0x18006a13d  mov     rcx, rax; void *
0x18006a140  call    memset_0
0x18006a145  jmp     short loc_18006A153
0x18006a147  mov     r9, r14; Size
0x18006a14a  call    cs:__imp_RtlReAllocateHeap
0x18006a150  mov     r15, rax
0x18006a153  test    r15, r15
0x18006a156  jz      short loc_18006A19D
0x18006a158  mov     [rbx+28h], r15
0x18006a15c  mov     [rbx+10h], r14
0x18006a160  mov     rcx, [rbx+28h]
0x18006a164  mov     r8, rsi; Size
0x18006a167  add     rcx, [rbx+20h]; void *
0x18006a16b  mov     rdx, rbp; Src
0x18006a16e  call    memcpy_0
0x18006a173  mov     rax, [rbx+20h]
0x18006a177  lea     rcx, [rax+rsi]
0x18006a17b  cmp     rcx, rax
0x18006a17e  jb      short loc_18006A195
0x18006a180  mov     [rbx+20h], rcx
0x18006a184  mov     rax, [rbx+8]
0x18006a188  cmp     rax, rcx
0x18006a18b  cmovbe  rax, rcx
0x18006a18f  mov     [rbx+8], rax
0x18006a193  jmp     short loc_18006A19D
0x18006a195  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x18006a19d  lea     rbx, [rdi+68h]
0x18006a1a1  mov     rcx, rbx; CriticalSection
0x18006a1a4  call    cs:__imp_RtlLeaveCriticalSection
0x18006a1aa  mov     rax, [rdi+0B8h]
0x18006a1b1  mov     bpl, 1
0x18006a1b4  mov     rcx, [rdi]
0x18006a1b7  mov     [rcx+40h], rax
0x18006a1bb  mov     eax, [rdi+98h]
0x18006a1c1  mov     rcx, [rdi]
0x18006a1c4  mov     [rcx+48h], eax
0x18006a1c7  mov     rax, [rdi]
0x18006a1ca  test    [rax+50h], bpl
0x18006a1ce  jz      short loc_18006A1D9
0x18006a1d0  mov     rcx, r12; lpOutputString
0x18006a1d3  call    cs:__imp_OutputDebugStringA
0x18006a1d9  mov     rax, [rdi]
0x18006a1dc  test    dword ptr [rax+50h], 100h
0x18006a1e3  jz      short loc_18006A215
0x18006a1e5  mov     ecx, 0FFFFFFF5h; nStdHandle
0x18006a1ea  call    cs:__imp_GetStdHandle
0x18006a1f0  lea     rcx, [rax-1]
0x18006a1f4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18006a1f8  ja      short loc_18006A215
0x18006a1fa  mov     r8d, esi; nNumberOfBytesToWrite
0x18006a1fd  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18006a206  xor     r9d, r9d; lpNumberOfBytesWritten
0x18006a209  mov     rdx, r12; lpBuffer
0x18006a20c  mov     rcx, rax; hFile
0x18006a20f  call    cs:__imp_WriteFile
0x18006a215  mov     rax, [rdi]
0x18006a218  test    byte ptr [rax+50h], 4
0x18006a21c  jz      short loc_18006A25D
0x18006a21e  mov     rcx, rbx; CriticalSection
0x18006a221  call    cs:__imp_RtlEnterCriticalSection
0x18006a227  mov     rax, [rdi]
0x18006a22a  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x18006a231  mov     r8, r13; unsigned __int64
0x18006a234  mov     rdx, r12; char *
0x18006a237  mov     r9d, [rax+50h]
0x18006a23b  mov     eax, r9d
0x18006a23e  shr     eax, 5
0x18006a241  shr     r9d, 3
0x18006a245  and     al, bpl
0x18006a248  and     r9b, bpl; unsigned __int8
0x18006a24b  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x18006a24f  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x18006a254  mov     rcx, rbx; CriticalSection
0x18006a257  call    cs:__imp_RtlLeaveCriticalSection
0x18006a25d  add     rsp, 38h
0x18006a261  pop     r15
0x18006a263  pop     r14
0x18006a265  pop     r13
0x18006a267  pop     r12
0x18006a269  pop     rdi
0x18006a26a  pop     rsi
0x18006a26b  pop     rbp
0x18006a26c  pop     rbx
0x18006a26d  retn
```
