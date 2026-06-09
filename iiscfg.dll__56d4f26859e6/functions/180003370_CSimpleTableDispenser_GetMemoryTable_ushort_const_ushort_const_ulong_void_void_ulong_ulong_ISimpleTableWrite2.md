# CSimpleTableDispenser::GetMemoryTable(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,ISimpleTableWrite2 * *)

- ea: `0x180003370`
- end: `0x180003912`
- name: `?GetMemoryTable@CSimpleTableDispenser@@UEAAJPEBG0KPEAX1KKPEAPEAUISimpleTableWrite2@@@Z`
- size: `1442`
- prototype: `__int64 __fastcall(CSimpleTableDispenser *this, const unsigned __int16 *, wchar_t *, unsigned int, void *, void *, unsigned int, unsigned int, struct ISimpleTableWrite2 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001f70`
- `0x180002970`
- `0x180002b50`
- `0x180002b90`
- `0x180003370`
- `0x180003918`
- `0x180003e04`
- `0x180029ab4`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180003629`
- `ole32!CoTaskMemAlloc` at `0x180003663`
- `ole32!CoTaskMemAlloc` at `0x180003695`
- `ole32!CoTaskMemAlloc` at `0x180003629`
- `ole32!CoTaskMemAlloc` at `0x180003663`
- `ole32!CoTaskMemAlloc` at `0x180003695`

## pseudocode

```c
__int64 __fastcall CSimpleTableDispenser::GetMemoryTable(
        CSimpleTableDispenser *this,
        const unsigned __int16 *a2,
        wchar_t *a3,
        unsigned int a4,
        void *a5,
        void *a6,
        unsigned int a7,
        unsigned int a8,
        struct ISimpleTableWrite2 **a9)
{
  unsigned int v9; // r14d
  int SimpleObjectByID; // ebx
  __int64 v14; // rax
  int v15; // edi
  _DWORD *v16; // rbx
  _QWORD *v17; // rdi
  _DWORD *v18; // rsi
  unsigned int i; // edx
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // r15d
  __int64 v23; // r8
  __int64 v24; // rdx
  struct ISimpleTableWrite2 **v25; // r15
  int v26; // r14d
  unsigned int v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  unsigned int v29; // [rsp+70h] [rbp-90h] BYREF
  void *v30; // [rsp+78h] [rbp-88h] BYREF
  void *v31; // [rsp+80h] [rbp-80h] BYREF
  void *v32; // [rsp+88h] [rbp-78h] BYREF
  int v33; // [rsp+90h] [rbp-70h] BYREF
  _DWORD *v34; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v35; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v36; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD *v37; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v39; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-30h]
  int v41; // [rsp+D8h] [rbp-28h] BYREF
  struct ISimpleTableWrite2 **v42; // [rsp+E0h] [rbp-20h]
  void *v43; // [rsp+E8h] [rbp-18h]
  void *v44; // [rsp+F0h] [rbp-10h]
  const unsigned __int16 *v45; // [rsp+F8h] [rbp-8h]
  char v46[32]; // [rsp+100h] [rbp+0h] BYREF
  _DWORD *v47; // [rsp+120h] [rbp+20h]
  _DWORD *v48; // [rsp+128h] [rbp+28h]
  _DWORD *v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  int v51; // [rsp+15Ch] [rbp+5Ch]

  v9 = 0;
  v44 = a5;
  v43 = a6;
  v42 = a9;
  v45 = a2;
  v29 = a4;
  v40 = 0;
  v31 = 0;
  v30 = 0;
  v33 = 1;
  v39 = 0;
  if ( (a2 && a3 || a4) && a9 )
  {
    v32 = 0;
    SimpleObjectByID = DllGetSimpleObjectByID(6, &IID_ISimpleTableInterceptor, &v32);
    if ( SimpleObjectByID < 0 )
      goto LABEL_6;
    if ( v29 )
      goto LABEL_16;
    if ( (int)TFixedPackedSchemaInterceptor::GetTableID(a3, &v29) < 0 && (a8 & 0x200000) != 0 )
    {
      v29 = 0;
      v14 = -1;
      *(_QWORD *)&v39 = a3;
      *((_QWORD *)&v39 + 1) = 0x100000002LL;
      LODWORD(v40) = 130;
      do
        ++v14;
      while ( a3[v14] );
      HIDWORD(v40) = v14;
      v15 = CSimpleTableDispenser::HardCodedIntercept(this, 16, L"META", L"TABLEMETA", 0, &v39, &v33);
      if ( v15 < 0 )
      {
        ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v32);
        ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v30);
        ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v31);
        return (unsigned int)v15;
      }
      HIDWORD(v39) = 0;
      SimpleObjectByID = CSimpleTableDispenser::HardCodedIntercept(this, 16, L"META", L"COLUMNMETA", 0, &v39, &v33);
      if ( SimpleObjectByID < 0 )
        goto LABEL_6;
    }
    if ( v29 )
    {
LABEL_16:
      *((_QWORD *)&v39 + 1) = 0xF000000600000002uLL;
      *(_QWORD *)&v39 = &v29;
      v40 = 19;
      SimpleObjectByID = CSimpleTableDispenser::GetMetaTable(this, 0x2A601B00u, &v39, &v33, v27, &v30);
      if ( SimpleObjectByID < 0 )
        goto LABEL_6;
      SimpleObjectByID = CSimpleTableDispenser::GetMetaTable(this, 0xE15A5200, &v39, &v33, v28, &v31);
      if ( SimpleObjectByID < 0 )
        goto LABEL_6;
    }
    v41 = 8;
    v35 = 0;
    SimpleObjectByID = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, int *, _QWORD, unsigned int **))(*(_QWORD *)v30 + 32LL))(
                         v30,
                         0,
                         1,
                         &v41,
                         0,
                         &v35);
    if ( SimpleObjectByID < 0 )
      goto LABEL_6;
    v34 = CoTaskMemAlloc(saturated_mul(*v35, 0xCu));
    v16 = v34;
    if ( v34 )
    {
      v36 = CoTaskMemAlloc(saturated_mul(*v35, 8u));
      v17 = v36;
      if ( v36 )
      {
        v37 = CoTaskMemAlloc(saturated_mul(*v35, 4u));
        v18 = v37;
        if ( v37 )
        {
          for ( i = 0; i < *v35; v16[3 * v20 + 1] = 0 )
            v20 = i++;
          memset_0(v46, 0, 0x40u);
          while ( 1 )
          {
            v21 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)v31 + 32LL))(v31, v9, 8);
            v22 = v21;
            if ( v21 == -2145318890 )
              break;
            if ( v21 < 0 )
            {
              TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v37);
              TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v36);
              TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v34);
              ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v32);
              ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v30);
              ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v31);
              return v22;
            }
            v23 = v9++;
            v24 = 3 * v23;
            v16[v24] = *v47;
            v16[v24 + 1] = *v48;
            v16[v24 + 2] = *v49;
            v17[v23] = v50;
            v18[v23] = v51;
          }
          if ( *v35 == v9 )
          {
            v25 = v42;
            v26 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, wchar_t *, _QWORD, void *, void *, unsigned int, unsigned int, CSimpleTableDispenser *, _QWORD, _QWORD, struct ISimpleTableWrite2 **))(*(_QWORD *)v32 + 24LL))(
                    v32,
                    v45,
                    a3,
                    v29,
                    v44,
                    v43,
                    a7,
                    a8,
                    this,
                    0,
                    0,
                    v42);
            if ( v26 < 0 )
            {
              TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v37);
              TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v36);
              TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v34);
              SimpleObjectByID = v26;
              goto LABEL_6;
            }
            ATL::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>::CComQIPtr<ISimpleTableController,&_GUID const IID_ISimpleTableController>(
              &v38,
              *v25);
            if ( v38 )
            {
              SimpleObjectByID = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *, _QWORD *, _DWORD *))(*(_QWORD *)v38 + 64LL))(
                                   v38,
                                   a8,
                                   *v35,
                                   v16,
                                   v17,
                                   v18);
              if ( SimpleObjectByID >= 0 )
                SimpleObjectByID = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 24LL))(v38);
              ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v38);
              TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v37);
              TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v36);
              TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v34);
              goto LABEL_6;
            }
            ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v38);
          }
          TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v37);
          TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v36);
          TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v34);
          SimpleObjectByID = -2147418113;
