# AACredHelper::CleanUpCreds(ushort const *)

- ea: `0x14009297c`
- end: `0x140092c83`
- name: `?CleanUpCreds@AACredHelper@@SAJPEBG@Z`
- size: `775`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14004e5c8`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000d078`
- `0x14001e210`
- `0x140042394`
- `0x14009297c`
- `0x140113390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140092ad2`
- `KERNEL32!GetLastError` at `0x140092b65`
- `KERNEL32!GetLastError` at `0x140092ba5`
- `KERNEL32!GetLastError` at `0x140092ad2`
- `KERNEL32!GetLastError` at `0x140092b65`
- `KERNEL32!GetLastError` at `0x140092ba5`
- `ADVAPI32!CredDeleteW` at `0x140092b5b`
- `ADVAPI32!CredDeleteW` at `0x140092b97`
- `ADVAPI32!CredDeleteW` at `0x140092b5b`
- `ADVAPI32!CredDeleteW` at `0x140092b97`
- `ADVAPI32!CredFree` at `0x140092c53`
- `ADVAPI32!CredFree` at `0x140092c53`
- `ADVAPI32!CredReadDomainCredentialsW` at `0x140092ac2`
- `ADVAPI32!CredReadDomainCredentialsW` at `0x140092ac2`

## string_xrefs

