# GetQueueNameFromDevice(_INIPRINTER *,void *,int)

- ea: `0x1800c003c`
- end: `0x1800c03dd`
- name: `?GetQueueNameFromDevice@@YAXPEAU_INIPRINTER@@PEAXH@Z`
- size: `929`
- prototype: `void __fastcall(struct _INIPRINTER *, void *, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting`

## callers

- `0x18004fe9c`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18000c380`
- `0x18000edc4`
- `0x180011e64`
- `0x180011e98`
- `0x180011ed0`
- `0x18002fda0`
- `0x18002fdcc`
- `0x18003e984`
- `0x18004531c`
- `0x180046650`
- `0x180046aa0`
- `0x1800547a4`
- `0x18005a810`
- `0x18005c3c0`
- `0x1800bfe20`
- `0x1800c003c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c024d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c024d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800c02e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800c02e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c017b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c017b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0200`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800c00e1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800c00e1`
- `SPOOLSS!DllFreeSplMem` at `0x1800c03ac`
- `SPOOLSS!DllFreeSplMem` at `0x1800c03ac`
- `SPOOLSS!DllAllocSplMem` at `0x1800c018e`
- `SPOOLSS!DllAllocSplMem` at `0x1800c018e`

## string_xrefs

- `0x1800c0246`: `printui.dll`
- `0x1800c0077`: `Attempting to retrieve queue name from device`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GetQueueNameFromDevice(struct _INIPRINTER *a1, void *a2, int a3)
{
  __int64 v6; // rsi
  unsigned int v7; // r8d
  int QueueNameFromBidi; // edi
  unsigned int v9; // r8d
  __int64 v10; // rcx
  WCHAR *v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  HMODULE Library; // rax
  void *v15; // rax
  void *v16; // rax
  void *v17; // rax
  const unsigned __int16 *v18; // r15
  unsigned __int16 *v19; // rdi
  unsigned int v20; // r14d
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v23; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR lpBuffer; // [rsp+48h] [rbp-B8h] BYREF
  HINSTANCE hInstance[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszFirst[264]; // [rsp+60h] [rbp-A0h] BYREF

  LocalSpoolerTelemetry::WriteDbgTraceInfo("GetQueueNameFromDevice", L"Attempting to retrieve queue name from device");
  v21 = 0;
  v6 = 0;
  QueueNameFromBidi = GetQueueNameFromBidi(a1, pszFirst, v7);
  if ( !QueueNameFromBidi )
    QueueNameFromBidi = GetQueueNameFrom1284(a1, pszFirst, v9);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl'::`2'::impl) )
  {
    if ( !QueueNameFromBidi )
      goto LABEL_15;
    if ( a3 && !StrStrIW(pszFirst, L"fax") )
      StringCchCatW(pszFirst, 0x104u, L" (FAX)");
  }
  else if ( !QueueNameFromBidi )
  {
    goto LABEL_15;
  }
  v11 = pszFirst;
  v12 = *((_QWORD *)a1 + 3) - (_QWORD)pszFirst;
  while ( 1 )
  {
    v10 = *v11;
    if ( (_WORD)v10 != *(WCHAR *)((char *)v11 + v12) )
      break;
    ++v11;
    if ( !(_WORD)v10 )
    {
      v13 = 0;
      goto LABEL_14;
    }
  }
  v13 = (unsigned __int16)v10 < *(WCHAR *)((char *)v11 + v12) ? -1 : 1;
LABEL_14:
  QueueNameFromBidi = v13 != 0 ? QueueNameFromBidi : 0;
