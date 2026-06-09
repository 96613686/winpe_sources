# CUserACLApplicator::Init(void)

- ea: `0x18000b7e0`
- end: `0x18000b97d`
- name: `?Init@CUserACLApplicator@@UEAAJXZ`
- size: `413`
- prototype: `__int64 __fastcall(CUserACLApplicator *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ab70`

## callees

- `0x180004594`
- `0x18000b7e0`
- `0x18000c7d4`
- `0x18000f864`
- `0x180011118`
- `0x18001d5e4`
- `0x180022830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000b8ea`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000b8ea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b892`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b892`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18000b92f`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18000b92f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000b847`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000b847`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b879`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b879`

## string_xrefs

- `0x18000b85b`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b8cc`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`
- `0x18000b8ff`: `onecore\ds\security\gina\profile\profext\DirJuncHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserACLApplicator::Init(CUserACLApplicator *this)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  DWORD v4; // esi
  void *v5; // rax
  struct _ACL *v6; // rdi
  const char *v7; // r9
  __int64 v8; // rdx
  int i; // ebx
  int v11; // [rsp+20h] [rbp-60h]
  HLOCAL hMem; // [rsp+60h] [rbp-20h] BYREF
  PSID pSid; // [rsp+68h] [rbp-18h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  hMem = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &hMem) )
  {
    pSid = hMem;
    v4 = GetLengthSid(hMem) + 16;
    v5 = operator new[](v4);
    wil::unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>::reset(
      (char *)this + 8,
      v5,
      v4);
    v6 = (struct _ACL *)*((_QWORD *)this + 1);
    if ( v6 )
    {
      if ( InitializeAcl(v6, v4, 2u) )
      {
        for ( i = 0; !i; i = 1 )
        {
          if ( !AddAccessDeniedAce(v6, 2u, 1u, pSid) )
          {
            v8 = 141;
            goto LABEL_8;
          }
        }
        LastError = 0;
      }
      else
      {
        v8 = 137;
LABEL_8:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v8,
                      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
                      v7);
      }
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
        (const char *)0x8007000ELL,
        v11);
    }
    wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&hMem);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7D,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\DirJuncHelper.h",
                  v2);
    if ( hMem )
      LocalFree(hMem);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000b7e0  mov     r11, rsp
