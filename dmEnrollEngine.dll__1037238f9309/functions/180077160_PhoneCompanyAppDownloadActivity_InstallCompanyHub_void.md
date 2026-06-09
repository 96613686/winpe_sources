# PhoneCompanyAppDownloadActivity::InstallCompanyHub(void)

- ea: `0x180077160`
- end: `0x18007744c`
- name: `?InstallCompanyHub@PhoneCompanyAppDownloadActivity@@AEAAJXZ`
- size: `748`
- prototype: `__int64 __fastcall(PhoneCompanyAppDownloadActivity *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800770a0`

## callees

- `0x18000de50`
- `0x18000e508`
- `0x18002e1a0`
- `0x180030f99`
- `0x18003708c`
- `0x18004e4b8`
- `0x1800770b8`
- `0x180077160`
- `0x18007b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800771eb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800771eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007726e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007726e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800773d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800773d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800773e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800773e1`
- `OLEAUT32!__imp_SysAllocString` at `0x180077306`
- `OLEAUT32!__imp_SysAllocString` at `0x18007731f`
- `OLEAUT32!__imp_SysAllocString` at `0x180077306`
- `OLEAUT32!__imp_SysAllocString` at `0x18007731f`
- `OLEAUT32!__imp_SysFreeString` at `0x18007722c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800773ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800773f8`
- `OLEAUT32!__imp_SysFreeString` at `0x180077403`
- `OLEAUT32!__imp_SysFreeString` at `0x18007740e`
- `OLEAUT32!__imp_SysFreeString` at `0x18007722c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800773ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800773f8`
- `OLEAUT32!__imp_SysFreeString` at `0x180077403`
- `OLEAUT32!__imp_SysFreeString` at `0x18007740e`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall PhoneCompanyAppDownloadActivity::InstallCompanyHub(PhoneCompanyAppDownloadActivity *this)
{
  BSTR v1; // rbx
  OLECHAR *v2; // rdi
  __int128 v3; // xmm6
  HRESULT EnterpriseId; // esi
  wchar_t *v5; // rsi
  unsigned int v6; // eax
  unsigned int v7; // edx
  OLECHAR *v8; // rcx
  const OLECHAR *v9; // rax
  const OLECHAR *v10; // rax
  wchar_t *String; // [rsp+58h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-71h] BYREF
  __int64 v14; // [rsp+68h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-61h] BYREF
  wchar_t *EndPtr[2]; // [rsp+78h] [rbp-59h] BYREF
  int v17; // [rsp+88h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-41h] BYREF
  BSTR v19; // [rsp+98h] [rbp-39h] BYREF
  BSTR v20; // [rsp+A0h] [rbp-31h] BYREF
  BSTR v21; // [rsp+A8h] [rbp-29h] BYREF
  __int128 v22; // [rsp+B8h] [rbp-19h] BYREF
  __int128 v23; // [rsp+C8h] [rbp-9h] BYREF
  GUID Buf1; // [rsp+D8h] [rbp+7h] BYREF

  ppv = 0;
  v14 = 0;
  v23 = 0;
  v19 = 0;
  bstrString = 0;
  v1 = 0;
  v20 = 0;
  v2 = 0;
  v21 = 0;
  pv = 0;
  v17 = 0;
  Buf1 = GUID_NULL;
  String = 0;
  v3 = 0;
  EnterpriseId = PhoneCompanyAppDownloadActivity::GetEnterpriseId(this, &String);
  if ( !EnterpriseId )
  {
    EndPtr[0] = 0;
    v5 = String;
    v6 = wcstoul(String, EndPtr, 10);
    if ( v5 == EndPtr[0] )
    {
      EnterpriseId = -2147467259;
    }
    else
    {
      EnterpriseId = 0;
      *(_OWORD *)EndPtr = 0;
      LODWORD(EndPtr[0]) = v6;
      v3 = *(_OWORD *)EndPtr;
    }
  }
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&String);
  if ( EnterpriseId >= 0 )
  {
    LODWORD(String) = 0;
    EnterpriseId = AutoCoInitialize::CoInitializeEx((AutoCoInitialize *)&String, v7);
    if ( EnterpriseId >= 0 )
    {
      EnterpriseId = CoCreateInstance(
                       &GUID_c63261e4_6052_41ff_b919_496fecf4c4e5,
                       0,
                       4u,
                       &GUID_d52ee9f5_41da_4df2_8c6e_b19a23654c93,
                       &ppv);
      if ( EnterpriseId >= 0 )
      {
        *(_OWORD *)EndPtr = v3;
        EnterpriseId = (*(__int64 (__fastcall **)(LPVOID, wchar_t **, __int64 *))(*(_QWORD *)ppv + 72LL))(
                         ppv,
                         EndPtr,
                         &v14);
        if ( EnterpriseId >= 0 )
        {
          EnterpriseId = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 64LL))(v14, &v19);
          if ( EnterpriseId >= 0 )
          {
            EnterpriseId = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 72LL))(v14, &bstrString);
            if ( EnterpriseId >= 0 )
            {
              EnterpriseId = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v14 + 56LL))(v14, &v23);
              if ( EnterpriseId >= 0 )
              {
                v9 = SysAllocString(&wszURI);
                ATL::CComBSTR::operator=(&v21, v9);
                v10 = SysAllocString(&wszURI);
                ATL::CComBSTR::operator=(&v20, v10);
                *(_OWORD *)EndPtr = v3;
                v22 = v23;
                v1 = v20;
                v2 = v21;
                EnterpriseId = (*(__int64 (__fastcall **)(LPVOID, BSTR, BSTR, BSTR, __int128 *, wchar_t **, BSTR, _DWORD, GUID *))(*(_QWORD *)ppv + 104LL))(
                                 ppv,
                                 v19,
                                 v21,
                                 bstrString,
                                 &v22,
                                 EndPtr,
                                 v20,
                                 0,
                                 &Buf1);
                if ( EnterpriseId >= 0 )
                {
                  if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
                  {
                    v22 = v3;
                    EnterpriseId = (*(__int64 (__fastcall **)(LPVOID, __int128 *, LPVOID *, int *))(*(_QWORD *)ppv
                                                                                                  + 120LL))(
                                     ppv,
                                     &v22,
                                     &pv,
                                     &v17);
                    if ( EnterpriseId < 0 )
                      EnterpriseId = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( (_DWORD)String )
      CoUninitialize();
    CoTaskMemFree(pv);
    pv = 0;
    SysFreeString(v2);
    v8 = v1;
  }
  else
  {
    CoTaskMemFree(pv);
    pv = 0;
    SysFreeString(0);
    v8 = 0;
  }
  SysFreeString(v8);
  SysFreeString(bstrString);
  SysFreeString(v19);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v14);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&ppv);
  return (unsigned int)EnterpriseId;
}

