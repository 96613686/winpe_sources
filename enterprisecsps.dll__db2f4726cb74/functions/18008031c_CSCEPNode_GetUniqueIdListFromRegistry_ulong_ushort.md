# CSCEPNode::GetUniqueIdListFromRegistry(ulong *,ushort * * *)

- ea: `0x18008031c`
- end: `0x180080624`
- name: `?GetUniqueIdListFromRegistry@CSCEPNode@@AEAAJPEAKPEAPEAPEAG@Z`
- size: `776`
- prototype: `__int64 __fastcall(CSCEPNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007fea0`

## callees

- `0x180009cc4`
- `0x180015e90`
- `0x1800232e4`
- `0x180025ac0`
- `0x18003ba80`
- `0x18003f3a0`
- `0x18003f6f0`
- `0x1800600bc`
- `0x18007db90`
- `0x18008031c`
- `0x180081954`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800803fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080476`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800803fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080476`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x18008042f`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x1800804b4`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x18008042f`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x1800804b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080580`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080580`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CSCEPNode::GetUniqueIdListFromRegistry(CSCEPNode *this, unsigned int *a2, unsigned __int16 ***a3)
{
  __int64 v5; // rdx
  LSTATUS v6; // eax
  bool v7; // sf
  int AllSubKeys; // edi
  unsigned int i; // esi
  LSTATUS v10; // eax
  bool v11; // sf
  _QWORD *v12; // rcx
  unsigned int j; // edi
  __int64 v14; // rsi
  size_t v15; // r15
  unsigned __int16 **v16; // rax
  unsigned __int16 **v17; // r14
  __int64 v18; // rdx
  __int64 k; // r8
  unsigned int v21; // [rsp+30h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-B8h] BYREF
  SIZE_T cb; // [rsp+48h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-A8h] BYREF
  unsigned __int16 **v26; // [rsp+58h] [rbp-A0h] BYREF
  __int16 v27; // [rsp+60h] [rbp-98h] BYREF
  char v28; // [rsp+62h] [rbp-96h]
  __int64 v29; // [rsp+68h] [rbp-90h]
  _QWORD v30[3]; // [rsp+70h] [rbp-88h] BYREF
  _QWORD v31[5]; // [rsp+88h] [rbp-70h] BYREF
  char v32; // [rsp+B0h] [rbp-48h]
  unsigned int v33; // [rsp+118h] [rbp+20h] BYREF

  hKey = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  LODWORD(cb) = 0;
  v21 = 0;
  v33 = 0;
  v26 = 0;
  pv = 0;
  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(v30);
  v31[0] = &v26;
  v31[1] = &v21;
  v31[2] = &pv;
  v31[3] = &v33;
  v31[4] = v30;
  v32 = 1;
  if ( CSCEPNode::m_fIsUser )
    AutoImpersonate::ImpersonateTargetedUser((AutoImpersonate *)&v27, *(struct CConfigServiceProvider2Impl **)(v5 + 16));
  v6 = RegOpenKeyExW(CSCEPNode::m_hCurrentHive, L"Software\\Microsoft\\SCEP\\", 0, 0x20019u, &hKey);
  v7 = v6 < 0;
  if ( v6 > 0 )
    v7 = 1;
  if ( v7 )
  {
    AllSubKeys = 0;
  }
  else
  {
    AllSubKeys = OmaDmRegistryGetAllSubKeys(hKey, &v21, &v26);
    if ( AllSubKeys >= 0 )
    {
      for ( i = 0; i < v21; ++i )
      {
        phkResult = 0;
        v10 = RegOpenKeyExW(hKey, v26[i], 0, 0x20019u, &phkResult);
        v11 = v10 < 0;
        if ( v10 > 0 )
          v11 = 1;
        if ( !v11 )
        {
          v33 = 0;
          pv = 0;
          AllSubKeys = OmaDmRegistryGetAllSubKeys(phkResult, &v33, (unsigned __int16 ***)&pv);
          if ( AllSubKeys < 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
            goto LABEL_29;
          }
          v12 = pv;
          if ( pv )
          {
            for ( j = 0; j < v33; ++j )
            {
              if ( v12[j] )
              {
                std::vector<IConfigNode *>::push_back(v30);
                *((_QWORD *)pv + j) = 0;
                v12 = pv;
              }
            }
            CoTaskMemFree(v12);
            pv = 0;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      }
      v14 = (__int64)(v30[1] - v30[0]) >> 3;
      AllSubKeys = ULongLongToULong(8LL * (unsigned int)v14, (unsigned int *)&cb);
      if ( AllSubKeys >= 0 )
      {
        v15 = (unsigned int)cb;
        v16 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)cb);
        v17 = v16;
        if ( v16 )
        {
          memset_0(v16, 0, v15);
          for ( k = 0; (unsigned int)k < (unsigned int)v14; k = (unsigned int)(k + 1) )
          {
            v18 = (unsigned int)k;
            v17[(unsigned int)k] = *(unsigned __int16 **)(v30[0] + 8LL * (unsigned int)k);
          }
          std::vector<unsigned short *>::clear(v30, v18, k);
          *a2 = v14;
          *a3 = v17;
        }
        else
        {
          AllSubKeys = -2147024882;
        }
      }
    }
  }
LABEL_29:
  v32 = 0;
  lambda_08caf8ab2051d287a2afafff80b82ba2_::operator()(v31);
  std::vector<IConfigNode *>::_Tidy(v30);
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v27);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)AllSubKeys;
}

```

