# COutputQueue::~COutputQueue(void)

- ea: `0x18001c108`
- end: `0x18001c1d5`
- name: `??1COutputQueue@@QEAA@XZ`
- size: `205`
- prototype: `void __fastcall(COutputQueue *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800081a0`
- `0x18000a7e0`

## callees

- `0x180001008`
- `0x180006f10`
- `0x18001c108`
- `0x18001c28c`
- `0x18001c480`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001c11c`
- `KERNEL32!EnterCriticalSection` at `0x18001c11c`
- `KERNEL32!LeaveCriticalSection` at `0x18001c13b`
- `KERNEL32!LeaveCriticalSection` at `0x18001c13b`
- `KERNEL32!DeleteCriticalSection` at `0x18001c1ce`
- `KERNEL32!CloseHandle` at `0x18001c152`
- `KERNEL32!CloseHandle` at `0x18001c1a3`
- `KERNEL32!CloseHandle` at `0x18001c1bb`
- `KERNEL32!CloseHandle` at `0x18001c152`
- `KERNEL32!CloseHandle` at `0x18001c1a3`
- `KERNEL32!CloseHandle` at `0x18001c1bb`
- `KERNEL32!WaitForSingleObject` at `0x18001c148`
- `KERNEL32!WaitForSingleObject` at `0x18001c148`

## pseudocode

```c
void __fastcall COutputQueue::~COutputQueue(COutputQueue *this)
{
  unsigned __int64 v2; // rdx
  void *v3; // rdi
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  if ( *((_QWORD *)this + 11) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    *((_DWORD *)this + 31) = 1;
    *((_DWORD *)this + 33) = 1;
    COutputQueue::NotifyThread(this);
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 11));
    v3 = (void *)*((_QWORD *)this + 8);
    if ( v3 )
    {
      CBaseList::~CBaseList(*((CBaseList **)this + 8));
      operator delete(v3, 0x28u);
    }
  }
  else
  {
    COutputQueue::FreeSamples(this);
  }
  v4 = *((_QWORD *)this + 6);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 6) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 9);
  if ( v5 )
    CloseHandle(v5);
  operator delete(*((void **)this + 12), v2);
  v6 = (void *)*((_QWORD *)this + 10);
  if ( v6 )
    CloseHandle(v6);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18001c108  mov     [rsp+arg_0], rbx
0x18001c10d  push    rdi
0x18001c10e  sub     rsp, 20h
0x18001c112  cmp     qword ptr [rcx+58h], 0
0x18001c117  mov     rbx, rcx
0x18001c11a  jz      short loc_18001C178
0x18001c11c  call    cs:__imp_EnterCriticalSection
0x18001c122  mov     eax, 1
0x18001c127  mov     rcx, rbx; this
0x18001c12a  mov     [rbx+7Ch], eax
0x18001c12d  mov     [rbx+84h], eax
0x18001c133  call    ?NotifyThread@COutputQueue@@IEAAXXZ; COutputQueue::NotifyThread(void)
0x18001c138  mov     rcx, rbx; lpCriticalSection
0x18001c13b  call    cs:__imp_LeaveCriticalSection
0x18001c141  mov     rcx, [rbx+58h]; hHandle
0x18001c145  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c148  call    cs:__imp_WaitForSingleObject
0x18001c14e  mov     rcx, [rbx+58h]; hObject
0x18001c152  call    cs:__imp_CloseHandle
0x18001c158  mov     rdi, [rbx+40h]
0x18001c15c  test    rdi, rdi
0x18001c15f  jz      short loc_18001C17D
0x18001c161  mov     rcx, rdi; this
0x18001c164  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x18001c169  mov     edx, 28h ; '('; unsigned __int64
0x18001c16e  mov     rcx, rdi; void *
0x18001c171  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c176  jmp     short loc_18001C17D
0x18001c178  call    ?FreeSamples@COutputQueue@@IEAAXXZ; COutputQueue::FreeSamples(void)
0x18001c17d  mov     rcx, [rbx+30h]
0x18001c181  test    rcx, rcx
0x18001c184  jz      short loc_18001C19A
0x18001c186  mov     rax, [rcx]
0x18001c189  mov     rax, [rax+10h]
0x18001c18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c192  mov     qword ptr [rbx+30h], 0
0x18001c19a  mov     rcx, [rbx+48h]; hObject
0x18001c19e  test    rcx, rcx
0x18001c1a1  jz      short loc_18001C1A9
0x18001c1a3  call    cs:__imp_CloseHandle
0x18001c1a9  mov     rcx, [rbx+60h]; void *
0x18001c1ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c1b2  mov     rcx, [rbx+50h]; hObject
0x18001c1b6  test    rcx, rcx
0x18001c1b9  jz      short loc_18001C1C1
0x18001c1bb  call    cs:__imp_CloseHandle
0x18001c1c1  mov     rcx, rbx
0x18001c1c4  mov     rbx, [rsp+28h+arg_0]
0x18001c1c9  add     rsp, 20h
0x18001c1cd  pop     rdi
0x18001c1ce  jmp     cs:__imp_DeleteCriticalSection
```
