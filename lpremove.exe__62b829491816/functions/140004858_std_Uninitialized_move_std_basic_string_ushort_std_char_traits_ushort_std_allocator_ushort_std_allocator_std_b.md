# std::_Uninitialized_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &)

- ea: `0x140004858`
- end: `0x1400048a3`
- name: `??$_Uninitialized_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z`
- size: `75`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400104a0`
- `0x14001053a`

## callees

- `0x140004858`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<std::wstring *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rax

  for ( i = a1; i != a2; i += 32 )
  {
    *(_OWORD *)a3 = 0;
    *(_QWORD *)(a3 + 16) = 0;
    *(_QWORD *)(a3 + 24) = 0;
    *(_OWORD *)a3 = *(_OWORD *)i;
    *(_OWORD *)(a3 + 16) = *(_OWORD *)(i + 16);
    *(_QWORD *)(i + 16) = 0;
    a3 += 32;
    *(_QWORD *)(i + 24) = 7;
    *(_WORD *)i = 0;
  }
  return a3;
}

```

## disassembly

```asm
0x140004858  mov     rax, rcx
0x14000485b  cmp     rcx, rdx
0x14000485e  jz      short loc_14000489F
0x140004860  xor     r9d, r9d
0x140004863  xorps   xmm0, xmm0
0x140004866  movups  xmmword ptr [r8], xmm0
0x14000486a  mov     [r8+10h], r9
0x14000486e  mov     [r8+18h], r9
0x140004872  movups  xmm0, xmmword ptr [rax]
0x140004875  movups  xmmword ptr [r8], xmm0
0x140004879  movups  xmm1, xmmword ptr [rax+10h]
0x14000487d  movups  xmmword ptr [r8+10h], xmm1
0x140004882  mov     [rax+10h], r9
0x140004886  add     r8, 20h ; ' '
0x14000488a  mov     qword ptr [rax+18h], 7
0x140004892  mov     [rax], r9w
0x140004896  add     rax, 20h ; ' '
0x14000489a  cmp     rax, rdx
0x14000489d  jnz     short loc_140004863
0x14000489f  mov     rax, r8
0x1400048a2  retn
```
