# GetCorrelationVectorForEnrollmentSession(ushort const *,char *)

- ea: `0x180074fac`
- end: `0x18007520a`
- name: `?GetCorrelationVectorForEnrollmentSession@@YAJPEBGPEAD@Z`
- size: `606`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001aec8`

## callees

- `0x1800071c0`
- `0x180016c54`
- `0x18002d998`
- `0x18002e1a0`
- `0x18002e5ac`
- `0x180032fac`
- `0x18003d458`
- `0x180070818`
- `0x180070880`
- `0x180074980`
- `0x180074fac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075012`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075092`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075012`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075092`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075050`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800750c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075050`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800750c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075172`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800751e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075172`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800751e1`
- `DMCmnUtils!UnicodeToMB` at `0x18007510d`
- `DMCmnUtils!UnicodeToMB` at `0x18007510d`

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
  char *v7; // rcx
  void *v8; // rax
  volatile signed __int64 *v9; // rbx
  unsigned int v10; // edx
  char *v12; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v17; // [rsp+50h] [rbp-B0h] BYREF
  char **v18; // [rsp+58h] [rbp-A8h] BYREF
  char *v19; // [rsp+60h] [rbp-A0h] BYREF
  char v20; // [rsp+68h] [rbp-98h]
  WCHAR Data[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v22[136]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  byte_1800B0910 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = (const WCHAR *)DMGetKnownRegPath(0);
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
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    RegOpenKeyExW(hKey, Data, 0, 0x20019u, &phkResult);
    lpcbData = 258;
    v6 = RegQueryValueExW(phkResult, L"EnrollmentSvc", 0, 0, (LPBYTE)v22, &lpcbData);
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v12 = 0;
      v17 = 0;
      v18 = &v12;
      v19 = 0;
      v20 = 1;
      v4 = UnicodeToMB(v22, 0xFDE9u, &v19, &v17);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v18);
      v7 = v12;
      if ( v4 >= 0 && v12 )
      {
        v4 = StringCchCopyA(&byte_1800B0910, 0x81u, v12);
        v7 = v12;
      }
      v12 = 0;
      if ( v7 )
        MemoryFree(v7);
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( v4 < 0 )
  {
    v8 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8 ? (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v8) : 0LL;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v9,
      _InterlockedExchangeAdd64(v9 + 17, 0),
      &byte_1800B0910);
    if ( v9 )
      TraceLoggingCorrelationVector::`scalar deleting destructor'((TraceLoggingCorrelationVector *)v9, v10);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180074fac  mov     [rsp-8+arg_0], rbx
