# RepoMan::Legacy::Descriptor::LoadDocument(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180194664`
- end: `0x180194b26`
- name: `?LoadDocument@Descriptor@Legacy@RepoMan@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1218`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800c6430`

## callees

- `0x180002010`
- `0x180013b14`
- `0x1800245b4`
- `0x18002d958`
- `0x18003e358`
- `0x180045350`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18018e288`
- `0x180194664`
- `0x180194e04`
- `0x1801951a8`
- `0x18019561c`
- `0x180195ad0`
- `0x18019a840`
- `0x18019f7a0`
- `0x18019f800`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180194856`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180194856`
- `OLEAUT32!__imp_SysFreeString` at `0x180194a96`
- `OLEAUT32!__imp_SysFreeString` at `0x180194a96`
- `OLEAUT32!__imp_VariantInit` at `0x18019480b`
- `OLEAUT32!__imp_VariantInit` at `0x18019480b`
- `OLEAUT32!__imp_VariantClear` at `0x180194a6f`
- `OLEAUT32!__imp_VariantClear` at `0x180194aa7`
- `OLEAUT32!__imp_VariantClear` at `0x180194a6f`
- `OLEAUT32!__imp_VariantClear` at `0x180194aa7`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18019471c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18019471c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801948b4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801948b4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180194787`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801948ad`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180194787`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801948ad`
- `ole32!CoCreateInstance` at `0x1801947c8`
- `ole32!CoCreateInstance` at `0x1801947c8`
- `ole32!CoInitializeEx` at `0x1801946a2`
- `ole32!CoInitializeEx` at `0x1801946a2`

## string_xrefs

