# CDSLPageHolder::SetCLSID(CDSLProviderInformation *,ulong,_GUID const &,ushort const *,ulong,CDSLObject *)

- ea: `0x18005a7c4`
- end: `0x18005ac60`
- name: `?SetCLSID@CDSLPageHolder@@QEAAJPEAVCDSLProviderInformation@@KAEBU_GUID@@PEBGKPEAVCDSLObject@@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(CDSLPageHolder *__hidden this, struct CDSLProviderInformation *, unsigned int, const struct _GUID *, const unsigned __int16 *, unsigned int, struct CDSLObject *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180055d3c`

## callees

- `0x1800112b0`
- `0x180013870`
- `0x180029560`
- `0x180059fdc`
- `0x18005a7c4`
- `0x18007e6ca`
- `0x180087010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18005aa9e`
- `ole32!CoTaskMemAlloc` at `0x18005ab34`
- `ole32!CoTaskMemAlloc` at `0x18005aa9e`
- `ole32!CoTaskMemAlloc` at `0x18005ab34`
- `ole32!CoTaskMemFree` at `0x18005a85e`
- `ole32!CoTaskMemFree` at `0x18005a872`
- `ole32!CoTaskMemFree` at `0x18005ac0d`
- `ole32!CoTaskMemFree` at `0x18005ac17`
- `ole32!CoTaskMemFree` at `0x18005ac21`
- `ole32!CoTaskMemFree` at `0x18005a85e`
- `ole32!CoTaskMemFree` at `0x18005a872`
- `ole32!CoTaskMemFree` at `0x18005ac0d`
- `ole32!CoTaskMemFree` at `0x18005ac17`
- `ole32!CoTaskMemFree` at `0x18005ac21`
- `ole32!CoCreateInstance` at `0x18005a8cc`
- `ole32!CoCreateInstance` at `0x18005a8cc`

## string_xrefs

