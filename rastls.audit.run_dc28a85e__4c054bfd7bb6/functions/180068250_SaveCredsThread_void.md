# SaveCredsThread(void *)

- ea: `0x180068250`
- end: `0x180068533`
- name: `?SaveCredsThread@@YAKPEAX@Z`
- size: `739`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18001e0c0`
- `0x18002f324`
- `0x180038270`
- `0x180038e64`
- `0x180060158`
- `0x1800681a8`
- `0x180068250`
- `0x18007c99c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18006835d`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180068379`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18006835d`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180068379`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x180068396`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x180068396`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006842e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006842e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068471`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800684ca`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800684ca`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180068411`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180068411`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x180068461`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x180068461`

## pseudocode

```c
__int64 __fastcall SaveCredsThread(PVOID Parameter)
{
  DWORD v2; // edi
  char v3; // r14
  __int64 v4; // rdx
  struct _EAPTLS_CONTROL_BLOCK *v5; // rcx
  int IsJoined; // eax
  struct _EAPTLS_CONTROL_BLOCK *v7; // rcx
  __int64 v8; // rdx
  char v9; // si
  void *v10; // rcx
  DWORD LastError; // eax
  DWORD v12; // eax
  _DWORD v14[4]; // [rsp+30h] [rbp-D0h] BYREF
  _CREDENTIALA Credential; // [rsp+40h] [rbp-C0h] BYREF
  char Destination[528]; // [rsp+90h] [rbp-70h] BYREF

  v2 = 0;
  v3 = 0;
  memset_0(Destination, 0, 0x202u);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
  v14[0] = 0;
  IsJoined = DeviceRegistrationStateApi::IsJoined(v5, v4, v14);
  if ( IsJoined >= 0 )
  {
    if ( v14[0] )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_29;
      v8 = 51;
      goto LABEL_11;
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DsrIsDeviceJoinedEx",
      L"DeviceRegistrationStateApi::IsJoined",
      (unsigned int)IsJoined);
  }
  if ( (unsigned int)isMachineJoinedToDomain() )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    v8 = 52;
LABEL_11:
    WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
    goto LABEL_29;
  }
  v9 = 0;
  if ( *(_QWORD *)Parameter && **(_BYTE **)Parameter )
  {
    _o_strcat_s(Destination, 514);
    _o_strcat_s(Destination, 514);
  }
  strncat_s(Destination, 0x202u, *((const char **)Parameter + 1), 0xFFFFFFFFFFFFFFFFuLL);
  memset_0(&Credential, 0, sizeof(Credential));
  Credential.Type = 2;
  Credential.TargetName = "*Session";
  Credential.UserName = Destination;
  Credential.Persist = 1;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, Destination);
  v10 = (void *)*((_QWORD *)Parameter + 4);
  Credential.CredentialBlob = (LPBYTE)*((_QWORD *)Parameter + 2);
  Credential.CredentialBlobSize = *((_DWORD *)Parameter + 6);
  if ( v10 != (void *)-1LL )
  {
    if ( !ImpersonateLoggedOnUser(v10) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
      }
      goto LABEL_29;
    }
    v9 = 1;
  }
  if ( CredWriteA(&Credential, 0) )
  {
    v3 = 1;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids,
        Credential.UserName);
  }
  else
  {
    v12 = GetLastError();
    v2 = v12;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v12);
  }
  if ( v9 )
    RevertToSelf();
LABEL_29:
  FreeEapCredStructure(Parameter);
  byte_1800ABFB0 = v3;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180068250  mov     [rsp-8+arg_8], rbx
