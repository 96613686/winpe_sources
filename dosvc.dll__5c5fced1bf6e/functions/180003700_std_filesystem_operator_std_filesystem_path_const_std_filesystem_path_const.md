# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180003700`
- end: `0x1800038ee`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `494`
- prototype: `_QWORD *__fastcall(_QWORD *Src, _QWORD *, std::filesystem *this)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x1800010f0`
- `0x180001170`
- `0x180001380`
- `0x1800035b0`
- `0x180009d00`

## callees

- `0x180001f30`
- `0x180002f20`
- `0x180003700`
- `0x1800038f4`
- `0x180003e14`
- `0x1800094bc`
- `0x18000a6d4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000385d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000385d`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::operator/(_QWORD *Src, _QWORD *a2, std::filesystem *this)
{
  const unsigned __int16 *v6; // r8
  std::filesystem *v7; // rcx
  _WORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int8 v11; // dl
  __int16 v12; // ax
  unsigned __int64 v13; // rbp
  __int64 v14; // rcx
  void *v15; // rax
  _QWORD v17[2]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int8 v18; // [rsp+30h] [rbp-38h]
  _WORD *v19; // [rsp+38h] [rbp-30h]
  __int64 v20; // [rsp+40h] [rbp-28h]
  __int64 v21; // [rsp+80h] [rbp+18h] BYREF

  LODWORD(v21) = 1;
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 2);
  if ( *((_QWORD *)this + 3) <= 7u )
    v7 = this;
  else
    v7 = *(std::filesystem **)this;
  if ( v6
    && !std::filesystem::_Has_drive_letter_prefix(v7, (const unsigned __int16 *const)v7 + (_QWORD)v6, v6)
    && *v8 != 92
    && *v8 != 47 )
  {
    v10 = a2[2];
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    if ( v10 == 2 )
    {
      if ( (*(_DWORD *)a2 & 0xFFFFFFDF) - 3801153 < 0x1A )
        goto LABEL_12;
    }
    else if ( !v10 )
    {
      goto LABEL_12;
    }
    v12 = *((_WORD *)a2 + v10 - 1);
    if ( v12 != 92 && v12 != 47 )
    {
      v11 = 1;
      goto LABEL_13;
    }
LABEL_12:
    v11 = 0;
LABEL_13:
    *(_OWORD *)Src = 0;
    Src[2] = 0;
    Src[3] = 7;
    *(_WORD *)Src = 0;
    LODWORD(v21) = 1;
    v17[0] = a2;
    v17[1] = v10;
    v18 = v11;
    v19 = v8;
    v20 = v9;
    ____Resize_and_overwrite_V_lambda_1___4___Kfilesystem_std__YA_AVpath_23_AEBV423_0_Z____basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAX_KV_lambda_1___4___Kfilesystem_1_YA_AVpath_31_AEBV431_1_Z__Z(
      Src,
      v9 + v10 + v11,
      v17);
    return Src;
  }
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 0;
  v13 = a2[2];
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  if ( v13 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v13 > 7 )
  {
    v21 = std::wstring::_Calculate_growth(v13, 7);
    v15 = (void *)std::wstring::_Allocate_for_capacity<0>(v14, &v21);
    *Src = v15;
    Src[2] = v13;
    Src[3] = v21;
    memcpy_0(v15, a2, 2 * v13 + 2);
  }
  else
  {
    Src[2] = v13;
    Src[3] = 7;
    *(_OWORD *)Src = *(_OWORD *)a2;
  }
  LODWORD(v21) = 3;
  std::filesystem::path::operator/=(Src, this);
  return Src;
}

