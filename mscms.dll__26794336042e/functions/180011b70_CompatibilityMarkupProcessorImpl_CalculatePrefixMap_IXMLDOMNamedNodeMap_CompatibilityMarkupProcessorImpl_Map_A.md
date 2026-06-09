# CompatibilityMarkupProcessorImpl::CalculatePrefixMap(IXMLDOMNamedNodeMap *,CompatibilityMarkupProcessorImpl::Map<ATL::CComBSTR,ATL::CComBSTR,25> * *)

- ea: `0x180011b70`
- end: `0x18001218f`
- name: `?CalculatePrefixMap@CompatibilityMarkupProcessorImpl@@AEAAJPEAUIXMLDOMNamedNodeMap@@PEAPEAU?$Map@VCComBSTR@ATL@@V12@$0BJ@@1@@Z`
- size: `1567`
- prototype: `__int64 __fastcall(__int64, __int64, char **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180010670`

## callees

- `0x180011b70`
- `0x180022d50`
- `0x18002e670`
- `0x18002ea84`
- `0x18002eac0`
- `0x18002f324`
- `0x18002ff70`
- `0x18004bed8`
- `0x1800815d4`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011cd9`
- `OLEAUT32!__imp_SysAllocString` at `0x180011d22`
- `OLEAUT32!__imp_SysAllocString` at `0x180011e61`
- `OLEAUT32!__imp_SysAllocString` at `0x180011cd9`
- `OLEAUT32!__imp_SysAllocString` at `0x180011d22`
- `OLEAUT32!__imp_SysAllocString` at `0x180011e61`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c61`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c95`
- `OLEAUT32!__imp_SysFreeString` at `0x180011cd0`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d75`
- `OLEAUT32!__imp_SysFreeString` at `0x180011e13`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ebc`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f1c`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f68`
- `OLEAUT32!__imp_SysFreeString` at `0x180011faa`
- `OLEAUT32!__imp_SysFreeString` at `0x180011fb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180011fc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180011fce`
- `OLEAUT32!__imp_SysFreeString` at `0x180012008`
- `OLEAUT32!__imp_SysFreeString` at `0x180012012`
- `OLEAUT32!__imp_SysFreeString` at `0x18001201d`
- `OLEAUT32!__imp_SysFreeString` at `0x180012071`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c61`
- `OLEAUT32!__imp_SysFreeString` at `0x180011c95`
- `OLEAUT32!__imp_SysFreeString` at `0x180011cd0`
- `OLEAUT32!__imp_SysFreeString` at `0x180011d75`
- `OLEAUT32!__imp_SysFreeString` at `0x180011e13`
- `OLEAUT32!__imp_SysFreeString` at `0x180011ebc`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f1c`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f68`
- `OLEAUT32!__imp_SysFreeString` at `0x180011faa`
- `OLEAUT32!__imp_SysFreeString` at `0x180011fb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180011fc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180011fce`
- `OLEAUT32!__imp_SysFreeString` at `0x180012008`
- `OLEAUT32!__imp_SysFreeString` at `0x180012012`
- `OLEAUT32!__imp_SysFreeString` at `0x18001201d`
- `OLEAUT32!__imp_SysFreeString` at `0x180012071`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180011ecf`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180011f2f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180011f7b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180011ecf`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180011f2f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180011f7b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180011eda`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180011f3a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180011f86`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180011eda`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180011f3a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180011f86`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180011d57`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180011ea7`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180011d57`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180011ea7`

## string_xrefs

- `0x180011c4e`: `xmlns`

## pseudocode

