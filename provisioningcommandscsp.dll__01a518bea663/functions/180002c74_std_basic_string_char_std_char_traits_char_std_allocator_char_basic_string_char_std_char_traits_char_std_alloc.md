# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x180002c74`
- end: `0x180002d21`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `173`
- prototype: `_QWORD *__fastcall(_QWORD *, _BYTE *Src)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005d40`
- `0x180005d80`
- `0x180005dd0`

## callees

- `0x180002c74`
- `0x180005a0c`
- `0x180005b8c`
- `0x18000c5b6`

## pseudocode

```c
_QWORD *__fastcall std::string::string(_QWORD *a1, _BYTE *Src)
{
  size_t v4; // rdi
  void *v5; // rcx
  _QWORD *v6; // rax

  a1[3] = 15;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  if ( *Src )
  {
    v4 = -1;
    do
      ++v4;
    while ( Src[v4] );
  }
  else
  {
    v4 = 0;
  }
  if ( v4 == -1 )
    std::wstring::_Xlen();
  if ( v4 <= 0xF )
  {
    if ( !v4 )
    {
      a1[2] = 0;
      *(_BYTE *)a1 = 0;
      return a1;
    }
  }
  else
  {
    std::string::_Copy(a1);
  }
  if ( a1[3] < 0x10u )
    v5 = a1;
  else
    v5 = (void *)*a1;
  memcpy_0(v5, Src, v4);
  if ( a1[3] < 0x10u )
    v6 = a1;
  else
    v6 = (_QWORD *)*a1;
  a1[2] = v4;
  *((_BYTE *)v6 + v4) = 0;
  return a1;
}

```

## disassembly

```asm
0x180002c74  mov     [rsp+arg_0], rbx
0x180002c79  mov     [rsp+arg_8], rsi
0x180002c7e  push    rdi
0x180002c7f  sub     rsp, 20h
0x180002c83  mov     qword ptr [rcx+18h], 0Fh
0x180002c8b  mov     rsi, rdx
0x180002c8e  mov     qword ptr [rcx+10h], 0
0x180002c96  mov     rbx, rcx
0x180002c99  mov     byte ptr [rcx], 0
0x180002c9c  cmp     byte ptr [rdx], 0
0x180002c9f  jnz     short loc_180002CA5
0x180002ca1  xor     edi, edi
0x180002ca3  jmp     short loc_180002CB2
0x180002ca5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002ca9  inc     rdi
0x180002cac  cmp     byte ptr [rdx+rdi], 0
0x180002cb0  jnz     short loc_180002CA9
0x180002cb2  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180002cb6  ja      short loc_180002D1B
0x180002cb8  cmp     rdi, 0Fh
0x180002cbc  jbe     short loc_180002CD5
0x180002cbe  xor     r8d, r8d
0x180002cc1  mov     rdx, rdi
0x180002cc4  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002cc9  cmp     qword ptr [rbx+18h], 10h
0x180002cce  jb      short loc_180002CE3
0x180002cd0  mov     rcx, [rbx]
0x180002cd3  jmp     short loc_180002CE6
0x180002cd5  test    rdi, rdi
0x180002cd8  jnz     short loc_180002CC9
0x180002cda  mov     [rcx+10h], rdi
0x180002cde  mov     [rcx], dil
0x180002ce1  jmp     short loc_180002D08
0x180002ce3  mov     rcx, rbx; void *
0x180002ce6  mov     r8, rdi; Size
0x180002ce9  mov     rdx, rsi; Src
0x180002cec  call    memcpy_0
0x180002cf1  cmp     qword ptr [rbx+18h], 10h
0x180002cf6  jb      short loc_180002CFD
0x180002cf8  mov     rax, [rbx]
0x180002cfb  jmp     short loc_180002D00
0x180002cfd  mov     rax, rbx
0x180002d00  mov     [rbx+10h], rdi
0x180002d04  mov     byte ptr [rax+rdi], 0
0x180002d08  mov     rsi, [rsp+28h+arg_8]
0x180002d0d  mov     rax, rbx
0x180002d10  mov     rbx, [rsp+28h+arg_0]
0x180002d15  add     rsp, 20h
0x180002d19  pop     rdi
0x180002d1a  retn
0x180002d1b  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
