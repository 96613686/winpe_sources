# DefaultActivityContextStore::GetActivityContextFromStore(_GUID const &,ActivityContext * *)

- ea: `0x18000faf0`
- end: `0x18000fe05`
- name: `?GetActivityContextFromStore@DefaultActivityContextStore@@UEAAJAEBU_GUID@@PEAPEAVActivityContext@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(DefaultActivityContextStore *this, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001a70`
- `0x180001b40`
- `0x180002d9c`
- `0x1800040a4`
- `0x180005aec`
- `0x18000dd1c`
- `0x18000dd70`
- `0x18000deb0`
- `0x18000e938`
- `0x18000ec2c`
- `0x18000eecc`
- `0x18000faf0`
- `0x180011170`
- `0x1800115bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000fb69`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000fb69`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fc91`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fcfc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fd4e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fda1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fc91`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fcfc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fd4e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000fda1`

## string_xrefs

- `0x18000fd21`: `AttemptCounter`
- `0x18000fd74`: `Rollback`

## pseudocode

```c
__int64 __fastcall DefaultActivityContextStore::GetActivityContextFromStore(
        DefaultActivityContextStore *this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  LSTATUS v5; // edi
  const unsigned __int16 *EnrollmentsRootKey; // rax
  __int64 v7; // rdx
  ActivityContext *v8; // rax
  struct IUnknown *v9; // rax
  struct IUnknown *v10; // rsi
  HKEY v11; // rbx
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+44h] [rbp-BCh] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v16; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v18; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD v19; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v20; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v22; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v24[40]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SubKey[264]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 pvData[264]; // [rsp+330h] [rbp+230h] BYREF

  v16 = 0;
  hkey = 0;
  v22 = 0;
  SubKey[0] = 0;
  v24[0] = 0;
  sz[0] = 0;
  if ( a3 )
  {
    if ( StringFromGUID2(a2, sz, 39) == 39 )
    {
      v5 = EEDBTrimGuidBracket(sz, v24);
      if ( v5 >= 0 )
      {
        EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
        v5 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v24);
        if ( v5 >= 0 )
        {
          v5 = EEDBManager::OpenHKEY(SubKey, v7, &v22);
          if ( v5 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &hkey,
              v22);
            v8 = (ActivityContext *)operator new(0x3D8u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v8
              && (v9 = (struct IUnknown *)ActivityContext::ActivityContext(v8)) != 0
              && (ATL::AtlComPtrAssign(&v16, v9), (v10 = v16) != 0) )
            {
              v5 = ActivityContext::set_Key((ActivityContext *)v16, a2);
              if ( v5 >= 0 )
              {
                v11 = hkey;
                pcbData = 520;
                if ( RegGetValueW(hkey, 0, L"OrchestratorType", 2u, 0, pvData, &pcbData)
                  || (v5 = StringCchCopyW((unsigned __int16 *)&v10[56], 0x104u, pvData), v5 >= 0) )
                {
                  v13 = 0;
                  v18 = 4;
                  if ( !RegGetValueW(v11, 0, L"ActivityType", 0x10u, 0, &v13, &v18) )
                  {
                    v5 = 0;
                    LODWORD(v10[4].lpVtbl) = v13;
                  }
                  v14 = 0;
                  v19 = 4;
                  if ( !RegGetValueW(v11, 0, L"AttemptCounter", 0x10u, 0, &v14, &v19) )
                    LODWORD(v10[121].lpVtbl) = v14;
                  v15 = 0;
                  v20 = 4;
                  if ( !RegGetValueW(v11, 0, L"Rollback", 0x10u, 0, &v15, &v20) )
                    LODWORD(v10[54].lpVtbl) = v15;
                  v16 = 0;
                  *a3 = v10;
                }
              }
            }
            else
            {
              v5 = -2147024882;
            }
          }
        }
      }
    }
    else
    {
      v5 = -2147418113;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>((__int64 *)&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000faf0  mov     [rsp-8+arg_0], rbx
0x18000faf5  mov     [rsp-8+arg_18], rsi
0x18000fafa  push    rbp
0x18000fafb  push    rdi
0x18000fafc  push    r14
0x18000fafe  lea     rbp, [rsp-450h]
0x18000fb06  sub     rsp, 550h
0x18000fb0d  mov     rax, cs:__security_cookie
0x18000fb14  xor     rax, rsp
0x18000fb17  mov     [rbp+460h+var_20], rax
0x18000fb1e  xor     eax, eax
0x18000fb20  mov     [rsp+560h+var_510], 0
0x18000fb29  mov     [rsp+560h+hkey], 0
0x18000fb32  mov     r14, r8
0x18000fb35  mov     [rsp+560h+var_4F0], 0
0x18000fb3e  mov     rbx, rdx
0x18000fb41  mov     [rbp+460h+SubKey], ax
0x18000fb45  mov     [rbp+460h+var_490], ax
0x18000fb49  mov     [rbp+460h+sz], ax
0x18000fb4d  test    r8, r8
0x18000fb50  jnz     short loc_18000FB5C
0x18000fb52  mov     edi, 80070057h
0x18000fb57  jmp     loc_18000FDC8
0x18000fb5c  mov     r8d, 27h ; '''; cchMax
0x18000fb62  lea     rdx, [rbp+460h+sz]; lpsz
0x18000fb66  mov     rcx, rbx; rguid
0x18000fb69  call    cs:__imp_StringFromGUID2
0x18000fb6f  cmp     eax, 27h ; '''
0x18000fb72  jz      short loc_18000FB7E
0x18000fb74  mov     edi, 8000FFFFh
0x18000fb79  jmp     loc_18000FDC8
0x18000fb7e  lea     rdx, [rbp+460h+var_490]; unsigned __int16 *
0x18000fb82  lea     rcx, [rbp+460h+sz]; unsigned __int16 *
0x18000fb86  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x18000fb8b  mov     edi, eax
0x18000fb8d  test    eax, eax
0x18000fb8f  js      loc_18000FDC8
0x18000fb95  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18000fb9a  lea     rcx, [rbp+460h+var_490]
0x18000fb9e  mov     r9, rax
0x18000fba1  mov     [rsp+560h+pvData], rcx
0x18000fba6  lea     r8, aSSS; "%s\\%s\\%s"
0x18000fbad  lea     rcx, aContext; "Context"
0x18000fbb4  mov     edx, 104h; unsigned __int64
0x18000fbb9  mov     [rsp+560h+pdwType], rcx
0x18000fbbe  lea     rcx, [rbp+460h+SubKey]; unsigned __int16 *
0x18000fbc2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fbc7  mov     edi, eax
0x18000fbc9  test    eax, eax
0x18000fbcb  js      loc_18000FDC8
0x18000fbd1  lea     r8, [rsp+560h+var_4F0]; HKEY *
0x18000fbd6  lea     rcx, [rbp+460h+SubKey]; lpSubKey
0x18000fbda  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x18000fbdf  mov     edi, eax
0x18000fbe1  test    eax, eax
0x18000fbe3  js      loc_18000FDC8
0x18000fbe9  mov     rdx, [rsp+560h+var_4F0]
0x18000fbee  lea     rcx, [rsp+560h+hkey]
0x18000fbf3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000fbf8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fbff  mov     ecx, 3D8h; unsigned __int64
0x18000fc04  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000fc09  test    rax, rax
0x18000fc0c  jz      loc_18000FDC3
0x18000fc12  mov     rcx, rax; this
0x18000fc15  call    ??0ActivityContext@@QEAA@XZ; ActivityContext::ActivityContext(void)
0x18000fc1a  test    rax, rax
0x18000fc1d  jz      loc_18000FDC3
0x18000fc23  mov     rdx, rax; struct IUnknown *
0x18000fc26  lea     rcx, [rsp+560h+var_510]; struct IUnknown **
0x18000fc2b  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000fc30  mov     rsi, [rsp+560h+var_510]
0x18000fc35  test    rsi, rsi
0x18000fc38  jz      loc_18000FDC3
0x18000fc3e  mov     rdx, rbx; struct _GUID *
0x18000fc41  mov     rcx, rsi; this
0x18000fc44  call    ?set_Key@ActivityContext@@QEAAJAEBU_GUID@@@Z; ActivityContext::set_Key(_GUID const &)
0x18000fc49  mov     edi, eax
0x18000fc4b  test    eax, eax
0x18000fc4d  js      loc_18000FDC8
0x18000fc53  mov     rbx, [rsp+560h+hkey]
0x18000fc58  lea     rax, [rsp+560h+var_508]
0x18000fc5d  mov     [rsp+560h+pcbData], rax; pcbData
0x18000fc62  lea     r8, aOrchestratorty; "OrchestratorType"
0x18000fc69  lea     rax, [rbp+460h+var_230]
0x18000fc70  mov     [rsp+560h+var_508], 208h
0x18000fc78  mov     [rsp+560h+pvData], rax; pvData
0x18000fc7d  mov     r9d, 2; dwFlags
0x18000fc83  xor     edx, edx; lpSubKey
0x18000fc85  mov     [rsp+560h+pdwType], 0; pdwType
0x18000fc8e  mov     rcx, rbx; hkey
0x18000fc91  call    cs:__imp_RegGetValueW
0x18000fc97  test    eax, eax
0x18000fc99  jnz     short loc_18000FCBD
0x18000fc9b  lea     rcx, [rsi+1C0h]; unsigned __int16 *
0x18000fca2  mov     edx, 104h; unsigned __int64
0x18000fca7  lea     r8, [rbp+460h+var_230]; unsigned __int16 *
0x18000fcae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fcb3  mov     edi, eax
0x18000fcb5  test    eax, eax
0x18000fcb7  js      loc_18000FDC8
0x18000fcbd  lea     rax, [rsp+560h+var_504]
0x18000fcc2  mov     [rsp+560h+var_520], 0
0x18000fcca  mov     [rsp+560h+pcbData], rax; pcbData
0x18000fccf  lea     r8, aActivitytype; "ActivityType"
0x18000fcd6  lea     rax, [rsp+560h+var_520]
0x18000fcdb  mov     [rsp+560h+var_504], 4
0x18000fce3  mov     [rsp+560h+pvData], rax; pvData
0x18000fce8  mov     r9d, 10h; dwFlags
0x18000fcee  xor     edx, edx; lpSubKey
0x18000fcf0  mov     [rsp+560h+pdwType], 0; pdwType
0x18000fcf9  mov     rcx, rbx; hkey
0x18000fcfc  call    cs:__imp_RegGetValueW
0x18000fd02  test    eax, eax
0x18000fd04  jnz     short loc_18000FD0F
0x18000fd06  mov     eax, [rsp+560h+var_520]
0x18000fd0a  xor     edi, edi
0x18000fd0c  mov     [rsi+20h], eax
0x18000fd0f  lea     rax, [rsp+560h+var_500]
0x18000fd14  mov     [rsp+560h+var_51C], 0
0x18000fd1c  mov     [rsp+560h+pcbData], rax; pcbData
0x18000fd21  lea     r8, aAttemptcounter; "AttemptCounter"
0x18000fd28  lea     rax, [rsp+560h+var_51C]
0x18000fd2d  mov     [rsp+560h+var_500], 4
0x18000fd35  mov     [rsp+560h+pvData], rax; pvData
0x18000fd3a  mov     r9d, 10h; dwFlags
0x18000fd40  xor     edx, edx; lpSubKey
0x18000fd42  mov     [rsp+560h+pdwType], 0; pdwType
0x18000fd4b  mov     rcx, rbx; hkey
0x18000fd4e  call    cs:__imp_RegGetValueW
0x18000fd54  test    eax, eax
0x18000fd56  jnz     short loc_18000FD62
0x18000fd58  mov     eax, [rsp+560h+var_51C]
0x18000fd5c  mov     [rsi+3C8h], eax
0x18000fd62  lea     rax, [rsp+560h+var_4FC]
0x18000fd67  mov     [rsp+560h+var_518], 0
0x18000fd6f  mov     [rsp+560h+pcbData], rax; pcbData
0x18000fd74  lea     r8, aRollback; "Rollback"
0x18000fd7b  lea     rax, [rsp+560h+var_518]
0x18000fd80  mov     [rsp+560h+var_4FC], 4
0x18000fd88  mov     [rsp+560h+pvData], rax; pvData
0x18000fd8d  mov     r9d, 10h; dwFlags
0x18000fd93  xor     edx, edx; lpSubKey
0x18000fd95  mov     [rsp+560h+pdwType], 0; pdwType
0x18000fd9e  mov     rcx, rbx; hkey
0x18000fda1  call    cs:__imp_RegGetValueW
0x18000fda7  test    eax, eax
0x18000fda9  jnz     short loc_18000FDB5
0x18000fdab  mov     eax, [rsp+560h+var_518]
0x18000fdaf  mov     [rsi+1B0h], eax
0x18000fdb5  mov     [rsp+560h+var_510], 0
0x18000fdbe  mov     [r14], rsi
0x18000fdc1  jmp     short loc_18000FDC8
0x18000fdc3  mov     edi, 8007000Eh
0x18000fdc8  lea     rcx, [rsp+560h+hkey]
0x18000fdcd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000fdd2  lea     rcx, [rsp+560h+var_510]
0x18000fdd7  call    ??1?$CComPtrBase@VEnrollment@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(void)
0x18000fddc  mov     eax, edi
0x18000fdde  mov     rcx, [rbp+460h+var_20]
0x18000fde5  xor     rcx, rsp; StackCookie
0x18000fde8  call    __security_check_cookie
0x18000fded  lea     r11, [rsp+560h+var_10]
0x18000fdf5  mov     rbx, [r11+20h]
0x18000fdf9  mov     rsi, [r11+38h]
0x18000fdfd  mov     rsp, r11
0x18000fe00  pop     r14
0x18000fe02  pop     rdi
0x18000fe03  pop     rbp
0x18000fe04  retn
```
