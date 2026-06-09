# CMockEngine::GetContext(ushort const *,tagVARIANT *)

- ea: `0x180112290`
- end: `0x180112333`
- name: `?GetContext@CMockEngine@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `163`
- prototype: `int(CMockEngine *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180019000`
- `0x1800e66dc`
- `0x1800ece5c`
- `0x1800ef5d8`
- `0x180112290`
- `0x1801145a0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180112304`
- `OLEAUT32!__imp_VariantInit` at `0x180112304`
- `OLEAUT32!__imp_VariantCopy` at `0x180112311`
- `OLEAUT32!__imp_VariantCopy` at `0x180112311`

## string_xrefs

- `0x1801122ec`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\multivariantdiagdata.cpp`

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
0x180112290  push    rbx
0x180112292  push    rsi
0x180112293  push    rdi
0x180112294  sub     rsp, 50h
0x180112298  mov     rax, cs:__security_cookie
0x18011229f  xor     rax, rsp
0x1801122a2  mov     [rsp+68h+var_20], rax
0x1801122a7  mov     rsi, r8
0x1801122aa  mov     rdi, rcx
0x1801122ad  lea     rcx, [rsp+68h+var_40]
0x1801122b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801122b7  lea     r8, [rsp+68h+var_40]
0x1801122bc  lea     rdx, [rsp+68h+var_48]
0x1801122c1  lea     rcx, [rdi+10h]
0x1801122c5  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>::find(std::wstring const &)
0x1801122ca  lea     rcx, [rsp+68h+var_40]
0x1801122cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801122d4  mov     rbx, [rsp+68h+var_48]
0x1801122d9  cmp     rbx, [rdi+10h]
0x1801122dd  jnz     short loc_180112301
0x1801122df  mov     rcx, [rsp+68h]; this
0x1801122e4  mov     ebx, 80070002h
0x1801122e9  mov     r9d, ebx; char *
0x1801122ec  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801122f3  mov     edx, 38h ; '8'; void *
0x1801122f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801122fd  mov     eax, ebx
0x1801122ff  jmp     short loc_18011231D
0x180112301  mov     rcx, rsi; pvarg
0x180112304  call    cs:__imp_VariantInit
0x18011230a  lea     rdx, [rbx+40h]; pvargSrc
0x18011230e  mov     rcx, rsi; pvargDest
0x180112311  call    cs:__imp_VariantCopy
0x180112317  jmp     short loc_18011231D
0x180112319  mov     eax, dword ptr [rsp+68h+var_48]
0x18011231d  mov     rcx, [rsp+68h+var_20]
0x180112322  xor     rcx, rsp; StackCookie
0x180112325  call    __security_check_cookie
0x18011232a  add     rsp, 50h
0x18011232e  pop     rdi
0x18011232f  pop     rsi
0x180112330  pop     rbx
0x180112331  retn
```
