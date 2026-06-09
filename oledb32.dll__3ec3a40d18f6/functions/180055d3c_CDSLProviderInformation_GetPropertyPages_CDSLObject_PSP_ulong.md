# CDSLProviderInformation::GetPropertyPages(CDSLObject *,_PSP * * *,ulong *)

- ea: `0x180055d3c`
- end: `0x180056332`
- name: `?GetPropertyPages@CDSLProviderInformation@@QEAAJPEAVCDSLObject@@PEAPEAPEAU_PSP@@PEAK@Z`
- size: `1526`
- prototype: `__int64 __fastcall(CDSLProviderInformation *__hidden this, struct CDSLObject *, struct _PSP ***, unsigned int *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004be30`
- `0x18004d2a4`
- `0x180056e50`

## callees

- `0x180011bcc`
- `0x180013870`
- `0x18002c1b8`
- `0x18002c328`
- `0x18002eb50`
- `0x18004d950`
- `0x180055520`
- `0x1800555b8`
- `0x180055b74`
- `0x180055d3c`
- `0x180056394`
- `0x180056438`
- `0x18005a7c4`
- `0x180087010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180055eb5`
- `MSDART!MpHeapAlloc` at `0x180055eb5`
- `KERNEL32!GetThreadLocale` at `0x180056042`
- `KERNEL32!GetThreadLocale` at `0x180056042`
- `ole32!CoTaskMemAlloc` at `0x180055f19`
- `ole32!CoTaskMemAlloc` at `0x180055f40`
- `ole32!CoTaskMemAlloc` at `0x180056161`
- `ole32!CoTaskMemAlloc` at `0x180055f19`
- `ole32!CoTaskMemAlloc` at `0x180055f40`
- `ole32!CoTaskMemAlloc` at `0x180056161`
- `ole32!CoTaskMemFree` at `0x180055f77`
- `ole32!CoTaskMemFree` at `0x180056111`
- `ole32!CoTaskMemFree` at `0x18005614f`
- `ole32!CoTaskMemFree` at `0x180055f77`
- `ole32!CoTaskMemFree` at `0x180056111`
- `ole32!CoTaskMemFree` at `0x18005614f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDSLProviderInformation::GetPropertyPages(
        LPVOID *this,
        struct CDSLObject *a2,
        struct _PSP ***a3,
        unsigned int *a4)
{
  struct _PSP ***v5; // rdi
  struct CDSLObject *v6; // rsi
  int v8; // r13d
  int v9; // eax
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // edi
  unsigned int i; // edx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  __int64 v19; // rbx
  LPVOID v20; // rax
  unsigned int v21; // r8d
  LPVOID v22; // rax
  CDSLProviderInformation *j; // rcx
  _QWORD *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // r10
  struct CDSLPropertyPageRoot *ConnectionPage; // r9
  unsigned int v29; // r8d
  __int64 v30; // rdx
  CDSLPageHolder *v31; // rsi
  unsigned int v32; // edi
  const struct _GUID *v33; // rbx
  LCID ThreadLocale; // eax
  int v35; // eax
  CDSLPageHolder *v36; // rcx
  void *v37; // rcx
  LPVOID v38; // rax
  LPVOID v39; // rax
  unsigned int v40; // ebx
  __int64 k; // rcx
  __int64 v42; // rcx
  char *v43; // rdx
  __int64 v44; // rax
  __int64 PropertySheetPageW; // rax
  __int64 v46; // rdx
  __int64 m; // rax
  __int64 v48; // rax
  LPVOID pv[4]; // [rsp+48h] [rbp-20h] BYREF
  __int64 v50; // [rsp+B0h] [rbp+48h] BYREF
  struct CDSLObject *v51; // [rsp+B8h] [rbp+50h]
  struct _PSP ***v52; // [rsp+C0h] [rbp+58h]
  __int64 v53; // [rsp+C8h] [rbp+60h] BYREF

  v52 = a3;
  v51 = a2;
  v5 = a3;
  v6 = a2;
  v8 = 0;
  *a3 = 0;
  *a4 = 0;
  if ( !this[10] && !this[5] )
  {
    v50 = 0;
    v53 = 0;
    *(_OWORD *)pv = 0;
    v9 = CDSLProviderInformation::ActivateProvider((CDSLProviderInformation *)this, 0);
    v10 = v9;
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v9, L"<CDSLProviderInformation::GetPropertyPages|OLEDB|ERR> ", 0x301u);
    if ( v10 >= 0
      && (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))this[12])(this[12], &IID_IServiceProvider, &v50) >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, const GUID *, GUID *, __int64 *))(*(_QWORD *)v50 + 24LL))(
              v50,
              &OLEDB_SVC_DSLPropertyPages,
              &IID_ISpecifyPropertyPages,
              &v53);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      if ( v11 >= 0 )
      {
        *(_OWORD *)pv = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v53 + 24LL))(v53, pv);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
        if ( v12 >= 0 )
        {
          if ( LODWORD(pv[0]) == 2 )
          {
            v13 = 0;
            for ( i = 0; i < 2; ++i )
            {
              v15 = (char *)pv[1] + 16 * (int)i;
              v16 = *v15 - *(_QWORD *)&GUID_NULL.Data1;
              if ( *v15 == *(_QWORD *)&GUID_NULL.Data1 )
                v16 = v15[1] - *(_QWORD *)GUID_NULL.Data4;
              if ( !v16 )
                ++v13;
            }
            if ( v13 != 2 )
            {
              v17 = (_QWORD *)MpHeapAlloc(g_hHeapHandle, 19922944, 520);
              if ( v17 )
              {
                *v17 = 2;
                v18 = v17 + 1;
                `eh vector constructor iterator'(
                  v17 + 1,
                  0x100u,
                  2u,
                  (void (*)(void *))CDSLPageHolder::CDSLPageHolder,
                  (void (*)(void *))CDSLPageHolder::~CDSLPageHolder);
              }
              else
              {
                v18 = 0;
              }
              this[10] = v18;
              if ( v18 )
              {
                *((_DWORD *)this + 18) = 0;
                v19 = v13 + 1;
                v20 = CoTaskMemAlloc(8 * v19);
                this[8] = v20;
                if ( !v20 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    v21 = 811;
LABEL_86:
                    OLEDBTraceErr(-2147024882, L"<CDSLProviderInformation::GetPropertyPages|OLEDB|ERR> ", v21);
                    return 2147942414LL;
                  }
                  return 2147942414LL;
                }
                v22 = CoTaskMemAlloc(104 * v19);
                this[5] = v22;
                if ( !v22 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                    OLEDBTraceErr(-2147024882, L"<CDSLProviderInformation::GetPropertyPages|OLEDB|ERR> ", 0x331u);
                  CoTaskMemFree(this[8]);
                  this[8] = 0;
                  return 2147942414LL;
                }
                *((_DWORD *)this + 12) = 0;
                for ( j = 0; (unsigned int)j < LODWORD(pv[0]); j = (CDSLProviderInformation *)*((unsigned int *)this + 12) )
                {
                  v25 = (char *)pv[1] + 16 * (unsigned int)j;
                  v26 = *v25 - *(_QWORD *)&GUID_NULL.Data1;
                  if ( *v25 == *(_QWORD *)&GUID_NULL.Data1 )
                    v26 = v25[1] - *(_QWORD *)GUID_NULL.Data4;
                  if ( v26 )
                  {
                    GetDialogTitle(hInstance);
                    v30 = *((unsigned int *)this + 12);
                    v31 = (CDSLPageHolder *)((char *)this[10] + 256 * v30);
                    v32 = dword_18009B510[v30];
                    v33 = (const struct _GUID *)((char *)pv[1] + 16 * v30);
                    ThreadLocale = GetThreadLocale();
                    v35 = CDSLPageHolder::SetCLSID(
                            v31,
                            (struct CDSLProviderInformation *)this,
                            ThreadLocale,
                            v33,
                            0,
                            v32,
                            v51);
                    if ( v35 < 0 )
                    {
                      if ( (bidGblFlags & 2) != 0 )
                        OLEDBTraceErr(v35, L"<CDSLProviderInformation::GetPropertyPages|OLEDB|ERR> ", 0x35Au);
                      v36 = (CDSLPageHolder *)this[10];
                      if ( v36 )
                      {
                        if ( *((_QWORD *)v36 - 1) )
                          CDSLPageHolder::`vector deleting destructor'(v36, 3u);
                        else
                          operator delete((char *)v36 - 8);
                      }
                      this[10] = 0;
                      *((_DWORD *)this + 12) = 0;
                      j = 0;
                      v6 = v51;
                      break;
                    }
                    v6 = v51;
                  }
                  else
                  {
                    v27 = 104LL * v8;
                    if ( (_DWORD)j )
                    {
                      ConnectionPage = (struct CDSLObject *)((char *)v6 + 824);
                      v29 = 122;
                    }
                    else
                    {
                      ConnectionPage = CDSLObject::GetConnectionPage(v6, (const struct _GUID *)*this);
                      v29 = 112;
                    }
                    CDSLProviderInformation::LoadPropPageTemplate(
                      j,
                      (struct _PROPSHEETPAGEW *)((char *)this[5] + v27),
                      v29,
                      ConnectionPage);
                    ++v8;
                  }
                  ++*((_DWORD *)this + 12);
                }
                if ( this[10] )
                {
                  *((_DWORD *)this + 12) = (_DWORD)j + 1;
                  CDSLProviderInformation::LoadPropPageTemplate(
                    j,
                    (struct _PROPSHEETPAGEW *)this[5] + v8,
                    0x7Bu,
                    (struct CDSLObject *)((char *)v6 + 904));
                }
              }
            }
            v5 = v52;
          }
          CoTaskMemFree(pv[1]);
        }
      }
    }
    if ( !this[10] )
    {
      CDSLProviderInformation::LoadPropPageTemplates((CDSLProviderInformation *)this, v6);
      if ( !this[5] )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v21 = 884;
          goto LABEL_86;
        }
        return 2147942414LL;
      }
    }
  }
  v37 = this[7];
  if ( v37 )
  {
    CoTaskMemFree(v37);
    this[7] = 0;
  }
  v38 = CoTaskMemAlloc(8LL * *((unsigned int *)this + 12));
  this[7] = v38;
  if ( !v38 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v21 = 899;
      goto LABEL_86;
    }
    return 2147942414LL;
  }
  v39 = this[10];
  *a4 = 0;
  if ( v39 )
  {
    v40 = 0;
    for ( k = 0; (unsigned int)k < *((_DWORD *)this + 12) - 1; k = *a4 )
    {
      v42 = k << 8;
      v43 = (char *)this[10];
      v44 = *(_QWORD *)&v43[v42 + 16] - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v44 )
        v44 = *(_QWORD *)&v43[v42 + 24] - *(_QWORD *)GUID_NULL.Data4;
      if ( v44 )
      {
        if ( *(_QWORD *)&v43[v42 + 32] )
          PropertySheetPageW = IsolationAwareCreatePropertySheetPageW(&v43[v42 + 48]);
        else
          PropertySheetPageW = 0;
        *((_QWORD *)this[7] + *a4) = PropertySheetPageW;
        v46 = *a4;
        if ( !*((_QWORD *)this[7] + v46) )
          goto LABEL_83;
      }
      else
      {
        *((_QWORD *)this[7] + *a4) = IsolationAwareCreatePropertySheetPageW((char *)this[5] + 104 * v40);
        v46 = *a4;
        if ( !*((_QWORD *)this[7] + v46) )
          goto LABEL_83;
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v6 + 6) + 8LL))((__int64)v6 + 48);
        ++v40;
      }
      ++*a4;
    }
    *((_QWORD *)this[7] + *a4) = IsolationAwareCreatePropertySheetPageW((char *)this[5] + 104 * v40);
    v46 = *a4;
    if ( !*((_QWORD *)this[7] + v46) )
    {
LABEL_83:
      while ( (_DWORD)v46 )
      {
        v48 = (unsigned int)(v46 - 1);
        *a4 = v48;
        IsolationAwareDestroyPropertySheetPage(*((_QWORD *)this[7] + v48));
        LODWORD(v46) = *a4;
      }
      if ( (bidGblFlags & 2) == 0 )
        return 2147942414LL;
      v21 = 946;
      goto LABEL_86;
    }
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v6 + 6) + 8LL))((__int64)v6 + 48);
    ++*a4;
  }
  else
  {
    for ( m = 0; (unsigned int)m < *((_DWORD *)this + 12); m = *a4 )
    {
      *((_QWORD *)this[7] + *a4) = IsolationAwareCreatePropertySheetPageW((char *)this[5] + 104 * m);
      v46 = *a4;
      if ( !*((_QWORD *)this[7] + v46) )
        goto LABEL_83;
      (*(void (__fastcall **)(__int64, __int64))(*((_QWORD *)v6 + 6) + 8LL))((__int64)v6 + 48, v46);
      ++*a4;
    }
  }
  *v5 = (struct _PSP **)this[7];
  return 0;
}

```

## disassembly

```asm
0x180055d3c  mov     [rsp-40h+arg_10], r8
0x180055d41  mov     [rsp-40h+arg_8], rdx
0x180055d46  push    rbp
0x180055d47  push    rbx
0x180055d48  push    rsi
0x180055d49  push    rdi
0x180055d4a  push    r12
0x180055d4c  push    r13
0x180055d4e  push    r14
0x180055d50  push    r15
0x180055d52  mov     rbp, rsp
0x180055d55  sub     rsp, 68h
0x180055d59  mov     r15, r9
0x180055d5c  mov     rdi, r8
0x180055d5f  mov     rsi, rdx
0x180055d62  mov     r14, rcx
0x180055d65  xor     r13d, r13d
0x180055d68  mov     [r8], r13
0x180055d6b  mov     [r9], r13d
0x180055d6e  mov     r12d, 8007000Eh
0x180055d74  cmp     [rcx+50h], r13
0x180055d78  jnz     loc_180056146
0x180055d7e  cmp     [rcx+28h], r13
0x180055d82  jnz     loc_180056146
0x180055d88  mov     [rbp+arg_0], r13
0x180055d8c  mov     [rbp+arg_18], r13
0x180055d90  xorps   xmm0, xmm0
0x180055d93  movups  xmmword ptr [rbp+pv], xmm0
0x180055d97  xor     edx, edx; struct IUnknown *
0x180055d99  call    ?ActivateProvider@CDSLProviderInformation@@QEAAJPEAUIUnknown@@@Z; CDSLProviderInformation::ActivateProvider(IUnknown *)
0x180055d9e  mov     ebx, eax
0x180055da0  test    byte ptr cs:_bidGblFlags, 2
0x180055da7  jz      short loc_180055DBD
0x180055da9  mov     r8d, 301h; unsigned int
0x180055daf  lea     rdx, aCdslproviderin; "<CDSLProviderInformation::GetPropertyPa"...
0x180055db6  mov     ecx, eax; int
0x180055db8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180055dbd  test    ebx, ebx
0x180055dbf  js      loc_180056117
0x180055dc5  mov     rcx, [r14+60h]
0x180055dc9  mov     rax, [rcx]
0x180055dcc  lea     r8, [rbp+arg_0]
0x180055dd0  lea     rdx, IID_IServiceProvider
0x180055dd7  mov     rax, [rax]
0x180055dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ddf  test    eax, eax
0x180055de1  js      loc_180056117
0x180055de7  mov     rcx, [rbp+arg_0]
0x180055deb  mov     rax, [rcx]
0x180055dee  lea     r9, [rbp+arg_18]
0x180055df2  lea     r8, IID_ISpecifyPropertyPages
0x180055df9  lea     rdx, OLEDB_SVC_DSLPropertyPages
0x180055e00  mov     rax, [rax+18h]
0x180055e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e09  mov     ebx, eax
0x180055e0b  mov     rcx, [rbp+arg_0]
0x180055e0f  mov     rax, [rcx]
0x180055e12  mov     rax, [rax+10h]
0x180055e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e1b  test    ebx, ebx
0x180055e1d  js      loc_180056117
0x180055e23  xorps   xmm0, xmm0
0x180055e26  movups  xmmword ptr [rbp+pv], xmm0
0x180055e2a  mov     rcx, [rbp+arg_18]
0x180055e2e  mov     rax, [rcx]
0x180055e31  lea     rdx, [rbp+pv]
0x180055e35  mov     rax, [rax+18h]
0x180055e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e3e  mov     ebx, eax
0x180055e40  mov     rcx, [rbp+arg_18]
0x180055e44  mov     rax, [rcx]
0x180055e47  mov     rax, [rax+10h]
0x180055e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e50  test    ebx, ebx
0x180055e52  js      loc_180056117
0x180055e58  mov     ebx, 2
0x180055e5d  cmp     dword ptr [rbp+pv], ebx
0x180055e60  jnz     loc_18005610D
0x180055e66  mov     edi, r13d
0x180055e69  mov     edx, r13d
0x180055e6c  movsxd  rcx, edx
0x180055e6f  shl     rcx, 4
0x180055e73  add     rcx, [rbp+pv+8]
0x180055e77  mov     rax, [rcx]
0x180055e7a  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180055e81  jnz     short loc_180055E8E
0x180055e83  mov     rax, [rcx+8]
0x180055e87  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180055e8e  test    rax, rax
0x180055e91  jnz     short loc_180055E95
0x180055e93  inc     edi
0x180055e95  inc     edx
0x180055e97  cmp     edx, ebx
0x180055e99  jb      short loc_180055E6C
0x180055e9b  cmp     edi, ebx
0x180055e9d  jz      loc_180056109
0x180055ea3  mov     edx, 1300000h
0x180055ea8  mov     r8d, 208h
0x180055eae  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180055eb5  call    cs:__imp_MpHeapAlloc
0x180055ebb  mov     [rbp+var_28], rax
0x180055ebf  test    rax, rax
0x180055ec2  jz      short loc_180055EF3
0x180055ec4  mov     [rax], rbx
0x180055ec7  lea     rbx, [rax+8]
0x180055ecb  lea     rax, ??1CDSLPageHolder@@UEAA@XZ; CDSLPageHolder::~CDSLPageHolder(void)
0x180055ed2  mov     [rsp+68h+var_48], rax; void (*)(void *)
0x180055ed7  lea     r9, ??0CDSLPageHolder@@QEAA@XZ; void (*)(void *)
0x180055ede  mov     edx, 100h; unsigned __int64
0x180055ee3  mov     r8d, 2; unsigned __int64
0x180055ee9  mov     rcx, rbx; void *
0x180055eec  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180055ef1  jmp     short loc_180055EF6
0x180055ef3  mov     rbx, r13
0x180055ef6  mov     [r14+50h], rbx
0x180055efa  test    rbx, rbx
0x180055efd  jz      loc_180056109
0x180055f03  mov     [rbp+var_28], r13
0x180055f07  mov     [r14+48h], r13d
0x180055f0b  lea     eax, [rdi+1]
0x180055f0e  movsxd  rbx, eax
0x180055f11  lea     rcx, ds:0[rbx*8]; cb
0x180055f19  call    cs:__imp_CoTaskMemAlloc
0x180055f1f  mov     [r14+40h], rax
0x180055f23  test    rax, rax
0x180055f26  jnz     short loc_180055F3C
0x180055f28  test    byte ptr cs:_bidGblFlags, 2
0x180055f2f  jz      short loc_180055F81
0x180055f31  mov     r8d, 32Bh
0x180055f37  jmp     loc_18005631E
0x180055f3c  imul    rcx, rbx, 68h ; 'h'; cb
0x180055f40  call    cs:__imp_CoTaskMemAlloc
0x180055f46  mov     [r14+28h], rax
0x180055f4a  test    rax, rax
0x180055f4d  jnz     short loc_180055F89
0x180055f4f  mov     r12d, 8007000Eh
0x180055f55  test    byte ptr cs:_bidGblFlags, 2
0x180055f5c  jz      short loc_180055F73
0x180055f5e  mov     r8d, 331h; unsigned int
0x180055f64  lea     rdx, aCdslproviderin; "<CDSLProviderInformation::GetPropertyPa"...
0x180055f6b  mov     ecx, r12d; int
0x180055f6e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180055f73  mov     rcx, [r14+40h]; pv
0x180055f77  call    cs:__imp_CoTaskMemFree
0x180055f7d  mov     [r14+40h], r13
0x180055f81  mov     eax, r12d
0x180055f84  jmp     loc_180056298
0x180055f89  xor     ebx, ebx
0x180055f8b  mov     [r14+30h], ebx
0x180055f8f  mov     ecx, ebx; this
0x180055f91  lea     rdi, __ImageBase
0x180055f98  cmp     ecx, dword ptr [rbp+pv]
0x180055f9b  jnb     loc_1800560DC
0x180055fa1  mov     r8d, ecx
0x180055fa4  mov     edx, ecx
0x180055fa6  shl     rdx, 4
0x180055faa  add     rdx, [rbp+pv+8]
0x180055fae  mov     rax, [rdx]
0x180055fb1  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180055fb8  jnz     short loc_180055FC5
0x180055fba  mov     rax, [rdx+8]
0x180055fbe  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180055fc5  test    rax, rax
0x180055fc8  jnz     short loc_180056009
0x180055fca  movsxd  rax, r13d
0x180055fcd  imul    r10, rax, 68h ; 'h'
0x180055fd1  test    ecx, ecx
0x180055fd3  jnz     short loc_180055FEB
0x180055fd5  mov     rdx, [r14]; struct _GUID *
0x180055fd8  mov     rcx, rsi; this
0x180055fdb  call    ?GetConnectionPage@CDSLObject@@QEAAPEAVCDSLPropertyPageRoot@@AEBU_GUID@@@Z; CDSLObject::GetConnectionPage(_GUID const &)
0x180055fe0  mov     r9, rax
0x180055fe3  mov     r8d, 70h ; 'p'
0x180055fe9  jmp     short loc_180055FF8
0x180055feb  lea     r9, [rsi+338h]; struct CDSLPropertyPageRoot *
0x180055ff2  mov     r8d, 7Ah ; 'z'; unsigned int
0x180055ff8  mov     rdx, [r14+28h]
0x180055ffc  add     rdx, r10; struct _PROPSHEETPAGEW *
0x180055fff  call    ?LoadPropPageTemplate@CDSLProviderInformation@@IEAAXPEAU_PROPSHEETPAGEW@@KPEAVCDSLPropertyPageRoot@@@Z; CDSLProviderInformation::LoadPropPageTemplate(_PROPSHEETPAGEW *,ulong,CDSLPropertyPageRoot *)
0x180056004  inc     r13d
0x180056007  jmp     short loc_180056080
0x180056009  movzx   edx, ds:rva word_18009B518[rdi+r8*4]
0x180056012  lea     r8, [rbp+var_28]
0x180056016  mov     rcx, cs:hInstance; hModule
0x18005601d  call    GetDialogTitle
0x180056022  mov     edx, [r14+30h]
0x180056026  mov     esi, edx
0x180056028  shl     rsi, 8
0x18005602c  add     rsi, [r14+50h]
0x180056030  mov     edi, ds:rva dword_18009B510[rdi+rdx*4]
0x180056037  shl     rdx, 4
0x18005603b  mov     rbx, [rbp+pv+8]
0x18005603f  add     rbx, rdx
0x180056042  call    cs:__imp_GetThreadLocale
0x180056048  mov     rcx, [rbp+arg_8]
0x18005604c  mov     [rsp+68h+var_38], rcx; struct CDSLObject *
0x180056051  mov     [rsp+68h+var_40], edi; unsigned int
0x180056055  mov     rdx, [rbp+var_28]
0x180056059  mov     [rsp+68h+var_48], rdx; unsigned __int16 *
0x18005605e  mov     r9, rbx; struct _GUID *
0x180056061  mov     r8d, eax; unsigned int
0x180056064  mov     rdx, r14; struct CDSLProviderInformation *
0x180056067  mov     rcx, rsi; this
0x18005606a  call    ?SetCLSID@CDSLPageHolder@@QEAAJPEAVCDSLProviderInformation@@KAEBU_GUID@@PEBGKPEAVCDSLObject@@@Z; CDSLPageHolder::SetCLSID(CDSLProviderInformation *,ulong,_GUID const &,ushort const *,ulong,CDSLObject *)
0x18005606f  xor     ebx, ebx
0x180056071  test    eax, eax
0x180056073  js      short loc_18005608D
0x180056075  mov     rsi, [rbp+arg_8]
0x180056079  lea     rdi, __ImageBase
0x180056080  inc     dword ptr [r14+30h]
0x180056084  mov     ecx, [r14+30h]
0x180056088  jmp     loc_180055F98
0x18005608d  test    byte ptr cs:_bidGblFlags, 2
0x180056094  jz      short loc_1800560AA
0x180056096  mov     r8d, 35Ah; unsigned int
0x18005609c  lea     rdx, aCdslproviderin; "<CDSLProviderInformation::GetPropertyPa"...
0x1800560a3  mov     ecx, eax; int
0x1800560a5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800560aa  mov     rcx, [r14+50h]; this
0x1800560ae  test    rcx, rcx
0x1800560b1  jz      short loc_1800560CE
0x1800560b3  cmp     [rcx-8], rbx
0x1800560b7  jz      short loc_1800560C5
0x1800560b9  mov     edx, 3; unsigned int
0x1800560be  call    ??_ECDSLPageHolder@@UEAAPEAXI@Z; CDSLPageHolder::`vector deleting destructor'(uint)
0x1800560c3  jmp     short loc_1800560CE
0x1800560c5  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800560c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800560ce  mov     [r14+50h], rbx
0x1800560d2  mov     [r14+30h], ebx
0x1800560d6  mov     ecx, ebx; this
0x1800560d8  mov     rsi, [rbp+arg_8]
0x1800560dc  cmp     [r14+50h], rbx
0x1800560e0  jz      short loc_180056106
0x1800560e2  lea     eax, [rcx+1]
0x1800560e5  mov     [r14+30h], eax
0x1800560e9  lea     r9, [rsi+388h]; struct CDSLPropertyPageRoot *
0x1800560f0  movsxd  rax, r13d
0x1800560f3  imul    rdx, rax, 68h ; 'h'
0x1800560f7  add     rdx, [r14+28h]; struct _PROPSHEETPAGEW *
0x1800560fb  mov     r8d, 7Bh ; '{'; unsigned int
0x180056101  call    ?LoadPropPageTemplate@CDSLProviderInformation@@IEAAXPEAU_PROPSHEETPAGEW@@KPEAVCDSLPropertyPageRoot@@@Z; CDSLProviderInformation::LoadPropPageTemplate(_PROPSHEETPAGEW *,ulong,CDSLPropertyPageRoot *)
0x180056106  xor     r13d, r13d
0x180056109  mov     rdi, [rbp+arg_10]
0x18005610d  mov     rcx, [rbp+pv+8]; pv
0x180056111  call    cs:__imp_CoTaskMemFree
0x180056117  cmp     [r14+50h], r13
0x18005611b  jnz     short loc_180056146
0x18005611d  mov     rdx, rsi; struct CDSLObject *
0x180056120  mov     rcx, r14; this
0x180056123  call    ?LoadPropPageTemplates@CDSLProviderInformation@@IEAAXPEAVCDSLObject@@@Z; CDSLProviderInformation::LoadPropPageTemplates(CDSLObject *)
0x180056128  cmp     [r14+28h], r13
0x18005612c  jnz     short loc_180056146
0x18005612e  test    byte ptr cs:_bidGblFlags, 2
0x180056135  jz      loc_180055F81
0x18005613b  mov     r8d, 374h
0x180056141  jmp     loc_18005631E
0x180056146  mov     rcx, [r14+38h]; pv
0x18005614a  test    rcx, rcx
0x18005614d  jz      short loc_180056159
0x18005614f  call    cs:__imp_CoTaskMemFree
0x180056155  mov     [r14+38h], r13
0x180056159  mov     ecx, [r14+30h]
0x18005615d  shl     rcx, 3; cb
0x180056161  call    cs:__imp_CoTaskMemAlloc
0x180056167  mov     [r14+38h], rax
0x18005616b  test    rax, rax
0x18005616e  jnz     short loc_180056188
0x180056170  test    byte ptr cs:_bidGblFlags, 2
0x180056177  jz      loc_180055F81
0x18005617d  mov     r8d, 383h
0x180056183  jmp     loc_18005631E
0x180056188  mov     rax, [r14+50h]
0x18005618c  mov     [r15], r13d
0x18005618f  test    rax, rax
0x180056192  jz      loc_1800562A9
0x180056198  mov     ebx, r13d
0x18005619b  mov     ecx, r13d
0x18005619e  mov     eax, [r14+30h]
0x1800561a2  dec     eax
0x1800561a4  cmp     ecx, eax
0x1800561a6  jnb     loc_180056251
0x1800561ac  shl     rcx, 8
0x1800561b0  mov     rdx, [r14+50h]
0x1800561b4  mov     rax, [rcx+rdx+10h]
0x1800561b9  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800561c0  jnz     short loc_1800561CE
0x1800561c2  mov     rax, [rcx+rdx+18h]
0x1800561c7  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800561ce  test    rax, rax
0x1800561d1  jz      short loc_180056209
0x1800561d3  cmp     [rcx+rdx+20h], r13
0x1800561d8  jnz     short loc_1800561DF
0x1800561da  mov     rax, r13
0x1800561dd  jmp     short loc_1800561EB
0x1800561df  add     rdx, 30h ; '0'
0x1800561e3  add     rcx, rdx
0x1800561e6  call    IsolationAwareCreatePropertySheetPageW
0x1800561eb  mov     edx, [r15]
0x1800561ee  mov     rcx, [r14+38h]
  ... truncated ...
```
