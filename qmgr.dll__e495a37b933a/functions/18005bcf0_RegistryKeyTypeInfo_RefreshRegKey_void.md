# RegistryKeyTypeInfo::RefreshRegKey(void)

- ea: `0x18005bcf0`
- end: `0x18005bf77`
- name: `?RefreshRegKey@RegistryKeyTypeInfo@@UEAAJXZ`
- size: `647`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800388c0`
- `0x1800960f4`

## callees

- `0x180011760`
- `0x18005bcf0`
- `0x18005bf80`
- `0x180080430`
- `0x180086674`
- `0x1800959c0`
- `0x18009b668`
- `0x1800f6278`
- `0x1800f62dc`
- `0x1800f6398`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005bd9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005bd9e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005bdb3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005bdb3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005bdf8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005bdf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bdbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bdbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005beb2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005beb2`

## string_xrefs

- `0x18005bdcf`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistryKeyTypeInfo::RefreshRegKey(HKEY *this)
{
  const unsigned __int16 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // r10
  int v6; // edx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r11
  __int64 v10; // rbx
  void **v11; // rdi
  HANDLE CurrentThread; // rax
  const char *v13; // r9
  __int64 v14; // rdx
  int LastError; // edi
  const WCHAR *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  HKEY v20; // r14
  HKEY v21; // rdi
  __int64 result; // rax
  const ComError *v23; // rbx
  const ComError *v24; // [rsp+50h] [rbp-E8h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-D8h] BYREF
  __int128 v26; // [rsp+68h] [rbp-D0h]
  int v27; // [rsp+78h] [rbp-C0h]
  int v28; // [rsp+7Ch] [rbp-BCh]
  int v29; // [rsp+80h] [rbp-B8h]
  void **v30; // [rsp+C0h] [rbp-78h] BYREF
  __int128 v31; // [rsp+C8h] [rbp-70h]
  int v32; // [rsp+D8h] [rbp-60h]
  int v33; // [rsp+DCh] [rbp-5Ch]
  int v34; // [rsp+E0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]
  __int64 v36; // [rsp+148h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+150h] [rbp+18h] BYREF
  __int64 v38; // [rsp+158h] [rbp+20h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v2 = RegistryKeyTypeInfo::StringifyPredefinedRegKey(this[2]);
    v4 = RegistryKeyTypeInfo::StringifyRegistryKeyType(*((unsigned int *)this + 2), v3, v2);
    WPP_SF_qSSSS(*(_QWORD *)(v5 + 16), v6, v7, (_DWORD)this, v4, v7, v8, v9);
  }
  v10 = -1;
  v38 = -1;
  v36 = 0;
  v11 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v36);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, v11) && GetLastError() != 1008 )
  {
    v14 = 450;
LABEL_7:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v14,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v13);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
    goto LABEL_29;
  }
  if ( !SetThreadToken(0, 0) )
  {
    v14 = 454;
    goto LABEL_7;
  }
  v10 = v36;
  v38 = v36;
  LastError = 0;
