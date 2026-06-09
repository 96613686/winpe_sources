# TMBSchemaCompilation::Compile(ISimpleTableDispenser2 *,ushort const *,ushort const *,FixedTableHeap const *,TOutput *)

- ea: `0x180015f34`
- end: `0x1800169f7`
- name: `?Compile@TMBSchemaCompilation@@QEAAJPEAUISimpleTableDispenser2@@PEBG1PEBVFixedTableHeap@@PEAVTOutput@@@Z`
- size: `2755`
- prototype: `__int64 __fastcall(TMBSchemaCompilation *this, struct ISimpleTableDispenser2 *, const unsigned __int16 *, const unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180002d30`

## callees

- `0x180002bc4`
- `0x180005870`
- `0x180011b38`
- `0x180012734`
- `0x18001565c`
- `0x180015f34`
- `0x180017614`
- `0x180017814`
- `0x180017e84`
- `0x18001e000`
- `0x180020d60`
- `0x180020e10`
- `0x1800226a0`
- `0x18002324c`
- `0x1800232f0`
- `0x180023e00`
- `0x18002e0b2`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180016214`
- `msvcrt!wcscat_s` at `0x18001622b`
- `msvcrt!wcscat_s` at `0x180016394`
- `msvcrt!wcscat_s` at `0x180016214`
- `msvcrt!wcscat_s` at `0x18001622b`
- `msvcrt!wcscat_s` at `0x180016394`
- `msvcrt!swprintf_s` at `0x1800161e6`
- `msvcrt!swprintf_s` at `0x1800161e6`
- `msvcrt!wcscpy_s` at `0x1800161fd`
- `msvcrt!wcscpy_s` at `0x180016385`
- `msvcrt!wcscpy_s` at `0x1800161fd`
- `msvcrt!wcscpy_s` at `0x180016385`
- `KERNEL32!GetTickCount` at `0x180015fb0`
- `KERNEL32!GetTickCount` at `0x18001665f`
- `KERNEL32!GetTickCount` at `0x180015fb0`
- `KERNEL32!GetTickCount` at `0x18001665f`
- `KERNEL32!MoveFileExW` at `0x180016322`
- `KERNEL32!MoveFileExW` at `0x180016332`
- `KERNEL32!MoveFileExW` at `0x180016322`
- `KERNEL32!MoveFileExW` at `0x180016332`
- `KERNEL32!GetLastError` at `0x180016340`
- `KERNEL32!GetLastError` at `0x180016340`
- `ole32!CoTaskMemAlloc` at `0x180016139`
- `ole32!CoTaskMemAlloc` at `0x18001615a`
- `ole32!CoTaskMemAlloc` at `0x18001617f`
- `ole32!CoTaskMemAlloc` at `0x18001635e`
- `ole32!CoTaskMemAlloc` at `0x180016139`
- `ole32!CoTaskMemAlloc` at `0x18001615a`
- `ole32!CoTaskMemAlloc` at `0x18001617f`
- `ole32!CoTaskMemAlloc` at `0x18001635e`
- `IisRTL!PuDbgPrint` at `0x180016559`
- `IisRTL!PuDbgPrint` at `0x180016559`

## string_xrefs

- `0x180015ff0`: `TMetaInferrence().Compile(mbmeta, *pOut);\n`
- `0x18001604d`: `THashedPKIndexes().Compile(mbmeta, *pOut);\n`
- `0x1800160c3`: `THashedUniqueIndexes().Compile(mbmeta, *pOut);\n`
- `0x180016435`: `inetsrv\iis\mb\config\src\core\schemagen\mbschemacompilation.cpp`
- `0x1800164f1`: `inetsrv\iis\mb\config\src\core\schemagen\mbschemacompilation.cpp`
- `0x1800164b6`: `MoveFileEx`
- `0x180016532`: `Could not move to %ws, hr=0x%x\n`
- `0x18001653e`: `TMBSchemaCompilation::Compile`
- `0x18001654b`: `inetsrv\iis\mb\config\src\core\schemagen\mbschemacompilation.cpp`
- `0x180016378`: `MoveFileEx to `

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall TMBSchemaCompilation::Compile(
        TMBSchemaCompilation *this,
        struct ISimpleTableDispenser2 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *Src)
{
  __int64 v9; // r12
  wchar_t *v10; // rsi
  wchar_t *v11; // rbx
  char *v12; // rax
  char *v13; // rdi
  __int64 v14; // r14
  signed int LastError; // edi
  unsigned __int64 v16; // r12
  wchar_t *v17; // rax
  wchar_t *v18; // rbx
  __int64 v19; // r9
  __int64 v20; // r9
  int v21; // ebx
  DWORD TickCount; // ebx
  void (*v23)(void ***, const wchar_t *, ...); // rdi
  unsigned int v24; // eax
  struct TOutput *v25; // [rsp+20h] [rbp-C48h]
  __int64 v26; // [rsp+30h] [rbp-C38h]
  void **v27; // [rsp+B0h] [rbp-BB8h] BYREF
  int v28; // [rsp+B8h] [rbp-BB0h] BYREF
  void **v29; // [rsp+C0h] [rbp-BA8h] BYREF
  char *v30; // [rsp+C8h] [rbp-BA0h]
  char *v31; // [rsp+D0h] [rbp-B98h] BYREF
  wchar_t *v32; // [rsp+D8h] [rbp-B90h] BYREF
  wchar_t *v33; // [rsp+E0h] [rbp-B88h] BYREF
  wchar_t *v34; // [rsp+E8h] [rbp-B80h] BYREF
  _QWORD v35[4]; // [rsp+F0h] [rbp-B78h] BYREF
  __int128 v36; // [rsp+110h] [rbp-B58h]
  void **v37; // [rsp+120h] [rbp-B48h] BYREF
  __int128 v38; // [rsp+128h] [rbp-B40h]
  int v39; // [rsp+138h] [rbp-B30h]
  _QWORD v40[4]; // [rsp+148h] [rbp-B20h] BYREF
  __int128 v41; // [rsp+168h] [rbp-B00h]
  __int128 v42; // [rsp+178h] [rbp-AF0h]
  __int128 v43; // [rsp+188h] [rbp-AE0h]
  wchar_t *v44; // [rsp+198h] [rbp-AD0h]
  _BYTE v45[28]; // [rsp+1A0h] [rbp-AC8h] BYREF
  unsigned int v46; // [rsp+1BCh] [rbp-AACh]
  unsigned int v47; // [rsp+1D4h] [rbp-A94h]
  int v48; // [rsp+1ECh] [rbp-A7Ch]
  unsigned int v49; // [rsp+204h] [rbp-A64h]
  unsigned int v50; // [rsp+21Ch] [rbp-A4Ch]
  unsigned int v51; // [rsp+234h] [rbp-A34h]
  unsigned int v52; // [rsp+24Ch] [rbp-A1Ch]
  unsigned int v53; // [rsp+264h] [rbp-A04h]
  unsigned int v54; // [rsp+27Ch] [rbp-9ECh]
  int v55; // [rsp+294h] [rbp-9D4h]
  __int64 v56[305]; // [rsp+298h] [rbp-9D0h] BYREF

  v27 = &TNullOutput::`vftable';
  if ( !a2 || !Src || !FixedTableHeap::IsValid((FixedTableHeap *)&g_aFixedTableHeap) )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 321) )
    return 2149648480LL;
  LODWORD(v34) = GetTickCount();
  TMetabaseMetaXmlFile::TMetabaseMetaXmlFile(
    (TMetabaseMetaXmlFile *)v45,
    (const struct FixedTableHeap *)&g_aFixedTableHeap,
    a3,
    a2,
    (struct TOutput *)&v27);
  ((void (__fastcall *)(void ***, const wchar_t *))*v27)(&v27, L"TMetaInferrence().Compile(mbmeta, *pOut);\r\n");
  v37 = &TMetaInferrence::`vftable';
  v38 = 0;
  v39 = 0;
  TMetaInferrence::Compile((TMetaInferrence *)&v37, (struct TPEFixup *)v45, (struct TOutput *)&v27);
  ((void (__fastcall *)(void ***, const wchar_t *))*v27)(&v27, L"THashedPKIndexes().Compile(mbmeta, *pOut);\r\n");
  v35[0] = &THashedPKIndexes::`vftable';
  v35[2] = 0;
  v35[3] = 0;
  v35[1] = &THeap<DatabaseMeta>::`vftable';
  v36 = 0;
  THashedPKIndexes::Compile((THashedPKIndexes *)v35, (struct TPEFixup *)v45, (struct TOutput *)&v27);
  ((void (__fastcall *)(void ***, const wchar_t *))*v27)(&v27, L"THashedUniqueIndexes().Compile(mbmeta, *pOut);\r\n");
  v37 = &THashedUniqueIndexes::`vftable';
  v38 = 0;
  THashedUniqueIndexes::Compile((THashedUniqueIndexes *)&v37, (struct TPEFixup *)v45, (struct TOutput *)&v27);
  v9 = -1;
  do
    ++v9;
  while ( Src[v9] );
  v10 = (wchar_t *)CoTaskMemAlloc(saturated_mul(*((_QWORD *)this + 320), 2u));
  v33 = v10;
  v11 = (wchar_t *)CoTaskMemAlloc(saturated_mul(*((_QWORD *)this + 320), 2u));
  v32 = v11;
  v12 = (char *)CoTaskMemAlloc(saturated_mul(v9 + 5, 2u));
  v13 = v12;
  v31 = v12;
  if ( v10 && v11 && v12 )
  {
    v28 = 0;
    _InterlockedExchange(&v28, *((_DWORD *)this + 644) + 1);
    LODWORD(v25) = v28;
    swprintf_s(v10, *((_QWORD *)this + 320), L"%sMBSchema.bin.%08xh", *((_QWORD *)this + 321), v25);
    wcscpy_s(v11, *((_QWORD *)this + 320), *((const wchar_t **)this + 321));
    wcscat_s(v11, *((_QWORD *)this + 320), L"MBSchema.bin.");
    wcscat_s(v11, *((_QWORD *)this + 320), L"tmp");
    v14 = 2 * v9;
    memcpy_0(v13, Src, 2 * v9);
    *(_QWORD *)&v13[v14] = *(_QWORD *)L".tmp";
    *(_WORD *)&v13[v14 + 8] = aTmp_0[4];
    v40[2] = 0;
    v40[3] = 0;
    v40[1] = &THeap<DatabaseMeta>::`vftable';
    v41 = 0;
    v40[0] = &TWriteSchemaBin::`vftable';
    v42 = 0;
    v43 = 0;
    v44 = v11;
    TWriteSchemaBin::Compile((TWriteSchemaBin *)v40, (struct TPEFixup *)v45, (struct TOutput *)&v27);
    TWriteSchemaBin::~TWriteSchemaBin((TWriteSchemaBin *)v40);
    v29 = &TMBSchemaGeneration::`vftable';
    v30 = v13;
    TMBSchemaGeneration::Compile((TMBSchemaGeneration *)&v29, (struct TPEFixup *)v45, (struct TOutput *)&v27);
    MoveFileExW(v11, v10, 3u);
    if ( MoveFileExW((LPCWSTR)v13, Src, 3u) )
    {
      v21 = TMBSchemaCompilation::SetBinFileVersion(this, v28);
      if ( v21 >= 0 )
      {
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"\r\n%s file generated\n", v10);
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"\r\n%s file generated\n", Src);
        TickCount = GetTickCount();
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"HeapColumnMeta       %8d bytes\n", 84LL * (v46 / 0x54));
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"HeapDatabaseMeta     %8d bytes\n", 48LL * (v47 / 0x30));
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"HeapHashedIndex      %8d bytes\n", v48 & 0xFFFFFFF8);
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"HeapIndexMeta        %8d bytes\n", 28LL * (v49 / 0x1C));
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"HeapQueryMeta        %8d bytes\n", 28LL * (v50 / 0x1C));
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"HeapRelationMeta     %8d bytes\n", 20LL * (v51 / 0x14));
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"HeapServerWiringMeta %8d bytes\n", 52LL * (v52 / 0x34));
        ((void (*)(void ***, const wchar_t *, ...))*v27)(
          &v27,
          L"HeapTableMeta        %8d bytes\n",
          108LL * (v53 / 0x6C));
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"HeapTagMeta          %8d bytes\n", 24LL * (v54 / 0x18));
        ((void (*)(void ***, const wchar_t *, ...))*v27)(&v27, L"HeapULONG            %8d bytes\n", v55 & 0xFFFFFFFC);
        v23 = (void (*)(void ***, const wchar_t *, ...))*v27;
        v24 = (*(__int64 (__fastcall **)(__int64 *))(v56[0] + 16))(v56);
        v23(&v27, L"HeapPooled           %8d bytes\n", v24);
        ((void (*)(void ***, const wchar_t *, ...))*v27)(
          &v27,
          L"Total time to build the %s file: %d milliseconds\n",
          Src,
          TickCount - (unsigned int)v34);
        TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v31);
        TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v32);
        TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v33);
        THashedPKIndexes::~THashedPKIndexes((THashedPKIndexes *)v35);
        TMetabaseMetaXmlFile::~TMetabaseMetaXmlFile((TMetabaseMetaXmlFile *)v45);
        return 0;
      }
      else
      {
        TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v31);
        TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v32);
        TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v33);
        THashedPKIndexes::~THashedPKIndexes((THashedPKIndexes *)v35);
        TMetabaseMetaXmlFile::~TMetabaseMetaXmlFile((TMetabaseMetaXmlFile *)v45);
        return (unsigned int)v21;
      }
    }
    else
    {
      LastError = GetLastError();
      v16 = v9 + 15;
      v17 = (wchar_t *)CoTaskMemAlloc(saturated_mul(v16, 2u));
      v18 = v17;
      v34 = v17;
      if ( v17 )
      {
        wcscpy_s(v17, v16, L"MoveFileEx to ");
        wcscat_s(v18, v16, Src);
        if ( LastError > 0 )
          v19 = (unsigned __int16)LastError | 0x80070000;
        else
          v19 = (unsigned int)LastError;
        v30 = 0;
        CErrorInterceptor::Init(
          &v29,
          0,
          0,
          v19,
          3,
          -2147348263,
          v18,
          &word_180034198,
          &word_180034198,
          &word_180034198,
          0,
          0,
          0,
          -1,
          -1,
          0,
          0);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)&v29,
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\mbschemacompilation.cpp",
          136,
          0x400000);
      }
      else
      {
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
        else
          v20 = (unsigned int)LastError;
        v30 = 0;
        CErrorInterceptor::Init(
          &v29,
          0,
          0,
          v20,
          3,
          -2147348263,
          L"MoveFileEx",
          &word_180034198,
          &word_180034198,
          &word_180034198,
          0,
          0,
          0,
          -1,
          -1,
          0,
          0);
        CErrorInterceptor::WriteToLog(
          (CErrorInterceptor *)&v29,
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\mbschemacompilation.cpp",
          140,
          0x400000);
      }
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)&v29);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        LODWORD(v26) = LastError;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\mbschemacompilation.cpp",
          144,
          "TMBSchemaCompilation::Compile",
          "Could not move to %ws, hr=0x%x\n",
          Src,
          v26);
      }
      TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v34);
      TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v31);
      TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v32);
      TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v33);
      THashedPKIndexes::~THashedPKIndexes((THashedPKIndexes *)v35);
      TMetabaseMetaXmlFile::~TMetabaseMetaXmlFile((TMetabaseMetaXmlFile *)v45);
      return (unsigned int)LastError;
    }
  }
  else
  {
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v31);
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v32);
    TSmartPointerArray<bool>::~TSmartPointerArray<bool>(&v33);
    THashedPKIndexes::~THashedPKIndexes((THashedPKIndexes *)v35);
    TMetabaseMetaXmlFile::~TMetabaseMetaXmlFile((TMetabaseMetaXmlFile *)v45);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180015f34  push    rbx
0x180015f36  push    rsi
0x180015f37  push    rdi
0x180015f38  push    r12
0x180015f3a  push    r13
0x180015f3c  push    r14
0x180015f3e  push    r15
0x180015f40  sub     rsp, 0C30h
0x180015f47  mov     rax, cs:__security_cookie
0x180015f4e  xor     rax, rsp
0x180015f51  mov     [rsp+0C68h+var_48], rax
0x180015f59  mov     r13, r9
0x180015f5c  mov     rdi, r8
0x180015f5f  mov     rbx, rdx
0x180015f62  mov     r15, rcx
0x180015f65  lea     rax, ??_7TNullOutput@@6B@; const TNullOutput::`vftable'
0x180015f6c  mov     [rsp+0C68h+var_BB8], rax
0x180015f74  xor     r14d, r14d
0x180015f77  test    rdx, rdx
0x180015f7a  jz      loc_1800169CE
0x180015f80  test    r9, r9
0x180015f83  jz      loc_1800169CE
0x180015f89  lea     rcx, ?g_aFixedTableHeap@@3PAKA; this
0x180015f90  call    ?IsValid@FixedTableHeap@@QEBA_NXZ; FixedTableHeap::IsValid(void)
0x180015f95  test    al, al
0x180015f97  jz      loc_1800169CE
0x180015f9d  cmp     [r15+0A08h], r14
0x180015fa4  jnz     short loc_180015FB0
0x180015fa6  mov     eax, 80210860h
0x180015fab  jmp     loc_1800169D3
0x180015fb0  call    cs:__imp_GetTickCount
0x180015fb6  mov     dword ptr [rsp+0C68h+var_B80], eax
0x180015fbd  lea     rax, [rsp+0C68h+var_BB8]
0x180015fc5  mov     [rsp+0C68h+var_C48], rax; struct TOutput *
0x180015fca  mov     r9, rbx; struct ISimpleTableDispenser2 *
0x180015fcd  mov     r8, rdi; unsigned __int16 *
0x180015fd0  lea     rdx, ?g_aFixedTableHeap@@3PAKA; struct FixedTableHeap *
0x180015fd7  lea     rcx, [rsp+0C68h+var_AC8]; this
0x180015fdf  call    ??0TMetabaseMetaXmlFile@@QEAA@PEBVFixedTableHeap@@PEBGPEAUISimpleTableDispenser2@@AEAVTOutput@@@Z; TMetabaseMetaXmlFile::TMetabaseMetaXmlFile(FixedTableHeap const *,ushort const *,ISimpleTableDispenser2 *,TOutput &)
0x180015fe4  nop
0x180015fe5  mov     rcx, [rsp+0C68h+var_BB8]
0x180015fed  mov     rax, [rcx]
0x180015ff0  lea     rdx, aTmetainferrenc; "TMetaInferrence().Compile(mbmeta, *pOut"...
0x180015ff7  lea     rcx, [rsp+0C68h+var_BB8]
0x180015fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016004  lea     rax, ??_7TMetaInferrence@@6B@; const TMetaInferrence::`vftable'
0x18001600b  mov     [rsp+0C68h+var_B48], rax
0x180016013  xorps   xmm0, xmm0
0x180016016  movdqu  [rsp+0C68h+var_B40], xmm0
0x18001601f  mov     [rsp+0C68h+var_B30], r14d
0x180016027  lea     r8, [rsp+0C68h+var_BB8]; struct TOutput *
0x18001602f  lea     rdx, [rsp+0C68h+var_AC8]; struct TPEFixup *
0x180016037  lea     rcx, [rsp+0C68h+var_B48]; this
0x18001603f  call    ?Compile@TMetaInferrence@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z; TMetaInferrence::Compile(TPEFixup &,TOutput &)
0x180016044  nop
0x180016045  mov     rax, [rsp+0C68h+var_BB8]
0x18001604d  lea     rdx, aThashedpkindex; "THashedPKIndexes().Compile(mbmeta, *pOu"...
0x180016054  lea     rcx, [rsp+0C68h+var_BB8]
0x18001605c  mov     rax, [rax]
0x18001605f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016064  lea     rax, ??_7THashedPKIndexes@@6B@; const THashedPKIndexes::`vftable'
0x18001606b  mov     [rsp+0C68h+var_B78], rax
0x180016073  mov     [rsp+0C68h+var_B68], r14
0x18001607b  mov     [rsp+0C68h+var_B60], r14
0x180016083  lea     rax, ??_7?$THeap@UDatabaseMeta@@@@6B@; const THeap<DatabaseMeta>::`vftable'
0x18001608a  mov     [rsp+0C68h+var_B70], rax
0x180016092  xorps   xmm0, xmm0
0x180016095  movdqu  [rsp+0C68h+var_B58], xmm0
0x18001609e  lea     r8, [rsp+0C68h+var_BB8]; struct TOutput *
0x1800160a6  lea     rdx, [rsp+0C68h+var_AC8]; struct TPEFixup *
0x1800160ae  lea     rcx, [rsp+0C68h+var_B78]; this
0x1800160b6  call    ?Compile@THashedPKIndexes@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z; THashedPKIndexes::Compile(TPEFixup &,TOutput &)
0x1800160bb  mov     rax, [rsp+0C68h+var_BB8]
0x1800160c3  lea     rdx, aThasheduniquei; "THashedUniqueIndexes().Compile(mbmeta, "...
0x1800160ca  lea     rcx, [rsp+0C68h+var_BB8]
0x1800160d2  mov     rax, [rax]
0x1800160d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160da  lea     rax, ??_7THashedUniqueIndexes@@6B@; const THashedUniqueIndexes::`vftable'
0x1800160e1  mov     [rsp+0C68h+var_B48], rax
0x1800160e9  xorps   xmm0, xmm0
0x1800160ec  movdqu  [rsp+0C68h+var_B40], xmm0
0x1800160f5  lea     r8, [rsp+0C68h+var_BB8]; struct TOutput *
0x1800160fd  lea     rdx, [rsp+0C68h+var_AC8]; struct TPEFixup *
0x180016105  lea     rcx, [rsp+0C68h+var_B48]; this
0x18001610d  call    ?Compile@THashedUniqueIndexes@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z; THashedUniqueIndexes::Compile(TPEFixup &,TOutput &)
0x180016112  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016116  mov     r12, rdi
0x180016119  inc     r12
0x18001611c  cmp     [r13+r12*2+0], r14w
0x180016122  jnz     short loc_180016119
0x180016124  mov     ebx, 2
0x180016129  mov     eax, ebx
0x18001612b  mul     qword ptr [r15+0A00h]
0x180016132  cmovb   rax, rdi
0x180016136  mov     rcx, rax; cb
0x180016139  call    cs:__imp_CoTaskMemAlloc
0x18001613f  mov     rsi, rax
0x180016142  mov     [rsp+0C68h+var_B88], rax
0x18001614a  mov     eax, ebx
0x18001614c  mul     qword ptr [r15+0A00h]
0x180016153  cmovb   rax, rdi
0x180016157  mov     rcx, rax; cb
0x18001615a  call    cs:__imp_CoTaskMemAlloc
0x180016160  mov     rbx, rax
0x180016163  mov     [rsp+0C68h+var_B90], rax
0x18001616b  lea     rcx, [r12+5]
0x180016170  mov     eax, 2
0x180016175  mul     rcx
0x180016178  cmovb   rax, rdi
0x18001617c  mov     rcx, rax; cb
0x18001617f  call    cs:__imp_CoTaskMemAlloc
0x180016185  mov     rdi, rax
0x180016188  mov     [rsp+0C68h+var_B98], rax
0x180016190  test    rsi, rsi
0x180016193  jz      loc_18001697B
0x180016199  test    rbx, rbx
0x18001619c  jz      loc_18001697B
0x1800161a2  test    rax, rax
0x1800161a5  jz      loc_18001697B
0x1800161ab  mov     [rsp+0C68h+var_BB0], r14d
0x1800161b3  mov     eax, [r15+0A10h]
0x1800161ba  inc     eax
0x1800161bc  xchg    eax, [rsp+0C68h+var_BB0]
0x1800161c3  mov     eax, [rsp+0C68h+var_BB0]
0x1800161ca  mov     dword ptr [rsp+0C68h+var_C48], eax
0x1800161ce  mov     r9, [r15+0A08h]
0x1800161d5  lea     r8, aSmbschemaBin08; "%sMBSchema.bin.%08xh"
0x1800161dc  mov     rdx, [r15+0A00h]; BufferCount
0x1800161e3  mov     rcx, rsi; Buffer
0x1800161e6  call    cs:__imp_swprintf_s
0x1800161ec  mov     r8, [r15+0A08h]; Source
0x1800161f3  mov     rdx, [r15+0A00h]; SizeInWords
0x1800161fa  mov     rcx, rbx; Destination
0x1800161fd  call    cs:__imp_wcscpy_s
0x180016203  lea     r8, aMbschemaBin; "MBSchema.bin."
0x18001620a  mov     rdx, [r15+0A00h]; SizeInWords
0x180016211  mov     rcx, rbx; Destination
0x180016214  call    cs:__imp_wcscat_s
0x18001621a  lea     r8, aTmp; "tmp"
0x180016221  mov     rdx, [r15+0A00h]; SizeInWords
0x180016228  mov     rcx, rbx; Destination
0x18001622b  call    cs:__imp_wcscat_s
0x180016231  lea     r14, [r12+r12]
0x180016235  mov     r8, r14; Size
0x180016238  mov     rdx, r13; Src
0x18001623b  mov     rcx, rdi; void *
0x18001623e  call    memcpy_0
0x180016243  movsd   xmm0, qword ptr cs:aTmp_0; ".tmp"
0x18001624b  movsd   qword ptr [r14+rdi], xmm0
0x180016251  movzx   eax, word ptr cs:aTmp_0+8; ""
0x180016258  mov     [r14+rdi+8], ax
0x18001625e  xor     r14d, r14d
0x180016261  mov     [rsp+0C68h+var_B10], r14
0x180016269  mov     [rsp+0C68h+var_B08], r14
0x180016271  lea     rax, ??_7?$THeap@UDatabaseMeta@@@@6B@; const THeap<DatabaseMeta>::`vftable'
0x180016278  mov     [rsp+0C68h+var_B18], rax
0x180016280  xorps   xmm0, xmm0
0x180016283  movdqu  [rsp+0C68h+var_B00], xmm0
0x18001628c  lea     rax, ??_7TWriteSchemaBin@@6B@; const TWriteSchemaBin::`vftable'
0x180016293  mov     [rsp+0C68h+var_B20], rax
0x18001629b  movdqu  [rsp+0C68h+var_AF0], xmm0
0x1800162a4  xorps   xmm1, xmm1
0x1800162a7  movdqu  [rsp+0C68h+var_AE0], xmm1
0x1800162b0  mov     [rsp+0C68h+var_AD0], rbx
0x1800162b8  lea     r8, [rsp+0C68h+var_BB8]; struct TOutput *
0x1800162c0  lea     rdx, [rsp+0C68h+var_AC8]; struct TPEFixup *
0x1800162c8  lea     rcx, [rsp+0C68h+var_B20]; this
0x1800162d0  call    ?Compile@TWriteSchemaBin@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z; TWriteSchemaBin::Compile(TPEFixup &,TOutput &)
0x1800162d5  nop
0x1800162d6  lea     rcx, [rsp+0C68h+var_B20]; this
0x1800162de  call    ??1TWriteSchemaBin@@UEAA@XZ; TWriteSchemaBin::~TWriteSchemaBin(void)
0x1800162e3  lea     rax, ??_7TMBSchemaGeneration@@6B@; const TMBSchemaGeneration::`vftable'
0x1800162ea  mov     [rsp+0C68h+var_BA8], rax
0x1800162f2  mov     [rsp+0C68h+var_BA0], rdi
0x1800162fa  lea     r8, [rsp+0C68h+var_BB8]; struct TOutput *
0x180016302  lea     rdx, [rsp+0C68h+var_AC8]; struct TPEFixup *
0x18001630a  lea     rcx, [rsp+0C68h+var_BA8]; this
0x180016312  call    ?Compile@TMBSchemaGeneration@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z; TMBSchemaGeneration::Compile(TPEFixup &,TOutput &)
0x180016317  nop
0x180016318  lea     r8d, [r14+3]; dwFlags
0x18001631c  mov     rdx, rsi; lpNewFileName
0x18001631f  mov     rcx, rbx; lpExistingFileName
0x180016322  call    cs:__imp_MoveFileExW
0x180016328  lea     r8d, [r14+3]; dwFlags
0x18001632c  mov     rdx, r13; lpNewFileName
0x18001632f  mov     rcx, rdi; lpExistingFileName
0x180016332  call    cs:__imp_MoveFileExW
0x180016338  test    eax, eax
0x18001633a  jnz     loc_1800165BA
0x180016340  call    cs:__imp_GetLastError
0x180016346  mov     edi, eax
0x180016348  add     r12, 0Fh
0x18001634c  lea     eax, [r14+2]
0x180016350  mul     r12
0x180016353  lea     rcx, [r14-1]
0x180016357  cmovb   rax, rcx
0x18001635b  mov     rcx, rax; cb
0x18001635e  call    cs:__imp_CoTaskMemAlloc
0x180016364  mov     rbx, rax
0x180016367  mov     [rsp+0C68h+var_B80], rax
0x18001636f  test    rax, rax
0x180016372  jz      loc_18001644F
0x180016378  lea     r8, aMovefileexTo; "MoveFileEx to "
0x18001637f  mov     rdx, r12; SizeInWords
0x180016382  mov     rcx, rax; Destination
0x180016385  call    cs:__imp_wcscpy_s
0x18001638b  mov     r8, r13; Source
0x18001638e  mov     rdx, r12; SizeInWords
0x180016391  mov     rcx, rbx; Destination
0x180016394  call    cs:__imp_wcscat_s
0x18001639a  test    edi, edi
0x18001639c  jg      short loc_1800163A3
0x18001639e  mov     r9d, edi
0x1800163a1  jmp     short loc_1800163AE
0x1800163a3  movzx   r9d, di
0x1800163a7  or      r9d, 80070000h
0x1800163ae  mov     [rsp+0C68h+var_BA0], r14
0x1800163b6  or      eax, 0FFFFFFFFh
0x1800163b9  mov     [rsp+0C68h+var_BC8], eax
0x1800163c0  mov     [rsp+0C68h+var_BD0], eax
0x1800163c7  mov     [rsp+0C68h+var_BE8], r14d
0x1800163cf  mov     [rsp+0C68h+var_BF0], r14
0x1800163d4  mov     [rsp+0C68h+var_BF8], eax
0x1800163d8  mov     [rsp+0C68h+var_C00], eax
0x1800163dc  mov     [rsp+0C68h+var_C08], r14d
0x1800163e1  mov     [rsp+0C68h+var_C10], r14
0x1800163e6  mov     [rsp+0C68h+var_C18], r14d
0x1800163eb  lea     rax, word_180034198
0x1800163f2  mov     [rsp+0C68h+var_C20], rax
0x1800163f7  mov     [rsp+0C68h+var_C28], rax
0x1800163fc  mov     [rsp+0C68h+var_C30], rax
0x180016401  mov     [rsp+0C68h+var_C38], rbx
0x180016406  mov     dword ptr [rsp+0C68h+var_C40], 800210D9h
0x18001640e  mov     dword ptr [rsp+0C68h+var_C48], 3
0x180016416  xor     r8d, r8d
0x180016419  xor     edx, edx
0x18001641b  lea     rcx, [rsp+0C68h+var_BA8]
0x180016423  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180016428  nop
0x180016429  mov     r9d, 400000h; unsigned int
0x18001642f  mov     r8d, 88h; unsigned int
0x180016435  lea     rdx, aInetsrvIisMbCo_9; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001643c  lea     rcx, [rsp+0C68h+var_BA8]; this
0x180016444  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180016449  nop
0x18001644a  jmp     loc_180016506
0x18001644f  test    edi, edi
0x180016451  jg      short loc_180016458
0x180016453  mov     r9d, edi
0x180016456  jmp     short loc_180016463
0x180016458  movzx   r9d, di
0x18001645c  or      r9d, 80070000h
0x180016463  mov     [rsp+0C68h+var_BA0], r14
0x18001646b  or      eax, 0FFFFFFFFh
0x18001646e  mov     [rsp+0C68h+var_BC8], eax
0x180016475  mov     [rsp+0C68h+var_BD0], eax
0x18001647c  mov     [rsp+0C68h+var_BE8], r14d
0x180016484  mov     [rsp+0C68h+var_BF0], r14
0x180016489  mov     [rsp+0C68h+var_BF8], eax
0x18001648d  mov     [rsp+0C68h+var_C00], eax
0x180016491  mov     [rsp+0C68h+var_C08], r14d
0x180016496  mov     [rsp+0C68h+var_C10], r14
0x18001649b  mov     [rsp+0C68h+var_C18], r14d
0x1800164a0  lea     rax, word_180034198
0x1800164a7  mov     [rsp+0C68h+var_C20], rax
0x1800164ac  mov     [rsp+0C68h+var_C28], rax
0x1800164b1  mov     [rsp+0C68h+var_C30], rax
0x1800164b6  lea     rax, aMovefileex; "MoveFileEx"
0x1800164bd  mov     [rsp+0C68h+var_C38], rax
0x1800164c2  mov     dword ptr [rsp+0C68h+var_C40], 800210D9h
0x1800164ca  mov     dword ptr [rsp+0C68h+var_C48], 3
0x1800164d2  xor     r8d, r8d
0x1800164d5  xor     edx, edx
0x1800164d7  lea     rcx, [rsp+0C68h+var_BA8]
0x1800164df  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x1800164e4  nop
0x1800164e5  mov     r9d, 400000h; unsigned int
0x1800164eb  mov     r8d, 8Ch; unsigned int
0x1800164f1  lea     rdx, aInetsrvIisMbCo_9; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x1800164f8  lea     rcx, [rsp+0C68h+var_BA8]; this
0x180016500  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180016505  nop
0x180016506  lea     rcx, [rsp+0C68h+var_BA8]; this
0x18001650e  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180016513  test    edi, edi
0x180016515  jle     short loc_180016520
0x180016517  movzx   edi, di
0x18001651a  or      edi, 80070000h
0x180016520  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180016527  jz      short loc_180016560
0x180016529  mov     dword ptr [rsp+0C68h+var_C38], edi
0x18001652d  mov     [rsp+0C68h+var_C40], r13
0x180016532  lea     rax, aCouldNotMoveTo; "Could not move to %ws, hr=0x%x\n"
0x180016539  mov     [rsp+0C68h+var_C48], rax
0x18001653e  lea     r9, aTmbschemacompi; "TMBSchemaCompilation::Compile"
0x180016545  mov     r8d, 90h
0x18001654b  lea     rdx, aInetsrvIisMbCo_12; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180016552  mov     rcx, cs:g_pDebug
0x180016559  call    cs:__imp_PuDbgPrint
0x18001655f  nop
  ... truncated ...
```