```c
__int64 __fastcall CompatibilityMarkupProcessorImpl::CalculatePrefixMap(__int64 a1, __int64 a2, char **a3)
{
  __int64 v3; // rbx
  char *v4; // r13
  int v5; // r14d
  char *v6; // rsi
  __int64 result; // rax
  char v8; // r15
  unsigned int v9; // r12d
  int v10; // ebx
  wchar_t *v11; // rbx
  wchar_t v12; // ax
  OLECHAR *v13; // rdi
  const OLECHAR *v14; // rbx
  OLECHAR *v15; // rbx
  char *v16; // rbx
  OLECHAR *v17; // rbx
  OLECHAR *v18; // rcx
  int v19; // eax
  int v20; // edx
  int v21; // r14d
  int v22; // eax
  OLECHAR *v23; // rcx
  BSTR v24; // rax
  UINT v25; // eax
  __int64 v26; // r14
  OLECHAR *v27; // rcx
  BSTR v28; // rax
  UINT v29; // eax
  __int64 v30; // r14
  OLECHAR *v31; // rcx
  BSTR v32; // rax
  UINT v33; // eax
  __int64 v34; // [rsp+30h] [rbp-48h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-40h] BYREF
  wchar_t *String2; // [rsp+40h] [rbp-38h] BYREF
  OLECHAR *v37; // [rsp+48h] [rbp-30h]
  char *v38; // [rsp+50h] [rbp-28h]
  OLECHAR *v39; // [rsp+58h] [rbp-20h]
  char *v40; // [rsp+60h] [rbp-18h]
  char v41; // [rsp+C0h] [rbp+48h]
  __int64 pExceptionObject; // [rsp+C8h] [rbp+50h] BYREF
  char **v43; // [rsp+D0h] [rbp+58h]
  int v44; // [rsp+D8h] [rbp+60h] BYREF

  v43 = a3;
  pExceptionObject = a2;
  v3 = a2;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v4 = *a3;
  v5 = 0;
  v6 = 0;
  v38 = 0;
  v44 = 0;
  result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 88LL))(a2, &v44);
  if ( (int)result < 0 )
    return result;
  v8 = 0;
  v41 = 0;
  v9 = 0;
  if ( v44 <= 0 )
  {
LABEL_83:
    *v43 = v4;
    return 0;
  }
  while ( 1 )
  {
    v34 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v3 + 80LL))(v3, v9, &v34);
    if ( v10 < 0 )
      goto LABEL_78;
    if ( !v34 )
    {
      v10 = -2147467259;
LABEL_78:
      if ( v34 )
        (*(void (**)(void))(*(_QWORD *)v34 + 16LL))();
      if ( v6 )
      {
        `eh vector destructor iterator'(
          v6,
          16,
          25,
          (void (__fastcall *)(char *))CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR>::~Pair<ATL::CComBSTR,ATL::CComBSTR>);
        operator delete(v6);
      }
      return (unsigned int)v10;
    }
    String2 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v34 + 56LL))(v34, &String2);
    if ( v10 < 0 )
    {
      SysFreeString(String2);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      if ( v6 )
        goto LABEL_72;
      return (unsigned int)v10;
    }
    v11 = String2;
    if ( wcsncmp_0(L"xmlns", String2, 5u) )
    {
      SysFreeString(v11);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      goto LABEL_67;
    }
    v12 = v11[5];
    if ( v12 != 58 && v12 )
    {
      SysFreeString(v11);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      goto LABEL_67;
    }
    v13 = 0;
    v37 = 0;
    if ( v12 == 58 )
    {
      v14 = v11 + 6;
      if ( v14 )
      {
        SysFreeString(0);
        v13 = SysAllocString(v14);
        v37 = v13;
        if ( !v13 )
          ATL::AtlThrowImpl(-2147024882);
      }
    }
    psz = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, OLECHAR **))(*(_QWORD *)v34 + 208LL))(v34, &psz);
    if ( v10 < 0 )
      break;
    if ( psz )
    {
      v15 = SysAllocString(psz);
      if ( !v15 )
        goto LABEL_86;
    }
    else
    {
      v15 = 0;
    }
    if ( *((int *)v4 + 100) <= 0 )
    {
LABEL_27:
      SysFreeString(v15);
LABEL_28:
      if ( !v8 )
      {
        v16 = (char *)operator new(0x198u);
        v40 = v16;
        `eh vector copy constructor iterator'(
          v16,
          v4,
          16,
          25,
          (void (*)(void *, void *))CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR>::Pair<ATL::CComBSTR,ATL::CComBSTR>);
        *((_DWORD *)v16 + 100) = *((_DWORD *)v4 + 100);
        v4 = v16;
        if ( v6 )
        {
          `eh vector destructor iterator'(
            v6,
            16,
            25,
            (void (__fastcall *)(char *))CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR>::~Pair<ATL::CComBSTR,ATL::CComBSTR>);
          operator delete(v6);
        }
        v6 = v16;
        v38 = v16;
        v41 = 1;
      }
      if ( psz )
      {
        v17 = SysAllocString(psz);
        v39 = v17;
        if ( !v17 )
LABEL_86:
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        v17 = 0;
        v39 = 0;
      }
      v21 = 0;
      v22 = *((_DWORD *)v4 + 100);
      if ( v22 > 0 )
      {
        while ( 1 )
        {
          if ( VarBstrCmp(*(BSTR *)&v4[16 * v21], v13, 0x400u, 0) == 1 )
          {
            v23 = *(OLECHAR **)&v4[16 * v21 + 8];
            if ( v23 != v17 )
            {
              SysFreeString(v23);
              if ( v17 )
              {
                v25 = SysStringByteLen(v17);
                v24 = SysAllocStringByteLen((LPCSTR)v17, v25);
              }
              else
              {
                v24 = 0;
              }
              *(_QWORD *)&v4[16 * v21 + 8] = v24;
              if ( v17 )
              {
                if ( !v24 )
                  break;
              }
            }
          }
          ++v21;
          v22 = *((_DWORD *)v4 + 100);
          if ( v21 >= v22 )
            goto LABEL_50;
        }
LABEL_88:
        ATL::AtlThrowImpl(-2147024882);
      }
