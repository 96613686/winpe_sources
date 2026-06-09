# CLinkedList::~CLinkedList(void)

- ea: `0x18003b4ec`
- end: `0x18003b555`
- name: `??1CLinkedList@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(void (**this)(void))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003b39c`

## callees

- `0x18003b4ec`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b52e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b52e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b506`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b506`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b53d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003b53d`

## pseudocode

```c
void __fastcall CLinkedList::~CLinkedList(void (**this)(void))
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  if ( *((_DWORD *)this + 2) )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
    EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
    while ( *this )
    {
      *this = *(void (**)(void))*this;
      this[8]();
    }
    LeaveCriticalSection(v2);
    DeleteCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x18003b4ec  mov     [rsp+arg_0], rbx
0x18003b4f1  push    rdi
0x18003b4f2  sub     rsp, 20h
0x18003b4f6  cmp     dword ptr [rcx+8], 0
0x18003b4fa  mov     rbx, rcx
0x18003b4fd  jz      short loc_18003B549
0x18003b4ff  lea     rdi, [rcx+10h]
0x18003b503  mov     rcx, rdi; lpCriticalSection
0x18003b506  call    cs:__imp_EnterCriticalSection
0x18003b50d  nop     dword ptr [rax+rax+00h]
0x18003b512  jmp     short loc_18003B523
0x18003b514  mov     rax, [rcx]
0x18003b517  mov     [rbx], rax
0x18003b51a  mov     rax, [rbx+40h]
0x18003b51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b523  mov     rcx, [rbx]
0x18003b526  test    rcx, rcx
0x18003b529  jnz     short loc_18003B514
0x18003b52b  mov     rcx, rdi; lpCriticalSection
0x18003b52e  call    cs:__imp_LeaveCriticalSection
0x18003b535  nop     dword ptr [rax+rax+00h]
0x18003b53a  mov     rcx, rdi; lpCriticalSection
0x18003b53d  call    cs:__imp_DeleteCriticalSection
0x18003b544  nop     dword ptr [rax+rax+00h]
0x18003b549  mov     rbx, [rsp+28h+arg_0]
0x18003b54e  add     rsp, 20h
0x18003b552  pop     rdi
0x18003b553  retn
```
