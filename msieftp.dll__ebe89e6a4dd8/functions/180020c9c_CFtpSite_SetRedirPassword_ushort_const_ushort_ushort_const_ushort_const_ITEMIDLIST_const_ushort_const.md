# CFtpSite::_SetRedirPassword(ushort const *,ushort,ushort const *,ushort const *,_ITEMIDLIST const *,ushort const *)

- ea: `0x180020c9c`
- end: `0x180020e01`
- name: `?_SetRedirPassword@CFtpSite@@AEAAJPEBGG00PEFBU_ITEMIDLIST@@0@Z`
- size: `357`
- prototype: `__int64 __fastcall(CFtpSite *__hidden this, const unsigned __int16 *, unsigned __int16, const unsigned __int16 *, LPCWSTR psz, LPCITEMIDLIST pidl2, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800207b8`

## callees

- `0x180002240`
- `0x18001b91c`
- `0x18001fdb0`
- `0x180020c9c`
- `0x180021714`
- `0x180026f48`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180020d78`
- `SHELL32!__imp_ILCombine` at `0x180020d78`
- `SHELL32!__imp_ILFree` at `0x180020dcb`
- `SHELL32!__imp_ILFree` at `0x180020dd6`
- `SHELL32!__imp_ILFree` at `0x180020dcb`
- `SHELL32!__imp_ILFree` at `0x180020dd6`

## pseudocode

```c
__int64 __fastcall CFtpSite::_SetRedirPassword(
        CFtpSite *this,
        WCHAR *a2,
        INTERNET_PORT a3,
        WCHAR *a4,
        LPCWSTR psz,
        LPCITEMIDLIST pidl2,
        unsigned __int16 *a7)
{
  int v8; // edi
  unsigned int v9; // edx
  const struct _ITEMIDLIST *v10; // rax
  ITEMIDLIST *v11; // rsi
  struct IMalloc *v12; // r8
  struct CFtpSite *v13; // rbx
  unsigned __int16 *v15; // [rsp+20h] [rbp-10B8h]
  const unsigned __int16 *v16; // [rsp+30h] [rbp-10A8h]
  LPCITEMIDLIST pidl1; // [rsp+50h] [rbp-1088h] BYREF
  struct CFtpSite *v18; // [rsp+58h] [rbp-1080h] BYREF
  WCHAR szUrl[2088]; // [rsp+60h] [rbp-1078h] BYREF

  v8 = UrlCreateEx(a2, a4, (WCHAR *)&lParam, (WCHAR *)&lParam, a7, a3, v16, szUrl, 0x824u, 0x80000000);
  if ( v8 >= 0 )
  {
    v9 = *((_DWORD *)this + 49);
    v15 = (unsigned __int16 *)*((_QWORD *)this + 7);
    pidl1 = 0;
    v8 = CreateFtpPidlFromUrlEx(szUrl, v9, 0, &pidl1, (struct IMalloc *)v15, 1, 0, 0);
    if ( v8 >= 0 )
    {
      v10 = ILCombine(pidl1, pidl2);
      v11 = (ITEMIDLIST *)v10;
      if ( v10 )
      {
        v12 = (struct IMalloc *)*((_QWORD *)this + 7);
        v18 = 0;
        v8 = SiteCache_PidlLookup(v10, 0, v12, &v18);
        if ( v8 >= 0 )
        {
          v13 = v18;
          Str_SetPtrW((LPWSTR *)v18 + 14, psz);
          (*(void (__fastcall **)(struct CFtpSite *))(*(_QWORD *)v13 + 16LL))(v13);
        }
        ILFree(v11);
      }
      ILFree((LPITEMIDLIST)pidl1);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180020c9c  mov     [rsp+arg_10], rbx
0x180020ca1  push    rbp
0x180020ca2  push    rsi
0x180020ca3  push    rdi
0x180020ca4  mov     eax, 10C0h
0x180020ca9  call    _alloca_probe
0x180020cae  sub     rsp, rax
0x180020cb1  mov     rax, cs:__security_cookie
0x180020cb8  xor     rax, rsp
0x180020cbb  mov     [rsp+10D8h+var_28], rax
0x180020cc3  mov     rax, [rsp+10D8h+arg_30]
0x180020ccb  mov     rbx, rcx
0x180020cce  mov     rbp, [rsp+10D8h+psz]
0x180020cd6  lea     rcx, [rsp+10D8h+szUrl]
0x180020cdb  mov     rsi, [rsp+10D8h+pidl2]
0x180020ce3  mov     r11, r9
0x180020ce6  mov     [rsp+10D8h+var_1090], 80000000h; unsigned int
0x180020cee  mov     r10, rdx
0x180020cf1  mov     [rsp+10D8h+dwUrlLength], 824h; dwUrlLength
0x180020cf9  mov     rdx, r11; unsigned __int16 *
0x180020cfc  mov     [rsp+10D8h+lpszUrl], rcx; lpszUrl
0x180020d01  mov     rcx, r10; unsigned __int16 *
0x180020d04  mov     [rsp+10D8h+var_10B0], r8w; unsigned __int16
0x180020d0a  lea     r8, lParam; unsigned __int16 *
0x180020d11  mov     r9, r8; unsigned __int16 *
0x180020d14  mov     [rsp+10D8h+var_10B8], rax; unsigned __int16 *
0x180020d19  call    ?UrlCreateEx@@YAJPEBG0000G0PEAGKK@Z; UrlCreateEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort,ushort const *,ushort *,ulong,ulong)
0x180020d1e  mov     edi, eax
0x180020d20  test    eax, eax
0x180020d22  js      loc_180020DDC
0x180020d28  mov     rax, [rbx+38h]
0x180020d2c  lea     r9, [rsp+10D8h+pidl1]
0x180020d31  mov     edx, [rbx+0C4h]
0x180020d37  lea     rcx, [rsp+10D8h+szUrl]
0x180020d3c  mov     dword ptr [rsp+10D8h+lpszUrl], 0
0x180020d44  xor     r8d, r8d
0x180020d47  mov     dword ptr [rsp+10D8h+var_10A8], 0
0x180020d4f  mov     dword ptr [rsp+10D8h+var_10B0], 1
0x180020d57  mov     [rsp+10D8h+var_10B8], rax
0x180020d5c  mov     [rsp+10D8h+pidl1], 0
0x180020d65  call    ?CreateFtpPidlFromUrlEx@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@HHH@Z; CreateFtpPidlFromUrlEx(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,IMalloc *,int,int,int)
0x180020d6a  mov     edi, eax
0x180020d6c  test    eax, eax
0x180020d6e  js      short loc_180020DDC
0x180020d70  mov     rcx, [rsp+10D8h+pidl1]; pidl1
0x180020d75  mov     rdx, rsi; pidl2
0x180020d78  call    cs:__imp_ILCombine
0x180020d7e  mov     rsi, rax
0x180020d81  test    rax, rax
0x180020d84  jz      short loc_180020DD1
0x180020d86  mov     r8, [rbx+38h]; struct IMalloc *
0x180020d8a  lea     r9, [rsp+10D8h+var_1080]; struct CFtpSite **
0x180020d8f  xor     edx, edx; int
0x180020d91  mov     [rsp+10D8h+var_1080], 0
0x180020d9a  mov     rcx, rax; struct _ITEMIDLIST *
0x180020d9d  call    ?SiteCache_PidlLookup@@YAJPEFBU_ITEMIDLIST@@HPEAUIMalloc@@PEAPEAVCFtpSite@@@Z; SiteCache_PidlLookup(_ITEMIDLIST const *,int,IMalloc *,CFtpSite * *)
0x180020da2  mov     edi, eax
0x180020da4  test    eax, eax
0x180020da6  js      short loc_180020DC8
0x180020da8  mov     rbx, [rsp+10D8h+var_1080]
0x180020dad  mov     rdx, rbp; psz
0x180020db0  lea     rcx, [rbx+70h]; ppsz
0x180020db4  call    Str_SetPtrW
0x180020db9  mov     rax, [rbx]
0x180020dbc  mov     rcx, rbx
0x180020dbf  mov     rax, [rax+10h]
0x180020dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dc8  mov     rcx, rsi; pidl
0x180020dcb  call    cs:__imp_ILFree
0x180020dd1  mov     rcx, [rsp+10D8h+pidl1]; pidl
0x180020dd6  call    cs:__imp_ILFree
0x180020ddc  mov     eax, edi
0x180020dde  mov     rcx, [rsp+10D8h+var_28]
0x180020de6  xor     rcx, rsp; StackCookie
0x180020de9  call    __security_check_cookie
0x180020dee  mov     rbx, [rsp+10D8h+arg_10]
0x180020df6  add     rsp, 10C0h
0x180020dfd  pop     rdi
0x180020dfe  pop     rsi
0x180020dff  pop     rbp
0x180020e00  retn
```
