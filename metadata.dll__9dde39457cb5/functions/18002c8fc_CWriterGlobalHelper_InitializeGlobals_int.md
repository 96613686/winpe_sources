# CWriterGlobalHelper::InitializeGlobals(int)

- ea: `0x18002c8fc`
- end: `0x18002d13c`
- name: `?InitializeGlobals@CWriterGlobalHelper@@QEAAJH@Z`
- size: `2112`
- prototype: `__int64 __fastcall(CWriterGlobalHelper *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002da58`

## callees

- `0x18002c17c`
- `0x18002c390`
- `0x18002c8fc`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18002c9db`
- `IisRTL!PuDbgPrintW` at `0x18002ca2e`
- `IisRTL!PuDbgPrintW` at `0x18002cae5`
- `IisRTL!PuDbgPrintW` at `0x18002cbd6`
- `IisRTL!PuDbgPrintW` at `0x18002cc89`
- `IisRTL!PuDbgPrintW` at `0x18002cd3d`
- `IisRTL!PuDbgPrintW` at `0x18002cf1b`
- `IisRTL!PuDbgPrintW` at `0x18002cfd2`
- `IisRTL!PuDbgPrintW` at `0x18002c9db`
- `IisRTL!PuDbgPrintW` at `0x18002ca2e`
- `IisRTL!PuDbgPrintW` at `0x18002cae5`
- `IisRTL!PuDbgPrintW` at `0x18002cbd6`
- `IisRTL!PuDbgPrintW` at `0x18002cc89`
- `IisRTL!PuDbgPrintW` at `0x18002cd3d`
- `IisRTL!PuDbgPrintW` at `0x18002cf1b`
- `IisRTL!PuDbgPrintW` at `0x18002cfd2`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18002ca54`
- `IISCFG!DllGetSimpleObjectByIDEx` at `0x18002ca54`

## string_xrefs

