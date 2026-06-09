# Utils::ExecuteWmiQuery(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<IEnumWbemClassObject> &)

- ea: `0x1800d210c`
- end: `0x1800d250b`
- name: `?ExecuteWmiQuery@Utils@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV?$ComPtr@UIEnumWbemClassObject@@@WRL@Microsoft@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800292f0`
- `0x1800295ec`
- `0x18007f814`
- `0x1800d3ffc`

## callees

- `0x180011ce4`
- `0x18007245c`
- `0x180072610`
- `0x1800d210c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800d22eb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800d2466`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800d22eb`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800d2466`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d2152`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d2152`

## string_xrefs

- `0x1800d2271`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d22fe`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d23f5`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`
- `0x1800d2479`: `onecore\base\appcompat\programs\devicecensus\dlls\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Utils::ExecuteWmiQuery(unsigned __int16 *a1, unsigned __int16 *a2, IUnknown **a3)
{
  HRESULT v6; // esi
  LPVOID v7; // rcx
  LPVOID v9; // rsi
  __int64 (__fastcall *v10)(LPVOID, __int64, _QWORD, _QWORD); // r15
  _bstr_t *v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // ebx
  LPVOID v14; // rcx
  LPVOID v15; // rcx
  HRESULT v16; // eax
  LPVOID v17; // rcx
  __int64 (__fastcall *v18)(_QWORD, __int64, __int64, __int64); // r15
  IUnknown *v19; // rcx
  _bstr_t *v20; // rax
  __int64 v21; // rbx
  _bstr_t *v22; // rax
  __int64 v23; // rdx
  LPVOID v24; // rcx
  HRESULT v25; // eax
  LPVOID v26; // rcx
  LPVOID v27; // rcx
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  LPVOID v30; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v31[8]; // [rsp+58h] [rbp-20h] BYREF
  _BYTE v32[24]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v30 = 0;
  v6 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &v30);
  if ( v6 < 0 )
  {
    v7 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return (unsigned int)v6;
  }
  v9 = v30;
  v10 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)v30 + 24LL);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(unsigned __int16 **)a2;
  v11 = _bstr_t::_bstr_t((_bstr_t *)v31, a2);
  if ( *(_QWORD *)v11 )
    v12 = **(_QWORD **)v11;
  else
    v12 = 0;
  v13 = v10(v9, v12, 0, 0);
  _bstr_t::~_bstr_t((_bstr_t *)v31);
  if ( (v13 & 0x80000000) != 0 )
  {
    if ( v13 == -2147217394 )
    {
      v14 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
      }
      return 2147749902LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41D,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
      (const char *)v13,
      0);
    v15 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v13;
  }
  v16 = CoSetProxyBlanket(
          0,
          0xFFFFFFFF,
          0xFFFFFFFF,
          (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
          0,
          3u,
          (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
          0x800u);
  v13 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x427,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
      (const char *)(unsigned int)v16,
      ppv);
    v17 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v13;
  }
  v18 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(MEMORY[0] + 160LL);
  v19 = *a3;
  if ( *a3 )
  {
    *a3 = 0;
    ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
  }
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(unsigned __int16 **)a1;
  v20 = _bstr_t::_bstr_t((_bstr_t *)v32, a1);
  if ( *(_QWORD *)v20 )
    v21 = **(_QWORD **)v20;
  else
    v21 = 0;
  v22 = _bstr_t::_bstr_t((_bstr_t *)v31, L"WQL");
  if ( *(_QWORD *)v22 )
    v23 = **(_QWORD **)v22;
  else
    v23 = 0;
  v13 = v18(0, v23, v21, 48);
  _bstr_t::~_bstr_t((_bstr_t *)v31);
  _bstr_t::~_bstr_t((_bstr_t *)v32);
  if ( (v13 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
      (const char *)v13,
      0);
    v24 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return v13;
  }
  v25 = CoSetProxyBlanket(
          *a3,
          0xFFFFFFFF,
          0xFFFFFFFF,
          (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
          0,
          3u,
          (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
          0x800u);
  v13 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x436,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\utils.cpp",
      (const char *)(unsigned int)v25,
      ppva);
    v26 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
    }
    return v13;
  }
  v27 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  }
  return 0;
}

