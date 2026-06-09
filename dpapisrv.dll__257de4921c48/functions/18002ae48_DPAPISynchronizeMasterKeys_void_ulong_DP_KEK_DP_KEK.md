# DPAPISynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *)

- ea: `0x18002ae48`
- end: `0x18002afba`
- name: `?DPAPISynchronizeMasterKeys@@YAXPEAXKPEAUDP_KEK@@1@Z`
- size: `370`
- prototype: `void __fastcall(HANDLE hToken, unsigned int, struct DP_KEK *, struct DP_KEK *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800290c8`
- `0x18002c0a0`

## callees

- `0x180007f10`
- `0x1800097f0`
- `0x18000db40`
- `0x180013f2c`
- `0x18001ab70`
- `0x18001d810`
- `0x18001e1b4`
- `0x18002ae48`
- `0x18002e130`
- `0x180039d90`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002aeb7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002aeb7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002af07`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002af07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aec7`

## string_xrefs

- `0x18002aee2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002af72`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
void __fastcall DPAPISynchronizeMasterKeys(HANDLE hToken, unsigned int a2, struct DP_KEK *a3, struct DP_KEK *a4)
{
  __int64 LastError; // rcx
  __int64 v9; // r9
  unsigned int v10; // ebx
  void *v11; // rcx
  unsigned int v12; // eax
  _DWORD v13[13]; // [rsp+40h] [rbp-2A8h] BYREF
  unsigned int v14; // [rsp+74h] [rbp-274h] BYREF
  unsigned int v15[142]; // [rsp+78h] [rbp-270h] BYREF

  memset_0(v13, 0, 0x270u);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, a2);
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    LastError = GetLastError();
    v9 = 1593;
LABEL_6:
    DebugTraceError(LastError, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v9);
    return;
  }
  v10 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v13, 0, 0, 0);
  RevertToSelf();
  if ( v10 )
  {
    v9 = 1603;
    LastError = v10;
    goto LABEL_6;
  }
  GetDefaultAlgInfo(v11, &v14, 0, v15, 0);
  v12 = SynchronizeMasterKeys(v13, a2, a3, a4, 0, 0, 0);
  if ( v12 )
    DebugTraceError(v12, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 1630);
  else
    UpdateLastMasterKeySync(v13);
  CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v13);
}

```

## disassembly

```asm
0x18002ae48  push    rbx
0x18002ae4a  push    rbp
0x18002ae4b  push    rsi
0x18002ae4c  push    rdi
0x18002ae4d  sub     rsp, 2C8h
0x18002ae54  mov     rax, cs:__security_cookie
0x18002ae5b  xor     rax, rsp
0x18002ae5e  mov     [rsp+2E8h+var_38], rax
0x18002ae66  mov     rsi, r8
0x18002ae69  mov     edi, edx
0x18002ae6b  mov     rbx, rcx
0x18002ae6e  xor     edx, edx; Val
0x18002ae70  mov     r8d, 270h; Size
0x18002ae76  lea     rcx, [rsp+2E8h+var_2A8]; void *
0x18002ae7b  mov     rbp, r9
0x18002ae7e  call    memset_0
0x18002ae83  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae8a  lea     rax, WPP_GLOBAL_Control
0x18002ae91  cmp     rcx, rax
0x18002ae94  jz      short loc_18002AEB4
0x18002ae96  test    byte ptr [rcx+1Ch], 4
0x18002ae9a  jz      short loc_18002AEB4
0x18002ae9c  mov     rcx, [rcx+10h]
0x18002aea0  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002aea7  mov     edx, 1Dh
0x18002aeac  mov     r9d, edi
0x18002aeaf  call    WPP_SF_d
0x18002aeb4  mov     rcx, rbx; hToken
0x18002aeb7  call    cs:__imp_ImpersonateLoggedOnUser
0x18002aebe  nop     dword ptr [rax+rax+00h]
0x18002aec3  test    eax, eax
0x18002aec5  jnz     short loc_18002AEF3
0x18002aec7  call    cs:__imp_GetLastError
0x18002aece  nop     dword ptr [rax+rax+00h]
0x18002aed3  mov     ecx, eax
0x18002aed5  mov     r9d, 639h
0x18002aedb  lea     rdx, aDwerror; "dwError"
0x18002aee2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002aee9  call    DebugTraceError
0x18002aeee  jmp     loc_18002AF9D
0x18002aef3  xor     r9d, r9d; unsigned int *
0x18002aef6  lea     rcx, [rsp+2E8h+var_2A8]; struct CRYPT_SERVER_CONTEXT *
0x18002aefb  xor     r8d, r8d; unsigned __int16 **
0x18002aefe  xor     edx, edx; void *
0x18002af00  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x18002af05  mov     ebx, eax
0x18002af07  call    cs:__imp_RevertToSelf
0x18002af0e  nop     dword ptr [rax+rax+00h]
0x18002af13  test    ebx, ebx
0x18002af15  jz      short loc_18002AF21
0x18002af17  mov     r9d, 643h
0x18002af1d  mov     ecx, ebx
0x18002af1f  jmp     short loc_18002AEDB
0x18002af21  lea     r9, [rsp+2E8h+var_270]; unsigned int *
0x18002af26  mov     [rsp+2E8h+var_2C8], 0; unsigned int *
0x18002af2f  xor     r8d, r8d; unsigned int *
0x18002af32  lea     rdx, [rsp+2E8h+var_274]; unsigned int *
0x18002af37  call    ?GetDefaultAlgInfo@@YAXPEAXPEAK111@Z; GetDefaultAlgInfo(void *,ulong *,ulong *,ulong *,ulong *)
0x18002af3c  mov     [rsp+2E8h+var_2B8], 0; unsigned int *
0x18002af45  lea     rcx, [rsp+2E8h+var_2A8]; void *
0x18002af4a  mov     [rsp+2E8h+var_2C0], 0; unsigned int *
0x18002af53  mov     r9, rbp; struct DP_KEK *
0x18002af56  mov     r8, rsi; struct DP_KEK *
0x18002af59  mov     dword ptr [rsp+2E8h+var_2C8], 0; unsigned int
0x18002af61  mov     edx, edi; unsigned int
0x18002af63  call    ?SynchronizeMasterKeys@@YAKPEAXKPEAUDP_KEK@@1KPEAK2@Z; SynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x18002af68  test    eax, eax
0x18002af6a  jz      short loc_18002AF89
0x18002af6c  mov     r9d, 65Eh
0x18002af72  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002af79  lea     rdx, aDwerror; "dwError"
0x18002af80  mov     ecx, eax
0x18002af82  call    DebugTraceError
0x18002af87  jmp     short loc_18002AF93
0x18002af89  lea     rcx, [rsp+2E8h+var_2A8]; void *
0x18002af8e  call    ?UpdateLastMasterKeySync@@YAKPEAX@Z; UpdateLastMasterKeySync(void *)
0x18002af93  lea     rcx, [rsp+2E8h+var_2A8]; struct CRYPT_SERVER_CONTEXT *
0x18002af98  call    ?CPSDeleteServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@@Z; CPSDeleteServerContext(CRYPT_SERVER_CONTEXT *)
0x18002af9d  mov     rcx, [rsp+2E8h+var_38]
0x18002afa5  xor     rcx, rsp; StackCookie
0x18002afa8  call    __security_check_cookie
0x18002afad  add     rsp, 2C8h
0x18002afb4  pop     rdi
0x18002afb5  pop     rsi
0x18002afb6  pop     rbp
0x18002afb7  pop     rbx
0x18002afb8  retn
```
