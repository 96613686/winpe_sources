# CloseObjHandle

- ea: `0x180001e40`
- end: `0x180001f3f`
- name: `CloseObjHandle`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180003ba8`
- `0x180004520`
- `0x180004670`
- `0x1800063b0`
- `0x1800066e0`
- `0x180006a20`

## callees

- `0x180001de8`
- `0x180001e40`
- `0x1800025c4`
- `0x180007df8`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CloseObjHandle(const void *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rcx

  v2 = (unsigned int)a1 >> 1;
  AcquireWriteLock(&CriticalSection);
  if ( (unsigned __int16)v2 < (unsigned int)dword_18000E2FC
    && (v3 = 80LL * (unsigned __int16)v2,
        v4 = (struct _RTL_CRITICAL_SECTION *)((char *)hMem + v3),
        HIWORD(v2) == *(_WORD *)((char *)hMem + v3 + 72))
    && v4[1].OwningThread )
  {
    AcquireWriteLock(v4);
    (*(void (__fastcall **)(_QWORD))((char *)hMem + v3 + 64))(*(_QWORD *)((char *)hMem + v3 + 56));
    *(_QWORD *)((char *)hMem + v3 + 56) = 0;
    *(_QWORD *)((char *)hMem + v3 + 64) = 0;
    *(_WORD *)((char *)hMem + v3 + 72) = 0;
    *(_WORD *)((char *)hMem + v3 + 74) = HIWORD(dword_18000E2F8);
    ++dword_18000E300;
    HIWORD(dword_18000E2F8) = v2;
    ReleaseWriteLock((struct _RTL_CRITICAL_SECTION *)((char *)hMem + v3));
    ReleaseWriteLock(&CriticalSection);
    return 0;
  }
  else
  {
    TspLog(2, "CloseObjHandle: bad handle(%p)", a1);
    ReleaseWriteLock(&CriticalSection);
    return 2147483720LL;
  }
}

```

## disassembly

```asm
0x180001e40  push    rbx
0x180001e42  push    rbp
0x180001e43  push    rsi
0x180001e44  push    rdi
0x180001e45  sub     rsp, 28h
0x180001e49  mov     ebx, ecx
0x180001e4b  mov     rbp, rcx
0x180001e4e  lea     rcx, CriticalSection; lpCriticalSection
0x180001e55  shr     ebx, 1
0x180001e57  call    AcquireWriteLock
0x180001e5c  movzx   esi, bx
0x180001e5f  cmp     esi, cs:dword_18000E2FC
0x180001e65  jnb     loc_180001F10
0x180001e6b  mov     rcx, cs:hMem
0x180001e72  lea     rdi, [rsi+rsi*4]
0x180001e76  shl     rdi, 4
0x180001e7a  add     rcx, rdi; lpCriticalSection
0x180001e7d  shr     ebx, 10h
0x180001e80  cmp     bx, [rcx+48h]
0x180001e84  jnz     loc_180001F10
0x180001e8a  xor     ebx, ebx
0x180001e8c  cmp     [rcx+38h], rbx
0x180001e90  jz      short loc_180001F10
0x180001e92  call    AcquireWriteLock
0x180001e97  mov     rax, cs:hMem
0x180001e9e  mov     rcx, [rdi+rax+38h]
0x180001ea3  mov     rax, [rdi+rax+40h]
0x180001ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ead  mov     rax, cs:hMem
0x180001eb4  mov     [rdi+rax+38h], rbx
0x180001eb9  mov     rax, cs:hMem
0x180001ec0  mov     [rdi+rax+40h], rbx
0x180001ec5  mov     rax, cs:hMem
0x180001ecc  mov     [rdi+rax+48h], bx
0x180001ed1  movzx   eax, word ptr cs:dword_18000E2F8+2
0x180001ed8  mov     rdx, cs:hMem
0x180001edf  mov     [rdi+rdx+4Ah], ax
0x180001ee4  mov     rcx, cs:hMem
0x180001eeb  inc     cs:dword_18000E300
0x180001ef1  add     rcx, rdi
0x180001ef4  mov     word ptr cs:dword_18000E2F8+2, si
0x180001efb  call    ReleaseWriteLock
0x180001f00  lea     rcx, CriticalSection
0x180001f07  call    ReleaseWriteLock
0x180001f0c  xor     eax, eax
0x180001f0e  jmp     short loc_180001F35
0x180001f10  mov     r8, rbp
0x180001f13  lea     rdx, aCloseobjhandle; "CloseObjHandle: bad handle(%p)"
0x180001f1a  mov     ecx, 2
0x180001f1f  call    TspLog
0x180001f24  lea     rcx, CriticalSection
0x180001f2b  call    ReleaseWriteLock
0x180001f30  mov     eax, 80000048h
0x180001f35  add     rsp, 28h
0x180001f39  pop     rdi
0x180001f3a  pop     rsi
0x180001f3b  pop     rbp
0x180001f3c  pop     rbx
0x180001f3d  retn
```
