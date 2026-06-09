# LocalAllocAndCopyWStr(ushort *)

- ea: `0x1800059ec`
- end: `0x180005a48`
- name: `?LocalAllocAndCopyWStr@@YAPEAGPEAG@Z`
- size: `92`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *Src)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800066f8`
- `0x1800067b8`
- `0x18001acb0`
- `0x180020cc0`
- `0x180021724`
- `0x18002b79c`
- `0x18002c0f0`
- `0x180032638`
- `0x18003275c`
- `0x180032850`

## callees

- `0x180001f66`
- `0x1800059ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005a20`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005a20`

## pseudocode

```c
unsigned __int16 *__fastcall LocalAllocAndCopyWStr(unsigned __int16 *Src)
{
  __int64 v2; // rax
  SIZE_T v3; // rdi
  unsigned __int16 *result; // rax
  unsigned __int16 *v5; // rsi

  if ( Src )
  {
    v2 = -1;
    do
      ++v2;
    while ( Src[v2] );
  }
  else
  {
    LODWORD(v2) = 0;
  }
  v3 = 2LL * ((int)v2 + 1);
  result = (unsigned __int16 *)LocalAlloc(0x40u, v3);
  v5 = result;
  if ( result )
  {
    memcpy_0(result, Src, v3);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800059ec  push    rbx
0x1800059ee  push    rbp
0x1800059ef  push    rsi
0x1800059f0  push    rdi
0x1800059f1  sub     rsp, 28h
0x1800059f5  xor     ebp, ebp
0x1800059f7  mov     rbx, rcx
0x1800059fa  test    rcx, rcx
0x1800059fd  jz      short loc_180005A0E
0x1800059ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005a03  inc     rax
0x180005a06  cmp     [rcx+rax*2], bp
0x180005a0a  jnz     short loc_180005A03
0x180005a0c  jmp     short loc_180005A10
0x180005a0e  mov     eax, ebp
0x180005a10  inc     eax
0x180005a12  mov     ecx, 40h ; '@'; uFlags
0x180005a17  movsxd  rdi, eax
0x180005a1a  add     rdi, rdi
0x180005a1d  mov     rdx, rdi; uBytes
0x180005a20  call    cs:__imp_LocalAlloc
0x180005a26  mov     rsi, rax
0x180005a29  test    rax, rax
0x180005a2c  jz      short loc_180005A3F
0x180005a2e  mov     r8, rdi; Size
0x180005a31  mov     rdx, rbx; Src
0x180005a34  mov     rcx, rsi; void *
0x180005a37  call    memcpy_0
0x180005a3c  mov     rax, rsi
0x180005a3f  add     rsp, 28h
0x180005a43  pop     rdi
0x180005a44  pop     rsi
0x180005a45  pop     rbp
0x180005a46  pop     rbx
0x180005a47  retn
```
