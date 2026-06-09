# LsaIfGetCurrentCredentialKeyId(void *,_GUID *)

- ea: `0x180003510`
- end: `0x180003902`
- name: `?LsaIfGetCurrentCredentialKeyId@@YAKPEAXPEAU_GUID@@@Z`
- size: `1010`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800033a8`
- `0x180003510`
- `0x180003b98`
- `0x1800045c0`
- `0x180007f10`
- `0x18001c340`
- `0x18001d810`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000384b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000384b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003772`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003772`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003570`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003570`
- `USERENV!__imp_GetUserProfileDirectoryForUserSidW` at `0x180003593`
- `USERENV!__imp_GetUserProfileDirectoryForUserSidW` at `0x180003593`

## string_xrefs

- `0x18000374a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800037e1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180003872`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180003889`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800038ad`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall LsaIfGetCurrentCredentialKeyId(void *a1, struct _GUID *a2)
{
  HLOCAL v4; // r15
  __int64 v5; // rdx
  _WORD *v6; // rax
  unsigned int v7; // r10d
  __int64 v8; // r8
  __int64 v9; // rcx
  _WORD *v10; // rax
  const wchar_t *v11; // rdx
  __int64 v12; // rbx
  _WORD *v13; // rcx
  struct _CREDENTIAL_HISTORY *v14; // rsi
  int v15; // edx
  DWORD LastError; // ebx
  HANDLE v17; // rax
  struct _CREDENTIAL_HISTORY *PreviousCredentialHistory; // rax
  DWORD v20; // eax
  int v21; // edx
  const wchar_t *v22; // r9
  __int64 v23; // rcx
  __int64 v24; // r9
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v29[264]; // [rsp+60h] [rbp-A0h] BYREF

  v26 = 261;
  StringSid = 0;
  v4 = 0;
  if ( a2 )
  {
    *a2 = 0;
    if ( !ConvertSidToStringSidW(a1, &StringSid) )
    {
      LastError = GetLastError();
      v23 = LastError;
      v24 = 8928;
LABEL_44:
      DebugTraceError(v23, "dwRet", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v24);
      goto LABEL_25;
    }
    if ( !(unsigned int)GetUserProfileDirectoryForUserSidW(StringSid, v29, &v26) )
    {
      v20 = GetLastError();
      LastError = v20;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v21,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwRet",
          v20,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
          234);
      goto LABEL_25;
    }
    v5 = 261;
    v6 = v29;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (261 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = 2147483646;
      v10 = &v29[v8];
      v11 = L"\\AppData\\Roaming";
      v12 = 261 - v8;
      if ( 261 != v8 )
      {
        do
        {
          if ( !v9 )
            break;
          if ( !*v11 )
            break;
          *v10++ = *v11++;
          --v9;
          --v12;
        }
        while ( v12 );
      }
      v13 = v10 - 1;
      if ( v12 )
        v13 = v10;
      v7 = v12 == 0 ? 0x8007007A : 0;
      *v13 = 0;
    }
    if ( !v7 )
    {
      hObject = 0;
      hMem = 0;
      v14 = 0;
      LastError = CreateCredentialHistoryMap(0, v29, 0, a1, 1, &hMem, &hObject);
      v17 = hObject;
      if ( hObject )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v22 = L"NULL";
          if ( hMem )
            v22 = (const wchar_t *)((char *)hMem + 8);
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, v22);
          v17 = hObject;
        }
        CloseHandle(v17);
      }
      if ( LastError )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            v15,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwError",
            LastError,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
            145);
      }
      else
      {
        PreviousCredentialHistory = GetPreviousCredentialHistory((struct _CREDENTIAL_HISTORY_MAP *)hMem, 0);
        if ( PreviousCredentialHistory )
        {
          v4 = hMem;
          v14 = PreviousCredentialHistory;
          hMem = 0;
        }
        else
        {
          LastError = 87;
        }
      }
      if ( hMem )
        DestroyCredentialHistoryMap(hMem);
      if ( !LastError )
      {
        LastError = 0;
        *a2 = *(struct _GUID *)((char *)v14 + 4);
        goto LABEL_25;
      }
      v24 = 8964;
      v23 = LastError;
      goto LABEL_44;
    }
    DebugTraceError(v7, "dwRet", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 8950);
    LastError = 87;
  }
  else
  {
    LastError = 87;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_27;
    WPP_SF_sDsd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      0,
      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
      (unsigned int)"dwRet",
      87,
      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
      216);
  }
LABEL_25:
  if ( StringSid )
    LocalFree(StringSid);
LABEL_27:
  DestroyCredentialHistoryMap(v4);
  return LastError;
}

```

