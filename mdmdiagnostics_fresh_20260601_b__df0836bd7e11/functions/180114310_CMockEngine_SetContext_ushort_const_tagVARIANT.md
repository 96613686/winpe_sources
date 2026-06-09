# CMockEngine::SetContext(ushort const *,tagVARIANT *)

- ea: `0x180114310`
- end: `0x180114435`
- name: `?SetContext@CMockEngine@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `293`
- prototype: `int(CMockEngine *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180019000`
- `0x1800e66dc`
- `0x1800ece5c`
- `0x1800ef5d8`
- `0x18011186c`
- `0x180114310`
- `0x1801145a0`
- `0x1801145f8`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18011433d`
- `OLEAUT32!__imp_VariantInit` at `0x18011433d`
- `OLEAUT32!__imp_VariantClear` at `0x180114384`
- `OLEAUT32!__imp_VariantClear` at `0x18011440e`
- `OLEAUT32!__imp_VariantClear` at `0x180114384`
- `OLEAUT32!__imp_VariantClear` at `0x18011440e`
- `OLEAUT32!__imp_VariantCopy` at `0x180114356`
- `OLEAUT32!__imp_VariantCopy` at `0x180114356`

## string_xrefs

- `0x18011436d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\multivariantdiagdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMockEngine::SetContext(CMockEngine *this, const unsigned __int16 *a2, struct tagVARIANT *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 result; // rax
  __int64 v9; // rax
  __int128 v10; // xmm2
  IRecordInfo *v11; // xmm3_8
  const char *v12; // r9
  VARIANTARG pvarg; // [rsp+20h] [rbp-78h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-60h] BYREF
  const unsigned __int16 *v15; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v16[32]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v15 = a2;
  VariantInit(&pvarg);
  wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::reset(&pvarg);
  v6 = VariantCopy(&pvarg, a3);
  v7 = v6;
  if ( v6 >= 0 )
  {
    try
    {
      std::wstring::wstring(v16, a2);
      std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>,0>>::find(
        (char *)this + 16,
        v14,
        v16);
      std::wstring::_Tidy_deallocate(v16);
      v9 = v14[0];
      if ( v14[0] == *((_QWORD *)this + 2) )
      {
        std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>>,0>>::_Emplace<unsigned short const * &,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>(
          (char *)this + 16,
          v14,
          &v15,
          &pvarg);
      }
      else
      {
        v10 = *(_OWORD *)(v14[0] + 64LL);
        v11 = *(IRecordInfo **)(v14[0] + 80LL);
        *(_OWORD *)(v14[0] + 64LL) = *(_OWORD *)&pvarg.vt;
        *(_QWORD *)(v9 + 80) = pvarg.pRecInfo;
        *(_OWORD *)&pvarg.vt = v10;
        pvarg.pRecInfo = v11;
      }
      VariantClear(&pvarg);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x33,
                             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\multivariantdiagdata.cpp",
                             v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\multivariantdiagdata.cpp",
      (const char *)(unsigned int)v6,
      *(int *)&pvarg.vt);
    VariantClear(&pvarg);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180114310  push    rbx
0x180114312  push    rsi
0x180114313  push    rdi
0x180114314  sub     rsp, 80h
0x18011431b  mov     rax, cs:__security_cookie
0x180114322  xor     rax, rsp
0x180114325  mov     [rsp+98h+var_28], rax
0x18011432a  mov     rbx, r8
0x18011432d  mov     rdi, rdx
0x180114330  mov     rsi, rcx
0x180114333  mov     [rsp+98h+var_50], rdx
0x180114338  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18011433d  call    cs:__imp_VariantInit
0x180114343  nop
0x180114344  lea     rcx, [rsp+98h+pvarg]
0x180114349  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x18011434e  mov     rdx, rbx; pvargSrc
0x180114351  lea     rcx, [rsp+98h+pvarg]; pvargDest
0x180114356  call    cs:__imp_VariantCopy
0x18011435c  mov     ebx, eax
0x18011435e  test    eax, eax
0x180114360  jns     short loc_180114391
0x180114362  mov     rcx, [rsp+98h]; this
0x18011436a  mov     r9d, eax; char *
0x18011436d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180114374  mov     edx, 27h ; '''; void *
0x180114379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011437e  nop
0x18011437f  lea     rcx, [rsp+98h+pvarg]; pvarg
0x180114384  call    cs:__imp_VariantClear
0x18011438a  mov     eax, ebx
0x18011438c  jmp     loc_18011441C
0x180114391  lea     rbx, [rsi+10h]
0x180114395  mov     rdx, rdi
0x180114398  lea     rcx, [rsp+98h+var_48]
0x18011439d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801143a2  lea     r8, [rsp+98h+var_48]
0x1801143a7  lea     rdx, [rsp+98h+var_60]
0x1801143ac  mov     rcx, rbx
0x1801143af  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>::find(std::wstring const &)
0x1801143b4  lea     rcx, [rsp+98h+var_48]
0x1801143b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801143be  mov     rax, [rsp+98h+var_60]
0x1801143c3  cmp     rax, [rbx]
0x1801143c6  jnz     short loc_1801143E1
0x1801143c8  lea     r9, [rsp+98h+pvarg]
0x1801143cd  lea     r8, [rsp+98h+var_50]
0x1801143d2  lea     rdx, [rsp+98h+var_60]
0x1801143d7  mov     rcx, rbx
0x1801143da  call    ??$_Emplace@AEAPEBGV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@PEAX@std@@_N@1@AEAPEBG$$QEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>::_Emplace<ushort const * &,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>(ushort const * &,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &&)
0x1801143df  jmp     short loc_180114409
0x1801143e1  movups  xmm2, xmmword ptr [rax+40h]
0x1801143e5  movsd   xmm3, qword ptr [rax+50h]
0x1801143ea  movups  xmm0, xmmword ptr [rsp+98h+pvarg]
0x1801143ef  movups  xmmword ptr [rax+40h], xmm0
0x1801143f3  movsd   xmm1, qword ptr [rsp+98h+pvarg+10h]
0x1801143f9  movsd   qword ptr [rax+50h], xmm1
0x1801143fe  movups  xmmword ptr [rsp+98h+pvarg], xmm2
0x180114403  movsd   qword ptr [rsp+98h+pvarg+10h], xmm3
0x180114409  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18011440e  call    cs:__imp_VariantClear
0x180114414  xor     eax, eax
0x180114416  jmp     short loc_18011441C
0x180114418  mov     eax, dword ptr [rsp+98h+var_60]
0x18011441c  mov     rcx, [rsp+98h+var_28]
0x180114421  xor     rcx, rsp; StackCookie
0x180114424  call    __security_check_cookie
0x180114429  add     rsp, 80h
0x180114430  pop     rdi
0x180114431  pop     rsi
0x180114432  pop     rbx
0x180114433  retn
```
