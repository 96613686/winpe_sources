# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x18000bee0`
- end: `0x18000bf7b`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b67c`
- `0x18000c358`

## callees

- `0x1800024b4`
- `0x18000bee0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Desired_grow_bucket_count(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v2; // rbx
  float v3; // xmm0_4
  float v4; // xmm0_4
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx

  v2 = *(_QWORD *)(a1 + 56);
  if ( a2 < 0 )
    v3 = (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1))
       + (float)(a2 & 1 | (unsigned int)((unsigned __int64)a2 >> 1));
  else
    v3 = (float)(int)a2;
  v4 = o_ceilf_0(v3 / *(float *)a1);
  v5 = 0;
  if ( v4 >= 9.223372e18 )
  {
    v4 = v4 - 9.223372e18;
    if ( v4 < 9.223372e18 )
      v5 = 0x8000000000000000uLL;
  }
  v6 = 8;
  if ( v5 + (unsigned int)(int)v4 > 8 )
    v6 = v5 + (unsigned int)(int)v4;
  if ( v2 >= v6 )
    return v2;
  if ( v2 < 0x200 && 8 * v2 >= v6 )
    return 8 * v2;
  return v6;
}

```

## disassembly

```asm
0x18000bee0  push    rbx
0x18000bee2  sub     rsp, 20h
0x18000bee6  mov     rbx, [rcx+38h]
0x18000beea  xorps   xmm0, xmm0
0x18000beed  test    rdx, rdx
0x18000bef0  js      short loc_18000BEF9
0x18000bef2  cvtsi2ss xmm0, rdx
0x18000bef7  jmp     short loc_18000BF0E
0x18000bef9  mov     rax, rdx
0x18000befc  and     edx, 1
0x18000beff  shr     rax, 1
0x18000bf02  or      rax, rdx
0x18000bf05  cvtsi2ss xmm0, rax
0x18000bf0a  addss   xmm0, xmm0
0x18000bf0e  divss   xmm0, dword ptr [rcx]; X
0x18000bf12  call    _o_ceilf_0
0x18000bf17  movss   xmm1, cs:__real@5f000000
0x18000bf1f  xor     eax, eax
0x18000bf21  comiss  xmm0, xmm1
0x18000bf24  jb      short loc_18000BF3C
0x18000bf26  subss   xmm0, xmm1
0x18000bf2a  comiss  xmm0, xmm1
0x18000bf2d  jnb     short loc_18000BF3C
0x18000bf2f  mov     rcx, 8000000000000000h
0x18000bf39  mov     rax, rcx
0x18000bf3c  mov     edx, 8
0x18000bf41  cvttss2si rcx, xmm0
0x18000bf46  add     rcx, rax
0x18000bf49  cmp     rcx, rdx
0x18000bf4c  cmova   rdx, rcx
0x18000bf50  cmp     rbx, rdx
0x18000bf53  jb      short loc_18000BF5A
0x18000bf55  mov     rax, rbx
0x18000bf58  jmp     short loc_18000BF75
0x18000bf5a  cmp     rbx, 200h
0x18000bf61  jnb     short loc_18000BF72
0x18000bf63  lea     rax, ds:0[rbx*8]
0x18000bf6b  cmp     rax, rdx
0x18000bf6e  cmovnb  rdx, rax
0x18000bf72  mov     rax, rdx
0x18000bf75  add     rsp, 20h
0x18000bf79  pop     rbx
0x18000bf7a  retn
```
