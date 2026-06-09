# AssetElementNode::_GetWpxInfoForPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,IWpxConfig * *)

- ea: `0x180027d6c`
- end: `0x180028047`
- name: `?_GetWpxInfoForPath@AssetElementNode@@AEAA?AV?$unique_ptr@UIWpxSetting@@U?$ProvReleaser@UIWpxSetting@@@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@PEAPEAUIWpxConfig@@@Z`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180026dbc`

## callees

- `0x180001a30`
- `0x180001a40`
- `0x180001b14`
- `0x1800046ac`
- `0x1800090e0`
- `0x18000918c`
- `0x18000929c`
- `0x1800125f4`
- `0x180026be4`
- `0x180027d6c`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180027f0a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027f4f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027f0a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027f4f`
- `wpx!WpxCreateConfig` at `0x180027dbd`
- `wpx!WpxCreateConfig` at `0x180027dbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct IWpxConfig **__fastcall AssetElementNode::_GetWpxInfoForPath(
        __int64 a1,
        struct IWpxConfig **a2,
        __int64 a3,
        struct IWpxConfig **a4)
{
  struct IWpxConfig *v7; // rbx
  int v8; // eax
  struct IWpxConfig *v9; // r14
  int v10; // r12d
  int v11; // eax
  struct IWpxConfig *v12; // r14
  struct IWpxConfig *v13; // rcx
  unsigned __int64 v14; // r15
  void **v15; // rdx
  int v16; // eax
  struct IWpxConfig *v17; // r14
  struct IWpxConfig *v18; // rcx
  unsigned __int64 v19; // r14
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // eax
  int v27; // [rsp+20h] [rbp-49h]
  struct IWpxConfig *v28; // [rsp+30h] [rbp-39h] BYREF
  int v29; // [rsp+38h] [rbp-31h]
  struct IWpxConfig *v30; // [rsp+40h] [rbp-29h]
  struct IWpxConfig **v31; // [rsp+48h] [rbp-21h]
  char v32[8]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v33; // [rsp+58h] [rbp-11h]
  void *v34[3]; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int64 v35; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v31 = a2;
  v33 = a3;
  v29 = 0;
  v7 = 0;
  v30 = 0;
  v28 = 0;
  v8 = WpxCreateConfig(&v28);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v8,
      v27);
  v9 = 0;
  if ( v28 )
  {
    v7 = v28;
    v30 = v28;
    v9 = v28;
  }
  AssetElementNode::LoadKnobsStores(retaddr, v7);
  *a2 = 0;
  v10 = 1;
  v29 = 1;
  v28 = 0;
  v11 = (*(__int64 (__fastcall **)(struct IWpxConfig *, struct IWpxConfig **))(*(_QWORD *)v9 + 176LL))(v9, &v28);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v11,
      v27);
  v12 = v28;
  v13 = *a2;
  if ( v28 != *a2 )
  {
    if ( v13 )
      (*(void (__fastcall **)(struct IWpxConfig *))(*(_QWORD *)v13 + 736LL))(v13);
    *a2 = v12;
  }
  v14 = std::wstring::find(a3, 47, 1);
  if ( *(_QWORD *)(a3 + 16) )
  {
    do
    {
      v28 = 0;
      v35 = 7;
      v34[2] = 0;
      LOWORD(v34[0]) = 0;
      std::wstring::assign(v34);
      v10 |= 2u;
      v29 = v10;
      v15 = v34;
      if ( v35 >= 8 )
        v15 = (void **)v34[0];
      v16 = (*(__int64 (__fastcall **)(struct IWpxConfig *, void **, struct IWpxConfig **))(*(_QWORD *)*a2 + 72LL))(
              *a2,
              v15,
              &v28);
      if ( v16 == -2147023728 )
      {
        if ( (unsigned int)dword_1800495B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800495B0, 0x400000000000LL) )
        {
          v21 = std::wstring::c_str(a3);
          v22 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v32, v21);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v23,
            (unsigned int)byte_1800416E1,
            v24,
            v25,
            v22);
        }
        v26 = wil::verify_hresult<long>(2248146946LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
          (const char *)v26,
          v27);
      }
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
          (const char *)(unsigned int)v16,
          v27);
      v17 = v28;
      v18 = *a2;
      if ( v28 != *a2 )
      {
        if ( v18 )
          (*(void (__fastcall **)(struct IWpxConfig *))(*(_QWORD *)v18 + 736LL))(v18);
        *a2 = v17;
      }
      if ( v35 >= 8 )
        operator delete(v34[0]);
      v19 = v14;
      if ( v14 < v14 + 1 )
        v19 = v14 + 1;
      v14 = std::wstring::find(a3, 47, v19);
    }
    while ( v19 < *(_QWORD *)(a3 + 16) );
  }
  *a4 = v7;
  if ( *(_QWORD *)(a3 + 24) >= 8u )
    operator delete(*(void **)a3);
  *(_QWORD *)(a3 + 24) = 7;
  *(_QWORD *)(a3 + 16) = 0;
  *(_WORD *)a3 = 0;
  return a2;
}

```

