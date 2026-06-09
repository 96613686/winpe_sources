# QueryDerivedCredential

- ea: `0x180004e60`
- end: `0x180005651`
- name: `QueryDerivedCredential`
- size: `2033`
- prototype: `__int64 __fastcall(struct _GUID *, struct _LUID *, char, UCHAR *, ULONG cbInput, UCHAR *, unsigned int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005880`
- `0x18002955c`

## callees

- `0x1800033a8`
- `0x180003b98`
- `0x1800045c0`
- `0x180004e60`
- `0x180007f10`
- `0x18000a5d0`
- `0x18000df80`
- `0x180011710`
- `0x180012710`
- `0x180012838`
- `0x18001444c`
- `0x1800146ac`
- `0x18001c340`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x180029ed4`
- `0x180029f10`
- `0x180029f68`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800050bf`
- `ntdll!RtlNtStatusToDosError` at `0x1800055d5`
- `ntdll!RtlNtStatusToDosError` at `0x1800055d5`

## string_xrefs

- `0x180004fad`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180005005`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x1800050e4`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x18000514b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
__int64 __fastcall QueryDerivedCredential(
        struct _GUID *a1,
        struct _LUID *a2,
        char a3,
        UCHAR *a4,
        ULONG cbInput,
        UCHAR *a6,
        unsigned int *a7)
{
  struct _GUID *v10; // r12
  struct _CREDENTIAL_HISTORY *v11; // r13
  __int64 v12; // r8
  __int64 v13; // rcx
  unsigned int CurrentDerivedCredential; // eax
  unsigned int v15; // edi
  int v16; // edx
  int v17; // edx
  HANDLE v18; // rax
  const wchar_t *v19; // r9
  struct _CREDENTIAL_HISTORY *PreviousCredentialHistory; // rax
  __int64 v21; // r14
  int v22; // ecx
  unsigned int v23; // eax
  struct _CREDENTIAL_HISTORY *v24; // rax
  __int64 v25; // r9
  int v26; // ecx
  unsigned int v27; // eax
  int v28; // r8d
  __int64 v29; // rcx
  __int64 v30; // r12
  struct _CREDENTIAL_HISTORY *v31; // rdi
  unsigned int CurrentDerivedCredentialWithRetry; // eax
  unsigned __int8 *v33; // rcx
  __int64 v34; // rax
  unsigned __int8 *v35; // rcx
  __int64 v36; // rax
  unsigned __int8 *v37; // rcx
  unsigned int v38; // eax
  unsigned __int8 *v39; // rcx
  __int64 v40; // rcx
  unsigned __int8 *v41; // rax
  unsigned __int8 *v42; // rax
  HLOCAL hMem; // [rsp+48h] [rbp-520h] BYREF
  struct _CREDENTIAL_HISTORY *v45; // [rsp+50h] [rbp-518h]
  unsigned int *v46; // [rsp+58h] [rbp-510h]
  struct _LUID *v47; // [rsp+60h] [rbp-508h]
  PUCHAR v48; // [rsp+68h] [rbp-500h]
  HANDLE hObject; // [rsp+70h] [rbp-4F8h] BYREF
  PUCHAR v50; // [rsp+78h] [rbp-4F0h]
  HLOCAL v51; // [rsp+80h] [rbp-4E8h]
  int v52; // [rsp+88h] [rbp-4E0h]
  unsigned __int8 *v53; // [rsp+90h] [rbp-4D8h]
  __int64 v54; // [rsp+98h] [rbp-4D0h]
  unsigned __int8 *v55; // [rsp+A0h] [rbp-4C8h]
  __int64 v56; // [rsp+A8h] [rbp-4C0h]
  struct _GUID *v57; // [rsp+B0h] [rbp-4B8h]
  unsigned __int8 Src[24]; // [rsp+B8h] [rbp-4B0h] BYREF
  unsigned __int8 v59[24]; // [rsp+D0h] [rbp-498h] BYREF
  UCHAR pbOutput[24]; // [rsp+E8h] [rbp-480h] BYREF
  _WORD pbInput[264]; // [rsp+100h] [rbp-468h] BYREF
  _BYTE v62[528]; // [rsp+310h] [rbp-258h] BYREF

  v50 = a4;
  v47 = a2;
  v10 = a1;
  v57 = a1;
  v48 = a6;
  v46 = a7;
  v11 = 0;
  v45 = 0;
  v51 = 0;
  memset_0(v62, 0, 0x20Au);
  v13 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF__guid_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, v12, v10, a2->LowPart, a2->HighPart);
    v13 = WPP_GLOBAL_Control;
  }
  if ( (a3 & 2) != 0 && !v10 )
  {
    if ( (_UNKNOWN *)v13 != &WPP_GLOBAL_Control && (*(_BYTE *)(v13 + 28) & 4) != 0 )
      WPP_SF_dd(*(_QWORD *)(v13 + 16), 20, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, a2->LowPart, a2->HighPart);
    CurrentDerivedCredential = RetrieveCurrentDerivedCredential(v13, a2, 0, a3 & 1, a4, cbInput, v48, v46);
    v15 = CurrentDerivedCredential;
    if ( CurrentDerivedCredential )
      DebugTraceError(
        CurrentDerivedCredential,
        "dwLastError",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
        582);
    return v15;
  }
  v15 = PRGetProfilePath(0, v62);
  if ( v15 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v16,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        v15,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
        92);
    return v15;
  }
  hObject = 0;
  hMem = 0;
  v15 = CreateCredentialHistoryMap(0, v62, 0, 0, 0, &hMem, &hObject);
  v18 = hObject;
  if ( hObject )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v19 = L"NULL";
      if ( hMem )
        v19 = (const wchar_t *)((char *)hMem + 8);
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids, v19);
      v18 = hObject;
    }
    CloseHandle(v18);
  }
  if ( v15 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v17,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwError",
        v15,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
        145);
  }
  else
  {
    PreviousCredentialHistory = GetPreviousCredentialHistory((struct _CREDENTIAL_HISTORY_MAP *)hMem, 0);
    if ( PreviousCredentialHistory )
    {
      v11 = PreviousCredentialHistory;
      v45 = PreviousCredentialHistory;
      v51 = hMem;
      hMem = 0;
    }
    else
    {
      v15 = 87;
    }
  }
  if ( hMem )
    DestroyCredentialHistoryMap(hMem);
  if ( v15 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v17,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        v15,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
        104);
  }
  else
  {
    LODWORD(hMem) = 1;
    if ( (a3 & 2) == 0 )
    {
      v21 = 20;
      while ( v11
           && (!v10
            || *(_QWORD *)((char *)v11 + 4) != *(_QWORD *)&v10->Data1
            || *(_QWORD *)((char *)v11 + 12) != *(_QWORD *)v10->Data4) )
      {
        v24 = GetPreviousCredentialHistory((struct _CREDENTIAL_HISTORY_MAP *)v51, v11);
        v11 = v24;
        if ( !v24 )
        {
          if ( v10 )
          {
            v15 = -2146893821;
            v25 = 693;
            goto LABEL_61;
          }
          v15 = 0;
          goto LABEL_51;
        }
        if ( !(unsigned int)GetTextualSid((char *)v24 + 68, pbInput, 261) )
        {
          v15 = 87;
          v25 = 716;
          goto LABEL_61;
        }
        v30 = -1;
        do
          ++v30;
        while ( pbInput[v30] );
        if ( (_DWORD)hMem )
        {
          v31 = v45;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            WPP_SF__guid__guid_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, v28, (_DWORD)v45 + 4, (__int64)v11 + 4);
          CurrentDerivedCredentialWithRetry = RetrieveCurrentDerivedCredentialWithRetry(
                                                (int)pbOutput,
                                                v47,
                                                (struct _GUID *)((char *)v31 + 4),
                                                *((_DWORD *)v11 + 6) & 1,
                                                (unsigned __int8 *)pbInput,
                                                2 * v30 + 2,
                                                pbOutput,
                                                v46);
          v15 = CurrentDerivedCredentialWithRetry;
          if ( CurrentDerivedCredentialWithRetry )
            DebugTraceError(
              CurrentDerivedCredentialWithRetry,
              "dwLastError",
              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
              746);
          LODWORD(hMem) = 0;
          v52 = 0;
        }
        else
        {
          v33 = v59;
          if ( (*((_DWORD *)v11 + 6) & 1) != 0 )
            v33 = Src;
          DeriveWithHMAC_SHA1(v33, 0x14u, (PUCHAR)pbInput, 2 * v30 + 2, pbOutput);
          v34 = 20;
          v54 = 20;
          v35 = Src;
          v53 = Src;
          while ( v34 )
          {
            *v35++ = 0;
            v53 = v35;
            v54 = --v34;
          }
          v36 = 20;
          v56 = 20;
          v37 = v59;
          v55 = v59;
          while ( v36 )
          {
            *v37++ = 0;
            v55 = v37;
            v56 = --v36;
          }
        }
        if ( v15 )
        {
          v25 = 773;
LABEL_61:
          v29 = v15;
LABEL_62:
          DebugTraceError(v29, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v25);
LABEL_51:
          v11 = v45;
          break;
        }
        v38 = DecryptCredentialHistory(v11, pbOutput, Src, v59);
        v15 = v38;
        if ( v38 )
        {
          v25 = 790;
          v29 = v38;
          goto LABEL_62;
        }
        v45 = v11;
        hObject = v11;
        v10 = v57;
      }
      if ( !v15 )
      {
        if ( (_DWORD)hMem )
        {
          v26 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            WPP_SF__guid_(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              23,
              WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids,
              (char *)v11 + 4);
          v27 = RetrieveCurrentDerivedCredentialWithRetry(
                  v26,
                  v47,
                  (struct _GUID *)((char *)v11 + 4),
                  a3 & 1,
                  v50,
                  cbInput,
                  v48,
                  v46);
          v15 = v27;
          if ( v27 )
            DebugTraceError(v27, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 846);
        }
        else
        {
          v39 = v59;
          if ( (a3 & 1) != 0 )
            v39 = Src;
          DeriveWithHMAC_SHA1(v39, 0x14u, v50, cbInput, v48);
        }
      }
      goto LABEL_88;
    }
    *v10 = *(struct _GUID *)((char *)v11 + 4);
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF__guid_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, v47, v10, v47->LowPart, v47->HighPart);
    v23 = RetrieveCurrentDerivedCredentialWithRetry(v22, v47, v10, a3 & 1, v50, cbInput, v48, v46);
    v15 = v23;
    if ( v23 )
      DebugTraceError(v23, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", 655);
  }
  v21 = 20;
