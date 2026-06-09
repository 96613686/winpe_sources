# ParsedSchema::~ParsedSchema(void)

- ea: `0x180093d94`
- end: `0x180093e75`
- name: `??1ParsedSchema@@UEAA@XZ`
- size: `225`
- prototype: `void __fastcall(ParsedSchema *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180093ec0`

## callees

- `0x180084298`
- `0x180093d94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180093e19`
- `OLEAUT32!__imp_SysFreeString` at `0x180093e3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180093e44`
- `OLEAUT32!__imp_SysFreeString` at `0x180093e4e`
- `OLEAUT32!__imp_SysFreeString` at `0x180093e3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180093e44`
- `OLEAUT32!__imp_SysFreeString` at `0x180093e4e`

## pseudocode

```c
void __fastcall ParsedSchema::~ParsedSchema(ParsedSchema *this)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 i; // rsi
  unsigned __int64 *v4; // rdi
  unsigned __int64 j; // rsi

  v1 = (unsigned __int64 *)((char *)this + 88);
  if ( *((_QWORD *)this + 10) )
  {
    for ( i = 0; i < *v1; ++i )
      ATL::CComPtrBase<ParsedSemanticTypeList>::~CComPtrBase<ParsedSemanticTypeList>(*((_QWORD *)this + 10) + 8 * i);
    CoTaskMemFree(*((LPVOID *)this + 10));
    *((_QWORD *)this + 10) = 0;
  }
  *v1 = 0;
  v4 = (unsigned __int64 *)((char *)this + 56);
  *((_QWORD *)this + 13) = 0;
  if ( *((_QWORD *)this + 6) )
  {
    for ( j = 0; j < *v4; ++j )
      ATL::CComPtrBase<ParsedSemanticTypeList>::~CComPtrBase<ParsedSemanticTypeList>(*((_QWORD *)this + 6) + 8 * j);
    CoTaskMemFree(*((LPVOID *)this + 6));
    *((_QWORD *)this + 6) = 0;
  }
  *v4 = 0;
  *((_QWORD *)this + 9) = 0;
  SysFreeString(*((BSTR *)this + 4));
  SysFreeString(*((BSTR *)this + 3));
  SysFreeString(*((BSTR *)this + 2));
  *(_QWORD *)this = &RefCountedParsedData<ParsedPropertyDescription>::`vftable';
  _InterlockedDecrement(&g_cRefThisDll);
}

```

## disassembly

```asm
0x180093d94  mov     [rsp+arg_0], rbx
0x180093d99  mov     [rsp+arg_8], rsi
0x180093d9e  push    rdi
0x180093d9f  sub     rsp, 20h
0x180093da3  cmp     qword ptr [rcx+50h], 0
0x180093da8  lea     rdi, [rcx+58h]
0x180093dac  mov     rbx, rcx
0x180093daf  jz      short loc_180093DDF
0x180093db1  xor     esi, esi
0x180093db3  cmp     [rdi], rsi
0x180093db6  jbe     short loc_180093DCD
0x180093db8  mov     rax, [rbx+50h]
0x180093dbc  lea     rcx, [rax+rsi*8]
0x180093dc0  call    ??1?$CComPtrBase@UParsedSemanticTypeList@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ParsedSemanticTypeList>::~CComPtrBase<ParsedSemanticTypeList>(void)
0x180093dc5  inc     rsi
0x180093dc8  cmp     rsi, [rdi]
0x180093dcb  jb      short loc_180093DB8
0x180093dcd  mov     rcx, [rbx+50h]; pv
0x180093dd1  call    cs:__imp_CoTaskMemFree
0x180093dd7  mov     qword ptr [rbx+50h], 0
0x180093ddf  mov     qword ptr [rdi], 0
0x180093de6  lea     rdi, [rbx+38h]
0x180093dea  mov     qword ptr [rbx+68h], 0
0x180093df2  cmp     qword ptr [rbx+30h], 0
0x180093df7  jz      short loc_180093E27
0x180093df9  xor     esi, esi
0x180093dfb  cmp     [rdi], rsi
0x180093dfe  jbe     short loc_180093E15
0x180093e00  mov     rax, [rbx+30h]
0x180093e04  lea     rcx, [rax+rsi*8]
0x180093e08  call    ??1?$CComPtrBase@UParsedSemanticTypeList@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ParsedSemanticTypeList>::~CComPtrBase<ParsedSemanticTypeList>(void)
0x180093e0d  inc     rsi
0x180093e10  cmp     rsi, [rdi]
0x180093e13  jb      short loc_180093E00
0x180093e15  mov     rcx, [rbx+30h]; pv
0x180093e19  call    cs:__imp_CoTaskMemFree
0x180093e1f  mov     qword ptr [rbx+30h], 0
0x180093e27  mov     qword ptr [rdi], 0
0x180093e2e  mov     qword ptr [rbx+48h], 0
0x180093e36  mov     rcx, [rbx+20h]; bstrString
0x180093e3a  call    cs:__imp_SysFreeString
0x180093e40  mov     rcx, [rbx+18h]; bstrString
0x180093e44  call    cs:__imp_SysFreeString
0x180093e4a  mov     rcx, [rbx+10h]; bstrString
0x180093e4e  call    cs:__imp_SysFreeString
0x180093e54  mov     rsi, [rsp+28h+arg_8]
0x180093e59  lea     rax, ??_7?$RefCountedParsedData@UParsedPropertyDescription@@@@6B@; const RefCountedParsedData<ParsedPropertyDescription>::`vftable'
0x180093e60  mov     [rbx], rax
0x180093e63  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180093e6a  mov     rbx, [rsp+28h+arg_0]
0x180093e6f  add     rsp, 20h
0x180093e73  pop     rdi
0x180093e74  retn
```
