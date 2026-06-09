# STRA::AuxAppend(uchar const *,ulong,ulong,bool)

- ea: `0x180003278`
- end: `0x180003321`
- name: `?AuxAppend@STRA@@AEAAJPEBEKK_N@Z`
- size: `169`
- prototype: `__int64 __usercall@<rax>(STRA *__hidden this@<rcx>, const unsigned __int8 *Src@<rdx>, size_t Size@<r8>, unsigned int@<r9d>, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003328`

## callees

- `0x180003024`
- `0x180003278`
- `0x180003605`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800032dc`
- `KERNEL32!GetLastError` at `0x1800032dc`
- `KERNEL32!SetLastError` at `0x1800032c4`
- `KERNEL32!SetLastError` at `0x1800032c4`

## pseudocode

```c
signed int __fastcall STRA::AuxAppend(STRA *this, const unsigned __int8 *Src, size_t Size, unsigned int a4, bool a5)
{
  __int64 v5; // rdi
  unsigned __int64 v7; // rcx
  size_t v9; // rsi
  unsigned __int64 v10; // r10
  unsigned __int64 v11; // rdx
  signed int result; // eax

  v5 = a4;
  v7 = *((unsigned int *)this + 10);
  v9 = (unsigned int)Size;
  v10 = (unsigned int)Size + (unsigned __int64)a4;
  if ( v7 >= v10 + 1 )
    goto LABEL_8;
  v11 = v10 + (a5 ? 128LL : 1LL);
  if ( v11 > 0xFFFFFFFF )
  {
    SetLastError(0x216u);
    return 0;
  }
  if ( (unsigned int)v11 <= (unsigned int)v7 || BUFFER::ReallocStorage(this, v11) )
  {
LABEL_8:
    memcpy_0((void *)(v5 + *((_QWORD *)this + 4)), Src, v9);
    *((_DWORD *)this + 12) = v9 + v5;
    *(_BYTE *)((unsigned int)(v9 + v5) + *((_QWORD *)this + 4)) = 0;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003278  push    rbx
0x18000327a  push    rbp
0x18000327b  push    rsi
0x18000327c  push    rdi
0x18000327d  push    r14
0x18000327f  push    r15
0x180003281  sub     rsp, 28h
0x180003285  mov     edi, r9d
0x180003288  mov     rbx, rcx
0x18000328b  mov     ecx, [rcx+28h]
0x18000328e  mov     rbp, rdx
0x180003291  mov     esi, r8d
0x180003294  lea     r10, [rsi+rdi]
0x180003298  lea     rax, [r10+1]
0x18000329c  cmp     rcx, rax
0x18000329f  jnb     short loc_1800032F0
0x1800032a1  neg     [rsp+58h+arg_20]
0x1800032a8  sbb     rax, rax
0x1800032ab  and     eax, 7Fh
0x1800032ae  lea     rdx, [rax+1]
0x1800032b2  mov     eax, 0FFFFFFFFh
0x1800032b7  add     rdx, r10; unsigned int
0x1800032ba  cmp     rdx, rax
0x1800032bd  jbe     short loc_1800032CC
0x1800032bf  mov     ecx, 216h; dwErrCode
0x1800032c4  call    cs:__imp_SetLastError
0x1800032ca  jmp     short loc_180003312
0x1800032cc  cmp     edx, ecx
0x1800032ce  jbe     short loc_1800032F0
0x1800032d0  mov     rcx, rbx; this
0x1800032d3  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x1800032d8  test    al, al
0x1800032da  jnz     short loc_1800032F0
0x1800032dc  call    cs:__imp_GetLastError
0x1800032e2  test    eax, eax
0x1800032e4  jle     short loc_180003314
0x1800032e6  movzx   eax, ax
0x1800032e9  or      eax, 80070000h
0x1800032ee  jmp     short loc_180003314
0x1800032f0  mov     rcx, [rbx+20h]
0x1800032f4  mov     r8, rsi; Size
0x1800032f7  add     rcx, rdi; void *
0x1800032fa  mov     rdx, rbp; Src
0x1800032fd  call    memcpy_0
0x180003302  lea     eax, [rsi+rdi]
0x180003305  mov     [rbx+30h], eax
0x180003308  mov     ecx, eax
0x18000330a  mov     rax, [rbx+20h]
0x18000330e  mov     byte ptr [rcx+rax], 0
0x180003312  xor     eax, eax
0x180003314  add     rsp, 28h
0x180003318  pop     r15
0x18000331a  pop     r14
0x18000331c  pop     rdi
0x18000331d  pop     rsi
0x18000331e  pop     rbp
0x18000331f  pop     rbx
0x180003320  retn
```
