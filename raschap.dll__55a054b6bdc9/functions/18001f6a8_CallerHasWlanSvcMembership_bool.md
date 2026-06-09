# CallerHasWlanSvcMembership(bool *)

- ea: `0x18001f6a8`
- end: `0x18001f89d`
- name: `?CallerHasWlanSvcMembership@@YAKPEA_N@Z`
- size: `501`
- prototype: `unsigned int __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006c60`

## callees

- `0x180003bd0`
- `0x18000ea70`
- `0x18001f6a8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001f7c7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001f7c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f878`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f86e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f86e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001f834`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001f834`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001f6d1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001f6d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f722`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f722`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f73a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f73a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f78b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f78b`

## pseudocode

```c
__int64 __fastcall CallerHasWlanSvcMembership(bool *a1)
{
  HRESULT v2; // eax
  DWORD v3; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  const char *v8; // r9
  HRESULT v9; // eax
  bool v10; // al
  WINBOOL IsMember; // [rsp+48h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+30h] BYREF
  PSID Sid; // [rsp+58h] [rbp+38h] BYREF

  TokenHandle = (void *)-1LL;
  Sid = 0;
  IsMember = 0;
  v2 = CoImpersonateClient();
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids,
        (unsigned int)v2);
    if ( (v3 & 0x1FFF0000) == 0x70000 )
      v3 = (unsigned __int16)v3;
    goto LABEL_24;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_24;
    v7 = 41;
    goto LABEL_9;
  }
  if ( !ConvertStringSidToSidW(L"S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142", &Sid) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_24;
    v7 = 42;
    goto LABEL_9;
  }
  if ( !CheckTokenMembership(TokenHandle, Sid, &IsMember) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_24;
    v7 = 43;
LABEL_9:
    WPP_SF_d(v6[2], v7, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v8 = "has";
    if ( !IsMember )
      v8 = "does not have";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v8);
  }
  v9 = CoRevertToSelf();
  if ( v9 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids,
      (unsigned int)v9);
  v3 = 0;
LABEL_24:
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  LocalFree(Sid);
  if ( v3 )
    v10 = 0;
  else
    v10 = IsMember != 0;
  *a1 = v10;
  return v3;
}

