# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Reserve(unsigned __int64)

- ea: `0x140008b0c`
- end: `0x140008b81`
- name: `?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140004ce0`
- `0x14000ad18`
- `0x14000b250`

## callees

- `0x140008994`
- `0x140008b0c`
- `0x140008ca8`

## pseudocode

```c
__int64 __fastcall std::vector<std::wstring>::_Reserve(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 result; // rax
  __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rcx

  v2 = a1[1];
  result = (a1[2] - v2) >> 5;
  if ( !result )
  {
    v4 = (v2 - *a1) >> 5;
    if ( v4 == 0x7FFFFFFFFFFFFFFLL )
      std::vector<std::unique_ptr<ProvPackage>>::_Xlen();
    v5 = v4 + 1;
    v6 = (__int64)(a1[2] - *a1) >> 5;
    v7 = 0;
    if ( 0x7FFFFFFFFFFFFFFLL - (v6 >> 1) >= v6 )
      v7 = v6 + (v6 >> 1);
    if ( v7 >= v5 )
      v5 = v7;
    return std::vector<std::wstring>::_Reallocate(a1, v5);
  }
  return result;
}

```

## disassembly

```asm
0x140008b0c  sub     rsp, 28h
0x140008b10  mov     r9, [rcx+10h]
0x140008b14  mov     r8, rcx
0x140008b17  mov     rdx, [rcx+8]
0x140008b1b  mov     rax, r9
0x140008b1e  sub     rax, rdx
0x140008b21  sar     rax, 5
0x140008b25  cmp     rax, 1
0x140008b29  jnb     short loc_140008B76
0x140008b2b  sub     rdx, [rcx]
0x140008b2e  mov     r10, 7FFFFFFFFFFFFFFh
0x140008b38  sar     rdx, 5
0x140008b3c  mov     rax, r10
0x140008b3f  sub     rax, rdx
0x140008b42  cmp     rax, 1
0x140008b46  jb      short loc_140008B7B
0x140008b48  sub     r9, [rcx]
0x140008b4b  inc     rdx
0x140008b4e  sar     r9, 5
0x140008b52  xor     ecx, ecx
0x140008b54  mov     rax, r9
0x140008b57  shr     rax, 1
0x140008b5a  sub     r10, rax
0x140008b5d  add     rax, r9
0x140008b60  cmp     r10, r9
0x140008b63  cmovnb  rcx, rax
0x140008b67  cmp     rcx, rdx
0x140008b6a  cmovnb  rdx, rcx
0x140008b6e  mov     rcx, r8
0x140008b71  call    ?_Reallocate@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reallocate(unsigned __int64)
0x140008b76  add     rsp, 28h
0x140008b7a  retn
0x140008b7b  call    ?_Xlen@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::unique_ptr<ProvPackage>>::_Xlen(void)
```