- `0x18005a8eb`: `<CDSLPageHolder::SetCLSID|OLEDB|ERR> `
- `0x18005a957`: `<CDSLPageHolder::SetCLSID|OLEDB|ERR> `
- `0x18005a9a4`: `<CDSLPageHolder::SetCLSID|OLEDB|ERR> `
- `0x18005a9fc`: `<CDSLPageHolder::SetCLSID|OLEDB|ERR> `
- `0x18005aacb`: `<CDSLPageHolder::SetCLSID|OLEDB|ERR> `
- `0x18005ab61`: `<CDSLPageHolder::SetCLSID|OLEDB|ERR> `
- `0x18005aba6`: `<CDSLPageHolder::SetCLSID|OLEDB|ERR> `
- `0x18005a912`: `<CDSLPageHolder::SetCLSID|Trace|HR> `
- `0x18005ab82`: `<CDSLPageHolder::SetCLSID|Trace|HR> `
- `0x18005ac37`: `<CDSLPageHolder::SetCLSID|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDSLPageHolder::SetCLSID(
        CDSLPageHolder *this,
        struct CDSLProviderInformation *a2,
        int a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        struct CDSLObject *a7)
{
  _QWORD *v7; // r12
  __int64 v9; // rcx
  _QWORD *v13; // r15
  __int64 v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  unsigned int v17; // edi
  HRESULT Instance; // eax
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  unsigned __int16 *v24; // rcx
  __int64 v25; // r14
  __int64 v26; // rax
  unsigned __int64 v27; // rbx
  unsigned __int16 *v28; // rax
  __int64 v29; // rdx
  const unsigned __int16 *v30; // rbx
  unsigned __int64 v31; // r14
  unsigned __int16 *v32; // rax
  LPVOID pv[2]; // [rsp+30h] [rbp-38h] BYREF
  struct tagSIZE v35[2]; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v36[2]; // [rsp+50h] [rbp-18h]

  v7 = (_QWORD *)((char *)this + 40);
  v9 = *((_QWORD *)this + 5);
  *(_OWORD *)pv = 0;
  *(_OWORD *)&v35[0].cx = 0;
  *(_OWORD *)v36 = 0;
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *v7 = 0;
  }
  v13 = (_QWORD *)((char *)this + 32);
  v14 = *((_QWORD *)this + 4);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, 0);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 16LL))(*v13);
    *v13 = 0;
  }
  v15 = (void *)*((_QWORD *)this + 19);
  *((_DWORD *)this + 53) = a3;
  *((_QWORD *)this + 28) = a2;
  *((struct _GUID *)this + 1) = *a4;
  CoTaskMemFree(v15);
  v16 = (void *)*((_QWORD *)this + 29);
  *((_QWORD *)this + 19) = 0;
  CoTaskMemFree(v16);
  *((_QWORD *)this + 31) = a7;
  *((_QWORD *)this + 29) = 0;
  if ( *((_OWORD *)this + 1) == *(_OWORD *)&GUID_NULL )
  {
    v17 = 0;
    goto LABEL_50;
  }
  *((_DWORD *)this + 60) = a6;
  Instance = CoCreateInstance((const IID *const)this + 1, 0, 0x17u, &IID_IPropertyPage, (LPVOID *)this + 4);
  v17 = Instance;
  if ( Instance < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(Instance, L"<CDSLPageHolder::SetCLSID|OLEDB|ERR> ", 0x51u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v19 = 82953;
LABEL_11:
        bidTraceHR(off_1800C8408[0], v19, L"<CDSLPageHolder::SetCLSID|Trace|HR> ", v17);
LABEL_43:
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v17, L"<CDSLPageHolder::SetCLSID|OLEDB|ERR> ", 0x87u);
        goto LABEL_45;
      }
    }
    goto LABEL_45;
  }
  v20 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*v13)(*v13, &IID_IPersistPropertyBag, v7);
  v17 = v20;
  if ( v20 >= 0 )
  {
    v21 = (*(__int64 (__fastcall **)(_QWORD, CDSLPageHolder *))(*(_QWORD *)*v13 + 24LL))(*v13, this);
    v17 = v21;
    if ( v21 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v21, L"<CDSLPageHolder::SetCLSID|OLEDB|ERR> ", 0x55u);
        if ( (bidGblFlags & 2) != 0 )
        {
          v19 = 87049;
          goto LABEL_11;
        }
      }
      goto LABEL_45;
    }
    v22 = *v13;
    LODWORD(pv[0]) = 48;
    v23 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v22 + 48LL))(v22, pv);
    v17 = v23;
    if ( v23 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v23, L"<CDSLPageHolder::SetCLSID|OLEDB|ERR> ", 0x58u);
        if ( (bidGblFlags & 2) != 0 )
        {
          v19 = 90121;
          goto LABEL_11;
        }
      }
      goto LABEL_45;
    }
    if ( !CDSLPageHolder::tagCDlgTemplate::Init((CDSLPageHolder *)((char *)this + 160), v35) )
      goto LABEL_50;
    memset_0((char *)this + 48, 0, 0x68u);
    v24 = v36[0];
    *((_DWORD *)this + 12) = 104;
    *((_QWORD *)this + 8) = (char *)this + 160;
    v25 = -1;
    *((_QWORD *)this + 11) = CDSLPageHolder::_PageHolderDlgProc;
    *((_QWORD *)this + 13) = CDSLPageHolder::_PageHolderPageProc;
    *((_DWORD *)this + 13) = 169;
    *((_QWORD *)this + 12) = this;
    if ( v24 )
    {
      v26 = -1;
      do
        ++v26;
      while ( v24[v26] );
      v27 = v26 + 1;
      v28 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v26 + 1));
      *((_QWORD *)this + 19) = v28;
      if ( !v28 )
      {
        v17 = -2147024882;
        if ( (bidGblFlags & 2) == 0
          || (OLEDBTraceErr(-2147024882, L"<CDSLPageHolder::SetCLSID|OLEDB|ERR> ", 0x69u), (bidGblFlags & 2) == 0) )
        {
LABEL_42:
          if ( (v17 & 0x80000000) == 0 )
            goto LABEL_50;
          goto LABEL_43;
        }
        v29 = 107529;
LABEL_41:
        v17 = bidTraceHR(off_1800C8408[0], v29, L"<CDSLPageHolder::SetCLSID|Trace|HR> ", 2147942414LL);
        goto LABEL_42;
      }
      StringCchCopyW(v28, v27, v36[0]);
      *((_DWORD *)this + 52) = v36[1];
    }
    v30 = a5;
    if ( !a5 )
    {
      v30 = &String;
      if ( pv[1] )
        v30 = (const unsigned __int16 *)pv[1];
    }
    do
      ++v25;
    while ( v30[v25] );
    v31 = v25 + 1;
    v32 = (unsigned __int16 *)CoTaskMemAlloc(2 * v31);
    *((_QWORD *)this + 29) = v32;
    if ( v32 )
    {
      StringCchCopyW(v32, v31, v30);
      *((_QWORD *)this + 10) = *((_QWORD *)this + 29);
      *((_DWORD *)this + 51) = 0;
      goto LABEL_50;
    }
    v17 = -2147024882;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_42;
    OLEDBTraceErr(-2147024882, L"<CDSLPageHolder::SetCLSID|OLEDB|ERR> ", 0x7Du);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_42;
    v29 = 128009;
    goto LABEL_41;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(v20, L"<CDSLPageHolder::SetCLSID|OLEDB|ERR> ", 0x53u);
    if ( (bidGblFlags & 2) != 0 )
    {
      v19 = 85001;
      goto LABEL_11;
    }
  }
LABEL_45:
  if ( *v7 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
    *v7 = 0;
  }
  if ( *v13 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 16LL))(*v13);
    *v13 = 0;
  }
LABEL_50:
  CoTaskMemFree(pv[1]);
  CoTaskMemFree(*(LPVOID *)&v35[1]);
  CoTaskMemFree(v36[0]);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8408[0], 145417, L"<CDSLPageHolder::SetCLSID|Trace|HR> ", v17);
  return v17;
}

```

