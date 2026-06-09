# ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(void)

- ea: `0x18005e0fc`
- end: `0x18005e225`
- name: `?GenerateImpersonationToken@ConstrainedImpersonateLoggedOnUser@@AEAAJXZ`
- size: `297`
- prototype: `__int64 __fastcall(ConstrainedImpersonateLoggedOnUser *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005df38`

## callees

- `0x180002b60`
- `0x180003a80`
- `0x18000683c`
- `0x1800076d4`
- `0x18000a4f8`
- `0x180054340`
- `0x18005d048`
- `0x18005e0fc`
- `0x18006e010`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18005e1ce`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18005e1ce`

## string_xrefs

- `0x18005e1e2`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConstrainedImpersonateLoggedOnUser::GenerateImpersonationToken(
        ConstrainedImpersonateLoggedOnUser *this)
{
  char *v2; // rsi
  int ConstrainedUserToken; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v8[2]; // [rsp+20h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-50h] BYREF
  __int64 v10; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( *((_QWORD *)this + 2) )
  {
    v2 = (char *)this + 8;
    if ( ((*((_QWORD *)this + 1) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( (unsigned __int8)IsUMgrGetConstrainedUserTokenPresent() )
      {
        *(_QWORD *)v8 = 0;
        v10 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.System.Internal.UserManager",
          0x24u,
          0x23u);
        ConstrainedUserToken = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
                                 v10,
                                 v8);
        v4 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          v5 = 129;
LABEL_10:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v5,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
            (const char *)(unsigned int)ConstrainedUserToken,
            v8[0]);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v8);
          return v4;
        }
        ConstrainedUserToken = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**(_QWORD **)v8 + 136LL))(
                                 *(_QWORD *)v8,
                                 *((_QWORD *)this + 2),
                                 (char *)this + 24);
        v4 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          v5 = 131;
          goto LABEL_10;
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          v2,
          0,
          v6);
        ConstrainedUserToken = UMgrGetConstrainedUserToken(0, *((_QWORD *)this + 3), 0, v2);
        v4 = ConstrainedUserToken;
        if ( ConstrainedUserToken < 0 )
        {
          v5 = 133;
          goto LABEL_10;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v8);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005e0fc  push    rbx
0x18005e0fe  push    rsi
0x18005e0ff  push    rdi
0x18005e100  push    r14
0x18005e102  sub     rsp, 58h
0x18005e106  mov     rax, cs:__security_cookie
0x18005e10d  xor     rax, rsp
0x18005e110  mov     [rsp+78h+var_30], rax
0x18005e115  mov     rdi, rcx
0x18005e118  cmp     qword ptr [rcx+10h], 0
0x18005e11d  jz      loc_18005E20C
0x18005e123  lea     rsi, [rcx+8]
0x18005e127  mov     rax, [rsi]
0x18005e12a  inc     rax
0x18005e12d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18005e133  jnz     loc_18005E20C
0x18005e139  call    IsUMgrGetConstrainedUserTokenPresent
0x18005e13e  test    al, al
0x18005e140  jz      loc_18005E20C
0x18005e146  mov     qword ptr [rsp+78h+var_58], 0; int
0x18005e14f  mov     [rsp+78h+var_38], 0
0x18005e158  mov     r9d, 23h ; '#'; unsigned int
0x18005e15e  lea     r8d, [r9+1]; unsigned int
0x18005e162  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18005e169  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x18005e16e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005e173  lea     rdx, [rsp+78h+var_58]
0x18005e178  mov     rcx, [rsp+78h+var_38]
0x18005e17d  call    ??$GetActivationFactory@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18005e182  mov     ebx, eax
0x18005e184  test    eax, eax
0x18005e186  jns     short loc_18005E18F
0x18005e188  mov     edx, 81h
0x18005e18d  jmp     short loc_18005E1DF
0x18005e18f  mov     rcx, qword ptr [rsp+78h+var_58]
0x18005e194  mov     rax, [rcx]
0x18005e197  lea     r8, [rdi+18h]
0x18005e19b  mov     rdx, [rdi+10h]
0x18005e19f  mov     rax, [rax+88h]
0x18005e1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1ab  mov     ebx, eax
0x18005e1ad  test    eax, eax
0x18005e1af  jns     short loc_18005E1B8
0x18005e1b1  mov     edx, 83h
0x18005e1b6  jmp     short loc_18005E1DF
0x18005e1b8  xor     edx, edx
0x18005e1ba  mov     rcx, rsi
0x18005e1bd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005e1c2  mov     r9, rsi
0x18005e1c5  xor     r8d, r8d
0x18005e1c8  mov     rdx, [rdi+18h]
0x18005e1cc  xor     ecx, ecx
0x18005e1ce  call    cs:__imp_UMgrGetConstrainedUserToken
0x18005e1d4  mov     ebx, eax
0x18005e1d6  test    eax, eax
0x18005e1d8  jns     short loc_18005E202
0x18005e1da  mov     edx, 85h; void *
0x18005e1df  mov     r9d, eax; char *
0x18005e1e2  lea     r8, aOnecoreInterna; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18005e1e9  mov     rcx, [rsp+78h]; this
0x18005e1ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e1f3  nop
0x18005e1f4  lea     rcx, [rsp+78h+var_58]
0x18005e1f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005e1fe  mov     eax, ebx
0x18005e200  jmp     short loc_18005E20E
0x18005e202  lea     rcx, [rsp+78h+var_58]
0x18005e207  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005e20c  xor     eax, eax
0x18005e20e  mov     rcx, [rsp+78h+var_30]
0x18005e213  xor     rcx, rsp; StackCookie
0x18005e216  call    __security_check_cookie
0x18005e21b  add     rsp, 58h
0x18005e21f  pop     r14
0x18005e221  pop     rdi
0x18005e222  pop     rsi
0x18005e223  pop     rbx
0x18005e224  retn
```
