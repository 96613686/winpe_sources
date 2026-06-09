# Rdp::Utils::Props::IPropertyStore_GetWString(IPropertyStore *,_tagpropertykey const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180013e3c`
- end: `0x180013f29`
- name: `?IPropertyStore_GetWString@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001339c`
- `0x18001367c`
- `0x1800140a8`
- `0x1800193e4`

## callees

- `0x180006a74`
- `0x18000ef54`
- `0x180013e3c`
- `0x18002834c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013e94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013eab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013f0a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013e94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013eab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180013f0a`

## string_xrefs

- `0x180013e7d`: `onecoreuap\termsrv\rdp_bin\win\common/inc/PropsHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Utils::Props::IPropertyStore_GetWString(__int64 a1, __int64 a2, char **a3)
{
  int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // edi
  const char *v7; // r9
  __int64 result; // rax
  PROPVARIANT v9; // r9
  unsigned __int64 v10; // rdx
  char *v11; // rdi
  __int64 v12; // rbx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v14; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_OWORD *)pvar = 0;
  v14 = 0;
  try
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
    v6 = v4;
    if ( v4 >= 0 )
    {
      if ( LOWORD(pvar[0]) == 31 )
      {
        v9 = pvar[1];
        v10 = -1;
        do
          ++v10;
        while ( *((_WORD *)pvar[1] + v10) );
        if ( v10 > (unsigned __int64)a3[3] )
        {
          ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
            a3,
            v10,
            v5,
            pvar[1]);
        }
        else
        {
          if ( (unsigned __int64)a3[3] <= 7 )
            v11 = (char *)a3;
          else
            v11 = *a3;
          a3[2] = (char *)v10;
          v12 = 2 * v10;
          memmove_0(v11, v9, 2 * v10);
          *(_WORD *)&v11[v12] = 0;
        }
        PropVariantClear(pvar);
        result = 0;
      }
      else
      {
        PropVariantClear(pvar);
        result = 2147500037LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFB,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
        (const char *)(unsigned int)v4,
        (int)pvar[0]);
      PropVariantClear(pvar);
      result = v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x104,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/PropsHelpers.h",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180013e3c  mov     r11, rsp
0x180013e3f  mov     [r11+10h], rbx
0x180013e43  mov     [r11+18h], rsi
0x180013e47  push    rdi
0x180013e48  sub     rsp, 40h
0x180013e4c  mov     rbx, r8
0x180013e4f  xorps   xmm0, xmm0
0x180013e52  xor     eax, eax
0x180013e54  movups  xmmword ptr [rsp+48h+pvar], xmm0; int
0x180013e59  mov     [r11-18h], rax
0x180013e5d  mov     rax, [rcx]
0x180013e60  lea     r8, [r11-28h]
0x180013e64  mov     rax, [rax+28h]
0x180013e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e6d  mov     edi, eax
0x180013e6f  xor     esi, esi
0x180013e71  test    eax, eax
0x180013e73  jns     short loc_180013E9E
0x180013e75  mov     rcx, [rsp+48h]; this
0x180013e7a  mov     r9d, eax; char *
0x180013e7d  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180013e84  mov     edx, 0FBh; void *
0x180013e89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e8e  nop
0x180013e8f  lea     rcx, [rsp+48h+pvar]; pvar
0x180013e94  call    cs:__imp_PropVariantClear
0x180013e9a  mov     eax, edi
0x180013e9c  jmp     short loc_180013F18
0x180013e9e  cmp     word ptr [rsp+48h+pvar], 1Fh
0x180013ea4  jz      short loc_180013EB8
0x180013ea6  lea     rcx, [rsp+48h+pvar]; pvar
0x180013eab  call    cs:__imp_PropVariantClear
0x180013eb1  mov     eax, 80004005h
0x180013eb6  jmp     short loc_180013F18
0x180013eb8  mov     r9, [rsp+48h+pvar+8]
0x180013ebd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180013ec1  inc     rdx
0x180013ec4  cmp     [r9+rdx*2], si
0x180013ec9  jnz     short loc_180013EC1
0x180013ecb  cmp     rdx, [rbx+18h]
0x180013ecf  ja      short loc_180013EFC
0x180013ed1  cmp     qword ptr [rbx+18h], 7
0x180013ed6  jbe     short loc_180013EDD
0x180013ed8  mov     rdi, [rbx]
0x180013edb  jmp     short loc_180013EE0
0x180013edd  mov     rdi, rbx
0x180013ee0  mov     [rbx+10h], rdx
0x180013ee4  lea     rbx, [rdx+rdx]
0x180013ee8  mov     r8, rbx; Size
0x180013eeb  mov     rdx, r9; Src
0x180013eee  mov     rcx, rdi; void *
0x180013ef1  call    memmove_0
0x180013ef6  mov     [rbx+rdi], si
0x180013efa  jmp     short loc_180013F05
0x180013efc  mov     rcx, rbx
0x180013eff  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180013f04  nop
0x180013f05  lea     rcx, [rsp+48h+pvar]; pvar
0x180013f0a  call    cs:__imp_PropVariantClear
0x180013f10  xor     eax, eax
0x180013f12  jmp     short loc_180013F18
0x180013f14  mov     eax, [rsp+48h+arg_0]
0x180013f18  mov     rbx, [rsp+48h+arg_8]
0x180013f1d  mov     rsi, [rsp+48h+arg_10]
0x180013f22  add     rsp, 40h
0x180013f26  pop     rdi
0x180013f27  retn
```
