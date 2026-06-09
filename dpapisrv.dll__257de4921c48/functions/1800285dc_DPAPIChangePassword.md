# DPAPIChangePassword

- ea: `0x1800285dc`
- end: `0x1800288ee`
- name: `DPAPIChangePassword`
- size: `786`
- prototype: `__int64 __fastcall(HANDLE hToken)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800290c8`

## callees

- `0x180003b98`
- `0x1800045c0`
- `0x180007f10`
- `0x18000d130`
- `0x18000df80`
- `0x180011710`
- `0x18001c340`
- `0x18001d810`
- `0x1800284ac`
- `0x1800285dc`
- `0x180028b1c`
- `0x180029f10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800286a8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800286a8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800287ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800287c8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800287ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800287c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800288a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800288a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028869`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028869`

## string_xrefs

- `0x18002868b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x1800287ae`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180028802`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall DPAPIChangePassword(HANDLE hToken, __int64 a2, __int64 a3)
{
  struct _CREDENTIAL_HISTORY *v4; // rdi
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r12
  DWORD LastError; // eax
  __int64 v12; // r9
  __int64 v13; // r9
  __int64 v14; // r9
  __int64 v15; // r8
  HANDLE v16; // rcx
  const wchar_t *v17; // r9
  __int64 v18; // rax
  struct _CREDENTIAL_HISTORY *v19; // rcx
  UCHAR *v20; // rax
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  struct _CREDENTIAL_HISTORY *v22; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  UCHAR pbOutput[32]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD pbInput[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v27[264]; // [rsp+290h] [rbp+190h] BYREF

  hObject = 0;
  v4 = 0;
  hMem = 0;
  v22 = 0;
  v21 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF__guid__guid_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, a3, a2, a3);
  if ( !g_fDPAPIInitialized )
    return 1359;
  v8 = PRGetProfilePath(hToken, v27);
  v9 = v8;
  if ( !v8 )
  {
    v10 = 20;
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastError = GetLastError();
      v9 = LastError;
      v12 = 2238;
LABEL_22:
      DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v12);
      goto LABEL_23;
    }
    if ( (unsigned int)GetUserTextualSid(hToken, pbInput) )
    {
      v14 = -1;
      do
        ++v14;
      while ( pbInput[v14] );
      DeriveWithHMAC_SHA1((void *)(a3 + 20), 0x14u, (PUCHAR)pbInput, 2 * v14 + 2, pbOutput);
      v9 = EncryptCredentialHistory(
             *(_DWORD *)(a3 + 16),
             pbOutput,
             v15,
             (unsigned __int8 *const)(a2 + 20),
             (unsigned __int8 *const)(a2 + 40),
             &v22,
             &v21);
      if ( v9 )
      {
        v13 = 2281;
      }
      else
      {
        v9 = CreateCredentialHistoryMap((__int64)hToken, v27, (__int64 *)a2, 0, 0, &hMem, &hObject);
        if ( !v9 )
        {
          RevertToSelf();
          v4 = v22;
          LastError = AppendCredentialHistoryMap(hObject, v21);
          v9 = LastError;
          if ( LastError )
          {
            v12 = 2317;
            goto LABEL_22;
          }
LABEL_23:
          v16 = hObject;
          if ( hObject )
          {
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              v17 = L"NULL";
              if ( hMem )
                v17 = (const wchar_t *)((char *)hMem + 8);
              WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, v17);
              v16 = hObject;
            }
            CloseHandle(v16);
          }
          if ( hMem )
            DestroyCredentialHistoryMap(hMem);
          if ( v4 )
          {
            v18 = v21;
            v19 = v4;
            if ( v21 )
            {
              do
              {
                *(_BYTE *)v19 = 0;
                v19 = (struct _CREDENTIAL_HISTORY *)((char *)v19 + 1);
                --v18;
              }
              while ( v18 );
            }
            LocalFree(v4);
          }
          v20 = pbOutput;
          do
          {
            *v20++ = 0;
            --v10;
          }
          while ( v10 );
          return v9;
        }
        v13 = 2297;
      }
      v4 = v22;
    }
    else
    {
      v9 = 13;
      v13 = 2252;
    }
    DebugTraceError(v9, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v13);
    RevertToSelf();
    goto LABEL_23;
  }
  DebugTraceError(v8, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 2231);
  return v9;
}

