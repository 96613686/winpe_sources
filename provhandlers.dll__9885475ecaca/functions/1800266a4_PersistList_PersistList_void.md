# PersistList::~PersistList(void)

- ea: `0x1800266a4`
- end: `0x18002673e`
- name: `??1PersistList@@UEAA@XZ`
- size: `154`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800268e0`

## callees

- `0x1800266a4`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800266c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800266c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026726`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026726`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026737`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800266f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800266f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026704`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026704`

## pseudocode

```c
void __fastcall PersistList::~PersistList(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  __int64 i; // rbx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  void (__fastcall ***SpinCount)(_QWORD, __int64); // rcx

  v2 = this + 1;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&PersistList::`vftable';
  EnterCriticalSection(this + 1);
  for ( i = 0; (unsigned int)i < LODWORD(this->OwningThread); i = (unsigned int)(i + 1) )
  {
    v4 = *(void (__fastcall ****)(_QWORD, __int64))(*(_QWORD *)&this->LockCount + 8 * i);
    if ( v4 )
      (**v4)(v4, 1);
  }
  v5 = *(void **)&this->LockCount;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v5);
  SpinCount = (void (__fastcall ***)(_QWORD, __int64))this->SpinCount;
  if ( SpinCount )
    (**SpinCount)(SpinCount, 1);
  LeaveCriticalSection(v2);
  DeleteCriticalSection(v2);
}

```

## disassembly

```asm
0x1800266a4  push    rbx
0x1800266a6  push    rbp
0x1800266a7  push    rsi
0x1800266a8  push    rdi
0x1800266a9  sub     rsp, 28h
0x1800266ad  lea     rax, ??_7PersistList@@6B@; const PersistList::`vftable'
0x1800266b4  mov     rdi, rcx
0x1800266b7  lea     rbp, [rcx+28h]
0x1800266bb  mov     [rcx], rax
0x1800266be  mov     rcx, rbp; lpCriticalSection
0x1800266c1  call    cs:__imp_EnterCriticalSection
0x1800266c7  xor     ebx, ebx
0x1800266c9  cmp     [rdi+10h], ebx
0x1800266cc  jbe     short loc_1800266F2
0x1800266ce  mov     rax, [rdi+8]
0x1800266d2  mov     rcx, [rax+rbx*8]
0x1800266d6  test    rcx, rcx
0x1800266d9  jz      short loc_1800266EB
0x1800266db  mov     rax, [rcx]
0x1800266de  mov     edx, 1
0x1800266e3  mov     rax, [rax]
0x1800266e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266eb  inc     ebx
0x1800266ed  cmp     ebx, [rdi+10h]
0x1800266f0  jb      short loc_1800266CE
0x1800266f2  mov     rbx, [rdi+8]
0x1800266f6  call    cs:__imp_GetProcessHeap
0x1800266fc  mov     r8, rbx; lpMem
0x1800266ff  xor     edx, edx; dwFlags
0x180026701  mov     rcx, rax; hHeap
0x180026704  call    cs:__imp_HeapFree
0x18002670a  mov     rcx, [rdi+20h]
0x18002670e  test    rcx, rcx
0x180026711  jz      short loc_180026723
0x180026713  mov     rax, [rcx]
0x180026716  mov     edx, 1
0x18002671b  mov     rax, [rax]
0x18002671e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026723  mov     rcx, rbp; lpCriticalSection
0x180026726  call    cs:__imp_LeaveCriticalSection
0x18002672c  mov     rcx, rbp
0x18002672f  add     rsp, 28h
0x180026733  pop     rdi
0x180026734  pop     rsi
0x180026735  pop     rbp
0x180026736  pop     rbx
0x180026737  jmp     cs:__imp_DeleteCriticalSection
```