```

## disassembly

```asm
0x18001f6a8  mov     [rsp-18h+arg_0], rbx
0x18001f6ad  push    rbp
0x18001f6ae  push    rsi
0x18001f6af  push    rdi
0x18001f6b0  mov     rbp, rsp
0x18001f6b3  sub     rsp, 20h
0x18001f6b7  mov     rsi, rcx
0x18001f6ba  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001f6c2  mov     [rbp+Sid], 0
0x18001f6ca  mov     [rbp+IsMember], 0
0x18001f6d1  call    cs:__imp_CoImpersonateClient
0x18001f6d7  mov     ebx, eax
0x18001f6d9  test    eax, eax
0x18001f6db  jns     short loc_18001F722
0x18001f6dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6e4  lea     rdi, WPP_GLOBAL_Control
0x18001f6eb  cmp     rcx, rdi
0x18001f6ee  jz      short loc_18001F708
0x18001f6f0  mov     rcx, [rcx+10h]
0x18001f6f4  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18001f6fb  mov     edx, 28h ; '('
0x18001f700  mov     r9d, eax
0x18001f703  call    WPP_SF_d
0x18001f708  mov     eax, ebx
0x18001f70a  and     eax, 1FFF0000h
0x18001f70f  cmp     eax, 70000h
0x18001f714  jnz     loc_18001F864
0x18001f71a  movzx   ebx, bx
0x18001f71d  jmp     loc_18001F864
0x18001f722  call    cs:__imp_GetCurrentThread
0x18001f728  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001f72c  mov     edx, 0F01FFh; DesiredAccess
0x18001f731  mov     rcx, rax; ThreadHandle
0x18001f734  mov     r8d, 1; OpenAsSelf
0x18001f73a  call    cs:__imp_OpenThreadToken
0x18001f740  test    eax, eax
0x18001f742  jnz     short loc_18001F780
0x18001f744  call    cs:__imp_GetLastError
0x18001f74a  mov     ebx, eax
0x18001f74c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f753  lea     rdi, WPP_GLOBAL_Control
0x18001f75a  cmp     rcx, rdi
0x18001f75d  jz      loc_18001F864
0x18001f763  mov     edx, 29h ; ')'
0x18001f768  mov     rcx, [rcx+10h]
0x18001f76c  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18001f773  mov     r9d, eax
0x18001f776  call    WPP_SF_d
0x18001f77b  jmp     loc_18001F864
0x18001f780  lea     rdx, [rbp+Sid]; Sid
0x18001f784  lea     rcx, StringSid; "S-1-5-80-1428027539-3309602793-26783530"...
0x18001f78b  call    cs:__imp_ConvertStringSidToSidW
0x18001f791  test    eax, eax
0x18001f793  jnz     short loc_18001F7BB
0x18001f795  call    cs:__imp_GetLastError
0x18001f79b  mov     ebx, eax
0x18001f79d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7a4  lea     rdi, WPP_GLOBAL_Control
0x18001f7ab  cmp     rcx, rdi
0x18001f7ae  jz      loc_18001F864
0x18001f7b4  mov     edx, 2Ah ; '*'
0x18001f7b9  jmp     short loc_18001F768
0x18001f7bb  mov     rdx, [rbp+Sid]; SidToCheck
0x18001f7bf  lea     r8, [rbp+IsMember]; IsMember
0x18001f7c3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001f7c7  call    cs:__imp_CheckTokenMembership
0x18001f7cd  test    eax, eax
0x18001f7cf  jnz     short loc_18001F7F6
0x18001f7d1  call    cs:__imp_GetLastError
0x18001f7d7  mov     ebx, eax
0x18001f7d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7e0  lea     rdi, WPP_GLOBAL_Control
0x18001f7e7  cmp     rcx, rdi
0x18001f7ea  jz      short loc_18001F864
0x18001f7ec  mov     edx, 2Bh ; '+'
0x18001f7f1  jmp     loc_18001F768
0x18001f7f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7fd  lea     rdi, WPP_GLOBAL_Control
0x18001f804  cmp     rcx, rdi
0x18001f807  jz      short loc_18001F834
0x18001f809  cmp     [rbp+IsMember], 0
0x18001f80d  lea     rax, aDoesNotHave; "does not have"
0x18001f814  mov     rcx, [rcx+10h]
0x18001f818  lea     r9, aHas; "has"
0x18001f81f  cmovz   r9, rax
0x18001f823  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18001f82a  mov     edx, 2Ch ; ','
0x18001f82f  call    WPP_SF_s
0x18001f834  call    cs:__imp_CoRevertToSelf
0x18001f83a  test    eax, eax
0x18001f83c  jns     short loc_18001F862
0x18001f83e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f845  cmp     rcx, rdi
0x18001f848  jz      short loc_18001F862
0x18001f84a  mov     rcx, [rcx+10h]
0x18001f84e  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18001f855  mov     edx, 2Dh ; '-'
0x18001f85a  mov     r9d, eax
0x18001f85d  call    WPP_SF_d
0x18001f862  xor     ebx, ebx
0x18001f864  mov     rcx, [rbp+TokenHandle]; hObject
0x18001f868  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f86c  jz      short loc_18001F874
0x18001f86e  call    cs:__imp_CloseHandle
0x18001f874  mov     rcx, [rbp+Sid]; hMem
0x18001f878  call    cs:__imp_LocalFree
0x18001f87e  test    ebx, ebx
0x18001f880  jnz     short loc_18001F88A
0x18001f882  cmp     [rbp+IsMember], ebx
0x18001f885  setnz   al
0x18001f888  jmp     short loc_18001F88C
0x18001f88a  xor     al, al
0x18001f88c  mov     [rsi], al
0x18001f88e  mov     eax, ebx
0x18001f890  mov     rbx, [rsp+20h+arg_0]
0x18001f895  add     rsp, 20h
0x18001f899  pop     rdi
0x18001f89a  pop     rsi
0x18001f89b  pop     rbp
0x18001f89c  retn
```