## disassembly

```asm
0x18008031c  mov     rax, rsp
0x18008031f  mov     [rax+18h], r8
0x180080323  mov     [rax+10h], rdx
0x180080327  push    rbx
0x180080328  push    rsi
0x180080329  push    rdi
0x18008032a  push    r12
0x18008032c  push    r13
0x18008032e  push    r14
0x180080330  push    r15
0x180080332  sub     rsp, 0C0h
0x180080339  mov     r12, r8
0x18008033c  mov     r13, rdx
0x18008033f  mov     rdx, rcx
0x180080342  xor     ebx, ebx
0x180080344  mov     [rsp+0F8h+hKey], rbx
0x180080349  mov     [rsp+0F8h+var_98], bx
0x18008034e  mov     [rsp+0F8h+var_96], bl
0x180080352  mov     [rsp+0F8h+var_90], rbx
0x180080357  mov     dword ptr [rsp+0F8h+cb], ebx
0x18008035b  mov     [rsp+0F8h+var_C8], ebx
0x18008035f  mov     [rax+20h], ebx
0x180080362  mov     [rsp+0F8h+var_A0], rbx
0x180080367  mov     [rsp+0F8h+pv], rbx
0x18008036c  lea     rcx, [rsp+0F8h+var_88]
0x180080371  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x180080376  nop
0x180080377  lea     rax, [rsp+0F8h+var_A0]
0x18008037c  mov     [rsp+0F8h+var_70], rax
0x180080384  lea     rax, [rsp+0F8h+var_C8]
0x180080389  mov     [rsp+0F8h+var_68], rax
0x180080391  lea     rax, [rsp+0F8h+pv]
0x180080396  mov     [rsp+0F8h+var_60], rax
0x18008039e  lea     rax, [rsp+0F8h+arg_18]
0x1800803a6  mov     [rsp+0F8h+var_58], rax
0x1800803ae  lea     rax, [rsp+0F8h+var_88]
0x1800803b3  mov     [rsp+0F8h+var_50], rax
0x1800803bb  mov     [rsp+0F8h+var_48], 1
0x1800803c3  cmp     cs:?m_fIsUser@CSCEPNode@@0HA, ebx; int CSCEPNode::m_fIsUser
0x1800803c9  jz      short loc_1800803D9
0x1800803cb  mov     rdx, [rdx+10h]; struct CConfigServiceProvider2Impl *
0x1800803cf  lea     rcx, [rsp+0F8h+var_98]; this
0x1800803d4  call    ?ImpersonateTargetedUser@AutoImpersonate@@QEAAJPEAVCConfigServiceProvider2Impl@@@Z; AutoImpersonate::ImpersonateTargetedUser(CConfigServiceProvider2Impl *)
0x1800803d9  lea     rax, [rsp+0F8h+hKey]
0x1800803de  mov     [rsp+0F8h+phkResult], rax; phkResult
0x1800803e3  mov     r15d, 20019h
0x1800803e9  mov     r9d, r15d; samDesired
0x1800803ec  xor     r8d, r8d; ulOptions
0x1800803ef  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\SCEP\\"
0x1800803f6  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hKey
0x1800803fd  call    cs:__imp_RegOpenKeyExW
0x180080404  nop     dword ptr [rax+rax+00h]
0x180080409  test    eax, eax
0x18008040b  jle     short loc_180080417
0x18008040d  movzx   eax, ax
0x180080410  or      eax, 80070000h
0x180080415  test    eax, eax
0x180080417  jns     short loc_180080420
0x180080419  mov     edi, ebx
0x18008041b  jmp     loc_1800805D9
0x180080420  lea     r8, [rsp+0F8h+var_A0]
0x180080425  lea     rdx, [rsp+0F8h+var_C8]
0x18008042a  mov     rcx, [rsp+0F8h+hKey]
0x18008042f  call    cs:__imp_?OmaDmRegistryGetAllSubKeys@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z; OmaDmRegistryGetAllSubKeys(HKEY__ *,ulong *,ushort * * *)
0x180080436  nop     dword ptr [rax+rax+00h]
0x18008043b  mov     edi, eax
0x18008043d  test    eax, eax
0x18008043f  js      loc_1800805D9
0x180080445  mov     esi, ebx
0x180080447  cmp     esi, [rsp+0F8h+var_C8]
0x18008044b  jnb     loc_180080535
0x180080451  mov     [rsp+0F8h+var_B8], rbx
0x180080456  mov     eax, esi
0x180080458  lea     rcx, [rsp+0F8h+var_B8]
0x18008045d  mov     [rsp+0F8h+phkResult], rcx; phkResult
0x180080462  mov     r9d, r15d; samDesired
0x180080465  xor     r8d, r8d; ulOptions
0x180080468  mov     rdx, [rsp+0F8h+var_A0]
0x18008046d  mov     rdx, [rdx+rax*8]; lpSubKey
0x180080471  mov     rcx, [rsp+0F8h+hKey]; hKey
0x180080476  call    cs:__imp_RegOpenKeyExW
0x18008047d  nop     dword ptr [rax+rax+00h]
0x180080482  test    eax, eax
0x180080484  jle     short loc_180080490
0x180080486  movzx   eax, ax
0x180080489  or      eax, 80070000h
0x18008048e  test    eax, eax
0x180080490  js      loc_180080524
0x180080496  mov     [rsp+0F8h+arg_18], ebx
0x18008049d  mov     [rsp+0F8h+pv], rbx
0x1800804a2  lea     r8, [rsp+0F8h+pv]
0x1800804a7  lea     rdx, [rsp+0F8h+arg_18]
0x1800804af  mov     rcx, [rsp+0F8h+var_B8]
0x1800804b4  call    cs:__imp_?OmaDmRegistryGetAllSubKeys@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z; OmaDmRegistryGetAllSubKeys(HKEY__ *,ulong *,ushort * * *)
0x1800804bb  nop     dword ptr [rax+rax+00h]
0x1800804c0  mov     edi, eax
0x1800804c2  test    eax, eax
0x1800804c4  jns     short loc_1800804D6
0x1800804c6  lea     rcx, [rsp+0F8h+var_B8]
0x1800804cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800804d0  nop
0x1800804d1  jmp     loc_1800805D9
0x1800804d6  mov     rcx, [rsp+0F8h+pv]; pv
0x1800804db  test    rcx, rcx
0x1800804de  jz      short loc_180080524
0x1800804e0  mov     edi, ebx
0x1800804e2  cmp     edi, [rsp+0F8h+arg_18]
0x1800804e9  jnb     short loc_180080513
0x1800804eb  mov     r14d, edi
0x1800804ee  lea     rdx, [rcx+r14*8]
0x1800804f2  cmp     [rdx], rbx
0x1800804f5  jz      short loc_18008050F
0x1800804f7  lea     rcx, [rsp+0F8h+var_88]
0x1800804fc  call    ?push_back@?$vector@PEAUIConfigNode@@V?$allocator@PEAUIConfigNode@@@std@@@std@@QEAAXAEBQEAUIConfigNode@@@Z; std::vector<IConfigNode *>::push_back(IConfigNode * const &)
0x180080501  mov     rax, [rsp+0F8h+pv]
0x180080506  mov     [rax+r14*8], rbx
0x18008050a  mov     rcx, [rsp+0F8h+pv]
0x18008050f  inc     edi
0x180080511  jmp     short loc_1800804E2
0x180080513  call    cs:__imp_CoTaskMemFree
0x18008051a  nop     dword ptr [rax+rax+00h]
0x18008051f  mov     [rsp+0F8h+pv], rbx
0x180080524  lea     rcx, [rsp+0F8h+var_B8]
0x180080529  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008052e  inc     esi
0x180080530  jmp     loc_180080447
0x180080535  jmp     short loc_180080554
0x180080537  xor     ebx, ebx
0x180080539  mov     edi, dword ptr [rsp+0F8h+var_B8]
0x18008053d  jmp     loc_1800805D9
0x180080542  xor     ebx, ebx
0x180080544  mov     r12, [rsp+0F8h+arg_10]
0x18008054c  mov     r13, [rsp+0F8h+arg_8]
0x180080554  mov     rsi, [rsp+0F8h+var_80]
0x180080559  sub     rsi, [rsp+0F8h+var_88]
0x18008055e  sar     rsi, 3
0x180080562  mov     ecx, esi
0x180080564  shl     rcx, 3; unsigned __int64
0x180080568  lea     rdx, [rsp+0F8h+cb]; unsigned int *
0x18008056d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180080572  mov     edi, eax
0x180080574  test    eax, eax
0x180080576  js      short loc_1800805D9
0x180080578  mov     r15d, dword ptr [rsp+0F8h+cb]
0x18008057d  mov     ecx, r15d; cb
0x180080580  call    cs:__imp_CoTaskMemAlloc
0x180080587  nop     dword ptr [rax+rax+00h]
0x18008058c  mov     r14, rax
0x18008058f  test    rax, rax
0x180080592  jnz     short loc_18008059B
0x180080594  mov     edi, 8007000Eh
0x180080599  jmp     short loc_1800805D9
0x18008059b  mov     r8, r15; Size
0x18008059e  xor     edx, edx; Val
0x1800805a0  mov     rcx, r14; void *
0x1800805a3  call    memset_0
0x1800805a8  mov     r8d, ebx
0x1800805ab  test    esi, esi
0x1800805ad  jz      short loc_1800805C7
0x1800805af  mov     edx, r8d
0x1800805b2  mov     rax, [rsp+0F8h+var_88]
0x1800805b7  mov     rcx, [rax+rdx*8]
0x1800805bb  mov     [r14+rdx*8], rcx
0x1800805bf  inc     r8d
0x1800805c2  cmp     r8d, esi
0x1800805c5  jb      short loc_1800805AF
0x1800805c7  lea     rcx, [rsp+0F8h+var_88]
0x1800805cc  call    ?clear@?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAAXXZ; std::vector<ushort *>::clear(void)
0x1800805d1  mov     [r13+0], esi
0x1800805d5  mov     [r12], r14
0x1800805d9  mov     [rsp+0F8h+var_48], bl
0x1800805e0  lea     rcx, [rsp+0F8h+var_70]
0x1800805e8  call    _lambda_08caf8ab2051d287a2afafff80b82ba2___operator__
0x1800805ed  nop
0x1800805ee  lea     rcx, [rsp+0F8h+var_88]
0x1800805f3  call    ?_Tidy@?$vector@PEAUIConfigNode@@V?$allocator@PEAUIConfigNode@@@std@@@std@@AEAAXXZ; std::vector<IConfigNode *>::_Tidy(void)
0x1800805f8  nop
0x1800805f9  lea     rcx, [rsp+0F8h+var_98]; this
0x1800805fe  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180080603  nop
0x180080604  lea     rcx, [rsp+0F8h+hKey]
0x180080609  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008060e  mov     eax, edi
0x180080610  add     rsp, 0C0h
0x180080617  pop     r15
0x180080619  pop     r14
0x18008061b  pop     r13
0x18008061d  pop     r12
0x18008061f  pop     rdi
0x180080620  pop     rsi
0x180080621  pop     rbx
0x180080622  retn
```
