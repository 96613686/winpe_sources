# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy_deallocate(void)

- ea: `0x1800036b4`
- end: `0x1800036ee`
- name: `?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ`
- size: `58`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010f0`
- `0x180001170`
- `0x180001380`
- `0x18000342c`
- `0x180003448`
- `0x1800035b0`
- `0x1800036a8`
- `0x1800087c0`
- `0x180009824`
- `0x180009a9c`
- `0x180009d00`

## callees

- `0x1800036b4`
- `0x180004270`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy_deallocate(__int64 a1)
{
  unsigned __int64 v1; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
    std::_Deallocate<16>(*(_QWORD **)a1, 2 * v1 + 2);
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800036b4  push    rbx
0x1800036b6  sub     rsp, 20h
0x1800036ba  mov     rdx, [rcx+18h]
0x1800036be  mov     rbx, rcx
0x1800036c1  cmp     rdx, 7
0x1800036c5  jbe     short loc_1800036D7
0x1800036c7  mov     rcx, [rcx]
0x1800036ca  lea     rdx, ds:2[rdx*2]
0x1800036d2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800036d7  xor     eax, eax
0x1800036d9  mov     qword ptr [rbx+18h], 7
0x1800036e1  mov     [rbx+10h], rax
0x1800036e5  mov     [rbx], ax
0x1800036e8  add     rsp, 20h
0x1800036ec  pop     rbx
0x1800036ed  retn
```
