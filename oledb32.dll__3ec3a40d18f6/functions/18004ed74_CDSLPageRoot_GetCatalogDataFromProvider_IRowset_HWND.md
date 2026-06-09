# CDSLPageRoot::GetCatalogDataFromProvider(IRowset *,HWND__ *)

- ea: `0x18004ed74`
- end: `0x18004f197`
- name: `?GetCatalogDataFromProvider@CDSLPageRoot@@IEAAJPEAUIRowset@@PEAUHWND__@@@Z`
- size: `1059`
- prototype: `int(CDSLPageRoot *__hidden this, struct IRowset *, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18004f1a0`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x18004ed74`
- `0x18007e6ca`
- `0x180087010`

## import_xrefs

- `MSDART!mpMalloc` at `0x18004edd8`
- `MSDART!mpMalloc` at `0x18004edd8`
- `MSDART!mpFree` at `0x18004f117`
- `MSDART!mpFree` at `0x18004f117`
- `USER32!SetWindowTextW` at `0x18004f0f7`
- `USER32!SetWindowTextW` at `0x18004f0f7`
- `USER32!GetWindowTextW` at `0x18004ee68`
- `USER32!GetWindowTextW` at `0x18004ee68`
- `USER32!GetWindowTextLengthW` at `0x18004edc6`
- `USER32!GetWindowTextLengthW` at `0x18004edc6`
- `USER32!SendMessageW` at `0x18004f0ab`
- `USER32!SendMessageW` at `0x18004f0ab`
- `ole32!CoTaskMemFree` at `0x18004f0b6`
- `ole32!CoTaskMemFree` at `0x18004f0b6`

## pseudocode

```c
__int64 __fastcall CDSLPageRoot::GetCatalogDataFromProvider(CDSLPageRoot *this, struct IRowset *a2, HWND a3)
{
  int WindowTextLengthW; // esi
  __int64 v6; // rdx
  WCHAR *v7; // rax
  WCHAR *v8; // rdi
  int v9; // ebx
  int v10; // esi
  int v11; // esi
  __int64 v12; // rdx
  int v13; // esi
  __int64 v14; // r8
  LPARAM v15; // r9
  __int64 result; // rax
  int pExceptionObject; // [rsp+40h] [rbp-E8h] BYREF
  int v18; // [rsp+44h] [rbp-E4h] BYREF
  int v19; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-D8h] BYREF
  LPARAM lParam[2]; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+70h] [rbp-B8h] BYREF
  __int64 *v24; // [rsp+78h] [rbp-B0h] BYREF
  int v25; // [rsp+80h] [rbp-A8h] BYREF
  void *v26; // [rsp+88h] [rbp-A0h]
  WCHAR *v27; // [rsp+90h] [rbp-98h]
  _QWORD v28[7]; // [rsp+A0h] [rbp-88h] BYREF
  int v29; // [rsp+D8h] [rbp-50h]
  __int16 v30; // [rsp+F4h] [rbp-34h]
  int v31; // [rsp+130h] [rbp+8h]
  __int64 v32; // [rsp+148h] [rbp+20h] BYREF

  v32 = 0;
  v20 = 0;
  v22 = 0;
  v23 = 0;
  v24 = &v23;
  v26 = 0;
  *(_OWORD *)lParam = 0;
  WindowTextLengthW = GetWindowTextLengthW(a3);
  v7 = (WCHAR *)mpMalloc((unsigned int)(2 * WindowTextLengthW + 2), v6);
  try
  {
    v8 = v7;
    v27 = v7;
    if ( !v7 )
    {
      v9 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024882, L"<CDSLPageRoot::GetCatalogDataFromProvider|OLEDB|ERR> ", 0x1D1u);
        if ( (bidGblFlags & 2) != 0 )
          v9 = bidTraceHR(
                 off_1800C83D8[0],
                 476169,
                 L"<CDSLPageRoot::GetCatalogDataFromProvider|Trace|HR> ",
                 2147942414LL);
      }
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
    memset_0(v7, 0, (unsigned int)(2 * WindowTextLengthW + 2));
    if ( WindowTextLengthW )
      GetWindowTextW(a3, v8, WindowTextLengthW + 1);
    v10 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IAccessor,
            &v32);
    if ( v10 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v10, L"<CDSLPageRoot::GetCatalogDataFromProvider|OLEDB|ERR> ", 0x1DDu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v10, L"<CDSLPageRoot::GetCatalogDataFromProvider|OLEDB|ERR> ", 0x1DDu);
          if ( (bidGblFlags & 2) != 0 )
            v10 = bidTraceHR(
                    off_1800C83D8[0],
                    488457,
                    L"<CDSLPageRoot::GetCatalogDataFromProvider|Trace|HR> ",
                    (unsigned int)v10);
        }
      }
      v18 = v10;
      throw (long *)&v18;
    }
    memset_0(v28, 0, 0x58u);
    v28[0] = 1;
    v28[1] = 8;
    v28[3] = 0;
    v29 = 5;
    v30 = 16514;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD *, __int64, __int64 *, _QWORD))(*(_QWORD *)v32 + 32LL))(
            v32,
            2,
            1,
            v28,
            16,
            &v20,
            0);
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v11, L"<CDSLPageRoot::GetCatalogDataFromProvider|OLEDB|ERR> ", 0x1ECu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v11, L"<CDSLPageRoot::GetCatalogDataFromProvider|OLEDB|ERR> ", 0x1ECu);
          if ( (bidGblFlags & 2) != 0 )
            v11 = bidTraceHR(
                    off_1800C83D8[0],
                    503817,
                    L"<CDSLPageRoot::GetCatalogDataFromProvider|Trace|HR> ",
                    (unsigned int)v11);
        }
      }
      v19 = v11;
      throw (long *)&v19;
    }
    do
    {
      v13 = ((__int64 (__fastcall *)(struct IRowset *, _QWORD, _QWORD, __int64, __int64 *, __int64 **))a2->lpVtbl->GetNextRows)(
              a2,
              0,
              0,
              1,
              &v22,
              &v24);
      if ( !v22 )
        break;
      v13 = ((__int64 (__fastcall *)(struct IRowset *, __int64, __int64, LPARAM *))a2->lpVtbl->GetData)(
              a2,
              v23,
              v20,
              lParam);
      ((void (__fastcall *)(struct IRowset *, __int64, __int64 *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->ReleaseRows)(
        a2,
        1,
        v24,
        0,
        0,
        0);
      if ( v13 < 0 || LODWORD(lParam[0]) || (v15 = lParam[1]) == 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v13, L"<CDSLPageRoot::GetCatalogDataFromProvider|OLEDB|ERR> ", 0x202u);
      }
      else
      {
        SendMessageW(a3, 0x143u, 0, lParam[1]);
        CoTaskMemFree((LPVOID)lParam[1]);
        lParam[1] = 0;
      }
    }
    while ( v13 != 265926 );
    if ( *v8 )
      SetWindowTextW(a3, v8);
  }
  catch ( long v25 )
  {
    v31 = v25;
    operator delete(v26);
    if ( lParam[1] )
      CoTaskMemFree((LPVOID)lParam[1]);
    v8 = v27;
    v13 = v31;
    if ( v27 )
      goto LABEL_32;
LABEL_33:
    if ( v20 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v32 + 48LL))(v32, v20, 0);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( (bidGblFlags & 2) != 0 )
      v13 = bidTraceHR(
              off_1800C83D8[0],
              562185,
              L"<CDSLPageRoot::GetCatalogDataFromProvider|Trace|HR> ",
              (unsigned int)v13);
    result = (unsigned int)v13;
  }
