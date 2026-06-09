# UserTokenUtility::GetVirtualAccountTokenFromProcessToken(void *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x1800250fc`
- end: `0x180025309`
- name: `?GetVirtualAccountTokenFromProcessToken@UserTokenUtility@@SAJPEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000e7c0`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180007704`
- `0x180024bc4`
- `0x1800250fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002529e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002529e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025167`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025167`
- `SspiCli!LogonUserExExW` at `0x180025294`
- `SspiCli!LogonUserExExW` at `0x180025294`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800251b6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180025246`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800251b6`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180025246`

## pseudocode

```c
__int64 __fastcall UserTokenUtility::GetVirtualAccountTokenFromProcessToken(void *a1, __int64 a2)
{
  signed int LastError; // eax
  unsigned int v4; // esi
  PSID v5; // r15
  WCHAR **unique_for; // rax
  const struct std::nothrow_t *v7; // rdx
  WCHAR *v8; // rbx
  WCHAR **v9; // rax
  const struct std::nothrow_t *v10; // rdx
  WCHAR *v11; // rdi
  __int64 v12; // rax
  const struct std::nothrow_t *v13; // rdx
  signed int v14; // eax
  DWORD cchReferencedDomainName; // [rsp+60h] [rbp-59h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-55h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+68h] [rbp-51h] BYREF
  DWORD ReturnLength; // [rsp+6Ch] [rbp-4Dh] BYREF
  void *v20[2]; // [rsp+70h] [rbp-49h] BYREF
  PSID TokenInformation[12]; // [rsp+80h] [rbp-39h] BYREF

  ReturnLength = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  if ( !GetTokenInformation(a1, TokenUser, TokenInformation, 0x54u, &ReturnLength) )
  {
    LastError = GetLastError();
    v4 = LastError;
LABEL_5:
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v4;
  }
  v5 = TokenInformation[0];
  if ( LookupAccountSidW(0, TokenInformation[0], 0, &cchName, 0, &cchReferencedDomainName, &peUse) )
    return (unsigned int)-2147418113;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 122 )
    goto LABEL_5;
  unique_for = (WCHAR **)utl::make_unique_for_overwrite<wchar_t [0],0>(v20, cchName);
  v8 = *unique_for;
  *unique_for = 0;
  if ( v20[0] )
    operator delete(v20[0], v7);
  if ( v8 )
  {
    v9 = (WCHAR **)utl::make_unique_for_overwrite<wchar_t [0],0>(v20, cchReferencedDomainName);
    v11 = *v9;
    *v9 = 0;
    if ( v20[0] )
      operator delete(v20[0], v10);
    if ( v11 )
    {
      if ( !LookupAccountSidW(0, v5, v8, &cchName, v11, &cchReferencedDomainName, &peUse)
        || (v4 = 0,
            v12 = tlx::replace<tlx::file_handle_traits>(a2),
            !(unsigned int)LogonUserExExW(v8, v11, &unk_18004FE4C, 2, 4, 0, v12, 0, 0, 0, 0)) )
      {
        v14 = GetLastError();
        v4 = v14;
        if ( v14 > 0 )
          v4 = (unsigned __int16)v14 | 0x80070000;
      }
      operator delete(v11, v13);
    }
    else
    {
      v4 = -2147024882;
    }
    operator delete(v8, v10);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v4;
}

