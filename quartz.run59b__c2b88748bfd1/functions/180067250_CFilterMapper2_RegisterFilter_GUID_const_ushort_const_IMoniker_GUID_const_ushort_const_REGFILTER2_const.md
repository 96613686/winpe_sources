# CFilterMapper2::RegisterFilter(_GUID const &,ushort const *,IMoniker * *,_GUID const *,ushort const *,REGFILTER2 const *)

- ea: `0x180067250`
- end: `0x180067738`
- name: `?RegisterFilter@CFilterMapper2@@EEAAJAEBU_GUID@@PEBGPEAPEAUIMoniker@@PEBU2@1PEBUREGFILTER2@@@Z`
- size: `1256`
- prototype: `int(CFilterMapper2 *__hidden this, const struct _GUID *, const unsigned __int16 *, struct IMoniker **, const struct _GUID *, const unsigned __int16 *, const struct REGFILTER2 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800078b0`
- `0x18002d8c0`
- `0x180038498`
- `0x1800384a4`
- `0x1800388a0`
- `0x180058e08`
- `0x180065b20`
- `0x180067250`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800676ff`
- `KERNEL32!LeaveCriticalSection` at `0x1800676ff`
- `KERNEL32!EnterCriticalSection` at `0x1800672c4`
- `KERNEL32!EnterCriticalSection` at `0x1800672c4`
- `ole32!CreateBindCtx` at `0x18006736e`
- `ole32!CreateBindCtx` at `0x18006736e`
- `ole32!StringFromGUID2` at `0x1800672fd`
- `ole32!StringFromGUID2` at `0x180067331`
- `ole32!StringFromGUID2` at `0x18006734a`
- `ole32!StringFromGUID2` at `0x1800672fd`
- `ole32!StringFromGUID2` at `0x180067331`
- `ole32!StringFromGUID2` at `0x18006734a`
- `ole32!CoCreateInstance` at `0x180067404`
- `ole32!CoCreateInstance` at `0x180067404`
- `OLEAUT32!__imp_SysAllocString` at `0x1800674df`
- `OLEAUT32!__imp_SysAllocString` at `0x18006754a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800674df`
- `OLEAUT32!__imp_SysAllocString` at `0x18006754a`
- `OLEAUT32!__imp_SysFreeString` at `0x180067517`
- `OLEAUT32!__imp_SysFreeString` at `0x180067588`
- `OLEAUT32!__imp_SysFreeString` at `0x180067517`
- `OLEAUT32!__imp_SysFreeString` at `0x180067588`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180067632`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180067632`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800676a6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800676a6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180067655`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180067655`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180067695`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180067695`

## string_xrefs

- `0x18006756e`: `CLSID`

## pseudocode

```c
__int64 __fastcall CFilterMapper2::RegisterFilter(
        CFilterMapper2 *this,
        const struct _GUID *a2,
        OLECHAR *a3,
        struct IMoniker **a4,
        struct _GUID *a5,
        unsigned __int16 *a6,
        const struct REGFILTER2 *a7)
{
  GUID *v8; // rdi
  OLECHAR *v10; // r14
  struct _RTL_CRITICAL_SECTION *v12; // r12
  CFilterMapper2 *v13; // rcx
  struct IMoniker *v14; // rbx
  BOOL v15; // esi
  bool v16; // zf
  HRESULT v17; // ebx
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rdi
  int v20; // ebx
  unsigned __int8 *v21; // rax
  unsigned __int8 *v22; // rdi
  unsigned int v23; // ebx
  SAFEARRAY *v24; // rax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  LPBC ppbc; // [rsp+40h] [rbp-C0h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp-B8h] BYREF
  struct IMoniker *v29; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v30[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h]
  OLECHAR *psz; // [rsp+70h] [rbp-90h]
  BSTR bstrString[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h]
  OLECHAR sz[40]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR v36[40]; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR v37[40]; // [rsp+130h] [rbp+30h] BYREF

  v8 = a5;
  v10 = a6;
  rgsabound = (SAFEARRAYBOUND)a7;
  psz = a3;
  if ( !a3 )
    return 2147500035LL;
  v12 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 48) & -(__int64)(this != 0));
  EnterCriticalSection(v12);
  CFilterMapper2::BreakCacheIfNotBuildingCache(v13);
  v14 = 0;
  v15 = 0;
  if ( a4 )
  {
    v14 = *a4;
    v16 = *a4 == 0;
    *a4 = 0;
    v15 = v16;
  }
  if ( !a6 )
  {
    StringFromGUID2(a2, sz, 39);
    v10 = sz;
  }
  v29 = 0;
  if ( !a5 )
    v8 = &CLSID_LegacyAmFilterCategory;
  StringFromGUID2(v8, v36, 39);
  StringFromGUID2(a2, v37, 39);
  if ( v14 )
  {
    v29 = v14;
    ((void (__fastcall *)(struct IMoniker *))v14->lpVtbl->AddRef)(v14);
  }
  else
  {
    ppbc = 0;
    v17 = CreateBindCtx(0, &ppbc);
    if ( v17 < 0 )
      goto LABEL_39;
    v18 = (unsigned __int16 *)operator new[](0x8000u);
    v19 = v18;
    if ( v18 )
    {
      StringCchCopyW(v18, 0x4000u, L"@device:sw:");
      StringCchCatW(v19, 0x4000u, v36);
      StringCchCatW(v19, 0x4000u, L"\\");
      StringCchCatW(v19, 0x4000u, v10);
      LODWORD(Size) = 0;
      ppv = 0;
      v17 = CoCreateInstance(&CLSID_CDeviceMoniker, 0, 1u, &IID_IParseDisplayName, &ppv);
      if ( v17 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(LPVOID, LPBC, unsigned __int16 *, size_t *, struct IMoniker **))(*(_QWORD *)ppv + 24LL))(
                ppv,
                ppbc,
                v19,
                &Size,
                &v29);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      operator delete(v19);
    }
    else
    {
      v17 = -2147024882;
    }
    if ( v17 < 0 )
      goto LABEL_39;
  }
  ppv = 0;
  v17 = ((__int64 (__fastcall *)(struct IMoniker *, _QWORD, _QWORD, GUID *, LPVOID *))v29->lpVtbl->BindToStorage)(
          v29,
          0,
          0,
          &IID_IPropertyBag,
          &ppv);
  if ( v17 >= 0 )
  {
    v34 = 0;
    *(_OWORD *)bstrString = 0;
    LOWORD(bstrString[0]) = 8;
    bstrString[1] = SysAllocString(psz);
    if ( bstrString[1] )
    {
      v17 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, BSTR *))(*(_QWORD *)ppv + 32LL))(
              ppv,
              L"FriendlyName",
              bstrString);
      SysFreeString(bstrString[1]);
    }
    else
    {
      v17 = -2147024882;
    }
    if ( v17 >= 0 )
    {
      *(_OWORD *)v30 = 0;
      LOWORD(v30[0]) = 8;
      v31 = 0;
      v30[1] = SysAllocString(v37);
      if ( !v30[1] )
      {
LABEL_33:
        v17 = -2147024882;
        goto LABEL_34;
      }
      v17 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, BSTR *))(*(_QWORD *)ppv + 32LL))(
              ppv,
              L"CLSID",
              v30);
      SysFreeString(v30[1]);
      if ( v17 >= 0 )
      {
        LODWORD(Size) = 0;
        v17 = RegSquish(0, (const struct REGFILTER2 **)&rgsabound, (unsigned int *)&Size, 1);
        if ( v17 >= 0 )
        {
          v20 = Size;
          v21 = (unsigned __int8 *)operator new[]((unsigned int)Size);
          v22 = v21;
          if ( v21 )
          {
            LODWORD(Size) = v20;
            v17 = RegSquish(v21, (const struct REGFILTER2 **)&rgsabound, (unsigned int *)&Size, 1);
            if ( !v17 )
            {
              v23 = Size;
              rgsabound.lLbound = 0;
              v31 = 0;
              rgsabound.cElements = Size;
              *(_OWORD *)v30 = 0;
              LOWORD(v30[0]) = 8209;
              v24 = SafeArrayCreate(0x11u, 1u, &rgsabound);
              v30[1] = &v24->cDims;
              if ( v24 )
              {
                ppbc = 0;
                SafeArrayAccessData(v24, (void **)&ppbc);
                memcpy_0(ppbc, v22, v23);
                v17 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, BSTR *))(*(_QWORD *)ppv + 32LL))(
                        ppv,
                        L"FilterData",
                        v30);
                SafeArrayUnaccessData((SAFEARRAY *)v30[1]);
                SafeArrayDestroy((SAFEARRAY *)v30[1]);
              }
              else
              {
                v17 = -2147024882;
              }
            }
            operator delete(v22);
            goto LABEL_34;
          }
          goto LABEL_33;
        }
      }
    }
  }
