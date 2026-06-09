# SEND_QUEUE::~SEND_QUEUE(void)

- ea: `0x180001cc4`
- end: `0x180001d48`
- name: `??1SEND_QUEUE@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(SEND_QUEUE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d50`

## callees

- `0x180001cc4`
- `0x180001d84`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001d1f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001d1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d31`

## pseudocode

```c
void __fastcall SEND_QUEUE::~SEND_QUEUE(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  if ( LODWORD(this[2].DebugInfo) )
    SEND_QUEUE::Empty((SEND_QUEUE *)this, 0, 0);
  if ( this->DebugInfo )
  {
    (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)this->DebugInfo + 16LL))(this->DebugInfo);
    this->DebugInfo = 0;
  }
  v2 = *(_QWORD *)&this->LockCount;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)&this->LockCount = 0;
  }
  if ( LODWORD(this[2].DebugInfo) )
    DeleteCriticalSection(this + 1);
  v3 = *(void **)&this[3].LockCount;
  if ( v3 )
  {
    CloseHandle(v3);
    *(_QWORD *)&this[3].LockCount = 0;
  }
}

```

## disassembly

```asm
0x180001cc4  push    rbx
0x180001cc6  sub     rsp, 20h
0x180001cca  cmp     dword ptr [rcx+50h], 0
0x180001cce  mov     rbx, rcx
0x180001cd1  jz      short loc_180001CDD
0x180001cd3  xor     r8d, r8d; int
0x180001cd6  xor     edx, edx; int
0x180001cd8  call    ?Empty@SEND_QUEUE@@QEAAJHH@Z; SEND_QUEUE::Empty(int,int)
0x180001cdd  mov     rcx, [rbx]
0x180001ce0  test    rcx, rcx
0x180001ce3  jz      short loc_180001CF8
0x180001ce5  mov     rax, [rcx]
0x180001ce8  mov     rax, [rax+10h]
0x180001cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cf1  mov     qword ptr [rbx], 0
0x180001cf8  mov     rcx, [rbx+8]
0x180001cfc  test    rcx, rcx
0x180001cff  jz      short loc_180001D15
0x180001d01  mov     rax, [rcx]
0x180001d04  mov     rax, [rax+10h]
0x180001d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0d  mov     qword ptr [rbx+8], 0
0x180001d15  cmp     dword ptr [rbx+50h], 0
0x180001d19  jz      short loc_180001D25
0x180001d1b  lea     rcx, [rbx+28h]; lpCriticalSection
0x180001d1f  call    cs:__imp_DeleteCriticalSection
0x180001d25  mov     rcx, [rbx+80h]; hObject
0x180001d2c  test    rcx, rcx
0x180001d2f  jz      short loc_180001D42
0x180001d31  call    cs:__imp_CloseHandle
0x180001d37  mov     qword ptr [rbx+80h], 0
0x180001d42  add     rsp, 20h
0x180001d46  pop     rbx
0x180001d47  retn
```
