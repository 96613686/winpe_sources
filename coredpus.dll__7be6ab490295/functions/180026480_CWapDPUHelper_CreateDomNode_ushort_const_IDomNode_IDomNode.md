# CWapDPUHelper::CreateDomNode(ushort const *,IDomNode * *,IDomNode *)

- ea: `0x180026480`
- end: `0x18002684c`
- name: `?CreateDomNode@CWapDPUHelper@@UEAAJPEBGPEAPEAUIDomNode@@PEAU2@@Z`
- size: `972`
- prototype: `int(CWapDPUHelper *__hidden this, const unsigned __int16 *, struct IDomNode **, struct IDomNode *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800110bc`
- `0x180023b0c`
- `0x180024308`
- `0x180026480`
- `0x18002e4d4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180026802`
- `OLEAUT32!__imp_SysFreeString` at `0x180026802`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002659c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800265da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002663f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002659c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800265da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002663f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CWapDPUHelper::CreateDomNode(
        CWapDPUHelper *this,
        const unsigned __int16 *a2,
        struct IUnknown **a3,
        struct IUnknown *a4)
{
  struct IUnknown *v7; // rbx
  HRESULT Instance; // edi
  int v9; // r15d
  struct IUnknown *v10; // rdx
  struct IUnknown *v11; // rcx
  struct IUnknown *ppv; // [rsp+30h] [rbp-48h] BYREF
  struct IUnknown *v14; // [rsp+38h] [rbp-40h] BYREF
  struct IUnknown *v15; // [rsp+40h] [rbp-38h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-30h] BYREF

  ppv = 0;
  v7 = 0;
  v15 = 0;
  v14 = 0;
  String2 = 0;
  if ( !a2 || (v9 = 0, !a3) )
  {
    Instance = -2147024809;
    goto LABEL_44;
  }
  if ( !wcscmp_0(L"characteristic", a2)
    || !wcscmp_0(L"characteristic-query", a2)
    || !wcscmp_0(L"nocharacteristic", a2)
    || !wcscmp_0(L"characteristic-error", a2) )
  {
    Instance = CoCreateInstance(
                 &GUID_d78c3a7d_9018_41b6_9ce3_2bfdd45d45a1,
                 0,
                 1u,
                 &GUID_1c7ef7df_3bbe_4d43_acc2_eb9708d2a52f,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
      goto LABEL_44;
    if ( !wcscmp_0(L"nocharacteristic", a2) )
      v9 = 1;
  }
  else if ( !wcscmp_0(L"parm", a2)
         || !wcscmp_0(L"parm-query", a2)
         || !wcscmp_0(L"noparm", a2)
         || !wcscmp_0(L"parm-error", a2) )
  {
    Instance = CoCreateInstance(
                 &GUID_cfc44584_e947_47fe_b9c4_99168114c866,
                 0,
                 1u,
                 &GUID_1c7ef7df_3bbe_4d43_acc2_eb9708d2a52f,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
      goto LABEL_44;
    if ( !wcscmp_0(L"parm", a2) || !wcscmp_0(L"noparm", a2) )
      v9 = 1;
  }
  else
  {
    Instance = CoCreateInstance(
                 &GUID_7a63d67d_014e_4f5f_ae9d_cc0c1fe16dac,
                 0,
                 1u,
                 &GUID_1c7ef7df_3bbe_4d43_acc2_eb9708d2a52f,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
      goto LABEL_44;
  }
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int16 *))ppv->lpVtbl[2].QueryInterface)(
               ppv,
               a2);
  if ( Instance < 0 )
    goto LABEL_44;
  if ( a4 )
  {
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown *))a4->lpVtbl[9].QueryInterface)(a4, ppv);
    if ( Instance < 0 )
      goto LABEL_44;
  }
  else if ( !wcscmp_0(L"wap-provisioningdoc", a2) )
  {
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, const wchar_t *))ppv->lpVtbl[4].QueryInterface)(
                 ppv,
                 L"cfgmgr_execute",
                 L"false");
    if ( Instance < 0 )
      goto LABEL_44;
  }
  if ( !v9 || *((_DWORD *)this + 9) )
    goto LABEL_43;
  if ( ppv )
  {
    ATL::AtlComPtrAssign(&v15, ppv);
    v7 = v15;
  }
  v10 = v14;
  if ( v14 == a4 )
    goto LABEL_34;
  ATL::AtlComPtrAssign(&v14, a4);
  while ( 1 )
  {
    v10 = v14;
LABEL_34:
    if ( !v10 )
      break;
    if ( v7 != v10 )
    {
      ATL::AtlComPtrAssign(&v15, v10);
      v7 = v15;
    }
    ATL::CComPtrBase<IDomNode>::Release(&v14);
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknown **))v7->lpVtbl[6].QueryInterface)(v7, &v14);
    if ( Instance < 0 )
      goto LABEL_44;
  }
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, wchar_t **))v7->lpVtbl[1].Release)(v7, &String2);
  if ( Instance >= 0 )
  {
    if ( wcscmp_0(L"wap-provisioningdoc", String2) )
    {
LABEL_43:
      v11 = ppv;
      *a3 = ppv;
      ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->AddRef)(v11);
      goto LABEL_44;
    }
    Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, const wchar_t *))v7->lpVtbl[4].QueryInterface)(
                 v7,
                 L"cfgmgr_execute",
                 L"true");
    if ( Instance >= 0 )
    {
      *((_DWORD *)this + 9) = 1;
      goto LABEL_43;
    }
  }