## disassembly

```asm
0x18005a7c4  push    rbp
0x18005a7c6  push    rbx
0x18005a7c7  push    rsi
0x18005a7c8  push    rdi
0x18005a7c9  push    r12
0x18005a7cb  push    r13
0x18005a7cd  push    r14
0x18005a7cf  push    r15
0x18005a7d1  mov     rbp, rsp
0x18005a7d4  sub     rsp, 68h
0x18005a7d8  xorps   xmm0, xmm0
0x18005a7db  lea     r12, [rcx+28h]
0x18005a7df  mov     rsi, rcx
0x18005a7e2  xor     r13d, r13d
0x18005a7e5  mov     rcx, [r12]
0x18005a7e9  mov     rdi, r9
0x18005a7ec  mov     ebx, r8d
0x18005a7ef  mov     r14, rdx
0x18005a7f2  movups  xmmword ptr [rbp+pv], xmm0
0x18005a7f6  movups  xmmword ptr [rbp+var_28.cx], xmm0
0x18005a7fa  movups  xmmword ptr [rbp+var_18], xmm0
0x18005a7fe  test    rcx, rcx
0x18005a801  jz      short loc_18005A813
0x18005a803  mov     rax, [rcx]
0x18005a806  mov     rax, [rax+10h]
0x18005a80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a80f  mov     [r12], r13
0x18005a813  lea     r15, [rsi+20h]
0x18005a817  mov     rcx, [r15]
0x18005a81a  test    rcx, rcx
0x18005a81d  jz      short loc_18005A83F
0x18005a81f  mov     rax, [rcx]
0x18005a822  xor     edx, edx
0x18005a824  mov     rax, [rax+18h]
0x18005a828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a82d  mov     rcx, [r15]
0x18005a830  mov     rax, [rcx]
0x18005a833  mov     rax, [rax+10h]
0x18005a837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a83c  mov     [r15], r13
0x18005a83f  mov     rcx, [rsi+98h]; pv
0x18005a846  mov     [rsi+0D4h], ebx
0x18005a84c  lea     rbx, [rsi+10h]
0x18005a850  mov     [rsi+0E0h], r14
0x18005a857  movups  xmm0, xmmword ptr [rdi]
0x18005a85a  movdqu  xmmword ptr [rbx], xmm0
0x18005a85e  call    cs:__imp_CoTaskMemFree
0x18005a864  mov     rcx, [rsi+0E8h]; pv
0x18005a86b  mov     [rsi+98h], r13
0x18005a872  call    cs:__imp_CoTaskMemFree
0x18005a878  mov     rax, [rbp+arg_30]
0x18005a87c  mov     r14b, 2
0x18005a87f  mov     [rsi+0F8h], rax
0x18005a886  mov     [rsi+0E8h], r13
0x18005a88d  mov     rax, [rbx]
0x18005a890  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18005a897  jnz     short loc_18005A8AE
0x18005a899  mov     rax, [rbx+8]
0x18005a89d  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18005a8a4  jnz     short loc_18005A8AE
0x18005a8a6  mov     edi, r13d
0x18005a8a9  jmp     loc_18005AC09
0x18005a8ae  mov     eax, [rbp+arg_28]
0x18005a8b1  lea     r9, IID_IPropertyPage; riid
0x18005a8b8  xor     edx, edx; pUnkOuter
0x18005a8ba  mov     [rsi+0F0h], eax
0x18005a8c0  mov     rcx, rbx; rclsid
0x18005a8c3  mov     [rsp+68h+ppv], r15; ppv
0x18005a8c8  lea     r8d, [rdx+17h]; dwClsContext
0x18005a8cc  call    cs:__imp_CoCreateInstance
0x18005a8d2  mov     edi, eax
0x18005a8d4  test    eax, eax
0x18005a8d6  jns     short loc_18005A926
0x18005a8d8  test    byte ptr cs:_bidGblFlags, r14b
0x18005a8df  jz      loc_18005ABB4
0x18005a8e5  mov     r8d, 51h ; 'Q'; unsigned int
0x18005a8eb  lea     rdx, aCdslpageholder; "<CDSLPageHolder::SetCLSID|OLEDB|ERR> "
0x18005a8f2  mov     ecx, eax; int
0x18005a8f4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005a8f9  test    byte ptr cs:_bidGblFlags, r14b
0x18005a900  jz      loc_18005ABB4
0x18005a906  mov     edx, 14409h
0x18005a90b  mov     rcx, cs:off_1800C8408; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005a912  lea     r8, aCdslpageholder_0; "<CDSLPageHolder::SetCLSID|Trace|HR> "
0x18005a919  mov     r9d, edi
0x18005a91c  call    _bidTraceHR
0x18005a921  jmp     loc_18005AB97
0x18005a926  mov     rcx, [r15]
0x18005a929  lea     rdx, IID_IPersistPropertyBag
0x18005a930  mov     r8, r12
0x18005a933  mov     rax, [rcx]
0x18005a936  mov     rax, [rax]
0x18005a939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a93e  mov     edi, eax
0x18005a940  test    eax, eax
0x18005a942  jns     short loc_18005A979
0x18005a944  test    byte ptr cs:_bidGblFlags, r14b
0x18005a94b  jz      loc_18005ABB4
0x18005a951  mov     r8d, 53h ; 'S'; unsigned int
0x18005a957  lea     rdx, aCdslpageholder; "<CDSLPageHolder::SetCLSID|OLEDB|ERR> "
0x18005a95e  mov     ecx, eax; int
0x18005a960  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005a965  test    byte ptr cs:_bidGblFlags, r14b
0x18005a96c  jz      loc_18005ABB4
0x18005a972  mov     edx, 14C09h
0x18005a977  jmp     short loc_18005A90B
0x18005a979  mov     rcx, [r15]
0x18005a97c  mov     rdx, rsi
0x18005a97f  mov     rax, [rcx]
0x18005a982  mov     rax, [rax+18h]
0x18005a986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a98b  mov     edi, eax
0x18005a98d  test    eax, eax
0x18005a98f  jns     short loc_18005A9C9
0x18005a991  test    byte ptr cs:_bidGblFlags, r14b
0x18005a998  jz      loc_18005ABB4
0x18005a99e  mov     r8d, 55h ; 'U'; unsigned int
0x18005a9a4  lea     rdx, aCdslpageholder; "<CDSLPageHolder::SetCLSID|OLEDB|ERR> "
0x18005a9ab  mov     ecx, eax; int
0x18005a9ad  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005a9b2  test    byte ptr cs:_bidGblFlags, r14b
0x18005a9b9  jz      loc_18005ABB4
0x18005a9bf  mov     edx, 15409h
0x18005a9c4  jmp     loc_18005A90B
0x18005a9c9  mov     rcx, [r15]
0x18005a9cc  lea     rdx, [rbp+pv]
0x18005a9d0  mov     dword ptr [rbp+pv], 30h ; '0'
0x18005a9d7  mov     rax, [rcx]
0x18005a9da  mov     rax, [rax+30h]
0x18005a9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a9e3  mov     edi, eax
0x18005a9e5  test    eax, eax
0x18005a9e7  jns     short loc_18005AA21
0x18005a9e9  test    byte ptr cs:_bidGblFlags, r14b
0x18005a9f0  jz      loc_18005ABB4
0x18005a9f6  mov     r8d, 58h ; 'X'; unsigned int
0x18005a9fc  lea     rdx, aCdslpageholder; "<CDSLPageHolder::SetCLSID|OLEDB|ERR> "
0x18005aa03  mov     ecx, eax; int
0x18005aa05  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005aa0a  test    byte ptr cs:_bidGblFlags, r14b
0x18005aa11  jz      loc_18005ABB4
0x18005aa17  mov     edx, 16009h
0x18005aa1c  jmp     loc_18005A90B
0x18005aa21  lea     r14, [rsi+0A0h]
0x18005aa28  mov     rcx, r14; this
0x18005aa2b  lea     rdx, [rbp+var_28]; struct tagSIZE *
0x18005aa2f  call    ?Init@tagCDlgTemplate@CDSLPageHolder@@QEAA_NPEAUtagSIZE@@@Z; CDSLPageHolder::tagCDlgTemplate::Init(tagSIZE *)
0x18005aa34  test    al, al
0x18005aa36  jz      loc_18005AC06
0x18005aa3c  mov     r13d, 68h ; 'h'
0x18005aa42  lea     rcx, [rsi+30h]; void *
0x18005aa46  mov     r8d, r13d; Size
0x18005aa49  xor     edx, edx; Val
0x18005aa4b  call    memset_0
0x18005aa50  mov     rcx, [rbp+var_18]
0x18005aa54  lea     rax, ?_PageHolderDlgProc@CDSLPageHolder@@KA_JPEAUHWND__@@I_K_J@Z; CDSLPageHolder::_PageHolderDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18005aa5b  mov     [rsi+30h], r13d
0x18005aa5f  xor     r13d, r13d
0x18005aa62  mov     [rsi+40h], r14
0x18005aa66  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005aa6a  mov     [rsi+58h], rax
0x18005aa6e  lea     rax, ?_PageHolderPageProc@CDSLPageHolder@@KAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z; CDSLPageHolder::_PageHolderPageProc(HWND__ *,uint,_PROPSHEETPAGEW *)
0x18005aa75  mov     [rsi+68h], rax
0x18005aa79  mov     dword ptr [rsi+34h], 0A9h
0x18005aa80  mov     [rsi+60h], rsi
0x18005aa84  test    rcx, rcx
0x18005aa87  jz      short loc_18005AB08
0x18005aa89  mov     rax, r14
0x18005aa8c  inc     rax
0x18005aa8f  cmp     [rcx+rax*2], r13w
0x18005aa94  jnz     short loc_18005AA8C
0x18005aa96  lea     rbx, [rax+1]
0x18005aa9a  lea     rcx, [rbx+rbx]; cb
0x18005aa9e  call    cs:__imp_CoTaskMemAlloc
0x18005aaa4  mov     [rsi+98h], rax
0x18005aaab  test    rax, rax
0x18005aaae  jnz     short loc_18005AAEE
0x18005aab0  mov     r14b, 2
0x18005aab3  mov     edi, 8007000Eh
0x18005aab8  test    byte ptr cs:_bidGblFlags, r14b
0x18005aabf  jz      loc_18005AB93
0x18005aac5  lea     r8d, [rax+69h]; unsigned int
0x18005aac9  mov     ecx, edi; int
0x18005aacb  lea     rdx, aCdslpageholder; "<CDSLPageHolder::SetCLSID|OLEDB|ERR> "
0x18005aad2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005aad7  test    byte ptr cs:_bidGblFlags, r14b
0x18005aade  jz      loc_18005AB93
0x18005aae4  mov     edx, 1A409h
0x18005aae9  jmp     loc_18005AB7B
0x18005aaee  mov     r8, [rbp+var_18]; unsigned __int16 *
0x18005aaf2  mov     rdx, rbx; unsigned __int64
0x18005aaf5  mov     rcx, rax; unsigned __int16 *
0x18005aaf8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005aafd  mov     r11d, dword ptr [rbp+var_18+8]
0x18005ab01  mov     [rsi+0D0h], r11d
0x18005ab08  mov     rbx, [rbp+arg_20]
0x18005ab0c  test    rbx, rbx
0x18005ab0f  jnz     short loc_18005AB23
0x18005ab11  mov     rax, [rbp+pv+8]
0x18005ab15  lea     rbx, String
0x18005ab1c  test    rax, rax
0x18005ab1f  cmovnz  rbx, rax
0x18005ab23  inc     r14
0x18005ab26  cmp     [rbx+r14*2], r13w
0x18005ab2b  jnz     short loc_18005AB23
0x18005ab2d  inc     r14
0x18005ab30  lea     rcx, [r14+r14]; cb
0x18005ab34  call    cs:__imp_CoTaskMemAlloc
0x18005ab3a  mov     [rsi+0E8h], rax
0x18005ab41  test    rax, rax
0x18005ab44  jnz     loc_18005ABE6
0x18005ab4a  mov     r14b, 2
0x18005ab4d  mov     edi, 8007000Eh
0x18005ab52  test    byte ptr cs:_bidGblFlags, r14b
0x18005ab59  jz      short loc_18005AB93
0x18005ab5b  lea     r8d, [rax+7Dh]; unsigned int
0x18005ab5f  mov     ecx, edi; int
0x18005ab61  lea     rdx, aCdslpageholder; "<CDSLPageHolder::SetCLSID|OLEDB|ERR> "
0x18005ab68  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005ab6d  test    byte ptr cs:_bidGblFlags, r14b
0x18005ab74  jz      short loc_18005AB93
0x18005ab76  mov     edx, 1F409h
0x18005ab7b  mov     rcx, cs:off_1800C8408; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005ab82  lea     r8, aCdslpageholder_0; "<CDSLPageHolder::SetCLSID|Trace|HR> "
0x18005ab89  mov     r9d, edi
0x18005ab8c  call    _bidTraceHR
0x18005ab91  mov     edi, eax
0x18005ab93  test    edi, edi
0x18005ab95  jns     short loc_18005AC09
0x18005ab97  test    byte ptr cs:_bidGblFlags, r14b
0x18005ab9e  jz      short loc_18005ABB4
0x18005aba0  mov     r8d, 87h; unsigned int
0x18005aba6  lea     rdx, aCdslpageholder; "<CDSLPageHolder::SetCLSID|OLEDB|ERR> "
0x18005abad  mov     ecx, edi; int
0x18005abaf  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005abb4  mov     rcx, [r12]
0x18005abb8  test    rcx, rcx
0x18005abbb  jz      short loc_18005ABCD
0x18005abbd  mov     rax, [rcx]
0x18005abc0  mov     rax, [rax+10h]
0x18005abc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005abc9  mov     [r12], r13
0x18005abcd  mov     rcx, [r15]
0x18005abd0  test    rcx, rcx
0x18005abd3  jz      short loc_18005AC09
0x18005abd5  mov     rax, [rcx]
0x18005abd8  mov     rax, [rax+10h]
0x18005abdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005abe1  mov     [r15], r13
0x18005abe4  jmp     short loc_18005AC09
0x18005abe6  mov     r8, rbx; unsigned __int16 *
0x18005abe9  mov     rdx, r14; unsigned __int64
0x18005abec  mov     rcx, rax; unsigned __int16 *
0x18005abef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005abf4  mov     r11, [rsi+0E8h]
0x18005abfb  mov     [rsi+50h], r11
0x18005abff  mov     [rsi+0CCh], r13d
0x18005ac06  mov     r14b, 2
0x18005ac09  mov     rcx, [rbp+pv+8]; pv
0x18005ac0d  call    cs:__imp_CoTaskMemFree
0x18005ac13  mov     rcx, qword ptr [rbp+var_28.cx+8]; pv
0x18005ac17  call    cs:__imp_CoTaskMemFree
0x18005ac1d  mov     rcx, [rbp+var_18]; pv
0x18005ac21  call    cs:__imp_CoTaskMemFree
0x18005ac27  test    byte ptr cs:_bidGblFlags, r14b
0x18005ac2e  jz      short loc_18005AC4D
0x18005ac30  mov     rcx, cs:off_1800C8408; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005ac37  lea     r8, aCdslpageholder_0; "<CDSLPageHolder::SetCLSID|Trace|HR> "
0x18005ac3e  mov     r9d, edi
0x18005ac41  mov     edx, 23809h
0x18005ac46  call    _bidTraceHR
0x18005ac4b  mov     edi, eax
0x18005ac4d  mov     eax, edi
0x18005ac4f  add     rsp, 68h
0x18005ac53  pop     r15
0x18005ac55  pop     r14
0x18005ac57  pop     r13
0x18005ac59  pop     r12
0x18005ac5b  pop     rdi
0x18005ac5c  pop     rsi
0x18005ac5d  pop     rbx
0x18005ac5e  pop     rbp
0x18005ac5f  retn
```
