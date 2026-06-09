# NpOpenSymlink

- ea: `0x14000c734`
- end: `0x14000c7f4`
- name: `NpOpenSymlink`
- size: `192`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140011490`
- `0x140011aa0`

## callees

- `0x140001f40`
- `0x14000c734`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000c75c`
- `ntoskrnl!ExAllocatePool2` at `0x14000c75c`

## pseudocode

```c
__int64 __fastcall NpOpenSymlink(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebp
  __int64 Pool2; // rax
  __int64 v6; // rbx
  __int64 result; // rax
  void *v8; // rcx
  unsigned int v9; // eax

  v4 = *(unsigned __int16 *)(a1 + 256) + 24;
  Pool2 = ExAllocatePool2(64, v4, 1281781838);
  v6 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v8 = (void *)(Pool2 + 20);
  *(_OWORD *)Pool2 = 0;
  *(_QWORD *)(Pool2 + 16) = 0;
  *(_DWORD *)Pool2 = -1610612724;
  *(_WORD *)(Pool2 + 4) = v4 - 8;
  v9 = *(unsigned __int16 *)(a1 + 256);
  *(_WORD *)(v6 + 10) = v9;
  memmove(v8, *(const void **)(a1 + 264), v9);
  if ( (*(_DWORD *)(a1 + 248) & 1) != 0 )
  {
    *(_QWORD *)(a2 + 56) = 2684354585LL;
  }
  else
  {
    *(_QWORD *)(a2 + 56) = 2684354572LL;
    if ( (*(_DWORD *)(a1 + 248) & 2) != 0 )
      *(_DWORD *)(v6 + 16) |= 1u;
  }
  result = 260;
  *(_QWORD *)(a2 + 160) = v6;
  *(_DWORD *)(a2 + 48) = 260;
  return result;
}

```

## disassembly

```asm
0x14000c734  push    rbx
0x14000c736  push    rbp
0x14000c737  push    rsi
0x14000c738  push    rdi
0x14000c739  push    r14
0x14000c73b  sub     rsp, 20h
0x14000c73f  movzx   ebp, word ptr [rcx+100h]
0x14000c746  mov     rdi, rdx
0x14000c749  mov     rsi, rcx
0x14000c74c  add     ebp, 18h
0x14000c74f  mov     edx, ebp
0x14000c751  mov     ecx, 40h ; '@'
0x14000c756  mov     r8d, 4C66704Eh
0x14000c75c  call    cs:__imp_ExAllocatePool2
0x14000c763  nop     dword ptr [rax+rax+00h]
0x14000c768  mov     rbx, rax
0x14000c76b  test    rax, rax
0x14000c76e  jnz     short loc_14000C777
0x14000c770  mov     eax, 0C000009Ah
0x14000c775  jmp     short loc_14000C7E8
0x14000c777  xor     eax, eax
0x14000c779  lea     rcx, [rbx+14h]; void *
0x14000c77d  xorps   xmm0, xmm0
0x14000c780  mov     r14d, 0A000000Ch
0x14000c786  movups  xmmword ptr [rbx], xmm0
0x14000c789  mov     [rbx+10h], rax
0x14000c78d  sub     bp, 8
0x14000c791  mov     [rbx], r14d
0x14000c794  mov     [rbx+4], bp
0x14000c798  movzx   eax, word ptr [rsi+100h]
0x14000c79f  mov     [rbx+0Ah], ax
0x14000c7a3  mov     r8d, eax; Size
0x14000c7a6  mov     rdx, [rsi+108h]; Src
0x14000c7ad  call    memmove
0x14000c7b2  mov     eax, [rsi+0F8h]
0x14000c7b8  test    al, 1
0x14000c7ba  jz      short loc_14000C7C7
0x14000c7bc  mov     eax, 0A0000019h
0x14000c7c1  mov     [rdi+38h], rax
0x14000c7c5  jmp     short loc_14000C7D9
0x14000c7c7  mov     [rdi+38h], r14
0x14000c7cb  mov     eax, [rsi+0F8h]
0x14000c7d1  test    al, 2
0x14000c7d3  jz      short loc_14000C7D9
0x14000c7d5  or      dword ptr [rbx+10h], 1
0x14000c7d9  mov     eax, 104h
0x14000c7de  mov     [rdi+0A0h], rbx
0x14000c7e5  mov     [rdi+30h], eax
0x14000c7e8  add     rsp, 20h
0x14000c7ec  pop     r14
0x14000c7ee  pop     rdi
0x14000c7ef  pop     rsi
0x14000c7f0  pop     rbp
0x14000c7f1  pop     rbx
0x14000c7f2  retn
```
