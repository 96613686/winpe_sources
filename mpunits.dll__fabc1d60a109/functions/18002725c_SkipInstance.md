# SkipInstance

- ea: `0x18002725c`
- end: `0x1800272b4`
- name: `SkipInstance`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026e78`

## callees

- `0x18002725c`

## import_xrefs

- `msvcrt!_read` at `0x18002727c`
- `msvcrt!_read` at `0x18002727c`
- `msvcrt!_lseeki64` at `0x180027296`
- `msvcrt!_lseeki64` at `0x180027296`

## pseudocode

```c
_BOOL8 __fastcall SkipInstance(__int64 a1)
{
  __int64 DstBuf; // [rsp+30h] [rbp+8h] BYREF

  DstBuf = 0;
  return _read(*(_DWORD *)(a1 + 4), &DstBuf, 8u) != 8 || _lseeki64(*(_DWORD *)(a1 + 4), HIDWORD(DstBuf) - 8LL, 1) == -1;
}

```

## disassembly

```asm
0x18002725c  push    rbx
0x18002725e  sub     rsp, 20h
0x180027262  mov     rbx, rcx
0x180027265  mov     [rsp+28h+DstBuf], 0
0x18002726e  mov     ecx, [rcx+4]; FileHandle
0x180027271  lea     rdx, [rsp+28h+DstBuf]; DstBuf
0x180027276  mov     r8d, 8; MaxCharCount
0x18002727c  call    cs:__imp__read
0x180027282  cmp     eax, 8
0x180027285  jnz     short loc_1800272A9
0x180027287  mov     edx, dword ptr [rsp+28h+DstBuf+4]
0x18002728b  lea     r8d, [rax-7]; Origin
0x18002728f  mov     ecx, [rbx+4]; FileHandle
0x180027292  sub     rdx, 8; Offset
0x180027296  call    cs:__imp__lseeki64
0x18002729c  xor     ecx, ecx
0x18002729e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800272a2  setz    cl
0x1800272a5  mov     eax, ecx
0x1800272a7  jmp     short loc_1800272AE
0x1800272a9  mov     eax, 1
0x1800272ae  add     rsp, 20h
0x1800272b2  pop     rbx
0x1800272b3  retn
```
