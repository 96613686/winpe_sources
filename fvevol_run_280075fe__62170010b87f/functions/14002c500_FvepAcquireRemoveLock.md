# FvepAcquireRemoveLock

- ea: `0x14002c500`
- end: `0x14002c5ee`
- name: `FvepAcquireRemoveLock`
- size: `238`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400567d0`
- `0x14006cfc8`
- `0x1400769d4`
- `0x14007d31c`
- `0x14007dbf0`
- `0x14007ea40`
- `0x140085180`
- `0x140091220`
- `0x1400bd230`
- `0x1400c0ec0`
- `0x1400d9cc8`

## callees

- `0x14002c500`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002c522`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002c522`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14002c565`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14002c565`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002c5d8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002c5d8`
- `ntoskrnl!KeBugCheckEx` at `0x14002c5ba`
- `ntoskrnl!KeBugCheckEx` at `0x14002c5ba`

## pseudocode

```c
__int64 __fastcall FvepAcquireRemoveLock(ULONG_PTR BugCheckParameter2)
{
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v2; // rcx
  ULONG_PTR v3; // rbx
  signed __int64 v5; // rax
  signed __int64 v6; // [rsp+48h] [rbp+10h]

  v2 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(BugCheckParameter2 + 48);
  if ( !v2 )
  {
    v3 = IoAcquireRemoveLockEx(
           (PIO_REMOVE_LOCK)(BugCheckParameter2 + 16),
           *(PVOID *)BugCheckParameter2,
           File,
           1u,
           0x20u);
    while ( 1 )
    {
      v6 = *(_QWORD *)(BugCheckParameter2 + 8);
      v5 = v6;
      if ( (v6 & 0xFF000000000000LL) != 0 )
        break;
      if ( (_DWORD)v3 )
        KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, v3, (unsigned int)v6);
      LODWORD(v6) = v6 + 1;
      if ( v5 == _InterlockedCompareExchange64((volatile signed __int64 *)(BugCheckParameter2 + 8), v6, v5) )
        return (unsigned int)v3;
    }
    if ( !(_DWORD)v3 )
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(BugCheckParameter2 + 16), *(PVOID *)BugCheckParameter2, 0x20u);
    goto LABEL_12;
  }
  LODWORD(v3) = 0;
  if ( !ExAcquireRundownProtectionCacheAware(v2) )
LABEL_12:
    LODWORD(v3) = -1073741738;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002c500  mov     [rsp+arg_0], rbx
0x14002c505  mov     [rsp+arg_10], rsi
0x14002c50a  mov     [rsp+arg_8], rdx
0x14002c50f  push    rdi
0x14002c510  sub     rsp, 30h
0x14002c514  mov     rdi, rcx
0x14002c517  mov     rcx, [rcx+30h]; RunRefCacheAware
0x14002c51b  test    rcx, rcx
0x14002c51e  jz      short loc_14002C549
0x14002c520  xor     ebx, ebx
0x14002c522  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002c529  nop     dword ptr [rax+rax+00h]
0x14002c52e  test    al, al
0x14002c530  jz      loc_14002C5E4
0x14002c536  mov     rsi, [rsp+38h+arg_10]
0x14002c53b  mov     eax, ebx
0x14002c53d  mov     rbx, [rsp+38h+arg_0]
0x14002c542  add     rsp, 30h
0x14002c546  pop     rdi
0x14002c547  retn
0x14002c549  mov     rdx, [rdi]; Tag
0x14002c54c  lea     r8, File; File
0x14002c553  mov     r9d, 1; Line
0x14002c559  mov     [rsp+38h+RemlockSize], 20h ; ' '; RemlockSize
0x14002c561  lea     rcx, [rdi+10h]; RemoveLock
0x14002c565  call    cs:__imp_IoAcquireRemoveLockEx
0x14002c56c  nop     dword ptr [rax+rax+00h]
0x14002c571  movsxd  rbx, eax
0x14002c574  mov     rax, [rdi+8]
0x14002c578  mov     rcx, rax
0x14002c57b  mov     [rsp+38h+arg_8], rax
0x14002c580  shr     rcx, 20h
0x14002c584  test    ecx, 0FF0000h
0x14002c58a  jnz     short loc_14002C5C7
0x14002c58c  test    ebx, ebx
0x14002c58e  jnz     short loc_14002C5A3
0x14002c590  inc     dword ptr [rsp+38h+arg_8]
0x14002c594  mov     rcx, [rsp+38h+arg_8]
0x14002c599  lock cmpxchg [rdi+8], rcx
0x14002c59f  jz      short loc_14002C536
0x14002c5a1  jmp     short loc_14002C574
0x14002c5a3  mov     eax, eax
0x14002c5a5  mov     r9, rbx; BugCheckParameter3
0x14002c5a8  mov     r8, rdi; BugCheckParameter2
0x14002c5ab  mov     qword ptr [rsp+38h+RemlockSize], rax; BugCheckParameter4
0x14002c5b0  mov     edx, 0Eh; BugCheckParameter1
0x14002c5b5  mov     ecx, 120h; BugCheckCode
0x14002c5ba  call    cs:__imp_KeBugCheckEx
0x14002c5c7  test    ebx, ebx
0x14002c5c9  jnz     short loc_14002C5E4
0x14002c5cb  mov     rdx, [rdi]; Tag
0x14002c5ce  lea     rcx, [rdi+10h]; RemoveLock
0x14002c5d2  mov     r8d, 20h ; ' '; RemlockSize
0x14002c5d8  call    cs:__imp_IoReleaseRemoveLockEx
0x14002c5df  nop     dword ptr [rax+rax+00h]
0x14002c5e4  mov     ebx, 0C0000056h
0x14002c5e9  jmp     loc_14002C536
```
