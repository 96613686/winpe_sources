# CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)

- ea: `0x1400a8f14`
- end: `0x1400a9492`
- name: `?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z`
- size: `1406`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x140020b08`
- `0x1400a8f14`
- `0x1400ab334`
- `0x1400b4e74`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x1400947cc`
- `0x1400a8d00`
- `0x1400a8f14`
- `0x1400a9de4`
- `0x1400aa3e8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400a936e`
- `KERNEL32!LocalFree` at `0x1400a936e`
- `KERNEL32!GetLastError` at `0x1400a9188`
- `KERNEL32!GetLastError` at `0x1400a92c7`
- `KERNEL32!GetLastError` at `0x1400a93be`
- `KERNEL32!GetLastError` at `0x1400a942a`
- `KERNEL32!GetLastError` at `0x1400a9188`
- `KERNEL32!GetLastError` at `0x1400a92c7`
- `KERNEL32!GetLastError` at `0x1400a93be`
- `KERNEL32!GetLastError` at `0x1400a942a`
- `ADVAPI32!CredDeleteW` at `0x1400a917e`
- `ADVAPI32!CredDeleteW` at `0x1400a92ad`
- `ADVAPI32!CredDeleteW` at `0x1400a93b4`
- `ADVAPI32!CredDeleteW` at `0x1400a917e`
- `ADVAPI32!CredDeleteW` at `0x1400a92ad`
- `ADVAPI32!CredDeleteW` at `0x1400a93b4`
- `ADVAPI32!CredFree` at `0x1400a937e`
- `ADVAPI32!CredFree` at `0x1400a937e`
- `ADVAPI32!CredReadW` at `0x1400a9335`
- `ADVAPI32!CredReadW` at `0x1400a9335`

## string_xrefs

- `0x1400a9294`: `CreateSPN failed`
- `0x1400a8fb2`: `DeleteSavedCreds(CRED_TYPE_GENERIC) failed`
- `0x1400a9486`: `CredRead(Server) failed`
- `0x1400a9040`: `DeleteSavedCreds(CRED_TYPE_DOMAIN_PASSWORD) failed`
- `0x1400a91f0`: `CredDelete(Server,CRED_TYPE_DOMAIN_EXTENDED) failed`
- `0x1400a9319`: `CredDelete(SPN) failed`
- `0x1400a941e`: `CredDelete(Server) failed`

## pseudocode

