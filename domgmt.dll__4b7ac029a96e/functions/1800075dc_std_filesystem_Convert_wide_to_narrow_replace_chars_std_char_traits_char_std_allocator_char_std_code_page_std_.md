# std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort,std::char_traits<ushort>>,std::allocator<char> const &)

- ea: `0x1800075dc`
- end: `0x180007734`
- name: `??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z`
- size: `344`
- prototype: `_QWORD *__fastcall(_QWORD *Src, UINT CodePage, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a59c`

## callees

- `0x180001218`
- `0x18000296c`
- `0x1800075dc`
- `0x180007ae8`
- `0x18000a9bc`
- `0x18000a9fc`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
        _QWORD *Src,
        UINT CodePage,
        __int64 a3)
{
  int v5; // r15d
  const WCHAR *v6; // r12
  __int64 v7; // rbx
  unsigned __int64 v8; // rdx
  _QWORD *v9; // rax
  unsigned __int64 v10; // r14
  _QWORD *v11; // rax
  char *v12; // rdi
  CHAR *v13; // r9
  unsigned __int64 v14; // rax

  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  if ( *(_QWORD *)(a3 + 8) )
  {
    if ( *(_QWORD *)(a3 + 8) > 0x7FFFFFFFu )
      std::_Throw_system_error();
    v5 = *(_DWORD *)(a3 + 8);
    v6 = *(const WCHAR **)a3;
    v7 = _std_fs_convert_wide_to_narrow_replace_chars(CodePage, *(LPCWCH *)a3, v5, 0, 0);
    if ( HIDWORD(v7) )
      ((void (__noreturn *)(void))std::_Throw_system_error_from_std_win_error)();
    v8 = Src[2];
    if ( (int)v7 > v8 )
    {
      v10 = (int)v7 - v8;
      if ( v10 > Src[3] - v8 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34__KD_Z__KD___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0D_Z__KD_Z(Src);
      }
      else
      {
        Src[2] = (int)v7;
        if ( Src[3] <= 0xFu )
          v11 = Src;
        else
          v11 = (_QWORD *)*Src;
        v12 = (char *)v11 + v8;
        memset_0((char *)v11 + v8, 0, (int)v7 - v8);
        v12[v10] = 0;
      }
    }
    else
    {
      Src[2] = (int)v7;
      if ( Src[3] <= 0xFu )
        v9 = Src;
      else
        v9 = (_QWORD *)*Src;
      *((_BYTE *)v9 + (int)v7) = 0;
    }
    if ( Src[3] <= 0xFu )
      v13 = (CHAR *)Src;
    else
      v13 = (CHAR *)*Src;
    v14 = (unsigned __int64)_std_fs_convert_wide_to_narrow_replace_chars(CodePage, v6, v5, v13, v7) >> 32;
    if ( (_DWORD)v14 )
      std::_Throw_system_error_from_std_win_error((unsigned int)v14);
  }
  return Src;
}

