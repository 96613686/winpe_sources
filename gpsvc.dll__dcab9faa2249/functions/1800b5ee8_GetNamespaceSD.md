# GetNamespaceSD

- ea: `0x1800b5ee8`
- end: `0x1800b6137`
- name: `GetNamespaceSD`
- size: `591`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180070b54`
- `0x1800b7a18`

## callees

- `0x18000a504`
- `0x1800585e8`
- `0x18005ce04`
- `0x1800b5ee8`
- `0x1800bb958`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b608b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b608b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b5f1d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b5f45`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b5f1d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b5f45`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b5f56`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b5fa5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b5fae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b5f56`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b5fa5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b5fae`
- `OLEAUT32!__imp_VariantInit` at `0x1800b5fd5`
- `OLEAUT32!__imp_VariantInit` at `0x1800b5fd5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800b6070`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800b6070`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800b6053`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800b6053`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800b60c6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800b60c6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800b60f3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800b60f3`

## string_xrefs

- `0x1800b5f0e`: `__systemsecurity=@`

## pseudocode

```c
__int64 __fastcall GetNamespaceSD(__int64 a1, _QWORD *a2)
{
  OLECHAR *v5; // rdi
  OLECHAR *v6; // rsi
  HRESULT LBound; // ebx
  SIZE_T v8; // rsi
  HLOCAL v9; // rdi
  HLOCAL v10; // [rsp+50h] [rbp-30h] BYREF
  __int64 v11; // [rsp+58h] [rbp-28h] BYREF
  void *ppvData; // [rsp+60h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-18h] BYREF
  LONG plUbound; // [rsp+B0h] [rbp+30h] BYREF
  LONG plLbound; // [rsp+C0h] [rbp+40h] BYREF
  VARIANTARG *p_pvarg; // [rsp+C8h] [rbp+48h] BYREF

  if ( !a1 )
    return 2147500035LL;
  v11 = 0;
  v5 = SysAllocString(L"__systemsecurity=@");
  if ( !v5 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
    return 2147942414LL;
  }
  v6 = SysAllocString(L"GetSD");
  if ( !v6 )
  {
    SysFreeString(v5);
LABEL_16:
    LBound = -2147024882;
    goto LABEL_21;
  }
  LBound = (*(__int64 (__fastcall **)(__int64, OLECHAR *, OLECHAR *, _QWORD, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)a1 + 192LL))(
             a1,
             v5,
             v6,
             0,
             0,
             0,
             &v11,
             0);
  SysFreeString(v5);
  SysFreeString(v6);
  if ( LBound >= 0 )
  {
    p_pvarg = &pvarg;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    LBound = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v11 + 32LL))(
               v11,
               L"sd",
               0,
               &pvarg,
               0,
               0);
    if ( LBound >= 0 )
    {
      if ( pvarg.vt != 8209 )
      {
        XVariant::~XVariant(&p_pvarg);
        LBound = -2147467259;
        goto LABEL_21;
      }
      plLbound = 0;
      LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
      if ( LBound >= 0 )
      {
        plUbound = 0;
        LBound = SafeArrayGetUBound(pvarg.parray, 1u, &plUbound);
        if ( LBound >= 0 )
        {
          v8 = (unsigned int)(plUbound - plLbound + 1);
          v10 = LocalAlloc(0x40u, v8);
          v9 = v10;
          if ( !v10 )
          {
            XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v10);
            XVariant::~XVariant(&p_pvarg);
            goto LABEL_16;
          }
          ppvData = 0;
          LBound = SafeArrayAccessData(pvarg.parray, &ppvData);
          if ( LBound >= 0 )
          {
            memcpy_0(v10, ppvData, v8);
            LBound = SafeArrayUnaccessData(pvarg.parray);
            if ( LBound >= 0 )
            {
              v10 = 0;
              *a2 = v9;
              XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v10);
              XVariant::~XVariant(&p_pvarg);
              LBound = 0;
              goto LABEL_21;
            }
          }
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v10);
        }
      }
    }
    XVariant::~XVariant(&p_pvarg);
  }
LABEL_21:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x1800b5ee8  push    rbp
0x1800b5eea  push    rbx
0x1800b5eeb  push    rsi
0x1800b5eec  push    rdi
0x1800b5eed  push    r14
0x1800b5eef  mov     rbp, rsp
0x1800b5ef2  sub     rsp, 80h
0x1800b5ef9  mov     r14, rdx
0x1800b5efc  mov     rbx, rcx
0x1800b5eff  test    rcx, rcx
0x1800b5f02  jnz     short loc_1800B5F0E
0x1800b5f04  mov     eax, 80004003h
0x1800b5f09  jmp     loc_1800B6129
0x1800b5f0e  lea     rcx, aSystemsecurity_0; "__systemsecurity=@"
0x1800b5f15  mov     [rbp+var_28], 0
0x1800b5f1d  call    cs:__imp_SysAllocString
0x1800b5f23  mov     rdi, rax
0x1800b5f26  test    rax, rax
0x1800b5f29  jnz     short loc_1800B5F3E
0x1800b5f2b  lea     rcx, [rbp+var_28]
0x1800b5f2f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b5f34  mov     eax, 8007000Eh
0x1800b5f39  jmp     loc_1800B6129
0x1800b5f3e  lea     rcx, aGetsd; "GetSD"
0x1800b5f45  call    cs:__imp_SysAllocString
0x1800b5f4b  mov     rsi, rax
0x1800b5f4e  test    rax, rax
0x1800b5f51  jnz     short loc_1800B5F61
0x1800b5f53  mov     rcx, rdi; bstrString
0x1800b5f56  call    cs:__imp_SysFreeString
0x1800b5f5c  jmp     loc_1800B60AF
0x1800b5f61  mov     rax, [rbx]
0x1800b5f64  lea     rcx, [rbp+var_28]
0x1800b5f68  mov     [rsp+80h+var_48], 0
0x1800b5f71  xor     r9d, r9d
0x1800b5f74  mov     [rsp+80h+var_50], rcx
0x1800b5f79  mov     r8, rsi
0x1800b5f7c  mov     [rsp+80h+var_58], 0
0x1800b5f85  mov     rdx, rdi
0x1800b5f88  mov     rax, [rax+0C0h]
0x1800b5f8f  mov     rcx, rbx
0x1800b5f92  mov     [rsp+80h+var_60], 0
0x1800b5f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5fa0  mov     rcx, rdi; bstrString
0x1800b5fa3  mov     ebx, eax
0x1800b5fa5  call    cs:__imp_SysFreeString
0x1800b5fab  mov     rcx, rsi; bstrString
0x1800b5fae  call    cs:__imp_SysFreeString
0x1800b5fb4  test    ebx, ebx
0x1800b5fb6  js      loc_1800B611E
0x1800b5fbc  xor     eax, eax
0x1800b5fbe  lea     rcx, [rbp+pvarg]; pvarg
0x1800b5fc2  mov     qword ptr [rbp+pvarg+10h], rax
0x1800b5fc6  xorps   xmm0, xmm0
0x1800b5fc9  lea     rax, [rbp+pvarg]
0x1800b5fcd  mov     [rbp+arg_18], rax
0x1800b5fd1  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800b5fd5  call    cs:__imp_VariantInit
0x1800b5fdb  mov     rcx, [rbp+var_28]
0x1800b5fdf  lea     r9, [rbp+pvarg]
0x1800b5fe3  mov     [rsp+80h+var_58], 0
0x1800b5fec  lea     rdx, aSd; "sd"
0x1800b5ff3  xor     r8d, r8d
0x1800b5ff6  mov     [rsp+80h+var_60], 0
0x1800b5fff  mov     rax, [rcx]
0x1800b6002  mov     rax, [rax+20h]
0x1800b6006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b600b  mov     ebx, eax
0x1800b600d  test    eax, eax
0x1800b600f  jns     short loc_1800B601F
0x1800b6011  lea     rcx, [rbp+arg_18]; this
0x1800b6015  call    ??1XVariant@@QEAA@XZ; XVariant::~XVariant(void)
0x1800b601a  jmp     loc_1800B611E
0x1800b601f  mov     eax, 2011h
0x1800b6024  cmp     word ptr [rbp+pvarg], ax
0x1800b6028  jz      short loc_1800B603D
0x1800b602a  lea     rcx, [rbp+arg_18]; this
0x1800b602e  call    ??1XVariant@@QEAA@XZ; XVariant::~XVariant(void)
0x1800b6033  mov     ebx, 80004005h
0x1800b6038  jmp     loc_1800B611E
0x1800b603d  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x1800b6041  lea     r8, [rbp+plLbound]; plLbound
0x1800b6045  mov     edi, 1
0x1800b604a  mov     [rbp+plLbound], 0
0x1800b6051  mov     edx, edi; nDim
0x1800b6053  call    cs:__imp_SafeArrayGetLBound
0x1800b6059  mov     ebx, eax
0x1800b605b  test    eax, eax
0x1800b605d  js      short loc_1800B6011
0x1800b605f  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x1800b6063  lea     r8, [rbp+plUbound]; plUbound
0x1800b6067  mov     edx, edi; nDim
0x1800b6069  mov     [rbp+plUbound], 0
0x1800b6070  call    cs:__imp_SafeArrayGetUBound
0x1800b6076  mov     ebx, eax
0x1800b6078  test    eax, eax
0x1800b607a  js      short loc_1800B6011
0x1800b607c  mov     eax, [rbp+plUbound]
0x1800b607f  lea     ecx, [rdi+3Fh]; uFlags
0x1800b6082  sub     eax, [rbp+plLbound]
0x1800b6085  add     eax, edi
0x1800b6087  mov     edx, eax; uBytes
0x1800b6089  mov     esi, eax
0x1800b608b  call    cs:__imp_LocalAlloc
0x1800b6091  mov     [rbp+var_30], rax
0x1800b6095  mov     rdi, rax
0x1800b6098  test    rax, rax
0x1800b609b  jnz     short loc_1800B60B6
0x1800b609d  lea     rcx, [rbp+var_30]
0x1800b60a1  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b60a6  lea     rcx, [rbp+arg_18]; this
0x1800b60aa  call    ??1XVariant@@QEAA@XZ; XVariant::~XVariant(void)
0x1800b60af  mov     ebx, 8007000Eh
0x1800b60b4  jmp     short loc_1800B611E
0x1800b60b6  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x1800b60ba  lea     rdx, [rbp+ppvData]; ppvData
0x1800b60be  mov     [rbp+ppvData], 0
0x1800b60c6  call    cs:__imp_SafeArrayAccessData
0x1800b60cc  mov     ebx, eax
0x1800b60ce  test    eax, eax
0x1800b60d0  jns     short loc_1800B60E0
0x1800b60d2  lea     rcx, [rbp+var_30]
0x1800b60d6  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b60db  jmp     loc_1800B6011
0x1800b60e0  mov     rdx, [rbp+ppvData]; Src
0x1800b60e4  mov     r8, rsi; Size
0x1800b60e7  mov     rcx, rdi; void *
0x1800b60ea  call    memcpy_0
0x1800b60ef  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x1800b60f3  call    cs:__imp_SafeArrayUnaccessData
0x1800b60f9  lea     rcx, [rbp+var_30]
0x1800b60fd  mov     ebx, eax
0x1800b60ff  test    eax, eax
0x1800b6101  js      short loc_1800B60D6
0x1800b6103  mov     [rbp+var_30], 0
0x1800b610b  mov     [r14], rdi
0x1800b610e  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b6113  lea     rcx, [rbp+arg_18]; this
0x1800b6117  call    ??1XVariant@@QEAA@XZ; XVariant::~XVariant(void)
0x1800b611c  xor     ebx, ebx
0x1800b611e  lea     rcx, [rbp+var_28]
0x1800b6122  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b6127  mov     eax, ebx
0x1800b6129  add     rsp, 80h
0x1800b6130  pop     r14
0x1800b6132  pop     rdi
0x1800b6133  pop     rsi
0x1800b6134  pop     rbx
0x1800b6135  pop     rbp
0x1800b6136  retn
```
