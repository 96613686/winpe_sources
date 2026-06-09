# InitXMLDocWithString(ushort * const,IXMLDOMDocument2 * *)

- ea: `0x140038db8`
- end: `0x14003905a`
- name: `?InitXMLDocWithString@@YAJQEAGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `674`
- prototype: `__int64 __fastcall(unsigned __int16 *const, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400393ac`

## callees

- `0x140034ce4`
- `0x140038db8`
- `0x14004d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140038e05`
- `ole32!CoCreateInstance` at `0x140038e05`
- `OLEAUT32!__imp_VariantClear` at `0x140038e8b`
- `OLEAUT32!__imp_VariantClear` at `0x140038ee8`
- `OLEAUT32!__imp_VariantClear` at `0x140038f47`
- `OLEAUT32!__imp_VariantClear` at `0x140038e8b`
- `OLEAUT32!__imp_VariantClear` at `0x140038ee8`
- `OLEAUT32!__imp_VariantClear` at `0x140038f47`

## string_xrefs

- `0x140038e1f`: `InitXMLDocWithString`
- `0x140038e2b`: `base\diagnosis\ra\racommon\src\xmlutils.cpp`

## pseudocode

```c
__int64 __fastcall InitXMLDocWithString(unsigned __int16 *const a1, struct IXMLDOMDocument2 **a2)
{
  HRESULT v4; // eax
  CEventLogger *v5; // rcx
  signed int v6; // ebx
  __int64 v7; // rax
  CEventLogger *v8; // rcx
  __int64 v9; // rax
  CEventLogger *v10; // rcx
  __int64 v11; // rax
  CEventLogger *v12; // rcx
  struct IXMLDOMDocument2 *v13; // rax
  LPVOID ppv; // [rsp+30h] [rbp-50h] BYREF
  __int64 v16; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG v18; // [rsp+60h] [rbp-20h] BYREF
  __int16 v19; // [rsp+C0h] [rbp+40h] BYREF
  int v20; // [rsp+C8h] [rbp+48h] BYREF

  v19 = 0;
  v16 = 0;
  ppv = 0;
  v20 = 0;
  v4 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, &ppv);
  v6 = v4;
  if ( v4 < 0 )
  {
    CEventLogger::LogError(
      v5,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      0x3Eu,
      L"InitXMLDocWithString",
      v4);
    goto LABEL_19;
  }
  v7 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = -1;
  v18 = pvarg;
  v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v7 + 640))(ppv, L"ProhibitDTD", &v18);
  VariantClear(&pvarg);
  if ( v6 < 0 )
  {
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      0x40u,
      L"InitXMLDocWithString",
      v6);
    goto LABEL_19;
  }
  v9 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v18 = pvarg;
  v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v9 + 640))(ppv, L"AllowXsltScript", &v18);
  VariantClear(&pvarg);
  if ( v6 < 0 )
  {
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      0x41u,
      L"InitXMLDocWithString",
      v6);
    goto LABEL_19;
  }
  v11 = *(_QWORD *)ppv;
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v18 = pvarg;
  v6 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(v11 + 640))(
         ppv,
         L"AllowDocumentFunction",
         &v18);
  VariantClear(&pvarg);
  if ( v6 < 0 )
  {
    CEventLogger::LogError(
      v12,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\xmlutils.cpp",
      0x42u,
      L"InitXMLDocWithString",
      v6);
    goto LABEL_19;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 560LL))(ppv, 0);
    if ( v6 >= 0 )
    {
      if ( (*(int (__fastcall **)(LPVOID, unsigned __int16 *const, __int16 *))(*(_QWORD *)ppv + 520LL))(ppv, a1, &v19) < 0
        || !v19 )
      {
LABEL_18:
        v6 = -2147467259;
        goto LABEL_19;
      }
      v6 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 480LL))(ppv, &v16);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 56LL))(v16, &v20);
        if ( v6 >= 0 )
        {
          if ( !v20 )
          {
            v13 = (struct IXMLDOMDocument2 *)ppv;
            ppv = 0;
            *a2 = v13;
            goto LABEL_19;
          }
          goto LABEL_18;
        }
      }
    }
  }
