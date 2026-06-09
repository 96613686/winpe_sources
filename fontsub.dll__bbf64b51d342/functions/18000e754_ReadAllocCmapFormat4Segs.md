# ReadAllocCmapFormat4Segs

- ea: `0x18000e754`
- end: `0x18000e8ed`
- name: `ReadAllocCmapFormat4Segs`
- size: `409`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a8dc`
- `0x18000e4c8`

## callees

- `0x18000e754`
- `0x180011538`
- `0x180011574`
- `0x18001a680`

## pseudocode

```c
__int64 __fastcall ReadAllocCmapFormat4Segs(__int64 a1, unsigned __int16 a2, __int64 *a3, unsigned int a4, _DWORD *a5)
{
  int v5; // ebp
  unsigned int v9; // edx
  __int64 result; // rax
  __int64 v11; // rax
  unsigned __int16 i; // r10
  unsigned __int16 Word; // di
  __int16 v14; // r10
  int v15; // r10d
  int v16; // edi
  unsigned __int16 j; // si
  unsigned __int16 v18; // r15
  int v19; // edi
  unsigned __int16 k; // si
  int v21; // edi
  unsigned __int16 m; // si
  char v23; // [rsp+78h] [rbp+10h] BYREF

  v5 = a2;
  v9 = 8 * a2;
  if ( v9 + a4 + 2 < a4 )
    return 1001;
  v11 = Mem_Alloc(v9);
  *a3 = v11;
  if ( !v11 )
    return 1005;
  for ( i = 0; i < (unsigned __int16)v5; i = v14 + 1 )
  {
    Word = ReadWord(a1, *a3 + 8LL * i, a4 + 2 * i);
    if ( Word )
      goto LABEL_9;
  }
  Word = ReadWord(a1, (__int64)&v23, 2 * v5 + a4);
  if ( Word )
  {
LABEL_9:
    Mem_Free(*a3);
    result = Word;
    *a3 = 0;
    return result;
  }
  v16 = 2 * v5 + a4 + 2;
  for ( j = 0; j < (unsigned __int16)v5; ++j )
  {
    v18 = ReadWord(a1, *a3 + 2 + 8LL * j, v16 + 2 * (unsigned int)j);
    if ( v18 )
    {
LABEL_15:
      Mem_Free(*a3);
      result = v18;
      *a3 = 0;
      return result;
    }
  }
  v19 = v15 + v16;
  for ( k = 0; k < (unsigned __int16)v5; ++k )
  {
    v18 = ReadWord(a1, *a3 + 4 + 8LL * k, v19 + 2 * (unsigned int)k);
    if ( v18 )
      goto LABEL_15;
  }
  v21 = v15 + v19;
  for ( m = 0; m < (unsigned __int16)v5; ++m )
  {
    v18 = ReadWord(a1, *a3 + 6 + 8LL * m, v21 + 2 * (unsigned int)m);
    if ( v18 )
      goto LABEL_15;
  }
  *a5 = v21 + v15 - a4;
  return 0;
}

