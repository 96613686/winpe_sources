# CManagerThread::CreateMaintenanceModeEvent(void)

- ea: `0x1800029e0`
- end: `0x180002f1c`
- name: `?CreateMaintenanceModeEvent@CManagerThread@@QEAAJXZ`
- size: `1340`
- prototype: `__int64 __fastcall(CManagerThread *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800026a0`

## callees

- `0x1800029e0`
- `0x18000ca14`
- `0x18000d0dc`
- `0x18000d910`
- `0x18000d970`
- `0x18000daf0`
- `0x180011980`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180002ee1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002eea`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002ef3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002ee1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002eea`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002ef3`
- `msvcrt!swprintf_s` at `0x180002e4c`
- `msvcrt!swprintf_s` at `0x180002e4c`
- `ADVAPI32!SystemFunction036` at `0x180002e21`
- `ADVAPI32!SystemFunction036` at `0x180002e21`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180002d9f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180002d9f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180002d46`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180002d46`
- `ADVAPI32!AddAccessAllowedAce` at `0x180002c9d`
- `ADVAPI32!AddAccessAllowedAce` at `0x180002cf2`
- `ADVAPI32!AddAccessAllowedAce` at `0x180002c9d`
- `ADVAPI32!AddAccessAllowedAce` at `0x180002cf2`
- `ADVAPI32!InitializeAcl` at `0x180002c32`
- `ADVAPI32!InitializeAcl` at `0x180002c32`
- `ADVAPI32!GetLengthSid` at `0x180002bb8`
- `ADVAPI32!GetLengthSid` at `0x180002bc3`
- `ADVAPI32!GetLengthSid` at `0x180002bb8`
- `ADVAPI32!GetLengthSid` at `0x180002bc3`
- `ADVAPI32!CreateWellKnownSid` at `0x180002b04`
- `ADVAPI32!CreateWellKnownSid` at `0x180002b6e`
- `ADVAPI32!CreateWellKnownSid` at `0x180002b04`
- `ADVAPI32!CreateWellKnownSid` at `0x180002b6e`
- `KERNEL32!CreateEventW` at `0x180002e63`
- `KERNEL32!CreateEventW` at `0x180002e63`
- `KERNEL32!GetLastError` at `0x180002b0e`
- `KERNEL32!GetLastError` at `0x180002b78`
- `KERNEL32!GetLastError` at `0x180002c3c`
- `KERNEL32!GetLastError` at `0x180002ca7`
- `KERNEL32!GetLastError` at `0x180002cfc`
- `KERNEL32!GetLastError` at `0x180002d50`
- `KERNEL32!GetLastError` at `0x180002da9`
- `KERNEL32!GetLastError` at `0x180002b0e`
- `KERNEL32!GetLastError` at `0x180002b78`
- `KERNEL32!GetLastError` at `0x180002c3c`
- `KERNEL32!GetLastError` at `0x180002ca7`
- `KERNEL32!GetLastError` at `0x180002cfc`
- `KERNEL32!GetLastError` at `0x180002d50`
- `KERNEL32!GetLastError` at `0x180002da9`

## string_xrefs

- `0x180002a83`: `authUsersSid`
- `0x180002adf`: `creatorOwnerSid`

## pseudocode

```c
__int64 __fastcall CManagerThread::CreateMaintenanceModeEvent(CManagerThread *this)
{
  void *v1; // r12
  unsigned int v2; // ebx
  void *v3; // r15
  signed int LastError; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  signed int v7; // eax
  DWORD LengthSid; // ebx
  DWORD v9; // ebx
  ACL *v10; // rax
  ACL *v11; // r14
  signed int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  unsigned int i; // esi
  int RandomBuffer; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v22; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-C8h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h]
  wchar_t Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  v26 = 0;
  v22 = 0;
  dword_180019958 = 0;
  cbSid = 68;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v1 = operator new[](0x44u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v1 )
  {
    v22 = 68;
    v3 = operator new[](0x44u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v3 )
    {
      v2 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          73,
          &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          "creatorOwnerSid");
      goto LABEL_72;
    }
    if ( !CreateWellKnownSid(WinAuthenticatedUserSid, 0, v1, &cbSid) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_71;
      v6 = 74;
      goto LABEL_15;
    }
    if ( !CreateWellKnownSid(WinCreatorOwnerSid, 0, v3, &v22) )
    {
      v7 = GetLastError();
      v2 = v7;
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_71;
      v6 = 75;
LABEL_15:
      WPP_SF_d(v5[2], v6, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v2);
LABEL_71:
      operator delete[](v3);
LABEL_72:
      operator delete[](v1);
      return v2;
    }
    LengthSid = GetLengthSid(v3);
    v9 = GetLengthSid(v1) + 32 + LengthSid;
    v10 = (ACL *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( !v10 )
    {
      v2 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, "dacl");
      goto LABEL_71;
    }
    if ( InitializeAcl(v10, v9, 2u) )
    {
      if ( AddAccessAllowedAce(v11, 2u, 0x100000u, v1) )
      {
        if ( AddAccessAllowedAce(v11, 2u, 0x10002u, v3) )
        {
          if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
          {
            if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v11, 0) )
            {
              v2 = 0;
              EventAttributes.nLength = 24;
              EventAttributes.bInheritHandle = 0;
              EventAttributes.lpSecurityDescriptor = pSecurityDescriptor;
              for ( i = 0; i < 0xA; ++i )
              {
                RandomBuffer = 0;
                SystemFunction036(&RandomBuffer, 4u);
                if ( !RandomBuffer )
                  RandomBuffer = 1;
                swprintf_s(Buffer, 0x105u, L"Global\\FhMaintenanceModeEvent-%x");
                qword_180019950 = CreateEventW(&EventAttributes, 1, 1, Buffer);
                if ( qword_180019950 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    WPP_SF_S(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      83,
                      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
                      Buffer);
                  dword_180019958 = RandomBuffer;
                  goto LABEL_70;
                }
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    82,
                    (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
                    (unsigned int)Buffer,
                    0);
              }
              goto LABEL_70;
            }
            v18 = GetLastError();
            v2 = v18;
            if ( v18 > 0 )
              v2 = (unsigned __int16)v18 | 0x80070000;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
LABEL_70:
              operator delete[](v11);
              goto LABEL_71;
            }
            v14 = 81;
          }
          else
          {
            v17 = GetLastError();
            v2 = v17;
            if ( v17 > 0 )
              v2 = (unsigned __int16)v17 | 0x80070000;
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v14 = 80;
          }
        }
        else
        {
          v16 = GetLastError();
          v2 = v16;
          if ( v16 > 0 )
            v2 = (unsigned __int16)v16 | 0x80070000;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_70;
          v14 = 79;
        }
      }
      else
      {
        v15 = GetLastError();
        v2 = v15;
        if ( v15 > 0 )
          v2 = (unsigned __int16)v15 | 0x80070000;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_70;
        v14 = 78;
      }
    }
    else
    {
      v12 = GetLastError();
      v2 = v12;
      if ( v12 > 0 )
        v2 = (unsigned __int16)v12 | 0x80070000;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_70;
      v14 = 77;
    }
    WPP_SF_d(v13[2], v14, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v2);
    goto LABEL_70;
  }
  v2 = -2147024882;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, "authUsersSid");
  return v2;
}

