# EtwEventWrite_CredUI_Elevation(_CREDUI_CONTEXT const *,void *,void *,ulong)

- ea: `0x140019b34`
- end: `0x140019f37`
- name: `?EtwEventWrite_CredUI_Elevation@@YAXPEBU_CREDUI_CONTEXT@@PEAX1K@Z`
- size: `1027`
- prototype: `void __fastcall(const struct _CREDUI_CONTEXT *, void *, void *, DWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000cfdc`
- `0x140015d68`

## callees

- `0x14000a6cc`
- `0x14000de20`
- `0x14000e938`
- `0x140010080`
- `0x140010ad3`
- `0x140019a6c`
- `0x140019a8c`
- `0x140019b34`
- `0x140019fa8`
- `0x140019fbc`
- `0x14001cf48`
- `0x14001e050`

## import_xrefs

- `msvcrt!wcsrchr` at `0x140019c9f`
- `msvcrt!wcsrchr` at `0x140019d4c`
- `msvcrt!wcsrchr` at `0x140019c9f`
- `msvcrt!wcsrchr` at `0x140019d4c`
- `msvcrt!wcsnlen` at `0x140019cc3`
- `msvcrt!wcsnlen` at `0x140019dfe`
- `msvcrt!wcsnlen` at `0x140019cc3`
- `msvcrt!wcsnlen` at `0x140019dfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140019dbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140019dbc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140019e89`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140019e89`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140019c70`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140019d1e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140019c70`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140019d1e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140019cb5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140019d67`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140019d82`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140019cb5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140019d67`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140019d82`
- `SspiCli!GetUserNameExW` at `0x140019c8b`
- `SspiCli!GetUserNameExW` at `0x140019d39`
- `SspiCli!GetUserNameExW` at `0x140019c8b`
- `SspiCli!GetUserNameExW` at `0x140019d39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140019dd9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140019dd9`
- `ntdll!EtwEventWrite` at `0x140019ee9`
- `ntdll!EtwEventWrite` at `0x140019ee9`

## pseudocode

```c
void __fastcall EtwEventWrite_CredUI_Elevation(const struct _CREDUI_CONTEXT *a1, void *a2, void *a3, DWORD a4)
{
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  WCHAR *v14; // rbx
  wchar_t *v15; // rax
  int v16; // eax
  WCHAR *v17; // rbx
  wchar_t *v18; // rax
  int token_information; // eax
  PSID *v20; // rsi
  HLOCAL v21; // r14
  int v22; // eax
  __int64 v23; // rcx
  __int64 *v24; // rdx
  struct _TOKEN_LINKED_TOKEN *v25; // rdx
  DWORD dwMessageId; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hToken; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  ULONG nSize; // [rsp+68h] [rbp-98h] BYREF
  ULONG v32; // [rsp+6Ch] [rbp-94h] BYREF
  WCHAR Buffer[8]; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v34; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h]
  const wchar_t *v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  const wchar_t *v38; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  WCHAR *v40; // [rsp+B0h] [rbp-50h]
  int v41; // [rsp+B8h] [rbp-48h]
  int v42; // [rsp+BCh] [rbp-44h]
  WCHAR *v43; // [rsp+C0h] [rbp-40h]
  int v44; // [rsp+C8h] [rbp-38h]
  int v45; // [rsp+CCh] [rbp-34h]
  const wchar_t *v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h]
  DWORD *p_dwMessageId; // [rsp+E0h] [rbp-20h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  const wchar_t *v50; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]
  WCHAR NameBuffer[520]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Str[520]; // [rsp+510h] [rbp+410h] BYREF

  dwMessageId = a4;
  if ( !(unsigned int)LUAIsShadowAdminEnabled() )
    return;
  v27 = 0;
  if ( (int)SLGetWindowsInformationDWORD_noinline(v6, &v27) < 0 || v27 != 1 )
    return;
  v7 = *((_QWORD *)a1 + 2);
  v8 = -1;
  if ( v7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(v7 + 2 * v9) );
    v34 = (const wchar_t *)*((_QWORD *)a1 + 2);
    v35 = (unsigned int)(2 * v9 + 2);
  }
  else
  {
    v34 = L"(empty)";
    v35 = 16;
  }
  v10 = *((_QWORD *)a1 + 3);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v10 + 2 * v11) );
    v36 = (const wchar_t *)*((_QWORD *)a1 + 3);
    v37 = (unsigned int)(2 * v11 + 2);
  }
  else
  {
    v36 = L"(empty)";
    v37 = 16;
  }
  v12 = *((_QWORD *)a1 + 4);
  if ( v12 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(v12 + 2 * v13) );
    v38 = (const wchar_t *)*((_QWORD *)a1 + 4);
    v39 = (unsigned int)(2 * v13 + 2);
  }
  else
  {
    v38 = L"(empty)";
    v39 = 16;
  }
  memset_0(NameBuffer, 0, 0x404u);
  nSize = 514;
  v14 = (WCHAR *)L"(empty)";
  if ( !ImpersonateLoggedOnUser(a2) )
    goto LABEL_23;
  if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
  {
    v15 = wcsrchr(NameBuffer, 0x5Cu);
    if ( !v15 )
    {
      v14 = NameBuffer;
      RevertToSelf();
LABEL_23:
      v16 = wcsnlen(v14, 0x201u);
      goto LABEL_24;
    }
    v14 = v15 + 1;
  }
  RevertToSelf();
  if ( v14 )
    goto LABEL_23;
  v16 = 0;
