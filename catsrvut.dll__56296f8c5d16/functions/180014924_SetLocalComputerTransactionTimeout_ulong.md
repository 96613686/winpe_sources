# SetLocalComputerTransactionTimeout(ulong)

- ea: `0x180014924`
- end: `0x180014bab`
- name: `?SetLocalComputerTransactionTimeout@@YAJK@Z`
- size: `647`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016260`

## callees

- `0x180014924`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014b97`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180014b97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001499d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001499d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001496c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001496c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800149b4`
- `OLEAUT32!__imp_SysAllocString` at `0x180014ac8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800149b4`
- `OLEAUT32!__imp_SysAllocString` at `0x180014ac8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800149e8`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b18`
- `OLEAUT32!__imp_SysFreeString` at `0x1800149e8`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b18`
- `OLEAUT32!__imp_VariantInit` at `0x18001495f`
- `OLEAUT32!__imp_VariantInit` at `0x18001495f`

## string_xrefs

- `0x1800149ad`: `LocalComputer`

## pseudocode

```c
__int64 __fastcall SetLocalComputerTransactionTimeout()
{
  HRESULT v0; // ebx
  int v1; // edi
  BSTR v2; // rax
  OLECHAR *v3; // rsi
  BSTR v4; // rax
  OLECHAR *v5; // rsi
  BSTR v6; // rdx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(__int64 *, BSTR, __int128 *); // rax
  LPVOID ppv; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v11; // [rsp+38h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-9h] BYREF
  __int128 v13; // [rsp+60h] [rbp+17h] BYREF
  IRecordInfo *pRecInfo; // [rsp+70h] [rbp+27h]
  int v15; // [rsp+B0h] [rbp+67h] BYREF
  int v16; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v17; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v18; // [rsp+C8h] [rbp+7Fh] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v18 = 0;
  v17 = 0;
  v11 = 0;
  ppv = 0;
  v15 = 0;
  v16 = 0;
  VariantInit(&pvarg);
  v0 = CoInitializeEx(0, 2u);
  if ( v0 < 0 )
  {
    v1 = 0;
  }
  else
  {
    v1 = 1;
    v0 = CoCreateInstance(&CLSID_Catalog, 0, 1u, &IID_ICatalog, &ppv);
    if ( v0 < 0 )
      goto LABEL_17;
    v2 = SysAllocString(L"LocalComputer");
    v3 = v2;
    if ( !v2 )
      goto LABEL_4;
    v0 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v2, &v18);
    SysFreeString(v3);
    if ( v0 >= 0 )
    {
      v0 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(v18, &IID_ICatalogCollection, &v17);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      if ( v0 >= 0 )
      {
        v0 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 96LL))(v17);
        if ( v0 >= 0 )
        {
          v0 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 72LL))(v17, &v15);
          if ( v0 >= 0 )
          {
            if ( v15 == 1 )
            {
              v0 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 64LL))(v17, 0, &v18);
              if ( v0 >= 0 )
              {
                v0 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v18)(v18, &IID_ICatalogObject, &v11);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                if ( v0 >= 0 )
                {
                  v4 = SysAllocString(L"TransactionTimeout");
                  v5 = v4;
                  if ( !v4 )
                  {
LABEL_4:
                    v0 = -2147024882;
                    goto LABEL_17;
                  }
                  pvarg.vt = 3;
                  v6 = v4;
                  pvarg.lVal = 0;
                  v7 = *v11;
                  pRecInfo = pvarg.pRecInfo;
                  v8 = *(__int64 (__fastcall **)(__int64 *, BSTR, __int128 *))(v7 + 64);
                  v13 = *(_OWORD *)&pvarg.vt;
                  v0 = v8(v11, v6, &v13);
                  SysFreeString(v5);
                  if ( v0 >= 0 )
                    v0 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 104LL))(v17, &v16);
                }
              }
            }
            else
            {
              v0 = -2147467259;
            }
          }
        }
      }
    }
  }