## disassembly

```asm
0x180003510  mov     [rsp-8+arg_10], rbx
0x180003515  mov     [rsp-8+arg_18], rsi
0x18000351a  push    rbp
0x18000351b  push    rdi
0x18000351c  push    r12
0x18000351e  push    r14
0x180003520  push    r15
0x180003522  lea     rbp, [rsp-180h]
0x18000352a  sub     rsp, 280h
0x180003531  mov     rax, cs:__security_cookie
0x180003538  xor     rax, rsp
0x18000353b  mov     [rbp+1A0h+var_30], rax
0x180003542  xor     r12d, r12d
0x180003545  mov     ebx, 105h
0x18000354a  mov     [rsp+2A0h+var_258], ebx
0x18000354e  mov     r14, rdx
0x180003551  mov     [rsp+2A0h+StringSid], r12
0x180003556  mov     rdi, rcx
0x180003559  mov     r15d, r12d
0x18000355c  test    rdx, rdx
0x18000355f  jz      loc_180003724
0x180003565  xorps   xmm0, xmm0
0x180003568  movups  xmmword ptr [rdx], xmm0
0x18000356b  lea     rdx, [rsp+2A0h+StringSid]; StringSid
0x180003570  call    cs:__imp_ConvertSidToStringSidW
0x180003577  nop     dword ptr [rax+rax+00h]
0x18000357c  test    eax, eax
0x18000357e  jz      loc_18000384B
0x180003584  mov     rcx, [rsp+2A0h+StringSid]
0x180003589  lea     r8, [rsp+2A0h+var_258]
0x18000358e  lea     rdx, [rsp+2A0h+var_240]
0x180003593  call    cs:__imp_GetUserProfileDirectoryForUserSidW
0x18000359a  nop     dword ptr [rax+rax+00h]
0x18000359f  test    eax, eax
0x1800035a1  jz      loc_1800037AA
0x1800035a7  mov     edx, ebx
0x1800035a9  lea     rax, [rsp+2A0h+var_240]
0x1800035ae  cmp     [rax], r12w
0x1800035b2  jz      short loc_1800035BE
0x1800035b4  add     rax, 2
0x1800035b8  sub     rdx, 1
0x1800035bc  jnz     short loc_1800035AE
0x1800035be  mov     rax, rdx
0x1800035c1  mov     rcx, rbx
0x1800035c4  neg     rax
0x1800035c7  mov     rax, rdx
0x1800035ca  sbb     r10d, r10d
0x1800035cd  sub     rcx, rdx
0x1800035d0  not     r10d
0x1800035d3  and     r10d, 80070057h
0x1800035da  neg     rax
0x1800035dd  sbb     r8, r8
0x1800035e0  and     r8, rcx
0x1800035e3  test    rdx, rdx
0x1800035e6  jz      short loc_180003645
0x1800035e8  lea     rax, [rsp+2A0h+var_240]
0x1800035ed  mov     ecx, 7FFFFFFEh
0x1800035f2  lea     rax, [rax+r8*2]
0x1800035f6  lea     rdx, aAppdataRoaming; "\\AppData\\Roaming"
0x1800035fd  sub     rbx, r8
0x180003600  jz      short loc_180003626
0x180003602  test    rcx, rcx
0x180003605  jz      short loc_180003626
0x180003607  movzx   r8d, word ptr [rdx]
0x18000360b  test    r8w, r8w
0x18000360f  jz      short loc_180003626
0x180003611  mov     [rax], r8w
0x180003615  add     rdx, 2
0x180003619  add     rax, 2
0x18000361d  dec     rcx
0x180003620  sub     rbx, 1
0x180003624  jnz     short loc_180003602
0x180003626  test    rbx, rbx
0x180003629  lea     rcx, [rax-2]
0x18000362d  cmovnz  rcx, rax
0x180003631  neg     rbx
0x180003634  sbb     r10d, r10d
0x180003637  not     r10d
0x18000363a  and     r10d, 8007007Ah
0x180003641  mov     [rcx], r12w
0x180003645  test    r10d, r10d
0x180003648  jnz     loc_180003883
0x18000364e  lea     rax, [rsp+2A0h+hObject]
0x180003653  mov     [rsp+2A0h+hObject], r12
0x180003658  mov     [rsp+2A0h+var_270], rax
0x18000365d  lea     rdx, [rsp+2A0h+var_240]
0x180003662  lea     rax, [rsp+2A0h+hMem]
0x180003667  mov     [rsp+2A0h+hMem], r12
0x18000366c  mov     [rsp+2A0h+var_278], rax
0x180003671  mov     r9, rdi
0x180003674  xor     r8d, r8d
0x180003677  mov     [rsp+2A0h+var_280], 1
0x18000367f  xor     ecx, ecx
0x180003681  mov     rsi, r12
0x180003684  call    CreateCredentialHistoryMap
0x180003689  mov     ebx, eax
0x18000368b  lea     rdi, WPP_GLOBAL_Control
0x180003692  mov     rax, [rsp+2A0h+hObject]
0x180003697  test    rax, rax
0x18000369a  jnz     loc_18000375F
0x1800036a0  test    ebx, ebx
0x1800036a2  jz      loc_180003783
0x1800036a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036af  cmp     rcx, rdi
0x1800036b2  jz      short loc_1800036BE
0x1800036b4  test    byte ptr [rcx+1Ch], 1
0x1800036b8  jnz     loc_1800038A9
0x1800036be  mov     rcx, [rsp+2A0h+hMem]; hMem
0x1800036c3  test    rcx, rcx
0x1800036c6  jnz     loc_1800038E7
0x1800036cc  test    ebx, ebx
0x1800036ce  jnz     loc_180003863
0x1800036d4  movups  xmm0, xmmword ptr [rsi+4]
0x1800036d8  mov     ebx, r12d
0x1800036db  movdqu  xmmword ptr [r14], xmm0
0x1800036e0  mov     rcx, [rsp+2A0h+StringSid]; hMem
0x1800036e5  test    rcx, rcx
0x1800036e8  jnz     loc_1800038F1
0x1800036ee  mov     rcx, r15; hMem
0x1800036f1  call    DestroyCredentialHistoryMap
0x1800036f6  mov     eax, ebx
0x1800036f8  mov     rcx, [rbp+1A0h+var_30]
0x1800036ff  xor     rcx, rsp; StackCookie
0x180003702  call    __security_check_cookie
0x180003707  lea     r11, [rsp+2A0h+var_20]
0x18000370f  mov     rbx, [r11+40h]
0x180003713  mov     rsi, [r11+48h]
0x180003717  mov     rsp, r11
0x18000371a  pop     r15
0x18000371c  pop     r14
0x18000371e  pop     r12
0x180003720  pop     rdi
0x180003721  pop     rbp
0x180003722  retn
0x180003724  mov     ebx, 57h ; 'W'
0x180003729  mov     rcx, cs:WPP_GLOBAL_Control
0x180003730  lea     rdi, WPP_GLOBAL_Control
0x180003737  cmp     rcx, rdi
0x18000373a  jz      short loc_1800036EE
0x18000373c  test    byte ptr [rcx+1Ch], 1
0x180003740  jz      short loc_1800036EE
0x180003742  mov     dword ptr [rsp+2A0h+var_270], 22D8h
0x18000374a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180003751  mov     [rsp+2A0h+var_278], r8
0x180003756  mov     [rsp+2A0h+var_280], ebx
0x18000375a  jmp     loc_1800037F1
0x18000375f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003766  cmp     rcx, rdi
0x180003769  jnz     loc_18000380D
0x18000376f  mov     rcx, rax; hObject
0x180003772  call    cs:__imp_CloseHandle
0x180003779  nop     dword ptr [rax+rax+00h]
0x18000377e  jmp     loc_1800036A0
0x180003783  mov     rcx, [rsp+2A0h+hMem]; struct _CREDENTIAL_HISTORY_MAP *
0x180003788  xor     edx, edx; struct _CREDENTIAL_HISTORY *
0x18000378a  call    ?GetPreviousCredentialHistory@@YAPEAU_CREDENTIAL_HISTORY@@PEAU_CREDENTIAL_HISTORY_MAP@@PEAU1@@Z; GetPreviousCredentialHistory(_CREDENTIAL_HISTORY_MAP *,_CREDENTIAL_HISTORY *)
0x18000378f  test    rax, rax
0x180003792  jz      loc_1800038DD
0x180003798  mov     r15, [rsp+2A0h+hMem]
0x18000379d  mov     rsi, rax
0x1800037a0  mov     [rsp+2A0h+hMem], r12
0x1800037a5  jmp     loc_1800036BE
0x1800037aa  call    cs:__imp_GetLastError
0x1800037b1  nop     dword ptr [rax+rax+00h]
0x1800037b6  mov     ebx, eax
0x1800037b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037bf  lea     rdi, WPP_GLOBAL_Control
0x1800037c6  cmp     rcx, rdi
0x1800037c9  jz      loc_1800036E0
0x1800037cf  test    byte ptr [rcx+1Ch], 1
0x1800037d3  jz      loc_1800036E0
0x1800037d9  mov     dword ptr [rsp+2A0h+var_270], 22EAh
0x1800037e1  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800037e8  mov     [rsp+2A0h+var_278], r8
0x1800037ed  mov     [rsp+2A0h+var_280], eax
0x1800037f1  mov     rcx, [rcx+10h]
0x1800037f5  lea     r9, aDwret; "dwRet"
0x1800037fc  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180003803  call    WPP_SF_sDsd
0x180003808  jmp     loc_1800036E0
0x18000380d  test    byte ptr [rcx+1Ch], 4
0x180003811  jz      loc_18000376F
0x180003817  mov     rax, [rsp+2A0h+hMem]
0x18000381c  lea     r9, aNull_0; "NULL"
0x180003823  test    rax, rax
0x180003826  jz      short loc_18000382C
0x180003828  lea     r9, [rax+8]
0x18000382c  mov     rcx, [rcx+10h]
0x180003830  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180003837  mov     edx, 1Fh
0x18000383c  call    WPP_SF_S
0x180003841  mov     rax, [rsp+2A0h+hObject]
0x180003846  jmp     loc_18000376F
0x18000384b  call    cs:__imp_GetLastError
0x180003852  nop     dword ptr [rax+rax+00h]
0x180003857  mov     ebx, eax
0x180003859  mov     ecx, eax
0x18000385b  mov     r9d, 22E0h
0x180003861  jmp     short loc_18000386B
0x180003863  mov     r9d, 2304h
0x180003869  mov     ecx, ebx
0x18000386b  lea     rdx, aDwret; "dwRet"
0x180003872  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180003879  call    DebugTraceError
0x18000387e  jmp     loc_1800036E0
0x180003883  mov     r9d, 22F6h
0x180003889  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180003890  lea     rdx, aDwret; "dwRet"
0x180003897  mov     ecx, r10d
0x18000389a  call    DebugTraceError
0x18000389f  mov     ebx, 57h ; 'W'
0x1800038a4  jmp     loc_1800036E0
0x1800038a9  mov     rcx, [rcx+10h]
0x1800038ad  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800038b4  mov     dword ptr [rsp+2A0h+var_270], 791h
0x1800038bc  lea     r9, aDwerror; "dwError"
0x1800038c3  mov     [rsp+2A0h+var_278], rax
0x1800038c8  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x1800038cf  mov     [rsp+2A0h+var_280], ebx
0x1800038d3  call    WPP_SF_sDsd
0x1800038d8  jmp     loc_1800036BE
0x1800038dd  mov     ebx, 57h ; 'W'
0x1800038e2  jmp     loc_1800036BE
0x1800038e7  call    DestroyCredentialHistoryMap
0x1800038ec  jmp     loc_1800036CC
0x1800038f1  call    cs:__imp_LocalFree
0x1800038f8  nop     dword ptr [rax+rax+00h]
0x1800038fd  jmp     loc_1800036EE
```
