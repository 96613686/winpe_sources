# ServiceUserTokenHelper::GetServiceNameFromServiceSid(void *,GenericStringHandle<ushort> *)

- ea: `0x180012c00`
- end: `0x1800130b0`
- name: `?GetServiceNameFromServiceSid@ServiceUserTokenHelper@@SAJPEAXPEAV?$GenericStringHandle@G@@@Z`
- size: `1200`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005aba0`

## callees

- `0x18000c7d0`
- `0x180011760`
- `0x180012c00`
- `0x180086674`
- `0x1800959c0`
- `0x180099740`
- `0x18009c140`
- `0x1800a1114`
- `0x1800a3444`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012c84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012c84`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012c9a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012c9a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012cdd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001307f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001307f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012d5b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012d5b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180012e4e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180012f45`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180012e4e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180012f45`

## string_xrefs

- `0x180012cb6`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ServiceUserTokenHelper::GetServiceNameFromServiceSid(PSID Sid, void **a2)
{
  volatile signed __int32 *v4; // rdx
  __int64 v5; // rbx
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  int LastError; // r14d
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  void *v14; // rdx
  __int64 v15; // r14
  __int64 result; // rax
  const ComError *v17; // rbx
  void *TokenHandle; // [rsp+30h] [rbp-1F8h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-1F0h] BYREF
  LPWSTR Name[2]; // [rsp+40h] [rbp-1E8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-1D8h]
  LPWSTR ReferencedDomainName[2]; // [rsp+58h] [rbp-1D0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-1C0h]
  __int64 v24; // [rsp+70h] [rbp-1B8h]
  const ComError *v25; // [rsp+78h] [rbp-1B0h] BYREF
  void **pExceptionObject; // [rsp+80h] [rbp-1A8h] BYREF
  __int128 v27; // [rsp+88h] [rbp-1A0h]
  int v28; // [rsp+98h] [rbp-190h]
  int v29; // [rsp+9Ch] [rbp-18Ch]
  int v30; // [rsp+A0h] [rbp-188h]
  void **v31; // [rsp+E0h] [rbp-148h] BYREF
  __int128 v32; // [rsp+E8h] [rbp-140h]
  unsigned int v33; // [rsp+F8h] [rbp-130h]
  int v34; // [rsp+FCh] [rbp-12Ch]
  int v35; // [rsp+100h] [rbp-128h]
  void **v36; // [rsp+140h] [rbp-E8h] BYREF
  __int128 v37; // [rsp+148h] [rbp-E0h]
  unsigned int v38; // [rsp+158h] [rbp-D0h]
  int v39; // [rsp+15Ch] [rbp-CCh]
  int v40; // [rsp+160h] [rbp-C8h]
  void **v41; // [rsp+1A0h] [rbp-88h] BYREF
  __int128 v42; // [rsp+1A8h] [rbp-80h]
  unsigned int v43; // [rsp+1B8h] [rbp-70h]
  int v44; // [rsp+1BCh] [rbp-6Ch]
  int v45; // [rsp+1C0h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]
  DWORD cchReferencedDomainName; // [rsp+238h] [rbp+10h] BYREF
  DWORD cchName; // [rsp+240h] [rbp+18h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+248h] [rbp+20h] BYREF

  _InterlockedAdd(&dword_180145058, 1u);
  _InterlockedAdd(&dword_180145058, 1u);
  v4 = (volatile signed __int32 *)*a2;
  if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    operator delete(*a2, 0x10u);
  *a2 = &GenericStringHandle<unsigned short>::s_EmptyString;
  if ( _InterlockedExchangeAdd(&dword_180145058, 0xFFFFFFFF) == 1 )
    operator delete(&GenericStringHandle<unsigned short>::s_EmptyString, 0x10u);
  v5 = -1;
  v24 = -1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v8 = 450;
LABEL_9:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v7);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_54;
  }
  if ( !SetThreadToken(0, 0) )
  {
    v8 = 454;
    goto LABEL_9;
  }
  v5 = (__int64)TokenHandle;
  v24 = (__int64)TokenHandle;
  LastError = 0;