LABEL_24:
  v40 = v14;
  v41 = 2 * v16 + 2;
  v42 = 0;
  hToken = 0;
  hMem = 0;
  memset_0(Str, 0, 0x404u);
  v32 = 514;
  v17 = (WCHAR *)L"(empty)";
  if ( (int)wil::get_token_information_nothrow(&hToken) < 0 )
    goto LABEL_42;
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    if ( GetUserNameExW(NameSamCompatible, Str, &v32) )
    {
      v18 = wcsrchr(Str, 0x5Cu);
      if ( v18 )
        v17 = v18 + 1;
      else
        v17 = Str;
    }
    RevertToSelf();
  }
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, (__int64)hToken);
  v20 = (PSID *)Block;
  if ( token_information >= 0 )
  {
    v21 = hMem;
    if ( hMem )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&Block);
      LocalFree(v21);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&Block);
    }
    hMem = 0;
    ConvertSidToStringSidW(*v20, (LPWSTR *)&hMem);
  }
  if ( v20 )
    operator delete(v20);
  if ( v17 )
LABEL_42:
    v22 = wcsnlen(v17, 0x201u);
  else
    v22 = 0;
  v43 = v17;
  v44 = 2 * v22 + 2;
  v45 = 0;
  if ( hMem )
  {
    v23 = -1;
    do
      ++v23;
    while ( *((_WORD *)hMem + v23) );
    v46 = (const wchar_t *)hMem;
    v47 = (unsigned int)(2 * v23 + 2);
  }
  else
  {
    v46 = L"(empty)";
    v47 = 16;
  }
  p_dwMessageId = &dwMessageId;
  v49 = 4;
  *(_QWORD *)Buffer = 0;
  FormatMessageW(0x1300u, 0, dwMessageId, 0x400u, Buffer, 0, 0);
  if ( *(_QWORD *)Buffer )
  {
    do
      ++v8;
    while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v8) );
    v50 = *(const wchar_t **)Buffer;
    v51 = (unsigned int)(2 * v8 + 2);
  }
  else
  {
    v50 = L"(empty)";
    v51 = 16;
  }
  v24 = CredUI_Elevation;
  if ( dwMessageId )
    v24 = CredUI_Elevation_Failure;
  EtwEventWrite(g_ConsentPerfRegHandle, v24, 8, &v34);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Buffer);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  wil::details::CloseTokenLinkedToken(&hToken, v25);
}