```c
__int64 __fastcall CTSCredManAssistant::DeleteSavedCreds(
        CTSCredManAssistant *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        unsigned int a5)
{
  unsigned int v8; // r12d
  signed int v9; // eax
  signed int TargetForExtednedCredential; // ebx
  signed int v11; // esi
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  signed int v15; // eax
  signed int v16; // ebp
  signed int v17; // eax
  BOOL v18; // ecx
  unsigned int v19; // eax
  int v20; // edx
  const char *v21; // rcx
  signed int LastError; // eax
  BOOL v23; // esi
  int v24; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v26; // eax
  int v27; // r12d
  signed int v29; // eax
  int v30; // eax
  signed int v31; // eax
  PCREDENTIALW Credential; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR TargetName; // [rsp+80h] [rbp+18h] BYREF

  TargetName = 0;
  Credential = 0;
  if ( a4 )
  {
    if ( a4 == 6 )
    {
      if ( !(unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater() )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
        TargetForExtednedCredential = -2147023728;
        goto LABEL_79;
      }
      TargetForExtednedCredential = CTSCredManAssistant::GetTargetForExtednedCredential(
                                      this,
                                      a2,
                                      (unsigned __int16 **)&TargetName);
      if ( TargetForExtednedCredential < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 34;
          v21 = "GetTargetForExtednedCredential failed";
LABEL_38:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v20,
            (unsigned int)WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
            v19,
            (__int64)v21,
            TargetForExtednedCredential);
          goto LABEL_77;
        }
        goto LABEL_77;
      }
      if ( !CredDeleteW(TargetName, 6u, 0) )
      {
        LastError = GetLastError();
        TargetForExtednedCredential = LastError;
        if ( LastError > 0 )
          TargetForExtednedCredential = (unsigned __int16)LastError | 0x80070000;
      }
      v23 = TargetForExtednedCredential != -2147023728;
      v24 = 0;
      if ( TargetForExtednedCredential != -2147023728 )
        v24 = TargetForExtednedCredential;
      TargetForExtednedCredential = v24;
      if ( v24 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 35;
          v21 = "CredDelete(Server,CRED_TYPE_DOMAIN_EXTENDED) failed";
          goto LABEL_38;
        }
LABEL_77:
        if ( TargetName )
          LocalFree((HLOCAL)TargetName);
        goto LABEL_79;
      }
    }
    else
    {
      TargetForExtednedCredential = CTSCredManAssistant::CreateSPN(this, a2, a3, (unsigned __int16 **)&TargetName);
      if ( TargetForExtednedCredential < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 37;
          v21 = "CreateSPN failed";
          goto LABEL_38;
        }
        goto LABEL_77;
      }
      v23 = 1;
      if ( !CredDeleteW(TargetName, a4, 0) )
      {
        v26 = GetLastError();
        TargetForExtednedCredential = v26;
        if ( v26 > 0 )
          TargetForExtednedCredential = (unsigned __int16)v26 | 0x80070000;
        if ( TargetForExtednedCredential == -2147023728 )
          goto LABEL_64;
      }
      if ( TargetForExtednedCredential == -2147024809 )
      {
LABEL_64:
        TargetForExtednedCredential = 0;
        v27 = 0;
      }
      else
      {
        if ( TargetForExtednedCredential < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            v20 = 38;
            v21 = "CredDelete(SPN) failed";
            goto LABEL_38;
          }
          goto LABEL_77;
        }
        v27 = 1;
      }
      if ( CredReadW(a2, a4, 0, &Credential) )
      {
        if ( (unsigned int)IsHomeGroupCredential(Credential->UserName) )
        {
          v23 = 0;
        }
        else if ( (a5 & 1) == 0 || a4 != 2 )
        {
          if ( !CredDeleteW(a2, a4, 0) )
          {
            v29 = GetLastError();
            TargetForExtednedCredential = v29;
            if ( v29 > 0 )
              TargetForExtednedCredential = (unsigned __int16)v29 | 0x80070000;
          }
          v23 = TargetForExtednedCredential != -2147023728;
          v30 = 0;
          if ( TargetForExtednedCredential != -2147023728 )
            v30 = TargetForExtednedCredential;
          TargetForExtednedCredential = v30;
          if ( v30 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 39;
              v21 = "CredDelete(Server) failed";
              goto LABEL_38;
            }
            goto LABEL_77;
          }
        }
      }
      else
      {
        v31 = GetLastError();
        if ( v31 > 0 )
          v31 = (unsigned __int16)v31 | 0x80070000;
        v23 = v31 != -2147023728;
        TargetForExtednedCredential = 0;
        if ( v31 != -2147023728 )
          TargetForExtednedCredential = v31;
        if ( TargetForExtednedCredential < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            v20 = 40;
            v21 = "CredRead(Server) failed";
            goto LABEL_38;
          }
          goto LABEL_77;
        }
      }
      if ( v27 )
        goto LABEL_77;
    }
    if ( !v23 )
      TargetForExtednedCredential = -2147023728;
    goto LABEL_77;
  }
  v8 = a5;
  v9 = CTSCredManAssistant::DeleteSavedCreds(this, a2, L"TERMSRV", 1u, a5);
  TargetForExtednedCredential = 0;
  v11 = v9;
  if ( v9 != -2147023728 )
    TargetForExtednedCredential = v9;
  if ( TargetForExtednedCredential >= 0 )
  {
    v15 = CTSCredManAssistant::DeleteSavedCreds(this, a2, L"TERMSRV", 2u, v8);
    TargetForExtednedCredential = 0;
    v16 = v15;
    if ( v15 != -2147023728 )
      TargetForExtednedCredential = v15;
    if ( TargetForExtednedCredential < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_79;
      }
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 32;
      goto LABEL_17;
    }
    if ( (unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater() )
    {
      v17 = CTSCredManAssistant::DeleteSavedCreds(this, a2, L"TERMSRV", 6u, v8);
      v18 = v17 != -2147023728;
      TargetForExtednedCredential = 0;
      if ( v17 != -2147023728 )
        TargetForExtednedCredential = v17;
      if ( TargetForExtednedCredential < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_79;
        }
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 33;
LABEL_17:
        v14 = "DeleteSavedCreds(CRED_TYPE_DOMAIN_PASSWORD) failed";
        goto LABEL_9;
      }
    }
    else
    {
      TargetForExtednedCredential = 0;
      v18 = 0;
    }
    if ( v11 == -2147023728 && v16 == -2147023728 && !v18 )
      TargetForExtednedCredential = -2147023728;
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 31;
    v14 = "DeleteSavedCreds(CRED_TYPE_GENERIC) failed";
LABEL_9:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (unsigned int)WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
      v12,
      (__int64)v14,
      TargetForExtednedCredential);
  }
LABEL_79:
  if ( Credential )
    CredFree(Credential);
  return (unsigned int)TargetForExtednedCredential;
}

```