- `0x140092be8`: `CredDelete for canonical name failed`
- `0x140092c23`: `CredDelete failed`
- `0x140092a6b`: `StringCchCopy`
- `0x140092b30`: `CredReadDomainCredentials failed`

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
0x14009297c  mov     [rsp-8+arg_8], rbx
0x140092981  mov     [rsp-8+arg_10], r12
0x140092986  push    rbp
0x140092987  push    r13
0x140092989  push    r14
0x14009298b  lea     rbp, [rsp-1B0h]
0x140092993  sub     rsp, 2B0h
0x14009299a  mov     rax, cs:__security_cookie
0x1400929a1  xor     rax, rsp
0x1400929a4  mov     [rbp+1C0h+var_20], rax
0x1400929ab  mov     rbx, rcx
0x1400929ae  mov     [rsp+2C0h+Count], 0
0x1400929b6  mov     r13d, 48h ; 'H'
0x1400929bc  mov     [rsp+2C0h+Credential], 0
0x1400929c5  mov     r8d, r13d; Size
0x1400929c8  lea     rcx, [rsp+2C0h+TargetInfo]; void *
0x1400929cd  xor     edx, edx; Val
0x1400929cf  call    memset_0
0x1400929d4  mov     [rsp+2C0h+var_28C], 2
0x1400929dc  mov     rax, cs:WPP_GLOBAL_Control
0x1400929e3  lea     r14, WPP_GLOBAL_Control
0x1400929ea  lea     r12, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x1400929f1  cmp     rax, r14
0x1400929f4  jz      short loc_140092A26
0x1400929f6  test    byte ptr [rax+1Ch], 1
0x1400929fa  jz      short loc_140092A26
0x1400929fc  cmp     byte ptr [rax+19h], 5
0x140092a00  jb      short loc_140092A26
0x140092a02  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092a07  mov     rcx, cs:WPP_GLOBAL_Control
0x140092a0e  lea     edx, [r13-30h]
0x140092a12  mov     r9d, eax
0x140092a15  mov     [rsp+2C0h+var_2A0], rbx
0x140092a1a  mov     r8, r12
0x140092a1d  mov     rcx, [rcx+10h]
0x140092a21  call    WPP_SF_DS
0x140092a26  mov     r8, rbx; unsigned __int16 *
0x140092a29  lea     rcx, [rbp+1C0h+TargetName]; unsigned __int16 *
0x140092a2d  mov     edx, 20Ah; unsigned __int64
0x140092a32  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140092a37  mov     ebx, eax
0x140092a39  test    eax, eax
0x140092a3b  jns     short loc_140092A77
0x140092a3d  mov     rax, cs:WPP_GLOBAL_Control
0x140092a44  cmp     rax, r14
0x140092a47  jz      loc_140092C49
0x140092a4d  test    byte ptr [rax+1Ch], 8
0x140092a51  jz      loc_140092C49
0x140092a57  cmp     byte ptr [rax+19h], 2
0x140092a5b  jb      loc_140092C49
0x140092a61  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092a66  mov     edx, 19h
0x140092a6b  lea     rcx, aStringcchcopy; "StringCchCopy"
0x140092a72  jmp     loc_140092C2A
0x140092a77  mov     r8, r13; Size
0x140092a7a  lea     rcx, [rsp+2C0h+TargetInfo]; void *
0x140092a7f  xor     edx, edx; Val
0x140092a81  call    memset_0
0x140092a86  lea     rax, [rbp+1C0h+TargetName]
0x140092a8a  mov     [rsp+2C0h+TargetInfo.CredTypeCount], 1
0x140092a92  mov     [rsp+2C0h+TargetInfo.TargetName], rax
0x140092a97  lea     r9, [rsp+2C0h+Credential]; Credential
0x140092a9c  lea     rax, [rsp+2C0h+var_28C]
0x140092aa1  mov     [rsp+2C0h+TargetInfo.Flags], 1
0x140092aa9  mov     [rbp+1C0h+TargetInfo.CredTypes], rax
0x140092aad  lea     r8, [rsp+2C0h+Count]; Count
0x140092ab2  lea     rax, [rbp+1C0h+TargetName]
0x140092ab6  xor     edx, edx; Flags
0x140092ab8  lea     rcx, [rsp+2C0h+TargetInfo]; TargetInfo
0x140092abd  mov     [rsp+2C0h+TargetInfo.DnsServerName], rax
0x140092ac2  call    cs:__imp_CredReadDomainCredentialsW
0x140092ac8  mov     r13d, 80070000h
0x140092ace  test    eax, eax
0x140092ad0  jnz     short loc_140092B3C
0x140092ad2  call    cs:__imp_GetLastError
0x140092ad8  mov     ebx, eax
0x140092ada  test    eax, eax
0x140092adc  jle     short loc_140092AE4
0x140092ade  movzx   ebx, ax
0x140092ae1  or      ebx, r13d
0x140092ae4  test    ebx, ebx
0x140092ae6  jnz     short loc_140092AEF
0x140092ae8  mov     ebx, 80004005h
0x140092aed  jmp     short loc_140092B02
0x140092aef  cmp     ebx, 80070490h
0x140092af5  jnz     short loc_140092AFE
0x140092af7  xor     ebx, ebx
0x140092af9  jmp     loc_140092C49
0x140092afe  test    ebx, ebx
0x140092b00  jns     short loc_140092B3C
0x140092b02  mov     rax, cs:WPP_GLOBAL_Control
0x140092b09  cmp     rax, r14
0x140092b0c  jz      loc_140092C49
0x140092b12  test    byte ptr [rax+1Ch], 8
0x140092b16  jz      loc_140092C49
0x140092b1c  cmp     byte ptr [rax+19h], 2
0x140092b20  jb      loc_140092C49
0x140092b26  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092b2b  mov     edx, 1Ah
0x140092b30  lea     rcx, aCredreaddomain_1; "CredReadDomainCredentials failed"
0x140092b37  jmp     loc_140092C2A
0x140092b3c  cmp     [rsp+2C0h+Count], 0
0x140092b41  jbe     short loc_140092B8C
0x140092b43  mov     rax, [rsp+2C0h+Credential]
0x140092b48  mov     rcx, [rax]
0x140092b4b  mov     rcx, [rcx+10h]; TargetName
0x140092b4f  test    rcx, rcx
0x140092b52  jz      short loc_140092B8C
0x140092b54  xor     r8d, r8d; Flags
0x140092b57  lea     edx, [r8+2]; Type
0x140092b5b  call    cs:__imp_CredDeleteW
0x140092b61  test    eax, eax
0x140092b63  jnz     short loc_140092B8C
0x140092b65  call    cs:__imp_GetLastError
0x140092b6b  mov     ebx, eax
0x140092b6d  test    eax, eax
0x140092b6f  jle     short loc_140092B77
0x140092b71  movzx   ebx, ax
0x140092b74  or      ebx, r13d
0x140092b77  test    ebx, ebx
0x140092b79  jnz     short loc_140092B82
0x140092b7b  mov     ebx, 80004005h
0x140092b80  jmp     short loc_140092BC6
0x140092b82  cmp     ebx, 80070490h
0x140092b88  jnz     short loc_140092BC2
0x140092b8a  xor     ebx, ebx
0x140092b8c  xor     r8d, r8d; Flags
0x140092b8f  lea     rcx, [rbp+1C0h+TargetName]; TargetName
0x140092b93  lea     edx, [r8+2]; Type
0x140092b97  call    cs:__imp_CredDeleteW
0x140092b9d  test    eax, eax
0x140092b9f  jnz     loc_140092C49
0x140092ba5  call    cs:__imp_GetLastError
0x140092bab  mov     ebx, eax
0x140092bad  test    eax, eax
0x140092baf  jle     short loc_140092BB7
0x140092bb1  movzx   ebx, ax
0x140092bb4  or      ebx, r13d
0x140092bb7  test    ebx, ebx
0x140092bb9  jnz     short loc_140092BF1
0x140092bbb  mov     ebx, 80004005h
0x140092bc0  jmp     short loc_140092C01
0x140092bc2  test    ebx, ebx
0x140092bc4  jns     short loc_140092B8C
0x140092bc6  mov     rax, cs:WPP_GLOBAL_Control
0x140092bcd  cmp     rax, r14
0x140092bd0  jz      short loc_140092C49
0x140092bd2  test    byte ptr [rax+1Ch], 8
0x140092bd6  jz      short loc_140092C49
0x140092bd8  cmp     byte ptr [rax+19h], 2
0x140092bdc  jb      short loc_140092C49
0x140092bde  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092be3  mov     edx, 1Bh
0x140092be8  lea     rcx, aCreddeleteForC; "CredDelete for canonical name failed"
0x140092bef  jmp     short loc_140092C2A
0x140092bf1  cmp     ebx, 80070490h
0x140092bf7  jz      loc_140092AF7
0x140092bfd  test    ebx, ebx
0x140092bff  jns     short loc_140092C49
0x140092c01  mov     rax, cs:WPP_GLOBAL_Control
0x140092c08  cmp     rax, r14
0x140092c0b  jz      short loc_140092C49
0x140092c0d  test    byte ptr [rax+1Ch], 8
0x140092c11  jz      short loc_140092C49
0x140092c13  cmp     byte ptr [rax+19h], 2
0x140092c17  jb      short loc_140092C49
0x140092c19  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092c1e  mov     edx, 1Ch
0x140092c23  lea     rcx, aCreddeleteFail; "CredDelete failed"
0x140092c2a  mov     [rsp+2C0h+var_298], ebx
0x140092c2e  mov     r9d, eax
0x140092c31  mov     [rsp+2C0h+var_2A0], rcx
0x140092c36  mov     r8, r12
0x140092c39  mov     rcx, cs:WPP_GLOBAL_Control
0x140092c40  mov     rcx, [rcx+10h]
0x140092c44  call    WPP_SF_DsD
0x140092c49  mov     rcx, [rsp+2C0h+Credential]; Buffer
0x140092c4e  test    rcx, rcx
0x140092c51  jz      short loc_140092C59
0x140092c53  call    cs:__imp_CredFree
0x140092c59  mov     eax, ebx
0x140092c5b  mov     rcx, [rbp+1C0h+var_20]
0x140092c62  xor     rcx, rsp; StackCookie
0x140092c65  call    __security_check_cookie
0x140092c6a  lea     r11, [rsp+2C0h+var_10]
0x140092c72  mov     rbx, [r11+28h]
0x140092c76  mov     r12, [r11+30h]
0x140092c7a  mov     rsp, r11
0x140092c7d  pop     r14
0x140092c7f  pop     r13
0x140092c81  pop     rbp
0x140092c82  retn
```
