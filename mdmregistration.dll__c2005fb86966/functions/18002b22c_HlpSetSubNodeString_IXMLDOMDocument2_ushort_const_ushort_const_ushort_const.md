# HlpSetSubNodeString(IXMLDOMDocument2 * *,ushort const *,ushort const *,ushort const *)

- ea: `0x18002b22c`
- end: `0x18002b697`
- name: `?HlpSetSubNodeString@@YAJPEAPEAUIXMLDOMDocument2@@PEBG11@Z`
- size: `1131`
- prototype: `int(struct IXMLDOMDocument2 **, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022948`

## callees

- `0x18002b22c`
- `0x18004e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b281`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b29b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b2b5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b2cb`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b281`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b29b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b2b5`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b2cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b380`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b390`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b3a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b3b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b42e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b43e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b44e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b45e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b51b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b52b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b53b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b54b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b380`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b390`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b3a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b3b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b42e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b43e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b44e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b45e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b51b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b52b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b53b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b54b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b5e9`
- `OLEAUT32!__imp_VariantClear` at `0x18002b370`
- `OLEAUT32!__imp_VariantClear` at `0x18002b41e`
- `OLEAUT32!__imp_VariantClear` at `0x18002b50b`
- `OLEAUT32!__imp_VariantClear` at `0x18002b595`
- `OLEAUT32!__imp_VariantClear` at `0x18002b635`
- `OLEAUT32!__imp_VariantClear` at `0x18002b370`
- `OLEAUT32!__imp_VariantClear` at `0x18002b41e`
- `OLEAUT32!__imp_VariantClear` at `0x18002b50b`
- `OLEAUT32!__imp_VariantClear` at `0x18002b595`
- `OLEAUT32!__imp_VariantClear` at `0x18002b635`

## string_xrefs

