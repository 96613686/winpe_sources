# CallerHasWlanSvcMembership(bool *)

- ea: `0x180067eac`
- end: `0x1800680e4`
- name: `?CallerHasWlanSvcMembership@@YAKPEA_N@Z`
- size: `568`
- prototype: `unsigned int __fastcall(bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068c68`
- `0x180068e40`

## callees

- `0x180005010`
- `0x18001e0c0`
- `0x180067eac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067fff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067f4a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067f4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067f2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067f2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800680a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800680a8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180068068`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180068068`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180067ed5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180067ed5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800680b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800680b8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180067fef`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180067fef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180067fa7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180067fa7`

## pseudocode

```c
__int64 __fastcall CallerHasWlanSvcMembership(bool *a1)
{
  HRESULT v2; // eax
  DWORD v3; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v6; // rcx
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
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids,
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
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_24;
    v7 = 41;
    goto LABEL_9;
  }
  if ( !ConvertStringSidToSidW(L"S-1-5-80-1428027539-3309602793-2678353003-1498846795-3763184142", &Sid) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_24;
    v7 = 42;
    goto LABEL_9;
  }
  if ( !CheckTokenMembership(TokenHandle, Sid, &IsMember) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_24;
    v7 = 43;
LABEL_9:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v8 = "has";
    if ( !IsMember )
      v8 = "does not have";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v8);
  }
  v9 = CoRevertToSelf();
  if ( v9 < 0 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, (unsigned int)v9);
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
0x180067eac  mov     [rsp-18h+arg_0], rbx
0x180067eb1  push    rbp
0x180067eb2  push    rsi
0x180067eb3  push    rdi
0x180067eb4  mov     rbp, rsp
0x180067eb7  sub     rsp, 20h
0x180067ebb  mov     rsi, rcx
0x180067ebe  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180067ec6  mov     [rbp+Sid], 0
0x180067ece  mov     [rbp+IsMember], 0
0x180067ed5  call    cs:__imp_CoImpersonateClient
0x180067edc  nop     dword ptr [rax+rax+00h]
0x180067ee1  mov     ebx, eax
0x180067ee3  test    eax, eax
0x180067ee5  jns     short loc_180067F2C
0x180067ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180067eee  lea     rdi, WPP_GLOBAL_Control
0x180067ef5  cmp     rcx, rdi
0x180067ef8  jz      short loc_180067F12
0x180067efa  mov     rcx, [rcx+10h]
0x180067efe  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180067f05  mov     edx, 28h ; '('
0x180067f0a  mov     r9d, eax
0x180067f0d  call    WPP_SF_d
0x180067f12  mov     eax, ebx
0x180067f14  and     eax, 1FFF0000h
0x180067f19  cmp     eax, 70000h
0x180067f1e  jnz     loc_18006809E
0x180067f24  movzx   ebx, bx
0x180067f27  jmp     loc_18006809E
0x180067f2c  call    cs:__imp_GetCurrentThread
0x180067f33  nop     dword ptr [rax+rax+00h]
0x180067f38  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180067f3c  mov     edx, 0F01FFh; DesiredAccess
0x180067f41  mov     rcx, rax; ThreadHandle
0x180067f44  mov     r8d, 1; OpenAsSelf
0x180067f4a  call    cs:__imp_OpenThreadToken
0x180067f51  nop     dword ptr [rax+rax+00h]
0x180067f56  test    eax, eax
0x180067f58  jnz     short loc_180067F9C
0x180067f5a  call    cs:__imp_GetLastError
0x180067f61  nop     dword ptr [rax+rax+00h]
0x180067f66  mov     ebx, eax
0x180067f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180067f6f  lea     rdi, WPP_GLOBAL_Control
0x180067f76  cmp     rcx, rdi
0x180067f79  jz      loc_18006809E
0x180067f7f  mov     edx, 29h ; ')'
0x180067f84  mov     rcx, [rcx+10h]
0x180067f88  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180067f8f  mov     r9d, eax
0x180067f92  call    WPP_SF_d
0x180067f97  jmp     loc_18006809E
0x180067f9c  lea     rdx, [rbp+Sid]; Sid
0x180067fa0  lea     rcx, StringSid; "S-1-5-80-1428027539-3309602793-26783530"...
0x180067fa7  call    cs:__imp_ConvertStringSidToSidW
0x180067fae  nop     dword ptr [rax+rax+00h]
0x180067fb3  test    eax, eax
0x180067fb5  jnz     short loc_180067FE3
0x180067fb7  call    cs:__imp_GetLastError
0x180067fbe  nop     dword ptr [rax+rax+00h]
0x180067fc3  mov     ebx, eax
0x180067fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180067fcc  lea     rdi, WPP_GLOBAL_Control
0x180067fd3  cmp     rcx, rdi
0x180067fd6  jz      loc_18006809E
0x180067fdc  mov     edx, 2Ah ; '*'
0x180067fe1  jmp     short loc_180067F84
0x180067fe3  mov     rdx, [rbp+Sid]; SidToCheck
0x180067fe7  lea     r8, [rbp+IsMember]; IsMember
0x180067feb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180067fef  call    cs:__imp_CheckTokenMembership
0x180067ff6  nop     dword ptr [rax+rax+00h]
0x180067ffb  test    eax, eax
0x180067ffd  jnz     short loc_18006802A
0x180067fff  call    cs:__imp_GetLastError
0x180068006  nop     dword ptr [rax+rax+00h]
0x18006800b  mov     ebx, eax
0x18006800d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068014  lea     rdi, WPP_GLOBAL_Control
0x18006801b  cmp     rcx, rdi
0x18006801e  jz      short loc_18006809E
0x180068020  mov     edx, 2Bh ; '+'
0x180068025  jmp     loc_180067F84
0x18006802a  mov     rcx, cs:WPP_GLOBAL_Control
0x180068031  lea     rdi, WPP_GLOBAL_Control
0x180068038  cmp     rcx, rdi
0x18006803b  jz      short loc_180068068
0x18006803d  cmp     [rbp+IsMember], 0
0x180068041  lea     rax, aDoesNotHave; "does not have"
0x180068048  mov     rcx, [rcx+10h]
0x18006804c  lea     r9, aHas; "has"
0x180068053  cmovz   r9, rax
0x180068057  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18006805e  mov     edx, 2Ch ; ','
0x180068063  call    WPP_SF_s
0x180068068  call    cs:__imp_CoRevertToSelf
0x18006806f  nop     dword ptr [rax+rax+00h]
0x180068074  test    eax, eax
0x180068076  jns     short loc_18006809C
0x180068078  mov     rcx, cs:WPP_GLOBAL_Control
0x18006807f  cmp     rcx, rdi
0x180068082  jz      short loc_18006809C
0x180068084  mov     rcx, [rcx+10h]
0x180068088  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18006808f  mov     edx, 2Dh ; '-'
0x180068094  mov     r9d, eax
0x180068097  call    WPP_SF_d
0x18006809c  xor     ebx, ebx
0x18006809e  mov     rcx, [rbp+TokenHandle]; hObject
0x1800680a2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800680a6  jz      short loc_1800680B4
0x1800680a8  call    cs:__imp_CloseHandle
0x1800680af  nop     dword ptr [rax+rax+00h]
0x1800680b4  mov     rcx, [rbp+Sid]; hMem
0x1800680b8  call    cs:__imp_LocalFree
0x1800680bf  nop     dword ptr [rax+rax+00h]
0x1800680c4  test    ebx, ebx
0x1800680c6  jnz     short loc_1800680D0
0x1800680c8  cmp     [rbp+IsMember], ebx
0x1800680cb  setnz   al
0x1800680ce  jmp     short loc_1800680D2
0x1800680d0  xor     al, al
0x1800680d2  mov     [rsi], al
0x1800680d4  mov     eax, ebx
0x1800680d6  mov     rbx, [rsp+20h+arg_0]
0x1800680db  add     rsp, 20h
0x1800680df  pop     rdi
0x1800680e0  pop     rsi
0x1800680e1  pop     rbp
0x1800680e2  retn
```
