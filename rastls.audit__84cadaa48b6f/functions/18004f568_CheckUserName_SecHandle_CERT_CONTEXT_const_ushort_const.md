# CheckUserName(_SecHandle,_CERT_CONTEXT const *,ushort const *)

- ea: `0x18004f568`
- end: `0x18004f8d4`
- name: `?CheckUserName@@YAKU_SecHandle@@PEBU_CERT_CONTEXT@@PEBG@Z`
- size: `876`
- prototype: `unsigned int(struct _SecHandle *__struct_ptr, const struct _CERT_CONTEXT *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004eaf8`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18002e900`
- `0x180038270`
- `0x18004f568`
- `0x18005dbe4`
- `0x18007a688`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004f71b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004f7c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004f71b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004f7c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f88b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f88b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f8c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f8c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f80d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f81c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f82b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f80d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f81c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f82b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004f872`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004f872`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004f65c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004f65c`
- `SspiCli!GetUserNameExW` at `0x18004f6c1`
- `SspiCli!GetUserNameExW` at `0x18004f6c1`
- `SspiCli!QuerySecurityContextToken` at `0x18004f618`
- `SspiCli!QuerySecurityContextToken` at `0x18004f618`

## pseudocode

```c
__int64 __fastcall CheckUserName(struct _SecHandle *a1, const struct _CERT_CONTEXT *a2, const unsigned __int16 *a3)
{
  struct _SecHandle v3; // xmm0
  unsigned __int16 *v6; // rsi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  DWORD v9; // eax
  DWORD LastError; // eax
  DWORD v12; // eax
  ULONG nSize; // [rsp+30h] [rbp-D0h] BYREF
  void *Token; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v15; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v16; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v17; // [rsp+50h] [rbp-B0h]
  struct _SecHandle phContext; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR NameBuffer[520]; // [rsp+70h] [rbp-90h] BYREF

  v3 = *a1;
  Token = 0;
  phContext = v3;
  nSize = 0;
  v6 = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
  if ( g_eapTlsDisableADChecks || g_useCustomRootStore )
  {
    v6 = v15;
    FCertToStr(a2, 0);
    v8 = -2146893044;
  }
  else
  {
    v7 = QuerySecurityContextToken(&phContext, &Token);
    v8 = v7;
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v7);
    }
    else
    {
      if ( ImpersonateLoggedOnUser(Token) )
      {
        nSize = 514;
        if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
        {
          if ( (unsigned int)_o__wcsicmp(a3, NameBuffer) )
          {
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                166,
                (unsigned int)&WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
                (_DWORD)a3,
                (__int64)NameBuffer);
            v8 = -2146893044;
          }
          else
          {
            v8 = 0;
          }
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              165,
              &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
              LastError);
        }
        if ( !RevertToSelf() && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v12 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v12);
        }
      }
      else
      {
        v9 = GetLastError();
        v8 = v9;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v9);
      }
      CloseHandle(Token);
    }
  }
  LocalFree(v6);
  LocalFree(0);
  LocalFree(0);
  return v8;
}

```

## disassembly

