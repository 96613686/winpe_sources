# MsaAccount::GetStrongAuthenticationHelper(ICDPComStrongAuthenticationHelper * *)

- ea: `0x1801a0fe0`
- end: `0x1801a1129`
- name: `?GetStrongAuthenticationHelper@MsaAccount@@AEBAXPEAPEAUICDPComStrongAuthenticationHelper@@@Z`
- size: `329`
- prototype: `void __fastcall(MsaAccount *__hidden this, struct ICDPComStrongAuthenticationHelper **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1801a0e98`

## callees

- `0x1800624cc`
- `0x180093e18`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x180114c58`
- `0x180143248`
- `0x1801a0fe0`
- `0x1801fcb36`
- `0x180223130`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x1801a104b`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1801a104b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801a10b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801a10b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a102f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a102f`

## string_xrefs

- `0x1801a10d9`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1801a1067`: `Failed to CoCreateAsUser for ICDPComStrongAuthenticationHelper`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall MsaAccount::GetStrongAuthenticationHelper(MsaAccount *this, LPVOID *a2)
{
  unsigned __int64 CurrentUserContextToken; // rdi
  shared *v4; // rcx
  HRESULT v5; // eax
  __int64 v6; // rax
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  const char *v12; // [rsp+30h] [rbp-19h] BYREF
  int v13; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v14[24]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+58h] [rbp+Fh] BYREF
  MsaAccount *v16; // [rsp+B0h] [rbp+67h] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp+77h] BYREF
  __int64 CurrentThreadId; // [rsp+C8h] [rbp+7Fh] BYREF

  v16 = this;
  ppv = 0;
  CurrentUserContextToken = shared::GetCurrentUserContextToken(this);
  if ( shared::IsRunningInContainerOS(v4) )
    v5 = CoCreateInstance(
           &GUID_cc56090a_6cb2_4579_b606_c1ba9b57273a,
           0,
           0x100004u,
           &GUID_478e819b_baf4_482e_b5d8_d33e109fbe16,
           &ppv);
  else
    v5 = CoCreateInstanceAsUser(
           &GUID_cc56090a_6cb2_4579_b606_c1ba9b57273a,
           0,
           1048580,
           CurrentUserContextToken,
           &GUID_478e819b_baf4_482e_b5d8_d33e109fbe16,
           &ppv);
  if ( v5 < 0 )
  {
    v12 = ".\\accountfix.cpp";
    v13 = 231;
    v6 = cdp::MakeException<cdp::hresult_exception,>(
           pExceptionObject,
           &v12,
           (unsigned int)v5,
           "Failed to CoCreateAsUser for ICDPComStrongAuthenticationHelper");
    cdp::CdpThrow<cdp::hresult_exception>(&v12, v6);
  }
  if ( !ppv )
  {
    v12 = ".\\accountfix.cpp";
    v13 = 233;
    LODWORD(v16) = -2147418113;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v7,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v16,
      (unsigned int)&v12,
      (__int64)&v13,
      (__int64)&CurrentThreadId);
    v8 = cdp::ExceptionStackFromSourceLocationInfo(v14, &v12);
    v11 = cdp::ErrorCodeToString(2147549183LL, v9, v10, v8);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147549183LL, v11);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  *a2 = ppv;
}