LABEL_17:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
    v11 = 0;
  }
  if ( v1 )
    CoUninitialize();
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180014924  mov     [rsp-8+arg_0], ecx
0x180014928  push    rbp
0x180014929  push    rbx
0x18001492a  push    rsi
0x18001492b  push    rdi
0x18001492c  lea     rbp, [rsp-3Fh]
0x180014931  sub     rsp, 88h
0x180014938  xor     eax, eax
0x18001493a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001493e  xorps   xmm0, xmm0
0x180014941  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180014945  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180014949  mov     [rbp+57h+arg_18], rax
0x18001494d  mov     [rbp+57h+arg_10], rax
0x180014951  mov     [rbp+57h+var_68], rax
0x180014955  mov     [rbp+57h+var_70], rax
0x180014959  mov     [rbp+57h+arg_0], eax
0x18001495c  mov     [rbp+57h+arg_8], eax
0x18001495f  call    cs:__imp_VariantInit
0x180014965  mov     edx, 2; dwCoInit
0x18001496a  xor     ecx, ecx; pvReserved
0x18001496c  call    cs:__imp_CoInitializeEx
0x180014972  mov     ebx, eax
0x180014974  test    eax, eax
0x180014976  js      loc_180014B3A
0x18001497c  lea     rax, [rbp+57h+var_70]
0x180014980  mov     edi, 1
0x180014985  mov     r8d, edi; dwClsContext
0x180014988  mov     [rsp+0A0h+ppv], rax; ppv
0x18001498d  lea     r9, IID_ICatalog; riid
0x180014994  xor     edx, edx; pUnkOuter
0x180014996  lea     rcx, CLSID_Catalog; rclsid
0x18001499d  call    cs:__imp_CoCreateInstance
0x1800149a3  mov     ebx, eax
0x1800149a5  test    eax, eax
0x1800149a7  js      loc_180014B3C
0x1800149ad  lea     rcx, psz; "LocalComputer"
0x1800149b4  call    cs:__imp_SysAllocString
0x1800149ba  mov     rsi, rax
0x1800149bd  test    rax, rax
0x1800149c0  jnz     short loc_1800149CC
0x1800149c2  mov     ebx, 8007000Eh
0x1800149c7  jmp     loc_180014B3C
0x1800149cc  mov     rcx, [rbp+57h+var_70]
0x1800149d0  lea     r8, [rbp+57h+arg_18]
0x1800149d4  mov     rdx, rsi
0x1800149d7  mov     rax, [rcx]
0x1800149da  mov     rax, [rax+38h]
0x1800149de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e3  mov     rcx, rsi; bstrString
0x1800149e6  mov     ebx, eax
0x1800149e8  call    cs:__imp_SysFreeString
0x1800149ee  test    ebx, ebx
0x1800149f0  js      loc_180014B3C
0x1800149f6  mov     rcx, [rbp+57h+arg_18]
0x1800149fa  lea     r8, [rbp+57h+arg_10]
0x1800149fe  lea     rdx, IID_ICatalogCollection
0x180014a05  mov     rax, [rcx]
0x180014a08  mov     rax, [rax]
0x180014a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a10  mov     rcx, [rbp+57h+arg_18]
0x180014a14  mov     ebx, eax
0x180014a16  mov     rax, [rcx]
0x180014a19  mov     rax, [rax+10h]
0x180014a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a22  test    ebx, ebx
0x180014a24  js      loc_180014B3C
0x180014a2a  mov     rcx, [rbp+57h+arg_10]
0x180014a2e  mov     rax, [rcx]
0x180014a31  mov     rax, [rax+60h]
0x180014a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a3a  mov     ebx, eax
0x180014a3c  test    eax, eax
0x180014a3e  js      loc_180014B3C
0x180014a44  mov     rcx, [rbp+57h+arg_10]
0x180014a48  lea     rdx, [rbp+57h+arg_0]
0x180014a4c  mov     rax, [rcx]
0x180014a4f  mov     rax, [rax+48h]
0x180014a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a58  mov     ebx, eax
0x180014a5a  test    eax, eax
0x180014a5c  js      loc_180014B3C
0x180014a62  cmp     [rbp+57h+arg_0], edi
0x180014a65  jz      short loc_180014A71
0x180014a67  mov     ebx, 80004005h
0x180014a6c  jmp     loc_180014B3C
0x180014a71  mov     rcx, [rbp+57h+arg_10]
0x180014a75  lea     r8, [rbp+57h+arg_18]
0x180014a79  xor     edx, edx
0x180014a7b  mov     rax, [rcx]
0x180014a7e  mov     rax, [rax+40h]
0x180014a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a87  mov     ebx, eax
0x180014a89  test    eax, eax
0x180014a8b  js      loc_180014B3C
0x180014a91  mov     rcx, [rbp+57h+arg_18]
0x180014a95  lea     r8, [rbp+57h+var_68]
0x180014a99  lea     rdx, IID_ICatalogObject
0x180014aa0  mov     rax, [rcx]
0x180014aa3  mov     rax, [rax]
0x180014aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aab  mov     rcx, [rbp+57h+arg_18]
0x180014aaf  mov     ebx, eax
0x180014ab1  mov     rax, [rcx]
0x180014ab4  mov     rax, [rax+10h]
0x180014ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014abd  test    ebx, ebx
0x180014abf  js      short loc_180014B3C
0x180014ac1  lea     rcx, aTransactiontim; "TransactionTimeout"
0x180014ac8  call    cs:__imp_SysAllocString
0x180014ace  mov     rsi, rax
0x180014ad1  test    rax, rax
0x180014ad4  jz      loc_1800149C2
0x180014ada  mov     rcx, [rbp+57h+var_68]
0x180014ade  lea     r8, [rbp+57h+var_40]
0x180014ae2  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180014ae7  mov     eax, 3
0x180014aec  mov     word ptr [rbp+57h+pvarg], ax
0x180014af0  mov     rdx, rsi
0x180014af3  mov     dword ptr [rbp+57h+pvarg+8], 0
0x180014afa  mov     rax, [rcx]
0x180014afd  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180014b01  movsd   [rbp+57h+var_30], xmm1
0x180014b06  mov     rax, [rax+40h]
0x180014b0a  movaps  [rbp+57h+var_40], xmm0
0x180014b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b13  mov     rcx, rsi; bstrString
0x180014b16  mov     ebx, eax
0x180014b18  call    cs:__imp_SysFreeString
0x180014b1e  test    ebx, ebx
0x180014b20  js      short loc_180014B3C
0x180014b22  mov     rcx, [rbp+57h+arg_10]
0x180014b26  lea     rdx, [rbp+57h+arg_8]
0x180014b2a  mov     rax, [rcx]
0x180014b2d  mov     rax, [rax+68h]
0x180014b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b36  mov     ebx, eax
0x180014b38  jmp     short loc_180014B3C
0x180014b3a  xor     edi, edi
0x180014b3c  mov     rcx, [rbp+57h+arg_10]
0x180014b40  test    rcx, rcx
0x180014b43  jz      short loc_180014B59
0x180014b45  mov     rax, [rcx]
0x180014b48  mov     rax, [rax+10h]
0x180014b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b51  mov     [rbp+57h+arg_10], 0
0x180014b59  mov     rcx, [rbp+57h+var_70]
0x180014b5d  test    rcx, rcx
0x180014b60  jz      short loc_180014B76
0x180014b62  mov     rax, [rcx]
0x180014b65  mov     rax, [rax+10h]
0x180014b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b6e  mov     [rbp+57h+var_70], 0
0x180014b76  mov     rcx, [rbp+57h+var_68]
0x180014b7a  test    rcx, rcx
0x180014b7d  jz      short loc_180014B93
0x180014b7f  mov     rax, [rcx]
0x180014b82  mov     rax, [rax+10h]
0x180014b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b8b  mov     [rbp+57h+var_68], 0
0x180014b93  test    edi, edi
0x180014b95  jz      short loc_180014B9D
0x180014b97  call    cs:__imp_CoUninitialize
0x180014b9d  mov     eax, ebx
0x180014b9f  add     rsp, 88h
0x180014ba6  pop     rdi
0x180014ba7  pop     rsi
0x180014ba8  pop     rbx
0x180014ba9  pop     rbp
0x180014baa  retn
```