```asm
0x18004f568  mov     [rsp-8+arg_18], rbx
0x18004f56d  push    rbp
0x18004f56e  push    rsi
0x18004f56f  push    rdi
0x18004f570  push    r12
0x18004f572  push    r13
0x18004f574  push    r14
0x18004f576  push    r15
0x18004f578  lea     rbp, [rsp-390h]
0x18004f580  sub     rsp, 490h
0x18004f587  mov     rax, cs:__security_cookie
0x18004f58e  xor     rax, rsp
0x18004f591  mov     [rbp+3C0h+var_40], rax
0x18004f598  movups  xmm0, xmmword ptr [rcx]
0x18004f59b  xor     r13d, r13d
0x18004f59e  mov     r14, r8
0x18004f5a1  mov     rbx, rdx
0x18004f5a4  mov     [rsp+4C0h+Token], r13
0x18004f5a9  movdqu  xmmword ptr [rsp+4C0h+phContext.dwLower], xmm0
0x18004f5af  mov     [rsp+4C0h+nSize], r13d
0x18004f5b4  mov     esi, r13d
0x18004f5b7  mov     [rsp+4C0h+var_480], r13
0x18004f5bc  mov     r15d, r13d
0x18004f5bf  mov     [rsp+4C0h+var_470], r13
0x18004f5c4  mov     r12d, r13d
0x18004f5c7  mov     [rsp+4C0h+var_478], r13
0x18004f5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f5d3  lea     rdi, WPP_GLOBAL_Control
0x18004f5da  cmp     rcx, rdi
0x18004f5dd  jz      short loc_18004F5F4
0x18004f5df  mov     rcx, [rcx+10h]
0x18004f5e3  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18004f5ea  mov     edx, 0A2h
0x18004f5ef  call    WPP_SF_
0x18004f5f4  cmp     cs:?g_eapTlsDisableADChecks@@3HA, r13d; int g_eapTlsDisableADChecks
0x18004f5fb  jnz     loc_18004F76E
0x18004f601  cmp     cs:?g_useCustomRootStore@@3_NA, r13b; bool g_useCustomRootStore
0x18004f608  jnz     loc_18004F76E
0x18004f60e  lea     rdx, [rsp+4C0h+Token]; Token
0x18004f613  lea     rcx, [rsp+4C0h+phContext]; phContext
0x18004f618  call    cs:__imp_QuerySecurityContextToken
0x18004f61f  nop     dword ptr [rax+rax+00h]
0x18004f624  mov     ebx, eax
0x18004f626  test    eax, eax
0x18004f628  jz      short loc_18004F657
0x18004f62a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f631  cmp     rcx, rdi
0x18004f634  jz      loc_18004F80A
0x18004f63a  mov     rcx, [rcx+10h]
0x18004f63e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18004f645  mov     edx, 0A3h
0x18004f64a  mov     r9d, eax
0x18004f64d  call    WPP_SF_d
0x18004f652  jmp     loc_18004F80A
0x18004f657  mov     rcx, [rsp+4C0h+Token]; hToken
0x18004f65c  call    cs:__imp_ImpersonateLoggedOnUser
0x18004f663  nop     dword ptr [rax+rax+00h]
0x18004f668  test    eax, eax
0x18004f66a  jnz     short loc_18004F6A7
0x18004f66c  call    cs:__imp_GetLastError
0x18004f673  nop     dword ptr [rax+rax+00h]
0x18004f678  mov     ebx, eax
0x18004f67a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f681  cmp     rcx, rdi
0x18004f684  jz      loc_18004F8BE
0x18004f68a  mov     rcx, [rcx+10h]
0x18004f68e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18004f695  mov     edx, 0A4h
0x18004f69a  mov     r9d, eax
0x18004f69d  call    WPP_SF_d
0x18004f6a2  jmp     loc_18004F8BE
0x18004f6a7  mov     edi, 1
0x18004f6ac  mov     [rsp+4C0h+nSize], 202h
0x18004f6b4  lea     r8, [rsp+4C0h+nSize]; nSize
0x18004f6b9  lea     rdx, [rsp+4C0h+NameBuffer]; lpNameBuffer
0x18004f6be  lea     ecx, [rdi+1]; NameFormat
0x18004f6c1  call    cs:__imp_GetUserNameExW
0x18004f6c8  nop     dword ptr [rax+rax+00h]
0x18004f6cd  test    al, al
0x18004f6cf  jnz     short loc_18004F713
0x18004f6d1  call    cs:__imp_GetLastError
0x18004f6d8  nop     dword ptr [rax+rax+00h]
0x18004f6dd  mov     ebx, eax
0x18004f6df  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f6e6  lea     r14, WPP_GLOBAL_Control
0x18004f6ed  cmp     rcx, r14
0x18004f6f0  jz      loc_18004F872
0x18004f6f6  mov     rcx, [rcx+10h]
0x18004f6fa  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18004f701  mov     edx, 0A5h
0x18004f706  mov     r9d, eax
0x18004f709  call    WPP_SF_d
0x18004f70e  jmp     loc_18004F872
0x18004f713  lea     rdx, [rsp+4C0h+NameBuffer]
0x18004f718  mov     rcx, r14
0x18004f71b  call    cs:__imp__o__wcsicmp
0x18004f722  nop     dword ptr [rax+rax+00h]
0x18004f727  test    eax, eax
0x18004f729  jz      loc_18004F864
0x18004f72f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f736  lea     rax, WPP_GLOBAL_Control
0x18004f73d  cmp     rcx, rax
0x18004f740  jz      short loc_18004F764
0x18004f742  mov     rcx, [rcx+10h]
0x18004f746  lea     rax, [rsp+4C0h+NameBuffer]
0x18004f74b  mov     edx, 0A6h
0x18004f750  mov     [rsp+4C0h+var_4A0], rax
0x18004f755  mov     r9, r14
0x18004f758  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18004f75f  call    WPP_SF_SS
0x18004f764  mov     ebx, 8009030Ch
0x18004f769  jmp     loc_18004F86B
0x18004f76e  lea     r9, [rsp+4C0h+var_480]
0x18004f773  xor     r8d, r8d
0x18004f776  xor     edx, edx; dwFlags
0x18004f778  mov     rcx, rbx; pCertContext
0x18004f77b  call    FCertToStr
0x18004f780  mov     rsi, [rsp+4C0h+var_480]
0x18004f785  test    eax, eax
0x18004f787  jz      short loc_18004F805
0x18004f789  test    rsi, rsi
0x18004f78c  jz      short loc_18004F805
0x18004f78e  cmp     [rsi], r13w
0x18004f792  jz      short loc_18004F805
0x18004f794  lea     rdx, [rsp+4C0h+var_470]; unsigned __int16 **
0x18004f799  mov     rcx, r14; unsigned __int16 *
0x18004f79c  mov     edi, r13d
0x18004f79f  call    ?ExtractUserName@@YAJPEBGPEAPEAG@Z; ExtractUserName(ushort const *,ushort * *)
0x18004f7a4  lea     rdx, [rsp+4C0h+var_478]; unsigned __int16 **
0x18004f7a9  mov     rcx, rsi; unsigned __int16 *
0x18004f7ac  call    ?ExtractUserName@@YAJPEBGPEAPEAG@Z; ExtractUserName(ushort const *,ushort * *)
0x18004f7b1  mov     r12, [rsp+4C0h+var_478]
0x18004f7b6  mov     r15, [rsp+4C0h+var_470]
0x18004f7bb  mov     rdx, r12
0x18004f7be  mov     rcx, r15
0x18004f7c1  call    cs:__imp__o__wcsicmp
0x18004f7c8  nop     dword ptr [rax+rax+00h]
0x18004f7cd  test    eax, eax
0x18004f7cf  jz      loc_18004F864
0x18004f7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f7dc  lea     rax, WPP_GLOBAL_Control
0x18004f7e3  cmp     rcx, rax
0x18004f7e6  jz      short loc_18004F805
0x18004f7e8  mov     rcx, [rcx+10h]
0x18004f7ec  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18004f7f3  mov     edx, 0A7h
0x18004f7f8  mov     [rsp+4C0h+var_4A0], r12
0x18004f7fd  mov     r9, r15
0x18004f800  call    WPP_SF_SS
0x18004f805  mov     ebx, 8009030Ch
0x18004f80a  mov     rcx, rsi; hMem
0x18004f80d  call    cs:__imp_LocalFree
0x18004f814  nop     dword ptr [rax+rax+00h]
0x18004f819  mov     rcx, r15; hMem
0x18004f81c  call    cs:__imp_LocalFree
0x18004f823  nop     dword ptr [rax+rax+00h]
0x18004f828  mov     rcx, r12; hMem
0x18004f82b  call    cs:__imp_LocalFree
0x18004f832  nop     dword ptr [rax+rax+00h]
0x18004f837  mov     eax, ebx
0x18004f839  mov     rcx, [rbp+3C0h+var_40]
0x18004f840  xor     rcx, rsp; StackCookie
0x18004f843  call    __security_check_cookie
0x18004f848  mov     rbx, [rsp+4C0h+arg_18]
0x18004f850  add     rsp, 490h
0x18004f857  pop     r15
0x18004f859  pop     r14
0x18004f85b  pop     r13
0x18004f85d  pop     r12
0x18004f85f  pop     rdi
0x18004f860  pop     rsi
0x18004f861  pop     rbp
0x18004f862  retn
0x18004f864  mov     ebx, r13d
0x18004f867  test    edi, edi
0x18004f869  jz      short loc_18004F80A
0x18004f86b  lea     r14, WPP_GLOBAL_Control
0x18004f872  call    cs:__imp_RevertToSelf
0x18004f879  nop     dword ptr [rax+rax+00h]
0x18004f87e  test    eax, eax
0x18004f880  jnz     short loc_18004F8B6
0x18004f882  cmp     cs:WPP_GLOBAL_Control, r14
0x18004f889  jz      short loc_18004F8B6
0x18004f88b  call    cs:__imp_GetLastError
0x18004f892  nop     dword ptr [rax+rax+00h]
0x18004f897  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f89e  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18004f8a5  mov     edx, 0A8h
0x18004f8aa  mov     r9d, eax
0x18004f8ad  mov     rcx, [rcx+10h]
0x18004f8b1  call    WPP_SF_d
0x18004f8b6  test    edi, edi
0x18004f8b8  jz      loc_18004F80A
0x18004f8be  mov     rcx, [rsp+4C0h+Token]; hObject
0x18004f8c3  call    cs:__imp_CloseHandle
0x18004f8ca  nop     dword ptr [rax+rax+00h]
0x18004f8cf  jmp     loc_18004F80A
```
