# AddQuotes(ushort *,ulong)

- ea: `0x18000cd0c`
- end: `0x18000cd6c`
- name: `?AddQuotes@@YAXPEAGK@Z`
- size: `96`
- prototype: `void __fastcall(unsigned __int16 *Src, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001140c`
- `0x180011c90`
- `0x180011fc0`
- `0x180012a04`

## callees

- `0x18000cd0c`
- `0x18001aa8e`

## pseudocode

```c
void __fastcall AddQuotes(unsigned __int16 *Src, int a2)
{
  __int64 v2; // rbx

  v2 = -1;
  do
    ++v2;
  while ( Src[v2] );
  if ( (unsigned int)v2 < a2 - 2 )
  {
    memmove_0(Src + 1, Src, 2LL * (unsigned int)v2);
    Src[(unsigned int)(v2 + 1)] = 34;
    *Src = 34;
    Src[(unsigned int)(v2 + 2)] = 0;
  }
}

```

## disassembly

```asm
0x18000cd0c  mov     [rsp+arg_0], rbx
0x18000cd11  mov     [rsp+arg_8], rsi
0x18000cd16  push    rdi
0x18000cd17  sub     rsp, 20h
0x18000cd1b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000cd1f  mov     rdi, rcx
0x18000cd22  xor     esi, esi
0x18000cd24  inc     rbx
0x18000cd27  cmp     [rcx+rbx*2], si
0x18000cd2b  jnz     short loc_18000CD24
0x18000cd2d  lea     eax, [rdx-2]
0x18000cd30  cmp     ebx, eax
0x18000cd32  jnb     short loc_18000CD5C
0x18000cd34  mov     r8d, ebx
0x18000cd37  add     rcx, 2; void *
0x18000cd3b  add     r8, r8; Size
0x18000cd3e  mov     rdx, rdi; Src
0x18000cd41  call    memmove_0
0x18000cd46  mov     eax, 22h ; '"'
0x18000cd4b  lea     ecx, [rbx+1]
0x18000cd4e  mov     [rdi+rcx*2], ax
0x18000cd52  mov     [rdi], ax
0x18000cd55  lea     eax, [rbx+2]
0x18000cd58  mov     [rdi+rax*2], si
0x18000cd5c  mov     rbx, [rsp+28h+arg_0]
0x18000cd61  mov     rsi, [rsp+28h+arg_8]
0x18000cd66  add     rsp, 20h
0x18000cd6a  pop     rdi
0x18000cd6b  retn
```
