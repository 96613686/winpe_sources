# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1800016c0`
- end: `0x1800017b7`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001940`
- `0x1800019b0`
- `0x180001a40`

## callees

- `0x1800013b8`
- `0x180001540`
- `0x1800015c8`
- `0x1800016c0`
- `0x180002676`

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
0x1800016c0  mov     [rsp+arg_0], rbx
0x1800016c5  mov     [rsp+arg_8], rsi
0x1800016ca  push    rdi
0x1800016cb  sub     rsp, 20h
0x1800016cf  mov     rdi, r8
0x1800016d2  mov     rsi, rdx
0x1800016d5  mov     rbx, rcx
0x1800016d8  test    rdx, rdx
0x1800016db  jz      short loc_180001729
0x1800016dd  cmp     qword ptr [rcx+18h], 10h
0x1800016e2  jb      short loc_1800016E9
0x1800016e4  mov     rax, [rcx]
0x1800016e7  jmp     short loc_1800016EC
0x1800016e9  mov     rax, rbx
0x1800016ec  cmp     rsi, rax
0x1800016ef  jb      short loc_180001729
0x1800016f1  cmp     qword ptr [rcx+18h], 10h
0x1800016f6  jb      short loc_1800016FB
0x1800016f8  mov     rcx, [rcx]
0x1800016fb  add     rcx, [rbx+10h]
0x1800016ff  cmp     rcx, rsi
0x180001702  jbe     short loc_180001729
0x180001704  cmp     qword ptr [rbx+18h], 10h
0x180001709  jb      short loc_180001710
0x18000170b  mov     rax, [rbx]
0x18000170e  jmp     short loc_180001713
0x180001710  mov     rax, rbx
0x180001713  sub     rsi, rax
0x180001716  mov     r9, rdi
0x180001719  mov     r8, rsi
0x18000171c  mov     rdx, rbx
0x18000171f  mov     rcx, rbx; void *
0x180001722  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180001727  jmp     short loc_18000179E
0x180001729  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000172d  ja      short loc_1800017AE
0x18000172f  cmp     [rbx+18h], rdi
0x180001733  jnb     short loc_180001755
0x180001735  mov     r8, [rbx+10h]
0x180001739  mov     rdx, rdi
0x18000173c  mov     rcx, rbx; Src
0x18000173f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180001744  test    rdi, rdi
0x180001747  jz      short loc_18000179B
0x180001749  cmp     qword ptr [rbx+18h], 10h
0x18000174e  jb      short loc_180001776
0x180001750  mov     rcx, [rbx]
0x180001753  jmp     short loc_180001779
0x180001755  test    rdi, rdi
0x180001758  jnz     short loc_180001749
0x18000175a  cmp     qword ptr [rbx+18h], 10h
0x18000175f  jb      short loc_180001766
0x180001761  mov     rax, [rbx]
0x180001764  jmp     short loc_180001769
0x180001766  mov     rax, rbx
0x180001769  mov     qword ptr [rbx+10h], 0
0x180001771  mov     byte ptr [rax], 0
0x180001774  jmp     short loc_18000179B
0x180001776  mov     rcx, rbx; void *
0x180001779  mov     r8, rdi; Size
0x18000177c  mov     rdx, rsi; Src
0x18000177f  call    memcpy_0
0x180001784  cmp     qword ptr [rbx+18h], 10h
0x180001789  jb      short loc_180001790
0x18000178b  mov     rax, [rbx]
0x18000178e  jmp     short loc_180001793
0x180001790  mov     rax, rbx
0x180001793  mov     [rbx+10h], rdi
0x180001797  mov     byte ptr [rax+rdi], 0
0x18000179b  mov     rax, rbx
0x18000179e  mov     rbx, [rsp+28h+arg_0]
0x1800017a3  mov     rsi, [rsp+28h+arg_8]
0x1800017a8  add     rsp, 20h
0x1800017ac  pop     rdi
0x1800017ad  retn
0x1800017ae  mov     rcx, rbx
0x1800017b1  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
