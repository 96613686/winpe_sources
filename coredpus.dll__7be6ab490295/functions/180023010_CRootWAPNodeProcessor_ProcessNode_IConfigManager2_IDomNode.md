# CRootWAPNodeProcessor::ProcessNode(IConfigManager2 *,IDomNode *)

- ea: `0x180023010`
- end: `0x1800233aa`
- name: `?ProcessNode@CRootWAPNodeProcessor@@UEAAJPEAUIConfigManager2@@PEAUIDomNode@@@Z`
- size: `922`
- prototype: `__int64 __fastcall(CRootWAPNodeProcessor *__hidden this, struct IConfigManager2 *, struct IDomNode *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800012b0`
- `0x180001390`
- `0x1800034d0`
- `0x1800110bc`
- `0x180014330`
- `0x180015174`
- `0x180023010`
- `0x180023b0c`
- `0x18002e4d4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180023141`
- `OLEAUT32!__imp_SysFreeString` at `0x180023365`
- `OLEAUT32!__imp_SysFreeString` at `0x180023377`
- `OLEAUT32!__imp_SysFreeString` at `0x180023141`
- `OLEAUT32!__imp_SysFreeString` at `0x180023365`
- `OLEAUT32!__imp_SysFreeString` at `0x180023377`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800231b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800231b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023271`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023271`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002321e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002321e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRootWAPNodeProcessor::ProcessNode(
        CRootWAPNodeProcessor *this,
        struct IConfigManager2 *a2,
        struct IDomNode *a3)
{
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  signed int v8; // ebx
  unsigned int v9; // esi
  LSTATUS ValueW; // eax
  int v11; // ecx
  __int64 v12; // rdx
  HRESULT v13; // eax
  LPVOID v14; // rcx
  HRESULT v15; // eax
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR *v21; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *String2; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR *v24; // [rsp+78h] [rbp-88h] BYREF
  BSTR v25; // [rsp+80h] [rbp-80h] BYREF
  GUID pclsid; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR sz[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v28[108]; // [rsp+A4h] [rbp-5Ch] BYREF

  String2 = 0;
  bstrString = 0;
  v17 = 0;
  v18 = 0;
  ppv = 0;
  *(_DWORD *)sz = 48;
  memset_0(v28, 0, 0x60u);
  pcbData = 0;
  pclsid = 0;
  if ( !a2 || !a3 )
    goto LABEL_2;
  v8 = (*(__int64 (__fastcall **)(struct IDomNode *, wchar_t **))(*(_QWORD *)a3 + 40LL))(a3, &String2);
  if ( v8 < 0 )
  {
LABEL_29:
    if ( (unsigned int)dword_18003E080 > 2 )
    {
      LODWORD(v21) = v8;
      v24 = sz;
      v25 = bstrString;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v5,
        (unsigned int)byte_1800375F5,
        v6,
        v7,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v21);
    }
    goto LABEL_31;
  }
  if ( wcscmp_0(L"wap-provisioningdoc", String2) )
  {
LABEL_2:
    v8 = -2147024809;
    goto LABEL_29;
  }
  v8 = (*(__int64 (__fastcall **)(struct IDomNode *, unsigned int *))(*(_QWORD *)a3 + 200LL))(a3, &v17);
  if ( v8 < 0 )
    goto LABEL_29;
  v9 = 0;
  if ( v17 )
  {
    while ( 1 )
    {
      ATL::CComPtrBase<IDomNode>::Release(&v18);
      v8 = (*(__int64 (__fastcall **)(struct IDomNode *, _QWORD, __int64 *))(*(_QWORD *)a3 + 192LL))(a3, v9, &v18);
      if ( v8 < 0 )
        break;
      if ( !v18 )
      {
        v8 = -2147024882;
        break;
      }
      SysFreeString(bstrString);
      bstrString = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v18 + 64LL))(v18, &bstrString);
      if ( v8 < 0 )
        break;
      pcbData = 100;
      ValueW = RegGetValueW(HKEY_CLASSES_ROOT, bstrString, L"WAPNodeProcessor", 2u, 0, sz, &pcbData);
      v8 = ValueW;
      if ( ValueW > 0 )
        v8 = (unsigned __int16)ValueW | 0x80070000;
      v12 = (unsigned int)v8;
      if ( v8 < 0 )
        goto LABEL_25;
      if ( (unsigned int)dword_18003E080 > 5 )
      {
        v21 = sz;
        v24 = bstrString;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v11,
          (unsigned int)&word_18003757E,
          v6,
          v7,
          (__int64)&v24,
          (__int64)&v21);
      }
      v13 = CLSIDFromString(sz, &pclsid);
      v12 = (unsigned int)v13;
      v8 = v13;
      if ( v13 < 0 )
        goto LABEL_25;
      v14 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v14 + 16LL))(v14, (unsigned int)v13);
      }
      v15 = CoCreateInstance(&pclsid, 0, 1u, &GUID_c5ad6fc0_df79_4813_a854_08ccaff5f314, &ppv);
      v12 = (unsigned int)v15;
      v8 = v15;
      if ( v15 < 0 )
      {
LABEL_25:
        v5 = v18;
        if ( v18 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 24LL))(v18, v12);
        break;
      }
      v8 = (*(__int64 (__fastcall **)(LPVOID, struct IConfigManager2 *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, a2, v18);
      if ( (unsigned int)dword_18003E080 > 5 )
      {
        LODWORD(v21) = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (int)&dword_18003E080,
          (int)word_1800376BA,
          v6,
          v7,
          (__int64)&v21);
      }
      if ( v8 < 0 )
        goto LABEL_29;
      if ( ++v9 >= v17 )
        goto LABEL_31;
    }
    if ( v8 < 0 )
      goto LABEL_29;
  }
