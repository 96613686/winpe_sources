# InitializeIIS6GlobalsToDefaults(ulong,ulong,char *)

- ea: `0x18002025c`
- end: `0x18002040b`
- name: `?InitializeIIS6GlobalsToDefaults@@YAJKKPEAD@Z`
- size: `431`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021330`
- `0x180021c40`

## callees

- `0x18002025c`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x1800202e3`
- `IisRTL!PuDbgPrintW` at `0x1800203d1`
- `IisRTL!PuDbgPrintW` at `0x1800202e3`
- `IisRTL!PuDbgPrintW` at `0x1800203d1`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x180020315`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x180020315`

## string_xrefs

- `0x180020338`: `[InitializeIIS6GlobalsToDefaults] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x180020376`: `[InitializeIIS6GlobalsToDefaults] QueryInterface on compiler failed with hr = 0x%x.\n`
- `0x1800203b0`: `[InitializeIIS6GlobalsToDefaults] SetBinPath failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall InitializeIIS6GlobalsToDefaults(unsigned int a1, __int64 a2, char *a3)
{
  int SimpleObjectByIDEx; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  __int64 v8; // [rsp+50h] [rbp+18h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  g_dwEnableEditWhileRunning = 0;
  g_ulHistoryMajorVersionNumber = 0;
  g_dwEnableHistory = 1;
  g_dwMaxHistoryFiles = 10;
  g_dwMaxErrorFiles = 10;
  g_dwSchemaChangeNumber = 1;
  g_dwLastSchemaChangeNumber = a1;
  if ( !a3 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        11102,
        "InitializeIIS6GlobalsToDefaults",
        L"[InitializeIIS6GlobalsToDefaults] Initializing global file handle array.\n");
    *(__m128i *)&g_ahMetabaseFile = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    qword_1800488F0 = (__int64)g_ahMetabaseFile;
  }
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v9, L"IIS");
  v4 = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx >= 0 )
  {
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(v9, &IID_IMetabaseSchemaCompiler, &v8);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v8 + 40LL))(v8, g_wszMetabaseDir);
      v4 = v6;
      if ( v6 < 0 && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          11147,
          "InitializeIIS6GlobalsToDefaults",
          L"[InitializeIIS6GlobalsToDefaults] SetBinPath failed with hr = 0x%x.\n",
          v6);
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        11138,
        "InitializeIIS6GlobalsToDefaults",
        L"[InitializeIIS6GlobalsToDefaults] QueryInterface on compiler failed with hr = 0x%x.\n",
        v5);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      11122,
      "InitializeIIS6GlobalsToDefaults",
      L"[InitializeIIS6GlobalsToDefaults] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
      SimpleObjectByIDEx);
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return v4;
}

```

## disassembly

