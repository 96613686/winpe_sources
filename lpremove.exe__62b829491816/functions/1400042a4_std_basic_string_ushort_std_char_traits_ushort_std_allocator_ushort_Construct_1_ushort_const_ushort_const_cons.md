# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x1400042a4`
- end: `0x140004351`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x140003260`
- `0x1400081a8`
- `0x140008558`
- `0x14000dd80`
- `0x14000e114`
- `0x14000e25c`
- `0x14000eac8`
- `0x14000eeb8`
- `0x14000f358`
- `0x14000f490`
- `0x14000f530`

## callees

- `0x140003211`
- `0x14000422c`
- `0x1400042a4`
- `0x14000cea0`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rax
  __int64 v7; // rbx
  __int64 result; // rax
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  size_t v13; // rbx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    v9 = a3 | 7;
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v3 = a3 | 7;
      if ( v9 < 0xA )
        v3 = 10;
    }
    v14 = v3;
    v10 = std::wstring::_Allocate_for_capacity<0>(v9, &v14);
    v11 = v14;
    a1[2] = a3;
    v12 = v10;
    a1[3] = v11;
    v13 = 2 * a3;
    *a1 = v10;
    memcpy_0(v10, a2, v13);
    result = 0;
    *(_WORD *)((char *)v12 + v13) = 0;
  }
  else
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    memcpy_0(a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)a1 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400042a4  push    rbx
0x1400042a6  push    rbp
0x1400042a7  push    rsi
0x1400042a8  push    rdi
0x1400042a9  sub     rsp, 28h
0x1400042ad  mov     rax, 7FFFFFFFFFFFFFFEh
0x1400042b7  mov     rbx, r8
0x1400042ba  mov     rbp, rdx
0x1400042bd  mov     rsi, rcx
0x1400042c0  cmp     r8, rax
0x1400042c3  ja      loc_14000434B
0x1400042c9  cmp     rbx, 7
0x1400042cd  ja      short loc_1400042EE
0x1400042cf  mov     [rcx+10h], rbx
0x1400042d3  add     rbx, rbx
0x1400042d6  mov     r8, rbx; Size
0x1400042d9  mov     qword ptr [rcx+18h], 7
0x1400042e1  call    memcpy_0
0x1400042e6  xor     eax, eax
0x1400042e8  mov     [rbx+rsi], ax
0x1400042ec  jmp     short loc_140004342
0x1400042ee  mov     rcx, rbx
0x1400042f1  or      rcx, 7
0x1400042f5  cmp     rcx, rax
0x1400042f8  ja      short loc_140004309
0x1400042fa  mov     edx, 0Ah
0x1400042ff  mov     rax, rcx
0x140004302  cmp     rcx, rdx
0x140004305  cmovb   rax, rdx
0x140004309  lea     rdx, [rsp+48h+arg_0]
0x14000430e  mov     [rsp+48h+arg_0], rax
0x140004313  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x140004318  mov     rcx, [rsp+48h+arg_0]
0x14000431d  mov     rdx, rbp; Src
0x140004320  mov     [rsi+10h], rbx
0x140004324  mov     rdi, rax
0x140004327  mov     [rsi+18h], rcx
0x14000432b  add     rbx, rbx
0x14000432e  mov     rcx, rax; void *
0x140004331  mov     [rsi], rax
0x140004334  mov     r8, rbx; Size
0x140004337  call    memcpy_0
0x14000433c  xor     eax, eax
0x14000433e  mov     [rbx+rdi], ax
0x140004342  add     rsp, 28h
0x140004346  pop     rdi
0x140004347  pop     rsi
0x140004348  pop     rbp
0x140004349  pop     rbx
0x14000434a  retn
0x14000434b  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
