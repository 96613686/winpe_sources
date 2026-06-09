# CTSCredManAssistant::GetSavedCreds(ushort const *,ulong,ushort *,ulong,ushort *,ulong)

- ea: `0x1400a9ab4`
- end: `0x1400a9ddb`
- name: `?GetSavedCreds@CTSCredManAssistant@@QEAAJPEBGKPEAGK1K@Z`
- size: `807`
- prototype: `__int64 __fastcall(CTSCredManAssistant *__hidden this, const unsigned __int16 *, DWORD Type, unsigned __int16 *, unsigned int, LPCWSTR TargetName, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400ab8ac`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400947cc`
- `0x1400a9ab4`
- `0x1400a9de4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400a9dca`
- `KERNEL32!LocalFree` at `0x1400a9dca`
- `KERNEL32!GetLastError` at `0x1400a9b8c`
- `KERNEL32!GetLastError` at `0x1400a9c7d`
- `KERNEL32!GetLastError` at `0x1400a9b8c`
- `KERNEL32!GetLastError` at `0x1400a9c7d`
- `ADVAPI32!CredFree` at `0x1400a9dbc`
- `ADVAPI32!CredFree` at `0x1400a9dbc`
- `ADVAPI32!CredReadW` at `0x1400a9b7e`
- `ADVAPI32!CredReadW` at `0x1400a9c73`
- `ADVAPI32!CredReadW` at `0x1400a9b7e`
- `ADVAPI32!CredReadW` at `0x1400a9c73`

## string_xrefs

- `0x1400a9d88`: `StringCchCopy failed!`

## pseudocode

```c
__int64 __fastcall CTSCredManAssistant::GetSavedCreds(
        CTSCredManAssistant *this,
        const unsigned __int16 *a2,
        DWORD Type,
        unsigned __int16 *a4,
        unsigned int a5,
        WCHAR *TargetName)
{
  WCHAR *v6; // rdi
  signed int TargetForExtednedCredential; // ebx
  unsigned int v11; // eax
  signed int v12; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  signed int LastError; // eax
  const unsigned __int16 *UserName; // r8
  unsigned int v18; // eax
  int v19; // edx
  PCREDENTIALW Credential[7]; // [rsp+30h] [rbp-38h] BYREF

  v6 = 0;
  Credential[0] = 0;
  TargetName = 0;
  if ( Type != 6 )
  {
    if ( CredReadW(a2, Type, 0, Credential) )
      goto LABEL_36;
    LastError = GetLastError();
    TargetForExtednedCredential = LastError;
    if ( LastError > 0 )
      TargetForExtednedCredential = (unsigned __int16)LastError | 0x80070000;
    if ( TargetForExtednedCredential != -2147024809 )
    {
      if ( TargetForExtednedCredential < 0 )
      {
        if ( TargetForExtednedCredential == -2147023728
          || TargetForExtednedCredential == -2147024891
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_50;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 26;
LABEL_19:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
          CurrentThreadActivityIdPrefix,
          TargetForExtednedCredential);
        goto LABEL_50;
      }
LABEL_37:
      if ( !a4 )
        goto LABEL_50;
      UserName = Credential[0]->UserName;
      if ( UserName )
      {
        TargetForExtednedCredential = StringCchCopyW(a4, a5, UserName);
        if ( TargetForExtednedCredential >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_50;
        }
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 27;
      }
      else
      {
        TargetForExtednedCredential = StringCchCopyW(a4, a5, &pszPassword);
        if ( TargetForExtednedCredential >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_50;
        }
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 28;
      }
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        (unsigned int)WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
        v18,
        (__int64)"StringCchCopy failed!",
        TargetForExtednedCredential);
      goto LABEL_50;
    }
LABEL_24:
    TargetForExtednedCredential = -2147023728;
    goto LABEL_50;
  }
  if ( !(unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater() )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids, v15);
    }
    goto LABEL_24;
  }
  TargetForExtednedCredential = CTSCredManAssistant::GetTargetForExtednedCredential(this, a2, &TargetName);
  if ( TargetForExtednedCredential >= 0 )
  {
    v6 = TargetName;
    if ( !CredReadW(TargetName, 6u, 0, Credential) )
    {
      v12 = GetLastError();
      TargetForExtednedCredential = v12;
      if ( v12 > 0 )
        TargetForExtednedCredential = (unsigned __int16)v12 | 0x80070000;
      if ( TargetForExtednedCredential < 0 )
      {
        if ( TargetForExtednedCredential == -2147023728
          || TargetForExtednedCredential == -2147024891
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_50;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 24;
        goto LABEL_19;
      }
      goto LABEL_37;
    }
LABEL_36:
    TargetForExtednedCredential = 0;
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids,
      v11,
      (__int64)"GetTargetForExtednedCredential failed",
      TargetForExtednedCredential);
  }
  v6 = TargetName;