- `0x1801946aa`: `src\repoman\src\reposhared\pal\masterdescriptor\win32\masterdescriptor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall RepoMan::Legacy::Descriptor::LoadDocument(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // eax
  const char *v5; // r9
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // rdx
  void *v12; // rcx
  _QWORD *v13; // rcx
  LPVOID v14; // rcx
  unsigned int v15; // eax
  const char *v16; // r9
  unsigned int v17; // eax
  const char *v18; // r9
  const OLECHAR *v19; // rcx
  OLECHAR *v20; // rbx
  OLECHAR *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // eax
  const char *v24; // r9
  __int64 v25; // rax
  unsigned int v26; // eax
  const char *v27; // r9
  unsigned int v28; // eax
  const char *v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  void **v32; // rcx
  size_t v33; // rsi
  void *v34; // r15
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rcx
  LONGLONG v39; // rcx
  LPVOID v40; // rcx
  int Reserved; // [rsp+20h] [rbp-E0h]
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v43; // [rsp+38h] [rbp-C8h] BYREF
  char v44[8]; // [rsp+40h] [rbp-C0h] BYREF
  LONGLONG v45; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  char v47[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v49; // [rsp+68h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-90h]
  __int64 v51; // [rsp+78h] [rbp-88h]
  int v52; // [rsp+80h] [rbp-80h]
  VARIANTARG v53; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  char v55; // [rsp+C8h] [rbp-38h]
  VARIANTARG v56; // [rsp+D0h] [rbp-30h] BYREF
  char v57; // [rsp+E8h] [rbp-18h]
  OLECHAR *v58; // [rsp+F0h] [rbp-10h]
  OLECHAR *strIn[2]; // [rsp+F8h] [rbp-8h] BYREF
  UINT ui[4]; // [rsp+108h] [rbp+8h]

  ppv = 0;
  v4 = CoInitializeEx(0, 0);
  RepoMan::RaiseExceptionIfFailed(
    (RepoMan *)v4,
    225,
    (int)"src\\repoman\\src\\reposhared\\pal\\masterdescriptor\\win32\\masterdescriptor.cpp",
    v5);
  std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(v47);
  v52 = 0;
  v6 = v49;
  if ( v49 <= v51 + 1 )
  {
    std::deque<std::function<void (void)>>::_Growmap(v47);
    v6 = v49;
  }
  v7 = v6 - 1;
  v8 = (v6 - 1) & v50;
  v50 = v8;
  if ( !v8 )
    v8 = v6;
  v9 = v8 - 1;
  v10 = v7 & v9;
  v11 = v48;
  if ( !*(_QWORD *)(v48 + 8 * (v7 & v9)) )
  {
    v12 = malloc(0x40u);
    if ( !v12 )
      std::_Xbad_alloc();
    *(_QWORD *)(v48 + 8 * v10) = v12;
    v6 = v49;
    v11 = v48;
  }
  v13 = *(_QWORD **)(v11 + 8 * (v9 & (v6 - 1)));
  *v13 = off_1801DB220;
  v13[1] = &ppv;
  v13[7] = v13;
  v50 = v9;
  if ( !++v51 )
    _invoke_watson(0, 0, 0, 0, 0);
  v14 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = CoCreateInstance(
          &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
          0,
          1u,
          &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
          &ppv);
  RepoMan::RaiseExceptionIfFailed(
    (RepoMan *)v15,
    231,
    (int)"src\\repoman\\src\\reposhared\\pal\\masterdescriptor\\win32\\masterdescriptor.cpp",
    v16);
  v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  RepoMan::RaiseExceptionIfFailed(
    (RepoMan *)v17,
    232,
    (int)"src\\repoman\\src\\reposhared\\pal\\masterdescriptor\\win32\\masterdescriptor.cpp",
    v18);
  v55 = 1;
  VariantInit(&pvarg);
  pvarg.vt = 11;
  pvarg.iVal = -1;
  *(_OWORD *)strIn = 0;
  *(_OWORD *)ui = 0;
  std::wstring::_Construct<1,wchar_t const *>(strIn, L"NewParser", 9);
  v19 = (const OLECHAR *)strIn;
  if ( *(_QWORD *)&ui[2] > 7u )
    v19 = strIn[0];
  v20 = SysAllocStringLen(v19, ui[0]);
  v58 = v20;
  if ( !v20 )
    RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
      39,
      (unsigned int)"src\\repoman\\src\\reposhared\\pal\\masterdescriptor\\win32\\masterdescriptor.cpp",
      (unsigned int)"SysAllocStringLen failed!",
      -2147024882,
      8);
  if ( *(_QWORD *)&ui[2] > 7u )
  {
    v21 = strIn[0];
    if ( (unsigned __int64)(2LL * *(_QWORD *)&ui[2] + 2) >= 0x1000 )
    {
      v21 = (OLECHAR *)*((_QWORD *)strIn[0] - 1);
      if ( (unsigned __int64)((char *)strIn[0] - (char *)v21 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v21);
  }
  strIn[0] = (OLECHAR *)19937;
  *(__m128i *)ui = _mm_load_si128((const __m128i *)&_xmm);
  v22 = *(_QWORD *)ppv;
  v53 = pvarg;
  v23 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(v22 + 640))(ppv, v20, &v53);
  RepoMan::RaiseExceptionIfFailed(
    (RepoMan *)v23,
    237,
    (int)"src\\repoman\\src\\reposhared\\pal\\masterdescriptor\\win32\\masterdescriptor.cpp",
    v24);
  v46 = 0;
  LOBYTE(Reserved) = 0;
  RepoMan::FileSystem::OpenFileAsStream(&v45, a1, 0, &v46, Reserved);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  v57 = 0;
  v56.vt = 13;
  v56.llVal = v45;
  v25 = *(_QWORD *)ppv;
  v53 = v56;
  v26 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, char *))(v25 + 464))(ppv, &v53, v44);
  RepoMan::RaiseExceptionIfFailed(
    (RepoMan *)v26,
    242,
    (int)"src\\repoman\\src\\reposhared\\pal\\masterdescriptor\\win32\\masterdescriptor.cpp",
    v27);
  v43 = 0;
  v28 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 360LL))(ppv, &v43);
  RepoMan::RaiseExceptionIfFailed(
    (RepoMan *)v28,
    245,
    (int)"src\\repoman\\src\\reposhared\\pal\\masterdescriptor\\win32\\masterdescriptor.cpp",
    v29);
  v32 = (void **)(a1 + 120);
  if ( (_QWORD *)(a1 + 120) != a2 )
  {
    v33 = a2[2];
    if ( a2[3] > 0xFu )
      a2 = (_QWORD *)*a2;
    if ( v33 > *(_QWORD *)(a1 + 144) )
    {
      ____Reallocate_for_V_lambda_1___1__assign___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34_QEBD_K_Z_PEBD___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__assign_01_QEAAAEAV01_QEBD0_Z_PEBD_Z(
        v32,
        v33,
        v31,
        a2);
    }
    else
    {
      v34 = (void *)(a1 + 120);
      if ( *(_QWORD *)(a1 + 144) > 0xFu )
        v34 = *v32;
      *(_QWORD *)(a1 + 136) = v33;
      memmove(v34, a2, v33);
      *((_BYTE *)v34 + v33) = 0;
    }
  }
  sub_180194E04(&v43, v30, a1);
  sub_1801951A8(&v43, v35, a1);
  sub_18019561C(&v43, v36, a1);
  sub_180195AD0(&v43, v37, a1);
  v38 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  if ( v57 )
    VariantClear(&v56);
  v39 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v39 + 16LL))(v39);
  }
  SysFreeString(v20);
  if ( v55 )
    VariantClear(&pvarg);
  RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v47);
  v40 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40 + 16LL))(v40);
  }
}

```

