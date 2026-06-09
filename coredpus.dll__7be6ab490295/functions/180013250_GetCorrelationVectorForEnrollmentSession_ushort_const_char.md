# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x180013250`
- end: `0x18001350e`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `702`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18002e1b8`

## callees

- `0x1800121f4`
- `0x180012284`
- `0x180013250`
- `0x180013514`
- `0x180014330`
- `0x1800145f0`
- `0x180019834`
- `0x18001c748`
- `0x18002e0f4`
- `0x18002e164`
- `0x18002e194`
- `0x18002e218`
- `0x18002e38c`

## import_xrefs

- `DMCmnUtils!UnicodeToMB` at `0x18001341d`
- `DMCmnUtils!UnicodeToMB` at `0x18001341d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013396`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013396`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013323`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800133cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013323`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800133cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001329d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013359`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001329d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013359`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCorrelationVectorForEnrollmentSession(const unsigned __int16 *a1, char *a2)
{
  const WCHAR *v2; // rax
  LSTATUS v3; // eax
  signed int v4; // ebx
  bool v5; // cc
  LSTATUS v6; // eax
  void *v7; // rdx
  wil::details *v8; // rcx
  void *v9; // rax
  char *v10; // r8
  volatile signed __int64 *v11; // rbx
  unsigned int v12; // edx
  wil::details *v14; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v19; // [rsp+50h] [rbp-B0h] BYREF
  wil::details **v20; // [rsp+58h] [rbp-A8h] BYREF
  char *v21; // [rsp+60h] [rbp-A0h] BYREF
  char v22; // [rsp+68h] [rbp-98h]
  WCHAR Data[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v24[136]; // [rsp+C0h] [rbp-40h] BYREF

  byte_18003EE90 = 0;
  hKey = 0;
  v2 = (const WCHAR *)DMGetKnownRegPath(a1, a2);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x20019u, &hKey);
  v4 = v3;
  v5 = v3 <= 0;
  if ( v3
    || (cbData = 78,
        v3 = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, &cbData),
        v4 = v3,
        v5 = v3 <= 0,
        v3) )
  {
    if ( !v5 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    phkResult = 0;
    RegOpenKeyExW(hKey, Data, 0, 0x20019u, &phkResult);
    lpcbData = 258;
    v6 = RegQueryValueExW(phkResult, L"EnrollmentSvc", 0, 0, (LPBYTE)v24, &lpcbData);
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v14 = 0;
      v19 = 0;
      v20 = &v14;
      v21 = 0;
      v22 = 1;
      v4 = UnicodeToMB(v24, 0xFDE9u, &v21, &v19);
      wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(&v20);
      v8 = v14;
      if ( v4 >= 0 && v14 )
      {
        v4 = StringCchCopyA(&byte_18003EE90, 0x81u, (const char *)v14);
        v8 = v14;
      }
      v14 = 0;
      if ( v8 )
        wil::details::FreeProcessHeap(v8, v7);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  if ( v4 < 0 )
  {
    v9 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
      v11 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v9);
    else
      v11 = 0;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v11,
      _InterlockedExchangeAdd64(v11 + 17, 0),
      v10);
    if ( v11 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v11, v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180013250  mov     [rsp-8+arg_0], rbx
0x180013255  push    rbp
0x180013256  lea     rbp, [rsp-0E0h]
0x18001325e  sub     rsp, 1E0h
0x180013265  mov     rax, cs:__security_cookie
0x18001326c  xor     rax, rsp
0x18001326f  mov     [rbp+0E0h+var_10], rax
0x180013276  mov     [rsp+1E0h+hKey], 0
0x18001327f  mov     cs:byte_18003EE90, 0
0x180013286  mov     rbx, [rsp+1E0h+hKey]
0x18001328b  test    rbx, rbx
0x18001328e  jz      short loc_1800132B4
0x180013290  lea     rcx, [rsp+1E0h+var_1A8]; this
0x180013295  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001329a  mov     rcx, rbx; hKey
0x18001329d  call    cs:__imp_RegCloseKey
0x1800132a4  nop     dword ptr [rax+rax+00h]
0x1800132a9  lea     rcx, [rsp+1E0h+var_1A8]; this
0x1800132ae  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800132b3  nop
0x1800132b4  mov     [rsp+1E0h+hKey], 0
0x1800132bd  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800132c2  lea     rcx, [rsp+1E0h+hKey]
0x1800132c7  mov     [rsp+1E0h+phkResult], rcx; phkResult
0x1800132cc  mov     r9d, 20019h; samDesired
0x1800132d2  xor     r8d, r8d; ulOptions
0x1800132d5  mov     rdx, rax; lpSubKey
0x1800132d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800132df  call    cs:__imp_RegOpenKeyExW
0x1800132e6  nop     dword ptr [rax+rax+00h]
0x1800132eb  mov     ebx, eax
0x1800132ed  test    eax, eax
0x1800132ef  jnz     loc_18001348B
0x1800132f5  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x1800132fd  lea     rax, [rsp+1E0h+cbData]
0x180013302  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x180013307  lea     rax, [rsp+1E0h+Data]
0x18001330c  mov     [rsp+1E0h+phkResult], rax; lpData
0x180013311  xor     r9d, r9d; lpType
0x180013314  xor     r8d, r8d; lpReserved
0x180013317  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18001331e  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180013323  call    cs:__imp_RegQueryValueExW
0x18001332a  nop     dword ptr [rax+rax+00h]
0x18001332f  mov     ebx, eax
0x180013331  test    eax, eax
0x180013333  jnz     loc_18001348B
0x180013339  mov     [rsp+1E0h+var_1A8], 0
0x180013342  mov     rbx, [rsp+1E0h+var_1A8]
0x180013347  test    rbx, rbx
0x18001334a  jz      short loc_180013370
0x18001334c  lea     rcx, [rsp+1E0h+var_1B0]; this
0x180013351  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180013356  mov     rcx, rbx; hKey
0x180013359  call    cs:__imp_RegCloseKey
0x180013360  nop     dword ptr [rax+rax+00h]
0x180013365  lea     rcx, [rsp+1E0h+var_1B0]; this
0x18001336a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001336f  nop
0x180013370  mov     [rsp+1E0h+var_1A8], 0
0x180013379  lea     rax, [rsp+1E0h+var_1A8]
0x18001337e  mov     [rsp+1E0h+phkResult], rax; phkResult
0x180013383  mov     r9d, 20019h; samDesired
0x180013389  xor     r8d, r8d; ulOptions
0x18001338c  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x180013391  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180013396  call    cs:__imp_RegOpenKeyExW
0x18001339d  nop     dword ptr [rax+rax+00h]
0x1800133a2  mov     [rsp+1E0h+var_194], 102h
0x1800133aa  lea     rax, [rsp+1E0h+var_194]
0x1800133af  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x1800133b4  lea     rax, [rbp+0E0h+var_120]
0x1800133b8  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800133bd  xor     r9d, r9d; lpType
0x1800133c0  xor     r8d, r8d; lpReserved
0x1800133c3  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x1800133ca  mov     rcx, [rsp+1E0h+var_1A8]; hKey
0x1800133cf  call    cs:__imp_RegQueryValueExW
0x1800133d6  nop     dword ptr [rax+rax+00h]
0x1800133db  mov     ebx, eax
0x1800133dd  test    eax, eax
0x1800133df  jnz     loc_180013473
0x1800133e5  mov     [rsp+1E0h+var_1B0], 0
0x1800133ee  mov     [rsp+1E0h+var_190], eax
0x1800133f2  lea     rax, [rsp+1E0h+var_1B0]
0x1800133f7  mov     [rsp+1E0h+var_188], rax
0x1800133fc  mov     [rsp+1E0h+var_180], 0
0x180013405  mov     [rsp+1E0h+var_178], 1
0x18001340a  lea     r9, [rsp+1E0h+var_190]
0x18001340f  lea     r8, [rsp+1E0h+var_180]
0x180013414  mov     edx, 0FDE9h
0x180013419  lea     rcx, [rbp+0E0h+var_120]
0x18001341d  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x180013424  nop     dword ptr [rax+rax+00h]
0x180013429  mov     ebx, eax
0x18001342b  lea     rcx, [rsp+1E0h+var_188]
0x180013430  call    ??1?$out_param_t@V?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<char,wil::process_heap_deleter>>(void)
0x180013435  mov     rcx, [rsp+1E0h+var_1B0]
0x18001343a  test    ebx, ebx
0x18001343c  js      short loc_18001345E
0x18001343e  test    rcx, rcx
0x180013441  jz      short loc_18001345E
0x180013443  mov     r8, rcx; char *
0x180013446  mov     edx, 81h; unsigned __int64
0x18001344b  lea     rcx, byte_18003EE90; char *
0x180013452  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180013457  mov     ebx, eax
0x180013459  mov     rcx, [rsp+1E0h+var_1B0]; this
0x18001345e  mov     [rsp+1E0h+var_1B0], 0
0x180013467  test    rcx, rcx
0x18001346a  jz      short loc_18001347E
0x18001346c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180013471  jmp     short loc_18001347E
0x180013473  jle     short loc_18001347E
0x180013475  movzx   ebx, ax
0x180013478  or      ebx, 80070000h
0x18001347e  lea     rcx, [rsp+1E0h+var_1A8]
0x180013483  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013488  nop
0x180013489  jmp     short loc_180013496
0x18001348b  jle     short loc_180013496
0x18001348d  movzx   ebx, ax
0x180013490  or      ebx, 80070000h
0x180013496  test    ebx, ebx
0x180013498  jns     short loc_1800134E0
0x18001349a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800134a1  mov     ecx, 90h; unsigned __int64
0x1800134a6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800134ab  test    rax, rax
0x1800134ae  jz      short loc_1800134BD
0x1800134b0  mov     rcx, rax
0x1800134b3  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x1800134b8  mov     rbx, rax
0x1800134bb  jmp     short loc_1800134BF
0x1800134bd  xor     ebx, ebx
0x1800134bf  xor     edx, edx
0x1800134c1  lock xadd [rbx+88h], rdx; unsigned __int64
0x1800134ca  mov     rcx, rbx; this
0x1800134cd  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800134d2  test    rbx, rbx
0x1800134d5  jz      short loc_1800134E0
0x1800134d7  mov     rcx, rbx; this
0x1800134da  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800134df  nop
0x1800134e0  lea     rcx, [rsp+1E0h+hKey]
0x1800134e5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800134ea  nop
0x1800134eb  xor     eax, eax
0x1800134ed  mov     rcx, [rbp+0E0h+var_10]
0x1800134f4  xor     rcx, rsp; StackCookie
0x1800134f7  call    __security_check_cookie
0x1800134fc  mov     rbx, [rsp+1E0h+arg_0]
0x180013504  add     rsp, 1E0h
0x18001350b  pop     rbp
0x18001350c  retn
```