LABEL_50:
  if ( Credential[0] )
    CredFree(Credential[0]);
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)TargetForExtednedCredential;
}

```

## disassembly

```asm
0x1400a9ab4  mov     r11, rsp
0x1400a9ab7  push    rbx
0x1400a9ab8  push    rbp
0x1400a9ab9  push    rsi
0x1400a9aba  push    rdi
0x1400a9abb  sub     rsp, 48h
0x1400a9abf  xor     edi, edi
0x1400a9ac1  mov     qword ptr [r11-38h], 0
0x1400a9ac9  mov     [r11+30h], rdi
0x1400a9acd  mov     rsi, r9
0x1400a9ad0  mov     eax, r8d
0x1400a9ad3  mov     rbx, rdx
0x1400a9ad6  mov     rbp, rcx
0x1400a9ad9  cmp     r8d, 6
0x1400a9add  jnz     loc_1400A9C66
0x1400a9ae3  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x1400a9ae8  test    eax, eax
0x1400a9aea  jz      loc_1400A9C19
0x1400a9af0  lea     r8, [rsp+68h+TargetName]; unsigned __int16 **
0x1400a9af8  mov     rdx, rbx; unsigned __int16 *
0x1400a9afb  mov     rcx, rbp; this
0x1400a9afe  call    ?GetTargetForExtednedCredential@CTSCredManAssistant@@AEAAJPEBGPEAPEAG@Z; CTSCredManAssistant::GetTargetForExtednedCredential(ushort const *,ushort * *)
0x1400a9b03  mov     ebx, eax
0x1400a9b05  test    eax, eax
0x1400a9b07  jns     short loc_1400A9B67
0x1400a9b09  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9b10  lea     rax, WPP_GLOBAL_Control
0x1400a9b17  cmp     rcx, rax
0x1400a9b1a  jz      short loc_1400A9B5A
0x1400a9b1c  test    byte ptr [rcx+1Ch], 8
0x1400a9b20  jz      short loc_1400A9B5A
0x1400a9b22  cmp     byte ptr [rcx+19h], 2
0x1400a9b26  jb      short loc_1400A9B5A
0x1400a9b28  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9b2d  lea     rcx, aGettargetforex; "GetTargetForExtednedCredential failed"
0x1400a9b34  mov     [rsp+68h+var_40], ebx
0x1400a9b38  mov     [rsp+68h+var_48], rcx
0x1400a9b3d  lea     edx, [rdi+17h]
0x1400a9b40  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9b47  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a9b4e  mov     r9d, eax
0x1400a9b51  mov     rcx, [rcx+10h]
0x1400a9b55  call    WPP_SF_DsD
0x1400a9b5a  mov     rdi, [rsp+68h+TargetName]
0x1400a9b62  jmp     loc_1400A9DB2
0x1400a9b67  mov     rdi, [rsp+68h+TargetName]
0x1400a9b6f  lea     r9, [rsp+68h+Credential]; Credential
0x1400a9b74  xor     r8d, r8d; Flags
0x1400a9b77  mov     rcx, rdi; TargetName
0x1400a9b7a  lea     edx, [r8+6]; Type
0x1400a9b7e  call    cs:__imp_CredReadW
0x1400a9b84  test    eax, eax
0x1400a9b86  jnz     loc_1400A9CF0
0x1400a9b8c  call    cs:__imp_GetLastError
0x1400a9b92  mov     ebx, eax
0x1400a9b94  test    eax, eax
0x1400a9b96  jle     short loc_1400A9BA1
0x1400a9b98  movzx   ebx, ax
0x1400a9b9b  or      ebx, 80070000h
0x1400a9ba1  test    ebx, ebx
0x1400a9ba3  jns     loc_1400A9CF2
0x1400a9ba9  cmp     ebx, 80070490h
0x1400a9baf  jz      loc_1400A9DB2
0x1400a9bb5  cmp     ebx, 80070005h
0x1400a9bbb  jz      loc_1400A9DB2
0x1400a9bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9bc8  lea     rax, WPP_GLOBAL_Control
0x1400a9bcf  cmp     rcx, rax
0x1400a9bd2  jz      loc_1400A9DB2
0x1400a9bd8  test    byte ptr [rcx+1Ch], 1
0x1400a9bdc  jz      loc_1400A9DB2
0x1400a9be2  cmp     byte ptr [rcx+19h], 2
0x1400a9be6  jb      loc_1400A9DB2
0x1400a9bec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9bf1  mov     edx, 18h
0x1400a9bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9bfd  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a9c04  mov     r9d, eax
0x1400a9c07  mov     dword ptr [rsp+68h+var_48], ebx
0x1400a9c0b  mov     rcx, [rcx+10h]
0x1400a9c0f  call    WPP_SF_Dd
0x1400a9c14  jmp     loc_1400A9DB2
0x1400a9c19  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9c20  lea     rax, WPP_GLOBAL_Control
0x1400a9c27  cmp     rcx, rax
0x1400a9c2a  jz      short loc_1400A9C5C
0x1400a9c2c  test    byte ptr [rcx+1Ch], 1
0x1400a9c30  jz      short loc_1400A9C5C
0x1400a9c32  cmp     byte ptr [rcx+19h], 2
0x1400a9c36  jb      short loc_1400A9C5C
0x1400a9c38  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9c44  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a9c4b  mov     edx, 19h
0x1400a9c50  mov     r9d, eax
0x1400a9c53  mov     rcx, [rcx+10h]
0x1400a9c57  call    WPP_SF_d
0x1400a9c5c  mov     ebx, 80070490h
0x1400a9c61  jmp     loc_1400A9DB2
0x1400a9c66  lea     r9, [rsp+68h+Credential]; Credential
0x1400a9c6b  xor     r8d, r8d; Flags
0x1400a9c6e  mov     edx, eax; Type
0x1400a9c70  mov     rcx, rbx; TargetName
0x1400a9c73  call    cs:__imp_CredReadW
0x1400a9c79  test    eax, eax
0x1400a9c7b  jnz     short loc_1400A9CF0
0x1400a9c7d  call    cs:__imp_GetLastError
0x1400a9c83  mov     ebx, eax
0x1400a9c85  test    eax, eax
0x1400a9c87  jle     short loc_1400A9C92
0x1400a9c89  movzx   ebx, ax
0x1400a9c8c  or      ebx, 80070000h
0x1400a9c92  cmp     ebx, 80070057h
0x1400a9c98  jz      short loc_1400A9C5C
0x1400a9c9a  test    ebx, ebx
0x1400a9c9c  jns     short loc_1400A9CF2
0x1400a9c9e  cmp     ebx, 80070490h
0x1400a9ca4  jz      loc_1400A9DB2
0x1400a9caa  cmp     ebx, 80070005h
0x1400a9cb0  jz      loc_1400A9DB2
0x1400a9cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9cbd  lea     rax, WPP_GLOBAL_Control
0x1400a9cc4  cmp     rcx, rax
0x1400a9cc7  jz      loc_1400A9DB2
0x1400a9ccd  test    byte ptr [rcx+1Ch], 1
0x1400a9cd1  jz      loc_1400A9DB2
0x1400a9cd7  cmp     byte ptr [rcx+19h], 2
0x1400a9cdb  jb      loc_1400A9DB2
0x1400a9ce1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9ce6  mov     edx, 1Ah
0x1400a9ceb  jmp     loc_1400A9BF6
0x1400a9cf0  xor     ebx, ebx
0x1400a9cf2  test    rsi, rsi
0x1400a9cf5  jz      loc_1400A9DB2
0x1400a9cfb  mov     rax, [rsp+68h+Credential]
0x1400a9d00  mov     rcx, rsi; unsigned __int16 *
0x1400a9d03  mov     edx, [rsp+68h+arg_20]; unsigned __int64
0x1400a9d0a  mov     r8, [rax+48h]; unsigned __int16 *
0x1400a9d0e  test    r8, r8
0x1400a9d11  jz      short loc_1400A9D4D
0x1400a9d13  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400a9d18  mov     ebx, eax
0x1400a9d1a  test    eax, eax
0x1400a9d1c  jns     loc_1400A9DB2
0x1400a9d22  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9d29  lea     rax, WPP_GLOBAL_Control
0x1400a9d30  cmp     rcx, rax
0x1400a9d33  jz      short loc_1400A9DB2
0x1400a9d35  test    byte ptr [rcx+1Ch], 8
0x1400a9d39  jz      short loc_1400A9DB2
0x1400a9d3b  cmp     byte ptr [rcx+19h], 2
0x1400a9d3f  jb      short loc_1400A9DB2
0x1400a9d41  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9d46  mov     edx, 1Bh
0x1400a9d4b  jmp     short loc_1400A9D88
0x1400a9d4d  lea     r8, pszPassword; unsigned __int16 *
0x1400a9d54  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400a9d59  mov     ebx, eax
0x1400a9d5b  test    eax, eax
0x1400a9d5d  jns     short loc_1400A9DB2
0x1400a9d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9d66  lea     rax, WPP_GLOBAL_Control
0x1400a9d6d  cmp     rcx, rax
0x1400a9d70  jz      short loc_1400A9DB2
0x1400a9d72  test    byte ptr [rcx+1Ch], 8
0x1400a9d76  jz      short loc_1400A9DB2
0x1400a9d78  cmp     byte ptr [rcx+19h], 2
0x1400a9d7c  jb      short loc_1400A9DB2
0x1400a9d7e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9d83  mov     edx, 1Ch
0x1400a9d88  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x1400a9d8f  mov     [rsp+68h+var_40], ebx
0x1400a9d93  mov     [rsp+68h+var_48], rcx
0x1400a9d98  lea     r8, WPP_c2b8a8bd8c0f3aae1fba090a7c51fc13_Traceguids
0x1400a9d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9da6  mov     r9d, eax
0x1400a9da9  mov     rcx, [rcx+10h]
0x1400a9dad  call    WPP_SF_DsD
0x1400a9db2  mov     rcx, [rsp+68h+Credential]; Buffer
0x1400a9db7  test    rcx, rcx
0x1400a9dba  jz      short loc_1400A9DC2
0x1400a9dbc  call    cs:__imp_CredFree
0x1400a9dc2  test    rdi, rdi
0x1400a9dc5  jz      short loc_1400A9DD0
0x1400a9dc7  mov     rcx, rdi; hMem
0x1400a9dca  call    cs:__imp_LocalFree
0x1400a9dd0  mov     eax, ebx
0x1400a9dd2  add     rsp, 48h
0x1400a9dd6  pop     rdi
0x1400a9dd7  pop     rsi
0x1400a9dd8  pop     rbp
0x1400a9dd9  pop     rbx
0x1400a9dda  retn
```
