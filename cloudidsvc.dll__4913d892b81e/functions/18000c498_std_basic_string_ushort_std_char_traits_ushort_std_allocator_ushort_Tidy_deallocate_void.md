# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy_deallocate(void)

- ea: `0x18000c498`
- end: `0x18000c4d2`
- name: `?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ`
- size: `58`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x180009154`
- `0x18000a700`
- `0x18000a73c`
- `0x18000a7bc`
- `0x18000a93c`
- `0x18000aaf4`
- `0x18000adb8`
- `0x18000b1d0`
- `0x18000b67c`
- `0x18000ba60`
- `0x18000dcc0`
- `0x18000de34`
- `0x18000e0b0`
- `0x18000e668`
- `0x18000e8e8`
- `0x18000eaf4`
- `0x18000ed90`
- `0x18000f4ac`
- `0x18000f7cc`

## callees

- `0x180009014`
- `0x18000c498`

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
0x18000c498  push    rbx
0x18000c49a  sub     rsp, 20h
0x18000c49e  mov     rdx, [rcx+18h]
0x18000c4a2  mov     rbx, rcx
0x18000c4a5  cmp     rdx, 7
0x18000c4a9  jbe     short loc_18000C4BB
0x18000c4ab  mov     rcx, [rcx]
0x18000c4ae  lea     rdx, ds:2[rdx*2]
0x18000c4b6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c4bb  xor     eax, eax
0x18000c4bd  mov     qword ptr [rbx+18h], 7
0x18000c4c5  mov     [rbx+10h], rax
0x18000c4c9  mov     [rbx], ax
0x18000c4cc  add     rsp, 20h
0x18000c4d0  pop     rbx
0x18000c4d1  retn
```