LABEL_50:
      if ( v22 == 25 )
      {
        ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, -2147221483);
        throw (ATL::CAtlException *)&pExceptionObject;
      }
      v26 = 2LL * v22;
      v27 = *(OLECHAR **)&v4[16 * v22];
      if ( v27 != v13 )
      {
        SysFreeString(v27);
        if ( v13 )
        {
          v29 = SysStringByteLen(v13);
          v28 = SysAllocStringByteLen((LPCSTR)v13, v29);
        }
        else
        {
          v28 = 0;
        }
        *(_QWORD *)&v4[8 * v26] = v28;
        if ( v13 )
        {
          if ( !v28 )
            goto LABEL_88;
        }
      }
      v30 = 2LL * *((int *)v4 + 100);
      v31 = *(OLECHAR **)&v4[16 * *((int *)v4 + 100) + 8];
      if ( v31 != v17 )
      {
        SysFreeString(v31);
        if ( v17 )
        {
          v33 = SysStringByteLen(v17);
          v32 = SysAllocStringByteLen((LPCSTR)v17, v33);
        }
        else
        {
          v32 = 0;
        }
        *(_QWORD *)&v4[8 * v30 + 8] = v32;
        if ( v17 )
        {
          if ( !v32 )
            goto LABEL_88;
        }
      }
      ++*((_DWORD *)v4 + 100);
      SysFreeString(v17);
      v8 = v41;
      goto LABEL_64;
    }
    while ( VarBstrCmp(*(BSTR *)&v4[16 * v5], v15, 0x400u, 0) != 1 )
    {
      if ( ++v5 >= *((_DWORD *)v4 + 100) )
        goto LABEL_27;
    }
    SysFreeString(v15);
    if ( v5 == -1 )
      goto LABEL_28;
    v18 = psz;
    do
    {
      v19 = *(OLECHAR *)((char *)v18 + *(_QWORD *)&v4[16 * v5 + 8] - (_QWORD)psz);
      v20 = *v18 - v19;
      if ( v20 )
        break;
      ++v18;
    }
    while ( v19 );
    if ( v20 )
      goto LABEL_28;
LABEL_64:
    SysFreeString(psz);
    SysFreeString(v13);
    SysFreeString(String2);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v5 = 0;