LABEL_88:
  v40 = 20;
  v41 = Src;
  do
  {
    *v41++ = 0;
    --v40;
  }
  while ( v40 );
  v42 = v59;
  do
  {
    *v42++ = 0;
    --v21;
  }
  while ( v21 );
  if ( v51 )
    DestroyCredentialHistoryMap(v51);
  return v15;
}

```

## disassembly

```asm
0x180004e60  push    rbx
0x180004e62  push    rsi
0x180004e63  push    rdi
0x180004e64  push    r12
0x180004e66  push    r13
0x180004e68  push    r14
0x180004e6a  push    r15
0x180004e6c  sub     rsp, 530h
0x180004e73  mov     rax, cs:__security_cookie
0x180004e7a  xor     rax, rsp
0x180004e7d  mov     [rsp+568h+var_48], rax
0x180004e85  mov     rsi, r9
0x180004e88  mov     [rsp+568h+var_4F0], r9
0x180004e8d  mov     r15d, r8d
0x180004e90  mov     rdi, rdx
0x180004e93  mov     [rsp+568h+var_508], rdx
0x180004e98  mov     r12, rcx
0x180004e9b  mov     [rsp+568h+var_4B8], rcx
0x180004ea3  mov     rax, [rsp+568h+arg_28]
0x180004eab  mov     [rsp+568h+var_500], rax
0x180004eb0  mov     rax, [rsp+568h+arg_30]
0x180004eb8  mov     [rsp+568h+var_510], rax
0x180004ebd  xor     ebx, ebx
0x180004ebf  mov     r13d, ebx
0x180004ec2  mov     [rsp+568h+var_518], rbx
0x180004ec7  mov     [rsp+568h+var_4E8], rbx
0x180004ecf  xor     edx, edx; Val
0x180004ed1  mov     r8d, 20Ah; Size
0x180004ed7  lea     rcx, [rsp+568h+var_258]; void *
0x180004edf  call    memset_0
0x180004ee4  lea     rax, WPP_GLOBAL_Control
0x180004eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ef2  cmp     rcx, rax
0x180004ef5  jz      short loc_180004F27
0x180004ef7  test    byte ptr [rcx+1Ch], 4
0x180004efb  jz      short loc_180004F27
0x180004efd  lea     edx, [rbx+13h]
0x180004f00  mov     eax, [rdi+4]
0x180004f03  mov     [rsp+568h+var_540], eax
0x180004f07  mov     eax, [rdi]
0x180004f09  mov     dword ptr [rsp+568h+pbOutput], eax
0x180004f0d  mov     r9, r12
0x180004f10  mov     rcx, [rcx+10h]
0x180004f14  call    WPP_SF__guid_dd
0x180004f19  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f20  lea     rax, WPP_GLOBAL_Control
0x180004f27  mov     r14d, r15d
0x180004f2a  and     r14d, 2
0x180004f2e  jz      loc_180004FC7
0x180004f34  test    r12, r12
0x180004f37  jnz     loc_180004FC7
0x180004f3d  cmp     rcx, rax
0x180004f40  jz      short loc_180004F67
0x180004f42  test    byte ptr [rcx+1Ch], 4
0x180004f46  jz      short loc_180004F67
0x180004f48  lea     edx, [r12+14h]
0x180004f4d  mov     eax, [rdi+4]
0x180004f50  mov     dword ptr [rsp+568h+pbOutput], eax
0x180004f54  mov     r9d, [rdi]
0x180004f57  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180004f5e  mov     rcx, [rcx+10h]
0x180004f62  call    WPP_SF_dd
0x180004f67  and     r15d, 1
0x180004f6b  mov     rax, [rsp+568h+var_510]
0x180004f70  mov     [rsp+568h+var_530], rax; unsigned int *
0x180004f75  mov     rax, [rsp+568h+var_500]
0x180004f7a  mov     [rsp+568h+var_538], rax; unsigned __int8 *
0x180004f7f  mov     eax, [rsp+568h+cbInput]
0x180004f86  mov     [rsp+568h+var_540], eax; cbInput
0x180004f8a  mov     [rsp+568h+pbOutput], rsi; unsigned __int8 *
0x180004f8f  mov     r9d, r15d; int
0x180004f92  xor     r8d, r8d; struct _GUID *
0x180004f95  mov     rdx, rdi; struct _LUID *
0x180004f98  call    ?RetrieveCurrentDerivedCredential@@YAKHPEAU_LUID@@PEAU_GUID@@HPEAEKQEAEPEAK@Z; RetrieveCurrentDerivedCredential(int,_LUID *,_GUID *,int,uchar *,ulong,uchar * const,ulong *)
0x180004f9d  mov     edi, eax
0x180004f9f  test    eax, eax
0x180004fa1  jz      loc_18000562B
0x180004fa7  mov     r9d, 246h
0x180004fad  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180004fb4  lea     rdx, aDwlasterror; "dwLastError"
0x180004fbb  mov     ecx, eax
0x180004fbd  call    DebugTraceError
0x180004fc2  jmp     loc_18000562B
0x180004fc7  lea     rdx, [rsp+568h+var_258]
0x180004fcf  xor     ecx, ecx
0x180004fd1  call    PRGetProfilePath
0x180004fd6  mov     edi, eax
0x180004fd8  test    eax, eax
0x180004fda  jz      short loc_180005031
0x180004fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fe3  lea     rax, WPP_GLOBAL_Control
0x180004fea  cmp     rcx, rax
0x180004fed  jz      loc_18000562B
0x180004ff3  test    byte ptr [rcx+1Ch], 1
0x180004ff7  jz      loc_18000562B
0x180004ffd  mov     dword ptr [rsp+568h+var_538], 25Ch
0x180005005  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000500c  mov     qword ptr [rsp+568h+var_540], rsi
0x180005011  mov     dword ptr [rsp+568h+pbOutput], edi
0x180005015  lea     r9, aDwlasterror; "dwLastError"
0x18000501c  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180005023  mov     rcx, [rcx+10h]
0x180005027  call    WPP_SF_sDsd
0x18000502c  jmp     loc_18000562B
0x180005031  mov     [rsp+568h+hObject], rbx
0x180005036  mov     [rsp+568h+hMem], rbx
0x18000503b  lea     rax, [rsp+568h+hObject]
0x180005040  mov     [rsp+568h+var_538], rax
0x180005045  lea     rax, [rsp+568h+hMem]
0x18000504a  mov     qword ptr [rsp+568h+var_540], rax
0x18000504f  mov     dword ptr [rsp+568h+pbOutput], ebx
0x180005053  xor     r9d, r9d
0x180005056  xor     r8d, r8d
0x180005059  lea     rdx, [rsp+568h+var_258]
0x180005061  xor     ecx, ecx
0x180005063  call    CreateCredentialHistoryMap
0x180005068  mov     edi, eax
0x18000506a  mov     rax, [rsp+568h+hObject]
0x18000506f  test    rax, rax
0x180005072  jz      short loc_1800050CD
0x180005074  mov     rcx, cs:WPP_GLOBAL_Control
0x18000507b  lea     rsi, WPP_GLOBAL_Control
0x180005082  cmp     rcx, rsi
0x180005085  jz      short loc_1800050BC
0x180005087  test    byte ptr [rcx+1Ch], 4
0x18000508b  jz      short loc_1800050BC
0x18000508d  mov     rax, [rsp+568h+hMem]
0x180005092  test    rax, rax
0x180005095  lea     r9, aNull_0; "NULL"
0x18000509c  jz      short loc_1800050A2
0x18000509e  lea     r9, [rax+8]
0x1800050a2  mov     edx, 1Fh
0x1800050a7  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x1800050ae  mov     rcx, [rcx+10h]
0x1800050b2  call    WPP_SF_S
0x1800050b7  mov     rax, [rsp+568h+hObject]
0x1800050bc  mov     rcx, rax; hObject
0x1800050bf  call    cs:__imp_CloseHandle
0x1800050c6  nop     dword ptr [rax+rax+00h]
0x1800050cb  jmp     short loc_1800050D4
0x1800050cd  lea     rsi, WPP_GLOBAL_Control
0x1800050d4  test    edi, edi
0x1800050d6  jz      short loc_18000511B
0x1800050d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050df  cmp     rcx, rsi
0x1800050e2  jz      short loc_18000514B
0x1800050e4  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800050eb  test    byte ptr [rcx+1Ch], 1
0x1800050ef  jz      short loc_180005152
0x1800050f1  mov     dword ptr [rsp+568h+var_538], 791h
0x1800050f9  mov     qword ptr [rsp+568h+var_540], rsi
0x1800050fe  mov     dword ptr [rsp+568h+pbOutput], edi
0x180005102  lea     r9, aDwerror; "dwError"
0x180005109  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180005110  mov     rcx, [rcx+10h]
0x180005114  call    WPP_SF_sDsd
0x180005119  jmp     short loc_180005152
0x18000511b  xor     edx, edx; struct _CREDENTIAL_HISTORY *
0x18000511d  mov     rcx, [rsp+568h+hMem]; struct _CREDENTIAL_HISTORY_MAP *
0x180005122  call    ?GetPreviousCredentialHistory@@YAPEAU_CREDENTIAL_HISTORY@@PEAU_CREDENTIAL_HISTORY_MAP@@PEAU1@@Z; GetPreviousCredentialHistory(_CREDENTIAL_HISTORY_MAP *,_CREDENTIAL_HISTORY *)
0x180005127  test    rax, rax
0x18000512a  jnz     short loc_180005131
0x18000512c  lea     edi, [rax+57h]
0x18000512f  jmp     short loc_18000514B
0x180005131  mov     r13, rax
0x180005134  mov     [rsp+568h+var_518], rax
0x180005139  mov     rax, [rsp+568h+hMem]
0x18000513e  mov     [rsp+568h+var_4E8], rax
0x180005146  mov     [rsp+568h+hMem], rbx
0x18000514b  lea     rsi, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180005152  mov     rcx, [rsp+568h+hMem]; hMem
0x180005157  test    rcx, rcx
0x18000515a  jz      short loc_180005161
0x18000515c  call    DestroyCredentialHistoryMap
0x180005161  test    edi, edi
0x180005163  jz      short loc_1800051B1
0x180005165  mov     rcx, cs:WPP_GLOBAL_Control
0x18000516c  lea     rax, WPP_GLOBAL_Control
0x180005173  cmp     rcx, rax
0x180005176  jz      short loc_1800051A6
0x180005178  test    byte ptr [rcx+1Ch], 1
0x18000517c  jz      short loc_1800051A6
0x18000517e  mov     dword ptr [rsp+568h+var_538], 268h
0x180005186  mov     qword ptr [rsp+568h+var_540], rsi
0x18000518b  mov     dword ptr [rsp+568h+pbOutput], edi
0x18000518f  lea     r9, aDwlasterror; "dwLastError"
0x180005196  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000519d  mov     rcx, [rcx+10h]
0x1800051a1  call    WPP_SF_sDsd
0x1800051a6  mov     r14d, 14h
0x1800051ac  jmp     loc_1800055ED
0x1800051b1  mov     dword ptr [rsp+568h+hMem], 1
0x1800051b9  test    r14d, r14d
0x1800051bc  jz      loc_18000526E
0x1800051c2  movups  xmm0, xmmword ptr [r13+4]
0x1800051c7  movdqu  xmmword ptr [r12], xmm0
0x1800051cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051d4  lea     rax, WPP_GLOBAL_Control
0x1800051db  cmp     rcx, rax
0x1800051de  jz      short loc_18000520B
0x1800051e0  test    byte ptr [rcx+1Ch], 4
0x1800051e4  jz      short loc_18000520B
0x1800051e6  mov     edx, 15h
0x1800051eb  mov     r8, [rsp+568h+var_508]
0x1800051f0  mov     eax, [r8+4]
0x1800051f4  mov     [rsp+568h+var_540], eax
0x1800051f8  mov     eax, [r8]
0x1800051fb  mov     dword ptr [rsp+568h+pbOutput], eax
0x1800051ff  mov     r9, r12
0x180005202  mov     rcx, [rcx+10h]
0x180005206  call    WPP_SF__guid_dd
0x18000520b  and     r15d, 1
0x18000520f  mov     rax, [rsp+568h+var_510]
0x180005214  mov     [rsp+568h+var_530], rax; unsigned int *
0x180005219  mov     rax, [rsp+568h+var_500]
0x18000521e  mov     [rsp+568h+var_538], rax; unsigned __int8 *
0x180005223  mov     eax, [rsp+568h+cbInput]
0x18000522a  mov     [rsp+568h+var_540], eax; unsigned int
0x18000522e  mov     rax, [rsp+568h+var_4F0]
0x180005233  mov     [rsp+568h+pbOutput], rax; unsigned __int8 *
0x180005238  mov     r9d, r15d; int
0x18000523b  mov     r8, r12; struct _GUID *
0x18000523e  mov     rdx, [rsp+568h+var_508]; struct _LUID *
0x180005243  call    ?RetrieveCurrentDerivedCredentialWithRetry@@YAKHPEAU_LUID@@PEAU_GUID@@HPEAEKQEAEPEAK@Z; RetrieveCurrentDerivedCredentialWithRetry(int,_LUID *,_GUID *,int,uchar *,ulong,uchar * const,ulong *)
0x180005248  mov     edi, eax
0x18000524a  test    eax, eax
0x18000524c  jz      loc_1800051A6
0x180005252  mov     r9d, 28Fh
0x180005258  mov     r8, rsi
0x18000525b  lea     rdx, aDwlasterror; "dwLastError"
0x180005262  mov     ecx, eax
0x180005264  call    DebugTraceError
0x180005269  jmp     loc_1800051A6
0x18000526e  mov     r14d, 14h
0x180005274  test    r13, r13
0x180005277  jz      short loc_1800052CF
0x180005279  test    r12, r12
0x18000527c  jz      short loc_180005293
0x18000527e  mov     rax, [r13+4]
0x180005282  cmp     rax, [r12]
0x180005286  jnz     short loc_180005293
0x180005288  mov     rax, [r13+0Ch]
0x18000528c  cmp     rax, [r12+8]
0x180005291  jz      short loc_1800052CF
0x180005293  mov     rdx, r13; struct _CREDENTIAL_HISTORY *
0x180005296  mov     rcx, [rsp+568h+var_4E8]; struct _CREDENTIAL_HISTORY_MAP *
0x18000529e  call    ?GetPreviousCredentialHistory@@YAPEAU_CREDENTIAL_HISTORY@@PEAU_CREDENTIAL_HISTORY_MAP@@PEAU1@@Z; GetPreviousCredentialHistory(_CREDENTIAL_HISTORY_MAP *,_CREDENTIAL_HISTORY *)
0x1800052a3  mov     r13, rax
0x1800052a6  test    rax, rax
0x1800052a9  jnz     loc_180005379
0x1800052af  test    r12, r12
0x1800052b2  jz      short loc_1800052C4
0x1800052b4  mov     edi, 80090003h
0x1800052b9  mov     r9d, 2B5h
0x1800052bf  jmp     loc_18000539D
0x1800052c4  mov     edi, ebx
0x1800052c6  mov     [rsp+568h+var_528], ebx
0x1800052ca  mov     r13, [rsp+568h+var_518]
0x1800052cf  test    edi, edi
0x1800052d1  jnz     loc_1800055D1
0x1800052d7  cmp     dword ptr [rsp+568h+hMem], ebx
0x1800052db  jz      loc_18000559A
0x1800052e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052e8  lea     rax, WPP_GLOBAL_Control
0x1800052ef  cmp     rcx, rax
0x1800052f2  jz      short loc_180005311
0x1800052f4  test    byte ptr [rcx+1Ch], 4
0x1800052f8  jz      short loc_180005311
0x1800052fa  lea     r9, [r13+4]
0x1800052fe  lea     edx, [rdi+17h]
0x180005301  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180005308  mov     rcx, [rcx+10h]
0x18000530c  call    WPP_SF__guid_
0x180005311  and     r15d, 1
0x180005315  lea     r8, [r13+4]; struct _GUID *
0x180005319  mov     rax, [rsp+568h+var_510]
0x18000531e  mov     [rsp+568h+var_530], rax; unsigned int *
0x180005323  mov     rax, [rsp+568h+var_500]
0x180005328  mov     [rsp+568h+var_538], rax; unsigned __int8 *
0x18000532d  mov     eax, [rsp+568h+cbInput]
0x180005334  mov     [rsp+568h+var_540], eax; unsigned int
0x180005338  mov     rax, [rsp+568h+var_4F0]
0x18000533d  mov     [rsp+568h+pbOutput], rax; unsigned __int8 *
0x180005342  mov     r9d, r15d; int
0x180005345  mov     rdx, [rsp+568h+var_508]; struct _LUID *
0x18000534a  call    ?RetrieveCurrentDerivedCredentialWithRetry@@YAKHPEAU_LUID@@PEAU_GUID@@HPEAEKQEAEPEAK@Z; RetrieveCurrentDerivedCredentialWithRetry(int,_LUID *,_GUID *,int,uchar *,ulong,uchar * const,ulong *)
0x18000534f  mov     edi, eax
0x180005351  mov     [rsp+568h+var_528], eax
0x180005355  test    eax, eax
0x180005357  jz      loc_1800055D1
0x18000535d  mov     r9d, 34Eh
0x180005363  mov     r8, rsi
0x180005366  lea     rdx, aDwlasterror; "dwLastError"
0x18000536d  mov     ecx, eax
0x18000536f  call    DebugTraceError
0x180005374  jmp     loc_1800055D1
0x180005379  lea     rcx, [rax+44h]
0x18000537d  mov     r8d, 105h
0x180005383  lea     rdx, [rsp+568h+pbInput]
0x18000538b  call    GetTextualSid
  ... truncated ...
```
