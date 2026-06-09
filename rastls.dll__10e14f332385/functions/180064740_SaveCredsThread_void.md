# SaveCredsThread(void *)

- ea: `0x180064740`
- end: `0x1800649f2`
- name: `?SaveCredsThread@@YAKPEAX@Z`
- size: `690`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001c680`
- `0x18002ce0c`
- `0x180035680`
- `0x180036254`
- `0x18005caf4`
- `0x1800646bc`
- `0x180064740`
- `0x1800775b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18006484d`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180064863`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18006484d`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180064863`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x18006487a`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x18006487a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006493d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006493d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180064990`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180064990`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800648ef`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800648ef`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x180064933`
- `api-ms-win-security-credentials-l1-1-0!CredWriteA` at `0x180064933`

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
  byte_1800A5EE0 = v3;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180064740  mov     [rsp-8+arg_8], rbx
0x180064745  mov     [rsp-8+arg_10], rsi
0x18006474a  push    rbp
0x18006474b  push    rdi
0x18006474c  push    r12
0x18006474e  push    r13
0x180064750  push    r14
0x180064752  lea     rbp, [rsp-1B0h]
0x18006475a  sub     rsp, 2B0h
0x180064761  mov     rax, cs:__security_cookie
0x180064768  xor     rax, rsp
0x18006476b  mov     [rbp+1D0h+var_30], rax
0x180064772  mov     rbx, rcx
0x180064775  xor     edi, edi
0x180064777  lea     rcx, [rbp+1D0h+Destination]; void *
0x18006477b  xor     r14b, r14b
0x18006477e  xor     edx, edx; Val
0x180064780  mov     r8d, 202h; Size
0x180064786  call    memset_0
0x18006478b  mov     rcx, cs:WPP_GLOBAL_Control
0x180064792  lea     r12, WPP_GLOBAL_Control
0x180064799  lea     r13, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800647a0  cmp     rcx, r12
0x1800647a3  jz      short loc_1800647B4
0x1800647a5  mov     rcx, [rcx+10h]
0x1800647a9  lea     edx, [rdi+32h]
0x1800647ac  mov     r8, r13
0x1800647af  call    WPP_SF_
0x1800647b4  lea     r8, [rsp+2D0h+var_2A0]
0x1800647b9  mov     [rsp+2D0h+var_2A0], edi
0x1800647bd  mov     [rsp+2D0h+var_2A8], rdi
0x1800647c2  call    ?IsJoined@DeviceRegistrationStateApi@@SAJPEBGW4_JOIN_TYPE@@PEAH2PEAPEBU_CERT_CONTEXT@@2@Z; DeviceRegistrationStateApi::IsJoined(ushort const *,_JOIN_TYPE,int *,int *,_CERT_CONTEXT const * *,int *)
0x1800647c7  test    eax, eax
0x1800647c9  jns     short loc_180064808
0x1800647cb  mov     r9d, eax
0x1800647ce  lea     r8, aDeviceregistra; "DeviceRegistrationStateApi::IsJoined"
0x1800647d5  lea     rdx, aDsrisdevicejoi; "DsrIsDeviceJoinedEx"
0x1800647dc  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800647e3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800647e8  call    isMachineJoinedToDomain
0x1800647ed  test    eax, eax
0x1800647ef  jz      short loc_180064834
0x1800647f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800647f8  cmp     rcx, r12
0x1800647fb  jz      loc_180064996
0x180064801  mov     edx, 34h ; '4'
0x180064806  jmp     short loc_180064823
0x180064808  cmp     [rsp+2D0h+var_2A0], edi
0x18006480c  jz      short loc_1800647E8
0x18006480e  mov     rcx, cs:WPP_GLOBAL_Control
0x180064815  cmp     rcx, r12
0x180064818  jz      loc_180064996
0x18006481e  mov     edx, 33h ; '3'
0x180064823  mov     rcx, [rcx+10h]
0x180064827  mov     r8, r13
0x18006482a  call    WPP_SF_
0x18006482f  jmp     loc_180064996
0x180064834  mov     r8, [rbx]
0x180064837  xor     sil, sil
0x18006483a  test    r8, r8
0x18006483d  jz      short loc_180064869
0x18006483f  cmp     [r8], sil
0x180064842  jz      short loc_180064869
0x180064844  mov     edx, 202h
0x180064849  lea     rcx, [rbp+1D0h+Destination]
0x18006484d  call    cs:__imp__o_strcat_s
0x180064853  lea     r8, asc_1800868C8; "\\"
0x18006485a  mov     edx, 202h
0x18006485f  lea     rcx, [rbp+1D0h+Destination]
0x180064863  call    cs:__imp__o_strcat_s
0x180064869  mov     r8, [rbx+8]; Source
0x18006486d  lea     rcx, [rbp+1D0h+Destination]; Destination
0x180064871  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180064875  mov     edx, 202h; SizeInBytes
0x18006487a  call    cs:__imp_strncat_s
0x180064880  xor     edx, edx; Val
0x180064882  lea     rcx, [rsp+2D0h+Credential]; void *
0x180064887  lea     r8d, [rdx+50h]; Size
0x18006488b  call    memset_0
0x180064890  lea     rax, aSession_0; "*Session"
0x180064897  mov     [rsp+2D0h+Credential.Type], 2
0x18006489f  mov     [rsp+2D0h+Credential.TargetName], rax
0x1800648a4  lea     rax, [rbp+1D0h+Destination]
0x1800648a8  mov     [rbp+1D0h+Credential.UserName], rax
0x1800648ac  mov     [rsp+2D0h+Credential.Persist], 1
0x1800648b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800648bb  cmp     rcx, r12
0x1800648be  jz      short loc_1800648D5
0x1800648c0  mov     rcx, [rcx+10h]
0x1800648c4  lea     r9, [rbp+1D0h+Destination]
0x1800648c8  mov     edx, 35h ; '5'
0x1800648cd  mov     r8, r13
0x1800648d0  call    WPP_SF_s
0x1800648d5  mov     rax, [rbx+10h]
0x1800648d9  mov     rcx, [rbx+20h]; hToken
0x1800648dd  mov     [rsp+2D0h+Credential.CredentialBlob], rax
0x1800648e2  mov     eax, [rbx+18h]
0x1800648e5  mov     [rsp+2D0h+Credential.CredentialBlobSize], eax
0x1800648e9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800648ed  jz      short loc_18006492C
0x1800648ef  call    cs:__imp_ImpersonateLoggedOnUser
0x1800648f5  test    eax, eax
0x1800648f7  jnz     short loc_180064929
0x1800648f9  cmp     cs:WPP_GLOBAL_Control, r12
0x180064900  jz      loc_180064996
0x180064906  call    cs:__imp_GetLastError
0x18006490c  mov     rcx, cs:WPP_GLOBAL_Control
0x180064913  mov     edx, 36h ; '6'
0x180064918  mov     r9d, eax
0x18006491b  mov     r8, r13
0x18006491e  mov     rcx, [rcx+10h]
0x180064922  call    WPP_SF_d
0x180064927  jmp     short loc_180064996
0x180064929  mov     sil, 1
0x18006492c  xor     edx, edx; Flags
0x18006492e  lea     rcx, [rsp+2D0h+Credential]; Credential
0x180064933  call    cs:__imp_CredWriteA
0x180064939  test    eax, eax
0x18006493b  jnz     short loc_180064967
0x18006493d  call    cs:__imp_GetLastError
0x180064943  mov     edi, eax
0x180064945  mov     rcx, cs:WPP_GLOBAL_Control
0x18006494c  cmp     rcx, r12
0x18006494f  jz      short loc_18006498B
0x180064951  mov     rcx, [rcx+10h]
0x180064955  mov     edx, 37h ; '7'
0x18006495a  mov     r9d, eax
0x18006495d  mov     r8, r13
0x180064960  call    WPP_SF_d
0x180064965  jmp     short loc_18006498B
0x180064967  mov     r14b, 1
0x18006496a  mov     rcx, cs:WPP_GLOBAL_Control
0x180064971  cmp     rcx, r12
0x180064974  jz      short loc_18006498B
0x180064976  mov     r9, [rbp+1D0h+Credential.UserName]
0x18006497a  mov     edx, 38h ; '8'
0x18006497f  mov     rcx, [rcx+10h]
0x180064983  mov     r8, r13
0x180064986  call    WPP_SF_s
0x18006498b  test    sil, sil
0x18006498e  jz      short loc_180064996
0x180064990  call    cs:__imp_RevertToSelf
0x180064996  mov     rcx, rbx; hMem
0x180064999  call    ?FreeEapCredStructure@@YAXPEAU_EapCredThreadArgs@@@Z; FreeEapCredStructure(_EapCredThreadArgs *)
0x18006499e  mov     cs:byte_1800A5EE0, r14b
0x1800649a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800649ac  cmp     rcx, r12
0x1800649af  jz      short loc_1800649C5
0x1800649b1  mov     rcx, [rcx+10h]
0x1800649b5  mov     edx, 39h ; '9'
0x1800649ba  mov     r9d, edi
0x1800649bd  mov     r8, r13
0x1800649c0  call    WPP_SF_d
0x1800649c5  mov     eax, edi
0x1800649c7  mov     rcx, [rbp+1D0h+var_30]
0x1800649ce  xor     rcx, rsp; StackCookie
0x1800649d1  call    __security_check_cookie
0x1800649d6  lea     r11, [rsp+2D0h+var_20]
0x1800649de  mov     rbx, [r11+38h]
0x1800649e2  mov     rsi, [r11+40h]
0x1800649e6  mov     rsp, r11
0x1800649e9  pop     r14
0x1800649eb  pop     r13
0x1800649ed  pop     r12
0x1800649ef  pop     rdi
0x1800649f0  pop     rbp
0x1800649f1  retn
```
