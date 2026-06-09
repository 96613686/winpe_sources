# UnparseDatatype(String * *,tagVARIANT *,DataType)

- ea: `0x180066598`
- end: `0x1800668e4`
- name: `?UnparseDatatype@@YAJPEAPEAVString@@PEAUtagVARIANT@@W4DataType@@@Z`
- size: `844`
- prototype: `int __high(struct String **, struct tagVARIANT *, enum DataType)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180078fa4`
- `0x18009a7c0`

## callees

- `0x1800222c0`
- `0x18002d8d0`
- `0x180064034`
- `0x180065ff8`
- `0x1800661b4`
- `0x1800663e0`
- `0x180066598`
- `0x180066980`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180066814`
- `msvcrt!_resetstkoflw` at `0x180066814`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066867`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180066867`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180066802`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180066893`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180066802`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180066893`
- `OLEAUT32!__imp_VariantClear` at `0x1800668bf`
- `OLEAUT32!__imp_VariantClear` at `0x1800668bf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18006669e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18006669e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18006667f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18006667f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800666b7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800666b7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180066710`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180066710`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18006676f`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800667d4`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18006676f`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800667d4`

## pseudocode

```c
__int64 __fastcall UnparseDatatype(struct String **a1, const VARIANTARG *a2, int a3)
{
  HRESULT LBound; // ebx
  const wchar_t *bstrVal; // r14
  bool v8; // sf
  const unsigned __int16 *v9; // rcx
  HRESULT v10; // eax
  int v11; // eax
  LONG plLbound[2]; // [rsp+30h] [rbp-68h] BYREF
  struct String *v14; // [rsp+38h] [rbp-60h] BYREF
  void *ppvData[2]; // [rsp+40h] [rbp-58h] BYREF
  VARIANTARG pvargDest; // [rsp+50h] [rbp-48h] BYREF
  int v17; // [rsp+B0h] [rbp+18h] BYREF
  LONG plUbound; // [rsp+B8h] [rbp+20h] BYREF

  LBound = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  v14 = 0;
  bstrVal = 0;
  v17 = 0;
  pvargDest.vt = 1;
  if ( a3 > 17 )
  {
    switch ( a3 )
    {
      case 18:
      case 31:
      case 32:
        goto LABEL_8;
      case 38:
        *(_OWORD *)ppvData = 0;
        LBound = VariantChangeTypeEx(&pvargDest, a2, 0x409u, 1u, 8u);
        if ( LBound < 0 )
          goto LABEL_36;
        v11 = xstrlenw(pvargDest.bstrVal, 0x7FFFFFFFu);
        LBound = ParseUuid(pvargDest.bstrVal, v11, (struct _GUID *)ppvData, 0);
        if ( LBound < 0 )
          goto LABEL_36;
        bstrVal = pvargDest.bstrVal;
        break;
      case 39:
        LBound = -2147467259;
        goto LABEL_36;
    }
  }
  else
  {
    switch ( a3 )
    {
      case 17:
LABEL_8:
        LBound = UnparseISO8601(&v14, (unsigned int)a3, &a2->decVal.Lo32);
        v8 = LBound < 0;
LABEL_9:
        if ( v8 )
          goto LABEL_36;
        break;
      case 12:
      case 13:
        plLbound[0] = 0;
        plUbound = 0;
        ppvData[0] = 0;
        LBound = SafeArrayGetLBound(a2->parray, 1u, plLbound);
        if ( LBound < 0 )
          goto LABEL_36;
        LBound = SafeArrayGetUBound(a2->parray, 1u, &plUbound);
        if ( LBound < 0 )
          goto LABEL_36;
        LBound = SafeArrayAccessData(a2->parray, ppvData);
        if ( LBound < 0 )
          goto LABEL_36;
        if ( a3 == 13 )
          v10 = UnparseBinHex(&v14, (unsigned __int8 *)ppvData[0], plUbound - plLbound[0] + 1);
        else
          v10 = UnparseBase64(ppvData[0], plUbound - plLbound[0] + 1, &v14);
        LBound = v10;
        SafeArrayUnaccessData(a2->parray);
        v8 = LBound < 0;
        goto LABEL_9;
      case 14:
        bstrVal = L"1";
        if ( a2->iVal != -1 )
          bstrVal = L"0";
        break;
      case 15:
        LOWORD(v17) = a2->iVal;
        bstrVal = (const wchar_t *)&v17;
        break;
      case 16:
        goto LABEL_8;
    }
  }
  if ( bstrVal )
  {
    v9 = bstrVal;
LABEL_35:
    v14 = String::newString(v9);
    goto LABEL_36;
  }
  if ( !v14 )
  {
    LBound = VariantChangeTypeEx(&pvargDest, a2, 0x409u, 1u, 8u);
    plLbound[1] = LBound;
    if ( LBound >= 0 )
    {
      v9 = pvargDest.bstrVal;
      goto LABEL_35;
    }
  }
LABEL_36:
  VariantClear(&pvargDest);
  *a1 = v14;
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x180066598  mov     r11, rsp
0x18006659b  mov     [r11+10h], rbx
0x18006659f  mov     [r11+8], rcx
0x1800665a3  push    rsi
0x1800665a4  push    rdi
0x1800665a5  push    r13
0x1800665a7  push    r14
0x1800665a9  push    r15
0x1800665ab  sub     rsp, 70h
0x1800665af  mov     edi, r8d
0x1800665b2  mov     rsi, rdx
0x1800665b5  mov     r15, rcx
0x1800665b8  xor     ebx, ebx
0x1800665ba  xorps   xmm0, xmm0
0x1800665bd  xor     eax, eax
0x1800665bf  movups  xmmword ptr [rsp+98h+pvargDest], xmm0
0x1800665c4  mov     [r11-38h], rax
0x1800665c8  mov     [r11-60h], rax
0x1800665cc  xor     r14d, r14d
0x1800665cf  mov     [r11+18h], eax
0x1800665d3  lea     r13d, [rbx+1]
0x1800665d7  mov     [r11-48h], r13w
0x1800665dc  cmp     r8d, 11h
0x1800665e0  jg      loc_18006671D
0x1800665e6  jz      short loc_180066604
0x1800665e8  mov     ecx, r8d
0x1800665eb  sub     ecx, 0Ch
0x1800665ee  jz      short loc_180066663
0x1800665f0  sub     ecx, r13d
0x1800665f3  jz      short loc_180066663
0x1800665f5  sub     ecx, r13d
0x1800665f8  jz      short loc_18006664A
0x1800665fa  sub     ecx, r13d
0x1800665fd  jz      short loc_180066634
0x1800665ff  cmp     ecx, r13d
0x180066602  jnz     short loc_18006661E
0x180066604  lea     r8, [rdx+8]
0x180066608  mov     edx, edi
0x18006660a  lea     rcx, [rsp+98h+var_60]
0x18006660f  call    ?UnparseISO8601@@YAJPEAPEAVString@@W4DataType@@PEAN@Z; UnparseISO8601(String * *,DataType,double *)
0x180066614  mov     ebx, eax
0x180066616  test    eax, eax
0x180066618  js      loc_1800668BA
0x18006661e  mov     edi, 8
0x180066623  test    r14, r14
0x180066626  jz      loc_1800667B6
0x18006662c  mov     rcx, r14
0x18006662f  jmp     loc_1800667ED
0x180066634  movzx   eax, word ptr [rdx+8]
0x180066638  mov     word ptr [rsp+98h+arg_10], ax
0x180066640  lea     r14, [rsp+98h+arg_10]
0x180066648  jmp     short loc_18006661E
0x18006664a  lea     rax, a0; "0"
0x180066651  lea     r14, a1; "1"
0x180066658  cmp     word ptr [rdx+8], 0FFFFh
0x18006665d  cmovnz  r14, rax
0x180066661  jmp     short loc_18006661E
0x180066663  mov     [rsp+98h+plLbound], eax
0x180066667  mov     [rsp+98h+plUbound], eax
0x18006666e  mov     [rsp+98h+ppvData], rax
0x180066673  lea     r8, [rsp+98h+plLbound]; plLbound
0x180066678  mov     edx, r13d; nDim
0x18006667b  mov     rcx, [rsi+8]; psa
0x18006667f  call    cs:__imp_SafeArrayGetLBound
0x180066685  mov     ebx, eax
0x180066687  test    eax, eax
0x180066689  js      loc_1800668BA
0x18006668f  lea     r8, [rsp+98h+plUbound]; plUbound
0x180066697  mov     edx, r13d; nDim
0x18006669a  mov     rcx, [rsi+8]; psa
0x18006669e  call    cs:__imp_SafeArrayGetUBound
0x1800666a4  mov     ebx, eax
0x1800666a6  test    eax, eax
0x1800666a8  js      loc_1800668BA
0x1800666ae  lea     rdx, [rsp+98h+ppvData]; ppvData
0x1800666b3  mov     rcx, [rsi+8]; psa
0x1800666b7  call    cs:__imp_SafeArrayAccessData
0x1800666bd  mov     ebx, eax
0x1800666bf  test    eax, eax
0x1800666c1  js      loc_1800668BA
0x1800666c7  cmp     edi, 0Dh
0x1800666ca  jnz     short loc_1800666ED
0x1800666cc  mov     r8d, [rsp+98h+plUbound]
0x1800666d4  sub     r8d, [rsp+98h+plLbound]
0x1800666d9  add     r8d, r13d; int
0x1800666dc  mov     rdx, [rsp+98h+ppvData]; unsigned __int8 *
0x1800666e1  lea     rcx, [rsp+98h+var_60]; struct String **
0x1800666e6  call    ?UnparseBinHex@@YAJPEAPEAVString@@PEAEJ@Z; UnparseBinHex(String * *,uchar *,long)
0x1800666eb  jmp     short loc_18006670A
0x1800666ed  mov     edx, [rsp+98h+plUbound]
0x1800666f4  sub     edx, [rsp+98h+plLbound]
0x1800666f8  add     edx, r13d; int
0x1800666fb  lea     r8, [rsp+98h+var_60]; struct String **
0x180066700  mov     rcx, [rsp+98h+ppvData]; void *
0x180066705  call    ?UnparseBase64@@YAJPEAXHPEAPEAVString@@@Z; UnparseBase64(void *,int,String * *)
0x18006670a  mov     ebx, eax
0x18006670c  mov     rcx, [rsi+8]; psa
0x180066710  call    cs:__imp_SafeArrayUnaccessData
0x180066716  test    ebx, ebx
0x180066718  jmp     loc_180066618
0x18006671d  mov     ecx, edi
0x18006671f  sub     ecx, 12h
0x180066722  jz      loc_180066604
0x180066728  sub     ecx, 0Dh
0x18006672b  jz      loc_180066604
0x180066731  sub     ecx, r13d
0x180066734  jz      loc_180066604
0x18006673a  sub     ecx, 6
0x18006673d  jz      short loc_180066752
0x18006673f  cmp     ecx, r13d
0x180066742  jnz     loc_18006661E
0x180066748  mov     ebx, 80004005h
0x18006674d  jmp     loc_1800668BA
0x180066752  movups  xmmword ptr [rsp+98h+ppvData], xmm0
0x180066757  mov     edi, 8
0x18006675c  mov     r9d, r13d; wFlags
0x18006675f  mov     [rsp+98h+vt], di; vt
0x180066764  mov     r8d, 409h; lcid
0x18006676a  lea     rcx, [rsp+98h+pvargDest]; pvargDest
0x18006676f  call    cs:__imp_VariantChangeTypeEx
0x180066775  mov     ebx, eax
0x180066777  test    eax, eax
0x180066779  js      loc_1800668BA
0x18006677f  mov     edx, 7FFFFFFFh; unsigned __int64
0x180066784  mov     rcx, qword ptr [rsp+98h+pvargDest+8]; unsigned __int16 *
0x180066789  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x18006678e  mov     edx, eax; int
0x180066790  xor     r9d, r9d; unsigned __int16 **
0x180066793  lea     r8, [rsp+98h+ppvData]; struct _GUID *
0x180066798  mov     rcx, qword ptr [rsp+98h+pvargDest+8]; unsigned __int16 *
0x18006679d  call    ?ParseUuid@@YAJPEBGHPEAU_GUID@@PEAPEBG@Z; ParseUuid(ushort const *,int,_GUID *,ushort const * *)
0x1800667a2  mov     ebx, eax
0x1800667a4  test    eax, eax
0x1800667a6  js      loc_1800668BA
0x1800667ac  mov     r14, qword ptr [rsp+98h+pvargDest+8]
0x1800667b1  jmp     loc_180066623
0x1800667b6  cmp     [rsp+98h+var_60], 0
0x1800667bc  jnz     short loc_1800667F7
0x1800667be  mov     r9d, r13d; wFlags
0x1800667c1  mov     [rsp+98h+vt], di; vt
0x1800667c6  mov     r8d, 409h; lcid
0x1800667cc  mov     rdx, rsi; pvarSrc
0x1800667cf  lea     rcx, [rsp+98h+pvargDest]; pvargDest
0x1800667d4  call    cs:__imp_VariantChangeTypeEx
0x1800667da  mov     ebx, eax
0x1800667dc  mov     [rsp+98h+var_64], eax
0x1800667e0  test    eax, eax
0x1800667e2  js      loc_1800668BA
0x1800667e8  mov     rcx, qword ptr [rsp+98h+pvargDest+8]; unsigned __int16 *
0x1800667ed  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800667f2  mov     [rsp+98h+var_60], rax
0x1800667f7  jmp     loc_1800668BA
0x1800667fc  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180066802  call    cs:__imp_TlsGetValue
0x180066808  mov     rbx, rax
0x18006680b  cmp     dword ptr [rax+54h], 0C00000FDh
0x180066812  jnz     short loc_18006688D
0x180066814  call    cs:__imp__resetstkoflw
0x18006681a  test    eax, eax
0x18006681c  jnz     short loc_18006686F
0x18006681e  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180066825  test    rcx, rcx
0x180066828  jz      short loc_18006683C
0x18006682a  cmp     [rcx+50h], rbx
0x18006682e  jnz     short loc_18006683C
0x180066830  mov     rax, [rcx]
0x180066833  mov     rax, [rax+20h]
0x180066837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006683c  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180066843  test    rcx, rcx
0x180066846  jz      short loc_18006685A
0x180066848  cmp     [rcx+50h], rbx
0x18006684c  jnz     short loc_18006685A
0x18006684e  mov     rax, [rcx]
0x180066851  mov     rax, [rax+20h]
0x180066855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006685a  xor     r9d, r9d; lpArguments
0x18006685d  xor     r8d, r8d; nNumberOfArguments
0x180066860  xor     edx, edx; dwExceptionFlags
0x180066862  mov     ecx, 0C00000FDh; dwExceptionCode
0x180066867  call    cs:__imp_RaiseException
0x18006686d  jmp     short loc_18006688D
0x18006686f  mov     rax, [rbx+60h]
0x180066873  mov     [rbx+68h], rax
0x180066877  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x18006687e  mov     [rbx+60h], rax
0x180066882  mov     dword ptr [rbx+54h], 800703E9h
0x180066889  mov     byte ptr [rbx+78h], 0
0x18006688d  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180066893  call    cs:__imp_TlsGetValue
0x180066899  mov     rcx, [rax+60h]
0x18006689d  mov     rax, [rcx]
0x1800668a0  mov     rax, [rax+80h]
0x1800668a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668ac  mov     ebx, eax
0x1800668ae  mov     [rsp+98h+var_64], eax
0x1800668b2  mov     r15, [rsp+98h+arg_0]
0x1800668ba  lea     rcx, [rsp+98h+pvargDest]; pvarg
0x1800668bf  call    cs:__imp_VariantClear
0x1800668c5  mov     rax, [rsp+98h+var_60]
0x1800668ca  mov     [r15], rax
0x1800668cd  mov     eax, ebx
0x1800668cf  mov     rbx, [rsp+98h+arg_8]
0x1800668d7  add     rsp, 70h
0x1800668db  pop     r15
0x1800668dd  pop     r14
0x1800668df  pop     r13
0x1800668e1  pop     rdi
0x1800668e2  pop     rsi
0x1800668e3  retn
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
```
