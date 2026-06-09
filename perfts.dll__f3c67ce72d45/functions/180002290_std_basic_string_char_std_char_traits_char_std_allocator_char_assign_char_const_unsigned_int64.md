# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180002290`
- end: `0x180002387`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002510`
- `0x180002580`
- `0x180002610`

## callees

- `0x180001f88`
- `0x180002110`
- `0x180002198`
- `0x180002290`
- `0x180002806`

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
    std::string::_Xlen(v5);
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
0x180002290  mov     [rsp+arg_0], rbx
0x180002295  mov     [rsp+arg_8], rsi
0x18000229a  push    rdi
0x18000229b  sub     rsp, 20h
0x18000229f  mov     rdi, r8
0x1800022a2  mov     rsi, rdx
0x1800022a5  mov     rbx, rcx
0x1800022a8  test    rdx, rdx
0x1800022ab  jz      short loc_1800022F9
0x1800022ad  cmp     qword ptr [rcx+18h], 10h
0x1800022b2  jb      short loc_1800022B9
0x1800022b4  mov     rax, [rcx]
0x1800022b7  jmp     short loc_1800022BC
0x1800022b9  mov     rax, rbx
0x1800022bc  cmp     rsi, rax
0x1800022bf  jb      short loc_1800022F9
0x1800022c1  cmp     qword ptr [rcx+18h], 10h
0x1800022c6  jb      short loc_1800022CB
0x1800022c8  mov     rcx, [rcx]
0x1800022cb  add     rcx, [rbx+10h]
0x1800022cf  cmp     rcx, rsi
0x1800022d2  jbe     short loc_1800022F9
0x1800022d4  cmp     qword ptr [rbx+18h], 10h
0x1800022d9  jb      short loc_1800022E0
0x1800022db  mov     rax, [rbx]
0x1800022de  jmp     short loc_1800022E3
0x1800022e0  mov     rax, rbx
0x1800022e3  sub     rsi, rax
0x1800022e6  mov     r9, rdi
0x1800022e9  mov     r8, rsi
0x1800022ec  mov     rdx, rbx
0x1800022ef  mov     rcx, rbx; void *
0x1800022f2  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1800022f7  jmp     short loc_18000236E
0x1800022f9  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800022fd  ja      short loc_18000237E
0x1800022ff  cmp     [rbx+18h], rdi
0x180002303  jnb     short loc_180002325
0x180002305  mov     r8, [rbx+10h]
0x180002309  mov     rdx, rdi
0x18000230c  mov     rcx, rbx; Src
0x18000230f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002314  test    rdi, rdi
0x180002317  jz      short loc_18000236B
0x180002319  cmp     qword ptr [rbx+18h], 10h
0x18000231e  jb      short loc_180002346
0x180002320  mov     rcx, [rbx]
0x180002323  jmp     short loc_180002349
0x180002325  test    rdi, rdi
0x180002328  jnz     short loc_180002319
0x18000232a  cmp     qword ptr [rbx+18h], 10h
0x18000232f  jb      short loc_180002336
0x180002331  mov     rax, [rbx]
0x180002334  jmp     short loc_180002339
0x180002336  mov     rax, rbx
0x180002339  mov     qword ptr [rbx+10h], 0
0x180002341  mov     byte ptr [rax], 0
0x180002344  jmp     short loc_18000236B
0x180002346  mov     rcx, rbx; void *
0x180002349  mov     r8, rdi; Size
0x18000234c  mov     rdx, rsi; Src
0x18000234f  call    memcpy_0
0x180002354  cmp     qword ptr [rbx+18h], 10h
0x180002359  jb      short loc_180002360
0x18000235b  mov     rax, [rbx]
0x18000235e  jmp     short loc_180002363
0x180002360  mov     rax, rbx
0x180002363  mov     [rbx+10h], rdi
0x180002367  mov     byte ptr [rax+rdi], 0
0x18000236b  mov     rax, rbx
0x18000236e  mov     rbx, [rsp+28h+arg_0]
0x180002373  mov     rsi, [rsp+28h+arg_8]
0x180002378  add     rsp, 20h
0x18000237c  pop     rdi
0x18000237d  retn
0x18000237e  mov     rcx, rbx
0x180002381  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