LABEL_54:
  try
  {
    if ( LastError < 0 )
    {
      v27 = 0;
      pExceptionObject = &ComError::`vftable';
      v28 = LastError;
      v29 = 132;
      v30 = 1;
      throw (ComError *)&pExceptionObject;
    }
    StringSid = 0;
    if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    {
      if ( (int)GetLastError() > 0 )
        v11 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v11 = GetLastError();
      v32 = 0;
      v31 = &ComError::`vftable';
      v33 = v11;
      v34 = 137;
      v35 = 1;
      throw (ComError *)&v31;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_3e78b7e784103a2eddd42a41df8e41c2_Traceguids, StringSid);
    cchName = 0;
    cchReferencedDomainName = 0;
    peUse = 0;
    if ( !LookupAccountSidLocalW(Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) && GetLastError() != 122 )
    {
      if ( (int)GetLastError() > 0 )
        v12 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v12 = GetLastError();
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = v12;
      v39 = 157;
      v40 = 1;
      throw (ComError *)&v36;
    }
    *(_OWORD *)Name = 0;
    v21 = 0;
    std::vector<unsigned short>::_Construct_n<>(Name, cchName);
    *(_OWORD *)ReferencedDomainName = 0;
    v23 = 0;
    std::vector<unsigned short>::_Construct_n<>(ReferencedDomainName, cchReferencedDomainName);
    if ( !LookupAccountSidLocalW(Sid, Name[0], &cchName, ReferencedDomainName[0], &cchReferencedDomainName, &peUse) )
    {
      if ( (int)GetLastError() > 0 )
        v13 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v13 = GetLastError();
      v42 = 0;
      v41 = &ComError::`vftable';
      v43 = v13;
      v44 = 172;
      v45 = 1;
      throw (ComError *)&v41;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3e78b7e784103a2eddd42a41df8e41c2_Traceguids, Name[0]);
    v15 = GenericStringHandle<unsigned short>::NewString(Name[0]);
    if ( *a2 && _InterlockedExchangeAdd((volatile signed __int32 *)*a2 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a2, 0x10u);
    *a2 = (void *)v15;
    if ( ReferencedDomainName[0] )
    {
      std::_Deallocate<16>(
        ReferencedDomainName[0],
        2 * ((signed __int64)(v23 - (unsigned __int64)ReferencedDomainName[0]) >> 1));
      *(_OWORD *)ReferencedDomainName = 0;
      v23 = 0;
    }
    if ( Name[0] )
    {
      std::_Deallocate<16>(Name[0], 2 * ((signed __int64)(v21 - (unsigned __int64)Name[0]) >> 1));
      *(_OWORD *)Name = 0;
      v21 = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
    if ( v5 != -1 )
      wil::details::RevertImpersonateToken((HANDLE)v5, v14);
    result = 0;
  }
  catch ( const ComError *v25 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v17 = v25;
    }
    else
    {
      v17 = v25;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_3e78b7e784103a2eddd42a41df8e41c2_Traceguids,
        *((unsigned int *)v17 + 6),
        *((_DWORD *)v17 + 7));
    }
    return (DWORD)*((_DWORD *)v17 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x180012c00  push    rbx
0x180012c02  push    rsi
0x180012c03  push    r13
0x180012c05  push    r14
0x180012c07  push    r15
0x180012c09  sub     rsp, 200h
0x180012c10  mov     rsi, rdx
0x180012c13  mov     r15, rcx
0x180012c16  mov     r13d, 1
0x180012c1c  lock add cs:dword_180145058, r13d
0x180012c24  lock add cs:dword_180145058, r13d
0x180012c2c  mov     rdx, [rdx]
0x180012c2f  test    rdx, rdx
0x180012c32  jz      short loc_180012C4D
0x180012c34  or      eax, 0FFFFFFFFh
0x180012c37  lock xadd [rdx+8], eax
0x180012c3c  cmp     eax, r13d
0x180012c3f  jnz     short loc_180012C4D
0x180012c41  lea     edx, [r13+0Fh]; unsigned __int64
0x180012c45  mov     rcx, [rsi]; void *
0x180012c48  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012c4d  lea     rcx, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; void *
0x180012c54  mov     [rsi], rcx
0x180012c57  or      eax, 0FFFFFFFFh
0x180012c5a  lock xadd cs:dword_180145058, eax
0x180012c62  cmp     eax, r13d
0x180012c65  jnz     short loc_180012C72
0x180012c67  mov     edx, 10h; unsigned __int64
0x180012c6c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012c71  nop
0x180012c72  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012c76  mov     [rsp+228h+var_1B8], rbx
0x180012c7b  mov     [rsp+228h+TokenHandle], 0
0x180012c84  call    cs:__imp_GetCurrentThread
0x180012c8a  lea     r9, [rsp+228h+TokenHandle]; TokenHandle
0x180012c8f  mov     r8d, r13d; OpenAsSelf
0x180012c92  mov     edx, 0F01FFh; DesiredAccess
0x180012c97  mov     rcx, rax; ThreadHandle
0x180012c9a  call    cs:__imp_OpenThreadToken
0x180012ca0  test    eax, eax
0x180012ca2  jnz     short loc_180012CD9
0x180012ca4  call    cs:__imp_GetLastError
0x180012caa  cmp     eax, 3F0h
0x180012caf  jz      short loc_180012CD9
0x180012cb1  mov     edx, 1C2h; void *
0x180012cb6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012cbd  mov     rcx, [rsp+228h]; this
0x180012cc5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012cca  mov     r14d, eax
0x180012ccd  lea     rcx, [rsp+228h+TokenHandle]
0x180012cd2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180012cd7  jmp     short loc_180012CFB
0x180012cd9  xor     edx, edx; Token
0x180012cdb  xor     ecx, ecx; Thread
0x180012cdd  call    cs:__imp_SetThreadToken
0x180012ce3  test    eax, eax
0x180012ce5  jnz     short loc_180012CEE
0x180012ce7  mov     edx, 1C6h
0x180012cec  jmp     short loc_180012CB6
0x180012cee  mov     rbx, [rsp+228h+TokenHandle]
0x180012cf3  mov     [rsp+228h+var_1B8], rbx
0x180012cf8  xor     r14d, r14d
0x180012cfb  test    r14d, r14d
0x180012cfe  jns     short loc_180012D4A
0x180012d00  xorps   xmm0, xmm0
0x180012d03  movups  [rsp+228h+var_1A0], xmm0
0x180012d0b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180012d12  mov     [rsp+228h+pExceptionObject], rax
0x180012d1a  mov     [rsp+228h+var_190], r14d
0x180012d22  mov     [rsp+228h+var_18C], 84h
0x180012d2d  mov     [rsp+228h+var_188], r13d
0x180012d35  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180012d3c  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x180012d44  call    _CxxThrowException_0
0x180012d4a  mov     [rsp+228h+StringSid], 0
0x180012d53  lea     rdx, [rsp+228h+StringSid]; StringSid
0x180012d58  mov     rcx, r15; Sid
0x180012d5b  call    cs:__imp_ConvertSidToStringSidW
0x180012d61  test    eax, eax
0x180012d63  jnz     short loc_180012DD0
0x180012d65  call    cs:__imp_GetLastError
0x180012d6b  test    eax, eax
0x180012d6d  jg      short loc_180012D79
0x180012d6f  call    cs:__imp_GetLastError
0x180012d75  mov     ecx, eax
0x180012d77  jmp     short loc_180012D88
0x180012d79  call    cs:__imp_GetLastError
0x180012d7f  movzx   ecx, ax
0x180012d82  or      ecx, 80070000h
0x180012d88  xorps   xmm0, xmm0
0x180012d8b  movups  [rsp+228h+var_140], xmm0
0x180012d93  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180012d9a  mov     [rsp+228h+var_148], rax
0x180012da2  mov     [rsp+228h+var_130], ecx
0x180012da9  mov     [rsp+228h+var_12C], 89h
0x180012db4  mov     [rsp+228h+var_128], r13d
0x180012dbc  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180012dc3  lea     rcx, [rsp+228h+var_148]; pExceptionObject
0x180012dcb  call    _CxxThrowException_0
0x180012dd0  lea     r14, WPP_GLOBAL_Control
0x180012dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012dde  cmp     rcx, r14
0x180012de1  jz      short loc_180012E03
0x180012de3  test    [rcx+1Ch], r13b
0x180012de7  jz      short loc_180012E03
0x180012de9  mov     edx, 0Dh
0x180012dee  mov     r9, [rsp+228h+StringSid]
0x180012df3  lea     r8, WPP_3e78b7e784103a2eddd42a41df8e41c2_Traceguids
0x180012dfa  mov     rcx, [rcx+10h]
0x180012dfe  call    WPP_SF_S
0x180012e03  mov     [rsp+228h+cchName], 0
0x180012e0e  mov     [rsp+228h+arg_8], 0
0x180012e19  mov     [rsp+228h+arg_18], 0
0x180012e24  lea     rax, [rsp+228h+arg_18]
0x180012e2c  mov     [rsp+228h+peUse], rax; peUse
0x180012e31  lea     rax, [rsp+228h+arg_8]
0x180012e39  mov     [rsp+228h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180012e3e  xor     r9d, r9d; ReferencedDomainName
0x180012e41  lea     r8, [rsp+228h+cchName]; cchName
0x180012e49  xor     edx, edx; Name
0x180012e4b  mov     rcx, r15; Sid
0x180012e4e  call    cs:__imp_LookupAccountSidLocalW
0x180012e54  test    eax, eax
0x180012e56  jnz     short loc_180012ECE
0x180012e58  call    cs:__imp_GetLastError
0x180012e5e  cmp     eax, 7Ah ; 'z'
0x180012e61  jz      short loc_180012ECE
0x180012e63  call    cs:__imp_GetLastError
0x180012e69  test    eax, eax
0x180012e6b  jg      short loc_180012E77
0x180012e6d  call    cs:__imp_GetLastError
0x180012e73  mov     ecx, eax
0x180012e75  jmp     short loc_180012E86
0x180012e77  call    cs:__imp_GetLastError
0x180012e7d  movzx   ecx, ax
0x180012e80  or      ecx, 80070000h
0x180012e86  xorps   xmm0, xmm0
0x180012e89  movups  [rsp+228h+var_E0], xmm0
0x180012e91  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180012e98  mov     [rsp+228h+var_E8], rax
0x180012ea0  mov     [rsp+228h+var_D0], ecx
0x180012ea7  mov     [rsp+228h+var_CC], 9Dh
0x180012eb2  mov     [rsp+228h+var_C8], r13d
0x180012eba  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180012ec1  lea     rcx, [rsp+228h+var_E8]; pExceptionObject
0x180012ec9  call    _CxxThrowException_0
0x180012ece  xorps   xmm0, xmm0
0x180012ed1  movdqu  xmmword ptr [rsp+228h+Name], xmm0
0x180012ed7  mov     [rsp+228h+var_1D8], 0
0x180012ee0  mov     edx, [rsp+228h+cchName]
0x180012ee7  lea     rcx, [rsp+228h+Name]
0x180012eec  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x180012ef1  nop
0x180012ef2  xorps   xmm0, xmm0
0x180012ef5  movdqu  xmmword ptr [rsp+228h+ReferencedDomainName], xmm0
0x180012efb  mov     [rsp+228h+var_1C0], 0
0x180012f04  mov     edx, [rsp+228h+arg_8]
0x180012f0b  lea     rcx, [rsp+228h+ReferencedDomainName]
0x180012f10  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x180012f15  nop
0x180012f16  lea     rax, [rsp+228h+arg_18]
0x180012f1e  mov     [rsp+228h+peUse], rax; peUse
0x180012f23  lea     rax, [rsp+228h+arg_8]
0x180012f2b  mov     [rsp+228h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180012f30  mov     r9, [rsp+228h+ReferencedDomainName]; ReferencedDomainName
0x180012f35  lea     r8, [rsp+228h+cchName]; cchName
0x180012f3d  mov     rdx, [rsp+228h+Name]; Name
0x180012f42  mov     rcx, r15; Sid
0x180012f45  call    cs:__imp_LookupAccountSidLocalW
0x180012f4b  test    eax, eax
0x180012f4d  jnz     short loc_180012FBA
0x180012f4f  call    cs:__imp_GetLastError
0x180012f55  test    eax, eax
0x180012f57  jg      short loc_180012F63
0x180012f59  call    cs:__imp_GetLastError
0x180012f5f  mov     ecx, eax
0x180012f61  jmp     short loc_180012F72
0x180012f63  call    cs:__imp_GetLastError
0x180012f69  movzx   ecx, ax
0x180012f6c  or      ecx, 80070000h
0x180012f72  xorps   xmm0, xmm0
0x180012f75  movups  [rsp+228h+var_80], xmm0
0x180012f7d  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180012f84  mov     [rsp+228h+var_88], rax
0x180012f8c  mov     [rsp+228h+var_70], ecx
0x180012f93  mov     [rsp+228h+var_6C], 0ACh
0x180012f9e  mov     [rsp+228h+var_68], r13d
0x180012fa6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180012fad  lea     rcx, [rsp+228h+var_88]; pExceptionObject
0x180012fb5  call    _CxxThrowException_0
0x180012fba  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fc1  cmp     rcx, r14
0x180012fc4  jz      short loc_180012FE6
0x180012fc6  test    [rcx+1Ch], r13b
0x180012fca  jz      short loc_180012FE6
0x180012fcc  mov     edx, 0Eh
0x180012fd1  mov     r9, [rsp+228h+Name]
0x180012fd6  lea     r8, WPP_3e78b7e784103a2eddd42a41df8e41c2_Traceguids
0x180012fdd  mov     rcx, [rcx+10h]
0x180012fe1  call    WPP_SF_S
0x180012fe6  mov     rcx, [rsp+228h+Name]
0x180012feb  call    ?NewString@?$GenericStringHandle@G@@CAPEAUStringData@1@PEBG@Z; GenericStringHandle<ushort>::NewString(ushort const *)
0x180012ff0  mov     r14, rax
0x180012ff3  mov     r8, [rsi]
0x180012ff6  test    r8, r8
0x180012ff9  jz      short loc_180013014
0x180012ffb  or      ecx, 0FFFFFFFFh
0x180012ffe  lock xadd [r8+8], ecx
0x180013004  cmp     ecx, 1
0x180013007  jnz     short loc_180013014
0x180013009  lea     edx, [rcx+0Fh]; unsigned __int64
0x18001300c  mov     rcx, [rsi]; void *
0x18001300f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013014  mov     [rsi], r14
0x180013017  mov     rcx, [rsp+228h+ReferencedDomainName]
0x18001301c  test    rcx, rcx
0x18001301f  jz      short loc_180013046
0x180013021  mov     rdx, [rsp+228h+var_1C0]
0x180013026  sub     rdx, rcx
0x180013029  sar     rdx, 1
0x18001302c  add     rdx, rdx
0x18001302f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013034  xorps   xmm0, xmm0
0x180013037  movdqu  xmmword ptr [rsp+228h+ReferencedDomainName], xmm0
0x18001303d  mov     [rsp+228h+var_1C0], 0
0x180013046  mov     rcx, [rsp+228h+Name]
0x18001304b  test    rcx, rcx
0x18001304e  jz      short loc_180013075
0x180013050  mov     rdx, [rsp+228h+var_1D8]
0x180013055  sub     rdx, rcx
0x180013058  sar     rdx, 1
0x18001305b  add     rdx, rdx
0x18001305e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013063  xorps   xmm0, xmm0
0x180013066  movdqu  xmmword ptr [rsp+228h+Name], xmm0
0x18001306c  mov     [rsp+228h+var_1D8], 0
0x180013075  mov     rcx, [rsp+228h+StringSid]; hMem
0x18001307a  test    rcx, rcx
0x18001307d  jz      short loc_180013086
0x18001307f  call    cs:__imp_LocalFree
0x180013085  nop
0x180013086  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001308a  jz      short loc_180013094
0x18001308c  mov     rcx, rbx; Token
0x18001308f  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180013094  xor     eax, eax
0x180013096  jmp     short loc_18001309F
0x180013098  mov     eax, [rsp+228h+arg_8]
0x18001309f  add     rsp, 200h
0x1800130a6  pop     r15
0x1800130a8  pop     r14
0x1800130aa  pop     r13
0x1800130ac  pop     rsi
0x1800130ad  pop     rbx
0x1800130ae  retn
```
