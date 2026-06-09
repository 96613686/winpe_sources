# DevAuthGenerateRandomNumber

- ea: `0x1800026e8`
- end: `0x180002737`
- name: `DevAuthGenerateRandomNumber`
- size: `79`
- prototype: `__int64 __fastcall(void *, size_t Size)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e04`
- `0x180002348`
- `0x180003e20`

## callees

- `0x1800026e8`
- `0x180006cc0`

## import_xrefs

- `cng!BCryptGenRandom` at `0x180002705`
- `cng!BCryptGenRandom` at `0x180002705`

## pseudocode

```c
__int64 __fastcall DevAuthGenerateRandomNumber(UCHAR *a1, size_t Size)
{
  unsigned int v2; // ebx

  v2 = Size;
  if ( BCryptGenRandom(0, a1, Size, 2u) >= 0 )
    return 1;
  memset(a1, 0, v2);
  return 0;
}

```

## disassembly

```asm
0x1800026e8  mov     [rsp+arg_0], rbx
0x1800026ed  push    rdi
0x1800026ee  sub     rsp, 20h
0x1800026f2  mov     ebx, edx
0x1800026f4  mov     r8d, edx; cbBuffer
0x1800026f7  mov     rdx, rcx; pbBuffer
0x1800026fa  mov     rdi, rcx
0x1800026fd  xor     ecx, ecx; hAlgorithm
0x1800026ff  mov     r9d, 2; dwFlags
0x180002705  call    cs:__imp_BCryptGenRandom
0x18000270c  nop     dword ptr [rax+rax+00h]
0x180002711  test    eax, eax
0x180002713  jns     short loc_180002726
0x180002715  mov     r8d, ebx; Size
0x180002718  xor     edx, edx; Val
0x18000271a  mov     rcx, rdi; void *
0x18000271d  call    memset
0x180002722  xor     eax, eax
0x180002724  jmp     short loc_18000272B
0x180002726  mov     eax, 1
0x18000272b  mov     rbx, [rsp+28h+arg_0]
0x180002730  add     rsp, 20h
0x180002734  pop     rdi
0x180002735  retn
```
