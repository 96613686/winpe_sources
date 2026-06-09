# AcquireObjWriteLock

- ea: `0x180001d2c`
- end: `0x180001dad`
- name: `AcquireObjWriteLock`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003ba8`
- `0x180004670`
- `0x180004d30`

## callees

- `0x180001d2c`
- `0x180001db4`
- `0x180001de8`
- `0x18000257c`
- `0x180007df8`

## string_xrefs

- `0x180001d7f`: `AcquireObjWriteLock: bad handle(%p)`

## pseudocode

```c
__int64 __fastcall AcquireObjWriteLock(const void *a1)
{
  unsigned int v2; // ebx
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9

  v2 = (unsigned int)a1 >> 1;
  AcquireReadLock(&CriticalSection);
  if ( (unsigned __int16)v2 < (unsigned int)dword_18000E2FC
    && (v3 = (struct _RTL_CRITICAL_SECTION *)((char *)hMem + 80 * (unsigned __int16)v2),
        HIWORD(v2) == LOWORD(v3[1].SpinCount))
    && v3[1].OwningThread )
  {
    AcquireWriteLock(v3);
    return 0;
  }
  else
  {
    TspLog(2, "AcquireObjWriteLock: bad handle(%p)", a1);
    ReleaseReadLock(&CriticalSection, v5, v6, v7);
    return 2147483720LL;
  }
}

```

## disassembly

```asm
0x180001d2c  mov     [rsp+arg_0], rbx
0x180001d31  push    rdi
0x180001d32  sub     rsp, 20h
0x180001d36  mov     ebx, ecx
0x180001d38  mov     rdi, rcx
0x180001d3b  lea     rcx, CriticalSection
0x180001d42  shr     ebx, 1
0x180001d44  call    AcquireReadLock
0x180001d49  movzx   eax, bx
0x180001d4c  cmp     eax, cs:dword_18000E2FC
0x180001d52  jnb     short loc_180001D7C
0x180001d54  lea     rcx, [rax+rax*4]
0x180001d58  shr     ebx, 10h
0x180001d5b  shl     rcx, 4
0x180001d5f  add     rcx, cs:hMem; lpCriticalSection
0x180001d66  cmp     bx, [rcx+48h]
0x180001d6a  jnz     short loc_180001D7C
0x180001d6c  cmp     qword ptr [rcx+38h], 0
0x180001d71  jz      short loc_180001D7C
0x180001d73  call    AcquireWriteLock
0x180001d78  xor     eax, eax
0x180001d7a  jmp     short loc_180001DA1
0x180001d7c  mov     r8, rdi
0x180001d7f  lea     rdx, aAcquireobjwrit; "AcquireObjWriteLock: bad handle(%p)"
0x180001d86  mov     ecx, 2
0x180001d8b  call    TspLog
0x180001d90  lea     rcx, CriticalSection
0x180001d97  call    ReleaseReadLock
0x180001d9c  mov     eax, 80000048h
0x180001da1  mov     rbx, [rsp+28h+arg_0]
0x180001da6  add     rsp, 20h
0x180001daa  pop     rdi
0x180001dab  retn
```