```

## disassembly

```asm
0x1800250fc  mov     [rsp-8+arg_10], rbx
0x180025101  mov     [rsp-8+arg_18], rsi
0x180025106  push    rbp
0x180025107  push    rdi
0x180025108  push    r12
0x18002510a  push    r14
0x18002510c  push    r15
0x18002510e  lea     rbp, [rsp-37h]
0x180025113  sub     rsp, 0F0h
0x18002511a  mov     rax, cs:__security_cookie
0x180025121  xor     rax, rsp
0x180025124  mov     [rbp+57h+var_30], rax
0x180025128  xor     r12d, r12d
0x18002512b  mov     r14, rdx
0x18002512e  mov     [rbp+57h+var_A4], r12d
0x180025132  mov     [rbp+57h+cchName], r12d
0x180025136  mov     [rbp+57h+var_B0], r12d
0x18002513a  mov     [rbp+57h+var_A8], r12d
0x18002513e  test    rcx, rcx
0x180025141  jz      loc_1800252DA
0x180025147  test    rdx, rdx
0x18002514a  jz      loc_1800252DA
0x180025150  lea     rax, [rbp+57h+var_A4]
0x180025154  lea     r9d, [r12+54h]; TokenInformationLength
0x180025159  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18002515e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180025162  lea     edx, [r12+1]; TokenInformationClass
0x180025167  call    cs:__imp_GetTokenInformation
0x18002516d  test    eax, eax
0x18002516f  jnz     short loc_18002518F
0x180025171  call    cs:__imp_GetLastError
0x180025177  mov     esi, eax
0x180025179  test    eax, eax
0x18002517b  jle     loc_1800252DF
0x180025181  movzx   esi, ax
0x180025184  or      esi, 80070000h
0x18002518a  jmp     loc_1800252DF
0x18002518f  mov     r15, [rbp+57h+TokenInformation]
0x180025193  lea     rax, [rbp+57h+var_A8]
0x180025197  mov     [rsp+110h+peUse], rax; peUse
0x18002519c  lea     r9, [rbp+57h+cchName]; cchName
0x1800251a0  lea     rax, [rbp+57h+var_B0]
0x1800251a4  xor     r8d, r8d; Name
0x1800251a7  mov     [rsp+110h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800251ac  mov     rdx, r15; Sid
0x1800251af  xor     ecx, ecx; lpSystemName
0x1800251b1  mov     [rsp+110h+ReturnLength], r12; ReferencedDomainName
0x1800251b6  call    cs:__imp_LookupAccountSidW
0x1800251bc  test    eax, eax
0x1800251be  jnz     loc_1800252D3
0x1800251c4  call    cs:__imp_GetLastError
0x1800251ca  mov     esi, eax
0x1800251cc  cmp     eax, 7Ah ; 'z'
0x1800251cf  jnz     short loc_180025179
0x1800251d1  mov     edx, [rbp+57h+cchName]
0x1800251d4  lea     rcx, [rbp+57h+var_A0]
0x1800251d8  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800251dd  mov     rbx, [rax]
0x1800251e0  mov     [rax], r12
0x1800251e3  mov     rcx, [rbp+57h+var_A0]; void *
0x1800251e7  test    rcx, rcx
0x1800251ea  jz      short loc_1800251F1
0x1800251ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800251f1  test    rbx, rbx
0x1800251f4  jz      loc_1800252CC
0x1800251fa  mov     edx, [rbp+57h+var_B0]
0x1800251fd  lea     rcx, [rbp+57h+var_A0]
0x180025201  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180025206  mov     rdi, [rax]
0x180025209  mov     [rax], r12
0x18002520c  mov     rcx, [rbp+57h+var_A0]; void *
0x180025210  test    rcx, rcx
0x180025213  jz      short loc_18002521A
0x180025215  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002521a  test    rdi, rdi
0x18002521d  jz      loc_1800252BD
0x180025223  lea     rax, [rbp+57h+var_A8]
0x180025227  mov     r8, rbx; Name
0x18002522a  mov     [rsp+110h+peUse], rax; peUse
0x18002522f  lea     r9, [rbp+57h+cchName]; cchName
0x180025233  lea     rax, [rbp+57h+var_B0]
0x180025237  mov     rdx, r15; Sid
0x18002523a  mov     [rsp+110h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002523f  xor     ecx, ecx; lpSystemName
0x180025241  mov     [rsp+110h+ReturnLength], rdi; ReferencedDomainName
0x180025246  call    cs:__imp_LookupAccountSidW
0x18002524c  test    eax, eax
0x18002524e  jz      short loc_18002529E
0x180025250  mov     rcx, r14
0x180025253  mov     esi, r12d
0x180025256  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18002525b  mov     [rsp+110h+var_C0], r12
0x180025260  lea     r8, unk_18004FE4C
0x180025267  mov     [rsp+110h+var_C8], r12
0x18002526c  mov     r9d, 2
0x180025272  mov     [rsp+110h+var_D0], r12
0x180025277  mov     rdx, rdi
0x18002527a  mov     [rsp+110h+var_D8], r12
0x18002527f  mov     rcx, rbx
0x180025282  mov     [rsp+110h+peUse], rax
0x180025287  mov     [rsp+110h+cchReferencedDomainName], r12
0x18002528c  mov     dword ptr [rsp+110h+ReturnLength], 4
0x180025294  call    cs:__imp_LogonUserExExW
0x18002529a  test    eax, eax
0x18002529c  jnz     short loc_1800252B3
0x18002529e  call    cs:__imp_GetLastError
0x1800252a4  mov     esi, eax
0x1800252a6  test    eax, eax
0x1800252a8  jle     short loc_1800252B3
0x1800252aa  movzx   esi, ax
0x1800252ad  or      esi, 80070000h
0x1800252b3  mov     rcx, rdi; void *
0x1800252b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800252bb  jmp     short loc_1800252C2
0x1800252bd  mov     esi, 8007000Eh
0x1800252c2  mov     rcx, rbx; void *
0x1800252c5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800252ca  jmp     short loc_1800252DF
0x1800252cc  mov     esi, 8007000Eh
0x1800252d1  jmp     short loc_1800252DF
0x1800252d3  mov     esi, 8000FFFFh
0x1800252d8  jmp     short loc_1800252DF
0x1800252da  mov     esi, 80070057h
0x1800252df  mov     eax, esi
0x1800252e1  mov     rcx, [rbp+57h+var_30]
0x1800252e5  xor     rcx, rsp; StackCookie
0x1800252e8  call    __security_check_cookie
0x1800252ed  lea     r11, [rsp+110h+var_20]
0x1800252f5  mov     rbx, [r11+40h]
0x1800252f9  mov     rsi, [r11+48h]
0x1800252fd  mov     rsp, r11
0x180025300  pop     r15
0x180025302  pop     r14
0x180025304  pop     r12
0x180025306  pop     rdi
0x180025307  pop     rbp
0x180025308  retn
```