LABEL_29:
  try
  {
    if ( LastError < 0 )
    {
      v26 = 0;
      pExceptionObject = &ComError::`vftable';
      v27 = LastError;
      v28 = 328;
      v29 = 1;
      throw (ComError *)&pExceptionObject;
    }
    phkResult = 0;
    v17 = (const WCHAR *)(this + 3);
    if ( (unsigned __int64)this[6] > 7 )
      v17 = *(const WCHAR **)v17;
    v18 = RegCreateKeyExW(this[2], v17, 0, 0, *((_BYTE *)this + 56) != 0, 0xF003Fu, 0, &phkResult, 0);
    if ( v18 )
    {
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      v31 = 0;
      v30 = &ComError::`vftable';
      v32 = v18;
      v33 = 345;
      v34 = 1;
      throw (ComError *)&v30;
    }
    v20 = phkResult;
    v21 = this[8];
    if ( v21 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v36);
      RegCloseKey(v21);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v36);
    }
    this[8] = v20;
    if ( v10 != -1 )
      wil::details::RevertImpersonateToken((HANDLE)v10, v19);
    result = 0;
  }
  catch ( const ComError *v24 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v23 = v24;
    }
    else
    {
      v23 = v24;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_37e8ee7438c23e813b7f65a690b97145_Traceguids,
        *((unsigned int *)v23 + 6),
        *((_DWORD *)v23 + 7));
    }
    LODWORD(v36) = *((_DWORD *)v23 + 6);
    return (unsigned int)v36;
  }
  if ( LastError < 0 )
  {
    v26 = 0;
    pExceptionObject = &ComError::`vftable';
    v27 = LastError;
    v28 = 328;
    v29 = 1;
    throw (ComError *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18005bcf0  mov     [rsp+arg_0], rbx
0x18005bcf5  push    rsi
0x18005bcf6  push    rdi
0x18005bcf7  push    r14
0x18005bcf9  sub     rsp, 120h
0x18005bd00  mov     rsi, rcx
0x18005bd03  lea     rax, WPP_GLOBAL_Control
0x18005bd0a  mov     r10, cs:WPP_GLOBAL_Control
0x18005bd11  cmp     r10, rax
0x18005bd14  jz      short loc_18005BD76
0x18005bd16  test    byte ptr [r10+1Ch], 1
0x18005bd1b  jz      short loc_18005BD76
0x18005bd1d  lea     rax, aNo; "NO"
0x18005bd24  lea     r11, aYes; "YES"
0x18005bd2b  cmp     byte ptr [rcx+38h], 0
0x18005bd2f  cmovz   r11, rax
0x18005bd33  lea     r9, [rcx+18h]
0x18005bd37  cmp     qword ptr [r9+18h], 7
0x18005bd3c  jbe     short loc_18005BD41
0x18005bd3e  mov     r9, [r9]
0x18005bd41  mov     rcx, [rcx+10h]; HKEY
0x18005bd45  call    ?StringifyPredefinedRegKey@RegistryKeyTypeInfo@@CAPEBGPEAUHKEY__@@@Z; RegistryKeyTypeInfo::StringifyPredefinedRegKey(HKEY__ *)
0x18005bd4a  mov     r8, rax
0x18005bd4d  mov     ecx, [rsi+8]
0x18005bd50  call    ?StringifyRegistryKeyType@RegistryKeyTypeInfo@@SAPEBGW4RegistryKeyType@@@Z; RegistryKeyTypeInfo::StringifyRegistryKeyType(RegistryKeyType)
0x18005bd55  mov     [rsp+138h+phkResult], r11
0x18005bd5a  mov     [rsp+138h+lpSecurityAttributes], r9
0x18005bd5f  mov     qword ptr [rsp+138h+samDesired], r8
0x18005bd64  mov     qword ptr [rsp+138h+dwOptions], rax
0x18005bd69  mov     r9, rsi
0x18005bd6c  mov     rcx, [r10+10h]
0x18005bd70  call    WPP_SF_qSSSS
0x18005bd75  nop
0x18005bd76  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005bd7a  mov     [rsp+138h+arg_18], rbx
0x18005bd82  mov     [rsp+138h+arg_8], 0
0x18005bd8e  lea     rcx, [rsp+138h+arg_8]
0x18005bd96  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x18005bd9b  mov     rdi, rax
0x18005bd9e  call    cs:__imp_GetCurrentThread
0x18005bda4  mov     r9, rdi; TokenHandle
0x18005bda7  mov     edx, 0F01FFh; DesiredAccess
0x18005bdac  lea     r8d, [rbx+2]; OpenAsSelf
0x18005bdb0  mov     rcx, rax; ThreadHandle
0x18005bdb3  call    cs:__imp_OpenThreadToken
0x18005bdb9  test    eax, eax
0x18005bdbb  jnz     short loc_18005BDF4
0x18005bdbd  call    cs:__imp_GetLastError
0x18005bdc3  cmp     eax, 3F0h
0x18005bdc8  jz      short loc_18005BDF4
0x18005bdca  mov     edx, 1C2h; void *
0x18005bdcf  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005bdd6  mov     rcx, [rsp+138h]; this
0x18005bdde  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005bde3  mov     edi, eax
0x18005bde5  lea     rcx, [rsp+138h+arg_8]
0x18005bded  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005bdf2  jmp     short loc_18005BE1B
0x18005bdf4  xor     edx, edx; Token
0x18005bdf6  xor     ecx, ecx; Thread
0x18005bdf8  call    cs:__imp_SetThreadToken
0x18005bdfe  test    eax, eax
0x18005be00  jnz     short loc_18005BE09
0x18005be02  mov     edx, 1C6h
0x18005be07  jmp     short loc_18005BDCF
0x18005be09  mov     rbx, [rsp+138h+arg_8]
0x18005be11  mov     [rsp+138h+arg_18], rbx
0x18005be19  xor     edi, edi
0x18005be1b  test    edi, edi
0x18005be1d  jns     short loc_18005BE5B
0x18005be1f  xorps   xmm0, xmm0
0x18005be22  movups  [rsp+138h+var_D0], xmm0
0x18005be27  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18005be2e  mov     [rsp+138h+pExceptionObject], rcx
0x18005be33  mov     [rsp+138h+var_C0], edi
0x18005be37  mov     [rsp+138h+var_BC], 148h
0x18005be3f  mov     [rsp+138h+var_B8], 1
0x18005be4a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005be51  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18005be56  call    _CxxThrowException_0
0x18005be5b  mov     [rsp+138h+arg_10], 0
0x18005be67  xor     eax, eax
0x18005be69  cmp     [rsi+38h], al
0x18005be6c  setnz   al
0x18005be6f  lea     rdx, [rsi+18h]
0x18005be73  cmp     qword ptr [rdx+18h], 7
0x18005be78  jbe     short loc_18005BE7D
0x18005be7a  mov     rdx, [rdx]; lpSubKey
0x18005be7d  mov     [rsp+138h+lpdwDisposition], 0; lpdwDisposition
0x18005be86  lea     rcx, [rsp+138h+arg_10]
0x18005be8e  mov     [rsp+138h+phkResult], rcx; phkResult
0x18005be93  mov     [rsp+138h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005be9c  mov     [rsp+138h+samDesired], 0F003Fh; samDesired
0x18005bea4  mov     [rsp+138h+dwOptions], eax; dwOptions
0x18005bea8  xor     r9d, r9d; lpClass
0x18005beab  xor     r8d, r8d; Reserved
0x18005beae  mov     rcx, [rsi+10h]; hKey
0x18005beb2  call    cs:__imp_RegCreateKeyExW
0x18005beb8  test    eax, eax
0x18005beba  jz      short loc_18005BF11
0x18005bebc  jle     short loc_18005BEC6
0x18005bebe  movzx   eax, ax
0x18005bec1  or      eax, 80070000h
0x18005bec6  xorps   xmm0, xmm0
0x18005bec9  movups  [rsp+138h+var_70], xmm0
0x18005bed1  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18005bed8  mov     [rsp+138h+var_78], rcx
0x18005bee0  mov     [rsp+138h+var_60], eax
0x18005bee7  mov     [rsp+138h+var_5C], 159h
0x18005bef2  mov     [rsp+138h+var_58], 1
0x18005befd  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005bf04  lea     rcx, [rsp+138h+var_78]; pExceptionObject
0x18005bf0c  call    _CxxThrowException_0
0x18005bf11  mov     r14, [rsp+138h+arg_10]
0x18005bf19  mov     rdi, [rsi+40h]
0x18005bf1d  test    rdi, rdi
0x18005bf20  jz      short loc_18005BF45
0x18005bf22  lea     rcx, [rsp+138h+arg_8]; this
0x18005bf2a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005bf2f  mov     rcx, rdi; hKey
0x18005bf32  call    cs:__imp_RegCloseKey
0x18005bf38  lea     rcx, [rsp+138h+arg_8]; this
0x18005bf40  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005bf45  mov     [rsi+40h], r14
0x18005bf49  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18005bf4d  jz      short loc_18005BF57
0x18005bf4f  mov     rcx, rbx; Token
0x18005bf52  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18005bf57  xor     eax, eax
0x18005bf59  jmp     short loc_18005BF62
0x18005bf5b  mov     eax, dword ptr [rsp+138h+arg_8]
0x18005bf62  mov     rbx, [rsp+138h+arg_0]
0x18005bf6a  add     rsp, 120h
0x18005bf71  pop     r14
0x18005bf73  pop     rdi
0x18005bf74  pop     rsi
0x18005bf75  retn
```
