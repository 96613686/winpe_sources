# PAL_System_SemaphoreAlloc

- ea: `0x18001f3b8`
- end: `0x18001f3f5`
- name: `PAL_System_SemaphoreAlloc`
- size: `61`
- prototype: `__int64 __fastcall(LONG lInitialCount)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800251d0`
- `0x1800252e0`
- `0x1800253f0`

## callees

- `0x18001f3b8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18001f3da`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18001f3da`

## pseudocode

```c
__int64 __fastcall PAL_System_SemaphoreAlloc(LONG lInitialCount, _QWORD *a2)
{
  HANDLE SemaphoreW; // rax

  if ( !a2 )
    return 2147942487LL;
  SemaphoreW = CreateSemaphoreW(0, lInitialCount, 0x7FFFFFFF, 0);
  *a2 = SemaphoreW;
  return SemaphoreW == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18001f3b8  push    rbx
0x18001f3ba  sub     rsp, 20h
0x18001f3be  mov     rbx, rdx
0x18001f3c1  test    rdx, rdx
0x18001f3c4  jnz     short loc_18001F3CD
0x18001f3c6  mov     eax, 80070057h
0x18001f3cb  jmp     short loc_18001F3EF
0x18001f3cd  mov     edx, ecx; lInitialCount
0x18001f3cf  xor     r9d, r9d; lpName
0x18001f3d2  xor     ecx, ecx; lpSemaphoreAttributes
0x18001f3d4  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18001f3da  call    cs:__imp_CreateSemaphoreW
0x18001f3e0  mov     [rbx], rax
0x18001f3e3  neg     rax
0x18001f3e6  sbb     eax, eax
0x18001f3e8  not     eax
0x18001f3ea  and     eax, 80004005h
0x18001f3ef  add     rsp, 20h
0x18001f3f3  pop     rbx
0x18001f3f4  retn
```
