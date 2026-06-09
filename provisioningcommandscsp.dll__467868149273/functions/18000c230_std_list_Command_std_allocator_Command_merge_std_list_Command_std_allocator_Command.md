# std::list<Command,std::allocator<Command>>::merge(std::list<Command,std::allocator<Command>> &)

- ea: `0x18000c230`
- end: `0x18000c357`
- name: `?merge@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXAEAV12@@Z`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c47c`

## callees

- `0x18000c230`
- `0x18000ca0c`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c2ff`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000c2ff`

## pseudocode

```c
void __fastcall std::list<Command>::merge(wchar_t ***a1, wchar_t ***a2)
{
  wchar_t **v2; // r14
  wchar_t **v4; // rsi
  wchar_t *v6; // rdi
  wchar_t *v7; // rbx
  int v8; // ebp
  __int64 **v9; // rcx
  wchar_t *v10; // rdx
  __int64 v11; // rcx
  __int64 **v12; // rax
  unsigned __int64 v13; // rcx
  wchar_t *v14; // rcx

  if ( a2 != a1 )
  {
    v2 = *a1;
    v4 = *a2;
    v6 = **a1;
    v7 = **a2;
    while ( v6 != (wchar_t *)v2 )
    {
      if ( v7 == (wchar_t *)v4 )
        return;
      v8 = std::stoi(v7 + 8);
      if ( v8 >= (int)std::stoi(v6 + 8) )
      {
        v6 = *(wchar_t **)v6;
      }
      else
      {
        v9 = (__int64 **)a1[1];
        if ( v9 == (__int64 **)0x1FFFFFFFFFFFFFELL )
          goto LABEL_11;
        v10 = *(wchar_t **)v7;
        a1[1] = (wchar_t **)((char *)v9 + 1);
        a2[1] = (wchar_t **)((char *)a2[1] - 1);
        **((_QWORD **)v7 + 1) = v10;
        **((_QWORD **)v10 + 1) = v6;
        **((_QWORD **)v6 + 1) = v7;
        v11 = *((_QWORD *)v6 + 1);
        *((_QWORD *)v6 + 1) = *((_QWORD *)v10 + 1);
        *((_QWORD *)v10 + 1) = *((_QWORD *)v7 + 1);
        *((_QWORD *)v7 + 1) = v11;
        v7 = v10;
      }
    }
    if ( v7 != (wchar_t *)v4 )
    {
      v12 = (__int64 **)a1[1];
      v13 = (unsigned __int64)a2[1];
      if ( 0x1FFFFFFFFFFFFFELL - (__int64)v12 < v13 )
LABEL_11:
        std::_Xlength_error("list<T> too long");
      a1[1] = (wchar_t **)((char *)v12 + v13);
      a2[1] = (wchar_t **)((char *)a2[1] - v13);
      **((_QWORD **)v7 + 1) = v4;
      *(_QWORD *)v4[1] = v2;
      *(_QWORD *)v2[1] = v7;
      v14 = v2[1];
      v2[1] = v4[1];
      v4[1] = (wchar_t *)*((_QWORD *)v7 + 1);
      *((_QWORD *)v7 + 1) = v14;
    }
  }
}

```

## disassembly

```asm
0x18000c230  cmp     rdx, rcx
0x18000c233  jz      locret_18000C355
0x18000c239  push    rbx
0x18000c23a  push    rbp
0x18000c23b  push    rsi
0x18000c23c  push    rdi
0x18000c23d  push    r12
0x18000c23f  push    r13
0x18000c241  push    r14
0x18000c243  push    r15
0x18000c245  sub     rsp, 28h
0x18000c249  mov     r14, [rcx]
0x18000c24c  mov     r12, rdx
0x18000c24f  mov     rsi, [rdx]
0x18000c252  mov     r15, rcx
0x18000c255  mov     r13, 1FFFFFFFFFFFFFEh
0x18000c25f  mov     rdi, [r14]
0x18000c262  mov     rbx, [rsi]
0x18000c265  cmp     rdi, r14
0x18000c268  jz      short loc_18000C2E2
0x18000c26a  cmp     rbx, rsi
0x18000c26d  jz      loc_18000C345
0x18000c273  lea     rcx, [rbx+10h]; String
0x18000c277  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x18000c27c  lea     rcx, [rdi+10h]; String
0x18000c280  mov     ebp, eax
0x18000c282  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x18000c287  cmp     ebp, eax
0x18000c289  jge     short loc_18000C2DD
0x18000c28b  mov     rcx, [r15+8]
0x18000c28f  mov     rax, r13
0x18000c292  sub     rax, rcx
0x18000c295  cmp     rax, 1
0x18000c299  jb      short loc_18000C2F8
0x18000c29b  mov     rdx, [rbx]
0x18000c29e  lea     rax, [rcx+1]
0x18000c2a2  mov     [r15+8], rax
0x18000c2a6  dec     qword ptr [r12+8]
0x18000c2ab  mov     rax, [rbx+8]
0x18000c2af  mov     [rax], rdx
0x18000c2b2  mov     rax, [rdx+8]
0x18000c2b6  mov     [rax], rdi
0x18000c2b9  mov     rax, [rdi+8]
0x18000c2bd  mov     [rax], rbx
0x18000c2c0  mov     rax, [rdx+8]
0x18000c2c4  mov     rcx, [rdi+8]
0x18000c2c8  mov     [rdi+8], rax
0x18000c2cc  mov     rax, [rbx+8]
0x18000c2d0  mov     [rdx+8], rax
0x18000c2d4  mov     [rbx+8], rcx
0x18000c2d8  mov     rbx, rdx
0x18000c2db  jmp     short loc_18000C265
0x18000c2dd  mov     rdi, [rdi]
0x18000c2e0  jmp     short loc_18000C265
0x18000c2e2  cmp     rbx, rsi
0x18000c2e5  jz      short loc_18000C345
0x18000c2e7  mov     rax, [r15+8]
0x18000c2eb  mov     rcx, [r12+8]
0x18000c2f0  sub     r13, rax
0x18000c2f3  cmp     r13, rcx
0x18000c2f6  jnb     short loc_18000C30C
0x18000c2f8  lea     rcx, aListTTooLong; "list<T> too long"
0x18000c2ff  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000c30c  add     rax, rcx
0x18000c30f  mov     [r15+8], rax
0x18000c313  sub     [r12+8], rcx
0x18000c318  mov     rax, [rbx+8]
0x18000c31c  mov     [rax], rsi
0x18000c31f  mov     rax, [rsi+8]
0x18000c323  mov     [rax], r14
0x18000c326  mov     rax, [r14+8]
0x18000c32a  mov     [rax], rbx
0x18000c32d  mov     rax, [rsi+8]
0x18000c331  mov     rcx, [r14+8]
0x18000c335  mov     [r14+8], rax
0x18000c339  mov     rax, [rbx+8]
0x18000c33d  mov     [rsi+8], rax
0x18000c341  mov     [rbx+8], rcx
0x18000c345  add     rsp, 28h
0x18000c349  pop     r15
0x18000c34b  pop     r14
0x18000c34d  pop     r13
0x18000c34f  pop     r12
0x18000c351  pop     rdi
0x18000c352  pop     rsi
0x18000c353  pop     rbp
0x18000c354  pop     rbx
0x18000c355  retn
```
