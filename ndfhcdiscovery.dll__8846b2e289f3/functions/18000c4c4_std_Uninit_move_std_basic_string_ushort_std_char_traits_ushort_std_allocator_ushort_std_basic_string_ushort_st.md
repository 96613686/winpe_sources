# std::_Uninit_move<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Wrap_alloc<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000c4c4`
- end: `0x18000c520`
- name: `??$_Uninit_move@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV12@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010eac`

## callees

- `0x180005460`
- `0x18000c4c4`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<std::wstring *,std::wstring *,std::allocator<std::wstring>,std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 32 )
  {
    std::wstring::wstring(a3, i);
    a3 += 32;
  }
  return a3;
}

```

## disassembly

```asm
0x18000c4c4  mov     rax, rsp
0x18000c4c7  mov     [rax+8], rbx
0x18000c4cb  mov     [rax+10h], rsi
0x18000c4cf  mov     [rax+20h], r9
0x18000c4d3  mov     [rax+18h], r8
0x18000c4d7  push    rdi
0x18000c4d8  sub     rsp, 20h
0x18000c4dc  mov     rbx, r8
0x18000c4df  mov     rsi, rdx
0x18000c4e2  mov     rdi, rcx
0x18000c4e5  mov     [rsp+28h+arg_18], rbx
0x18000c4ea  cmp     rcx, rdx
0x18000c4ed  jz      short loc_18000C50C
0x18000c4ef  mov     rdx, rdi
0x18000c4f2  mov     rcx, rbx
0x18000c4f5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c4fa  add     rbx, 20h ; ' '
0x18000c4fe  mov     [rsp+28h+arg_10], rbx
0x18000c503  add     rdi, 20h ; ' '
0x18000c507  cmp     rdi, rsi
0x18000c50a  jnz     short loc_18000C4EF
0x18000c50c  mov     rax, rbx
0x18000c50f  mov     rbx, [rsp+28h+arg_0]
0x18000c514  mov     rsi, [rsp+28h+arg_8]
0x18000c519  add     rsp, 20h
0x18000c51d  pop     rdi
0x18000c51e  retn
```
