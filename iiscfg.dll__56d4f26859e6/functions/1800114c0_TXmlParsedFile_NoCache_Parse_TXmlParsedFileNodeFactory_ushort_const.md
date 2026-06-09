# TXmlParsedFile_NoCache::Parse(TXmlParsedFileNodeFactory &,ushort const *)

- ea: `0x1800114c0`
- end: `0x180011618`
- name: `?Parse@TXmlParsedFile_NoCache@@UEAAJAEAVTXmlParsedFileNodeFactory@@PEBG@Z`
- size: `344`
- prototype: `__int64 __fastcall(TXmlParsedFile_NoCache *__hidden this, struct TXmlParsedFileNodeFactory *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180017e84`

## callees

- `0x180001f70`
- `0x1800114c0`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800115db`
- `ole32!CoTaskMemFree` at `0x1800115db`
- `ole32!CoTaskMemAlloc` at `0x1800114f4`
- `ole32!CoTaskMemAlloc` at `0x1800114f4`

## pseudocode

```c
__int64 __fastcall TXmlParsedFile_NoCache::Parse(
        TXmlParsedFile_NoCache *this,
        struct TXmlParsedFileNodeFactory *a2,
        const unsigned __int16 *a3)
{
  LPVOID v3; // rax
  __int64 (__fastcall **v8)(struct TXmlParsedFileNodeFactory *, GUID *, _QWORD, __int64, GUID *, __int64 *); // rax
  int v9; // ebx
  __int64 v10; // [rsp+40h] [rbp-20h] BYREF
  GUID v11; // [rsp+48h] [rbp-18h] BYREF

  v3 = (LPVOID)*((_QWORD *)this + 9);
  if ( !v3 )
  {
    v3 = CoTaskMemAlloc(0x4000u);
    *((_QWORD *)this + 9) = v3;
    if ( !v3 )
      return 2147942414LL;
  }
  *((_QWORD *)this + 7) = v3;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 8) = a2;
  v8 = *(__int64 (__fastcall ***)(struct TXmlParsedFileNodeFactory *, GUID *, _QWORD, __int64, GUID *, __int64 *))a2;
  v10 = 0;
  v11 = TMSXMLBase::m_CLSID_XMLParser30;
  v9 = (*v8)(a2, &v11, 0, 1, &IID_IXMLParser, &v10);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, TXmlParsedFile_NoCache *))(*(_QWORD *)v10 + 24LL))(v10, this);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 224LL))(v10, 16);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD))(*(_QWORD *)v10 + 112LL))(
               v10,
               0,
               a3,
               0);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 192LL))(v10, 0xFFFFFFFFLL);
          CoTaskMemFree(*((LPVOID *)this + 9));
          *((_QWORD *)this + 9) = 0;
          *((_QWORD *)this + 7) = 0;
        }
      }
    }
  }
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(&v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800114c0  mov     [rsp-18h+arg_18], rbx
0x1800114c5  push    rbp
0x1800114c6  push    rsi
0x1800114c7  push    rdi
0x1800114c8  mov     rbp, rsp
0x1800114cb  sub     rsp, 60h
0x1800114cf  mov     rax, cs:__security_cookie
0x1800114d6  xor     rax, rsp
0x1800114d9  mov     [rbp+var_8], rax
0x1800114dd  mov     rax, [rcx+48h]
0x1800114e1  mov     rsi, r8
0x1800114e4  mov     rbx, rdx
0x1800114e7  mov     rdi, rcx
0x1800114ea  test    rax, rax
0x1800114ed  jnz     short loc_18001150D
0x1800114ef  mov     ecx, 4000h; cb
0x1800114f4  call    cs:__imp_CoTaskMemAlloc
0x1800114fa  mov     [rdi+48h], rax
0x1800114fe  test    rax, rax
0x180011501  jnz     short loc_18001150D
0x180011503  mov     eax, 8007000Eh
0x180011508  jmp     loc_1800115FC
0x18001150d  movups  xmm0, xmmword ptr cs:?m_CLSID_XMLParser30@TMSXMLBase@@1U_GUID@@A.Data1; _GUID TMSXMLBase::m_CLSID_XMLParser30 ...
0x180011514  mov     [rdi+38h], rax
0x180011518  lea     rcx, [rbp+var_20]
0x18001151c  mov     [rsp+60h+var_38], rcx
0x180011521  lea     rdx, [rbp+var_18]
0x180011525  mov     dword ptr [rdi+30h], 0
0x18001152c  lea     rcx, IID_IXMLParser
0x180011533  mov     [rdi+40h], rbx
0x180011537  mov     r9d, 1
0x18001153d  mov     rax, [rbx]
0x180011540  xor     r8d, r8d
0x180011543  mov     [rsp+60h+var_40], rcx
0x180011548  mov     rcx, rbx
0x18001154b  mov     [rbp+var_20], 0
0x180011553  movdqu  [rbp+var_18], xmm0
0x180011558  mov     rax, [rax]
0x18001155b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011560  mov     ebx, eax
0x180011562  test    eax, eax
0x180011564  js      loc_1800115F1
0x18001156a  mov     rcx, [rbp+var_20]
0x18001156e  mov     rdx, rdi
0x180011571  mov     rax, [rcx]
0x180011574  mov     rax, [rax+18h]
0x180011578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001157d  mov     ebx, eax
0x18001157f  test    eax, eax
0x180011581  js      short loc_1800115F1
0x180011583  mov     rcx, [rbp+var_20]
0x180011587  mov     edx, 10h
0x18001158c  mov     rax, [rcx]
0x18001158f  mov     rax, [rax+0E0h]
0x180011596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001159b  mov     ebx, eax
0x18001159d  test    eax, eax
0x18001159f  js      short loc_1800115F1
0x1800115a1  mov     rcx, [rbp+var_20]
0x1800115a5  xor     r9d, r9d
0x1800115a8  mov     r8, rsi
0x1800115ab  xor     edx, edx
0x1800115ad  mov     rax, [rcx]
0x1800115b0  mov     rax, [rax+70h]
0x1800115b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115b9  mov     ebx, eax
0x1800115bb  test    eax, eax
0x1800115bd  js      short loc_1800115F1
0x1800115bf  mov     rcx, [rbp+var_20]
0x1800115c3  or      edx, 0FFFFFFFFh
0x1800115c6  mov     rax, [rcx]
0x1800115c9  mov     rax, [rax+0C0h]
0x1800115d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115d5  mov     rcx, [rdi+48h]; pv
0x1800115d9  mov     ebx, eax
0x1800115db  call    cs:__imp_CoTaskMemFree
0x1800115e1  mov     qword ptr [rdi+48h], 0
0x1800115e9  mov     qword ptr [rdi+38h], 0
0x1800115f1  lea     rcx, [rbp+var_20]
0x1800115f5  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800115fa  mov     eax, ebx
0x1800115fc  mov     rcx, [rbp+var_8]
0x180011600  xor     rcx, rsp; StackCookie
0x180011603  call    __security_check_cookie
0x180011608  mov     rbx, [rsp+60h+arg_18]
0x180011610  add     rsp, 60h
0x180011614  pop     rdi
0x180011615  pop     rsi
0x180011616  pop     rbp
0x180011617  retn
```
