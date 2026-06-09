# RtlMemoryStream::Write(void const *,unsigned __int64)

- ea: `0x180007f8c`
- end: `0x180008075`
- name: `?Write@RtlMemoryStream@@QEAAKPEBX_K@Z`
- size: `233`
- prototype: `unsigned int __fastcall(RtlMemoryStream *__hidden this, const void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005794`
- `0x180006934`

## callees

- `0x180007f8c`
- `0x1800191a2`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180007fe2`
- `KERNEL32!HeapAlloc` at `0x180007fe2`
- `KERNEL32!HeapReAlloc` at `0x180008002`
- `KERNEL32!HeapReAlloc` at `0x180008002`

## pseudocode

```c
__int64 __fastcall RtlMemoryStream::Write(RtlMemoryStream *this, _WORD *a2)
{
  unsigned __int64 *v2; // rsi
  unsigned __int64 v4; // rax
  unsigned __int64 v6; // rcx
  __int64 v7; // rdi
  unsigned __int64 v8; // rax
  void *v9; // r8
  void *v10; // rcx
  SIZE_T v11; // rdi
  void *v12; // rax
  LPVOID v13; // rbp
  unsigned __int64 *v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax

  v2 = (unsigned __int64 *)((char *)this + 32);
  v4 = *((_QWORD *)this + 4);
  v6 = v4 + 2;
  if ( v4 + 2 < v4 )
    return 160;
  if ( v6 <= *((_QWORD *)this + 2) )
  {
    v15 = v2;
  }
  else
  {
    v7 = *((_QWORD *)this + 3) - 1LL;
    v8 = v7 + v6;
    if ( v7 + v6 < v6 )
      return 534;
    v9 = (void *)*((_QWORD *)this + 5);
    v10 = *(void **)this;
    v11 = v8 & ~v7;
    if ( v9 )
    {
      v13 = HeapReAlloc(v10, 0, v9, v11);
    }
    else
    {
      v12 = HeapAlloc(v10, 0, v11);
      v13 = v12;
      if ( v12 )
        memset_0(v12, 0, v11);
    }
    if ( !v13 )
      return 14;
    *((_QWORD *)this + 5) = v13;
    v15 = (unsigned __int64 *)((char *)this + 32);
    *((_QWORD *)this + 2) = v11;
  }
  *(_WORD *)(*((_QWORD *)this + 5) + *v15) = *a2;
  v16 = *v2 + 2;
  if ( v16 < *v2 )
  {
    *v2 = -1;
    return 534;
  }
  *v2 = v16;
  v17 = *((_QWORD *)this + 1);
  if ( v17 <= v16 )
    v17 = v16;
  *((_QWORD *)this + 1) = v17;
  return 0;
}

```

## disassembly

```asm
0x180007f8c  push    rbx
0x180007f8e  push    rbp
0x180007f8f  push    rsi
0x180007f90  push    rdi
0x180007f91  push    r14
0x180007f93  sub     rsp, 20h
0x180007f97  lea     rsi, [rcx+20h]
0x180007f9b  mov     rbx, rcx
0x180007f9e  mov     rax, [rsi]
0x180007fa1  mov     r14, rdx
0x180007fa4  lea     rcx, [rax+2]
0x180007fa8  cmp     rcx, rax
0x180007fab  jb      loc_180008065
0x180007fb1  cmp     rcx, [rbx+10h]
0x180007fb5  jbe     short loc_180008023
0x180007fb7  mov     rdi, [rbx+18h]
0x180007fbb  dec     rdi
0x180007fbe  lea     rax, [rdi+rcx]
0x180007fc2  cmp     rax, rcx
0x180007fc5  jb      loc_18000805E
0x180007fcb  mov     r8, [rbx+28h]; lpMem
0x180007fcf  not     rdi
0x180007fd2  mov     rcx, [rbx]; hHeap
0x180007fd5  and     rdi, rax
0x180007fd8  xor     edx, edx; dwFlags
0x180007fda  test    r8, r8
0x180007fdd  jnz     short loc_180007FFF
0x180007fdf  mov     r8, rdi; dwBytes
0x180007fe2  call    cs:__imp_HeapAlloc
0x180007fe8  mov     rbp, rax
0x180007feb  test    rax, rax
0x180007fee  jz      short loc_18000800B
0x180007ff0  mov     r8, rdi; Size
0x180007ff3  xor     edx, edx; Val
0x180007ff5  mov     rcx, rax; void *
0x180007ff8  call    memset_0
0x180007ffd  jmp     short loc_18000800B
0x180007fff  mov     r9, rdi; dwBytes
0x180008002  call    cs:__imp_HeapReAlloc
0x180008008  mov     rbp, rax
0x18000800b  test    rbp, rbp
0x18000800e  jnz     short loc_180008015
0x180008010  lea     eax, [rbp+0Eh]
0x180008013  jmp     short loc_18000806A
0x180008015  mov     [rbx+28h], rbp
0x180008019  lea     rcx, [rbx+20h]
0x18000801d  mov     [rbx+10h], rdi
0x180008021  jmp     short loc_180008026
0x180008023  mov     rcx, rsi
0x180008026  mov     rcx, [rcx]
0x180008029  movzx   eax, word ptr [r14]
0x18000802d  mov     rdx, [rbx+28h]
0x180008031  mov     [rdx+rcx], ax
0x180008035  mov     rax, [rsi]
0x180008038  lea     rcx, [rax+2]
0x18000803c  cmp     rcx, rax
0x18000803f  jb      short loc_180008057
0x180008041  mov     [rsi], rcx
0x180008044  mov     rax, [rbx+8]
0x180008048  cmp     rax, rcx
0x18000804b  cmovbe  rax, rcx
0x18000804f  mov     [rbx+8], rax
0x180008053  xor     eax, eax
0x180008055  jmp     short loc_18000806A
0x180008057  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18000805e  mov     eax, 216h
0x180008063  jmp     short loc_18000806A
0x180008065  mov     eax, 0A0h
0x18000806a  add     rsp, 20h
0x18000806e  pop     r14
0x180008070  pop     rdi
0x180008071  pop     rsi
0x180008072  pop     rbp
0x180008073  pop     rbx
0x180008074  retn
```