0x180074fb1  push    rbp
0x180074fb2  lea     rbp, [rsp-0E0h]
0x180074fba  sub     rsp, 1E0h
0x180074fc1  mov     rax, cs:__security_cookie
0x180074fc8  xor     rax, rsp
0x180074fcb  mov     [rbp+0E0h+var_10], rax
0x180074fd2  mov     [rsp+1E0h+hKey], 0
0x180074fdb  mov     cs:byte_1800B0910, 0
0x180074fe2  xor     edx, edx
0x180074fe4  lea     rcx, [rsp+1E0h+hKey]
0x180074fe9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180074fee  xor     ecx, ecx
0x180074ff0  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180074ff5  lea     rcx, [rsp+1E0h+hKey]
0x180074ffa  mov     [rsp+1E0h+phkResult], rcx; phkResult
0x180074fff  mov     r9d, 20019h; samDesired
0x180075005  xor     r8d, r8d; ulOptions
0x180075008  mov     rdx, rax; lpSubKey
0x18007500b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075012  call    cs:__imp_RegOpenKeyExW
0x180075018  mov     ebx, eax
0x18007501a  test    eax, eax
0x18007501c  jnz     loc_18007517B
0x180075022  mov     [rsp+1E0h+cbData], 4Eh ; 'N'
0x18007502a  lea     rax, [rsp+1E0h+cbData]
0x18007502f  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x180075034  lea     rax, [rsp+1E0h+Data]
0x180075039  mov     [rsp+1E0h+phkResult], rax; lpData
0x18007503e  xor     r9d, r9d; lpType
0x180075041  xor     r8d, r8d; lpReserved
0x180075044  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18007504b  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180075050  call    cs:__imp_RegQueryValueExW
0x180075056  mov     ebx, eax
0x180075058  test    eax, eax
0x18007505a  jnz     loc_18007517B
0x180075060  mov     [rsp+1E0h+var_1A0], 0
0x180075069  xor     edx, edx
0x18007506b  lea     rcx, [rsp+1E0h+var_1A0]
0x180075070  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180075075  lea     rax, [rsp+1E0h+var_1A0]
0x18007507a  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18007507f  mov     r9d, 20019h; samDesired
0x180075085  xor     r8d, r8d; ulOptions
0x180075088  lea     rdx, [rsp+1E0h+Data]; lpSubKey
0x18007508d  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180075092  call    cs:__imp_RegOpenKeyExW
0x180075098  mov     [rsp+1E0h+var_194], 102h
0x1800750a0  lea     rax, [rsp+1E0h+var_194]
0x1800750a5  mov     [rsp+1E0h+lpcbData], rax; lpcbData
0x1800750aa  lea     rax, [rbp+0E0h+var_120]
0x1800750ae  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800750b3  xor     r9d, r9d; lpType
0x1800750b6  xor     r8d, r8d; lpReserved
0x1800750b9  lea     rdx, c_szCvValueNameEnrollmentSvc; "EnrollmentSvc"
0x1800750c0  mov     rcx, [rsp+1E0h+var_1A0]; hKey
0x1800750c5  call    cs:__imp_RegQueryValueExW
0x1800750cb  mov     ebx, eax
0x1800750cd  test    eax, eax
0x1800750cf  jnz     loc_18007515D
0x1800750d5  mov     [rsp+1E0h+var_1B0], 0
0x1800750de  mov     [rsp+1E0h+var_190], eax
0x1800750e2  lea     rax, [rsp+1E0h+var_1B0]
0x1800750e7  mov     [rsp+1E0h+var_188], rax
0x1800750ec  mov     [rsp+1E0h+var_180], 0
0x1800750f5  mov     [rsp+1E0h+var_178], 1
0x1800750fa  lea     r9, [rsp+1E0h+var_190]
0x1800750ff  lea     r8, [rsp+1E0h+var_180]
0x180075104  mov     edx, 0FDE9h
0x180075109  lea     rcx, [rbp+0E0h+var_120]
0x18007510d  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x180075113  mov     ebx, eax
0x180075115  lea     rcx, [rsp+1E0h+var_188]
0x18007511a  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x18007511f  mov     rcx, [rsp+1E0h+var_1B0]
0x180075124  test    ebx, ebx
0x180075126  js      short loc_180075148
0x180075128  test    rcx, rcx
0x18007512b  jz      short loc_180075148
0x18007512d  mov     r8, rcx; char *
0x180075130  mov     edx, 81h; unsigned __int64
0x180075135  lea     rcx, byte_1800B0910; char *
0x18007513c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180075141  mov     ebx, eax
0x180075143  mov     rcx, [rsp+1E0h+var_1B0]; void *
0x180075148  mov     [rsp+1E0h+var_1B0], 0
0x180075151  test    rcx, rcx
0x180075154  jz      short loc_180075168
0x180075156  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18007515b  jmp     short loc_180075168
0x18007515d  jle     short loc_180075168
0x18007515f  movzx   ebx, ax
0x180075162  or      ebx, 80070000h
0x180075168  mov     rcx, [rsp+1E0h+var_1A0]; hKey
0x18007516d  test    rcx, rcx
0x180075170  jz      short loc_180075179
0x180075172  call    cs:__imp_RegCloseKey
0x180075178  nop
0x180075179  jmp     short loc_180075186
0x18007517b  jle     short loc_180075186
0x18007517d  movzx   ebx, ax
0x180075180  or      ebx, 80070000h
0x180075186  test    ebx, ebx
0x180075188  jns     short loc_1800751D7
0x18007518a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180075191  mov     ecx, 90h; unsigned __int64
0x180075196  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007519b  test    rax, rax
0x18007519e  jz      short loc_1800751AD
0x1800751a0  mov     rcx, rax
0x1800751a3  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x1800751a8  mov     rbx, rax
0x1800751ab  jmp     short loc_1800751AF
0x1800751ad  xor     ebx, ebx
0x1800751af  xor     edx, edx
0x1800751b1  lock xadd [rbx+88h], rdx; unsigned __int64
0x1800751ba  lea     r8, byte_1800B0910; char *
0x1800751c1  mov     rcx, rbx; this
0x1800751c4  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800751c9  test    rbx, rbx
0x1800751cc  jz      short loc_1800751D7
0x1800751ce  mov     rcx, rbx; this
0x1800751d1  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800751d6  nop
0x1800751d7  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800751dc  test    rcx, rcx
0x1800751df  jz      short loc_1800751E8
0x1800751e1  call    cs:__imp_RegCloseKey
0x1800751e7  nop
0x1800751e8  xor     eax, eax
0x1800751ea  mov     rcx, [rbp+0E0h+var_10]
0x1800751f1  xor     rcx, rsp; StackCookie
0x1800751f4  call    __security_check_cookie
0x1800751f9  mov     rbx, [rsp+1E0h+arg_0]
0x180075201  add     rsp, 1E0h
0x180075208  pop     rbp
0x180075209  retn
```