```

## disassembly

```asm
0x1800285dc  mov     [rsp-8+arg_18], rbx
0x1800285e1  push    rbp
0x1800285e2  push    rsi
0x1800285e3  push    rdi
0x1800285e4  push    r12
0x1800285e6  push    r13
0x1800285e8  push    r14
0x1800285ea  push    r15
0x1800285ec  lea     rbp, [rsp-3B0h]
0x1800285f4  sub     rsp, 4B0h
0x1800285fb  mov     rax, cs:__security_cookie
0x180028602  xor     rax, rsp
0x180028605  mov     [rbp+3E0h+var_40], rax
0x18002860c  xor     r13d, r13d
0x18002860f  mov     r14, r8
0x180028612  mov     [rsp+4E0h+hObject], r13
0x180028617  mov     edi, r13d
0x18002861a  mov     [rsp+4E0h+hMem], r13
0x18002861f  mov     r15, rdx
0x180028622  mov     [rsp+4E0h+var_498], r13
0x180028627  mov     rsi, rcx
0x18002862a  mov     [rsp+4E0h+var_4A0], r13d
0x18002862f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028636  lea     rax, WPP_GLOBAL_Control
0x18002863d  cmp     rcx, rax
0x180028640  jz      short loc_18002865D
0x180028642  test    byte ptr [rcx+1Ch], 4
0x180028646  jz      short loc_18002865D
0x180028648  mov     rcx, [rcx+10h]
0x18002864c  lea     edx, [r13+22h]
0x180028650  mov     r9, r15
0x180028653  mov     [rsp+4E0h+pbOutput], r8
0x180028658  call    WPP_SF__guid__guid_
0x18002865d  cmp     cs:?g_fDPAPIInitialized@@3HA, r13d; int g_fDPAPIInitialized
0x180028664  jnz     short loc_180028670
0x180028666  mov     eax, 54Fh
0x18002866b  jmp     loc_1800288C3
0x180028670  lea     rdx, [rbp+3E0h+var_250]
0x180028677  mov     rcx, rsi
0x18002867a  call    PRGetProfilePath
0x18002867f  mov     ebx, eax
0x180028681  test    eax, eax
0x180028683  jz      short loc_1800286A5
0x180028685  mov     r9d, 8B7h
0x18002868b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180028692  lea     rdx, aDwlasterror; "dwLastError"
0x180028699  mov     ecx, eax
0x18002869b  call    DebugTraceError
0x1800286a0  jmp     loc_1800288C1
0x1800286a5  mov     rcx, rsi; hToken
0x1800286a8  call    cs:__imp_ImpersonateLoggedOnUser
0x1800286af  nop     dword ptr [rax+rax+00h]
0x1800286b4  mov     r12d, 14h
0x1800286ba  test    eax, eax
0x1800286bc  jnz     short loc_1800286D7
0x1800286be  call    cs:__imp_GetLastError
0x1800286c5  nop     dword ptr [rax+rax+00h]
0x1800286ca  mov     ebx, eax
0x1800286cc  mov     r9d, 8BEh
0x1800286d2  jmp     loc_180028802
0x1800286d7  lea     rdx, [rbp+3E0h+pbInput]
0x1800286db  mov     rcx, rsi
0x1800286de  call    GetUserTextualSid
0x1800286e3  test    eax, eax
0x1800286e5  jnz     short loc_1800286F5
0x1800286e7  lea     ebx, [rax+0Dh]
0x1800286ea  mov     r9d, 8CCh
0x1800286f0  jmp     loc_1800287A5
0x1800286f5  lea     rax, [rbp+3E0h+pbInput]
0x1800286f9  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800286fd  inc     r9
0x180028700  cmp     [rax+r9*2], r13w
0x180028705  jnz     short loc_1800286FD
0x180028707  lea     rax, [rsp+4E0h+var_480]
0x18002870c  mov     edx, r12d; Size
0x18002870f  lea     r9d, ds:2[r9*2]; cbInput
0x180028717  mov     [rsp+4E0h+pbOutput], rax; pbOutput
0x18002871c  lea     rcx, [r14+14h]; Src
0x180028720  lea     r8, [rbp+3E0h+pbInput]; pbInput
0x180028724  call    DeriveWithHMAC_SHA1
0x180028729  lea     rcx, [rsp+4E0h+var_4A0]
0x18002872e  mov     [rsp+4E0h+var_4B0], rcx; unsigned int *
0x180028733  lea     rax, [r15+28h]
0x180028737  lea     rcx, [rsp+4E0h+var_498]
0x18002873c  mov     [rsp+4E0h+var_4B8], rcx; struct _CREDENTIAL_HISTORY **
0x180028741  lea     r9, [r15+14h]; unsigned __int8 *
0x180028745  mov     ecx, [r14+10h]; unsigned int
0x180028749  lea     rdx, [rsp+4E0h+var_480]; unsigned __int8 *
0x18002874e  mov     [rsp+4E0h+pbOutput], rax; unsigned __int8 *
0x180028753  call    ?EncryptCredentialHistory@@YAKKQEAEK00PEAPEAU_CREDENTIAL_HISTORY@@PEAK@Z; EncryptCredentialHistory(ulong,uchar * const,ulong,uchar * const,uchar * const,_CREDENTIAL_HISTORY * *,ulong *)
0x180028758  mov     ebx, eax
0x18002875a  test    eax, eax
0x18002875c  jz      short loc_180028766
0x18002875e  mov     r9d, 8E9h
0x180028764  jmp     short loc_1800287A0
0x180028766  lea     rax, [rsp+4E0h+hObject]
0x18002876b  xor     r9d, r9d
0x18002876e  mov     [rsp+4E0h+var_4B0], rax
0x180028773  lea     rdx, [rbp+3E0h+var_250]
0x18002877a  lea     rax, [rsp+4E0h+hMem]
0x18002877f  mov     r8, r15
0x180028782  mov     [rsp+4E0h+var_4B8], rax
0x180028787  mov     rcx, rsi
0x18002878a  mov     dword ptr [rsp+4E0h+pbOutput], r13d
0x18002878f  call    CreateCredentialHistoryMap
0x180028794  mov     ebx, eax
0x180028796  test    eax, eax
0x180028798  jz      short loc_1800287C8
0x18002879a  mov     r9d, 8F9h
0x1800287a0  mov     rdi, [rsp+4E0h+var_498]
0x1800287a5  lea     rdx, aDwlasterror; "dwLastError"
0x1800287ac  mov     ecx, ebx
0x1800287ae  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800287b5  call    DebugTraceError
0x1800287ba  call    cs:__imp_RevertToSelf
0x1800287c1  nop     dword ptr [rax+rax+00h]
0x1800287c6  jmp     short loc_180028817
0x1800287c8  call    cs:__imp_RevertToSelf
0x1800287cf  nop     dword ptr [rax+rax+00h]
0x1800287d4  mov     eax, [rsp+4E0h+var_4A0]
0x1800287d8  mov     rdx, r14
0x1800287db  mov     rdi, [rsp+4E0h+var_498]
0x1800287e0  mov     r8, [rsp+4E0h+hMem]
0x1800287e5  mov     r9, rdi
0x1800287e8  mov     rcx, [rsp+4E0h+hObject]; hFile
0x1800287ed  mov     dword ptr [rsp+4E0h+pbOutput], eax; int
0x1800287f1  call    AppendCredentialHistoryMap
0x1800287f6  mov     ebx, eax
0x1800287f8  test    eax, eax
0x1800287fa  jz      short loc_180028817
0x1800287fc  mov     r9d, 90Dh
0x180028802  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180028809  mov     ecx, eax
0x18002880b  lea     rdx, aDwlasterror; "dwLastError"
0x180028812  call    DebugTraceError
0x180028817  mov     rcx, [rsp+4E0h+hObject]
0x18002881c  test    rcx, rcx
0x18002881f  jz      short loc_180028875
0x180028821  mov     rax, cs:WPP_GLOBAL_Control
0x180028828  lea     rdx, WPP_GLOBAL_Control
0x18002882f  cmp     rax, rdx
0x180028832  jz      short loc_180028869
0x180028834  test    byte ptr [rax+1Ch], 4
0x180028838  jz      short loc_180028869
0x18002883a  mov     rcx, [rsp+4E0h+hMem]
0x18002883f  lea     r9, aNull_0; "NULL"
0x180028846  test    rcx, rcx
0x180028849  jz      short loc_18002884F
0x18002884b  lea     r9, [rcx+8]
0x18002884f  mov     rcx, [rax+10h]
0x180028853  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x18002885a  mov     edx, 23h ; '#'
0x18002885f  call    WPP_SF_S
0x180028864  mov     rcx, [rsp+4E0h+hObject]; hObject
0x180028869  call    cs:__imp_CloseHandle
0x180028870  nop     dword ptr [rax+rax+00h]
0x180028875  mov     rcx, [rsp+4E0h+hMem]; hMem
0x18002887a  test    rcx, rcx
0x18002887d  jz      short loc_180028884
0x18002887f  call    DestroyCredentialHistoryMap
0x180028884  test    rdi, rdi
0x180028887  jz      short loc_1800288B0
0x180028889  mov     eax, [rsp+4E0h+var_4A0]
0x18002888d  mov     rcx, rdi
0x180028890  test    rax, rax
0x180028893  jz      short loc_1800288A1
0x180028895  mov     [rcx], r13b
0x180028898  inc     rcx
0x18002889b  sub     rax, 1
0x18002889f  jnz     short loc_180028895
0x1800288a1  mov     rcx, rdi; hMem
0x1800288a4  call    cs:__imp_LocalFree
0x1800288ab  nop     dword ptr [rax+rax+00h]
0x1800288b0  lea     rax, [rsp+4E0h+var_480]
0x1800288b5  mov     [rax], r13b
0x1800288b8  inc     rax
0x1800288bb  sub     r12, 1
0x1800288bf  jnz     short loc_1800288B5
0x1800288c1  mov     eax, ebx
0x1800288c3  mov     rcx, [rbp+3E0h+var_40]
0x1800288ca  xor     rcx, rsp; StackCookie
0x1800288cd  call    __security_check_cookie
0x1800288d2  mov     rbx, [rsp+4E0h+arg_18]
0x1800288da  add     rsp, 4B0h
0x1800288e1  pop     r15
0x1800288e3  pop     r14
0x1800288e5  pop     r13
0x1800288e7  pop     r12
0x1800288e9  pop     rdi
0x1800288ea  pop     rsi
0x1800288eb  pop     rbp
0x1800288ec  retn
```
