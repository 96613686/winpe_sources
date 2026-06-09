# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x180005bf0`
- end: `0x180005c8b`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003eac`
- `0x180005070`
- `0x1800051b0`
- `0x180005354`
- `0x1800056d0`
- `0x180005820`
- `0x18000a564`
- `0x18000a6d8`
- `0x18001076c`

## callees

- `0x1800028c4`
- `0x180005bf0`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Desired_grow_bucket_count(
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
0x180005bf0  push    rbx
0x180005bf2  sub     rsp, 20h
0x180005bf6  mov     rbx, [rcx+38h]
0x180005bfa  xorps   xmm0, xmm0
0x180005bfd  test    rdx, rdx
0x180005c00  js      short loc_180005C09
0x180005c02  cvtsi2ss xmm0, rdx
0x180005c07  jmp     short loc_180005C1E
0x180005c09  mov     rax, rdx
0x180005c0c  and     edx, 1
0x180005c0f  shr     rax, 1
0x180005c12  or      rax, rdx
0x180005c15  cvtsi2ss xmm0, rax
0x180005c1a  addss   xmm0, xmm0
0x180005c1e  divss   xmm0, dword ptr [rcx]; X
0x180005c22  call    _o_ceilf_0
0x180005c27  movss   xmm1, cs:__real@5f000000
0x180005c2f  xor     eax, eax
0x180005c31  comiss  xmm0, xmm1
0x180005c34  jb      short loc_180005C4C
0x180005c36  subss   xmm0, xmm1
0x180005c3a  comiss  xmm0, xmm1
0x180005c3d  jnb     short loc_180005C4C
0x180005c3f  mov     rcx, 8000000000000000h
0x180005c49  mov     rax, rcx
0x180005c4c  mov     edx, 8
0x180005c51  cvttss2si rcx, xmm0
0x180005c56  add     rcx, rax
0x180005c59  cmp     rcx, rdx
0x180005c5c  cmova   rdx, rcx
0x180005c60  cmp     rbx, rdx
0x180005c63  jb      short loc_180005C6A
0x180005c65  mov     rax, rbx
0x180005c68  jmp     short loc_180005C85
0x180005c6a  cmp     rbx, 200h
0x180005c71  jnb     short loc_180005C82
0x180005c73  lea     rax, ds:0[rbx*8]
0x180005c7b  cmp     rax, rdx
0x180005c7e  cmovnb  rdx, rax
0x180005c82  mov     rax, rdx
0x180005c85  add     rsp, 20h
0x180005c89  pop     rbx
0x180005c8a  retn
```
