# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x18001a31c`
- end: `0x18001a3b7`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA_K_K@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018328`

## callees

- `0x180002354`
- `0x18001a31c`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Desired_grow_bucket_count(
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
0x18001a31c  push    rbx
0x18001a31e  sub     rsp, 20h
0x18001a322  mov     rbx, [rcx+38h]
0x18001a326  xorps   xmm0, xmm0
0x18001a329  test    rdx, rdx
0x18001a32c  js      short loc_18001A335
0x18001a32e  cvtsi2ss xmm0, rdx
0x18001a333  jmp     short loc_18001A34A
0x18001a335  mov     rax, rdx
0x18001a338  and     edx, 1
0x18001a33b  shr     rax, 1
0x18001a33e  or      rax, rdx
0x18001a341  cvtsi2ss xmm0, rax
0x18001a346  addss   xmm0, xmm0
0x18001a34a  divss   xmm0, dword ptr [rcx]; X
0x18001a34e  call    _o_ceilf_0
0x18001a353  movss   xmm1, cs:__real@5f000000
0x18001a35b  xor     eax, eax
0x18001a35d  comiss  xmm0, xmm1
0x18001a360  jb      short loc_18001A378
0x18001a362  subss   xmm0, xmm1
0x18001a366  comiss  xmm0, xmm1
0x18001a369  jnb     short loc_18001A378
0x18001a36b  mov     rcx, 8000000000000000h
0x18001a375  mov     rax, rcx
0x18001a378  mov     edx, 8
0x18001a37d  cvttss2si rcx, xmm0
0x18001a382  add     rcx, rax
0x18001a385  cmp     rcx, rdx
0x18001a388  cmova   rdx, rcx
0x18001a38c  cmp     rbx, rdx
0x18001a38f  jb      short loc_18001A396
0x18001a391  mov     rax, rbx
0x18001a394  jmp     short loc_18001A3B1
0x18001a396  cmp     rbx, 200h
0x18001a39d  jnb     short loc_18001A3AE
0x18001a39f  lea     rax, ds:0[rbx*8]
0x18001a3a7  cmp     rax, rdx
0x18001a3aa  cmovnb  rdx, rax
0x18001a3ae  mov     rax, rdx
0x18001a3b1  add     rsp, 20h
0x18001a3b5  pop     rbx
0x18001a3b6  retn
```
