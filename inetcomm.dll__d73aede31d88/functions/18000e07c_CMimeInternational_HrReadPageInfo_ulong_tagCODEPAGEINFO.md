# CMimeInternational::_HrReadPageInfo(ulong,tagCODEPAGEINFO * *)

- ea: `0x18000e07c`
- end: `0x18000e3f8`
- name: `?_HrReadPageInfo@CMimeInternational@@AEAAJKPEAPEAUtagCODEPAGEINFO@@@Z`
- size: `892`
- prototype: `__int64 __fastcall(CMimeInternational *__hidden this, UINT CodePage, struct tagCODEPAGEINFO **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dfa8`

## callees

- `0x180002098`
- `0x18000e07c`
- `0x180019dd8`
- `0x180019fe8`
- `0x1800340a8`
- `0x1800341a4`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!IsValidCodePage` at `0x18000e22a`
- `KERNEL32!IsValidCodePage` at `0x18000e22a`
- `KERNEL32!GetThreadUILanguage` at `0x18000e142`
- `KERNEL32!GetThreadUILanguage` at `0x18000e142`
- `ole32!CoCreateInstance` at `0x18000e0f9`
- `ole32!CoCreateInstance` at `0x18000e121`
- `ole32!CoCreateInstance` at `0x18000e0f9`
- `ole32!CoCreateInstance` at `0x18000e121`

## pseudocode

```c
__int64 __fastcall CMimeInternational::_HrReadPageInfo(
        CMimeInternational *this,
        UINT CodePage,
        struct tagCODEPAGEINFO **a3)
{
  void *v6; // rdi
  HRESULT v7; // ebx
  __int64 (__fastcall *v8)(LPVOID, _QWORD, _QWORD, _BYTE *); // rbx
  LANGID ThreadUILanguage; // ax
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // r8d
  void *v13; // rax
  unsigned int v14; // r8d
  int v15; // ecx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  int v21; // eax
  int v22; // r8d
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v25; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+54h] [rbp-ACh]
  int v29; // [rsp+58h] [rbp-A8h]
  WCHAR WideCharStr[64]; // [rsp+5Ch] [rbp-A4h] BYREF
  WCHAR v31[50]; // [rsp+DCh] [rbp-24h] BYREF
  WCHAR v32[50]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR v33[50]; // [rsp+1A4h] [rbp+A4h] BYREF
  WCHAR v34[32]; // [rsp+208h] [rbp+108h] BYREF
  WCHAR v35[36]; // [rsp+248h] [rbp+148h] BYREF

  v6 = 0;
  memset_0(v27, 0, 0x23Cu);
  *a3 = 0;
  v25 = 0;
  ppv[0] = 0;
  if ( (g_dwCompatMode & 2) == 0 || CoCreateInstance(&CLSID_CMultiLanguage, 0, 3u, &IID_IMultiLanguage2, ppv) < 0 )
  {
    v7 = CoCreateInstance(&CLSID_CMultiLanguage, 0, 3u, &IID_IMultiLanguage, &v25);
    if ( v7 < 0 )
      goto LABEL_32;
  }
  if ( ppv[0] )
  {
    v8 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _BYTE *))(*(_QWORD *)ppv[0] + 32LL);
    ThreadUILanguage = GetThreadUILanguage();
    v10 = v8(ppv[0], CodePage, ThreadUILanguage, v27);
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _BYTE *))(*(_QWORD *)v25 + 32LL))(v25, CodePage, v27);
  }
  if ( v10 < 0 )
  {
    v7 = -2146644475;
    goto LABEL_32;
  }
  v11 = *((_DWORD *)this + 8);
  if ( v11 + 1 < v11 )
  {
    v7 = -2147024362;
    goto LABEL_32;
  }
  v12 = *((_DWORD *)this + 9);
  if ( v11 + 1 >= v12 )
  {
    v24 = 0;
    v7 = SafeScaleSumD2((unsigned int)&v24, 8, v12, 5, 0);
    if ( v7 < 0 )
      goto LABEL_32;
    v7 = HrRealloc((void **)this + 5, v24);
    if ( v7 < 0 )
      goto LABEL_32;
    *((_DWORD *)this + 9) += 5;
  }
  v13 = (void *)((__int64 (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 804);
  v6 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 0x324u);
    *((_DWORD *)v6 + 200) = *((_DWORD *)this + 8);
    *((_DWORD *)v6 + 1) = CodePage;
    *((_DWORD *)v6 + 2) = IsValidCodePage(CodePage);
    *((_DWORD *)v6 + 3) = 1;
    if ( CodePage - 932 <= 0x12 && (v15 = 393233, _bittest(&v15, CodePage - 932))
      || CodePage == 874
      || CodePage == 10001
      || CodePage == 1200 )
    {
      *((_DWORD *)v6 + 3) = 2;
    }
    v7 = convert_mimecpinfo_element(WideCharStr, (char *)v6 + 24, v14, (unsigned int *)v6, 2u);
    if ( v7 >= 0 )
    {
      v7 = convert_mimecpinfo_element(v33, (char *)v6 + 152, v16, (unsigned int *)v6, 4u);
      if ( v7 >= 0 )
      {
        v7 = convert_mimecpinfo_element(v32, (char *)v6 + 280, v17, (unsigned int *)v6, 8u);
        if ( v7 >= 0 )
        {
          v7 = convert_mimecpinfo_element(v31, (char *)v6 + 408, v18, (unsigned int *)v6, 0x10u);
          if ( v7 >= 0 )
          {
            v7 = convert_mimecpinfo_element(v34, (char *)v6 + 536, v19, (unsigned int *)v6, 0x20u);
            if ( v7 >= 0 )
            {
              v7 = convert_mimecpinfo_element(v35, (char *)v6 + 664, v20, (unsigned int *)v6, 0x40u);
              if ( v7 >= 0 )
              {
                v21 = v29;
                *(_DWORD *)v6 |= 1u;
                *((_DWORD *)v6 + 5) = v21;
                if ( v29 != v28 )
                  *((_DWORD *)v6 + 4) = 1;
                *((_QWORD *)v6 + 99) = 0;
                *(_QWORD *)(*((_QWORD *)this + 5) + 8LL * *((unsigned int *)this + 8)) = v6;
                *a3 = (struct tagCODEPAGEINFO *)v6;
                v6 = 0;
                v22 = *((_DWORD *)this + 8);
                *((_DWORD *)this + 8) = v22 + 1;
                CMimeInternational::_QuickSortPageInfo(this, 0, v22);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
LABEL_32:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v25);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(ppv);
  if ( v6 )
    ((void (__fastcall *)(LPMALLOC, void *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e07c  mov     [rsp-8+arg_18], rbx
0x18000e081  push    rbp
0x18000e082  push    rsi
0x18000e083  push    rdi
0x18000e084  push    r14
0x18000e086  push    r15
0x18000e088  lea     rbp, [rsp-1A0h]
0x18000e090  sub     rsp, 2A0h
0x18000e097  mov     rax, cs:__security_cookie
0x18000e09e  xor     rax, rsp
0x18000e0a1  mov     [rbp+1C0h+var_30], rax
0x18000e0a8  mov     r15, r8
0x18000e0ab  mov     r14d, edx
0x18000e0ae  mov     rsi, rcx
0x18000e0b1  xor     edx, edx; Val
0x18000e0b3  mov     r8d, 23Ch; Size
0x18000e0b9  lea     rcx, [rsp+2C0h+var_270]; void *
0x18000e0be  xor     edi, edi
0x18000e0c0  call    memset_0
0x18000e0c5  xor     edx, edx; pUnkOuter
0x18000e0c7  mov     [r15], rdi
0x18000e0ca  test    byte ptr cs:?g_dwCompatMode@@3KA, 2; ulong g_dwCompatMode
0x18000e0d1  lea     r8d, [rdi+3]; dwClsContext
0x18000e0d5  mov     [rsp+2C0h+var_288], rdi
0x18000e0da  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18000e0e1  mov     [rsp+2C0h+var_280], rdi
0x18000e0e6  jz      short loc_18000E110
0x18000e0e8  lea     rax, [rsp+2C0h+var_280]
0x18000e0ed  lea     r9, IID_IMultiLanguage2; riid
0x18000e0f4  mov     [rsp+2C0h+ppv], rax; ppv
0x18000e0f9  call    cs:__imp_CoCreateInstance
0x18000e0ff  test    eax, eax
0x18000e101  jns     short loc_18000E131
0x18000e103  xor     edx, edx; pUnkOuter
0x18000e105  lea     r8d, [rdi+3]; dwClsContext
0x18000e109  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18000e110  lea     rax, [rsp+2C0h+var_288]
0x18000e115  lea     r9, IID_IMultiLanguage; riid
0x18000e11c  mov     [rsp+2C0h+ppv], rax; ppv
0x18000e121  call    cs:__imp_CoCreateInstance
0x18000e127  mov     ebx, eax
0x18000e129  test    eax, eax
0x18000e12b  js      loc_18000E3A1
0x18000e131  mov     rax, [rsp+2C0h+var_280]
0x18000e136  test    rax, rax
0x18000e139  jz      short loc_18000E16F
0x18000e13b  mov     rax, [rax]
0x18000e13e  mov     rbx, [rax+20h]
0x18000e142  call    cs:__imp_GetThreadUILanguage
0x18000e148  mov     rcx, [rsp+2C0h+var_280]
0x18000e14d  lea     r9, [rsp+2C0h+var_270]
0x18000e152  movzx   r8d, ax
0x18000e156  mov     edx, r14d
0x18000e159  mov     rax, rbx
0x18000e15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e161  test    eax, eax
0x18000e163  jns     short loc_18000E18A
0x18000e165  mov     ebx, 800CCE05h
0x18000e16a  jmp     loc_18000E3A1
0x18000e16f  mov     rcx, [rsp+2C0h+var_288]
0x18000e174  lea     r8, [rsp+2C0h+var_270]
0x18000e179  mov     edx, r14d
0x18000e17c  mov     rax, [rcx]
0x18000e17f  mov     rax, [rax+20h]
0x18000e183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e188  jmp     short loc_18000E161
0x18000e18a  mov     eax, [rsi+20h]
0x18000e18d  lea     ecx, [rax+1]
0x18000e190  cmp     ecx, eax
0x18000e192  jb      loc_18000E39C
0x18000e198  mov     r8d, [rsi+24h]
0x18000e19c  cmp     ecx, r8d
0x18000e19f  jb      short loc_18000E1E1
0x18000e1a1  mov     edx, 8
0x18000e1a6  mov     [rsp+2C0h+var_290], edi
0x18000e1aa  lea     rcx, [rsp+2C0h+var_290]
0x18000e1af  mov     dword ptr [rsp+2C0h+ppv], edi
0x18000e1b3  lea     r9d, [rdx-3]
0x18000e1b7  call    SafeScaleSumD2
0x18000e1bc  mov     ebx, eax
0x18000e1be  test    eax, eax
0x18000e1c0  js      loc_18000E3A1
0x18000e1c6  mov     edx, [rsp+2C0h+var_290]; unsigned int
0x18000e1ca  lea     rcx, [rsi+28h]; void **
0x18000e1ce  call    ?HrRealloc@@YAJPEAPEAXK@Z; HrRealloc(void * *,ulong)
0x18000e1d3  mov     ebx, eax
0x18000e1d5  test    eax, eax
0x18000e1d7  js      loc_18000E3A1
0x18000e1dd  add     dword ptr [rsi+24h], 5
0x18000e1e1  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000e1e8  mov     ebx, 324h
0x18000e1ed  mov     edx, ebx
0x18000e1ef  mov     rax, [rcx]
0x18000e1f2  mov     rax, [rax+18h]
0x18000e1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1fb  mov     rdi, rax
0x18000e1fe  test    rax, rax
0x18000e201  jnz     short loc_18000E20D
0x18000e203  mov     ebx, 8007000Eh
0x18000e208  jmp     loc_18000E3A1
0x18000e20d  mov     r8, rbx; Size
0x18000e210  xor     edx, edx; Val
0x18000e212  mov     rcx, rdi; void *
0x18000e215  call    memset_0
0x18000e21a  mov     eax, [rsi+20h]
0x18000e21d  mov     ecx, r14d; CodePage
0x18000e220  mov     [rdi+320h], eax
0x18000e226  mov     [rdi+4], r14d
0x18000e22a  call    cs:__imp_IsValidCodePage
0x18000e230  mov     [rdi+8], eax
0x18000e233  lea     eax, [r14-3A4h]
0x18000e23a  mov     dword ptr [rdi+0Ch], 1
0x18000e241  cmp     eax, 12h
0x18000e244  ja      short loc_18000E250
0x18000e246  mov     ecx, 60011h
0x18000e24b  bt      ecx, eax
0x18000e24e  jb      short loc_18000E26B
0x18000e250  cmp     r14d, 36Ah
0x18000e257  jz      short loc_18000E26B
0x18000e259  cmp     r14d, 2711h
0x18000e260  jz      short loc_18000E26B
0x18000e262  cmp     r14d, 4B0h
0x18000e269  jnz     short loc_18000E272
0x18000e26b  mov     dword ptr [rdi+0Ch], 2
0x18000e272  lea     rdx, [rdi+18h]; char *
0x18000e276  mov     dword ptr [rsp+2C0h+ppv], 2; unsigned int
0x18000e27e  mov     r9, rdi; unsigned int *
0x18000e281  lea     rcx, [rsp+2C0h+WideCharStr]; lpWideCharStr
0x18000e286  call    ?convert_mimecpinfo_element@@YAJPEBGPEADKAEAKK@Z; convert_mimecpinfo_element(ushort const *,char *,ulong,ulong &,ulong)
0x18000e28b  mov     ebx, eax
0x18000e28d  test    eax, eax
0x18000e28f  js      loc_18000E3A1
0x18000e295  lea     rdx, [rdi+98h]; char *
0x18000e29c  mov     dword ptr [rsp+2C0h+ppv], 4; unsigned int
0x18000e2a4  mov     r9, rdi; unsigned int *
0x18000e2a7  lea     rcx, [rbp+1C0h+var_11C]; lpWideCharStr
0x18000e2ae  call    ?convert_mimecpinfo_element@@YAJPEBGPEADKAEAKK@Z; convert_mimecpinfo_element(ushort const *,char *,ulong,ulong &,ulong)
0x18000e2b3  mov     ebx, eax
0x18000e2b5  test    eax, eax
0x18000e2b7  js      loc_18000E3A1
0x18000e2bd  lea     rdx, [rdi+118h]; char *
0x18000e2c4  mov     dword ptr [rsp+2C0h+ppv], 8; unsigned int
0x18000e2cc  mov     r9, rdi; unsigned int *
0x18000e2cf  lea     rcx, [rbp+1C0h+var_180]; lpWideCharStr
0x18000e2d3  call    ?convert_mimecpinfo_element@@YAJPEBGPEADKAEAKK@Z; convert_mimecpinfo_element(ushort const *,char *,ulong,ulong &,ulong)
0x18000e2d8  mov     ebx, eax
0x18000e2da  test    eax, eax
0x18000e2dc  js      loc_18000E3A1
0x18000e2e2  lea     rdx, [rdi+198h]; char *
0x18000e2e9  mov     dword ptr [rsp+2C0h+ppv], 10h; unsigned int
0x18000e2f1  mov     r9, rdi; unsigned int *
0x18000e2f4  lea     rcx, [rbp+1C0h+var_1E4]; lpWideCharStr
0x18000e2f8  call    ?convert_mimecpinfo_element@@YAJPEBGPEADKAEAKK@Z; convert_mimecpinfo_element(ushort const *,char *,ulong,ulong &,ulong)
0x18000e2fd  mov     ebx, eax
0x18000e2ff  test    eax, eax
0x18000e301  js      loc_18000E3A1
0x18000e307  lea     rdx, [rdi+218h]; char *
0x18000e30e  mov     dword ptr [rsp+2C0h+ppv], 20h ; ' '; unsigned int
0x18000e316  mov     r9, rdi; unsigned int *
0x18000e319  lea     rcx, [rbp+1C0h+var_B8]; lpWideCharStr
0x18000e320  call    ?convert_mimecpinfo_element@@YAJPEBGPEADKAEAKK@Z; convert_mimecpinfo_element(ushort const *,char *,ulong,ulong &,ulong)
0x18000e325  mov     ebx, eax
0x18000e327  test    eax, eax
0x18000e329  js      short loc_18000E3A1
0x18000e32b  lea     rdx, [rdi+298h]; char *
0x18000e332  mov     dword ptr [rsp+2C0h+ppv], 40h ; '@'; unsigned int
0x18000e33a  mov     r9, rdi; unsigned int *
0x18000e33d  lea     rcx, [rbp+1C0h+var_78]; lpWideCharStr
0x18000e344  call    ?convert_mimecpinfo_element@@YAJPEBGPEADKAEAKK@Z; convert_mimecpinfo_element(ushort const *,char *,ulong,ulong &,ulong)
0x18000e349  mov     ebx, eax
0x18000e34b  test    eax, eax
0x18000e34d  js      short loc_18000E3A1
0x18000e34f  mov     eax, [rsp+2C0h+var_268]
0x18000e353  or      dword ptr [rdi], 1
0x18000e356  mov     [rdi+14h], eax
0x18000e359  mov     eax, [rsp+2C0h+var_26C]
0x18000e35d  cmp     [rsp+2C0h+var_268], eax
0x18000e361  jz      short loc_18000E36A
0x18000e363  mov     dword ptr [rdi+10h], 1
0x18000e36a  mov     qword ptr [rdi+318h], 0
0x18000e375  mov     rcx, rsi; this
0x18000e378  mov     edx, [rsi+20h]
0x18000e37b  mov     rax, [rsi+28h]
0x18000e37f  mov     [rax+rdx*8], rdi
0x18000e383  xor     edx, edx; int
0x18000e385  mov     [r15], rdi
0x18000e388  xor     edi, edi
0x18000e38a  mov     r8d, [rsi+20h]; int
0x18000e38e  lea     eax, [r8+1]
0x18000e392  mov     [rsi+20h], eax
0x18000e395  call    ?_QuickSortPageInfo@CMimeInternational@@AEAAXJJ@Z; CMimeInternational::_QuickSortPageInfo(long,long)
0x18000e39a  jmp     short loc_18000E3A1
0x18000e39c  mov     ebx, 80070216h
0x18000e3a1  lea     rcx, [rsp+2C0h+var_288]
0x18000e3a6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000e3ab  lea     rcx, [rsp+2C0h+var_280]
0x18000e3b0  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18000e3b5  test    rdi, rdi
0x18000e3b8  jz      short loc_18000E3D0
0x18000e3ba  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000e3c1  mov     rdx, rdi
0x18000e3c4  mov     rax, [rcx]
0x18000e3c7  mov     rax, [rax+28h]
0x18000e3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3d0  mov     eax, ebx
0x18000e3d2  mov     rcx, [rbp+1C0h+var_30]
0x18000e3d9  xor     rcx, rsp; StackCookie
0x18000e3dc  call    __security_check_cookie
0x18000e3e1  mov     rbx, [rsp+2C0h+arg_18]
0x18000e3e9  add     rsp, 2A0h
0x18000e3f0  pop     r15
0x18000e3f2  pop     r14
0x18000e3f4  pop     rdi
0x18000e3f5  pop     rsi
0x18000e3f6  pop     rbp
0x18000e3f7  retn
```