```

## disassembly

```asm
0x18000e754  push    rbx
0x18000e756  push    rbp
0x18000e757  push    rsi
0x18000e758  push    rdi
0x18000e759  push    r12
0x18000e75b  push    r13
0x18000e75d  push    r14
0x18000e75f  push    r15
0x18000e761  sub     rsp, 28h
0x18000e765  movzx   ebp, dx
0x18000e768  lea     eax, [r9+2]
0x18000e76c  mov     r14d, r9d
0x18000e76f  mov     rbx, r8
0x18000e772  mov     r12, rcx
0x18000e775  lea     edx, ds:0[rbp*8]
0x18000e77c  add     eax, edx
0x18000e77e  cmp     eax, r9d
0x18000e781  jnb     short loc_18000E78D
0x18000e783  mov     eax, 3E9h
0x18000e788  jmp     loc_18000E8DC
0x18000e78d  mov     ecx, edx; Size
0x18000e78f  call    Mem_Alloc
0x18000e794  xor     r13d, r13d
0x18000e797  mov     [rbx], rax
0x18000e79a  test    rax, rax
0x18000e79d  jnz     short loc_18000E7A9
0x18000e79f  mov     eax, 3EDh
0x18000e7a4  jmp     loc_18000E8DC
0x18000e7a9  mov     r10d, r13d
0x18000e7ac  cmp     r10w, bp
0x18000e7b0  jnb     short loc_18000E7EE
0x18000e7b2  movzx   eax, r10w
0x18000e7b6  movzx   ecx, r10w
0x18000e7ba  lea     r8d, [r14+rax*2]
0x18000e7be  mov     rax, [rbx]
0x18000e7c1  lea     rdx, [rax+rcx*8]
0x18000e7c5  mov     rcx, r12
0x18000e7c8  call    ReadWord
0x18000e7cd  movzx   edi, ax
0x18000e7d0  test    ax, ax
0x18000e7d3  jnz     short loc_18000E7DB
0x18000e7d5  inc     r10w
0x18000e7d9  jmp     short loc_18000E7AC
0x18000e7db  mov     rcx, [rbx]
0x18000e7de  call    Mem_Free
0x18000e7e3  movzx   eax, di
0x18000e7e6  mov     [rbx], r13
0x18000e7e9  jmp     loc_18000E8DC
0x18000e7ee  lea     r10d, ds:0[rbp*2]
0x18000e7f6  mov     rcx, r12
0x18000e7f9  lea     esi, [r10+r14]
0x18000e7fd  mov     r8d, esi
0x18000e800  lea     rdx, [rsp+68h+arg_8]
0x18000e805  call    ReadWord
0x18000e80a  movzx   edi, ax
0x18000e80d  test    ax, ax
0x18000e810  jnz     short loc_18000E7DB
0x18000e812  lea     edi, [rsi+2]
0x18000e815  mov     esi, r13d
0x18000e818  cmp     si, bp
0x18000e81b  jnb     short loc_18000E85C
0x18000e81d  mov     rdx, [rbx]
0x18000e820  add     rdx, 2
0x18000e824  movzx   ecx, si
0x18000e827  movzx   eax, si
0x18000e82a  lea     rdx, [rdx+rcx*8]
0x18000e82e  mov     rcx, r12
0x18000e831  lea     r8d, [rdi+rax*2]
0x18000e835  call    ReadWord
0x18000e83a  movzx   r15d, ax
0x18000e83e  test    ax, ax
0x18000e841  jnz     short loc_18000E848
0x18000e843  inc     si
0x18000e846  jmp     short loc_18000E818
0x18000e848  mov     rcx, [rbx]
0x18000e84b  call    Mem_Free
0x18000e850  movzx   eax, r15w
0x18000e854  mov     [rbx], r13
0x18000e857  jmp     loc_18000E8DC
0x18000e85c  add     edi, r10d
0x18000e85f  mov     esi, r13d
0x18000e862  cmp     si, bp
0x18000e865  jnb     short loc_18000E892
0x18000e867  mov     rdx, [rbx]
0x18000e86a  add     rdx, 4
0x18000e86e  movzx   ecx, si
0x18000e871  movzx   eax, si
0x18000e874  lea     rdx, [rdx+rcx*8]
0x18000e878  mov     rcx, r12
0x18000e87b  lea     r8d, [rdi+rax*2]
0x18000e87f  call    ReadWord
0x18000e884  movzx   r15d, ax
0x18000e888  test    ax, ax
0x18000e88b  jnz     short loc_18000E848
0x18000e88d  inc     si
0x18000e890  jmp     short loc_18000E862
0x18000e892  add     edi, r10d
0x18000e895  mov     esi, r13d
0x18000e898  cmp     si, bp
0x18000e89b  jnb     short loc_18000E8C8
0x18000e89d  mov     rdx, [rbx]
0x18000e8a0  add     rdx, 6
0x18000e8a4  movzx   ecx, si
0x18000e8a7  movzx   eax, si
0x18000e8aa  lea     rdx, [rdx+rcx*8]
0x18000e8ae  mov     rcx, r12
0x18000e8b1  lea     r8d, [rdi+rax*2]
0x18000e8b5  call    ReadWord
0x18000e8ba  movzx   r15d, ax
0x18000e8be  test    ax, ax
0x18000e8c1  jnz     short loc_18000E848
0x18000e8c3  inc     si
0x18000e8c6  jmp     short loc_18000E898
0x18000e8c8  mov     rax, [rsp+68h+arg_20]
0x18000e8d0  sub     r10d, r14d
0x18000e8d3  add     r10d, edi
0x18000e8d6  mov     [rax], r10d
0x18000e8d9  mov     eax, r13d
0x18000e8dc  add     rsp, 28h
0x18000e8e0  pop     r15
0x18000e8e2  pop     r14
0x18000e8e4  pop     r13
0x18000e8e6  pop     r12
0x18000e8e8  pop     rdi
0x18000e8e9  pop     rsi
0x18000e8ea  pop     rbp
0x18000e8eb  pop     rbx
0x18000e8ec  retn
```
