# RemoveApplication(ushort const *,ushort const *)

- ea: `0x1800166f8`
- end: `0x180016aa5`
- name: `?RemoveApplication@@YAJPEBG0@Z`
- size: `941`
- prototype: `__int64 __fastcall(wchar_t *String2, OLECHAR *psz)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016e20`

## callees

- `0x1800166f8`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180016946`
- `msvcrt!_wcsicmp` at `0x180016946`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016a17`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016a17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001676b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001676b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016745`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016745`
- `OLEAUT32!__imp_SysAllocString` at `0x18001677e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800167c6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001677e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800167c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800167f0`
- `OLEAUT32!__imp_VariantClear` at `0x180016960`
- `OLEAUT32!__imp_VariantClear` at `0x180016996`
- `OLEAUT32!__imp_VariantClear` at `0x1800169af`
- `OLEAUT32!__imp_VariantClear` at `0x180016a48`
- `OLEAUT32!__imp_VariantClear` at `0x180016a61`
- `OLEAUT32!__imp_VariantClear` at `0x180016a7d`
- `OLEAUT32!__imp_VariantClear` at `0x180016a99`
- `OLEAUT32!__imp_VariantClear` at `0x180016960`
- `OLEAUT32!__imp_VariantClear` at `0x180016996`
- `OLEAUT32!__imp_VariantClear` at `0x1800169af`
- `OLEAUT32!__imp_VariantClear` at `0x180016a48`
- `OLEAUT32!__imp_VariantClear` at `0x180016a61`
- `OLEAUT32!__imp_VariantClear` at `0x180016a7d`
- `OLEAUT32!__imp_VariantClear` at `0x180016a99`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001692f`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001692f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RemoveApplication(wchar_t *String2, OLECHAR *psz)
{
  HRESULT v4; // r14d
  HRESULT v5; // ebx
  BSTR v6; // rax
  OLECHAR *v7; // rdi
  BSTR v8; // rax
  OLECHAR *v9; // rdi
  unsigned int i; // edi
  bool v11; // zf
  __int64 v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+38h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-20h] BYREF
  VARIANTARG pvargDest; // [rsp+48h] [rbp-18h] BYREF
  int v17; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+48h] BYREF

  ppv = 0;
  v18 = 0;
  v14 = 0;
  v13 = 0;
  v17 = 0;
  v4 = CoInitializeEx(0, 2u);
  v5 = CoCreateInstance(&CLSID_COMAdminCatalog, 0, 1u, &GUID_790c6e0b_9194_4cc9_9426_a48a63185696, &ppv);
  if ( v5 >= 0 )
  {
    v6 = SysAllocString(psz);
    v7 = v6;
    if ( !v6 )
    {
LABEL_3:
      v5 = -2147024882;
      goto LABEL_31;
    }
    v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 368LL))(ppv, v6);
    SysFreeString(v7);
    if ( v5 >= 0 )
    {
      v8 = SysAllocString(L"Applications");
      v9 = v8;
      if ( !v8 )
        goto LABEL_3;
      v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v8, &v13);
      SysFreeString(v9);
      if ( v5 >= 0 )
      {
        v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(v13, &IID_ICatalogCollection, &v18);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 96LL))(v18);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 72LL))(v18, &v17);
            if ( v5 >= 0 )
            {
              for ( i = 0; ; ++i )
              {
                v11 = i == v17;
                if ( (int)i >= v17 )
                  goto LABEL_29;
                memset(&pvargDest, 0, sizeof(pvargDest));
                pvargDest.vt = 0;
                if ( v14 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                  v14 = 0;
                }
                v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 64LL))(v18, i, &v13);
                if ( v5 < 0 )
                {
                  if ( pvargDest.vt == 4095 )
                    pvargDest.vt = 8;
                  goto LABEL_51;
                }
                v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(v13, &IID_ICatalogObject, &v14);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                if ( v5 < 0 )
                {
                  if ( pvargDest.vt == 4095 )
                    pvargDest.vt = 8;
                  goto LABEL_51;
                }
                v5 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v14 + 72LL))(v14, &pvargDest);
                if ( v5 < 0 )
                {
                  if ( pvargDest.vt == 4095 )
                    pvargDest.vt = 8;
                  goto LABEL_51;
                }
                v5 = VariantChangeType(&pvargDest, &pvargDest, 0, 8u);
                if ( v5 < 0 )
                {
                  if ( pvargDest.vt == 4095 )
                    pvargDest.vt = 8;
                  goto LABEL_51;
                }
                if ( !_wcsicmp(pvargDest.bstrVal, String2) )
                  break;
                if ( pvargDest.vt == 4095 )
                  pvargDest.vt = 8;
                VariantClear(&pvargDest);
              }
              v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 80LL))(v18, i);
              if ( v5 < 0 )
              {
                if ( pvargDest.vt == 4095 )
                  pvargDest.vt = 8;
LABEL_51:
                VariantClear(&pvargDest);
                goto LABEL_31;
              }
              if ( pvargDest.vt == 4095 )
                pvargDest.vt = 8;
              VariantClear(&pvargDest);
              v11 = i == v17;
LABEL_29:
              if ( !v11 )
                v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 104LL))(v18, &v17);
            }
          }
        }
      }
    }
  }
LABEL_31:
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v4 >= 0 )
    CoUninitialize();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800166f8  mov     [rsp-28h+arg_0], rbx
0x1800166fd  mov     [rsp-28h+arg_8], rsi
0x180016702  push    rbp
0x180016703  push    rdi
0x180016704  push    r12
0x180016706  push    r13
0x180016708  push    r14
0x18001670a  mov     rbp, rsp
0x18001670d  sub     rsp, 60h
0x180016711  mov     rdi, rdx
0x180016714  mov     rsi, rcx
0x180016717  mov     [rbp+var_20], 0
0x18001671f  mov     [rbp+arg_18], 0
0x180016727  mov     [rbp+var_28], 0
0x18001672f  mov     [rbp+var_30], 0
0x180016737  mov     [rbp+arg_10], 0
0x18001673e  mov     edx, 2; dwCoInit
0x180016743  xor     ecx, ecx; pvReserved
0x180016745  call    cs:__imp_CoInitializeEx
0x18001674b  mov     r14d, eax
0x18001674e  lea     rax, [rbp+var_20]
0x180016752  mov     [rsp+60h+ppv], rax; ppv
0x180016757  lea     r9, _GUID_790c6e0b_9194_4cc9_9426_a48a63185696; riid
0x18001675e  xor     edx, edx; pUnkOuter
0x180016760  lea     r8d, [rdx+1]; dwClsContext
0x180016764  lea     rcx, CLSID_COMAdminCatalog; rclsid
0x18001676b  call    cs:__imp_CoCreateInstance
0x180016771  mov     ebx, eax
0x180016773  test    eax, eax
0x180016775  js      loc_1800169D3
0x18001677b  mov     rcx, rdi; psz
0x18001677e  call    cs:__imp_SysAllocString
0x180016784  mov     rdi, rax
0x180016787  test    rax, rax
0x18001678a  jnz     short loc_180016796
0x18001678c  mov     ebx, 8007000Eh
0x180016791  jmp     loc_1800169D3
0x180016796  mov     rcx, [rbp+var_20]
0x18001679a  mov     rax, [rcx]
0x18001679d  mov     rdx, rdi
0x1800167a0  mov     rax, [rax+170h]
0x1800167a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167ac  mov     ebx, eax
0x1800167ae  mov     rcx, rdi; bstrString
0x1800167b1  call    cs:__imp_SysFreeString
0x1800167b7  test    ebx, ebx
0x1800167b9  js      loc_1800169D3
0x1800167bf  lea     rcx, aApplications; "Applications"
0x1800167c6  call    cs:__imp_SysAllocString
0x1800167cc  mov     rdi, rax
0x1800167cf  test    rax, rax
0x1800167d2  jz      short loc_18001678C
0x1800167d4  mov     rcx, [rbp+var_20]
0x1800167d8  mov     rax, [rcx]
0x1800167db  lea     r8, [rbp+var_30]
0x1800167df  mov     rdx, rdi
0x1800167e2  mov     rax, [rax+38h]
0x1800167e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167eb  mov     ebx, eax
0x1800167ed  mov     rcx, rdi; bstrString
0x1800167f0  call    cs:__imp_SysFreeString
0x1800167f6  test    ebx, ebx
0x1800167f8  js      loc_1800169D3
0x1800167fe  mov     rcx, [rbp+var_30]
0x180016802  mov     rax, [rcx]
0x180016805  lea     r8, [rbp+arg_18]
0x180016809  lea     rdx, IID_ICatalogCollection
0x180016810  mov     rax, [rax]
0x180016813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016818  mov     ebx, eax
0x18001681a  mov     rcx, [rbp+var_30]
0x18001681e  mov     rax, [rcx]
0x180016821  mov     rax, [rax+10h]
0x180016825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001682a  test    ebx, ebx
0x18001682c  js      loc_1800169D3
0x180016832  mov     rcx, [rbp+arg_18]
0x180016836  mov     rax, [rcx]
0x180016839  mov     rax, [rax+60h]
0x18001683d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016842  mov     ebx, eax
0x180016844  test    eax, eax
0x180016846  js      loc_1800169D3
0x18001684c  mov     rcx, [rbp+arg_18]
0x180016850  mov     rax, [rcx]
0x180016853  lea     rdx, [rbp+arg_10]
0x180016857  mov     rax, [rax+48h]
0x18001685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016860  mov     ebx, eax
0x180016862  test    eax, eax
0x180016864  js      loc_1800169D3
0x18001686a  xor     edi, edi
0x18001686c  lea     r12d, [rdi+8]
0x180016870  mov     r13d, 0FFFh
0x180016876  mov     eax, [rbp+arg_10]
0x180016879  cmp     edi, eax
0x18001687b  jge     loc_1800169BB
0x180016881  xorps   xmm0, xmm0
0x180016884  xor     eax, eax
0x180016886  movups  xmmword ptr [rbp+pvargDest], xmm0
0x18001688a  mov     qword ptr [rbp+pvargDest+10h], rax
0x18001688e  mov     word ptr [rbp+pvargDest], ax
0x180016892  mov     rcx, [rbp+var_28]
0x180016896  test    rcx, rcx
0x180016899  jz      short loc_1800168AF
0x18001689b  mov     rax, [rcx]
0x18001689e  mov     rax, [rax+10h]
0x1800168a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168a7  mov     [rbp+var_28], 0
0x1800168af  mov     rcx, [rbp+arg_18]
0x1800168b3  mov     rax, [rcx]
0x1800168b6  lea     r8, [rbp+var_30]
0x1800168ba  mov     edx, edi
0x1800168bc  mov     rax, [rax+40h]
0x1800168c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168c5  mov     ebx, eax
0x1800168c7  test    eax, eax
0x1800168c9  js      loc_180016A89
0x1800168cf  mov     rcx, [rbp+var_30]
0x1800168d3  mov     rax, [rcx]
0x1800168d6  lea     r8, [rbp+var_28]
0x1800168da  lea     rdx, IID_ICatalogObject
0x1800168e1  mov     rax, [rax]
0x1800168e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e9  mov     ebx, eax
0x1800168eb  mov     rcx, [rbp+var_30]
0x1800168ef  mov     rax, [rcx]
0x1800168f2  mov     rax, [rax+10h]
0x1800168f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168fb  test    ebx, ebx
0x1800168fd  js      loc_180016A6D
0x180016903  mov     rcx, [rbp+var_28]
0x180016907  mov     rax, [rcx]
0x18001690a  lea     rdx, [rbp+pvargDest]
0x18001690e  mov     rax, [rax+48h]
0x180016912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016917  mov     ebx, eax
0x180016919  test    eax, eax
0x18001691b  js      loc_180016A51
0x180016921  mov     r9d, r12d; vt
0x180016924  xor     r8d, r8d; wFlags
0x180016927  lea     rdx, [rbp+pvargDest]; pvarSrc
0x18001692b  lea     rcx, [rbp+pvargDest]; pvargDest
0x18001692f  call    cs:__imp_VariantChangeType
0x180016935  mov     ebx, eax
0x180016937  test    eax, eax
0x180016939  js      loc_180016A38
0x18001693f  mov     rdx, rsi; String2
0x180016942  mov     rcx, qword ptr [rbp+pvargDest+8]; String1
0x180016946  call    cs:__imp__wcsicmp
0x18001694c  test    eax, eax
0x18001694e  jz      short loc_18001696E
0x180016950  cmp     word ptr [rbp+pvargDest], r13w
0x180016955  jnz     short loc_18001695C
0x180016957  mov     word ptr [rbp+pvargDest], r12w
0x18001695c  lea     rcx, [rbp+pvargDest]; pvarg
0x180016960  call    cs:__imp_VariantClear
0x180016966  nop
0x180016967  inc     edi
0x180016969  jmp     loc_180016876
0x18001696e  mov     rcx, [rbp+arg_18]
0x180016972  mov     rax, [rcx]
0x180016975  mov     edx, edi
0x180016977  mov     rax, [rax+50h]
0x18001697b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016980  mov     ebx, eax
0x180016982  test    eax, eax
0x180016984  jns     short loc_18001699F
0x180016986  cmp     word ptr [rbp+pvargDest], r13w
0x18001698b  jnz     short loc_180016992
0x18001698d  mov     word ptr [rbp+pvargDest], r12w
0x180016992  lea     rcx, [rbp+pvargDest]; pvarg
0x180016996  call    cs:__imp_VariantClear
0x18001699c  nop
0x18001699d  jmp     short loc_1800169D3
0x18001699f  cmp     word ptr [rbp+pvargDest], r13w
0x1800169a4  jnz     short loc_1800169AB
0x1800169a6  mov     word ptr [rbp+pvargDest], r12w
0x1800169ab  lea     rcx, [rbp+pvargDest]; pvarg
0x1800169af  call    cs:__imp_VariantClear
0x1800169b5  nop
0x1800169b6  mov     eax, [rbp+arg_10]
0x1800169b9  cmp     edi, eax
0x1800169bb  jz      short loc_1800169D3
0x1800169bd  mov     rcx, [rbp+arg_18]
0x1800169c1  mov     rax, [rcx]
0x1800169c4  lea     rdx, [rbp+arg_10]
0x1800169c8  mov     rax, [rax+68h]
0x1800169cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169d1  mov     ebx, eax
0x1800169d3  mov     rcx, [rbp+var_28]
0x1800169d7  test    rcx, rcx
0x1800169da  jz      short loc_1800169E8
0x1800169dc  mov     rax, [rcx]
0x1800169df  mov     rax, [rax+10h]
0x1800169e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169e8  mov     rcx, [rbp+arg_18]
0x1800169ec  test    rcx, rcx
0x1800169ef  jz      short loc_1800169FD
0x1800169f1  mov     rax, [rcx]
0x1800169f4  mov     rax, [rax+10h]
0x1800169f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169fd  mov     rcx, [rbp+var_20]
0x180016a01  test    rcx, rcx
0x180016a04  jz      short loc_180016A12
0x180016a06  mov     rax, [rcx]
0x180016a09  mov     rax, [rax+10h]
0x180016a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a12  test    r14d, r14d
0x180016a15  js      short loc_180016A1D
0x180016a17  call    cs:__imp_CoUninitialize
0x180016a1d  mov     eax, ebx
0x180016a1f  lea     r11, [rsp+60h+var_s0]
0x180016a24  mov     rbx, [r11+30h]
0x180016a28  mov     rsi, [r11+38h]
0x180016a2c  mov     rsp, r11
0x180016a2f  pop     r14
0x180016a31  pop     r13
0x180016a33  pop     r12
0x180016a35  pop     rdi
0x180016a36  pop     rbp
0x180016a37  retn
0x180016a38  cmp     word ptr [rbp+pvargDest], r13w
0x180016a3d  jnz     short loc_180016A44
0x180016a3f  mov     word ptr [rbp+pvargDest], r12w
0x180016a44  lea     rcx, [rbp+pvargDest]; pvarg
0x180016a48  call    cs:__imp_VariantClear
0x180016a4e  nop
0x180016a4f  jmp     short loc_1800169D3
0x180016a51  cmp     word ptr [rbp+pvargDest], r13w
0x180016a56  jnz     short loc_180016A5D
0x180016a58  mov     word ptr [rbp+pvargDest], r12w
0x180016a5d  lea     rcx, [rbp+pvargDest]; pvarg
0x180016a61  call    cs:__imp_VariantClear
0x180016a67  nop
0x180016a68  jmp     loc_1800169D3
0x180016a6d  cmp     word ptr [rbp+pvargDest], r13w
0x180016a72  jnz     short loc_180016A79
0x180016a74  mov     word ptr [rbp+pvargDest], r12w
0x180016a79  lea     rcx, [rbp+pvargDest]; pvarg
0x180016a7d  call    cs:__imp_VariantClear
0x180016a83  nop
0x180016a84  jmp     loc_1800169D3
0x180016a89  cmp     word ptr [rbp+pvargDest], r13w
0x180016a8e  jnz     short loc_180016A95
0x180016a90  mov     word ptr [rbp+pvargDest], r12w
0x180016a95  lea     rcx, [rbp+pvargDest]; pvarg
0x180016a99  call    cs:__imp_VariantClear
0x180016a9f  nop
0x180016aa0  jmp     loc_1800169D3
```
