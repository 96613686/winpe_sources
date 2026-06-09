# CallerHasWlanSvcMembership(bool *)

- ea: `0x180064404`
- end: `0x1800645f9`
- name: `?CallerHasWlanSvcMembership@@YAKPEA_N@Z`
- size: `501`
- prototype: `unsigned int __fastcall(bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800650c0`
- `0x180065294`

## callees

- `0x180004bd0`
- `0x18001c680`
- `0x180064404`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800644a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800644f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006452d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800644a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800644f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006452d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064496`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180064496`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006447e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006447e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800645ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800645ca`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180064590`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180064590`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006442d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18006442d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800645d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800645d4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180064523`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180064523`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800644e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800644e7`

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
0x180064404  mov     [rsp-18h+arg_0], rbx
0x180064409  push    rbp
0x18006440a  push    rsi
0x18006440b  push    rdi
0x18006440c  mov     rbp, rsp
0x18006440f  sub     rsp, 20h
0x180064413  mov     rsi, rcx
0x180064416  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18006441e  mov     [rbp+Sid], 0
0x180064426  mov     [rbp+IsMember], 0
0x18006442d  call    cs:__imp_CoImpersonateClient
0x180064433  mov     ebx, eax
0x180064435  test    eax, eax
0x180064437  jns     short loc_18006447E
0x180064439  mov     rcx, cs:WPP_GLOBAL_Control
0x180064440  lea     rdi, WPP_GLOBAL_Control
0x180064447  cmp     rcx, rdi
0x18006444a  jz      short loc_180064464
0x18006444c  mov     rcx, [rcx+10h]
0x180064450  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180064457  mov     edx, 28h ; '('
0x18006445c  mov     r9d, eax
0x18006445f  call    WPP_SF_d
0x180064464  mov     eax, ebx
0x180064466  and     eax, 1FFF0000h
0x18006446b  cmp     eax, 70000h
0x180064470  jnz     loc_1800645C0
0x180064476  movzx   ebx, bx
0x180064479  jmp     loc_1800645C0
0x18006447e  call    cs:__imp_GetCurrentThread
0x180064484  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180064488  mov     edx, 0F01FFh; DesiredAccess
0x18006448d  mov     rcx, rax; ThreadHandle
0x180064490  mov     r8d, 1; OpenAsSelf
0x180064496  call    cs:__imp_OpenThreadToken
0x18006449c  test    eax, eax
0x18006449e  jnz     short loc_1800644DC
0x1800644a0  call    cs:__imp_GetLastError
0x1800644a6  mov     ebx, eax
0x1800644a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800644af  lea     rdi, WPP_GLOBAL_Control
0x1800644b6  cmp     rcx, rdi
0x1800644b9  jz      loc_1800645C0
0x1800644bf  mov     edx, 29h ; ')'
0x1800644c4  mov     rcx, [rcx+10h]
0x1800644c8  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800644cf  mov     r9d, eax
0x1800644d2  call    WPP_SF_d
0x1800644d7  jmp     loc_1800645C0
0x1800644dc  lea     rdx, [rbp+Sid]; Sid
0x1800644e0  lea     rcx, StringSid; "S-1-5-80-1428027539-3309602793-26783530"...
0x1800644e7  call    cs:__imp_ConvertStringSidToSidW
0x1800644ed  test    eax, eax
0x1800644ef  jnz     short loc_180064517
0x1800644f1  call    cs:__imp_GetLastError
0x1800644f7  mov     ebx, eax
0x1800644f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180064500  lea     rdi, WPP_GLOBAL_Control
0x180064507  cmp     rcx, rdi
0x18006450a  jz      loc_1800645C0
0x180064510  mov     edx, 2Ah ; '*'
0x180064515  jmp     short loc_1800644C4
0x180064517  mov     rdx, [rbp+Sid]; SidToCheck
0x18006451b  lea     r8, [rbp+IsMember]; IsMember
0x18006451f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180064523  call    cs:__imp_CheckTokenMembership
0x180064529  test    eax, eax
0x18006452b  jnz     short loc_180064552
0x18006452d  call    cs:__imp_GetLastError
0x180064533  mov     ebx, eax
0x180064535  mov     rcx, cs:WPP_GLOBAL_Control
0x18006453c  lea     rdi, WPP_GLOBAL_Control
0x180064543  cmp     rcx, rdi
0x180064546  jz      short loc_1800645C0
0x180064548  mov     edx, 2Bh ; '+'
0x18006454d  jmp     loc_1800644C4
0x180064552  mov     rcx, cs:WPP_GLOBAL_Control
0x180064559  lea     rdi, WPP_GLOBAL_Control
0x180064560  cmp     rcx, rdi
0x180064563  jz      short loc_180064590
0x180064565  cmp     [rbp+IsMember], 0
0x180064569  lea     rax, aDoesNotHave; "does not have"
0x180064570  mov     rcx, [rcx+10h]
0x180064574  lea     r9, aHas; "has"
0x18006457b  cmovz   r9, rax
0x18006457f  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180064586  mov     edx, 2Ch ; ','
0x18006458b  call    WPP_SF_s
0x180064590  call    cs:__imp_CoRevertToSelf
0x180064596  test    eax, eax
0x180064598  jns     short loc_1800645BE
0x18006459a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800645a1  cmp     rcx, rdi
0x1800645a4  jz      short loc_1800645BE
0x1800645a6  mov     rcx, [rcx+10h]
0x1800645aa  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800645b1  mov     edx, 2Dh ; '-'
0x1800645b6  mov     r9d, eax
0x1800645b9  call    WPP_SF_d
0x1800645be  xor     ebx, ebx
0x1800645c0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800645c4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800645c8  jz      short loc_1800645D0
0x1800645ca  call    cs:__imp_CloseHandle
0x1800645d0  mov     rcx, [rbp+Sid]; hMem
0x1800645d4  call    cs:__imp_LocalFree
0x1800645da  test    ebx, ebx
0x1800645dc  jnz     short loc_1800645E6
0x1800645de  cmp     [rbp+IsMember], ebx
0x1800645e1  setnz   al
0x1800645e4  jmp     short loc_1800645E8
0x1800645e6  xor     al, al
0x1800645e8  mov     [rsi], al
0x1800645ea  mov     eax, ebx
0x1800645ec  mov     rbx, [rsp+20h+arg_0]
0x1800645f1  add     rsp, 20h
0x1800645f5  pop     rdi
0x1800645f6  pop     rsi
0x1800645f7  pop     rbp
0x1800645f8  retn
```
