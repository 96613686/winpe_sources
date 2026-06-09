# GetAttribute(IXMLDOMNode *,ushort *,ushort * *)

- ea: `0x18000d020`
- end: `0x18000d1b3`
- name: `?GetAttribute@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b2a4`
- `0x18000b6ec`
- `0x18000ba98`
- `0x18000c454`
- `0x18000d1bc`
- `0x18000f034`

## callees

- `0x18000ce98`
- `0x18000d020`
- `0x18000da60`
- `0x18002b010`

## import_xrefs

- `msvcrt!_itow` at `0x18000d12a`
- `msvcrt!_itow` at `0x18000d12a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d112`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d112`
- `OLEAUT32!__imp_VariantInit` at `0x18000d05b`
- `OLEAUT32!__imp_VariantInit` at `0x18000d05b`
- `OLEAUT32!__imp_VariantClear` at `0x18000d160`
- `OLEAUT32!__imp_VariantClear` at `0x18000d19b`
- `OLEAUT32!__imp_VariantClear` at `0x18000d160`
- `OLEAUT32!__imp_VariantClear` at `0x18000d19b`

## pseudocode

```c
__int64 __fastcall GetAttribute(struct IXMLDOMNode *a1, unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  const OLECHAR *bstrVal; // rcx
  VARIANTARG psz; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  struct IXMLDOMNode *v13; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  v13 = 0;
  memset(&psz, 0, sizeof(psz));
  VariantInit(&psz);
  if ( a1 )
  {
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))a1->lpVtbl->get_attributes)(a1, &v12);
    v6 = v7;
    if ( v7 != 1 )
    {
      if ( (unsigned int)CheckHR(v7) )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct IXMLDOMNode **))(*(_QWORD *)v12 + 56LL))(
               v12,
               a2,
               &v13);
        v6 = v8;
        if ( v8 != 1 )
        {
          if ( (unsigned int)CheckHR(v8) )
          {
            v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, VARIANTARG *))v13->lpVtbl->get_nodeValue)(v13, &psz);
            if ( (unsigned int)CheckHR(v6) )
            {
              if ( psz.vt == 3 )
              {
                _itow(psz.lVal, *a3, 10);
              }
              else
              {
                bstrVal = &LocaleName;
                if ( psz.vt == 8 )
                  bstrVal = psz.bstrVal;
                *a3 = SysAllocString(bstrVal);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v6 = 1;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  ReleaseDomNode(&v13);
  VariantClear(&psz);
  return v6;
}

```

## disassembly

```asm
0x18000d020  mov     r11, rsp
0x18000d023  mov     [r11+10h], rbx
0x18000d027  mov     [r11+18h], rsi
0x18000d02b  push    rdi
0x18000d02c  sub     rsp, 40h
0x18000d030  mov     rdi, r8
0x18000d033  mov     rsi, rdx
0x18000d036  mov     rbx, rcx
0x18000d039  mov     qword ptr [r11+8], 0
0x18000d041  mov     qword ptr [r11+20h], 0
0x18000d049  xorps   xmm0, xmm0
0x18000d04c  xor     eax, eax
0x18000d04e  movups  xmmword ptr [rsp+48h+psz], xmm0
0x18000d053  mov     [r11-18h], rax
0x18000d057  lea     rcx, [r11-28h]; pvarg
0x18000d05b  call    cs:__imp_VariantInit
0x18000d061  test    rbx, rbx
0x18000d064  jnz     short loc_18000D070
0x18000d066  mov     ebx, 1
0x18000d06b  jmp     loc_18000D16D
0x18000d070  mov     rax, [rbx]
0x18000d073  lea     rdx, [rsp+48h+arg_0]
0x18000d078  mov     rcx, rbx
0x18000d07b  mov     rax, [rax+88h]
0x18000d082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d087  mov     ebx, eax
0x18000d089  cmp     eax, 1
0x18000d08c  jz      loc_18000D16D
0x18000d092  mov     ecx, eax; int
0x18000d094  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000d099  test    eax, eax
0x18000d09b  jz      loc_18000D16D
0x18000d0a1  mov     rcx, [rsp+48h+arg_0]
0x18000d0a6  mov     rax, [rcx]
0x18000d0a9  lea     r8, [rsp+48h+arg_18]
0x18000d0ae  mov     rdx, rsi
0x18000d0b1  mov     rax, [rax+38h]
0x18000d0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0ba  mov     ebx, eax
0x18000d0bc  cmp     eax, 1
0x18000d0bf  jz      loc_18000D16D
0x18000d0c5  mov     ecx, eax; int
0x18000d0c7  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000d0cc  test    eax, eax
0x18000d0ce  jz      loc_18000D16D
0x18000d0d4  mov     rcx, [rsp+48h+arg_18]
0x18000d0d9  mov     rax, [rcx]
0x18000d0dc  lea     rdx, [rsp+48h+psz]
0x18000d0e1  mov     rax, [rax+40h]
0x18000d0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0ea  mov     ebx, eax
0x18000d0ec  mov     ecx, eax; int
0x18000d0ee  call    ?CheckHR@@YAHJ@Z; CheckHR(long)
0x18000d0f3  test    eax, eax
0x18000d0f5  jz      short loc_18000D16D
0x18000d0f7  movzx   eax, word ptr [rsp+48h+psz]
0x18000d0fc  cmp     eax, 3
0x18000d0ff  jz      short loc_18000D11D
0x18000d101  cmp     eax, 8
0x18000d104  lea     rcx, LocaleName
0x18000d10b  jnz     short loc_18000D112
0x18000d10d  mov     rcx, qword ptr [rsp+48h+psz+8]; psz
0x18000d112  call    cs:__imp_SysAllocString
0x18000d118  mov     [rdi], rax
0x18000d11b  jmp     short loc_18000D130
0x18000d11d  mov     r8d, 0Ah; Radix
0x18000d123  mov     rdx, [rdi]; Buffer
0x18000d126  mov     ecx, dword ptr [rsp+48h+psz+8]; Value
0x18000d12a  call    cs:__imp__itow
0x18000d130  jmp     short loc_18000D16D
0x18000d132  mov     rcx, [rsp+48h+arg_0]
0x18000d137  test    rcx, rcx
0x18000d13a  jz      short loc_18000D151
0x18000d13c  mov     rax, [rcx]
0x18000d13f  mov     rax, [rax+10h]
0x18000d143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d148  mov     [rsp+48h+arg_0], 0
0x18000d151  lea     rcx, [rsp+48h+arg_18]; struct IXMLDOMNode **
0x18000d156  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000d15b  lea     rcx, [rsp+48h+psz]; pvarg
0x18000d160  call    cs:__imp_VariantClear
0x18000d166  mov     eax, 80004005h
0x18000d16b  jmp     short loc_18000D1A3
0x18000d16d  mov     rcx, [rsp+48h+arg_0]
0x18000d172  test    rcx, rcx
0x18000d175  jz      short loc_18000D18C
0x18000d177  mov     rax, [rcx]
0x18000d17a  mov     rax, [rax+10h]
0x18000d17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d183  mov     [rsp+48h+arg_0], 0
0x18000d18c  lea     rcx, [rsp+48h+arg_18]; struct IXMLDOMNode **
0x18000d191  call    ?ReleaseDomNode@@YAXPEAPEAUIXMLDOMNode@@@Z; ReleaseDomNode(IXMLDOMNode * *)
0x18000d196  lea     rcx, [rsp+48h+psz]; pvarg
0x18000d19b  call    cs:__imp_VariantClear
0x18000d1a1  mov     eax, ebx
0x18000d1a3  mov     rbx, [rsp+48h+arg_8]
0x18000d1a8  mov     rsi, [rsp+48h+arg_10]
0x18000d1ad  add     rsp, 40h
0x18000d1b1  pop     rdi
0x18000d1b2  retn
0x18002a7b5  push    rbp
0x18002a7b7  sub     rsp, 20h
0x18002a7bb  mov     rbp, rdx
0x18002a7be  mov     rax, [rcx]
0x18002a7c1  xor     ecx, ecx
0x18002a7c3  cmp     dword ptr [rax], 0C00000FDh
0x18002a7c9  setz    cl
0x18002a7cc  mov     eax, ecx
0x18002a7ce  add     rsp, 20h
0x18002a7d2  pop     rbp
0x18002a7d3  retn
```
