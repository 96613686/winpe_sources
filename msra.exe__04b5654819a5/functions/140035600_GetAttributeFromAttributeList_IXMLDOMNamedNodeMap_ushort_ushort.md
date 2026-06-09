# GetAttributeFromAttributeList(IXMLDOMNamedNodeMap *,ushort *,ushort * *)

- ea: `0x140035600`
- end: `0x140035782`
- name: `?GetAttributeFromAttributeList@@YAJPEAUIXMLDOMNamedNodeMap@@PEAGPEAPEAG@Z`
- size: `386`
- prototype: `int(struct IXMLDOMNamedNodeMap *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140035788`
- `0x140041d58`
- `0x1400482bc`

## callees

- `0x140034ce4`
- `0x140035600`
- `0x14004d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14003567e`
- `OLEAUT32!__imp_SysAllocString` at `0x1400356f5`
- `OLEAUT32!__imp_SysAllocString` at `0x14003567e`
- `OLEAUT32!__imp_SysAllocString` at `0x1400356f5`
- `OLEAUT32!__imp_SysFreeString` at `0x14003574d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003574d`
- `OLEAUT32!__imp_VariantInit` at `0x140035633`
- `OLEAUT32!__imp_VariantInit` at `0x140035633`
- `OLEAUT32!__imp_VariantClear` at `0x140035739`
- `OLEAUT32!__imp_VariantClear` at `0x140035739`

## string_xrefs

- `0x14003565e`: `base\diagnosis\ra\racommon\src\fileutils.cpp`
- `0x14003570a`: `base\diagnosis\ra\racommon\src\fileutils.cpp`

## pseudocode

```c
__int64 __fastcall GetAttributeFromAttributeList(
        struct IXMLDOMNamedNodeMap *a1,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  CEventLogger *v6; // rcx
  OLECHAR *v7; // rbx
  unsigned int v8; // edi
  BSTR v9; // rax
  CEventLogger *v10; // rcx
  signed int v11; // eax
  CEventLogger *v12; // rcx
  signed int v13; // eax
  CEventLogger *v14; // rcx
  VARIANTARG psz; // [rsp+30h] [rbp-28h] BYREF
  CEventLogger *v17; // [rsp+70h] [rbp+18h] BYREF

  v17 = 0;
  memset(&psz, 0, sizeof(psz));
  VariantInit(&psz);
  if ( a3 )
  {
    v9 = SysAllocString(a2);
    v7 = v9;
    if ( v9 )
    {
      v11 = ((__int64 (__fastcall *)(struct IXMLDOMNamedNodeMap *, BSTR, CEventLogger **))a1->lpVtbl->getNamedItem)(
              a1,
              v9,
              &v17);
      if ( v11 >= 0 && (v12 = v17) != 0 )
      {
        v13 = (*(__int64 (__fastcall **)(CEventLogger *, VARIANTARG *))(*(_QWORD *)v17 + 64LL))(v17, &psz);
        v8 = v13;
        if ( v13 >= 0 )
          *a3 = SysAllocString(psz.bstrVal);
        else
          CEventLogger::LogError(
            v14,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
            0x81u,
            L"GetAttributeFromAttributeList",
            v13);
      }
      else
      {
        CEventLogger::LogError(
          v12,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
          0x79u,
          L"GetAttributeFromAttributeList",
          v11);
        v8 = -2147467259;
      }
    }
    else
    {
      v8 = -2147024882;
      CEventLogger::LogError(
        v10,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
        0x75u,
        L"GetAttributeFromAttributeList",
        0x8007000E);
    }
  }
  else
  {
    v7 = 0;
    v8 = -2147467261;
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x72u,
      L"GetAttributeFromAttributeList",
      0x80004003);
  }
  VariantClear(&psz);
  if ( v7 )
    SysFreeString(v7);
  if ( v17 )
    (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v17 + 16LL))(v17);
  return v8;
}

```

## disassembly