## disassembly

```asm
0x180027d6c  mov     [rsp-8+arg_0], rbx
0x180027d71  push    rbp
0x180027d72  push    rsi
0x180027d73  push    rdi
0x180027d74  push    r12
0x180027d76  push    r13
0x180027d78  push    r14
0x180027d7a  push    r15
0x180027d7c  lea     rbp, [rsp-27h]
0x180027d81  sub     rsp, 90h
0x180027d88  mov     rax, cs:__security_cookie
0x180027d8f  xor     rax, rsp
0x180027d92  mov     [rbp+57h+var_40], rax
0x180027d96  mov     r13, r9
0x180027d99  mov     rdi, r8
0x180027d9c  mov     rsi, rdx
0x180027d9f  mov     [rbp+57h+var_78], rdx
0x180027da3  mov     [rbp+57h+var_68], r8
0x180027da7  xor     r15d, r15d
0x180027daa  mov     [rbp+57h+var_88], r15d
0x180027dae  mov     ebx, r15d
0x180027db1  mov     [rbp+57h+var_80], rbx
0x180027db5  mov     [rbp+57h+var_90], r15
0x180027db9  lea     rcx, [rbp+57h+var_90]
0x180027dbd  call    cs:__imp_?WpxCreateConfig@@YAJPEAPEAUIWpxConfig@@@Z; WpxCreateConfig(IWpxConfig * *)
0x180027dc4  nop     dword ptr [rax+rax+00h]
0x180027dc9  mov     rcx, [rbp+5Fh]; this
0x180027dcd  test    eax, eax
0x180027dcf  js      loc_18002801D
0x180027dd5  mov     rax, [rbp+57h+var_90]
0x180027dd9  mov     r14d, r15d
0x180027ddc  test    rax, rax
0x180027ddf  jz      short loc_180027DEB
0x180027de1  mov     rbx, rax
0x180027de4  mov     [rbp+57h+var_80], rax
0x180027de8  mov     r14, rax
0x180027deb  mov     rdx, rbx; struct IWpxConfig *
0x180027dee  call    ?LoadKnobsStores@AssetElementNode@@AEAAXPEAUIWpxConfig@@@Z; AssetElementNode::LoadKnobsStores(IWpxConfig *)
0x180027df3  mov     [rsi], r15
0x180027df6  mov     r12d, 1
0x180027dfc  mov     [rbp+57h+var_88], r12d
0x180027e00  mov     [rbp+57h+var_90], r15
0x180027e04  mov     rax, [r14]
0x180027e07  lea     rdx, [rbp+57h+var_90]
0x180027e0b  mov     rcx, r14
0x180027e0e  mov     rax, [rax+0B0h]
0x180027e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e1a  mov     rcx, [rbp+5Fh]; this
0x180027e1e  test    eax, eax
0x180027e20  js      loc_180028032
0x180027e26  mov     r14, [rbp+57h+var_90]
0x180027e2a  mov     rcx, [rsi]
0x180027e2d  cmp     r14, rcx
0x180027e30  jz      short loc_180027E49
0x180027e32  test    rcx, rcx
0x180027e35  jz      short loc_180027E46
0x180027e37  mov     rax, [rcx]
0x180027e3a  mov     rax, [rax+2E0h]
0x180027e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e46  mov     [rsi], r14
0x180027e49  mov     r14, r15
0x180027e4c  mov     edx, 2Fh ; '/'
0x180027e51  mov     r8, r12
0x180027e54  mov     rcx, rdi
0x180027e57  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x180027e5c  mov     r15, rax
0x180027e5f  cmp     [rdi+10h], r14
0x180027e63  jbe     loc_180027F41
0x180027e69  mov     [rbp+57h+var_90], 0
0x180027e71  mov     [rbp+57h+var_48], 7
0x180027e79  mov     [rbp+57h+var_50], 0
0x180027e81  xor     eax, eax
0x180027e83  mov     word ptr [rbp+57h+var_60], ax
0x180027e87  mov     r9, r15
0x180027e8a  sub     r9, r14
0x180027e8d  mov     r8, r14
0x180027e90  mov     rdx, rdi
0x180027e93  lea     rcx, [rbp+57h+var_60]; void *
0x180027e97  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180027e9c  or      r12d, 2
0x180027ea0  mov     [rbp+57h+var_88], r12d
0x180027ea4  mov     rcx, [rsi]
0x180027ea7  mov     rax, [rcx]
0x180027eaa  lea     rdx, [rbp+57h+var_60]
0x180027eae  cmp     [rbp+57h+var_48], 8
0x180027eb3  cmovnb  rdx, [rbp+57h+var_60]
0x180027eb8  lea     r8, [rbp+57h+var_90]
0x180027ebc  mov     rax, [rax+48h]
0x180027ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ec5  cmp     eax, 80070490h
0x180027eca  jz      loc_180027FB0
0x180027ed0  mov     rcx, [rbp+5Fh]; this
0x180027ed4  test    eax, eax
0x180027ed6  js      loc_180027F9B
0x180027edc  mov     r14, [rbp+57h+var_90]
0x180027ee0  mov     rcx, [rsi]
0x180027ee3  cmp     r14, rcx
0x180027ee6  jz      short loc_180027EFF
0x180027ee8  test    rcx, rcx
0x180027eeb  jz      short loc_180027EFC
0x180027eed  mov     rax, [rcx]
0x180027ef0  mov     rax, [rax+2E0h]
0x180027ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027efc  mov     [rsi], r14
0x180027eff  cmp     [rbp+57h+var_48], 8
0x180027f04  jb      short loc_180027F16
0x180027f06  mov     rcx, [rbp+57h+var_60]
0x180027f0a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027f11  nop     dword ptr [rax+rax+00h]
0x180027f16  lea     rax, [r15+1]
0x180027f1a  mov     r14, r15
0x180027f1d  cmp     r15, rax
0x180027f20  cmovbe  r14, rax
0x180027f24  mov     edx, 2Fh ; '/'
0x180027f29  mov     r8, r14
0x180027f2c  mov     rcx, rdi
0x180027f2f  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x180027f34  mov     r15, rax
0x180027f37  cmp     r14, [rdi+10h]
0x180027f3b  jb      loc_180027E69
0x180027f41  mov     [r13+0], rbx
0x180027f45  cmp     qword ptr [rdi+18h], 8
0x180027f4a  jb      short loc_180027F5B
0x180027f4c  mov     rcx, [rdi]
0x180027f4f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027f56  nop     dword ptr [rax+rax+00h]
0x180027f5b  mov     qword ptr [rdi+18h], 7
0x180027f63  mov     qword ptr [rdi+10h], 0
0x180027f6b  xor     ecx, ecx
0x180027f6d  mov     [rdi], cx
0x180027f70  mov     rax, rsi
0x180027f73  mov     rcx, [rbp+57h+var_40]
0x180027f77  xor     rcx, rsp; StackCookie
0x180027f7a  call    __security_check_cookie
0x180027f7f  mov     rbx, [rsp+0C0h+arg_0]
0x180027f87  add     rsp, 90h
0x180027f8e  pop     r15
0x180027f90  pop     r14
0x180027f92  pop     r13
0x180027f94  pop     r12
0x180027f96  pop     rdi
0x180027f97  pop     rsi
0x180027f98  pop     rbp
0x180027f99  retn
0x180027f9b  mov     r9d, eax; char *
0x180027f9e  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180027fa5  mov     edx, 0BAh; void *
0x180027faa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027fb0  mov     eax, cs:dword_1800495B0
0x180027fb6  cmp     eax, 2
0x180027fb9  jbe     short loc_180027FFA
0x180027fbb  mov     rdx, 400000000000h
0x180027fc5  lea     rcx, dword_1800495B0
0x180027fcc  call    _tlgKeywordOn
0x180027fd1  test    al, al
0x180027fd3  jz      short loc_180027FFA
0x180027fd5  mov     rcx, rdi
0x180027fd8  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180027fdd  mov     rdx, rax
0x180027fe0  lea     rcx, [rbp+57h+var_70]
0x180027fe4  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180027fe9  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180027fee  lea     rdx, byte_1800416E1
0x180027ff5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180027ffa  mov     ecx, 86000002h
0x180027fff  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180028004  mov     r9d, eax; char *
0x180028007  mov     rcx, [rbp+5Fh]; this
0x18002800b  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028012  mov     edx, 0B8h; void *
0x180028017  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002801d  mov     r9d, eax; char *
0x180028020  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028027  mov     edx, 9Bh; void *
0x18002802c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028032  mov     r9d, eax; char *
0x180028035  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x18002803c  mov     edx, 0A5h; void *
0x180028041  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
