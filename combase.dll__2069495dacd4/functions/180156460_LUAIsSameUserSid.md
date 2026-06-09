# LUAIsSameUserSid

- ea: `0x180156460`
- end: `0x180156607`
- name: `LUAIsSameUserSid`
- size: `423`
- prototype: `int __fastcall(void *hTokenToCompare, void *hToken)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801374dc`

## callees

- `0x180156460`
- `0x180156610`
- `0x18018508c`
- `0x1801850d0`
- `0x180209550`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18015654e`
- `ntdll!NtQueryInformationToken` at `0x180156591`
- `ntdll!NtQueryInformationToken` at `0x18015654e`
- `ntdll!NtQueryInformationToken` at `0x180156591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801565c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801565c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015655b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015659e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801565d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801565e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015655b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015659e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801565d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801565e4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801564ec`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180156580`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801564ec`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180156580`

## pseudocode

```c
int __fastcall LUAIsSameUserSid(void *hTokenToCompare, void *hToken)
{
  _TOKEN_USER *v2; // rbx
  int result; // eax
  int v5; // r12d
  int v6; // r14d
  int v7; // esi
  int v8; // eax
  _TOKEN_USER *v9; // rdi
  void *v10; // rcx
  int v11; // eax
  _TOKEN_USER *user; // [rsp+30h] [rbp-20h] BYREF
  _TOKEN_USER *userToCompare; // [rsp+38h] [rbp-18h] BYREF
  _TOKEN_LINKED_TOKEN linkedToken; // [rsp+40h] [rbp-10h] BYREF
  __int64 isSplitToken; // [rsp+90h] [rbp+40h] BYREF
  int isElevatedToken; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int cbSize; // [rsp+A8h] [rbp+58h] BYREF

  HIDWORD(isSplitToken) = HIDWORD(hTokenToCompare);
  v2 = 0;
  isElevatedToken = 0;
  userToCompare = 0;
  linkedToken.LinkedToken = 0;
  cbSize = 0;
  LODWORD(isSplitToken) = 0;
  user = 0;
  result = Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline();
  if ( !result )
    return result;
  v5 = 0;
  v6 = 0;
  v7 = 1;
  if ( _LUAGetUserFromToken((void *)0xFFFFFFFFFFFFFFFCLL, &user) < 0 )
  {
    v9 = user;
    goto $CleanExit;
  }
  v8 = _LUAGetUserFromToken(hToken, &userToCompare);
  v2 = userToCompare;
  v9 = user;
  if ( v8 >= 0 )
  {
    if ( !EqualSid(user->User.Sid, userToCompare->User.Sid) )
    {
      if ( !LUAIsShadowAdminEnabled()
        || LUAIsElevatedToken(v10, &isElevatedToken, (int *)&isSplitToken) < 0
        || !(_DWORD)isSplitToken )
      {
        goto $CleanExit;
      }
      if ( isElevatedToken )
      {
        if ( NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenLinkedToken, &linkedToken, 8u, &cbSize) < 0 )
          goto $CleanExit;
        LocalFree(v9);
        user = 0;
        v11 = _LUAGetUserFromToken(linkedToken.LinkedToken, &user);
        v9 = user;
      }
      else
      {
        if ( NtQueryInformationToken(hToken, TokenLinkedToken, &linkedToken, 8u, &cbSize) < 0 )
          goto $CleanExit;
        LocalFree(v2);
        userToCompare = 0;
        v11 = _LUAGetUserFromToken(linkedToken.LinkedToken, &userToCompare);
        v2 = userToCompare;
      }
      if ( v11 >= 0 && EqualSid(v9->User.Sid, v2->User.Sid) )
        v6 = 1;
      goto $CleanExit;
    }
    v5 = 1;
  }
$CleanExit:
  if ( linkedToken.LinkedToken )
    CloseHandle(linkedToken.LinkedToken);
  if ( v9 )
    LocalFree(v9);
  if ( v2 )
    LocalFree(v2);
  if ( !v5 && !v6 )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x180156460  mov     [rsp-38h+isSplitToken], rcx
0x180156465  push    rbp
0x180156466  push    rbx
0x180156467  push    rsi
0x180156468  push    rdi
0x180156469  push    r12
0x18015646b  push    r14
0x18015646d  push    r15
0x18015646f  mov     rbp, rsp
0x180156472  sub     rsp, 50h
0x180156476  xor     ebx, ebx
0x180156478  mov     [rbp+isElevatedToken], 0
0x18015647f  mov     [rbp+userToCompare], rbx
0x180156483  mov     r15, hTokenToCompare
0x180156486  mov     [rbp+linkedToken.LinkedToken], rbx
0x18015648a  mov     [rbp+cbSize], ebx
0x18015648d  mov     dword ptr [rbp+isSplitToken], 0
0x180156494  mov     [rbp+user], 0
0x18015649c  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline; __annotation("WILSTG:|60288851|Feature_ShadowAdmin|DisabledByDefault")
0x1801564a1  test    eax, eax
0x1801564a3  jz      loc_1801565F8
0x1801564a9  xor     r12d, r12d
0x1801564ac  lea     hTokenToCompare, [rbp+user]; User
0x1801564b0  xor     r14d, r14d
0x1801564b3  lea     rcx, [r12-4]; Token
0x1801564b8  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x1801564bd  lea     esi, [r12+1]
0x1801564c2  test    eax, eax
0x1801564c4  js      loc_1801565BB
0x1801564ca  lea     hTokenToCompare, [rbp+userToCompare]; User
0x1801564ce  mov     rcx, r15; Token
0x1801564d1  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x1801564d6  mov     rbx, [rbp+userToCompare]
0x1801564da  mov     rdi, [rbp+user]
0x1801564de  test    eax, eax
0x1801564e0  js      $CleanExit
0x1801564e6  mov     hTokenToCompare, [rbx]; pSid2
0x1801564e9  mov     rcx, [rdi]; pSid1
0x1801564ec  call    cs:__imp_EqualSid
0x1801564f2  test    eax, eax
0x1801564f4  jz      short loc_1801564FE
0x1801564f6  mov     r12d, esi
0x1801564f9  jmp     $CleanExit
0x1801564fe  call    LUAIsShadowAdminEnabled
0x180156503  test    eax, eax
0x180156505  jz      $CleanExit
0x18015650b  lea     r8, [rbp+isSplitToken]; hToken
0x18015650f  lea     hTokenToCompare, [rbp+isElevatedToken]; pfSplitToken
0x180156513  call    LUAIsElevatedToken
0x180156518  test    eax, eax
0x18015651a  js      $CleanExit
0x180156520  cmp     dword ptr [rbp+isSplitToken], r12d
0x180156524  jz      $CleanExit
0x18015652a  lea     rax, [rbp+cbSize]
0x18015652e  mov     r9d, 8; TokenInformationLength
0x180156534  lea     r8, [rbp+linkedToken]; TokenInformation
0x180156538  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18015653d  lea     edx, [r9+0Bh]; TokenInformationClass
0x180156541  cmp     [rbp+isElevatedToken], r12d
0x180156545  jz      short loc_18015658E
0x180156547  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x18015654e  call    cs:__imp_NtQueryInformationToken
0x180156554  test    eax, eax
0x180156556  js      short $CleanExit
0x180156558  mov     rcx, rdi; hMem
0x18015655b  call    cs:__imp_LocalFree
0x180156561  mov     rcx, [rbp+linkedToken.LinkedToken]; Token
0x180156565  lea     hTokenToCompare, [rbp+user]; User
0x180156569  mov     [rbp+user], r12
0x18015656d  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x180156572  mov     rdi, [rbp+user]
0x180156576  test    eax, eax
0x180156578  js      short $CleanExit
0x18015657a  mov     hTokenToCompare, [rbx]; pSid2
0x18015657d  mov     rcx, [rdi]; pSid1
0x180156580  call    cs:__imp_EqualSid
0x180156586  test    eax, eax
0x180156588  cmovnz  r14d, esi
0x18015658c  jmp     short $CleanExit
0x18015658e  mov     rcx, r15; TokenHandle
0x180156591  call    cs:__imp_NtQueryInformationToken
0x180156597  test    eax, eax
0x180156599  js      short $CleanExit
0x18015659b  mov     rcx, rbx; hMem
0x18015659e  call    cs:__imp_LocalFree
0x1801565a4  mov     rcx, [rbp+linkedToken.LinkedToken]; Token
0x1801565a8  lea     hTokenToCompare, [rbp+userToCompare]; User
0x1801565ac  mov     [rbp+userToCompare], r12
0x1801565b0  call    ?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; _LUAGetUserFromToken(void *,_TOKEN_USER * *)
0x1801565b5  mov     rbx, [rbp+userToCompare]
0x1801565b9  jmp     short loc_180156576
0x1801565bb  mov     rdi, [rbp+user]
0x1801565bf  mov     rcx, [rbp+linkedToken.LinkedToken]; hObject
0x1801565c3  test    rcx, rcx
0x1801565c6  jz      short loc_1801565CE
0x1801565c8  call    cs:__imp_CloseHandle
0x1801565ce  test    rdi, rdi
0x1801565d1  jz      short loc_1801565DC
0x1801565d3  mov     rcx, rdi; hMem
0x1801565d6  call    cs:__imp_LocalFree
0x1801565dc  test    rbx, rbx
0x1801565df  jz      short loc_1801565EA
0x1801565e1  mov     rcx, rbx; hMem
0x1801565e4  call    cs:__imp_LocalFree
0x1801565ea  test    r12d, r12d
0x1801565ed  jnz     short loc_1801565F6
0x1801565ef  test    r14d, r14d
0x1801565f2  jnz     short loc_1801565F6
0x1801565f4  xor     esi, esi
0x1801565f6  mov     eax, esi
0x1801565f8  add     rsp, 50h
0x1801565fc  pop     r15
0x1801565fe  pop     r14
0x180156600  pop     r12
0x180156602  pop     rdi
0x180156603  pop     rsi
0x180156604  pop     rbx
0x180156605  pop     rbp
0x180156606  retn
```
