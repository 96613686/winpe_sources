# GetObjWithWriteLock

- ea: `0x180001fe4`
- end: `0x180002079`
- name: `GetObjWithWriteLock`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180003310`
- `0x18000381c`

## callees

- `0x180001db4`
- `0x180001de8`
- `0x180001fe4`
- `0x18000257c`
- `0x180007df8`

## string_xrefs

- `0x18000204c`: `GetObjWithWriteLock: bad handle(%p)`

## pseudocode

```c
__int64 __fastcall GetObjWithWriteLock(const void *a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9

  v3 = (unsigned int)a1 >> 1;
  AcquireReadLock(&CriticalSection);
  if ( (unsigned __int16)v3 < (unsigned int)dword_18000E2FC
    && (v5 = (struct _RTL_CRITICAL_SECTION *)((char *)hMem + 80 * (unsigned __int16)v3),
        HIWORD(v3) == LOWORD(v5[1].SpinCount))
    && v5[1].OwningThread )
  {
    AcquireWriteLock(v5);
    result = 0;
    *a2 = *((_QWORD *)hMem + 10 * (unsigned __int16)v3 + 7);
  }
  else
  {
    TspLog(2, "GetObjWithWriteLock: bad handle(%p)", a1);
    ReleaseReadLock(&CriticalSection, v7, v8, v9);
    return 2147483720LL;
  }
  return result;
}

```

## disassembly

```asm
0x180001fe4  push    rbx
0x180001fe6  push    rsi
0x180001fe7  push    rdi
0x180001fe8  push    r14
0x180001fea  sub     rsp, 28h
0x180001fee  mov     ebx, ecx
0x180001ff0  mov     rsi, rcx
0x180001ff3  lea     rcx, CriticalSection
0x180001ffa  shr     ebx, 1
0x180001ffc  mov     r14, rdx
0x180001fff  call    AcquireReadLock
0x180002004  movzx   eax, bx
0x180002007  cmp     eax, cs:dword_18000E2FC
0x18000200d  jnb     short loc_180002049
0x18000200f  mov     rcx, cs:hMem
0x180002016  lea     rdi, [rax+rax*4]
0x18000201a  shl     rdi, 4
0x18000201e  add     rcx, rdi; lpCriticalSection
0x180002021  shr     ebx, 10h
0x180002024  cmp     bx, [rcx+48h]
0x180002028  jnz     short loc_180002049
0x18000202a  cmp     qword ptr [rcx+38h], 0
0x18000202f  jz      short loc_180002049
0x180002031  call    AcquireWriteLock
0x180002036  mov     rax, cs:hMem
0x18000203d  mov     rcx, [rdi+rax+38h]
0x180002042  xor     eax, eax
0x180002044  mov     [r14], rcx
0x180002047  jmp     short loc_18000206E
0x180002049  mov     r8, rsi
0x18000204c  lea     rdx, aGetobjwithwrit; "GetObjWithWriteLock: bad handle(%p)"
0x180002053  mov     ecx, 2
0x180002058  call    TspLog
0x18000205d  lea     rcx, CriticalSection
0x180002064  call    ReleaseReadLock
0x180002069  mov     eax, 80000048h
0x18000206e  add     rsp, 28h
0x180002072  pop     r14
0x180002074  pop     rdi
0x180002075  pop     rsi
0x180002076  pop     rbx
0x180002077  retn
```
