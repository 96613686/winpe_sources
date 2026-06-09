# OfflineDomainJoinCspNode::Execute(tagVARIANT)

- ea: `0x180054f40`
- end: `0x1800551a5`
- name: `?Execute@OfflineDomainJoinCspNode@@UEAAJUtagVARIANT@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(OfflineDomainJoinCspNode *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000d4d4`
- `0x180025ac0`
- `0x18002dcc8`
- `0x180054f40`
- `0x1800d11a4`
- `0x1800d16c8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800550d3`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800550d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054fc5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18005505c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18005505c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18005502a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18005502a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180054ff8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180054ff8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005512c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005512c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180054fb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180054fb5`
- `netjoin!NetRequestOfflineDomainJoin` at `0x18005508c`
- `netjoin!NetRequestOfflineDomainJoin` at `0x18005508c`

## pseudocode

```c
signed int __fastcall OfflineDomainJoinCspNode::Execute(OfflineDomainJoinCspNode *this, struct tagVARIANT *a2)
{
  int LBound; // ebx
  __int64 v4; // rdx
  signed int result; // eax
  SAFEARRAY *parray; // rcx
  SAFEARRAY *v7; // rcx
  SAFEARRAY *v8; // rcx
  signed int v9; // eax
  CEnrollmentLogger *Logger; // rax
  char IsStateSeparationEnabled; // al
  const WCHAR *v12; // rdx
  LSTATUS v13; // eax
  signed int v14; // edi
  DWORD dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-E0h]
  LONG plUbound; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  LONG plLbound; // [rsp+60h] [rbp-A0h] BYREF
  void *ppvData; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  if ( *((_DWORD *)this + 11) )
  {
    LBound = -2046820335;
    v4 = 109;
    goto LABEL_3;
  }
  memset_0(Buffer, 0, 0x208u);
  if ( GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    parray = a2->parray;
    ppvData = 0;
    LBound = SafeArrayAccessData(parray, &ppvData);
    if ( LBound >= 0 )
    {
      v7 = a2->parray;
      plLbound = 0;
      LBound = SafeArrayGetLBound(v7, 1u, &plLbound);
      if ( LBound >= 0 )
      {
        v8 = a2->parray;
        plUbound = 0;
        LBound = SafeArrayGetUBound(v8, 1u, &plUbound);
        if ( LBound >= 0 )
        {
          v9 = NetRequestOfflineDomainJoin((BYTE *)ppvData, plUbound, 0x40000000u, Buffer);
          LBound = v9;
          if ( v9 > 0 )
            LBound = (unsigned __int16)v9 | 0x80070000;
          Logger = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogNetRequestOfflineDomainJoin(Logger, LBound);
          if ( LBound >= 0 )
          {
            phkResult = 0;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &phkResult,
              0);
            IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
            v12 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\SyncML\\OdjApplied";
            if ( !IsStateSeparationEnabled )
              v12 = L"Software\\Microsoft\\Provisioning\\OMADM\\SyncML\\OdjApplied";
            v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
            v14 = v13;
            if ( v13 > 0 )
              v14 = (unsigned __int16)v13 | 0x80070000;
            if ( v14 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x65,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\offlinedomainjoin\\offlinedomainjoincspnode.cpp",
                (const char *)(unsigned int)v14,
                dwOptionsa);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
              return v14;
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          }
          return LBound;
        }
        v4 = 78;
      }
      else
      {
        v4 = 74;
      }
    }
    else
    {
      v4 = 68;
    }
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\offlinedomainjoin\\offlinedomainjoincspnode.cpp",
      (const char *)(unsigned int)LBound,
      dwOptions);
    return LBound;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180054f40  mov     [rsp-8+arg_0], rbx
