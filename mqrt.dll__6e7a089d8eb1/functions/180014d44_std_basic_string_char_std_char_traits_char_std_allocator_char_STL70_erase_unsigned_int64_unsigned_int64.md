# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x180014d44`
- end: `0x180014dcc`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014bf0`

## callees

- `0x180001920`
- `0x180014d44`

## import_xrefs

- `msvcrt!memmove_s` at `0x180014da1`
- `msvcrt!memmove_s` at `0x180014da1`

## pseudocode

```c
_QWORD *__fastcall std::string::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  unsigned __int64 v11; // rax

  v3 = a3;
  if ( a1[3] < a2 )
    std::_String_base::_Xran();
  v6 = a1[3] - a2;
  if ( v6 < a3 )
    v3 = a1[3] - a2;
  if ( v3 )
  {
    v7 = a1[4];
    v8 = a1 + 1;
    if ( v7 < 0x10 )
    {
      v9 = a1 + 1;
      v10 = a1 + 1;
    }
    else
    {
      v9 = (_QWORD *)*v8;
      v10 = (_QWORD *)*v8;
    }
    memmove_s((char *)v9 + a2, v7 - a2, (char *)v10 + a2 + v3, v6 - v3);
    v11 = a1[3] - v3;
    if ( a1[4] >= 0x10u )
      v8 = (_QWORD *)*v8;
    a1[3] = v11;
    *((_BYTE *)v8 + v11) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180014d44  push    rbx
0x180014d46  push    rbp
0x180014d47  push    rsi
0x180014d48  push    rdi
0x180014d49  sub     rsp, 28h
0x180014d4d  mov     rsi, r8
0x180014d50  mov     rbp, rdx
0x180014d53  mov     rbx, rcx
0x180014d56  cmp     [rcx+18h], rdx
0x180014d5a  jnb     short loc_180014D61
0x180014d5c  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180014d61  mov     r9, [rbx+18h]
0x180014d65  sub     r9, rbp
0x180014d68  cmp     r9, rsi
0x180014d6b  cmovb   rsi, r9
0x180014d6f  test    rsi, rsi
0x180014d72  jz      short loc_180014DC0
0x180014d74  mov     rdx, [rbx+20h]
0x180014d78  lea     rdi, [rbx+8]
0x180014d7c  cmp     rdx, 10h
0x180014d80  jb      short loc_180014D8A
0x180014d82  mov     rax, [rdi]
0x180014d85  mov     rcx, rax
0x180014d88  jmp     short loc_180014D90
0x180014d8a  mov     rax, rdi
0x180014d8d  mov     rcx, rdi
0x180014d90  lea     r8, [rcx+rbp]
0x180014d94  sub     r9, rsi; SourceSize
0x180014d97  add     r8, rsi; Source
0x180014d9a  lea     rcx, [rax+rbp]; Destination
0x180014d9e  sub     rdx, rbp; DestinationSize
0x180014da1  call    cs:__imp_memmove_s
0x180014da7  mov     rax, [rbx+18h]
0x180014dab  sub     rax, rsi
0x180014dae  cmp     qword ptr [rbx+20h], 10h
0x180014db3  jb      short loc_180014DB8
0x180014db5  mov     rdi, [rdi]
0x180014db8  mov     [rbx+18h], rax
0x180014dbc  mov     byte ptr [rax+rdi], 0
0x180014dc0  mov     rax, rbx
0x180014dc3  add     rsp, 28h
0x180014dc7  pop     rdi
0x180014dc8  pop     rsi
0x180014dc9  pop     rbp
0x180014dca  pop     rbx
0x180014dcb  retn
```
