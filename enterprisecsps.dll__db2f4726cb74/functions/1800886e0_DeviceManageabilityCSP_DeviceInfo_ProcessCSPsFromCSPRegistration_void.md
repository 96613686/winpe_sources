# DeviceManageabilityCSP::DeviceInfo::ProcessCSPsFromCSPRegistration(void)

- ea: `0x1800886e0`
- end: `0x180088b71`
- name: `?ProcessCSPsFromCSPRegistration@DeviceInfo@DeviceManageabilityCSP@@IEAAXXZ`
- size: `1169`
- prototype: `void __fastcall(DeviceManageabilityCSP::DeviceInfo *__hidden this)`
- caller_count: `1`
- callee_count: `35`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800882f8`

## callees

- `0x180008de0`
- `0x18000f0c8`
- `0x180016274`
- `0x180019fd8`
- `0x18002031c`
- `0x180020424`
- `0x1800232e4`
- `0x180023b70`
- `0x180025824`
- `0x180025ac0`
- `0x18002dcc8`
- `0x18005afc4`
- `0x180065770`
- `0x1800657d4`
- `0x180083cec`
- `0x180087888`
- `0x1800878cc`
- `0x18008793c`
- `0x1800880d8`
- `0x18008810c`
- `0x180088140`
- `0x180088158`
- `0x1800881b4`
- `0x1800884ec`
- `0x1800885d0`
- `0x1800886e0`
- `0x180088da8`
- `0x180088dc0`
- `0x180088dd0`
- `0x180088df8`
- `0x180088e50`
- `0x180088e8c`
- `0x180088ed8`
- `0x180088ee4`
- `0x180088fa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180088809`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180088809`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800888ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800888ed`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180088a99`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180088a99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180088798`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180088798`

## string_xrefs

