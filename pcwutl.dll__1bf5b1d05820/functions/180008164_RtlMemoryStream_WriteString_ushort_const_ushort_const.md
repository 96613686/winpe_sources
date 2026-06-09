# RtlMemoryStream::WriteString(ushort const *,ushort const *)

- ea: `0x180008164`
- end: `0x180008248`
- name: `?WriteString@RtlMemoryStream@@QEAAKPEBG0@Z`
- size: `228`
- prototype: `unsigned int __fastcall(RtlMemoryStream *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005794`

## callees

- `0x180008164`
- `0x1800191a2`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800081b5`
- `KERNEL32!HeapAlloc` at `0x1800081b5`
- `KERNEL32!HeapReAlloc` at `0x1800081d5`
- `KERNEL32!HeapReAlloc` at `0x1800081d5`

## pseudocode

```c
__int64 __fastcall RtlMemoryStream::WriteString(
        RtlMemoryStream *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int64 *v3; // rsi
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rcx
  __int64 v7; // rdi
  unsigned __int64 v8; // rax
  void *v9; // r8
  void *v10; // rcx
  SIZE_T v11; // rdi
  void *v12; // rax
  LPVOID v13; // rbp
  unsigned __int64 *v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax

  v3 = (unsigned __int64 *)((char *)this + 32);
  v5 = *((_QWORD *)this + 4);
  v6 = v5 + 2;
  if ( v5 + 2 < v5 )
    return 160;
  if ( v6 <= *((_QWORD *)this + 2) )
  {
    v15 = v3;
  }
  else
  {
    v7 = *((_QWORD *)this + 3) - 1LL;
    v8 = v6 + v7;
    if ( v6 + v7 < v6 )
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
  *(_WORD *)(*v15 + *((_QWORD *)this + 5)) = 0;
  v16 = *v3 + 2;
  if ( v16 < *v3 )
  {
    *v3 = -1;
    return 534;
  }
  *v3 = v16;
  v17 = *((_QWORD *)this + 1);
  if ( v17 <= v16 )
    v17 = v16;
  *((_QWORD *)this + 1) = v17;
  return 0;
}

```

## disassembly

```asm
0x180008164  push    rbx
0x180008166  push    rbp
0x180008167  push    rsi
0x180008168  push    rdi
0x180008169  sub     rsp, 28h
0x18000816d  lea     rsi, [rcx+20h]
0x180008171  mov     rbx, rcx
0x180008174  mov     rax, [rsi]
0x180008177  lea     rcx, [rax+2]
0x18000817b  cmp     rcx, rax
0x18000817e  jb      loc_18000823A
0x180008184  cmp     rcx, [rbx+10h]
0x180008188  jbe     short loc_1800081F6
0x18000818a  mov     rdi, [rbx+18h]
0x18000818e  dec     rdi
0x180008191  lea     rax, [rcx+rdi]
0x180008195  cmp     rax, rcx
0x180008198  jb      loc_180008233
0x18000819e  mov     r8, [rbx+28h]; lpMem
0x1800081a2  not     rdi
0x1800081a5  mov     rcx, [rbx]; hHeap
0x1800081a8  and     rdi, rax
0x1800081ab  xor     edx, edx; dwFlags
0x1800081ad  test    r8, r8
0x1800081b0  jnz     short loc_1800081D2
0x1800081b2  mov     r8, rdi; dwBytes
0x1800081b5  call    cs:__imp_HeapAlloc
0x1800081bb  mov     rbp, rax
0x1800081be  test    rax, rax
0x1800081c1  jz      short loc_1800081DE
0x1800081c3  mov     r8, rdi; Size
0x1800081c6  xor     edx, edx; Val
0x1800081c8  mov     rcx, rax; void *
0x1800081cb  call    memset_0
0x1800081d0  jmp     short loc_1800081DE
0x1800081d2  mov     r9, rdi; dwBytes
0x1800081d5  call    cs:__imp_HeapReAlloc
0x1800081db  mov     rbp, rax
0x1800081de  test    rbp, rbp
0x1800081e1  jnz     short loc_1800081E8
0x1800081e3  lea     eax, [rbp+0Eh]
0x1800081e6  jmp     short loc_18000823F
0x1800081e8  mov     [rbx+28h], rbp
0x1800081ec  lea     rdx, [rbx+20h]
0x1800081f0  mov     [rbx+10h], rdi
0x1800081f4  jmp     short loc_1800081F9
0x1800081f6  mov     rdx, rsi
0x1800081f9  mov     rcx, [rbx+28h]
0x1800081fd  mov     eax, cs:dword_18001D244
0x180008203  mov     rdx, [rdx]
0x180008206  mov     [rdx+rcx], ax
0x18000820a  mov     rax, [rsi]
0x18000820d  lea     rcx, [rax+2]
0x180008211  cmp     rcx, rax
0x180008214  jb      short loc_18000822C
0x180008216  mov     [rsi], rcx
0x180008219  mov     rax, [rbx+8]
0x18000821d  cmp     rax, rcx
0x180008220  cmovbe  rax, rcx
0x180008224  mov     [rbx+8], rax
0x180008228  xor     eax, eax
0x18000822a  jmp     short loc_18000823F
0x18000822c  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180008233  mov     eax, 216h
0x180008238  jmp     short loc_18000823F
0x18000823a  mov     eax, 0A0h
0x18000823f  add     rsp, 28h
0x180008243  pop     rdi
0x180008244  pop     rsi
0x180008245  pop     rbp
0x180008246  pop     rbx
0x180008247  retn
```