```

## disassembly

```asm
0x140019b34  mov     [rsp-8+arg_0], rbx
0x140019b39  push    rbp
0x140019b3a  push    rsi
0x140019b3b  push    rdi
0x140019b3c  push    r12
0x140019b3e  push    r13
0x140019b40  push    r14
0x140019b42  push    r15
0x140019b44  lea     rbp, [rsp-830h]
0x140019b4c  sub     rsp, 930h
0x140019b53  mov     rax, cs:__security_cookie
0x140019b5a  xor     rax, rsp
0x140019b5d  mov     [rbp+860h+var_40], rax
0x140019b64  mov     r14, r8
0x140019b67  mov     [rsp+960h+dwMessageId], r9d
0x140019b6c  mov     rsi, rdx
0x140019b6f  mov     rbx, rcx
0x140019b72  call    LUAIsShadowAdminEnabled
0x140019b77  xor     r15d, r15d
0x140019b7a  test    eax, eax
0x140019b7c  jz      loc_140019F0D
0x140019b82  lea     rdx, [rsp+960h+var_918]; unsigned int *
0x140019b87  mov     [rsp+960h+var_918], r15d
0x140019b8c  call    ?SLGetWindowsInformationDWORD_noinline@@YAJPEBGPEAK@Z; SLGetWindowsInformationDWORD_noinline(ushort const *,ulong *)
0x140019b91  test    eax, eax
0x140019b93  js      loc_140019F0D
0x140019b99  cmp     [rsp+960h+var_918], 1
0x140019b9e  jnz     loc_140019F0D
0x140019ba4  mov     rcx, [rbx+10h]
0x140019ba8  lea     r12, Source; "(empty)"
0x140019baf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140019bb3  test    rcx, rcx
0x140019bb6  jz      short loc_140019BD9
0x140019bb8  mov     rax, rdi
0x140019bbb  inc     rax
0x140019bbe  cmp     [rcx+rax*2], r15w
0x140019bc3  jnz     short loc_140019BBB
0x140019bc5  lea     eax, ds:2[rax*2]
0x140019bcc  mov     [rbp+860h+var_8E0], rcx
0x140019bd0  mov     dword ptr [rbp+860h+var_8D8], eax
0x140019bd3  mov     dword ptr [rbp+860h+var_8D8+4], r15d
0x140019bd7  jmp     short loc_140019BE5
0x140019bd9  mov     [rbp+860h+var_8E0], r12
0x140019bdd  mov     [rbp+860h+var_8D8], 10h
0x140019be5  mov     rcx, [rbx+18h]
0x140019be9  test    rcx, rcx
0x140019bec  jz      short loc_140019C0F
0x140019bee  mov     rax, rdi
0x140019bf1  inc     rax
0x140019bf4  cmp     [rcx+rax*2], r15w
0x140019bf9  jnz     short loc_140019BF1
0x140019bfb  lea     eax, ds:2[rax*2]
0x140019c02  mov     [rbp+860h+var_8D0], rcx
0x140019c06  mov     dword ptr [rbp+860h+var_8C8], eax
0x140019c09  mov     dword ptr [rbp+860h+var_8C8+4], r15d
0x140019c0d  jmp     short loc_140019C1B
0x140019c0f  mov     [rbp+860h+var_8D0], r12
0x140019c13  mov     [rbp+860h+var_8C8], 10h
0x140019c1b  mov     rcx, [rbx+20h]
0x140019c1f  test    rcx, rcx
0x140019c22  jz      short loc_140019C45
0x140019c24  mov     rax, rdi
0x140019c27  inc     rax
0x140019c2a  cmp     [rcx+rax*2], r15w
0x140019c2f  jnz     short loc_140019C27
0x140019c31  lea     eax, ds:2[rax*2]
0x140019c38  mov     [rbp+860h+var_8C0], rcx
0x140019c3c  mov     dword ptr [rbp+860h+var_8B8], eax
0x140019c3f  mov     dword ptr [rbp+860h+var_8B8+4], r15d
0x140019c43  jmp     short loc_140019C51
0x140019c45  mov     [rbp+860h+var_8C0], r12
0x140019c49  mov     [rbp+860h+var_8B8], 10h
0x140019c51  xor     edx, edx; Val
0x140019c53  lea     rcx, [rbp+860h+NameBuffer]; void *
0x140019c57  mov     r8d, 404h; Size
0x140019c5d  call    memset_0
0x140019c62  mov     rcx, rsi; hToken
0x140019c65  mov     [rsp+960h+nSize], 202h
0x140019c6d  mov     rbx, r12
0x140019c70  call    cs:__imp_ImpersonateLoggedOnUser
0x140019c76  mov     esi, 5Ch ; '\'
0x140019c7b  test    eax, eax
0x140019c7d  jz      short loc_140019CBB
0x140019c7f  lea     r8, [rsp+960h+nSize]; nSize
0x140019c84  lea     rdx, [rbp+860h+NameBuffer]; lpNameBuffer
0x140019c88  lea     ecx, [rsi-5Ah]; NameFormat
0x140019c8b  call    cs:__imp_GetUserNameExW
0x140019c91  test    al, al
0x140019c93  jz      loc_140019D67
0x140019c99  mov     edx, esi; Ch
0x140019c9b  lea     rcx, [rbp+860h+NameBuffer]; Str
0x140019c9f  call    cs:__imp_wcsrchr
0x140019ca5  mov     rbx, rax
0x140019ca8  test    rax, rax
0x140019cab  jnz     loc_140019D63
0x140019cb1  lea     rbx, [rbp+860h+NameBuffer]
0x140019cb5  call    cs:__imp_RevertToSelf
0x140019cbb  mov     edx, 201h; MaxCount
0x140019cc0  mov     rcx, rbx; Source
0x140019cc3  call    cs:__imp_wcsnlen
0x140019cc9  lea     eax, ds:2[rax*2]
0x140019cd0  mov     [rbp+860h+var_8B0], rbx
0x140019cd4  xor     edx, edx; Val
0x140019cd6  mov     [rbp+860h+var_8A8], eax
0x140019cd9  mov     r8d, 404h; Size
0x140019cdf  mov     [rbp+860h+var_8A4], r15d
0x140019ce3  lea     rcx, [rbp+860h+Str]; void *
0x140019cea  mov     [rsp+960h+hToken], r15
0x140019cef  mov     [rsp+960h+hMem], r15
0x140019cf4  call    memset_0
0x140019cf9  mov     rdx, r14
0x140019cfc  mov     [rsp+960h+var_8F4], 202h
0x140019d04  lea     rcx, [rsp+960h+hToken]; TokenInformation
0x140019d09  mov     rbx, r12
0x140019d0c  call    ?get_token_information_nothrow@wil@@YAJAEAV?$unique_struct@U_TOKEN_LINKED_TOKEN@@P6AXPEAU1@@_E$1?CloseTokenLinkedToken@details@wil@@YAX0@Z$$T$0A@@1@PEAX@Z
0x140019d11  test    eax, eax
0x140019d13  js      loc_140019DF6
0x140019d19  mov     rcx, [rsp+960h+hToken]; hToken
0x140019d1e  call    cs:__imp_ImpersonateLoggedOnUser
0x140019d24  test    eax, eax
0x140019d26  jz      short loc_140019D88
0x140019d28  lea     r8, [rsp+960h+var_8F4]; nSize
0x140019d2d  mov     ecx, 2; NameFormat
0x140019d32  lea     rdx, [rbp+860h+Str]; lpNameBuffer
0x140019d39  call    cs:__imp_GetUserNameExW
0x140019d3f  test    al, al
0x140019d41  jz      short loc_140019D82
0x140019d43  mov     edx, esi; Ch
0x140019d45  lea     rcx, [rbp+860h+Str]; Str
0x140019d4c  call    cs:__imp_wcsrchr
0x140019d52  mov     rbx, rax
0x140019d55  test    rax, rax
0x140019d58  jnz     short loc_140019D7E
0x140019d5a  lea     rbx, [rbp+860h+Str]
0x140019d61  jmp     short loc_140019D82
0x140019d63  add     rbx, 2
0x140019d67  call    cs:__imp_RevertToSelf
0x140019d6d  test    rbx, rbx
0x140019d70  jnz     loc_140019CBB
0x140019d76  mov     rax, r15
0x140019d79  jmp     loc_140019CC9
0x140019d7e  add     rbx, 2
0x140019d82  call    cs:__imp_RevertToSelf
0x140019d88  mov     rdx, [rsp+960h+hToken]
0x140019d8d  lea     rcx, [rsp+960h+Block]
0x140019d92  mov     [rsp+960h+Block], r15
0x140019d97  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x140019d9c  mov     rsi, [rsp+960h+Block]
0x140019da1  test    eax, eax
0x140019da3  js      short loc_140019DDF
0x140019da5  mov     r14, [rsp+960h+hMem]
0x140019daa  test    r14, r14
0x140019dad  jz      short loc_140019DCC
0x140019daf  lea     rcx, [rsp+960h+Block]; this
0x140019db4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140019db9  mov     rcx, r14; hMem
0x140019dbc  call    cs:__imp_LocalFree
0x140019dc2  lea     rcx, [rsp+960h+Block]; this
0x140019dc7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140019dcc  mov     [rsp+960h+hMem], r15
0x140019dd1  lea     rdx, [rsp+960h+hMem]; StringSid
0x140019dd6  mov     rcx, [rsi]; Sid
0x140019dd9  call    cs:__imp_ConvertSidToStringSidW
0x140019ddf  test    rsi, rsi
0x140019de2  jz      short loc_140019DEC
0x140019de4  mov     rcx, rsi; Block
0x140019de7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140019dec  test    rbx, rbx
0x140019def  jnz     short loc_140019DF6
0x140019df1  mov     rax, r15
0x140019df4  jmp     short loc_140019E04
0x140019df6  mov     edx, 201h; MaxCount
0x140019dfb  mov     rcx, rbx; Source
0x140019dfe  call    cs:__imp_wcsnlen
0x140019e04  lea     eax, ds:2[rax*2]
0x140019e0b  mov     [rbp+860h+var_8A0], rbx
0x140019e0f  mov     [rbp+860h+var_898], eax
0x140019e12  mov     rax, [rsp+960h+hMem]
0x140019e17  mov     [rbp+860h+var_894], r15d
0x140019e1b  test    rax, rax
0x140019e1e  jz      short loc_140019E41
0x140019e20  mov     rcx, rdi
0x140019e23  inc     rcx
0x140019e26  cmp     [rax+rcx*2], r15w
0x140019e2b  jnz     short loc_140019E23
0x140019e2d  mov     [rbp+860h+var_890], rax
0x140019e31  lea     eax, ds:2[rcx*2]
0x140019e38  mov     dword ptr [rbp+860h+var_888], eax
0x140019e3b  mov     dword ptr [rbp+860h+var_888+4], r15d
0x140019e3f  jmp     short loc_140019E4D
0x140019e41  mov     [rbp+860h+var_890], r12
0x140019e45  mov     [rbp+860h+var_888], 10h
0x140019e4d  mov     r8d, [rsp+960h+dwMessageId]; dwMessageId
0x140019e52  lea     rax, [rsp+960h+dwMessageId]
0x140019e57  mov     [rbp+860h+var_880], rax
0x140019e5b  mov     r9d, 400h; dwLanguageId
0x140019e61  lea     rax, [rsp+960h+Buffer]
0x140019e66  mov     [rsp+960h+Arguments], r15; Arguments
0x140019e6b  mov     [rsp+960h+var_938], r15d; nSize
0x140019e70  xor     edx, edx; lpSource
0x140019e72  mov     ecx, 1300h; dwFlags
0x140019e77  mov     [rsp+960h+lpBuffer], rax; lpBuffer
0x140019e7c  mov     [rbp+860h+var_878], 4
0x140019e84  mov     qword ptr [rsp+960h+Buffer], r15
0x140019e89  call    cs:__imp_FormatMessageW
0x140019e8f  mov     rax, qword ptr [rsp+960h+Buffer]
0x140019e94  test    rax, rax
0x140019e97  jz      short loc_140019EB7
0x140019e99  inc     rdi
0x140019e9c  cmp     [rax+rdi*2], r15w
0x140019ea1  jnz     short loc_140019E99
0x140019ea3  mov     [rbp+860h+var_870], rax
0x140019ea7  lea     eax, ds:2[rdi*2]
0x140019eae  mov     dword ptr [rbp+860h+var_868], eax
0x140019eb1  mov     dword ptr [rbp+860h+var_868+4], r15d
0x140019eb5  jmp     short loc_140019EC3
0x140019eb7  mov     [rbp+860h+var_870], r12
0x140019ebb  mov     [rbp+860h+var_868], 10h
0x140019ec3  lea     r9, [rbp+860h+var_8E0]
0x140019ec7  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x140019ece  lea     rdx, CredUI_Elevation
0x140019ed5  mov     r8d, 8
0x140019edb  cmp     [rsp+960h+dwMessageId], r15d
0x140019ee0  jz      short loc_140019EE9
0x140019ee2  lea     rdx, CredUI_Elevation_Failure
0x140019ee9  call    cs:__imp_EtwEventWrite
0x140019eef  lea     rcx, [rsp+960h+Buffer]
0x140019ef4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140019ef9  lea     rcx, [rsp+960h+hMem]
0x140019efe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140019f03  lea     rcx, [rsp+960h+hToken]; this
0x140019f08  call    ?CloseTokenLinkedToken@details@wil@@YAXPEAU_TOKEN_LINKED_TOKEN@@@Z; wil::details::CloseTokenLinkedToken(_TOKEN_LINKED_TOKEN *)
0x140019f0d  mov     rcx, [rbp+860h+var_40]
0x140019f14  xor     rcx, rsp; StackCookie
0x140019f17  call    __security_check_cookie
0x140019f1c  mov     rbx, [rsp+960h+arg_0]
0x140019f24  add     rsp, 930h
0x140019f2b  pop     r15
0x140019f2d  pop     r14
0x140019f2f  pop     r13
0x140019f31  pop     r12
0x140019f33  pop     rdi
0x140019f34  pop     rsi
0x140019f35  pop     rbp
0x140019f36  retn
```
