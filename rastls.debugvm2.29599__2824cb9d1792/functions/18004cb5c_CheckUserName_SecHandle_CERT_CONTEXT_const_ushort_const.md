# CheckUserName(_SecHandle,_CERT_CONTEXT const *,ushort const *)

- ea: `0x18004cb5c`
- end: `0x18004ce75`
- name: `?CheckUserName@@YAKU_SecHandle@@PEBU_CERT_CONTEXT@@PEBG@Z`
- size: `793`
- prototype: `unsigned int(struct _SecHandle *__struct_ptr, const struct _CERT_CONTEXT *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c178`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18002c710`
- `0x180035680`
- `0x18004cb5c`
- `0x18005a800`
- `0x18007539c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004ccf1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004cd91`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004ccf1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004cd91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cc54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ccad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cc54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ccad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ce38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ce6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ce6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cdd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cddc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cde5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cdd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cddc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cde5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004ce25`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004ce25`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004cc4a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004cc4a`
- `SspiCli!GetUserNameExW` at `0x18004cca3`
- `SspiCli!GetUserNameExW` at `0x18004cca3`
- `SspiCli!QuerySecurityContextToken` at `0x18004cc0c`
- `SspiCli!QuerySecurityContextToken` at `0x18004cc0c`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v7);
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
                (unsigned int)&WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
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
              &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
              LastError);
        }
        if ( !RevertToSelf() && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v12 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v12);
        }
      }
      else
      {
        v9 = GetLastError();
        v8 = v9;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v9);
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
0x18004cb5c  mov     [rsp-8+arg_18], rbx
0x18004cb61  push    rbp
0x18004cb62  push    rsi
0x18004cb63  push    rdi
0x18004cb64  push    r12
0x18004cb66  push    r13
0x18004cb68  push    r14
0x18004cb6a  push    r15
0x18004cb6c  lea     rbp, [rsp-390h]
0x18004cb74  sub     rsp, 490h
0x18004cb7b  mov     rax, cs:__security_cookie
0x18004cb82  xor     rax, rsp
0x18004cb85  mov     [rbp+3C0h+var_40], rax
0x18004cb8c  movups  xmm0, xmmword ptr [rcx]
0x18004cb8f  xor     r13d, r13d
0x18004cb92  mov     r14, r8
0x18004cb95  mov     rbx, rdx
0x18004cb98  mov     [rsp+4C0h+Token], r13
0x18004cb9d  movdqu  xmmword ptr [rsp+4C0h+phContext.dwLower], xmm0
0x18004cba3  mov     [rsp+4C0h+nSize], r13d
0x18004cba8  mov     esi, r13d
0x18004cbab  mov     [rsp+4C0h+var_480], r13
0x18004cbb0  mov     r15d, r13d
0x18004cbb3  mov     [rsp+4C0h+var_470], r13
0x18004cbb8  mov     r12d, r13d
0x18004cbbb  mov     [rsp+4C0h+var_478], r13
0x18004cbc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cbc7  lea     rdi, WPP_GLOBAL_Control
0x18004cbce  cmp     rcx, rdi
0x18004cbd1  jz      short loc_18004CBE8
0x18004cbd3  mov     rcx, [rcx+10h]
0x18004cbd7  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004cbde  mov     edx, 0A2h
0x18004cbe3  call    WPP_SF_
0x18004cbe8  cmp     cs:?g_eapTlsDisableADChecks@@3HA, r13d; int g_eapTlsDisableADChecks
0x18004cbef  jnz     loc_18004CD3E
0x18004cbf5  cmp     cs:?g_useCustomRootStore@@3_NA, r13b; bool g_useCustomRootStore
0x18004cbfc  jnz     loc_18004CD3E
0x18004cc02  lea     rdx, [rsp+4C0h+Token]; Token
0x18004cc07  lea     rcx, [rsp+4C0h+phContext]; phContext
0x18004cc0c  call    cs:__imp_QuerySecurityContextToken
0x18004cc12  mov     ebx, eax
0x18004cc14  test    eax, eax
0x18004cc16  jz      short loc_18004CC45
0x18004cc18  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc1f  cmp     rcx, rdi
0x18004cc22  jz      loc_18004CDD0
0x18004cc28  mov     rcx, [rcx+10h]
0x18004cc2c  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004cc33  mov     edx, 0A3h
0x18004cc38  mov     r9d, eax
0x18004cc3b  call    WPP_SF_d
0x18004cc40  jmp     loc_18004CDD0
0x18004cc45  mov     rcx, [rsp+4C0h+Token]; hToken
0x18004cc4a  call    cs:__imp_ImpersonateLoggedOnUser
0x18004cc50  test    eax, eax
0x18004cc52  jnz     short loc_18004CC89
0x18004cc54  call    cs:__imp_GetLastError
0x18004cc5a  mov     ebx, eax
0x18004cc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cc63  cmp     rcx, rdi
0x18004cc66  jz      loc_18004CE65
0x18004cc6c  mov     rcx, [rcx+10h]
0x18004cc70  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004cc77  mov     edx, 0A4h
0x18004cc7c  mov     r9d, eax
0x18004cc7f  call    WPP_SF_d
0x18004cc84  jmp     loc_18004CE65
0x18004cc89  mov     edi, 1
0x18004cc8e  mov     [rsp+4C0h+nSize], 202h
0x18004cc96  lea     r8, [rsp+4C0h+nSize]; nSize
0x18004cc9b  lea     rdx, [rsp+4C0h+NameBuffer]; lpNameBuffer
0x18004cca0  lea     ecx, [rdi+1]; NameFormat
0x18004cca3  call    cs:__imp_GetUserNameExW
0x18004cca9  test    al, al
0x18004ccab  jnz     short loc_18004CCE9
0x18004ccad  call    cs:__imp_GetLastError
0x18004ccb3  mov     ebx, eax
0x18004ccb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ccbc  lea     r14, WPP_GLOBAL_Control
0x18004ccc3  cmp     rcx, r14
0x18004ccc6  jz      loc_18004CE25
0x18004cccc  mov     rcx, [rcx+10h]
0x18004ccd0  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004ccd7  mov     edx, 0A5h
0x18004ccdc  mov     r9d, eax
0x18004ccdf  call    WPP_SF_d
0x18004cce4  jmp     loc_18004CE25
0x18004cce9  lea     rdx, [rsp+4C0h+NameBuffer]
0x18004ccee  mov     rcx, r14
0x18004ccf1  call    cs:__imp__o__wcsicmp
0x18004ccf7  test    eax, eax
0x18004ccf9  jz      loc_18004CE17
0x18004ccff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cd06  lea     rax, WPP_GLOBAL_Control
0x18004cd0d  cmp     rcx, rax
0x18004cd10  jz      short loc_18004CD34
0x18004cd12  mov     rcx, [rcx+10h]
0x18004cd16  lea     rax, [rsp+4C0h+NameBuffer]
0x18004cd1b  mov     edx, 0A6h
0x18004cd20  mov     [rsp+4C0h+var_4A0], rax
0x18004cd25  mov     r9, r14
0x18004cd28  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004cd2f  call    WPP_SF_SS
0x18004cd34  mov     ebx, 8009030Ch
0x18004cd39  jmp     loc_18004CE1E
0x18004cd3e  lea     r9, [rsp+4C0h+var_480]
0x18004cd43  xor     r8d, r8d
0x18004cd46  xor     edx, edx; dwFlags
0x18004cd48  mov     rcx, rbx; pCertContext
0x18004cd4b  call    FCertToStr
0x18004cd50  mov     rsi, [rsp+4C0h+var_480]
0x18004cd55  test    eax, eax
0x18004cd57  jz      short loc_18004CDCB
0x18004cd59  test    rsi, rsi
0x18004cd5c  jz      short loc_18004CDCB
0x18004cd5e  cmp     [rsi], r13w
0x18004cd62  jz      short loc_18004CDCB
0x18004cd64  lea     rdx, [rsp+4C0h+var_470]; unsigned __int16 **
0x18004cd69  mov     rcx, r14; unsigned __int16 *
0x18004cd6c  mov     edi, r13d
0x18004cd6f  call    ?ExtractUserName@@YAJPEBGPEAPEAG@Z; ExtractUserName(ushort const *,ushort * *)
0x18004cd74  lea     rdx, [rsp+4C0h+var_478]; unsigned __int16 **
0x18004cd79  mov     rcx, rsi; unsigned __int16 *
0x18004cd7c  call    ?ExtractUserName@@YAJPEBGPEAPEAG@Z; ExtractUserName(ushort const *,ushort * *)
0x18004cd81  mov     r12, [rsp+4C0h+var_478]
0x18004cd86  mov     r15, [rsp+4C0h+var_470]
0x18004cd8b  mov     rdx, r12
0x18004cd8e  mov     rcx, r15
0x18004cd91  call    cs:__imp__o__wcsicmp
0x18004cd97  test    eax, eax
0x18004cd99  jz      short loc_18004CE17
0x18004cd9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cda2  lea     rax, WPP_GLOBAL_Control
0x18004cda9  cmp     rcx, rax
0x18004cdac  jz      short loc_18004CDCB
0x18004cdae  mov     rcx, [rcx+10h]
0x18004cdb2  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004cdb9  mov     edx, 0A7h
0x18004cdbe  mov     [rsp+4C0h+var_4A0], r12
0x18004cdc3  mov     r9, r15
0x18004cdc6  call    WPP_SF_SS
0x18004cdcb  mov     ebx, 8009030Ch
0x18004cdd0  mov     rcx, rsi; hMem
0x18004cdd3  call    cs:__imp_LocalFree
0x18004cdd9  mov     rcx, r15; hMem
0x18004cddc  call    cs:__imp_LocalFree
0x18004cde2  mov     rcx, r12; hMem
0x18004cde5  call    cs:__imp_LocalFree
0x18004cdeb  mov     eax, ebx
0x18004cded  mov     rcx, [rbp+3C0h+var_40]
0x18004cdf4  xor     rcx, rsp; StackCookie
0x18004cdf7  call    __security_check_cookie
0x18004cdfc  mov     rbx, [rsp+4C0h+arg_18]
0x18004ce04  add     rsp, 490h
0x18004ce0b  pop     r15
0x18004ce0d  pop     r14
0x18004ce0f  pop     r13
0x18004ce11  pop     r12
0x18004ce13  pop     rdi
0x18004ce14  pop     rsi
0x18004ce15  pop     rbp
0x18004ce16  retn
0x18004ce17  mov     ebx, r13d
0x18004ce1a  test    edi, edi
0x18004ce1c  jz      short loc_18004CDD0
0x18004ce1e  lea     r14, WPP_GLOBAL_Control
0x18004ce25  call    cs:__imp_RevertToSelf
0x18004ce2b  test    eax, eax
0x18004ce2d  jnz     short loc_18004CE5D
0x18004ce2f  cmp     cs:WPP_GLOBAL_Control, r14
0x18004ce36  jz      short loc_18004CE5D
0x18004ce38  call    cs:__imp_GetLastError
0x18004ce3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ce45  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18004ce4c  mov     edx, 0A8h
0x18004ce51  mov     r9d, eax
0x18004ce54  mov     rcx, [rcx+10h]
0x18004ce58  call    WPP_SF_d
0x18004ce5d  test    edi, edi
0x18004ce5f  jz      loc_18004CDD0
0x18004ce65  mov     rcx, [rsp+4C0h+Token]; hObject
0x18004ce6a  call    cs:__imp_CloseHandle
0x18004ce70  jmp     loc_18004CDD0
```
