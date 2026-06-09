# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x1800152dc`
- end: `0x1800154da`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180016880`

## callees

- `0x1800027d6`
- `0x180015020`
- `0x180015218`
- `0x1800152dc`
- `0x1800191a2`

## import_xrefs

- `KERNEL32!GetStdHandle` at `0x180015456`
- `KERNEL32!GetStdHandle` at `0x180015456`
- `KERNEL32!WriteFile` at `0x18001547b`
- `KERNEL32!WriteFile` at `0x18001547b`
- `KERNEL32!OutputDebugStringA` at `0x18001543f`
- `KERNEL32!OutputDebugStringA` at `0x18001543f`
- `KERNEL32!HeapAlloc` at `0x180015396`
- `KERNEL32!HeapAlloc` at `0x180015396`
- `KERNEL32!HeapReAlloc` at `0x1800153b6`
- `KERNEL32!HeapReAlloc` at `0x1800153b6`
- `ntdll!RtlLeaveCriticalSection` at `0x180015410`
- `ntdll!RtlLeaveCriticalSection` at `0x1800154c3`
- `ntdll!RtlLeaveCriticalSection` at `0x180015410`
- `ntdll!RtlLeaveCriticalSection` at `0x1800154c3`
- `ntdll!RtlEnterCriticalSection` at `0x18001530b`
- `ntdll!RtlEnterCriticalSection` at `0x18001548d`
- `ntdll!RtlEnterCriticalSection` at `0x18001530b`
- `ntdll!RtlEnterCriticalSection` at `0x18001548d`

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
  void *v17; // rax
  LPVOID v18; // r15
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
          v18 = HeapReAlloc(v15, 0, v14, v16);
        }
        else
        {
          v17 = HeapAlloc(v15, 0, v16);
          v18 = v17;
          if ( v17 )
            memset_0(v17, 0, v16);
        }
        if ( v18 )
        {
          *((_QWORD *)a1 + 23) = v18;
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
0x1800152dc  push    rbx
0x1800152de  push    rbp
0x1800152df  push    rsi
0x1800152e0  push    rdi
0x1800152e1  push    r12
0x1800152e3  push    r13
0x1800152e5  push    r14
0x1800152e7  push    r15
0x1800152e9  sub     rsp, 38h
0x1800152ed  mov     rax, [rcx]
0x1800152f0  mov     rdi, rcx
0x1800152f3  add     rcx, 68h ; 'h'; CriticalSection
0x1800152f7  mov     r13, r8
0x1800152fa  mov     r12, rdx
0x1800152fd  mov     rbp, rdx
0x180015300  mov     rsi, r8
0x180015303  mov     qword ptr [rax+40h], 0
0x18001530b  call    cs:__imp_RtlEnterCriticalSection
0x180015311  mov     rax, [rdi]
0x180015314  lea     rbx, [rdi+90h]
0x18001531b  cmp     dword ptr [rax+4Ch], 0
0x18001531f  jz      short loc_18001534B
0x180015321  mov     ecx, [rax+4Ch]
0x180015324  cmp     rsi, rcx
0x180015327  jbe     short loc_180015331
0x180015329  sub     rbp, rcx
0x18001532c  add     rbp, rsi
0x18001532f  mov     esi, ecx
0x180015331  mov     edx, [rbx+8]
0x180015334  lea     rax, [rdx+rsi]
0x180015338  cmp     rax, rcx
0x18001533b  jbe     short loc_18001534B
0x18001533d  sub     rdx, rcx
0x180015340  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x180015343  add     rdx, rsi; unsigned __int64
0x180015346  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x18001534b  test    rsi, rsi
0x18001534e  jz      loc_180015409
0x180015354  mov     rax, [rbx+20h]
0x180015358  lea     rcx, [rax+rsi]
0x18001535c  cmp     rcx, rax
0x18001535f  jb      loc_180015409
0x180015365  cmp     rcx, [rbx+10h]
0x180015369  jbe     short loc_1800153CC
0x18001536b  mov     r14, [rbx+18h]
0x18001536f  dec     r14
0x180015372  lea     rax, [r14+rcx]
0x180015376  cmp     rax, rcx
0x180015379  jb      loc_180015409
0x18001537f  mov     r8, [rbx+28h]; lpMem
0x180015383  not     r14
0x180015386  mov     rcx, [rbx]; hHeap
0x180015389  and     r14, rax
0x18001538c  xor     edx, edx; dwFlags
0x18001538e  test    r8, r8
0x180015391  jnz     short loc_1800153B3
0x180015393  mov     r8, r14; dwBytes
0x180015396  call    cs:__imp_HeapAlloc
0x18001539c  mov     r15, rax
0x18001539f  test    rax, rax
0x1800153a2  jz      short loc_1800153BF
0x1800153a4  mov     r8, r14; Size
0x1800153a7  xor     edx, edx; Val
0x1800153a9  mov     rcx, rax; void *
0x1800153ac  call    memset_0
0x1800153b1  jmp     short loc_1800153BF
0x1800153b3  mov     r9, r14; dwBytes
0x1800153b6  call    cs:__imp_HeapReAlloc
0x1800153bc  mov     r15, rax
0x1800153bf  test    r15, r15
0x1800153c2  jz      short loc_180015409
0x1800153c4  mov     [rbx+28h], r15
0x1800153c8  mov     [rbx+10h], r14
0x1800153cc  mov     rcx, [rbx+28h]
0x1800153d0  mov     r8, rsi; Size
0x1800153d3  add     rcx, [rbx+20h]; void *
0x1800153d7  mov     rdx, rbp; Src
0x1800153da  call    memcpy_0
0x1800153df  mov     rax, [rbx+20h]
0x1800153e3  lea     rcx, [rax+rsi]
0x1800153e7  cmp     rcx, rax
0x1800153ea  jb      short loc_180015401
0x1800153ec  mov     [rbx+20h], rcx
0x1800153f0  mov     rax, [rbx+8]
0x1800153f4  cmp     rax, rcx
0x1800153f7  cmovbe  rax, rcx
0x1800153fb  mov     [rbx+8], rax
0x1800153ff  jmp     short loc_180015409
0x180015401  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x180015409  lea     rbx, [rdi+68h]
0x18001540d  mov     rcx, rbx; CriticalSection
0x180015410  call    cs:__imp_RtlLeaveCriticalSection
0x180015416  mov     rax, [rdi+0B8h]
0x18001541d  mov     bpl, 1
0x180015420  mov     rcx, [rdi]
0x180015423  mov     [rcx+40h], rax
0x180015427  mov     eax, [rdi+98h]
0x18001542d  mov     rcx, [rdi]
0x180015430  mov     [rcx+48h], eax
0x180015433  mov     rax, [rdi]
0x180015436  test    [rax+50h], bpl
0x18001543a  jz      short loc_180015445
0x18001543c  mov     rcx, r12; lpOutputString
0x18001543f  call    cs:__imp_OutputDebugStringA
0x180015445  mov     rax, [rdi]
0x180015448  test    dword ptr [rax+50h], 100h
0x18001544f  jz      short loc_180015481
0x180015451  mov     ecx, 0FFFFFFF5h; nStdHandle
0x180015456  call    cs:__imp_GetStdHandle
0x18001545c  lea     rcx, [rax-1]
0x180015460  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180015464  ja      short loc_180015481
0x180015466  mov     r8d, esi; nNumberOfBytesToWrite
0x180015469  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180015472  xor     r9d, r9d; lpNumberOfBytesWritten
0x180015475  mov     rdx, r12; lpBuffer
0x180015478  mov     rcx, rax; hFile
0x18001547b  call    cs:__imp_WriteFile
0x180015481  mov     rax, [rdi]
0x180015484  test    byte ptr [rax+50h], 4
0x180015488  jz      short loc_1800154C9
0x18001548a  mov     rcx, rbx; CriticalSection
0x18001548d  call    cs:__imp_RtlEnterCriticalSection
0x180015493  mov     rax, [rdi]
0x180015496  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x18001549d  mov     r8, r13; unsigned __int64
0x1800154a0  mov     rdx, r12; char *
0x1800154a3  mov     r9d, [rax+50h]
0x1800154a7  mov     eax, r9d
0x1800154aa  shr     eax, 5
0x1800154ad  shr     r9d, 3
0x1800154b1  and     al, bpl
0x1800154b4  and     r9b, bpl; unsigned __int8
0x1800154b7  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x1800154bb  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x1800154c0  mov     rcx, rbx; CriticalSection
0x1800154c3  call    cs:__imp_RtlLeaveCriticalSection
0x1800154c9  add     rsp, 38h
0x1800154cd  pop     r15
0x1800154cf  pop     r14
0x1800154d1  pop     r13
0x1800154d3  pop     r12
0x1800154d5  pop     rdi
0x1800154d6  pop     rsi
0x1800154d7  pop     rbp
0x1800154d8  pop     rbx
0x1800154d9  retn
```
