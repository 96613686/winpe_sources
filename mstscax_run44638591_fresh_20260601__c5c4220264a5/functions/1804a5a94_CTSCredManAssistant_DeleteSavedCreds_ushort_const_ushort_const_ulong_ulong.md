# CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)

- ea: `0x1804a5a94`
- end: `0x1804a5fea`
- name: `?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z`
- size: `1366`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1803db4f0`
- `0x1804a5a94`
- `0x1804a927c`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x18010f3bc`
- `0x1801a7bac`
- `0x1804a5878`
- `0x1804a5a94`
- `0x1804a7b20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804a5cef`
- `KERNEL32!GetLastError` at `0x1804a5e28`
- `KERNEL32!GetLastError` at `0x1804a5f16`
- `KERNEL32!GetLastError` at `0x1804a5f82`
- `KERNEL32!GetLastError` at `0x1804a5cef`
- `KERNEL32!GetLastError` at `0x1804a5e28`
- `KERNEL32!GetLastError` at `0x1804a5f16`
- `KERNEL32!GetLastError` at `0x1804a5f82`
- `KERNEL32!LocalFree` at `0x1804a5ecc`
- `KERNEL32!LocalFree` at `0x1804a5ecc`
- `ADVAPI32!CredReadW` at `0x1804a5e96`
- `ADVAPI32!CredReadW` at `0x1804a5e96`
- `ADVAPI32!CredFree` at `0x1804a5edc`
- `ADVAPI32!CredFree` at `0x1804a5edc`
- `ADVAPI32!CredDeleteW` at `0x1804a5ce5`
- `ADVAPI32!CredDeleteW` at `0x1804a5e0e`
- `ADVAPI32!CredDeleteW` at `0x1804a5f0c`
- `ADVAPI32!CredDeleteW` at `0x1804a5ce5`
- `ADVAPI32!CredDeleteW` at `0x1804a5e0e`
- `ADVAPI32!CredDeleteW` at `0x1804a5f0c`

## string_xrefs

- `0x1804a5d57`: `CredDelete(Server,CRED_TYPE_DOMAIN_EXTENDED) failed`
- `0x1804a5bb1`: `DeleteSavedCreds(CRED_TYPE_DOMAIN_PASSWORD) failed`
- `0x1804a5b27`: `DeleteSavedCreds(CRED_TYPE_GENERIC) failed`
- `0x1804a5df8`: `CreateSPN failed`
- `0x1804a5fde`: `CredRead(Server) failed`
- `0x1804a5f76`: `CredDelete(Server) failed`
- `0x1804a5e7a`: `CredDelete(SPN) failed`

## pseudocode