LABEL_67:
    if ( (int)++v9 >= v44 )
      goto LABEL_83;
    v3 = pExceptionObject;
  }
  SysFreeString(psz);
  SysFreeString(v13);
  SysFreeString(String2);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v6 )
  {
LABEL_72:
    `eh vector destructor iterator'(
      v6,
      16,
      25,
      (void (__fastcall *)(char *))CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR>::~Pair<ATL::CComBSTR,ATL::CComBSTR>);
    operator delete(v6);
    return (unsigned int)v10;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011b70  mov     [rsp-40h+arg_10], r8
0x180011b75  mov     [rsp-40h+pExceptionObject], rdx
0x180011b7a  mov     [rsp-40h+arg_0], rcx
0x180011b7f  push    rbp
0x180011b80  push    rbx
0x180011b81  push    rsi
0x180011b82  push    rdi
0x180011b83  push    r12
0x180011b85  push    r13
0x180011b87  push    r14
0x180011b89  push    r15
0x180011b8b  mov     rbp, rsp
0x180011b8e  sub     rsp, 78h
0x180011b92  mov     rax, r8
0x180011b95  mov     rbx, rdx
0x180011b98  test    rdx, rdx
0x180011b9b  jz      loc_180012139
0x180011ba1  test    rax, rax
0x180011ba4  jz      loc_180012139
0x180011baa  mov     r13, [r8]
0x180011bad  xor     r14d, r14d
0x180011bb0  mov     esi, r14d
0x180011bb3  mov     [rbp+var_28], r14
0x180011bb7  mov     [rbp+arg_18], r14d
0x180011bbb  mov     rax, [rdx]
0x180011bbe  lea     rdx, [rbp+arg_18]
0x180011bc2  mov     rcx, rbx
0x180011bc5  mov     rax, [rax+58h]
0x180011bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bce  test    eax, eax
0x180011bd0  jns     short loc_180011BD7
0x180011bd2  jmp     loc_18001213E
0x180011bd7  xor     r15b, r15b
0x180011bda  mov     byte ptr [rbp+arg_0], r15b
0x180011bde  mov     r12d, r14d
0x180011be1  lea     rdi, ??1?$Pair@VCComBSTR@ATL@@V12@@CompatibilityMarkupProcessorImpl@@QEAA@XZ; CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR>::~Pair<ATL::CComBSTR,ATL::CComBSTR>(void)
0x180011be8  cmp     [rbp+arg_18], r14d
0x180011bec  jle     loc_180012107
0x180011bf2  mov     [rbp+var_48], r14
0x180011bf6  mov     rax, [rbx]
0x180011bf9  lea     r8, [rbp+var_48]
0x180011bfd  mov     edx, r12d
0x180011c00  mov     rcx, rbx
0x180011c03  mov     rax, [rax+50h]
0x180011c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c0c  mov     ebx, eax
0x180011c0e  mov     rcx, [rbp+var_48]
0x180011c12  test    eax, eax
0x180011c14  js      loc_1800120C2
0x180011c1a  test    rcx, rcx
0x180011c1d  jz      loc_1800120BD
0x180011c23  mov     [rbp+String2], r14
0x180011c27  mov     rax, [rcx]
0x180011c2a  lea     rdx, [rbp+String2]
0x180011c2e  mov     rax, [rax+38h]
0x180011c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c37  mov     ebx, eax
0x180011c39  test    eax, eax
0x180011c3b  js      loc_18001206D
0x180011c41  mov     r8d, 5; MaxCount
0x180011c47  mov     rbx, [rbp+String2]
0x180011c4b  mov     rdx, rbx; String2
0x180011c4e  lea     rcx, aXmlns; "xmlns"
0x180011c55  call    wcsncmp_0
0x180011c5a  test    eax, eax
0x180011c5c  jz      short loc_180011C83
0x180011c5e  mov     rcx, rbx; bstrString
0x180011c61  call    cs:__imp_SysFreeString
0x180011c67  nop
0x180011c68  mov     rcx, [rbp+var_48]
0x180011c6c  test    rcx, rcx
0x180011c6f  jz      short loc_180011C7E
0x180011c71  mov     rax, [rcx]
0x180011c74  mov     rax, [rax+10h]
0x180011c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c7d  nop
0x180011c7e  jmp     loc_180011FEE
0x180011c83  movzx   eax, word ptr [rbx+0Ah]
0x180011c87  cmp     ax, 3Ah ; ':'
0x180011c8b  jz      short loc_180011CB7
0x180011c8d  test    ax, ax
0x180011c90  jz      short loc_180011CB7
0x180011c92  mov     rcx, rbx; bstrString
0x180011c95  call    cs:__imp_SysFreeString
0x180011c9b  nop
0x180011c9c  mov     rcx, [rbp+var_48]
0x180011ca0  test    rcx, rcx
0x180011ca3  jz      short loc_180011CB2
0x180011ca5  mov     rax, [rcx]
0x180011ca8  mov     rax, [rax+10h]
0x180011cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb1  nop
0x180011cb2  jmp     loc_180011FEE
0x180011cb7  mov     rdi, r14
0x180011cba  mov     [rbp+var_30], r14
0x180011cbe  mov     ecx, 3Ah ; ':'
0x180011cc3  cmp     cx, ax
0x180011cc6  jnz     short loc_180011CEF
0x180011cc8  add     rbx, 0Ch
0x180011ccc  jz      short loc_180011CEF
0x180011cce  xor     ecx, ecx; bstrString
0x180011cd0  call    cs:__imp_SysFreeString
0x180011cd6  mov     rcx, rbx; psz
0x180011cd9  call    cs:__imp_SysAllocString
0x180011cdf  mov     rdi, rax
0x180011ce2  mov     [rbp+var_30], rax
0x180011ce6  test    rax, rax
0x180011ce9  jz      loc_18001215A
0x180011cef  mov     [rbp+psz], r14
0x180011cf3  mov     rcx, [rbp+var_48]
0x180011cf7  mov     rax, [rcx]
0x180011cfa  lea     rdx, [rbp+psz]
0x180011cfe  mov     rax, [rax+0D0h]
0x180011d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d0a  mov     ebx, eax
0x180011d0c  test    eax, eax
0x180011d0e  js      loc_180012004
0x180011d14  mov     rcx, [rbp+psz]; psz
0x180011d18  test    rcx, rcx
0x180011d1b  jnz     short loc_180011D22
0x180011d1d  mov     rbx, r14
0x180011d20  jmp     short loc_180011D34
0x180011d22  call    cs:__imp_SysAllocString
0x180011d28  mov     rbx, rax
0x180011d2b  test    rax, rax
0x180011d2e  jz      loc_18001214F
0x180011d34  cmp     dword ptr [r13+190h], 0
0x180011d3c  jle     short loc_180011D72
0x180011d3e  xchg    ax, ax
0x180011d40  movsxd  rcx, r14d
0x180011d43  add     rcx, rcx
0x180011d46  xor     r9d, r9d; dwFlags
0x180011d49  mov     r8d, 400h; lcid
0x180011d4f  mov     rdx, rbx; bstrRight
0x180011d52  mov     rcx, [r13+rcx*8+0]; bstrLeft
0x180011d57  call    cs:__imp_VarBstrCmp
0x180011d5d  cmp     eax, 1
0x180011d60  jz      loc_180011E10
0x180011d66  inc     r14d
0x180011d69  cmp     r14d, [r13+190h]
0x180011d70  jl      short loc_180011D40
0x180011d72  mov     rcx, rbx; bstrString
0x180011d75  call    cs:__imp_SysFreeString
0x180011d7b  test    r15b, r15b
0x180011d7e  jnz     short loc_180011DFF
0x180011d80  mov     ecx, 198h; Size
0x180011d85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011d8a  mov     rbx, rax
0x180011d8d  mov     [rbp+var_18], rax
0x180011d91  lea     r14, ??1?$Pair@VCComBSTR@ATL@@V12@@CompatibilityMarkupProcessorImpl@@QEAA@XZ; CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR>::~Pair<ATL::CComBSTR,ATL::CComBSTR>(void)
0x180011d98  mov     [rsp+78h+var_50], r14; void (*)(void *)
0x180011d9d  lea     rax, ??0?$Pair@VCComBSTR@ATL@@V12@@CompatibilityMarkupProcessorImpl@@QEAA@AEBU01@@Z; CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR>::Pair<ATL::CComBSTR,ATL::CComBSTR>(CompatibilityMarkupProcessorImpl::Pair<ATL::CComBSTR,ATL::CComBSTR> const &)
0x180011da4  mov     [rsp+78h+var_58], rax; void (*)(void *, void *)
0x180011da9  mov     r9d, 19h; unsigned __int64
0x180011daf  mov     r8d, 10h; unsigned __int64
0x180011db5  mov     rdx, r13; void *
0x180011db8  mov     rcx, rbx; void *
0x180011dbb  call    ??__C@YAXPEAX0_K1P6AX00@ZP6AX0@Z@Z; `eh vector copy constructor iterator'(void *,void *,unsigned __int64,unsigned __int64,void (*)(void *,void *),void (*)(void *))
0x180011dc0  mov     ecx, [r13+190h]
0x180011dc7  mov     [rbx+190h], ecx
0x180011dcd  mov     r13, rbx
0x180011dd0  test    rsi, rsi
0x180011dd3  jz      short loc_180011DF4
0x180011dd5  mov     r9, r14; void (*)(void *)
0x180011dd8  mov     edx, 10h; unsigned __int64
0x180011ddd  mov     r8d, 19h; unsigned __int64
0x180011de3  mov     rcx, rsi; void *
0x180011de6  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180011deb  nop
0x180011dec  mov     rcx, rsi; Block
0x180011def  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011df4  mov     rsi, rbx
0x180011df7  mov     [rbp+var_28], rbx
0x180011dfb  mov     byte ptr [rbp+arg_0], 1
0x180011dff  mov     rcx, [rbp+psz]; psz
0x180011e03  test    rcx, rcx
0x180011e06  jnz     short loc_180011E61
0x180011e08  xor     ebx, ebx
0x180011e0a  mov     [rbp+var_20], rbx
0x180011e0e  jmp     short loc_180011E77
0x180011e10  mov     rcx, rbx; bstrString
0x180011e13  call    cs:__imp_SysFreeString
0x180011e19  cmp     r14d, 0FFFFFFFFh
0x180011e1d  jz      loc_180011D7B
0x180011e23  movsxd  rax, r14d
0x180011e26  add     rax, rax
0x180011e29  mov     rcx, [rbp+psz]
0x180011e2d  mov     r8, [r13+rax*8+8]
0x180011e32  sub     r8, rcx
0x180011e35  nop     word ptr [rax+rax+00000000h]
0x180011e40  movzx   edx, word ptr [rcx]
0x180011e43  movzx   eax, word ptr [rcx+r8]
0x180011e48  sub     edx, eax
0x180011e4a  jnz     short loc_180011E54
0x180011e4c  add     rcx, 2
0x180011e50  test    eax, eax
0x180011e52  jnz     short loc_180011E40
0x180011e54  test    edx, edx
0x180011e56  jz      loc_180011FB5
0x180011e5c  jmp     loc_180011D7B
0x180011e61  call    cs:__imp_SysAllocString
0x180011e67  mov     rbx, rax
0x180011e6a  mov     [rbp+var_20], rax
0x180011e6e  test    rax, rax
0x180011e71  jz      loc_18001214F
0x180011e77  xor     r14d, r14d
0x180011e7a  mov     eax, [r13+190h]
0x180011e81  test    eax, eax
0x180011e83  jle     short loc_180011F03
0x180011e85  nop     word ptr [rax+rax+00000000h]
0x180011e90  movsxd  r15, r14d
0x180011e93  add     r15, r15
0x180011e96  xor     r9d, r9d; dwFlags
0x180011e99  mov     r8d, 400h; lcid
0x180011e9f  mov     rdx, rdi; bstrRight
0x180011ea2  mov     rcx, [r13+r15*8+0]; bstrLeft
0x180011ea7  call    cs:__imp_VarBstrCmp
0x180011ead  cmp     eax, 1
0x180011eb0  jnz     short loc_180011EF4
0x180011eb2  mov     rcx, [r13+r15*8+8]; bstrString
0x180011eb7  cmp     rcx, rbx
0x180011eba  jz      short loc_180011EF4
0x180011ebc  call    cs:__imp_SysFreeString
0x180011ec2  nop
0x180011ec3  test    rbx, rbx
0x180011ec6  jnz     short loc_180011ECC
0x180011ec8  xor     eax, eax
0x180011eca  jmp     short loc_180011EE1
0x180011ecc  mov     rcx, rbx; bstr
0x180011ecf  call    cs:__imp_SysStringByteLen
0x180011ed5  mov     edx, eax; len
0x180011ed7  mov     rcx, rbx; psz
0x180011eda  call    cs:__imp_SysAllocStringByteLen
0x180011ee0  nop
0x180011ee1  mov     [r13+r15*8+8], rax
0x180011ee6  test    rbx, rbx
0x180011ee9  jz      short loc_180011EF4
0x180011eeb  test    rax, rax
0x180011eee  jz      loc_180012165
0x180011ef4  inc     r14d
0x180011ef7  mov     eax, [r13+190h]
0x180011efe  cmp     r14d, eax
0x180011f01  jl      short loc_180011E90
0x180011f03  cmp     eax, 19h
0x180011f06  jz      loc_180012170
0x180011f0c  movsxd  r14, eax
0x180011f0f  add     r14, r14
0x180011f12  mov     rcx, [r13+r14*8+0]; bstrString
0x180011f17  cmp     rcx, rdi
0x180011f1a  jz      short loc_180011F54
0x180011f1c  call    cs:__imp_SysFreeString
0x180011f22  nop
0x180011f23  test    rdi, rdi
0x180011f26  jnz     short loc_180011F2C
0x180011f28  xor     eax, eax
0x180011f2a  jmp     short loc_180011F41
0x180011f2c  mov     rcx, rdi; bstr
0x180011f2f  call    cs:__imp_SysStringByteLen
0x180011f35  mov     edx, eax; len
0x180011f37  mov     rcx, rdi; psz
0x180011f3a  call    cs:__imp_SysAllocStringByteLen
0x180011f40  nop
0x180011f41  mov     [r13+r14*8+0], rax
0x180011f46  test    rdi, rdi
0x180011f49  jz      short loc_180011F54
0x180011f4b  test    rax, rax
0x180011f4e  jz      loc_180012165
0x180011f54  movsxd  r14, dword ptr [r13+190h]
0x180011f5b  add     r14, r14
0x180011f5e  mov     rcx, [r13+r14*8+8]; bstrString
0x180011f63  cmp     rcx, rbx
0x180011f66  jz      short loc_180011FA0
0x180011f68  call    cs:__imp_SysFreeString
0x180011f6e  nop
0x180011f6f  test    rbx, rbx
0x180011f72  jnz     short loc_180011F78
0x180011f74  xor     eax, eax
0x180011f76  jmp     short loc_180011F8D
0x180011f78  mov     rcx, rbx; bstr
0x180011f7b  call    cs:__imp_SysStringByteLen
0x180011f81  mov     edx, eax; len
0x180011f83  mov     rcx, rbx; psz
0x180011f86  call    cs:__imp_SysAllocStringByteLen
0x180011f8c  nop
0x180011f8d  mov     [r13+r14*8+8], rax
0x180011f92  test    rbx, rbx
0x180011f95  jz      short loc_180011FA0
0x180011f97  test    rax, rax
0x180011f9a  jz      loc_180012165
0x180011fa0  inc     dword ptr [r13+190h]
0x180011fa7  mov     rcx, rbx; bstrString
0x180011faa  call    cs:__imp_SysFreeString
0x180011fb0  movzx   r15d, byte ptr [rbp+arg_0]
0x180011fb5  mov     rcx, [rbp+psz]; bstrString
0x180011fb9  call    cs:__imp_SysFreeString
0x180011fbf  nop
0x180011fc0  mov     rcx, rdi; bstrString
0x180011fc3  call    cs:__imp_SysFreeString
0x180011fc9  nop
0x180011fca  mov     rcx, [rbp+String2]; bstrString
  ... truncated ...
```
