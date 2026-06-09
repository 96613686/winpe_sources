# CImporter::InitIST(void)

- ea: `0x180013344`
- end: `0x1800136da`
- name: `?InitIST@CImporter@@AEAAJXZ`
- size: `918`
- prototype: `__int64 __fastcall(CImporter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022dac`

## callees

- `0x180012e64`
- `0x180013344`
- `0x18003099a`
- `0x180031010`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18001337b`
- `KERNEL32!lstrlenW` at `0x18001337b`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18001345d`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18001345d`
- `IisRTL!PuDbgPrint` at `0x1800133f5`
- `IisRTL!PuDbgPrint` at `0x180013511`
- `IisRTL!PuDbgPrint` at `0x18001356d`
- `IisRTL!PuDbgPrint` at `0x180013664`
- `IisRTL!PuDbgPrint` at `0x1800136b8`
- `IisRTL!PuDbgPrint` at `0x1800133f5`
- `IisRTL!PuDbgPrint` at `0x180013511`
- `IisRTL!PuDbgPrint` at `0x18001356d`
- `IisRTL!PuDbgPrint` at `0x180013664`
- `IisRTL!PuDbgPrint` at `0x1800136b8`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x1800133ac`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x1800133ac`

## string_xrefs

- `0x1800133de`: `[%s] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n`
- `0x18001354d`: `[%s] Could not get ISTRead2 from IErrorInfo\n, __FUNCTION__`
- `0x180013638`: `[%s] Could not read an error row.\n`

## pseudocode

```c
__int64 __fastcall CImporter::InitIST(CImporter *this)
{
  int v2; // eax
  int SimpleObjectByIDEx; // eax
  int v4; // ebx
  int v5; // eax
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  int v7; // eax
  _QWORD *v8; // rsi
  int v9; // eax
  _QWORD *v10; // r14
  unsigned int i; // edi
  int v12; // eax
  const char *v14; // [rsp+28h] [rbp-D8h]
  __int64 v15; // [rsp+30h] [rbp-D0h]
  LPCWSTR v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  int v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+64h] [rbp-9Ch]
  _BYTE v21[272]; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+190h] [rbp+90h] BYREF
  __int64 v23; // [rsp+198h] [rbp+98h] BYREF
  IErrorInfo *pperrinfo; // [rsp+1A0h] [rbp+A0h] BYREF

  v17 = 2;
  v16 = (LPCWSTR)*((_QWORD *)this + 4);
  v18 = -268435455;
  v19 = 130;
  v2 = lstrlenW(v16);
  v22 = 1;
  v20 = 2 * v2 + 2;
  SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, this, L"IIS");
  v4 = SimpleObjectByIDEx;
  if ( SimpleObjectByIDEx >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 *, LPCWSTR *, int *, int, int, char *))(**(_QWORD **)this + 24LL))(
           *(_QWORD *)this,
           L"METABASE",
           L"MBProperty",
           &v16,
           &v22,
           3,
           12582912,
           (char *)this + 8);
    pperrinfo = 0;
    v4 = v5;
    if ( GetErrorInfo(0, &pperrinfo) )
    {
LABEL_27:
      if ( v4 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\importer.cpp",
          540,
          "CImporter::InitIST",
          "[%s] GetTable failed with hr = 0x%x.\n",
          "CImporter::InitIST",
          v4);
    }
    else
    {
      v6 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this;
      v23 = 0;
      v7 = (**v6)(v6, &IID_IAdvancedTableDispenser, &v23);
      if ( v7 >= 0 )
      {
        v8 = (_QWORD *)((char *)this + 24);
        v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v23 + 48LL))(v23, (char *)this + 24);
        if ( v9 >= 0 )
        {
          v10 = (_QWORD *)((char *)this + 16);
          if ( ((__int64 (__fastcall *)(IErrorInfo *, GUID *, char *))pperrinfo->lpVtbl->QueryInterface)(
                 pperrinfo,
                 &IID_ISimpleTableRead2,
                 (char *)this + 16) >= 0 )
          {
            for ( i = 0; ; ++i )
            {
              memset_0(v21, 0, 0xE8u);
              v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v10 + 32LL))(*v10, i, 29);
              if ( v12 == -2145318890 )
              {
                ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(&v23);
                goto LABEL_27;
              }
              if ( v12 < 0 )
                break;
              if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD, _BYTE *))(*(_QWORD *)*v8 + 24LL))(
                     *v8,
                     0,
                     0,
                     29,
                     0,
                     v21) < 0 )
              {
                if ( (g_dwDebugFlags & 7) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\mb\\metadata\\importer.cpp",
                    531,
                    "CImporter::InitIST",
                    "[%s] Could not log error.\n",
                    "CImporter::InitIST");
                goto LABEL_15;
              }
              v4 = -2146645991;
            }
            if ( (g_dwDebugFlags & 7) != 0 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\importer.cpp",
                518,
                "CImporter::InitIST",
                "[%s] Could not read an error row.\n",
                "CImporter::InitIST");
          }
          else if ( (g_dwDebugFlags & 7) != 0 )
          {
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\importer.cpp",
              499,
              "CImporter::InitIST",
              "[%s] Could not get ISTRead2 from IErrorInfo\n, __FUNCTION__",
              v14);
          }
        }
        else if ( (g_dwDebugFlags & 7) != 0 )
        {
          LODWORD(v15) = v9;
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\importer.cpp",
            488,
            "CImporter::InitIST",
            "[%s] Could not get ICatalogErrorLogger2, hr=0x%x\n",
            "CImporter::InitIST",
            v15);
        }
      }
      else if ( (g_dwDebugFlags & 7) != 0 )
      {
        LODWORD(v15) = v7;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\importer.cpp",
          479,
          "CImporter::InitIST",
          "[%s] Could not QI for Adv Dispenser, hr=0x%x\n",
          "CImporter::InitIST",
          v15);
      }
