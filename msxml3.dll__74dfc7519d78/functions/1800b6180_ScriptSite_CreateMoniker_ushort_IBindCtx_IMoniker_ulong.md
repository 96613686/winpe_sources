# ScriptSite::CreateMoniker(ushort *,IBindCtx *,IMoniker * *,ulong)

- ea: `0x1800b6180`
- end: `0x1800b627a`
- name: `?CreateMoniker@ScriptSite@@UEAAJPEAGPEAUIBindCtx@@PEAPEAUIMoniker@@K@Z`
- size: `250`
- prototype: `int(ScriptSite *__hidden this, unsigned __int16 *, struct IBindCtx *, struct IMoniker **, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002ac90`
- `0x18002d7e0`
- `0x1800b6180`
- `0x1800b6a48`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1800b61fc`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1800b61fc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b6249`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b6249`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b61ef`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b61ef`
- `urlmon!CreateURLMonikerEx` at `0x1800b6221`
- `urlmon!CreateURLMonikerEx` at `0x1800b623e`
- `urlmon!CreateURLMonikerEx` at `0x1800b6221`
- `urlmon!CreateURLMonikerEx` at `0x1800b623e`

## pseudocode

```c
__int64 __fastcall ScriptSite::CreateMoniker(
        ScriptSite *this,
        unsigned __int16 *a2,
        struct IBindCtx *a3,
        struct IMoniker **a4)
{
  ScriptSite *v5; // rsi
  HRESULT URLMoniker; // ebx
  int URL; // eax
  WCHAR *v9; // rsi
  IMoniker *v10; // rcx
  BSTR pbstr; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v13[48]; // [rsp+28h] [rbp-30h] BYREF
  LPMONIKER ppmk; // [rsp+60h] [rbp+8h] BYREF

  v5 = (ScriptSite *)((char *)this - 48);
  URLMoniker = ModelInit::init(v13, (*((_DWORD *)this - 8) & 4LL) == 0, a3);
  if ( URLMoniker < 0 )
    goto LABEL_14;
  pbstr = 0;
  ppmk = 0;
  if ( !a2 )
  {
    URLMoniker = -2147024809;
    goto LABEL_14;
  }
  URL = ScriptSite::getURL(v5, &pbstr);
  v9 = pbstr;
  URLMoniker = URL;
  if ( URL >= 0 )
  {
    if ( SysStringLen(pbstr) )
    {
      URLMoniker = CreateURLMonikerEx(0, v9, &ppmk, 1u);
      if ( URLMoniker < 0 )
        goto LABEL_12;
      v10 = ppmk;
    }
    else
    {
      if ( !PathIsURLW(a2) )
      {
        URLMoniker = -2147024809;
        goto LABEL_12;
      }
      v10 = 0;
    }
    URLMoniker = CreateURLMonikerEx(v10, a2, a4, 1u);
  }
LABEL_12:
  SysFreeString(v9);
  if ( ppmk )
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
LABEL_14:
  ModelInit::~ModelInit((ModelInit *)v13);
  return (unsigned int)URLMoniker;
}

```

## disassembly

```asm
0x1800b6180  push    rbx
0x1800b6182  push    rbp
0x1800b6183  push    rsi
0x1800b6184  push    rdi
0x1800b6185  sub     rsp, 38h
0x1800b6189  mov     rdi, rdx
0x1800b618c  lea     rsi, [rcx-30h]
0x1800b6190  mov     edx, [rsi+10h]
0x1800b6193  lea     rcx, [rsp+58h+var_30]
0x1800b6198  shr     rdx, 2
0x1800b619c  mov     rbp, r9
0x1800b619f  not     edx
0x1800b61a1  and     edx, 1
0x1800b61a4  call    ?init@ModelInit@@QEAAJW4RentalEnum@@@Z; ModelInit::init(RentalEnum)
0x1800b61a9  mov     ebx, eax
0x1800b61ab  test    eax, eax
0x1800b61ad  js      loc_1800B6265
0x1800b61b3  mov     [rsp+58h+pbstr], 0
0x1800b61bc  mov     [rsp+58h+ppmk], 0
0x1800b61c5  test    rdi, rdi
0x1800b61c8  jnz     short loc_1800B61D4
0x1800b61ca  mov     ebx, 80070057h
0x1800b61cf  jmp     loc_1800B6265
0x1800b61d4  lea     rdx, [rsp+58h+pbstr]; unsigned __int16 **
0x1800b61d9  mov     rcx, rsi; this
0x1800b61dc  call    ?getURL@ScriptSite@@IEAAJPEAPEAG@Z; ScriptSite::getURL(ushort * *)
0x1800b61e1  mov     rsi, [rsp+58h+pbstr]
0x1800b61e6  mov     ebx, eax
0x1800b61e8  test    eax, eax
0x1800b61ea  js      short loc_1800B6246
0x1800b61ec  mov     rcx, rsi; pbstr
0x1800b61ef  call    cs:__imp_SysStringLen
0x1800b61f5  test    eax, eax
0x1800b61f7  jnz     short loc_1800B6211
0x1800b61f9  mov     rcx, rdi; pszPath
0x1800b61fc  call    cs:__imp_PathIsURLW
0x1800b6202  test    eax, eax
0x1800b6204  jz      short loc_1800B620A
0x1800b6206  xor     ecx, ecx
0x1800b6208  jmp     short loc_1800B6232
0x1800b620a  mov     ebx, 80070057h
0x1800b620f  jmp     short loc_1800B6246
0x1800b6211  mov     r9d, 1; dwFlags
0x1800b6217  lea     r8, [rsp+58h+ppmk]; ppmk
0x1800b621c  mov     rdx, rsi; szURL
0x1800b621f  xor     ecx, ecx; pMkCtx
0x1800b6221  call    cs:__imp_CreateURLMonikerEx
0x1800b6227  mov     ebx, eax
0x1800b6229  test    eax, eax
0x1800b622b  js      short loc_1800B6246
0x1800b622d  mov     rcx, [rsp+58h+ppmk]; pMkCtx
0x1800b6232  mov     r9d, 1; dwFlags
0x1800b6238  mov     r8, rbp; ppmk
0x1800b623b  mov     rdx, rdi; szURL
0x1800b623e  call    cs:__imp_CreateURLMonikerEx
0x1800b6244  mov     ebx, eax
0x1800b6246  mov     rcx, rsi; bstrString
0x1800b6249  call    cs:__imp_SysFreeString
0x1800b624f  mov     rcx, [rsp+58h+ppmk]
0x1800b6254  test    rcx, rcx
0x1800b6257  jz      short loc_1800B6265
0x1800b6259  mov     rax, [rcx]
0x1800b625c  mov     rax, [rax+10h]
0x1800b6260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6265  lea     rcx, [rsp+58h+var_30]; this
0x1800b626a  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x1800b626f  mov     eax, ebx
0x1800b6271  add     rsp, 38h
0x1800b6275  pop     rdi
0x1800b6276  pop     rsi
0x1800b6277  pop     rbp
0x1800b6278  pop     rbx
0x1800b6279  retn
```
