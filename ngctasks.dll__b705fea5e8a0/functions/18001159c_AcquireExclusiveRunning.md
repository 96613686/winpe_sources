# AcquireExclusiveRunning

- ea: `0x18001159c`
- end: `0x1800117d4`
- name: `AcquireExclusiveRunning`
- size: `568`
- prototype: `char __fastcall(HANDLE hHandle, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014c24`
- `0x180014ea4`

## callees

- `0x180008c74`
- `0x18000ebc0`
- `0x18000ef9c`
- `0x180010310`
- `0x18001159c`
- `0x180013be0`
- `0x180013c00`
- `0x180014bcc`
- `0x18001c9ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011705`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011705`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011649`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800116d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011649`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800116d2`

## string_xrefs

- `0x1800115dc`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180011666`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180011726`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x18001174c`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x18001179a`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall AcquireExclusiveRunning(HANDLE hHandle, LPCWSTR lpSubKey)
{
  const unsigned __int16 *v4; // rdx
  NgcUtils *v5; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  int v7; // eax
  int v8; // eax
  char v9; // bl
  signed int v10; // eax
  const char *v11; // r9
  DWORD dwOptions; // [rsp+20h] [rbp-58h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-58h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-58h]
  DWORD dwDisposition; // [rsp+50h] [rbp-28h] BYREF
  LPCWSTR lpSubKeya; // [rsp+58h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-18h] BYREF
  HKEY phkResult[2]; // [rsp+68h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  lpSubKeya = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKeya,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v5,
                                        v4,
                                        L"PregenKeys",
                                        (unsigned __int16 *)&lpSubKeya);
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    hKey = 0;
    dwDisposition = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKeya, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    if ( v7 >= 0 )
    {
      while ( 1 )
      {
        phkResult[0] = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          phkResult,
          0);
        v8 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, 0x20006u, 0, phkResult, &dwDisposition);
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        if ( v8 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x7A,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
            (const char *)(unsigned int)v8,
            dwOptionsb);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          goto LABEL_23;
        }
        if ( dwDisposition == 1 )
        {
          v9 = 1;
LABEL_21:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKeya);
          return v9;
        }
        v9 = 0;
        if ( !hHandle )
          goto LABEL_21;
        v10 = WaitForSingleObject(hHandle, 0x927C0u);
        if ( v10 )
          break;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
      }
      if ( v10 == -1 )
      {
        wil::details::in1diag3::Log_GetLastError(
          retaddr,
          (void *)0x8E,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          v11);
      }
      else
      {
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x92,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v10,
          dwOptionsb);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v7,
        dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      dwOptions);
  }
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKeya);
  return 0;
}