LABEL_44:
  SysFreeString(String2);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v14);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v15);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180026480  mov     r11, rsp
0x180026483  mov     [r11+8], rbx
0x180026487  mov     [r11+20h], rsi
0x18002648b  mov     [r11+18h], r8
0x18002648f  push    rdi
0x180026490  push    r12
0x180026492  push    r13
0x180026494  push    r14
0x180026496  push    r15
0x180026498  sub     rsp, 50h
0x18002649c  mov     r12, r9
0x18002649f  mov     rax, r8
0x1800264a2  mov     rsi, rdx
0x1800264a5  mov     r13, rcx
0x1800264a8  xor     edi, edi
0x1800264aa  mov     [r11-48h], rdi
0x1800264ae  mov     ebx, edi
0x1800264b0  mov     [rsp+78h+var_38], rbx
0x1800264b5  mov     [r11-40h], rdi
0x1800264b9  mov     [r11-30h], rdi
0x1800264bd  test    rdx, rdx
0x1800264c0  jnz     short loc_1800264CC
0x1800264c2  mov     edi, 80070057h
0x1800264c7  jmp     loc_1800267FD
0x1800264cc  mov     r15d, edi
0x1800264cf  test    rax, rax
0x1800264d2  jz      short loc_1800264C2
0x1800264d4  lea     rcx, aCharacteristic_0; "characteristic"
0x1800264db  call    wcscmp_0
0x1800264e0  test    eax, eax
0x1800264e2  jz      loc_18002661C
0x1800264e8  mov     rdx, rsi; String2
0x1800264eb  lea     rcx, aCharacteristic; "characteristic-query"
0x1800264f2  call    wcscmp_0
0x1800264f7  test    eax, eax
0x1800264f9  jz      loc_18002661C
0x1800264ff  mov     rdx, rsi; String2
0x180026502  lea     rcx, aNocharacterist; "nocharacteristic"
0x180026509  call    wcscmp_0
0x18002650e  test    eax, eax
0x180026510  jz      loc_18002661C
0x180026516  mov     rdx, rsi; String2
0x180026519  lea     rcx, aCharacteristic_1; "characteristic-error"
0x180026520  call    wcscmp_0
0x180026525  test    eax, eax
0x180026527  jz      loc_18002661C
0x18002652d  mov     rdx, rsi; String2
0x180026530  lea     rcx, aParm; "parm"
0x180026537  call    wcscmp_0
0x18002653c  test    eax, eax
0x18002653e  jz      short loc_1800265B7
0x180026540  mov     rdx, rsi; String2
0x180026543  lea     rcx, aParmQuery; "parm-query"
0x18002654a  call    wcscmp_0
0x18002654f  test    eax, eax
0x180026551  jz      short loc_1800265B7
0x180026553  mov     rdx, rsi; String2
0x180026556  lea     rcx, aNoparm; "noparm"
0x18002655d  call    wcscmp_0
0x180026562  test    eax, eax
0x180026564  jz      short loc_1800265B7
0x180026566  mov     rdx, rsi; String2
0x180026569  lea     rcx, aParmError; "parm-error"
0x180026570  call    wcscmp_0
0x180026575  test    eax, eax
0x180026577  jz      short loc_1800265B7
0x180026579  lea     rax, [rsp+78h+var_48]
0x18002657e  mov     [rsp+78h+ppv], rax; ppv
0x180026583  lea     r9, _GUID_1c7ef7df_3bbe_4d43_acc2_eb9708d2a52f; riid
0x18002658a  mov     r14d, 1
0x180026590  mov     r8d, r14d; dwClsContext
0x180026593  xor     edx, edx; pUnkOuter
0x180026595  lea     rcx, _GUID_7a63d67d_014e_4f5f_ae9d_cc0c1fe16dac; rclsid
0x18002659c  call    cs:__imp_CoCreateInstance
0x1800265a3  nop     dword ptr [rax+rax+00h]
0x1800265a8  mov     edi, eax
0x1800265aa  test    eax, eax
0x1800265ac  jns     loc_18002666B
0x1800265b2  jmp     loc_1800267FD
0x1800265b7  lea     rax, [rsp+78h+var_48]
0x1800265bc  mov     [rsp+78h+ppv], rax; ppv
0x1800265c1  lea     r9, _GUID_1c7ef7df_3bbe_4d43_acc2_eb9708d2a52f; riid
0x1800265c8  mov     r14d, 1
0x1800265ce  mov     r8d, r14d; dwClsContext
0x1800265d1  xor     edx, edx; pUnkOuter
0x1800265d3  lea     rcx, _GUID_cfc44584_e947_47fe_b9c4_99168114c866; rclsid
0x1800265da  call    cs:__imp_CoCreateInstance
0x1800265e1  nop     dword ptr [rax+rax+00h]
0x1800265e6  mov     edi, eax
0x1800265e8  test    eax, eax
0x1800265ea  jns     short loc_1800265F1
0x1800265ec  jmp     loc_1800267FD
0x1800265f1  mov     rdx, rsi; String2
0x1800265f4  lea     rcx, aParm; "parm"
0x1800265fb  call    wcscmp_0
0x180026600  test    eax, eax
0x180026602  jz      short loc_180026617
0x180026604  mov     rdx, rsi; String2
0x180026607  lea     rcx, aNoparm; "noparm"
0x18002660e  call    wcscmp_0
0x180026613  test    eax, eax
0x180026615  jnz     short loc_18002666B
0x180026617  mov     r15d, r14d
0x18002661a  jmp     short loc_18002666B
0x18002661c  lea     rax, [rsp+78h+var_48]
0x180026621  mov     [rsp+78h+ppv], rax; ppv
0x180026626  lea     r9, _GUID_1c7ef7df_3bbe_4d43_acc2_eb9708d2a52f; riid
0x18002662d  mov     r14d, 1
0x180026633  mov     r8d, r14d; dwClsContext
0x180026636  xor     edx, edx; pUnkOuter
0x180026638  lea     rcx, _GUID_d78c3a7d_9018_41b6_9ce3_2bfdd45d45a1; rclsid
0x18002663f  call    cs:__imp_CoCreateInstance
0x180026646  nop     dword ptr [rax+rax+00h]
0x18002664b  mov     edi, eax
0x18002664d  test    eax, eax
0x18002664f  jns     short loc_180026656
0x180026651  jmp     loc_1800267FD
0x180026656  mov     rdx, rsi; String2
0x180026659  lea     rcx, aNocharacterist; "nocharacteristic"
0x180026660  call    wcscmp_0
0x180026665  test    eax, eax
0x180026667  cmovz   r15d, r14d
0x18002666b  mov     rcx, [rsp+78h+var_48]
0x180026670  mov     rax, [rcx]
0x180026673  mov     rdx, rsi
0x180026676  mov     rax, [rax+30h]
0x18002667a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002667f  mov     edi, eax
0x180026681  test    eax, eax
0x180026683  jns     short loc_18002668A
0x180026685  jmp     loc_1800267FD
0x18002668a  test    r12, r12
0x18002668d  jz      short loc_1800266B2
0x18002668f  mov     rax, [r12]
0x180026693  mov     rdx, [rsp+78h+var_48]
0x180026698  mov     rcx, r12
0x18002669b  mov     rax, [rax+0D8h]
0x1800266a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266a7  mov     edi, eax
0x1800266a9  test    eax, eax
0x1800266ab  jns     short loc_1800266EF
0x1800266ad  jmp     loc_1800267FD
0x1800266b2  mov     rdx, rsi; String2
0x1800266b5  lea     rcx, aWapProvisionin_0; "wap-provisioningdoc"
0x1800266bc  call    wcscmp_0
0x1800266c1  test    eax, eax
0x1800266c3  jnz     short loc_1800266EF
0x1800266c5  mov     rcx, [rsp+78h+var_48]
0x1800266ca  mov     rax, [rcx]
0x1800266cd  lea     r8, aFalse; "false"
0x1800266d4  lea     rdx, aCfgmgrExecute; "cfgmgr_execute"
0x1800266db  mov     rax, [rax+60h]
0x1800266df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266e4  mov     edi, eax
0x1800266e6  test    eax, eax
0x1800266e8  jns     short loc_1800266EF
0x1800266ea  jmp     loc_1800267FD
0x1800266ef  test    r15d, r15d
0x1800266f2  jz      loc_1800267D7
0x1800266f8  cmp     dword ptr [r13+24h], 0
0x1800266fd  jnz     loc_1800267D7
0x180026703  mov     rdx, [rsp+78h+var_48]; struct IUnknown *
0x180026708  test    rdx, rdx
0x18002670b  jz      short loc_18002671C
0x18002670d  lea     rcx, [rsp+78h+var_38]; struct IUnknown **
0x180026712  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180026717  mov     rbx, [rsp+78h+var_38]
0x18002671c  mov     rdx, [rsp+78h+var_40]
0x180026721  cmp     rdx, r12
0x180026724  jz      short loc_180026738
0x180026726  mov     rdx, r12; struct IUnknown *
0x180026729  lea     rcx, [rsp+78h+var_40]; struct IUnknown **
0x18002672e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180026733  mov     rdx, [rsp+78h+var_40]; struct IUnknown *
0x180026738  test    rdx, rdx
0x18002673b  jz      short loc_18002677D
0x18002673d  cmp     rbx, rdx
0x180026740  jz      short loc_180026751
0x180026742  lea     rcx, [rsp+78h+var_38]; struct IUnknown **
0x180026747  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002674c  mov     rbx, [rsp+78h+var_38]
0x180026751  lea     rcx, [rsp+78h+var_40]
0x180026756  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x18002675b  mov     rax, [rbx]
0x18002675e  lea     rdx, [rsp+78h+var_40]
0x180026763  mov     rcx, rbx
0x180026766  mov     rax, [rax+90h]
0x18002676d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026772  mov     edi, eax
0x180026774  test    eax, eax
0x180026776  jns     short loc_180026733
0x180026778  jmp     loc_1800267FD
0x18002677d  mov     rax, [rbx]
0x180026780  lea     rdx, [rsp+78h+String2]
0x180026785  mov     rcx, rbx
0x180026788  mov     rax, [rax+28h]
0x18002678c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026791  mov     edi, eax
0x180026793  test    eax, eax
0x180026795  jns     short loc_180026799
0x180026797  jmp     short loc_1800267FD
0x180026799  mov     rdx, [rsp+78h+String2]; String2
0x18002679e  lea     rcx, aWapProvisionin_0; "wap-provisioningdoc"
0x1800267a5  call    wcscmp_0
0x1800267aa  test    eax, eax
0x1800267ac  jnz     short loc_1800267D7
0x1800267ae  mov     rax, [rbx]
0x1800267b1  lea     r8, aTrue; "true"
0x1800267b8  lea     rdx, aCfgmgrExecute; "cfgmgr_execute"
0x1800267bf  mov     rcx, rbx
0x1800267c2  mov     rax, [rax+60h]
0x1800267c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267cb  mov     edi, eax
0x1800267cd  test    eax, eax
0x1800267cf  jns     short loc_1800267D3
0x1800267d1  jmp     short loc_1800267FD
0x1800267d3  mov     [r13+24h], r14d
0x1800267d7  mov     rcx, [rsp+78h+var_48]
0x1800267dc  mov     rax, [rsp+78h+arg_10]
0x1800267e4  mov     [rax], rcx
0x1800267e7  mov     rax, [rcx]
0x1800267ea  mov     rax, [rax+8]
0x1800267ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267f3  nop
0x1800267f4  jmp     short loc_1800267FD
0x1800267f6  mov     edi, [rsp+78h+arg_8]
0x1800267fd  mov     rcx, [rsp+78h+String2]; bstrString
0x180026802  call    cs:__imp_SysFreeString
0x180026809  nop     dword ptr [rax+rax+00h]
0x18002680e  nop
0x18002680f  lea     rcx, [rsp+78h+var_40]
0x180026814  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180026819  nop
0x18002681a  lea     rcx, [rsp+78h+var_38]
0x18002681f  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180026824  nop
0x180026825  lea     rcx, [rsp+78h+var_48]
0x18002682a  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002682f  mov     eax, edi
0x180026831  lea     r11, [rsp+78h+var_28]
0x180026836  mov     rbx, [r11+30h]
0x18002683a  mov     rsi, [r11+48h]
0x18002683e  mov     rsp, r11
0x180026841  pop     r15
0x180026843  pop     r14
0x180026845  pop     r13
0x180026847  pop     r12
0x180026849  pop     rdi
0x18002684a  retn
```