```

## disassembly

```asm
0x1801a0fe0  mov     [rsp-8+arg_0], rcx
0x1801a0fe5  push    rbp
0x1801a0fe6  push    rbx
0x1801a0fe7  push    rdi
0x1801a0fe8  lea     rbp, [rsp-47h]
0x1801a0fed  sub     rsp, 90h
0x1801a0ff4  mov     rbx, rdx
0x1801a0ff7  mov     [rbp+57h+arg_10], 0
0x1801a0fff  call    ?GetCurrentUserContextToken@shared@@YA_KXZ; shared::GetCurrentUserContextToken(void)
0x1801a1004  mov     rdi, rax
0x1801a1007  call    ?IsRunningInContainerOS@shared@@YA_NXZ; shared::IsRunningInContainerOS(void)
0x1801a100c  xor     edx, edx; pUnkOuter
0x1801a100e  mov     r8d, 100004h; dwClsContext
0x1801a1014  lea     rcx, _GUID_cc56090a_6cb2_4579_b606_c1ba9b57273a; rclsid
0x1801a101b  test    al, al
0x1801a101d  lea     rax, [rbp+57h+arg_10]
0x1801a1021  jz      short loc_1801A1037
0x1801a1023  mov     [rsp+0A0h+ppv], rax; ppv
0x1801a1028  lea     r9, _GUID_478e819b_baf4_482e_b5d8_d33e109fbe16; riid
0x1801a102f  call    cs:__imp_CoCreateInstance
0x1801a1035  jmp     short loc_1801A1051
0x1801a1037  mov     [rsp+0A0h+var_78], rax
0x1801a103c  lea     rax, _GUID_478e819b_baf4_482e_b5d8_d33e109fbe16
0x1801a1043  mov     [rsp+0A0h+ppv], rax
0x1801a1048  mov     r9, rdi
0x1801a104b  call    cs:__imp_CoCreateInstanceAsUser
0x1801a1051  test    eax, eax
0x1801a1053  jns     short loc_1801A108C
0x1801a1055  lea     rcx, aAccountfixCpp; ".\\accountfix.cpp"
0x1801a105c  mov     [rbp+57h+var_70], rcx
0x1801a1060  mov     [rbp+57h+var_68], 0E7h
0x1801a1067  lea     r9, aFailedToCocrea_0; "Failed to CoCreateAsUser for ICDPComStr"...
0x1801a106e  mov     r8d, eax
0x1801a1071  lea     rdx, [rbp+57h+var_70]
0x1801a1075  lea     rcx, [rbp+57h+pExceptionObject]
0x1801a1079  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801a107e  nop
0x1801a107f  mov     rdx, rax
0x1801a1082  lea     rcx, [rbp+57h+var_70]
0x1801a1086  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801a108c  mov     rax, [rbp+57h+arg_10]
0x1801a1090  test    rax, rax
0x1801a1093  jnz     loc_1801A111B
0x1801a1099  lea     rcx, aAccountfixCpp; ".\\accountfix.cpp"
0x1801a10a0  mov     [rbp+57h+var_70], rcx
0x1801a10a4  mov     [rbp+57h+var_68], 0E9h
0x1801a10ab  mov     ebx, 8000FFFFh
0x1801a10b0  mov     dword ptr [rbp+57h+arg_0], ebx
0x1801a10b3  call    cs:__imp_GetCurrentThreadId
0x1801a10b9  mov     eax, eax
0x1801a10bb  mov     [rbp+57h+arg_18], rax
0x1801a10bf  lea     rax, [rbp+57h+arg_18]
0x1801a10c3  mov     [rsp+0A0h+var_78], rax
0x1801a10c8  lea     rax, [rbp+57h+var_68]
0x1801a10cc  mov     [rsp+0A0h+ppv], rax
0x1801a10d1  lea     r9, [rbp+57h+var_70]
0x1801a10d5  lea     r8, [rbp+57h+arg_0]
0x1801a10d9  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1801a10e0  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1801a10e5  lea     rdx, [rbp+57h+var_70]
0x1801a10e9  lea     rcx, [rbp+57h+var_60]
0x1801a10ed  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1801a10f2  mov     r9, rax
0x1801a10f5  mov     ecx, ebx
0x1801a10f7  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1801a10fc  mov     r8, rax
0x1801a10ff  mov     edx, ebx
0x1801a1101  lea     rcx, [rbp+57h+pExceptionObject]
0x1801a1105  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1801a110a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1801a1111  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1801a1115  call    _CxxThrowException_0
0x1801a111b  mov     [rbx], rax
0x1801a111e  add     rsp, 90h
0x1801a1125  pop     rdi
0x1801a1126  pop     rbx
0x1801a1127  pop     rbp
0x1801a1128  retn
```
