# GetObjWithReadLock

- ea: `0x180001f48`
- end: `0x180001fdd`
- name: `GetObjWithReadLock`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180003294`
- `0x18000338c`
- `0x180003720`
- `0x1800037a8`

## callees

- `0x180001db4`
- `0x180001f48`
- `0x18000257c`
- `0x180007df8`

## string_xrefs

- `0x180001fb0`: `GetObjWithReadLock: bad handle(%p)`

## pseudocode

```c
__int64 __fastcall GetObjWithReadLock(const void *a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  char *v5; // rcx
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9

  v3 = (unsigned int)a1 >> 1;
  AcquireReadLock(&CriticalSection);
  if ( (unsigned __int16)v3 < (unsigned int)dword_18000E2FC
    && (v5 = (char *)hMem + 80 * (unsigned __int16)v3, HIWORD(v3) == *((_WORD *)v5 + 36))
    && *((_QWORD *)v5 + 7) )
  {
    AcquireReadLock(v5);
    result = 0;
    *a2 = *((_QWORD *)hMem + 10 * (unsigned __int16)v3 + 7);
  }
  else
  {
    TspLog(2, "GetObjWithReadLock: bad handle(%p)", a1);
    ReleaseReadLock(&CriticalSection, v7, v8, v9);
    return 2147483720LL;
  }
  return result;
}

```

## disassembly

```asm
0x180001f48  push    rbx
0x180001f4a  push    rsi
0x180001f4b  push    rdi
0x180001f4c  push    r14
0x180001f4e  sub     rsp, 28h
0x180001f52  mov     ebx, ecx
0x180001f54  mov     rsi, rcx
0x180001f57  lea     rcx, CriticalSection
0x180001f5e  shr     ebx, 1
0x180001f60  mov     r14, rdx
0x180001f63  call    AcquireReadLock
0x180001f68  movzx   eax, bx
0x180001f6b  cmp     eax, cs:dword_18000E2FC
0x180001f71  jnb     short loc_180001FAD
0x180001f73  mov     rcx, cs:hMem
0x180001f7a  lea     rdi, [rax+rax*4]
0x180001f7e  shl     rdi, 4
0x180001f82  add     rcx, rdi
0x180001f85  shr     ebx, 10h
0x180001f88  cmp     bx, [rcx+48h]
0x180001f8c  jnz     short loc_180001FAD
0x180001f8e  cmp     qword ptr [rcx+38h], 0
0x180001f93  jz      short loc_180001FAD
0x180001f95  call    AcquireReadLock
0x180001f9a  mov     rax, cs:hMem
0x180001fa1  mov     rcx, [rdi+rax+38h]
0x180001fa6  xor     eax, eax
0x180001fa8  mov     [r14], rcx
0x180001fab  jmp     short loc_180001FD2
0x180001fad  mov     r8, rsi
0x180001fb0  lea     rdx, aGetobjwithread; "GetObjWithReadLock: bad handle(%p)"
0x180001fb7  mov     ecx, 2
0x180001fbc  call    TspLog
0x180001fc1  lea     rcx, CriticalSection
0x180001fc8  call    ReleaseReadLock
0x180001fcd  mov     eax, 80000048h
0x180001fd2  add     rsp, 28h
0x180001fd6  pop     r14
0x180001fd8  pop     rdi
0x180001fd9  pop     rsi
0x180001fda  pop     rbx
0x180001fdb  retn
```