```

## disassembly

```asm
0x1800075dc  mov     rax, rsp
0x1800075df  mov     [rax+10h], rbx
0x1800075e3  mov     [rax+18h], rbp
0x1800075e7  mov     [rax+8], rcx
0x1800075eb  push    rsi
0x1800075ec  push    rdi
0x1800075ed  push    r12
0x1800075ef  push    r14
0x1800075f1  push    r15
0x1800075f3  sub     rsp, 40h
0x1800075f7  mov     ebp, edx
0x1800075f9  mov     rsi, rcx
0x1800075fc  mov     dword ptr [rax-38h], 0
0x180007603  xorps   xmm0, xmm0
0x180007606  movups  xmmword ptr [rcx], xmm0
0x180007609  mov     qword ptr [rcx+10h], 0
0x180007611  mov     qword ptr [rcx+18h], 0Fh
0x180007619  mov     byte ptr [rcx], 0
0x18000761c  mov     dword ptr [rax-38h], 1
0x180007623  cmp     qword ptr [r8+8], 0
0x180007628  jz      loc_180007704
0x18000762e  cmp     qword ptr [r8+8], 7FFFFFFFh
0x180007636  ja      loc_180007728
0x18000763c  mov     r15d, [r8+8]
0x180007640  mov     r12, [r8]
0x180007643  mov     dword ptr [rax-48h], 0
0x18000764a  xor     r9d, r9d; lpMultiByteStr
0x18000764d  mov     r8d, r15d; cchWideChar
0x180007650  mov     rdx, r12; lpWideCharStr
0x180007653  mov     ecx, ebp; CodePage
0x180007655  call    __std_fs_convert_wide_to_narrow_replace_chars
0x18000765a  mov     rbx, rax
0x18000765d  mov     rcx, rax
0x180007660  shr     rcx, 20h
0x180007664  test    ecx, ecx
0x180007666  jnz     loc_18000772E
0x18000766c  mov     rdx, [rsi+10h]
0x180007670  movsxd  rcx, ebx
0x180007673  cmp     rcx, rdx
0x180007676  ja      short loc_180007691
0x180007678  mov     [rsi+10h], rcx
0x18000767c  cmp     qword ptr [rsi+18h], 0Fh
0x180007681  jbe     short loc_180007688
0x180007683  mov     rax, [rsi]
0x180007686  jmp     short loc_18000768B
0x180007688  mov     rax, rsi
0x18000768b  mov     byte ptr [rcx+rax], 0
0x18000768f  jmp     short loc_1800076DC
0x180007691  mov     r14, rcx
0x180007694  sub     r14, rdx
0x180007697  mov     rax, [rsi+18h]
0x18000769b  sub     rax, rdx
0x18000769e  cmp     r14, rax
0x1800076a1  ja      short loc_1800076CE
0x1800076a3  mov     [rsi+10h], rcx
0x1800076a7  cmp     qword ptr [rsi+18h], 0Fh
0x1800076ac  jbe     short loc_1800076B3
0x1800076ae  mov     rax, [rsi]
0x1800076b1  jmp     short loc_1800076B6
0x1800076b3  mov     rax, rsi
0x1800076b6  lea     rdi, [rdx+rax]
0x1800076ba  mov     r8, r14; Size
0x1800076bd  xor     edx, edx; Val
0x1800076bf  mov     rcx, rdi; void *
0x1800076c2  call    memset_0
0x1800076c7  mov     byte ptr [r14+rdi], 0
0x1800076cc  jmp     short loc_1800076DC
0x1800076ce  mov     r9, r14
0x1800076d1  mov     rdx, r14
0x1800076d4  mov     rcx, rsi; Src
0x1800076d7  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@_KD@Z@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0D@Z@_KD@Z; std::string::_Reallocate_grow_by<`std::string::append(unsigned __int64,char)'::`2'::_lambda_1_,unsigned __int64,char>(unsigned __int64,`std::string::append(unsigned __int64,char)'::`2'::_lambda_1_,unsigned __int64,char)
0x1800076dc  cmp     qword ptr [rsi+18h], 0Fh
0x1800076e1  jbe     short loc_1800076E8
0x1800076e3  mov     r9, [rsi]
0x1800076e6  jmp     short loc_1800076EB
0x1800076e8  mov     r9, rsi; lpMultiByteStr
0x1800076eb  mov     [rsp+68h+var_48], ebx; int
0x1800076ef  mov     r8d, r15d; cchWideChar
0x1800076f2  mov     rdx, r12; lpWideCharStr
0x1800076f5  mov     ecx, ebp; CodePage
0x1800076f7  call    __std_fs_convert_wide_to_narrow_replace_chars
0x1800076fc  shr     rax, 20h
0x180007700  test    eax, eax
0x180007702  jnz     short loc_180007720
0x180007704  mov     rax, rsi
0x180007707  lea     r11, [rsp+68h+var_28]
0x18000770c  mov     rbx, [r11+38h]
0x180007710  mov     rbp, [r11+40h]
0x180007714  mov     rsp, r11
0x180007717  pop     r15
0x180007719  pop     r14
0x18000771b  pop     r12
0x18000771d  pop     rdi
0x18000771e  pop     rsi
0x18000771f  retn
0x180007720  mov     ecx, eax
0x180007722  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
0x180007728  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x18000772e  call    ?_Throw_system_error_from_std_win_error@std@@YAXW4__std_win_error@@@Z; std::_Throw_system_error_from_std_win_error(__std_win_error)
```
