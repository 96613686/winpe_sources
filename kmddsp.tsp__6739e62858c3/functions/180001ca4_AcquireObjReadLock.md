# AcquireObjReadLock

- ea: `0x180001ca4`
- end: `0x180001d25`
- name: `AcquireObjReadLock`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000338c`
- `0x180003ba8`
- `0x1800063b0`

## callees

- `0x180001ca4`
- `0x180001db4`
- `0x18000257c`
- `0x180007df8`

## string_xrefs

- `0x180001cf7`: `AcquireObjReadLock: bad handle(%p)`

## pseudocode

```c
__int64 __fastcall AcquireObjReadLock(const void *a1)
{
  unsigned int v2; // ebx
  char *v3; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9

  v2 = (unsigned int)a1 >> 1;
  AcquireReadLock(&CriticalSection);
  if ( (unsigned __int16)v2 < (unsigned int)dword_18000E2FC
    && (v3 = (char *)hMem + 80 * (unsigned __int16)v2, HIWORD(v2) == *((_WORD *)v3 + 36))
    && *((_QWORD *)v3 + 7) )
  {
    AcquireReadLock(v3);
    return 0;
  }
  else
  {
    TspLog(2, "AcquireObjReadLock: bad handle(%p)", a1);
    ReleaseReadLock(&CriticalSection, v5, v6, v7);
    return 2147483720LL;
  }
}

```

## disassembly

```asm
0x180001ca4  mov     [rsp+arg_0], rbx
0x180001ca9  push    rdi
0x180001caa  sub     rsp, 20h
0x180001cae  mov     ebx, ecx
0x180001cb0  mov     rdi, rcx
0x180001cb3  lea     rcx, CriticalSection
0x180001cba  shr     ebx, 1
0x180001cbc  call    AcquireReadLock
0x180001cc1  movzx   eax, bx
0x180001cc4  cmp     eax, cs:dword_18000E2FC
0x180001cca  jnb     short loc_180001CF4
0x180001ccc  lea     rcx, [rax+rax*4]
0x180001cd0  shr     ebx, 10h
0x180001cd3  shl     rcx, 4
0x180001cd7  add     rcx, cs:hMem
0x180001cde  cmp     bx, [rcx+48h]
0x180001ce2  jnz     short loc_180001CF4
0x180001ce4  cmp     qword ptr [rcx+38h], 0
0x180001ce9  jz      short loc_180001CF4
0x180001ceb  call    AcquireReadLock
0x180001cf0  xor     eax, eax
0x180001cf2  jmp     short loc_180001D19
0x180001cf4  mov     r8, rdi
0x180001cf7  lea     rdx, aAcquireobjread; "AcquireObjReadLock: bad handle(%p)"
0x180001cfe  mov     ecx, 2
0x180001d03  call    TspLog
0x180001d08  lea     rcx, CriticalSection
0x180001d0f  call    ReleaseReadLock
0x180001d14  mov     eax, 80000048h
0x180001d19  mov     rbx, [rsp+28h+arg_0]
0x180001d1e  add     rsp, 20h
0x180001d22  pop     rdi
0x180001d23  retn
```