```

## disassembly

```asm
0x180003700  mov     [rsp+arg_8], rbx
0x180003705  mov     [rsp+arg_0], rcx
0x18000370a  push    rbp
0x18000370b  push    rsi
0x18000370c  push    rdi
0x18000370d  sub     rsp, 50h
0x180003711  mov     rsi, r8
0x180003714  mov     rbx, rdx
0x180003717  mov     rdi, rcx
0x18000371a  mov     dword ptr [rsp+68h+arg_10], 1
0x180003725  mov     r8, [r8+10h]; unsigned __int16 *
0x180003729  cmp     qword ptr [rsi+18h], 7
0x18000372e  jbe     short loc_180003735
0x180003730  mov     rcx, [rsi]
0x180003733  jmp     short loc_180003738
0x180003735  mov     rcx, rsi; this
0x180003738  test    r8, r8
0x18000373b  jz      loc_180003829
0x180003741  lea     rdx, [rcx+r8*2]; unsigned __int16 *
0x180003745  call    ?_Has_drive_letter_prefix@filesystem@std@@YA_NQEBG0@Z; std::filesystem::_Has_drive_letter_prefix(ushort const * const,ushort const * const)
0x18000374a  test    al, al
0x18000374c  jnz     loc_180003829
0x180003752  movzx   eax, word ptr [rcx]
0x180003755  cmp     ax, 5Ch ; '\'
0x180003759  jz      loc_180003829
0x18000375f  cmp     ax, 2Fh ; '/'
0x180003763  jz      loc_180003829
0x180003769  mov     r9, [rbx+10h]
0x18000376d  cmp     qword ptr [rbx+18h], 7
0x180003772  jbe     short loc_180003777
0x180003774  mov     rbx, [rbx]
0x180003777  cmp     r9, 2
0x18000377b  jnz     loc_180003803
0x180003781  mov     eax, [rbx]
0x180003783  and     eax, 0FFFFFFDFh
0x180003786  sub     eax, 3A0041h
0x18000378b  cmp     eax, 1Ah
0x18000378e  jnb     short loc_180003808
0x180003790  xor     dl, dl
0x180003792  xorps   xmm0, xmm0
0x180003795  movups  xmmword ptr [rdi], xmm0
0x180003798  xor     eax, eax
0x18000379a  mov     [rdi+10h], rax
0x18000379e  mov     qword ptr [rdi+18h], 7
0x1800037a6  mov     [rdi], ax
0x1800037a9  mov     dword ptr [rsp+68h+arg_10], 1
0x1800037b4  mov     [rsp+68h+var_48], rbx
0x1800037b9  mov     [rsp+68h+var_40], r9
0x1800037be  mov     [rsp+68h+var_38], dl
0x1800037c2  mov     eax, [rsp+68h+var_37]
0x1800037c6  mov     [rsp+68h+var_37], eax
0x1800037ca  movzx   eax, [rsp+68h+var_33]
0x1800037cf  mov     [rsp+68h+var_33], ax
0x1800037d4  movzx   eax, [rsp+68h+var_31]
0x1800037d9  mov     [rsp+68h+var_31], al
0x1800037dd  mov     [rsp+68h+var_30], rcx
0x1800037e2  mov     [rsp+68h+var_28], r8
0x1800037e7  movzx   edx, dl
0x1800037ea  add     rdx, r9
0x1800037ed  add     rdx, r8
0x1800037f0  lea     r8, [rsp+68h+var_48]
0x1800037f5  mov     rcx, rdi
0x1800037f8  call    ??$_Resize_and_overwrite@V_lambda_1_@?4???Kfilesystem@std@@YA?AVpath@23@AEBV423@0@Z@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KV_lambda_1_@?4???Kfilesystem@1@YA?AVpath@31@AEBV431@1@Z@@Z; std::wstring::_Resize_and_overwrite<`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_>(unsigned __int64,`std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)'::`5'::_lambda_1_)
0x1800037fd  nop
0x1800037fe  jmp     loc_1800038DE
0x180003803  test    r9, r9
0x180003806  jz      short loc_180003790
0x180003808  movzx   eax, word ptr [rbx+r9*2-2]
0x18000380e  cmp     ax, 5Ch ; '\'
0x180003812  jz      loc_180003790
0x180003818  cmp     ax, 2Fh ; '/'
0x18000381c  jz      loc_180003790
0x180003822  mov     dl, 1
0x180003824  jmp     loc_180003792
0x180003829  xorps   xmm0, xmm0
0x18000382c  movups  xmmword ptr [rdi], xmm0
0x18000382f  xor     eax, eax
0x180003831  mov     [rdi+10h], rax
0x180003835  mov     [rdi+18h], rax
0x180003839  mov     rbp, [rbx+10h]
0x18000383d  cmp     qword ptr [rbx+18h], 7
0x180003842  jbe     short loc_180003847
0x180003844  mov     rbx, [rbx]
0x180003847  mov     r8, 7FFFFFFFFFFFFFFEh
0x180003851  cmp     rbp, r8
0x180003854  jbe     short loc_180003864
0x180003856  lea     rcx, aStringTooLong; "string too long"
0x18000385d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180003864  cmp     rbp, 7
0x180003868  ja      short loc_18000387E
0x18000386a  mov     [rdi+10h], rbp
0x18000386e  mov     qword ptr [rdi+18h], 7
0x180003876  movups  xmm0, xmmword ptr [rbx]
0x180003879  movups  xmmword ptr [rdi], xmm0
0x18000387c  jmp     short loc_1800038C7
0x18000387e  mov     edx, 7
0x180003883  mov     rcx, rbp
0x180003886  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18000388b  mov     [rsp+68h+arg_10], rax
0x180003893  lea     rdx, [rsp+68h+arg_10]
0x18000389b  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x1800038a0  mov     [rdi], rax
0x1800038a3  mov     [rdi+10h], rbp
0x1800038a7  mov     rcx, [rsp+68h+arg_10]
0x1800038af  mov     [rdi+18h], rcx
0x1800038b3  lea     r8, ds:2[rbp*2]; Size
0x1800038bb  mov     rdx, rbx; Src
0x1800038be  mov     rcx, rax; void *
0x1800038c1  call    memcpy_0
0x1800038c6  nop
0x1800038c7  mov     dword ptr [rsp+68h+arg_10], 3
0x1800038d2  mov     rdx, rsi; this
0x1800038d5  mov     rcx, rdi; Src
0x1800038d8  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x1800038dd  nop
0x1800038de  mov     rax, rdi
0x1800038e1  mov     rbx, [rsp+68h+arg_8]
0x1800038e6  add     rsp, 50h
0x1800038ea  pop     rdi
0x1800038eb  pop     rsi
0x1800038ec  pop     rbp
0x1800038ed  retn
```