- `0x18002b27a`: `http://schemas.microsoft.com/windows/management/2012/01/enrollment`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall HlpSetSubNodeString(
        struct IXMLDOMDocument2 **a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  OLECHAR *v6; // r14
  OLECHAR *v7; // rdi
  OLECHAR *v8; // rsi
  BSTR v9; // rax
  OLECHAR *v10; // rbx
  __int64 v11; // r15
  HRESULT (__stdcall *createNode)(IXMLDOMDocument2 *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // r13
  __int64 v13; // rcx
  int v14; // r15d
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r15
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMDocument2 *, BSTR, IXMLDOMNode **); // r12
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  VARIANTARG pvarg; // [rsp+58h] [rbp-19h] BYREF
  VARIANTARG v30; // [rsp+78h] [rbp+7h] BYREF
  __int64 v31; // [rsp+E0h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+E8h] [rbp+77h] BYREF

  v31 = 0;
  v32 = 0;
  pvarg.vt = 3;
  pvarg.lVal = 1;
  if ( a4 )
  {
    v6 = SysAllocString(L"http://schemas.microsoft.com/windows/management/2012/01/enrollment");
    v7 = SysAllocString(L"//e:Discover//e:AuthPolicies");
    v8 = SysAllocString(L"AuthPolicy");
    v9 = SysAllocString(a4);
    v10 = v9;
    if ( v6 && v7 && v8 && v9 )
    {
      v11 = (__int64)*a1;
      createNode = (*a1)->lpVtbl->createNode;
      v13 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      v30 = pvarg;
      v14 = ((__int64 (__fastcall *)(__int64, VARIANTARG *, OLECHAR *, OLECHAR *, __int64 *))createNode)(
              v11,
              &v30,
              v8,
              v6,
              &v32);
      if ( v14 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v32 + 216LL))(v32, v10);
        if ( v14 >= 0 )
        {
          v20 = (__int64)*a1;
          selectSingleNode = (*a1)->lpVtbl->selectSingleNode;
          v22 = v31;
          if ( v31 )
          {
            v31 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          v14 = ((__int64 (__fastcall *)(__int64, OLECHAR *, __int64 *))selectSingleNode)(v20, v7, &v31);
          if ( v14 >= 0 && v31 )
            v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v31 + 168LL))(v31, v32, 0);
          VariantClear(&pvarg);
          SysFreeString(v6);
          SysFreeString(v7);
          SysFreeString(v8);
          SysFreeString(v10);
          v23 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
          v24 = v31;
          if ( v31 )
          {
            v31 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
        }
        else
        {
          VariantClear(&pvarg);
          SysFreeString(v6);
          SysFreeString(v7);
          SysFreeString(v8);
          SysFreeString(v10);
          v18 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          }
          v19 = v31;
          if ( v31 )
          {
            v31 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
        }
      }
      else
      {
        VariantClear(&pvarg);
        SysFreeString(v6);
        SysFreeString(v7);
        SysFreeString(v8);
        SysFreeString(v10);
        v15 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        v16 = v31;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
      return (unsigned int)v14;
    }
    else
    {
      VariantClear(&pvarg);
      if ( v6 )
        SysFreeString(v6);
      if ( v7 )
        SysFreeString(v7);
      if ( v8 )
        SysFreeString(v8);
      if ( v10 )
        SysFreeString(v10);
      v25 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v26 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      return 2147942414LL;
    }
  }
  else
  {
    VariantClear(&pvarg);
    v27 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002b22c  mov     rax, rsp
0x18002b22f  mov     [rax+8], rbx
0x18002b233  mov     [rax+18h], r8
0x18002b237  mov     [rax+10h], rdx
0x18002b23b  push    rbp
0x18002b23c  push    rsi
0x18002b23d  push    rdi
0x18002b23e  push    r12
0x18002b240  push    r13
0x18002b242  push    r14
0x18002b244  push    r15
0x18002b246  lea     rbp, [rax-5Fh]
0x18002b24a  sub     rsp, 90h
0x18002b251  mov     rbx, r9
0x18002b254  mov     r12, rcx
0x18002b257  xor     r15d, r15d
0x18002b25a  mov     [rbp+57h+arg_8], r15
0x18002b25e  mov     [rbp+57h+arg_10], r15
0x18002b262  lea     eax, [r15+3]
0x18002b266  mov     word ptr [rbp+57h+pvarg], ax
0x18002b26a  mov     dword ptr [rbp+57h+pvarg+8], 1
0x18002b271  test    r9, r9
0x18002b274  jz      loc_18002B631
0x18002b27a  lea     rcx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/ma"...
0x18002b281  call    cs:__imp_SysAllocString
0x18002b288  nop     dword ptr [rax+rax+00h]
0x18002b28d  mov     r14, rax
0x18002b290  mov     [rbp+57h+var_90], rax
0x18002b294  lea     rcx, aEDiscoverEAuth; "//e:Discover//e:AuthPolicies"
0x18002b29b  call    cs:__imp_SysAllocString
0x18002b2a2  nop     dword ptr [rax+rax+00h]
0x18002b2a7  mov     rdi, rax
0x18002b2aa  mov     [rbp+57h+var_88], rax
0x18002b2ae  lea     rcx, aAuthpolicy; "AuthPolicy"
0x18002b2b5  call    cs:__imp_SysAllocString
0x18002b2bc  nop     dword ptr [rax+rax+00h]
0x18002b2c1  mov     rsi, rax
0x18002b2c4  mov     [rbp+57h+var_80], rax
0x18002b2c8  mov     rcx, rbx; psz
0x18002b2cb  call    cs:__imp_SysAllocString
0x18002b2d2  nop     dword ptr [rax+rax+00h]
0x18002b2d7  mov     rbx, rax
0x18002b2da  mov     [rbp+57h+var_78], rax
0x18002b2de  test    r14, r14
0x18002b2e1  jz      loc_18002B591
0x18002b2e7  test    rdi, rdi
0x18002b2ea  jz      loc_18002B591
0x18002b2f0  test    rsi, rsi
0x18002b2f3  jz      loc_18002B591
0x18002b2f9  test    rax, rax
0x18002b2fc  jz      loc_18002B591
0x18002b302  mov     r15, [r12]
0x18002b306  mov     rax, [r15]
0x18002b309  mov     r13, [rax+1C0h]
0x18002b310  mov     rcx, [rbp+57h+arg_10]
0x18002b314  test    rcx, rcx
0x18002b317  jz      short loc_18002B32E
0x18002b319  mov     [rbp+57h+arg_10], 0
0x18002b321  mov     rax, [rcx]
0x18002b324  mov     rax, [rax+10h]
0x18002b328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b32d  nop
0x18002b32e  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18002b332  movaps  [rbp+57h+var_50], xmm0
0x18002b336  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18002b33b  movsd   [rbp+57h+var_40], xmm1
0x18002b340  lea     rax, [rbp+57h+arg_10]
0x18002b344  mov     [rsp+20h], rax
0x18002b349  mov     r9, r14
0x18002b34c  mov     r8, rsi
0x18002b34f  lea     rdx, [rbp+57h+var_50]
0x18002b353  mov     rcx, r15
0x18002b356  mov     rax, r13
0x18002b359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b35e  mov     r15d, eax
0x18002b361  xor     r13d, r13d
0x18002b364  test    eax, eax
0x18002b366  jns     loc_18002B3F9
0x18002b36c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002b370  call    cs:__imp_VariantClear
0x18002b377  nop     dword ptr [rax+rax+00h]
0x18002b37c  nop
0x18002b37d  mov     rcx, r14; bstrString
0x18002b380  call    cs:__imp_SysFreeString
0x18002b387  nop     dword ptr [rax+rax+00h]
0x18002b38c  nop
0x18002b38d  mov     rcx, rdi; bstrString
0x18002b390  call    cs:__imp_SysFreeString
0x18002b397  nop     dword ptr [rax+rax+00h]
0x18002b39c  nop
0x18002b39d  mov     rcx, rsi; bstrString
0x18002b3a0  call    cs:__imp_SysFreeString
0x18002b3a7  nop     dword ptr [rax+rax+00h]
0x18002b3ac  nop
0x18002b3ad  mov     rcx, rbx; bstrString
0x18002b3b0  call    cs:__imp_SysFreeString
0x18002b3b7  nop     dword ptr [rax+rax+00h]
0x18002b3bc  nop
0x18002b3bd  mov     rcx, [rbp+57h+arg_10]
0x18002b3c1  test    rcx, rcx
0x18002b3c4  jz      short loc_18002B3D7
0x18002b3c6  mov     [rbp+57h+arg_10], r13
0x18002b3ca  mov     rax, [rcx]
0x18002b3cd  mov     rax, [rax+10h]
0x18002b3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3d6  nop
0x18002b3d7  mov     rcx, [rbp+57h+arg_8]
0x18002b3db  test    rcx, rcx
0x18002b3de  jz      short loc_18002B3F1
0x18002b3e0  mov     [rbp+57h+arg_8], r13
0x18002b3e4  mov     rax, [rcx]
0x18002b3e7  mov     rax, [rax+10h]
0x18002b3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3f0  nop
0x18002b3f1  mov     eax, r15d
0x18002b3f4  jmp     loc_18002B67B
0x18002b3f9  mov     rcx, [rbp+57h+arg_10]
0x18002b3fd  mov     rax, [rcx]
0x18002b400  mov     rdx, rbx
0x18002b403  mov     rax, [rax+0D8h]
0x18002b40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b40f  mov     r15d, eax
0x18002b412  test    eax, eax
0x18002b414  jns     loc_18002B4A4
0x18002b41a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002b41e  call    cs:__imp_VariantClear
0x18002b425  nop     dword ptr [rax+rax+00h]
0x18002b42a  nop
0x18002b42b  mov     rcx, r14; bstrString
0x18002b42e  call    cs:__imp_SysFreeString
0x18002b435  nop     dword ptr [rax+rax+00h]
0x18002b43a  nop
0x18002b43b  mov     rcx, rdi; bstrString
0x18002b43e  call    cs:__imp_SysFreeString
0x18002b445  nop     dword ptr [rax+rax+00h]
0x18002b44a  nop
0x18002b44b  mov     rcx, rsi; bstrString
0x18002b44e  call    cs:__imp_SysFreeString
0x18002b455  nop     dword ptr [rax+rax+00h]
0x18002b45a  nop
0x18002b45b  mov     rcx, rbx; bstrString
0x18002b45e  call    cs:__imp_SysFreeString
0x18002b465  nop     dword ptr [rax+rax+00h]
0x18002b46a  nop
0x18002b46b  mov     rcx, [rbp+57h+arg_10]
0x18002b46f  test    rcx, rcx
0x18002b472  jz      short loc_18002B485
0x18002b474  mov     [rbp+57h+arg_10], r13
0x18002b478  mov     rax, [rcx]
0x18002b47b  mov     rax, [rax+10h]
0x18002b47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b484  nop
0x18002b485  mov     rcx, [rbp+57h+arg_8]
0x18002b489  test    rcx, rcx
0x18002b48c  jz      short loc_18002B49F
0x18002b48e  mov     [rbp+57h+arg_8], r13
0x18002b492  mov     rax, [rcx]
0x18002b495  mov     rax, [rax+10h]
0x18002b499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b49e  nop
0x18002b49f  jmp     loc_18002B3F1
0x18002b4a4  mov     r15, [r12]
0x18002b4a8  mov     rax, [r15]
0x18002b4ab  mov     r12, [rax+128h]
0x18002b4b2  mov     rcx, [rbp+57h+arg_8]
0x18002b4b6  test    rcx, rcx
0x18002b4b9  jz      short loc_18002B4CC
0x18002b4bb  mov     [rbp+57h+arg_8], r13
0x18002b4bf  mov     rdx, [rcx]
0x18002b4c2  mov     rax, [rdx+10h]
0x18002b4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4cb  nop
0x18002b4cc  lea     r8, [rbp+57h+arg_8]
0x18002b4d0  mov     rdx, rdi
0x18002b4d3  mov     rcx, r15
0x18002b4d6  mov     rax, r12
0x18002b4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4de  mov     r15d, eax
0x18002b4e1  test    eax, eax
0x18002b4e3  js      short loc_18002B507
0x18002b4e5  mov     rcx, [rbp+57h+arg_8]
0x18002b4e9  test    rcx, rcx
0x18002b4ec  jz      short loc_18002B507
0x18002b4ee  mov     rax, [rcx]
0x18002b4f1  xor     r8d, r8d
0x18002b4f4  mov     rdx, [rbp+57h+arg_10]
0x18002b4f8  mov     rax, [rax+0A8h]
0x18002b4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b504  mov     r15d, eax
0x18002b507  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002b50b  call    cs:__imp_VariantClear
0x18002b512  nop     dword ptr [rax+rax+00h]
0x18002b517  nop
0x18002b518  mov     rcx, r14; bstrString
0x18002b51b  call    cs:__imp_SysFreeString
0x18002b522  nop     dword ptr [rax+rax+00h]
0x18002b527  nop
0x18002b528  mov     rcx, rdi; bstrString
0x18002b52b  call    cs:__imp_SysFreeString
0x18002b532  nop     dword ptr [rax+rax+00h]
0x18002b537  nop
0x18002b538  mov     rcx, rsi; bstrString
0x18002b53b  call    cs:__imp_SysFreeString
0x18002b542  nop     dword ptr [rax+rax+00h]
0x18002b547  nop
0x18002b548  mov     rcx, rbx; bstrString
0x18002b54b  call    cs:__imp_SysFreeString
0x18002b552  nop     dword ptr [rax+rax+00h]
0x18002b557  nop
0x18002b558  mov     rcx, [rbp+57h+arg_10]
0x18002b55c  test    rcx, rcx
0x18002b55f  jz      short loc_18002B572
0x18002b561  mov     [rbp+57h+arg_10], r13
0x18002b565  mov     rax, [rcx]
0x18002b568  mov     rax, [rax+10h]
0x18002b56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b571  nop
0x18002b572  mov     rcx, [rbp+57h+arg_8]
0x18002b576  test    rcx, rcx
0x18002b579  jz      short loc_18002B58C
0x18002b57b  mov     [rbp+57h+arg_8], r13
0x18002b57f  mov     rax, [rcx]
0x18002b582  mov     rax, [rax+10h]
0x18002b586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b58b  nop
0x18002b58c  jmp     loc_18002B3F1
0x18002b591  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002b595  call    cs:__imp_VariantClear
0x18002b59c  nop     dword ptr [rax+rax+00h]
0x18002b5a1  nop
0x18002b5a2  test    r14, r14
0x18002b5a5  jz      short loc_18002B5B7
0x18002b5a7  mov     rcx, r14; bstrString
0x18002b5aa  call    cs:__imp_SysFreeString
0x18002b5b1  nop     dword ptr [rax+rax+00h]
0x18002b5b6  nop
0x18002b5b7  test    rdi, rdi
0x18002b5ba  jz      short loc_18002B5CC
0x18002b5bc  mov     rcx, rdi; bstrString
0x18002b5bf  call    cs:__imp_SysFreeString
0x18002b5c6  nop     dword ptr [rax+rax+00h]
0x18002b5cb  nop
0x18002b5cc  test    rsi, rsi
0x18002b5cf  jz      short loc_18002B5E1
0x18002b5d1  mov     rcx, rsi; bstrString
0x18002b5d4  call    cs:__imp_SysFreeString
0x18002b5db  nop     dword ptr [rax+rax+00h]
0x18002b5e0  nop
0x18002b5e1  test    rbx, rbx
0x18002b5e4  jz      short loc_18002B5F6
0x18002b5e6  mov     rcx, rbx; bstrString
0x18002b5e9  call    cs:__imp_SysFreeString
0x18002b5f0  nop     dword ptr [rax+rax+00h]
0x18002b5f5  nop
0x18002b5f6  mov     rcx, [rbp+57h+arg_10]
0x18002b5fa  test    rcx, rcx
0x18002b5fd  jz      short loc_18002B610
0x18002b5ff  mov     [rbp+57h+arg_10], r15
0x18002b603  mov     rax, [rcx]
0x18002b606  mov     rax, [rax+10h]
0x18002b60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b60f  nop
0x18002b610  mov     rcx, [rbp+57h+arg_8]
0x18002b614  test    rcx, rcx
0x18002b617  jz      short loc_18002B62A
0x18002b619  mov     [rbp+57h+arg_8], r15
0x18002b61d  mov     rax, [rcx]
0x18002b620  mov     rax, [rax+10h]
0x18002b624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b629  nop
0x18002b62a  mov     eax, 8007000Eh
0x18002b62f  jmp     short loc_18002B67B
0x18002b631  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002b635  call    cs:__imp_VariantClear
0x18002b63c  nop     dword ptr [rax+rax+00h]
0x18002b641  nop
0x18002b642  mov     rcx, [rbp+57h+arg_10]
0x18002b646  test    rcx, rcx
0x18002b649  jz      short loc_18002B65C
0x18002b64b  mov     [rbp+57h+arg_10], r15
0x18002b64f  mov     rax, [rcx]
0x18002b652  mov     rax, [rax+10h]
0x18002b656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b65b  nop
0x18002b65c  mov     rcx, [rbp+57h+arg_8]
0x18002b660  test    rcx, rcx
0x18002b663  jz      short loc_18002B676
0x18002b665  mov     [rbp+57h+arg_8], r15
0x18002b669  mov     rax, [rcx]
0x18002b66c  mov     rax, [rax+10h]
0x18002b670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b675  nop
0x18002b676  mov     eax, 80070057h
0x18002b67b  mov     rbx, [rsp+0C0h+arg_0]
0x18002b683  add     rsp, 90h
0x18002b68a  pop     r15
0x18002b68c  pop     r14
0x18002b68e  pop     r13
0x18002b690  pop     r12
0x18002b692  pop     rdi
  ... truncated ...
```