## disassembly

```asm
0x1400a8f14  mov     rax, rsp
0x1400a8f17  mov     [rax+8], rbx
0x1400a8f1b  mov     [rax+10h], rbp
0x1400a8f1f  mov     [rax+18h], r8
0x1400a8f23  push    rsi
0x1400a8f24  push    rdi
0x1400a8f25  push    r12
0x1400a8f27  push    r14
0x1400a8f29  push    r15
0x1400a8f2b  sub     rsp, 40h
0x1400a8f2f  mov     qword ptr [rax+18h], 0
0x1400a8f37  mov     ebp, r9d
0x1400a8f3a  mov     qword ptr [rax-38h], 0
0x1400a8f42  mov     r15, rdx
0x1400a8f45  mov     r14, rcx
0x1400a8f48  test    r9d, r9d
0x1400a8f4b  jnz     loc_1400A90DE
0x1400a8f51  mov     r12d, [rsp+68h+arg_20]
0x1400a8f59  lea     r9d, [rbp+1]; unsigned int
0x1400a8f5d  lea     r8, aTermsrv; "TERMSRV"
0x1400a8f64  mov     [rax-48h], r12d
0x1400a8f68  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1400a8f6d  xor     ebx, ebx
0x1400a8f6f  mov     edi, 80070490h
0x1400a8f74  cmp     eax, edi
0x1400a8f76  mov     esi, eax
0x1400a8f78  cmovnz  ebx, eax
0x1400a8f7b  test    ebx, ebx
0x1400a8f7d  jns     short loc_1400A8FE1
0x1400a8f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8f86  lea     rax, WPP_GLOBAL_Control
0x1400a8f8d  cmp     rcx, rax
0x1400a8f90  jz      loc_1400A9374
0x1400a8f96  test    byte ptr [rcx+1Ch], 8
0x1400a8f9a  jz      loc_1400A9374
0x1400a8fa0  cmp     byte ptr [rcx+19h], 2
0x1400a8fa4  jb      loc_1400A9374
0x1400a8faa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a8faf  lea     edx, [rbp+1Fh]
0x1400a8fb2  lea     rcx, aDeletesavedcre_0; "DeleteSavedCreds(CRED_TYPE_GENERIC) fai"...
0x1400a8fb9  mov     [rsp+68h+var_40], ebx
0x1400a8fbd  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a8fc4  mov     qword ptr [rsp+68h+var_48], rcx
0x1400a8fc9  mov     r9d, eax
0x1400a8fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a8fd3  mov     rcx, [rcx+10h]
0x1400a8fd7  call    WPP_SF_DsD
0x1400a8fdc  jmp     loc_1400A9374
0x1400a8fe1  mov     r9d, 2; unsigned int
0x1400a8fe7  mov     [rsp+68h+var_48], r12d; unsigned int
0x1400a8fec  lea     r8, aTermsrv; "TERMSRV"
0x1400a8ff3  mov     rdx, r15; unsigned __int16 *
0x1400a8ff6  mov     rcx, r14; this
0x1400a8ff9  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1400a8ffe  xor     ebx, ebx
0x1400a9000  mov     ebp, eax
0x1400a9002  cmp     eax, edi
0x1400a9004  cmovnz  ebx, eax
0x1400a9007  test    ebx, ebx
0x1400a9009  jns     short loc_1400A904C
0x1400a900b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9012  lea     rax, WPP_GLOBAL_Control
0x1400a9019  cmp     rcx, rax
0x1400a901c  jz      loc_1400A9374
0x1400a9022  test    byte ptr [rcx+1Ch], 8
0x1400a9026  jz      loc_1400A9374
0x1400a902c  cmp     byte ptr [rcx+19h], 2
0x1400a9030  jb      loc_1400A9374
0x1400a9036  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a903b  mov     edx, 20h ; ' '
0x1400a9040  lea     rcx, aDeletesavedcre; "DeleteSavedCreds(CRED_TYPE_DOMAIN_PASSW"...
0x1400a9047  jmp     loc_1400A8FB9
0x1400a904c  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400a9051  test    eax, eax
0x1400a9053  jz      short loc_1400A90BB
0x1400a9055  mov     r9d, 6; unsigned int
0x1400a905b  mov     [rsp+68h+var_48], r12d; unsigned int
0x1400a9060  lea     r8, aTermsrv; "TERMSRV"
0x1400a9067  mov     rdx, r15; unsigned __int16 *
0x1400a906a  mov     rcx, r14; this
0x1400a906d  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1400a9072  xor     ecx, ecx
0x1400a9074  cmp     eax, edi
0x1400a9076  setnz   cl
0x1400a9079  xor     ebx, ebx
0x1400a907b  cmp     eax, edi
0x1400a907d  cmovnz  ebx, eax
0x1400a9080  test    ebx, ebx
0x1400a9082  jns     short loc_1400A90BF
0x1400a9084  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a908b  lea     rax, WPP_GLOBAL_Control
0x1400a9092  cmp     rcx, rax
0x1400a9095  jz      loc_1400A9374
0x1400a909b  test    byte ptr [rcx+1Ch], 8
0x1400a909f  jz      loc_1400A9374
0x1400a90a5  cmp     byte ptr [rcx+19h], 2
0x1400a90a9  jb      loc_1400A9374
0x1400a90af  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a90b4  mov     edx, 21h ; '!'
0x1400a90b9  jmp     short loc_1400A9040
0x1400a90bb  xor     ebx, ebx
0x1400a90bd  xor     ecx, ecx
0x1400a90bf  cmp     esi, edi
0x1400a90c1  jnz     loc_1400A9374
0x1400a90c7  cmp     ebp, edi
0x1400a90c9  jnz     loc_1400A9374
0x1400a90cf  test    ecx, ecx
0x1400a90d1  jnz     loc_1400A9374
0x1400a90d7  mov     ebx, edi
0x1400a90d9  jmp     loc_1400A9374
0x1400a90de  cmp     ebp, 6
0x1400a90e1  jnz     loc_1400A924C
0x1400a90e7  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400a90ec  test    eax, eax
0x1400a90ee  jz      loc_1400A91FC
0x1400a90f4  lea     r8, [rsp+68h+TargetName]; unsigned __int16 **
0x1400a90fc  mov     rdx, r15; unsigned __int16 *
0x1400a90ff  mov     rcx, r14; this
0x1400a9102  call    ?GetTargetForExtednedCredential@CTSCredManAssistant@@AEAAJPEBGPEAPEAG@Z; CTSCredManAssistant::GetTargetForExtednedCredential(ushort const *,ushort * *)
0x1400a9107  mov     ebx, eax
0x1400a9109  test    eax, eax
0x1400a910b  jns     short loc_1400A916F
0x1400a910d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9114  lea     rax, WPP_GLOBAL_Control
0x1400a911b  cmp     rcx, rax
0x1400a911e  jz      loc_1400A9361
0x1400a9124  test    byte ptr [rcx+1Ch], 8
0x1400a9128  jz      loc_1400A9361
0x1400a912e  cmp     byte ptr [rcx+19h], 2
0x1400a9132  jb      loc_1400A9361
0x1400a9138  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a913d  lea     edx, [rbp+1Ch]
0x1400a9140  lea     rcx, aGettargetforex; "GetTargetForExtednedCredential failed"
0x1400a9147  mov     [rsp+68h+var_40], ebx
0x1400a914b  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a9152  mov     qword ptr [rsp+68h+var_48], rcx
0x1400a9157  mov     r9d, eax
0x1400a915a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9161  mov     rcx, [rcx+10h]
0x1400a9165  call    WPP_SF_DsD
0x1400a916a  jmp     loc_1400A9361
0x1400a916f  mov     rcx, [rsp+68h+TargetName]; TargetName
0x1400a9177  xor     r8d, r8d; Flags
0x1400a917a  lea     edx, [r8+6]; Type
0x1400a917e  call    cs:__imp_CredDeleteW
0x1400a9184  test    eax, eax
0x1400a9186  jnz     short loc_1400A919D
0x1400a9188  call    cs:__imp_GetLastError
0x1400a918e  mov     ebx, eax
0x1400a9190  test    eax, eax
0x1400a9192  jle     short loc_1400A919D
0x1400a9194  movzx   ebx, ax
0x1400a9197  or      ebx, 80070000h
0x1400a919d  xor     esi, esi
0x1400a919f  mov     edi, 80070490h
0x1400a91a4  cmp     ebx, edi
0x1400a91a6  setnz   sil
0x1400a91aa  xor     eax, eax
0x1400a91ac  cmp     ebx, edi
0x1400a91ae  cmovnz  eax, ebx
0x1400a91b1  mov     ebx, eax
0x1400a91b3  test    eax, eax
0x1400a91b5  jns     loc_1400A935C
0x1400a91bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a91c2  lea     rax, WPP_GLOBAL_Control
0x1400a91c9  cmp     rcx, rax
0x1400a91cc  jz      loc_1400A9361
0x1400a91d2  test    byte ptr [rcx+1Ch], 8
0x1400a91d6  jz      loc_1400A9361
0x1400a91dc  cmp     byte ptr [rcx+19h], 2
0x1400a91e0  jb      loc_1400A9361
0x1400a91e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a91eb  mov     edx, 23h ; '#'
0x1400a91f0  lea     rcx, aCreddeleteServ_0; "CredDelete(Server,CRED_TYPE_DOMAIN_EXTE"...
0x1400a91f7  jmp     loc_1400A9147
0x1400a91fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9203  lea     rax, WPP_GLOBAL_Control
0x1400a920a  cmp     rcx, rax
0x1400a920d  jz      short loc_1400A9242
0x1400a920f  mov     esi, 1
0x1400a9214  test    [rcx+1Ch], sil
0x1400a9218  jz      short loc_1400A9242
0x1400a921a  cmp     byte ptr [rcx+19h], 2
0x1400a921e  jb      short loc_1400A9242
0x1400a9220  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9225  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a922c  lea     edx, [rsi+23h]
0x1400a922f  mov     r9d, eax
0x1400a9232  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a9239  mov     rcx, [rcx+10h]
0x1400a923d  call    WPP_SF_d
0x1400a9242  mov     ebx, 80070490h
0x1400a9247  jmp     loc_1400A9374
0x1400a924c  lea     r9, [rsp+68h+TargetName]; unsigned __int16 **
0x1400a9254  call    ?CreateSPN@CTSCredManAssistant@@AEAAJPEBG0PEAPEAG@Z; CTSCredManAssistant::CreateSPN(ushort const *,ushort const *,ushort * *)
0x1400a9259  mov     ebx, eax
0x1400a925b  test    eax, eax
0x1400a925d  jns     short loc_1400A92A0
0x1400a925f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9266  lea     rax, WPP_GLOBAL_Control
0x1400a926d  cmp     rcx, rax
0x1400a9270  jz      loc_1400A9361
0x1400a9276  test    byte ptr [rcx+1Ch], 8
0x1400a927a  jz      loc_1400A9361
0x1400a9280  cmp     byte ptr [rcx+19h], 2
0x1400a9284  jb      loc_1400A9361
0x1400a928a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a928f  mov     edx, 25h ; '%'
0x1400a9294  lea     rcx, aCreatespnFaile; "CreateSPN failed"
0x1400a929b  jmp     loc_1400A9147
0x1400a92a0  mov     rcx, [rsp+68h+TargetName]; TargetName
0x1400a92a8  xor     r8d, r8d; Flags
0x1400a92ab  mov     edx, ebp; Type
0x1400a92ad  call    cs:__imp_CredDeleteW
0x1400a92b3  mov     esi, 1
0x1400a92b8  mov     edi, 80070490h
0x1400a92bd  mov     r14d, 80070000h
0x1400a92c3  test    eax, eax
0x1400a92c5  jnz     short loc_1400A92DD
0x1400a92c7  call    cs:__imp_GetLastError
0x1400a92cd  mov     ebx, eax
0x1400a92cf  test    eax, eax
0x1400a92d1  jle     short loc_1400A92D9
0x1400a92d3  movzx   ebx, ax
0x1400a92d6  or      ebx, r14d
0x1400a92d9  cmp     ebx, edi
0x1400a92db  jz      short loc_1400A92E5
0x1400a92dd  cmp     ebx, 80070057h
0x1400a92e3  jnz     short loc_1400A92EC
0x1400a92e5  xor     ebx, ebx
0x1400a92e7  xor     r12d, r12d
0x1400a92ea  jmp     short loc_1400A9328
0x1400a92ec  test    ebx, ebx
0x1400a92ee  jns     short loc_1400A9325
0x1400a92f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a92f7  lea     rax, WPP_GLOBAL_Control
0x1400a92fe  cmp     rcx, rax
0x1400a9301  jz      short loc_1400A9361
0x1400a9303  test    byte ptr [rcx+1Ch], 8
0x1400a9307  jz      short loc_1400A9361
0x1400a9309  cmp     byte ptr [rcx+19h], 2
0x1400a930d  jb      short loc_1400A9361
0x1400a930f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9314  mov     edx, 26h ; '&'
0x1400a9319  lea     rcx, aCreddeleteSpnF; "CredDelete(SPN) failed"
0x1400a9320  jmp     loc_1400A9147
0x1400a9325  mov     r12d, esi
0x1400a9328  lea     r9, [rsp+68h+Credential]; Credential
0x1400a932d  xor     r8d, r8d; Flags
0x1400a9330  mov     edx, ebp; Type
0x1400a9332  mov     rcx, r15; TargetName
0x1400a9335  call    cs:__imp_CredReadW
0x1400a933b  test    eax, eax
0x1400a933d  jz      loc_1400A942A
0x1400a9343  mov     rcx, [rsp+68h+Credential]
0x1400a9348  mov     rcx, [rcx+48h]; UserName
0x1400a934c  call    ?IsHomeGroupCredential@@YAHPEBG@Z; IsHomeGroupCredential(ushort const *)
0x1400a9351  test    eax, eax
0x1400a9353  jz      short loc_1400A939D
0x1400a9355  xor     esi, esi
0x1400a9357  test    r12d, r12d
0x1400a935a  jnz     short loc_1400A9361
0x1400a935c  test    esi, esi
0x1400a935e  cmovz   ebx, edi
0x1400a9361  mov     rcx, [rsp+68h+TargetName]; hMem
0x1400a9369  test    rcx, rcx
0x1400a936c  jz      short loc_1400A9374
0x1400a936e  call    cs:__imp_LocalFree
0x1400a9374  mov     rcx, [rsp+68h+Credential]; Buffer
0x1400a9379  test    rcx, rcx
0x1400a937c  jz      short loc_1400A9384
0x1400a937e  call    cs:__imp_CredFree
0x1400a9384  mov     rbp, [rsp+68h+arg_8]
0x1400a9389  mov     eax, ebx
0x1400a938b  mov     rbx, [rsp+68h+arg_0]
0x1400a9390  add     rsp, 40h
0x1400a9394  pop     r15
0x1400a9396  pop     r14
0x1400a9398  pop     r12
0x1400a939a  pop     rdi
0x1400a939b  pop     rsi
0x1400a939c  retn
0x1400a939d  test    byte ptr [rsp+68h+arg_20], sil
0x1400a93a5  jz      short loc_1400A93AC
0x1400a93a7  cmp     ebp, 2
0x1400a93aa  jz      short loc_1400A9357
0x1400a93ac  xor     r8d, r8d; Flags
0x1400a93af  mov     edx, ebp; Type
0x1400a93b1  mov     rcx, r15; TargetName
0x1400a93b4  call    cs:__imp_CredDeleteW
0x1400a93ba  test    eax, eax
0x1400a93bc  jnz     short loc_1400A93D0
0x1400a93be  call    cs:__imp_GetLastError
0x1400a93c4  mov     ebx, eax
0x1400a93c6  test    eax, eax
0x1400a93c8  jle     short loc_1400A93D0
0x1400a93ca  movzx   ebx, ax
0x1400a93cd  or      ebx, r14d
0x1400a93d0  xor     esi, esi
0x1400a93d2  cmp     ebx, edi
  ... truncated ...
```
