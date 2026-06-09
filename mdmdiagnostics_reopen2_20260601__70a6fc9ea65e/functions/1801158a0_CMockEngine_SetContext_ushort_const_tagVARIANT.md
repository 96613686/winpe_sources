# CMockEngine::SetContext(ushort const *,tagVARIANT *)

- ea: `0x1801158a0`
- end: `0x1801159dd`
- name: `?SetContext@CMockEngine@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `317`
- prototype: `int(CMockEngine *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180019080`
- `0x1800e68b0`
- `0x1800ed46c`
- `0x1800efd9c`
- `0x180112d68`
- `0x1801158a0`
- `0x180115b48`
- `0x180115ba0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1801158cd`
- `OLEAUT32!__imp_VariantInit` at `0x1801158cd`
- `OLEAUT32!__imp_VariantClear` at `0x180115920`
- `OLEAUT32!__imp_VariantClear` at `0x1801159b0`
- `OLEAUT32!__imp_VariantClear` at `0x180115920`
- `OLEAUT32!__imp_VariantClear` at `0x1801159b0`
- `OLEAUT32!__imp_VariantCopy` at `0x1801158ec`
- `OLEAUT32!__imp_VariantCopy` at `0x1801158ec`

## string_xrefs

- `0x180115909`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\multivariantdiagdata.cpp`

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
0x1801158a0  push    rbx
0x1801158a2  push    rsi
0x1801158a3  push    rdi
0x1801158a4  sub     rsp, 80h
0x1801158ab  mov     rax, cs:__security_cookie
0x1801158b2  xor     rax, rsp
0x1801158b5  mov     [rsp+98h+var_28], rax
0x1801158ba  mov     rbx, r8
0x1801158bd  mov     rdi, rdx
0x1801158c0  mov     rsi, rcx
0x1801158c3  mov     [rsp+98h+var_50], rdx
0x1801158c8  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1801158cd  call    cs:__imp_VariantInit
0x1801158d4  nop     dword ptr [rax+rax+00h]
0x1801158d9  nop
0x1801158da  lea     rcx, [rsp+98h+pvarg]
0x1801158df  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x1801158e4  mov     rdx, rbx; pvargSrc
0x1801158e7  lea     rcx, [rsp+98h+pvarg]; pvargDest
0x1801158ec  call    cs:__imp_VariantCopy
0x1801158f3  nop     dword ptr [rax+rax+00h]
0x1801158f8  mov     ebx, eax
0x1801158fa  test    eax, eax
0x1801158fc  jns     short loc_180115933
0x1801158fe  mov     rcx, [rsp+98h]; this
0x180115906  mov     r9d, eax; char *
0x180115909  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180115910  mov     edx, 27h ; '''; void *
0x180115915  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011591a  nop
0x18011591b  lea     rcx, [rsp+98h+pvarg]; pvarg
0x180115920  call    cs:__imp_VariantClear
0x180115927  nop     dword ptr [rax+rax+00h]
0x18011592c  mov     eax, ebx
0x18011592e  jmp     loc_1801159C4
0x180115933  lea     rbx, [rsi+10h]
0x180115937  mov     rdx, rdi
0x18011593a  lea     rcx, [rsp+98h+var_48]
0x18011593f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180115944  lea     r8, [rsp+98h+var_48]
0x180115949  lea     rdx, [rsp+98h+var_60]
0x18011594e  mov     rcx, rbx
0x180115951  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>::find(std::wstring const &)
0x180115956  lea     rcx, [rsp+98h+var_48]
0x18011595b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180115960  mov     rax, [rsp+98h+var_60]
0x180115965  cmp     rax, [rbx]
0x180115968  jnz     short loc_180115983
0x18011596a  lea     r9, [rsp+98h+pvarg]
0x18011596f  lea     r8, [rsp+98h+var_50]
0x180115974  lea     rdx, [rsp+98h+var_60]
0x180115979  mov     rcx, rbx
0x18011597c  call    ??$_Emplace@AEAPEBGV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@PEAX@std@@_N@1@AEAPEBG$$QEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>>,0>>::_Emplace<ushort const * &,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>(ushort const * &,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &&)
0x180115981  jmp     short loc_1801159AB
0x180115983  movups  xmm2, xmmword ptr [rax+40h]
0x180115987  movsd   xmm3, qword ptr [rax+50h]
0x18011598c  movups  xmm0, xmmword ptr [rsp+98h+pvarg]
0x180115991  movups  xmmword ptr [rax+40h], xmm0
0x180115995  movsd   xmm1, qword ptr [rsp+98h+pvarg+10h]
0x18011599b  movsd   qword ptr [rax+50h], xmm1
0x1801159a0  movups  xmmword ptr [rsp+98h+pvarg], xmm2
0x1801159a5  movsd   qword ptr [rsp+98h+pvarg+10h], xmm3
0x1801159ab  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1801159b0  call    cs:__imp_VariantClear
0x1801159b7  nop     dword ptr [rax+rax+00h]
0x1801159bc  xor     eax, eax
0x1801159be  jmp     short loc_1801159C4
0x1801159c0  mov     eax, dword ptr [rsp+98h+var_60]
0x1801159c4  mov     rcx, [rsp+98h+var_28]
0x1801159c9  xor     rcx, rsp; StackCookie
0x1801159cc  call    __security_check_cookie
0x1801159d1  add     rsp, 80h
0x1801159d8  pop     rdi
0x1801159d9  pop     rsi
0x1801159da  pop     rbx
0x1801159db  retn
```