```c
__int64 __fastcall CTSCredManAssistant::DeleteSavedCreds(
        CTSCredManAssistant *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        unsigned int a5)
{
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
  LPCWSTR TargetName; // [rsp+30h] [rbp-58h] BYREF
  PCREDENTIALW Credential; // [rsp+38h] [rbp-50h] BYREF

  TargetName = 0;
  Credential = 0;
  if ( a4 )
  {
    if ( a4 == 6 )
    {
      if ( !(unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater() )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
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
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
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
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
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
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
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
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
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
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
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
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
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
  v9 = CTSCredManAssistant::DeleteSavedCreds(this, a2, a3, 1u, a5);
  TargetForExtednedCredential = 0;
  v11 = v9;
  if ( v9 != -2147023728 )
    TargetForExtednedCredential = v9;
  if ( TargetForExtednedCredential >= 0 )
  {
    v15 = CTSCredManAssistant::DeleteSavedCreds(this, a2, a3, 2u, a5);
    TargetForExtednedCredential = 0;
    v16 = v15;
    if ( v15 != -2147023728 )
      TargetForExtednedCredential = v15;
    if ( TargetForExtednedCredential < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
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
      v17 = CTSCredManAssistant::DeleteSavedCreds(this, a2, a3, 6u, a5);
      v18 = v17 != -2147023728;
      TargetForExtednedCredential = 0;
      if ( v17 != -2147023728 )
        TargetForExtednedCredential = v17;
      if ( TargetForExtednedCredential < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
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
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
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
0x1804a5a94  push    rbx
0x1804a5a96  push    rbp
0x1804a5a97  push    rsi
0x1804a5a98  push    rdi
0x1804a5a99  push    r12
0x1804a5a9b  push    r13
0x1804a5a9d  push    r14
0x1804a5a9f  push    r15
0x1804a5aa1  sub     rsp, 48h
0x1804a5aa5  mov     [rsp+88h+TargetName], 0
0x1804a5aae  mov     ebp, r9d
0x1804a5ab1  mov     [rsp+88h+Credential], 0
0x1804a5aba  mov     r14, r8
0x1804a5abd  mov     r15, rdx
0x1804a5ac0  mov     r12, rcx
0x1804a5ac3  test    r9d, r9d
0x1804a5ac6  jnz     loc_1804A5C4B
0x1804a5acc  mov     r13d, [rsp+88h+arg_20]
0x1804a5ad4  lea     r9d, [rbp+1]; unsigned int
0x1804a5ad8  mov     [rsp+88h+var_68], r13d; unsigned int
0x1804a5add  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1804a5ae2  xor     ebx, ebx
0x1804a5ae4  mov     edi, 80070490h
0x1804a5ae9  cmp     eax, edi
0x1804a5aeb  mov     esi, eax
0x1804a5aed  cmovnz  ebx, eax
0x1804a5af0  test    ebx, ebx
0x1804a5af2  jns     short loc_1804A5B56
0x1804a5af4  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5afb  lea     rax, WPP_GLOBAL_Control
0x1804a5b02  cmp     rcx, rax
0x1804a5b05  jz      loc_1804A5ED2
0x1804a5b0b  test    byte ptr [rcx+1Ch], 8
0x1804a5b0f  jz      loc_1804A5ED2
0x1804a5b15  cmp     byte ptr [rcx+19h], 2
0x1804a5b19  jb      loc_1804A5ED2
0x1804a5b1f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804a5b24  lea     edx, [rbp+1Fh]
0x1804a5b27  lea     rcx, aDeletesavedcre_1; "DeleteSavedCreds(CRED_TYPE_GENERIC) fai"...
0x1804a5b2e  mov     [rsp+88h+var_60], ebx
0x1804a5b32  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1804a5b39  mov     qword ptr [rsp+88h+var_68], rcx
0x1804a5b3e  mov     r9d, eax
0x1804a5b41  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5b48  mov     rcx, [rcx+10h]
0x1804a5b4c  call    WPP_SF_DsD
0x1804a5b51  jmp     loc_1804A5ED2
0x1804a5b56  mov     r9d, 2; unsigned int
0x1804a5b5c  mov     [rsp+88h+var_68], r13d; unsigned int
0x1804a5b61  mov     r8, r14; unsigned __int16 *
0x1804a5b64  mov     rdx, r15; unsigned __int16 *
0x1804a5b67  mov     rcx, r12; this
0x1804a5b6a  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1804a5b6f  xor     ebx, ebx
0x1804a5b71  mov     ebp, eax
0x1804a5b73  cmp     eax, edi
0x1804a5b75  cmovnz  ebx, eax
0x1804a5b78  test    ebx, ebx
0x1804a5b7a  jns     short loc_1804A5BBD
0x1804a5b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5b83  lea     rax, WPP_GLOBAL_Control
0x1804a5b8a  cmp     rcx, rax
0x1804a5b8d  jz      loc_1804A5ED2
0x1804a5b93  test    byte ptr [rcx+1Ch], 8
0x1804a5b97  jz      loc_1804A5ED2
0x1804a5b9d  cmp     byte ptr [rcx+19h], 2
0x1804a5ba1  jb      loc_1804A5ED2
0x1804a5ba7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804a5bac  mov     edx, 20h ; ' '
0x1804a5bb1  lea     rcx, aDeletesavedcre_0; "DeleteSavedCreds(CRED_TYPE_DOMAIN_PASSW"...
0x1804a5bb8  jmp     loc_1804A5B2E
0x1804a5bbd  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1804a5bc2  test    eax, eax
0x1804a5bc4  jz      short loc_1804A5C28
0x1804a5bc6  mov     r9d, 6; unsigned int
0x1804a5bcc  mov     [rsp+88h+var_68], r13d; unsigned int
0x1804a5bd1  mov     r8, r14; unsigned __int16 *
0x1804a5bd4  mov     rdx, r15; unsigned __int16 *
0x1804a5bd7  mov     rcx, r12; this
0x1804a5bda  call    ?DeleteSavedCreds@CTSCredManAssistant@@QEAAJPEBG0KK@Z; CTSCredManAssistant::DeleteSavedCreds(ushort const *,ushort const *,ulong,ulong)
0x1804a5bdf  xor     ecx, ecx
0x1804a5be1  cmp     eax, edi
0x1804a5be3  setnz   cl
0x1804a5be6  xor     ebx, ebx
0x1804a5be8  cmp     eax, edi
0x1804a5bea  cmovnz  ebx, eax
0x1804a5bed  test    ebx, ebx
0x1804a5bef  jns     short loc_1804A5C2C
0x1804a5bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5bf8  lea     rax, WPP_GLOBAL_Control
0x1804a5bff  cmp     rcx, rax
0x1804a5c02  jz      loc_1804A5ED2
0x1804a5c08  test    byte ptr [rcx+1Ch], 8
0x1804a5c0c  jz      loc_1804A5ED2
0x1804a5c12  cmp     byte ptr [rcx+19h], 2
0x1804a5c16  jb      loc_1804A5ED2
0x1804a5c1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804a5c21  mov     edx, 21h ; '!'
0x1804a5c26  jmp     short loc_1804A5BB1
0x1804a5c28  xor     ebx, ebx
0x1804a5c2a  xor     ecx, ecx
0x1804a5c2c  cmp     esi, edi
0x1804a5c2e  jnz     loc_1804A5ED2
0x1804a5c34  cmp     ebp, edi
0x1804a5c36  jnz     loc_1804A5ED2
0x1804a5c3c  test    ecx, ecx
0x1804a5c3e  jnz     loc_1804A5ED2
0x1804a5c44  mov     ebx, edi
0x1804a5c46  jmp     loc_1804A5ED2
0x1804a5c4b  cmp     ebp, 6
0x1804a5c4e  jnz     loc_1804A5DB3
0x1804a5c54  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1804a5c59  test    eax, eax
0x1804a5c5b  jz      loc_1804A5D63
0x1804a5c61  lea     r8, [rsp+88h+TargetName]; unsigned __int16 **
0x1804a5c66  mov     rdx, r15; unsigned __int16 *
0x1804a5c69  mov     rcx, r12; this
0x1804a5c6c  call    ?GetTargetForExtednedCredential@CTSCredManAssistant@@AEAAJPEBGPEAPEAG@Z; CTSCredManAssistant::GetTargetForExtednedCredential(ushort const *,ushort * *)
0x1804a5c71  mov     ebx, eax
0x1804a5c73  test    eax, eax
0x1804a5c75  jns     short loc_1804A5CD9
0x1804a5c77  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5c7e  lea     rax, WPP_GLOBAL_Control
0x1804a5c85  cmp     rcx, rax
0x1804a5c88  jz      loc_1804A5EC2
0x1804a5c8e  test    byte ptr [rcx+1Ch], 8
0x1804a5c92  jz      loc_1804A5EC2
0x1804a5c98  cmp     byte ptr [rcx+19h], 2
0x1804a5c9c  jb      loc_1804A5EC2
0x1804a5ca2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804a5ca7  lea     edx, [rbp+1Ch]
0x1804a5caa  lea     rcx, aGettargetforex; "GetTargetForExtednedCredential failed"
0x1804a5cb1  mov     [rsp+88h+var_60], ebx
0x1804a5cb5  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1804a5cbc  mov     qword ptr [rsp+88h+var_68], rcx
0x1804a5cc1  mov     r9d, eax
0x1804a5cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5ccb  mov     rcx, [rcx+10h]
0x1804a5ccf  call    WPP_SF_DsD
0x1804a5cd4  jmp     loc_1804A5EC2
0x1804a5cd9  mov     rcx, [rsp+88h+TargetName]; TargetName
0x1804a5cde  xor     r8d, r8d; Flags
0x1804a5ce1  lea     edx, [r8+6]; Type
0x1804a5ce5  call    cs:__imp_CredDeleteW
0x1804a5ceb  test    eax, eax
0x1804a5ced  jnz     short loc_1804A5D04
0x1804a5cef  call    cs:__imp_GetLastError
0x1804a5cf5  mov     ebx, eax
0x1804a5cf7  test    eax, eax
0x1804a5cf9  jle     short loc_1804A5D04
0x1804a5cfb  movzx   ebx, ax
0x1804a5cfe  or      ebx, 80070000h
0x1804a5d04  xor     esi, esi
0x1804a5d06  mov     edi, 80070490h
0x1804a5d0b  cmp     ebx, edi
0x1804a5d0d  setnz   sil
0x1804a5d11  xor     eax, eax
0x1804a5d13  cmp     ebx, edi
0x1804a5d15  cmovnz  eax, ebx
0x1804a5d18  mov     ebx, eax
0x1804a5d1a  test    eax, eax
0x1804a5d1c  jns     loc_1804A5EBD
0x1804a5d22  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5d29  lea     rax, WPP_GLOBAL_Control
0x1804a5d30  cmp     rcx, rax
0x1804a5d33  jz      loc_1804A5EC2
0x1804a5d39  test    byte ptr [rcx+1Ch], 8
0x1804a5d3d  jz      loc_1804A5EC2
0x1804a5d43  cmp     byte ptr [rcx+19h], 2
0x1804a5d47  jb      loc_1804A5EC2
0x1804a5d4d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804a5d52  mov     edx, 23h ; '#'
0x1804a5d57  lea     rcx, aCreddeleteServ_0; "CredDelete(Server,CRED_TYPE_DOMAIN_EXTE"...
0x1804a5d5e  jmp     loc_1804A5CB1
0x1804a5d63  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5d6a  lea     rax, WPP_GLOBAL_Control
0x1804a5d71  cmp     rcx, rax
0x1804a5d74  jz      short loc_1804A5DA9
0x1804a5d76  mov     esi, 1
0x1804a5d7b  test    [rcx+1Ch], sil
0x1804a5d7f  jz      short loc_1804A5DA9
0x1804a5d81  cmp     byte ptr [rcx+19h], 2
0x1804a5d85  jb      short loc_1804A5DA9
0x1804a5d87  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804a5d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5d93  lea     edx, [rsi+23h]
0x1804a5d96  mov     r9d, eax
0x1804a5d99  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1804a5da0  mov     rcx, [rcx+10h]
0x1804a5da4  call    WPP_SF_d
0x1804a5da9  mov     ebx, 80070490h
0x1804a5dae  jmp     loc_1804A5ED2
0x1804a5db3  lea     r9, [rsp+88h+TargetName]; unsigned __int16 **
0x1804a5db8  call    ?CreateSPN@CTSCredManAssistant@@AEAAJPEBG0PEAPEAG@Z; CTSCredManAssistant::CreateSPN(ushort const *,ushort const *,ushort * *)
0x1804a5dbd  mov     ebx, eax
0x1804a5dbf  test    eax, eax
0x1804a5dc1  jns     short loc_1804A5E04
0x1804a5dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5dca  lea     rax, WPP_GLOBAL_Control
0x1804a5dd1  cmp     rcx, rax
0x1804a5dd4  jz      loc_1804A5EC2
0x1804a5dda  test    byte ptr [rcx+1Ch], 8
0x1804a5dde  jz      loc_1804A5EC2
0x1804a5de4  cmp     byte ptr [rcx+19h], 2
0x1804a5de8  jb      loc_1804A5EC2
0x1804a5dee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804a5df3  mov     edx, 25h ; '%'
0x1804a5df8  lea     rcx, aCreatespnFaile; "CreateSPN failed"
0x1804a5dff  jmp     loc_1804A5CB1
0x1804a5e04  mov     rcx, [rsp+88h+TargetName]; TargetName
0x1804a5e09  xor     r8d, r8d; Flags
0x1804a5e0c  mov     edx, ebp; Type
0x1804a5e0e  call    cs:__imp_CredDeleteW
0x1804a5e14  mov     esi, 1
0x1804a5e19  mov     edi, 80070490h
0x1804a5e1e  mov     r14d, 80070000h
0x1804a5e24  test    eax, eax
0x1804a5e26  jnz     short loc_1804A5E3E
0x1804a5e28  call    cs:__imp_GetLastError
0x1804a5e2e  mov     ebx, eax
0x1804a5e30  test    eax, eax
0x1804a5e32  jle     short loc_1804A5E3A
0x1804a5e34  movzx   ebx, ax
0x1804a5e37  or      ebx, r14d
0x1804a5e3a  cmp     ebx, edi
0x1804a5e3c  jz      short loc_1804A5E46
0x1804a5e3e  cmp     ebx, 80070057h
0x1804a5e44  jnz     short loc_1804A5E4D
0x1804a5e46  xor     ebx, ebx
0x1804a5e48  xor     r12d, r12d
0x1804a5e4b  jmp     short loc_1804A5E89
0x1804a5e4d  test    ebx, ebx
0x1804a5e4f  jns     short loc_1804A5E86
0x1804a5e51  mov     rcx, cs:WPP_GLOBAL_Control
0x1804a5e58  lea     rax, WPP_GLOBAL_Control
0x1804a5e5f  cmp     rcx, rax
0x1804a5e62  jz      short loc_1804A5EC2
0x1804a5e64  test    byte ptr [rcx+1Ch], 8
0x1804a5e68  jz      short loc_1804A5EC2
0x1804a5e6a  cmp     byte ptr [rcx+19h], 2
0x1804a5e6e  jb      short loc_1804A5EC2
0x1804a5e70  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804a5e75  mov     edx, 26h ; '&'
0x1804a5e7a  lea     rcx, aCreddeleteSpnF; "CredDelete(SPN) failed"
0x1804a5e81  jmp     loc_1804A5CB1
0x1804a5e86  mov     r12d, esi
0x1804a5e89  lea     r9, [rsp+88h+Credential]; Credential
0x1804a5e8e  xor     r8d, r8d; Flags
0x1804a5e91  mov     edx, ebp; Type
0x1804a5e93  mov     rcx, r15; TargetName
0x1804a5e96  call    cs:__imp_CredReadW
0x1804a5e9c  test    eax, eax
0x1804a5e9e  jz      loc_1804A5F82
0x1804a5ea4  mov     rcx, [rsp+88h+Credential]
0x1804a5ea9  mov     rcx, [rcx+48h]; UserName
0x1804a5ead  call    ?IsHomeGroupCredential@@YAHPEBG@Z; IsHomeGroupCredential(ushort const *)
0x1804a5eb2  test    eax, eax
0x1804a5eb4  jz      short loc_1804A5EF5
0x1804a5eb6  xor     esi, esi
0x1804a5eb8  test    r12d, r12d
0x1804a5ebb  jnz     short loc_1804A5EC2
0x1804a5ebd  test    esi, esi
0x1804a5ebf  cmovz   ebx, edi
0x1804a5ec2  mov     rcx, [rsp+88h+TargetName]; hMem
0x1804a5ec7  test    rcx, rcx
0x1804a5eca  jz      short loc_1804A5ED2
0x1804a5ecc  call    cs:__imp_LocalFree
0x1804a5ed2  mov     rcx, [rsp+88h+Credential]; Buffer
0x1804a5ed7  test    rcx, rcx
0x1804a5eda  jz      short loc_1804A5EE2
0x1804a5edc  call    cs:__imp_CredFree
0x1804a5ee2  mov     eax, ebx
0x1804a5ee4  add     rsp, 48h
0x1804a5ee8  pop     r15
0x1804a5eea  pop     r14
0x1804a5eec  pop     r13
0x1804a5eee  pop     r12
0x1804a5ef0  pop     rdi
0x1804a5ef1  pop     rsi
0x1804a5ef2  pop     rbp
0x1804a5ef3  pop     rbx
0x1804a5ef4  retn
0x1804a5ef5  test    byte ptr [rsp+88h+arg_20], sil
0x1804a5efd  jz      short loc_1804A5F04
0x1804a5eff  cmp     ebp, 2
0x1804a5f02  jz      short loc_1804A5EB8
0x1804a5f04  xor     r8d, r8d; Flags
0x1804a5f07  mov     edx, ebp; Type
0x1804a5f09  mov     rcx, r15; TargetName
0x1804a5f0c  call    cs:__imp_CredDeleteW
0x1804a5f12  test    eax, eax
0x1804a5f14  jnz     short loc_1804A5F28
0x1804a5f16  call    cs:__imp_GetLastError
0x1804a5f1c  mov     ebx, eax
0x1804a5f1e  test    eax, eax
0x1804a5f20  jle     short loc_1804A5F28
0x1804a5f22  movzx   ebx, ax
0x1804a5f25  or      ebx, r14d
0x1804a5f28  xor     esi, esi
0x1804a5f2a  cmp     ebx, edi
  ... truncated ...
```