0x18000b7e3  mov     [r11+10h], rbx
0x18000b7e7  mov     [r11+18h], rsi
0x18000b7eb  push    rbp
0x18000b7ec  push    rdi
0x18000b7ed  push    r14
0x18000b7ef  mov     rbp, rsp
0x18000b7f2  sub     rsp, 80h
0x18000b7f9  mov     rax, cs:__security_cookie
0x18000b800  xor     rax, rsp
0x18000b803  mov     [rbp+var_8], rax
0x18000b807  mov     rdi, rcx
0x18000b80a  xor     r14d, r14d
0x18000b80d  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x18000b811  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 100h
0x18000b817  mov     [rbp+hMem], r14
0x18000b81b  lea     rax, [rbp+hMem]
0x18000b81f  mov     [r11-48h], rax
0x18000b823  mov     [r11-50h], r14d
0x18000b827  mov     [r11-58h], r14d
0x18000b82b  mov     [r11-60h], r14d
0x18000b82f  mov     [r11-68h], r14d
0x18000b833  mov     [r11-70h], r14d
0x18000b837  mov     [r11-78h], r14d
0x18000b83b  xor     r9d, r9d; nSubAuthority1
0x18000b83e  xor     r8d, r8d; nSubAuthority0
0x18000b841  mov     dl, 1; nSubAuthorityCount
0x18000b843  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18000b847  call    cs:__imp_AllocateAndInitializeSid
0x18000b84e  nop     dword ptr [rax+rax+00h]
0x18000b853  test    eax, eax
0x18000b855  jnz     short loc_18000B88A
0x18000b857  mov     rcx, [rbp+18h]; this
0x18000b85b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000b862  lea     edx, [rax+7Dh]; void *
0x18000b865  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b86a  mov     ebx, eax
0x18000b86c  mov     rcx, [rbp+hMem]; hMem
0x18000b870  test    rcx, rcx
0x18000b873  jz      loc_18000B956
0x18000b879  call    cs:__imp_LocalFree
0x18000b880  nop     dword ptr [rax+rax+00h]
0x18000b885  jmp     loc_18000B956
0x18000b88a  mov     rcx, [rbp+hMem]; pSid
0x18000b88e  mov     [rbp+pSid], rcx
0x18000b892  call    cs:__imp_GetLengthSid
0x18000b899  nop     dword ptr [rax+rax+00h]
0x18000b89e  lea     esi, [rax+10h]
0x18000b8a1  mov     ecx, esi; unsigned __int64
0x18000b8a3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b8a8  mov     r8d, esi
0x18000b8ab  mov     rdx, rax
0x18000b8ae  lea     rcx, [rdi+8]
0x18000b8b2  call    ?reset@?$unique_any_array_ptr@EU?$default_delete@$$BY0A@E@std@@Uempty_deleter@wil@@_K@wil@@QEAAXPEAE_K@Z; wil::unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>::reset(uchar *,unsigned __int64)
0x18000b8b7  mov     rdi, [rdi+8]
0x18000b8bb  test    rdi, rdi
0x18000b8be  jnz     short loc_18000B8DF
0x18000b8c0  mov     rcx, [rbp+18h]; this
0x18000b8c4  mov     ebx, 8007000Eh
0x18000b8c9  mov     r9d, ebx; char *
0x18000b8cc  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000b8d3  mov     edx, 85h; void *
0x18000b8d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8dd  jmp     short loc_18000B94D
0x18000b8df  mov     r8d, 2; dwAclRevision
0x18000b8e5  mov     edx, esi; nAclLength
0x18000b8e7  mov     rcx, rdi; pAcl
0x18000b8ea  call    cs:__imp_InitializeAcl
0x18000b8f1  nop     dword ptr [rax+rax+00h]
0x18000b8f6  test    eax, eax
0x18000b8f8  jnz     short loc_18000B913
0x18000b8fa  mov     edx, 89h; void *
0x18000b8ff  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000b906  mov     rcx, [rbp+18h]; this
0x18000b90a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b90f  mov     ebx, eax
0x18000b911  jmp     short loc_18000B94D
0x18000b913  mov     ebx, r14d
0x18000b916  cmp     ebx, 1
0x18000b919  jnb     short loc_18000B94A
0x18000b91b  mov     r9d, ebx
0x18000b91e  mov     r9, [rbp+r9*8+pSid]; pSid
0x18000b923  mov     edx, 2; dwAceRevision
0x18000b928  lea     r8d, [rdx-1]; AccessMask
0x18000b92c  mov     rcx, rdi; pAcl
0x18000b92f  call    cs:__imp_AddAccessDeniedAce
0x18000b936  nop     dword ptr [rax+rax+00h]
0x18000b93b  test    eax, eax
0x18000b93d  jz      short loc_18000B943
0x18000b93f  inc     ebx
0x18000b941  jmp     short loc_18000B916
0x18000b943  mov     edx, 8Dh
0x18000b948  jmp     short loc_18000B8FF
0x18000b94a  mov     ebx, r14d
0x18000b94d  lea     rcx, [rbp+hMem]
0x18000b951  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18000b956  mov     eax, ebx
0x18000b958  mov     rcx, [rbp+var_8]
0x18000b95c  xor     rcx, rsp; StackCookie
0x18000b95f  call    __security_check_cookie
0x18000b964  lea     r11, [rsp+80h+var_s0]
0x18000b96c  mov     rbx, [r11+28h]
0x18000b970  mov     rsi, [r11+30h]
0x18000b974  mov     rsp, r11
0x18000b977  pop     r14
0x18000b979  pop     rdi
0x18000b97a  pop     rbp
0x18000b97b  retn
```
