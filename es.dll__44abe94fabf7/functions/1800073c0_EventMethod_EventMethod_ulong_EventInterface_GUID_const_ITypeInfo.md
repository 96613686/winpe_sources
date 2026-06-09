# EventMethod::EventMethod(ulong,EventInterface &,_GUID const &,ITypeInfo *)

- ea: `0x1800073c0`
- end: `0x1800079df`
- name: `??0EventMethod@@QEAA@KAEAVEventInterface@@AEBU_GUID@@PEAUITypeInfo@@@Z`
- size: `1567`
- prototype: `EventMethod *__fastcall(EventMethod *__hidden this, unsigned int, struct EventInterface *, const struct _GUID *, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006b10`

## callees

- `0x180003d54`
- `0x180006194`
- `0x1800073c0`
- `0x180007d30`
- `0x180008938`
- `0x180012654`
- `0x180017aa0`
- `0x180043496`
- `0x1800434ba`
- `0x1800434c6`
- `0x1800434de`
- `0x180043510`
- `0x1800435a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007430`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180007430`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007925`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007925`
- `OLEAUT32!__imp_SysFreeString` at `0x180007761`
- `OLEAUT32!__imp_SysFreeString` at `0x180007950`
- `OLEAUT32!__imp_SysFreeString` at `0x1800437ab`
- `OLEAUT32!__imp_SysFreeString` at `0x180007761`
- `OLEAUT32!__imp_SysFreeString` at `0x180007950`
- `OLEAUT32!__imp_SysFreeString` at `0x1800437ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800075f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007542`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800075f2`

## string_xrefs

- `0x180007474`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800077c4`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007801`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007820`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007880`: `com\complus\src\events\tier1\agent.cpp`
- `0x180007842`: `com\complus\src\events\Shared\StringFuncs.h`

## pseudocode

