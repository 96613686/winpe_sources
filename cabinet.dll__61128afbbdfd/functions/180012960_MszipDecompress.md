# MszipDecompress

- ea: `0x180012960`
- end: `0x180012a2c`
- name: `MszipDecompress`
- size: `204`
- prototype: `__int64 __fastcall(__int64, int, unsigned __int64, void *, size_t Size, size_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005330`
- `0x1800058e4`
- `0x180012960`
- `0x18001b625`

## pseudocode

```c
__int64 __fastcall MszipDecompress(__int64 a1, int a2, unsigned __int64 a3, void *a4, size_t Size, size_t *a6)
{
  size_t v8; // rbx
  size_t v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // edx
  int v13; // [rsp+40h] [rbp+8h] BYREF

  if ( *(_DWORD *)a1 )
    return 774;
  v8 = Size;
  v9 = 0x8000;
  if ( Size > 0x8000 )
  {
    v11 = 111;
    goto LABEL_13;
  }
  if ( !a3 )
  {
    v11 = 122;
    v9 = Size + 12;
LABEL_13:
    *a6 = v9;
    return v11;
  }
  if ( a3 > 0x800C )
    return 605;
  if ( (unsigned int)NFM_Prepare(*(_QWORD *)(a1 + 16), a2, a3, *(_QWORD *)(a1 + 8), Size)
    || (v10 = *(_QWORD *)(a1 + 16), v13 = v8, (unsigned int)NFM_Decompress(v10, &v13))
    || v13 != v8 )
  {
    *(_DWORD *)a1 = 1;
    return 605;
  }
  memcpy_0(a4, *(const void **)(a1 + 8), v8);
  v11 = 0;
  *a6 = v8;
  return v11;
}

```

## disassembly

```asm
0x180012960  mov     [rsp+arg_8], rbx
0x180012965  mov     [rsp+arg_10], rsi
0x18001296a  push    rdi
0x18001296b  sub     rsp, 30h
0x18001296f  cmp     dword ptr [rcx], 0
0x180012972  mov     rsi, r9
0x180012975  mov     rdi, rcx
0x180012978  jnz     loc_180012A1E
0x18001297e  mov     rbx, [rsp+38h+Size]
0x180012983  mov     ecx, 8000h
0x180012988  cmp     rbx, rcx
0x18001298b  ja      loc_180012A25
0x180012991  test    r8, r8
0x180012994  jz      short loc_180012A0B
0x180012996  cmp     r8, 800Ch
0x18001299d  ja      short loc_180012A04
0x18001299f  mov     r9, [rdi+8]
0x1800129a3  mov     rcx, [rdi+10h]
0x1800129a7  mov     [rsp+38h+var_18], ebx
0x1800129ab  call    NFM_Prepare
0x1800129b0  test    eax, eax
0x1800129b2  jnz     short loc_1800129FE
0x1800129b4  mov     rcx, [rdi+10h]
0x1800129b8  lea     rdx, [rsp+38h+arg_0]
0x1800129bd  mov     [rsp+38h+arg_0], ebx
0x1800129c1  call    NFM_Decompress
0x1800129c6  test    eax, eax
0x1800129c8  jnz     short loc_1800129FE
0x1800129ca  mov     eax, [rsp+38h+arg_0]
0x1800129ce  cmp     rax, rbx
0x1800129d1  jnz     short loc_1800129FE
0x1800129d3  mov     rdx, [rdi+8]; Src
0x1800129d7  mov     r8, rbx; Size
0x1800129da  mov     rcx, rsi; void *
0x1800129dd  call    memcpy_0
0x1800129e2  mov     rax, [rsp+38h+arg_28]
0x1800129e7  xor     edx, edx
0x1800129e9  mov     [rax], rbx
0x1800129ec  mov     rbx, [rsp+38h+arg_8]
0x1800129f1  mov     eax, edx
0x1800129f3  mov     rsi, [rsp+38h+arg_10]
0x1800129f8  add     rsp, 30h
0x1800129fc  pop     rdi
0x1800129fd  retn
0x1800129fe  mov     dword ptr [rdi], 1
0x180012a04  mov     edx, 25Dh
0x180012a09  jmp     short loc_1800129EC
0x180012a0b  mov     edx, 7Ah ; 'z'
0x180012a10  lea     rcx, [rbx+0Ch]
0x180012a14  mov     rax, [rsp+38h+arg_28]
0x180012a19  mov     [rax], rcx
0x180012a1c  jmp     short loc_1800129EC
0x180012a1e  mov     edx, 306h
0x180012a23  jmp     short loc_1800129EC
0x180012a25  mov     edx, 6Fh ; 'o'
0x180012a2a  jmp     short loc_180012A14
```
