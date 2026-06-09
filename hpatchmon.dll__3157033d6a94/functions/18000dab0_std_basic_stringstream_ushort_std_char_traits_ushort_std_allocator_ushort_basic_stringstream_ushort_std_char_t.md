# std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000dab0`
- end: `0x18000db5f`
- name: `??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `175`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b30`
- `0x180001b60`
- `0x180001b90`
- `0x180001bc0`

## import_xrefs

- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18000dae9`
- `msvcp_win!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18000dae9`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18000db32`
- `msvcp_win!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x18000db32`
- `msvcp_win!??0?$basic_iostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x18000db05`
- `msvcp_win!??0?$basic_iostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x18000db05`

## pseudocode

```c
__int64 __fastcall std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
        __int64 a1)
{
  *(_QWORD *)a1 = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_istream<unsigned short>'};
  *(_QWORD *)(a1 + 16) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_ostream<unsigned short>'};
  std::basic_ios<unsigned short>::basic_ios<unsigned short>(a1 + 152);
  std::basic_iostream<unsigned short>::basic_iostream<unsigned short>(a1, a1 + 24, 0);
  *(_QWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(_DWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1 - 4) = *(_DWORD *)(*(_QWORD *)a1 + 4LL) - 152;
  std::basic_streambuf<unsigned short>::basic_streambuf<unsigned short>(a1 + 24);
  *(_QWORD *)(a1 + 24) = &std::basic_stringbuf<unsigned short>::`vftable';
  *(_QWORD *)(a1 + 128) = 0;
  *(_DWORD *)(a1 + 136) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000dab0  mov     rax, rsp
0x18000dab3  mov     [rax+18h], rbx
0x18000dab7  mov     [rax+10h], edx
0x18000daba  mov     [rax+8], rcx
0x18000dabe  push    rdi
0x18000dabf  sub     rsp, 20h
0x18000dac3  mov     rdi, rcx
0x18000dac6  mov     dword ptr [rax+10h], 0
0x18000dacd  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_istream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_istream<ushort>'}
0x18000dad4  mov     [rcx], rax
0x18000dad7  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_ostream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_ostream<ushort>'}
0x18000dade  mov     [rcx+10h], rax
0x18000dae2  add     rcx, 98h
0x18000dae9  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x18000daef  nop
0x18000daf0  mov     [rsp+28h+arg_8], 1
0x18000daf8  lea     rbx, [rdi+18h]
0x18000dafc  xor     r8d, r8d
0x18000daff  mov     rdx, rbx
0x18000db02  mov     rcx, rdi
0x18000db05  call    cs:__imp_??0?$basic_iostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z; std::basic_iostream<ushort>::basic_iostream<ushort>(std::basic_streambuf<ushort> *)
0x18000db0b  nop
0x18000db0c  mov     rax, [rdi]
0x18000db0f  movsxd  rcx, dword ptr [rax+4]
0x18000db13  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x18000db1a  mov     [rcx+rdi], rax
0x18000db1e  mov     rax, [rdi]
0x18000db21  movsxd  rcx, dword ptr [rax+4]
0x18000db25  lea     edx, [rcx-98h]
0x18000db2b  mov     [rcx+rdi-4], edx
0x18000db2f  mov     rcx, rbx
0x18000db32  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x18000db38  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x18000db3f  mov     [rbx], rax
0x18000db42  mov     qword ptr [rbx+68h], 0
0x18000db4a  mov     dword ptr [rbx+70h], 0
0x18000db51  mov     rax, rdi
0x18000db54  mov     rbx, [rsp+28h+arg_10]
0x18000db59  add     rsp, 20h
0x18000db5d  pop     rdi
0x18000db5e  retn
```
