# CDSLControlDataSource::EnumerateDSNs(unsigned __int64 &,CDSLControlDataSource::CDSLDSNInformation * &)

- ea: `0x18004e7dc`
- end: `0x18004ed6b`
- name: `?EnumerateDSNs@CDSLControlDataSource@@AEAAJAEA_KAEAPEAVCDSLDSNInformation@1@@Z`
- size: `1423`
- prototype: `__int64 __fastcall(CDSLControlDataSource *__hidden this, unsigned __int64 *, struct CDSLControlDataSource::CDSLDSNInformation **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180050be0`

## callees

- `0x1800112b0`
- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x18004e7dc`
- `0x180056be8`
- `0x18007e6ca`
- `0x180087010`

## import_xrefs

- `MSDART!mpFree` at `0x18004ed1c`
- `MSDART!mpFree` at `0x18004ed1c`
- `MSDART!MpHeapAlloc` at `0x18004ec5f`
- `MSDART!MpHeapAlloc` at `0x18004ec5f`
- `ole32!CoCreateInstance` at `0x18004e82f`
- `ole32!CoCreateInstance` at `0x18004e82f`

## pseudocode

```c
__int64 __fastcall CDSLControlDataSource::EnumerateDSNs(
        const IID *const *this,
        unsigned __int64 *a2,
        struct CDSLControlDataSource::CDSLDSNInformation **a3)
{
  HRESULT v5; // eax
  unsigned int v6; // edi
  int v7; // edi
  int v8; // edi
  int v9; // edi
  unsigned int v10; // edi
  _BYTE *v11; // rdx
  const unsigned __int16 *v12; // r8
  __int64 v13; // r9
  unsigned __int64 v14; // r14
  struct CDSLSourceRow *v15; // rsi
  __int64 v16; // rax
  struct CDSLControlDataSource::CDSLDSNInformation *v17; // rax
  int v18; // ebx
  unsigned int i; // r11d
  _BYTE *v21; // rbp
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  _BYTE *v24; // rdx
  _BYTE v25[32]; // [rsp+0h] [rbp-118h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+48h] [rbp-D0h] BYREF
  struct CDSLSourceRow *v28; // [rsp+50h] [rbp-C8h] BYREF
  unsigned int pExceptionObject; // [rsp+58h] [rbp-C0h] BYREF
  int v30; // [rsp+5Ch] [rbp-BCh] BYREF
  int v31; // [rsp+60h] [rbp-B8h] BYREF
  int v32; // [rsp+64h] [rbp-B4h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-B0h] BYREF
  int v34; // [rsp+6Ch] [rbp-ACh] BYREF
  __int64 v35; // [rsp+70h] [rbp-A8h] BYREF
  unsigned __int64 v36; // [rsp+78h] [rbp-A0h] BYREF
  unsigned __int64 v37; // [rsp+80h] [rbp-98h] BYREF
  __int64 v38; // [rsp+90h] [rbp-88h] BYREF
  _QWORD v39[7]; // [rsp+98h] [rbp-80h] BYREF
  int v40; // [rsp+D0h] [rbp-48h]
  __int64 v41; // [rsp+D8h] [rbp-40h]
  __int16 v42; // [rsp+E4h] [rbp-34h]
  int v43; // [rsp+120h] [rbp+8h]
  unsigned int v44; // [rsp+120h] [rbp+8h]
  struct IRowset *v47; // [rsp+138h] [rbp+20h] BYREF

