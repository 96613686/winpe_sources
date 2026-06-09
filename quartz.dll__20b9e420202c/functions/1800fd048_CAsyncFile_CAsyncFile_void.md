# CAsyncFile::~CAsyncFile(void)

- ea: `0x1800fd048`
- end: `0x1800fd136`
- name: `??1CAsyncFile@@QEAA@XZ`
- size: `238`
- prototype: `void __fastcall(CAsyncFile *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800fc794`

## callees

- `0x180003808`
- `0x1800135b0`
- `0x18001f290`
- `0x1800241ec`
- `0x180025158`
- `0x1800fd048`
- `0x1800fd13c`
- `0x180139f68`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800fd111`
- `KERNEL32!DeleteCriticalSection` at `0x1800fd111`
- `KERNEL32!DeleteCriticalSection` at `0x1800fd12a`
- `KERNEL32!CloseHandle` at `0x1800fd0a7`
- `KERNEL32!CloseHandle` at `0x1800fd0bd`
- `KERNEL32!CloseHandle` at `0x1800fd0a7`
- `KERNEL32!CloseHandle` at `0x1800fd0bd`

## pseudocode

```c
void __fastcall CAsyncFile::~CAsyncFile(CAsyncFile *this)
{
  CBaseList *v2; // rcx
  void *NextI; // rax
  void *v4; // rcx
  void *v5; // rcx
  struct __POSITION *v6; // [rsp+30h] [rbp+8h] BYREF

  CAsyncFile::BeginFlush(this);
  CAsyncFile::CloseThread(this);
  v6 = (struct __POSITION *)*((_QWORD *)this + 21);
  while ( v6 )
  {
    NextI = CBaseList::GetNextI(v2, &v6);
    operator delete(NextI);
  }
  CBaseList::RemoveAll((CAsyncFile *)((char *)this + 168));
  v4 = (void *)*((_QWORD *)this + 5);
  if ( v4 != (void *)-1LL )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 != (void *)-1LL )
    CloseHandle(v5);
  CAMEvent::~CAMEvent((CAsyncFile *)((char *)this + 240));
  CAMEvent::~CAMEvent((CAsyncFile *)((char *)this + 232));
  CAMEvent::~CAMEvent((CAsyncFile *)((char *)this + 216));
  CAMEvent::~CAMEvent((CAsyncFile *)((char *)this + 208));
  CBaseList::~CBaseList((CAsyncFile *)((char *)this + 168));
  CBaseList::~CBaseList((CAsyncFile *)((char *)this + 128));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x1800fd048  mov     [rsp+arg_8], rbx
0x1800fd04d  push    rdi
0x1800fd04e  sub     rsp, 20h
0x1800fd052  mov     rbx, rcx
0x1800fd055  call    ?BeginFlush@CAsyncFile@@QEAAJXZ; CAsyncFile::BeginFlush(void)
0x1800fd05a  mov     rcx, rbx; this
0x1800fd05d  call    ?CloseThread@CAsyncFile@@AEAAJXZ; CAsyncFile::CloseThread(void)
0x1800fd062  lea     rdi, [rbx+0A8h]
0x1800fd069  mov     rax, [rdi]
0x1800fd06c  mov     [rsp+28h+arg_0], rax
0x1800fd071  test    rax, rax
0x1800fd074  jz      short loc_1800FD095
0x1800fd076  lea     rdx, [rsp+28h+arg_0]; struct __POSITION **
0x1800fd07b  call    ?GetNextI@CBaseList@@IEBAPEAXAEAPEAU__POSITION@@@Z; CBaseList::GetNextI(__POSITION * &)
0x1800fd080  mov     rcx, rax; Block
0x1800fd083  mov     edx, 30h ; '0'
0x1800fd088  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x1800fd08d  cmp     [rsp+28h+arg_0], 0
0x1800fd093  jnz     short loc_1800FD076
0x1800fd095  mov     rcx, rdi; this
0x1800fd098  call    ?RemoveAll@CBaseList@@QEAAXXZ; CBaseList::RemoveAll(void)
0x1800fd09d  mov     rcx, [rbx+28h]; hObject
0x1800fd0a1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800fd0a5  jz      short loc_1800FD0B3
0x1800fd0a7  call    cs:__imp_CloseHandle
0x1800fd0ae  nop     dword ptr [rax+rax+00h]
0x1800fd0b3  mov     rcx, [rbx+30h]; hObject
0x1800fd0b7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800fd0bb  jz      short loc_1800FD0C9
0x1800fd0bd  call    cs:__imp_CloseHandle
0x1800fd0c4  nop     dword ptr [rax+rax+00h]
0x1800fd0c9  lea     rcx, [rbx+0F0h]; this
0x1800fd0d0  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800fd0d5  lea     rcx, [rbx+0E8h]; this
0x1800fd0dc  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800fd0e1  lea     rcx, [rbx+0D8h]; this
0x1800fd0e8  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800fd0ed  lea     rcx, [rbx+0D0h]; this
0x1800fd0f4  call    ??1CAMEvent@@QEAA@XZ; CAMEvent::~CAMEvent(void)
0x1800fd0f9  mov     rcx, rdi; this
0x1800fd0fc  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x1800fd101  lea     rcx, [rbx+80h]; this
0x1800fd108  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x1800fd10d  lea     rcx, [rbx+50h]; lpCriticalSection
0x1800fd111  call    cs:__imp_DeleteCriticalSection
0x1800fd118  nop     dword ptr [rax+rax+00h]
0x1800fd11d  mov     rcx, rbx
0x1800fd120  mov     rbx, [rsp+28h+arg_8]
0x1800fd125  add     rsp, 20h
0x1800fd129  pop     rdi
0x1800fd12a  jmp     cs:__imp_DeleteCriticalSection
```
