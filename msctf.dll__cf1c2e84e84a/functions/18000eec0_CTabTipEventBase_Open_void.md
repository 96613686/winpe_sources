# CTabTipEventBase::Open(void)

- ea: `0x18000eec0`
- end: `0x18000f020`
- name: `?Open@CTabTipEventBase@@QEAAJXZ`
- size: `352`
- prototype: `__int64 __fastcall(CTabTipEventBase *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ea1c`
- `0x18007a0f8`

## callees

- `0x18000eec0`
- `0x18000f030`
- `0x18000fac0`
- `0x180086b40`
- `0x180087150`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000efac`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000efac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ef10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ef10`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ef1d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000ef1d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef8f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efc1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ef8f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000efc1`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ef98`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ef98`

## pseudocode

```c
__int64 __fastcall CTabTipEventBase::Open(const unsigned __int16 **this)
{
  WCHAR *v2; // rbx
  unsigned int v3; // edi
  DWORD CurrentProcessId; // eax
  OLECHAR *v5; // rcx
  const unsigned __int16 *v6; // rax
  __int64 pSessionId; // [rsp+20h] [rbp-78h] BYREF
  BSTR pbstr; // [rsp+28h] [rbp-70h] BYREF
  unsigned __int16 v10[40]; // [rsp+30h] [rbp-68h] BYREF

  v2 = 0;
  pbstr = 0;
  v3 = -2147467259;
  if ( ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, L"Local\\") < 0 )
    goto LABEL_14;
  LODWORD(pSessionId) = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, (DWORD *)&pSessionId);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::GetImpl'::`2'::impl) )
  {
    if ( IsUsingSystemToken() )
      StringCchPrintfW(v10, 0x28u, L"s_%d", (unsigned int)pSessionId, pSessionId);
    else
      StringCchPrintfW(v10, 0x28u, L"u_%d", (unsigned int)pSessionId, pSessionId);
  }
  else
  {
    StringCchPrintfW(v10, 0x28u, L"%d", (unsigned int)pSessionId, pSessionId);
  }
  if ( ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, v10) < 0
    || ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, this[2]) < 0 )
  {
LABEL_14:
    v5 = pbstr;
  }
  else
  {
    v2 = pbstr;
    v5 = 0;
  }
  SysFreeString(v5);
  if ( SysStringLen(v2) )
  {
    v6 = (const unsigned __int16 *)OpenEventW(0x100000u, 0, v2);
    this[1] = v6;
    if ( v6 )
      v3 = 0;
  }
  SysFreeString(v2);
  return v3;
}

```

## disassembly

```asm
0x18000eec0  mov     [rsp+arg_8], rbx
0x18000eec5  mov     [rsp+arg_10], rsi
0x18000eeca  push    rdi
0x18000eecb  sub     rsp, 90h
0x18000eed2  mov     rax, cs:__security_cookie
0x18000eed9  xor     rax, rsp
0x18000eedc  mov     [rsp+98h+var_18], rax
0x18000eee4  mov     rsi, rcx
0x18000eee7  lea     rdx, aLocal_0; "Local\\"
0x18000eeee  xor     ebx, ebx
0x18000eef0  lea     rcx, [rsp+98h+pbstr]; this
0x18000eef5  mov     [rsp+98h+pbstr], rbx
0x18000eefa  mov     edi, 80004005h
0x18000eeff  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000ef04  test    eax, eax
0x18000ef06  js      loc_18000F016
0x18000ef0c  mov     dword ptr [rsp+98h+pSessionId], ebx
0x18000ef10  call    cs:__imp_GetCurrentProcessId
0x18000ef16  mov     ecx, eax; dwProcessId
0x18000ef18  lea     rdx, [rsp+98h+pSessionId]; pSessionId
0x18000ef1d  call    cs:__imp_ProcessIdToSessionId
0x18000ef23  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GamepadVKey_Initialize@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GamepadVKey_Initialize@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GamepadVKey_Initialize> `wil::Feature<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::GetImpl(void)'::`2'::impl
0x18000ef2a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GamepadVKey_Initialize@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::__private_IsEnabled(void)
0x18000ef2f  test    al, al
0x18000ef31  jnz     loc_18000EFEE
0x18000ef37  mov     r9d, dword ptr [rsp+98h+pSessionId]
0x18000ef3c  lea     r8, aD; "%d"
0x18000ef43  mov     edx, 28h ; '('
0x18000ef48  lea     rcx, [rsp+98h+var_68]
0x18000ef4d  jmp     short loc_18000EF56
0x18000ef4f  lea     r8, aSD_0; "s_%d"
0x18000ef56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ef5b  lea     rdx, [rsp+98h+var_68]; unsigned __int16 *
0x18000ef60  lea     rcx, [rsp+98h+pbstr]; this
0x18000ef65  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000ef6a  test    eax, eax
0x18000ef6c  js      loc_18000F016
0x18000ef72  mov     rdx, [rsi+10h]; unsigned __int16 *
0x18000ef76  lea     rcx, [rsp+98h+pbstr]; this
0x18000ef7b  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000ef80  test    eax, eax
0x18000ef82  js      loc_18000F016
0x18000ef88  mov     rbx, [rsp+98h+pbstr]
0x18000ef8d  xor     ecx, ecx; bstrString
0x18000ef8f  call    cs:__imp_SysFreeString
0x18000ef95  mov     rcx, rbx; pbstr
0x18000ef98  call    cs:__imp_SysStringLen
0x18000ef9e  test    eax, eax
0x18000efa0  jz      short loc_18000EFBE
0x18000efa2  mov     r8, rbx; lpName
0x18000efa5  xor     edx, edx; bInheritHandle
0x18000efa7  mov     ecx, 100000h; dwDesiredAccess
0x18000efac  call    cs:__imp_OpenEventW
0x18000efb2  xor     ecx, ecx
0x18000efb4  mov     [rsi+8], rax
0x18000efb8  test    rax, rax
0x18000efbb  cmovnz  edi, ecx
0x18000efbe  mov     rcx, rbx; bstrString
0x18000efc1  call    cs:__imp_SysFreeString
0x18000efc7  mov     eax, edi
0x18000efc9  mov     rcx, [rsp+98h+var_18]
0x18000efd1  xor     rcx, rsp; StackCookie
0x18000efd4  call    __security_check_cookie
0x18000efd9  lea     r11, [rsp+98h+var_8]
0x18000efe1  mov     rbx, [r11+18h]
0x18000efe5  mov     rsi, [r11+20h]
0x18000efe9  mov     rsp, r11
0x18000efec  pop     rdi
0x18000efed  retn
0x18000efee  call    ?IsUsingSystemToken@@YA_NXZ; IsUsingSystemToken(void)
0x18000eff3  mov     r9d, dword ptr [rsp+98h+pSessionId]
0x18000eff8  mov     edx, 28h ; '('; unsigned __int64
0x18000effd  lea     rcx, [rsp+98h+var_68]; unsigned __int16 *
0x18000f002  test    al, al
0x18000f004  jnz     loc_18000EF4F
0x18000f00a  lea     r8, aUD; "u_%d"
0x18000f011  jmp     loc_18000EF56
0x18000f016  mov     rcx, [rsp+98h+pbstr]
0x18000f01b  jmp     loc_18000EF8F
```