```c
EventMethod *__fastcall EventMethod::EventMethod(
        EventMethod *this,
        unsigned int a2,
        struct EventInterface *a3,
        const struct _GUID *a4,
        struct ITypeInfo *a5)
{
  int v9; // r12d
  int v10; // r13d
  struct ITypeInfo *v11; // rbx
  int v12; // eax
  int v13; // ecx
  size_t v14; // r8
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  int v19; // eax
  LPVOID v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // eax
  __int64 v24; // r14
  __int64 v25; // rsi
  unsigned int v26; // ecx
  _WORD *v27; // rbx
  __int64 v28; // rax
  size_t v29; // r14
  void *v30; // rsi
  char v31; // si
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  BSTR *v36; // rbx
  __int64 v38; // [rsp+0h] [rbp-40h] BYREF
  __int64 v39; // [rsp+40h] [rbp+0h] BYREF
  __int64 v40; // [rsp+48h] [rbp+8h] BYREF
  __int16 v41; // [rsp+50h] [rbp+10h]
  unsigned int v42; // [rsp+54h] [rbp+14h] BYREF
  unsigned int *v43; // [rsp+58h] [rbp+18h] BYREF
  struct ITypeInfo *v44; // [rsp+60h] [rbp+20h]
  int v45; // [rsp+68h] [rbp+28h]
  unsigned int *v46; // [rsp+70h] [rbp+30h]
  __int64 v47; // [rsp+78h] [rbp+38h] BYREF
  wchar_t *String1; // [rsp+80h] [rbp+40h] BYREF
  __int64 *v49; // [rsp+88h] [rbp+48h]
  EventMethod *v50; // [rsp+90h] [rbp+50h]
  _QWORD *v51; // [rsp+98h] [rbp+58h]
  size_t v52; // [rsp+A0h] [rbp+60h]
  __int64 v53; // [rsp+A8h] [rbp+68h]
  __int64 *v54; // [rsp+B0h] [rbp+70h]
  ULONG_PTR Arguments[5]; // [rsp+B8h] [rbp+78h] BYREF
  unsigned __int16 Src[12]; // [rsp+E0h] [rbp+A0h] BYREF

  v54 = &v38;
  v50 = this;
  v44 = a5;
  v9 = 1;
  *(_DWORD *)this = 1;
  v10 = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 16) = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 24), 0x1F4u);
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = a4;
  *((_QWORD *)this + 13) = a3;
  *(_OWORD *)((char *)this + 88) = 0;
  v49 = 0;
  v43 = 0;
  v40 = 0;
  v11 = v44;
  v12 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, unsigned int **))v44->lpVtbl->GetFuncDesc)(v44, a2, &v43);
  if ( v12 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x347u, 0x12u, v12);
  v13 = *((__int16 *)v43 + 18);
  *((_DWORD *)this + 22) = v13;
  v42 = v13 + 1;
  v14 = 8LL * (unsigned int)(v13 + 1);
  v51 = (_QWORD *)v14;
  if ( v14 > 0xFFFFFFFF )
  {
    memset(Src, 0, 22);
    StringCchPrintfW(Src, 0xBu, L"%d", 856);
    Arguments[0] = 2147488262LL;
    Arguments[1] = 18;
    Arguments[2] = (ULONG_PTR)L"com\\complus\\src\\events\\tier1\\agent.cpp";
    Arguments[3] = (ULONG_PTR)Src;
    Arguments[4] = (ULONG_PTR)L"0";
    DoDebugBreakIfAppropriate();
    RaiseException(0xCBADF00D, 0, 5u, Arguments);
    v23 = local_unwind_0(v54, &loc_180007989);
  }
  else
  {
    v15 = (unsigned int)v14 + 15LL;
    if ( v15 <= (unsigned int)v14 )
      v15 = 0xFFFFFFFFFFFFFF0LL;
    v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
    v17 = alloca(v16);
    v18 = alloca(v16);
    a4 = (const struct _GUID *)&v39;
    v49 = &v39;
    memset_0(&v39, 0, v14);
    v19 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, __int64 *, _QWORD, unsigned int *))v11->lpVtbl->GetNames)(
            v11,
            *v43,
            &v39,
            v42,
            &v42);
    if ( v19 < 0 )
      InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x35Fu, 0x12u, v19);
    if ( v42 != *((_DWORD *)this + 22) + 1 )
      InternalAssert(
        L"com\\complus\\src\\events\\tier1\\agent.cpp",
        0x360u,
        0x12u,
        L"cNames == (unsigned int)(_paramInfo.numColumns + 1)");
    *((_QWORD *)this + 1) = v39;
    v20 = CoTaskMemAlloc(saturated_mul(*((int *)this + 22), 0x10u));
    *((_QWORD *)this + 12) = v20;
    if ( !v20 )
      InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x366u, 0xC0001204, 0x12u);
    while ( 1 )
    {
      v45 = v10;
      v22 = (unsigned int)v10;
      v23 = *((_DWORD *)this + 22);
      if ( v10 >= v23 )
        break;
      v24 = *((_QWORD *)this + 12) + 16LL * v10;
      v51 = (_QWORD *)v24;
      v25 = 32LL * v10 + *((_QWORD *)v43 + 2);
      v46 = (unsigned int *)v25;
      v41 = *(_WORD *)(v25 + 8);
      if ( v41 == 26 )
      {
        v25 = *(_QWORD *)v25;
        v46 = (unsigned int *)v25;
      }
      ++v10;
      v26 = v22 + 1;
      if ( *(&v39 + v10) )
      {
        v27 = (_WORD *)*(&v39 + (int)v26);
        if ( v27 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v27[v28] );
        }
        else
        {
          v28 = 0;
        }
        v53 = v28;
        v29 = 2LL * ((int)v28 + 1);
        v52 = v29;
        v30 = CoTaskMemAlloc((unsigned int)(2 * (v28 + 1)));
        if ( !v30 )
          InternalError(L"com\\complus\\src\\events\\Shared\\StringFuncs.h", 0x13u, 0xC0001204, 0x10u);
        memcpy_0(v30, v27, v29);
        v24 = (__int64)v51;
        *v51 = v30;
        v11 = v44;
        v25 = (__int64)v46;
      }
      else
      {
        v35 = StringCchPrintfW(Src, 0xCu, L"$%d", v26);
        if ( v35 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x379u, 0x12u, v35);
        *(_QWORD *)v24 = WStringCopy(Src);
      }
      *(_WORD *)(v24 + 8) = *(_WORD *)(v25 + 8);
      *(_DWORD *)(v24 + 12) = 4;
      if ( v41 == 26 )
        *(_DWORD *)(v24 + 12) = 6;
      if ( *(_WORD *)(v25 + 8) == 29 )
      {
        v31 = 1;
        LOBYTE(v39) = 1;
        v32 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, __int64 *))v11->lpVtbl->GetRefTypeInfo)(
                v11,
                *v46,
                &v40);
        if ( v32 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x38Du, 0x12u, v32);
        v47 = 0;
        v33 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 24LL))(v40, &v47);
        if ( v33 < 0 )
          InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x391u, 0x12u, v33);
        if ( *(_DWORD *)(v47 + 40) != 16 || *(_DWORD *)(v47 + 44) != 1 )
        {
          v31 = 0;
          LOBYTE(v39) = 0;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 152LL))(v40);
        if ( v31 )
        {
          String1 = 0;
          v34 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v40 + 96LL))(
                  v40,
                  0xFFFFFFFFLL,
                  &String1,
                  0,
                  0,
                  0);
          if ( v34 < 0 )
            InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x39Bu, 0x12u, v34);
          if ( wcscmp_0(String1, L"GUID") )
            v31 = 0;
          LOBYTE(v39) = v31;
          SysFreeString(String1);
          v11 = v44;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        v40 = 0;
        if ( v31 )
          *(_WORD *)(v24 + 8) = 72;
      }
    }
  }
  if ( a4 && v23 >= 1 )
  {
    do
    {
      v36 = (BSTR *)a4 + v9;
      SysFreeString(*v36);
      *v36 = 0;
      ++v9;
    }
    while ( v9 <= *((_DWORD *)this + 22) );
    v11 = v44;
  }
  if ( v40 )
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v40 + 16LL))(v40, v21, v22);
  ((void (__fastcall *)(struct ITypeInfo *, unsigned int *, __int64))v11->lpVtbl->ReleaseFuncDesc)(v11, v43, v22);
  return v50;
}

```

