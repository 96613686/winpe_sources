# CBGImage::Init_CBGImage(IHTMLDocument2 *,IHTMLElement *,ulong)

- ea: `0x180083f5c`
- end: `0x180084138`
- name: `?Init_CBGImage@CBGImage@@QEAAJPEAUIHTMLDocument2@@PEAUIHTMLElement@@K@Z`
- size: `476`
- prototype: `__int64 __fastcall(CBGImage *__hidden this, struct IHTMLDocument2 *, struct IHTMLElement *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180083b4c`

## callees

- `0x180073b68`
- `0x180073d20`
- `0x18007523c`
- `0x180083f5c`
- `0x18008b690`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!UrlCombineW` at `0x18008408b`
- `SHLWAPI!UrlCombineW` at `0x1800840bf`
- `SHLWAPI!UrlCombineW` at `0x18008408b`
- `SHLWAPI!UrlCombineW` at `0x1800840bf`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18008409a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18008409a`
- `OLEAUT32!__imp_SysFreeString` at `0x18008401e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800840cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800840e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800840ea`
- `OLEAUT32!__imp_SysFreeString` at `0x180084116`
- `OLEAUT32!__imp_SysFreeString` at `0x18008401e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800840cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800840e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800840ea`
- `OLEAUT32!__imp_SysFreeString` at `0x180084116`

## pseudocode