```

## disassembly

```asm
0x18001159c  push    rbp
0x18001159e  push    rbx
0x18001159f  push    rsi
0x1800115a0  push    rdi
0x1800115a1  mov     rbp, rsp
0x1800115a4  sub     rsp, 78h
0x1800115a8  mov     rsi, rdx
0x1800115ab  mov     rdi, rcx
0x1800115ae  mov     [rbp+lpSubKey], 0
0x1800115b6  xor     edx, edx
0x1800115b8  lea     rcx, [rbp+lpSubKey]
0x1800115bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800115c1  lea     r9, [rbp+lpSubKey]; unsigned __int16 *
0x1800115c5  lea     r8, aPregenkeys; "PregenKeys"
0x1800115cc  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800115d1  mov     rcx, [rbp+20h]; this
0x1800115d5  test    eax, eax
0x1800115d7  jns     short loc_1800115F3
0x1800115d9  mov     r9d, eax; char *
0x1800115dc  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800115e3  mov     edx, 56h ; 'V'; void *
0x1800115e8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800115ed  nop
0x1800115ee  jmp     loc_1800117C0
0x1800115f3  mov     [rbp+hKey], 0
0x1800115fb  mov     [rbp+dwDisposition], 0
0x180011602  xor     edx, edx
0x180011604  lea     rcx, [rbp+hKey]
0x180011608  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001160d  lea     rax, [rbp+dwDisposition]
0x180011611  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180011616  lea     rax, [rbp+hKey]
0x18001161a  mov     [rsp+78h+phkResult], rax; phkResult
0x18001161f  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180011628  mov     [rsp+78h+samDesired], 20006h; samDesired
0x180011630  mov     [rsp+78h+dwOptions], 0; int
0x180011638  xor     r9d, r9d; lpClass
0x18001163b  xor     r8d, r8d; Reserved
0x18001163e  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180011642  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011649  call    cs:__imp_RegCreateKeyExW
0x18001164f  test    eax, eax
0x180011651  jle     short loc_18001165B
0x180011653  movzx   eax, ax
0x180011656  or      eax, 80070000h
0x18001165b  mov     rcx, [rbp+20h]; this
0x18001165f  test    eax, eax
0x180011661  jns     short loc_180011687
0x180011663  mov     r9d, eax; char *
0x180011666  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001166d  mov     edx, 67h ; 'g'; void *
0x180011672  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011677  nop
0x180011678  lea     rcx, [rbp+hKey]
0x18001167c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011681  nop
0x180011682  jmp     loc_1800117C0
0x180011687  mov     [rbp+var_10], 0
0x18001168f  xor     edx, edx
0x180011691  lea     rcx, [rbp+var_10]
0x180011695  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001169a  lea     rax, [rbp+dwDisposition]
0x18001169e  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x1800116a3  lea     rax, [rbp+var_10]
0x1800116a7  mov     [rsp+78h+phkResult], rax; phkResult
0x1800116ac  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800116b5  mov     [rsp+78h+samDesired], 20006h; samDesired
0x1800116bd  mov     [rsp+78h+dwOptions], 1; int
0x1800116c5  xor     r9d, r9d; lpClass
0x1800116c8  xor     r8d, r8d; Reserved
0x1800116cb  mov     rdx, rsi; lpSubKey
0x1800116ce  mov     rcx, [rbp+hKey]; hKey
0x1800116d2  call    cs:__imp_RegCreateKeyExW
0x1800116d8  test    eax, eax
0x1800116da  jle     short loc_1800116E4
0x1800116dc  movzx   eax, ax
0x1800116df  or      eax, 80070000h
0x1800116e4  mov     rcx, [rbp+20h]; this
0x1800116e8  test    eax, eax
0x1800116ea  js      loc_180011797
0x1800116f0  cmp     [rbp+dwDisposition], 1
0x1800116f4  jz      short loc_180011774
0x1800116f6  xor     bl, bl
0x1800116f8  test    rdi, rdi
0x1800116fb  jz      short loc_180011776
0x1800116fd  mov     edx, 927C0h; dwMilliseconds
0x180011702  mov     rcx, rdi; hHandle
0x180011705  call    cs:__imp_WaitForSingleObject
0x18001170b  test    eax, eax
0x18001170d  jnz     short loc_18001171D
0x18001170f  lea     rcx, [rbp+var_10]
0x180011713  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011718  jmp     loc_180011687
0x18001171d  cmp     eax, 0FFFFFFFFh
0x180011720  jnz     short loc_180011739
0x180011722  mov     rcx, [rbp+20h]; this
0x180011726  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001172d  mov     edx, 8Eh; void *
0x180011732  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180011737  jmp     short loc_18001175E
0x180011739  test    eax, eax
0x18001173b  jle     short loc_180011745
0x18001173d  movzx   eax, ax
0x180011740  or      eax, 80070000h
0x180011745  mov     rcx, [rbp+20h]; this
0x180011749  mov     r9d, eax; char *
0x18001174c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180011753  mov     edx, 92h; void *
0x180011758  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001175d  nop
0x18001175e  lea     rcx, [rbp+var_10]
0x180011762  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011767  nop
0x180011768  lea     rcx, [rbp+hKey]
0x18001176c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011771  nop
0x180011772  jmp     short loc_1800117C0
0x180011774  mov     bl, 1
0x180011776  lea     rcx, [rbp+var_10]
0x18001177a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001177f  nop
0x180011780  lea     rcx, [rbp+hKey]
0x180011784  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011789  nop
0x18001178a  lea     rcx, [rbp+lpSubKey]
0x18001178e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011793  mov     al, bl
0x180011795  jmp     short loc_1800117CB
0x180011797  mov     r9d, eax; char *
0x18001179a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800117a1  mov     edx, 7Ah ; 'z'; void *
0x1800117a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800117ab  nop
0x1800117ac  lea     rcx, [rbp+var_10]
0x1800117b0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800117b5  nop
0x1800117b6  lea     rcx, [rbp+hKey]
0x1800117ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800117bf  nop
0x1800117c0  lea     rcx, [rbp+lpSubKey]
0x1800117c4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800117c9  xor     al, al
0x1800117cb  add     rsp, 78h
0x1800117cf  pop     rdi
0x1800117d0  pop     rsi
0x1800117d1  pop     rbx
0x1800117d2  pop     rbp
0x1800117d3  retn
```
