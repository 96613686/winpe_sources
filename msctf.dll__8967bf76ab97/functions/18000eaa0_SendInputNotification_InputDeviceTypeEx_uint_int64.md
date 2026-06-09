# SendInputNotification(InputDeviceTypeEx,uint,__int64)

- ea: `0x18000eaa0`
- end: `0x18000ed2d`
- name: `?SendInputNotification@@YAXW4InputDeviceTypeEx@@I_J@Z`
- size: `653`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180080540`
- `0x18008cf24`

## callees

- `0x18000eaa0`
- `0x18000f030`
- `0x18000fac0`
- `0x180086b40`
- `0x180087150`
- `0x180106a60`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ec33`
- `msvcrt!memcpy_s` at `0x18000ec5a`
- `msvcrt!memcpy_s` at `0x18000ec94`
- `msvcrt!memcpy_s` at `0x18000ecbd`
- `msvcrt!memcpy_s` at `0x18000ec33`
- `msvcrt!memcpy_s` at `0x18000ec5a`
- `msvcrt!memcpy_s` at `0x18000ec94`
- `msvcrt!memcpy_s` at `0x18000ecbd`
- `ntdll!RtlPublishWnfStateData` at `0x18000ece1`
- `ntdll!RtlPublishWnfStateData` at `0x18000ece1`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000eb91`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000eb91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ebe9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ebe9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000eafb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000eafb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ec0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ec0d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000eb07`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000eb07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ebb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ebb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb74`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eba5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb74`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eba5`
- `OLEAUT32!__imp_SysStringLen` at `0x18000eb7d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000eb7d`

## pseudocode

```c
void __fastcall SendInputNotification(int a1, DWORD a2, int a3)
{
  WCHAR *v5; // rbx
  HANDLE v7; // rdi
  int v8; // esi
  DWORD CurrentProcessId; // eax
  OLECHAR *v10; // rcx
  int v11; // esi
  int v12; // r15d
  DWORD CurrentThreadId; // eax
  DWORD v14; // ebx
  BSTR pbstr; // [rsp+30h] [rbp-69h] BYREF
  DWORD pSessionId[2]; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v17[4]; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int16 v18[40]; // [rsp+60h] [rbp-39h] BYREF

  v5 = 0;
  pbstr = 0;
  v7 = 0;
  v8 = -2147467259;
  if ( ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, L"Local\\") < 0 )
    goto LABEL_23;
  pSessionId[0] = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, pSessionId);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::GetImpl'::`2'::impl) )
  {
    if ( IsUsingSystemToken() )
      StringCchPrintfW(v18, 0x28u, L"s_%d", pSessionId[0]);
    else
      StringCchPrintfW(v18, 0x28u, L"u_%d", pSessionId[0]);
  }
  else
  {
    StringCchPrintfW(v18, 0x28u, L"%d", pSessionId[0]);
  }
  if ( ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, v18) < 0
    || ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, L"ImmersiveFocusTrackingActiveEvent") < 0 )
  {
LABEL_23:
    v10 = pbstr;
  }
  else
  {
    v5 = pbstr;
    v10 = 0;
  }
  SysFreeString(v10);
  if ( SysStringLen(v5) )
  {
    v7 = OpenEventW(0x100000u, 0, v5);
    if ( v7 )
      v8 = 0;
  }
  SysFreeString(v5);
  if ( v8 >= 0 && !WaitForSingleObject(v7, 0) )
  {
    if ( a1 == 16 || a1 == 2 )
    {
      v12 = 0;
      v11 = a1 == 16;
    }
    else
    {
      v11 = 0;
      v12 = 4;
    }
    CurrentThreadId = GetCurrentThreadId();
    pSessionId[0] = a2;
    v14 = CurrentThreadId;
    pbstr = 0;
    memcpy_s(&pbstr, 8u, pSessionId, 4u);
    pSessionId[0] = v14;
    v17[1] = pbstr;
    pbstr = 0;
    memcpy_s(&pbstr, 8u, pSessionId, 4u);
    v17[2] = pbstr;
    LODWORD(pbstr) = (__int16)a3;
    HIDWORD(pbstr) = SHIWORD(a3);
    *(_QWORD *)pSessionId = pbstr;
    pbstr = 0;
    memcpy_s(&pbstr, 8u, pSessionId, 8u);
    v17[0] = pbstr;
    pSessionId[0] = v12 | (v11 << 8);
    pbstr = 0;
    memcpy_s(&pbstr, 8u, pSessionId, 4u);
    v17[3] = pbstr;
    RtlPublishWnfStateData(WNF_TKBN_TOUCH_EVENT, 0, v17, 32, 0);
  }
  if ( v7 )
    CloseHandle(v7);
}

