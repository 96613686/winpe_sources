# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x18000f36c`
- end: `0x18000f3ff`
- name: `?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000edd8`

## callees

- `0x180001990`
- `0x18000f36c`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000f3d1`
- `msvcrt!memmove_s` at `0x18000f3d1`

## pseudocode

```c
_QWORD *__fastcall std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::erase(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rcx
  _QWORD *v10; // r8
  unsigned __int64 v11; // rcx

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
    if ( v7 < 8 )
    {
      v9 = a1 + 1;
      v10 = a1 + 1;
    }
    else
    {
      v9 = (_QWORD *)*v8;
      v10 = (_QWORD *)*v8;
    }
    memmove_s((char *)v9 + 2 * a2, 2 * (v7 - a2), (char *)v10 + 2 * a2 + 2 * v3, 2 * (v6 - v3));
    v11 = a1[3] - v3;
    if ( a1[4] >= 8u )
      v8 = (_QWORD *)*v8;
    a1[3] = v11;
    *((_WORD *)v8 + v11) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000f36c  push    rbx
0x18000f36e  push    rsi
0x18000f36f  push    rdi
0x18000f370  push    r14
0x18000f372  sub     rsp, 28h
0x18000f376  mov     rsi, r8
0x18000f379  mov     r14, rdx
0x18000f37c  mov     rbx, rcx
0x18000f37f  cmp     [rcx+18h], rdx
0x18000f383  jnb     short loc_18000F38A
0x18000f385  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18000f38a  mov     r9, [rbx+18h]
0x18000f38e  sub     r9, r14
0x18000f391  cmp     r9, rsi
0x18000f394  cmovb   rsi, r9
0x18000f398  test    rsi, rsi
0x18000f39b  jz      short loc_18000F3F2
0x18000f39d  mov     rdx, [rbx+20h]
0x18000f3a1  lea     rdi, [rbx+8]
0x18000f3a5  cmp     rdx, 8
0x18000f3a9  jb      short loc_18000F3B3
0x18000f3ab  mov     rcx, [rdi]
0x18000f3ae  mov     r8, rcx
0x18000f3b1  jmp     short loc_18000F3B9
0x18000f3b3  mov     rcx, rdi
0x18000f3b6  mov     r8, rdi
0x18000f3b9  sub     r9, rsi
0x18000f3bc  lea     rax, [r14+rsi]
0x18000f3c0  sub     rdx, r14
0x18000f3c3  lea     r8, [r8+rax*2]; Source
0x18000f3c7  add     r9, r9; SourceSize
0x18000f3ca  lea     rcx, [rcx+r14*2]; Destination
0x18000f3ce  add     rdx, rdx; DestinationSize
0x18000f3d1  call    cs:__imp_memmove_s
0x18000f3d7  mov     rcx, [rbx+18h]
0x18000f3db  sub     rcx, rsi
0x18000f3de  cmp     qword ptr [rbx+20h], 8
0x18000f3e3  jb      short loc_18000F3E8
0x18000f3e5  mov     rdi, [rdi]
0x18000f3e8  xor     eax, eax
0x18000f3ea  mov     [rbx+18h], rcx
0x18000f3ee  mov     [rdi+rcx*2], ax
0x18000f3f2  mov     rax, rbx
0x18000f3f5  add     rsp, 28h
0x18000f3f9  pop     r14
0x18000f3fb  pop     rdi
0x18000f3fc  pop     rsi
0x18000f3fd  pop     rbx
0x18000f3fe  retn
```