LABEL_34:
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v17 >= 0 && v29 )
  {
    if ( v15 )
      *a4 = v29;
    else
      ((void (*)(void))v29->lpVtbl->Release)();
  }
LABEL_39:
  LeaveCriticalSection(v12);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180067250  mov     [rsp-8+arg_0], rbx
0x180067255  push    rbp
0x180067256  push    rsi
0x180067257  push    rdi
0x180067258  push    r12
0x18006725a  push    r13
0x18006725c  push    r14
0x18006725e  push    r15
0x180067260  lea     rbp, [rsp-90h]
0x180067268  sub     rsp, 190h
0x18006726f  mov     rax, cs:__security_cookie
0x180067276  xor     rax, rsp
0x180067279  mov     [rbp+0C0h+var_40], rax
0x180067280  mov     rax, [rbp+0C0h+arg_30]
0x180067287  mov     r15, r9
0x18006728a  mov     rdi, [rbp+0C0h+arg_20]
0x180067291  mov     r13, rdx
0x180067294  mov     r14, [rbp+0C0h+arg_28]
0x18006729b  mov     qword ptr [rsp+1C0h+rgsabound.cElements], rax
0x1800672a0  mov     [rsp+1C0h+psz], r8
0x1800672a5  test    r8, r8
0x1800672a8  jnz     short loc_1800672B4
0x1800672aa  mov     eax, 80004003h
0x1800672af  jmp     loc_18006770D
0x1800672b4  lea     rax, [rcx+30h]
0x1800672b8  neg     rcx
0x1800672bb  sbb     r12, r12
0x1800672be  and     r12, rax
0x1800672c1  mov     rcx, r12; lpCriticalSection
0x1800672c4  call    cs:__imp_EnterCriticalSection
0x1800672cb  nop     dword ptr [rax+rax+00h]
0x1800672d0  call    ?BreakCacheIfNotBuildingCache@CFilterMapper2@@AEAAXXZ; CFilterMapper2::BreakCacheIfNotBuildingCache(void)
0x1800672d5  xor     ebx, ebx
0x1800672d7  xor     esi, esi
0x1800672d9  lea     eax, [rbx+1]
0x1800672dc  test    r15, r15
0x1800672df  jz      short loc_1800672ED
0x1800672e1  mov     rbx, [r15]
0x1800672e4  test    rbx, rbx
0x1800672e7  mov     [r15], rsi
0x1800672ea  cmovz   esi, eax
0x1800672ed  test    r14, r14
0x1800672f0  jnz     short loc_18006730D
0x1800672f2  lea     r8d, [r14+27h]; cchMax
0x1800672f6  mov     rcx, r13; rguid
0x1800672f9  lea     rdx, [rbp+0C0h+sz]; lpsz
0x1800672fd  call    cs:__imp_StringFromGUID2
0x180067304  nop     dword ptr [rax+rax+00h]
0x180067309  lea     r14, [rbp+0C0h+sz]
0x18006730d  lea     rax, CLSID_LegacyAmFilterCategory
0x180067314  mov     [rsp+1C0h+var_170], 0
0x18006731d  test    rdi, rdi
0x180067320  lea     rdx, [rbp+0C0h+var_E0]; lpsz
0x180067324  mov     r8d, 27h ; '''; cchMax
0x18006732a  cmovz   rdi, rax
0x18006732e  mov     rcx, rdi; rguid
0x180067331  call    cs:__imp_StringFromGUID2
0x180067338  nop     dword ptr [rax+rax+00h]
0x18006733d  mov     r8d, 27h ; '''; cchMax
0x180067343  lea     rdx, [rbp+0C0h+var_90]; lpsz
0x180067347  mov     rcx, r13; rguid
0x18006734a  call    cs:__imp_StringFromGUID2
0x180067351  nop     dword ptr [rax+rax+00h]
0x180067356  xor     r13d, r13d
0x180067359  test    rbx, rbx
0x18006735c  jnz     loc_18006747A
0x180067362  lea     rdx, [rsp+1C0h+ppbc]; ppbc
0x180067367  mov     [rsp+1C0h+ppbc], r13
0x18006736c  xor     ecx, ecx; reserved
0x18006736e  call    cs:__imp_CreateBindCtx
0x180067375  nop     dword ptr [rax+rax+00h]
0x18006737a  mov     ebx, eax
0x18006737c  test    eax, eax
0x18006737e  js      loc_1800676FC
0x180067384  mov     ecx, 8000h; unsigned __int64
0x180067389  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006738e  mov     rdi, rax
0x180067391  test    rax, rax
0x180067394  jz      loc_18006746C
0x18006739a  mov     ebx, 4000h
0x18006739f  lea     r8, aDeviceSw; "@device:sw:"
0x1800673a6  mov     edx, ebx; unsigned __int64
0x1800673a8  mov     rcx, rax; unsigned __int16 *
0x1800673ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800673b0  lea     r8, [rbp+0C0h+var_E0]; unsigned __int16 *
0x1800673b4  mov     edx, ebx; unsigned __int64
0x1800673b6  mov     rcx, rdi; unsigned __int16 *
0x1800673b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800673be  lea     r8, asc_180176468; "\\"
0x1800673c5  mov     edx, ebx; unsigned __int64
0x1800673c7  mov     rcx, rdi; unsigned __int16 *
0x1800673ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800673cf  mov     r8, r14; unsigned __int16 *
0x1800673d2  mov     edx, ebx; unsigned __int64
0x1800673d4  mov     rcx, rdi; unsigned __int16 *
0x1800673d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800673dc  lea     rax, [rsp+1C0h+var_188]
0x1800673e1  mov     dword ptr [rsp+1C0h+Size], r13d
0x1800673e6  lea     r9, IID_IParseDisplayName; riid
0x1800673ed  mov     [rsp+1C0h+ppv], rax; ppv
0x1800673f2  xor     edx, edx; pUnkOuter
0x1800673f4  mov     [rsp+1C0h+var_188], r13
0x1800673f9  lea     r8d, [r13+1]; dwClsContext
0x1800673fd  lea     rcx, CLSID_CDeviceMoniker; rclsid
0x180067404  call    cs:__imp_CoCreateInstance
0x18006740b  nop     dword ptr [rax+rax+00h]
0x180067410  mov     ebx, eax
0x180067412  test    eax, eax
0x180067414  js      short loc_180067451
0x180067416  mov     rcx, [rsp+1C0h+var_188]
0x18006741b  lea     rdx, [rsp+1C0h+var_170]
0x180067420  mov     [rsp+1C0h+ppv], rdx
0x180067425  lea     r9, [rsp+1C0h+Size]
0x18006742a  mov     rdx, [rsp+1C0h+ppbc]
0x18006742f  mov     r8, rdi
0x180067432  mov     rax, [rcx]
0x180067435  mov     rax, [rax+18h]
0x180067439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006743e  mov     rcx, [rsp+1C0h+var_188]
0x180067443  mov     ebx, eax
0x180067445  mov     rax, [rcx]
0x180067448  mov     rax, [rax+10h]
0x18006744c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067451  mov     rcx, [rsp+1C0h+ppbc]
0x180067456  mov     rax, [rcx]
0x180067459  mov     rax, [rax+10h]
0x18006745d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067462  mov     rcx, rdi; Block
0x180067465  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006746a  jmp     short loc_180067471
0x18006746c  mov     ebx, 8007000Eh
0x180067471  test    ebx, ebx
0x180067473  jns     short loc_18006748E
0x180067475  jmp     loc_1800676FC
0x18006747a  mov     [rsp+1C0h+var_170], rbx
0x18006747f  mov     rcx, rbx
0x180067482  mov     rax, [rbx]
0x180067485  mov     rax, [rax+8]
0x180067489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006748e  mov     rcx, [rsp+1C0h+var_170]
0x180067493  lea     rdx, [rsp+1C0h+var_188]
0x180067498  mov     [rsp+1C0h+var_188], r13
0x18006749d  lea     r9, IID_IPropertyBag
0x1800674a4  mov     [rsp+1C0h+ppv], rdx
0x1800674a9  xor     r8d, r8d
0x1800674ac  xor     edx, edx
0x1800674ae  mov     rax, [rcx]
0x1800674b1  mov     rax, [rax+48h]
0x1800674b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800674ba  mov     ebx, eax
0x1800674bc  test    eax, eax
0x1800674be  js      loc_1800676C8
0x1800674c4  mov     rcx, [rsp+1C0h+psz]; psz
0x1800674c9  xor     eax, eax
0x1800674cb  xorps   xmm0, xmm0
0x1800674ce  mov     [rbp+0C0h+var_138], rax
0x1800674d2  movups  xmmword ptr [rsp+1C0h+bstrString], xmm0
0x1800674d7  lea     edi, [rax+8]
0x1800674da  mov     word ptr [rsp+1C0h+bstrString], di
0x1800674df  call    cs:__imp_SysAllocString
0x1800674e6  nop     dword ptr [rax+rax+00h]
0x1800674eb  mov     [rbp+0C0h+bstrString+8], rax
0x1800674ef  test    rax, rax
0x1800674f2  jz      short loc_180067525
0x1800674f4  mov     rcx, [rsp+1C0h+var_188]
0x1800674f9  lea     r8, [rsp+1C0h+bstrString]
0x1800674fe  lea     rdx, aFriendlyname; "FriendlyName"
0x180067505  mov     rax, [rcx]
0x180067508  mov     rax, [rax+20h]
0x18006750c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067511  mov     rcx, [rbp+0C0h+bstrString+8]; bstrString
0x180067515  mov     ebx, eax
0x180067517  call    cs:__imp_SysFreeString
0x18006751e  nop     dword ptr [rax+rax+00h]
0x180067523  jmp     short loc_18006752A
0x180067525  mov     ebx, 8007000Eh
0x18006752a  test    ebx, ebx
0x18006752c  js      loc_1800676C8
0x180067532  xorps   xmm0, xmm0
0x180067535  lea     rcx, [rbp+0C0h+var_90]; psz
0x180067539  xor     eax, eax
0x18006753b  movups  xmmword ptr [rsp+1C0h+var_168], xmm0
0x180067540  mov     word ptr [rsp+1C0h+var_168], di
0x180067545  mov     [rsp+1C0h+var_158], rax
0x18006754a  call    cs:__imp_SysAllocString
0x180067551  nop     dword ptr [rax+rax+00h]
0x180067556  mov     [rsp+1C0h+var_168+8], rax
0x18006755b  test    rax, rax
0x18006755e  jz      loc_1800676C3
0x180067564  mov     rcx, [rsp+1C0h+var_188]
0x180067569  lea     r8, [rsp+1C0h+var_168]
0x18006756e  lea     rdx, aClsid; "CLSID"
0x180067575  mov     rax, [rcx]
0x180067578  mov     rax, [rax+20h]
0x18006757c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067581  mov     rcx, [rsp+1C0h+var_168+8]; bstrString
0x180067586  mov     ebx, eax
0x180067588  call    cs:__imp_SysFreeString
0x18006758f  nop     dword ptr [rax+rax+00h]
0x180067594  test    ebx, ebx
0x180067596  js      loc_1800676C8
0x18006759c  mov     r9d, 1; int
0x1800675a2  mov     dword ptr [rsp+1C0h+Size], r13d
0x1800675a7  lea     r8, [rsp+1C0h+Size]; unsigned int *
0x1800675ac  xor     ecx, ecx; unsigned __int8 *
0x1800675ae  lea     rdx, [rsp+1C0h+rgsabound]; struct REGFILTER2 **
0x1800675b3  call    ?RegSquish@@YAJPEAEPEAPEBUREGFILTER2@@PEAKH@Z; RegSquish(uchar *,REGFILTER2 const * *,ulong *,int)
0x1800675b8  mov     ebx, eax
0x1800675ba  test    eax, eax
0x1800675bc  js      loc_1800676C8
0x1800675c2  mov     ebx, dword ptr [rsp+1C0h+Size]
0x1800675c6  mov     ecx, ebx; unsigned __int64
0x1800675c8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800675cd  mov     rdi, rax
0x1800675d0  test    rax, rax
0x1800675d3  jz      loc_1800676C3
0x1800675d9  mov     r9d, 1; int
0x1800675df  mov     dword ptr [rsp+1C0h+Size], ebx
0x1800675e3  lea     r8, [rsp+1C0h+Size]; unsigned int *
0x1800675e8  mov     rcx, rax; unsigned __int8 *
0x1800675eb  lea     rdx, [rsp+1C0h+rgsabound]; struct REGFILTER2 **
0x1800675f0  call    ?RegSquish@@YAJPEAEPEAPEBUREGFILTER2@@PEAKH@Z; RegSquish(uchar *,REGFILTER2 const * *,ulong *,int)
0x1800675f5  mov     ebx, eax
0x1800675f7  test    eax, eax
0x1800675f9  jnz     loc_1800676B9
0x1800675ff  mov     ebx, dword ptr [rsp+1C0h+Size]
0x180067603  lea     r8, [rsp+1C0h+rgsabound]; rgsabound
0x180067608  xor     eax, eax
0x18006760a  mov     [rsp+1C0h+rgsabound.lLbound], r13d
0x18006760f  mov     ecx, 11h; vt
0x180067614  mov     [rsp+1C0h+var_158], rax
0x180067619  xorps   xmm0, xmm0
0x18006761c  mov     [rsp+1C0h+rgsabound.cElements], ebx
0x180067620  mov     eax, 2011h
0x180067625  movups  xmmword ptr [rsp+1C0h+var_168], xmm0
0x18006762a  lea     edx, [rcx-10h]; cDims
0x18006762d  mov     word ptr [rsp+1C0h+var_168], ax
0x180067632  call    cs:__imp_SafeArrayCreate
0x180067639  nop     dword ptr [rax+rax+00h]
0x18006763e  mov     [rsp+1C0h+var_168+8], rax
0x180067643  test    rax, rax
0x180067646  jz      short loc_1800676B4
0x180067648  lea     rdx, [rsp+1C0h+ppbc]; ppvData
0x18006764d  mov     [rsp+1C0h+ppbc], r13
0x180067652  mov     rcx, rax; psa
0x180067655  call    cs:__imp_SafeArrayAccessData
0x18006765c  nop     dword ptr [rax+rax+00h]
0x180067661  mov     rcx, [rsp+1C0h+ppbc]; void *
0x180067666  mov     r8d, ebx; Size
0x180067669  mov     rdx, rdi; Src
0x18006766c  call    memcpy_0
0x180067671  mov     rcx, [rsp+1C0h+var_188]
0x180067676  lea     r8, [rsp+1C0h+var_168]
0x18006767b  lea     rdx, aFilterdata; "FilterData"
0x180067682  mov     rax, [rcx]
0x180067685  mov     rax, [rax+20h]
0x180067689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006768e  mov     rcx, [rsp+1C0h+var_168+8]; psa
0x180067693  mov     ebx, eax
0x180067695  call    cs:__imp_SafeArrayUnaccessData
0x18006769c  nop     dword ptr [rax+rax+00h]
0x1800676a1  mov     rcx, [rsp+1C0h+var_168+8]; psa
0x1800676a6  call    cs:__imp_SafeArrayDestroy
0x1800676ad  nop     dword ptr [rax+rax+00h]
0x1800676b2  jmp     short loc_1800676B9
0x1800676b4  mov     ebx, 8007000Eh
0x1800676b9  mov     rcx, rdi; Block
0x1800676bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800676c1  jmp     short loc_1800676C8
0x1800676c3  mov     ebx, 8007000Eh
0x1800676c8  mov     rcx, [rsp+1C0h+var_188]
0x1800676cd  mov     rax, [rcx]
0x1800676d0  mov     rax, [rax+10h]
0x1800676d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676d9  test    ebx, ebx
0x1800676db  js      short loc_1800676FC
0x1800676dd  mov     rcx, [rsp+1C0h+var_170]
0x1800676e2  test    rcx, rcx
0x1800676e5  jz      short loc_1800676FC
0x1800676e7  test    esi, esi
0x1800676e9  jz      short loc_1800676F0
0x1800676eb  mov     [r15], rcx
0x1800676ee  jmp     short loc_1800676FC
0x1800676f0  mov     rax, [rcx]
0x1800676f3  mov     rax, [rax+10h]
0x1800676f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676fc  mov     rcx, r12; lpCriticalSection
0x1800676ff  call    cs:__imp_LeaveCriticalSection
0x180067706  nop     dword ptr [rax+rax+00h]
0x18006770b  mov     eax, ebx
0x18006770d  mov     rcx, [rbp+0C0h+var_40]
0x180067714  xor     rcx, rsp; StackCookie
0x180067717  call    __security_check_cookie
0x18006771c  mov     rbx, [rsp+1C0h+arg_0]
0x180067724  add     rsp, 190h
0x18006772b  pop     r15
0x18006772d  pop     r14
0x18006772f  pop     r13
0x180067731  pop     r12
0x180067733  pop     rdi
  ... truncated ...
```
