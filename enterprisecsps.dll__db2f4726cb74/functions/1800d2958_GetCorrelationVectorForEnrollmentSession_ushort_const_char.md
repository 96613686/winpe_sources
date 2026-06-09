# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x1800d2958`
- end: `0x1800d2bdc`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `644`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, char *)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800d0728`
- `0x1800d11a4`
- `0x1800d1d98`
- `0x1800d1f1c`

## callees

- `0x180008de0`
- `0x180009284`
- `0x18000bef4`
- `0x18000da9c`
- `0x18002201c`
- `0x180025ac0`
- `0x18002dcc8`
- `0x1800bc9c8`
- `0x1800d1110`
- `0x1800d1180`
- `0x1800d1a84`
- `0x1800d2958`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d2a18`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d2a95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d2a18`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d2a95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d29d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2a60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d29d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2a60`
- `DMCmnUtils!UnicodeToMB` at `0x1800d2ae3`
- `DMCmnUtils!UnicodeToMB` at `0x1800d2ae3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCorrelationVectorForEnrollmentSession(LPCWSTR lpValueName, char *a2)
{
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  signed int v6; // ebx
  bool v7; // cc
  LSTATUS v8; // eax
  char *v9; // rcx
  void *v10; // rax
  volatile signed __int64 *v11; // rbx
  unsigned int v12; // edx
  char *v14; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v19; // [rsp+50h] [rbp-B0h] BYREF
  char **v20; // [rsp+58h] [rbp-A8h] BYREF
  char *v21; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+68h] [rbp-98h]
  WCHAR Data[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v24[136]; // [rsp+C0h] [rbp-40h] BYREF

  if ( !a2 || !lpValueName )
    return 2147942487LL;
  hKey = 0;
  *a2 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v4 = (const WCHAR *)DMGetKnownRegPath(0);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  v6 = v5;
  v7 = v5 <= 0;
  if ( v5
    || (cbData = 78,
        v5 = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, &cbData),
        v6 = v5,
        v7 = v5 <= 0,
        v5) )
  {
    if ( !v7 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    RegOpenKeyExW(hKey, Data, 0, 0x20019u, &phkResult);
    lpcbData = 258;
    v8 = RegQueryValueExW(phkResult, lpValueName, 0, 0, (LPBYTE)v24, &lpcbData);
    v6 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      v14 = 0;
      v19 = 0;
      v20 = &v14;
      v21 = 0;
      v22 = 1;
      v6 = UnicodeToMB(v24, 0xFDE9u, &v21, &v19);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v20);
      v9 = v14;
      if ( v6 >= 0 && v14 )
      {
        v6 = StringCchCopyA(a2, 0x81u, v14);
        v9 = v14;
      }
      v14 = 0;
      if ( v9 )
        MemoryFree(v9);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  if ( v6 < 0 )
  {
    v10 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    if ( v10 )
      v11 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v10);
    else
      v11 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v11,
      _InterlockedExchangeAdd64(v11 + 17, 0),
      a2);
    if ( v11 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v11, v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1800d2958  mov     [rsp-8+arg_10], rbx
0x1800d295d  push    rbp
0x1800d295e  push    rsi
0x1800d295f  push    rdi
0x1800d2960  lea     rbp, [rsp-0E0h]
0x1800d2968  sub     rsp, 1E0h
0x1800d296f  mov     rax, cs:__security_cookie
0x1800d2976  xor     rax, rsp
0x1800d2979  mov     [rbp+0F0h+var_20], rax
0x1800d2980  mov     rdi, rdx
0x1800d2983  mov     rsi, rcx
0x1800d2986  test    rdx, rdx
0x1800d2989  jz      loc_1800D2BB4
0x1800d298f  test    rcx, rcx
0x1800d2992  jz      loc_1800D2BB4
0x1800d2998  mov     [rsp+1F0h+hKey], 0
0x1800d29a1  mov     byte ptr [rdx], 0
0x1800d29a4  xor     edx, edx
0x1800d29a6  lea     rcx, [rsp+1F0h+hKey]
0x1800d29ab  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d29b0  xor     ecx, ecx
0x1800d29b2  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800d29b7  lea     rcx, [rsp+1F0h+hKey]
0x1800d29bc  mov     [rsp+1F0h+phkResult], rcx; phkResult
0x1800d29c1  mov     r9d, 20019h; samDesired
0x1800d29c7  xor     r8d, r8d; ulOptions
0x1800d29ca  mov     rdx, rax; lpSubKey
0x1800d29cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d29d4  call    cs:__imp_RegOpenKeyExW
0x1800d29db  nop     dword ptr [rax+rax+00h]
0x1800d29e0  mov     ebx, eax
0x1800d29e2  test    eax, eax
0x1800d29e4  jnz     loc_1800D2B4D
0x1800d29ea  mov     [rsp+1F0h+cbData], 4Eh ; 'N'
0x1800d29f2  lea     rax, [rsp+1F0h+cbData]
0x1800d29f7  mov     [rsp+1F0h+lpcbData], rax; lpcbData
0x1800d29fc  lea     rax, [rsp+1F0h+Data]
0x1800d2a01  mov     [rsp+1F0h+phkResult], rax; lpData
0x1800d2a06  xor     r9d, r9d; lpType
0x1800d2a09  xor     r8d, r8d; lpReserved
0x1800d2a0c  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x1800d2a13  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800d2a18  call    cs:__imp_RegQueryValueExW
0x1800d2a1f  nop     dword ptr [rax+rax+00h]
0x1800d2a24  mov     ebx, eax
0x1800d2a26  test    eax, eax
0x1800d2a28  jnz     loc_1800D2B4D
0x1800d2a2e  mov     [rsp+1F0h+var_1B0], 0
0x1800d2a37  xor     edx, edx
0x1800d2a39  lea     rcx, [rsp+1F0h+var_1B0]
0x1800d2a3e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d2a43  lea     rax, [rsp+1F0h+var_1B0]
0x1800d2a48  mov     [rsp+1F0h+phkResult], rax; phkResult
0x1800d2a4d  mov     r9d, 20019h; samDesired
0x1800d2a53  xor     r8d, r8d; ulOptions
0x1800d2a56  lea     rdx, [rsp+1F0h+Data]; lpSubKey
0x1800d2a5b  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800d2a60  call    cs:__imp_RegOpenKeyExW
0x1800d2a67  nop     dword ptr [rax+rax+00h]
0x1800d2a6c  mov     [rsp+1F0h+var_1A4], 102h
0x1800d2a74  lea     rax, [rsp+1F0h+var_1A4]
0x1800d2a79  mov     [rsp+1F0h+lpcbData], rax; lpcbData
0x1800d2a7e  lea     rax, [rbp+0F0h+var_130]
0x1800d2a82  mov     [rsp+1F0h+phkResult], rax; lpData
0x1800d2a87  xor     r9d, r9d; lpType
0x1800d2a8a  xor     r8d, r8d; lpReserved
0x1800d2a8d  mov     rdx, rsi; lpValueName
0x1800d2a90  mov     rcx, [rsp+1F0h+var_1B0]; hKey
0x1800d2a95  call    cs:__imp_RegQueryValueExW
0x1800d2a9c  nop     dword ptr [rax+rax+00h]
0x1800d2aa1  mov     ebx, eax
0x1800d2aa3  test    eax, eax
0x1800d2aa5  jnz     loc_1800D2B35
0x1800d2aab  mov     [rsp+1F0h+var_1C0], 0
0x1800d2ab4  mov     [rsp+1F0h+var_1A0], eax
0x1800d2ab8  lea     rax, [rsp+1F0h+var_1C0]
0x1800d2abd  mov     [rsp+1F0h+var_198], rax
0x1800d2ac2  mov     [rsp+1F0h+var_190], 0
0x1800d2acb  mov     [rsp+1F0h+var_188], 1
0x1800d2ad0  lea     r9, [rsp+1F0h+var_1A0]
0x1800d2ad5  lea     r8, [rsp+1F0h+var_190]
0x1800d2ada  mov     edx, 0FDE9h
0x1800d2adf  lea     rcx, [rbp+0F0h+var_130]
0x1800d2ae3  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x1800d2aea  nop     dword ptr [rax+rax+00h]
0x1800d2aef  mov     ebx, eax
0x1800d2af1  lea     rcx, [rsp+1F0h+var_198]
0x1800d2af6  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800d2afb  mov     rcx, [rsp+1F0h+var_1C0]
0x1800d2b00  test    ebx, ebx
0x1800d2b02  js      short loc_1800D2B20
0x1800d2b04  test    rcx, rcx
0x1800d2b07  jz      short loc_1800D2B20
0x1800d2b09  mov     r8, rcx; char *
0x1800d2b0c  mov     edx, 81h; unsigned __int64
0x1800d2b11  mov     rcx, rdi; char *
0x1800d2b14  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800d2b19  mov     ebx, eax
0x1800d2b1b  mov     rcx, [rsp+1F0h+var_1C0]; void *
0x1800d2b20  mov     [rsp+1F0h+var_1C0], 0
0x1800d2b29  test    rcx, rcx
0x1800d2b2c  jz      short loc_1800D2B40
0x1800d2b2e  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800d2b33  jmp     short loc_1800D2B40
0x1800d2b35  jle     short loc_1800D2B40
0x1800d2b37  movzx   ebx, ax
0x1800d2b3a  or      ebx, 80070000h
0x1800d2b40  lea     rcx, [rsp+1F0h+var_1B0]
0x1800d2b45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2b4a  nop
0x1800d2b4b  jmp     short loc_1800D2B58
0x1800d2b4d  jle     short loc_1800D2B58
0x1800d2b4f  movzx   ebx, ax
0x1800d2b52  or      ebx, 80070000h
0x1800d2b58  test    ebx, ebx
0x1800d2b5a  jns     short loc_1800D2BA5
0x1800d2b5c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d2b63  mov     ecx, 90h; unsigned __int64
0x1800d2b68  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d2b6d  test    rax, rax
0x1800d2b70  jz      short loc_1800D2B7F
0x1800d2b72  mov     rcx, rax
0x1800d2b75  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x1800d2b7a  mov     rbx, rax
0x1800d2b7d  jmp     short loc_1800D2B81
0x1800d2b7f  xor     ebx, ebx
0x1800d2b81  xor     edx, edx
0x1800d2b83  lock xadd [rbx+88h], rdx; unsigned __int64
0x1800d2b8c  mov     r8, rdi; char *
0x1800d2b8f  mov     rcx, rbx; this
0x1800d2b92  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800d2b97  test    rbx, rbx
0x1800d2b9a  jz      short loc_1800D2BA5
0x1800d2b9c  mov     rcx, rbx; this
0x1800d2b9f  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800d2ba4  nop
0x1800d2ba5  lea     rcx, [rsp+1F0h+hKey]
0x1800d2baa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2baf  nop
0x1800d2bb0  xor     eax, eax
0x1800d2bb2  jmp     short loc_1800D2BB9
0x1800d2bb4  mov     eax, 80070057h
0x1800d2bb9  mov     rcx, [rbp+0F0h+var_20]
0x1800d2bc0  xor     rcx, rsp; StackCookie
0x1800d2bc3  call    __security_check_cookie
0x1800d2bc8  mov     rbx, [rsp+1F0h+arg_10]
0x1800d2bd0  add     rsp, 1E0h
0x1800d2bd7  pop     rdi
0x1800d2bd8  pop     rsi
0x1800d2bd9  pop     rbp
0x1800d2bda  retn
```
