# IUnknown_IWebBrowserNavigate2(IUnknown *,_ITEMIDLIST const *,int)

- ea: `0x1800248ac`
- end: `0x1800249e8`
- name: `?IUnknown_IWebBrowserNavigate2@@YAJPEAUIUnknown@@PEFBU_ITEMIDLIST@@H@Z`
- size: `316`
- prototype: `__int64 __fastcall(IUnknown *punk, const struct _ITEMIDLIST *pv, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800249f0`

## callees

- `0x1800248ac`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILGetSize` at `0x180024906`
- `SHELL32!__imp_ILGetSize` at `0x180024906`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800248e0`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800249a6`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800248e0`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800249a6`
- `OLEAUT32!__imp_VariantClear` at `0x180024976`
- `OLEAUT32!__imp_VariantClear` at `0x180024976`
- `PROPSYS!InitVariantFromBuffer` at `0x180024915`
- `PROPSYS!InitVariantFromBuffer` at `0x180024915`

## pseudocode

```c
__int64 __fastcall IUnknown_IWebBrowserNavigate2(IUnknown *punk, const struct _ITEMIDLIST *pv, int a3)
{
  HRESULT v6; // ebx
  UINT v7; // eax
  __int64 *v8; // r8
  __int64 v9; // rdx
  void *v11; // [rsp+40h] [rbp-9h] BYREF
  __int128 v12; // [rsp+48h] [rbp-1h] BYREF
  __int64 v13; // [rsp+58h] [rbp+Fh]
  VARIANT pvar; // [rsp+60h] [rbp+17h] BYREF
  void *ppvOut; // [rsp+C8h] [rbp+7Fh] BYREF

  ppvOut = 0;
  IUnknown_QueryService(punk, &IID_IWebBrowserApp, &IID_IWebBrowser2, &ppvOut);
  if ( ppvOut )
  {
    memset(&pvar, 0, sizeof(pvar));
    v6 = -2147467259;
    v7 = ILGetSize(pv);
    if ( InitVariantFromBuffer(pv, v7, &pvar) >= 0 )
    {
      v13 = 0;
      v12 = 0;
      if ( !a3 )
      {
        DWORD2(v12) = 2;
        LOWORD(v12) = 3;
      }
      v8 = (__int64 *)&v12;
      if ( a3 )
        v8 = qword_18002BF48;
      v6 = (*(__int64 (__fastcall **)(void *, VARIANT *, __int64 *))(*(_QWORD *)ppvOut + 416LL))(ppvOut, &pvar, v8);
      VariantClear(&pvar);
    }
    (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 16LL))(ppvOut, *(_QWORD *)ppvOut);
  }
  else
  {
    v11 = 0;
    v6 = IUnknown_QueryService(punk, (const GUID *const)&SID_SCommDlgBrowser, &IID_IShellBrowser, &v11);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(void *, const struct _ITEMIDLIST *, _QWORD))(*(_QWORD *)v11 + 88LL))(v11, pv, 0);
      (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v11 + 16LL))(v11, v9);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800248ac  push    rbp
0x1800248ae  push    rbx
0x1800248af  push    rsi
0x1800248b0  push    rdi
0x1800248b1  lea     rbp, [rsp-3Fh]
0x1800248b6  sub     rsp, 88h
0x1800248bd  mov     esi, r8d
0x1800248c0  mov     [rbp+57h+ppvOut], 0
0x1800248c8  mov     rdi, rdx
0x1800248cb  lea     r8, IID_IWebBrowser2; riid
0x1800248d2  lea     rdx, IID_IWebBrowserApp; guidService
0x1800248d9  mov     rbx, rcx
0x1800248dc  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1800248e0  call    cs:__imp_IUnknown_QueryService
0x1800248e6  cmp     [rbp+57h+ppvOut], 0
0x1800248eb  jz      loc_180024989
0x1800248f1  xorps   xmm0, xmm0
0x1800248f4  xor     eax, eax
0x1800248f6  mov     rcx, rdi; pidl
0x1800248f9  mov     qword ptr [rbp+57h+pvar+10h], rax
0x1800248fd  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180024901  mov     ebx, 80004005h
0x180024906  call    cs:__imp_ILGetSize
0x18002490c  lea     r8, [rbp+57h+pvar]; pvar
0x180024910  mov     rcx, rdi; pv
0x180024913  mov     edx, eax; cb
0x180024915  call    cs:__imp_InitVariantFromBuffer
0x18002491b  test    eax, eax
0x18002491d  js      short loc_18002497C
0x18002491f  xor     eax, eax
0x180024921  xorps   xmm0, xmm0
0x180024924  mov     [rbp+57h+var_48], rax
0x180024928  movups  [rbp+57h+var_58], xmm0
0x18002492c  test    esi, esi
0x18002492e  jnz     short loc_18002493E
0x180024930  lea     eax, [rsi+3]
0x180024933  mov     dword ptr [rbp+57h+var_58+8], 2
0x18002493a  mov     word ptr [rbp+57h+var_58], ax
0x18002493e  mov     rcx, [rbp+57h+ppvOut]
0x180024942  lea     r9, qword_18002BF48
0x180024949  mov     [rsp+0A0h+var_78], r9
0x18002494e  lea     r8, [rbp+57h+var_58]
0x180024952  test    esi, esi
0x180024954  mov     [rsp+0A0h+var_80], r9
0x180024959  lea     rdx, [rbp+57h+pvar]
0x18002495d  mov     rax, [rcx]
0x180024960  cmovnz  r8, r9
0x180024964  mov     rax, [rax+1A0h]
0x18002496b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024970  lea     rcx, [rbp+57h+pvar]; pvarg
0x180024974  mov     ebx, eax
0x180024976  call    cs:__imp_VariantClear
0x18002497c  mov     rcx, [rbp+57h+ppvOut]
0x180024980  mov     rdx, [rcx]
0x180024983  mov     rax, [rdx+10h]
0x180024987  jmp     short loc_1800249D5
0x180024989  lea     r9, [rbp+57h+var_60]; ppvOut
0x18002498d  mov     [rbp+57h+var_60], 0
0x180024995  lea     r8, IID_IShellBrowser; riid
0x18002499c  mov     rcx, rbx; punk
0x18002499f  lea     rdx, SID_SCommDlgBrowser; guidService
0x1800249a6  call    cs:__imp_IUnknown_QueryService
0x1800249ac  mov     ebx, eax
0x1800249ae  test    eax, eax
0x1800249b0  js      short loc_1800249DA
0x1800249b2  mov     rcx, [rbp+57h+var_60]
0x1800249b6  xor     r8d, r8d
0x1800249b9  mov     rdx, rdi
0x1800249bc  mov     rax, [rcx]
0x1800249bf  mov     rax, [rax+58h]
0x1800249c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249c8  mov     rcx, [rbp+57h+var_60]
0x1800249cc  mov     ebx, eax
0x1800249ce  mov     rax, [rcx]
0x1800249d1  mov     rax, [rax+10h]
0x1800249d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249da  mov     eax, ebx
0x1800249dc  add     rsp, 88h
0x1800249e3  pop     rdi
0x1800249e4  pop     rsi
0x1800249e5  pop     rbx
0x1800249e6  pop     rbp
0x1800249e7  retn
```
