# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180002794`
- end: `0x18000288b`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002a10`
- `0x180002a80`
- `0x180002b10`

## callees

- `0x180001d06`
- `0x1800024b0`
- `0x18000266c`
- `0x18000269c`
- `0x180002794`

## pseudocode

```c
size_t *__fastcall std::string::assign(size_t *a1, char *Src, size_t Size)
{
  size_t *v5; // rbx
  char *v6; // rax
  void *v8; // rcx
  _BYTE *v9; // rax
  size_t v10; // rax

  v5 = a1;
  if ( Src )
  {
    v6 = a1[3] < 0x10 ? (char *)a1 : (char *)*a1;
    if ( Src >= v6 )
    {
      if ( a1[3] >= 0x10 )
        a1 = (size_t *)*a1;
      if ( (char *)a1 + v5[2] > Src )
        return (size_t *)std::string::assign(v5);
    }
  }
  if ( Size == -1 )
    std::wstring::_Xlen(v5);
  if ( v5[3] >= Size )
  {
    if ( !Size )
    {
      if ( v5[3] < 0x10 )
        v9 = v5;
      else
        v9 = (_BYTE *)*v5;
      v5[2] = 0;
      *v9 = 0;
      return v5;
    }
    goto LABEL_13;
  }
  std::string::_Copy((const void **)v5, Size, v5[2]);
  if ( Size )
  {
LABEL_13:
    if ( v5[3] < 0x10 )
      v8 = v5;
    else
      v8 = (void *)*v5;
    memcpy_0(v8, Src, Size);
    if ( v5[3] < 0x10 )
      v10 = (size_t)v5;
    else
      v10 = *v5;
    v5[2] = Size;
    *(_BYTE *)(v10 + Size) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180002794  mov     [rsp+arg_0], rbx
0x180002799  mov     [rsp+arg_8], rsi
0x18000279e  push    rdi
0x18000279f  sub     rsp, 20h
0x1800027a3  mov     rdi, r8
0x1800027a6  mov     rsi, rdx
0x1800027a9  mov     rbx, rcx
0x1800027ac  test    rdx, rdx
0x1800027af  jz      short loc_1800027FD
0x1800027b1  cmp     qword ptr [rcx+18h], 10h
0x1800027b6  jb      short loc_1800027BD
0x1800027b8  mov     rax, [rcx]
0x1800027bb  jmp     short loc_1800027C0
0x1800027bd  mov     rax, rbx
0x1800027c0  cmp     rsi, rax
0x1800027c3  jb      short loc_1800027FD
0x1800027c5  cmp     qword ptr [rcx+18h], 10h
0x1800027ca  jb      short loc_1800027CF
0x1800027cc  mov     rcx, [rcx]
0x1800027cf  add     rcx, [rbx+10h]
0x1800027d3  cmp     rcx, rsi
0x1800027d6  jbe     short loc_1800027FD
0x1800027d8  cmp     qword ptr [rbx+18h], 10h
0x1800027dd  jb      short loc_1800027E4
0x1800027df  mov     rax, [rbx]
0x1800027e2  jmp     short loc_1800027E7
0x1800027e4  mov     rax, rbx
0x1800027e7  sub     rsi, rax
0x1800027ea  mov     r9, rdi
0x1800027ed  mov     r8, rsi
0x1800027f0  mov     rdx, rbx
0x1800027f3  mov     rcx, rbx; void *
0x1800027f6  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1800027fb  jmp     short loc_180002872
0x1800027fd  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180002801  ja      short loc_180002882
0x180002803  cmp     [rbx+18h], rdi
0x180002807  jnb     short loc_180002829
0x180002809  mov     r8, [rbx+10h]
0x18000280d  mov     rdx, rdi
0x180002810  mov     rcx, rbx; Src
0x180002813  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002818  test    rdi, rdi
0x18000281b  jz      short loc_18000286F
0x18000281d  cmp     qword ptr [rbx+18h], 10h
0x180002822  jb      short loc_18000284A
0x180002824  mov     rcx, [rbx]
0x180002827  jmp     short loc_18000284D
0x180002829  test    rdi, rdi
0x18000282c  jnz     short loc_18000281D
0x18000282e  cmp     qword ptr [rbx+18h], 10h
0x180002833  jb      short loc_18000283A
0x180002835  mov     rax, [rbx]
0x180002838  jmp     short loc_18000283D
0x18000283a  mov     rax, rbx
0x18000283d  mov     qword ptr [rbx+10h], 0
0x180002845  mov     byte ptr [rax], 0
0x180002848  jmp     short loc_18000286F
0x18000284a  mov     rcx, rbx; void *
0x18000284d  mov     r8, rdi; Size
0x180002850  mov     rdx, rsi; Src
0x180002853  call    memcpy_0
0x180002858  cmp     qword ptr [rbx+18h], 10h
0x18000285d  jb      short loc_180002864
0x18000285f  mov     rax, [rbx]
0x180002862  jmp     short loc_180002867
0x180002864  mov     rax, rbx
0x180002867  mov     [rbx+10h], rdi
0x18000286b  mov     byte ptr [rax+rdi], 0
0x18000286f  mov     rax, rbx
0x180002872  mov     rbx, [rsp+28h+arg_0]
0x180002877  mov     rsi, [rsp+28h+arg_8]
0x18000287c  add     rsp, 20h
0x180002880  pop     rdi
0x180002881  retn
0x180002882  mov     rcx, rbx
0x180002885  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