## disassembly

```asm
0x180194664  mov     [rsp-8+arg_10], rbx
0x180194669  mov     [rsp-8+arg_18], rsi
0x18019466e  push    rbp
0x18019466f  push    rdi
0x180194670  push    r12
0x180194672  push    r14
0x180194674  push    r15
0x180194676  lea     rbp, [rsp-20h]
0x18019467b  sub     rsp, 120h
0x180194682  mov     rax, cs:__security_cookie
0x180194689  xor     rax, rsp
0x18019468c  mov     [rbp+40h+var_28], rax
0x180194690  mov     rdi, rdx
0x180194693  mov     r14, rcx
0x180194696  xor     r12d, r12d
0x180194699  mov     [rsp+140h+ppv], r12
0x18019469e  xor     edx, edx; dwCoInit
0x1801946a0  xor     ecx, ecx; pvReserved
0x1801946a2  call    cs:__imp_CoInitializeEx
0x1801946a8  mov     ecx, eax; this
0x1801946aa  lea     r15, aSrcRepomanSrcR_18; "src\\repoman\\src\\reposhared\\pal\\mas"...
0x1801946b1  mov     r8, r15; int
0x1801946b4  mov     edx, 0E1h; int
0x1801946b9  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1801946be  nop
0x1801946bf  lea     rcx, [rsp+140h+var_E8]
0x1801946c4  call    ??0?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(void)
0x1801946c9  mov     [rbp+40h+var_C0], r12d
0x1801946cd  mov     rax, [rsp+140h+var_C8]
0x1801946d2  inc     rax
0x1801946d5  mov     rcx, [rsp+140h+var_D8]
0x1801946da  cmp     rcx, rax
0x1801946dd  ja      short loc_1801946EE
0x1801946df  lea     rcx, [rsp+140h+var_E8]
0x1801946e4  call    ?_Growmap@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAX_K@Z; std::deque<std::function<void (void)>>::_Growmap(unsigned __int64)
0x1801946e9  mov     rcx, [rsp+140h+var_D8]
0x1801946ee  lea     rax, [rcx-1]
0x1801946f2  mov     rbx, [rsp+140h+var_D0]
0x1801946f7  and     rbx, rax
0x1801946fa  mov     [rsp+140h+var_D0], rbx
0x1801946ff  cmovz   rbx, rcx
0x180194703  dec     rbx
0x180194706  mov     rsi, rbx
0x180194709  and     rsi, rax
0x18019470c  mov     rdx, [rsp+140h+var_E0]
0x180194711  cmp     [rdx+rsi*8], r12
0x180194715  jnz     short loc_180194741
0x180194717  mov     ecx, 40h ; '@'; Size
0x18019471c  call    cs:__imp_malloc
0x180194722  mov     rcx, rax
0x180194725  test    rax, rax
0x180194728  jz      loc_180194B20
0x18019472e  mov     rax, [rsp+140h+var_E0]
0x180194733  mov     [rax+rsi*8], rcx
0x180194737  mov     rcx, [rsp+140h+var_D8]
0x18019473c  mov     rdx, [rsp+140h+var_E0]
0x180194741  lea     rax, [rcx-1]
0x180194745  and     rax, rbx
0x180194748  mov     rcx, [rdx+rax*8]
0x18019474c  lea     rax, off_1801DB220
0x180194753  mov     [rcx], rax
0x180194756  lea     rax, [rsp+140h+ppv]
0x18019475b  mov     [rcx+8], rax
0x18019475f  mov     [rcx+38h], rcx
0x180194763  mov     [rsp+140h+var_D0], rbx
0x180194768  mov     rax, [rsp+140h+var_C8]
0x18019476d  add     rax, 1
0x180194771  mov     [rsp+140h+var_C8], rax
0x180194776  jnz     short loc_18019478E
0x180194778  mov     qword ptr [rsp+140h+Reserved], r12; Reserved
0x18019477d  xor     r9d, r9d; LineNo
0x180194780  xor     r8d, r8d; FileName
0x180194783  xor     edx, edx; FunctionName
0x180194785  xor     ecx, ecx; Expression
0x180194787  call    cs:__imp__invoke_watson
0x18019478e  mov     rcx, [rsp+140h+ppv]
0x180194793  test    rcx, rcx
0x180194796  jz      short loc_1801947AA
0x180194798  mov     [rsp+140h+ppv], r12
0x18019479d  mov     rax, [rcx]
0x1801947a0  mov     rax, [rax+10h]
0x1801947a4  call    cs:__guard_dispatch_icall_fptr
0x1801947aa  lea     rax, [rsp+140h+ppv]
0x1801947af  mov     qword ptr [rsp+140h+Reserved], rax; ppv
0x1801947b4  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x1801947bb  xor     edx, edx; pUnkOuter
0x1801947bd  lea     r8d, [rdx+1]; dwClsContext
0x1801947c1  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1801947c8  call    cs:__imp_CoCreateInstance
0x1801947ce  mov     ecx, eax; this
0x1801947d0  mov     r8, r15; int
0x1801947d3  mov     edx, 0E7h; int
0x1801947d8  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1801947dd  mov     rcx, [rsp+140h+ppv]
0x1801947e2  mov     rax, [rcx]
0x1801947e5  xor     edx, edx
0x1801947e7  mov     rax, [rax+1F8h]
0x1801947ee  call    cs:__guard_dispatch_icall_fptr
0x1801947f4  mov     ecx, eax; this
0x1801947f6  mov     r8, r15; int
0x1801947f9  mov     edx, 0E8h; int
0x1801947fe  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x180194803  mov     [rbp+40h+var_78], 1
0x180194807  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18019480b  call    cs:__imp_VariantInit
0x180194811  mov     eax, 0Bh
0x180194816  mov     word ptr [rbp+40h+pvarg], ax
0x18019481a  or      eax, 0FFFFFFFFh
0x18019481d  mov     word ptr [rbp+40h+pvarg+8], ax
0x180194821  xorps   xmm0, xmm0
0x180194824  movups  xmmword ptr [rbp+40h+strIn], xmm0
0x180194828  xorps   xmm1, xmm1
0x18019482b  movdqu  xmmword ptr [rbp+40h+ui], xmm1
0x180194830  lea     r8d, [rax+0Ah]
0x180194834  lea     rdx, aNewparser; "NewParser"
0x18019483b  lea     rcx, [rbp+40h+strIn]
0x18019483f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180194844  nop
0x180194845  lea     rcx, [rbp+40h+strIn]
0x180194849  cmp     qword ptr [rbp+40h+ui+8], 7
0x18019484e  cmova   rcx, [rbp+40h+strIn]; strIn
0x180194853  mov     edx, [rbp+40h+ui]; ui
0x180194856  call    cs:__imp_SysAllocStringLen
0x18019485c  mov     rbx, rax
0x18019485f  mov     [rbp+40h+var_50], rax
0x180194863  test    rax, rax
0x180194866  jz      loc_180194AFD
0x18019486c  mov     rax, qword ptr [rbp+40h+ui+8]
0x180194870  cmp     rax, 7
0x180194874  jbe     short loc_1801948BA
0x180194876  mov     rcx, [rbp+40h+strIn]; Block
0x18019487a  mov     rdx, rcx
0x18019487d  lea     rax, ds:2[rax*2]
0x180194885  cmp     rax, 1000h
0x18019488b  jb      short loc_1801948B4
0x18019488d  mov     rcx, [rcx-8]
0x180194891  sub     rdx, rcx
0x180194894  lea     rax, [rdx-8]
0x180194898  cmp     rax, 1Fh
0x18019489c  jbe     short loc_1801948B4
0x18019489e  mov     qword ptr [rsp+140h+Reserved], r12; Reserved
0x1801948a3  xor     r9d, r9d; LineNo
0x1801948a6  xor     r8d, r8d; FileName
0x1801948a9  xor     edx, edx; FunctionName
0x1801948ab  xor     ecx, ecx; Expression
0x1801948ad  call    cs:__imp__invoke_watson
0x1801948b4  call    cs:__imp_free
0x1801948ba  mov     [rbp+40h+strIn], 4DE1h
0x1801948c2  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1801948ca  movdqu  xmmword ptr [rbp+40h+ui], xmm0
0x1801948cf  mov     rcx, [rsp+140h+ppv]
0x1801948d4  mov     rax, [rcx]
0x1801948d7  movups  xmm0, xmmword ptr [rbp+40h+pvarg]
0x1801948db  movaps  [rbp+40h+var_B0], xmm0
0x1801948df  movsd   xmm1, qword ptr [rbp+40h+pvarg+10h]
0x1801948e4  movsd   [rbp+40h+var_A0], xmm1
0x1801948e9  lea     r8, [rbp+40h+var_B0]
0x1801948ed  mov     rdx, rbx
0x1801948f0  mov     rax, [rax+280h]
0x1801948f7  call    cs:__guard_dispatch_icall_fptr
0x1801948fd  mov     ecx, eax; this
0x1801948ff  mov     r8, r15; int
0x180194902  mov     edx, 0EDh; int
0x180194907  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18019490c  mov     [rsp+140h+var_F0], r12
0x180194911  mov     byte ptr [rsp+140h+Reserved], r12b
0x180194916  lea     r9, [rsp+140h+var_F0]
0x18019491b  xor     r8d, r8d
0x18019491e  mov     rdx, r14
0x180194921  lea     rcx, [rsp+140h+var_F8]
0x180194926  call    ?OpenFileAsStream@FileSystem@RepoMan@@YA?AV?$ComPtr@UIStream@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4OpenMode@12@AEBV?$ComPtr@UIRepoProgress@@@2@W4OpenFlags@@@Z; RepoMan::FileSystem::OpenFileAsStream(std::string const &,RepoMan::FileSystem::OpenMode,RepoMan::ComPtr<IRepoProgress> const &,OpenFlags)
0x18019492b  nop
0x18019492c  mov     rcx, [rsp+140h+var_F0]
0x180194931  test    rcx, rcx
0x180194934  jz      short loc_180194943
0x180194936  mov     rax, [rcx]
0x180194939  mov     rax, [rax+10h]
0x18019493d  call    cs:__guard_dispatch_icall_fptr
0x180194943  mov     [rbp+40h+var_58], r12b
0x180194947  mov     eax, 0Dh
0x18019494c  mov     word ptr [rbp+40h+var_70], ax
0x180194950  mov     rax, [rsp+140h+var_F8]
0x180194955  mov     qword ptr [rbp+40h+var_70+8], rax
0x180194959  mov     rcx, [rsp+140h+ppv]
0x18019495e  mov     rax, [rcx]
0x180194961  movups  xmm0, xmmword ptr [rbp+40h+var_70]
0x180194965  movaps  [rbp+40h+var_B0], xmm0
0x180194969  movsd   xmm1, qword ptr [rbp+40h+var_70+10h]
0x18019496e  movsd   [rbp+40h+var_A0], xmm1
0x180194973  lea     r8, [rsp+140h+var_100]
0x180194978  lea     rdx, [rbp+40h+var_B0]
0x18019497c  mov     rax, [rax+1D0h]
0x180194983  call    cs:__guard_dispatch_icall_fptr
0x180194989  mov     ecx, eax; this
0x18019498b  mov     r8, r15; int
0x18019498e  mov     edx, 0F2h; int
0x180194993  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x180194998  mov     [rsp+140h+var_108], r12
0x18019499d  mov     rcx, [rsp+140h+ppv]
0x1801949a2  mov     rax, [rcx]
0x1801949a5  lea     rdx, [rsp+140h+var_108]
0x1801949aa  mov     rax, [rax+168h]
0x1801949b1  call    cs:__guard_dispatch_icall_fptr
0x1801949b7  mov     ecx, eax; this
0x1801949b9  mov     r8, r15; int
0x1801949bc  mov     edx, 0F5h; int
0x1801949c1  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1801949c6  lea     rcx, [r14+78h]
0x1801949ca  cmp     rcx, rdi
0x1801949cd  jz      short loc_180194A13
0x1801949cf  mov     rsi, [rdi+10h]
0x1801949d3  cmp     qword ptr [rdi+18h], 0Fh
0x1801949d8  jbe     short loc_1801949DD
0x1801949da  mov     rdi, [rdi]
0x1801949dd  cmp     rsi, [rcx+18h]
0x1801949e1  ja      short loc_180194A08
0x1801949e3  mov     r15, rcx
0x1801949e6  cmp     qword ptr [rcx+18h], 0Fh
0x1801949eb  jbe     short loc_1801949F0
0x1801949ed  mov     r15, [rcx]
0x1801949f0  mov     [rcx+10h], rsi
0x1801949f4  mov     r8, rsi; Size
0x1801949f7  mov     rdx, rdi; Src
0x1801949fa  mov     rcx, r15; void *
0x1801949fd  call    memmove
0x180194a02  mov     [rsi+r15], r12b
0x180194a06  jmp     short loc_180194A13
0x180194a08  mov     r9, rdi
0x180194a0b  mov     rdx, rsi
0x180194a0e  call    ??$_Reallocate_for@V_lambda_1_@?1??assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@QEBD_K@Z@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??assign@01@QEAAAEAV01@QEBD0@Z@PEBD@Z; std::string::_Reallocate_for<`std::string::assign(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *>(unsigned __int64,`std::string::assign(char const * const,unsigned __int64)'::`2'::_lambda_1_,char const *)
0x180194a13  mov     r8, r14
0x180194a16  lea     rcx, [rsp+140h+var_108]
0x180194a1b  call    sub_180194E04
0x180194a20  mov     r8, r14
0x180194a23  lea     rcx, [rsp+140h+var_108]
0x180194a28  call    sub_1801951A8
0x180194a2d  mov     r8, r14
0x180194a30  lea     rcx, [rsp+140h+var_108]
0x180194a35  call    sub_18019561C
0x180194a3a  mov     r8, r14
0x180194a3d  lea     rcx, [rsp+140h+var_108]
0x180194a42  call    sub_180195AD0
0x180194a47  nop
0x180194a48  mov     rcx, [rsp+140h+var_108]
0x180194a4d  test    rcx, rcx
0x180194a50  jz      short loc_180194A65
0x180194a52  mov     [rsp+140h+var_108], r12
0x180194a57  mov     rax, [rcx]
0x180194a5a  mov     rax, [rax+10h]
0x180194a5e  call    cs:__guard_dispatch_icall_fptr
0x180194a64  nop
0x180194a65  cmp     [rbp+40h+var_58], r12b
0x180194a69  jz      short loc_180194A76
0x180194a6b  lea     rcx, [rbp+40h+var_70]; pvarg
0x180194a6f  call    cs:__imp_VariantClear
0x180194a75  nop
0x180194a76  mov     rcx, [rsp+140h+var_F8]
0x180194a7b  test    rcx, rcx
0x180194a7e  jz      short loc_180194A93
0x180194a80  mov     [rsp+140h+var_F8], r12
0x180194a85  mov     rax, [rcx]
0x180194a88  mov     rax, [rax+10h]
0x180194a8c  call    cs:__guard_dispatch_icall_fptr
0x180194a92  nop
0x180194a93  mov     rcx, rbx; bstrString
0x180194a96  call    cs:__imp_SysFreeString
0x180194a9c  nop
0x180194a9d  cmp     [rbp+40h+var_78], r12b
0x180194aa1  jz      short loc_180194AAE
0x180194aa3  lea     rcx, [rbp+40h+pvarg]; pvarg
0x180194aa7  call    cs:__imp_VariantClear
0x180194aad  nop
0x180194aae  lea     rcx, [rsp+140h+var_E8]; this
0x180194ab3  call    ??1ScopeGuard@Meta@RepoMan@@QEAA@XZ; RepoMan::Meta::ScopeGuard::~ScopeGuard(void)
0x180194ab8  nop
0x180194ab9  mov     rcx, [rsp+140h+ppv]
0x180194abe  test    rcx, rcx
0x180194ac1  jz      short loc_180194AD5
0x180194ac3  mov     [rsp+140h+ppv], r12
0x180194ac8  mov     rax, [rcx]
0x180194acb  mov     rax, [rax+10h]
0x180194acf  call    cs:__guard_dispatch_icall_fptr
0x180194ad5  mov     rcx, [rbp+40h+var_28]
0x180194ad9  xor     rcx, rsp; StackCookie
0x180194adc  call    __security_check_cookie
0x180194ae1  lea     r11, [rsp+140h+var_20]
0x180194ae9  mov     rbx, [r11+40h]
0x180194aed  mov     rsi, [r11+48h]
0x180194af1  mov     rsp, r11
0x180194af4  pop     r15
0x180194af6  pop     r14
0x180194af8  pop     r12
0x180194afa  pop     rdi
0x180194afb  pop     rbp
0x180194afc  retn
0x180194afd  mov     [rsp+140h+Reserved], 8
0x180194b05  mov     r9d, 8007000Eh
0x180194b0b  lea     r8, aSysallocstring; "SysAllocStringLen failed!"
0x180194b12  mov     rdx, r15
0x180194b15  mov     ecx, 27h ; '''
  ... truncated ...
```
