# COEnumConnectionPoints::Init(ulong,IConnectionPoint * *,ulong)

- ea: `0x18000cd48`
- end: `0x18000cdd1`
- name: `?Init@COEnumConnectionPoints@@QEAAJKPEAPEAUIConnectionPoint@@K@Z`
- size: `137`
- prototype: `__int64 __fastcall(COEnumConnectionPoints *__hidden this, unsigned int, struct IConnectionPoint **, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c360`
- `0x18000c8d0`

## callees

- `0x1800010bc`
- `0x18000cd48`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall COEnumConnectionPoints::Init(
        COEnumConnectionPoints *this,
        unsigned int a2,
        struct IConnectionPoint **a3,
        int a4)
{
  void *v7; // rax
  unsigned int v8; // ebx
  unsigned int v9; // ebp
  __int64 v10; // rdi
  __int64 v11; // rcx

  *((_DWORD *)this + 7) = a2;
  *((_DWORD *)this + 6) = a4;
  v7 = operator new[](saturated_mul(a2, 8u));
  *((_QWORD *)this + 4) = v7;
  if ( v7 )
  {
    v8 = 0;
    v9 = 0;
    if ( a2 )
    {
      v10 = 0;
      do
      {
        *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v10) = a3[v10];
        v11 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * v10);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
        ++v9;
        ++v10;
      }
      while ( v9 < a2 );
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x18000cd48  push    rbx
0x18000cd4a  push    rbp
0x18000cd4b  push    rsi
0x18000cd4c  push    rdi
0x18000cd4d  push    r14
0x18000cd4f  push    r15
0x18000cd51  sub     rsp, 28h
0x18000cd55  mov     esi, edx
0x18000cd57  mov     r14, rcx
0x18000cd5a  mov     [rcx+1Ch], esi
0x18000cd5d  mov     eax, 8
0x18000cd62  mov     [rcx+18h], r9d
0x18000cd66  mov     r15, r8
0x18000cd69  mul     rsi
0x18000cd6c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cd73  cmovb   rax, rcx
0x18000cd77  mov     rcx, rax; unsigned __int64
0x18000cd7a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000cd7f  mov     [r14+20h], rax
0x18000cd83  test    rax, rax
0x18000cd86  jz      short loc_18000CDBD
0x18000cd88  xor     ebx, ebx
0x18000cd8a  xor     ebp, ebp
0x18000cd8c  test    esi, esi
0x18000cd8e  jz      short loc_18000CDC2
0x18000cd90  xor     edi, edi
0x18000cd92  mov     rcx, [r14+20h]
0x18000cd96  mov     rax, [r15+rdi*8]
0x18000cd9a  mov     [rcx+rdi*8], rax
0x18000cd9e  mov     rax, [r14+20h]
0x18000cda2  mov     rcx, [rax+rdi*8]
0x18000cda6  mov     rax, [rcx]
0x18000cda9  mov     rax, [rax+8]
0x18000cdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdb2  inc     ebp
0x18000cdb4  inc     rdi
0x18000cdb7  cmp     ebp, esi
0x18000cdb9  jb      short loc_18000CD92
0x18000cdbb  jmp     short loc_18000CDC2
0x18000cdbd  mov     ebx, 8007000Eh
0x18000cdc2  mov     eax, ebx
0x18000cdc4  add     rsp, 28h
0x18000cdc8  pop     r15
0x18000cdca  pop     r14
0x18000cdcc  pop     rdi
0x18000cdcd  pop     rsi
0x18000cdce  pop     rbp
0x18000cdcf  pop     rbx
0x18000cdd0  retn
```
