# CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)

- ea: `0x1400ab084`
- end: `0x1400ab602`
- name: `?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z`
- size: `1406`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x140020b08`
- `0x1400ab084`
- `0x1400ad4a4`
- `0x1400b6fe4`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x14009693c`
- `0x1400aae70`
- `0x1400ab084`
- `0x1400abf54`
- `0x1400ac558`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400ab4de`
- `KERNEL32!LocalFree` at `0x1400ab4de`
- `KERNEL32!GetLastError` at `0x1400ab2f8`
- `KERNEL32!GetLastError` at `0x1400ab437`
- `KERNEL32!GetLastError` at `0x1400ab52e`
- `KERNEL32!GetLastError` at `0x1400ab59a`
- `KERNEL32!GetLastError` at `0x1400ab2f8`
- `KERNEL32!GetLastError` at `0x1400ab437`
- `KERNEL32!GetLastError` at `0x1400ab52e`
- `KERNEL32!GetLastError` at `0x1400ab59a`
- `ADVAPI32!CredDeleteW` at `0x1400ab2ee`
- `ADVAPI32!CredDeleteW` at `0x1400ab41d`
- `ADVAPI32!CredDeleteW` at `0x1400ab524`
- `ADVAPI32!CredDeleteW` at `0x1400ab2ee`
- `ADVAPI32!CredDeleteW` at `0x1400ab41d`
- `ADVAPI32!CredDeleteW` at `0x1400ab524`
- `ADVAPI32!CredFree` at `0x1400ab4ee`
- `ADVAPI32!CredFree` at `0x1400ab4ee`
- `ADVAPI32!CredReadW` at `0x1400ab4a5`
- `ADVAPI32!CredReadW` at `0x1400ab4a5`

## string_xrefs

- `0x1400ab404`: `CreateSPN failed`
- `0x1400ab489`: `CredDelete(SPN) failed`
- `0x1400ab58e`: `CredDelete(Server) failed`
- `0x1400ab5f6`: `CredRead(Server) failed`
- `0x1400ab122`: `DeleteSavedCreds(CRED_TYPE_GENERIC) failed`
- `0x1400ab1b0`: `DeleteSavedCreds(CRED_TYPE_DOMAIN_PASSWORD) failed`
- `0x1400ab360`: `CredDelete(Server,CRED_TYPE_DOMAIN_EXTENDED) failed`

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
    v13 = a4 + 31;
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
0x1400ab084  mov     rax, rsp
0x1400ab087  mov     [rax+8], rbx
0x1400ab08b  mov     [rax+10h], rbp
0x1400ab08f  mov     [rax+18h], r8
0x1400ab093  push    rsi
0x1400ab094  push    rdi
0x1400ab095  push    r12
0x1400ab097  push    r14
0x1400ab099  push    r15
0x1400ab09b  sub     rsp, 40h
0x1400ab09f  mov     qword ptr [rax+18h], 0
0x1400ab0a7  mov     ebp, r9d
0x1400ab0aa  mov     qword ptr [rax-38h], 0
0x1400ab0b2  mov     r15, rdx
0x1400ab0b5  mov     r14, rcx
0x1400ab0b8  test    r9d, r9d
0x1400ab0bb  jnz     loc_1400AB24E
0x1400ab0c1  mov     r12d, [rsp+68h+arg_20]
0x1400ab0c9  lea     r9d, [rbp+1]; unsigned int
0x1400ab0cd  lea     r8, aTermsrv; "TERMSRV"
0x1400ab0d4  mov     [rax-48h], r12d
0x1400ab0d8  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1400ab0dd  xor     ebx, ebx
0x1400ab0df  mov     edi, 80070490h
0x1400ab0e4  cmp     eax, edi
0x1400ab0e6  mov     esi, eax
0x1400ab0e8  cmovnz  ebx, eax
0x1400ab0eb  test    ebx, ebx
0x1400ab0ed  jns     short loc_1400AB151
0x1400ab0ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab0f6  lea     rax, WPP_GLOBAL_Control
0x1400ab0fd  cmp     rcx, rax
0x1400ab100  jz      loc_1400AB4E4
0x1400ab106  test    byte ptr [rcx+1Ch], 8
0x1400ab10a  jz      loc_1400AB4E4
0x1400ab110  cmp     byte ptr [rcx+19h], 2
0x1400ab114  jb      loc_1400AB4E4
0x1400ab11a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab11f  lea     edx, [rbp+1Fh]
0x1400ab122  lea     rcx, aDeletesavedcre_0; "DeleteSavedCreds(CRED_TYPE_GENERIC) fai"...
0x1400ab129  mov     [rsp+68h+var_40], ebx
0x1400ab12d  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab134  mov     qword ptr [rsp+68h+var_48], rcx
0x1400ab139  mov     r9d, eax
0x1400ab13c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab143  mov     rcx, [rcx+10h]
0x1400ab147  call    WPP_SF_DsD
0x1400ab14c  jmp     loc_1400AB4E4
0x1400ab151  mov     r9d, 2; unsigned int
0x1400ab157  mov     [rsp+68h+var_48], r12d; unsigned int
0x1400ab15c  lea     r8, aTermsrv; "TERMSRV"
0x1400ab163  mov     rdx, r15; unsigned __int16 *
0x1400ab166  mov     rcx, r14; this
0x1400ab169  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1400ab16e  xor     ebx, ebx
0x1400ab170  mov     ebp, eax
0x1400ab172  cmp     eax, edi
0x1400ab174  cmovnz  ebx, eax
0x1400ab177  test    ebx, ebx
0x1400ab179  jns     short loc_1400AB1BC
0x1400ab17b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab182  lea     rax, WPP_GLOBAL_Control
0x1400ab189  cmp     rcx, rax
0x1400ab18c  jz      loc_1400AB4E4
0x1400ab192  test    byte ptr [rcx+1Ch], 8
0x1400ab196  jz      loc_1400AB4E4
0x1400ab19c  cmp     byte ptr [rcx+19h], 2
0x1400ab1a0  jb      loc_1400AB4E4
0x1400ab1a6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab1ab  mov     edx, 20h ; ' '
0x1400ab1b0  lea     rcx, aDeletesavedcre; "DeleteSavedCreds(CRED_TYPE_DOMAIN_PASSW"...
0x1400ab1b7  jmp     loc_1400AB129
0x1400ab1bc  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400ab1c1  test    eax, eax
0x1400ab1c3  jz      short loc_1400AB22B
0x1400ab1c5  mov     r9d, 6; unsigned int
0x1400ab1cb  mov     [rsp+68h+var_48], r12d; unsigned int
0x1400ab1d0  lea     r8, aTermsrv; "TERMSRV"
0x1400ab1d7  mov     rdx, r15; unsigned __int16 *
0x1400ab1da  mov     rcx, r14; this
0x1400ab1dd  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1400ab1e2  xor     ecx, ecx
0x1400ab1e4  cmp     eax, edi
0x1400ab1e6  setnz   cl
0x1400ab1e9  xor     ebx, ebx
0x1400ab1eb  cmp     eax, edi
0x1400ab1ed  cmovnz  ebx, eax
0x1400ab1f0  test    ebx, ebx
0x1400ab1f2  jns     short loc_1400AB22F
0x1400ab1f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab1fb  lea     rax, WPP_GLOBAL_Control
0x1400ab202  cmp     rcx, rax
0x1400ab205  jz      loc_1400AB4E4
0x1400ab20b  test    byte ptr [rcx+1Ch], 8
0x1400ab20f  jz      loc_1400AB4E4
0x1400ab215  cmp     byte ptr [rcx+19h], 2
0x1400ab219  jb      loc_1400AB4E4
0x1400ab21f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab224  mov     edx, 21h ; '!'
0x1400ab229  jmp     short loc_1400AB1B0
0x1400ab22b  xor     ebx, ebx
0x1400ab22d  xor     ecx, ecx
0x1400ab22f  cmp     esi, edi
0x1400ab231  jnz     loc_1400AB4E4
0x1400ab237  cmp     ebp, edi
0x1400ab239  jnz     loc_1400AB4E4
0x1400ab23f  test    ecx, ecx
0x1400ab241  jnz     loc_1400AB4E4
0x1400ab247  mov     ebx, edi
0x1400ab249  jmp     loc_1400AB4E4
0x1400ab24e  cmp     ebp, 6
0x1400ab251  jnz     loc_1400AB3BC
0x1400ab257  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400ab25c  test    eax, eax
0x1400ab25e  jz      loc_1400AB36C
0x1400ab264  lea     r8, [rsp+68h+TargetName]; unsigned __int16 **
0x1400ab26c  mov     rdx, r15; unsigned __int16 *
0x1400ab26f  mov     rcx, r14; this
0x1400ab272  call    ?GetTargetForExtednedCredential@CTSCredManAssistant@@AEAAJPEBGPEAPEAG@Z; CTSCredManAssistant::GetTargetForExtednedCredential(ushort const *,ushort * *)
0x1400ab277  mov     ebx, eax
0x1400ab279  test    eax, eax
0x1400ab27b  jns     short loc_1400AB2DF
0x1400ab27d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab284  lea     rax, WPP_GLOBAL_Control
0x1400ab28b  cmp     rcx, rax
0x1400ab28e  jz      loc_1400AB4D1
0x1400ab294  test    byte ptr [rcx+1Ch], 8
0x1400ab298  jz      loc_1400AB4D1
0x1400ab29e  cmp     byte ptr [rcx+19h], 2
0x1400ab2a2  jb      loc_1400AB4D1
0x1400ab2a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab2ad  lea     edx, [rbp+1Ch]
0x1400ab2b0  lea     rcx, aGettargetforex; "GetTargetForExtednedCredential failed"
0x1400ab2b7  mov     [rsp+68h+var_40], ebx
0x1400ab2bb  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab2c2  mov     qword ptr [rsp+68h+var_48], rcx
0x1400ab2c7  mov     r9d, eax
0x1400ab2ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab2d1  mov     rcx, [rcx+10h]
0x1400ab2d5  call    WPP_SF_DsD
0x1400ab2da  jmp     loc_1400AB4D1
0x1400ab2df  mov     rcx, [rsp+68h+TargetName]; TargetName
0x1400ab2e7  xor     r8d, r8d; Flags
0x1400ab2ea  lea     edx, [r8+6]; Type
0x1400ab2ee  call    cs:__imp_CredDeleteW
0x1400ab2f4  test    eax, eax
0x1400ab2f6  jnz     short loc_1400AB30D
0x1400ab2f8  call    cs:__imp_GetLastError
0x1400ab2fe  mov     ebx, eax
0x1400ab300  test    eax, eax
0x1400ab302  jle     short loc_1400AB30D
0x1400ab304  movzx   ebx, ax
0x1400ab307  or      ebx, 80070000h
0x1400ab30d  xor     esi, esi
0x1400ab30f  mov     edi, 80070490h
0x1400ab314  cmp     ebx, edi
0x1400ab316  setnz   sil
0x1400ab31a  xor     eax, eax
0x1400ab31c  cmp     ebx, edi
0x1400ab31e  cmovnz  eax, ebx
0x1400ab321  mov     ebx, eax
0x1400ab323  test    eax, eax
0x1400ab325  jns     loc_1400AB4CC
0x1400ab32b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab332  lea     rax, WPP_GLOBAL_Control
0x1400ab339  cmp     rcx, rax
0x1400ab33c  jz      loc_1400AB4D1
0x1400ab342  test    byte ptr [rcx+1Ch], 8
0x1400ab346  jz      loc_1400AB4D1
0x1400ab34c  cmp     byte ptr [rcx+19h], 2
0x1400ab350  jb      loc_1400AB4D1
0x1400ab356  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab35b  mov     edx, 23h ; '#'
0x1400ab360  lea     rcx, aCreddeleteServ_0; "CredDelete(Server,CRED_TYPE_DOMAIN_EXTE"...
0x1400ab367  jmp     loc_1400AB2B7
0x1400ab36c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab373  lea     rax, WPP_GLOBAL_Control
0x1400ab37a  cmp     rcx, rax
0x1400ab37d  jz      short loc_1400AB3B2
0x1400ab37f  mov     esi, 1
0x1400ab384  test    [rcx+1Ch], sil
0x1400ab388  jz      short loc_1400AB3B2
0x1400ab38a  cmp     byte ptr [rcx+19h], 2
0x1400ab38e  jb      short loc_1400AB3B2
0x1400ab390  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab395  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab39c  lea     edx, [rsi+23h]
0x1400ab39f  mov     r9d, eax
0x1400ab3a2  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400ab3a9  mov     rcx, [rcx+10h]
0x1400ab3ad  call    WPP_SF_d
0x1400ab3b2  mov     ebx, 80070490h
0x1400ab3b7  jmp     loc_1400AB4E4
0x1400ab3bc  lea     r9, [rsp+68h+TargetName]; unsigned __int16 **
0x1400ab3c4  call    ?CreateSPN@CTSCredManAssistant@@AEAAJPEBG0PEAPEAG@Z; CTSCredManAssistant::CreateSPN(ushort const *,ushort const *,ushort * *)
0x1400ab3c9  mov     ebx, eax
0x1400ab3cb  test    eax, eax
0x1400ab3cd  jns     short loc_1400AB410
0x1400ab3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab3d6  lea     rax, WPP_GLOBAL_Control
0x1400ab3dd  cmp     rcx, rax
0x1400ab3e0  jz      loc_1400AB4D1
0x1400ab3e6  test    byte ptr [rcx+1Ch], 8
0x1400ab3ea  jz      loc_1400AB4D1
0x1400ab3f0  cmp     byte ptr [rcx+19h], 2
0x1400ab3f4  jb      loc_1400AB4D1
0x1400ab3fa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab3ff  mov     edx, 25h ; '%'
0x1400ab404  lea     rcx, aCreatespnFaile; "CreateSPN failed"
0x1400ab40b  jmp     loc_1400AB2B7
0x1400ab410  mov     rcx, [rsp+68h+TargetName]; TargetName
0x1400ab418  xor     r8d, r8d; Flags
0x1400ab41b  mov     edx, ebp; Type
0x1400ab41d  call    cs:__imp_CredDeleteW
0x1400ab423  mov     esi, 1
0x1400ab428  mov     edi, 80070490h
0x1400ab42d  mov     r14d, 80070000h
0x1400ab433  test    eax, eax
0x1400ab435  jnz     short loc_1400AB44D
0x1400ab437  call    cs:__imp_GetLastError
0x1400ab43d  mov     ebx, eax
0x1400ab43f  test    eax, eax
0x1400ab441  jle     short loc_1400AB449
0x1400ab443  movzx   ebx, ax
0x1400ab446  or      ebx, r14d
0x1400ab449  cmp     ebx, edi
0x1400ab44b  jz      short loc_1400AB455
0x1400ab44d  cmp     ebx, 80070057h
0x1400ab453  jnz     short loc_1400AB45C
0x1400ab455  xor     ebx, ebx
0x1400ab457  xor     r12d, r12d
0x1400ab45a  jmp     short loc_1400AB498
0x1400ab45c  test    ebx, ebx
0x1400ab45e  jns     short loc_1400AB495
0x1400ab460  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab467  lea     rax, WPP_GLOBAL_Control
0x1400ab46e  cmp     rcx, rax
0x1400ab471  jz      short loc_1400AB4D1
0x1400ab473  test    byte ptr [rcx+1Ch], 8
0x1400ab477  jz      short loc_1400AB4D1
0x1400ab479  cmp     byte ptr [rcx+19h], 2
0x1400ab47d  jb      short loc_1400AB4D1
0x1400ab47f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ab484  mov     edx, 26h ; '&'
0x1400ab489  lea     rcx, aCreddeleteSpnF; "CredDelete(SPN) failed"
0x1400ab490  jmp     loc_1400AB2B7
0x1400ab495  mov     r12d, esi
0x1400ab498  lea     r9, [rsp+68h+Credential]; Credential
0x1400ab49d  xor     r8d, r8d; Flags
0x1400ab4a0  mov     edx, ebp; Type
0x1400ab4a2  mov     rcx, r15; TargetName
0x1400ab4a5  call    cs:__imp_CredReadW
0x1400ab4ab  test    eax, eax
0x1400ab4ad  jz      loc_1400AB59A
0x1400ab4b3  mov     rcx, [rsp+68h+Credential]
0x1400ab4b8  mov     rcx, [rcx+48h]; UserName
0x1400ab4bc  call    ?IsHomeGroupCredential@@YAHPEBG@Z; IsHomeGroupCredential(ushort const *)
0x1400ab4c1  test    eax, eax
0x1400ab4c3  jz      short loc_1400AB50D
0x1400ab4c5  xor     esi, esi
0x1400ab4c7  test    r12d, r12d
0x1400ab4ca  jnz     short loc_1400AB4D1
0x1400ab4cc  test    esi, esi
0x1400ab4ce  cmovz   ebx, edi
0x1400ab4d1  mov     rcx, [rsp+68h+TargetName]; hMem
0x1400ab4d9  test    rcx, rcx
0x1400ab4dc  jz      short loc_1400AB4E4
0x1400ab4de  call    cs:__imp_LocalFree
0x1400ab4e4  mov     rcx, [rsp+68h+Credential]; Buffer
0x1400ab4e9  test    rcx, rcx
0x1400ab4ec  jz      short loc_1400AB4F4
0x1400ab4ee  call    cs:__imp_CredFree
0x1400ab4f4  mov     rbp, [rsp+68h+arg_8]
0x1400ab4f9  mov     eax, ebx
0x1400ab4fb  mov     rbx, [rsp+68h+arg_0]
0x1400ab500  add     rsp, 40h
0x1400ab504  pop     r15
0x1400ab506  pop     r14
0x1400ab508  pop     r12
0x1400ab50a  pop     rdi
0x1400ab50b  pop     rsi
0x1400ab50c  retn
0x1400ab50d  test    byte ptr [rsp+68h+arg_20], sil
0x1400ab515  jz      short loc_1400AB51C
0x1400ab517  cmp     ebp, 2
0x1400ab51a  jz      short loc_1400AB4C7
0x1400ab51c  xor     r8d, r8d; Flags
0x1400ab51f  mov     edx, ebp; Type
0x1400ab521  mov     rcx, r15; TargetName
0x1400ab524  call    cs:__imp_CredDeleteW
0x1400ab52a  test    eax, eax
0x1400ab52c  jnz     short loc_1400AB540
0x1400ab52e  call    cs:__imp_GetLastError
0x1400ab534  mov     ebx, eax
0x1400ab536  test    eax, eax
0x1400ab538  jle     short loc_1400AB540
0x1400ab53a  movzx   ebx, ax
0x1400ab53d  or      ebx, r14d
0x1400ab540  xor     esi, esi
0x1400ab542  cmp     ebx, edi
  ... truncated ...
```