```

## disassembly

```asm
0x18000eaa0  mov     [rsp-8+arg_0], rbx
0x18000eaa5  push    rbp
0x18000eaa6  push    rsi
0x18000eaa7  push    rdi
0x18000eaa8  push    r12
0x18000eaaa  push    r13
0x18000eaac  push    r14
0x18000eaae  push    r15
0x18000eab0  lea     rbp, [rsp-27h]
0x18000eab5  sub     rsp, 0C0h
0x18000eabc  mov     rax, cs:__security_cookie
0x18000eac3  xor     rax, rsp
0x18000eac6  mov     [rbp+57h+var_40], rax
0x18000eaca  mov     r13d, edx
0x18000eacd  mov     r14d, ecx
0x18000ead0  xor     ebx, ebx
0x18000ead2  lea     rdx, aLocal_0; "Local\\"
0x18000ead9  lea     rcx, [rbp+57h+pbstr]; this
0x18000eadd  mov     [rbp+57h+pbstr], rbx
0x18000eae1  mov     r12, r8
0x18000eae4  xor     edi, edi
0x18000eae6  mov     esi, 80004005h
0x18000eaeb  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000eaf0  test    eax, eax
0x18000eaf2  js      loc_18000ED24
0x18000eaf8  mov     [rbp+57h+pSessionId], ebx
0x18000eafb  call    cs:__imp_GetCurrentProcessId
0x18000eb01  mov     ecx, eax; dwProcessId
0x18000eb03  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x18000eb07  call    cs:__imp_ProcessIdToSessionId
0x18000eb0d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GamepadVKey_Initialize@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GamepadVKey_Initialize@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GamepadVKey_Initialize> `wil::Feature<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::GetImpl(void)'::`2'::impl
0x18000eb14  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GamepadVKey_Initialize@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GamepadVKey_Initialize>::__private_IsEnabled(void)
0x18000eb19  test    al, al
0x18000eb1b  jnz     loc_18000ECFE
0x18000eb21  mov     r9d, [rbp+57h+pSessionId]
0x18000eb25  lea     r8, aD; "%d"
0x18000eb2c  lea     edx, [rdi+28h]
0x18000eb2f  lea     rcx, [rbp+57h+var_90]
0x18000eb33  jmp     short loc_18000EB3C
0x18000eb35  lea     r8, aSD_0; "s_%d"
0x18000eb3c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eb41  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x18000eb45  lea     rcx, [rbp+57h+pbstr]; this
0x18000eb49  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000eb4e  test    eax, eax
0x18000eb50  js      loc_18000ED24
0x18000eb56  lea     rdx, aImmersivefocus; "ImmersiveFocusTrackingActiveEvent"
0x18000eb5d  lea     rcx, [rbp+57h+pbstr]; this
0x18000eb61  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18000eb66  test    eax, eax
0x18000eb68  js      loc_18000ED24
0x18000eb6e  mov     rbx, [rbp+57h+pbstr]
0x18000eb72  xor     ecx, ecx; bstrString
0x18000eb74  call    cs:__imp_SysFreeString
0x18000eb7a  mov     rcx, rbx; pbstr
0x18000eb7d  call    cs:__imp_SysStringLen
0x18000eb83  test    eax, eax
0x18000eb85  jz      short loc_18000EBA2
0x18000eb87  mov     r8, rbx; lpName
0x18000eb8a  xor     edx, edx; bInheritHandle
0x18000eb8c  mov     ecx, 100000h; dwDesiredAccess
0x18000eb91  call    cs:__imp_OpenEventW
0x18000eb97  mov     rdi, rax
0x18000eb9a  xor     eax, eax
0x18000eb9c  test    rdi, rdi
0x18000eb9f  cmovnz  esi, eax
0x18000eba2  mov     rcx, rbx; bstrString
0x18000eba5  call    cs:__imp_SysFreeString
0x18000ebab  test    esi, esi
0x18000ebad  jns     short loc_18000EBE4
0x18000ebaf  test    rdi, rdi
0x18000ebb2  jz      short loc_18000EBBD
0x18000ebb4  mov     rcx, rdi; hObject
0x18000ebb7  call    cs:__imp_CloseHandle
0x18000ebbd  mov     rcx, [rbp+57h+var_40]
0x18000ebc1  xor     rcx, rsp; StackCookie
0x18000ebc4  call    __security_check_cookie
0x18000ebc9  mov     rbx, [rsp+0F0h+arg_0]
0x18000ebd1  add     rsp, 0C0h
0x18000ebd8  pop     r15
0x18000ebda  pop     r14
0x18000ebdc  pop     r13
0x18000ebde  pop     r12
0x18000ebe0  pop     rdi
0x18000ebe1  pop     rsi
0x18000ebe2  pop     rbp
0x18000ebe3  retn
0x18000ebe4  xor     edx, edx; dwMilliseconds
0x18000ebe6  mov     rcx, rdi; hHandle
0x18000ebe9  call    cs:__imp_WaitForSingleObject
0x18000ebef  test    eax, eax
0x18000ebf1  jnz     short loc_18000EBAF
0x18000ebf3  cmp     r14d, 10h
0x18000ebf7  jz      loc_18000ECEC
0x18000ebfd  cmp     r14d, 2
0x18000ec01  jz      loc_18000ECEC
0x18000ec07  xor     esi, esi
0x18000ec09  lea     r15d, [rax+4]
0x18000ec0d  call    cs:__imp_GetCurrentThreadId
0x18000ec13  mov     [rbp+57h+pSessionId], r13d
0x18000ec17  lea     r8, [rbp+57h+pSessionId]; Source
0x18000ec1b  xor     r13d, r13d
0x18000ec1e  lea     rcx, [rbp+57h+pbstr]; Destination
0x18000ec22  mov     ebx, eax
0x18000ec24  mov     [rbp+57h+pbstr], r13
0x18000ec28  lea     r14d, [r13+8]
0x18000ec2c  mov     edx, r14d; DestinationSize
0x18000ec2f  lea     r9d, [r13+4]; SourceSize
0x18000ec33  call    cs:__imp_memcpy_s
0x18000ec39  mov     rcx, [rbp+57h+pbstr]
0x18000ec3d  lea     r8, [rbp+57h+pSessionId]; Source
0x18000ec41  mov     [rbp+57h+pSessionId], ebx
0x18000ec44  mov     edx, r14d; DestinationSize
0x18000ec47  mov     [rbp+57h+var_A8], rcx
0x18000ec4b  lea     ebx, [r13+4]
0x18000ec4f  lea     rcx, [rbp+57h+pbstr]; Destination
0x18000ec53  mov     [rbp+57h+pbstr], r13
0x18000ec57  mov     r9d, ebx; SourceSize
0x18000ec5a  call    cs:__imp_memcpy_s
0x18000ec60  mov     rax, [rbp+57h+pbstr]
0x18000ec64  lea     r8, [rbp+57h+pSessionId]; Source
0x18000ec68  mov     [rbp+57h+var_A0], rax
0x18000ec6c  lea     rcx, [rbp+57h+pbstr]; Destination
0x18000ec70  movsx   eax, r12w
0x18000ec74  mov     r9d, r14d; SourceSize
0x18000ec77  mov     dword ptr [rbp+57h+pbstr], eax
0x18000ec7a  mov     edx, r14d; DestinationSize
0x18000ec7d  shr     r12, 10h
0x18000ec81  movsx   eax, r12w
0x18000ec85  mov     dword ptr [rbp+57h+pbstr+4], eax
0x18000ec88  mov     rax, [rbp+57h+pbstr]
0x18000ec8c  mov     qword ptr [rbp+57h+pSessionId], rax
0x18000ec90  mov     [rbp+57h+pbstr], r13
0x18000ec94  call    cs:__imp_memcpy_s
0x18000ec9a  mov     rax, [rbp+57h+pbstr]
0x18000ec9e  lea     r8, [rbp+57h+pSessionId]; Source
0x18000eca2  shl     esi, 8
0x18000eca5  lea     rcx, [rbp+57h+pbstr]; Destination
0x18000eca9  or      esi, r15d
0x18000ecac  mov     [rbp+57h+var_B0], rax
0x18000ecb0  mov     r9d, ebx; SourceSize
0x18000ecb3  mov     [rbp+57h+pSessionId], esi
0x18000ecb6  mov     edx, r14d; DestinationSize
0x18000ecb9  mov     [rbp+57h+pbstr], r13
0x18000ecbd  call    cs:__imp_memcpy_s
0x18000ecc3  mov     rax, [rbp+57h+pbstr]
0x18000ecc7  lea     r9d, [r13+20h]
0x18000eccb  mov     rcx, cs:WNF_TKBN_TOUCH_EVENT
0x18000ecd2  lea     r8, [rbp+57h+var_B0]
0x18000ecd6  xor     edx, edx
0x18000ecd8  mov     [rbp+57h+var_98], rax
0x18000ecdc  mov     [rsp+0F0h+var_D0], r13
0x18000ece1  call    cs:__imp_RtlPublishWnfStateData
0x18000ece7  jmp     loc_18000EBAF
0x18000ecec  xor     esi, esi
0x18000ecee  xor     r15d, r15d
0x18000ecf1  cmp     r14d, 10h
0x18000ecf5  setz    sil
0x18000ecf9  jmp     loc_18000EC0D
0x18000ecfe  call    ?IsUsingSystemToken@@YA_NXZ; IsUsingSystemToken(void)
0x18000ed03  mov     r9d, [rbp+57h+pSessionId]
0x18000ed07  mov     edx, 28h ; '('; unsigned __int64
0x18000ed0c  lea     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x18000ed10  test    al, al
0x18000ed12  jnz     loc_18000EB35
0x18000ed18  lea     r8, aUD; "u_%d"
0x18000ed1f  jmp     loc_18000EB3C
0x18000ed24  mov     rcx, [rbp+57h+pbstr]
0x18000ed28  jmp     loc_18000EB74
```