LABEL_15:
  if ( a1 && SafeIncrementReference((unsigned int *)a1 + 4) > *((_DWORD *)a1 + 62) )
    *((_DWORD *)a1 + 62) = *((_DWORD *)a1 + 4);
  LeaveSplSem(v10);
  if ( QueueNameFromBidi )
  {
    SplGetPrinter((_DWORD)a2, 2, 0, 0, (char)&v21);
    if ( GetLastError() == 122 )
    {
      v6 = DllAllocSplMem(v21);
      if ( v6 )
      {
        if ( (unsigned int)SplGetPrinter((_DWORD)a2, 2, v6, v21, (char)&v21) )
        {
          *(_QWORD *)(v6 + 8) = pszFirst;
          if ( (unsigned int)SplSetPrinter(a2, 2, v6, 0) )
          {
            LocalSpoolerTelemetry::WriteDbgTraceInfo("GetQueueNameFromDevice", L"New queue name: %ws", pszFirst);
          }
          else if ( GetLastError() == 1802 )
          {
            hInstance[0] = 0;
            NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(&lpBuffer, 0);
            NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(&v22, 0);
            NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(&v23, 0);
            Library = LoadLibraryExW(L"printui.dll", 0, 2u);
            if ( NCoreLibrary::TAutoHandleHMODULE::operator=(hInstance, Library) )
            {
              v15 = operator new[](0x410u);
              NCoreLibrary::TAutoPtrArray<unsigned long>::operator=(&lpBuffer, v15);
              v16 = operator new[](0x410u);
              NCoreLibrary::TAutoPtrArray<unsigned long>::operator=(&v22, v16);
              v17 = operator new[](0x410u);
              NCoreLibrary::TAutoPtrArray<unsigned long>::operator=(&v23, v17);
            }
            v18 = lpBuffer;
            if ( lpBuffer )
            {
              if ( v22 )
              {
                v19 = v23;
                if ( v23 )
                {
                  if ( LoadStringW(hInstance[0], 0x4A38u, lpBuffer, 520) )
                  {
                    *(_QWORD *)(v6 + 8) = v19;
                    v20 = 1;
                    while ( StringCchPrintfW(v22, 0x208u, v18, v20) < 0
                         || StringCchPrintfW(v19, 0x208u, v22, pszFirst) < 0
                         || !(unsigned int)SplSetPrinter(a2, 2, v6, 0) )
                    {
                      if ( ++v20 >= 0x3E8 )
                        goto LABEL_38;
                    }
                    LocalSpoolerTelemetry::WriteDbgTraceInfo("GetQueueNameFromDevice", L"New queue name: %ws", v19);
                  }
                }
              }
            }
LABEL_38:
            NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v23);
            NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v22);
            NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&lpBuffer);
            NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(hInstance);
          }
        }
      }
    }
  }
  EnterSplSem(0);
  if ( a1 && *((_DWORD *)a1 + 4) )
    SafeDecrementReference((unsigned int *)a1 + 4);
  DllFreeSplMem(v6);
}

