# CConnectionPoint::~CConnectionPoint(void)

- ea: `0x18005af50`
- end: `0x18005afd6`
- name: `??1CConnectionPoint@@QEAA@XZ`
- size: `134`
- prototype: `void __fastcall(CConnectionPoint *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18004d29c`

## callees

- `0x180042bd0`
- `0x18005af50`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005af6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005af6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005afbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005afbe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005afc7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005afc7`

## pseudocode

```c
void __fastcall CConnectionPoint::~CConnectionPoint(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  HANDLE LockSemaphore; // rcx
  _QWORD *OwningThread; // rbp
  _QWORD *v5; // rbx

  v2 = this + 1;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CConnectionPoint::`vftable';
  EnterCriticalSection(this + 1);
  LockSemaphore = this->LockSemaphore;
  if ( LockSemaphore )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)LockSemaphore + 16LL))(LockSemaphore);
  OwningThread = this->OwningThread;
  while ( OwningThread )
  {
    v5 = OwningThread;
    OwningThread = (_QWORD *)OwningThread[2];
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
    operator delete(v5, 0x18u);
  }
  if ( LODWORD(this->SpinCount) )
  {
    LeaveCriticalSection(v2);
    DeleteCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x18005af50  push    rbx
0x18005af52  push    rbp
0x18005af53  push    rsi
0x18005af54  push    rdi
0x18005af55  sub     rsp, 28h
0x18005af59  lea     rax, ??_7CConnectionPoint@@6B@; const CConnectionPoint::`vftable'
0x18005af60  mov     rdi, rcx
0x18005af63  lea     rsi, [rcx+28h]
0x18005af67  mov     [rcx], rax
0x18005af6a  mov     rcx, rsi; lpCriticalSection
0x18005af6d  call    cs:__imp_EnterCriticalSection
0x18005af73  mov     rcx, [rdi+18h]
0x18005af77  test    rcx, rcx
0x18005af7a  jz      short loc_18005AF88
0x18005af7c  mov     rax, [rcx]
0x18005af7f  mov     rax, [rax+10h]
0x18005af83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005af88  mov     rbp, [rdi+10h]
0x18005af8c  jmp     short loc_18005AFB1
0x18005af8e  mov     rbx, rbp
0x18005af91  mov     rbp, [rbp+10h]
0x18005af95  mov     rcx, [rbx]
0x18005af98  mov     rax, [rcx]
0x18005af9b  mov     rax, [rax+10h]
0x18005af9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005afa4  mov     edx, 18h; unsigned __int64
0x18005afa9  mov     rcx, rbx; void *
0x18005afac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005afb1  test    rbp, rbp
0x18005afb4  jnz     short loc_18005AF8E
0x18005afb6  cmp     [rdi+20h], ebp
0x18005afb9  jz      short loc_18005AFCD
0x18005afbb  mov     rcx, rsi; lpCriticalSection
0x18005afbe  call    cs:__imp_LeaveCriticalSection
0x18005afc4  mov     rcx, rsi; lpCriticalSection
0x18005afc7  call    cs:__imp_DeleteCriticalSection
0x18005afcd  add     rsp, 28h
0x18005afd1  pop     rdi
0x18005afd2  pop     rsi
0x18005afd3  pop     rbp
0x18005afd4  pop     rbx
0x18005afd5  retn
```
