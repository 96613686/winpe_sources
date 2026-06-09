# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x18001e2ec`
- end: `0x18001e43d`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `337`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075538`
- `0x1800756c8`

## callees

- `0x1800071c0`
- `0x18001e2ec`
- `0x18001e444`
- `0x18002d998`
- `0x18002e1a0`
- `0x18002e5ac`
- `0x180070818`
- `0x180074980`
- `0x18007530c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e345`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e345`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e379`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e379`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e3f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e430`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e3f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e430`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetCorrelationVectorForDmSession(const unsigned __int16 *a1, char *a2)
{
  const WCHAR *v3; // rax
  int ComponentCVForEnrollmentId; // eax
  bool v5; // cc
  const unsigned __int16 *v6; // rcx
  volatile signed __int64 *v7; // rax
  HKEY hKey; // [rsp+30h] [rbp-19h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-11h] BYREF
  unsigned __int16 Data[40]; // [rsp+40h] [rbp-9h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = (const WCHAR *)DMGetKnownRegPath(0);
  ComponentCVForEnrollmentId = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  v5 = ComponentCVForEnrollmentId <= 0;
  if ( ComponentCVForEnrollmentId
    || (cbData[0] = 78,
        ComponentCVForEnrollmentId = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, cbData),
        v5 = ComponentCVForEnrollmentId <= 0,
        ComponentCVForEnrollmentId) )
  {
    if ( !v5 )
      ComponentCVForEnrollmentId = (unsigned __int16)ComponentCVForEnrollmentId | 0x80070000;
  }
  else
  {
    ComponentCVForEnrollmentId = GetComponentCVForEnrollmentId(v6, Data, a2, hKey);
  }
  if ( ComponentCVForEnrollmentId >= 0 )
    goto LABEL_11;
  v7 = (volatile signed __int64 *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)cbData = v7;
  if ( v7 )
    v7 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v7);
  *(_QWORD *)cbData = v7;
  if ( v7 )
  {
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v7,
      _InterlockedExchangeAdd64(v7 + 17, 0),
      a2);
    wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(cbData);
LABEL_11:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(cbData);
  if ( hKey )
    RegCloseKey(hKey);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001e2ec  mov     [rsp-8+arg_0], rbx
0x18001e2f1  push    rbp
0x18001e2f2  lea     rbp, [rsp-57h]
0x18001e2f7  sub     rsp, 0A0h
0x18001e2fe  mov     rax, cs:__security_cookie
0x18001e305  xor     rax, rsp
0x18001e308  mov     [rbp+57h+var_10], rax
0x18001e30c  mov     rbx, rdx
0x18001e30f  mov     [rbp+57h+hKey], 0
0x18001e317  xor     edx, edx
0x18001e319  lea     rcx, [rbp+57h+hKey]
0x18001e31d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001e322  xor     ecx, ecx
0x18001e324  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18001e329  lea     rcx, [rbp+57h+hKey]
0x18001e32d  mov     [rsp+0A0h+phkResult], rcx; phkResult
0x18001e332  mov     r9d, 20019h; samDesired
0x18001e338  xor     r8d, r8d; ulOptions
0x18001e33b  mov     rdx, rax; lpSubKey
0x18001e33e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e345  call    cs:__imp_RegOpenKeyExW
0x18001e34b  test    eax, eax
0x18001e34d  jnz     short loc_18001E395
0x18001e34f  mov     [rbp+57h+cbData], 4Eh ; 'N'
0x18001e356  lea     rax, [rbp+57h+cbData]
0x18001e35a  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18001e35f  lea     rax, [rbp+57h+Data]
0x18001e363  mov     [rsp+0A0h+phkResult], rax; lpData
0x18001e368  xor     r9d, r9d; lpType
0x18001e36b  xor     r8d, r8d; lpReserved
0x18001e36e  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x18001e375  mov     rcx, [rbp+57h+hKey]; hKey
0x18001e379  call    cs:__imp_RegQueryValueExW
0x18001e37f  test    eax, eax
0x18001e381  jnz     short loc_18001E395
0x18001e383  mov     r9, [rbp+57h+hKey]; HKEY
0x18001e387  mov     r8, rbx; char *
0x18001e38a  lea     rdx, [rbp+57h+Data]; unsigned __int16 *
0x18001e38e  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x18001e393  jmp     short loc_18001E39F
0x18001e395  jle     short loc_18001E39F
0x18001e397  movzx   eax, ax
0x18001e39a  or      eax, 80070000h
0x18001e39f  test    eax, eax
0x18001e3a1  jns     short loc_18001E3EF
0x18001e3a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e3aa  mov     ecx, 90h; unsigned __int64
0x18001e3af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e3b4  mov     qword ptr [rbp+57h+cbData], rax
0x18001e3b8  test    rax, rax
0x18001e3bb  jz      short loc_18001E3C6
0x18001e3bd  mov     rcx, rax
0x18001e3c0  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x18001e3c5  nop
0x18001e3c6  mov     qword ptr [rbp+57h+cbData], rax
0x18001e3ca  test    rax, rax
0x18001e3cd  jz      short loc_18001E41D
0x18001e3cf  xor     edx, edx
0x18001e3d1  lock xadd [rax+88h], rdx; unsigned __int64
0x18001e3da  mov     r8, rbx; char *
0x18001e3dd  mov     rcx, rax; this
0x18001e3e0  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18001e3e5  lea     rcx, [rbp+57h+cbData]
0x18001e3e9  call    ?reset@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z; wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(TraceLoggingCorrelationVector *)
0x18001e3ee  nop
0x18001e3ef  mov     rcx, [rbp+57h+hKey]; hKey
0x18001e3f3  test    rcx, rcx
0x18001e3f6  jz      short loc_18001E3FE
0x18001e3f8  call    cs:__imp_RegCloseKey
0x18001e3fe  xor     eax, eax
0x18001e400  mov     rcx, [rbp+57h+var_10]
0x18001e404  xor     rcx, rsp; StackCookie
0x18001e407  call    __security_check_cookie
0x18001e40c  mov     rbx, [rsp+0A0h+arg_0]
0x18001e414  add     rsp, 0A0h
0x18001e41b  pop     rbp
0x18001e41c  retn
0x18001e41d  lea     rcx, [rbp+57h+cbData]
0x18001e421  call    ?reset@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@QEAAXPEAVTraceLoggingCorrelationVector@@@Z; wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>>::reset(TraceLoggingCorrelationVector *)
0x18001e426  nop
0x18001e427  mov     rcx, [rbp+57h+hKey]; hKey
0x18001e42b  test    rcx, rcx
0x18001e42e  jz      short loc_18001E436
0x18001e430  call    cs:__imp_RegCloseKey
0x18001e436  mov     eax, 8007000Eh
0x18001e43b  jmp     short loc_18001E400
```