```

## disassembly

```asm
0x1800c003c  mov     [rsp-8+arg_10], rbx
0x1800c0041  mov     [rsp-8+arg_18], rsi
0x1800c0046  push    rbp
0x1800c0047  push    rdi
0x1800c0048  push    r13
0x1800c004a  push    r14
0x1800c004c  push    r15
0x1800c004e  lea     rbp, [rsp-180h]
0x1800c0056  sub     rsp, 280h
0x1800c005d  mov     rax, cs:__security_cookie
0x1800c0064  xor     rax, rsp
0x1800c0067  mov     [rbp+1A0h+var_30], rax
0x1800c006e  mov     r14d, r8d
0x1800c0071  mov     r13, rdx
0x1800c0074  mov     rbx, rcx
0x1800c0077  lea     rdx, aAttemptingToRe; "Attempting to retrieve queue name from "...
0x1800c007e  lea     rcx, aGetqueuenamefr_0; "GetQueueNameFromDevice"
0x1800c0085  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c008a  mov     [rsp+2A0h+var_270], 0
0x1800c0092  xor     esi, esi
0x1800c0094  lea     rdx, [rsp+2A0h+pszFirst]; unsigned __int16 *
0x1800c0099  mov     rcx, rbx; struct _INIPRINTER *
0x1800c009c  call    ?GetQueueNameFromBidi@@YAHPEAU_INIPRINTER@@PEAGK@Z; GetQueueNameFromBidi(_INIPRINTER *,ushort *,ulong)
0x1800c00a1  mov     edi, eax
0x1800c00a3  test    eax, eax
0x1800c00a5  jnz     short loc_1800C00B6
0x1800c00a7  lea     rdx, [rsp+2A0h+pszFirst]; unsigned __int16 *
0x1800c00ac  mov     rcx, rbx; struct _INIPRINTER *
0x1800c00af  call    ?GetQueueNameFrom1284@@YAHPEAU_INIPRINTER@@PEAGK@Z; GetQueueNameFrom1284(_INIPRINTER *,ushort *,ulong)
0x1800c00b4  mov     edi, eax
0x1800c00b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::GetImpl(void)'::`2'::impl
0x1800c00bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave2>::__private_IsEnabled(void)
0x1800c00c2  mov     r15d, 2
0x1800c00c8  test    al, al
0x1800c00ca  jz      short loc_1800C0104
0x1800c00cc  test    edi, edi
0x1800c00ce  jz      short loc_1800C0134
0x1800c00d0  test    r14d, r14d
0x1800c00d3  jz      short loc_1800C0108
0x1800c00d5  lea     rdx, pszSrch; "fax"
0x1800c00dc  lea     rcx, [rsp+2A0h+pszFirst]; pszFirst
0x1800c00e1  call    cs:__imp_StrStrIW
0x1800c00e7  test    rax, rax
0x1800c00ea  jnz     short loc_1800C0108
0x1800c00ec  lea     r8, aFax; " (FAX)"
0x1800c00f3  mov     edx, 104h; unsigned __int64
0x1800c00f8  lea     rcx, [rsp+2A0h+pszFirst]; unsigned __int16 *
0x1800c00fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c0102  jmp     short loc_1800C0108
0x1800c0104  test    edi, edi
0x1800c0106  jz      short loc_1800C0134
0x1800c0108  lea     rax, [rsp+2A0h+pszFirst]
0x1800c010d  mov     rdx, [rbx+18h]
0x1800c0111  sub     rdx, rax
0x1800c0114  movzx   ecx, word ptr [rax]
0x1800c0117  cmp     cx, [rax+rdx]
0x1800c011b  jnz     short loc_1800C0129
0x1800c011d  add     rax, r15
0x1800c0120  test    cx, cx
0x1800c0123  jnz     short loc_1800C0114
0x1800c0125  xor     eax, eax
0x1800c0127  jmp     short loc_1800C012E
0x1800c0129  sbb     eax, eax
0x1800c012b  or      eax, 1
0x1800c012e  neg     eax
0x1800c0130  sbb     eax, eax
0x1800c0132  and     edi, eax
0x1800c0134  test    rbx, rbx
0x1800c0137  jz      short loc_1800C0153
0x1800c0139  lea     rcx, [rbx+10h]; unsigned int *
0x1800c013d  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x1800c0142  cmp     eax, [rbx+0F8h]
0x1800c0148  jbe     short loc_1800C0153
0x1800c014a  mov     eax, [rbx+10h]
0x1800c014d  mov     [rbx+0F8h], eax
0x1800c0153  call    LeaveSplSem
0x1800c0158  test    edi, edi
0x1800c015a  jz      loc_1800C038F
0x1800c0160  lea     rax, [rsp+2A0h+var_270]
0x1800c0165  mov     [rsp+2A0h+var_280], rax
0x1800c016a  xor     r9d, r9d
0x1800c016d  xor     r8d, r8d
0x1800c0170  mov     edx, r15d
0x1800c0173  mov     rcx, r13
0x1800c0176  call    SplGetPrinter
0x1800c017b  call    cs:__imp_GetLastError
0x1800c0181  cmp     eax, 7Ah ; 'z'
0x1800c0184  jnz     loc_1800C038F
0x1800c018a  mov     ecx, [rsp+2A0h+var_270]
0x1800c018e  call    cs:__imp_DllAllocSplMem
0x1800c0194  mov     rsi, rax
0x1800c0197  test    rax, rax
0x1800c019a  jz      loc_1800C038F
0x1800c01a0  lea     rax, [rsp+2A0h+var_270]
0x1800c01a5  mov     [rsp+2A0h+var_280], rax
0x1800c01aa  mov     r9d, [rsp+2A0h+var_270]
0x1800c01af  mov     r8, rsi
0x1800c01b2  mov     edx, r15d
0x1800c01b5  mov     rcx, r13
0x1800c01b8  call    SplGetPrinter
0x1800c01bd  test    eax, eax
0x1800c01bf  jz      loc_1800C038F
0x1800c01c5  lea     rax, [rsp+2A0h+pszFirst]
0x1800c01ca  mov     [rsi+8], rax
0x1800c01ce  xor     r9d, r9d
0x1800c01d1  mov     r8, rsi
0x1800c01d4  mov     edx, r15d
0x1800c01d7  mov     rcx, r13
0x1800c01da  call    SplSetPrinter
0x1800c01df  test    eax, eax
0x1800c01e1  jz      short loc_1800C0200
0x1800c01e3  lea     r8, [rsp+2A0h+pszFirst]
0x1800c01e8  lea     rdx, aNewQueueNameWs; "New queue name: %ws"
0x1800c01ef  lea     rcx, aGetqueuenamefr_0; "GetQueueNameFromDevice"
0x1800c01f6  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c01fb  jmp     loc_1800C038F
0x1800c0200  call    cs:__imp_GetLastError
0x1800c0206  cmp     eax, 70Ah
0x1800c020b  jnz     loc_1800C038F
0x1800c0211  mov     [rsp+2A0h+hInstance], 0
0x1800c021a  xor     edx, edx
0x1800c021c  lea     rcx, [rsp+2A0h+lpBuffer]
0x1800c0221  call    ??0?$TAutoPtrArray@UPrintNamedProperty@@@NCoreLibrary@@QEAA@PEAUPrintNamedProperty@@@Z; NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(PrintNamedProperty *)
0x1800c0226  nop
0x1800c0227  xor     edx, edx
0x1800c0229  lea     rcx, [rsp+2A0h+var_268]
0x1800c022e  call    ??0?$TAutoPtrArray@UPrintNamedProperty@@@NCoreLibrary@@QEAA@PEAUPrintNamedProperty@@@Z; NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(PrintNamedProperty *)
0x1800c0233  nop
0x1800c0234  xor     edx, edx
0x1800c0236  lea     rcx, [rsp+2A0h+var_260]
0x1800c023b  call    ??0?$TAutoPtrArray@UPrintNamedProperty@@@NCoreLibrary@@QEAA@PEAUPrintNamedProperty@@@Z; NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(PrintNamedProperty *)
0x1800c0240  nop
0x1800c0241  mov     r8d, r15d; dwFlags
0x1800c0244  xor     edx, edx; hFile
0x1800c0246  lea     rcx, aPrintuiDll; "printui.dll"
0x1800c024d  call    cs:__imp_LoadLibraryExW
0x1800c0253  mov     rdx, rax
0x1800c0256  lea     rcx, [rsp+2A0h+hInstance]
0x1800c025b  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x1800c0260  test    rax, rax
0x1800c0263  jz      short loc_1800C02A6
0x1800c0265  mov     edi, 410h
0x1800c026a  mov     ecx, edi; unsigned __int64
0x1800c026c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c0271  mov     rdx, rax
0x1800c0274  lea     rcx, [rsp+2A0h+lpBuffer]
0x1800c0279  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x1800c027e  mov     ecx, edi; unsigned __int64
0x1800c0280  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c0285  mov     rdx, rax
0x1800c0288  lea     rcx, [rsp+2A0h+var_268]
0x1800c028d  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x1800c0292  mov     ecx, edi; unsigned __int64
0x1800c0294  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c0299  mov     rdx, rax
0x1800c029c  lea     rcx, [rsp+2A0h+var_260]
0x1800c02a1  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x1800c02a6  mov     r15, [rsp+2A0h+lpBuffer]
0x1800c02ab  test    r15, r15
0x1800c02ae  jz      loc_1800C0364
0x1800c02b4  cmp     [rsp+2A0h+var_268], 0
0x1800c02ba  jz      loc_1800C0364
0x1800c02c0  mov     rdi, [rsp+2A0h+var_260]
0x1800c02c5  test    rdi, rdi
0x1800c02c8  jz      loc_1800C0364
0x1800c02ce  mov     r9d, 208h; cchBufferMax
0x1800c02d4  mov     r8, r15; lpBuffer
0x1800c02d7  mov     edx, 4A38h; uID
0x1800c02dc  mov     rcx, [rsp+2A0h+hInstance]; hInstance
0x1800c02e1  call    cs:__imp_LoadStringW
0x1800c02e7  test    eax, eax
0x1800c02e9  jz      short loc_1800C0364
0x1800c02eb  mov     [rsi+8], rdi
0x1800c02ef  mov     r14d, 1
0x1800c02f5  mov     r9d, r14d
0x1800c02f8  mov     r8, r15; unsigned __int16 *
0x1800c02fb  mov     edx, 208h; unsigned __int64
0x1800c0300  mov     rcx, [rsp+2A0h+var_268]; unsigned __int16 *
0x1800c0305  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c030a  test    eax, eax
0x1800c030c  js      short loc_1800C033F
0x1800c030e  lea     r9, [rsp+2A0h+pszFirst]
0x1800c0313  mov     r8, [rsp+2A0h+var_268]; unsigned __int16 *
0x1800c0318  mov     edx, 208h; unsigned __int64
0x1800c031d  mov     rcx, rdi; unsigned __int16 *
0x1800c0320  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c0325  test    eax, eax
0x1800c0327  js      short loc_1800C033F
0x1800c0329  xor     r9d, r9d
0x1800c032c  mov     r8, rsi
0x1800c032f  lea     edx, [r9+2]
0x1800c0333  mov     rcx, r13
0x1800c0336  call    SplSetPrinter
0x1800c033b  test    eax, eax
0x1800c033d  jnz     short loc_1800C034D
0x1800c033f  inc     r14d
0x1800c0342  cmp     r14d, 3E8h
0x1800c0349  jb      short loc_1800C02F5
0x1800c034b  jmp     short loc_1800C0364
0x1800c034d  mov     r8, rdi
0x1800c0350  lea     rdx, aNewQueueNameWs; "New queue name: %ws"
0x1800c0357  lea     rcx, aGetqueuenamefr_0; "GetQueueNameFromDevice"
0x1800c035e  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800c0363  nop
0x1800c0364  lea     rcx, [rsp+2A0h+var_260]
0x1800c0369  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x1800c036e  nop
0x1800c036f  lea     rcx, [rsp+2A0h+var_268]
0x1800c0374  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x1800c0379  nop
0x1800c037a  lea     rcx, [rsp+2A0h+lpBuffer]
0x1800c037f  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x1800c0384  nop
0x1800c0385  lea     rcx, [rsp+2A0h+hInstance]
0x1800c038a  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x1800c038f  xor     ecx, ecx
0x1800c0391  call    EnterSplSem
0x1800c0396  test    rbx, rbx
0x1800c0399  jz      short loc_1800C03A9
0x1800c039b  lea     rcx, [rbx+10h]; unsigned int *
0x1800c039f  cmp     dword ptr [rcx], 0
0x1800c03a2  jz      short loc_1800C03A9
0x1800c03a4  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800c03a9  mov     rcx, rsi
0x1800c03ac  call    cs:__imp_DllFreeSplMem
0x1800c03b2  mov     rcx, [rbp+1A0h+var_30]
0x1800c03b9  xor     rcx, rsp; StackCookie
0x1800c03bc  call    __security_check_cookie
0x1800c03c1  lea     r11, [rsp+2A0h+var_20]
0x1800c03c9  mov     rbx, [r11+40h]
0x1800c03cd  mov     rsi, [r11+48h]
0x1800c03d1  mov     rsp, r11
0x1800c03d4  pop     r15
0x1800c03d6  pop     r14
0x1800c03d8  pop     r13
0x1800c03da  pop     rdi
0x1800c03db  pop     rbp
0x1800c03dc  retn
```
