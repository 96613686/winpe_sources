# CApplicationWAPNodeProcessor::ProcessNode(IConfigManager2 *,IDomNode *)

- ea: `0x180022b90`
- end: `0x180022ed8`
- name: `?ProcessNode@CApplicationWAPNodeProcessor@@UEAAJPEAUIConfigManager2@@PEAUIDomNode@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(CApplicationWAPNodeProcessor *__hidden this, struct IConfigManager2 *, struct IDomNode *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001584`
- `0x1800110bc`
- `0x180014330`
- `0x180015174`
- `0x180022b90`
- `0x18002e4d4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180022e93`
- `OLEAUT32!__imp_SysFreeString` at `0x180022ea5`
- `OLEAUT32!__imp_SysFreeString` at `0x180022e93`
- `OLEAUT32!__imp_SysFreeString` at `0x180022ea5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022ceb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022ceb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022dcb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022dcb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180022d9e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180022d9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CApplicationWAPNodeProcessor::ProcessNode(
        CApplicationWAPNodeProcessor *this,
        struct IConfigManager2 *a2,
        struct IDomNode *a3)
{
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  LSTATUS ValueW; // eax
  int v10; // esi
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpValue; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v18; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR v19; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v20; // [rsp+80h] [rbp-80h] BYREF
  GUID pclsid; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR sz[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v23[108]; // [rsp+A4h] [rbp-5Ch] BYREF

  lpValue = 0;
  String2 = 0;
  v15 = 0;
  ppv = 0;
  *(_DWORD *)sz = 48;
  memset_0(v23, 0, 0x60u);
  pcbData = 100;
  pclsid = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    goto LABEL_24;
  }
  if ( !a3 )
  {
    v8 = -2147024809;
    goto LABEL_26;
  }
  v8 = (*(__int64 (__fastcall **)(struct IDomNode *, wchar_t **))(*(_QWORD *)a3 + 64LL))(a3, &String2);
  if ( v8 < 0 )
  {
LABEL_25:
    (*(void (__fastcall **)(struct IDomNode *, _QWORD))(*(_QWORD *)a3 + 24LL))(a3, (unsigned int)v8);
    goto LABEL_26;
  }
  if ( wcscmp_0(L"APPLICATION", String2) )
    goto LABEL_7;
  v8 = (*(__int64 (__fastcall **)(struct IDomNode *, const wchar_t *, __int64 *))(*(_QWORD *)a3 + 184LL))(
         a3,
         L"APPID",
         &v15);
  if ( v8 < 0 )
    goto LABEL_25;
  if ( !v15 )
  {
LABEL_7:
    v8 = -2147024809;
    goto LABEL_25;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *))(*(_QWORD *)v15 + 88LL))(v15, L"value", &lpValue);
  if ( v8 < 0 )
    goto LABEL_25;
  ValueW = RegGetValueW(HKEY_CLASSES_ROOT, L"APPLICATION", lpValue, 2u, 0, sz, &pcbData);
  if ( ValueW > 0 )
    v8 = (unsigned __int16)ValueW | 0x80070000;
  else
    v8 = ValueW;
  if ( v8 >= 0 )
  {
    v8 = CLSIDFromString(sz, &pclsid);
    if ( v8 < 0 )
      goto LABEL_25;
    v8 = CoCreateInstance(&pclsid, 0, 1u, &GUID_c5ad6fc0_df79_4813_a854_08ccaff5f314, &ppv);
    if ( v8 < 0 )
      goto LABEL_25;
    v10 = 1;
    v8 = (*(__int64 (__fastcall **)(LPVOID, struct IConfigManager2 *, struct IDomNode *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           a2,
           a3);
  }
  else
  {
    if ( ValueW != 2 )
      goto LABEL_25;
    v10 = 0;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, (unsigned int)v8);
    if ( (unsigned int)dword_18003E080 > 2 )
    {
      v18 = (wchar_t *)&word_180032B28;
      v19 = lpValue;
      v20 = String2;
      v12 = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v5,
        (unsigned int)word_1800374B2,
        v6,
        v7,
        (__int64)&v12,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v18);
    }
    v8 = 1;
  }
  if ( v8 >= 0 )
    goto LABEL_28;
  if ( !v10 )
  {
LABEL_24:
    if ( !a3 )
      goto LABEL_26;
    goto LABEL_25;
  }
LABEL_26:
  if ( (unsigned int)dword_18003E080 > 2 )
  {
    v20 = sz;
    v19 = lpValue;
    v18 = String2;
    v12 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v5,
      (unsigned int)word_18003753A,
      v6,
      v7,
      (__int64)&v12,
      (__int64)&v18,
      (__int64)&v19,
      (__int64)&v20);
  }
LABEL_28:
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppv);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v15);
  SysFreeString(String2);
  SysFreeString((BSTR)lpValue);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022b90  mov     [rsp-8+arg_0], rbx
0x180022b95  mov     [rsp-8+arg_18], rsi
0x180022b9a  push    rbp
0x180022b9b  push    rdi
0x180022b9c  push    r14
0x180022b9e  lea     rbp, [rsp-20h]
0x180022ba3  sub     rsp, 120h
0x180022baa  mov     rax, cs:__security_cookie
0x180022bb1  xor     rax, rsp
0x180022bb4  mov     [rbp+30h+var_20], rax
0x180022bb8  mov     rdi, r8
0x180022bbb  mov     r14, rdx
0x180022bbe  mov     [rsp+130h+lpValue], 0
0x180022bc7  mov     [rsp+130h+String2], 0
0x180022bd0  mov     [rsp+130h+var_D8], 0
0x180022bd9  mov     [rsp+130h+ppv], 0
0x180022be2  mov     dword ptr [rbp+30h+sz], 30h ; '0'
0x180022be9  xor     edx, edx; Val
0x180022beb  lea     r8d, [rdx+60h]; Size
0x180022bef  lea     rcx, [rbp+30h+var_8C]; void *
0x180022bf3  call    memset_0
0x180022bf8  mov     [rsp+130h+var_D0], 64h ; 'd'
0x180022c00  xorps   xmm0, xmm0
0x180022c03  movups  xmmword ptr [rbp+30h+pclsid.Data1], xmm0
0x180022c07  test    r14, r14
0x180022c0a  jnz     short loc_180022C16
0x180022c0c  mov     ebx, 80070057h
0x180022c11  jmp     loc_180022E03
0x180022c16  test    rdi, rdi
0x180022c19  jnz     short loc_180022C25
0x180022c1b  mov     ebx, 80070057h
0x180022c20  jmp     loc_180022E19
0x180022c25  mov     rax, [rdi]
0x180022c28  lea     rdx, [rsp+130h+String2]
0x180022c2d  mov     rcx, rdi
0x180022c30  mov     rax, [rax+40h]
0x180022c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c39  mov     ebx, eax
0x180022c3b  test    eax, eax
0x180022c3d  js      loc_180022E08
0x180022c43  mov     rdx, [rsp+130h+String2]; String2
0x180022c48  lea     rcx, aApplication; "APPLICATION"
0x180022c4f  call    wcscmp_0
0x180022c54  test    eax, eax
0x180022c56  jz      short loc_180022C62
0x180022c58  mov     ebx, 80070057h
0x180022c5d  jmp     loc_180022E08
0x180022c62  mov     rax, [rdi]
0x180022c65  lea     r8, [rsp+130h+var_D8]
0x180022c6a  lea     rdx, aAppid; "APPID"
0x180022c71  mov     rcx, rdi
0x180022c74  mov     rax, [rax+0B8h]
0x180022c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c80  mov     ebx, eax
0x180022c82  test    eax, eax
0x180022c84  js      loc_180022E08
0x180022c8a  mov     rcx, [rsp+130h+var_D8]
0x180022c8f  test    rcx, rcx
0x180022c92  jz      short loc_180022C58
0x180022c94  mov     rax, [rcx]
0x180022c97  lea     r8, [rsp+130h+lpValue]
0x180022c9c  lea     rdx, aValue; "value"
0x180022ca3  mov     rax, [rax+58h]
0x180022ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cac  mov     ebx, eax
0x180022cae  test    eax, eax
0x180022cb0  js      loc_180022E08
0x180022cb6  lea     rax, [rsp+130h+var_D0]
0x180022cbb  mov     [rsp+130h+pcbData], rax; pcbData
0x180022cc0  lea     rax, [rbp+30h+sz]
0x180022cc4  mov     [rsp+130h+pvData], rax; pvData
0x180022cc9  mov     [rsp+130h+pdwType], 0; pdwType
0x180022cd2  mov     r9d, 2; dwFlags
0x180022cd8  mov     r8, [rsp+130h+lpValue]; lpValue
0x180022cdd  lea     rdx, aApplication; "APPLICATION"
0x180022ce4  mov     rcx, 0FFFFFFFF80000000h; hkey
0x180022ceb  call    cs:__imp_RegGetValueW
0x180022cf2  nop     dword ptr [rax+rax+00h]
0x180022cf7  test    eax, eax
0x180022cf9  jg      short loc_180022CFF
0x180022cfb  mov     ebx, eax
0x180022cfd  jmp     short loc_180022D08
0x180022cff  movzx   ebx, ax
0x180022d02  or      ebx, 80070000h
0x180022d08  test    ebx, ebx
0x180022d0a  jns     loc_180022D96
0x180022d10  cmp     eax, 2
0x180022d13  jnz     loc_180022E08
0x180022d19  xor     esi, esi
0x180022d1b  mov     rcx, [rsp+130h+var_D8]
0x180022d20  mov     rax, [rcx]
0x180022d23  mov     edx, ebx
0x180022d25  mov     rax, [rax+18h]
0x180022d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d2e  mov     eax, cs:dword_18003E080
0x180022d34  cmp     eax, 2
0x180022d37  jbe     short loc_180022D8F
0x180022d39  lea     rax, word_180032B28
0x180022d40  mov     [rsp+130h+var_C0], rax
0x180022d45  mov     rax, [rsp+130h+lpValue]
0x180022d4a  mov     [rsp+130h+var_B8], rax
0x180022d4f  mov     rax, [rsp+130h+String2]
0x180022d54  mov     [rbp+30h+var_B0], rax
0x180022d58  mov     [rsp+130h+var_F0], ebx
0x180022d5c  lea     rax, [rsp+130h+var_C0]
0x180022d61  mov     [rsp+130h+var_F8], rax
0x180022d66  lea     rax, [rsp+130h+var_B8]
0x180022d6b  mov     [rsp+130h+pcbData], rax
0x180022d70  lea     rax, [rbp+30h+var_B0]
0x180022d74  mov     [rsp+130h+pvData], rax
0x180022d79  lea     rax, [rsp+130h+var_F0]
0x180022d7e  mov     [rsp+130h+pdwType], rax
0x180022d83  lea     rdx, word_1800374B2
0x180022d8a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180022d8f  mov     ebx, 1
0x180022d94  jmp     short loc_180022DFB
0x180022d96  lea     rdx, [rbp+30h+pclsid]; pclsid
0x180022d9a  lea     rcx, [rbp+30h+sz]; lpsz
0x180022d9e  call    cs:__imp_CLSIDFromString
0x180022da5  nop     dword ptr [rax+rax+00h]
0x180022daa  mov     ebx, eax
0x180022dac  test    eax, eax
0x180022dae  js      short loc_180022E08
0x180022db0  lea     rax, [rsp+130h+ppv]
0x180022db5  mov     [rsp+130h+pdwType], rax; ppv
0x180022dba  lea     r9, _GUID_c5ad6fc0_df79_4813_a854_08ccaff5f314; riid
0x180022dc1  xor     edx, edx; pUnkOuter
0x180022dc3  lea     r8d, [rdx+1]; dwClsContext
0x180022dc7  lea     rcx, [rbp+30h+pclsid]; rclsid
0x180022dcb  call    cs:__imp_CoCreateInstance
0x180022dd2  nop     dword ptr [rax+rax+00h]
0x180022dd7  mov     ebx, eax
0x180022dd9  test    eax, eax
0x180022ddb  js      short loc_180022E08
0x180022ddd  mov     esi, 1
0x180022de2  mov     rcx, [rsp+130h+ppv]
0x180022de7  mov     rax, [rcx]
0x180022dea  mov     r8, rdi
0x180022ded  mov     rdx, r14
0x180022df0  mov     rax, [rax+18h]
0x180022df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022df9  mov     ebx, eax
0x180022dfb  test    ebx, ebx
0x180022dfd  jns     short loc_180022E78
0x180022dff  test    esi, esi
0x180022e01  jnz     short loc_180022E19
0x180022e03  test    rdi, rdi
0x180022e06  jz      short loc_180022E19
0x180022e08  mov     rax, [rdi]
0x180022e0b  mov     edx, ebx
0x180022e0d  mov     rcx, rdi
0x180022e10  mov     rax, [rax+18h]
0x180022e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e19  mov     eax, cs:dword_18003E080
0x180022e1f  cmp     eax, 2
0x180022e22  jbe     short loc_180022E78
0x180022e24  lea     rax, [rbp+30h+sz]
0x180022e28  mov     [rbp+30h+var_B0], rax
0x180022e2c  mov     rax, [rsp+130h+lpValue]
0x180022e31  mov     [rsp+130h+var_B8], rax
0x180022e36  mov     rax, [rsp+130h+String2]
0x180022e3b  mov     [rsp+130h+var_C0], rax
0x180022e40  mov     [rsp+130h+var_F0], ebx
0x180022e44  lea     rax, [rbp+30h+var_B0]
0x180022e48  mov     [rsp+130h+var_F8], rax
0x180022e4d  lea     rax, [rsp+130h+var_B8]
0x180022e52  mov     [rsp+130h+pcbData], rax
0x180022e57  lea     rax, [rsp+130h+var_C0]
0x180022e5c  mov     [rsp+130h+pvData], rax
0x180022e61  lea     rax, [rsp+130h+var_F0]
0x180022e66  mov     [rsp+130h+pdwType], rax
0x180022e6b  lea     rdx, word_18003753A
0x180022e72  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180022e77  nop
0x180022e78  lea     rcx, [rsp+130h+ppv]
0x180022e7d  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180022e82  nop
0x180022e83  lea     rcx, [rsp+130h+var_D8]
0x180022e88  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180022e8d  nop
0x180022e8e  mov     rcx, [rsp+130h+String2]; bstrString
0x180022e93  call    cs:__imp_SysFreeString
0x180022e9a  nop     dword ptr [rax+rax+00h]
0x180022e9f  nop
0x180022ea0  mov     rcx, [rsp+130h+lpValue]; bstrString
0x180022ea5  call    cs:__imp_SysFreeString
0x180022eac  nop     dword ptr [rax+rax+00h]
0x180022eb1  mov     eax, ebx
0x180022eb3  mov     rcx, [rbp+30h+var_20]
0x180022eb7  xor     rcx, rsp; StackCookie
0x180022eba  call    __security_check_cookie
0x180022ebf  lea     r11, [rsp+130h+var_10]
0x180022ec7  mov     rbx, [r11+20h]
0x180022ecb  mov     rsi, [r11+38h]
0x180022ecf  mov     rsp, r11
0x180022ed2  pop     r14
0x180022ed4  pop     rdi
0x180022ed5  pop     rbp
0x180022ed6  retn
```