```asm
0x18002025c  push    rbx
0x18002025e  sub     rsp, 30h
0x180020262  mov     [rsp+38h+arg_18], 0
0x18002026b  mov     ebx, 1
0x180020270  mov     [rsp+38h+arg_10], 0
0x180020279  mov     cs:?g_dwEnableEditWhileRunning@@3KA, 0; ulong g_dwEnableEditWhileRunning
0x180020283  mov     cs:?g_ulHistoryMajorVersionNumber@@3KA, 0; ulong g_ulHistoryMajorVersionNumber
0x18002028d  mov     cs:?g_dwEnableHistory@@3KA, ebx; ulong g_dwEnableHistory
0x180020293  lea     eax, [rbx+9]
0x180020296  mov     cs:?g_dwMaxHistoryFiles@@3KA, eax; ulong g_dwMaxHistoryFiles
0x18002029c  mov     cs:?g_dwMaxErrorFiles@@3KA, eax; ulong g_dwMaxErrorFiles
0x1800202a2  mov     cs:?g_dwSchemaChangeNumber@@3KA, ebx; ulong g_dwSchemaChangeNumber
0x1800202a8  mov     cs:?g_dwLastSchemaChangeNumber@@3KA, ecx; ulong g_dwLastSchemaChangeNumber
0x1800202ae  test    r8, r8
0x1800202b1  jnz     short loc_180020300
0x1800202b3  test    byte ptr cs:g_dwDebugFlags, 3
0x1800202ba  jz      short loc_1800202E9
0x1800202bc  mov     rcx, cs:g_pDebug
0x1800202c3  lea     rax, aInitializeiis6_1; "[InitializeIIS6GlobalsToDefaults] Initi"...
0x1800202ca  lea     r9, aInitializeiis6_2; "InitializeIIS6GlobalsToDefaults"
0x1800202d1  mov     [rsp+38h+var_18], rax
0x1800202d6  mov     r8d, 2B5Eh
0x1800202dc  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x1800202e3  call    cs:__imp_PuDbgPrintW
0x1800202e9  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800202f1  movups  cs:?g_ahMetabaseFile@@3PAPEAXA, xmm0; void * near * g_ahMetabaseFile
0x1800202f8  movq    cs:qword_1800488F0, xmm0
0x180020300  lea     r9, aIis; "IIS"
0x180020307  mov     ecx, ebx
0x180020309  lea     r8, [rsp+38h+arg_18]
0x18002030e  lea     rdx, IID_ISimpleTableDispenser2
0x180020315  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18002031b  mov     ebx, eax
0x18002031d  test    eax, eax
0x18002031f  jns     short loc_180020341
0x180020321  test    byte ptr cs:g_dwDebugFlags, 3
0x180020328  jz      loc_1800203D7
0x18002032e  mov     [rsp+38h+var_10], eax
0x180020332  mov     r8d, 2B72h
0x180020338  lea     rax, aInitializeiis6; "[InitializeIIS6GlobalsToDefaults] DllGe"...
0x18002033f  jmp     short loc_1800203B7
0x180020341  mov     rcx, [rsp+38h+arg_18]
0x180020346  lea     r8, [rsp+38h+arg_10]
0x18002034b  lea     rdx, IID_IMetabaseSchemaCompiler
0x180020352  mov     rax, [rcx]
0x180020355  mov     rax, [rax]
0x180020358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002035d  mov     ebx, eax
0x18002035f  test    eax, eax
0x180020361  jns     short loc_18002037F
0x180020363  test    byte ptr cs:g_dwDebugFlags, 3
0x18002036a  jz      short loc_1800203D7
0x18002036c  mov     [rsp+38h+var_10], eax
0x180020370  mov     r8d, 2B82h
0x180020376  lea     rax, aInitializeiis6_0; "[InitializeIIS6GlobalsToDefaults] Query"...
0x18002037d  jmp     short loc_1800203B7
0x18002037f  mov     rcx, [rsp+38h+arg_10]
0x180020384  mov     rdx, cs:?g_wszMetabaseDir@@3PEAGEA; ushort * g_wszMetabaseDir
0x18002038b  mov     rax, [rcx]
0x18002038e  mov     rax, [rax+28h]
0x180020392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020397  mov     ebx, eax
0x180020399  test    eax, eax
0x18002039b  jns     short loc_1800203D7
0x18002039d  test    byte ptr cs:g_dwDebugFlags, 3
0x1800203a4  jz      short loc_1800203D7
0x1800203a6  mov     [rsp+38h+var_10], eax
0x1800203aa  mov     r8d, 2B8Bh
0x1800203b0  lea     rax, aInitializeiis6_3; "[InitializeIIS6GlobalsToDefaults] SetBi"...
0x1800203b7  mov     rcx, cs:g_pDebug
0x1800203be  lea     r9, aInitializeiis6_2; "InitializeIIS6GlobalsToDefaults"
0x1800203c5  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x1800203cc  mov     [rsp+38h+var_18], rax
0x1800203d1  call    cs:__imp_PuDbgPrintW
0x1800203d7  mov     rcx, [rsp+38h+arg_10]
0x1800203dc  test    rcx, rcx
0x1800203df  jz      short loc_1800203ED
0x1800203e1  mov     rax, [rcx]
0x1800203e4  mov     rax, [rax+10h]
0x1800203e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203ed  mov     rcx, [rsp+38h+arg_18]
0x1800203f2  test    rcx, rcx
0x1800203f5  jz      short loc_180020403
0x1800203f7  mov     rax, [rcx]
0x1800203fa  mov     rax, [rax+10h]
0x1800203fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020403  mov     eax, ebx
0x180020405  add     rsp, 30h
0x180020409  pop     rbx
0x18002040a  retn
```
