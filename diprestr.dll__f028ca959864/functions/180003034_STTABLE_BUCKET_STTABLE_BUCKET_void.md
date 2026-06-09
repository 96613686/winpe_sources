# STTABLE_BUCKET::~STTABLE_BUCKET(void)

- ea: `0x180003034`
- end: `0x1800030ae`
- name: `??1STTABLE_BUCKET@@UEAA@XZ`
- size: `122`
- prototype: `void __fastcall(STTABLE_BUCKET *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003180`

## callees

- `0x180003034`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003093`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003093`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000309d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000309d`

## pseudocode

```c
void __fastcall STTABLE_BUCKET::~STTABLE_BUCKET(struct _RTL_CRITICAL_SECTION *this)
{
  LONG *p_LockCount; // rdi
  __int64 v3; // rax
  volatile signed __int32 *v4; // rcx
  __int64 *v5; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&STTABLE_BUCKET::`vftable';
  p_LockCount = &this->LockCount;
  while ( 1 )
  {
    v5 = *(__int64 **)p_LockCount;
    if ( *(LONG **)p_LockCount == p_LockCount )
      break;
    v3 = *v5;
    v4 = (volatile signed __int32 *)(v5 - 1);
    *(_QWORD *)p_LockCount = v3;
    *(_QWORD *)(v3 + 8) = p_LockCount;
    if ( _InterlockedExchangeAdd(v4 + 6, 0xFFFFFFFF) == 1 && v4 )
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v4)(v4, 1);
  }
  if ( LODWORD(this->LockSemaphore) )
  {
    DeleteCriticalSection(this + 1);
    CloseHandle(this[2].DebugInfo);
  }
}

```

## disassembly

```asm
0x180003034  mov     [rsp+arg_8], rbx
0x180003039  push    rdi
0x18000303a  sub     rsp, 20h
0x18000303e  lea     rax, ??_7STTABLE_BUCKET@@6B@; const STTABLE_BUCKET::`vftable'
0x180003045  mov     rbx, rcx
0x180003048  mov     [rcx], rax
0x18000304b  lea     rdi, [rcx+8]
0x18000304f  jmp     short loc_180003081
0x180003051  mov     rax, [rcx]
0x180003054  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180003058  mov     [rdi], rax
0x18000305b  mov     [rax+8], rdi
0x18000305f  or      eax, 0FFFFFFFFh
0x180003062  lock xadd [rcx+18h], eax
0x180003067  cmp     eax, 1
0x18000306a  jnz     short loc_180003081
0x18000306c  test    rcx, rcx
0x18000306f  jz      short loc_180003081
0x180003071  mov     rax, [rcx]
0x180003074  mov     edx, 1
0x180003079  mov     rax, [rax]
0x18000307c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003081  mov     rcx, [rdi]
0x180003084  cmp     rcx, rdi
0x180003087  jnz     short loc_180003051
0x180003089  cmp     dword ptr [rbx+18h], 0
0x18000308d  jz      short loc_1800030A3
0x18000308f  lea     rcx, [rbx+28h]; lpCriticalSection
0x180003093  call    cs:__imp_DeleteCriticalSection
0x180003099  mov     rcx, [rbx+50h]; hObject
0x18000309d  call    cs:__imp_CloseHandle
0x1800030a3  mov     rbx, [rsp+28h+arg_8]
0x1800030a8  add     rsp, 20h
0x1800030ac  pop     rdi
0x1800030ad  retn
```