  ppv = 0;
  v47 = 0;
  v27 = 0;
  v37 = 0;
  v28 = 0;
  v5 = CoCreateInstance(this[11], 0, 1u, &IID_ISourcesRowset, &ppv);
  try
  {
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v5, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x673u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v6, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x673u);
          if ( (bidGblFlags & 2) != 0 )
            v6 = bidTraceHR(off_1800C83D8[0], 1690633, L"<CDSLControlDataSource::EnumerateDSNs|Trace|HR> ", v6);
        }
      }
      pExceptionObject = v6;
      throw (long *)&pExceptionObject;
    }
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, _QWORD, _QWORD, struct IRowset **))(*(_QWORD *)ppv + 24LL))(
           ppv,
           0,
           &IID_IRowset,
           0,
           0,
           &v47);
    if ( v7 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v7, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x675u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v7, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x675u);
          if ( (bidGblFlags & 2) != 0 )
            v7 = bidTraceHR(
                   off_1800C83D8[0],
                   1692681,
                   L"<CDSLControlDataSource::EnumerateDSNs|Trace|HR> ",
                   (unsigned int)v7);
        }
      }
      v30 = v7;
      throw (long *)&v30;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
    memset_0(v39, 0, 0x50u);
    v39[6] = 5;
    v40 = 0;
    v38 = 1;
    v42 = 130;
    v39[0] = 0;
    v39[2] = 512;
    v41 = 512;
    v8 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))v47->lpVtbl->QueryInterface)(
           v47,
           &IID_IAccessor,
           &v27);
    if ( v8 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v8, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x685u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v8, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x685u);
          if ( (bidGblFlags & 2) != 0 )
            v8 = bidTraceHR(
                   off_1800C83D8[0],
                   1709065,
                   L"<CDSLControlDataSource::EnumerateDSNs|Trace|HR> ",
                   (unsigned int)v8);
        }
      }
      v31 = v8;
      throw (long *)&v31;
    }
    v36 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, _QWORD, unsigned __int64 *, _QWORD))(*(_QWORD *)v27 + 32LL))(
           v27,
           2,
           1,
           &v38,
           0,
           &v36,
           0);
    if ( v9 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v9, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x689u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v9, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x689u);
          if ( (bidGblFlags & 2) != 0 )
            v9 = bidTraceHR(
                   off_1800C83D8[0],
                   1713161,
                   L"<CDSLControlDataSource::EnumerateDSNs|Trace|HR> ",
                   (unsigned int)v9);
        }
      }
      v32 = v9;
      throw (long *)&v32;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
    v10 = DSLGetProviderData(v47, v36, &v37, &v28);
    v43 = v10;
    if ( (v10 & 0x80000000) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v10, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x68Eu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v10, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x68Eu);
          if ( (bidGblFlags & 2) != 0 )
            v10 = bidTraceHR(off_1800C83D8[0], 1718281, L"<CDSLControlDataSource::EnumerateDSNs|Trace|HR> ", v10);
        }
      }
      v33 = v10;
      throw (long *)&v33;
    }
    ((void (__fastcall *)(struct IRowset *))v47->lpVtbl->Release)(v47);
    v47 = 0;
  }
  catch ( ... )
  {
    v24 = v25;
    v23 = v43;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v43, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x695u);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C8850[0] )
          bidTraceA(off_1800C83D8[0], 1726464, off_1800C8850[0], 0);
      }
    }
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
    if ( v47 )
    {
      ((void (__fastcall *)(struct IRowset *))v47->lpVtbl->Release)(v47);
      v47 = 0;
    }
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v27 = 0;
    }
    mpFree(v28, v24, v12, v13);
    if ( v43 >= 0 )
      v23 = -2147467259;
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(
                             off_1800C83D8[0],
                             1755145,
                             L"<CDSLControlDataSource::EnumerateDSNs|Trace|HR> ",
                             v23);
    else
      return v23;
  }
  v14 = v37;
  v15 = v28;
  if ( v37 )
  {
    if ( !v28 )
      goto LABEL_47;
    *a2 = v37;
    v16 = v14 << 9;
    if ( !is_mul_ok(v14, 0x200u) )
      v16 = -1;
    v17 = (struct CDSLControlDataSource::CDSLDSNInformation *)MpHeapAlloc(g_hHeapHandle, 19922944, v16);
    *a3 = v17;
    if ( !v17 )
    {
      v18 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<CDSLControlDataSource::EnumerateDSNs|OLEDB|ERR> ", 0x6BFu);
        if ( (bidGblFlags & 2) != 0 )
          v18 = bidTraceHR(off_1800C83D8[0], 1768457, L"<CDSLControlDataSource::EnumerateDSNs|Trace|HR> ", 2147942414LL);
      }
      try
      {
        v34 = v18;
        throw (long *)&v34;
      }
      catch ( long v35 )
      {
        v11 = v25;
        v21 = v11;
        if ( (bidGblFlags & 2) != 0 && off_1800C8848[0] )
        {
          v22 = *((_DWORD *)v21 + 28);
          bidTraceA(off_1800C83D8[0], 1789952, off_1800C8848[0], v22);
        }
        else
        {
          v22 = *((_DWORD *)v21 + 28);
        }
        *((_DWORD *)v21 + 72) = v22;
        v10 = v44;
        v15 = v28;
        goto LABEL_45;
      }
    }
    for ( i = 0; i < v14; ++i )
    {
      v12 = (const unsigned __int16 *)((char *)v15 + 1060 * i);
      if ( !*((_DWORD *)v12 + 128) )
        StringCchCopyW((unsigned __int16 *)*a3 + 256 * (unsigned __int64)i, 0x100u, v12);
    }
  }
