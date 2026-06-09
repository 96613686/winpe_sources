# _SrvAdjustPrivilege

- ea: `0x1800066e0`
- end: `0x18000693e`
- name: `_SrvAdjustPrivilege`
- size: `606`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003360`
- `0x180003f60`

## callees

- `0x180002d20`
- `0x180003cf0`
- `0x180004470`
- `0x180006280`
- `0x1800066e0`
- `0x180006944`
- `0x180010340`
- `0x180018950`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006908`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006908`
- `ntdll!RtlNtStatusToDosError` at `0x180006918`
- `ntdll!RtlNtStatusToDosError` at `0x180006918`
- `ntdll!NtAdjustPrivilegesToken` at `0x180006813`
- `ntdll!NtAdjustPrivilegesToken` at `0x180006868`
- `ntdll!NtAdjustPrivilegesToken` at `0x1800068ce`
- `ntdll!NtAdjustPrivilegesToken` at `0x180006813`
- `ntdll!NtAdjustPrivilegesToken` at `0x180006868`
- `ntdll!NtAdjustPrivilegesToken` at `0x1800068ce`

## string_xrefs

- `0x180006727`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800067cf`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800068a3`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800068ed`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
ULONG __fastcall SrvAdjustPrivilege(__int64 a1, unsigned int a2, __int64 a3, PTOKEN_PRIVILEGES *a4)
{
  struct _TOKEN_PRIVILEGES *PreviousState; // rdi
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  HANDLE v10; // rsi
  int v11; // ebx
  _QWORD *v12; // rcx
  int v13; // edx
  __int64 v14; // r9
  __int64 v15; // rcx
  HANDLE TokenHandle; // [rsp+40h] [rbp-20h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-18h] BYREF

  TokenHandle = 0;
  PreviousState = 0;
  v7 = OpenCallerToken(a1, &TokenHandle);
  v10 = TokenHandle;
  if ( v7 )
  {
    DebugTraceError(v7, "dwStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 67);
    v11 = -1073741727;
    goto LABEL_27;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, a2, TokenHandle);
    v12 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    NewState.PrivilegeCount = 1;
    LODWORD(TokenHandle) = 16;
    NewState.Privileges[0].Luid = (LUID)8LL;
    NewState.Privileges[0].Attributes = 2;
    PreviousState = (struct _TOKEN_PRIVILEGES *)MSCryptAlloc(16);
    if ( !PreviousState )
    {
      v11 = -1073741801;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          102);
      goto LABEL_27;
    }
    v11 = NtAdjustPrivilegesToken(v10, 0, &NewState, (ULONG)TokenHandle, PreviousState, (PULONG)&TokenHandle);
    if ( v11 == -1073741789 )
    {
      MSCryptFree(PreviousState);
      PreviousState = (struct _TOKEN_PRIVILEGES *)MSCryptAlloc((unsigned int)TokenHandle);
      if ( !PreviousState )
      {
        v11 = -1073741801;
        v14 = 122;
        v15 = 3221225495LL;
LABEL_26:
        DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", v14);
        goto LABEL_27;
      }
      v11 = NtAdjustPrivilegesToken(v10, 0, &NewState, (ULONG)TokenHandle, PreviousState, (PULONG)&TokenHandle);
    }
    if ( v11 >= 0 )
    {
      *a4 = PreviousState;
      PreviousState = 0;
      goto LABEL_27;
    }
    v14 = 136;
LABEL_25:
    v15 = (unsigned int)v11;
    goto LABEL_26;
  }
  if ( *a4 )
  {
    v11 = NtAdjustPrivilegesToken(v10, 0, *a4, 0, 0, 0);
    MSCryptFree(*a4);
    *a4 = 0;
    if ( v11 >= 0 )
      goto LABEL_27;
    v14 = 164;
    goto LABEL_25;
  }
  v11 = -1073741811;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      v12[2],
      v8,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
      148);
