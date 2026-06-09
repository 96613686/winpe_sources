# HyperVRepository::ClearCachedData(void)

- ea: `0x180092fb4`
- end: `0x180093015`
- name: `?ClearCachedData@HyperVRepository@@AEAAXXZ`
- size: `97`
- prototype: `void __fastcall(HyperVRepository *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180093ae0`

## callees

- `0x180092fb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009300e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180092fcb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180092fcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092fd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092fd1`

## pseudocode

```c
void __fastcall HyperVRepository::ClearCachedData(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  RTL_SRWLOCK *v3; // rcx

  v1 = this + 20;
  AcquireSRWLockExclusive(this + 20);
  LODWORD(v1[1].Ptr) = GetCurrentThreadId();
  v3 = this + 22;
  this[24].Ptr = 0;
  if ( this[25].Ptr > (PVOID)7 )
    v3 = (RTL_SRWLOCK *)v3->Ptr;
  LOWORD(v3->Ptr) = 0;
  LODWORD(v1[1].Ptr) = 0;
  ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x180092fb4  mov     [rsp+arg_8], rbx
0x180092fb9  push    rdi
0x180092fba  sub     rsp, 20h
0x180092fbe  lea     rdi, [rcx+0A0h]
0x180092fc5  mov     rbx, rcx
0x180092fc8  mov     rcx, rdi; SRWLock
0x180092fcb  call    cs:__imp_AcquireSRWLockExclusive
0x180092fd1  call    cs:__imp_GetCurrentThreadId
0x180092fd7  mov     [rdi+8], eax
0x180092fda  lea     rcx, [rbx+0B0h]
0x180092fe1  mov     qword ptr [rbx+0C0h], 0
0x180092fec  cmp     qword ptr [rbx+0C8h], 7
0x180092ff4  jbe     short loc_180092FF9
0x180092ff6  mov     rcx, [rcx]
0x180092ff9  xor     eax, eax
0x180092ffb  mov     [rcx], ax
0x180092ffe  mov     rcx, rdi
0x180093001  mov     [rdi+8], eax
0x180093004  mov     rbx, [rsp+28h+arg_8]
0x180093009  add     rsp, 20h
0x18009300d  pop     rdi
0x18009300e  jmp     cs:__imp_ReleaseSRWLockExclusive
```