```c
__int64 __fastcall CBGImage::Init_CBGImage(CBGImage *this, struct IHTMLDocument2 *a2, struct IHTMLElement *a3, int a4)
{
  int v8; // r9d
  __int64 v9; // rcx
  WCHAR *v10; // rbx
  OLECHAR *v11; // rax
  unsigned int v12; // ebx
  PCWSTR pszRelative; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  PCWSTR pszBase; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcchCombined; // [rsp+80h] [rbp+30h] BYREF

  bstrString = 0;
  pszRelative = 0;
  pszBase = 0;
  pcchCombined = 0;
  if ( !a3 )
    return 2147942487LL;
  *((_DWORD *)this + 12) = a4;
  if ( a4 )
  {
    v8 = a4 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
        return 2147500037LL;
      if ( !(unsigned int)FindStyleRule(a2, (const unsigned __int16 *)a2, (struct IHTMLRuleStyle **)this + 9) )
      {
        v9 = *((_QWORD *)this + 9);
LABEL_9:
        (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9 + 208LL))(v9, &bstrString);
        UnWrapStyleSheetUrl(bstrString, (unsigned __int16 **)&pszRelative);
        SysFreeString(bstrString);
      }
    }
    else
    {
      ((void (__fastcall *)(struct IHTMLElement *, char *))a3->lpVtbl->get_style)(a3, (char *)this + 64);
      v9 = *((_QWORD *)this + 8);
      if ( v9 )
        goto LABEL_9;
    }
  }
  else if ( !((__int64 (__fastcall *)(struct IHTMLElement *, GUID *, char *))a3->lpVtbl->QueryInterface)(
               a3,
               &IID_IHTMLBodyElement,
               (char *)this + 56) )
  {
    (*(void (__fastcall **)(_QWORD, PCWSTR *))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7), &pszRelative);
  }
  if ( pszRelative )
  {
    if ( !(unsigned int)FindNearestBaseUrl(a2, a3, (unsigned __int16 **)&pszBase) )
    {
      v10 = (WCHAR *)pszBase;
      UrlCombineW(pszBase, pszRelative, 0, &pcchCombined, 0);
      if ( pcchCombined )
      {
        v11 = SysAllocStringLen(0, pcchCombined);
        bstrString = v11;
        if ( v11 )
        {
          if ( UrlCombineW(v10, pszRelative, v11, &pcchCombined, 0x10000000u) < 0 )
          {
            SysFreeString(bstrString);
          }
          else
          {
            SysFreeString((BSTR)pszRelative);
            pszRelative = bstrString;
          }
        }
      }
      SysFreeString(v10);
    }
    if ( pszRelative )
    {
      *((_QWORD *)this + 4) = pszRelative;
      pszRelative = 0;
      v12 = CBaseTag::Init(this, a3);
      SysFreeString((BSTR)pszRelative);
      return v12;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180083f5c  mov     [rsp-18h+arg_0], rbx
0x180083f61  mov     [rsp-18h+arg_8], rsi
0x180083f66  push    rbp
0x180083f67  push    rdi
0x180083f68  push    r14
0x180083f6a  mov     rbp, rsp
0x180083f6d  sub     rsp, 50h
0x180083f71  mov     [rbp+bstrString], 0
0x180083f79  mov     rsi, r8
0x180083f7c  mov     [rbp+pszRelative], 0
0x180083f84  mov     r14, rdx
0x180083f87  mov     [rbp+pszBase], 0
0x180083f8f  mov     rdi, rcx
0x180083f92  mov     [rbp+pcchCombined], 0
0x180083f99  test    r8, r8
0x180083f9c  jnz     short loc_180083FA8
0x180083f9e  mov     eax, 80070057h
0x180083fa3  jmp     loc_180084125
0x180083fa8  mov     [rcx+30h], r9d
0x180083fac  test    r9d, r9d
0x180083faf  jz      short loc_180084026
0x180083fb1  sub     r9d, 1
0x180083fb5  jz      short loc_180083FDB
0x180083fb7  cmp     r9d, 1
0x180083fbb  jnz     loc_180084120
0x180083fc1  lea     r8, [rcx+48h]; struct IHTMLRuleStyle **
0x180083fc5  mov     rcx, r14; struct IHTMLDocument2 *
0x180083fc8  call    ?FindStyleRule@@YAJPEAUIHTMLDocument2@@PEBGPEAPEAUIHTMLRuleStyle@@@Z; FindStyleRule(IHTMLDocument2 *,ushort const *,IHTMLRuleStyle * *)
0x180083fcd  test    eax, eax
0x180083fcf  jnz     loc_180084057
0x180083fd5  mov     rcx, [rdi+48h]
0x180083fd9  jmp     short loc_180083FFA
0x180083fdb  mov     rax, [r8]
0x180083fde  lea     rdx, [rcx+40h]
0x180083fe2  mov     rcx, rsi
0x180083fe5  mov     rax, [rax+80h]
0x180083fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ff1  mov     rcx, [rdi+40h]
0x180083ff5  test    rcx, rcx
0x180083ff8  jz      short loc_180084057
0x180083ffa  mov     rax, [rcx]
0x180083ffd  lea     rdx, [rbp+bstrString]
0x180084001  mov     rax, [rax+0D0h]
0x180084008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008400d  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x180084011  lea     rdx, [rbp+pszRelative]; unsigned __int16 **
0x180084015  call    ?UnWrapStyleSheetUrl@@YAJPEAGPEAPEAG@Z; UnWrapStyleSheetUrl(ushort *,ushort * *)
0x18008401a  mov     rcx, [rbp+bstrString]; bstrString
0x18008401e  call    cs:__imp_SysFreeString
0x180084024  jmp     short loc_180084057
0x180084026  mov     rax, [r8]
0x180084029  lea     rdx, IID_IHTMLBodyElement
0x180084030  lea     r8, [rcx+38h]
0x180084034  mov     rcx, rsi
0x180084037  mov     rax, [rax]
0x18008403a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008403f  test    eax, eax
0x180084041  jnz     short loc_180084057
0x180084043  mov     rcx, [rdi+38h]
0x180084047  lea     rdx, [rbp+pszRelative]
0x18008404b  mov     rax, [rcx]
0x18008404e  mov     rax, [rax+40h]
0x180084052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084057  cmp     [rbp+pszRelative], 0
0x18008405c  jz      loc_180084120
0x180084062  lea     r8, [rbp+pszBase]; unsigned __int16 **
0x180084066  mov     rdx, rsi; struct IHTMLElement *
0x180084069  mov     rcx, r14; struct IHTMLDocument2 *
0x18008406c  call    ?FindNearestBaseUrl@@YAJPEAUIHTMLDocument2@@PEAUIHTMLElement@@PEAPEAG@Z; FindNearestBaseUrl(IHTMLDocument2 *,IHTMLElement *,ushort * *)
0x180084071  test    eax, eax
0x180084073  jnz     short loc_1800840F0
0x180084075  mov     rbx, [rbp+pszBase]
0x180084079  lea     r9, [rbp+pcchCombined]; pcchCombined
0x18008407d  mov     rdx, [rbp+pszRelative]; pszRelative
0x180084081  mov     rcx, rbx; pszBase
0x180084084  xor     r8d, r8d; pszCombined
0x180084087  mov     [rsp+50h+dwFlags], eax; dwFlags
0x18008408b  call    cs:__imp_UrlCombineW
0x180084091  mov     edx, [rbp+pcchCombined]; ui
0x180084094  test    edx, edx
0x180084096  jz      short loc_1800840E7
0x180084098  xor     ecx, ecx; strIn
0x18008409a  call    cs:__imp_SysAllocStringLen
0x1800840a0  mov     [rbp+bstrString], rax
0x1800840a4  test    rax, rax
0x1800840a7  jz      short loc_1800840E7
0x1800840a9  mov     rdx, [rbp+pszRelative]; pszRelative
0x1800840ad  lea     r9, [rbp+pcchCombined]; pcchCombined
0x1800840b1  mov     r8, rax; pszCombined
0x1800840b4  mov     [rsp+50h+dwFlags], 10000000h; dwFlags
0x1800840bc  mov     rcx, rbx; pszBase
0x1800840bf  call    cs:__imp_UrlCombineW
0x1800840c5  test    eax, eax
0x1800840c7  js      short loc_1800840DD
0x1800840c9  mov     rcx, [rbp+pszRelative]; bstrString
0x1800840cd  call    cs:__imp_SysFreeString
0x1800840d3  mov     rax, [rbp+bstrString]
0x1800840d7  mov     [rbp+pszRelative], rax
0x1800840db  jmp     short loc_1800840E7
0x1800840dd  mov     rcx, [rbp+bstrString]; bstrString
0x1800840e1  call    cs:__imp_SysFreeString
0x1800840e7  mov     rcx, rbx; bstrString
0x1800840ea  call    cs:__imp_SysFreeString
0x1800840f0  mov     rax, [rbp+pszRelative]
0x1800840f4  test    rax, rax
0x1800840f7  jz      short loc_180084120
0x1800840f9  mov     rdx, rsi; struct IHTMLElement *
0x1800840fc  mov     [rdi+20h], rax
0x180084100  mov     rcx, rdi; this
0x180084103  mov     [rbp+pszRelative], 0
0x18008410b  call    ?Init@CBaseTag@@UEAAJPEAUIHTMLElement@@@Z; CBaseTag::Init(IHTMLElement *)
0x180084110  mov     ebx, eax
0x180084112  mov     rcx, [rbp+pszRelative]; bstrString
0x180084116  call    cs:__imp_SysFreeString
0x18008411c  mov     eax, ebx
0x18008411e  jmp     short loc_180084125
0x180084120  mov     eax, 80004005h
0x180084125  mov     rbx, [rsp+50h+arg_0]
0x18008412a  mov     rsi, [rsp+50h+arg_8]
0x18008412f  add     rsp, 50h
0x180084133  pop     r14
0x180084135  pop     rdi
0x180084136  pop     rbp
0x180084137  retn
```
