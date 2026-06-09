# DPAPINotifyCredentialKeyChange(void *,_CREDENTIAL_KEY *,_CREDENTIAL_KEY *,ulong)

- ea: `0x180028900`
- end: `0x180028b16`
- name: `?DPAPINotifyCredentialKeyChange@@YAJPEAXPEAU_CREDENTIAL_KEY@@1K@Z`
- size: `534`
- prototype: `__int64 __fastcall(HANDLE hToken, struct _CREDENTIAL_KEY *, struct _CREDENTIAL_KEY *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002d90`
- `0x180003080`
- `0x180007f10`
- `0x18001c9c0`
- `0x180028900`
- `0x1800290c8`
- `0x180029e7c`
- `0x18002c0a0`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002898d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002898d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ae0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ae0`
- `USERENV!UnloadUserProfile` at `0x180028afa`
- `USERENV!UnloadUserProfile` at `0x180028afa`

## string_xrefs

- `0x1800289aa`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180028aa1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall DPAPINotifyCredentialKeyChange(
        HANDLE hToken,
        struct _CREDENTIAL_KEY *a2,
        struct _CREDENTIAL_KEY *a3,
        unsigned int a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned int LastError; // ebx
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rcx
  HANDLE hProfile; // [rsp+20h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF

  hProfile = (HANDLE)-1LL;
  hMem = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 59, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids);
  v8 = *((_DWORD *)a2 + 3);
  if ( v8 > 0xFFFF || (v9 = *((_DWORD *)a2 + 2), v9 > *(_DWORD *)a2) || v9 + v8 > *(_DWORD *)a2 )
  {
    DebugTraceError(87, "dwStatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 3106);
    LastError = -1073282985;
    goto LABEL_29;
  }
  if ( !(unsigned int)GetTokenUserSid(hToken, &hMem) )
  {
    LastError = GetLastError();
    v11 = LastError;
    v12 = 3114;
    goto LABEL_9;
  }
  LastError = LoadProfileWithUserToken(hToken, &hProfile);
  if ( !LastError )
  {
    if ( (*((unsigned __int8 (__fastcall **)(HLOCAL))g_pDPAPILsasrvIfTable + 14))(hMem) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 61, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids);
      if ( (*((_BYTE *)a2 + 4) & 1) != 0 )
      {
        LastError = -1073741595;
        goto LABEL_29;
      }
      LastError = HandleDomainUserPasswordChange(hToken, a2);
      if ( LastError )
      {
        v12 = 3160;
        goto LABEL_13;
      }
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 60, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids);
      LastError = HandleLocalUserPasswordChange(hToken, a4, a2, a3);
      if ( LastError )
      {
        v12 = 3138;
        goto LABEL_13;
      }
    }
    LastError = 0;
    goto LABEL_29;
  }
  v12 = 3122;
LABEL_13:
  v11 = LastError;
LABEL_9:
  DebugTraceError(v11, "dwStatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v12);
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0xC0070000;
LABEL_29:
  if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 4) != 0 )
    McTemplateU0d_EtwEventWriteTransfer(v13, ETW_LOG_DPAPI_PASSWORD_CHANGE_TRIGGERED, LastError);
  if ( hMem )
    LocalFree(hMem);
  if ( hProfile != (HANDLE)-1LL )
    UnloadUserProfile(hToken, hProfile);
  return LastError;
}

```

## disassembly