LABEL_15:
      ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(&v23);
    }
    ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(&pperrinfo);
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\importer.cpp",
      447,
      "CImporter::InitIST",
      "[%s] DllGetSimpleObjectByIDEx failed with hr = 0x%x.\n",
      "CImporter::InitIST",
      SimpleObjectByIDEx);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013344  push    rbp
0x180013346  push    rbx
0x180013347  push    rsi
0x180013348  push    rdi
0x180013349  push    r14
0x18001334b  lea     rbp, [rsp-60h]
0x180013350  sub     rsp, 160h
0x180013357  mov     rdi, rcx
0x18001335a  mov     [rsp+180h+var_128], 2
0x180013362  mov     rcx, [rcx+20h]; lpString
0x180013366  mov     [rsp+180h+var_130], rcx
0x18001336b  mov     [rsp+180h+var_124], 0F0000001h
0x180013373  mov     [rsp+180h+var_120], 82h
0x18001337b  call    cs:__imp_lstrlenW
0x180013381  lea     r9, aIis; "IIS"
0x180013388  mov     [rbp+80h+arg_0], 1
0x180013392  mov     r8, rdi
0x180013395  lea     rdx, IID_ISimpleTableDispenser2
0x18001339c  mov     ecx, 1
0x1800133a1  lea     eax, ds:2[rax*2]
0x1800133a8  mov     [rsp+180h+var_11C], eax
0x1800133ac  call    cs:__imp_DllGetSimpleObjectByIDEx
0x1800133b2  mov     ebx, eax
0x1800133b4  test    eax, eax
0x1800133b6  jns     short loc_180013400
0x1800133b8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800133bf  jz      loc_1800136CA
0x1800133c5  mov     rcx, cs:g_pDebug
0x1800133cc  lea     r9, aCimporterIniti; "CImporter::InitIST"
0x1800133d3  mov     dword ptr [rsp+180h+var_150], eax
0x1800133d7  lea     rdx, aInetsrvIisMbMe_6; "inetsrv\\iis\\mb\\metadata\\importer.cp"...
0x1800133de  lea     rax, aSDllgetsimpleo; "[%s] DllGetSimpleObjectByIDEx failed wi"...
0x1800133e5  mov     [rsp+180h+var_158], r9
0x1800133ea  mov     r8d, 1BFh
0x1800133f0  mov     [rsp+180h+var_160], rax
0x1800133f5  call    cs:__imp_PuDbgPrint
0x1800133fb  jmp     loc_1800136CA
0x180013400  mov     rcx, [rdi]
0x180013403  lea     rdx, [rdi+8]
0x180013407  mov     [rsp+180h+var_148], rdx
0x18001340c  lea     r9, [rsp+180h+var_130]
0x180013411  mov     dword ptr [rsp+180h+var_150], 0C00000h
0x180013419  lea     rdx, [rbp+80h+arg_0]
0x180013420  mov     dword ptr [rsp+180h+var_158], 3
0x180013428  lea     r8, aMbproperty_0; "MBProperty"
0x18001342f  mov     rax, [rcx]
0x180013432  mov     [rsp+180h+var_160], rdx
0x180013437  lea     rdx, aMetabase; "METABASE"
0x18001343e  mov     rax, [rax+18h]
0x180013442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013447  lea     rdx, [rbp+80h+pperrinfo]; pperrinfo
0x18001344e  mov     [rbp+80h+pperrinfo], 0
0x180013459  xor     ecx, ecx; dwReserved
0x18001345b  mov     ebx, eax
0x18001345d  call    cs:__imp_GetErrorInfo
0x180013463  test    eax, eax
0x180013465  jnz     loc_18001367B
0x18001346b  mov     rcx, [rdi]
0x18001346e  lea     r8, [rbp+80h+arg_8]
0x180013475  mov     [rbp+80h+arg_8], 0
0x180013480  mov     rdx, [rcx]
0x180013483  mov     rax, [rdx]
0x180013486  lea     rdx, IID_IAdvancedTableDispenser
0x18001348d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013492  test    eax, eax
0x180013494  jns     short loc_1800134B6
0x180013496  test    byte ptr cs:g_dwDebugFlags, 7
0x18001349d  jz      loc_180013573
0x1800134a3  mov     dword ptr [rsp+180h+var_150], eax
0x1800134a7  mov     r8d, 1DFh
0x1800134ad  lea     rax, aSCouldNotQiFor; "[%s] Could not QI for Adv Dispenser, hr"...
0x1800134b4  jmp     short loc_1800134F2
0x1800134b6  mov     rcx, [rbp+80h+arg_8]
0x1800134bd  lea     rsi, [rdi+18h]
0x1800134c1  mov     rdx, rsi
0x1800134c4  mov     rax, [rcx]
0x1800134c7  mov     rax, [rax+30h]
0x1800134cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134d0  test    eax, eax
0x1800134d2  jns     short loc_180013519
0x1800134d4  test    byte ptr cs:g_dwDebugFlags, 7
0x1800134db  jz      loc_180013573
0x1800134e1  mov     dword ptr [rsp+180h+var_150], eax
0x1800134e5  mov     r8d, 1E8h
0x1800134eb  lea     rax, aSCouldNotGetIc; "[%s] Could not get ICatalogErrorLogger2"...
0x1800134f2  mov     rcx, cs:g_pDebug
0x1800134f9  lea     r9, aCimporterIniti; "CImporter::InitIST"
0x180013500  mov     [rsp+180h+var_158], r9
0x180013505  lea     rdx, aInetsrvIisMbMe_6; "inetsrv\\iis\\mb\\metadata\\importer.cp"...
0x18001350c  mov     [rsp+180h+var_160], rax
0x180013511  call    cs:__imp_PuDbgPrint
0x180013517  jmp     short loc_180013573
0x180013519  mov     rcx, [rbp+80h+pperrinfo]
0x180013520  lea     r14, [rdi+10h]
0x180013524  mov     r8, r14
0x180013527  lea     rdx, IID_ISimpleTableRead2
0x18001352e  mov     rax, [rcx]
0x180013531  mov     rax, [rax]
0x180013534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013539  test    eax, eax
0x18001353b  jns     short loc_180013584
0x18001353d  test    byte ptr cs:g_dwDebugFlags, 7
0x180013544  jz      short loc_180013573
0x180013546  mov     rcx, cs:g_pDebug
0x18001354d  lea     rax, aSCouldNotGetIs; "[%s] Could not get ISTRead2 from IError"...
0x180013554  lea     r9, aCimporterIniti; "CImporter::InitIST"
0x18001355b  mov     [rsp+180h+var_160], rax
0x180013560  mov     r8d, 1F3h
0x180013566  lea     rdx, aInetsrvIisMbMe_6; "inetsrv\\iis\\mb\\metadata\\importer.cp"...
0x18001356d  call    cs:__imp_PuDbgPrint
0x180013573  lea     rcx, [rbp+80h+arg_8]
0x18001357a  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x18001357f  jmp     loc_1800136BE
0x180013584  xor     edi, edi
0x180013586  xor     edx, edx; Val
0x180013588  lea     rcx, [rsp+180h+var_110]; void *
0x18001358d  mov     r8d, 0E8h; Size
0x180013593  call    memset_0
0x180013598  mov     rcx, [r14]
0x18001359b  lea     rdx, [rsp+180h+var_110]
0x1800135a0  mov     [rsp+180h+var_158], rdx
0x1800135a5  xor     r9d, r9d
0x1800135a8  mov     edx, edi
0x1800135aa  mov     [rsp+180h+var_160], 0
0x1800135b3  mov     rax, [rcx]
0x1800135b6  lea     r8d, [r9+1Dh]
0x1800135ba  mov     rax, [rax+20h]
0x1800135be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135c3  cmp     eax, 80210816h
0x1800135c8  jz      loc_18001366F
0x1800135ce  test    eax, eax
0x1800135d0  js      short loc_18001362B
0x1800135d2  mov     rcx, [rsi]
0x1800135d5  lea     rdx, [rsp+180h+var_110]
0x1800135da  mov     [rsp+180h+var_158], rdx
0x1800135df  mov     r9d, 1Dh
0x1800135e5  xor     r8d, r8d
0x1800135e8  mov     [rsp+180h+var_160], 0
0x1800135f1  xor     edx, edx
0x1800135f3  mov     rax, [rcx]
0x1800135f6  mov     rax, [rax+18h]
0x1800135fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135ff  test    eax, eax
0x180013601  js      short loc_18001360F
0x180013603  mov     ebx, 800CC819h
0x180013608  inc     edi
0x18001360a  jmp     loc_180013586
0x18001360f  test    byte ptr cs:g_dwDebugFlags, 7
0x180013616  jz      loc_180013573
0x18001361c  lea     rax, aSCouldNotLogEr; "[%s] Could not log error.\n"
0x180013623  mov     r8d, 213h
0x180013629  jmp     short loc_180013645
0x18001362b  test    byte ptr cs:g_dwDebugFlags, 7
0x180013632  jz      loc_180013573
0x180013638  lea     rax, aSCouldNotReadA; "[%s] Could not read an error row.\n"
0x18001363f  mov     r8d, 206h
0x180013645  mov     rcx, cs:g_pDebug
0x18001364c  lea     r9, aCimporterIniti; "CImporter::InitIST"
0x180013653  mov     [rsp+180h+var_158], r9
0x180013658  lea     rdx, aInetsrvIisMbMe_6; "inetsrv\\iis\\mb\\metadata\\importer.cp"...
0x18001365f  mov     [rsp+180h+var_160], rax
0x180013664  call    cs:__imp_PuDbgPrint
0x18001366a  jmp     loc_180013573
0x18001366f  lea     rcx, [rbp+80h+arg_8]
0x180013676  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x18001367b  test    ebx, ebx
0x18001367d  jns     short loc_1800136BE
0x18001367f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180013686  jz      short loc_1800136BE
0x180013688  mov     rcx, cs:g_pDebug
0x18001368f  lea     r9, aCimporterIniti; "CImporter::InitIST"
0x180013696  mov     dword ptr [rsp+180h+var_150], ebx
0x18001369a  lea     rax, aSGettableFaile; "[%s] GetTable failed with hr = 0x%x.\n"
0x1800136a1  mov     [rsp+180h+var_158], r9
0x1800136a6  lea     rdx, aInetsrvIisMbMe_6; "inetsrv\\iis\\mb\\metadata\\importer.cp"...
0x1800136ad  mov     r8d, 21Ch
0x1800136b3  mov     [rsp+180h+var_160], rax
0x1800136b8  call    cs:__imp_PuDbgPrint
0x1800136be  lea     rcx, [rbp+80h+pperrinfo]
0x1800136c5  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x1800136ca  mov     eax, ebx
0x1800136cc  add     rsp, 160h
0x1800136d3  pop     r14
0x1800136d5  pop     rdi
0x1800136d6  pop     rsi
0x1800136d7  pop     rbx
0x1800136d8  pop     rbp
0x1800136d9  retn
```
