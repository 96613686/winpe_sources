# CMapperCache::Cache(void)

- ea: `0x180065f88`
- end: `0x1800662ec`
- name: `?Cache@CMapperCache@@QEAAJXZ`
- size: `868`
- prototype: `__int64 __fastcall(CMapperCache *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180015760`

## callees

- `0x18000e770`
- `0x180011ff0`
- `0x18001476c`
- `0x180019ecc`
- `0x18001bd10`
- `0x180025fe0`
- `0x18002a30c`
- `0x180038458`
- `0x180038498`
- `0x1800388a0`
- `0x180065f88`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180066030`
- `KERNEL32!LeaveCriticalSection` at `0x1800662be`
- `KERNEL32!LeaveCriticalSection` at `0x180066030`
- `KERNEL32!LeaveCriticalSection` at `0x1800662be`
- `KERNEL32!EnterCriticalSection` at `0x180065fae`
- `KERNEL32!EnterCriticalSection` at `0x180065fae`
- `ole32!CLSIDFromString` at `0x1800661c0`
- `ole32!CLSIDFromString` at `0x1800661c0`
- `ole32!CoCreateInstance` at `0x180066088`
- `ole32!CoCreateInstance` at `0x180066088`
- `OLEAUT32!__imp_SysFreeString` at `0x18006623c`
- `OLEAUT32!__imp_SysFreeString` at `0x18006624c`
- `OLEAUT32!__imp_SysFreeString` at `0x18006623c`
- `OLEAUT32!__imp_SysFreeString` at `0x18006624c`

## string_xrefs

- `0x180066183`: `CLSID`
- `0x18006604f`: `Build Mapper Cache`

## pseudocode

```c
__int64 __fastcall CMapperCache::Cache(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rcx
  unsigned int v3; // edx
  CMapperCache *v4; // rcx
  unsigned int v5; // r8d
  _QWORD *v6; // rax
  struct _FILTER_CACHE *Cache; // rax
  struct _FILTER_CACHE *v8; // rsi
  int v9; // ebx
  struct ICreateDevEnum **p_SpinCount; // rsi
  unsigned int v12; // edx
  unsigned int v13; // r8d
  struct ICreateDevEnum *v14; // rcx
  int v15; // eax
  const unsigned __int16 *v16; // r8
  int v17; // ebx
  bool v18; // cc
  __int64 v19; // [rsp+30h] [rbp-79h] BYREF
  int v20; // [rsp+38h] [rbp-71h] BYREF
  __int64 v21; // [rsp+40h] [rbp-69h] BYREF
  __int64 v22; // [rsp+48h] [rbp-61h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-59h] BYREF
  __int64 v24; // [rsp+60h] [rbp-49h]
  LPCOLESTR lpsz[2]; // [rsp+68h] [rbp-41h] BYREF
  __int64 v26; // [rsp+78h] [rbp-31h]
  __int128 v27; // [rsp+80h] [rbp-29h] BYREF
  __int64 v28; // [rsp+90h] [rbp-19h]
  _BYTE v29[16]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v30[16]; // [rsp+A8h] [rbp-1h] BYREF
  GUID pclsid; // [rsp+B8h] [rbp+Fh] BYREF

  EnterCriticalSection(this);
  OwningThread = this[1].OwningThread;
  ++HIDWORD(this[1].DebugInfo);
  if ( OwningThread )
  {
    ((void (*)(void))CMapperCache::Del)();
LABEL_5:
    if ( this[1].RecursionCount > 0x200000u )
    {
      Cache = CMapperCache::LoadCache(v4, v3, v5);
      v8 = Cache;
      if ( Cache )
      {
        v9 = CMapperCache::RestoreFromCacheInternal((CMapperCache *)this, Cache);
        operator delete(v8);
        if ( v9 >= 0 )
        {
LABEL_8:
          LeaveCriticalSection(this);
          return 0;
        }
      }
      CMapperCache::Del(this[1].OwningThread);
    }
    CAutoTimer::CAutoTimer((CAutoTimer *)v30, L"Build Mapper Cache", 0);
    p_SpinCount = (struct ICreateDevEnum **)&this[1].SpinCount;
    this[1].LockCount = 1;
    if ( !this[1].SpinCount
      && CoCreateInstance(&CLSID_SystemDeviceEnum, 0, 1u, &IID_ICreateDevEnum, (LPVOID *)&this[1].SpinCount) < 0
      || (v14 = *p_SpinCount,
          v22 = 0,
          ((unsigned int (__fastcall *)(struct ICreateDevEnum *, GUID *, __int64 *, _QWORD))v14->lpVtbl->CreateClassEnumerator)(
            v14,
            &CLSID_ActiveMovieCategories,
            &v22,
            0)) )
    {
LABEL_29:
      v18 = this[1].RecursionCount <= 0x200000u;
      this[1].LockCount = 0;
      if ( !v18 )
        CMapperCache::SaveCacheToRegistry((CMapperCache *)this, v12, v13);
      CAutoTimer::~CAutoTimer((CAutoTimer *)v30);
      goto LABEL_8;
    }
    v21 = 0;
    v20 = 0;
    while ( 1 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v22 + 24LL))(
             v22,
             1,
             &v21,
             &v20)
        || (v19 = 0,
            (*(int (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, __int64 *))(*(_QWORD *)v21 + 72LL))(
              v21,
              0,
              0,
              &IID_IPropertyBag,
              &v19) < 0) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        goto LABEL_29;
      }
      v28 = 0;
      v27 = 0;
      LOWORD(v27) = 3;
      if ( (*(int (__fastcall **)(__int64, const WCHAR *, __int128 *, _QWORD))(*(_QWORD *)v19 + 24LL))(
             v19,
             L"Merit",
             &v27,
             0) < 0 )
      {
        if ( this[1].RecursionCount > 0x200000u )
          goto LABEL_27;
      }
      else if ( SDWORD2(v27) < this[1].RecursionCount )
      {
        goto LABEL_27;
      }
      v26 = 0;
      *(_OWORD *)lpsz = 0;
      LOWORD(lpsz[0]) = 8;
      if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, LPCOLESTR *, _QWORD))(*(_QWORD *)v19 + 24LL))(
             v19,
             L"CLSID",
             lpsz,
             0) >= 0 )
      {
        pclsid = 0;
        if ( !CLSIDFromString(lpsz[1], &pclsid) )
        {
          v24 = 0;
          *(_OWORD *)bstrString = 0;
          LOWORD(bstrString[0]) = 8;
          v15 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, BSTR *, _QWORD))(*(_QWORD *)v19 + 24LL))(
                  v19,
                  L"FriendlyName",
                  bstrString,
                  0);
          v16 = 0;
          if ( v15 >= 0 )
            v16 = bstrString[1];
          v17 = v15;
          CAutoTimer::CAutoTimer((CAutoTimer *)v29, L"Process Category ", v16);
          CMapperCache::ProcessOneCategory((CMapperCache *)this, &pclsid, *p_SpinCount);
          CAutoTimer::~CAutoTimer((CAutoTimer *)v29);
          if ( v17 >= 0 )
            SysFreeString(bstrString[1]);
        }
        SysFreeString((BSTR)lpsz[1]);
      }
