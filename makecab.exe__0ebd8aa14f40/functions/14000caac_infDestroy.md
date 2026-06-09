# infDestroy

- ea: `0x14000caac`
- end: `0x14000cb78`
- name: `infDestroy`
- size: `204`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140003f68`
- `0x140007934`
- `0x14000c6d4`

## callees

- `0x140008620`
- `0x140008ee4`
- `0x14000caac`

## import_xrefs

- `msvcrt!remove` at `0x14000cafa`
- `msvcrt!remove` at `0x14000cafa`
- `msvcrt!fclose` at `0x14000caf0`
- `msvcrt!fclose` at `0x14000caf0`
- `msvcrt!free` at `0x14000cb30`
- `msvcrt!free` at `0x14000cb3f`
- `msvcrt!free` at `0x14000cb48`
- `msvcrt!free` at `0x14000cb62`
- `msvcrt!free` at `0x14000cb30`
- `msvcrt!free` at `0x14000cb3f`
- `msvcrt!free` at `0x14000cb48`
- `msvcrt!free` at `0x14000cb62`

## string_xrefs

- `0x14000cb13`: `Cannot delete %1: %2`

## pseudocode

```c
__int64 __fastcall infDestroy(_QWORD *Block, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 i; // rdi
  __int64 v7; // rbx
  void *v8; // rcx
  void *v9; // rcx

  v4 = 0;
  do
  {
    v5 = Block[v4];
    if ( v5 && !(unsigned int)TmpClose(v5, a2) )
      return 0;
    v4 = (unsigned int)(v4 + 1);
  }
  while ( (int)v4 < 3 );
  for ( i = 0; i != 3; ++i )
  {
    v7 = Block[i];
    if ( v7 )
    {
      if ( *(_QWORD *)v7 )
        fclose(*(FILE **)v7);
      if ( remove(*(const char **)(v7 + 8)) )
        ErrSet(a2, "Cannot delete %1: %2", "%s%s", *(const char **)(v7 + 16), *(const char **)(v7 + 8));
      v8 = *(void **)(v7 + 16);
      if ( v8 )
        free(v8);
      v9 = *(void **)(v7 + 8);
      if ( v9 )
        free(v9);
      free((void *)v7);
      Block[i] = 0;
    }
  }
  free(Block);
  return 1;
}

```

## disassembly

```asm
0x14000caac  push    rbx
0x14000caae  push    rbp
0x14000caaf  push    rsi
0x14000cab0  push    rdi
0x14000cab1  sub     rsp, 38h
0x14000cab5  mov     rbp, rdx
0x14000cab8  mov     rsi, rcx
0x14000cabb  xor     ebx, ebx
0x14000cabd  mov     rcx, [rsi+rbx*8]
0x14000cac1  test    rcx, rcx
0x14000cac4  jz      short loc_14000CAD6
0x14000cac6  mov     rdx, rbp
0x14000cac9  call    TmpClose
0x14000cace  test    eax, eax
0x14000cad0  jz      loc_14000CB74
0x14000cad6  inc     ebx
0x14000cad8  cmp     ebx, 3
0x14000cadb  jl      short loc_14000CABD
0x14000cadd  xor     edi, edi
0x14000cadf  mov     rbx, [rsi+rdi*8]
0x14000cae3  test    rbx, rbx
0x14000cae6  jz      short loc_14000CB56
0x14000cae8  mov     rcx, [rbx]; Stream
0x14000caeb  test    rcx, rcx
0x14000caee  jz      short loc_14000CAF6
0x14000caf0  call    cs:__imp_fclose
0x14000caf6  mov     rcx, [rbx+8]; FileName
0x14000cafa  call    cs:__imp_remove
0x14000cb00  test    eax, eax
0x14000cb02  jz      short loc_14000CB27
0x14000cb04  mov     rax, [rbx+8]
0x14000cb08  lea     r8, aSS_1; "%s%s"
0x14000cb0f  mov     r9, [rbx+10h]
0x14000cb13  lea     rdx, aCannotDelete12; "Cannot delete %1: %2"
0x14000cb1a  mov     rcx, rbp
0x14000cb1d  mov     [rsp+58h+var_38], rax
0x14000cb22  call    ErrSet
0x14000cb27  mov     rcx, [rbx+10h]; Block
0x14000cb2b  test    rcx, rcx
0x14000cb2e  jz      short loc_14000CB36
0x14000cb30  call    cs:__imp_free
0x14000cb36  mov     rcx, [rbx+8]; Block
0x14000cb3a  test    rcx, rcx
0x14000cb3d  jz      short loc_14000CB45
0x14000cb3f  call    cs:__imp_free
0x14000cb45  mov     rcx, rbx; Block
0x14000cb48  call    cs:__imp_free
0x14000cb4e  mov     qword ptr [rsi+rdi*8], 0
0x14000cb56  inc     rdi
0x14000cb59  cmp     rdi, 3
0x14000cb5d  jnz     short loc_14000CADF
0x14000cb5f  mov     rcx, rsi; Block
0x14000cb62  call    cs:__imp_free
0x14000cb68  lea     eax, [rdi-2]
0x14000cb6b  add     rsp, 38h
0x14000cb6f  pop     rdi
0x14000cb70  pop     rsi
0x14000cb71  pop     rbp
0x14000cb72  pop     rbx
0x14000cb73  retn
0x14000cb74  xor     eax, eax
0x14000cb76  jmp     short loc_14000CB6B
```