```

## disassembly

```asm
0x180077160  mov     rax, rsp
0x180077163  push    rbp
0x180077164  push    rbx
0x180077165  push    rsi
0x180077166  push    rdi
0x180077167  push    r14
0x180077169  lea     rbp, [rax-5Fh]
0x18007716d  sub     rsp, 100h
0x180077174  movaps  xmmword ptr [rax-38h], xmm6
0x180077178  mov     rax, cs:__security_cookie
0x18007717f  xor     rax, rsp
0x180077182  mov     [rbp+57h+var_40], rax
0x180077186  xor     r14d, r14d
0x180077189  mov     [rbp+57h+var_B8], r14
0x18007718d  mov     [rbp+57h+var_C0], r14
0x180077191  xorps   xmm0, xmm0
0x180077194  movups  [rbp+57h+var_60], xmm0
0x180077198  mov     [rbp+57h+var_90], r14
0x18007719c  mov     [rbp+57h+bstrString], r14
0x1800771a0  mov     ebx, r14d
0x1800771a3  mov     [rbp+57h+var_88], rbx
0x1800771a7  mov     edi, r14d
0x1800771aa  mov     [rbp+57h+var_80], r14
0x1800771ae  mov     [rbp+57h+pv], r14
0x1800771b2  mov     [rbp+57h+var_A0], r14d
0x1800771b6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800771bd  movdqu  [rbp+57h+Buf1], xmm0
0x1800771c2  mov     [rbp+57h+String], r14
0x1800771c6  xorps   xmm6, xmm6
0x1800771c9  lea     rdx, [rbp+57h+String]; unsigned __int16 **
0x1800771cd  call    ?GetEnterpriseId@PhoneCompanyAppDownloadActivity@@AEAAJPEAPEAG@Z; PhoneCompanyAppDownloadActivity::GetEnterpriseId(ushort * *)
0x1800771d2  mov     esi, eax
0x1800771d4  test    eax, eax
0x1800771d6  jnz     short loc_18007720F
0x1800771d8  mov     [rbp+57h+EndPtr], r14
0x1800771dc  mov     rsi, [rbp+57h+String]
0x1800771e0  lea     r8d, [r14+0Ah]; Radix
0x1800771e4  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x1800771e8  mov     rcx, rsi; String
0x1800771eb  call    cs:__imp_wcstoul
0x1800771f1  cmp     rsi, [rbp+57h+EndPtr]
0x1800771f5  jnz     short loc_1800771FE
0x1800771f7  mov     esi, 80004005h
0x1800771fc  jmp     short loc_18007720F
0x1800771fe  mov     esi, r14d
0x180077201  xorps   xmm0, xmm0
0x180077204  movups  xmmword ptr [rbp+57h+EndPtr], xmm0
0x180077208  mov     dword ptr [rbp+57h+EndPtr], eax
0x18007720b  movaps  xmm6, xmmword ptr [rbp+57h+EndPtr]
0x18007720f  lea     rcx, [rbp+57h+String]
0x180077213  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180077218  test    esi, esi
0x18007721a  jns     short loc_18007723A
0x18007721c  mov     rcx, [rbp+57h+pv]; pv
0x180077220  call    cs:__imp_CoTaskMemFree
0x180077226  mov     [rbp+57h+pv], r14
0x18007722a  xor     ecx, ecx; bstrString
0x18007722c  call    cs:__imp_SysFreeString
0x180077232  nop
0x180077233  xor     ecx, ecx
0x180077235  jmp     loc_1800773F8
0x18007723a  mov     dword ptr [rbp+57h+String], r14d
0x18007723e  lea     rcx, [rbp+57h+String]; this
0x180077242  call    ?CoInitializeEx@AutoCoInitialize@@QEAAJK@Z; AutoCoInitialize::CoInitializeEx(ulong)
0x180077247  mov     esi, eax
0x180077249  test    eax, eax
0x18007724b  js      loc_1800773D0
0x180077251  lea     rax, [rbp+57h+var_B8]
0x180077255  mov     [rsp+120h+ppv], rax; ppv
0x18007725a  lea     r9, _GUID_d52ee9f5_41da_4df2_8c6e_b19a23654c93; riid
0x180077261  xor     edx, edx; pUnkOuter
0x180077263  lea     r8d, [rdx+4]; dwClsContext
0x180077267  lea     rcx, _GUID_c63261e4_6052_41ff_b919_496fecf4c4e5; rclsid
0x18007726e  call    cs:__imp_CoCreateInstance
0x180077274  mov     esi, eax
0x180077276  test    eax, eax
0x180077278  js      loc_1800773D0
0x18007727e  mov     rcx, [rbp+57h+var_B8]
0x180077282  movdqa  xmmword ptr [rbp+57h+EndPtr], xmm6
0x180077287  mov     rax, [rcx]
0x18007728a  lea     r8, [rbp+57h+var_C0]
0x18007728e  lea     rdx, [rbp+57h+EndPtr]
0x180077292  mov     rax, [rax+48h]
0x180077296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007729b  mov     esi, eax
0x18007729d  test    eax, eax
0x18007729f  js      loc_1800773D0
0x1800772a5  mov     rcx, [rbp+57h+var_C0]
0x1800772a9  mov     rax, [rcx]
0x1800772ac  lea     rdx, [rbp+57h+var_90]
0x1800772b0  mov     rax, [rax+40h]
0x1800772b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772b9  mov     esi, eax
0x1800772bb  test    eax, eax
0x1800772bd  js      loc_1800773D0
0x1800772c3  mov     rcx, [rbp+57h+var_C0]
0x1800772c7  mov     rax, [rcx]
0x1800772ca  lea     rdx, [rbp+57h+bstrString]
0x1800772ce  mov     rax, [rax+48h]
0x1800772d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772d7  mov     esi, eax
0x1800772d9  test    eax, eax
0x1800772db  js      loc_1800773D0
0x1800772e1  mov     rcx, [rbp+57h+var_C0]
0x1800772e5  mov     rax, [rcx]
0x1800772e8  lea     rdx, [rbp+57h+var_60]
0x1800772ec  mov     rax, [rax+38h]
0x1800772f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772f5  mov     esi, eax
0x1800772f7  test    eax, eax
0x1800772f9  js      loc_1800773D0
0x1800772ff  lea     rcx, wszURI; psz
0x180077306  call    cs:__imp_SysAllocString
0x18007730c  mov     rdx, rax
0x18007730f  lea     rcx, [rbp+57h+var_80]
0x180077313  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180077318  lea     rcx, wszURI; psz
0x18007731f  call    cs:__imp_SysAllocString
0x180077325  mov     rdx, rax
0x180077328  lea     rcx, [rbp+57h+var_88]
0x18007732c  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180077331  mov     rcx, [rbp+57h+var_B8]
0x180077335  movdqa  xmmword ptr [rbp+57h+EndPtr], xmm6
0x18007733a  movaps  xmm0, [rbp+57h+var_60]
0x18007733e  movdqa  [rbp+57h+var_70], xmm0
0x180077343  mov     rax, [rcx]
0x180077346  lea     rdx, [rbp+57h+Buf1]
0x18007734a  mov     [rsp+40h], rdx
0x18007734f  mov     dword ptr [rsp+120h+var_E8], r14d
0x180077354  mov     rbx, [rbp+57h+var_88]
0x180077358  mov     qword ptr [rsp+120h+var_F0], rbx
0x18007735d  lea     rdx, [rbp+57h+EndPtr]
0x180077361  mov     [rsp+120h+var_F8], rdx
0x180077366  lea     rdx, [rbp+57h+var_70]
0x18007736a  mov     [rsp+120h+ppv], rdx
0x18007736f  mov     r9, [rbp+57h+bstrString]
0x180077373  mov     rdi, [rbp+57h+var_80]
0x180077377  mov     r8, rdi
0x18007737a  mov     rdx, [rbp+57h+var_90]
0x18007737e  mov     rax, [rax+68h]
0x180077382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077387  mov     esi, eax
0x180077389  test    eax, eax
0x18007738b  js      short loc_1800773D0
0x18007738d  mov     r8d, 10h; Size
0x180077393  lea     rdx, GUID_NULL; Buf2
0x18007739a  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18007739e  call    memcmp_0
0x1800773a3  test    eax, eax
0x1800773a5  jz      short loc_1800773D0
0x1800773a7  mov     rcx, [rbp+57h+var_B8]
0x1800773ab  movdqa  [rbp+57h+var_70], xmm6
0x1800773b0  mov     rax, [rcx]
0x1800773b3  lea     r9, [rbp+57h+var_A0]
0x1800773b7  lea     r8, [rbp+57h+pv]
0x1800773bb  lea     rdx, [rbp+57h+var_70]
0x1800773bf  mov     rax, [rax+78h]
0x1800773c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800773c8  mov     esi, eax
0x1800773ca  test    eax, eax
0x1800773cc  cmovs   esi, r14d
0x1800773d0  cmp     dword ptr [rbp+57h+String], r14d
0x1800773d4  jz      short loc_1800773DD
0x1800773d6  call    cs:__imp_CoUninitialize
0x1800773dc  nop
0x1800773dd  mov     rcx, [rbp+57h+pv]; pv
0x1800773e1  call    cs:__imp_CoTaskMemFree
0x1800773e7  mov     [rbp+57h+pv], r14
0x1800773eb  mov     rcx, rdi; bstrString
0x1800773ee  call    cs:__imp_SysFreeString
0x1800773f4  nop
0x1800773f5  mov     rcx, rbx; bstrString
0x1800773f8  call    cs:__imp_SysFreeString
0x1800773fe  nop
0x1800773ff  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180077403  call    cs:__imp_SysFreeString
0x180077409  nop
0x18007740a  mov     rcx, [rbp+57h+var_90]; bstrString
0x18007740e  call    cs:__imp_SysFreeString
0x180077414  nop
0x180077415  lea     rcx, [rbp+57h+var_C0]
0x180077419  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18007741e  nop
0x18007741f  lea     rcx, [rbp+57h+var_B8]
0x180077423  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180077428  mov     eax, esi
0x18007742a  mov     rcx, [rbp+57h+var_40]
0x18007742e  xor     rcx, rsp; StackCookie
0x180077431  call    __security_check_cookie
0x180077436  movaps  xmm6, [rsp+120h+var_38+8]
0x18007743e  add     rsp, 100h
0x180077445  pop     r14
0x180077447  pop     rdi
0x180077448  pop     rsi
0x180077449  pop     rbx
0x18007744a  pop     rbp
0x18007744b  retn
```