0x180054f45  mov     [rsp-8+arg_10], rdi
0x180054f4a  push    rbp
0x180054f4b  lea     rbp, [rsp-190h]
0x180054f53  sub     rsp, 290h
0x180054f5a  mov     rax, cs:__security_cookie
0x180054f61  xor     rax, rsp
0x180054f64  mov     [rbp+190h+var_10], rax
0x180054f6b  cmp     dword ptr [rcx+2Ch], 0
0x180054f6f  mov     rdi, rdx
0x180054f72  jz      short loc_180054F99
0x180054f74  mov     ebx, 86000011h
0x180054f79  mov     edx, 6Dh ; 'm'; void *
0x180054f7e  mov     rcx, [rbp+198h]; this
0x180054f85  lea     r8, aOnecoreuapAdmi_43; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180054f8c  mov     r9d, ebx; char *
0x180054f8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054f94  jmp     loc_18005517E
0x180054f99  xor     edx, edx; Val
0x180054f9b  lea     rcx, [rsp+290h+Buffer]; void *
0x180054fa0  mov     r8d, 208h; Size
0x180054fa6  call    memset_0
0x180054fab  mov     edx, 104h; uSize
0x180054fb0  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x180054fb5  call    cs:__imp_GetWindowsDirectoryW
0x180054fbc  nop     dword ptr [rax+rax+00h]
0x180054fc1  test    eax, eax
0x180054fc3  jnz     short loc_180054FE6
0x180054fc5  call    cs:__imp_GetLastError
0x180054fcc  nop     dword ptr [rax+rax+00h]
0x180054fd1  test    eax, eax
0x180054fd3  jle     loc_180055180
0x180054fd9  movzx   eax, ax
0x180054fdc  or      eax, 80070000h
0x180054fe1  jmp     loc_180055180
0x180054fe6  mov     rcx, [rdi+8]; psa
0x180054fea  lea     rdx, [rsp+290h+ppvData]; ppvData
0x180054fef  mov     [rsp+290h+ppvData], 0
0x180054ff8  call    cs:__imp_SafeArrayAccessData
0x180054fff  nop     dword ptr [rax+rax+00h]
0x180055004  mov     ebx, eax
0x180055006  test    eax, eax
0x180055008  jns     short loc_180055014
0x18005500a  mov     edx, 44h ; 'D'
0x18005500f  jmp     loc_180054F7E
0x180055014  mov     rcx, [rdi+8]; psa
0x180055018  lea     r8, [rsp+290h+plLbound]; plLbound
0x18005501d  mov     edx, 1; nDim
0x180055022  mov     [rsp+290h+plLbound], 0
0x18005502a  call    cs:__imp_SafeArrayGetLBound
0x180055031  nop     dword ptr [rax+rax+00h]
0x180055036  mov     ebx, eax
0x180055038  test    eax, eax
0x18005503a  jns     short loc_180055046
0x18005503c  mov     edx, 4Ah ; 'J'
0x180055041  jmp     loc_180054F7E
0x180055046  mov     rcx, [rdi+8]; psa
0x18005504a  lea     r8, [rsp+290h+plUbound]; plUbound
0x18005504f  mov     edx, 1; nDim
0x180055054  mov     [rsp+290h+plUbound], 0
0x18005505c  call    cs:__imp_SafeArrayGetUBound
0x180055063  nop     dword ptr [rax+rax+00h]
0x180055068  mov     ebx, eax
0x18005506a  test    eax, eax
0x18005506c  jns     short loc_180055078
0x18005506e  mov     edx, 4Eh ; 'N'
0x180055073  jmp     loc_180054F7E
0x180055078  mov     edx, [rsp+290h+plUbound]; cbProvisionBinDataSize
0x18005507c  lea     r9, [rsp+290h+Buffer]; lpWindowsPath
0x180055081  mov     rcx, [rsp+290h+ppvData]; pProvisionBinData
0x180055086  mov     r8d, 40000000h; dwOptions
0x18005508c  call    cs:__imp_NetRequestOfflineDomainJoin
0x180055093  nop     dword ptr [rax+rax+00h]
0x180055098  mov     ebx, eax
0x18005509a  test    eax, eax
0x18005509c  jle     short loc_1800550A7
0x18005509e  movzx   ebx, ax
0x1800550a1  or      ebx, 80070000h
0x1800550a7  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800550ac  mov     edx, ebx; int
0x1800550ae  mov     rcx, rax; this
0x1800550b1  call    ?LogNetRequestOfflineDomainJoin@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogNetRequestOfflineDomainJoin(long)
0x1800550b6  test    ebx, ebx
0x1800550b8  js      loc_18005517E
0x1800550be  xor     edx, edx
0x1800550c0  mov     [rsp+290h+var_238], 0
0x1800550c9  lea     rcx, [rsp+290h+var_238]
0x1800550ce  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800550d3  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800550da  nop     dword ptr [rax+rax+00h]
0x1800550df  mov     [rsp+290h+lpdwDisposition], 0; lpdwDisposition
0x1800550e8  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\Provisioning\\OMAD"...
0x1800550ef  test    al, al
0x1800550f1  lea     rdx, aOsdataSoftware_6; "OSData\\Software\\Microsoft\\Provisioni"...
0x1800550f8  lea     rax, [rsp+290h+var_238]
0x1800550fd  mov     [rsp+290h+phkResult], rax; phkResult
0x180055102  cmovz   rdx, rcx; lpSubKey
0x180055106  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005510f  xor     r9d, r9d; lpClass
0x180055112  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x18005511a  xor     r8d, r8d; Reserved
0x18005511d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180055124  mov     [rsp+290h+dwOptions], 0; int
0x18005512c  call    cs:__imp_RegCreateKeyExW
0x180055133  nop     dword ptr [rax+rax+00h]
0x180055138  mov     edi, eax
0x18005513a  test    eax, eax
0x18005513c  jle     short loc_180055147
0x18005513e  movzx   edi, ax
0x180055141  or      edi, 80070000h
0x180055147  test    edi, edi
0x180055149  jns     short loc_180055174
0x18005514b  mov     rcx, [rbp+198h]; this
0x180055152  lea     r8, aOnecoreuapAdmi_43; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180055159  mov     r9d, edi; char *
0x18005515c  mov     edx, 65h ; 'e'; void *
0x180055161  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055166  lea     rcx, [rsp+290h+var_238]
0x18005516b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180055170  mov     eax, edi
0x180055172  jmp     short loc_180055180
0x180055174  lea     rcx, [rsp+290h+var_238]
0x180055179  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005517e  mov     eax, ebx
0x180055180  mov     rcx, [rbp+190h+var_10]
0x180055187  xor     rcx, rsp; StackCookie
0x18005518a  call    __security_check_cookie
0x18005518f  lea     r11, [rsp+290h+var_s0]
0x180055197  mov     rbx, [r11+10h]
0x18005519b  mov     rdi, [r11+20h]
0x18005519f  mov     rsp, r11
0x1800551a2  pop     rbp
0x1800551a3  retn
```