LABEL_27:
  if ( v10 )
    CloseHandle(v10);
  MSCryptFree(PreviousState);
  return RtlNtStatusToDosError(v11);
}

```

## disassembly

```asm
0x1800066e0  mov     [rsp-28h+arg_0], rbx
0x1800066e5  push    rbp
0x1800066e6  push    rsi
0x1800066e7  push    rdi
0x1800066e8  push    r12
0x1800066ea  push    r14
0x1800066ec  mov     rbp, rsp
0x1800066ef  sub     rsp, 60h
0x1800066f3  mov     rax, cs:__security_cookie
0x1800066fa  xor     rax, rsp
0x1800066fd  mov     [rbp+var_8], rax
0x180006701  mov     ebx, edx
0x180006703  mov     [rbp+TokenHandle], 0
0x18000670b  lea     rdx, [rbp+TokenHandle]
0x18000670f  mov     r14, r9
0x180006712  xor     edi, edi
0x180006714  call    OpenCallerToken
0x180006719  mov     rsi, [rbp+TokenHandle]
0x18000671d  test    eax, eax
0x18000671f  jz      short loc_180006744
0x180006721  lea     r9d, [rdi+43h]
0x180006725  mov     ecx, eax
0x180006727  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000672e  lea     rdx, aDwstatus; "dwStatus"
0x180006735  call    DebugTraceError
0x18000673a  mov     ebx, 0C0000061h
0x18000673f  jmp     loc_180006900
0x180006744  mov     rcx, cs:WPP_GLOBAL_Control
0x18000674b  lea     r12, WPP_GLOBAL_Control
0x180006752  cmp     rcx, r12
0x180006755  jz      short loc_180006775
0x180006757  test    byte ptr [rcx+1Ch], 8
0x18000675b  jz      short loc_180006775
0x18000675d  mov     rcx, [rcx+10h]
0x180006761  mov     r9d, ebx
0x180006764  mov     [rsp+60h+PreviousState], rsi
0x180006769  call    WPP_SF_dq
0x18000676e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006775  test    ebx, ebx
0x180006777  jz      loc_180006883
0x18000677d  mov     ecx, 10h
0x180006782  mov     [rbp+NewState.PrivilegeCount], 1
0x180006789  mov     dword ptr [rbp+TokenHandle], ecx
0x18000678c  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 8
0x180006794  mov     [rbp+NewState.Privileges.Attributes], 2
0x18000679b  call    MSCryptAlloc
0x1800067a0  mov     rdi, rax
0x1800067a3  test    rax, rax
0x1800067a6  jnz     short loc_1800067F8
0x1800067a8  mov     ebx, 0C0000017h
0x1800067ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067b4  cmp     rcx, r12
0x1800067b7  jz      loc_180006900
0x1800067bd  test    byte ptr [rcx+1Ch], 1
0x1800067c1  jz      loc_180006900
0x1800067c7  mov     [rsp+60h+var_30], 66h ; 'f'
0x1800067cf  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800067d6  mov     [rsp+60h+ReturnLength], r8
0x1800067db  mov     dword ptr [rsp+60h+PreviousState], 0C0000017h
0x1800067e3  mov     rcx, [rcx+10h]
0x1800067e7  lea     r9, aStatus; "Status"
0x1800067ee  call    WPP_SF_sDsd
0x1800067f3  jmp     loc_180006900
0x1800067f8  mov     r9d, dword ptr [rbp+TokenHandle]; BufferLength
0x1800067fc  lea     rax, [rbp+TokenHandle]
0x180006800  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180006805  lea     r8, [rbp+NewState]; NewState
0x180006809  xor     edx, edx; DisableAllPrivileges
0x18000680b  mov     [rsp+60h+PreviousState], rdi; PreviousState
0x180006810  mov     rcx, rsi; TokenHandle
0x180006813  call    cs:__imp_NtAdjustPrivilegesToken
0x180006819  mov     ebx, eax
0x18000681b  cmp     eax, 0C0000023h
0x180006820  jnz     short loc_180006870
0x180006822  mov     rcx, rdi
0x180006825  call    MSCryptFree
0x18000682a  mov     ecx, dword ptr [rbp+TokenHandle]
0x18000682d  call    MSCryptAlloc
0x180006832  mov     rdi, rax
0x180006835  test    rax, rax
0x180006838  jnz     short loc_18000684D
0x18000683a  mov     ebx, 0C0000017h
0x18000683f  lea     r9d, [rax+7Ah]
0x180006843  mov     ecx, 0C0000017h
0x180006848  jmp     loc_1800068ED
0x18000684d  mov     r9d, dword ptr [rbp+TokenHandle]; BufferLength
0x180006851  lea     rax, [rbp+TokenHandle]
0x180006855  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18000685a  lea     r8, [rbp+NewState]; NewState
0x18000685e  xor     edx, edx; DisableAllPrivileges
0x180006860  mov     [rsp+60h+PreviousState], rdi; PreviousState
0x180006865  mov     rcx, rsi; TokenHandle
0x180006868  call    cs:__imp_NtAdjustPrivilegesToken
0x18000686e  mov     ebx, eax
0x180006870  test    ebx, ebx
0x180006872  jns     short loc_18000687C
0x180006874  mov     r9d, 88h
0x18000687a  jmp     short loc_1800068EB
0x18000687c  mov     [r14], rdi
0x18000687f  xor     edi, edi
0x180006881  jmp     short loc_180006900
0x180006883  mov     r8, [r14]; NewState
0x180006886  test    r8, r8
0x180006889  jnz     short loc_1800068BC
0x18000688b  mov     ebx, 0C000000Dh
0x180006890  cmp     rcx, r12
0x180006893  jz      short loc_180006900
0x180006895  test    byte ptr [rcx+1Ch], 1
0x180006899  jz      short loc_180006900
0x18000689b  mov     [rsp+60h+var_30], 94h
0x1800068a3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800068aa  mov     [rsp+60h+ReturnLength], r8
0x1800068af  mov     dword ptr [rsp+60h+PreviousState], 0C000000Dh
0x1800068b7  jmp     loc_1800067E3
0x1800068bc  mov     [rsp+60h+ReturnLength], rdi; ReturnLength
0x1800068c1  xor     r9d, r9d; BufferLength
0x1800068c4  xor     edx, edx; DisableAllPrivileges
0x1800068c6  mov     [rsp+60h+PreviousState], rdi; PreviousState
0x1800068cb  mov     rcx, rsi; TokenHandle
0x1800068ce  call    cs:__imp_NtAdjustPrivilegesToken
0x1800068d4  mov     rcx, [r14]
0x1800068d7  mov     ebx, eax
0x1800068d9  call    MSCryptFree
0x1800068de  mov     [r14], rdi
0x1800068e1  test    ebx, ebx
0x1800068e3  jns     short loc_180006900
0x1800068e5  mov     r9d, 0A4h
0x1800068eb  mov     ecx, ebx
0x1800068ed  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800068f4  lea     rdx, aStatus; "Status"
0x1800068fb  call    DebugTraceError
0x180006900  test    rsi, rsi
0x180006903  jz      short loc_18000690E
0x180006905  mov     rcx, rsi; hObject
0x180006908  call    cs:__imp_CloseHandle
0x18000690e  mov     rcx, rdi
0x180006911  call    MSCryptFree
0x180006916  mov     ecx, ebx; Status
0x180006918  call    cs:__imp_RtlNtStatusToDosError
0x18000691e  mov     rcx, [rbp+var_8]
0x180006922  xor     rcx, rsp; StackCookie
0x180006925  call    __security_check_cookie
0x18000692a  mov     rbx, [rsp+60h+arg_0]
0x180006932  add     rsp, 60h
0x180006936  pop     r14
0x180006938  pop     r12
0x18000693a  pop     rdi
0x18000693b  pop     rsi
0x18000693c  pop     rbp
0x18000693d  retn
```
