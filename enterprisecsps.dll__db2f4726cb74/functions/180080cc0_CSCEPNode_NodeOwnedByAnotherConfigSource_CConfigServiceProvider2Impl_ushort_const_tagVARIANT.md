# CSCEPNode::NodeOwnedByAnotherConfigSource(CConfigServiceProvider2Impl *,ushort const *,tagVARIANT *)

- ea: `0x180080cc0`
- end: `0x180080f21`
- name: `?NodeOwnedByAnotherConfigSource@CSCEPNode@@CAJPEAVCConfigServiceProvider2Impl@@PEBGPEAUtagVARIANT@@@Z`
- size: `609`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180080094`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000d4d4`
- `0x18000da10`
- `0x180025a9c`
- `0x180025ac0`
- `0x18003f3a0`
- `0x18003f6f0`
- `0x18007dcc8`
- `0x180080cc0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180080e81`
- `OLEAUT32!__imp_SysAllocString` at `0x180080e81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080d70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080e49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080d70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080e49`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x180080da2`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x180080da2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSCEPNode::NodeOwnedByAnotherConfigSource(
        struct CConfigServiceProvider2Impl *a1,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  LSTATUS v5; // eax
  bool v6; // sf
  int AllSubKeys; // ebx
  __int64 i; // rdi
  LSTATUS v9; // eax
  bool v10; // sf
  BSTR v11; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 **v15; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v17; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v18; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v19; // [rsp+58h] [rbp-A8h] BYREF
  char v20; // [rsp+5Ah] [rbp-A6h]
  __int64 v21; // [rsp+60h] [rbp-A0h]
  _QWORD v22[2]; // [rsp+68h] [rbp-98h] BYREF
  char v23; // [rsp+78h] [rbp-88h]
  WCHAR SubKey[1280]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AC8h] [rbp+9C8h]

  hKey = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v14 = 0;
  v15 = 0;
  v22[0] = &v15;
  v22[1] = &v14;
  v23 = 1;
  if ( CSCEPNode::m_fIsUser )
    AutoImpersonate::ImpersonateTargetedUser((AutoImpersonate *)&v19, a1);
  v5 = RegOpenKeyExW(CSCEPNode::m_hCurrentHive, L"Software\\Microsoft\\SCEP\\", 0, 0x20019u, &hKey);
  v6 = v5 < 0;
  if ( v5 > 0 )
    v6 = 1;
  if ( v6 )
  {
    AllSubKeys = 0;
  }
  else
  {
    AllSubKeys = OmaDmRegistryGetAllSubKeys(hKey, &v14, &v15);
    if ( AllSubKeys >= 0 )
    {
      for ( i = 0; (unsigned int)i < v14; i = (unsigned int)(i + 1) )
      {
        memset_0(SubKey, 0, 0x9FEu);
        AllSubKeys = StringCchCatW(SubKey, 0x4FFu, v15[i]);
        if ( AllSubKeys >= 0 )
        {
          AllSubKeys = StringCchCatW(SubKey, 0x4FFu, L"\\");
          if ( AllSubKeys >= 0 )
          {
            AllSubKeys = StringCchCatW(SubKey, 0x4FFu, a2);
            if ( AllSubKeys >= 0 )
            {
              v17 = 0;
              v9 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &v17);
              v10 = v9 < 0;
              if ( v9 > 0 )
                v10 = 1;
              if ( !v10 )
              {
                v11 = SysAllocString(v15[i]);
                v18 = v11;
                if ( v11 )
                {
                  v18 = 0;
                  a3->llVal = (LONGLONG)v11;
                  AllSubKeys = 0;
                }
                else
                {
                  AllSubKeys = -2147024882;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x967,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\clientcertificates\\scep\\scepnode.cpp",
                    (const char *)0x8007000ELL,
                    phkResult);
                }
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
                break;
              }
              AllSubKeys = 0;
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
            }
          }
        }
      }
    }
  }
  wil::details::ScopeExitFn__lambda_0fef244227ed8fbe41619eaed633318d___::operator()(v22);
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)&v19);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)AllSubKeys;
}

```

## disassembly

