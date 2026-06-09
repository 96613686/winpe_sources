# CMockEngine::GetContext(ushort const *,tagVARIANT *)

- ea: `0x1801137a0`
- end: `0x18011384f`
- name: `?GetContext@CMockEngine@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `175`
- prototype: `int(CMockEngine *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180019080`
- `0x1800e68b0`
- `0x1800ed46c`
- `0x1800efd9c`
- `0x1801137a0`
- `0x180115b48`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180113814`
- `OLEAUT32!__imp_VariantInit` at `0x180113814`
- `OLEAUT32!__imp_VariantCopy` at `0x180113827`
- `OLEAUT32!__imp_VariantCopy` at `0x180113827`

## string_xrefs

- `0x1801137fc`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\multivariantdiagdata.cpp`

## pseudocode

```c
HRESULT __fastcall CMockEngine::GetContext(CMockEngine *this, const unsigned __int16 *a2, struct tagVARIANT *a3)
{
  __int64 v5; // rbx
  const char *v6; // r9
  HRESULT result; // eax
  __int64 v8; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v9[32]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    std::wstring::wstring(v9, a2);
    std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>,0>>::find(
      (char *)this + 16,
      &v8,
      v9);
    std::wstring::_Tidy_deallocate(v9);
    v5 = v8;
    if ( v8 == *((_QWORD *)this + 2) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\multivariantdiagdata.cpp",
        (const char *)0x80070002LL,
        v8);
      result = -2147024894;
    }
    else
    {
      VariantInit(a3);
      result = VariantCopy(a3, (const VARIANTARG *)(v5 + 64));
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x3C,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\multivariantdiagdata.cpp",
             v6);
  }
  return result;
}

```

## disassembly

```asm
0x1801137a0  push    rbx
0x1801137a2  push    rsi
0x1801137a3  push    rdi
0x1801137a4  sub     rsp, 50h
0x1801137a8  mov     rax, cs:__security_cookie
0x1801137af  xor     rax, rsp
0x1801137b2  mov     [rsp+68h+var_20], rax
0x1801137b7  mov     rsi, r8
0x1801137ba  mov     rdi, rcx
0x1801137bd  lea     rcx, [rsp+68h+var_40]
0x1801137c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801137c7  lea     r8, [rsp+68h+var_40]
0x1801137cc  lea     rdx, [rsp+68h+var_48]
0x1801137d1  lea     rcx, [rdi+10h]
0x1801137d5  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>::find(std::wstring const &)
0x1801137da  lea     rcx, [rsp+68h+var_40]
0x1801137df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801137e4  mov     rbx, [rsp+68h+var_48]
0x1801137e9  cmp     rbx, [rdi+10h]
0x1801137ed  jnz     short loc_180113811
0x1801137ef  mov     rcx, [rsp+68h]; this
0x1801137f4  mov     ebx, 80070002h
0x1801137f9  mov     r9d, ebx; char *
0x1801137fc  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180113803  mov     edx, 38h ; '8'; void *
0x180113808  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011380d  mov     eax, ebx
0x18011380f  jmp     short loc_180113839
0x180113811  mov     rcx, rsi; pvarg
0x180113814  call    cs:__imp_VariantInit
0x18011381b  nop     dword ptr [rax+rax+00h]
0x180113820  lea     rdx, [rbx+40h]; pvargSrc
0x180113824  mov     rcx, rsi; pvargDest
0x180113827  call    cs:__imp_VariantCopy
0x18011382e  nop     dword ptr [rax+rax+00h]
0x180113833  jmp     short loc_180113839
0x180113835  mov     eax, dword ptr [rsp+68h+var_48]
0x180113839  mov     rcx, [rsp+68h+var_20]
0x18011383e  xor     rcx, rsp; StackCookie
0x180113841  call    __security_check_cookie
0x180113846  add     rsp, 50h
0x18011384a  pop     rdi
0x18011384b  pop     rsi
0x18011384c  pop     rbx
0x18011384d  retn
```
