# PolicyChecker::GetClientSid(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800129fc`
- end: `0x180012afa`
- name: `?GetClientSid@PolicyChecker@@SAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `254`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000da68`
- `0x18000f740`

## callees

- `0x180006b84`
- `0x180006e2c`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c93c`
- `0x180012364`
- `0x180012748`
- `0x1800129fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a56`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012a4c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012a4c`

## string_xrefs

- `0x180012a70`: `Unable to convert SID to String! HR=0x%x`
- `0x180012a81`: `PolicyChecker::GetClientSid`
- `0x180012ac0`: `PolicyChecker::GetClientSid`
- `0x180012aaf`: `Unable to get SID from client token HR=0x%x`

## pseudocode

```c
__int64 __fastcall PolicyChecker::GetClientSid(__int64 a1)
{
  void ***v2; // rax
  __int64 v3; // rcx
  int CallerSid; // ebx
  LPWSTR *v5; // rax
  signed int LastError; // eax
  __int64 v7; // rcx
  int *v8; // rax
  int *v9; // rax
  __int64 v11; // [rsp+20h] [rbp-18h]
  int v12; // [rsp+20h] [rbp-18h]
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF
  PSID Sid; // [rsp+50h] [rbp+18h] BYREF
  void *v15; // [rsp+58h] [rbp+20h] BYREF

  v15 = 0;
  Sid = 0;
  v13 = 0;
  v2 = (void ***)tlx::replace<void *,void * (*)(void *),&void * LocalFree(void *),0>(&Sid);
  CallerSid = GetCallerSid(v2);
  if ( CallerSid < 0 )
    goto LABEL_8;
  v5 = (LPWSTR *)tlx::replace<void *,void * (*)(void *),&void * LocalFree(void *),0>(&v13);
  if ( !ConvertSidToStringSidW(Sid, v5) )
  {
    LastError = GetLastError();
    CallerSid = LastError;
    if ( LastError > 0 )
      CallerSid = (unsigned __int16)LastError | 0x80070000;
    v8 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v7);
    v12 = CallerSid;
    DSLogger::LogError(
      (DSLogger *)v8,
      L"PolicyChecker::GetClientSid",
      0x15Eu,
      L"Unable to convert SID to String! HR=0x%x",
      v12);
    if ( CallerSid < 0 )
      goto LABEL_8;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a1,
                           v13) )
  {
    CallerSid = -2147024882;
LABEL_8:
    v9 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v3);
    LODWORD(v11) = CallerSid;
    DSLogger::LogError(
      (DSLogger *)v9,
      L"PolicyChecker::GetClientSid",
      0x169u,
      L"Unable to get SID from client token HR=0x%x",
      v11);
  }
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete((void **)&v13);
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&Sid);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v15);
  return (unsigned int)CallerSid;
}

```

## disassembly

```asm
0x1800129fc  mov     rax, rsp
0x1800129ff  mov     [rax+8], rbx
0x180012a03  push    rdi
0x180012a04  sub     rsp, 30h
0x180012a08  mov     rdi, rcx
0x180012a0b  mov     qword ptr [rax+20h], 0
0x180012a13  lea     rcx, [rax+18h]
0x180012a17  mov     qword ptr [rax+18h], 0
0x180012a1f  mov     qword ptr [rax+10h], 0
0x180012a27  call    ??$replace@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<void *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0> &)
0x180012a2c  mov     rcx, rax; void **
0x180012a2f  call    ?GetCallerSid@@YAJPEAPEAX@Z; GetCallerSid(void * *)
0x180012a34  mov     ebx, eax
0x180012a36  test    eax, eax
0x180012a38  js      short loc_180012AAA
0x180012a3a  lea     rcx, [rsp+38h+arg_8]
0x180012a3f  call    ??$replace@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<void *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0> &)
0x180012a44  mov     rcx, [rsp+38h+Sid]; Sid
0x180012a49  mov     rdx, rax; StringSid
0x180012a4c  call    cs:__imp_ConvertSidToStringSidW
0x180012a52  test    eax, eax
0x180012a54  jnz     short loc_180012A94
0x180012a56  call    cs:__imp_GetLastError
0x180012a5c  mov     ebx, eax
0x180012a5e  test    eax, eax
0x180012a60  jle     short loc_180012A6B
0x180012a62  movzx   ebx, ax
0x180012a65  or      ebx, 80070000h
0x180012a6b  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012a70  lea     r9, aUnableToConver_0; "Unable to convert SID to String! HR=0x%"...
0x180012a77  mov     dword ptr [rsp+38h+var_18], ebx
0x180012a7b  mov     r8d, 15Eh; unsigned int
0x180012a81  lea     rdx, aPolicycheckerG_0; "PolicyChecker::GetClientSid"
0x180012a88  mov     rcx, rax; this
0x180012a8b  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012a90  test    ebx, ebx
0x180012a92  js      short loc_180012AAA
0x180012a94  mov     rdx, [rsp+38h+arg_8]
0x180012a99  mov     rcx, rdi
0x180012a9c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180012aa1  test    al, al
0x180012aa3  jnz     short loc_180012ACF
0x180012aa5  mov     ebx, 8007000Eh
0x180012aaa  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012aaf  lea     r9, aUnableToGetSid_0; "Unable to get SID from client token HR="...
0x180012ab6  mov     dword ptr [rsp+38h+var_18], ebx
0x180012aba  mov     r8d, 169h; unsigned int
0x180012ac0  lea     rdx, aPolicycheckerG_0; "PolicyChecker::GetClientSid"
0x180012ac7  mov     rcx, rax; this
0x180012aca  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012acf  lea     rcx, [rsp+38h+arg_8]
0x180012ad4  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180012ad9  lea     rcx, [rsp+38h+Sid]
0x180012ade  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180012ae3  lea     rcx, [rsp+38h+arg_18]
0x180012ae8  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180012aed  mov     eax, ebx
0x180012aef  mov     rbx, [rsp+38h+arg_0]
0x180012af4  add     rsp, 30h
0x180012af8  pop     rdi
0x180012af9  retn
```
