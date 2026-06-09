# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::find(ushort const * const,unsigned __int64)

- ea: `0x140009d24`
- end: `0x140009da6`
- name: `?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140008590`
- `0x14000a604`
- `0x14000ba74`

## callees

- `0x140001910`
- `0x140009d24`

## pseudocode

```c
__int64 __fastcall std::wstring::find(_QWORD *a1, __int64 a2, unsigned __int64 a3)
{
  _QWORD *v3; // rdi
  unsigned __int64 v4; // r9
  unsigned __int64 v5; // rcx
  char *v6; // rbx
  __int64 v7; // rax

  v3 = a1;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a2 + 2 * v4) );
  v5 = a1[2];
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  if ( v4 > v5 || a3 > v5 - v4 )
    return -1;
  if ( v4 )
  {
    v6 = (char *)v3 + 2 * v5;
    v7 = _std_search_2((char *)v3 + 2 * a3, v6, a2);
    if ( (char *)v7 != v6 )
      return (v7 - (__int64)v3) >> 1;
    return -1;
  }
  return a3;
}

```

## disassembly

```asm
0x140009d24  mov     [rsp+arg_0], rbx
0x140009d29  mov     [rsp+arg_8], rsi
0x140009d2e  push    rdi
0x140009d2f  sub     rsp, 20h
0x140009d33  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140009d37  mov     rdi, rcx
0x140009d3a  mov     r9, rsi
0x140009d3d  xor     r10d, r10d
0x140009d40  inc     r9
0x140009d43  cmp     [rdx+r9*2], r10w
0x140009d48  jnz     short loc_140009D40
0x140009d4a  cmp     qword ptr [rdi+18h], 7
0x140009d4f  mov     rcx, [rcx+10h]
0x140009d53  jbe     short loc_140009D58
0x140009d55  mov     rdi, [rdi]
0x140009d58  cmp     r9, rcx
0x140009d5b  ja      short loc_140009D90
0x140009d5d  mov     rax, rcx
0x140009d60  sub     rax, r9
0x140009d63  cmp     r8, rax
0x140009d66  ja      short loc_140009D90
0x140009d68  test    r9, r9
0x140009d6b  jz      short loc_140009D93
0x140009d6d  lea     rbx, [rdi+rcx*2]
0x140009d71  lea     rcx, [rdi+r8*2]
0x140009d75  mov     r8, rdx
0x140009d78  mov     rdx, rbx
0x140009d7b  call    __std_search_2
0x140009d80  mov     r8, rax
0x140009d83  cmp     rax, rbx
0x140009d86  jz      short loc_140009D90
0x140009d88  sub     r8, rdi
0x140009d8b  sar     r8, 1
0x140009d8e  jmp     short loc_140009D93
0x140009d90  mov     r8, rsi
0x140009d93  mov     rbx, [rsp+28h+arg_0]
0x140009d98  mov     rax, r8
0x140009d9b  mov     rsi, [rsp+28h+arg_8]
0x140009da0  add     rsp, 20h
0x140009da4  pop     rdi
0x140009da5  retn
```