LABEL_45:
  if ( v15 )
    mpFree(v15, v11, v12, v13);
LABEL_47:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C83D8[0], 1801225, L"<CDSLControlDataSource::EnumerateDSNs|Trace|HR> ", v10);
  return v10;
}

```

## disassembly

```asm
0x18004e7dc  mov     rax, rsp
0x18004e7df  mov     [rax+10h], rbx
0x18004e7e3  push    rsi
0x18004e7e4  push    rdi
0x18004e7e5  push    r12
0x18004e7e7  push    r14
0x18004e7e9  push    r15
0x18004e7eb  sub     rsp, 0F0h
0x18004e7f2  mov     r15, r8
0x18004e7f5  mov     r12, rdx
0x18004e7f8  xor     ebx, ebx
0x18004e7fa  mov     [rsp+118h+var_D8], rbx
0x18004e7ff  mov     [rax+20h], rbx
0x18004e803  mov     [rsp+118h+var_D0], rbx
0x18004e808  mov     [rax-98h], rbx
0x18004e80f  mov     [rsp+118h+var_C8], rbx
0x18004e814  lea     rax, [rsp+118h+var_D8]
0x18004e819  mov     [rsp+118h+ppv], rax; ppv
0x18004e81e  lea     r9, IID_ISourcesRowset; riid
0x18004e825  xor     edx, edx; pUnkOuter
0x18004e827  lea     r8d, [rbx+1]; dwClsContext
0x18004e82b  mov     rcx, [rcx+58h]; rclsid
0x18004e82f  call    cs:__imp_CoCreateInstance
0x18004e835  mov     edi, eax
0x18004e837  mov     [rsp+118h+arg_0], eax
0x18004e83e  test    eax, eax
0x18004e840  jns     short loc_18004E8BA
0x18004e842  mov     eax, cs:_bidGblFlags
0x18004e848  test    al, 2
0x18004e84a  jz      short loc_18004E8A5
0x18004e84c  mov     r8d, 673h; unsigned int
0x18004e852  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004e859  mov     ecx, edi; int
0x18004e85b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e860  mov     eax, cs:_bidGblFlags
0x18004e866  test    al, 2
0x18004e868  jz      short loc_18004E8A5
0x18004e86a  mov     r8d, 673h; unsigned int
0x18004e870  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004e877  mov     ecx, edi; int
0x18004e879  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e87e  mov     eax, cs:_bidGblFlags
0x18004e884  test    al, 2
0x18004e886  jz      short loc_18004E8A5
0x18004e888  mov     r9d, edi
0x18004e88b  lea     r8, aCdslcontroldat_3; "<CDSLControlDataSource::EnumerateDSNs|T"...
0x18004e892  mov     edx, 19CC09h
0x18004e897  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004e89e  call    _bidTraceHR
0x18004e8a3  mov     edi, eax
0x18004e8a5  mov     [rsp+118h+pExceptionObject], edi
0x18004e8a9  lea     rdx, _TI1J; pThrowInfo
0x18004e8b0  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18004e8b5  call    _CxxThrowException_0
0x18004e8ba  mov     rcx, [rsp+118h+var_D8]
0x18004e8bf  mov     rax, [rcx]
0x18004e8c2  lea     rdx, [rsp+118h+arg_18]
0x18004e8ca  mov     [rsp+118h+var_F0], rdx
0x18004e8cf  mov     [rsp+118h+ppv], rbx
0x18004e8d4  xor     r9d, r9d
0x18004e8d7  lea     r8, IID_IRowset
0x18004e8de  xor     edx, edx
0x18004e8e0  mov     rax, [rax+18h]
0x18004e8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8e9  mov     edi, eax
0x18004e8eb  mov     [rsp+118h+arg_0], eax
0x18004e8f2  test    eax, eax
0x18004e8f4  jns     short loc_18004E96E
0x18004e8f6  mov     eax, cs:_bidGblFlags
0x18004e8fc  test    al, 2
0x18004e8fe  jz      short loc_18004E959
0x18004e900  mov     r8d, 675h; unsigned int
0x18004e906  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004e90d  mov     ecx, edi; int
0x18004e90f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e914  mov     eax, cs:_bidGblFlags
0x18004e91a  test    al, 2
0x18004e91c  jz      short loc_18004E959
0x18004e91e  mov     r8d, 675h; unsigned int
0x18004e924  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004e92b  mov     ecx, edi; int
0x18004e92d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e932  mov     eax, cs:_bidGblFlags
0x18004e938  test    al, 2
0x18004e93a  jz      short loc_18004E959
0x18004e93c  mov     r9d, edi
0x18004e93f  lea     r8, aCdslcontroldat_3; "<CDSLControlDataSource::EnumerateDSNs|T"...
0x18004e946  mov     edx, 19D409h
0x18004e94b  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004e952  call    _bidTraceHR
0x18004e957  mov     edi, eax
0x18004e959  mov     [rsp+118h+var_BC], edi
0x18004e95d  lea     rdx, _TI1J; pThrowInfo
0x18004e964  lea     rcx, [rsp+118h+var_BC]; pExceptionObject
0x18004e969  call    _CxxThrowException_0
0x18004e96e  mov     rcx, [rsp+118h+var_D8]
0x18004e973  mov     rax, [rcx]
0x18004e976  mov     rax, [rax+10h]
0x18004e97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e97f  mov     [rsp+118h+var_D8], rbx
0x18004e984  xor     edx, edx; Val
0x18004e986  lea     r8d, [rdx+50h]; Size
0x18004e98a  lea     rcx, [rsp+118h+var_80]; void *
0x18004e992  call    memset_0
0x18004e997  mov     [rsp+118h+var_50], 5
0x18004e9a3  mov     [rsp+118h+var_48], ebx
0x18004e9aa  mov     [rsp+118h+var_88], 1
0x18004e9b6  mov     eax, 82h
0x18004e9bb  mov     [rsp+118h+var_34], ax
0x18004e9c3  mov     [rsp+118h+var_80], rbx
0x18004e9cb  mov     eax, 200h
0x18004e9d0  mov     [rsp+118h+var_70], rax
0x18004e9d8  mov     [rsp+118h+var_40], rax
0x18004e9e0  mov     rcx, [rsp+118h+arg_18]
0x18004e9e8  mov     rax, [rcx]
0x18004e9eb  lea     r8, [rsp+118h+var_D0]
0x18004e9f0  lea     rdx, IID_IAccessor
0x18004e9f7  mov     rax, [rax]
0x18004e9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9ff  mov     edi, eax
0x18004ea01  mov     [rsp+118h+arg_0], eax
0x18004ea08  test    eax, eax
0x18004ea0a  jns     short loc_18004EA84
0x18004ea0c  mov     eax, cs:_bidGblFlags
0x18004ea12  test    al, 2
0x18004ea14  jz      short loc_18004EA6F
0x18004ea16  mov     r8d, 685h; unsigned int
0x18004ea1c  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004ea23  mov     ecx, edi; int
0x18004ea25  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004ea2a  mov     eax, cs:_bidGblFlags
0x18004ea30  test    al, 2
0x18004ea32  jz      short loc_18004EA6F
0x18004ea34  mov     r8d, 685h; unsigned int
0x18004ea3a  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004ea41  mov     ecx, edi; int
0x18004ea43  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004ea48  mov     eax, cs:_bidGblFlags
0x18004ea4e  test    al, 2
0x18004ea50  jz      short loc_18004EA6F
0x18004ea52  mov     r9d, edi
0x18004ea55  lea     r8, aCdslcontroldat_3; "<CDSLControlDataSource::EnumerateDSNs|T"...
0x18004ea5c  mov     edx, 1A1409h
0x18004ea61  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004ea68  call    _bidTraceHR
0x18004ea6d  mov     edi, eax
0x18004ea6f  mov     [rsp+118h+var_B8], edi
0x18004ea73  lea     rdx, _TI1J; pThrowInfo
0x18004ea7a  lea     rcx, [rsp+118h+var_B8]; pExceptionObject
0x18004ea7f  call    _CxxThrowException_0
0x18004ea84  mov     [rsp+118h+var_A0], rbx
0x18004ea89  mov     rcx, [rsp+118h+var_D0]
0x18004ea8e  mov     rax, [rcx]
0x18004ea91  mov     [rsp+118h+var_E8], rbx
0x18004ea96  lea     rdx, [rsp+118h+var_A0]
0x18004ea9b  mov     [rsp+118h+var_F0], rdx
0x18004eaa0  mov     [rsp+118h+ppv], rbx
0x18004eaa5  lea     r9, [rsp+118h+var_88]
0x18004eaad  mov     edx, 2
0x18004eab2  lea     r8d, [rdx-1]
0x18004eab6  mov     rax, [rax+20h]
0x18004eaba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eabf  mov     edi, eax
0x18004eac1  mov     [rsp+118h+arg_0], eax
0x18004eac8  test    eax, eax
0x18004eaca  jns     short loc_18004EB44
0x18004eacc  mov     eax, cs:_bidGblFlags
0x18004ead2  test    al, 2
0x18004ead4  jz      short loc_18004EB2F
0x18004ead6  mov     r8d, 689h; unsigned int
0x18004eadc  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004eae3  mov     ecx, edi; int
0x18004eae5  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004eaea  mov     eax, cs:_bidGblFlags
0x18004eaf0  test    al, 2
0x18004eaf2  jz      short loc_18004EB2F
0x18004eaf4  mov     r8d, 689h; unsigned int
0x18004eafa  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004eb01  mov     ecx, edi; int
0x18004eb03  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004eb08  mov     eax, cs:_bidGblFlags
0x18004eb0e  test    al, 2
0x18004eb10  jz      short loc_18004EB2F
0x18004eb12  mov     r9d, edi
0x18004eb15  lea     r8, aCdslcontroldat_3; "<CDSLControlDataSource::EnumerateDSNs|T"...
0x18004eb1c  mov     edx, 1A2409h
0x18004eb21  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004eb28  call    _bidTraceHR
0x18004eb2d  mov     edi, eax
0x18004eb2f  mov     [rsp+118h+var_B4], edi
0x18004eb33  lea     rdx, _TI1J; pThrowInfo
0x18004eb3a  lea     rcx, [rsp+118h+var_B4]; pExceptionObject
0x18004eb3f  call    _CxxThrowException_0
0x18004eb44  mov     rcx, [rsp+118h+var_D0]
0x18004eb49  mov     rax, [rcx]
0x18004eb4c  mov     rax, [rax+10h]
0x18004eb50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb55  mov     [rsp+118h+var_D0], rbx
0x18004eb5a  lea     r9, [rsp+118h+var_C8]; struct CDSLSourceRow **
0x18004eb5f  lea     r8, [rsp+118h+var_98]; unsigned __int64 *
0x18004eb67  mov     rdx, [rsp+118h+var_A0]; unsigned __int64
0x18004eb6c  mov     rcx, [rsp+118h+arg_18]; struct IRowset *
0x18004eb74  call    ?DSLGetProviderData@@YAJPEAUIRowset@@_KAEA_KAEAPEAUCDSLSourceRow@@@Z; DSLGetProviderData(IRowset *,unsigned __int64,unsigned __int64 &,CDSLSourceRow * &)
0x18004eb79  mov     edi, eax
0x18004eb7b  mov     [rsp+118h+arg_0], eax
0x18004eb82  test    eax, eax
0x18004eb84  jns     short loc_18004EBFE
0x18004eb86  mov     eax, cs:_bidGblFlags
0x18004eb8c  test    al, 2
0x18004eb8e  jz      short loc_18004EBE9
0x18004eb90  mov     r8d, 68Eh; unsigned int
0x18004eb96  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004eb9d  mov     ecx, edi; int
0x18004eb9f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004eba4  mov     eax, cs:_bidGblFlags
0x18004ebaa  test    al, 2
0x18004ebac  jz      short loc_18004EBE9
0x18004ebae  mov     r8d, 68Eh; unsigned int
0x18004ebb4  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004ebbb  mov     ecx, edi; int
0x18004ebbd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004ebc2  mov     eax, cs:_bidGblFlags
0x18004ebc8  test    al, 2
0x18004ebca  jz      short loc_18004EBE9
0x18004ebcc  mov     r9d, edi
0x18004ebcf  lea     r8, aCdslcontroldat_3; "<CDSLControlDataSource::EnumerateDSNs|T"...
0x18004ebd6  mov     edx, 1A3809h
0x18004ebdb  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004ebe2  call    _bidTraceHR
0x18004ebe7  mov     edi, eax
0x18004ebe9  mov     [rsp+118h+var_B0], edi
0x18004ebed  lea     rdx, _TI1J; pThrowInfo
0x18004ebf4  lea     rcx, [rsp+118h+var_B0]; pExceptionObject
0x18004ebf9  call    _CxxThrowException_0
0x18004ebfe  mov     rcx, [rsp+118h+arg_18]
0x18004ec06  mov     rax, [rcx]
0x18004ec09  mov     rax, [rax+10h]
0x18004ec0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec12  mov     [rsp+118h+arg_18], rbx
0x18004ec1a  mov     r14, [rsp+118h+var_98]
0x18004ec22  mov     rsi, [rsp+118h+var_C8]
0x18004ec27  test    r14, r14
0x18004ec2a  jz      loc_18004ED14
0x18004ec30  test    rsi, rsi
0x18004ec33  jz      loc_18004ED22
0x18004ec39  mov     [r12], r14
0x18004ec3d  mov     eax, 200h
0x18004ec42  mul     r14
0x18004ec45  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004ec4c  cmovb   rax, rcx
0x18004ec50  mov     r8, rax
0x18004ec53  mov     edx, 1300000h
0x18004ec58  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18004ec5f  call    cs:__imp_MpHeapAlloc
0x18004ec65  mov     [r15], rax
0x18004ec68  test    rax, rax
0x18004ec6b  jnz     short loc_18004ECCC
0x18004ec6d  mov     eax, cs:_bidGblFlags
0x18004ec73  mov     ebx, 8007000Eh
0x18004ec78  test    al, 2
0x18004ec7a  jz      short loc_18004ECB7
0x18004ec7c  mov     r8d, 6BFh; unsigned int
0x18004ec82  lea     rdx, aCdslcontroldat_0; "<CDSLControlDataSource::EnumerateDSNs|O"...
0x18004ec89  mov     ecx, ebx; int
0x18004ec8b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004ec90  mov     eax, cs:_bidGblFlags
0x18004ec96  test    al, 2
0x18004ec98  jz      short loc_18004ECB7
0x18004ec9a  mov     r9d, ebx
0x18004ec9d  lea     r8, aCdslcontroldat_3; "<CDSLControlDataSource::EnumerateDSNs|T"...
0x18004eca4  mov     edx, 1AFC09h
0x18004eca9  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004ecb0  call    _bidTraceHR
0x18004ecb5  mov     ebx, eax
0x18004ecb7  mov     [rsp+118h+var_AC], ebx
0x18004ecbb  lea     rdx, _TI1J; pThrowInfo
0x18004ecc2  lea     rcx, [rsp+118h+var_AC]; pExceptionObject
0x18004ecc7  call    _CxxThrowException_0
0x18004eccc  mov     r11d, ebx
0x18004eccf  test    r14, r14
0x18004ecd2  jz      short loc_18004ED06
0x18004ecd4  mov     ecx, r11d
0x18004ecd7  imul    r8, rcx, 424h
0x18004ecde  add     r8, rsi; unsigned __int16 *
0x18004ece1  cmp     [r8+200h], ebx
0x18004ece8  jnz     short loc_18004ECFB
0x18004ecea  shl     rcx, 9
0x18004ecee  add     rcx, [r15]; unsigned __int16 *
0x18004ecf1  mov     edx, 100h; unsigned __int64
0x18004ecf6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004ecfb  inc     r11d
0x18004ecfe  mov     eax, r11d
0x18004ed01  cmp     rax, r14
0x18004ed04  jb      short loc_18004ECD4
0x18004ed06  jmp     short loc_18004ED14
0x18004ed08  mov     edi, [rsp+118h+arg_0]
0x18004ed0f  mov     rsi, [rsp+118h+var_C8]
0x18004ed14  test    rsi, rsi
0x18004ed17  jz      short loc_18004ED22
0x18004ed19  mov     rcx, rsi
  ... truncated ...
```