- `0x1800889c2`: `com.microsoft/1.0/MDM/`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall DeviceManageabilityCSP::DeviceInfo::ProcessCSPsFromCSPRegistration(
        DeviceManageabilityCSP::DeviceInfo *this)
{
  __int64 v2; // rax
  const WCHAR *v3; // rax
  __int64 first_of; // rax
  _QWORD *v5; // rax
  __int64 v6; // r10
  void *v7; // rax
  LSTATUS ValueW; // eax
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 last_of; // rax
  DWORD i; // edi
  LPWSTR v14; // rbx
  __int64 v15; // rax
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD pdwType; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxValueLen; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v26[3]; // [rsp+98h] [rbp-68h] BYREF
  LPWSTR lpName[3]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v28[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v29[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v30[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v31[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v32[16]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v33[16]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v34[16]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v35[32]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v36[32]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v37[32]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v38[32]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v39[8]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v40[32]; // [rsp+1C0h] [rbp+C0h] BYREF

  std::deque<std::wstring>::deque<std::wstring>(v28);
  std::wstring::wstring(v36, L"SOFTWARE\\Microsoft\\Provisioning\\CSPs\\.");
  std::deque<std::wstring>::push_back(v28, v36);
  while ( 1 )
  {
    std::wstring::~wstring(v36);
    if ( (unsigned __int8)std::deque<std::wstring>::empty(v28) )
      break;
    v2 = std::stack<std::wstring>::top(v28);
    std::wstring::wstring(v36, v2);
    std::deque<std::wstring>::pop_back(v28);
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey) )
    {
      cbMaxSubKeyLen = 0;
      cbMaxValueNameLen = 0;
      cbMaxValueLen = 0;
      cSubKeys = 0;
      if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
      {
        first_of = std::wstring::find_first_of(v36, L".");
        std::wstring::wstring(v35, v36, first_of, -1);
        LOWORD(pdwType) = 47;
        LOWORD(pcbData) = 92;
        std::wstring::end(v35, v29);
        v5 = (_QWORD *)std::wstring::begin(v35, v30);
        std::replace<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short>(
          *v5,
          v6,
          &pcbData,
          &pdwType);
        if ( cSubKeys )
          goto LABEL_12;
        pdwType = 0;
        pcbData = cbMaxValueLen;
        std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(v26);
        std::vector<unsigned short>::resize(v26, cbMaxValueLen);
        v7 = (void *)std::shared_ptr<CCAStore>::operator-><CCAStore,0>(v26);
        ValueW = RegGetValueW(hKey, 0, L"csp_version", 2u, &pdwType, v7, &pcbData);
        if ( ValueW )
        {
          if ( ValueW == 2 && (unsigned __int8)DeviceManageabilityCSP::DeviceInfo::AllowCSPVersionEnumeration(this, v35) )
          {
            last_of = std::wstring::find_last_of(v35);
            std::wstring::wstring(v37, v35, last_of + 1, -1);
            std::operator+<unsigned short>(v38, L"com.microsoft/1.0/MDM/", v37);
            std::wstring::~wstring(v37);
            v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
            std::pair<unsigned short const *,std::wstring>::pair<unsigned short const *,std::wstring>(v39, &v23, v38);
            std::map<std::wstring,std::wstring>::insert<std::pair<unsigned short const *,std::wstring>,0>(
              this,
              v34,
              v39);
            std::wstring::~wstring(v40);
            std::wstring::~wstring(v38);
          }
        }
        else
        {
          v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
          std::wstring::wstring(v37, v9);
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
            this,
            &v24,
            v37);
          std::wstring::~wstring(v37);
          v10 = (_QWORD *)std::vector<NetworkIdentifier>::begin(this, v31);
          if ( v24 == *v10 )
          {
            v25 = v26[0];
            v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
            v11 = std::make_pair<unsigned short const *,unsigned short *>(v32, &v23, &v25);
            std::map<std::wstring,std::wstring>::insert<std::pair<unsigned short const *,unsigned short *>,0>(
              this,
              v33,
              v11);
          }
        }
        std::vector<unsigned short>::_Tidy(v26);
        if ( cSubKeys )
        {
LABEL_12:
          std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(lpName);
          std::vector<unsigned short>::resize(lpName, 255);
          for ( i = 0; i < cSubKeys; ++i )
          {
            pcbData = 255;
            if ( !RegEnumKeyExW(hKey, i, lpName[0], &pcbData, 0, 0, 0, 0) )
            {
              v14 = lpName[0];
              v15 = std::operator+<unsigned short>(v37, v36, L"\\");
              std::operator+<unsigned short>(v38, v15, v14);
              std::wstring::~wstring(v37);
              std::deque<std::wstring>::push_back(v28, v38);
              std::wstring::~wstring(v38);
            }
          }
          std::vector<unsigned short>::_Tidy(lpName);
        }
        std::wstring::~wstring(v35);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  std::deque<std::wstring>::~deque<std::wstring>(v28);
}

```

## disassembly

```asm
0x1800886e0  mov     [rsp-8+arg_8], rbx
0x1800886e5  mov     [rsp-8+arg_10], rsi
0x1800886ea  push    rbp
0x1800886eb  push    rdi
0x1800886ec  push    r14
0x1800886ee  lea     rbp, [rsp-0F0h]
0x1800886f6  sub     rsp, 1F0h
0x1800886fd  mov     rax, cs:__security_cookie
0x180088704  xor     rax, rsp
0x180088707  mov     [rbp+100h+var_20], rax
0x18008870e  mov     rsi, rcx
0x180088711  xor     r14d, r14d
0x180088714  lea     rcx, [rbp+100h+var_138]
0x180088718  call    ??0?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::deque<std::wstring>::deque<std::wstring>(void)
0x18008871d  nop
0x18008871e  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Provisioning\\CSPs"...
0x180088725  lea     rcx, [rbp+100h+var_A8]
0x180088729  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008872e  nop
0x18008872f  lea     rdx, [rbp+100h+var_A8]
0x180088733  lea     rcx, [rbp+100h+var_138]
0x180088737  call    ?push_back@?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::deque<std::wstring>::push_back(std::wstring &&)
0x18008873c  nop
0x18008873d  jmp     loc_180088B26
0x180088742  lea     rcx, [rbp+100h+var_138]
0x180088746  call    ?top@?$stack@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::stack<std::wstring>::top(void)
0x18008874b  mov     rdx, rax
0x18008874e  lea     rcx, [rbp+100h+var_A8]
0x180088752  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180088757  nop
0x180088758  lea     rcx, [rbp+100h+var_138]
0x18008875c  call    ?pop_back@?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::deque<std::wstring>::pop_back(void)
0x180088761  mov     [rsp+200h+hKey], r14
0x180088766  xor     edx, edx
0x180088768  lea     rcx, [rsp+200h+hKey]
0x18008876d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180088772  lea     rcx, [rbp+100h+var_A8]
0x180088776  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008877b  mov     rdx, rax; lpSubKey
0x18008877e  lea     rax, [rsp+200h+hKey]
0x180088783  mov     [rsp+200h+phkResult], rax; phkResult
0x180088788  mov     r9d, 20019h; samDesired
0x18008878e  xor     r8d, r8d; ulOptions
0x180088791  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180088798  call    cs:__imp_RegOpenKeyExW
0x18008879f  nop     dword ptr [rax+rax+00h]
0x1800887a4  test    eax, eax
0x1800887a6  jnz     loc_180088B1B
0x1800887ac  mov     [rsp+200h+cbMaxSubKeyLen], r14d
0x1800887b1  mov     [rsp+200h+cbMaxValueNameLen], r14d
0x1800887b6  mov     [rsp+200h+cbMaxValueLen], r14d
0x1800887bb  mov     [rsp+200h+cSubKeys], r14d
0x1800887c0  mov     [rsp+200h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800887c5  mov     [rsp+200h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800887ca  lea     rax, [rsp+200h+cbMaxValueLen]
0x1800887cf  mov     [rsp+200h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800887d4  lea     rax, [rsp+200h+cbMaxValueNameLen]
0x1800887d9  mov     [rsp+200h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800887de  mov     [rsp+200h+lpcValues], r14; lpcValues
0x1800887e3  mov     [rsp+200h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800887e8  lea     rax, [rsp+200h+cbMaxSubKeyLen]
0x1800887ed  mov     [rsp+200h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800887f2  lea     rax, [rsp+200h+cSubKeys]
0x1800887f7  mov     [rsp+200h+phkResult], rax; lpcSubKeys
0x1800887fc  xor     r9d, r9d; lpReserved
0x1800887ff  xor     r8d, r8d; lpcchClass
0x180088802  xor     edx, edx; lpClass
0x180088804  mov     rcx, [rsp+200h+hKey]; hKey
0x180088809  call    cs:__imp_RegQueryInfoKeyW
0x180088810  nop     dword ptr [rax+rax+00h]
0x180088815  test    eax, eax
0x180088817  jnz     loc_180088B1B
0x18008881d  lea     rdx, asc_180122D4C; "."
0x180088824  lea     rcx, [rbp+100h+var_A8]
0x180088828  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x18008882d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180088831  mov     r8, rax
0x180088834  lea     rdx, [rbp+100h+var_A8]
0x180088838  lea     rcx, [rbp+100h+var_C8]
0x18008883c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x180088841  nop
0x180088842  mov     eax, 2Fh ; '/'
0x180088847  mov     word ptr [rsp+200h+pdwType], ax
0x18008884c  mov     eax, 5Ch ; '\'
0x180088851  mov     word ptr [rsp+200h+pcbData], ax
0x180088856  lea     rdx, [rbp+100h+var_110]
0x18008885a  lea     rcx, [rbp+100h+var_C8]
0x18008885e  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180088863  mov     r10, [rax]
0x180088866  lea     rdx, [rbp+100h+var_108]
0x18008886a  lea     rcx, [rbp+100h+var_C8]
0x18008886e  call    ?begin@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::begin(void)
0x180088873  lea     r9, [rsp+200h+pdwType]
0x180088878  lea     r8, [rsp+200h+pcbData]
0x18008887d  mov     rdx, r10
0x180088880  mov     rcx, [rax]
0x180088883  call    ??$replace@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@G@std@@YAXV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@0AEBG1@Z; std::replace<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort const &,ushort const &)
0x180088888  cmp     [rsp+200h+cSubKeys], r14d
0x18008888d  jnz     loc_180088A47
0x180088893  mov     [rsp+200h+pdwType], r14d
0x180088898  mov     eax, [rsp+200h+cbMaxValueLen]
0x18008889c  mov     [rsp+200h+pcbData], eax
0x1800888a0  lea     rcx, [rbp+100h+var_168]
0x1800888a4  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x1800888a9  nop
0x1800888aa  mov     edx, [rsp+200h+cbMaxValueLen]
0x1800888ae  lea     rcx, [rbp+100h+var_168]
0x1800888b2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800888b7  lea     rcx, [rbp+100h+var_168]
0x1800888bb  call    ??$?CVCCAStore@@$0A@@?$shared_ptr@VCCAStore@@@std@@QEBAPEAVCCAStore@@XZ; std::shared_ptr<CCAStore>::operator-><CCAStore,0>(void)
0x1800888c0  lea     rcx, [rsp+200h+pcbData]
0x1800888c5  mov     [rsp+200h+lpcbMaxClassLen], rcx; pcbData
0x1800888ca  mov     [rsp+200h+lpcbMaxSubKeyLen], rax; pvData
0x1800888cf  lea     rax, [rsp+200h+pdwType]
0x1800888d4  mov     [rsp+200h+phkResult], rax; pdwType
0x1800888d9  mov     r9d, 2; dwFlags
0x1800888df  lea     r8, aCspVersion; "csp_version"
0x1800888e6  xor     edx, edx; lpSubKey
0x1800888e8  mov     rcx, [rsp+200h+hKey]; hkey
0x1800888ed  call    cs:__imp_RegGetValueW
0x1800888f4  nop     dword ptr [rax+rax+00h]
0x1800888f9  test    eax, eax
0x1800888fb  jnz     loc_180088982
0x180088901  lea     rcx, [rbp+100h+var_C8]
0x180088905  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008890a  mov     rdx, rax
0x18008890d  lea     rcx, [rbp+100h+var_88]
0x180088911  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180088916  lea     r8, [rbp+100h+var_88]
0x18008891a  lea     rdx, [rbp+100h+var_178]
0x18008891e  mov     rcx, rsi
0x180088921  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180088926  lea     rcx, [rbp+100h+var_88]
0x18008892a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008892f  lea     rdx, [rbp+100h+var_100]
0x180088933  mov     rcx, rsi
0x180088936  call    ?begin@?$vector@VNetworkIdentifier@@V?$allocator@VNetworkIdentifier@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VNetworkIdentifier@@@std@@@std@@@2@XZ; std::vector<NetworkIdentifier>::begin(void)
0x18008893b  mov     rcx, [rax]
0x18008893e  cmp     [rbp+100h+var_178], rcx
0x180088942  jnz     loc_180088A33
0x180088948  mov     rax, [rbp+100h+var_168]
0x18008894c  mov     [rbp+100h+var_170], rax
0x180088950  lea     rcx, [rbp+100h+var_C8]
0x180088954  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180088959  mov     [rbp+100h+var_180], rax
0x18008895d  lea     r8, [rbp+100h+var_170]
0x180088961  lea     rdx, [rbp+100h+var_180]
0x180088965  lea     rcx, [rbp+100h+var_F8]
0x180088969  call    ??$make_pair@PEBGPEAG@std@@YA?AU?$pair@PEBGPEAG@0@$$QEAPEBG$$QEAPEAG@Z; std::make_pair<ushort const *,ushort *>(ushort const * &&,ushort * &&)
0x18008896e  mov     r8, rax
0x180088971  lea     rdx, [rbp+100h+var_E8]
0x180088975  mov     rcx, rsi
0x180088978  call    ??$insert@U?$pair@PEBGPEAG@std@@$0A@@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGPEAG@1@@Z; std::map<std::wstring,std::wstring>::insert<std::pair<ushort const *,ushort *>,0>(std::pair<ushort const *,ushort *> &&)
0x18008897d  jmp     loc_180088A33
0x180088982  cmp     eax, 2
0x180088985  jnz     loc_180088A33
0x18008898b  lea     rdx, [rbp+100h+var_C8]
0x18008898f  mov     rcx, rsi
0x180088992  call    ?AllowCSPVersionEnumeration@DeviceInfo@DeviceManageabilityCSP@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DeviceManageabilityCSP::DeviceInfo::AllowCSPVersionEnumeration(std::wstring const &)
0x180088997  test    al, al
0x180088999  jz      loc_180088A33
0x18008899f  lea     rcx, [rbp+100h+var_C8]
0x1800889a3  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x1800889a8  lea     r8, [rax+1]
0x1800889ac  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800889b0  lea     rdx, [rbp+100h+var_C8]
0x1800889b4  lea     rcx, [rbp+100h+var_88]
0x1800889b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x1800889bd  nop
0x1800889be  lea     r8, [rbp+100h+var_88]
0x1800889c2  lea     rdx, aComMicrosoft10; "com.microsoft/1.0/MDM/"
0x1800889c9  lea     rcx, [rbp+100h+var_68]
0x1800889d0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x1800889d5  nop
0x1800889d6  lea     rcx, [rbp+100h+var_88]
0x1800889da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800889df  nop
0x1800889e0  lea     rcx, [rbp+100h+var_C8]
0x1800889e4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800889e9  mov     [rbp+100h+var_180], rax
0x1800889ed  lea     r8, [rbp+100h+var_68]
0x1800889f4  lea     rdx, [rbp+100h+var_180]
0x1800889f8  lea     rcx, [rbp+100h+var_48]
0x1800889ff  call    ??$?0PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAPEBG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const *,std::wstring>::pair<ushort const *,std::wstring>(ushort const * &&,std::wstring &&)
0x180088a04  nop
0x180088a05  lea     r8, [rbp+100h+var_48]
0x180088a0c  lea     rdx, [rbp+100h+var_D8]
0x180088a10  mov     rcx, rsi
0x180088a13  call    ??$insert@U?$pair@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$0A@@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::map<std::wstring,std::wstring>::insert<std::pair<ushort const *,std::wstring>,0>(std::pair<ushort const *,std::wstring> &&)
0x180088a18  nop
0x180088a19  lea     rcx, [rbp+100h+var_40]
0x180088a20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088a25  nop
0x180088a26  lea     rcx, [rbp+100h+var_68]
0x180088a2d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088a32  nop
0x180088a33  lea     rcx, [rbp+100h+var_168]
0x180088a37  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180088a3c  cmp     [rsp+200h+cSubKeys], r14d
0x180088a41  jz      loc_180088B11
0x180088a47  lea     rcx, [rbp+100h+lpName]
0x180088a4b  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x180088a50  nop
0x180088a51  mov     edx, 0FFh
0x180088a56  lea     rcx, [rbp+100h+lpName]
0x180088a5a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180088a5f  mov     edi, r14d
0x180088a62  cmp     [rsp+200h+cSubKeys], r14d
0x180088a67  jbe     loc_180088B07
0x180088a6d  mov     [rsp+200h+pcbData], 0FFh
0x180088a75  mov     [rsp+200h+lpcValues], r14; lpftLastWriteTime
0x180088a7a  mov     [rsp+200h+lpcbMaxClassLen], r14; lpcchClass
0x180088a7f  mov     [rsp+200h+lpcbMaxSubKeyLen], r14; lpClass
0x180088a84  mov     [rsp+200h+phkResult], r14; lpReserved
0x180088a89  lea     r9, [rsp+200h+pcbData]; lpcchName
0x180088a8e  mov     r8, [rbp+100h+lpName]; lpName
0x180088a92  mov     edx, edi; dwIndex
0x180088a94  mov     rcx, [rsp+200h+hKey]; hKey
0x180088a99  call    cs:__imp_RegEnumKeyExW
0x180088aa0  nop     dword ptr [rax+rax+00h]
0x180088aa5  test    eax, eax
0x180088aa7  jnz     short loc_180088AFB
0x180088aa9  mov     rbx, [rbp+100h+lpName]
0x180088aad  lea     r8, StringValue; "\\"
0x180088ab4  lea     rdx, [rbp+100h+var_A8]
0x180088ab8  lea     rcx, [rbp+100h+var_88]
0x180088abc  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180088ac1  nop
0x180088ac2  mov     r8, rbx
0x180088ac5  mov     rdx, rax
0x180088ac8  lea     rcx, [rbp+100h+var_68]
0x180088acf  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180088ad4  nop
0x180088ad5  lea     rcx, [rbp+100h+var_88]
0x180088ad9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088ade  lea     rdx, [rbp+100h+var_68]
0x180088ae5  lea     rcx, [rbp+100h+var_138]
0x180088ae9  call    ?push_back@?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::deque<std::wstring>::push_back(std::wstring const &)
0x180088aee  nop
0x180088aef  lea     rcx, [rbp+100h+var_68]
0x180088af6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088afb  inc     edi
0x180088afd  cmp     edi, [rsp+200h+cSubKeys]
0x180088b01  jb      loc_180088A6D
0x180088b07  lea     rcx, [rbp+100h+lpName]
0x180088b0b  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180088b10  nop
0x180088b11  lea     rcx, [rbp+100h+var_C8]
0x180088b15  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088b1a  nop
0x180088b1b  lea     rcx, [rsp+200h+hKey]
0x180088b20  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180088b25  nop
0x180088b26  lea     rcx, [rbp+100h+var_A8]
0x180088b2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180088b2f  lea     rcx, [rbp+100h+var_138]
0x180088b33  call    ?empty@?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NXZ; std::deque<std::wstring>::empty(void)
0x180088b38  test    al, al
0x180088b3a  jz      loc_180088742
0x180088b40  lea     rcx, [rbp+100h+var_138]
0x180088b44  call    ??1?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::deque<std::wstring>::~deque<std::wstring>(void)
0x180088b49  mov     rcx, [rbp+100h+var_20]
0x180088b50  xor     rcx, rsp; StackCookie
0x180088b53  call    __security_check_cookie
0x180088b58  lea     r11, [rsp+200h+var_10]
0x180088b60  mov     rbx, [r11+28h]
0x180088b64  mov     rsi, [r11+30h]
0x180088b68  mov     rsp, r11
0x180088b6b  pop     r14
0x180088b6d  pop     rdi
0x180088b6e  pop     rbp
0x180088b6f  retn
```
