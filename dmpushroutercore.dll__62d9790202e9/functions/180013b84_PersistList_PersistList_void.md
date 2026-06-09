# PersistList::~PersistList(void)

- ea: `0x180013b84`
- end: `0x180013c1e`
- name: `??1PersistList@@UEAA@XZ`
- size: `154`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180013c24`
- `0x180013ca0`
- `0x180017ba0`

## callees

- `0x180013b84`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013be4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013be4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013bd6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013bd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013c06`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013c17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ba1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ba1`

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
0x180013b84  push    rbx
0x180013b86  push    rbp
0x180013b87  push    rsi
0x180013b88  push    rdi
0x180013b89  sub     rsp, 28h
0x180013b8d  lea     rax, ??_7PersistList@@6B@; const PersistList::`vftable'
0x180013b94  mov     rdi, rcx
0x180013b97  lea     rbp, [rcx+28h]
0x180013b9b  mov     [rcx], rax
0x180013b9e  mov     rcx, rbp; lpCriticalSection
0x180013ba1  call    cs:__imp_EnterCriticalSection
0x180013ba7  xor     ebx, ebx
0x180013ba9  cmp     [rdi+10h], ebx
0x180013bac  jbe     short loc_180013BD2
0x180013bae  mov     rax, [rdi+8]
0x180013bb2  mov     rcx, [rax+rbx*8]
0x180013bb6  test    rcx, rcx
0x180013bb9  jz      short loc_180013BCB
0x180013bbb  mov     rax, [rcx]
0x180013bbe  mov     edx, 1
0x180013bc3  mov     rax, [rax]
0x180013bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bcb  inc     ebx
0x180013bcd  cmp     ebx, [rdi+10h]
0x180013bd0  jb      short loc_180013BAE
0x180013bd2  mov     rbx, [rdi+8]
0x180013bd6  call    cs:__imp_GetProcessHeap
0x180013bdc  mov     r8, rbx; lpMem
0x180013bdf  xor     edx, edx; dwFlags
0x180013be1  mov     rcx, rax; hHeap
0x180013be4  call    cs:__imp_HeapFree
0x180013bea  mov     rcx, [rdi+20h]
0x180013bee  test    rcx, rcx
0x180013bf1  jz      short loc_180013C03
0x180013bf3  mov     rax, [rcx]
0x180013bf6  mov     edx, 1
0x180013bfb  mov     rax, [rax]
0x180013bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c03  mov     rcx, rbp; lpCriticalSection
0x180013c06  call    cs:__imp_LeaveCriticalSection
0x180013c0c  mov     rcx, rbp
0x180013c0f  add     rsp, 28h
0x180013c13  pop     rdi
0x180013c14  pop     rsi
0x180013c15  pop     rbp
0x180013c16  pop     rbx
0x180013c17  jmp     cs:__imp_DeleteCriticalSection
```