```

## disassembly

```asm
0x1800029e0  push    rbp
0x1800029e2  push    rbx
0x1800029e3  push    rsi
0x1800029e4  push    rdi
0x1800029e5  push    r12
0x1800029e7  push    r14
0x1800029e9  push    r15
0x1800029eb  lea     rbp, [rsp-1A0h]
0x1800029f3  sub     rsp, 2A0h
0x1800029fa  mov     rax, cs:__security_cookie
0x180002a01  xor     rax, rsp
0x180002a04  mov     [rbp+1D0h+var_40], rax
0x180002a0b  xor     eax, eax
0x180002a0d  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180002a14  xorps   xmm1, xmm1
0x180002a17  mov     qword ptr [rsp+2D0h+EventAttributes.bInheritHandle], rax
0x180002a1c  xorps   xmm0, xmm0
0x180002a1f  mov     [rsp+2D0h+var_258], rax
0x180002a24  mov     rdx, rdi; struct std::nothrow_t *
0x180002a27  mov     [rsp+2D0h+var_29C], eax
0x180002a2b  lea     ebx, [rax+44h]
0x180002a2e  mov     cs:dword_180019958, eax
0x180002a34  mov     ecx, ebx; unsigned __int64
0x180002a36  mov     [rsp+2D0h+cbSid], ebx
0x180002a3a  movups  xmmword ptr [rsp+2D0h+EventAttributes.nLength], xmm0
0x180002a3f  movups  [rsp+2D0h+pSecurityDescriptor], xmm1
0x180002a44  movups  [rsp+2D0h+var_268], xmm1
0x180002a49  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002a4e  mov     r12, rax
0x180002a51  test    rax, rax
0x180002a54  jnz     short loc_180002A9B
0x180002a56  mov     ebx, 8007000Eh
0x180002a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a62  lea     rdi, WPP_GLOBAL_Control
0x180002a69  cmp     rcx, rdi
0x180002a6c  jz      loc_180002EF9
0x180002a72  test    byte ptr [rcx+1Ch], 1
0x180002a76  jz      loc_180002EF9
0x180002a7c  mov     rcx, [rcx+10h]
0x180002a80  lea     edx, [rax+48h]
0x180002a83  lea     r9, aAuthuserssid; "authUsersSid"
0x180002a8a  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180002a91  call    WPP_SF_s
0x180002a96  jmp     loc_180002EF9
0x180002a9b  mov     rdx, rdi; struct std::nothrow_t *
0x180002a9e  mov     [rsp+2D0h+var_29C], ebx
0x180002aa2  mov     rcx, rbx; unsigned __int64
0x180002aa5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002aaa  mov     r15, rax
0x180002aad  test    rax, rax
0x180002ab0  jnz     short loc_180002AF7
0x180002ab2  mov     ebx, 8007000Eh
0x180002ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002abe  lea     rdi, WPP_GLOBAL_Control
0x180002ac5  cmp     rcx, rdi
0x180002ac8  jz      loc_180002EF0
0x180002ace  test    byte ptr [rcx+1Ch], 1
0x180002ad2  jz      loc_180002EF0
0x180002ad8  mov     rcx, [rcx+10h]
0x180002adc  lea     edx, [rax+49h]
0x180002adf  lea     r9, aCreatorownersi; "creatorOwnerSid"
0x180002ae6  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180002aed  call    WPP_SF_s
0x180002af2  jmp     loc_180002EF0
0x180002af7  xor     edx, edx; DomainSid
0x180002af9  lea     r9, [rsp+2D0h+cbSid]; cbSid
0x180002afe  mov     r8, r12; pSid
0x180002b01  lea     ecx, [rdx+11h]; WellKnownSidType
0x180002b04  call    cs:__imp_CreateWellKnownSid
0x180002b0a  test    eax, eax
0x180002b0c  jnz     short loc_180002B61
0x180002b0e  call    cs:__imp_GetLastError
0x180002b14  mov     ebx, eax
0x180002b16  test    eax, eax
0x180002b18  jle     short loc_180002B23
0x180002b1a  movzx   ebx, ax
0x180002b1d  or      ebx, 80070000h
0x180002b23  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b2a  lea     rdi, WPP_GLOBAL_Control
0x180002b31  cmp     rcx, rdi
0x180002b34  jz      loc_180002EE7
0x180002b3a  test    byte ptr [rcx+1Ch], 1
0x180002b3e  jz      loc_180002EE7
0x180002b44  mov     edx, 4Ah ; 'J'
0x180002b49  mov     rcx, [rcx+10h]
0x180002b4d  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180002b54  mov     r9d, ebx
0x180002b57  call    WPP_SF_d
0x180002b5c  jmp     loc_180002EE7
0x180002b61  xor     edx, edx; DomainSid
0x180002b63  lea     r9, [rsp+2D0h+var_29C]; cbSid
0x180002b68  mov     r8, r15; pSid
0x180002b6b  lea     ecx, [rdx+3]; WellKnownSidType
0x180002b6e  call    cs:__imp_CreateWellKnownSid
0x180002b74  test    eax, eax
0x180002b76  jnz     short loc_180002BB5
0x180002b78  call    cs:__imp_GetLastError
0x180002b7e  mov     ebx, eax
0x180002b80  test    eax, eax
0x180002b82  jle     short loc_180002B8D
0x180002b84  movzx   ebx, ax
0x180002b87  or      ebx, 80070000h
0x180002b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b94  lea     rdi, WPP_GLOBAL_Control
0x180002b9b  cmp     rcx, rdi
0x180002b9e  jz      loc_180002EE7
0x180002ba4  test    byte ptr [rcx+1Ch], 1
0x180002ba8  jz      loc_180002EE7
0x180002bae  mov     edx, 4Bh ; 'K'
0x180002bb3  jmp     short loc_180002B49
0x180002bb5  mov     rcx, r15; pSid
0x180002bb8  call    cs:__imp_GetLengthSid
0x180002bbe  mov     rcx, r12; pSid
0x180002bc1  mov     ebx, eax
0x180002bc3  call    cs:__imp_GetLengthSid
0x180002bc9  add     eax, 20h ; ' '
0x180002bcc  mov     rdx, rdi; struct std::nothrow_t *
0x180002bcf  add     ebx, eax
0x180002bd1  mov     ecx, ebx; unsigned __int64
0x180002bd3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002bd8  mov     r14, rax
0x180002bdb  test    rax, rax
0x180002bde  jnz     short loc_180002C25
0x180002be0  mov     ebx, 8007000Eh
0x180002be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bec  lea     rdi, WPP_GLOBAL_Control
0x180002bf3  cmp     rcx, rdi
0x180002bf6  jz      loc_180002EE7
0x180002bfc  test    byte ptr [rcx+1Ch], 1
0x180002c00  jz      loc_180002EE7
0x180002c06  mov     rcx, [rcx+10h]
0x180002c0a  lea     edx, [rax+4Ch]
0x180002c0d  lea     r9, aDacl; "dacl"
0x180002c14  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180002c1b  call    WPP_SF_s
0x180002c20  jmp     loc_180002EE7
0x180002c25  mov     edi, 2
0x180002c2a  mov     edx, ebx; nAclLength
0x180002c2c  mov     r8d, edi; dwAclRevision
0x180002c2f  mov     rcx, r14; pAcl
0x180002c32  call    cs:__imp_InitializeAcl
0x180002c38  test    eax, eax
0x180002c3a  jnz     short loc_180002C8F
0x180002c3c  call    cs:__imp_GetLastError
0x180002c42  mov     ebx, eax
0x180002c44  test    eax, eax
0x180002c46  jle     short loc_180002C51
0x180002c48  movzx   ebx, ax
0x180002c4b  or      ebx, 80070000h
0x180002c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c58  lea     rdi, WPP_GLOBAL_Control
0x180002c5f  cmp     rcx, rdi
0x180002c62  jz      loc_180002EDE
0x180002c68  test    byte ptr [rcx+1Ch], 1
0x180002c6c  jz      loc_180002EDE
0x180002c72  mov     edx, 4Dh ; 'M'
0x180002c77  mov     rcx, [rcx+10h]
0x180002c7b  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180002c82  mov     r9d, ebx
0x180002c85  call    WPP_SF_d
0x180002c8a  jmp     loc_180002EDE
0x180002c8f  mov     r9, r12; pSid
0x180002c92  mov     r8d, 100000h; AccessMask
0x180002c98  mov     edx, edi; dwAceRevision
0x180002c9a  mov     rcx, r14; pAcl
0x180002c9d  call    cs:__imp_AddAccessAllowedAce
0x180002ca3  test    eax, eax
0x180002ca5  jnz     short loc_180002CE4
0x180002ca7  call    cs:__imp_GetLastError
0x180002cad  mov     ebx, eax
0x180002caf  test    eax, eax
0x180002cb1  jle     short loc_180002CBC
0x180002cb3  movzx   ebx, ax
0x180002cb6  or      ebx, 80070000h
0x180002cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cc3  lea     rdi, WPP_GLOBAL_Control
0x180002cca  cmp     rcx, rdi
0x180002ccd  jz      loc_180002EDE
0x180002cd3  test    byte ptr [rcx+1Ch], 1
0x180002cd7  jz      loc_180002EDE
0x180002cdd  mov     edx, 4Eh ; 'N'
0x180002ce2  jmp     short loc_180002C77
0x180002ce4  mov     r9, r15; pSid
0x180002ce7  mov     r8d, 10002h; AccessMask
0x180002ced  mov     edx, edi; dwAceRevision
0x180002cef  mov     rcx, r14; pAcl
0x180002cf2  call    cs:__imp_AddAccessAllowedAce
0x180002cf8  test    eax, eax
0x180002cfa  jnz     short loc_180002D3C
0x180002cfc  call    cs:__imp_GetLastError
0x180002d02  mov     ebx, eax
0x180002d04  test    eax, eax
0x180002d06  jle     short loc_180002D11
0x180002d08  movzx   ebx, ax
0x180002d0b  or      ebx, 80070000h
0x180002d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d18  lea     rdi, WPP_GLOBAL_Control
0x180002d1f  cmp     rcx, rdi
0x180002d22  jz      loc_180002EDE
0x180002d28  test    byte ptr [rcx+1Ch], 1
0x180002d2c  jz      loc_180002EDE
0x180002d32  mov     edx, 4Fh ; 'O'
0x180002d37  jmp     loc_180002C77
0x180002d3c  mov     edx, 1; dwRevision
0x180002d41  lea     rcx, [rsp+2D0h+pSecurityDescriptor]; pSecurityDescriptor
0x180002d46  call    cs:__imp_InitializeSecurityDescriptor
0x180002d4c  test    eax, eax
0x180002d4e  jnz     short loc_180002D90
0x180002d50  call    cs:__imp_GetLastError
0x180002d56  mov     ebx, eax
0x180002d58  test    eax, eax
0x180002d5a  jle     short loc_180002D65
0x180002d5c  movzx   ebx, ax
0x180002d5f  or      ebx, 80070000h
0x180002d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d6c  lea     rdi, WPP_GLOBAL_Control
0x180002d73  cmp     rcx, rdi
0x180002d76  jz      loc_180002EDE
0x180002d7c  test    byte ptr [rcx+1Ch], 1
0x180002d80  jz      loc_180002EDE
0x180002d86  mov     edx, 50h ; 'P'
0x180002d8b  jmp     loc_180002C77
0x180002d90  xor     r9d, r9d; bDaclDefaulted
0x180002d93  lea     rcx, [rsp+2D0h+pSecurityDescriptor]; pSecurityDescriptor
0x180002d98  mov     r8, r14; pDacl
0x180002d9b  lea     edx, [r9+1]; bDaclPresent
0x180002d9f  call    cs:__imp_SetSecurityDescriptorDacl
0x180002da5  test    eax, eax
0x180002da7  jnz     short loc_180002DE9
0x180002da9  call    cs:__imp_GetLastError
0x180002daf  mov     ebx, eax
0x180002db1  test    eax, eax
0x180002db3  jle     short loc_180002DBE
0x180002db5  movzx   ebx, ax
0x180002db8  or      ebx, 80070000h
0x180002dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dc5  lea     rdi, WPP_GLOBAL_Control
0x180002dcc  cmp     rcx, rdi
0x180002dcf  jz      loc_180002EDE
0x180002dd5  test    byte ptr [rcx+1Ch], 1
0x180002dd9  jz      loc_180002EDE
0x180002ddf  mov     edx, 51h ; 'Q'
0x180002de4  jmp     loc_180002C77
0x180002de9  xor     ebx, ebx
0x180002deb  mov     [rsp+2D0h+EventAttributes.nLength], 18h
0x180002df3  lea     rax, [rsp+2D0h+pSecurityDescriptor]
0x180002df8  mov     [rsp+2D0h+EventAttributes.bInheritHandle], ebx
0x180002dfc  mov     [rsp+2D0h+EventAttributes.lpSecurityDescriptor], rax
0x180002e01  lea     rdi, WPP_GLOBAL_Control
0x180002e08  xor     esi, esi
0x180002e0a  cmp     esi, 0Ah
0x180002e0d  jnb     loc_180002EDE
0x180002e13  mov     edx, 4; RandomBufferLength
0x180002e18  mov     [rsp+2D0h+RandomBuffer], ebx
0x180002e1c  lea     rcx, [rsp+2D0h+RandomBuffer]; RandomBuffer
0x180002e21  call    cs:__imp_SystemFunction036
0x180002e27  mov     r9d, [rsp+2D0h+RandomBuffer]
0x180002e2c  test    r9d, r9d
0x180002e2f  jnz     short loc_180002E3C
0x180002e31  mov     r9d, 1
0x180002e37  mov     [rsp+2D0h+RandomBuffer], r9d
0x180002e3c  lea     r8, aGlobalFhmainte; "Global\\FhMaintenanceModeEvent-%x"
0x180002e43  mov     edx, 105h; BufferCount
0x180002e48  lea     rcx, [rbp+1D0h+Buffer]; Buffer
0x180002e4c  call    cs:__imp_swprintf_s
0x180002e52  mov     edx, 1; bManualReset
0x180002e57  lea     r9, [rbp+1D0h+Buffer]; lpName
0x180002e5b  mov     r8d, edx; bInitialState
0x180002e5e  lea     rcx, [rsp+2D0h+EventAttributes]; lpEventAttributes
0x180002e63  call    cs:__imp_CreateEventW
0x180002e69  mov     cs:qword_180019950, rax
0x180002e70  test    rax, rax
0x180002e73  jnz     short loc_180002EA9
0x180002e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e7c  cmp     rcx, rdi
0x180002e7f  jz      short loc_180002EA2
0x180002e81  test    byte ptr [rcx+1Ch], 2
0x180002e85  jz      short loc_180002EA2
0x180002e87  mov     rcx, [rcx+10h]
0x180002e8b  lea     edx, [rax+52h]
0x180002e8e  lea     r9, [rbp+1D0h+Buffer]
0x180002e92  mov     [rsp+2D0h+var_2B0], ebx
0x180002e96  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180002e9d  call    WPP_SF_Sd
0x180002ea2  inc     esi
0x180002ea4  jmp     loc_180002E0A
0x180002ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eb0  cmp     rcx, rdi
0x180002eb3  jz      short loc_180002ED4
0x180002eb5  test    byte ptr [rcx+1Ch], 2
0x180002eb9  jz      short loc_180002ED4
0x180002ebb  mov     rcx, [rcx+10h]
0x180002ebf  lea     r9, [rbp+1D0h+Buffer]
0x180002ec3  mov     edx, 53h ; 'S'
0x180002ec8  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180002ecf  call    WPP_SF_S
0x180002ed4  mov     eax, [rsp+2D0h+RandomBuffer]
0x180002ed8  mov     cs:dword_180019958, eax
0x180002ede  mov     rcx, r14
0x180002ee1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
  ... truncated ...
```