0x180068255  mov     [rsp-8+arg_10], rsi
0x18006825a  push    rbp
0x18006825b  push    rdi
0x18006825c  push    r12
0x18006825e  push    r13
0x180068260  push    r14
0x180068262  lea     rbp, [rsp-1B0h]
0x18006826a  sub     rsp, 2B0h
0x180068271  mov     rax, cs:__security_cookie
0x180068278  xor     rax, rsp
0x18006827b  mov     [rbp+1D0h+var_30], rax
0x180068282  mov     rbx, rcx
0x180068285  xor     edi, edi
0x180068287  lea     rcx, [rbp+1D0h+Destination]; void *
0x18006828b  xor     r14b, r14b
0x18006828e  xor     edx, edx; Val
0x180068290  mov     r8d, 202h; Size
0x180068296  call    memset_0
0x18006829b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800682a2  lea     r12, WPP_GLOBAL_Control
0x1800682a9  lea     r13, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800682b0  cmp     rcx, r12
0x1800682b3  jz      short loc_1800682C4
0x1800682b5  mov     rcx, [rcx+10h]
0x1800682b9  lea     edx, [rdi+32h]
0x1800682bc  mov     r8, r13
0x1800682bf  call    WPP_SF_
0x1800682c4  lea     r8, [rsp+2D0h+var_2A0]
0x1800682c9  mov     [rsp+2D0h+var_2A0], edi
0x1800682cd  mov     [rsp+2D0h+var_2A8], rdi
0x1800682d2  call    ?IsJoined@DeviceRegistrationStateApi@@SAJPEBGW4_JOIN_TYPE@@PEAH2PEAPEBU_CERT_CONTEXT@@2@Z; DeviceRegistrationStateApi::IsJoined(ushort const *,_JOIN_TYPE,int *,int *,_CERT_CONTEXT const * *,int *)
0x1800682d7  test    eax, eax
0x1800682d9  jns     short loc_180068318
0x1800682db  mov     r9d, eax
0x1800682de  lea     r8, aDeviceregistra; "DeviceRegistrationStateApi::IsJoined"
0x1800682e5  lea     rdx, aDsrisdevicejoi; "DsrIsDeviceJoinedEx"
0x1800682ec  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800682f3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800682f8  call    isMachineJoinedToDomain
0x1800682fd  test    eax, eax
0x1800682ff  jz      short loc_180068344
0x180068301  mov     rcx, cs:WPP_GLOBAL_Control
0x180068308  cmp     rcx, r12
0x18006830b  jz      loc_1800684D6
0x180068311  mov     edx, 34h ; '4'
0x180068316  jmp     short loc_180068333
0x180068318  cmp     [rsp+2D0h+var_2A0], edi
0x18006831c  jz      short loc_1800682F8
0x18006831e  mov     rcx, cs:WPP_GLOBAL_Control
0x180068325  cmp     rcx, r12
0x180068328  jz      loc_1800684D6
0x18006832e  mov     edx, 33h ; '3'
0x180068333  mov     rcx, [rcx+10h]
0x180068337  mov     r8, r13
0x18006833a  call    WPP_SF_
0x18006833f  jmp     loc_1800684D6
0x180068344  mov     r8, [rbx]
0x180068347  xor     sil, sil
0x18006834a  test    r8, r8
0x18006834d  jz      short loc_180068385
0x18006834f  cmp     [r8], sil
0x180068352  jz      short loc_180068385
0x180068354  mov     edx, 202h
0x180068359  lea     rcx, [rbp+1D0h+Destination]
0x18006835d  call    cs:__imp__o_strcat_s
0x180068364  nop     dword ptr [rax+rax+00h]
0x180068369  lea     r8, asc_18008C8D8; "\\"
0x180068370  mov     edx, 202h
0x180068375  lea     rcx, [rbp+1D0h+Destination]
0x180068379  call    cs:__imp__o_strcat_s
0x180068380  nop     dword ptr [rax+rax+00h]
0x180068385  mov     r8, [rbx+8]; Source
0x180068389  lea     rcx, [rbp+1D0h+Destination]; Destination
0x18006838d  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180068391  mov     edx, 202h; SizeInBytes
0x180068396  call    cs:__imp_strncat_s
0x18006839d  nop     dword ptr [rax+rax+00h]
0x1800683a2  xor     edx, edx; Val
0x1800683a4  lea     rcx, [rsp+2D0h+Credential]; void *
0x1800683a9  lea     r8d, [rdx+50h]; Size
0x1800683ad  call    memset_0
0x1800683b2  lea     rax, aSession_0; "*Session"
0x1800683b9  mov     [rsp+2D0h+Credential.Type], 2
0x1800683c1  mov     [rsp+2D0h+Credential.TargetName], rax
0x1800683c6  lea     rax, [rbp+1D0h+Destination]
0x1800683ca  mov     [rbp+1D0h+Credential.UserName], rax
0x1800683ce  mov     [rsp+2D0h+Credential.Persist], 1
0x1800683d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800683dd  cmp     rcx, r12
0x1800683e0  jz      short loc_1800683F7
0x1800683e2  mov     rcx, [rcx+10h]
0x1800683e6  lea     r9, [rbp+1D0h+Destination]
0x1800683ea  mov     edx, 35h ; '5'
0x1800683ef  mov     r8, r13
0x1800683f2  call    WPP_SF_s
0x1800683f7  mov     rax, [rbx+10h]
0x1800683fb  mov     rcx, [rbx+20h]; hToken
0x1800683ff  mov     [rsp+2D0h+Credential.CredentialBlob], rax
0x180068404  mov     eax, [rbx+18h]
0x180068407  mov     [rsp+2D0h+Credential.CredentialBlobSize], eax
0x18006840b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006840f  jz      short loc_18006845A
0x180068411  call    cs:__imp_ImpersonateLoggedOnUser
0x180068418  nop     dword ptr [rax+rax+00h]
0x18006841d  test    eax, eax
0x18006841f  jnz     short loc_180068457
0x180068421  cmp     cs:WPP_GLOBAL_Control, r12
0x180068428  jz      loc_1800684D6
0x18006842e  call    cs:__imp_GetLastError
0x180068435  nop     dword ptr [rax+rax+00h]
0x18006843a  mov     rcx, cs:WPP_GLOBAL_Control
0x180068441  mov     edx, 36h ; '6'
0x180068446  mov     r9d, eax
0x180068449  mov     r8, r13
0x18006844c  mov     rcx, [rcx+10h]
0x180068450  call    WPP_SF_d
0x180068455  jmp     short loc_1800684D6
0x180068457  mov     sil, 1
0x18006845a  xor     edx, edx; Flags
0x18006845c  lea     rcx, [rsp+2D0h+Credential]; Credential
0x180068461  call    cs:__imp_CredWriteA
0x180068468  nop     dword ptr [rax+rax+00h]
0x18006846d  test    eax, eax
0x18006846f  jnz     short loc_1800684A1
0x180068471  call    cs:__imp_GetLastError
0x180068478  nop     dword ptr [rax+rax+00h]
0x18006847d  mov     edi, eax
0x18006847f  mov     rcx, cs:WPP_GLOBAL_Control
0x180068486  cmp     rcx, r12
0x180068489  jz      short loc_1800684C5
0x18006848b  mov     rcx, [rcx+10h]
0x18006848f  mov     edx, 37h ; '7'
0x180068494  mov     r9d, eax
0x180068497  mov     r8, r13
0x18006849a  call    WPP_SF_d
0x18006849f  jmp     short loc_1800684C5
0x1800684a1  mov     r14b, 1
0x1800684a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800684ab  cmp     rcx, r12
0x1800684ae  jz      short loc_1800684C5
0x1800684b0  mov     r9, [rbp+1D0h+Credential.UserName]
0x1800684b4  mov     edx, 38h ; '8'
0x1800684b9  mov     rcx, [rcx+10h]
0x1800684bd  mov     r8, r13
0x1800684c0  call    WPP_SF_s
0x1800684c5  test    sil, sil
0x1800684c8  jz      short loc_1800684D6
0x1800684ca  call    cs:__imp_RevertToSelf
0x1800684d1  nop     dword ptr [rax+rax+00h]
0x1800684d6  mov     rcx, rbx; hMem
0x1800684d9  call    ?FreeEapCredStructure@@YAXPEAU_EapCredThreadArgs@@@Z; FreeEapCredStructure(_EapCredThreadArgs *)
0x1800684de  mov     cs:byte_1800ABFB0, r14b
0x1800684e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800684ec  cmp     rcx, r12
0x1800684ef  jz      short loc_180068505
0x1800684f1  mov     rcx, [rcx+10h]
0x1800684f5  mov     edx, 39h ; '9'
0x1800684fa  mov     r9d, edi
0x1800684fd  mov     r8, r13
0x180068500  call    WPP_SF_d
0x180068505  mov     eax, edi
0x180068507  mov     rcx, [rbp+1D0h+var_30]
0x18006850e  xor     rcx, rsp; StackCookie
0x180068511  call    __security_check_cookie
0x180068516  lea     r11, [rsp+2D0h+var_20]
0x18006851e  mov     rbx, [r11+38h]
0x180068522  mov     rsi, [r11+40h]
0x180068526  mov     rsp, r11
0x180068529  pop     r14
0x18006852b  pop     r13
0x18006852d  pop     r12
0x18006852f  pop     rdi
0x180068530  pop     rbp
0x180068531  retn
```