```asm
0x180028900  push    rbx
0x180028902  push    rbp
0x180028903  push    rsi
0x180028904  push    rdi
0x180028905  push    r14
0x180028907  push    r15
0x180028909  sub     rsp, 38h
0x18002890d  mov     ebp, r9d
0x180028910  mov     [rsp+68h+hProfile], 0FFFFFFFFFFFFFFFFh
0x180028919  mov     r14, r8
0x18002891c  mov     [rsp+68h+hMem], 0
0x180028925  mov     rdi, rdx
0x180028928  mov     rsi, rcx
0x18002892b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028932  lea     r15, WPP_GLOBAL_Control
0x180028939  cmp     rcx, r15
0x18002893c  jz      short loc_180028959
0x18002893e  test    byte ptr [rcx+1Ch], 4
0x180028942  jz      short loc_180028959
0x180028944  mov     rcx, [rcx+10h]
0x180028948  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x18002894f  mov     edx, 3Bh ; ';'
0x180028954  call    WPP_SF_
0x180028959  mov     eax, [rdi+0Ch]
0x18002895c  cmp     eax, 0FFFFh
0x180028961  ja      loc_180028A9B
0x180028967  mov     ecx, [rdi+8]
0x18002896a  cmp     ecx, [rdi]
0x18002896c  ja      loc_180028A9B
0x180028972  add     eax, ecx
0x180028974  cmp     eax, [rdi]
0x180028976  ja      loc_180028A9B
0x18002897c  lea     rdx, [rsp+68h+hMem]
0x180028981  mov     rcx, rsi
0x180028984  call    GetTokenUserSid
0x180028989  test    eax, eax
0x18002898b  jnz     short loc_1800289CC
0x18002898d  call    cs:__imp_GetLastError
0x180028994  nop     dword ptr [rax+rax+00h]
0x180028999  mov     ebx, eax
0x18002899b  mov     ecx, eax
0x18002899d  mov     r9d, 0C2Ah
0x1800289a3  lea     rdx, aDwstatus; "dwStatus"
0x1800289aa  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800289b1  call    DebugTraceError
0x1800289b6  test    ebx, ebx
0x1800289b8  jle     loc_180028ABE
0x1800289be  movzx   ebx, bx
0x1800289c1  or      ebx, 0C0070000h
0x1800289c7  jmp     loc_180028ABE
0x1800289cc  lea     rdx, [rsp+68h+hProfile]; void **
0x1800289d1  mov     rcx, rsi; hToken
0x1800289d4  call    ?LoadProfileWithUserToken@@YAKPEAXPEAPEAX@Z; LoadProfileWithUserToken(void *,void * *)
0x1800289d9  mov     ebx, eax
0x1800289db  test    eax, eax
0x1800289dd  jz      short loc_1800289E9
0x1800289df  mov     r9d, 0C32h
0x1800289e5  mov     ecx, ebx
0x1800289e7  jmp     short loc_1800289A3
0x1800289e9  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x1800289f0  mov     rcx, [rsp+68h+hMem]
0x1800289f5  mov     rax, [rax+70h]
0x1800289f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289fe  test    al, al
0x180028a00  jnz     short loc_180028A47
0x180028a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a09  cmp     rcx, r15
0x180028a0c  jz      short loc_180028A29
0x180028a0e  test    byte ptr [rcx+1Ch], 8
0x180028a12  jz      short loc_180028A29
0x180028a14  mov     rcx, [rcx+10h]
0x180028a18  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180028a1f  mov     edx, 3Ch ; '<'
0x180028a24  call    WPP_SF_
0x180028a29  mov     r9, r14; struct _CREDENTIAL_KEY *
0x180028a2c  mov     r8, rdi; struct _CREDENTIAL_KEY *
0x180028a2f  mov     edx, ebp; unsigned int
0x180028a31  mov     rcx, rsi; void *
0x180028a34  call    ?HandleLocalUserPasswordChange@@YAKPEAXKPEAU_CREDENTIAL_KEY@@1@Z; HandleLocalUserPasswordChange(void *,ulong,_CREDENTIAL_KEY *,_CREDENTIAL_KEY *)
0x180028a39  mov     ebx, eax
0x180028a3b  test    eax, eax
0x180028a3d  jz      short loc_180028A97
0x180028a3f  mov     r9d, 0C42h
0x180028a45  jmp     short loc_1800289E5
0x180028a47  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a4e  cmp     rcx, r15
0x180028a51  jz      short loc_180028A6E
0x180028a53  test    byte ptr [rcx+1Ch], 8
0x180028a57  jz      short loc_180028A6E
0x180028a59  mov     rcx, [rcx+10h]
0x180028a5d  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180028a64  mov     edx, 3Dh ; '='
0x180028a69  call    WPP_SF_
0x180028a6e  test    byte ptr [rdi+4], 1
0x180028a72  jz      short loc_180028A7B
0x180028a74  mov     ebx, 0C00000E5h
0x180028a79  jmp     short loc_180028ABE
0x180028a7b  mov     rdx, rdi; struct _CREDENTIAL_KEY *
0x180028a7e  mov     rcx, rsi; hToken
0x180028a81  call    ?HandleDomainUserPasswordChange@@YAKPEAXPEAU_CREDENTIAL_KEY@@@Z; HandleDomainUserPasswordChange(void *,_CREDENTIAL_KEY *)
0x180028a86  mov     ebx, eax
0x180028a88  test    eax, eax
0x180028a8a  jz      short loc_180028A97
0x180028a8c  mov     r9d, 0C58h
0x180028a92  jmp     loc_1800289E5
0x180028a97  xor     ebx, ebx
0x180028a99  jmp     short loc_180028ABE
0x180028a9b  mov     r9d, 0C22h
0x180028aa1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180028aa8  lea     rdx, aDwstatus; "dwStatus"
0x180028aaf  mov     ecx, 57h ; 'W'
0x180028ab4  call    DebugTraceError
0x180028ab9  mov     ebx, 0C0070057h
0x180028abe  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 4
0x180028ac5  jz      short loc_180028AD6
0x180028ac7  mov     r8d, ebx
0x180028aca  lea     rdx, ETW_LOG_DPAPI_PASSWORD_CHANGE_TRIGGERED
0x180028ad1  call    McTemplateU0d_EtwEventWriteTransfer
0x180028ad6  mov     rcx, [rsp+68h+hMem]; hMem
0x180028adb  test    rcx, rcx
0x180028ade  jz      short loc_180028AEC
0x180028ae0  call    cs:__imp_LocalFree
0x180028ae7  nop     dword ptr [rax+rax+00h]
0x180028aec  mov     rdx, [rsp+68h+hProfile]; hProfile
0x180028af1  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180028af5  jz      short loc_180028B06
0x180028af7  mov     rcx, rsi; hToken
0x180028afa  call    cs:__imp_UnloadUserProfile
0x180028b01  nop     dword ptr [rax+rax+00h]
0x180028b06  mov     eax, ebx
0x180028b08  add     rsp, 38h
0x180028b0c  pop     r15
0x180028b0e  pop     r14
0x180028b10  pop     rdi
0x180028b11  pop     rsi
0x180028b12  pop     rbp
0x180028b13  pop     rbx
0x180028b14  retn
```