- `0x18002cb57`: `IIsConfigObject`
- `0x18002c9c2`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002ca27`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002ca6a`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002c9b7`: `CWriterGlobalHelper::InitializeGlobals`
- `0x18002ca15`: `CWriterGlobalHelper::InitializeGlobals`
- `0x18002ca91`: `CWriterGlobalHelper::InitializeGlobals`
- `0x18002caab`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002cbbb`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002cc7d`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002cd31`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002cf0f`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002cfc6`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`

## pseudocode

```c
__int64 __fastcall CWriterGlobalHelper::InitializeGlobals(unsigned __int16 **this, int a2)
{
  __int64 *v4; // r12
  struct IMetabaseSchemaCompiler *v5; // rcx
  int BinFile; // eax
  int SimpleObjectByIDEx; // ebx
  __int64 v8; // rcx
  int v9; // eax
  struct ISimpleTableDispenser2 *v10; // rdx
  struct ISimpleTableDispenser2 *v11; // rdx
  int v12; // eax
  _QWORD *v13; // r13
  __int64 v14; // rcx
  unsigned __int16 *v15; // rcx
  int v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+68h] [rbp-98h]
  int v22; // [rsp+6Ch] [rbp-94h]
  int v23; // [rsp+70h] [rbp-90h]
  int v24; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v25; // [rsp+78h] [rbp-88h]
  unsigned __int64 v26; // [rsp+80h] [rbp-80h]
  __int64 v27; // [rsp+88h] [rbp-78h]
  unsigned int v28; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+94h] [rbp-6Ch] BYREF
  int v30; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v31[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v32; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v33[12]; // [rsp+ACh] [rbp-54h] BYREF
  int *v34; // [rsp+B8h] [rbp-48h]
  __int128 v35; // [rsp+C0h] [rbp-40h]
  __int128 v36; // [rsp+D0h] [rbp-30h]
  _QWORD v37[18]; // [rsp+E0h] [rbp-20h] BYREF

  v30 = 1002;
  v19 = 0;
  v31[0] = 0;
  v31[1] = 13;
  v28 = 0;
  v18 = 2;
  v29 = 2;
  memset_0(v37, 0, sizeof(v37));
  v32 = 0;
  *(_DWORD *)&v33[8] = 0;
  v4 = (__int64 *)(this + 31);
  v34 = &v29;
  *(_QWORD *)v33 = 1;
  v35 = 0;
  v36 = 0;
  BinFile = GetBinFile(v5, this + 31);
  SimpleObjectByIDEx = BinFile;
  if ( BinFile >= 0 )
  {
    if ( !a2 || *v4 && *(_WORD *)*v4 )
    {
      SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v19, L"IIS");
      if ( SimpleObjectByIDEx >= 0 )
      {
        v8 = *v4;
        v9 = 2 * *((_DWORD *)this + 64);
        v21 = 2;
        v24 = v9;
        v20 = v8;
        v22 = -268435455;
        v23 = 130;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
            680,
            "CWriterGlobalHelper::InitializeGlobals",
            L"[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n",
            L"COLUMNMETA",
            L"ByID",
            v8);
        v25 = L"METABASE";
        v26 = 2;
        v27 = 130;
        SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v19 + 24LL))(
                               v19,
                               L"META",
                               L"TABLEMETA",
                               &v20,
                               &v18,
                               3,
                               0,
                               (char *)this + 64);
        if ( SimpleObjectByIDEx >= 0 )
        {
          SimpleObjectByIDEx = CWriterGlobalHelper::GetInternalTableName(
                                 (CWriterGlobalHelper *)this,
                                 v10,
                                 L"IIsConfigObject",
                                 this + 29);
          if ( SimpleObjectByIDEx >= 0 )
          {
            SimpleObjectByIDEx = CWriterGlobalHelper::GetInternalTableName(
                                   (CWriterGlobalHelper *)this,
                                   v11,
                                   L"MBProperty",
                                   this + 28);
            if ( SimpleObjectByIDEx >= 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrintW(
                  g_pDebug,
                  "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
                  736,
                  "CWriterGlobalHelper::InitializeGlobals",
                  L"[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n",
                  L"TAGMETA",
                  L"ByTableAndColumnIndexAndNameOnly",
                  *v4);
              v25 = L"ByTableAndColumnIndexAndNameOnly";
              v26 = 0xF000000400000002uLL;
              v27 = 130;
              SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, unsigned __int16 **))(*(_QWORD *)v19 + 24LL))(
                                     v19,
                                     L"META",
                                     L"TAGMETA",
                                     &v20,
                                     &v18,
                                     3,
                                     0,
                                     this);
              if ( SimpleObjectByIDEx >= 0 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrintW(
                    g_pDebug,
                    "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
                    768,
                    "CWriterGlobalHelper::InitializeGlobals",
                    L"[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n",
                    L"TAGMETA",
                    L"ByTableAndColumnIndexAndValueOnly",
                    *v4);
                v25 = L"ByTableAndColumnIndexAndValueOnly";
                v26 = 0xF000000400000002uLL;
                v27 = 130;
                SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v19 + 24LL))(
                                       v19,
                                       L"META",
                                       L"TAGMETA",
                                       &v20,
                                       &v18,
                                       3,
                                       0,
                                       (char *)this + 8);
                if ( SimpleObjectByIDEx >= 0 )
                {
                  if ( (g_dwDebugFlags & 3) != 0 )
                    PuDbgPrintW(
                      g_pDebug,
                      "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
                      801,
                      "CWriterGlobalHelper::InitializeGlobals",
                      L"[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n",
                      L"TAGMETA",
                      L"ByTableAndColumnIndexOnly",
                      *v4);
                  v25 = L"ByTableAndColumnIndexOnly";
                  v26 = 0xF000000400000002uLL;
                  v27 = 130;
                  SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v19 + 24LL))(
                                         v19,
                                         L"META",
                                         L"TAGMETA",
                                         &v20,
                                         &v18,
                                         3,
                                         0,
                                         (char *)this + 16);
                  if ( SimpleObjectByIDEx >= 0 )
                  {
                    v25 = L"ByTableAndTagIDOnly";
                    v26 = 0xF000000400000002uLL;
                    v27 = 130;
                    SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v19 + 24LL))(
                                           v19,
                                           L"META",
                                           L"TAGMETA",
                                           &v20,
                                           &v18,
                                           3,
                                           0,
                                           (char *)this + 24);
                    if ( SimpleObjectByIDEx >= 0 )
                    {
                      v25 = L"ByTableAndTagNameOnly";
                      v26 = 0xF000000400000002uLL;
                      v27 = 130;
                      SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v19 + 24LL))(
                                             v19,
                                             L"META",
                                             L"TAGMETA",
                                             &v20,
                                             &v18,
                                             3,
                                             0,
                                             (char *)this + 32);
                      if ( SimpleObjectByIDEx >= 0 )
                      {
                        --v18;
                        v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v19 + 24LL))(
                                v19,
                                L"META",
                                L"COLUMNMETA",
                                &v20,
                                &v18,
                                3,
                                0,
                                (char *)this + 40);
                        ++v18;
                        SimpleObjectByIDEx = v12;
                        if ( v12 >= 0 )
                        {
                          if ( (g_dwDebugFlags & 3) != 0 )
                            PuDbgPrintW(
                              g_pDebug,
                              "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
                              910,
                              "CWriterGlobalHelper::InitializeGlobals",
                              L"[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n",
                              L"COLUMNMETA",
                              L"ByID",
                              *v4);
                          v25 = L"ByID";
                          v13 = this + 6;
                          v26 = 0xF000000400000002uLL;
                          v27 = 130;
                          SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v19 + 24LL))(
                                                 v19,
                                                 L"META",
                                                 L"COLUMNMETA",
                                                 &v20,
                                                 &v18,
                                                 3,
                                                 0,
                                                 (char *)this + 48);
                          if ( SimpleObjectByIDEx >= 0 )
                          {
                            if ( (g_dwDebugFlags & 3) != 0 )
                              PuDbgPrintW(
                                g_pDebug,
                                "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
                                942,
                                "CWriterGlobalHelper::InitializeGlobals",
                                L"[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n",
                                L"COLUMNMETA",
                                L"ByID",
                                *v4);
                            v25 = L"ByName";
                            v27 = 130;
                            v26 = 0xF000000400000002uLL;
                            SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v19 + 24LL))(
                                                   v19,
                                                   L"META",
                                                   L"COLUMNMETA",
                                                   &v20,
                                                   &v18,
                                                   3,
                                                   0,
                                                   (char *)this + 56);
                            if ( SimpleObjectByIDEx >= 0 )
                            {
                              v14 = *v13;
                              v37[0] = this[29];
                              v37[13] = &v30;
                              SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _DWORD *, _QWORD, _QWORD *, unsigned int *))(*(_QWORD *)v14 + 56LL))(
                                                     v14,
                                                     0,
                                                     2,
                                                     v31,
                                                     0,
                                                     v37,
                                                     &v28);
                              if ( SimpleObjectByIDEx >= 0 )
                              {
                                SimpleObjectByIDEx = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)*v13 + 32LL))(
                                                       *v13,
                                                       v28,
                                                       *((unsigned int *)this + 18),
                                                       0,
                                                       0,
                                                       (char *)this + 80);
                                if ( SimpleObjectByIDEx >= 0 )
                                {
                                  v15 = this[2];
                                  *(_QWORD *)&v33[4] = this[28];
                                  SimpleObjectByIDEx = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD, __int64, int *, _QWORD, _BYTE *, char *))(*(_QWORD *)v15 + 56LL))(
                                                         v15,
                                                         0,
                                                         2,
                                                         &v32,
                                                         0,
                                                         &v33[4],
                                                         (char *)this + 240);
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
          642,
          "CWriterGlobalHelper::InitializeGlobals",
          L"[InitializeGlobals] Expected to find a valid schema bin file. GetBinFileName returned a null file name. Bin fi"
           "le is either invalid or not found.\n");
      SimpleObjectByIDEx = -2147023890;
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v17 = BinFile;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
      633,
      "CWriterGlobalHelper::InitializeGlobals",
      L"[InitializeGlobals] Unable to get the the bin file name. GetBinFileName failed with hr = 0x%x.\n",
      v17);
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)SimpleObjectByIDEx;
}

