# RemovePartition(ushort const *)

- ea: `0x180016aac`
- end: `0x180016e0b`
- name: `?RemovePartition@@YAJPEBG@Z`
- size: `863`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016e20`

## callees

- `0x180016aac`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180016cb6`
- `msvcrt!_wcsicmp` at `0x180016cb6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016d87`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016d87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016b15`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016b15`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016aef`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016aef`
- `OLEAUT32!__imp_SysAllocString` at `0x180016b2c`
- `OLEAUT32!__imp_SysAllocString` at `0x180016b2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180016b60`
- `OLEAUT32!__imp_SysFreeString` at `0x180016b60`
- `OLEAUT32!__imp_VariantClear` at `0x180016cd0`
- `OLEAUT32!__imp_VariantClear` at `0x180016d06`
- `OLEAUT32!__imp_VariantClear` at `0x180016d1f`
- `OLEAUT32!__imp_VariantClear` at `0x180016dae`
- `OLEAUT32!__imp_VariantClear` at `0x180016dc7`
- `OLEAUT32!__imp_VariantClear` at `0x180016de3`
- `OLEAUT32!__imp_VariantClear` at `0x180016dff`
- `OLEAUT32!__imp_VariantClear` at `0x180016cd0`
- `OLEAUT32!__imp_VariantClear` at `0x180016d06`
- `OLEAUT32!__imp_VariantClear` at `0x180016d1f`
- `OLEAUT32!__imp_VariantClear` at `0x180016dae`
- `OLEAUT32!__imp_VariantClear` at `0x180016dc7`
- `OLEAUT32!__imp_VariantClear` at `0x180016de3`
- `OLEAUT32!__imp_VariantClear` at `0x180016dff`
- `OLEAUT32!__imp_VariantChangeType` at `0x180016c9f`
- `OLEAUT32!__imp_VariantChangeType` at `0x180016c9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RemovePartition(wchar_t *String2)
{
  HRESULT v2; // r14d
  HRESULT v3; // ebx
  BSTR v4; // rax
  OLECHAR *v5; // rdi
  unsigned int i; // edi
  bool v7; // zf
  __int64 v9; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvargDest; // [rsp+40h] [rbp-20h] BYREF
  int v12; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v13; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v14; // [rsp+B8h] [rbp+58h] BYREF

  ppv = 0;
  v13 = 0;
  v9 = 0;
  v14 = 0;
  v12 = 0;
  v2 = CoInitializeEx(0, 2u);
  v3 = CoCreateInstance(&CLSID_COMAdminCatalog, 0, 1u, &GUID_790c6e0b_9194_4cc9_9426_a48a63185696, &ppv);
  if ( v3 >= 0 )
  {
    v4 = SysAllocString(L"Partitions");
    v5 = v4;
    if ( v4 )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v4, &v14);
      SysFreeString(v5);
      if ( v3 >= 0 )
      {
        v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(v14, &IID_ICatalogCollection, &v13);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 96LL))(v13);
          if ( v3 >= 0 )
          {
            v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 72LL))(v13, &v12);
            if ( v3 >= 0 )
            {
              for ( i = 0; ; ++i )
              {
                v7 = i == v12;
                if ( (int)i >= v12 )
                  goto LABEL_27;
                memset(&pvargDest, 0, sizeof(pvargDest));
                pvargDest.vt = 0;
                if ( v9 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
                  v9 = 0;
                }
                v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v13 + 64LL))(v13, i, &v14);
                if ( v3 < 0 )
                {
                  if ( pvargDest.vt == 4095 )
                    pvargDest.vt = 8;
                  goto LABEL_49;
                }
                v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v14)(v14, &IID_ICatalogObject, &v9);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                if ( v3 < 0 )
                {
                  if ( pvargDest.vt == 4095 )
                    pvargDest.vt = 8;
                  goto LABEL_49;
                }
                v3 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v9 + 72LL))(v9, &pvargDest);
                if ( v3 < 0 )
                {
                  if ( pvargDest.vt == 4095 )
                    pvargDest.vt = 8;
                  goto LABEL_49;
                }
                v3 = VariantChangeType(&pvargDest, &pvargDest, 0, 8u);
                if ( v3 < 0 )
                {
                  if ( pvargDest.vt == 4095 )
                    pvargDest.vt = 8;
                  goto LABEL_49;
                }
                if ( !_wcsicmp(pvargDest.bstrVal, String2) )
                  break;
                if ( pvargDest.vt == 4095 )
                  pvargDest.vt = 8;
                VariantClear(&pvargDest);
              }
              v3 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 80LL))(v13, i);
              if ( v3 < 0 )
              {
                if ( pvargDest.vt == 4095 )
                  pvargDest.vt = 8;
LABEL_49:
                VariantClear(&pvargDest);
                goto LABEL_29;
              }
              if ( pvargDest.vt == 4095 )
                pvargDest.vt = 8;
              VariantClear(&pvargDest);
              v7 = i == v12;
LABEL_27:
              if ( !v7 )
                v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 104LL))(v13, &v12);
            }
          }
        }
      }
    }
    else
    {
      v3 = -2147024882;
    }
  }
LABEL_29:
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v2 >= 0 )
    CoUninitialize();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016aac  push    rbp
0x180016aae  push    rbx
0x180016aaf  push    rsi
0x180016ab0  push    rdi
0x180016ab1  push    r12
0x180016ab3  push    r13
0x180016ab5  push    r14
0x180016ab7  mov     rbp, rsp
0x180016aba  sub     rsp, 60h
0x180016abe  mov     rsi, rcx
0x180016ac1  mov     [rbp+var_28], 0
0x180016ac9  mov     [rbp+arg_10], 0
0x180016ad1  mov     [rbp+var_30], 0
0x180016ad9  mov     [rbp+arg_18], 0
0x180016ae1  mov     [rbp+arg_8], 0
0x180016ae8  mov     edx, 2; dwCoInit
0x180016aed  xor     ecx, ecx; pvReserved
0x180016aef  call    cs:__imp_CoInitializeEx
0x180016af5  mov     r14d, eax
0x180016af8  lea     rax, [rbp+var_28]
0x180016afc  mov     [rsp+60h+ppv], rax; ppv
0x180016b01  lea     r9, _GUID_790c6e0b_9194_4cc9_9426_a48a63185696; riid
0x180016b08  xor     edx, edx; pUnkOuter
0x180016b0a  lea     r8d, [rdx+1]; dwClsContext
0x180016b0e  lea     rcx, CLSID_COMAdminCatalog; rclsid
0x180016b15  call    cs:__imp_CoCreateInstance
0x180016b1b  mov     ebx, eax
0x180016b1d  test    eax, eax
0x180016b1f  js      loc_180016D43
0x180016b25  lea     rcx, aPartitions; "Partitions"
0x180016b2c  call    cs:__imp_SysAllocString
0x180016b32  mov     rdi, rax
0x180016b35  test    rax, rax
0x180016b38  jnz     short loc_180016B44
0x180016b3a  mov     ebx, 8007000Eh
0x180016b3f  jmp     loc_180016D43
0x180016b44  mov     rcx, [rbp+var_28]
0x180016b48  mov     rax, [rcx]
0x180016b4b  lea     r8, [rbp+arg_18]
0x180016b4f  mov     rdx, rdi
0x180016b52  mov     rax, [rax+38h]
0x180016b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b5b  mov     ebx, eax
0x180016b5d  mov     rcx, rdi; bstrString
0x180016b60  call    cs:__imp_SysFreeString
0x180016b66  test    ebx, ebx
0x180016b68  js      loc_180016D43
0x180016b6e  mov     rcx, [rbp+arg_18]
0x180016b72  mov     rax, [rcx]
0x180016b75  lea     r8, [rbp+arg_10]
0x180016b79  lea     rdx, IID_ICatalogCollection
0x180016b80  mov     rax, [rax]
0x180016b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b88  mov     ebx, eax
0x180016b8a  mov     rcx, [rbp+arg_18]
0x180016b8e  mov     rax, [rcx]
0x180016b91  mov     rax, [rax+10h]
0x180016b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b9a  test    ebx, ebx
0x180016b9c  js      loc_180016D43
0x180016ba2  mov     rcx, [rbp+arg_10]
0x180016ba6  mov     rax, [rcx]
0x180016ba9  mov     rax, [rax+60h]
0x180016bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bb2  mov     ebx, eax
0x180016bb4  test    eax, eax
0x180016bb6  js      loc_180016D43
0x180016bbc  mov     rcx, [rbp+arg_10]
0x180016bc0  mov     rax, [rcx]
0x180016bc3  lea     rdx, [rbp+arg_8]
0x180016bc7  mov     rax, [rax+48h]
0x180016bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bd0  mov     ebx, eax
0x180016bd2  test    eax, eax
0x180016bd4  js      loc_180016D43
0x180016bda  xor     edi, edi
0x180016bdc  lea     r12d, [rdi+8]
0x180016be0  mov     r13d, 0FFFh
0x180016be6  mov     eax, [rbp+arg_8]
0x180016be9  cmp     edi, eax
0x180016beb  jge     loc_180016D2B
0x180016bf1  xorps   xmm0, xmm0
0x180016bf4  xor     eax, eax
0x180016bf6  movups  xmmword ptr [rbp+pvargDest], xmm0
0x180016bfa  mov     qword ptr [rbp+pvargDest+10h], rax
0x180016bfe  mov     word ptr [rbp+pvargDest], ax
0x180016c02  mov     rcx, [rbp+var_30]
0x180016c06  test    rcx, rcx
0x180016c09  jz      short loc_180016C1F
0x180016c0b  mov     rax, [rcx]
0x180016c0e  mov     rax, [rax+10h]
0x180016c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c17  mov     [rbp+var_30], 0
0x180016c1f  mov     rcx, [rbp+arg_10]
0x180016c23  mov     rax, [rcx]
0x180016c26  lea     r8, [rbp+arg_18]
0x180016c2a  mov     edx, edi
0x180016c2c  mov     rax, [rax+40h]
0x180016c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c35  mov     ebx, eax
0x180016c37  test    eax, eax
0x180016c39  js      loc_180016DEF
0x180016c3f  mov     rcx, [rbp+arg_18]
0x180016c43  mov     rax, [rcx]
0x180016c46  lea     r8, [rbp+var_30]
0x180016c4a  lea     rdx, IID_ICatalogObject
0x180016c51  mov     rax, [rax]
0x180016c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c59  mov     ebx, eax
0x180016c5b  mov     rcx, [rbp+arg_18]
0x180016c5f  mov     rax, [rcx]
0x180016c62  mov     rax, [rax+10h]
0x180016c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c6b  test    ebx, ebx
0x180016c6d  js      loc_180016DD3
0x180016c73  mov     rcx, [rbp+var_30]
0x180016c77  mov     rax, [rcx]
0x180016c7a  lea     rdx, [rbp+pvargDest]
0x180016c7e  mov     rax, [rax+48h]
0x180016c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c87  mov     ebx, eax
0x180016c89  test    eax, eax
0x180016c8b  js      loc_180016DB7
0x180016c91  mov     r9d, r12d; vt
0x180016c94  xor     r8d, r8d; wFlags
0x180016c97  lea     rdx, [rbp+pvargDest]; pvarSrc
0x180016c9b  lea     rcx, [rbp+pvargDest]; pvargDest
0x180016c9f  call    cs:__imp_VariantChangeType
0x180016ca5  mov     ebx, eax
0x180016ca7  test    eax, eax
0x180016ca9  js      loc_180016D9E
0x180016caf  mov     rdx, rsi; String2
0x180016cb2  mov     rcx, qword ptr [rbp+pvargDest+8]; String1
0x180016cb6  call    cs:__imp__wcsicmp
0x180016cbc  test    eax, eax
0x180016cbe  jz      short loc_180016CDE
0x180016cc0  cmp     word ptr [rbp+pvargDest], r13w
0x180016cc5  jnz     short loc_180016CCC
0x180016cc7  mov     word ptr [rbp+pvargDest], r12w
0x180016ccc  lea     rcx, [rbp+pvargDest]; pvarg
0x180016cd0  call    cs:__imp_VariantClear
0x180016cd6  nop
0x180016cd7  inc     edi
0x180016cd9  jmp     loc_180016BE6
0x180016cde  mov     rcx, [rbp+arg_10]
0x180016ce2  mov     rax, [rcx]
0x180016ce5  mov     edx, edi
0x180016ce7  mov     rax, [rax+50h]
0x180016ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cf0  mov     ebx, eax
0x180016cf2  test    eax, eax
0x180016cf4  jns     short loc_180016D0F
0x180016cf6  cmp     word ptr [rbp+pvargDest], r13w
0x180016cfb  jnz     short loc_180016D02
0x180016cfd  mov     word ptr [rbp+pvargDest], r12w
0x180016d02  lea     rcx, [rbp+pvargDest]; pvarg
0x180016d06  call    cs:__imp_VariantClear
0x180016d0c  nop
0x180016d0d  jmp     short loc_180016D43
0x180016d0f  cmp     word ptr [rbp+pvargDest], r13w
0x180016d14  jnz     short loc_180016D1B
0x180016d16  mov     word ptr [rbp+pvargDest], r12w
0x180016d1b  lea     rcx, [rbp+pvargDest]; pvarg
0x180016d1f  call    cs:__imp_VariantClear
0x180016d25  nop
0x180016d26  mov     eax, [rbp+arg_8]
0x180016d29  cmp     edi, eax
0x180016d2b  jz      short loc_180016D43
0x180016d2d  mov     rcx, [rbp+arg_10]
0x180016d31  mov     rax, [rcx]
0x180016d34  lea     rdx, [rbp+arg_8]
0x180016d38  mov     rax, [rax+68h]
0x180016d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d41  mov     ebx, eax
0x180016d43  mov     rcx, [rbp+var_30]
0x180016d47  test    rcx, rcx
0x180016d4a  jz      short loc_180016D58
0x180016d4c  mov     rax, [rcx]
0x180016d4f  mov     rax, [rax+10h]
0x180016d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d58  mov     rcx, [rbp+arg_10]
0x180016d5c  test    rcx, rcx
0x180016d5f  jz      short loc_180016D6D
0x180016d61  mov     rax, [rcx]
0x180016d64  mov     rax, [rax+10h]
0x180016d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d6d  mov     rcx, [rbp+var_28]
0x180016d71  test    rcx, rcx
0x180016d74  jz      short loc_180016D82
0x180016d76  mov     rax, [rcx]
0x180016d79  mov     rax, [rax+10h]
0x180016d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d82  test    r14d, r14d
0x180016d85  js      short loc_180016D8D
0x180016d87  call    cs:__imp_CoUninitialize
0x180016d8d  mov     eax, ebx
0x180016d8f  add     rsp, 60h
0x180016d93  pop     r14
0x180016d95  pop     r13
0x180016d97  pop     r12
0x180016d99  pop     rdi
0x180016d9a  pop     rsi
0x180016d9b  pop     rbx
0x180016d9c  pop     rbp
0x180016d9d  retn
0x180016d9e  cmp     word ptr [rbp+pvargDest], r13w
0x180016da3  jnz     short loc_180016DAA
0x180016da5  mov     word ptr [rbp+pvargDest], r12w
0x180016daa  lea     rcx, [rbp+pvargDest]; pvarg
0x180016dae  call    cs:__imp_VariantClear
0x180016db4  nop
0x180016db5  jmp     short loc_180016D43
0x180016db7  cmp     word ptr [rbp+pvargDest], r13w
0x180016dbc  jnz     short loc_180016DC3
0x180016dbe  mov     word ptr [rbp+pvargDest], r12w
0x180016dc3  lea     rcx, [rbp+pvargDest]; pvarg
0x180016dc7  call    cs:__imp_VariantClear
0x180016dcd  nop
0x180016dce  jmp     loc_180016D43
0x180016dd3  cmp     word ptr [rbp+pvargDest], r13w
0x180016dd8  jnz     short loc_180016DDF
0x180016dda  mov     word ptr [rbp+pvargDest], r12w
0x180016ddf  lea     rcx, [rbp+pvargDest]; pvarg
0x180016de3  call    cs:__imp_VariantClear
0x180016de9  nop
0x180016dea  jmp     loc_180016D43
0x180016def  cmp     word ptr [rbp+pvargDest], r13w
0x180016df4  jnz     short loc_180016DFB
0x180016df6  mov     word ptr [rbp+pvargDest], r12w
0x180016dfb  lea     rcx, [rbp+pvargDest]; pvarg
0x180016dff  call    cs:__imp_VariantClear
0x180016e05  nop
0x180016e06  jmp     loc_180016D43
```
