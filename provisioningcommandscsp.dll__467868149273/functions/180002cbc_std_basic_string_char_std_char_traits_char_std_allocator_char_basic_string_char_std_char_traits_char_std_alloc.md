# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x180002cbc`
- end: `0x180002d6a`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `174`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180006000`
- `0x180006040`
- `0x180006090`

## callees

- `0x180002cbc`
- `0x180005be8`
- `0x180005d7c`
- `0x18000cc76`

## pseudocode

```c
const void **__fastcall std::string::string(const void **a1, _BYTE *Src)
{
  unsigned __int64 v4; // rdi
  void *v5; // rcx
  _QWORD *v6; // rax

  a1[3] = (const void *)15;
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
    std::string::_Copy(a1, v4, 0);
  }
  if ( (unsigned __int64)a1[3] < 0x10 )
    v5 = a1;
  else
    v5 = (void *)*a1;
  memcpy_0(v5, Src, v4);
  if ( (unsigned __int64)a1[3] < 0x10 )
    v6 = a1;
  else
    v6 = *a1;
  a1[2] = (const void *)v4;
  *((_BYTE *)v6 + v4) = 0;
  return a1;
}

```

## disassembly

```asm
0x180002cbc  mov     [rsp+arg_0], rbx
0x180002cc1  mov     [rsp+arg_8], rsi
0x180002cc6  push    rdi
0x180002cc7  sub     rsp, 20h
0x180002ccb  mov     qword ptr [rcx+18h], 0Fh
0x180002cd3  mov     rsi, rdx
0x180002cd6  mov     qword ptr [rcx+10h], 0
0x180002cde  mov     rbx, rcx
0x180002ce1  mov     byte ptr [rcx], 0
0x180002ce4  cmp     byte ptr [rdx], 0
0x180002ce7  jnz     short loc_180002CED
0x180002ce9  xor     edi, edi
0x180002ceb  jmp     short loc_180002CFA
0x180002ced  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002cf1  inc     rdi
0x180002cf4  cmp     byte ptr [rdx+rdi], 0
0x180002cf8  jnz     short loc_180002CF1
0x180002cfa  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180002cfe  ja      short loc_180002D64
0x180002d00  cmp     rdi, 0Fh
0x180002d04  jbe     short loc_180002D1D
0x180002d06  xor     r8d, r8d
0x180002d09  mov     rdx, rdi
0x180002d0c  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002d11  cmp     qword ptr [rbx+18h], 10h
0x180002d16  jb      short loc_180002D2B
0x180002d18  mov     rcx, [rbx]
0x180002d1b  jmp     short loc_180002D2E
0x180002d1d  test    rdi, rdi
0x180002d20  jnz     short loc_180002D11
0x180002d22  mov     [rcx+10h], rdi
0x180002d26  mov     [rcx], dil
0x180002d29  jmp     short loc_180002D50
0x180002d2b  mov     rcx, rbx; void *
0x180002d2e  mov     r8, rdi; Size
0x180002d31  mov     rdx, rsi; Src
0x180002d34  call    memcpy_0
0x180002d39  cmp     qword ptr [rbx+18h], 10h
0x180002d3e  jb      short loc_180002D45
0x180002d40  mov     rax, [rbx]
0x180002d43  jmp     short loc_180002D48
0x180002d45  mov     rax, rbx
0x180002d48  mov     [rbx+10h], rdi
0x180002d4c  mov     byte ptr [rax+rdi], 0
0x180002d50  mov     rsi, [rsp+28h+arg_8]
0x180002d55  mov     rax, rbx
0x180002d58  mov     rbx, [rsp+28h+arg_0]
0x180002d5d  add     rsp, 20h
0x180002d61  pop     rdi
0x180002d62  retn
0x180002d64  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
