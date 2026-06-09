# SetNamespaceSD

- ea: `0x1800b6140`
- end: `0x1800b63ee`
- name: `SetNamespaceSD`
- size: `686`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180070b54`
- `0x1800b7cc8`

## callees

- `0x1800585e8`
- `0x18005ce04`
- `0x1800b6140`
- `0x1800bb958`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800b620f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800b620f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b617a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b630b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b6345`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b617a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b630b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800b6345`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b61bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b6356`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b63a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b63ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b61bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b6356`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b63a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b63ab`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800b6228`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800b6228`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800b6258`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800b6258`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800b627a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800b627a`

## string_xrefs

- `0x1800b6304`: `__systemsecurity=@`
- `0x1800b616b`: `__systemsecurity`

## pseudocode

```c
__int64 __fastcall SetNamespaceSD(void *Src, __int64 a2)
{
  OLECHAR *v5; // rdi
  HRESULT v6; // ebx
  DWORD SecurityDescriptorLength; // eax
  size_t v8; // r15
  SAFEARRAY *v9; // rax
  SAFEARRAY *v10; // rdi
  OLECHAR *v11; // rdi
  OLECHAR *v12; // r14
  __int64 v13; // [rsp+50h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+58h] [rbp-28h] BYREF
  void *ppvData; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v16[3]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v17; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+40h] BYREF
  VARIANTARG *v19; // [rsp+C8h] [rbp+48h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v13 = 0;
  v5 = SysAllocString(L"__systemsecurity");
  if ( !v5 )
    goto LABEL_14;
  v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)a2 + 48LL))(
         a2,
         v5,
         0,
         0,
         &v13,
         0);
  SysFreeString(v5);
  if ( v6 >= 0 )
  {
    v17 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v13 + 152LL))(
           v13,
           L"SetSD",
           0,
           &v17,
           0);
    if ( v6 >= 0 )
    {
      rgsabound.lLbound = 0;
      SecurityDescriptorLength = GetSecurityDescriptorLength(Src);
      v8 = SecurityDescriptorLength;
      rgsabound.cElements = SecurityDescriptorLength;
      v9 = SafeArrayCreate(0x11u, 1u, &rgsabound);
      v10 = v9;
      if ( !v9 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
        v6 = -2147467259;
        goto LABEL_20;
      }
      ppvData = 0;
      v6 = SafeArrayAccessData(v9, &ppvData);
      if ( v6 >= 0 )
      {
        memcpy_0(ppvData, Src, v8);
        v6 = SafeArrayUnaccessData(v10);
        if ( v6 >= 0 )
        {
          v18 = 0;
          v16[2] = 0;
          v16[0] = 8209;
          v16[1] = v10;
          v19 = (VARIANTARG *)v16;
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 120LL))(v17, 0, &v18);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD *, _DWORD))(*(_QWORD *)v18 + 40LL))(
                   v18,
                   L"sd",
                   0,
                   v16,
                   0);
            if ( v6 >= 0 )
            {
              v11 = SysAllocString(L"__systemsecurity=@");
              if ( !v11 )
              {
LABEL_13:
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
                XVariant::~XVariant(&v19);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
LABEL_14:
                v6 = -2147024882;
                goto LABEL_20;
              }
              v12 = SysAllocString(L"SetSD");
              if ( !v12 )
              {
                SysFreeString(v11);
                goto LABEL_13;
              }
              v6 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, OLECHAR *, _QWORD, _QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 192LL))(
                     a2,
                     v11,
                     v12,
                     0,
                     0,
                     v18,
                     0,
                     0);
              SysFreeString(v11);
              SysFreeString(v12);
            }
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
          XVariant::~XVariant(&v19);
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  }
LABEL_20:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b6140  mov     [rsp-28h+arg_0], rbx
0x1800b6145  push    rbp
0x1800b6146  push    rsi
0x1800b6147  push    rdi
0x1800b6148  push    r14
0x1800b614a  push    r15
0x1800b614c  mov     rbp, rsp
0x1800b614f  sub     rsp, 80h
0x1800b6156  mov     rsi, rdx
0x1800b6159  mov     r14, rcx
0x1800b615c  test    rdx, rdx
0x1800b615f  jnz     short loc_1800B616B
0x1800b6161  mov     eax, 80004003h
0x1800b6166  jmp     loc_1800B63D7
0x1800b616b  lea     rcx, aSystemsecurity; "__systemsecurity"
0x1800b6172  mov     [rbp+var_30], 0
0x1800b617a  call    cs:__imp_SysAllocString
0x1800b6180  mov     rdi, rax
0x1800b6183  test    rax, rax
0x1800b6186  jz      loc_1800B6334
0x1800b618c  mov     rax, [rsi]
0x1800b618f  lea     rcx, [rbp+var_30]
0x1800b6193  mov     [rsp+80h+var_58], 0
0x1800b619c  xor     r9d, r9d
0x1800b619f  mov     [rsp+80h+var_60], rcx
0x1800b61a4  xor     r8d, r8d
0x1800b61a7  mov     rdx, rdi
0x1800b61aa  mov     rcx, rsi
0x1800b61ad  mov     rax, [rax+30h]
0x1800b61b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b61b6  mov     rcx, rdi; bstrString
0x1800b61b9  mov     ebx, eax
0x1800b61bb  call    cs:__imp_SysFreeString
0x1800b61c1  test    ebx, ebx
0x1800b61c3  js      loc_1800B63CC
0x1800b61c9  mov     rcx, [rbp+var_30]
0x1800b61cd  lea     r9, [rbp+arg_8]
0x1800b61d1  mov     [rbp+arg_8], 0
0x1800b61d9  lea     rdx, aSetsd; "SetSD"
0x1800b61e0  xor     r8d, r8d
0x1800b61e3  mov     [rsp+80h+var_60], 0
0x1800b61ec  mov     rax, [rcx]
0x1800b61ef  mov     rax, [rax+98h]
0x1800b61f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b61fb  mov     ebx, eax
0x1800b61fd  test    eax, eax
0x1800b61ff  js      loc_1800B63C3
0x1800b6205  mov     rcx, r14; pSecurityDescriptor
0x1800b6208  mov     [rbp+rgsabound.lLbound], 0
0x1800b620f  call    cs:__imp_GetSecurityDescriptorLength
0x1800b6215  mov     ecx, 11h; vt
0x1800b621a  mov     r15d, eax
0x1800b621d  lea     r8, [rbp+rgsabound]; rgsabound
0x1800b6221  mov     [rbp+rgsabound.cElements], r15d
0x1800b6225  lea     edx, [rcx-10h]; cDims
0x1800b6228  call    cs:__imp_SafeArrayCreate
0x1800b622e  mov     rdi, rax
0x1800b6231  test    rax, rax
0x1800b6234  jnz     short loc_1800B6249
0x1800b6236  lea     rcx, [rbp+arg_8]
0x1800b623a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b623f  mov     ebx, 80004005h
0x1800b6244  jmp     loc_1800B63CC
0x1800b6249  lea     rdx, [rbp+ppvData]; ppvData
0x1800b624d  mov     [rbp+ppvData], 0
0x1800b6255  mov     rcx, rdi; psa
0x1800b6258  call    cs:__imp_SafeArrayAccessData
0x1800b625e  mov     ebx, eax
0x1800b6260  test    eax, eax
0x1800b6262  js      loc_1800B63C3
0x1800b6268  mov     rcx, [rbp+ppvData]; void *
0x1800b626c  mov     r8, r15; Size
0x1800b626f  mov     rdx, r14; Src
0x1800b6272  call    memcpy_0
0x1800b6277  mov     rcx, rdi; psa
0x1800b627a  call    cs:__imp_SafeArrayUnaccessData
0x1800b6280  mov     ebx, eax
0x1800b6282  test    eax, eax
0x1800b6284  js      loc_1800B63C3
0x1800b628a  mov     rcx, [rbp+arg_8]
0x1800b628e  lea     r8, [rbp+arg_10]
0x1800b6292  xor     eax, eax
0x1800b6294  mov     [rbp+arg_10], 0
0x1800b629c  mov     [rbp+var_8], rax
0x1800b62a0  xorps   xmm0, xmm0
0x1800b62a3  movups  [rbp+var_18], xmm0
0x1800b62a7  lea     rax, [rbp+var_18]
0x1800b62ab  mov     qword ptr [rbp+var_18+8], rdi
0x1800b62af  mov     [rbp+arg_18], rax
0x1800b62b3  xor     edx, edx
0x1800b62b5  mov     eax, 2011h
0x1800b62ba  mov     word ptr [rbp+var_18], ax
0x1800b62be  mov     rax, [rcx]
0x1800b62c1  mov     rax, [rax+78h]
0x1800b62c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b62ca  mov     ebx, eax
0x1800b62cc  test    eax, eax
0x1800b62ce  js      loc_1800B63B1
0x1800b62d4  mov     rcx, [rbp+arg_10]
0x1800b62d8  lea     r9, [rbp+var_18]
0x1800b62dc  xor     r8d, r8d
0x1800b62df  mov     dword ptr [rsp+80h+var_60], 0
0x1800b62e7  lea     rdx, aSd; "sd"
0x1800b62ee  mov     rax, [rcx]
0x1800b62f1  mov     rax, [rax+28h]
0x1800b62f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b62fa  mov     ebx, eax
0x1800b62fc  test    eax, eax
0x1800b62fe  js      loc_1800B63B1
0x1800b6304  lea     rcx, aSystemsecurity_0; "__systemsecurity=@"
0x1800b630b  call    cs:__imp_SysAllocString
0x1800b6311  mov     rdi, rax
0x1800b6314  test    rax, rax
0x1800b6317  jnz     short loc_1800B633E
0x1800b6319  lea     rcx, [rbp+arg_10]
0x1800b631d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b6322  lea     rcx, [rbp+arg_18]; this
0x1800b6326  call    ??1XVariant@@QEAA@XZ; XVariant::~XVariant(void)
0x1800b632b  lea     rcx, [rbp+arg_8]
0x1800b632f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b6334  mov     ebx, 8007000Eh
0x1800b6339  jmp     loc_1800B63CC
0x1800b633e  lea     rcx, aSetsd; "SetSD"
0x1800b6345  call    cs:__imp_SysAllocString
0x1800b634b  mov     r14, rax
0x1800b634e  test    rax, rax
0x1800b6351  jnz     short loc_1800B635E
0x1800b6353  mov     rcx, rdi; bstrString
0x1800b6356  call    cs:__imp_SysFreeString
0x1800b635c  jmp     short loc_1800B6319
0x1800b635e  mov     rcx, [rbp+arg_10]
0x1800b6362  xor     r9d, r9d
0x1800b6365  mov     rax, [rsi]
0x1800b6368  mov     r8, r14
0x1800b636b  mov     [rsp+80h+var_48], 0
0x1800b6374  mov     rdx, rdi
0x1800b6377  mov     [rsp+80h+var_50], 0
0x1800b6380  mov     [rsp+80h+var_58], rcx
0x1800b6385  mov     rcx, rsi
0x1800b6388  mov     rax, [rax+0C0h]
0x1800b638f  mov     [rsp+80h+var_60], 0
0x1800b6398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b639d  mov     rcx, rdi; bstrString
0x1800b63a0  mov     ebx, eax
0x1800b63a2  call    cs:__imp_SysFreeString
0x1800b63a8  mov     rcx, r14; bstrString
0x1800b63ab  call    cs:__imp_SysFreeString
0x1800b63b1  lea     rcx, [rbp+arg_10]
0x1800b63b5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b63ba  lea     rcx, [rbp+arg_18]; this
0x1800b63be  call    ??1XVariant@@QEAA@XZ; XVariant::~XVariant(void)
0x1800b63c3  lea     rcx, [rbp+arg_8]
0x1800b63c7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b63cc  lea     rcx, [rbp+var_30]
0x1800b63d0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b63d5  mov     eax, ebx
0x1800b63d7  mov     rbx, [rsp+80h+arg_0]
0x1800b63df  add     rsp, 80h
0x1800b63e6  pop     r15
0x1800b63e8  pop     r14
0x1800b63ea  pop     rdi
0x1800b63eb  pop     rsi
0x1800b63ec  pop     rbp
0x1800b63ed  retn
```
