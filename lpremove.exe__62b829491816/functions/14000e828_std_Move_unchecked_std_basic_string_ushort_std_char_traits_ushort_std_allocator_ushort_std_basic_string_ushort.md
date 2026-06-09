# std::_Move_unchecked<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x14000e828`
- end: `0x14000e870`
- name: `??$_Move_unchecked@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00@Z`
- size: `72`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400104a0`

## callees

- `0x140005a04`
- `0x14000e828`

## pseudocode

```c
__int64 __fastcall std::_Move_unchecked<std::wstring *,std::wstring *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 32 )
  {
    std::wstring::operator=(a3, i);
    a3 += 32;
  }
  return a3;
}

```

## disassembly

```asm
0x14000e828  mov     [rsp+arg_0], rbx
0x14000e82d  mov     [rsp+arg_8], rsi
0x14000e832  push    rdi
0x14000e833  sub     rsp, 20h
0x14000e837  mov     rbx, r8
0x14000e83a  mov     rsi, rdx
0x14000e83d  mov     rdi, rcx
0x14000e840  cmp     rcx, rdx
0x14000e843  jz      short loc_14000E85D
0x14000e845  mov     rdx, rdi
0x14000e848  mov     rcx, rbx
0x14000e84b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000e850  add     rbx, 20h ; ' '
0x14000e854  add     rdi, 20h ; ' '
0x14000e858  cmp     rdi, rsi
0x14000e85b  jnz     short loc_14000E845
0x14000e85d  mov     rsi, [rsp+28h+arg_8]
0x14000e862  mov     rax, rbx
0x14000e865  mov     rbx, [rsp+28h+arg_0]
0x14000e86a  add     rsp, 20h
0x14000e86e  pop     rdi
0x14000e86f  retn
```