LABEL_27:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  v6 = operator new(0x28u);
  if ( v6 )
  {
    *v6 = 0;
    v6[1] = 0;
    *((_DWORD *)v6 + 4) = 0;
    v6[3] = 10;
    v6[4] = 0;
    this[1].OwningThread = v6;
    goto LABEL_5;
  }
  this[1].OwningThread = 0;
  LODWORD(this[1].DebugInfo) = 1;
  LeaveCriticalSection(this);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180065f88  push    rbp
0x180065f8a  push    rbx
0x180065f8b  push    rsi
0x180065f8c  push    rdi
0x180065f8d  push    r13
0x180065f8f  push    r14
0x180065f91  lea     rbp, [rsp-2Fh]
0x180065f96  sub     rsp, 0D8h
0x180065f9d  mov     rax, cs:__security_cookie
0x180065fa4  xor     rax, rsp
0x180065fa7  mov     [rbp+57h+var_38], rax
0x180065fab  mov     rdi, rcx
0x180065fae  call    cs:__imp_EnterCriticalSection
0x180065fb5  nop     dword ptr [rax+rax+00h]
0x180065fba  mov     rcx, [rdi+38h]
0x180065fbe  xor     r14d, r14d
0x180065fc1  inc     dword ptr [rdi+2Ch]
0x180065fc4  test    rcx, rcx
0x180065fc7  jz      short loc_180065FD0
0x180065fc9  call    ?Del@CMapperCache@@CAXPEAV?$CGenericList@VCMapFilter@CMapperCache@@@@@Z; CMapperCache::Del(CGenericList<CMapperCache::CMapFilter> *)
0x180065fce  jmp     short loc_180065FFE
0x180065fd0  mov     ecx, 28h ; '('; Size
0x180065fd5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065fda  test    rax, rax
0x180065fdd  jz      loc_1800662B0
0x180065fe3  mov     [rax], r14
0x180065fe6  mov     [rax+8], r14
0x180065fea  mov     [rax+10h], r14d
0x180065fee  mov     qword ptr [rax+18h], 0Ah
0x180065ff6  mov     [rax+20h], r14
0x180065ffa  mov     [rdi+38h], rax
0x180065ffe  cmp     dword ptr [rdi+34h], 200000h
0x180066005  jbe     short loc_18006604C
0x180066007  call    ?LoadCache@CMapperCache@@QEAAPEAU_FILTER_CACHE@@KK@Z; CMapperCache::LoadCache(ulong,ulong)
0x18006600c  mov     rsi, rax
0x18006600f  test    rax, rax
0x180066012  jz      short loc_180066043
0x180066014  mov     rdx, rax; struct _FILTER_CACHE *
0x180066017  mov     rcx, rdi; this
0x18006601a  call    ?RestoreFromCacheInternal@CMapperCache@@QEAAJPEAU_FILTER_CACHE@@@Z; CMapperCache::RestoreFromCacheInternal(_FILTER_CACHE *)
0x18006601f  mov     rcx, rsi; Block
0x180066022  mov     ebx, eax
0x180066024  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180066029  test    ebx, ebx
0x18006602b  js      short loc_180066043
0x18006602d  mov     rcx, rdi; lpCriticalSection
0x180066030  call    cs:__imp_LeaveCriticalSection
0x180066037  nop     dword ptr [rax+rax+00h]
0x18006603c  xor     eax, eax
0x18006603e  jmp     loc_1800662CF
0x180066043  mov     rcx, [rdi+38h]
0x180066047  call    ?Del@CMapperCache@@CAXPEAV?$CGenericList@VCMapFilter@CMapperCache@@@@@Z; CMapperCache::Del(CGenericList<CMapperCache::CMapFilter> *)
0x18006604c  xor     r8d, r8d; unsigned __int16 *
0x18006604f  lea     rdx, aBuildMapperCac; "Build Mapper Cache"
0x180066056  lea     rcx, [rbp+57h+var_58]; this
0x18006605a  call    ??0CAutoTimer@@QEAA@PEBG0@Z; CAutoTimer::CAutoTimer(ushort const *,ushort const *)
0x18006605f  lea     rsi, [rdi+48h]
0x180066063  mov     dword ptr [rdi+30h], 1
0x18006606a  cmp     [rsi], r14
0x18006606d  jnz     short loc_18006609C
0x18006606f  xor     edx, edx; pUnkOuter
0x180066071  mov     [rsp+100h+ppv], rsi; ppv
0x180066076  lea     r9, IID_ICreateDevEnum; riid
0x18006607d  lea     rcx, CLSID_SystemDeviceEnum; rclsid
0x180066084  lea     r8d, [rdx+1]; dwClsContext
0x180066088  call    cs:__imp_CoCreateInstance
0x18006608f  nop     dword ptr [rax+rax+00h]
0x180066094  test    eax, eax
0x180066096  js      loc_18006628D
0x18006609c  mov     rcx, [rsi]
0x18006609f  lea     r8, [rbp+57h+var_B8]
0x1800660a3  mov     [rbp+57h+var_B8], r14
0x1800660a7  lea     rdx, CLSID_ActiveMovieCategories
0x1800660ae  xor     r9d, r9d
0x1800660b1  mov     rax, [rcx]
0x1800660b4  mov     rax, [rax+18h]
0x1800660b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660bd  test    eax, eax
0x1800660bf  jnz     loc_18006628D
0x1800660c5  mov     [rbp+57h+var_C0], r14
0x1800660c9  lea     r13d, [rax+8]
0x1800660cd  mov     [rbp+57h+var_C8], r14d
0x1800660d1  mov     rcx, [rbp+57h+var_B8]
0x1800660d5  lea     r9, [rbp+57h+var_C8]
0x1800660d9  lea     r8, [rbp+57h+var_C0]
0x1800660dd  mov     edx, 1
0x1800660e2  mov     rax, [rcx]
0x1800660e5  mov     rax, [rax+18h]
0x1800660e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660ee  test    eax, eax
0x1800660f0  jnz     loc_18006627D
0x1800660f6  mov     rcx, [rbp+57h+var_C0]
0x1800660fa  lea     rdx, [rbp+57h+var_D0]
0x1800660fe  mov     [rbp+57h+var_D0], r14
0x180066102  lea     r9, IID_IPropertyBag
0x180066109  mov     [rsp+100h+ppv], rdx
0x18006610e  xor     r8d, r8d
0x180066111  xor     edx, edx
0x180066113  mov     rax, [rcx]
0x180066116  mov     rax, [rax+48h]
0x18006611a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006611f  test    eax, eax
0x180066121  js      loc_18006627D
0x180066127  mov     rcx, [rbp+57h+var_D0]
0x18006612b  lea     r8, [rbp+57h+var_80]
0x18006612f  xor     eax, eax
0x180066131  lea     rdx, aMerit; "Merit"
0x180066138  mov     [rbp+57h+var_70], rax
0x18006613c  xorps   xmm0, xmm0
0x18006613f  movups  [rbp+57h+var_80], xmm0
0x180066143  mov     eax, 3
0x180066148  xor     r9d, r9d
0x18006614b  mov     word ptr [rbp+57h+var_80], ax
0x18006614f  mov     rax, [rcx]
0x180066152  mov     rax, [rax+18h]
0x180066156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006615b  test    eax, eax
0x18006615d  js      short loc_18006616C
0x18006615f  mov     eax, [rdi+34h]
0x180066162  cmp     dword ptr [rbp+57h+var_80+8], eax
0x180066165  jge     short loc_180066179
0x180066167  jmp     loc_180066258
0x18006616c  cmp     dword ptr [rdi+34h], 200000h
0x180066173  ja      loc_180066258
0x180066179  mov     rcx, [rbp+57h+var_D0]
0x18006617d  lea     r8, [rbp+57h+lpsz]
0x180066181  xor     eax, eax
0x180066183  lea     rdx, aClsid; "CLSID"
0x18006618a  mov     [rbp+57h+var_88], rax
0x18006618e  xorps   xmm0, xmm0
0x180066191  movups  xmmword ptr [rbp+57h+lpsz], xmm0
0x180066195  mov     word ptr [rbp+57h+lpsz], r13w
0x18006619a  xor     r9d, r9d
0x18006619d  mov     rax, [rcx]
0x1800661a0  mov     rax, [rax+18h]
0x1800661a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661a9  test    eax, eax
0x1800661ab  js      loc_180066258
0x1800661b1  mov     rcx, [rbp+57h+lpsz+8]; lpsz
0x1800661b5  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1800661b9  xorps   xmm0, xmm0
0x1800661bc  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x1800661c0  call    cs:__imp_CLSIDFromString
0x1800661c7  nop     dword ptr [rax+rax+00h]
0x1800661cc  test    eax, eax
0x1800661ce  jnz     short loc_180066248
0x1800661d0  mov     rcx, [rbp+57h+var_D0]
0x1800661d4  lea     r8, [rbp+57h+bstrString]
0x1800661d8  xor     eax, eax
0x1800661da  lea     rdx, aFriendlyname; "FriendlyName"
0x1800661e1  mov     [rbp+57h+var_A0], rax
0x1800661e5  xorps   xmm0, xmm0
0x1800661e8  movups  xmmword ptr [rbp+57h+bstrString], xmm0
0x1800661ec  mov     word ptr [rbp+57h+bstrString], r13w
0x1800661f1  xor     r9d, r9d
0x1800661f4  mov     rax, [rcx]
0x1800661f7  mov     rax, [rax+18h]
0x1800661fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066200  test    eax, eax
0x180066202  lea     rdx, aProcessCategor; "Process Category "
0x180066209  mov     r8, r14
0x18006620c  lea     rcx, [rbp+57h+var_68]; this
0x180066210  cmovns  r8, [rbp+57h+bstrString+8]; unsigned __int16 *
0x180066215  mov     ebx, eax
0x180066217  call    ??0CAutoTimer@@QEAA@PEBG0@Z; CAutoTimer::CAutoTimer(ushort const *,ushort const *)
0x18006621c  mov     r8, [rsi]; struct ICreateDevEnum *
0x18006621f  lea     rdx, [rbp+57h+pclsid]; struct _GUID *
0x180066223  mov     rcx, rdi; this
0x180066226  call    ?ProcessOneCategory@CMapperCache@@AEAAJAEBU_GUID@@PEAUICreateDevEnum@@@Z; CMapperCache::ProcessOneCategory(_GUID const &,ICreateDevEnum *)
0x18006622b  lea     rcx, [rbp+57h+var_68]; this
0x18006622f  call    ??1CAutoTimer@@QEAA@XZ; CAutoTimer::~CAutoTimer(void)
0x180066234  test    ebx, ebx
0x180066236  js      short loc_180066248
0x180066238  mov     rcx, [rbp+57h+bstrString+8]; bstrString
0x18006623c  call    cs:__imp_SysFreeString
0x180066243  nop     dword ptr [rax+rax+00h]
0x180066248  mov     rcx, [rbp+57h+lpsz+8]; bstrString
0x18006624c  call    cs:__imp_SysFreeString
0x180066253  nop     dword ptr [rax+rax+00h]
0x180066258  mov     rcx, [rbp+57h+var_D0]
0x18006625c  mov     rax, [rcx]
0x18006625f  mov     rax, [rax+10h]
0x180066263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066268  mov     rcx, [rbp+57h+var_C0]
0x18006626c  mov     rax, [rcx]
0x18006626f  mov     rax, [rax+10h]
0x180066273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066278  jmp     loc_1800660D1
0x18006627d  mov     rcx, [rbp+57h+var_B8]
0x180066281  mov     rax, [rcx]
0x180066284  mov     rax, [rax+10h]
0x180066288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006628d  cmp     dword ptr [rdi+34h], 200000h
0x180066294  mov     [rdi+30h], r14d
0x180066298  jbe     short loc_1800662A2
0x18006629a  mov     rcx, rdi; this
0x18006629d  call    ?SaveCacheToRegistry@CMapperCache@@QEAAJKK@Z; CMapperCache::SaveCacheToRegistry(ulong,ulong)
0x1800662a2  lea     rcx, [rbp+57h+var_58]; this
0x1800662a6  call    ??1CAutoTimer@@QEAA@XZ; CAutoTimer::~CAutoTimer(void)
0x1800662ab  jmp     loc_18006602D
0x1800662b0  mov     rcx, rdi; lpCriticalSection
0x1800662b3  mov     [rdi+38h], r14
0x1800662b7  mov     dword ptr [rdi+28h], 1
0x1800662be  call    cs:__imp_LeaveCriticalSection
0x1800662c5  nop     dword ptr [rax+rax+00h]
0x1800662ca  mov     eax, 8007000Eh
0x1800662cf  mov     rcx, [rbp+57h+var_38]
0x1800662d3  xor     rcx, rsp; StackCookie
0x1800662d6  call    __security_check_cookie
0x1800662db  add     rsp, 0D8h
0x1800662e2  pop     r14
0x1800662e4  pop     r13
0x1800662e6  pop     rdi
0x1800662e7  pop     rsi
0x1800662e8  pop     rbx
0x1800662e9  pop     rbp
0x1800662ea  retn
```