```

## disassembly

```asm
0x18002c8fc  push    rbp
0x18002c8fe  push    rbx
0x18002c8ff  push    rsi
0x18002c900  push    rdi
0x18002c901  push    r12
0x18002c903  push    r13
0x18002c905  push    r14
0x18002c907  push    r15
0x18002c909  lea     rbp, [rsp-88h]
0x18002c911  sub     rsp, 188h
0x18002c918  mov     rax, cs:__security_cookie
0x18002c91f  xor     rax, rsp
0x18002c922  mov     [rbp+0C0h+var_50], rax
0x18002c926  xor     r13d, r13d
0x18002c929  mov     [rbp+0C0h+var_128], 3EAh
0x18002c930  mov     edi, edx
0x18002c932  mov     [rsp+1C0h+var_168], r13
0x18002c937  mov     rsi, rcx
0x18002c93a  mov     [rbp+0C0h+var_120], r13d
0x18002c93e  xor     edx, edx; Val
0x18002c940  mov     [rbp+0C0h+var_11C], 0Dh
0x18002c947  lea     r14d, [r13+2]
0x18002c94b  mov     [rbp+0C0h+var_130], r13d
0x18002c94f  mov     r8d, 90h; Size
0x18002c955  mov     [rsp+1C0h+var_170], r14d
0x18002c95a  lea     rcx, [rbp+0C0h+var_E0]; void *
0x18002c95e  mov     [rbp+0C0h+var_12C], r14d
0x18002c962  call    memset_0
0x18002c967  xorps   xmm0, xmm0
0x18002c96a  mov     [rbp+0C0h+var_118], r13d
0x18002c96e  lea     rax, [rbp+0C0h+var_12C]
0x18002c972  movups  [rbp+0C0h+var_110], xmm0
0x18002c976  lea     r12, [rsi+0F8h]
0x18002c97d  mov     qword ptr [rbp+0C0h+var_110+8], rax
0x18002c981  lea     r15d, [r13+1]
0x18002c985  mov     rdx, r12; unsigned __int16 **
0x18002c988  mov     [rbp+0C0h+var_114], r15d
0x18002c98c  movups  [rbp+0C0h+var_100], xmm0
0x18002c990  movups  [rbp+0C0h+var_F0], xmm0
0x18002c994  call    ?GetBinFile@@YAJPEAUIMetabaseSchemaCompiler@@PEAPEAG@Z; GetBinFile(IMetabaseSchemaCompiler *,ushort * *)
0x18002c999  mov     ebx, eax
0x18002c99b  test    eax, eax
0x18002c99d  jns     short loc_18002C9E6
0x18002c99f  lea     edi, [r13+3]
0x18002c9a3  test    byte ptr cs:g_dwDebugFlags, dil
0x18002c9aa  jz      loc_18002D104
0x18002c9b0  mov     rcx, cs:g_pDebug
0x18002c9b7  lea     r9, aCwriterglobalh; "CWriterGlobalHelper::InitializeGlobals"
0x18002c9be  mov     dword ptr [rsp+1C0h+var_198], eax
0x18002c9c2  lea     rdx, aInetsrvIisMbXm_1; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002c9c9  lea     rax, aInitializeglob; "[InitializeGlobals] Unable to get the t"...
0x18002c9d0  mov     r8d, 279h
0x18002c9d6  mov     [rsp+1C0h+var_1A0], rax
0x18002c9db  call    cs:__imp_PuDbgPrintW
0x18002c9e1  jmp     loc_18002D104
0x18002c9e6  test    edi, edi
0x18002c9e8  jz      short loc_18002CA3E
0x18002c9ea  mov     rcx, [r12]
0x18002c9ee  test    rcx, rcx
0x18002c9f1  jz      short loc_18002C9F9
0x18002c9f3  cmp     r13w, [rcx]
0x18002c9f7  jnz     short loc_18002CA3E
0x18002c9f9  mov     edi, 3
0x18002c9fe  test    byte ptr cs:g_dwDebugFlags, dil
0x18002ca05  jz      short loc_18002CA34
0x18002ca07  mov     rcx, cs:g_pDebug
0x18002ca0e  lea     rax, aInitializeglob_3; "[InitializeGlobals] Expected to find a "...
0x18002ca15  lea     r9, aCwriterglobalh; "CWriterGlobalHelper::InitializeGlobals"
0x18002ca1c  mov     [rsp+1C0h+var_1A0], rax
0x18002ca21  mov     r8d, 282h
0x18002ca27  lea     rdx, aInetsrvIisMbXm_1; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002ca2e  call    cs:__imp_PuDbgPrintW
0x18002ca34  mov     ebx, 800703EEh
0x18002ca39  jmp     loc_18002D104
0x18002ca3e  lea     r9, aIis; "IIS"
0x18002ca45  mov     ecx, r15d
0x18002ca48  lea     r8, [rsp+1C0h+var_168]
0x18002ca4d  lea     rdx, IID_ISimpleTableDispenser2
0x18002ca54  call    cs:__imp_DllGetSimpleObjectByIDEx
0x18002ca5a  mov     ebx, eax
0x18002ca5c  test    eax, eax
0x18002ca5e  js      loc_18002D104
0x18002ca64  mov     eax, [rsi+100h]
0x18002ca6a  lea     r15, aInetsrvIisMbXm_1; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002ca71  mov     rcx, [r12]
0x18002ca75  lea     r8, aByid; "ByID"
0x18002ca7c  add     eax, eax
0x18002ca7e  mov     [rsp+1C0h+var_158], r14d
0x18002ca83  mov     ebx, 82h
0x18002ca88  mov     [rsp+1C0h+var_14C], eax
0x18002ca8c  mov     [rsp+1C0h+var_160], rcx
0x18002ca91  lea     r14, aCwriterglobalh; "CWriterGlobalHelper::InitializeGlobals"
0x18002ca98  mov     [rsp+1C0h+var_154], 0F0000001h
0x18002caa0  lea     rdx, aColumnmeta; "COLUMNMETA"
0x18002caa7  mov     [rsp+1C0h+var_150], ebx
0x18002caab  lea     rax, aInitializeglob_0; "[InitializeGlobals] Reading table: %s w"...
0x18002cab2  lea     edi, [rbx-7Fh]
0x18002cab5  test    byte ptr cs:g_dwDebugFlags, dil
0x18002cabc  jz      short loc_18002CAEB
0x18002cabe  mov     [rsp+1C0h+var_188], rcx
0x18002cac3  mov     r9, r14
0x18002cac6  mov     rcx, cs:g_pDebug
0x18002cacd  mov     [rsp+1C0h+var_190], r8
0x18002cad2  mov     r8d, 2A8h
0x18002cad8  mov     [rsp+1C0h+var_198], rdx
0x18002cadd  mov     rdx, r15
0x18002cae0  mov     [rsp+1C0h+var_1A0], rax
0x18002cae5  call    cs:__imp_PuDbgPrintW
0x18002caeb  mov     rcx, [rsp+1C0h+var_168]
0x18002caf0  lea     rax, aMetabase; "METABASE"
0x18002caf7  mov     [rsp+1C0h+var_148], rax
0x18002cafc  lea     rdx, [rsi+40h]
0x18002cb00  mov     [rsp+1C0h+var_188], rdx
0x18002cb05  lea     r9, [rsp+1C0h+var_160]
0x18002cb0a  mov     [rbp+0C0h+var_140], 2
0x18002cb12  lea     rdx, [rsp+1C0h+var_170]
0x18002cb17  mov     [rbp+0C0h+var_138], rbx
0x18002cb1b  lea     r8, aTablemeta; "TABLEMETA"
0x18002cb22  mov     rax, [rcx]
0x18002cb25  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002cb2a  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002cb2e  mov     [rsp+1C0h+var_1A0], rdx
0x18002cb33  lea     rdx, aMeta; "META"
0x18002cb3a  mov     rax, [rax+18h]
0x18002cb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb43  mov     ebx, eax
0x18002cb45  test    eax, eax
0x18002cb47  js      loc_18002D104
0x18002cb4d  lea     r9, [rsi+0E8h]; unsigned __int16 **
0x18002cb54  mov     rcx, rsi; this
0x18002cb57  lea     r8, aIisconfigobjec; "IIsConfigObject"
0x18002cb5e  call    ?GetInternalTableName@CWriterGlobalHelper@@AEAAJPEAUISimpleTableDispenser2@@PEBGPEAPEAG@Z; CWriterGlobalHelper::GetInternalTableName(ISimpleTableDispenser2 *,ushort const *,ushort * *)
0x18002cb63  mov     ebx, eax
0x18002cb65  test    eax, eax
0x18002cb67  js      loc_18002D104
0x18002cb6d  lea     r9, [rsi+0E0h]; unsigned __int16 **
0x18002cb74  mov     rcx, rsi; this
0x18002cb77  lea     r8, aMbproperty_0; "MBProperty"
0x18002cb7e  call    ?GetInternalTableName@CWriterGlobalHelper@@AEAAJPEAUISimpleTableDispenser2@@PEBGPEAPEAG@Z; CWriterGlobalHelper::GetInternalTableName(ISimpleTableDispenser2 *,ushort const *,ushort * *)
0x18002cb83  mov     ebx, eax
0x18002cb85  test    eax, eax
0x18002cb87  js      loc_18002D104
0x18002cb8d  test    byte ptr cs:g_dwDebugFlags, dil
0x18002cb94  lea     rcx, aBytableandcolu_0; "ByTableAndColumnIndexAndNameOnly"
0x18002cb9b  lea     rbx, aTagmeta; "TAGMETA"
0x18002cba2  jz      short loc_18002CBE3
0x18002cba4  mov     rax, [r12]
0x18002cba8  mov     r9, r14
0x18002cbab  mov     [rsp+1C0h+var_188], rax
0x18002cbb0  mov     r8d, 2E0h
0x18002cbb6  mov     [rsp+1C0h+var_190], rcx
0x18002cbbb  lea     rax, aInitializeglob_0; "[InitializeGlobals] Reading table: %s w"...
0x18002cbc2  mov     rcx, cs:g_pDebug
0x18002cbc9  mov     rdx, r15
0x18002cbcc  mov     [rsp+1C0h+var_198], rbx
0x18002cbd1  mov     [rsp+1C0h+var_1A0], rax
0x18002cbd6  call    cs:__imp_PuDbgPrintW
0x18002cbdc  lea     rcx, aBytableandcolu_0; "ByTableAndColumnIndexAndNameOnly"
0x18002cbe3  mov     [rsp+1C0h+var_148], rcx
0x18002cbe8  lea     rdx, [rsp+1C0h+var_170]
0x18002cbed  mov     rcx, [rsp+1C0h+var_168]
0x18002cbf2  lea     r9, [rsp+1C0h+var_160]
0x18002cbf7  mov     [rsp+1C0h+var_188], rsi
0x18002cbfc  mov     r8, rbx
0x18002cbff  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002cc06  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002cc0d  mov     [rbp+0C0h+var_138], 82h
0x18002cc15  mov     rax, [rcx]
0x18002cc18  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002cc1d  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002cc21  mov     [rsp+1C0h+var_1A0], rdx
0x18002cc26  lea     rdx, aMeta; "META"
0x18002cc2d  mov     rax, [rax+18h]
0x18002cc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc36  mov     ebx, eax
0x18002cc38  test    eax, eax
0x18002cc3a  js      loc_18002D104
0x18002cc40  test    byte ptr cs:g_dwDebugFlags, dil
0x18002cc47  lea     rbx, aBytableandcolu_1; "ByTableAndColumnIndexAndValueOnly"
0x18002cc4e  jz      short loc_18002CC8F
0x18002cc50  mov     rax, [r12]
0x18002cc54  mov     r9, r14
0x18002cc57  mov     rcx, cs:g_pDebug
0x18002cc5e  mov     r8d, 300h
0x18002cc64  mov     [rsp+1C0h+var_188], rax
0x18002cc69  mov     rdx, r15
0x18002cc6c  lea     rax, aTagmeta; "TAGMETA"
0x18002cc73  mov     [rsp+1C0h+var_190], rbx
0x18002cc78  mov     [rsp+1C0h+var_198], rax
0x18002cc7d  lea     rax, aInitializeglob_0; "[InitializeGlobals] Reading table: %s w"...
0x18002cc84  mov     [rsp+1C0h+var_1A0], rax
0x18002cc89  call    cs:__imp_PuDbgPrintW
0x18002cc8f  mov     rcx, [rsp+1C0h+var_168]
0x18002cc94  lea     rdx, [rsi+8]
0x18002cc98  mov     [rsp+1C0h+var_188], rdx
0x18002cc9d  lea     r9, [rsp+1C0h+var_160]
0x18002cca2  mov     [rsp+1C0h+var_148], rbx
0x18002cca7  lea     rdx, [rsp+1C0h+var_170]
0x18002ccac  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002ccb3  lea     r8, aTagmeta; "TAGMETA"
0x18002ccba  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002ccc1  mov     [rbp+0C0h+var_138], 82h
0x18002ccc9  mov     rax, [rcx]
0x18002cccc  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002ccd1  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002ccd5  mov     [rsp+1C0h+var_1A0], rdx
0x18002ccda  lea     rdx, aMeta; "META"
0x18002cce1  mov     rax, [rax+18h]
0x18002cce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccea  mov     ebx, eax
0x18002ccec  test    eax, eax
0x18002ccee  js      loc_18002D104
0x18002ccf4  test    byte ptr cs:g_dwDebugFlags, dil
0x18002ccfb  lea     rbx, aBytableandcolu; "ByTableAndColumnIndexOnly"
0x18002cd02  jz      short loc_18002CD43
0x18002cd04  mov     rax, [r12]
0x18002cd08  mov     r9, r14
0x18002cd0b  mov     rcx, cs:g_pDebug
0x18002cd12  mov     r8d, 321h
0x18002cd18  mov     [rsp+1C0h+var_188], rax
0x18002cd1d  mov     rdx, r15
0x18002cd20  lea     rax, aTagmeta; "TAGMETA"
0x18002cd27  mov     [rsp+1C0h+var_190], rbx
0x18002cd2c  mov     [rsp+1C0h+var_198], rax
0x18002cd31  lea     rax, aInitializeglob_0; "[InitializeGlobals] Reading table: %s w"...
0x18002cd38  mov     [rsp+1C0h+var_1A0], rax
0x18002cd3d  call    cs:__imp_PuDbgPrintW
0x18002cd43  mov     rcx, [rsp+1C0h+var_168]
0x18002cd48  lea     rdx, [rsi+10h]
0x18002cd4c  mov     [rsp+1C0h+var_188], rdx
0x18002cd51  lea     r9, [rsp+1C0h+var_160]
0x18002cd56  mov     [rsp+1C0h+var_148], rbx
0x18002cd5b  lea     rdx, [rsp+1C0h+var_170]
0x18002cd60  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002cd67  lea     r8, aTagmeta; "TAGMETA"
0x18002cd6e  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002cd75  mov     [rbp+0C0h+var_138], 82h
0x18002cd7d  mov     rax, [rcx]
0x18002cd80  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002cd85  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002cd89  mov     [rsp+1C0h+var_1A0], rdx
0x18002cd8e  lea     rdx, aMeta; "META"
0x18002cd95  mov     rax, [rax+18h]
0x18002cd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd9e  mov     ebx, eax
0x18002cda0  test    eax, eax
0x18002cda2  js      loc_18002D104
0x18002cda8  mov     rcx, [rsp+1C0h+var_168]
0x18002cdad  lea     rax, aBytableandtagi; "ByTableAndTagIDOnly"
0x18002cdb4  mov     [rsp+1C0h+var_148], rax
0x18002cdb9  lea     rdx, [rsi+18h]
0x18002cdbd  mov     [rsp+1C0h+var_188], rdx
0x18002cdc2  lea     r9, [rsp+1C0h+var_160]
0x18002cdc7  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002cdce  lea     rdx, [rsp+1C0h+var_170]
0x18002cdd3  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002cdda  lea     r8, aTagmeta; "TAGMETA"
0x18002cde1  mov     [rbp+0C0h+var_138], 82h
0x18002cde9  mov     rax, [rcx]
0x18002cdec  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002cdf1  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002cdf5  mov     [rsp+1C0h+var_1A0], rdx
0x18002cdfa  lea     rdx, aMeta; "META"
0x18002ce01  mov     rax, [rax+18h]
0x18002ce05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce0a  mov     ebx, eax
0x18002ce0c  test    eax, eax
0x18002ce0e  js      loc_18002D104
0x18002ce14  mov     rcx, [rsp+1C0h+var_168]
0x18002ce19  lea     rax, aBytableandtagn; "ByTableAndTagNameOnly"
0x18002ce20  mov     [rsp+1C0h+var_148], rax
0x18002ce25  lea     rdx, [rsi+20h]
0x18002ce29  mov     [rsp+1C0h+var_188], rdx
0x18002ce2e  lea     r9, [rsp+1C0h+var_160]
0x18002ce33  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002ce3a  lea     rdx, [rsp+1C0h+var_170]
0x18002ce3f  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002ce46  lea     r8, aTagmeta; "TAGMETA"
0x18002ce4d  mov     [rbp+0C0h+var_138], 82h
0x18002ce55  mov     rax, [rcx]
0x18002ce58  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002ce5d  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002ce61  mov     [rsp+1C0h+var_1A0], rdx
0x18002ce66  lea     rdx, aMeta; "META"
0x18002ce6d  mov     rax, [rax+18h]
0x18002ce71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce76  mov     ebx, eax
0x18002ce78  test    eax, eax
0x18002ce7a  js      loc_18002D104
0x18002ce80  mov     rcx, [rsp+1C0h+var_168]
0x18002ce85  lea     rdx, [rsi+28h]
0x18002ce89  dec     [rsp+1C0h+var_170]
0x18002ce8d  lea     r9, [rsp+1C0h+var_160]
0x18002ce92  mov     [rsp+1C0h+var_188], rdx
0x18002ce97  lea     r8, aColumnmeta; "COLUMNMETA"
0x18002ce9e  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002cea3  lea     rdx, [rsp+1C0h+var_170]
0x18002cea8  mov     rax, [rcx]
0x18002ceab  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002ceaf  mov     [rsp+1C0h+var_1A0], rdx
  ... truncated ...
```
