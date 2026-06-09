# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x18001adb4`
- end: `0x18001ae50`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA_K_K@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018cd8`

## callees

- `0x180002374`
- `0x18001adb4`

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
0x18001adb4  push    rbx
0x18001adb6  sub     rsp, 20h
0x18001adba  mov     rbx, [rcx+38h]
0x18001adbe  xorps   xmm0, xmm0
0x18001adc1  test    rdx, rdx
0x18001adc4  js      short loc_18001ADCD
0x18001adc6  cvtsi2ss xmm0, rdx
0x18001adcb  jmp     short loc_18001ADE2
0x18001adcd  mov     rax, rdx
0x18001add0  and     edx, 1
0x18001add3  shr     rax, 1
0x18001add6  or      rax, rdx
0x18001add9  cvtsi2ss xmm0, rax
0x18001adde  addss   xmm0, xmm0
0x18001ade2  divss   xmm0, dword ptr [rcx]; X
0x18001ade6  call    _o_ceilf_0
0x18001adeb  movss   xmm1, cs:__real@5f000000
0x18001adf3  xor     eax, eax
0x18001adf5  comiss  xmm0, xmm1
0x18001adf8  jb      short loc_18001AE10
0x18001adfa  subss   xmm0, xmm1
0x18001adfe  comiss  xmm0, xmm1
0x18001ae01  jnb     short loc_18001AE10
0x18001ae03  mov     rcx, 8000000000000000h
0x18001ae0d  mov     rax, rcx
0x18001ae10  mov     edx, 8
0x18001ae15  cvttss2si rcx, xmm0
0x18001ae1a  add     rcx, rax
0x18001ae1d  cmp     rcx, rdx
0x18001ae20  cmova   rdx, rcx
0x18001ae24  cmp     rbx, rdx
0x18001ae27  jb      short loc_18001AE2E
0x18001ae29  mov     rax, rbx
0x18001ae2c  jmp     short loc_18001AE49
0x18001ae2e  cmp     rbx, 200h
0x18001ae35  jnb     short loc_18001AE46
0x18001ae37  lea     rax, ds:0[rbx*8]
0x18001ae3f  cmp     rax, rdx
0x18001ae42  cmovnb  rdx, rax
0x18001ae46  mov     rax, rdx
0x18001ae49  add     rsp, 20h
0x18001ae4d  pop     rbx
0x18001ae4e  retn
```