LABEL_6:
          ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v32);
          ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v30);
          ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v31);
          return (unsigned int)SimpleObjectByID;
        }
        TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v37);
      }
      TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v36);
    }
    TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(&v34);
    SimpleObjectByID = -2147024882;
    goto LABEL_6;
  }
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v30);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v31);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180003370  push    rbp
0x180003372  push    rbx
0x180003373  push    rsi
0x180003374  push    rdi
0x180003375  push    r12
0x180003377  push    r13
0x180003379  push    r14
0x18000337b  push    r15
0x18000337d  lea     rbp, [rsp-78h]
0x180003382  sub     rsp, 178h
0x180003389  mov     rax, cs:__security_cookie
0x180003390  xor     rax, rsp
0x180003393  mov     [rbp+0B0h+var_50], rax
0x180003397  mov     rax, [rbp+0B0h+arg_20]
0x18000339e  xor     r14d, r14d
0x1800033a1  mov     [rbp+0B0h+var_C0], rax
0x1800033a5  mov     r13, rcx
0x1800033a8  mov     rax, [rbp+0B0h+arg_28]
0x1800033af  xor     ecx, ecx
0x1800033b1  mov     [rbp+0B0h+var_C8], rax
0x1800033b5  xorps   xmm0, xmm0
0x1800033b8  mov     rax, [rbp+0B0h+arg_40]
0x1800033bf  mov     r12, r8
0x1800033c2  mov     [rbp+0B0h+var_D0], rax
0x1800033c6  mov     [rbp+0B0h+var_B8], rdx
0x1800033ca  mov     [rsp+1B0h+var_140], r9d
0x1800033cf  mov     [rbp+0B0h+var_E0], rcx
0x1800033d3  mov     [rbp+0B0h+var_130], r14
0x1800033d7  mov     [rsp+1B0h+var_138], r14
0x1800033dc  mov     [rbp+0B0h+var_120], 1
0x1800033e3  movups  [rbp+0B0h+var_F0], xmm0
0x1800033e7  test    rdx, rdx
0x1800033ea  jz      short loc_1800033F1
0x1800033ec  test    r8, r8
0x1800033ef  jnz     short loc_1800033FA
0x1800033f1  test    r9d, r9d
0x1800033f4  jz      loc_1800038DA
0x1800033fa  test    rax, rax
0x1800033fd  jz      loc_1800038DA
0x180003403  lea     r8, [rbp+0B0h+var_128]
0x180003407  mov     [rbp+0B0h+var_128], r14
0x18000340b  lea     rdx, IID_ISimpleTableInterceptor
0x180003412  mov     ecx, 6
0x180003417  call    DllGetSimpleObjectByID
0x18000341c  mov     ebx, eax
0x18000341e  test    eax, eax
0x180003420  jns     short loc_180003445
0x180003422  lea     rcx, [rbp+0B0h+var_128]
0x180003426  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000342b  lea     rcx, [rsp+1B0h+var_138]
0x180003430  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180003435  lea     rcx, [rbp+0B0h+var_130]
0x180003439  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000343e  mov     eax, ebx
0x180003440  jmp     loc_1800038F2
0x180003445  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003449  mov     r15d, 2
0x18000344f  cmp     [rsp+1B0h+var_140], r14d
0x180003454  jnz     loc_180003569
0x18000345a  lea     rdx, [rsp+1B0h+var_140]; unsigned int *
0x18000345f  mov     rcx, r12; String2
0x180003462  call    ?GetTableID@TFixedPackedSchemaInterceptor@@SAJPEBGAEAK@Z; TFixedPackedSchemaInterceptor::GetTableID(ushort const *,ulong &)
0x180003467  test    eax, eax
0x180003469  jns     loc_180003562
0x18000346f  mov     ebx, [rbp+0B0h+arg_38]
0x180003475  and     ebx, 200000h
0x18000347b  jz      loc_180003562
0x180003481  mov     [rsp+1B0h+var_140], r14d
0x180003486  mov     rax, rsi
0x180003489  mov     qword ptr [rbp+0B0h+var_F0], r12
0x18000348d  mov     dword ptr [rbp+0B0h+var_F0+8], r15d
0x180003491  mov     dword ptr [rbp+0B0h+var_F0+0Ch], 1
0x180003498  mov     dword ptr [rbp+0B0h+var_E0], 82h
0x18000349f  inc     rax
0x1800034a2  cmp     [r12+rax*2], r14w
0x1800034a7  jnz     short loc_18000349F
0x1800034a9  mov     dword ptr [rbp+0B0h+var_E0+4], eax
0x1800034ac  lea     r9, aTablemeta; "TABLEMETA"
0x1800034b3  lea     rax, [rsp+1B0h+var_138]
0x1800034b8  mov     edx, 10h
0x1800034bd  mov     [rsp+1B0h+var_168], rax
0x1800034c2  lea     r8, aMeta; "META"
0x1800034c9  mov     dword ptr [rsp+1B0h+var_170], ebx
0x1800034cd  lea     rax, [rbp+0B0h+var_120]
0x1800034d1  mov     [rsp+1B0h+var_180], rax
0x1800034d6  mov     rcx, r13
0x1800034d9  lea     rax, [rbp+0B0h+var_F0]
0x1800034dd  mov     [rsp+1B0h+var_188], rax
0x1800034e2  mov     [rsp+1B0h+var_190], r14d
0x1800034e7  call    ?HardCodedIntercept@CSimpleTableDispenser@@AEBAJW4eSERVERWIRINGMETA_Interceptor@@PEBG1KPEAX2KKPEAPEAX@Z; CSimpleTableDispenser::HardCodedIntercept(eSERVERWIRINGMETA_Interceptor,ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,void * *)
0x1800034ec  mov     edi, eax
0x1800034ee  test    eax, eax
0x1800034f0  jns     short loc_180003515
0x1800034f2  lea     rcx, [rbp+0B0h+var_128]
0x1800034f6  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800034fb  lea     rcx, [rsp+1B0h+var_138]
0x180003500  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180003505  lea     rcx, [rbp+0B0h+var_130]
0x180003509  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000350e  mov     eax, edi
0x180003510  jmp     loc_1800038F2
0x180003515  lea     rax, [rbp+0B0h+var_130]
0x180003519  mov     dword ptr [rbp+0B0h+var_F0+0Ch], r14d
0x18000351d  mov     [rsp+1B0h+var_168], rax
0x180003522  lea     r9, aColumnmeta; "COLUMNMETA"
0x180003529  mov     dword ptr [rsp+1B0h+var_170], ebx
0x18000352d  lea     rax, [rbp+0B0h+var_120]
0x180003531  mov     [rsp+1B0h+var_180], rax
0x180003536  lea     r8, aMeta; "META"
0x18000353d  lea     rax, [rbp+0B0h+var_F0]
0x180003541  mov     edx, 10h
0x180003546  mov     [rsp+1B0h+var_188], rax
0x18000354b  mov     rcx, r13
0x18000354e  mov     [rsp+1B0h+var_190], r14d; unsigned int
0x180003553  call    ?HardCodedIntercept@CSimpleTableDispenser@@AEBAJW4eSERVERWIRINGMETA_Interceptor@@PEBG1KPEAX2KKPEAPEAX@Z; CSimpleTableDispenser::HardCodedIntercept(eSERVERWIRINGMETA_Interceptor,ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,void * *)
0x180003558  mov     ebx, eax
0x18000355a  test    eax, eax
0x18000355c  js      loc_180003422
0x180003562  cmp     [rsp+1B0h+var_140], r14d
0x180003567  jz      short loc_1800035D6
0x180003569  lea     rax, [rsp+1B0h+var_140]
0x18000356e  mov     dword ptr [rbp+0B0h+var_F0+8], r15d
0x180003572  mov     qword ptr [rbp+0B0h+var_F0], rax
0x180003576  lea     r9, [rbp+0B0h+var_120]; void *
0x18000357a  lea     rax, [rsp+1B0h+var_138]
0x18000357f  mov     dword ptr [rbp+0B0h+var_F0+0Ch], 0F0000006h
0x180003586  lea     r8, [rbp+0B0h+var_F0]; void *
0x18000358a  mov     [rsp+1B0h+var_188], rax; void **
0x18000358f  mov     edx, 2A601B00h; unsigned int
0x180003594  mov     [rbp+0B0h+var_E0], 13h
0x18000359c  mov     rcx, r13; this
0x18000359f  call    ?GetMetaTable@CSimpleTableDispenser@@AEAAJKPEAX0KPEAPEAX@Z; CSimpleTableDispenser::GetMetaTable(ulong,void *,void *,ulong,void * *)
0x1800035a4  mov     ebx, eax
0x1800035a6  test    eax, eax
0x1800035a8  js      loc_180003422
0x1800035ae  lea     rax, [rbp+0B0h+var_130]
0x1800035b2  mov     edx, 0E15A5200h; unsigned int
0x1800035b7  lea     r9, [rbp+0B0h+var_120]; void *
0x1800035bb  mov     [rsp+1B0h+var_188], rax; void **
0x1800035c0  lea     r8, [rbp+0B0h+var_F0]; void *
0x1800035c4  mov     rcx, r13; this
0x1800035c7  call    ?GetMetaTable@CSimpleTableDispenser@@AEAAJKPEAX0KPEAPEAX@Z; CSimpleTableDispenser::GetMetaTable(ulong,void *,void *,ulong,void * *)
0x1800035cc  mov     ebx, eax
0x1800035ce  test    eax, eax
0x1800035d0  js      loc_180003422
0x1800035d6  mov     rcx, [rsp+1B0h+var_138]
0x1800035db  lea     rdx, [rbp+0B0h+var_110]
0x1800035df  mov     [rsp+1B0h+var_188], rdx
0x1800035e4  lea     r9, [rbp+0B0h+var_D8]
0x1800035e8  mov     [rbp+0B0h+var_D8], 8
0x1800035ef  xor     edx, edx
0x1800035f1  mov     [rbp+0B0h+var_110], r14
0x1800035f5  mov     rax, [rcx]
0x1800035f8  mov     qword ptr [rsp+1B0h+var_190], r14
0x1800035fd  lea     r8d, [rdx+1]
0x180003601  mov     rax, [rax+20h]
0x180003605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000360a  mov     ebx, eax
0x18000360c  test    eax, eax
0x18000360e  js      loc_180003422
0x180003614  mov     rax, [rbp+0B0h+var_110]
0x180003618  mov     ecx, [rax]
0x18000361a  mov     eax, 0Ch
0x18000361f  mul     rcx
0x180003622  cmovb   rax, rsi
0x180003626  mov     rcx, rax; cb
0x180003629  call    cs:__imp_CoTaskMemAlloc
0x18000362f  mov     [rbp+0B0h+var_118], rax
0x180003633  mov     rbx, rax
0x180003636  test    rax, rax
0x180003639  jnz     short loc_18000364E
0x18000363b  lea     rcx, [rbp+0B0h+var_118]
0x18000363f  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x180003644  mov     ebx, 8007000Eh
0x180003649  jmp     loc_180003422
0x18000364e  mov     rax, [rbp+0B0h+var_110]
0x180003652  mov     ecx, [rax]
0x180003654  mov     eax, 8
0x180003659  mul     rcx
0x18000365c  cmovb   rax, rsi
0x180003660  mov     rcx, rax; cb
0x180003663  call    cs:__imp_CoTaskMemAlloc
0x180003669  mov     [rbp+0B0h+var_108], rax
0x18000366d  mov     rdi, rax
0x180003670  test    rax, rax
0x180003673  jnz     short loc_180003680
0x180003675  lea     rcx, [rbp+0B0h+var_108]
0x180003679  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x18000367e  jmp     short loc_18000363B
0x180003680  mov     rax, [rbp+0B0h+var_110]
0x180003684  mov     ecx, [rax]
0x180003686  mov     eax, 4
0x18000368b  mul     rcx
0x18000368e  cmovb   rax, rsi
0x180003692  mov     rcx, rax; cb
0x180003695  call    cs:__imp_CoTaskMemAlloc
0x18000369b  mov     [rbp+0B0h+var_100], rax
0x18000369f  mov     rsi, rax
0x1800036a2  test    rax, rax
0x1800036a5  jnz     short loc_1800036B2
0x1800036a7  lea     rcx, [rbp+0B0h+var_100]
0x1800036ab  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x1800036b0  jmp     short loc_180003675
0x1800036b2  mov     rax, [rbp+0B0h+var_110]
0x1800036b6  mov     edx, r14d
0x1800036b9  cmp     [rax], r14d
0x1800036bc  jbe     short loc_1800036D3
0x1800036be  mov     eax, edx
0x1800036c0  inc     edx
0x1800036c2  lea     rcx, [rax+rax*2]
0x1800036c6  mov     [rbx+rcx*4+4], r14d
0x1800036cb  mov     rax, [rbp+0B0h+var_110]
0x1800036cf  cmp     edx, [rax]
0x1800036d1  jb      short loc_1800036BE
0x1800036d3  xor     edx, edx; Val
0x1800036d5  lea     rcx, [rbp+0B0h+var_B0]; void *
0x1800036d9  lea     r8d, [rdx+40h]; Size
0x1800036dd  call    memset_0
0x1800036e2  mov     rcx, [rbp+0B0h+var_130]
0x1800036e6  lea     rdx, [rbp+0B0h+var_B0]
0x1800036ea  mov     [rsp+1B0h+var_188], rdx
0x1800036ef  xor     r9d, r9d
0x1800036f2  lea     rdx, [rbp+0B0h+var_70]
0x1800036f6  mov     qword ptr [rsp+1B0h+var_190], rdx
0x1800036fb  mov     edx, r14d
0x1800036fe  mov     rax, [rcx]
0x180003701  lea     r8d, [r9+8]
0x180003705  mov     rax, [rax+20h]
0x180003709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370e  mov     r15d, eax
0x180003711  cmp     eax, 80210816h
0x180003716  jz      short loc_180003793
0x180003718  test    eax, eax
0x18000371a  js      short loc_180003754
0x18000371c  mov     rax, [rbp+0B0h+var_90]
0x180003720  mov     r8d, r14d
0x180003723  inc     r14d
0x180003726  mov     ecx, [rax]
0x180003728  lea     rdx, [r8+r8*2]
0x18000372c  mov     [rbx+rdx*4], ecx
0x18000372f  mov     rax, [rbp+0B0h+var_88]
0x180003733  mov     ecx, [rax]
0x180003735  mov     [rbx+rdx*4+4], ecx
0x180003739  mov     rax, [rbp+0B0h+var_80]
0x18000373d  mov     ecx, [rax]
0x18000373f  mov     [rbx+rdx*4+8], ecx
0x180003743  mov     rax, [rbp+0B0h+var_78]
0x180003747  mov     [rdi+r8*8], rax
0x18000374b  mov     eax, [rbp+0B0h+var_54]
0x18000374e  mov     [rsi+r8*4], eax
0x180003752  jmp     short loc_1800036E2
0x180003754  lea     rcx, [rbp+0B0h+var_100]
0x180003758  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x18000375d  lea     rcx, [rbp+0B0h+var_108]
0x180003761  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x180003766  lea     rcx, [rbp+0B0h+var_118]
0x18000376a  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x18000376f  lea     rcx, [rbp+0B0h+var_128]
0x180003773  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180003778  lea     rcx, [rsp+1B0h+var_138]
0x18000377d  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180003782  lea     rcx, [rbp+0B0h+var_130]
0x180003786  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18000378b  mov     eax, r15d
0x18000378e  jmp     loc_1800038F2
0x180003793  mov     rax, [rbp+0B0h+var_110]
0x180003797  cmp     [rax], r14d
0x18000379a  jz      short loc_1800037C1
0x18000379c  lea     rcx, [rbp+0B0h+var_100]
0x1800037a0  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x1800037a5  lea     rcx, [rbp+0B0h+var_108]
0x1800037a9  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x1800037ae  lea     rcx, [rbp+0B0h+var_118]
0x1800037b2  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x1800037b7  mov     ebx, 8000FFFFh
0x1800037bc  jmp     loc_180003422
0x1800037c1  mov     rcx, [rbp+0B0h+var_128]
0x1800037c5  mov     r8, r12
0x1800037c8  mov     r10d, [rbp+0B0h+arg_30]
0x1800037cf  mov     r9, [rbp+0B0h+var_C8]
0x1800037d3  mov     r15, [rbp+0B0h+var_D0]
0x1800037d7  mov     rax, [rcx]
0x1800037da  mov     rdx, [rbp+0B0h+var_B8]
0x1800037de  mov     [rsp+1B0h+var_158], r15
0x1800037e3  mov     [rsp+1B0h+var_160], 0
0x1800037ec  mov     rax, [rax+18h]
0x1800037f0  mov     [rsp+1B0h+var_168], 0
0x1800037f9  mov     [rsp+1B0h+var_170], r13
0x1800037fe  mov     r13d, [rbp+0B0h+arg_38]
0x180003805  mov     [rsp+1B0h+var_178], r13d
0x18000380a  mov     dword ptr [rsp+1B0h+var_180], r10d
0x18000380f  mov     [rsp+1B0h+var_188], r9
0x180003814  mov     r9, [rbp+0B0h+var_C0]
0x180003818  mov     qword ptr [rsp+1B0h+var_190], r9
0x18000381d  mov     r9d, [rsp+1B0h+var_140]
0x180003822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003827  mov     r14d, eax
0x18000382a  test    eax, eax
0x18000382c  jns     short loc_180003851
0x18000382e  lea     rcx, [rbp+0B0h+var_100]
  ... truncated ...
```