LABEL_31:
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppv);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v18);
  SysFreeString(bstrString);
  SysFreeString(String2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180023010  mov     [rsp-8+arg_0], rbx
0x180023015  mov     [rsp-8+arg_18], rsi
0x18002301a  push    rbp
0x18002301b  push    rdi
0x18002301c  push    r14
0x18002301e  lea     rbp, [rsp-20h]
0x180023023  sub     rsp, 120h
0x18002302a  mov     rax, cs:__security_cookie
0x180023031  xor     rax, rsp
0x180023034  mov     [rbp+30h+var_20], rax
0x180023038  mov     rdi, r8
0x18002303b  mov     r14, rdx
0x18002303e  mov     [rsp+130h+String2], 0
0x180023047  mov     [rsp+130h+bstrString], 0
0x180023050  mov     [rsp+130h+var_F0], 0
0x180023058  mov     [rsp+130h+var_E8], 0
0x180023061  mov     [rsp+130h+ppv], 0
0x18002306a  mov     dword ptr [rbp+30h+sz], 30h ; '0'
0x180023071  xor     edx, edx; Val
0x180023073  lea     r8d, [rdx+60h]; Size
0x180023077  lea     rcx, [rbp+30h+var_8C]; void *
0x18002307b  call    memset_0
0x180023080  mov     [rsp+130h+var_D8], 0
0x180023088  xorps   xmm0, xmm0
0x18002308b  movups  xmmword ptr [rbp+30h+pclsid.Data1], xmm0
0x18002308f  test    r14, r14
0x180023092  jnz     short loc_18002309E
0x180023094  mov     ebx, 80070057h
0x180023099  jmp     loc_1800232FF
0x18002309e  test    rdi, rdi
0x1800230a1  jz      short loc_180023094
0x1800230a3  mov     rax, [rdi]
0x1800230a6  lea     rdx, [rsp+130h+String2]
0x1800230ab  mov     rcx, rdi
0x1800230ae  mov     rax, [rax+28h]
0x1800230b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230b7  mov     ebx, eax
0x1800230b9  test    eax, eax
0x1800230bb  js      loc_1800232FF
0x1800230c1  mov     rdx, [rsp+130h+String2]; String2
0x1800230c6  lea     rcx, aWapProvisionin_0; "wap-provisioningdoc"
0x1800230cd  call    wcscmp_0
0x1800230d2  test    eax, eax
0x1800230d4  jnz     short loc_180023094
0x1800230d6  mov     rax, [rdi]
0x1800230d9  lea     rdx, [rsp+130h+var_F0]
0x1800230de  mov     rcx, rdi
0x1800230e1  mov     rax, [rax+0C8h]
0x1800230e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230ed  mov     ebx, eax
0x1800230ef  test    eax, eax
0x1800230f1  js      loc_1800232FF
0x1800230f7  xor     esi, esi
0x1800230f9  cmp     [rsp+130h+var_F0], esi
0x1800230fd  jbe     loc_18002334A
0x180023103  lea     rcx, [rsp+130h+var_E8]
0x180023108  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x18002310d  mov     rax, [rdi]
0x180023110  lea     r8, [rsp+130h+var_E8]
0x180023115  mov     edx, esi
0x180023117  mov     rcx, rdi
0x18002311a  mov     rax, [rax+0C0h]
0x180023121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023126  mov     ebx, eax
0x180023128  test    eax, eax
0x18002312a  js      loc_1800232FB
0x180023130  cmp     [rsp+130h+var_E8], 0
0x180023136  jz      loc_1800232F6
0x18002313c  mov     rcx, [rsp+130h+bstrString]; bstrString
0x180023141  call    cs:__imp_SysFreeString
0x180023148  nop     dword ptr [rax+rax+00h]
0x18002314d  mov     [rsp+130h+bstrString], 0
0x180023156  mov     rcx, [rsp+130h+var_E8]
0x18002315b  mov     rax, [rcx]
0x18002315e  lea     rdx, [rsp+130h+bstrString]
0x180023163  mov     rax, [rax+40h]
0x180023167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002316c  mov     ebx, eax
0x18002316e  test    eax, eax
0x180023170  js      loc_1800232FB
0x180023176  mov     [rsp+130h+var_D8], 64h ; 'd'
0x18002317e  lea     rax, [rsp+130h+var_D8]
0x180023183  mov     [rsp+130h+pcbData], rax; pcbData
0x180023188  lea     rax, [rbp+30h+sz]
0x18002318c  mov     [rsp+130h+pvData], rax; pvData
0x180023191  mov     [rsp+130h+pdwType], 0; pdwType
0x18002319a  mov     r9d, 2; dwFlags
0x1800231a0  lea     r8, aWapnodeprocess; "WAPNodeProcessor"
0x1800231a7  mov     rdx, [rsp+130h+bstrString]; lpSubKey
0x1800231ac  mov     rcx, 0FFFFFFFF80000000h; hkey
0x1800231b3  call    cs:__imp_RegGetValueW
0x1800231ba  nop     dword ptr [rax+rax+00h]
0x1800231bf  mov     ebx, eax
0x1800231c1  test    eax, eax
0x1800231c3  jle     short loc_1800231CE
0x1800231c5  movzx   ebx, ax
0x1800231c8  or      ebx, 80070000h
0x1800231ce  mov     edx, ebx
0x1800231d0  test    ebx, ebx
0x1800231d2  js      loc_1800232DE
0x1800231d8  mov     eax, cs:dword_18003E080
0x1800231de  cmp     eax, 5
0x1800231e1  jbe     short loc_180023216
0x1800231e3  lea     rax, [rbp+30h+sz]
0x1800231e7  mov     [rsp+130h+var_D0], rax
0x1800231ec  mov     rax, [rsp+130h+bstrString]
0x1800231f1  mov     [rsp+130h+var_B8], rax
0x1800231f6  lea     rax, [rsp+130h+var_D0]
0x1800231fb  mov     [rsp+130h+pvData], rax
0x180023200  lea     rax, [rsp+130h+var_B8]
0x180023205  mov     [rsp+130h+pdwType], rax
0x18002320a  lea     rdx, word_18003757E
0x180023211  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180023216  lea     rdx, [rbp+30h+pclsid]; pclsid
0x18002321a  lea     rcx, [rbp+30h+sz]; lpsz
0x18002321e  call    cs:__imp_CLSIDFromString
0x180023225  nop     dword ptr [rax+rax+00h]
0x18002322a  mov     edx, eax
0x18002322c  mov     ebx, eax
0x18002322e  test    eax, eax
0x180023230  js      loc_1800232DE
0x180023236  mov     rcx, [rsp+130h+ppv]
0x18002323b  test    rcx, rcx
0x18002323e  jz      short loc_180023256
0x180023240  mov     [rsp+130h+ppv], 0
0x180023249  mov     rax, [rcx]
0x18002324c  mov     rax, [rax+10h]
0x180023250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023255  nop
0x180023256  lea     rax, [rsp+130h+ppv]
0x18002325b  mov     [rsp+130h+pdwType], rax; ppv
0x180023260  lea     r9, _GUID_c5ad6fc0_df79_4813_a854_08ccaff5f314; riid
0x180023267  xor     edx, edx; pUnkOuter
0x180023269  lea     r8d, [rdx+1]; dwClsContext
0x18002326d  lea     rcx, [rbp+30h+pclsid]; rclsid
0x180023271  call    cs:__imp_CoCreateInstance
0x180023278  nop     dword ptr [rax+rax+00h]
0x18002327d  mov     edx, eax
0x18002327f  mov     ebx, eax
0x180023281  test    eax, eax
0x180023283  js      short loc_1800232DE
0x180023285  mov     rcx, [rsp+130h+ppv]
0x18002328a  mov     rax, [rcx]
0x18002328d  mov     r8, [rsp+130h+var_E8]
0x180023292  mov     rdx, r14
0x180023295  mov     rax, [rax+18h]
0x180023299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002329e  mov     ebx, eax
0x1800232a0  mov     eax, cs:dword_18003E080
0x1800232a6  cmp     eax, 5
0x1800232a9  jbe     short loc_1800232CC
0x1800232ab  mov     dword ptr [rsp+130h+var_D0], ebx
0x1800232af  lea     rax, [rsp+130h+var_D0]
0x1800232b4  mov     [rsp+130h+pdwType], rax
0x1800232b9  lea     rdx, word_1800376BA
0x1800232c0  lea     rcx, dword_18003E080
0x1800232c7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800232cc  test    ebx, ebx
0x1800232ce  js      short loc_1800232FF
0x1800232d0  inc     esi
0x1800232d2  cmp     esi, [rsp+130h+var_F0]
0x1800232d6  jb      loc_180023103
0x1800232dc  jmp     short loc_18002334A
0x1800232de  mov     rcx, [rsp+130h+var_E8]
0x1800232e3  test    rcx, rcx
0x1800232e6  jz      short loc_1800232FB
0x1800232e8  mov     rax, [rcx]
0x1800232eb  mov     rax, [rax+18h]
0x1800232ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232f4  jmp     short loc_1800232FB
0x1800232f6  mov     ebx, 8007000Eh
0x1800232fb  test    ebx, ebx
0x1800232fd  jns     short loc_18002334A
0x1800232ff  mov     eax, cs:dword_18003E080
0x180023305  cmp     eax, 2
0x180023308  jbe     short loc_18002334A
0x18002330a  mov     dword ptr [rsp+130h+var_D0], ebx
0x18002330e  lea     rax, [rbp+30h+sz]
0x180023312  mov     [rsp+130h+var_B8], rax
0x180023317  mov     rax, [rsp+130h+bstrString]
0x18002331c  mov     [rbp+30h+var_B0], rax
0x180023320  lea     rax, [rsp+130h+var_D0]
0x180023325  mov     [rsp+130h+pcbData], rax
0x18002332a  lea     rax, [rsp+130h+var_B8]
0x18002332f  mov     [rsp+130h+pvData], rax
0x180023334  lea     rax, [rbp+30h+var_B0]
0x180023338  mov     [rsp+130h+pdwType], rax
0x18002333d  lea     rdx, byte_1800375F5
0x180023344  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180023349  nop
0x18002334a  lea     rcx, [rsp+130h+ppv]
0x18002334f  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180023354  nop
0x180023355  lea     rcx, [rsp+130h+var_E8]
0x18002335a  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002335f  nop
0x180023360  mov     rcx, [rsp+130h+bstrString]; bstrString
0x180023365  call    cs:__imp_SysFreeString
0x18002336c  nop     dword ptr [rax+rax+00h]
0x180023371  nop
0x180023372  mov     rcx, [rsp+130h+String2]; bstrString
0x180023377  call    cs:__imp_SysFreeString
0x18002337e  nop     dword ptr [rax+rax+00h]
0x180023383  mov     eax, ebx
0x180023385  mov     rcx, [rbp+30h+var_20]
0x180023389  xor     rcx, rsp; StackCookie
0x18002338c  call    __security_check_cookie
0x180023391  lea     r11, [rsp+130h+var_10]
0x180023399  mov     rbx, [r11+20h]
0x18002339d  mov     rsi, [r11+38h]
0x1800233a1  mov     rsp, r11
0x1800233a4  pop     r14
0x1800233a6  pop     rdi
0x1800233a7  pop     rbp
0x1800233a8  retn
```
