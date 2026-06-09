# LpacRegHelper::CreateRegistryLpacFlex(void *,ushort const *,ushort const *,void *,ushort const *,HKEY__ * *)

- ea: `0x18001f7b0`
- end: `0x18001fa95`
- name: `?CreateRegistryLpacFlex@LpacRegHelper@@CAJPEAXPEBG101PEAPEAUHKEY__@@@Z`
- size: `741`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, void *, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f5e4`

## callees

- `0x180004594`
- `0x18000a4d8`
- `0x18000a740`
- `0x18000c7d4`
- `0x18000f864`
- `0x18000f938`
- `0x18001d388`
- `0x18001ef5c`
- `0x18001f7b0`
- `0x180020488`
- `0x180021564`
- `0x180021688`
- `0x180021ac0`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f934`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f934`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f86c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f86c`

## string_xrefs

- `0x18001f7f9`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f843`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f880`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f8d9`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f94b`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f996`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001fa01`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LpacRegHelper::CreateRegistryLpacFlex(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4,
        const unsigned __int16 *a5,
        HKEY *a6)
{
  __int64 v8; // rdx
  unsigned int LastError; // ebx
  int v10; // eax
  const char *v11; // r9
  int v12; // eax
  HKEY *phkResult; // rax
  unsigned int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rdx
  int v20; // eax
  HKEY v21; // rax
  __int64 v22; // rdx
  DWORD dwOptions; // [rsp+20h] [rbp-79h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-79h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-49h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-41h] BYREF
  HKEY v28; // [rsp+60h] [rbp-39h] BYREF
  __int64 v29; // [rsp+68h] [rbp-31h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+70h] [rbp-29h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-21h] BYREF
  _QWORD v32[3]; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int64 v33; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  if ( a2 )
  {
    if ( !a3 )
    {
      v8 = 172;
      goto LABEL_3;
    }
    if ( !a4 )
    {
      v8 = 173;
      goto LABEL_3;
    }
    StringSecurityDescriptor = 0;
    v10 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &StringSecurityDescriptor,
            L"D:(A;OICI;KA;;;CO)(A;OICI;KA;;;SY)(A;OICI;KA;;;%s)(A;OICI;KR;;;S-1-15-3-1024-3635283841-2530182609-996808640"
             "-1887759898-3848208603-3313616867-983405619-2501854204)(A;OICI;KA;;;BA)");
    LastError = v10;
    if ( v10 >= 0 )
    {
      SecurityDescriptor = 0;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
      {
        *(_QWORD *)&SecurityAttributes.nLength = 24;
        *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
        SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
        lpSubKey = 0;
        v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &lpSubKey,
                L"%s\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\LpacApi",
                a3);
        LastError = v12;
        if ( v12 >= 0 )
        {
          v29 = 0;
          phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v29);
          v14 = RegCreateKeyExW(HKEY_USERS, lpSubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, phkResult, 0);
          if ( v14 )
          {
            LastError = wil::details::in1diag3::Return_Win32(
                          retaddr,
                          (void *)0xDA,
                          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
                          (const char *)v14,
                          dwOptionsa);
          }
          else
          {
            v33 = 7;
            v32[2] = 0;
            LOWORD(v32[0]) = 0;
            v16 = LpacRegHelper::DeriveLpacTopRegistryKey(v15, a2, a3, v32);
            LastError = v16;
            if ( v16 >= 0 )
            {
              std::wstring::append(v32, L"\\LpacCapabilities", aLpaccapabiliti[0] != 0 ? 0x11 : 0);
              v28 = 0;
              v19 = v32;
              if ( v33 >= 8 )
                v19 = (_QWORD *)v32[0];
              v20 = wil::reg::create_unique_key_nothrow(v18, v19, &v28);
              LastError = v20;
              if ( v20 >= 0 )
              {
                if ( a6 )
                {
                  v21 = v28;
                  v28 = 0;
                  *a6 = v21;
                }
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v28);
                LOBYTE(v22) = 1;
                std::wstring::_Tidy(v32, v22, 0);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
                wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&lpSubKey);
                __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
                LastError = 0;
                goto LABEL_29;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xEA,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
                (const char *)(unsigned int)v20,
                dwOptionsa);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v28);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE1,
                (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
                (const char *)(unsigned int)v16,
                dwOptionsa);
            }
            LOBYTE(v17) = 1;
            std::wstring::_Tidy(v32, v17, 0);
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCD,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
            (const char *)(unsigned int)v12,
            dwOptions);
        }
        wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&lpSubKey);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xC1,
                      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
                      v11);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)(unsigned int)v10,
        dwOptions);
    }
LABEL_29:
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSecurityDescriptor);
    return LastError;
  }
  v8 = 171;
LABEL_3:
  LastError = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
    (const char *)0x80070057LL,
    dwOptions);
  return LastError;
}