```asm
0x180080cc0  push    rbp
0x180080cc2  push    rbx
0x180080cc3  push    rsi
0x180080cc4  push    rdi
0x180080cc5  push    r13
0x180080cc7  push    r14
0x180080cc9  push    r15
0x180080ccb  lea     rbp, [rsp-990h]
0x180080cd3  sub     rsp, 0A90h
0x180080cda  mov     rax, cs:__security_cookie
0x180080ce1  xor     rax, rsp
0x180080ce4  mov     [rbp+9C0h+var_40], rax
0x180080ceb  mov     r14, r8
0x180080cee  mov     r15, rdx
0x180080cf1  mov     [rsp+0AC0h+hKey], 0
0x180080cfa  mov     [rsp+0AC0h+var_A68], 0
0x180080d01  mov     [rsp+0AC0h+var_A66], 0
0x180080d06  mov     [rsp+0AC0h+var_A60], 0
0x180080d0f  mov     [rsp+0AC0h+var_A90], 0
0x180080d17  mov     [rsp+0AC0h+var_A88], 0
0x180080d20  lea     rax, [rsp+0AC0h+var_A88]
0x180080d25  mov     [rsp+0AC0h+var_A58], rax
0x180080d2a  lea     rax, [rsp+0AC0h+var_A90]
0x180080d2f  mov     [rsp+0AC0h+var_A50], rax
0x180080d34  mov     [rsp+0AC0h+var_A48], 1
0x180080d39  cmp     cs:?m_fIsUser@CSCEPNode@@0HA, 0; int CSCEPNode::m_fIsUser
0x180080d40  jz      short loc_180080D4F
0x180080d42  mov     rdx, rcx; struct CConfigServiceProvider2Impl *
0x180080d45  lea     rcx, [rsp+0AC0h+var_A68]; this
0x180080d4a  call    ?ImpersonateTargetedUser@AutoImpersonate@@QEAAJPEAVCConfigServiceProvider2Impl@@@Z; AutoImpersonate::ImpersonateTargetedUser(CConfigServiceProvider2Impl *)
0x180080d4f  lea     rax, [rsp+0AC0h+hKey]
0x180080d54  mov     qword ptr [rsp+0AC0h+phkResult], rax; phkResult
0x180080d59  mov     r9d, 20019h; samDesired
0x180080d5f  xor     r8d, r8d; ulOptions
0x180080d62  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\SCEP\\"
0x180080d69  mov     rcx, cs:?m_hCurrentHive@CSCEPNode@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hKey
0x180080d70  call    cs:__imp_RegOpenKeyExW
0x180080d77  nop     dword ptr [rax+rax+00h]
0x180080d7c  test    eax, eax
0x180080d7e  jle     short loc_180080D8A
0x180080d80  movzx   eax, ax
0x180080d83  or      eax, 80070000h
0x180080d88  test    eax, eax
0x180080d8a  jns     short loc_180080D93
0x180080d8c  xor     ebx, ebx
0x180080d8e  jmp     loc_180080EDD
0x180080d93  lea     r8, [rsp+0AC0h+var_A88]
0x180080d98  lea     rdx, [rsp+0AC0h+var_A90]
0x180080d9d  mov     rcx, [rsp+0AC0h+hKey]
0x180080da2  call    cs:__imp_?OmaDmRegistryGetAllSubKeys@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z; OmaDmRegistryGetAllSubKeys(HKEY__ *,ulong *,ushort * * *)
0x180080da9  nop     dword ptr [rax+rax+00h]
0x180080dae  mov     ebx, eax
0x180080db0  test    eax, eax
0x180080db2  js      loc_180080EDD
0x180080db8  xor     edi, edi
0x180080dba  mov     r13d, 4FFh
0x180080dc0  cmp     edi, [rsp+0AC0h+var_A90]
0x180080dc4  jnb     loc_180080EDD
0x180080dca  xor     edx, edx; Val
0x180080dcc  mov     r8d, 9FEh; Size
0x180080dd2  lea     rcx, [rbp+9C0h+SubKey]; void *
0x180080dd6  call    memset_0
0x180080ddb  mov     r8, [rsp+0AC0h+var_A88]
0x180080de0  mov     r8, [r8+rdi*8]; unsigned __int16 *
0x180080de4  mov     rdx, r13; unsigned __int64
0x180080de7  lea     rcx, [rbp+9C0h+SubKey]; unsigned __int16 *
0x180080deb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180080df0  mov     ebx, eax
0x180080df2  test    eax, eax
0x180080df4  js      short loc_180080E71
0x180080df6  lea     r8, StringValue; "\\"
0x180080dfd  mov     rdx, r13; unsigned __int64
0x180080e00  lea     rcx, [rbp+9C0h+SubKey]; unsigned __int16 *
0x180080e04  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180080e09  mov     ebx, eax
0x180080e0b  test    eax, eax
0x180080e0d  js      short loc_180080E71
0x180080e0f  mov     r8, r15; unsigned __int16 *
0x180080e12  mov     rdx, r13; unsigned __int64
0x180080e15  lea     rcx, [rbp+9C0h+SubKey]; unsigned __int16 *
0x180080e19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180080e1e  mov     ebx, eax
0x180080e20  test    eax, eax
0x180080e22  js      short loc_180080E71
0x180080e24  mov     [rsp+0AC0h+var_A78], 0
0x180080e2d  lea     rax, [rsp+0AC0h+var_A78]
0x180080e32  mov     qword ptr [rsp+0AC0h+phkResult], rax; int
0x180080e37  mov     r9d, 20019h; samDesired
0x180080e3d  xor     r8d, r8d; ulOptions
0x180080e40  lea     rdx, [rbp+9C0h+SubKey]; lpSubKey
0x180080e44  mov     rcx, [rsp+0AC0h+hKey]; hKey
0x180080e49  call    cs:__imp_RegOpenKeyExW
0x180080e50  nop     dword ptr [rax+rax+00h]
0x180080e55  test    eax, eax
0x180080e57  jle     short loc_180080E63
0x180080e59  movzx   eax, ax
0x180080e5c  or      eax, 80070000h
0x180080e61  test    eax, eax
0x180080e63  jns     short loc_180080E78
0x180080e65  xor     ebx, ebx
0x180080e67  lea     rcx, [rsp+0AC0h+var_A78]
0x180080e6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180080e71  inc     edi
0x180080e73  jmp     loc_180080DC0
0x180080e78  mov     rcx, [rsp+0AC0h+var_A88]
0x180080e7d  mov     rcx, [rcx+rdi*8]; psz
0x180080e81  call    cs:__imp_SysAllocString
0x180080e88  nop     dword ptr [rax+rax+00h]
0x180080e8d  mov     [rsp+0AC0h+var_A70], rax
0x180080e92  test    rax, rax
0x180080e95  jz      short loc_180080EA8
0x180080e97  mov     [rsp+0AC0h+var_A70], 0
0x180080ea0  mov     [r14+8], rax
0x180080ea4  xor     ebx, ebx
0x180080ea6  jmp     short loc_180080EC8
0x180080ea8  mov     rcx, [rbp+9C8h]; this
0x180080eaf  mov     ebx, 8007000Eh
0x180080eb4  mov     r9d, ebx; char *
0x180080eb7  lea     r8, aOnecoreuapAdmi_87; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180080ebe  mov     edx, 967h; void *
0x180080ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080ec8  lea     rcx, [rsp+0AC0h+var_A70]
0x180080ecd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180080ed2  lea     rcx, [rsp+0AC0h+var_A78]
0x180080ed7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180080edc  nop
0x180080edd  lea     rcx, [rsp+0AC0h+var_A58]
0x180080ee2  call    wil__details__ScopeExitFn__lambda_0fef244227ed8fbe41619eaed633318d_____operator__
0x180080ee7  nop
0x180080ee8  lea     rcx, [rsp+0AC0h+var_A68]; this
0x180080eed  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x180080ef2  nop
0x180080ef3  lea     rcx, [rsp+0AC0h+hKey]
0x180080ef8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180080efd  mov     eax, ebx
0x180080eff  mov     rcx, [rbp+9C0h+var_40]
0x180080f06  xor     rcx, rsp; StackCookie
0x180080f09  call    __security_check_cookie
0x180080f0e  add     rsp, 0A90h
0x180080f15  pop     r15
0x180080f17  pop     r14
0x180080f19  pop     r13
0x180080f1b  pop     rdi
0x180080f1c  pop     rsi
0x180080f1d  pop     rbx
0x180080f1e  pop     rbp
0x180080f1f  retn
```
