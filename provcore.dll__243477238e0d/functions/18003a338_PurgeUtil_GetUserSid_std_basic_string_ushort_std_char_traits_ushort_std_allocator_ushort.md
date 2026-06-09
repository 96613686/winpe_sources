# PurgeUtil::GetUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18003a338`
- end: `0x18003a6d8`
- name: `?GetUserSid@PurgeUtil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `928`
- prototype: `HRESULT __fastcall(std::wstring *UserSid)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180039b0c`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x18000866c`
- `0x18000b178`
- `0x180010984`
- `0x180012400`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x180012bc8`
- `0x18001a0d4`
- `0x180028e1c`
- `0x18003a338`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a3cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a3cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a3f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a3f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a403`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a403`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a3c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a3c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a3aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a3aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a43b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a662`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a662`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a4f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a4f5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003a5d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003a5d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PurgeUtil::GetUserSid(std::wstring *UserSid)
{
  signed int v2; // edi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  WPP_PROJECT_CONTROL_BLOCK *v5; // rcx
  unsigned __int16 v6; // dx
  HANDLE CurrentProcess; // rax
  __int64 v8; // rax
  const std::_Value_init_tag *v9; // r8
  unsigned __int8 *v10; // rbx
  DWORD v11; // eax
  WPP_PROJECT_CONTROL_BLOCK *v12; // rcx
  unsigned __int8 *Mylast; // rsi
  unsigned __int8 *v14; // rax
  size_t v15; // rbx
  DWORD v16; // eax
  wchar_t *v17; // r9
  unsigned __int64 v18; // rax
  const wchar_t *v19; // r9
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+30h] [rbp-50h] BYREF
  void *hToken; // [rsp+48h] [rbp-38h] BYREF
  wchar_t *strUserSid; // [rsp+50h] [rbp-30h] BYREF
  unsigned int dwBufferSize; // [rsp+58h] [rbp-28h] BYREF
  std::vector<unsigned char> tokenData; // [rsp+60h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
  }
  std::wstring::_Eos(UserSid, 0);
  v2 = 0;
  hToken = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &hToken) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError == 1008 )
    {
      v2 = 0;
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &hToken) )
        goto LABEL_14;
      LastError = GetLastError();
      v2 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
      {
        goto LABEL_14;
      }
      v6 = 12;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
      {
        goto LABEL_14;
      }
      v6 = 11;
    }
    WPP_SF_d(v5->Control.Logger, v6, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, LastError);
  }
LABEL_14:
  v8 = (__int64)hToken;
  if ( hToken == (void *)-1LL )
  {
    v8 = -1;
    j.dismissed_ = 1;
  }
  else
  {
    j.dismissed_ = 0;
  }
  j.fun_ = (void (__fastcall *)(void *))CloseHandle;
  j.p1_ = (WWAN_INTERFACE_OBJECT *const)v8;
  dwBufferSize = 0;
  memset(&tokenData, 0, sizeof(tokenData));
  std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&tokenData);
  if ( (unsigned __int8 *)(tokenData._Mypair._Myval2._Mylast - tokenData._Mypair._Myval2._Myfirst) <= (unsigned __int8 *)1 )
  {
    if ( tokenData._Mypair._Myval2._Mylast == tokenData._Mypair._Myval2._Myfirst )
    {
      if ( tokenData._Mypair._Myval2._Myend == tokenData._Mypair._Myval2._Myfirst )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&tokenData, 1u, v9);
      }
      else
      {
        v10 = tokenData._Mypair._Myval2._Myfirst + 1;
        memset_0(
          tokenData._Mypair._Myval2._Mylast,
          0,
          1 - (tokenData._Mypair._Myval2._Mylast - tokenData._Mypair._Myval2._Myfirst));
        tokenData._Mypair._Myval2._Mylast = v10;
      }
    }
  }
  else
  {
    tokenData._Mypair._Myval2._Mylast = tokenData._Mypair._Myval2._Myfirst + 1;
  }
  if ( v2 )
    goto LABEL_38;
  while ( !GetTokenInformation(hToken, TokenUser, tokenData._Mypair._Myval2._Myfirst, dwBufferSize, &dwBufferSize) )
  {
    v11 = GetLastError();
    v2 = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, v11);
      v12 = WPP_GLOBAL_Control;
    }
    Mylast = tokenData._Mypair._Myval2._Mylast;
    if ( (unsigned __int8 *)dwBufferSize < (unsigned __int8 *)(tokenData._Mypair._Myval2._Mylast
                                                             - tokenData._Mypair._Myval2._Myfirst) )
    {
      v14 = &tokenData._Mypair._Myval2._Myfirst[dwBufferSize];
LABEL_34:
      tokenData._Mypair._Myval2._Mylast = v14;
      goto LABEL_35;
    }
    if ( (unsigned __int8 *)dwBufferSize > (unsigned __int8 *)(tokenData._Mypair._Myval2._Mylast
                                                             - tokenData._Mypair._Myval2._Myfirst) )
    {
      if ( (unsigned __int8 *)dwBufferSize <= (unsigned __int8 *)(tokenData._Mypair._Myval2._Myend
                                                                - tokenData._Mypair._Myval2._Myfirst) )
      {
        v15 = dwBufferSize - (unsigned __int64)(tokenData._Mypair._Myval2._Mylast - tokenData._Mypair._Myval2._Myfirst);
        memset_0(tokenData._Mypair._Myval2._Mylast, 0, v15);
        v14 = &Mylast[v15];
        v12 = WPP_GLOBAL_Control;
        goto LABEL_34;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
        &tokenData,
        dwBufferSize,
        (const std::_Value_init_tag *)tokenData._Mypair._Myval2._Myfirst);
      v12 = WPP_GLOBAL_Control;
    }
LABEL_35:
    if ( v2 != 122 )
      goto LABEL_39;
  }
  v2 = 0;
LABEL_38:
  v12 = WPP_GLOBAL_Control;
LABEL_39:
  strUserSid = 0;
  if ( !v2 )
  {
    if ( ConvertSidToStringSidW(*(PSID *)tokenData._Mypair._Myval2._Myfirst, &strUserSid) )
    {
      v12 = WPP_GLOBAL_Control;
      goto LABEL_47;
    }
    v16 = GetLastError();
    v2 = v16;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xEu, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, v16);
      v12 = WPP_GLOBAL_Control;
    }
    if ( !v2 )
    {
LABEL_47:
      v17 = strUserSid;
      if ( strUserSid )
      {
        if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v12->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_S(v12->Control.Logger, 0xFu, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, strUserSid);
          v17 = strUserSid;
        }
        v18 = std::_WChar_traits<unsigned short>::length(v17);
        std::wstring::_Assign<unsigned short>(UserSid, v19, v18);
        LocalFree(strUserSid);
        v12 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v12->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v12->Control.Logger, 0x10u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, v2);
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
  std::vector<unsigned char>::_Tidy((std::vector<char> *)&tokenData);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003a338  mov     [rsp-28h+arg_8], rbx
0x18003a33d  mov     [rsp-28h+arg_10], rsi
0x18003a342  push    rbp
0x18003a343  push    rdi
0x18003a344  push    r12
0x18003a346  push    r13
0x18003a348  push    r14
0x18003a34a  mov     rbp, rsp
0x18003a34d  sub     rsp, 80h
0x18003a354  mov     rax, cs:__security_cookie
0x18003a35b  xor     rax, rsp
0x18003a35e  mov     [rbp+var_8], rax
0x18003a362  mov     r14, UserSid
0x18003a365  lea     r13, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a36c  lea     rsi, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids
0x18003a373  mov     UserSid, cs:WPP_GLOBAL_Control
0x18003a37a  cmp     UserSid, r13
0x18003a37d  jz      short loc_18003A396
0x18003a37f  test    byte ptr [UserSid+1Ch], 10h
0x18003a383  jz      short loc_18003A396
0x18003a385  mov     edx, 0Ah; id
0x18003a38a  mov     r8, rsi; TraceGuid
0x18003a38d  mov     UserSid, [UserSid+10h]; Logger
0x18003a391  call    WPP_SF_
0x18003a396  xor     edx, edx; _New_size
0x18003a398  mov     UserSid, r14; this
0x18003a39b  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x18003a3a0  xor     edi, edi
0x18003a3a2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003a3a6  mov     [rbp+hToken], rbx
0x18003a3aa  call    cs:__imp_GetCurrentThread
0x18003a3b0  mov     UserSid, rax; ThreadHandle
0x18003a3b3  lea     r9, [rbp+hToken]; TokenHandle
0x18003a3b7  xor     r8d, r8d; OpenAsSelf
0x18003a3ba  lea     r12d, [rdi+8]
0x18003a3be  mov     edx, r12d; DesiredAccess
0x18003a3c1  call    cs:__imp_OpenThreadToken
0x18003a3c7  test    eax, eax
0x18003a3c9  jnz     short loc_18003A43B
0x18003a3cb  call    cs:__imp_GetLastError
0x18003a3d1  mov     edi, eax
0x18003a3d3  cmp     eax, 3F0h
0x18003a3d8  jz      short loc_18003A3F1
0x18003a3da  mov     UserSid, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a3e1  cmp     UserSid, r13
0x18003a3e4  jz      short loc_18003A43B
0x18003a3e6  test    byte ptr [UserSid+1Ch], 2
0x18003a3ea  jz      short loc_18003A43B
0x18003a3ec  lea     edx, [rbx+0Ch]
0x18003a3ef  jmp     short loc_18003A42C
0x18003a3f1  xor     edi, edi
0x18003a3f3  call    cs:__imp_GetCurrentProcess
0x18003a3f9  mov     UserSid, rax; ProcessHandle
0x18003a3fc  lea     r8, [rbp+hToken]; TokenHandle
0x18003a400  mov     edx, r12d; DesiredAccess
0x18003a403  call    cs:__imp_OpenProcessToken
0x18003a409  test    eax, eax
0x18003a40b  jnz     short loc_18003A43B
0x18003a40d  call    cs:__imp_GetLastError
0x18003a413  mov     edi, eax
0x18003a415  mov     UserSid, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a41c  cmp     UserSid, r13
0x18003a41f  jz      short loc_18003A43B
0x18003a421  test    byte ptr [UserSid+1Ch], 2
0x18003a425  jz      short loc_18003A43B
0x18003a427  mov     edx, 0Ch; id
0x18003a42c  mov     r9d, eax; _a1
0x18003a42f  mov     r8, rsi; TraceGuid
0x18003a432  mov     UserSid, [UserSid+10h]; Logger
0x18003a436  call    WPP_SF_d
0x18003a43b  mov     UserSid, cs:__imp_CloseHandle
0x18003a442  mov     r12d, 1
0x18003a448  mov     rax, [rbp+hToken]
0x18003a44c  cmp     rax, rbx
0x18003a44f  jz      short loc_18003A457
0x18003a451  mov     [rbp+j.dismissed_], 0
0x18003a455  jmp     short loc_18003A45E
0x18003a457  mov     rax, rbx
0x18003a45a  mov     [rbp+j.dismissed_], r12b
0x18003a45e  mov     [rbp+j.fun_], UserSid
0x18003a462  mov     [rbp+j.p1_], rax
0x18003a466  mov     [rbp+dwBufferSize], 0
0x18003a46d  xorps   xmm0, xmm0
0x18003a470  xor     eax, eax
0x18003a472  movups  xmmword ptr [rbp+tokenData._Mypair._Myval2._Myfirst], xmm0
0x18003a476  mov     [rbp+tokenData._Mypair._Myval2._Myend], rax
0x18003a47a  lea     UserSid, [rbp+tokenData]; this
0x18003a47e  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18003a483  nop
0x18003a484  mov     rdx, [rbp+tokenData._Mypair._Myval2._Myfirst]
0x18003a488  mov     r9, [rbp+tokenData._Mypair._Myval2._Mylast]
0x18003a48c  mov     UserSid, r9
0x18003a48f  sub     UserSid, rdx
0x18003a492  cmp     UserSid, r12
0x18003a495  jbe     short loc_18003A4A1
0x18003a497  lea     rax, [rdx+1]
0x18003a49b  mov     [rbp+tokenData._Mypair._Myval2._Mylast], rax
0x18003a49f  jmp     short loc_18003A4D5
0x18003a4a1  jnb     short loc_18003A4D5
0x18003a4a3  mov     rax, [rbp+tokenData._Mypair._Myval2._Myend]
0x18003a4a7  sub     rax, rdx
0x18003a4aa  cmp     rax, r12
0x18003a4ad  jnb     short loc_18003A4BD
0x18003a4af  mov     rdx, r12; _Newsize
0x18003a4b2  lea     UserSid, [rbp+tokenData]; this
0x18003a4b6  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003a4bb  jmp     short loc_18003A4D5
0x18003a4bd  mov     r8, r12
0x18003a4c0  sub     r8, UserSid; Size
0x18003a4c3  lea     rbx, [r8+r9]
0x18003a4c7  xor     edx, edx; Val
0x18003a4c9  mov     UserSid, r9; void *
0x18003a4cc  call    memset_0
0x18003a4d1  mov     [rbp+tokenData._Mypair._Myval2._Mylast], rbx
0x18003a4d5  test    edi, edi
0x18003a4d7  jnz     loc_18003A5B1
0x18003a4dd  lea     rax, [rbp+dwBufferSize]
0x18003a4e1  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x18003a4e6  mov     r9d, [rbp+dwBufferSize]; TokenInformationLength
0x18003a4ea  mov     r8, [rbp+tokenData._Mypair._Myval2._Myfirst]; TokenInformation
0x18003a4ee  mov     edx, r12d; TokenInformationClass
0x18003a4f1  mov     UserSid, [rbp+hToken]; TokenHandle
0x18003a4f5  call    cs:__imp_GetTokenInformation
0x18003a4fb  test    eax, eax
0x18003a4fd  jnz     loc_18003A5AF
0x18003a503  call    cs:__imp_GetLastError
0x18003a509  mov     edi, eax
0x18003a50b  mov     UserSid, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a512  cmp     UserSid, r13
0x18003a515  jz      short loc_18003A538
0x18003a517  test    byte ptr [UserSid+1Ch], 10h
0x18003a51b  jz      short loc_18003A538
0x18003a51d  mov     edx, 0Dh; id
0x18003a522  mov     r9d, eax; _a1
0x18003a525  mov     r8, rsi; TraceGuid
0x18003a528  mov     UserSid, [UserSid+10h]; Logger
0x18003a52c  call    WPP_SF_d
0x18003a531  mov     UserSid, cs:WPP_GLOBAL_Control
0x18003a538  mov     ebx, [rbp+dwBufferSize]
0x18003a53b  mov     r8, [rbp+tokenData._Mypair._Myval2._Myfirst]; _Newsize
0x18003a53f  mov     rsi, [rbp+tokenData._Mypair._Myval2._Mylast]
0x18003a543  mov     rdx, rsi
0x18003a546  sub     rdx, r8
0x18003a549  cmp     rbx, rdx
0x18003a54c  jnb     short loc_18003A554
0x18003a54e  lea     rax, [rbx+r8]
0x18003a552  jmp     short loc_18003A592
0x18003a554  jbe     short loc_18003A596
0x18003a556  mov     rax, [rbp+tokenData._Mypair._Myval2._Myend]
0x18003a55a  sub     rax, r8
0x18003a55d  cmp     rbx, rax
0x18003a560  jbe     short loc_18003A577
0x18003a562  mov     rdx, rbx; _Newsize
0x18003a565  lea     UserSid, [rbp+tokenData]; this
0x18003a569  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003a56e  mov     UserSid, cs:WPP_GLOBAL_Control
0x18003a575  jmp     short loc_18003A596
0x18003a577  sub     rbx, rdx
0x18003a57a  mov     r8, rbx; Size
0x18003a57d  xor     edx, edx; Val
0x18003a57f  mov     UserSid, rsi; void *
0x18003a582  call    memset_0
0x18003a587  lea     rax, [rbx+rsi]
0x18003a58b  mov     UserSid, cs:WPP_GLOBAL_Control
0x18003a592  mov     [rbp+tokenData._Mypair._Myval2._Mylast], rax
0x18003a596  cmp     edi, 7Ah ; 'z'
0x18003a599  lea     rsi, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids
0x18003a5a0  jz      loc_18003A4DD
0x18003a5a6  lea     rsi, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids
0x18003a5ad  jmp     short loc_18003A5B8
0x18003a5af  xor     edi, edi
0x18003a5b1  mov     UserSid, cs:WPP_GLOBAL_Control
0x18003a5b8  mov     [rbp+strUserSid], 0
0x18003a5c0  test    edi, edi
0x18003a5c2  jnz     loc_18003A66F
0x18003a5c8  mov     UserSid, [rbp+tokenData._Mypair._Myval2._Myfirst]
0x18003a5cc  lea     rdx, [rbp+strUserSid]; StringSid
0x18003a5d0  mov     UserSid, [UserSid]; Sid
0x18003a5d3  call    cs:__imp_ConvertSidToStringSidW
0x18003a5d9  test    eax, eax
0x18003a5db  jnz     short loc_18003A618
0x18003a5dd  call    cs:__imp_GetLastError
0x18003a5e3  mov     edi, eax
0x18003a5e5  mov     UserSid, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a5ec  cmp     UserSid, r13
0x18003a5ef  jz      short loc_18003A612
0x18003a5f1  test    byte ptr [UserSid+1Ch], 2
0x18003a5f5  jz      short loc_18003A612
0x18003a5f7  mov     edx, 0Eh; id
0x18003a5fc  mov     r9d, eax; _a1
0x18003a5ff  mov     r8, rsi; TraceGuid
0x18003a602  mov     UserSid, [UserSid+10h]; Logger
0x18003a606  call    WPP_SF_d
0x18003a60b  mov     UserSid, cs:WPP_GLOBAL_Control
0x18003a612  test    edi, edi
0x18003a614  jnz     short loc_18003A66F
0x18003a616  jmp     short loc_18003A61F
0x18003a618  mov     UserSid, cs:WPP_GLOBAL_Control
0x18003a61f  mov     r9, [rbp+strUserSid]; _a1
0x18003a623  test    r9, r9
0x18003a626  jz      short loc_18003A66F
0x18003a628  cmp     UserSid, r13; __annotation("TMF:",
0x18003a62b  jz      short loc_18003A648
0x18003a62d  test    byte ptr [UserSid+1Ch], 10h
0x18003a631  jz      short loc_18003A648
0x18003a633  mov     edx, 0Fh; id
0x18003a638  mov     r8, rsi; TraceGuid
0x18003a63b  mov     UserSid, [UserSid+10h]; Logger
0x18003a63f  call    WPP_SF_S
0x18003a644  mov     r9, [rbp+strUserSid]
0x18003a648  mov     UserSid, r9; _First
0x18003a64b  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18003a650  mov     r8, rax; _Count
0x18003a653  mov     rdx, r9; _Ptr
0x18003a656  mov     UserSid, r14; this
0x18003a659  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003a65e  mov     UserSid, [rbp+strUserSid]; hMem
0x18003a662  call    cs:__imp_LocalFree
0x18003a668  mov     UserSid, cs:WPP_GLOBAL_Control
0x18003a66f  cmp     UserSid, r13; __annotation("TMF:",
0x18003a672  jz      short loc_18003A68E
0x18003a674  test    byte ptr [UserSid+1Ch], 10h
0x18003a678  jz      short loc_18003A68E
0x18003a67a  mov     edx, 10h; id
0x18003a67f  mov     r9d, edi; _a1
0x18003a682  mov     r8, rsi; TraceGuid
0x18003a685  mov     UserSid, [UserSid+10h]; Logger
0x18003a689  call    WPP_SF_d
0x18003a68e  test    edi, edi
0x18003a690  jle     short loc_18003A69B
0x18003a692  movzx   edi, di
0x18003a695  or      edi, 80070000h
0x18003a69b  lea     UserSid, [rbp+tokenData]; this
0x18003a69f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003a6a4  nop
0x18003a6a5  lea     UserSid, [rbp+j]; j
0x18003a6a9  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18003a6ae  mov     eax, edi
0x18003a6b0  mov     UserSid, [rbp+var_8]
0x18003a6b4  xor     UserSid, rsp; StackCookie
0x18003a6b7  call    __security_check_cookie
0x18003a6bc  lea     r11, [rsp+80h+var_s0]
0x18003a6c4  mov     rbx, [r11+38h]
0x18003a6c8  mov     rsi, [r11+40h]
0x18003a6cc  mov     rsp, r11
0x18003a6cf  pop     r14
0x18003a6d1  pop     r13
0x18003a6d3  pop     r12
0x18003a6d5  pop     rdi
0x18003a6d6  pop     rbp
0x18003a6d7  retn
```
