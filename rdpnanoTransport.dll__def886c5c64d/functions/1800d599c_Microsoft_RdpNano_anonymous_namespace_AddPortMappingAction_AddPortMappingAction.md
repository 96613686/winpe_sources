# Microsoft::RdpNano::_anonymous_namespace_::AddPortMappingAction::AddPortMappingAction

- ea: `0x1800d599c`
- end: `0x1800d5aee`
- name: `Microsoft::RdpNano::_anonymous_namespace_::AddPortMappingAction::AddPortMappingAction`
- size: `338`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800d7328`
- `0x1800dbb10`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180045eb4`
- `0x1800d3188`
- `0x1800d599c`
- `0x1800d6154`
- `0x18032f050`
- `0x180330b40`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800d5a28`
- `OLEAUT32!__imp_VariantInit` at `0x1800d5a33`
- `OLEAUT32!__imp_VariantInit` at `0x1800d5a3e`
- `OLEAUT32!__imp_VariantInit` at `0x1800d5a28`
- `OLEAUT32!__imp_VariantInit` at `0x1800d5a33`
- `OLEAUT32!__imp_VariantInit` at `0x1800d5a3e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d5a50`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d5a50`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::RdpNano::_anonymous_namespace_::AddPortMappingAction::AddPortMappingAction(
        __int64 a1,
        __int64 a2,
        __int16 a3,
        char a4,
        __int64 a5,
        char a6,
        __int64 a7,
        char a8)
{
  __int64 *v10; // rsi
  const char *v11; // rdx
  SAFEARRAY *Vector; // rax
  __int64 v13; // r9
  char v15; // [rsp+20h] [rbp-69h] BYREF
  char *v16[2]; // [rsp+28h] [rbp-61h] BYREF
  __int128 v17; // [rsp+38h] [rbp-51h]
  _QWORD v18[9]; // [rsp+48h] [rbp-41h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+90h] [rbp+7h] BYREF
  __int16 v20; // [rsp+E0h] [rbp+57h] BYREF

  v20 = a3;
  v18[8] = a1;
  v15 = 1;
  v10 = qword_18053D360;
  if ( a4 )
    v10 = qword_18053D2E0;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  std::string::_Construct<1,char const *>(v16, "AddPortMapping", 14);
  v11 = (const char *)v16;
  if ( *((_QWORD *)&v17 + 1) > 0xFu )
    v11 = v16[0];
  _bstr_t::_bstr_t((_bstr_t *)a1, v11);
  VariantInit((VARIANTARG *)(a1 + 8));
  VariantInit((VARIANTARG *)(a1 + 32));
  VariantInit((VARIANTARG *)(a1 + 56));
  Vector = SafeArrayCreateVector(0xCu, 0, 8u);
  *(_QWORD *)(a1 + 16) = Vector;
  if ( !Vector )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  *(_WORD *)(a1 + 8) = 8204;
  v18[0] = &a8;
  v18[1] = a7;
  v18[2] = &v15;
  v18[3] = a5;
  v18[4] = &a6;
  v18[5] = v10;
  v18[6] = &v20;
  v18[7] = a2;
  LOBYTE(v13) = v15;
  Microsoft::RdpNano::_anonymous_namespace_::UPnPAction_void_::FillVariantArrayFromTuple_std::tuple_std::basic_string_char_std::char_traits_char__std::allocator_char____const___unsigned_short___std::basic_string_char_std::char_traits_char__std::allocator_char____const___unsigned_short___std::basic_string_char_std::char_traits_char__std::allocator_char____const___bool___std::basic_string_char_std::char_traits_char__std::allocator_char____const___unsigned_int____0_1_2_3_4_5_6_7_(
    a1,
    a1 + 8,
    v18,
    v13);
  std::string::_Tidy_deallocate(v16);
  return a1;
}

