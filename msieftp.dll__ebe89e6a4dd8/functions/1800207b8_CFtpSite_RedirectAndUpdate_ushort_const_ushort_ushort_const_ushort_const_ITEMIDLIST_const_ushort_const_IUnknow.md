# CFtpSite::_RedirectAndUpdate(ushort const *,ushort,ushort const *,ushort const *,_ITEMIDLIST const *,ushort const *,IUnknown *,CFtpFolder *)

- ea: `0x1800207b8`
- end: `0x180020a46`
- name: `?_RedirectAndUpdate@CFtpSite@@IEAAJPEBGG00PEFBU_ITEMIDLIST@@0PEAUIUnknown@@PEAVCFtpFolder@@@Z`
- size: `654`
- prototype: `__int64 __fastcall(CFtpSite *__hidden this, const unsigned __int16 *, unsigned __int16, const unsigned __int16 *, PCWSTR psz, LPCITEMIDLIST pidl2, const unsigned __int16 *, struct IUnknown *, struct CFtpFolder *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800201c4`

## callees

- `0x180002240`
- `0x18001b91c`
- `0x18001fdb0`
- `0x1800207b8`
- `0x180020c9c`
- `0x180021714`
- `0x180021b08`
- `0x1800249f0`
- `0x180026f48`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180020908`
- `SHELL32!__imp_ILCombine` at `0x180020908`
- `SHELL32!__imp_ILFree` at `0x1800209f9`
- `SHELL32!__imp_ILFree` at `0x180020a09`
- `SHELL32!__imp_ILFree` at `0x180020a14`
- `SHELL32!__imp_ILFree` at `0x1800209f9`
- `SHELL32!__imp_ILFree` at `0x180020a09`
- `SHELL32!__imp_ILFree` at `0x180020a14`
- `SHLWAPI!StrCmpW` at `0x180020928`
- `SHLWAPI!StrCmpW` at `0x180020939`
- `SHLWAPI!StrCmpW` at `0x180020979`
- `SHLWAPI!StrCmpW` at `0x180020928`
- `SHLWAPI!StrCmpW` at `0x180020939`
- `SHLWAPI!StrCmpW` at `0x180020979`

## pseudocode

```c
__int64 __fastcall CFtpSite::_RedirectAndUpdate(
        CFtpSite *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        WCHAR *a4,
        PCWSTR psz,
        LPCITEMIDLIST pidl2,
        unsigned __int16 *a7,
        struct IUnknown *a8,
        struct CFtpFolder *a9)
{
  __int64 v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // rdx
  WCHAR *v16; // rcx
  int v17; // ebx
  unsigned int v18; // edx
  LPITEMIDLIST v19; // rsi
  const WCHAR *v20; // rcx
  const WCHAR *v21; // rcx
  struct IMalloc *v22; // r8
  struct CFtpSite *v23; // rbx
  const struct _ITEMIDLIST *FullPublicPidl; // rax
  ITEMIDLIST *v25; // rbx
  int v26; // edi
  struct IMalloc *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v28; // [rsp+30h] [rbp-D0h]
  struct CFtpSite *v29; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+58h] [rbp-A8h] BYREF
  CBaseFolder *v31; // [rsp+60h] [rbp-A0h]
  IUnknown *punk; // [rsp+68h] [rbp-98h]
  WCHAR psz2[128]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR szUrl[2088]; // [rsp+170h] [rbp+70h] BYREF

  punk = a8;
  v29 = (struct CFtpSite *)a7;
  v31 = a9;
  if ( !a9 )
    return 2147500037LL;
  v13 = 2147483646;
  v14 = psz2;
  v15 = 128;
  do
  {
    if ( !v13 )
      break;
    if ( !*a4 )
      break;
    *v14++ = *a4++;
    --v13;
    --v15;
  }
  while ( v15 );
  v16 = v14 - 1;
  if ( v15 )
    v16 = v14;
  *v16 = 0;
  v17 = UrlCreateEx(a2, psz2, psz, &lParam, a7, a3, v28, szUrl, 0x824u, 0x80000000);
  if ( v17 >= 0 )
  {
    v18 = *((_DWORD *)this + 49);
    v27 = (struct IMalloc *)*((_QWORD *)this + 7);
    pidl1 = 0;
    v17 = CreateFtpPidlFromUrlEx(szUrl, v18, 0, &pidl1, v27, 1, 0, 0);
    if ( v17 >= 0 )
    {
      v19 = ILCombine(pidl1, pidl2);
      if ( v19 )
      {
        v20 = (const WCHAR *)*((_QWORD *)this + 10);
        if ( v20 && !StrCmpW(v20, psz2) && StrCmpW(*((PCWSTR *)this + 11), psz) )
          CFtpSite::_SetRedirPassword(this, a2, a3, psz2, psz, pidl2, (const unsigned __int16 *)v29);
        v21 = (const WCHAR *)*((_QWORD *)this + 10);
        if ( !v21 || StrCmpW(v21, psz2) )
        {
          v22 = (struct IMalloc *)*((_QWORD *)this + 7);
          v29 = 0;
          v17 = SiteCache_PidlLookup(v19, 0, v22, &v29);
          if ( v17 >= 0 )
          {
            v23 = v29;
            Str_SetPtrW((LPWSTR *)v29 + 14, psz);
            (*(void (__fastcall **)(struct CFtpSite *))(*(_QWORD *)v23 + 16LL))(v23);
            FullPublicPidl = CBaseFolder::CreateFullPublicPidl((LPCITEMIDLIST *)v31, v19);
            v25 = (ITEMIDLIST *)FullPublicPidl;
            v26 = -2147024809;
            if ( FullPublicPidl )
            {
              v26 = IUnknown_PidlNavigate(punk, FullPublicPidl, 0);
              ILFree(v25);
            }
            v17 = 0;
            if ( v26 < 0 )
              v17 = v26;
          }
        }
        else
        {
          v17 = 1;
        }
        ILFree(v19);
      }
      ILFree((LPITEMIDLIST)pidl1);
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800207b8  mov     [rsp-8+arg_10], rbx
0x1800207bd  push    rbp
0x1800207be  push    rsi
0x1800207bf  push    rdi
0x1800207c0  push    r12
0x1800207c2  push    r13
0x1800207c4  push    r14
0x1800207c6  push    r15
0x1800207c8  lea     rbp, [rsp-10D0h]
0x1800207d0  mov     eax, 11D0h
0x1800207d5  call    _alloca_probe
0x1800207da  sub     rsp, rax
0x1800207dd  mov     rax, cs:__security_cookie
0x1800207e4  xor     rax, rsp
0x1800207e7  mov     [rbp+1100h+var_40], rax
0x1800207ee  mov     rax, [rbp+1100h+arg_38]
0x1800207f5  xor     esi, esi
0x1800207f7  mov     r10, [rbp+1100h+arg_30]
0x1800207fe  movzx   r12d, r8w
0x180020802  mov     r14, [rbp+1100h+psz]
0x180020809  mov     r13, rdx
0x18002080c  mov     r15, [rbp+1100h+pidl2]
0x180020813  mov     rdi, rcx
0x180020816  mov     [rsp+1200h+punk], rax
0x18002081b  mov     rax, [rbp+1100h+arg_40]
0x180020822  mov     [rsp+1200h+var_11B0], r10
0x180020827  mov     [rsp+1200h+var_11A0], rax
0x18002082c  test    rax, rax
0x18002082f  jnz     short loc_18002083B
0x180020831  mov     eax, 80004005h
0x180020836  jmp     loc_180020A1C
0x18002083b  mov     ecx, 7FFFFFFEh
0x180020840  lea     rax, [rsp+1200h+psz2]
0x180020845  mov     edx, 80h
0x18002084a  test    rcx, rcx
0x18002084d  jz      short loc_18002086E
0x18002084f  movzx   r8d, word ptr [r9]
0x180020853  test    r8w, r8w
0x180020857  jz      short loc_18002086E
0x180020859  mov     [rax], r8w
0x18002085d  add     r9, 2
0x180020861  add     rax, 2
0x180020865  dec     rcx
0x180020868  sub     rdx, 1
0x18002086c  jnz     short loc_18002084A
0x18002086e  mov     [rsp+1200h+var_11B8], 80000000h; unsigned int
0x180020876  lea     rcx, [rax-2]
0x18002087a  test    rdx, rdx
0x18002087d  mov     [rsp+1200h+dwUrlLength], 824h; dwUrlLength
0x180020885  lea     r9, lParam; unsigned __int16 *
0x18002088c  mov     r8, r14; unsigned __int16 *
0x18002088f  cmovnz  rcx, rax
0x180020893  lea     rdx, [rsp+1200h+psz2]; unsigned __int16 *
0x180020898  lea     rax, [rbp+1100h+szUrl]
0x18002089c  mov     [rsp+1200h+lpszUrl], rax; lpszUrl
0x1800208a1  mov     word ptr [rsp+1200h+var_11D8], r12w; unsigned __int16
0x1800208a7  mov     [rcx], si
0x1800208aa  mov     rcx, r13; unsigned __int16 *
0x1800208ad  mov     [rsp+1200h+var_11E0], r10; unsigned __int16 *
0x1800208b2  call    ?UrlCreateEx@@YAJPEBG0000G0PEAGKK@Z; UrlCreateEx(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort,ushort const *,ushort *,ulong,ulong)
0x1800208b7  mov     ebx, eax
0x1800208b9  test    eax, eax
0x1800208bb  js      loc_180020A1A
0x1800208c1  mov     rax, [rdi+38h]
0x1800208c5  lea     r9, [rsp+1200h+pidl1]
0x1800208ca  mov     edx, [rdi+0C4h]
0x1800208d0  lea     rcx, [rbp+1100h+szUrl]
0x1800208d4  mov     dword ptr [rsp+1200h+lpszUrl], esi
0x1800208d8  xor     r8d, r8d
0x1800208db  mov     dword ptr [rsp+1200h+var_11D0], esi
0x1800208df  mov     dword ptr [rsp+1200h+var_11D8], 1
0x1800208e7  mov     [rsp+1200h+var_11E0], rax
0x1800208ec  mov     [rsp+1200h+pidl1], rsi
0x1800208f1  call    ?CreateFtpPidlFromUrlEx@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@HHH@Z; CreateFtpPidlFromUrlEx(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,IMalloc *,int,int,int)
0x1800208f6  mov     ebx, eax
0x1800208f8  test    eax, eax
0x1800208fa  js      loc_180020A1A
0x180020900  mov     rcx, [rsp+1200h+pidl1]; pidl1
0x180020905  mov     rdx, r15; pidl2
0x180020908  call    cs:__imp_ILCombine
0x18002090e  mov     rsi, rax
0x180020911  test    rax, rax
0x180020914  jz      loc_180020A0F
0x18002091a  mov     rcx, [rdi+50h]; psz1
0x18002091e  test    rcx, rcx
0x180020921  jz      short loc_18002096B
0x180020923  lea     rdx, [rsp+1200h+psz2]; psz2
0x180020928  call    cs:__imp_StrCmpW
0x18002092e  test    eax, eax
0x180020930  jnz     short loc_18002096B
0x180020932  mov     rcx, [rdi+58h]; psz1
0x180020936  mov     rdx, r14; psz2
0x180020939  call    cs:__imp_StrCmpW
0x18002093f  test    eax, eax
0x180020941  jz      short loc_18002096B
0x180020943  mov     rax, [rsp+1200h+var_11B0]
0x180020948  lea     r9, [rsp+1200h+psz2]; unsigned __int16 *
0x18002094d  mov     [rsp+1200h+var_11D0], rax; unsigned __int16 *
0x180020952  movzx   r8d, r12w; unsigned __int16
0x180020956  mov     [rsp+1200h+var_11D8], r15; pidl2
0x18002095b  mov     rdx, r13; unsigned __int16 *
0x18002095e  mov     rcx, rdi; this
0x180020961  mov     [rsp+1200h+var_11E0], r14; psz
0x180020966  call    ?_SetRedirPassword@CFtpSite@@AEAAJPEBGG00PEFBU_ITEMIDLIST@@0@Z; CFtpSite::_SetRedirPassword(ushort const *,ushort,ushort const *,ushort const *,_ITEMIDLIST const *,ushort const *)
0x18002096b  mov     rcx, [rdi+50h]; psz1
0x18002096f  test    rcx, rcx
0x180020972  jz      short loc_180020988
0x180020974  lea     rdx, [rsp+1200h+psz2]; psz2
0x180020979  call    cs:__imp_StrCmpW
0x18002097f  test    eax, eax
0x180020981  jnz     short loc_180020988
0x180020983  lea     ebx, [rax+1]
0x180020986  jmp     short loc_180020A06
0x180020988  mov     r8, [rdi+38h]; struct IMalloc *
0x18002098c  lea     r9, [rsp+1200h+var_11B0]; struct CFtpSite **
0x180020991  xor     edx, edx; int
0x180020993  mov     [rsp+1200h+var_11B0], 0
0x18002099c  mov     rcx, rsi; struct _ITEMIDLIST *
0x18002099f  call    ?SiteCache_PidlLookup@@YAJPEFBU_ITEMIDLIST@@HPEAUIMalloc@@PEAPEAVCFtpSite@@@Z; SiteCache_PidlLookup(_ITEMIDLIST const *,int,IMalloc *,CFtpSite * *)
0x1800209a4  mov     ebx, eax
0x1800209a6  test    eax, eax
0x1800209a8  js      short loc_180020A06
0x1800209aa  mov     rbx, [rsp+1200h+var_11B0]
0x1800209af  mov     rdx, r14; psz
0x1800209b2  lea     rcx, [rbx+70h]; ppsz
0x1800209b6  call    Str_SetPtrW
0x1800209bb  mov     rax, [rbx]
0x1800209be  mov     rcx, rbx
0x1800209c1  mov     rax, [rax+10h]
0x1800209c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209ca  mov     rcx, [rsp+1200h+var_11A0]; this
0x1800209cf  mov     rdx, rsi; struct _ITEMIDLIST *
0x1800209d2  call    ?CreateFullPublicPidl@CBaseFolder@@QEAAPEFAU_ITEMIDLIST@@PEFBU2@@Z; CBaseFolder::CreateFullPublicPidl(_ITEMIDLIST const *)
0x1800209d7  mov     rbx, rax
0x1800209da  mov     edi, 80070057h
0x1800209df  test    rax, rax
0x1800209e2  jz      short loc_1800209FF
0x1800209e4  mov     rcx, [rsp+1200h+punk]; punk
0x1800209e9  xor     r8d, r8d; int
0x1800209ec  mov     rdx, rax; pv
0x1800209ef  call    ?IUnknown_PidlNavigate@@YAJPEAUIUnknown@@PEFBU_ITEMIDLIST@@H@Z; IUnknown_PidlNavigate(IUnknown *,_ITEMIDLIST const *,int)
0x1800209f4  mov     rcx, rbx; pidl
0x1800209f7  mov     edi, eax
0x1800209f9  call    cs:__imp_ILFree
0x1800209ff  xor     ebx, ebx
0x180020a01  test    edi, edi
0x180020a03  cmovs   ebx, edi
0x180020a06  mov     rcx, rsi; pidl
0x180020a09  call    cs:__imp_ILFree
0x180020a0f  mov     rcx, [rsp+1200h+pidl1]; pidl
0x180020a14  call    cs:__imp_ILFree
0x180020a1a  mov     eax, ebx
0x180020a1c  mov     rcx, [rbp+1100h+var_40]
0x180020a23  xor     rcx, rsp; StackCookie
0x180020a26  call    __security_check_cookie
0x180020a2b  mov     rbx, [rsp+1200h+arg_10]
0x180020a33  add     rsp, 11D0h
0x180020a3a  pop     r15
0x180020a3c  pop     r14
0x180020a3e  pop     r13
0x180020a40  pop     r12
0x180020a42  pop     rdi
0x180020a43  pop     rsi
0x180020a44  pop     rbp
0x180020a45  retn
```
