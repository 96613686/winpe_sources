# BufferReader::ReadNullTerminated(wchar_t * *)

- ea: `0x1800151d0`
- end: `0x18001526b`
- name: `?ReadNullTerminated@BufferReader@@QEAAXPEAPEA_W@Z`
- size: `155`
- prototype: `void __fastcall(BufferReader *__hidden this, wchar_t **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180014730`
- `0x180014c50`

## callees

- `0x18001513c`
- `0x1800151d0`
- `0x18001722c`

## import_xrefs

- `msvcrt!free` at `0x180015251`
- `msvcrt!free` at `0x180015251`

## pseudocode

```c
void __fastcall BufferReader::ReadNullTerminated(BufferReader *this, wchar_t **a2)
{
  _WORD *v4; // r9
  unsigned __int64 v5; // r8
  unsigned __int64 i; // rdi
  size_t v7; // rdi
  char *v8; // [rsp+40h] [rbp+8h]

  v4 = (_WORD *)*((_QWORD *)this + 1);
  v5 = (*((_QWORD *)this + 2) - (_QWORD)v4) >> 1;
  for ( i = 0; i < v5; ++v4 )
  {
    if ( !*v4 )
      break;
    ++i;
  }
  v8 = (char *)MmAllocate(saturated_mul(i + 1, 2u));
  v7 = 2 * i;
  BufferReader::ReadBytes(this, v8, v7);
  *(_WORD *)&v8[v7] = 0;
  *a2 = (wchar_t *)v8;
  free(0);
}

```

## disassembly

```asm
0x1800151d0  mov     [rsp+arg_8], rbx
0x1800151d5  mov     [rsp+arg_10], rbp
0x1800151da  push    rsi
0x1800151db  push    rdi
0x1800151dc  push    r14
0x1800151de  sub     rsp, 20h
0x1800151e2  mov     r14, rdx
0x1800151e5  mov     rsi, rcx
0x1800151e8  mov     r9, [rcx+8]
0x1800151ec  mov     r8, [rcx+10h]
0x1800151f0  sub     r8, r9
0x1800151f3  mov     eax, 2
0x1800151f8  shr     r8, 1
0x1800151fb  lea     ebp, [rax-2]
0x1800151fe  mov     edi, ebp
0x180015200  jz      short loc_180015213
0x180015202  cmp     [r9], bp
0x180015206  jz      short loc_180015213
0x180015208  inc     rdi
0x18001520b  add     r9, rax
0x18001520e  cmp     rdi, r8
0x180015211  jb      short loc_180015202
0x180015213  lea     rcx, [rdi+1]
0x180015217  mul     rcx
0x18001521a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180015221  cmovb   rax, rcx
0x180015225  mov     rcx, rax; unsigned __int64
0x180015228  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001522d  mov     rbx, rax
0x180015230  mov     [rsp+38h+arg_0], rax
0x180015235  add     rdi, rdi
0x180015238  mov     r8, rdi; unsigned __int64
0x18001523b  mov     rdx, rax; void *
0x18001523e  mov     rcx, rsi; this
0x180015241  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x180015246  mov     word ptr [rdi+rbx], 0
0x18001524c  mov     [r14], rbx
0x18001524f  xor     ecx, ecx; Block
0x180015251  call    cs:__imp_free
0x180015257  nop
0x180015258  mov     rbx, [rsp+38h+arg_8]
0x18001525d  mov     rbp, [rsp+38h+arg_10]
0x180015262  add     rsp, 20h
0x180015266  pop     r14
0x180015268  pop     rdi
0x180015269  pop     rsi
0x18001526a  retn
```