LABEL_32:
  mpFree(v8, v12, v14, v15);
  goto LABEL_33;
}

```

## disassembly

```asm
0x18004ed74  mov     rax, rsp
0x18004ed77  mov     [rax+10h], rbx
0x18004ed7b  mov     [rax+8], rcx
0x18004ed7f  push    rsi
0x18004ed80  push    rdi
0x18004ed81  push    r12
0x18004ed83  push    r14
0x18004ed85  push    r15
0x18004ed87  sub     rsp, 100h
0x18004ed8e  mov     r15, r8
0x18004ed91  mov     r14, rdx
0x18004ed94  xor     ebx, ebx
0x18004ed96  mov     [rax+20h], rbx
0x18004ed9a  mov     [rsp+128h+var_D8], rbx
0x18004ed9f  mov     [rsp+128h+var_C0], rbx
0x18004eda4  mov     [rsp+128h+var_B8], rbx
0x18004eda9  lea     rax, [rsp+128h+var_B8]
0x18004edae  mov     [rsp+128h+var_B0], rax
0x18004edb3  mov     [rsp+128h+var_A0], rbx
0x18004edbb  xorps   xmm0, xmm0
0x18004edbe  movups  xmmword ptr [rsp+128h+lParam], xmm0
0x18004edc3  mov     rcx, r8; hWnd
0x18004edc6  call    cs:__imp_GetWindowTextLengthW
0x18004edcc  mov     esi, eax
0x18004edce  lea     ecx, ds:2[rax*2]
0x18004edd5  mov     r12d, ecx
0x18004edd8  call    cs:__imp_mpMalloc
0x18004edde  mov     rdi, rax
0x18004ede1  mov     [rsp+128h+var_98], rax
0x18004ede9  test    rax, rax
0x18004edec  jnz     short loc_18004EE4D
0x18004edee  mov     eax, cs:_bidGblFlags
0x18004edf4  mov     ebx, 8007000Eh
0x18004edf9  test    al, 2
0x18004edfb  jz      short loc_18004EE38
0x18004edfd  mov     r8d, 1D1h; unsigned int
0x18004ee03  lea     rdx, aCdslpagerootGe_1; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004ee0a  mov     ecx, ebx; int
0x18004ee0c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004ee11  mov     eax, cs:_bidGblFlags
0x18004ee17  test    al, 2
0x18004ee19  jz      short loc_18004EE38
0x18004ee1b  mov     r9d, ebx
0x18004ee1e  lea     r8, aCdslpagerootGe_0; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004ee25  mov     edx, 74409h
0x18004ee2a  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004ee31  call    _bidTraceHR
0x18004ee36  mov     ebx, eax
0x18004ee38  mov     [rsp+128h+pExceptionObject], ebx
0x18004ee3c  lea     rdx, _TI1J; pThrowInfo
0x18004ee43  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18004ee48  call    _CxxThrowException_0
0x18004ee4d  mov     r8, r12; Size
0x18004ee50  xor     edx, edx; Val
0x18004ee52  mov     rcx, rdi; void *
0x18004ee55  call    memset_0
0x18004ee5a  test    esi, esi
0x18004ee5c  jz      short loc_18004EE6E
0x18004ee5e  lea     r8d, [rsi+1]; nMaxCount
0x18004ee62  mov     rdx, rdi; lpString
0x18004ee65  mov     rcx, r15; hWnd
0x18004ee68  call    cs:__imp_GetWindowTextW
0x18004ee6e  mov     rax, [r14]
0x18004ee71  lea     r8, [rsp+128h+arg_18]
0x18004ee79  lea     rdx, IID_IAccessor
0x18004ee80  mov     rcx, r14
0x18004ee83  mov     rax, [rax]
0x18004ee86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee8b  mov     esi, eax
0x18004ee8d  test    eax, eax
0x18004ee8f  jns     short loc_18004EF09
0x18004ee91  mov     eax, cs:_bidGblFlags
0x18004ee97  test    al, 2
0x18004ee99  jz      short loc_18004EEF4
0x18004ee9b  mov     r8d, 1DDh; unsigned int
0x18004eea1  lea     rdx, aCdslpagerootGe_1; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004eea8  mov     ecx, esi; int
0x18004eeaa  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004eeaf  mov     eax, cs:_bidGblFlags
0x18004eeb5  test    al, 2
0x18004eeb7  jz      short loc_18004EEF4
0x18004eeb9  mov     r8d, 1DDh; unsigned int
0x18004eebf  lea     rdx, aCdslpagerootGe_1; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004eec6  mov     ecx, esi; int
0x18004eec8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004eecd  mov     eax, cs:_bidGblFlags
0x18004eed3  test    al, 2
0x18004eed5  jz      short loc_18004EEF4
0x18004eed7  mov     r9d, esi
0x18004eeda  lea     r8, aCdslpagerootGe_0; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004eee1  mov     edx, 77409h
0x18004eee6  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004eeed  call    _bidTraceHR
0x18004eef2  mov     esi, eax
0x18004eef4  mov     [rsp+128h+var_E4], esi
0x18004eef8  lea     rdx, _TI1J; pThrowInfo
0x18004eeff  lea     rcx, [rsp+128h+var_E4]; pExceptionObject
0x18004ef04  call    _CxxThrowException_0
0x18004ef09  xor     edx, edx; Val
0x18004ef0b  lea     r8d, [rdx+58h]; Size
0x18004ef0f  lea     rcx, [rsp+128h+var_88]; void *
0x18004ef17  call    memset_0
0x18004ef1c  mov     r12d, 1
0x18004ef22  mov     [rsp+128h+var_88], r12
0x18004ef2a  mov     [rsp+128h+var_80], 8
0x18004ef36  mov     [rsp+128h+var_70], rbx
0x18004ef3e  mov     [rsp+128h+var_50], 5
0x18004ef49  mov     eax, 4082h
0x18004ef4e  mov     [rsp+128h+var_34], ax
0x18004ef56  mov     rcx, [rsp+128h+arg_18]
0x18004ef5e  mov     rax, [rcx]
0x18004ef61  mov     [rsp+128h+var_F8], rbx
0x18004ef66  lea     rdx, [rsp+128h+var_D8]
0x18004ef6b  mov     [rsp+128h+var_100], rdx
0x18004ef70  mov     [rsp+128h+var_108], 10h
0x18004ef79  lea     r9, [rsp+128h+var_88]
0x18004ef81  mov     r8d, r12d
0x18004ef84  lea     edx, [r12+1]
0x18004ef89  mov     rax, [rax+20h]
0x18004ef8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef92  mov     esi, eax
0x18004ef94  test    eax, eax
0x18004ef96  jns     short loc_18004F010
0x18004ef98  mov     eax, cs:_bidGblFlags
0x18004ef9e  test    al, 2
0x18004efa0  jz      short loc_18004EFFB
0x18004efa2  mov     r8d, 1ECh; unsigned int
0x18004efa8  lea     rdx, aCdslpagerootGe_1; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004efaf  mov     ecx, esi; int
0x18004efb1  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004efb6  mov     eax, cs:_bidGblFlags
0x18004efbc  test    al, 2
0x18004efbe  jz      short loc_18004EFFB
0x18004efc0  mov     r8d, 1ECh; unsigned int
0x18004efc6  lea     rdx, aCdslpagerootGe_1; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004efcd  mov     ecx, esi; int
0x18004efcf  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004efd4  mov     eax, cs:_bidGblFlags
0x18004efda  test    al, 2
0x18004efdc  jz      short loc_18004EFFB
0x18004efde  mov     r9d, esi
0x18004efe1  lea     r8, aCdslpagerootGe_0; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004efe8  mov     edx, 7B009h
0x18004efed  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004eff4  call    _bidTraceHR
0x18004eff9  mov     esi, eax
0x18004effb  mov     [rsp+128h+var_E0], esi
0x18004efff  lea     rdx, _TI1J; pThrowInfo
0x18004f006  lea     rcx, [rsp+128h+var_E0]; pExceptionObject
0x18004f00b  call    _CxxThrowException_0
0x18004f010  mov     rax, [r14]
0x18004f013  lea     rcx, [rsp+128h+var_B0]
0x18004f018  mov     [rsp+128h+var_100], rcx
0x18004f01d  lea     rcx, [rsp+128h+var_C0]
0x18004f022  mov     [rsp+128h+var_108], rcx
0x18004f027  mov     r9, r12
0x18004f02a  xor     r8d, r8d
0x18004f02d  xor     edx, edx
0x18004f02f  mov     rcx, r14
0x18004f032  mov     rax, [rax+28h]
0x18004f036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f03b  mov     esi, eax
0x18004f03d  cmp     [rsp+128h+var_C0], rbx
0x18004f042  jz      loc_18004F0EC
0x18004f048  mov     rax, [r14]
0x18004f04b  lea     r9, [rsp+128h+lParam]
0x18004f050  mov     r8, [rsp+128h+var_D8]
0x18004f055  mov     rdx, [rsp+128h+var_B8]
0x18004f05a  mov     rcx, r14
0x18004f05d  mov     rax, [rax+20h]
0x18004f061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f066  mov     esi, eax
0x18004f068  mov     rax, [r14]
0x18004f06b  mov     [rsp+128h+var_100], rbx
0x18004f070  mov     [rsp+128h+var_108], rbx
0x18004f075  xor     r9d, r9d
0x18004f078  mov     r8, [rsp+128h+var_B0]
0x18004f07d  mov     rdx, r12
0x18004f080  mov     rcx, r14
0x18004f083  mov     rax, [rax+30h]
0x18004f087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f08c  test    esi, esi
0x18004f08e  js      short loc_18004F0C3
0x18004f090  cmp     dword ptr [rsp+128h+lParam], ebx
0x18004f094  jnz     short loc_18004F0C3
0x18004f096  mov     r9, [rsp+128h+lParam+8]; lParam
0x18004f09b  test    r9, r9
0x18004f09e  jz      short loc_18004F0C3
0x18004f0a0  xor     r8d, r8d; wParam
0x18004f0a3  mov     edx, 143h; Msg
0x18004f0a8  mov     rcx, r15; hWnd
0x18004f0ab  call    cs:__imp_SendMessageW
0x18004f0b1  mov     rcx, [rsp+128h+lParam+8]; pv
0x18004f0b6  call    cs:__imp_CoTaskMemFree
0x18004f0bc  mov     [rsp+128h+lParam+8], rbx
0x18004f0c1  jmp     short loc_18004F0E0
0x18004f0c3  test    byte ptr cs:_bidGblFlags, 2
0x18004f0ca  jz      short loc_18004F0E0
0x18004f0cc  mov     r8d, 202h; unsigned int
0x18004f0d2  lea     rdx, aCdslpagerootGe_1; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004f0d9  mov     ecx, esi; int
0x18004f0db  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004f0e0  cmp     esi, 40EC6h
0x18004f0e6  jnz     loc_18004F010
0x18004f0ec  cmp     [rdi], bx
0x18004f0ef  jz      short loc_18004F0FE
0x18004f0f1  mov     rdx, rdi; lpString
0x18004f0f4  mov     rcx, r15; hWnd
0x18004f0f7  call    cs:__imp_SetWindowTextW
0x18004f0fd  nop
0x18004f0fe  jmp     short loc_18004F114
0x18004f100  mov     rdi, [rsp+128h+var_98]
0x18004f108  mov     esi, [rsp+128h+arg_0]
0x18004f10f  test    rdi, rdi
0x18004f112  jz      short loc_18004F11D
0x18004f114  mov     rcx, rdi
0x18004f117  call    cs:__imp_mpFree
0x18004f11d  mov     rdx, [rsp+128h+var_D8]
0x18004f122  test    rdx, rdx
0x18004f125  jz      short loc_18004F13E
0x18004f127  mov     rcx, [rsp+128h+arg_18]
0x18004f12f  mov     rax, [rcx]
0x18004f132  xor     r8d, r8d
0x18004f135  mov     rax, [rax+30h]
0x18004f139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f13e  mov     rcx, [rsp+128h+arg_18]
0x18004f146  test    rcx, rcx
0x18004f149  jz      short loc_18004F157
0x18004f14b  mov     rax, [rcx]
0x18004f14e  mov     rax, [rax+10h]
0x18004f152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f157  test    byte ptr cs:_bidGblFlags, 2
0x18004f15e  jz      short loc_18004F17D
0x18004f160  mov     r9d, esi
0x18004f163  lea     r8, aCdslpagerootGe_0; "<CDSLPageRoot::GetCatalogDataFromProvid"...
0x18004f16a  mov     edx, 89409h
0x18004f16f  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004f176  call    _bidTraceHR
0x18004f17b  mov     esi, eax
0x18004f17d  mov     eax, esi
0x18004f17f  mov     rbx, [rsp+128h+arg_8]
0x18004f187  add     rsp, 100h
0x18004f18e  pop     r15
0x18004f190  pop     r14
0x18004f192  pop     r12
0x18004f194  pop     rdi
0x18004f195  pop     rsi
0x18004f196  retn
```
