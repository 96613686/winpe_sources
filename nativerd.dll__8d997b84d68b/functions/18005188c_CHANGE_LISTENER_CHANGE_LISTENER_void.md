# CHANGE_LISTENER::~CHANGE_LISTENER(void)

- ea: `0x18005188c`
- end: `0x180051924`
- name: `??1CHANGE_LISTENER@@QEAA@XZ`
- size: `152`
- prototype: `void __fastcall(CHANGE_LISTENER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180051c64`

## callees

- `0x18005188c`
- `0x18005192c`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800518a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800518a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800518e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800518e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800518dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800518dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180051916`

## pseudocode

```c
void __fastcall CHANGE_LISTENER::~CHANGE_LISTENER(CHANGE_LISTENER *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  unsigned int v3; // edx
  CHANGE_ENTRY *v4; // rbx
  CHANGE_ENTRY *v5; // rcx
  __int64 v6; // rax
  struct _TP_WORK *v7; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v4 = (CHANGE_LISTENER *)((char *)this + 56);
  while ( 1 )
  {
    v5 = *(CHANGE_ENTRY **)v4;
    if ( *(CHANGE_ENTRY **)(*(_QWORD *)v4 + 8LL) != v4
      || (v6 = *(_QWORD *)v5, *(CHANGE_ENTRY **)(*(_QWORD *)v5 + 8LL) != v5) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)v4 = v6;
    *(_QWORD *)(v6 + 8) = v4;
    if ( v5 == v4 )
      break;
    if ( v5 )
      CHANGE_ENTRY::`scalar deleting destructor'(v5, v3);
  }
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
  v7 = (struct _TP_WORK *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 9) = 0;
  CloseThreadpoolWork(v7);
}

```

## disassembly

```asm
0x18005188c  mov     [rsp+arg_0], rbx
0x180051891  mov     [rsp+arg_8], rsi
0x180051896  push    rdi
0x180051897  sub     rsp, 20h
0x18005189b  lea     rsi, [rcx+8]
0x18005189f  mov     rdi, rcx
0x1800518a2  mov     rcx, rsi; lpCriticalSection
0x1800518a5  call    cs:__imp_EnterCriticalSection
0x1800518ab  lea     rbx, [rdi+38h]
0x1800518af  mov     rcx, [rbx]; this
0x1800518b2  cmp     [rcx+8], rbx
0x1800518b6  jnz     short loc_18005191D
0x1800518b8  mov     rax, [rcx]
0x1800518bb  cmp     [rax+8], rcx
0x1800518bf  jnz     short loc_18005191D
0x1800518c1  mov     [rbx], rax
0x1800518c4  mov     [rax+8], rbx
0x1800518c8  cmp     rcx, rbx
0x1800518cb  jz      short loc_1800518D9
0x1800518cd  test    rcx, rcx
0x1800518d0  jz      short loc_1800518AF
0x1800518d2  call    ??_GCHANGE_ENTRY@@QEAAPEAXI@Z; CHANGE_ENTRY::`scalar deleting destructor'(uint)
0x1800518d7  jmp     short loc_1800518AF
0x1800518d9  mov     rcx, rsi; lpCriticalSection
0x1800518dc  call    cs:__imp_LeaveCriticalSection
0x1800518e2  mov     rcx, rsi; lpCriticalSection
0x1800518e5  call    cs:__imp_DeleteCriticalSection
0x1800518eb  mov     rcx, [rdi+48h]
0x1800518ef  mov     rax, [rcx]
0x1800518f2  mov     rax, [rax+10h]
0x1800518f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800518fb  mov     rcx, [rdi+50h]
0x1800518ff  mov     qword ptr [rdi+48h], 0
0x180051907  mov     rbx, [rsp+28h+arg_0]
0x18005190c  mov     rsi, [rsp+28h+arg_8]
0x180051911  add     rsp, 20h
0x180051915  pop     rdi
0x180051916  jmp     cs:__imp_CloseThreadpoolWork
0x18005191d  mov     ecx, 3
0x180051922  int     29h; Win8: RtlFailFast(ecx)
```