```

## disassembly

```asm
0x18001f7b0  mov     [rsp-8+arg_0], rbx
0x18001f7b5  push    rbp
0x18001f7b6  push    rsi
0x18001f7b7  push    rdi
0x18001f7b8  push    r14
0x18001f7ba  push    r15
0x18001f7bc  lea     rbp, [rsp-27h]
0x18001f7c1  sub     rsp, 0C0h
0x18001f7c8  mov     rax, cs:__security_cookie
0x18001f7cf  xor     rax, rsp
0x18001f7d2  mov     [rbp+47h+var_30], rax
0x18001f7d6  mov     rdi, r8
0x18001f7d9  mov     r14, rdx
0x18001f7dc  mov     rsi, [rbp+47h+arg_28]
0x18001f7e0  xor     r15d, r15d
0x18001f7e3  test    rdx, rdx
0x18001f7e6  jnz     short loc_18001F80A
0x18001f7e8  mov     edx, 0ABh; void *
0x18001f7ed  mov     ebx, 80070057h
0x18001f7f2  mov     rcx, [rbp+4Fh]; this
0x18001f7f6  mov     r9d, ebx; char *
0x18001f7f9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f805  jmp     loc_18001FA6F
0x18001f80a  test    rdi, rdi
0x18001f80d  jnz     short loc_18001F816
0x18001f80f  mov     edx, 0ACh
0x18001f814  jmp     short loc_18001F7ED
0x18001f816  test    r9, r9
0x18001f819  jnz     short loc_18001F822
0x18001f81b  mov     edx, 0ADh
0x18001f820  jmp     short loc_18001F7ED
0x18001f822  mov     [rbp+47h+StringSecurityDescriptor], r15
0x18001f826  lea     rdx, aDAOiciKaCoAOic; "D:(A;OICI;KA;;;CO)(A;OICI;KA;;;SY)(A;OI"...
0x18001f82d  lea     rcx, [rbp+47h+StringSecurityDescriptor]
0x18001f831  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001f836  mov     ebx, eax
0x18001f838  test    eax, eax
0x18001f83a  jns     short loc_18001F859
0x18001f83c  mov     rcx, [rbp+4Fh]; this
0x18001f840  mov     r9d, eax; char *
0x18001f843  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f84a  mov     edx, 0B9h; void *
0x18001f84f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f854  jmp     loc_18001FA66
0x18001f859  mov     [rbp+47h+SecurityDescriptor], r15
0x18001f85d  xor     r9d, r9d; SecurityDescriptorSize
0x18001f860  lea     r8, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x18001f864  lea     edx, [r9+1]; StringSDRevision
0x18001f868  mov     rcx, [rbp+47h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001f86c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001f873  nop     dword ptr [rax+rax+00h]
0x18001f878  test    eax, eax
0x18001f87a  jnz     short loc_18001F8A1
0x18001f87c  mov     rcx, [rbp+4Fh]; this
0x18001f880  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f887  mov     edx, 0C1h; void *
0x18001f88c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f891  mov     ebx, eax
0x18001f893  lea     rcx, [rbp+47h+SecurityDescriptor]
0x18001f897  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f89c  jmp     loc_18001FA66
0x18001f8a1  mov     qword ptr [rbp+47h+SecurityAttributes.nLength], 18h
0x18001f8a9  mov     qword ptr [rbp+47h+SecurityAttributes.bInheritHandle], r15
0x18001f8ad  mov     rax, [rbp+47h+SecurityDescriptor]
0x18001f8b1  mov     [rbp+47h+SecurityAttributes.lpSecurityDescriptor], rax
0x18001f8b5  mov     [rbp+47h+lpSubKey], r15
0x18001f8b9  mov     r8, rdi
0x18001f8bc  lea     rdx, aSSoftwareClass_1; "%s\\Software\\Classes\\Local Settings\\"...
0x18001f8c3  lea     rcx, [rbp+47h+lpSubKey]
0x18001f8c7  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001f8cc  mov     ebx, eax
0x18001f8ce  test    eax, eax
0x18001f8d0  jns     short loc_18001F8F6
0x18001f8d2  mov     rcx, [rbp+4Fh]; this
0x18001f8d6  mov     r9d, eax; char *
0x18001f8d9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f8e0  mov     edx, 0CDh; void *
0x18001f8e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f8ea  nop
0x18001f8eb  lea     rcx, [rbp+47h+lpSubKey]
0x18001f8ef  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001f8f4  jmp     short loc_18001F893
0x18001f8f6  mov     [rbp+47h+var_78], r15
0x18001f8fa  lea     rcx, [rbp+47h+var_78]
0x18001f8fe  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001f903  mov     [rsp+0E0h+lpdwDisposition], r15; lpdwDisposition
0x18001f908  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18001f90d  lea     rax, [rbp+47h+SecurityAttributes]
0x18001f911  mov     [rsp+0E0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18001f916  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x18001f91e  mov     [rsp+0E0h+dwOptions], r15d; int
0x18001f923  xor     r9d, r9d; lpClass
0x18001f926  xor     r8d, r8d; Reserved
0x18001f929  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18001f92d  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001f934  call    cs:__imp_RegCreateKeyExW
0x18001f93b  nop     dword ptr [rax+rax+00h]
0x18001f940  test    eax, eax
0x18001f942  jz      short loc_18001F969
0x18001f944  mov     rcx, [rbp+4Fh]; this
0x18001f948  mov     r9d, eax; char *
0x18001f94b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f952  mov     edx, 0DAh; void *
0x18001f957  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f95c  mov     ebx, eax
0x18001f95e  lea     rcx, [rbp+47h+var_78]
0x18001f962  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001f967  jmp     short loc_18001F8EB
0x18001f969  mov     [rbp+47h+var_38], 7
0x18001f971  mov     [rbp+47h+var_40], r15
0x18001f975  mov     word ptr [rbp+47h+var_50], r15w
0x18001f97a  lea     r9, [rbp+47h+var_50]
0x18001f97e  mov     r8, rdi
0x18001f981  mov     rdx, r14
0x18001f984  call    ?DeriveLpacTopRegistryKey@LpacRegHelper@@CAJPEAXPEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LpacRegHelper::DeriveLpacTopRegistryKey(void *,ushort const *,ushort const *,std::wstring &)
0x18001f989  mov     ebx, eax
0x18001f98b  test    eax, eax
0x18001f98d  jns     short loc_18001F9B8
0x18001f98f  mov     rcx, [rbp+4Fh]; this
0x18001f993  mov     r9d, eax; char *
0x18001f996  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f99d  mov     edx, 0E1h; void *
0x18001f9a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9a7  nop
0x18001f9a8  xor     r8d, r8d
0x18001f9ab  mov     dl, 1
0x18001f9ad  lea     rcx, [rbp+47h+var_50]
0x18001f9b1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001f9b6  jmp     short loc_18001F95E
0x18001f9b8  movzx   eax, word ptr cs:aLpaccapabiliti; "\\LpacCapabilities"
0x18001f9bf  neg     ax
0x18001f9c2  sbb     r8, r8
0x18001f9c5  and     r8d, 11h
0x18001f9c9  lea     rdx, aLpaccapabiliti; "\\LpacCapabilities"
0x18001f9d0  lea     rcx, [rbp+47h+var_50]
0x18001f9d4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001f9d9  mov     [rbp+47h+var_80], r15
0x18001f9dd  lea     rdx, [rbp+47h+var_50]
0x18001f9e1  cmp     [rbp+47h+var_38], 8
0x18001f9e6  cmovnb  rdx, [rbp+47h+var_50]
0x18001f9eb  lea     r8, [rbp+47h+var_80]
0x18001f9ef  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001f9f4  mov     ebx, eax
0x18001f9f6  test    eax, eax
0x18001f9f8  jns     short loc_18001FA1D
0x18001f9fa  mov     rcx, [rbp+4Fh]; this
0x18001f9fe  mov     r9d, eax; char *
0x18001fa01  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fa08  mov     edx, 0EAh; void *
0x18001fa0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fa12  lea     rcx, [rbp+47h+var_80]
0x18001fa16  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fa1b  jmp     short loc_18001F9A8
0x18001fa1d  test    rsi, rsi
0x18001fa20  jz      short loc_18001FA2D
0x18001fa22  mov     rax, [rbp+47h+var_80]
0x18001fa26  mov     [rbp+47h+var_80], r15
0x18001fa2a  mov     [rsi], rax
0x18001fa2d  lea     rcx, [rbp+47h+var_80]
0x18001fa31  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fa36  nop
0x18001fa37  xor     r8d, r8d
0x18001fa3a  mov     dl, 1
0x18001fa3c  lea     rcx, [rbp+47h+var_50]
0x18001fa40  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001fa45  nop
0x18001fa46  lea     rcx, [rbp+47h+var_78]
0x18001fa4a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fa4f  nop
0x18001fa50  lea     rcx, [rbp+47h+lpSubKey]
0x18001fa54  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001fa59  nop
0x18001fa5a  lea     rcx, [rbp+47h+SecurityDescriptor]
0x18001fa5e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fa63  mov     ebx, r15d
0x18001fa66  lea     rcx, [rbp+47h+StringSecurityDescriptor]
0x18001fa6a  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001fa6f  mov     eax, ebx
0x18001fa71  mov     rcx, [rbp+47h+var_30]
0x18001fa75  xor     rcx, rsp; StackCookie
0x18001fa78  call    __security_check_cookie
0x18001fa7d  mov     rbx, [rsp+0E0h+arg_0]
0x18001fa85  add     rsp, 0C0h
0x18001fa8c  pop     r15
0x18001fa8e  pop     r14
0x18001fa90  pop     rdi
0x18001fa91  pop     rsi
0x18001fa92  pop     rbp
0x18001fa93  retn
```