```

## disassembly

```asm
0x1800d599c  mov     rax, rsp
0x1800d599f  mov     [rax+10h], rbx
0x1800d59a3  mov     [rax+20h], rsi
0x1800d59a7  mov     [rax+18h], r8w
0x1800d59ac  push    rbp
0x1800d59ad  push    rdi
0x1800d59ae  push    r14
0x1800d59b0  lea     rbp, [rax-3Fh]
0x1800d59b4  mov     eax, 0B0h
0x1800d59b9  call    _alloca_probe
0x1800d59be  sub     rsp, rax
0x1800d59c1  mov     r14, rdx
0x1800d59c4  mov     rbx, rcx
0x1800d59c7  mov     [rbp+37h+var_38], rcx
0x1800d59cb  mov     [rbp+37h+var_A0], 1
0x1800d59cf  lea     rax, qword_18053D2E0
0x1800d59d6  lea     rsi, qword_18053D360
0x1800d59dd  test    r9b, r9b
0x1800d59e0  cmovnz  rsi, rax
0x1800d59e4  xorps   xmm0, xmm0
0x1800d59e7  movups  xmmword ptr [rbp+37h+var_98], xmm0
0x1800d59eb  xorps   xmm1, xmm1
0x1800d59ee  movdqu  [rbp+37h+var_88], xmm1
0x1800d59f3  mov     r8d, 0Eh
0x1800d59f9  lea     rdx, aAddportmapping; "AddPortMapping"
0x1800d5a00  lea     rcx, [rbp+37h+var_98]
0x1800d5a04  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d5a09  nop
0x1800d5a0a  lea     rdx, [rbp+37h+var_98]
0x1800d5a0e  cmp     qword ptr [rbp+37h+var_88+8], 0Fh
0x1800d5a13  cmova   rdx, [rbp+37h+var_98]; char *
0x1800d5a18  mov     rcx, rbx; this
0x1800d5a1b  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x1800d5a20  nop
0x1800d5a21  lea     rdi, [rbx+8]
0x1800d5a25  mov     rcx, rdi; pvarg
0x1800d5a28  call    cs:__imp_VariantInit
0x1800d5a2e  nop
0x1800d5a2f  lea     rcx, [rbx+20h]; pvarg
0x1800d5a33  call    cs:__imp_VariantInit
0x1800d5a39  nop
0x1800d5a3a  lea     rcx, [rbx+38h]; pvarg
0x1800d5a3e  call    cs:__imp_VariantInit
0x1800d5a44  nop
0x1800d5a45  mov     ecx, 0Ch; vt
0x1800d5a4a  xor     edx, edx; lLbound
0x1800d5a4c  lea     r8d, [rcx-4]; cElements
0x1800d5a50  call    cs:__imp_SafeArrayCreateVector
0x1800d5a56  mov     [rbx+10h], rax
0x1800d5a5a  test    rax, rax
0x1800d5a5d  jz      short loc_1800D5AD4
0x1800d5a5f  mov     word ptr [rdi], 200Ch
0x1800d5a64  lea     rax, [rbp+37h+arg_38]
0x1800d5a68  mov     [rbp+37h+var_78], rax
0x1800d5a6c  mov     rax, [rbp+37h+arg_30]
0x1800d5a70  mov     [rbp+37h+var_70], rax
0x1800d5a74  lea     rax, [rbp+37h+var_A0]
0x1800d5a78  mov     [rbp+37h+var_68], rax
0x1800d5a7c  mov     rax, [rbp+37h+arg_20]
0x1800d5a80  mov     [rbp+37h+var_60], rax
0x1800d5a84  lea     rax, [rbp+37h+arg_28]
0x1800d5a88  mov     [rbp+37h+var_58], rax
0x1800d5a8c  mov     [rbp+37h+var_50], rsi
0x1800d5a90  lea     rax, [rbp+37h+arg_10]
0x1800d5a94  mov     [rbp+37h+var_48], rax
0x1800d5a98  mov     [rbp+37h+var_40], r14
0x1800d5a9c  mov     r9b, [rbp+37h+var_A0]
0x1800d5aa0  lea     r8, [rbp+37h+var_78]
0x1800d5aa4  mov     rdx, rdi
0x1800d5aa7  mov     rcx, rbx
0x1800d5aaa  call    Microsoft__RdpNano___anonymous_namespace___UPnPAction_void___FillVariantArrayFromTuple_std__tuple_std__basic_string_char_std__char_traits_char__std__allocator_char____const___unsigned_short___std__basic_string_char_std__char_traits_char__std__allocator_char____const___unsigned_short___std__basic_string_char_std__char_traits_char__std__allocator_char____const___bool___std__basic_string_char_std__char_traits_char__std__allocator_char____const___unsigned_int____0_1_2_3_4_5_6_7_
0x1800d5aaf  nop
0x1800d5ab0  lea     rcx, [rbp+37h+var_98]
0x1800d5ab4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d5ab9  mov     rax, rbx
0x1800d5abc  lea     r11, [rsp+0C0h+var_10]
0x1800d5ac4  mov     rbx, [r11+28h]
0x1800d5ac8  mov     rsi, [r11+38h]
0x1800d5acc  mov     rsp, r11
0x1800d5acf  pop     r14
0x1800d5ad1  pop     rdi
0x1800d5ad2  pop     rbp
0x1800d5ad3  retn
0x1800d5ad4  lea     rcx, [rbp+37h+pExceptionObject]; this
0x1800d5ad8  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800d5add  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800d5ae4  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1800d5ae8  call    _CxxThrowException
```
