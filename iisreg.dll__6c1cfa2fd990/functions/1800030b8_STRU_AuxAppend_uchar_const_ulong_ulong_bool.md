# STRU::AuxAppend(uchar const *,ulong,ulong,bool)

- ea: `0x1800030b8`
- end: `0x18000315b`
- name: `?AuxAppend@STRU@@AEAAJPEBEKK_N@Z`
- size: `163`
- prototype: `__int64 __usercall@<rax>(STRU *__hidden this@<rcx>, const unsigned __int8 *Src@<rdx>, size_t Size@<r8>, unsigned int@<r9d>, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002330`
- `0x18000283c`

## callees

- `0x180003024`
- `0x1800030b8`
- `0x180003605`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003116`
- `KERNEL32!GetLastError` at `0x180003116`

## pseudocode

```c
signed int __fastcall STRU::AuxAppend(STRU *this, const unsigned __int8 *Src, size_t Size, unsigned int a4, bool a5)
{
  __int64 v5; // rdi
  unsigned __int64 v7; // rcx
  size_t v9; // rsi
  unsigned __int64 v10; // r10
  unsigned __int64 v11; // rdx
  signed int result; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx

  v5 = a4;
  v7 = *((unsigned int *)this + 10);
  v9 = (unsigned int)Size;
  v10 = (unsigned int)Size + (unsigned __int64)a4;
  if ( v7 >= v10 + 2 )
    goto LABEL_8;
  v11 = v10 + (a5 ? 128LL : 2LL);
  if ( v11 > 0xFFFFFFFF )
    return -2147024362;
  if ( (unsigned int)v11 <= (unsigned int)v7 || BUFFER::ReallocStorage(this, v11) )
  {
LABEL_8:
    memcpy_0((void *)(v5 + *((_QWORD *)this + 4)), Src, v9);
    v13 = *((_QWORD *)this + 4);
    v14 = (unsigned int)(v9 + v5) >> 1;
    result = 0;
    *((_DWORD *)this + 12) = v14;
    *(_WORD *)(v13 + 2 * v14) = 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800030b8  push    rbx
0x1800030ba  push    rbp
0x1800030bb  push    rsi
0x1800030bc  push    rdi
0x1800030bd  push    r14
0x1800030bf  push    r15
0x1800030c1  sub     rsp, 28h
0x1800030c5  mov     edi, r9d
0x1800030c8  mov     rbx, rcx
0x1800030cb  mov     ecx, [rcx+28h]
0x1800030ce  mov     rbp, rdx
0x1800030d1  mov     esi, r8d
0x1800030d4  lea     r10, [rsi+rdi]
0x1800030d8  lea     rax, [r10+2]
0x1800030dc  cmp     rcx, rax
0x1800030df  jnb     short loc_18000312A
0x1800030e1  neg     [rsp+58h+arg_20]
0x1800030e8  sbb     rax, rax
0x1800030eb  and     eax, 7Eh
0x1800030ee  lea     rdx, [rax+2]
0x1800030f2  mov     eax, 0FFFFFFFFh
0x1800030f7  add     rdx, r10; unsigned int
0x1800030fa  cmp     rdx, rax
0x1800030fd  jbe     short loc_180003106
0x1800030ff  mov     eax, 80070216h
0x180003104  jmp     short loc_18000314E
0x180003106  cmp     edx, ecx
0x180003108  jbe     short loc_18000312A
0x18000310a  mov     rcx, rbx; this
0x18000310d  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180003112  test    al, al
0x180003114  jnz     short loc_18000312A
0x180003116  call    cs:__imp_GetLastError
0x18000311c  test    eax, eax
0x18000311e  jle     short loc_18000314E
0x180003120  movzx   eax, ax
0x180003123  or      eax, 80070000h
0x180003128  jmp     short loc_18000314E
0x18000312a  mov     rcx, [rbx+20h]
0x18000312e  mov     r8, rsi; Size
0x180003131  add     rcx, rdi; void *
0x180003134  mov     rdx, rbp; Src
0x180003137  call    memcpy_0
0x18000313c  mov     rcx, [rbx+20h]
0x180003140  lea     edx, [rsi+rdi]
0x180003143  shr     edx, 1
0x180003145  xor     eax, eax
0x180003147  mov     [rbx+30h], edx
0x18000314a  mov     [rcx+rdx*2], ax
0x18000314e  add     rsp, 28h
0x180003152  pop     r15
0x180003154  pop     r14
0x180003156  pop     rdi
0x180003157  pop     rsi
0x180003158  pop     rbp
0x180003159  pop     rbx
0x18000315a  retn
```
