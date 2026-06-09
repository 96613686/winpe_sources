# MidlCopyBuffer(uchar *,unsigned __int64,uchar * *)

- ea: `0x140019ac8`
- end: `0x140019b19`
- name: `?MidlCopyBuffer@@YAJPEAE_KPEAPEAE@Z`
- size: `81`
- prototype: `__int64 __fastcall(unsigned __int8 *Src, size_t Size, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140019c5c`
- `0x140019db0`

## callees

- `0x140009060`
- `0x140019ac8`
- `0x14001a83c`

## pseudocode

```c
__int64 __fastcall MidlCopyBuffer(unsigned __int8 *Src, size_t Size, unsigned __int8 **a3)
{
  unsigned __int8 *v6; // rax
  unsigned int v7; // ebx

  v6 = (unsigned __int8 *)DAF_user_alloc(Size);
  *a3 = v6;
  if ( v6 )
  {
    v7 = 0;
    memcpy_0(v6, Src, Size);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x140019ac8  mov     [rsp+arg_0], rbx
0x140019acd  mov     [rsp+arg_8], rsi
0x140019ad2  push    rdi
0x140019ad3  sub     rsp, 20h
0x140019ad7  mov     rsi, rcx
0x140019ada  mov     rbx, r8
0x140019add  mov     rcx, rdx
0x140019ae0  mov     rdi, rdx
0x140019ae3  call    DAF_user_alloc
0x140019ae8  mov     [rbx], rax
0x140019aeb  test    rax, rax
0x140019aee  jnz     short loc_140019AF7
0x140019af0  mov     ebx, 8007000Eh
0x140019af5  jmp     short loc_140019B07
0x140019af7  xor     ebx, ebx
0x140019af9  mov     r8, rdi; Size
0x140019afc  mov     rdx, rsi; Src
0x140019aff  mov     rcx, rax; void *
0x140019b02  call    memcpy_0
0x140019b07  mov     rsi, [rsp+28h+arg_8]
0x140019b0c  mov     eax, ebx
0x140019b0e  mov     rbx, [rsp+28h+arg_0]
0x140019b13  add     rsp, 20h
0x140019b17  pop     rdi
0x140019b18  retn
```
