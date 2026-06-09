# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy_deallocate(void)

- ea: `0x180007fd4`
- end: `0x18000800e`
- name: `?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ`
- size: `58`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ff4`
- `0x180007268`
- `0x180007b7c`

## callees

- `0x180006af0`
- `0x180007fd4`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy_deallocate(__int64 a1)
{
  unsigned __int64 v1; // rdx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
    std::_Deallocate<16>(*(void **)a1, (struct std::nothrow_t *)(2 * v1 + 2));
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180007fd4  push    rbx
0x180007fd6  sub     rsp, 20h
0x180007fda  mov     rdx, [rcx+18h]
0x180007fde  mov     rbx, rcx
0x180007fe1  cmp     rdx, 7
0x180007fe5  jbe     short loc_180007FF7
0x180007fe7  mov     rcx, [rcx]
0x180007fea  lea     rdx, ds:2[rdx*2]
0x180007ff2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180007ff7  xor     eax, eax
0x180007ff9  mov     qword ptr [rbx+18h], 7
0x180008001  mov     [rbx+10h], rax
0x180008005  mov     [rbx], ax
0x180008008  add     rsp, 20h
0x18000800c  pop     rbx
0x18000800d  retn
```
