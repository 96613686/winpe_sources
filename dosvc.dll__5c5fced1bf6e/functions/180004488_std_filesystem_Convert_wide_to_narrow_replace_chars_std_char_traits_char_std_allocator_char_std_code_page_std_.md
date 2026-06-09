# std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort,std::char_traits<ushort>>,std::allocator<char> const &)

- ea: `0x180004488`
- end: `0x180004606`
- name: `??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z`
- size: `382`
- prototype: `_QWORD *__fastcall(_QWORD *Src, UINT CodePage, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800042a4`

## callees

- `0x180004488`
- `0x180004694`
- `0x180005b2c`
- `0x180005b50`
- `0x1800090b0`
- `0x1800099a8`
- `0x180009f40`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
        _QWORD *Src,
        UINT CodePage,
        __int64 a3)
{
  int v5; // r14d
  const WCHAR *v6; // r15
  __int64 v7; // rax
  int v8; // eax
  int v9; // r12d
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  unsigned __int64 v13; // rsi
  _QWORD *v14; // rax
  char *v15; // rbx
  CHAR *v16; // r9
  __int64 v17; // rax
  int v19; // [rsp+40h] [rbp-68h] BYREF
  void ***v20; // [rsp+48h] [rbp-60h]
  _BYTE pExceptionObject[48]; // [rsp+50h] [rbp-58h] BYREF

  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  if ( *(_QWORD *)(a3 + 8) )
  {
    if ( *(_QWORD *)(a3 + 8) > 0x7FFFFFFFu )
    {
      v19 = 22;
      v20 = &`std::_Immortalize_memcpy_image<std::_Generic_error_category>'::`2'::_Static;
      std::system_error::system_error(pExceptionObject, &v19);
      throw (std::system_error *)pExceptionObject;
    }
    v5 = *(_DWORD *)(a3 + 8);
    v6 = *(const WCHAR **)a3;
    v7 = _std_fs_convert_wide_to_narrow_replace_chars(CodePage, *(LPCWCH *)a3, v5, 0, 0);
    v8 = std::_Check_convert_result(v7);
    v9 = v8;
    v10 = Src[2];
    v11 = v8;
    if ( v8 > v10 )
    {
      v13 = v8 - v10;
      if ( v13 > Src[3] - v10 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34__KD_Z__KD___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0D_Z__KD_Z(Src);
      }
      else
      {
        Src[2] = v8;
        if ( Src[3] <= 0xFu )
          v14 = Src;
        else
          v14 = (_QWORD *)*Src;
        v15 = (char *)v14 + v10;
        memset_0((char *)v14 + v10, 0, v11 - v10);
        v15[v13] = 0;
      }
    }
    else
    {
      Src[2] = v8;
      if ( Src[3] <= 0xFu )
        v12 = Src;
      else
        v12 = (_QWORD *)*Src;
      *((_BYTE *)v12 + v8) = 0;
    }
    if ( Src[3] <= 0xFu )
      v16 = (CHAR *)Src;
    else
      v16 = (CHAR *)*Src;
    v17 = _std_fs_convert_wide_to_narrow_replace_chars(CodePage, v6, v5, v16, v9);
    std::_Check_convert_result(v17);
  }
  return Src;
}