## disassembly

```asm
0x1800073c0  push    rbp
0x1800073c2  push    rsi
0x1800073c3  push    rdi
0x1800073c4  push    r12
0x1800073c6  push    r13
0x1800073c8  push    r14
0x1800073ca  push    r15
0x1800073cc  sub     rsp, 100h
0x1800073d3  lea     rbp, [rsp+40h]
0x1800073d8  mov     [rbp+0F0h+arg_10], rbx
0x1800073df  mov     rax, cs:__security_cookie
0x1800073e6  xor     rax, rbp
0x1800073e9  mov     [rbp+0F0h+var_38], rax
0x1800073f0  mov     [rbp+0F0h+var_80], rsp
0x1800073f4  mov     rdi, r9
0x1800073f7  mov     rsi, r8
0x1800073fa  mov     r14d, edx
0x1800073fd  mov     r15, rcx
0x180007400  mov     [rbp+0F0h+var_A0], rcx
0x180007404  mov     rax, [rbp+0F0h+arg_20]
0x18000740b  mov     [rbp+0F0h+var_D0], rax
0x18000740f  mov     r12d, 1
0x180007415  mov     [rcx], r12d
0x180007418  xor     r13d, r13d
0x18000741b  mov     [rcx+8], r13
0x18000741f  mov     [rcx+10h], r13
0x180007423  mov     [rcx+40h], r13d
0x180007427  mov     edx, 1F4h; dwSpinCount
0x18000742c  add     rcx, 18h; lpCriticalSection
0x180007430  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180007436  mov     [r15+40h], eax
0x18000743a  mov     [r15+48h], r13
0x18000743e  mov     [r15+50h], rdi
0x180007442  mov     [r15+68h], rsi
0x180007446  xorps   xmm0, xmm0
0x180007449  movups  xmmword ptr [r15+58h], xmm0
0x18000744e  mov     [rbp+0F0h+var_A8], r13
0x180007452  mov     [rbp+0F0h+var_D8], r13
0x180007456  mov     [rbp+0F0h+var_E8], r13
0x18000745a  mov     rbx, [rbp+0F0h+var_D0]
0x18000745e  mov     rax, [rbx]
0x180007461  lea     r8, [rbp+0F0h+var_D8]
0x180007465  mov     edx, r14d
0x180007468  mov     rcx, rbx
0x18000746b  mov     rax, [rax+28h]
0x18000746f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007474  lea     rsi, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18000747b  test    eax, eax
0x18000747d  js      loc_1800079B6
0x180007483  mov     rax, [rbp+0F0h+var_D8]
0x180007487  movsx   ecx, word ptr [rax+24h]
0x18000748b  mov     [r15+58h], ecx
0x18000748f  inc     ecx
0x180007491  mov     [rbp+0F0h+var_DC], ecx
0x180007494  mov     r8d, ecx
0x180007497  shl     r8, 3
0x18000749b  mov     [rbp+0F0h+var_98], r8
0x18000749f  mov     eax, 0FFFFFFFFh
0x1800074a4  cmp     r8, rax
0x1800074a7  ja      loc_1800078A7
0x1800074ad  mov     eax, r8d
0x1800074b0  lea     rcx, [rax+0Fh]
0x1800074b4  cmp     rcx, rax
0x1800074b7  ja      short loc_1800074C3
0x1800074b9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800074c3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800074c7  mov     rax, rcx
0x1800074ca  call    _alloca_probe
0x1800074cf  sub     rsp, rcx
0x1800074d2  lea     rdi, [rsp+130h+var_F0]
0x1800074d7  mov     [rbp+0F0h+var_A8], rdi
0x1800074db  xor     edx, edx; Val
0x1800074dd  mov     rcx, rdi; void *
0x1800074e0  call    memset_0
0x1800074e5  mov     rax, [rbx]
0x1800074e8  lea     rcx, [rbp+0F0h+var_DC]
0x1800074ec  mov     [rsp+130h+var_110], rcx
0x1800074f1  mov     r9d, [rbp+0F0h+var_DC]
0x1800074f5  mov     r8, rdi
0x1800074f8  mov     rdx, [rbp+0F0h+var_D8]
0x1800074fc  mov     edx, [rdx]
0x1800074fe  mov     rcx, rbx
0x180007501  mov     rax, [rax+38h]
0x180007505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750a  test    eax, eax
0x18000750c  js      loc_18000777C
0x180007512  mov     eax, [r15+58h]
0x180007516  inc     eax
0x180007518  cmp     [rbp+0F0h+var_DC], eax
0x18000751b  jnz     loc_180007797
0x180007521  mov     rax, [rdi]
0x180007524  mov     [r15+8], rax
0x180007528  movsxd  rcx, dword ptr [r15+58h]
0x18000752c  mov     eax, 10h
0x180007531  mul     rcx
0x180007534  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000753b  cmovb   rax, rcx
0x18000753f  mov     rcx, rax; cb
0x180007542  call    cs:__imp_CoTaskMemAlloc
0x180007548  mov     [r15+60h], rax
0x18000754c  test    rax, rax
0x18000754f  jz      loc_1800077D5
0x180007555  mov     [rbp+0F0h+var_C8], r13d
0x180007559  mov     r8d, r13d
0x18000755c  mov     eax, [r15+58h]
0x180007560  cmp     r13d, eax
0x180007563  jge     loc_18000764D
0x180007569  movsxd  rdx, r13d
0x18000756c  mov     r14, rdx
0x18000756f  shl     r14, 4
0x180007573  add     r14, [r15+60h]
0x180007577  mov     [rbp+0F0h+var_98], r14
0x18000757b  shl     rdx, 5
0x18000757f  mov     rax, [rbp+0F0h+var_D8]
0x180007583  mov     rsi, [rax+10h]
0x180007587  add     rsi, rdx
0x18000758a  mov     [rbp+0F0h+var_C0], rsi
0x18000758e  movzx   eax, word ptr [rsi+8]
0x180007592  mov     [rbp+0F0h+var_E0], ax
0x180007596  cmp     ax, 1Ah
0x18000759a  jz      loc_180007652
0x1800075a0  inc     r13d
0x1800075a3  lea     ecx, [r8+1]
0x1800075a7  movsxd  rax, r13d
0x1800075aa  cmp     qword ptr [rdi+rax*8], 0
0x1800075af  jz      loc_180007853
0x1800075b5  movsxd  rax, ecx
0x1800075b8  mov     rbx, [rdi+rax*8]
0x1800075bc  test    rbx, rbx
0x1800075bf  jz      loc_1800078A0
0x1800075c5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800075cc  nop     dword ptr [rax+00h]
0x1800075d0  inc     rax
0x1800075d3  cmp     word ptr [rbx+rax*2], 0
0x1800075d8  jnz     short loc_1800075D0
0x1800075da  mov     [rbp+0F0h+var_88], rax
0x1800075de  lea     ecx, [rax+1]
0x1800075e1  movsxd  rax, ecx
0x1800075e4  mov     [rbp+0F0h+var_90], rax
0x1800075e8  lea     r14, [rax+rax]
0x1800075ec  mov     [rbp+0F0h+var_90], r14
0x1800075f0  add     ecx, ecx; cb
0x1800075f2  call    cs:__imp_CoTaskMemAlloc
0x1800075f8  mov     rsi, rax
0x1800075fb  test    rax, rax
0x1800075fe  jz      loc_180007831
0x180007604  mov     r8, r14; Size
0x180007607  mov     rdx, rbx; Src
0x18000760a  mov     rcx, rsi; void *
0x18000760d  call    memcpy_0
0x180007612  mov     r14, [rbp+0F0h+var_98]
0x180007616  mov     [r14], rsi
0x180007619  mov     rbx, [rbp+0F0h+var_D0]
0x18000761d  mov     rsi, [rbp+0F0h+var_C0]
0x180007621  movzx   eax, word ptr [rsi+8]
0x180007625  mov     [r14+8], ax
0x18000762a  mov     dword ptr [r14+0Ch], 4
0x180007632  cmp     [rbp+0F0h+var_E0], 1Ah
0x180007637  jnz     short loc_180007641
0x180007639  mov     dword ptr [r14+0Ch], 6
0x180007641  cmp     word ptr [rsi+8], 1Dh
0x180007646  jz      short loc_18000765E
0x180007648  jmp     loc_180007555
0x18000764d  jmp     loc_18000793C
0x180007652  mov     rsi, [rsi]
0x180007655  mov     [rbp+0F0h+var_C0], rsi
0x180007659  jmp     loc_1800075A0
0x18000765e  mov     sil, 1
0x180007661  mov     byte ptr [rbp+0F0h+var_F0], sil
0x180007665  mov     rax, [rbx]
0x180007668  lea     r8, [rbp+0F0h+var_E8]
0x18000766c  mov     rdx, [rbp+0F0h+var_C0]
0x180007670  mov     edx, [rdx]
0x180007672  mov     rcx, rbx
0x180007675  mov     rax, [rax+70h]
0x180007679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767e  test    eax, eax
0x180007680  js      loc_1800077B6
0x180007686  mov     [rbp+0F0h+var_B8], 0
0x18000768e  mov     rcx, [rbp+0F0h+var_E8]
0x180007692  mov     rax, [rcx]
0x180007695  lea     rdx, [rbp+0F0h+var_B8]
0x180007699  mov     rax, [rax+18h]
0x18000769d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076a2  test    eax, eax
0x1800076a4  js      loc_1800077F3
0x1800076aa  mov     rdx, [rbp+0F0h+var_B8]
0x1800076ae  cmp     dword ptr [rdx+28h], 10h
0x1800076b2  jnz     loc_180007770
0x1800076b8  cmp     dword ptr [rdx+2Ch], 1
0x1800076bc  jnz     loc_180007770
0x1800076c2  mov     rcx, [rbp+0F0h+var_E8]
0x1800076c6  mov     rax, [rcx]
0x1800076c9  mov     rax, [rax+98h]
0x1800076d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d5  test    sil, sil
0x1800076d8  jnz     short loc_18000770A
0x1800076da  mov     rcx, [rbp+0F0h+var_E8]
0x1800076de  mov     rax, [rcx]
0x1800076e1  mov     rax, [rax+10h]
0x1800076e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ea  mov     [rbp+0F0h+var_E8], 0
0x1800076f2  test    sil, sil
0x1800076f5  jz      loc_180007648
0x1800076fb  mov     eax, 48h ; 'H'
0x180007700  mov     [r14+8], ax
0x180007705  jmp     loc_180007648
0x18000770a  xor     edx, edx
0x18000770c  mov     [rbp+0F0h+String1], rdx
0x180007710  mov     rcx, [rbp+0F0h+var_E8]
0x180007714  mov     rax, [rcx]
0x180007717  mov     [rsp+130h+var_108], rdx
0x18000771c  mov     [rsp+130h+var_110], rdx
0x180007721  xor     r9d, r9d
0x180007724  lea     r8, [rbp+0F0h+String1]
0x180007728  mov     edx, 0FFFFFFFFh
0x18000772d  mov     rax, [rax+60h]
0x180007731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007736  test    eax, eax
0x180007738  js      loc_180007812
0x18000773e  lea     rdx, aGuid; "GUID"
0x180007745  mov     rcx, [rbp+0F0h+String1]; String1
0x180007749  call    wcscmp_0
0x18000774e  movzx   esi, sil
0x180007752  xor     edx, edx
0x180007754  test    eax, eax
0x180007756  cmovnz  esi, edx
0x180007759  mov     byte ptr [rbp+0F0h+var_F0], sil
0x18000775d  mov     rcx, [rbp+0F0h+String1]; bstrString
0x180007761  call    cs:__imp_SysFreeString
0x180007767  mov     rbx, [rbp+0F0h+var_D0]
0x18000776b  jmp     loc_1800076DA
0x180007770  xor     sil, sil
0x180007773  mov     byte ptr [rbp+0F0h+var_F0], sil
0x180007777  jmp     loc_1800076C2
0x18000777c  mov     r8d, 12h; unsigned __int16
0x180007782  mov     r9d, eax; int
0x180007785  mov     edx, 35Fh; unsigned int
0x18000778a  mov     rcx, rsi; unsigned __int16 *
0x18000778d  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180007792  jmp     loc_180007512
0x180007797  mov     r8d, 12h; unsigned __int16
0x18000779d  lea     r9, aCnamesUnsigned; "cNames == (unsigned int)(_paramInfo.num"...
0x1800077a4  mov     edx, 360h; unsigned int
0x1800077a9  mov     rcx, rsi; unsigned __int16 *
0x1800077ac  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x1800077b1  jmp     loc_180007521
0x1800077b6  mov     r8d, 12h; unsigned __int16
0x1800077bc  mov     r9d, eax; int
0x1800077bf  mov     edx, 38Dh; unsigned int
0x1800077c4  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x1800077cb  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x1800077d0  jmp     loc_180007686
0x1800077d5  mov     edx, 366h; unsigned int
0x1800077da  mov     r9d, 12h; unsigned __int16
0x1800077e0  mov     r8d, 0C0001204h; unsigned int
0x1800077e6  mov     rcx, rsi; unsigned __int16 *
0x1800077e9  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800077ee  jmp     loc_180007555
0x1800077f3  mov     r8d, 12h; unsigned __int16
0x1800077f9  mov     r9d, eax; int
0x1800077fc  mov     edx, 391h; unsigned int
0x180007801  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180007808  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000780d  jmp     loc_1800076AA
0x180007812  mov     r8d, 12h; unsigned __int16
0x180007818  mov     r9d, eax; int
0x18000781b  mov     edx, 39Bh; unsigned int
0x180007820  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180007827  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000782c  jmp     loc_18000773E
0x180007831  mov     edx, 13h; unsigned int
0x180007836  mov     r9d, 10h; unsigned __int16
0x18000783c  mov     r8d, 0C0001204h; unsigned int
0x180007842  lea     rcx, aComComplusSrcE_1; "com\\complus\\src\\events\\Shared\\Stri"...
0x180007849  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000784e  jmp     loc_180007604
0x180007853  mov     r9d, ecx
0x180007856  lea     r8, aD_0; "$%d"
0x18000785d  mov     edx, 0Ch; unsigned __int64
0x180007862  lea     rcx, [rbp+0F0h+Src]; unsigned __int16 *
0x180007869  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000786e  test    eax, eax
0x180007870  jns     short loc_18000788C
0x180007872  mov     r8d, 12h; unsigned __int16
0x180007878  mov     r9d, eax; int
0x18000787b  mov     edx, 379h; unsigned int
0x180007880  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180007887  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000788c  lea     rcx, [rbp+0F0h+Src]; Src
0x180007893  call    ?WStringCopy@@YAPEAGPEBG@Z; WStringCopy(ushort const *)
0x180007898  mov     [r14], rax
0x18000789b  jmp     loc_180007621
0x1800078a0  xor     eax, eax
0x1800078a2  jmp     loc_1800075DA
0x1800078a7  xorps   xmm0, xmm0
0x1800078aa  xor     eax, eax
0x1800078ac  movups  xmmword ptr [rbp+0F0h+Src], xmm0
0x1800078b3  mov     qword ptr [rbp+0F0h+Src+0Eh], rax
0x1800078ba  mov     r9d, 358h
  ... truncated ...
```