```

## disassembly

```asm
0x1800d210c  push    rbp
0x1800d210e  push    rbx
0x1800d210f  push    rsi
0x1800d2110  push    rdi
0x1800d2111  push    r12
0x1800d2113  push    r13
0x1800d2115  push    r14
0x1800d2117  push    r15
0x1800d2119  mov     rbp, rsp
0x1800d211c  sub     rsp, 78h
0x1800d2120  mov     r14, r8
0x1800d2123  mov     rbx, rdx
0x1800d2126  mov     rdi, rcx
0x1800d2129  xor     r12d, r12d
0x1800d212c  mov     [rbp+var_28], r12
0x1800d2130  mov     [rbp+pProxy], r12
0x1800d2134  lea     rax, [rbp+var_28]
0x1800d2138  mov     [rsp+78h+ppv], rax; ppv
0x1800d213d  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x1800d2144  xor     edx, edx; pUnkOuter
0x1800d2146  lea     r8d, [r12+1]; dwClsContext
0x1800d214b  lea     rcx, CLSID_WbemLocator; rclsid
0x1800d2152  call    cs:__imp_CoCreateInstance
0x1800d2158  mov     esi, eax
0x1800d215a  test    eax, eax
0x1800d215c  jns     short loc_1800D2199
0x1800d215e  mov     rcx, [rbp+pProxy]
0x1800d2162  test    rcx, rcx
0x1800d2165  jz      short loc_1800D2178
0x1800d2167  mov     [rbp+pProxy], r12
0x1800d216b  mov     rdx, [rcx]
0x1800d216e  mov     rax, [rdx+10h]
0x1800d2172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2177  nop
0x1800d2178  mov     rcx, [rbp+var_28]
0x1800d217c  test    rcx, rcx
0x1800d217f  jz      short loc_1800D2192
0x1800d2181  mov     [rbp+var_28], r12
0x1800d2185  mov     rax, [rcx]
0x1800d2188  mov     rax, [rax+10h]
0x1800d218c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2191  nop
0x1800d2192  mov     eax, esi
0x1800d2194  jmp     loc_1800D24FA
0x1800d2199  mov     rsi, [rbp+var_28]
0x1800d219d  mov     rax, [rsi]
0x1800d21a0  mov     r15, [rax+18h]
0x1800d21a4  mov     rcx, [rbp+pProxy]
0x1800d21a8  test    rcx, rcx
0x1800d21ab  jz      short loc_1800D21BE
0x1800d21ad  mov     [rbp+pProxy], r12
0x1800d21b1  mov     rax, [rcx]
0x1800d21b4  mov     rax, [rax+10h]
0x1800d21b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d21bd  nop
0x1800d21be  cmp     qword ptr [rbx+18h], 7
0x1800d21c3  jbe     short loc_1800D21C8
0x1800d21c5  mov     rbx, [rbx]
0x1800d21c8  mov     rdx, rbx; unsigned __int16 *
0x1800d21cb  lea     rcx, [rbp+var_20]; this
0x1800d21cf  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800d21d4  nop
0x1800d21d5  mov     rcx, [rax]
0x1800d21d8  test    rcx, rcx
0x1800d21db  jz      short loc_1800D21E2
0x1800d21dd  mov     rdx, [rcx]
0x1800d21e0  jmp     short loc_1800D21E5
0x1800d21e2  mov     rdx, r12
0x1800d21e5  lea     rax, [rbp+pProxy]
0x1800d21e9  mov     [rsp+78h+var_38], rax
0x1800d21ee  mov     qword ptr [rsp+78h+dwCapabilities], r12
0x1800d21f3  mov     [rsp+78h+pAuthInfo], r12
0x1800d21f8  mov     [rsp+78h+dwImpLevel], r12d
0x1800d21fd  mov     [rsp+78h+ppv], r12; int
0x1800d2202  xor     r9d, r9d
0x1800d2205  xor     r8d, r8d
0x1800d2208  mov     rcx, rsi
0x1800d220b  mov     rax, r15
0x1800d220e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2213  mov     ebx, eax
0x1800d2215  lea     rcx, [rbp+var_20]; this
0x1800d2219  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800d221e  test    ebx, ebx
0x1800d2220  jns     loc_1800D22BE
0x1800d2226  mov     edi, 8004100Eh
0x1800d222b  cmp     ebx, edi
0x1800d222d  jnz     short loc_1800D226A
0x1800d222f  mov     rcx, [rbp+pProxy]
0x1800d2233  test    rcx, rcx
0x1800d2236  jz      short loc_1800D2249
0x1800d2238  mov     [rbp+pProxy], r12
0x1800d223c  mov     rax, [rcx]
0x1800d223f  mov     rax, [rax+10h]
0x1800d2243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2248  nop
0x1800d2249  mov     rcx, [rbp+var_28]
0x1800d224d  test    rcx, rcx
0x1800d2250  jz      short loc_1800D2263
0x1800d2252  mov     [rbp+var_28], r12
0x1800d2256  mov     rdx, [rcx]
0x1800d2259  mov     rax, [rdx+10h]
0x1800d225d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2262  nop
0x1800d2263  mov     eax, edi
0x1800d2265  jmp     loc_1800D24FA
0x1800d226a  mov     rcx, [rbp+40h]; this
0x1800d226e  mov     r9d, ebx; char *
0x1800d2271  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d2278  mov     edx, 41Dh; void *
0x1800d227d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2282  nop
0x1800d2283  mov     rcx, [rbp+pProxy]
0x1800d2287  test    rcx, rcx
0x1800d228a  jz      short loc_1800D229D
0x1800d228c  mov     [rbp+pProxy], r12
0x1800d2290  mov     rax, [rcx]
0x1800d2293  mov     rax, [rax+10h]
0x1800d2297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d229c  nop
0x1800d229d  mov     rcx, [rbp+var_28]
0x1800d22a1  test    rcx, rcx
0x1800d22a4  jz      short loc_1800D22B7
0x1800d22a6  mov     [rbp+var_28], r12
0x1800d22aa  mov     rax, [rcx]
0x1800d22ad  mov     rax, [rax+10h]
0x1800d22b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d22b6  nop
0x1800d22b7  mov     eax, ebx
0x1800d22b9  jmp     loc_1800D24FA
0x1800d22be  mov     [rsp+78h+dwCapabilities], 800h; dwCapabilities
0x1800d22c6  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800d22ca  mov     [rsp+78h+pAuthInfo], r13; pAuthInfo
0x1800d22cf  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x1800d22d7  mov     dword ptr [rsp+78h+ppv], r12d; int
0x1800d22dc  mov     r9, r13; pServerPrincName
0x1800d22df  or      eax, 0FFFFFFFFh
0x1800d22e2  mov     r8d, eax; dwAuthzSvc
0x1800d22e5  mov     edx, eax; dwAuthnSvc
0x1800d22e7  mov     rcx, [rbp+pProxy]; pProxy
0x1800d22eb  call    cs:__imp_CoSetProxyBlanket
0x1800d22f1  mov     ebx, eax
0x1800d22f3  test    eax, eax
0x1800d22f5  jns     short loc_1800D2349
0x1800d22f7  mov     rcx, [rbp+40h]; this
0x1800d22fb  mov     r9d, eax; char *
0x1800d22fe  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d2305  mov     edx, 427h; void *
0x1800d230a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d230f  nop
0x1800d2310  mov     rcx, [rbp+pProxy]
0x1800d2314  test    rcx, rcx
0x1800d2317  jz      short loc_1800D232A
0x1800d2319  mov     [rbp+pProxy], r12
0x1800d231d  mov     rax, [rcx]
0x1800d2320  mov     rax, [rax+10h]
0x1800d2324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2329  nop
0x1800d232a  mov     rcx, [rbp+var_28]
0x1800d232e  test    rcx, rcx
0x1800d2331  jz      short loc_1800D2344
0x1800d2333  mov     [rbp+var_28], r12
0x1800d2337  mov     rax, [rcx]
0x1800d233a  mov     rax, [rax+10h]
0x1800d233e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2343  nop
0x1800d2344  jmp     loc_1800D22B7
0x1800d2349  mov     rsi, [rbp+pProxy]
0x1800d234d  mov     rax, [rsi]
0x1800d2350  mov     r15, [rax+0A0h]
0x1800d2357  mov     rcx, [r14]
0x1800d235a  test    rcx, rcx
0x1800d235d  jz      short loc_1800D236F
0x1800d235f  mov     [r14], r12
0x1800d2362  mov     rax, [rcx]
0x1800d2365  mov     rax, [rax+10h]
0x1800d2369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d236e  nop
0x1800d236f  cmp     qword ptr [rdi+18h], 7
0x1800d2374  jbe     short loc_1800D2379
0x1800d2376  mov     rdi, [rdi]
0x1800d2379  mov     rdx, rdi; unsigned __int16 *
0x1800d237c  lea     rcx, [rbp+var_18]; this
0x1800d2380  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800d2385  nop
0x1800d2386  mov     rcx, [rax]
0x1800d2389  test    rcx, rcx
0x1800d238c  jz      short loc_1800D2393
0x1800d238e  mov     rbx, [rcx]
0x1800d2391  jmp     short loc_1800D2396
0x1800d2393  mov     rbx, r12
0x1800d2396  lea     rdx, aWql; "WQL"
0x1800d239d  lea     rcx, [rbp+var_20]; this
0x1800d23a1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800d23a6  nop
0x1800d23a7  mov     rcx, [rax]
0x1800d23aa  test    rcx, rcx
0x1800d23ad  jz      short loc_1800D23B4
0x1800d23af  mov     rdx, [rcx]
0x1800d23b2  jmp     short loc_1800D23B7
0x1800d23b4  mov     rdx, r12
0x1800d23b7  mov     qword ptr [rsp+78h+dwImpLevel], r14
0x1800d23bc  mov     [rsp+78h+ppv], r12; int
0x1800d23c1  mov     r9d, 30h ; '0'
0x1800d23c7  mov     r8, rbx
0x1800d23ca  mov     rcx, rsi
0x1800d23cd  mov     rax, r15
0x1800d23d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d23d5  mov     ebx, eax
0x1800d23d7  lea     rcx, [rbp+var_20]; this
0x1800d23db  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800d23e0  nop
0x1800d23e1  lea     rcx, [rbp+var_18]; this
0x1800d23e5  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800d23ea  test    ebx, ebx
0x1800d23ec  jns     short loc_1800D2440
0x1800d23ee  mov     rcx, [rbp+40h]; this
0x1800d23f2  mov     r9d, ebx; char *
0x1800d23f5  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d23fc  mov     edx, 42Dh; void *
0x1800d2401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2406  nop
0x1800d2407  mov     rcx, [rbp+pProxy]
0x1800d240b  test    rcx, rcx
0x1800d240e  jz      short loc_1800D2421
0x1800d2410  mov     [rbp+pProxy], r12
0x1800d2414  mov     rax, [rcx]
0x1800d2417  mov     rax, [rax+10h]
0x1800d241b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2420  nop
0x1800d2421  mov     rcx, [rbp+var_28]
0x1800d2425  test    rcx, rcx
0x1800d2428  jz      short loc_1800D243B
0x1800d242a  mov     [rbp+var_28], r12
0x1800d242e  mov     rax, [rcx]
0x1800d2431  mov     rax, [rax+10h]
0x1800d2435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d243a  nop
0x1800d243b  jmp     loc_1800D22B7
0x1800d2440  mov     [rsp+78h+dwCapabilities], 800h; dwCapabilities
0x1800d2448  mov     [rsp+78h+pAuthInfo], r13; pAuthInfo
0x1800d244d  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x1800d2455  mov     dword ptr [rsp+78h+ppv], r12d; int
0x1800d245a  mov     r9, r13; pServerPrincName
0x1800d245d  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800d2460  mov     r8d, edx; dwAuthzSvc
0x1800d2463  mov     rcx, [r14]; pProxy
0x1800d2466  call    cs:__imp_CoSetProxyBlanket
0x1800d246c  mov     ebx, eax
0x1800d246e  test    eax, eax
0x1800d2470  jns     short loc_1800D24C4
0x1800d2472  mov     rcx, [rbp+40h]; this
0x1800d2476  mov     r9d, eax; char *
0x1800d2479  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appcompat\\programs\\dev"...
0x1800d2480  mov     edx, 436h; void *
0x1800d2485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d248a  nop
0x1800d248b  mov     rcx, [rbp+pProxy]
0x1800d248f  test    rcx, rcx
0x1800d2492  jz      short loc_1800D24A5
0x1800d2494  mov     [rbp+pProxy], r12
0x1800d2498  mov     rax, [rcx]
0x1800d249b  mov     rax, [rax+10h]
0x1800d249f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d24a4  nop
0x1800d24a5  mov     rcx, [rbp+var_28]
0x1800d24a9  test    rcx, rcx
0x1800d24ac  jz      short loc_1800D24BF
0x1800d24ae  mov     [rbp+var_28], r12
0x1800d24b2  mov     rax, [rcx]
0x1800d24b5  mov     rax, [rax+10h]
0x1800d24b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d24be  nop
0x1800d24bf  jmp     loc_1800D22B7
0x1800d24c4  mov     rcx, [rbp+pProxy]
0x1800d24c8  test    rcx, rcx
0x1800d24cb  jz      short loc_1800D24DE
0x1800d24cd  mov     [rbp+pProxy], r12
0x1800d24d1  mov     rax, [rcx]
0x1800d24d4  mov     rax, [rax+10h]
0x1800d24d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d24dd  nop
0x1800d24de  mov     rcx, [rbp+var_28]
0x1800d24e2  test    rcx, rcx
0x1800d24e5  jz      short loc_1800D24F8
0x1800d24e7  mov     [rbp+var_28], r12
0x1800d24eb  mov     rax, [rcx]
0x1800d24ee  mov     rax, [rax+10h]
0x1800d24f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d24f7  nop
0x1800d24f8  xor     eax, eax
0x1800d24fa  add     rsp, 78h
0x1800d24fe  pop     r15
0x1800d2500  pop     r14
0x1800d2502  pop     r13
0x1800d2504  pop     r12
0x1800d2506  pop     rdi
0x1800d2507  pop     rsi
0x1800d2508  pop     rbx
0x1800d2509  pop     rbp
0x1800d250a  retn
  ... truncated ...
```