```

## disassembly

```asm
0x180004488  mov     rax, rsp
0x18000448b  mov     [rax+10h], rbx
0x18000448f  mov     [rax+18h], rbp
0x180004493  mov     [rax+8], rcx
0x180004497  push    rsi
0x180004498  push    rdi
0x180004499  push    r12
0x18000449b  push    r14
0x18000449d  push    r15
0x18000449f  sub     rsp, 80h
0x1800044a6  mov     ebp, edx
0x1800044a8  mov     rdi, rcx
0x1800044ab  mov     dword ptr [rax-78h], 0
0x1800044b2  xorps   xmm0, xmm0
0x1800044b5  movups  xmmword ptr [rcx], xmm0
0x1800044b8  mov     qword ptr [rcx+10h], 0
0x1800044c0  mov     qword ptr [rcx+18h], 0Fh
0x1800044c8  mov     byte ptr [rcx], 0
0x1800044cb  mov     dword ptr [rax-78h], 1
0x1800044d2  cmp     qword ptr [r8+8], 0
0x1800044d7  jz      loc_1800045E6
0x1800044dd  cmp     qword ptr [r8+8], 7FFFFFFFh
0x1800044e5  jbe     short loc_180004523
0x1800044e7  mov     dword ptr [rax-68h], 16h
0x1800044ee  mov     eax, [rsp+0A8h+var_64]
0x1800044f2  mov     [rsp+0A8h+var_64], eax
0x1800044f6  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_Generic_error_category@std@@@std@@YAAEBV_Generic_error_category@1@XZ@4V21@B; std::_Generic_error_category const `std::_Immortalize_memcpy_image<std::_Generic_error_category>(void)'::`2'::_Static
0x1800044fd  mov     [rsp+0A8h+var_60], rax
0x180004502  lea     rdx, [rsp+0A8h+var_68]
0x180004507  lea     rcx, [rsp+0A8h+pExceptionObject]
0x18000450c  call    ??0system_error@std@@QEAA@Verror_code@1@@Z; std::system_error::system_error(std::error_code)
0x180004511  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180004518  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18000451d  call    _CxxThrowException_0
0x180004523  mov     r14d, [r8+8]
0x180004527  mov     r15, [r8]
0x18000452a  mov     [rsp+0A8h+var_88], 0; int
0x180004532  xor     r9d, r9d; lpMultiByteStr
0x180004535  mov     r8d, r14d; cchWideChar
0x180004538  mov     rdx, r15; lpWideCharStr
0x18000453b  mov     ecx, ebp; CodePage
0x18000453d  call    __std_fs_convert_wide_to_narrow_replace_chars
0x180004542  mov     rcx, rax
0x180004545  call    ?_Check_convert_result@std@@YAHU__std_fs_convert_result@@@Z; std::_Check_convert_result(__std_fs_convert_result)
0x18000454a  movsxd  r12, eax
0x18000454d  mov     rdx, [rdi+10h]
0x180004551  mov     rcx, r12
0x180004554  cmp     r12, rdx
0x180004557  ja      short loc_180004573
0x180004559  mov     [rdi+10h], rcx
0x18000455d  cmp     qword ptr [rdi+18h], 0Fh
0x180004562  jbe     short loc_180004569
0x180004564  mov     rdx, [rdi]
0x180004567  jmp     short loc_18000456C
0x180004569  mov     rdx, rdi
0x18000456c  mov     byte ptr [r12+rdx], 0
0x180004571  jmp     short loc_1800045BD
0x180004573  mov     rsi, rcx
0x180004576  sub     rsi, rdx
0x180004579  mov     rax, [rdi+18h]
0x18000457d  sub     rax, rdx
0x180004580  cmp     rsi, rax
0x180004583  ja      short loc_1800045AF
0x180004585  mov     [rdi+10h], rcx
0x180004589  cmp     qword ptr [rdi+18h], 0Fh
0x18000458e  jbe     short loc_180004595
0x180004590  mov     rax, [rdi]
0x180004593  jmp     short loc_180004598
0x180004595  mov     rax, rdi
0x180004598  lea     rbx, [rdx+rax]
0x18000459c  mov     r8, rsi; Size
0x18000459f  xor     edx, edx; Val
0x1800045a1  mov     rcx, rbx; void *
0x1800045a4  call    memset_0
0x1800045a9  mov     byte ptr [rsi+rbx], 0
0x1800045ad  jmp     short loc_1800045BD
0x1800045af  mov     r9, rsi
0x1800045b2  mov     rdx, rsi
0x1800045b5  mov     rcx, rdi; Src
0x1800045b8  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@_KD@Z@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0D@Z@_KD@Z; std::string::_Reallocate_grow_by<`std::string::append(unsigned __int64,char)'::`2'::_lambda_1_,unsigned __int64,char>(unsigned __int64,`std::string::append(unsigned __int64,char)'::`2'::_lambda_1_,unsigned __int64,char)
0x1800045bd  cmp     qword ptr [rdi+18h], 0Fh
0x1800045c2  jbe     short loc_1800045C9
0x1800045c4  mov     r9, [rdi]
0x1800045c7  jmp     short loc_1800045CC
0x1800045c9  mov     r9, rdi; lpMultiByteStr
0x1800045cc  mov     [rsp+0A8h+var_88], r12d; int
0x1800045d1  mov     r8d, r14d; cchWideChar
0x1800045d4  mov     rdx, r15; lpWideCharStr
0x1800045d7  mov     ecx, ebp; CodePage
0x1800045d9  call    __std_fs_convert_wide_to_narrow_replace_chars
0x1800045de  mov     rcx, rax
0x1800045e1  call    ?_Check_convert_result@std@@YAHU__std_fs_convert_result@@@Z; std::_Check_convert_result(__std_fs_convert_result)
0x1800045e6  mov     rax, rdi
0x1800045e9  lea     r11, [rsp+0A8h+var_28]
0x1800045f1  mov     rbx, [r11+38h]
0x1800045f5  mov     rbp, [r11+40h]
0x1800045f9  mov     rsp, r11
0x1800045fc  pop     r15
0x1800045fe  pop     r14
0x180004600  pop     r12
0x180004602  pop     rdi
0x180004603  pop     rsi
0x180004604  retn
```