LABEL_19:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140038db8  mov     [rsp-28h+arg_0], rbx
0x140038dbd  push    rbp
0x140038dbe  push    rsi
0x140038dbf  push    rdi
0x140038dc0  push    r14
0x140038dc2  push    r15
0x140038dc4  mov     rbp, rsp
0x140038dc7  sub     rsp, 80h
0x140038dce  mov     rdi, rdx
0x140038dd1  mov     rsi, rcx
0x140038dd4  xor     r14d, r14d
0x140038dd7  mov     [rbp+arg_10], r14w
0x140038ddc  mov     [rbp+var_48], r14
0x140038de0  mov     [rbp+var_50], r14
0x140038de4  mov     [rbp+arg_18], r14d
0x140038de8  lea     rax, [rbp+var_50]
0x140038dec  mov     [rsp+80h+ppv], rax; ppv
0x140038df1  lea     r9, IID_IXMLDOMDocument; riid
0x140038df8  xor     edx, edx; pUnkOuter
0x140038dfa  lea     r8d, [r14+1]; dwClsContext
0x140038dfe  lea     rcx, CLSID_DOMDocument60; rclsid
0x140038e05  call    cs:__imp_CoCreateInstance
0x140038e0c  nop     dword ptr [rax+rax+00h]
0x140038e11  mov     ebx, eax
0x140038e13  test    eax, eax
0x140038e15  jns     short loc_140038E43
0x140038e17  mov     [rsp+80h+var_58], eax; unsigned int
0x140038e1b  lea     r9d, [r14+3Eh]; unsigned int
0x140038e1f  lea     rax, aInitxmldocwith; "InitXMLDocWithString"
0x140038e26  mov     [rsp+80h+ppv], rax; unsigned __int16 *
0x140038e2b  lea     r8, aBaseDiagnosisR_25; "base\\diagnosis\\ra\\racommon\\src\\xml"...
0x140038e32  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140038e39  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140038e3e  jmp     loc_140039014
0x140038e43  mov     rcx, [rbp+var_50]
0x140038e47  mov     rax, [rcx]
0x140038e4a  mov     r15d, 0Bh
0x140038e50  mov     word ptr [rbp+pvarg], r15w
0x140038e55  or      edx, 0FFFFFFFFh
0x140038e58  mov     word ptr [rbp+pvarg+8], dx
0x140038e5c  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140038e60  movaps  [rbp+var_20], xmm0
0x140038e64  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140038e69  movsd   [rbp+var_10], xmm1
0x140038e6e  lea     r8, [rbp+var_20]
0x140038e72  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x140038e79  mov     rax, [rax+280h]
0x140038e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038e85  mov     ebx, eax
0x140038e87  lea     rcx, [rbp+pvarg]; pvarg
0x140038e8b  call    cs:__imp_VariantClear
0x140038e92  nop     dword ptr [rax+rax+00h]
0x140038e97  test    ebx, ebx
0x140038e99  jns     short loc_140038EA8
0x140038e9b  mov     [rsp+80h+var_58], ebx
0x140038e9f  lea     r9d, [r15+35h]
0x140038ea3  jmp     loc_140038E1F
0x140038ea8  mov     rcx, [rbp+var_50]
0x140038eac  mov     rax, [rcx]
0x140038eaf  mov     word ptr [rbp+pvarg], r15w
0x140038eb4  mov     word ptr [rbp+pvarg+8], r14w
0x140038eb9  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140038ebd  movaps  [rbp+var_20], xmm0
0x140038ec1  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140038ec6  movsd   [rbp+var_10], xmm1
0x140038ecb  lea     r8, [rbp+var_20]
0x140038ecf  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x140038ed6  mov     rax, [rax+280h]
0x140038edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038ee2  mov     ebx, eax
0x140038ee4  lea     rcx, [rbp+pvarg]; pvarg
0x140038ee8  call    cs:__imp_VariantClear
0x140038eef  nop     dword ptr [rax+rax+00h]
0x140038ef4  test    ebx, ebx
0x140038ef6  jns     short loc_140038F07
0x140038ef8  mov     [rsp+80h+var_58], ebx
0x140038efc  mov     r9d, 41h ; 'A'
0x140038f02  jmp     loc_140038E1F
0x140038f07  mov     rcx, [rbp+var_50]
0x140038f0b  mov     rax, [rcx]
0x140038f0e  mov     word ptr [rbp+pvarg], r15w
0x140038f13  mov     word ptr [rbp+pvarg+8], r14w
0x140038f18  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140038f1c  movaps  [rbp+var_20], xmm0
0x140038f20  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x140038f25  movsd   [rbp+var_10], xmm1
0x140038f2a  lea     r8, [rbp+var_20]
0x140038f2e  lea     rdx, aAllowdocumentf; "AllowDocumentFunction"
0x140038f35  mov     rax, [rax+280h]
0x140038f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f41  mov     ebx, eax
0x140038f43  lea     rcx, [rbp+pvarg]; pvarg
0x140038f47  call    cs:__imp_VariantClear
0x140038f4e  nop     dword ptr [rax+rax+00h]
0x140038f53  test    ebx, ebx
0x140038f55  jns     short loc_140038F66
0x140038f57  mov     [rsp+80h+var_58], ebx
0x140038f5b  mov     r9d, 42h ; 'B'
0x140038f61  jmp     loc_140038E1F
0x140038f66  mov     rcx, [rbp+var_50]
0x140038f6a  mov     rax, [rcx]
0x140038f6d  xor     edx, edx
0x140038f6f  mov     rax, [rax+1F8h]
0x140038f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f7b  mov     ebx, eax
0x140038f7d  test    eax, eax
0x140038f7f  js      loc_140039014
0x140038f85  mov     rcx, [rbp+var_50]
0x140038f89  mov     rax, [rcx]
0x140038f8c  xor     edx, edx
0x140038f8e  mov     rax, [rax+230h]
0x140038f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038f9a  mov     ebx, eax
0x140038f9c  test    eax, eax
0x140038f9e  js      short loc_140039014
0x140038fa0  mov     rcx, [rbp+var_50]
0x140038fa4  mov     rax, [rcx]
0x140038fa7  lea     r8, [rbp+arg_10]
0x140038fab  mov     rdx, rsi
0x140038fae  mov     rax, [rax+208h]
0x140038fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038fba  test    eax, eax
0x140038fbc  js      short loc_14003900F
0x140038fbe  cmp     [rbp+arg_10], r14w
0x140038fc3  jz      short loc_14003900F
0x140038fc5  mov     rcx, [rbp+var_50]
0x140038fc9  mov     rax, [rcx]
0x140038fcc  lea     rdx, [rbp+var_48]
0x140038fd0  mov     rax, [rax+1E0h]
0x140038fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038fdc  mov     ebx, eax
0x140038fde  test    eax, eax
0x140038fe0  js      short loc_140039014
0x140038fe2  mov     rcx, [rbp+var_48]
0x140038fe6  mov     rax, [rcx]
0x140038fe9  lea     rdx, [rbp+arg_18]
0x140038fed  mov     rax, [rax+38h]
0x140038ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038ff6  mov     ebx, eax
0x140038ff8  test    eax, eax
0x140038ffa  js      short loc_140039014
0x140038ffc  cmp     [rbp+arg_18], r14d
0x140039000  jnz     short loc_14003900F
0x140039002  mov     rax, [rbp+var_50]
0x140039006  mov     [rbp+var_50], r14
0x14003900a  mov     [rdi], rax
0x14003900d  jmp     short loc_140039014
0x14003900f  mov     ebx, 80004005h
0x140039014  mov     rcx, [rbp+var_50]
0x140039018  test    rcx, rcx
0x14003901b  jz      short loc_14003902A
0x14003901d  mov     rax, [rcx]
0x140039020  mov     rax, [rax+10h]
0x140039024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039029  nop
0x14003902a  mov     rcx, [rbp+var_48]
0x14003902e  test    rcx, rcx
0x140039031  jz      short loc_140039040
0x140039033  mov     rax, [rcx]
0x140039036  mov     rax, [rax+10h]
0x14003903a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003903f  nop
0x140039040  mov     eax, ebx
0x140039042  mov     rbx, [rsp+80h+arg_0]
0x14003904a  add     rsp, 80h
0x140039051  pop     r15
0x140039053  pop     r14
0x140039055  pop     rdi
0x140039056  pop     rsi
0x140039057  pop     rbp
0x140039058  retn
```
