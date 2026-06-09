# CScrub::_ReleaseReservedIdlingThread(_SCRUB_THREAD_CONTEXT *,uchar)

- ea: `0x1800288ac`
- end: `0x180028923`
- name: `?_ReleaseReservedIdlingThread@CScrub@@AEAAXPEAU_SCRUB_THREAD_CONTEXT@@E@Z`
- size: `119`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct _SCRUB_THREAD_CONTEXT *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180021730`
- `0x180022450`

## callees

- `0x1800137d4`
- `0x1800288ac`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800288d1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800288d1`

## pseudocode

```c
void __fastcall CScrub::_ReleaseReservedIdlingThread(RTL_SRWLOCK *this, struct _SCRUB_THREAD_CONTEXT *a2, char a3)
{
  char *v3; // rdi
  __int64 v5; // rax
  __int64 v6; // rax
  RTL_SRWLOCK *v7; // [rsp+48h] [rbp+20h] BYREF

  v3 = (char *)&this[173];
  if ( !a3 )
  {
    v7 = this + 184;
    AcquireSRWLockExclusive(this + 184);
    v5 = *(_QWORD *)v3;
    if ( *(char **)(*(_QWORD *)v3 + 8LL) == v3 )
    {
      *(_QWORD *)a2 = v5;
      *((_QWORD *)a2 + 1) = v3;
      *(_QWORD *)(v5 + 8) = a2;
      *(_QWORD *)v3 = a2;
      CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v7);
      return;
    }
LABEL_5:
    __fastfail(3u);
  }
  v6 = *(_QWORD *)v3;
  if ( *(char **)(*(_QWORD *)v3 + 8LL) != v3 )
    goto LABEL_5;
  *(_QWORD *)a2 = v6;
  *((_QWORD *)a2 + 1) = v3;
  *(_QWORD *)(v6 + 8) = a2;
  *(_QWORD *)v3 = a2;
}

```

## disassembly

```asm
0x1800288ac  mov     [rsp+arg_0], rbx
0x1800288b1  push    rdi
0x1800288b2  sub     rsp, 20h
0x1800288b6  lea     rdi, [rcx+568h]
0x1800288bd  mov     rbx, rdx
0x1800288c0  test    r8b, r8b
0x1800288c3  jnz     short loc_1800288FA
0x1800288c5  add     rcx, 5C0h; SRWLock
0x1800288cc  mov     [rsp+28h+arg_18], rcx
0x1800288d1  call    cs:__imp_AcquireSRWLockExclusive
0x1800288d7  mov     rax, [rdi]
0x1800288da  cmp     [rax+8], rdi
0x1800288de  jnz     short loc_180028903
0x1800288e0  mov     [rbx], rax
0x1800288e3  lea     rcx, [rsp+28h+arg_18]; this
0x1800288e8  mov     [rbx+8], rdi
0x1800288ec  mov     [rax+8], rbx
0x1800288f0  mov     [rdi], rbx
0x1800288f3  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x1800288f8  jmp     short loc_180028918
0x1800288fa  mov     rax, [rdi]
0x1800288fd  cmp     [rax+8], rdi
0x180028901  jz      short loc_18002890A
0x180028903  mov     ecx, 3
0x180028908  int     29h; Win8: RtlFailFast(ecx)
0x18002890a  mov     [rdx], rax
0x18002890d  mov     [rdx+8], rdi
0x180028911  mov     [rax+8], rbx
0x180028915  mov     [rdi], rbx
0x180028918  mov     rbx, [rsp+28h+arg_0]
0x18002891d  add     rsp, 20h
0x180028921  pop     rdi
0x180028922  retn
```
