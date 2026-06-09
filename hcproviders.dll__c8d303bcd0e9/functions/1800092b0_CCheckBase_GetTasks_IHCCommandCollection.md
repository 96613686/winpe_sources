# CCheckBase::GetTasks(IHCCommandCollection * *)

- ea: `0x1800092b0`
- end: `0x180009324`
- name: `?GetTasks@CCheckBase@@UEAAJPEAPEAUIHCCommandCollection@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(CCheckBase *__hidden this, struct IHCCommandCollection **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800092b0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009305`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009305`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800092cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800092cc`

## pseudocode

```c
__int64 __fastcall CCheckBase::GetTasks(RTL_SRWLOCK *this, struct IHCCommandCollection **a2)
{
  RTL_SRWLOCK *v2; // rdi
  __int64 (__fastcall ***Ptr)(_QWORD, GUID *, struct IHCCommandCollection **); // rcx
  unsigned int v6; // ebx

  v2 = this + 2;
  AcquireSRWLockShared(this + 2);
  Ptr = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IHCCommandCollection **))this[24].Ptr;
  v6 = 0;
  if ( Ptr )
    v6 = (**Ptr)(Ptr, &GUID_58d879fe_5b40_46aa_ab68_d146ff6a68a0, a2);
  else
    *a2 = 0;
  ReleaseSRWLockShared(v2);
  return v6;
}

```

## disassembly

```asm
0x1800092b0  mov     [rsp+arg_0], rbx
0x1800092b5  mov     [rsp+arg_8], rsi
0x1800092ba  push    rdi
0x1800092bb  sub     rsp, 20h
0x1800092bf  lea     rdi, [rcx+10h]
0x1800092c3  mov     rbx, rcx
0x1800092c6  mov     rcx, rdi; SRWLock
0x1800092c9  mov     rsi, rdx
0x1800092cc  call    cs:__imp_AcquireSRWLockShared
0x1800092d3  nop     dword ptr [rax+rax+00h]
0x1800092d8  mov     rcx, [rbx+0C0h]
0x1800092df  xor     ebx, ebx
0x1800092e1  test    rcx, rcx
0x1800092e4  jz      short loc_1800092FF
0x1800092e6  mov     rax, [rcx]
0x1800092e9  lea     rdx, _GUID_58d879fe_5b40_46aa_ab68_d146ff6a68a0
0x1800092f0  mov     r8, rsi
0x1800092f3  mov     rax, [rax]
0x1800092f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092fb  mov     ebx, eax
0x1800092fd  jmp     short loc_180009302
0x1800092ff  mov     [rsi], rbx
0x180009302  mov     rcx, rdi; SRWLock
0x180009305  call    cs:__imp_ReleaseSRWLockShared
0x18000930c  nop     dword ptr [rax+rax+00h]
0x180009311  mov     rsi, [rsp+28h+arg_8]
0x180009316  mov     eax, ebx
0x180009318  mov     rbx, [rsp+28h+arg_0]
0x18000931d  add     rsp, 20h
0x180009321  pop     rdi
0x180009322  retn
```
