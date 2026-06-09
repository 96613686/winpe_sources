# std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Desired_grow_bucket_count(unsigned __int64)

- ea: `0x18000d304`
- end: `0x18000d39f`
- name: `?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@U_GUID@@PEAXV?$_Uhash_compare@U_GUID@@UIIDHash@IUnknownBase@Com@Utils@Rdp@@U?$equal_to@U_GUID@@@std@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAX@std@@@3@$0A@@std@@@std@@IEBA_K_K@Z`
- size: `155`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009e04`
- `0x18001c52c`
- `0x18001f55c`
- `0x18001f704`
- `0x18001f8ac`

## callees

- `0x180004124`
- `0x18000d304`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_GUID,void *,std::_Uhash_compare<_GUID,Rdp::Utils::Com::IUnknownBase::IIDHash,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,void *>>,0>>::_Desired_grow_bucket_count(
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
0x18000d304  push    rbx
0x18000d306  sub     rsp, 20h
0x18000d30a  mov     rbx, [rcx+38h]
0x18000d30e  xorps   xmm0, xmm0
0x18000d311  test    rdx, rdx
0x18000d314  js      short loc_18000D31D
0x18000d316  cvtsi2ss xmm0, rdx
0x18000d31b  jmp     short loc_18000D332
0x18000d31d  mov     rax, rdx
0x18000d320  and     edx, 1
0x18000d323  shr     rax, 1
0x18000d326  or      rax, rdx
0x18000d329  cvtsi2ss xmm0, rax
0x18000d32e  addss   xmm0, xmm0
0x18000d332  divss   xmm0, dword ptr [rcx]; X
0x18000d336  call    _o_ceilf_0
0x18000d33b  movss   xmm1, cs:__real@5f000000
0x18000d343  xor     eax, eax
0x18000d345  comiss  xmm0, xmm1
0x18000d348  jb      short loc_18000D360
0x18000d34a  subss   xmm0, xmm1
0x18000d34e  comiss  xmm0, xmm1
0x18000d351  jnb     short loc_18000D360
0x18000d353  mov     rcx, 8000000000000000h
0x18000d35d  mov     rax, rcx
0x18000d360  mov     edx, 8
0x18000d365  cvttss2si rcx, xmm0
0x18000d36a  add     rcx, rax
0x18000d36d  cmp     rcx, rdx
0x18000d370  cmova   rdx, rcx
0x18000d374  cmp     rbx, rdx
0x18000d377  jb      short loc_18000D37E
0x18000d379  mov     rax, rbx
0x18000d37c  jmp     short loc_18000D399
0x18000d37e  cmp     rbx, 200h
0x18000d385  jnb     short loc_18000D396
0x18000d387  lea     rax, ds:0[rbx*8]
0x18000d38f  cmp     rax, rdx
0x18000d392  cmovnb  rdx, rax
0x18000d396  mov     rax, rdx
0x18000d399  add     rsp, 20h
0x18000d39d  pop     rbx
0x18000d39e  retn
```
