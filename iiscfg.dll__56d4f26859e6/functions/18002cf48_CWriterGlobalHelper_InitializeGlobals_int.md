# CWriterGlobalHelper::InitializeGlobals(int)

- ea: `0x18002cf48`
- end: `0x18002d72a`
- name: `?InitializeGlobals@CWriterGlobalHelper@@QEAAJH@Z`
- size: `2018`
- prototype: `__int64 __fastcall(CWriterGlobalHelper *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a6f0`

## callees

- `0x180002af0`
- `0x18002c9cc`
- `0x18002cbe0`
- `0x18002cf48`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18002d023`
- `IisRTL!PuDbgPrintW` at `0x18002d0d3`
- `IisRTL!PuDbgPrintW` at `0x18002d1c4`
- `IisRTL!PuDbgPrintW` at `0x18002d277`
- `IisRTL!PuDbgPrintW` at `0x18002d32b`
- `IisRTL!PuDbgPrintW` at `0x18002d509`
- `IisRTL!PuDbgPrintW` at `0x18002d5c0`
- `IisRTL!PuDbgPrintW` at `0x18002d023`
- `IisRTL!PuDbgPrintW` at `0x18002d0d3`
- `IisRTL!PuDbgPrintW` at `0x18002d1c4`
- `IisRTL!PuDbgPrintW` at `0x18002d277`
- `IisRTL!PuDbgPrintW` at `0x18002d32b`
- `IisRTL!PuDbgPrintW` at `0x18002d509`
- `IisRTL!PuDbgPrintW` at `0x18002d5c0`

## string_xrefs

- `0x18002d145`: `IIsConfigObject`
- `0x18002d00a`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002d064`: `inetsrv\iis\mb\xmlwriter\writerglobalhelper.cpp`
- `0x18002cfff`: `CWriterGlobalHelper::InitializeGlobals`
- `0x18002d059`: `CWriterGlobalHelper::InitializeGlobals`
- `0x18002d099`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002d1a9`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002d26b`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002d31f`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002d4fd`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`
- `0x18002d5b4`: `[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n`

## pseudocode

```c
__int64 __fastcall CWriterGlobalHelper::InitializeGlobals(CWriterGlobalHelper *this)
{
  __int64 *v2; // r12
  struct IMetabaseSchemaCompiler *v3; // rcx
  int BinFile; // eax
  int SimpleObjectByIDEx; // ebx
  __int64 v6; // rcx
  int v7; // eax
  struct ISimpleTableDispenser2 *v8; // rdx
  struct ISimpleTableDispenser2 *v9; // rdx
  int v10; // eax
  _QWORD *v11; // r13
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v15; // [rsp+28h] [rbp-D8h]
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  void *v17; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+6Ch] [rbp-94h]
  int v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v23; // [rsp+78h] [rbp-88h]
  unsigned __int64 v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+88h] [rbp-78h]
  unsigned int v26; // [rsp+90h] [rbp-70h] BYREF
  int v27; // [rsp+94h] [rbp-6Ch] BYREF
  int v28; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v29[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v30; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v31[12]; // [rsp+ACh] [rbp-54h] BYREF
  int *v32; // [rsp+B8h] [rbp-48h]
  __int128 v33; // [rsp+C0h] [rbp-40h]
  __int128 v34; // [rsp+D0h] [rbp-30h]
  _QWORD v35[18]; // [rsp+E0h] [rbp-20h] BYREF

  v28 = 1002;
  v17 = 0;
  v29[0] = 0;
  v29[1] = 13;
  v26 = 0;
  v16 = 2;
  v27 = 2;
  memset_0(v35, 0, sizeof(v35));
  v30 = 0;
  *(_DWORD *)&v31[8] = 0;
  v2 = (__int64 *)((char *)this + 248);
  v32 = &v27;
  *(_QWORD *)v31 = 1;
  v33 = 0;
  v34 = 0;
  BinFile = GetBinFile(v3, (LPVOID *)this + 31);
  SimpleObjectByIDEx = BinFile;
  if ( BinFile >= 0 )
  {
    SimpleObjectByIDEx = DllGetSimpleObjectByIDEx(1, &IID_ISimpleTableDispenser2, &v17);
    if ( SimpleObjectByIDEx >= 0 )
    {
      v6 = *v2;
      v7 = 2 * *((_DWORD *)this + 64);
      v19 = 2;
      v22 = v7;
      v18 = v6;
      v20 = -268435455;
      v21 = 130;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
          680,
          "CWriterGlobalHelper::InitializeGlobals",
          L"[InitializeGlobals] Reading table: %s with hint %s from file: %s.\n",
          L"COLUMNMETA",
          L"ByID",
          v6);
      v23 = L"METABASE";
      v24 = 2;
      v25 = 130;
      SimpleObjectByIDEx = (*(__int64 (__fastcall **)(void *, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v17 + 24LL))(
                             v17,
                             L"META",
                             L"TABLEMETA",
                             &v18,
                             &v16,
                             3,
                             0,
                             (char *)this + 64);
      if ( SimpleObjectByIDEx >= 0 )
      {
        SimpleObjectByIDEx = CWriterGlobalHelper::GetInternalTableName(
                               this,
                               v8,
                               L"IIsConfigObject",
                               (unsigned __int16 **)this + 29);
        if ( SimpleObjectByIDEx >= 0 )
        {
          SimpleObjectByIDEx = CWriterGlobalHelper::GetInternalTableName(
                                 this,
                                 v9,
                                 L"MBProperty",
                                 (unsigned __int16 **)this + 28);
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
                *v2);
            v23 = L"ByTableAndColumnIndexAndNameOnly";
            v24 = 0xF000000400000002uLL;
            v25 = 130;
            SimpleObjectByIDEx = (*(__int64 (__fastcall **)(void *, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, CWriterGlobalHelper *))(*(_QWORD *)v17 + 24LL))(
                                   v17,
                                   L"META",
                                   L"TAGMETA",
                                   &v18,
                                   &v16,
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
                  *v2);
              v23 = L"ByTableAndColumnIndexAndValueOnly";
              v24 = 0xF000000400000002uLL;
              v25 = 130;
              SimpleObjectByIDEx = (*(__int64 (__fastcall **)(void *, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v17 + 24LL))(
                                     v17,
                                     L"META",
                                     L"TAGMETA",
                                     &v18,
                                     &v16,
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
                    *v2);
                v23 = L"ByTableAndColumnIndexOnly";
                v24 = 0xF000000400000002uLL;
                v25 = 130;
                SimpleObjectByIDEx = (*(__int64 (__fastcall **)(void *, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v17 + 24LL))(
                                       v17,
                                       L"META",
                                       L"TAGMETA",
                                       &v18,
                                       &v16,
                                       3,
                                       0,
                                       (char *)this + 16);
                if ( SimpleObjectByIDEx >= 0 )
                {
                  v23 = L"ByTableAndTagIDOnly";
                  v24 = 0xF000000400000002uLL;
                  v25 = 130;
                  SimpleObjectByIDEx = (*(__int64 (__fastcall **)(void *, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v17 + 24LL))(
                                         v17,
                                         L"META",
                                         L"TAGMETA",
                                         &v18,
                                         &v16,
                                         3,
                                         0,
                                         (char *)this + 24);
                  if ( SimpleObjectByIDEx >= 0 )
                  {
                    v23 = L"ByTableAndTagNameOnly";
                    v24 = 0xF000000400000002uLL;
                    v25 = 130;
                    SimpleObjectByIDEx = (*(__int64 (__fastcall **)(void *, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v17 + 24LL))(
                                           v17,
                                           L"META",
                                           L"TAGMETA",
                                           &v18,
                                           &v16,
                                           3,
                                           0,
                                           (char *)this + 32);
                    if ( SimpleObjectByIDEx >= 0 )
                    {
                      --v16;
                      v10 = (*(__int64 (__fastcall **)(void *, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v17 + 24LL))(
                              v17,
                              L"META",
                              L"COLUMNMETA",
                              &v18,
                              &v16,
                              3,
                              0,
                              (char *)this + 40);
                      ++v16;
                      SimpleObjectByIDEx = v10;
                      if ( v10 >= 0 )
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
                            *v2);
                        v23 = L"ByID";
                        v11 = (_QWORD *)((char *)this + 48);
                        v24 = 0xF000000400000002uLL;
                        v25 = 130;
                        SimpleObjectByIDEx = (*(__int64 (__fastcall **)(void *, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v17 + 24LL))(
                                               v17,
                                               L"META",
                                               L"COLUMNMETA",
                                               &v18,
                                               &v16,
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
                              *v2);
                          v23 = L"ByName";
                          v25 = 130;
                          v24 = 0xF000000400000002uLL;
                          SimpleObjectByIDEx = (*(__int64 (__fastcall **)(void *, const wchar_t *, const wchar_t *, __int64 *, int *, int, _DWORD, char *))(*(_QWORD *)v17 + 24LL))(
                                                 v17,
                                                 L"META",
                                                 L"COLUMNMETA",
                                                 &v18,
                                                 &v16,
                                                 3,
                                                 0,
                                                 (char *)this + 56);
                          if ( SimpleObjectByIDEx >= 0 )
                          {
                            v12 = *v11;
                            v35[0] = *((_QWORD *)this + 29);
                            v35[13] = &v28;
                            SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _DWORD *, _QWORD, _QWORD *, unsigned int *))(*(_QWORD *)v12 + 56LL))(
                                                   v12,
                                                   0,
                                                   2,
                                                   v29,
                                                   0,
                                                   v35,
                                                   &v26);
                            if ( SimpleObjectByIDEx >= 0 )
                            {
                              SimpleObjectByIDEx = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)*v11 + 32LL))(
                                                     *v11,
                                                     v26,
                                                     *((unsigned int *)this + 18),
                                                     0,
                                                     0,
                                                     (char *)this + 80);
                              if ( SimpleObjectByIDEx >= 0 )
                              {
                                v13 = *((_QWORD *)this + 2);
                                *(_QWORD *)&v31[4] = *((_QWORD *)this + 28);
                                SimpleObjectByIDEx = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *, _QWORD, _BYTE *, char *))(*(_QWORD *)v13 + 56LL))(
                                                       v13,
                                                       0,
                                                       2,
                                                       &v30,
                                                       0,
                                                       &v31[4],
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
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v15 = BinFile;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\xmlwriter\\writerglobalhelper.cpp",
      633,
      "CWriterGlobalHelper::InitializeGlobals",
      L"[InitializeGlobals] Unable to get the the bin file name. GetBinFileName failed with hr = 0x%x.\n",
      v15);
  }
  if ( v17 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)SimpleObjectByIDEx;
}

```

## disassembly

```asm
0x18002cf48  push    rbp
0x18002cf4a  push    rbx
0x18002cf4b  push    rsi
0x18002cf4c  push    rdi
0x18002cf4d  push    r12
0x18002cf4f  push    r13
0x18002cf51  push    r14
0x18002cf53  push    r15
0x18002cf55  lea     rbp, [rsp-88h]
0x18002cf5d  sub     rsp, 188h
0x18002cf64  mov     rax, cs:__security_cookie
0x18002cf6b  xor     rax, rsp
0x18002cf6e  mov     [rbp+0C0h+var_50], rax
0x18002cf72  xor     r13d, r13d
0x18002cf75  mov     [rbp+0C0h+var_128], 3EAh
0x18002cf7c  mov     rsi, rcx
0x18002cf7f  mov     [rsp+1C0h+var_168], r13
0x18002cf84  xor     edx, edx; Val
0x18002cf86  mov     [rbp+0C0h+var_120], r13d
0x18002cf8a  mov     r8d, 90h; Size
0x18002cf90  mov     [rbp+0C0h+var_11C], 0Dh
0x18002cf97  lea     edi, [r13+2]
0x18002cf9b  mov     [rbp+0C0h+var_130], r13d
0x18002cf9f  lea     rcx, [rbp+0C0h+var_E0]; void *
0x18002cfa3  mov     [rsp+1C0h+var_170], edi
0x18002cfa7  mov     [rbp+0C0h+var_12C], edi
0x18002cfaa  call    memset_0
0x18002cfaf  xorps   xmm0, xmm0
0x18002cfb2  mov     [rbp+0C0h+var_118], r13d
0x18002cfb6  lea     rax, [rbp+0C0h+var_12C]
0x18002cfba  movups  [rbp+0C0h+var_110], xmm0
0x18002cfbe  lea     r12, [rsi+0F8h]
0x18002cfc5  mov     qword ptr [rbp+0C0h+var_110+8], rax
0x18002cfc9  lea     r14d, [r13+1]
0x18002cfcd  mov     rdx, r12; unsigned __int16 **
0x18002cfd0  mov     [rbp+0C0h+var_114], r14d
0x18002cfd4  movups  [rbp+0C0h+var_100], xmm0
0x18002cfd8  movups  [rbp+0C0h+var_F0], xmm0
0x18002cfdc  call    ?GetBinFile@@YAJPEAUIMetabaseSchemaCompiler@@PEAPEAG@Z; GetBinFile(IMetabaseSchemaCompiler *,ushort * *)
0x18002cfe1  mov     ebx, eax
0x18002cfe3  test    eax, eax
0x18002cfe5  jns     short loc_18002D02E
0x18002cfe7  lea     edi, [r13+3]
0x18002cfeb  test    byte ptr cs:g_dwDebugFlags, dil
0x18002cff2  jz      loc_18002D6F2
0x18002cff8  mov     rcx, cs:g_pDebug
0x18002cfff  lea     r9, aCwriterglobalh; "CWriterGlobalHelper::InitializeGlobals"
0x18002d006  mov     dword ptr [rsp+1C0h+var_198], eax
0x18002d00a  lea     rdx, aInetsrvIisMbXm; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002d011  lea     rax, aInitializeglob; "[InitializeGlobals] Unable to get the t"...
0x18002d018  mov     r8d, 279h
0x18002d01e  mov     [rsp+1C0h+var_1A0], rax
0x18002d023  call    cs:__imp_PuDbgPrintW
0x18002d029  jmp     loc_18002D6F2
0x18002d02e  lea     r9, aIis; "IIS"
0x18002d035  mov     ecx, r14d
0x18002d038  lea     r8, [rsp+1C0h+var_168]
0x18002d03d  lea     rdx, IID_ISimpleTableDispenser2
0x18002d044  call    DllGetSimpleObjectByIDEx
0x18002d049  mov     ebx, eax
0x18002d04b  test    eax, eax
0x18002d04d  js      loc_18002D6F2
0x18002d053  mov     eax, [rsi+100h]
0x18002d059  lea     r14, aCwriterglobalh; "CWriterGlobalHelper::InitializeGlobals"
0x18002d060  mov     rcx, [r12]
0x18002d064  lea     r15, aInetsrvIisMbXm; "inetsrv\\iis\\mb\\xmlwriter\\writerglob"...
0x18002d06b  add     eax, eax
0x18002d06d  mov     [rsp+1C0h+var_158], edi
0x18002d071  mov     ebx, 82h
0x18002d076  mov     [rsp+1C0h+var_14C], eax
0x18002d07a  mov     [rsp+1C0h+var_160], rcx
0x18002d07f  lea     r8, aByid; "ByID"
0x18002d086  mov     [rsp+1C0h+var_154], 0F0000001h
0x18002d08e  lea     rdx, aColumnmeta; "COLUMNMETA"
0x18002d095  mov     [rsp+1C0h+var_150], ebx
0x18002d099  lea     rax, aInitializeglob_0; "[InitializeGlobals] Reading table: %s w"...
0x18002d0a0  lea     edi, [rbx-7Fh]
0x18002d0a3  test    byte ptr cs:g_dwDebugFlags, dil
0x18002d0aa  jz      short loc_18002D0D9
0x18002d0ac  mov     [rsp+1C0h+var_188], rcx
0x18002d0b1  mov     r9, r14
0x18002d0b4  mov     rcx, cs:g_pDebug
0x18002d0bb  mov     [rsp+1C0h+var_190], r8
0x18002d0c0  mov     r8d, 2A8h
0x18002d0c6  mov     [rsp+1C0h+var_198], rdx
0x18002d0cb  mov     rdx, r15
0x18002d0ce  mov     [rsp+1C0h+var_1A0], rax
0x18002d0d3  call    cs:__imp_PuDbgPrintW
0x18002d0d9  mov     rcx, [rsp+1C0h+var_168]
0x18002d0de  lea     rax, aMetabase; "METABASE"
0x18002d0e5  mov     [rsp+1C0h+var_148], rax
0x18002d0ea  lea     rdx, [rsi+40h]
0x18002d0ee  mov     [rsp+1C0h+var_188], rdx
0x18002d0f3  lea     r9, [rsp+1C0h+var_160]
0x18002d0f8  mov     [rbp+0C0h+var_140], 2
0x18002d100  lea     rdx, [rsp+1C0h+var_170]
0x18002d105  mov     [rbp+0C0h+var_138], rbx
0x18002d109  lea     r8, aTablemeta; "TABLEMETA"
0x18002d110  mov     rax, [rcx]
0x18002d113  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002d118  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002d11c  mov     [rsp+1C0h+var_1A0], rdx
0x18002d121  lea     rdx, aMeta; "META"
0x18002d128  mov     rax, [rax+18h]
0x18002d12c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d131  mov     ebx, eax
0x18002d133  test    eax, eax
0x18002d135  js      loc_18002D6F2
0x18002d13b  lea     r9, [rsi+0E8h]; unsigned __int16 **
0x18002d142  mov     rcx, rsi; this
0x18002d145  lea     r8, aIisconfigobjec; "IIsConfigObject"
0x18002d14c  call    ?GetInternalTableName@CWriterGlobalHelper@@AEAAJPEAUISimpleTableDispenser2@@PEBGPEAPEAG@Z; CWriterGlobalHelper::GetInternalTableName(ISimpleTableDispenser2 *,ushort const *,ushort * *)
0x18002d151  mov     ebx, eax
0x18002d153  test    eax, eax
0x18002d155  js      loc_18002D6F2
0x18002d15b  lea     r9, [rsi+0E0h]; unsigned __int16 **
0x18002d162  mov     rcx, rsi; this
0x18002d165  lea     r8, aMbproperty; "MBProperty"
0x18002d16c  call    ?GetInternalTableName@CWriterGlobalHelper@@AEAAJPEAUISimpleTableDispenser2@@PEBGPEAPEAG@Z; CWriterGlobalHelper::GetInternalTableName(ISimpleTableDispenser2 *,ushort const *,ushort * *)
0x18002d171  mov     ebx, eax
0x18002d173  test    eax, eax
0x18002d175  js      loc_18002D6F2
0x18002d17b  test    byte ptr cs:g_dwDebugFlags, dil
0x18002d182  lea     rcx, aBytableandcolu_0; "ByTableAndColumnIndexAndNameOnly"
0x18002d189  lea     rbx, aTagmeta; "TAGMETA"
0x18002d190  jz      short loc_18002D1D1
0x18002d192  mov     rax, [r12]
0x18002d196  mov     r9, r14
0x18002d199  mov     [rsp+1C0h+var_188], rax
0x18002d19e  mov     r8d, 2E0h
0x18002d1a4  mov     [rsp+1C0h+var_190], rcx
0x18002d1a9  lea     rax, aInitializeglob_0; "[InitializeGlobals] Reading table: %s w"...
0x18002d1b0  mov     rcx, cs:g_pDebug
0x18002d1b7  mov     rdx, r15
0x18002d1ba  mov     [rsp+1C0h+var_198], rbx
0x18002d1bf  mov     [rsp+1C0h+var_1A0], rax
0x18002d1c4  call    cs:__imp_PuDbgPrintW
0x18002d1ca  lea     rcx, aBytableandcolu_0; "ByTableAndColumnIndexAndNameOnly"
0x18002d1d1  mov     [rsp+1C0h+var_148], rcx
0x18002d1d6  lea     rdx, [rsp+1C0h+var_170]
0x18002d1db  mov     rcx, [rsp+1C0h+var_168]
0x18002d1e0  lea     r9, [rsp+1C0h+var_160]
0x18002d1e5  mov     [rsp+1C0h+var_188], rsi
0x18002d1ea  mov     r8, rbx
0x18002d1ed  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002d1f4  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002d1fb  mov     [rbp+0C0h+var_138], 82h
0x18002d203  mov     rax, [rcx]
0x18002d206  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002d20b  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002d20f  mov     [rsp+1C0h+var_1A0], rdx
0x18002d214  lea     rdx, aMeta; "META"
0x18002d21b  mov     rax, [rax+18h]
0x18002d21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d224  mov     ebx, eax
0x18002d226  test    eax, eax
0x18002d228  js      loc_18002D6F2
0x18002d22e  test    byte ptr cs:g_dwDebugFlags, dil
0x18002d235  lea     rbx, aBytableandcolu_1; "ByTableAndColumnIndexAndValueOnly"
0x18002d23c  jz      short loc_18002D27D
0x18002d23e  mov     rax, [r12]
0x18002d242  mov     r9, r14
0x18002d245  mov     rcx, cs:g_pDebug
0x18002d24c  mov     r8d, 300h
0x18002d252  mov     [rsp+1C0h+var_188], rax
0x18002d257  mov     rdx, r15
0x18002d25a  lea     rax, aTagmeta; "TAGMETA"
0x18002d261  mov     [rsp+1C0h+var_190], rbx
0x18002d266  mov     [rsp+1C0h+var_198], rax
0x18002d26b  lea     rax, aInitializeglob_0; "[InitializeGlobals] Reading table: %s w"...
0x18002d272  mov     [rsp+1C0h+var_1A0], rax
0x18002d277  call    cs:__imp_PuDbgPrintW
0x18002d27d  mov     rcx, [rsp+1C0h+var_168]
0x18002d282  lea     rdx, [rsi+8]
0x18002d286  mov     [rsp+1C0h+var_188], rdx
0x18002d28b  lea     r9, [rsp+1C0h+var_160]
0x18002d290  mov     [rsp+1C0h+var_148], rbx
0x18002d295  lea     rdx, [rsp+1C0h+var_170]
0x18002d29a  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002d2a1  lea     r8, aTagmeta; "TAGMETA"
0x18002d2a8  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002d2af  mov     [rbp+0C0h+var_138], 82h
0x18002d2b7  mov     rax, [rcx]
0x18002d2ba  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002d2bf  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002d2c3  mov     [rsp+1C0h+var_1A0], rdx
0x18002d2c8  lea     rdx, aMeta; "META"
0x18002d2cf  mov     rax, [rax+18h]
0x18002d2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2d8  mov     ebx, eax
0x18002d2da  test    eax, eax
0x18002d2dc  js      loc_18002D6F2
0x18002d2e2  test    byte ptr cs:g_dwDebugFlags, dil
0x18002d2e9  lea     rbx, aBytableandcolu; "ByTableAndColumnIndexOnly"
0x18002d2f0  jz      short loc_18002D331
0x18002d2f2  mov     rax, [r12]
0x18002d2f6  mov     r9, r14
0x18002d2f9  mov     rcx, cs:g_pDebug
0x18002d300  mov     r8d, 321h
0x18002d306  mov     [rsp+1C0h+var_188], rax
0x18002d30b  mov     rdx, r15
0x18002d30e  lea     rax, aTagmeta; "TAGMETA"
0x18002d315  mov     [rsp+1C0h+var_190], rbx
0x18002d31a  mov     [rsp+1C0h+var_198], rax
0x18002d31f  lea     rax, aInitializeglob_0; "[InitializeGlobals] Reading table: %s w"...
0x18002d326  mov     [rsp+1C0h+var_1A0], rax
0x18002d32b  call    cs:__imp_PuDbgPrintW
0x18002d331  mov     rcx, [rsp+1C0h+var_168]
0x18002d336  lea     rdx, [rsi+10h]
0x18002d33a  mov     [rsp+1C0h+var_188], rdx
0x18002d33f  lea     r9, [rsp+1C0h+var_160]
0x18002d344  mov     [rsp+1C0h+var_148], rbx
0x18002d349  lea     rdx, [rsp+1C0h+var_170]
0x18002d34e  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002d355  lea     r8, aTagmeta; "TAGMETA"
0x18002d35c  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002d363  mov     [rbp+0C0h+var_138], 82h
0x18002d36b  mov     rax, [rcx]
0x18002d36e  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002d373  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002d377  mov     [rsp+1C0h+var_1A0], rdx
0x18002d37c  lea     rdx, aMeta; "META"
0x18002d383  mov     rax, [rax+18h]
0x18002d387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d38c  mov     ebx, eax
0x18002d38e  test    eax, eax
0x18002d390  js      loc_18002D6F2
0x18002d396  mov     rcx, [rsp+1C0h+var_168]
0x18002d39b  lea     rax, aBytableandtagi; "ByTableAndTagIDOnly"
0x18002d3a2  mov     [rsp+1C0h+var_148], rax
0x18002d3a7  lea     rdx, [rsi+18h]
0x18002d3ab  mov     [rsp+1C0h+var_188], rdx
0x18002d3b0  lea     r9, [rsp+1C0h+var_160]
0x18002d3b5  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002d3bc  lea     rdx, [rsp+1C0h+var_170]
0x18002d3c1  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002d3c8  lea     r8, aTagmeta; "TAGMETA"
0x18002d3cf  mov     [rbp+0C0h+var_138], 82h
0x18002d3d7  mov     rax, [rcx]
0x18002d3da  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002d3df  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002d3e3  mov     [rsp+1C0h+var_1A0], rdx
0x18002d3e8  lea     rdx, aMeta; "META"
0x18002d3ef  mov     rax, [rax+18h]
0x18002d3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3f8  mov     ebx, eax
0x18002d3fa  test    eax, eax
0x18002d3fc  js      loc_18002D6F2
0x18002d402  mov     rcx, [rsp+1C0h+var_168]
0x18002d407  lea     rax, aBytableandtagn; "ByTableAndTagNameOnly"
0x18002d40e  mov     [rsp+1C0h+var_148], rax
0x18002d413  lea     rdx, [rsi+20h]
0x18002d417  mov     [rsp+1C0h+var_188], rdx
0x18002d41c  lea     r9, [rsp+1C0h+var_160]
0x18002d421  mov     dword ptr [rbp+0C0h+var_140], 2
0x18002d428  lea     rdx, [rsp+1C0h+var_170]
0x18002d42d  mov     dword ptr [rbp+0C0h+var_140+4], 0F0000004h
0x18002d434  lea     r8, aTagmeta; "TAGMETA"
0x18002d43b  mov     [rbp+0C0h+var_138], 82h
0x18002d443  mov     rax, [rcx]
0x18002d446  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002d44b  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002d44f  mov     [rsp+1C0h+var_1A0], rdx
0x18002d454  lea     rdx, aMeta; "META"
0x18002d45b  mov     rax, [rax+18h]
0x18002d45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d464  mov     ebx, eax
0x18002d466  test    eax, eax
0x18002d468  js      loc_18002D6F2
0x18002d46e  mov     rcx, [rsp+1C0h+var_168]
0x18002d473  lea     rdx, [rsi+28h]
0x18002d477  dec     [rsp+1C0h+var_170]
0x18002d47b  lea     r9, [rsp+1C0h+var_160]
0x18002d480  mov     [rsp+1C0h+var_188], rdx
0x18002d485  lea     r8, aColumnmeta; "COLUMNMETA"
0x18002d48c  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18002d491  lea     rdx, [rsp+1C0h+var_170]
0x18002d496  mov     rax, [rcx]
0x18002d499  mov     dword ptr [rsp+1C0h+var_198], edi
0x18002d49d  mov     [rsp+1C0h+var_1A0], rdx
0x18002d4a2  lea     rdx, aMeta; "META"
0x18002d4a9  mov     rax, [rax+18h]
0x18002d4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4b2  inc     [rsp+1C0h+var_170]
0x18002d4b6  mov     ebx, eax
0x18002d4b8  test    eax, eax
0x18002d4ba  js      loc_18002D6F2
0x18002d4c0  test    byte ptr cs:g_dwDebugFlags, dil
0x18002d4c7  lea     rbx, aByid; "ByID"
0x18002d4ce  jz      short loc_18002D50F
0x18002d4d0  mov     rax, [r12]
0x18002d4d4  mov     r9, r14
0x18002d4d7  mov     rcx, cs:g_pDebug
0x18002d4de  mov     r8d, 38Eh
0x18002d4e4  mov     [rsp+1C0h+var_188], rax
0x18002d4e9  mov     rdx, r15
0x18002d4ec  lea     rax, aColumnmeta; "COLUMNMETA"
0x18002d4f3  mov     [rsp+1C0h+var_190], rbx
0x18002d4f8  mov     [rsp+1C0h+var_198], rax
0x18002d4fd  lea     rax, aInitializeglob_0; "[InitializeGlobals] Reading table: %s w"...
  ... truncated ...
```
