# std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000dd1c`
- end: `0x18000dd91`
- name: `??1?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ`
- size: `117`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dea0`
- `0x1800146b0`
- `0x1800146e0`
- `0x180014710`
- `0x180014740`

## callees

- `0x18000eba8`

## import_xrefs

- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000dd76`
- `msvcp_win!??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000dd76`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18000dd8a`

## pseudocode

```c
__int64 __fastcall std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdx

  v1 = a1 - 128;
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 - 152) + 4LL) + a1 - 152) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  v3 = *(int *)(*(_QWORD *)(a1 - 152) + 4LL);
  *(_DWORD *)(v3 + a1 - 156) = v3 - 152;
  *(_QWORD *)(a1 - 128) = &std::basic_stringbuf<unsigned short>::`vftable';
  std::basic_stringbuf<unsigned short>::_Tidy(a1 - 128);
  std::basic_streambuf<unsigned short>::~basic_streambuf<unsigned short,std::char_traits<unsigned short>>(v1);
  return std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(a1 - 120);
}

```

## disassembly

```asm
0x18000dd1c  mov     [rsp+arg_0], rbx
0x18000dd21  push    rdi
0x18000dd22  sub     rsp, 20h
0x18000dd26  mov     rax, [rcx-98h]
0x18000dd2d  lea     rbx, [rcx-80h]
0x18000dd31  mov     rdi, rcx
0x18000dd34  movsxd  rdx, dword ptr [rax+4]
0x18000dd38  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x18000dd3f  mov     [rdx+rcx-98h], rax
0x18000dd47  mov     rax, [rcx-98h]
0x18000dd4e  movsxd  rdx, dword ptr [rax+4]
0x18000dd52  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x18000dd59  lea     r8d, [rdx-98h]
0x18000dd60  mov     [rdx+rcx-9Ch], r8d
0x18000dd68  mov     rcx, rbx
0x18000dd6b  mov     [rbx], rax
0x18000dd6e  call    ?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ; std::basic_stringbuf<ushort>::_Tidy(void)
0x18000dd73  mov     rcx, rbx
0x18000dd76  call    cs:__imp_??1?$basic_streambuf@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_streambuf<ushort>::~basic_streambuf<ushort,std::char_traits<ushort>>(void)
0x18000dd7c  lea     rcx, [rdi-78h]
0x18000dd80  mov     rbx, [rsp+28h+arg_0]
0x18000dd85  add     rsp, 20h
0x18000dd89  pop     rdi
0x18000dd8a  jmp     cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
```
