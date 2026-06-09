# AACredHelper::CleanUpCreds(ushort const *)

- ea: `0x14009080c`
- end: `0x140090b13`
- name: `?CleanUpCreds@AACredHelper@@SAJPEBG@Z`
- size: `775`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14004c458`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000d078`
- `0x14001e210`
- `0x1400403d0`
- `0x14009080c`
- `0x140111220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140090962`
- `KERNEL32!GetLastError` at `0x1400909f5`
- `KERNEL32!GetLastError` at `0x140090a35`
- `KERNEL32!GetLastError` at `0x140090962`
- `KERNEL32!GetLastError` at `0x1400909f5`
- `KERNEL32!GetLastError` at `0x140090a35`
- `ADVAPI32!CredDeleteW` at `0x1400909eb`
- `ADVAPI32!CredDeleteW` at `0x140090a27`
- `ADVAPI32!CredDeleteW` at `0x1400909eb`
- `ADVAPI32!CredDeleteW` at `0x140090a27`
- `ADVAPI32!CredFree` at `0x140090ae3`
- `ADVAPI32!CredFree` at `0x140090ae3`
- `ADVAPI32!CredReadDomainCredentialsW` at `0x140090952`
- `ADVAPI32!CredReadDomainCredentialsW` at `0x140090952`

## string_xrefs

- `0x1400909c0`: `CredReadDomainCredentials failed`
- `0x140090a78`: `CredDelete for canonical name failed`
- `0x140090ab3`: `CredDelete failed`
- `0x1400908fb`: `StringCchCopy`

## pseudocode

