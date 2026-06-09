# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x18016ae78`
- end: `0x18016b076`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `510`
- prototype: `void(struct _ASL_LOG *, const char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18016b7e0`

## callees

- `0x180009efc`
- `0x180009f14`
- `0x18016abbc`
- `0x18016adb4`
- `0x18016ae78`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18016afdb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18016afdb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18016b017`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18016b017`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18016aff2`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x18016aff2`
- `ntdll!RtlLeaveCriticalSection` at `0x18016afac`
- `ntdll!RtlLeaveCriticalSection` at `0x18016b05f`
- `ntdll!RtlLeaveCriticalSection` at `0x18016afac`
- `ntdll!RtlLeaveCriticalSection` at `0x18016b05f`
- `ntdll!RtlEnterCriticalSection` at `0x18016aea7`
- `ntdll!RtlEnterCriticalSection` at `0x18016b029`
- `ntdll!RtlEnterCriticalSection` at `0x18016aea7`
- `ntdll!RtlEnterCriticalSection` at `0x18016b029`
- `ntdll!RtlReAllocateHeap` at `0x18016af52`
- `ntdll!RtlReAllocateHeap` at `0x18016af52`
- `ntdll!RtlAllocateHeap` at `0x18016af32`
- `ntdll!RtlAllocateHeap` at `0x18016af32`

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
0x18016ae78  push    rbx
0x18016ae7a  push    rbp
0x18016ae7b  push    rsi
0x18016ae7c  push    rdi
0x18016ae7d  push    r12
0x18016ae7f  push    r13
0x18016ae81  push    r14
0x18016ae83  push    r15
0x18016ae85  sub     rsp, 38h
0x18016ae89  mov     rax, [rcx]
0x18016ae8c  mov     rdi, rcx
0x18016ae8f  add     rcx, 68h ; 'h'; CriticalSection
0x18016ae93  mov     r13, r8
0x18016ae96  mov     r12, rdx
0x18016ae99  mov     rbp, rdx
0x18016ae9c  mov     rsi, r8
0x18016ae9f  mov     qword ptr [rax+40h], 0
0x18016aea7  call    cs:__imp_RtlEnterCriticalSection
0x18016aead  mov     rax, [rdi]
0x18016aeb0  lea     rbx, [rdi+90h]
0x18016aeb7  cmp     dword ptr [rax+4Ch], 0
0x18016aebb  jz      short loc_18016AEE7
0x18016aebd  mov     ecx, [rax+4Ch]
0x18016aec0  cmp     rsi, rcx
0x18016aec3  jbe     short loc_18016AECD
0x18016aec5  sub     rbp, rcx
0x18016aec8  add     rbp, rsi
0x18016aecb  mov     esi, ecx
0x18016aecd  mov     edx, [rbx+8]
0x18016aed0  lea     rax, [rdx+rsi]
0x18016aed4  cmp     rax, rcx
0x18016aed7  jbe     short loc_18016AEE7
0x18016aed9  sub     rdx, rcx
0x18016aedc  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x18016aedf  add     rdx, rsi; unsigned __int64
0x18016aee2  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x18016aee7  test    rsi, rsi
0x18016aeea  jz      loc_18016AFA5
0x18016aef0  mov     rax, [rbx+20h]
0x18016aef4  lea     rcx, [rax+rsi]
0x18016aef8  cmp     rcx, rax
0x18016aefb  jb      loc_18016AFA5
0x18016af01  cmp     rcx, [rbx+10h]
0x18016af05  jbe     short loc_18016AF68
0x18016af07  mov     r14, [rbx+18h]
0x18016af0b  dec     r14
0x18016af0e  lea     rax, [r14+rcx]
0x18016af12  cmp     rax, rcx
0x18016af15  jb      loc_18016AFA5
0x18016af1b  mov     r8, [rbx+28h]; Ptr
0x18016af1f  not     r14
0x18016af22  mov     rcx, [rbx]; Heap
0x18016af25  and     r14, rax
0x18016af28  xor     edx, edx; Flags
0x18016af2a  test    r8, r8
0x18016af2d  jnz     short loc_18016AF4F
0x18016af2f  mov     r8, r14; Size
0x18016af32  call    cs:__imp_RtlAllocateHeap
0x18016af38  mov     r15, rax
0x18016af3b  test    rax, rax
0x18016af3e  jz      short loc_18016AF5B
0x18016af40  mov     r8, r14; Size
0x18016af43  xor     edx, edx; Val
0x18016af45  mov     rcx, rax; void *
0x18016af48  call    memset_0
0x18016af4d  jmp     short loc_18016AF5B
0x18016af4f  mov     r9, r14; Size
0x18016af52  call    cs:__imp_RtlReAllocateHeap
0x18016af58  mov     r15, rax
0x18016af5b  test    r15, r15
0x18016af5e  jz      short loc_18016AFA5
0x18016af60  mov     [rbx+28h], r15
0x18016af64  mov     [rbx+10h], r14
0x18016af68  mov     rcx, [rbx+28h]
0x18016af6c  mov     r8, rsi; Size
0x18016af6f  add     rcx, [rbx+20h]; void *
0x18016af73  mov     rdx, rbp; Src
0x18016af76  call    memcpy_0
0x18016af7b  mov     rax, [rbx+20h]
0x18016af7f  lea     rcx, [rax+rsi]
0x18016af83  cmp     rcx, rax
0x18016af86  jb      short loc_18016AF9D
0x18016af88  mov     [rbx+20h], rcx
0x18016af8c  mov     rax, [rbx+8]
0x18016af90  cmp     rax, rcx
0x18016af93  cmovbe  rax, rcx
0x18016af97  mov     [rbx+8], rax
0x18016af9b  jmp     short loc_18016AFA5
0x18016af9d  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x18016afa5  lea     rbx, [rdi+68h]
0x18016afa9  mov     rcx, rbx; CriticalSection
0x18016afac  call    cs:__imp_RtlLeaveCriticalSection
0x18016afb2  mov     rax, [rdi+0B8h]
0x18016afb9  mov     bpl, 1
0x18016afbc  mov     rcx, [rdi]
0x18016afbf  mov     [rcx+40h], rax
0x18016afc3  mov     eax, [rdi+98h]
0x18016afc9  mov     rcx, [rdi]
0x18016afcc  mov     [rcx+48h], eax
0x18016afcf  mov     rax, [rdi]
0x18016afd2  test    [rax+50h], bpl
0x18016afd6  jz      short loc_18016AFE1
0x18016afd8  mov     rcx, r12; lpOutputString
0x18016afdb  call    cs:__imp_OutputDebugStringA
0x18016afe1  mov     rax, [rdi]
0x18016afe4  test    dword ptr [rax+50h], 100h
0x18016afeb  jz      short loc_18016B01D
0x18016afed  mov     ecx, 0FFFFFFF5h; nStdHandle
0x18016aff2  call    cs:__imp_GetStdHandle
0x18016aff8  lea     rcx, [rax-1]
0x18016affc  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18016b000  ja      short loc_18016B01D
0x18016b002  mov     r8d, esi; nNumberOfBytesToWrite
0x18016b005  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18016b00e  xor     r9d, r9d; lpNumberOfBytesWritten
0x18016b011  mov     rdx, r12; lpBuffer
0x18016b014  mov     rcx, rax; hFile
0x18016b017  call    cs:__imp_WriteFile
0x18016b01d  mov     rax, [rdi]
0x18016b020  test    byte ptr [rax+50h], 4
0x18016b024  jz      short loc_18016B065
0x18016b026  mov     rcx, rbx; CriticalSection
0x18016b029  call    cs:__imp_RtlEnterCriticalSection
0x18016b02f  mov     rax, [rdi]
0x18016b032  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x18016b039  mov     r8, r13; unsigned __int64
0x18016b03c  mov     rdx, r12; char *
0x18016b03f  mov     r9d, [rax+50h]
0x18016b043  mov     eax, r9d
0x18016b046  shr     eax, 5
0x18016b049  shr     r9d, 3
0x18016b04d  and     al, bpl
0x18016b050  and     r9b, bpl; unsigned __int8
0x18016b053  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x18016b057  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x18016b05c  mov     rcx, rbx; CriticalSection
0x18016b05f  call    cs:__imp_RtlLeaveCriticalSection
0x18016b065  add     rsp, 38h
0x18016b069  pop     r15
0x18016b06b  pop     r14
0x18016b06d  pop     r13
0x18016b06f  pop     r12
0x18016b071  pop     rdi
0x18016b072  pop     rsi
0x18016b073  pop     rbp
0x18016b074  pop     rbx
0x18016b075  retn
```