```asm
0x140035600  mov     r11, rsp
0x140035603  mov     [r11+8], rbx
0x140035607  mov     [r11+10h], rsi
0x14003560b  push    rdi
0x14003560c  sub     rsp, 50h
0x140035610  xorps   xmm0, xmm0
0x140035613  mov     qword ptr [r11+18h], 0
0x14003561b  mov     rdi, rcx
0x14003561e  xor     eax, eax
0x140035620  movups  xmmword ptr [rsp+58h+psz], xmm0
0x140035625  lea     rcx, [r11-28h]; pvarg
0x140035629  mov     [r11-18h], rax
0x14003562d  mov     rsi, r8
0x140035630  mov     rbx, rdx
0x140035633  call    cs:__imp_VariantInit
0x14003563a  nop     dword ptr [rax+rax+00h]
0x14003563f  test    rsi, rsi
0x140035642  jnz     short loc_14003567B
0x140035644  xor     ebx, ebx
0x140035646  mov     [rsp+58h+var_30], 80004003h; unsigned int
0x14003564e  mov     edi, 80004003h
0x140035653  lea     r9d, [rsi+72h]; unsigned int
0x140035657  lea     rax, aGetattributefr; "GetAttributeFromAttributeList"
0x14003565e  lea     r8, aBaseDiagnosisR_16; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x140035665  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x14003566a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140035671  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140035676  jmp     loc_140035734
0x14003567b  mov     rcx, rbx; psz
0x14003567e  call    cs:__imp_SysAllocString
0x140035685  nop     dword ptr [rax+rax+00h]
0x14003568a  mov     rbx, rax
0x14003568d  test    rax, rax
0x140035690  jnz     short loc_1400356A5
0x140035692  mov     edi, 8007000Eh
0x140035697  mov     [rsp+58h+var_30], 8007000Eh
0x14003569f  lea     r9d, [rax+75h]
0x1400356a3  jmp     short loc_140035657
0x1400356a5  mov     rax, [rdi]
0x1400356a8  lea     r8, [rsp+58h+arg_10]
0x1400356ad  mov     rdx, rbx
0x1400356b0  mov     rcx, rdi
0x1400356b3  mov     rax, [rax+38h]
0x1400356b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400356bc  test    eax, eax
0x1400356be  js      short loc_140035706
0x1400356c0  mov     rcx, [rsp+58h+arg_10]
0x1400356c5  test    rcx, rcx
0x1400356c8  jz      short loc_140035706
0x1400356ca  mov     rax, [rcx]
0x1400356cd  lea     rdx, [rsp+58h+psz]
0x1400356d2  mov     rax, [rax+40h]
0x1400356d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400356db  mov     edi, eax
0x1400356dd  test    eax, eax
0x1400356df  jns     short loc_1400356F0
0x1400356e1  mov     [rsp+58h+var_30], eax
0x1400356e5  mov     r9d, 81h
0x1400356eb  jmp     loc_140035657
0x1400356f0  mov     rcx, qword ptr [rsp+58h+psz+8]; psz
0x1400356f5  call    cs:__imp_SysAllocString
0x1400356fc  nop     dword ptr [rax+rax+00h]
0x140035701  mov     [rsi], rax
0x140035704  jmp     short loc_140035734
0x140035706  mov     [rsp+58h+var_30], eax; unsigned int
0x14003570a  lea     r8, aBaseDiagnosisR_16; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x140035711  lea     rax, aGetattributefr; "GetAttributeFromAttributeList"
0x140035718  mov     r9d, 79h ; 'y'; unsigned int
0x14003571e  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140035725  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x14003572a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003572f  mov     edi, 80004005h
0x140035734  lea     rcx, [rsp+58h+psz]; pvarg
0x140035739  call    cs:__imp_VariantClear
0x140035740  nop     dword ptr [rax+rax+00h]
0x140035745  test    rbx, rbx
0x140035748  jz      short loc_140035759
0x14003574a  mov     rcx, rbx; bstrString
0x14003574d  call    cs:__imp_SysFreeString
0x140035754  nop     dword ptr [rax+rax+00h]
0x140035759  mov     rcx, [rsp+58h+arg_10]
0x14003575e  test    rcx, rcx
0x140035761  jz      short loc_14003576F
0x140035763  mov     rax, [rcx]
0x140035766  mov     rax, [rax+10h]
0x14003576a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003576f  mov     rbx, [rsp+58h+arg_0]
0x140035774  mov     eax, edi
0x140035776  mov     rsi, [rsp+58h+arg_8]
0x14003577b  add     rsp, 50h
0x14003577f  pop     rdi
0x140035780  retn
```
