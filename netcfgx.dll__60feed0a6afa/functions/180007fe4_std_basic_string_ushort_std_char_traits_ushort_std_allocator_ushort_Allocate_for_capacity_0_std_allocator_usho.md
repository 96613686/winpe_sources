# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x180007fe4`
- end: `0x180008054`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000805c`
- `0x1800085a0`
- `0x1800086a0`
- `0x180010630`
- `0x180010a00`

## callees

- `0x180007d38`
- `0x180007fe4`
- `0x180008520`

## pseudocode

```c
unsigned __int64 __fastcall std::wstring::_Allocate_for_capacity<0>(__int64 a1, _QWORD *a2)
{
  SIZE_T v3; // rcx
  unsigned __int64 result; // rax
  HANDLE v5; // rax
  HANDLE v6; // rcx

  if ( ++*a2 > 0x7FFFFFFFFFFFFFFFuLL )
    goto LABEL_11;
  v3 = 2LL * *a2;
  if ( !v3 )
  {
    result = 0;
    goto LABEL_10;
  }
  if ( v3 < 0x1000 )
  {
    result = (unsigned __int64)MemAlloc(v3);
    goto LABEL_10;
  }
  if ( v3 + 39 < v3 )
LABEL_11:
    std::_Throw_bad_array_new_length();
  v5 = MemAlloc(v3 + 39);
  v6 = v5;
  if ( !v5 )
    __fastfail(5u);
  result = ((unsigned __int64)v5 + 39) & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(result - 8) = v6;
LABEL_10:
  --*a2;
  return result;
}

```

## disassembly

```asm
0x180007fe4  push    rbx
0x180007fe6  sub     rsp, 20h
0x180007fea  inc     qword ptr [rdx]
0x180007fed  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007ff7  mov     rcx, [rdx]
0x180007ffa  mov     rbx, rdx
0x180007ffd  cmp     rcx, rax
0x180008000  ja      short loc_18000804E
0x180008002  add     rcx, rcx; unsigned __int64
0x180008005  jnz     short loc_18000800B
0x180008007  xor     eax, eax
0x180008009  jmp     short loc_180008045
0x18000800b  cmp     rcx, 1000h
0x180008012  jb      short loc_180008040
0x180008014  lea     rax, [rcx+27h]
0x180008018  cmp     rax, rcx
0x18000801b  jbe     short loc_18000804E
0x18000801d  mov     rcx, rax; unsigned __int64
0x180008020  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180008025  mov     rcx, rax
0x180008028  test    rax, rax
0x18000802b  jnz     short loc_180008032
0x18000802d  lea     ecx, [rax+5]
0x180008030  int     29h; Win8: RtlFailFast(ecx)
0x180008032  add     rax, 27h ; '''
0x180008036  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000803a  mov     [rax-8], rcx
0x18000803e  jmp     short loc_180008045
0x180008040  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x180008045  dec     qword ptr [rbx]
0x180008048  add     rsp, 20h
0x18000804c  pop     rbx
0x18000804d  retn
0x18000804e  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