```c
__int64 __fastcall AACredHelper::CleanUpCreds(const unsigned __int16 *a1)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v3; // ebx
  unsigned int v4; // eax
  int v5; // edx
  const char *v6; // rcx
  signed int LastError; // eax
  const WCHAR *Comment; // rcx
  signed int v9; // eax
  signed int v10; // eax
  DWORD Count; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+34h] [rbp-CCh] BYREF
  PCREDENTIALW *Credential; // [rsp+38h] [rbp-C8h] BYREF
  _CREDENTIAL_TARGET_INFORMATIONW TargetInfo; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR TargetName[264]; // [rsp+90h] [rbp-70h] BYREF

  Count = 0;
  Credential = 0;
  memset_0(&TargetInfo, 0, sizeof(TargetInfo));
  v13 = 2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)a1);
  }
  v3 = StringCbCopyW(TargetName, 0x20Au, a1);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 25;
      v6 = "StringCchCopy";
LABEL_47:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
        v4,
        (__int64)v6,
        v3);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  memset_0(&TargetInfo, 0, sizeof(TargetInfo));
  TargetInfo.CredTypeCount = 1;
  TargetInfo.TargetName = TargetName;
  TargetInfo.Flags = 1;
  TargetInfo.CredTypes = (LPDWORD)&v13;
  TargetInfo.DnsServerName = TargetName;
  if ( CredReadDomainCredentialsW(&TargetInfo, 0, &Count, &Credential) )
    goto LABEL_22;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 )
  {
    if ( v3 == -2147023728 )
    {
LABEL_16:
      v3 = 0;
      goto LABEL_48;
    }
    if ( v3 < 0 )
      goto LABEL_18;
LABEL_22:
    if ( Count )
    {
      Comment = (*Credential)->Comment;
      if ( Comment )
      {
        if ( !CredDeleteW(Comment, 2u, 0) )
        {
          v9 = GetLastError();
          v3 = v9;
          if ( v9 > 0 )
            v3 = (unsigned __int16)v9 | 0x80070000;
          if ( !v3 )
          {
            v3 = -2147467259;
LABEL_37:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v4 = RdpWppGetCurrentThreadActivityIdPrefix();
              v5 = 27;
              v6 = "CredDelete for canonical name failed";
              goto LABEL_47;
            }
            goto LABEL_48;
          }
          if ( v3 == -2147023728 )
          {
            v3 = 0;
          }
          else if ( v3 < 0 )
          {
            goto LABEL_37;
          }
        }
      }
    }
    if ( CredDeleteW(TargetName, 2u, 0) )
      goto LABEL_48;
    v10 = GetLastError();
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v3 )
    {
      if ( v3 == -2147023728 )
        goto LABEL_16;
      if ( v3 >= 0 )
        goto LABEL_48;
    }
    else
    {
      v3 = -2147467259;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 28;
      v6 = "CredDelete failed";
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  v3 = -2147467259;
LABEL_18:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 26;
    v6 = "CredReadDomainCredentials failed";
    goto LABEL_47;
  }
LABEL_48:
  if ( Credential )
    CredFree(Credential);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14009080c  mov     [rsp-8+arg_8], rbx
0x140090811  mov     [rsp-8+arg_10], r12
0x140090816  push    rbp
0x140090817  push    r13
0x140090819  push    r14
0x14009081b  lea     rbp, [rsp-1B0h]
0x140090823  sub     rsp, 2B0h
0x14009082a  mov     rax, cs:__security_cookie
0x140090831  xor     rax, rsp
0x140090834  mov     [rbp+1C0h+var_20], rax
0x14009083b  mov     rbx, rcx
0x14009083e  mov     [rsp+2C0h+Count], 0
0x140090846  mov     r13d, 48h ; 'H'
0x14009084c  mov     [rsp+2C0h+Credential], 0
0x140090855  mov     r8d, r13d; Size
0x140090858  lea     rcx, [rsp+2C0h+TargetInfo]; void *
0x14009085d  xor     edx, edx; Val
0x14009085f  call    memset_0
0x140090864  mov     [rsp+2C0h+var_28C], 2
0x14009086c  mov     rax, cs:WPP_GLOBAL_Control
0x140090873  lea     r14, WPP_GLOBAL_Control
0x14009087a  lea     r12, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140090881  cmp     rax, r14
0x140090884  jz      short loc_1400908B6
0x140090886  test    byte ptr [rax+1Ch], 1
0x14009088a  jz      short loc_1400908B6
0x14009088c  cmp     byte ptr [rax+19h], 5
0x140090890  jb      short loc_1400908B6
0x140090892  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140090897  mov     rcx, cs:WPP_GLOBAL_Control
0x14009089e  lea     edx, [r13-30h]
0x1400908a2  mov     r9d, eax
0x1400908a5  mov     [rsp+2C0h+var_2A0], rbx
0x1400908aa  mov     r8, r12
0x1400908ad  mov     rcx, [rcx+10h]
0x1400908b1  call    WPP_SF_DS
0x1400908b6  mov     r8, rbx; unsigned __int16 *
0x1400908b9  lea     rcx, [rbp+1C0h+TargetName]; unsigned __int16 *
0x1400908bd  mov     edx, 20Ah; unsigned __int64
0x1400908c2  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400908c7  mov     ebx, eax
0x1400908c9  test    eax, eax
0x1400908cb  jns     short loc_140090907
0x1400908cd  mov     rax, cs:WPP_GLOBAL_Control
0x1400908d4  cmp     rax, r14
0x1400908d7  jz      loc_140090AD9
0x1400908dd  test    byte ptr [rax+1Ch], 8
0x1400908e1  jz      loc_140090AD9
0x1400908e7  cmp     byte ptr [rax+19h], 2
0x1400908eb  jb      loc_140090AD9
0x1400908f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400908f6  mov     edx, 19h
0x1400908fb  lea     rcx, aStringcchcopy; "StringCchCopy"
0x140090902  jmp     loc_140090ABA
0x140090907  mov     r8, r13; Size
0x14009090a  lea     rcx, [rsp+2C0h+TargetInfo]; void *
0x14009090f  xor     edx, edx; Val
0x140090911  call    memset_0
0x140090916  lea     rax, [rbp+1C0h+TargetName]
0x14009091a  mov     [rsp+2C0h+TargetInfo.CredTypeCount], 1
0x140090922  mov     [rsp+2C0h+TargetInfo.TargetName], rax
0x140090927  lea     r9, [rsp+2C0h+Credential]; Credential
0x14009092c  lea     rax, [rsp+2C0h+var_28C]
0x140090931  mov     [rsp+2C0h+TargetInfo.Flags], 1
0x140090939  mov     [rbp+1C0h+TargetInfo.CredTypes], rax
0x14009093d  lea     r8, [rsp+2C0h+Count]; Count
0x140090942  lea     rax, [rbp+1C0h+TargetName]
0x140090946  xor     edx, edx; Flags
0x140090948  lea     rcx, [rsp+2C0h+TargetInfo]; TargetInfo
0x14009094d  mov     [rsp+2C0h+TargetInfo.DnsServerName], rax
0x140090952  call    cs:__imp_CredReadDomainCredentialsW
0x140090958  mov     r13d, 80070000h
0x14009095e  test    eax, eax
0x140090960  jnz     short loc_1400909CC
0x140090962  call    cs:__imp_GetLastError
0x140090968  mov     ebx, eax
0x14009096a  test    eax, eax
0x14009096c  jle     short loc_140090974
0x14009096e  movzx   ebx, ax
0x140090971  or      ebx, r13d
0x140090974  test    ebx, ebx
0x140090976  jnz     short loc_14009097F
0x140090978  mov     ebx, 80004005h
0x14009097d  jmp     short loc_140090992
0x14009097f  cmp     ebx, 80070490h
0x140090985  jnz     short loc_14009098E
0x140090987  xor     ebx, ebx
0x140090989  jmp     loc_140090AD9
0x14009098e  test    ebx, ebx
0x140090990  jns     short loc_1400909CC
0x140090992  mov     rax, cs:WPP_GLOBAL_Control
0x140090999  cmp     rax, r14
0x14009099c  jz      loc_140090AD9
0x1400909a2  test    byte ptr [rax+1Ch], 8
0x1400909a6  jz      loc_140090AD9
0x1400909ac  cmp     byte ptr [rax+19h], 2
0x1400909b0  jb      loc_140090AD9
0x1400909b6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400909bb  mov     edx, 1Ah
0x1400909c0  lea     rcx, aCredreaddomain_1; "CredReadDomainCredentials failed"
0x1400909c7  jmp     loc_140090ABA
0x1400909cc  cmp     [rsp+2C0h+Count], 0
0x1400909d1  jbe     short loc_140090A1C
0x1400909d3  mov     rax, [rsp+2C0h+Credential]
0x1400909d8  mov     rcx, [rax]
0x1400909db  mov     rcx, [rcx+10h]; TargetName
0x1400909df  test    rcx, rcx
0x1400909e2  jz      short loc_140090A1C
0x1400909e4  xor     r8d, r8d; Flags
0x1400909e7  lea     edx, [r8+2]; Type
0x1400909eb  call    cs:__imp_CredDeleteW
0x1400909f1  test    eax, eax
0x1400909f3  jnz     short loc_140090A1C
0x1400909f5  call    cs:__imp_GetLastError
0x1400909fb  mov     ebx, eax
0x1400909fd  test    eax, eax
0x1400909ff  jle     short loc_140090A07
0x140090a01  movzx   ebx, ax
0x140090a04  or      ebx, r13d
0x140090a07  test    ebx, ebx
0x140090a09  jnz     short loc_140090A12
0x140090a0b  mov     ebx, 80004005h
0x140090a10  jmp     short loc_140090A56
0x140090a12  cmp     ebx, 80070490h
0x140090a18  jnz     short loc_140090A52
0x140090a1a  xor     ebx, ebx
0x140090a1c  xor     r8d, r8d; Flags
0x140090a1f  lea     rcx, [rbp+1C0h+TargetName]; TargetName
0x140090a23  lea     edx, [r8+2]; Type
0x140090a27  call    cs:__imp_CredDeleteW
0x140090a2d  test    eax, eax
0x140090a2f  jnz     loc_140090AD9
0x140090a35  call    cs:__imp_GetLastError
0x140090a3b  mov     ebx, eax
0x140090a3d  test    eax, eax
0x140090a3f  jle     short loc_140090A47
0x140090a41  movzx   ebx, ax
0x140090a44  or      ebx, r13d
0x140090a47  test    ebx, ebx
0x140090a49  jnz     short loc_140090A81
0x140090a4b  mov     ebx, 80004005h
0x140090a50  jmp     short loc_140090A91
0x140090a52  test    ebx, ebx
0x140090a54  jns     short loc_140090A1C
0x140090a56  mov     rax, cs:WPP_GLOBAL_Control
0x140090a5d  cmp     rax, r14
0x140090a60  jz      short loc_140090AD9
0x140090a62  test    byte ptr [rax+1Ch], 8
0x140090a66  jz      short loc_140090AD9
0x140090a68  cmp     byte ptr [rax+19h], 2
0x140090a6c  jb      short loc_140090AD9
0x140090a6e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140090a73  mov     edx, 1Bh
0x140090a78  lea     rcx, aCreddeleteForC; "CredDelete for canonical name failed"
0x140090a7f  jmp     short loc_140090ABA
0x140090a81  cmp     ebx, 80070490h
0x140090a87  jz      loc_140090987
0x140090a8d  test    ebx, ebx
0x140090a8f  jns     short loc_140090AD9
0x140090a91  mov     rax, cs:WPP_GLOBAL_Control
0x140090a98  cmp     rax, r14
0x140090a9b  jz      short loc_140090AD9
0x140090a9d  test    byte ptr [rax+1Ch], 8
0x140090aa1  jz      short loc_140090AD9
0x140090aa3  cmp     byte ptr [rax+19h], 2
0x140090aa7  jb      short loc_140090AD9
0x140090aa9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140090aae  mov     edx, 1Ch
0x140090ab3  lea     rcx, aCreddeleteFail; "CredDelete failed"
0x140090aba  mov     [rsp+2C0h+var_298], ebx
0x140090abe  mov     r9d, eax
0x140090ac1  mov     [rsp+2C0h+var_2A0], rcx
0x140090ac6  mov     r8, r12
0x140090ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x140090ad0  mov     rcx, [rcx+10h]
0x140090ad4  call    WPP_SF_DsD
0x140090ad9  mov     rcx, [rsp+2C0h+Credential]; Buffer
0x140090ade  test    rcx, rcx
0x140090ae1  jz      short loc_140090AE9
0x140090ae3  call    cs:__imp_CredFree
0x140090ae9  mov     eax, ebx
0x140090aeb  mov     rcx, [rbp+1C0h+var_20]
0x140090af2  xor     rcx, rsp; StackCookie
0x140090af5  call    __security_check_cookie
0x140090afa  lea     r11, [rsp+2C0h+var_10]
0x140090b02  mov     rbx, [r11+28h]
0x140090b06  mov     r12, [r11+30h]
0x140090b0a  mov     rsp, r11
0x140090b0d  pop     r14
0x140090b0f  pop     r13
0x140090b11  pop     rbp
0x140090b12  retn
```
