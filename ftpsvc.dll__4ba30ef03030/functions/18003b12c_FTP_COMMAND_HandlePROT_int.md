# FTP_COMMAND::HandlePROT(int *)

- ea: `0x18003b12c`
- end: `0x18003b5a8`
- name: `?HandlePROT@FTP_COMMAND@@QEAAXPEAH@Z`
- size: `1148`
- prototype: `void __fastcall(FTP_COMMAND *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003732c`

## callees

- `0x180009090`
- `0x18002cb40`
- `0x180038ac0`
- `0x18003b12c`
- `0x18003e564`
- `0x18003f50c`
- `0x18003fed0`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003b591`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003b591`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b31b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b3d4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b466`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b4c6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b31b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b3d4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b466`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003b4c6`
- `iisutil!WriteRefTraceLog` at `0x18003b56f`
- `iisutil!WriteRefTraceLog` at `0x18003b56f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18003b402`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18003b50f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18003b402`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18003b50f`

## string_xrefs

- `0x18003b390`: `SSL certificate was not configured.`
- `0x18003b53f`: `%s command successful.`
- `0x18003b22a`: `Command valid only on secure connection.`
- `0x18003b268`: `Bad sequence of commands.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FTP_COMMAND::HandlePROT(FTP_SESSION **this, int *a2)
{
  struct FTP_SITE_CONFIG *ReferencedSiteConfig; // rsi
  FTP_SESSION *v5; // rcx
  struct _SecHandle *v6; // rbp
  int v7; // r9d
  int v8; // edi
  FTP_SESSION *v9; // rax
  const char *v10; // r8
  const char *v11; // rdx
  int v12; // eax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  int v15; // eax
  int v16; // eax
  unsigned __int32 v17; // ebx
  int v18; // [rsp+60h] [rbp+8h] BYREF

  v18 = 0;
  ReferencedSiteConfig = FTP_SESSION::GetReferencedSiteConfig(this[132]);
  v5 = this[132];
  v6 = (struct _SecHandle *)((char *)v5 + 2072);
  v7 = *((_DWORD *)this + 234);
  v8 = 1;
  if ( !v7 )
  {
    **((_BYTE **)v5 + 709) = 0;
    *((_DWORD *)v5 + 1422) = 0;
    *((_DWORD *)v5 + 1424) = 0;
    if ( *((_DWORD *)v5 + 275) != 2 )
    {
      if ( !*((_DWORD *)this + 292) )
        *((_DWORD *)this + 292) = -2147024120;
      FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, "503", "Command valid only on secure connection.");
      goto LABEL_72;
    }
    if ( !*((_DWORD *)this[132] + 1198) )
    {
      if ( !*((_DWORD *)this + 292) )
        *((_DWORD *)this + 292) = -2147024120;
      v10 = "Bad sequence of commands.";
      v11 = "503";
      goto LABEL_23;
    }
    if ( *((_DWORD *)this + 44) != 1 )
    {
      if ( !*((_DWORD *)this + 292) )
        *((_DWORD *)this + 292) = -2147024809;
      FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, "501", "Invalid argument.");
      goto LABEL_72;
    }
    *((_DWORD *)this + 234) = 1;
    FTP_DATA_CHANNEL::NotifyOnNewConnectionReady(
      (FTP_SESSION *)((char *)v5 + 2072),
      (struct FTP_ASYNC_CONTEXT *)(this + 109),
      &v18);
    if ( v18 )
    {
      v8 = 0;
      goto LABEL_77;
    }
LABEL_3:
    v9 = this[20];
    if ( *(_BYTE *)v9 != 67 )
    {
      switch ( *(_BYTE *)v9 )
      {
        case 'E':
          goto LABEL_55;
        case 'P':
          goto LABEL_31;
        case 'S':
          goto LABEL_55;
      }
      if ( *(_BYTE *)v9 != 99 )
      {
        if ( *(_BYTE *)v9 == 101 )
          goto LABEL_55;
        if ( *(_BYTE *)v9 != 112 )
        {
          if ( *(_BYTE *)v9 != 115 )
          {
            if ( !*((_DWORD *)this + 292) )
              *((_DWORD *)this + 292) = -2147024809;
            FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, "501", "Invalid argument.");
            goto LABEL_24;
          }
LABEL_55:
          if ( !*((_DWORD *)this + 292) )
            *((_DWORD *)this + 292) = -2147024891;
          if ( !*((_DWORD *)this + 274) )
          {
            *((_DWORD *)this + 274) = 24;
            STRU::Copy((STRU *)(this + 139), L"SSL policy requires SSL for data channel.");
            this[138] = this[143];
          }
          FTP_COMMAND::WriteResponseAndLog(
            (FTP_COMMAND *)this,
            "536",
            "Requested PROT level not supported by mechanism.");
          goto LABEL_24;
        }
LABEL_31:
        if ( *((_DWORD *)ReferencedSiteConfig + 29) == 2 )
        {
          if ( !*((_DWORD *)this + 292) )
            *((_DWORD *)this + 292) = -2147024891;
          if ( !*((_DWORD *)this + 274) )
          {
            *((_DWORD *)this + 274) = 27;
            STRU::Copy((STRU *)(this + 139), L"SSL policy denies SSL for data channel.");
            this[138] = this[143];
          }
          v10 = "Policy denies SSL.";
LABEL_66:
          v11 = "534";
LABEL_23:
          FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, v11, v10);
LABEL_24:
          *((_DWORD *)this[132] + 1424) = 1;
          goto LABEL_72;
        }
        v12 = FTP_DATA_CHANNEL::EnableSsl(v6);
        if ( v12 < 0 )
        {
          if ( !*((_DWORD *)this + 292) )
            *((_DWORD *)this + 292) = v12;
          switch ( v12 )
          {
            case -2146885628:
              v13 = 44;
              v14 = L"SSL certificate was not found.";
              break;
            case -2146893042:
              v13 = 45;
              v14 = L"Private key was not found for the specified SSL certificate.";
              break;
            case -2147024809:
              v13 = 31;
              v14 = L"SSL certificate was not configured.";
              break;
            case -2147023434:
              v13 = 46;
              v14 = L"SSL certificate hash has invalid length.";
              break;
            default:
              v13 = 32;
              v14 = L"SSL initialization failed.";
              break;
          }
          if ( !*((_DWORD *)this + 274) )
          {
            *((_DWORD *)this + 274) = v13;
            STRU::Copy((STRU *)(this + 139), v14);
            this[138] = this[143];
          }
LABEL_70:
          FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, "431", "Failed to setup secure session.");
          goto LABEL_24;
        }
        v15 = STRA::Copy((FTP_SESSION *)((char *)this[132] + 5640), (const char *)this[20]);
        if ( v15 < 0 )
        {
          if ( !*((_DWORD *)this + 292) )
            *((_DWORD *)this + 292) = v15;
          FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, "431", "Failed to setup secure session.");
          goto LABEL_72;
        }
        goto LABEL_71;
      }
    }
    if ( *((_DWORD *)ReferencedSiteConfig + 29) == 1 )
    {
      if ( !*((_DWORD *)this + 292) )
        *((_DWORD *)this + 292) = -2147024891;
      if ( !*((_DWORD *)this + 274) )
      {
        *((_DWORD *)this + 274) = 24;
        STRU::Copy((STRU *)(this + 139), L"SSL policy requires SSL for data channel.");
        this[138] = this[143];
      }
      v10 = "Policy requires SSL.";
      goto LABEL_66;
    }
    HIDWORD(v6[3].dwLower) = 0;
    SSL_STREAM_CONTEXT::DisableAndCleanupSslSession(v6 + 7);
    v16 = STRA::Copy((FTP_SESSION *)((char *)this[132] + 5640), (const char *)this[20]);
    if ( v16 < 0 )
    {
      if ( !*((_DWORD *)this + 292) )
        *((_DWORD *)this + 292) = v16;
      goto LABEL_70;
    }
LABEL_71:
    FTP_COMMAND::WriteResponseAndLog((FTP_COMMAND *)this, "200", "%s command successful.", (const char *)this[6]);
    goto LABEL_72;
  }
  if ( v7 == 1 )
    goto LABEL_3;
LABEL_72:
  v17 = _InterlockedDecrement((volatile signed __int32 *)ReferencedSiteConfig);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v17);
  if ( !v17 && ReferencedSiteConfig )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG(ReferencedSiteConfig);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, ReferencedSiteConfig);
  }
LABEL_77:
  *a2 = v8;
}

```

## disassembly

```asm
0x18003b12c  push    rbx
0x18003b12e  push    rbp
0x18003b12f  push    rsi
0x18003b130  push    rdi
0x18003b131  push    r14
0x18003b133  push    r15
0x18003b135  sub     rsp, 28h
0x18003b139  mov     r14, rdx
0x18003b13c  mov     rbx, rcx
0x18003b13f  xor     r15d, r15d
0x18003b142  mov     [rsp+58h+arg_0], r15d
0x18003b147  mov     rcx, [rcx+420h]; this
0x18003b14e  call    ?GetReferencedSiteConfig@FTP_SESSION@@QEAAPEAVFTP_SITE_CONFIG@@XZ; FTP_SESSION::GetReferencedSiteConfig(void)
0x18003b153  mov     rsi, rax
0x18003b156  mov     rcx, [rbx+420h]
0x18003b15d  lea     rbp, [rcx+818h]
0x18003b164  lea     rdx, [rbx+368h]; struct FTP_ASYNC_CONTEXT *
0x18003b16b  mov     r9d, [rdx+40h]
0x18003b16f  lea     edi, [r15+1]
0x18003b173  test    r9d, r9d
0x18003b176  jz      short loc_18003B1F6
0x18003b178  cmp     r9d, edi
0x18003b17b  jnz     loc_18003B555
0x18003b181  mov     rax, [rbx+0A0h]
0x18003b188  cmp     byte ptr [rax], 43h ; 'C'
0x18003b18b  jz      loc_18003B48D
0x18003b191  cmp     byte ptr [rax], 45h ; 'E'
0x18003b194  jz      loc_18003B432
0x18003b19a  cmp     byte ptr [rax], 50h ; 'P'
0x18003b19d  jz      loc_18003B2E1
0x18003b1a3  cmp     byte ptr [rax], 53h ; 'S'
0x18003b1a6  jz      loc_18003B432
0x18003b1ac  cmp     byte ptr [rax], 63h ; 'c'
0x18003b1af  jz      loc_18003B48D
0x18003b1b5  cmp     byte ptr [rax], 65h ; 'e'
0x18003b1b8  jz      loc_18003B432
0x18003b1be  cmp     byte ptr [rax], 70h ; 'p'
0x18003b1c1  jz      loc_18003B2E1
0x18003b1c7  cmp     byte ptr [rax], 73h ; 's'
0x18003b1ca  jz      loc_18003B432
0x18003b1d0  cmp     [rbx+490h], r15d
0x18003b1d7  jnz     short loc_18003B1E3
0x18003b1d9  mov     dword ptr [rbx+490h], 80070057h
0x18003b1e3  lea     r8, aInvalidArgumen; "Invalid argument."
0x18003b1ea  lea     rdx, a501; "501"
0x18003b1f1  jmp     loc_18003B276
0x18003b1f6  mov     rax, [rcx+1628h]
0x18003b1fd  mov     [rax], r15b
0x18003b200  mov     [rcx+1638h], r15d
0x18003b207  mov     [rcx+1640h], r15d
0x18003b20e  cmp     dword ptr [rcx+44Ch], 2
0x18003b215  jz      short loc_18003B245
0x18003b217  cmp     [rbx+490h], r15d
0x18003b21e  jnz     short loc_18003B22A
0x18003b220  mov     dword ptr [rbx+490h], 80070308h
0x18003b22a  lea     r8, aCommandValidOn; "Command valid only on secure connection"...
0x18003b231  lea     rdx, a503; "503"
0x18003b238  mov     rcx, rbx; this
0x18003b23b  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003b240  jmp     loc_18003B555
0x18003b245  mov     rax, [rbx+420h]
0x18003b24c  cmp     [rax+12B8h], r15d
0x18003b253  jnz     short loc_18003B290
0x18003b255  cmp     [rbx+490h], r15d
0x18003b25c  jnz     short loc_18003B268
0x18003b25e  mov     dword ptr [rbx+490h], 80070308h
0x18003b268  lea     r8, aBadSequenceOfC; "Bad sequence of commands."
0x18003b26f  lea     rdx, a503; "503"
0x18003b276  mov     rcx, rbx; this
0x18003b279  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003b27e  mov     rax, [rbx+420h]
0x18003b285  mov     [rax+1640h], edi
0x18003b28b  jmp     loc_18003B555
0x18003b290  cmp     [rbx+0B0h], edi
0x18003b296  jz      short loc_18003B2BE
0x18003b298  cmp     [rbx+490h], r15d
0x18003b29f  jnz     short loc_18003B2AB
0x18003b2a1  mov     dword ptr [rbx+490h], 80070057h
0x18003b2ab  lea     r8, aInvalidArgumen; "Invalid argument."
0x18003b2b2  lea     rdx, a501; "501"
0x18003b2b9  jmp     loc_18003B238
0x18003b2be  mov     [rdx+40h], edi
0x18003b2c1  lea     r8, [rsp+58h+arg_0]; int *
0x18003b2c6  mov     rcx, rbp; this
0x18003b2c9  call    ?NotifyOnNewConnectionReady@FTP_DATA_CHANNEL@@QEAAJPEAVFTP_ASYNC_CONTEXT@@PEAH@Z; FTP_DATA_CHANNEL::NotifyOnNewConnectionReady(FTP_ASYNC_CONTEXT *,int *)
0x18003b2ce  cmp     [rsp+58h+arg_0], r15d
0x18003b2d3  jz      loc_18003B181
0x18003b2d9  mov     edi, r15d
0x18003b2dc  jmp     loc_18003B598
0x18003b2e1  cmp     dword ptr [rsi+74h], 2
0x18003b2e5  jnz     short loc_18003B33B
0x18003b2e7  cmp     [rbx+490h], r15d
0x18003b2ee  jnz     short loc_18003B2FA
0x18003b2f0  mov     dword ptr [rbx+490h], 80070005h
0x18003b2fa  cmp     [rbx+448h], r15d
0x18003b301  jnz     short loc_18003B32F
0x18003b303  mov     dword ptr [rbx+448h], 1Bh
0x18003b30d  lea     rcx, [rbx+458h]
0x18003b314  lea     rdx, aSslPolicyDenie; "SSL policy denies SSL for data channel."
0x18003b31b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003b321  mov     rax, [rbx+478h]
0x18003b328  mov     [rbx+450h], rax
0x18003b32f  lea     r8, aPolicyDeniesSs; "Policy denies SSL."
0x18003b336  jmp     loc_18003B4E1
0x18003b33b  mov     rcx, rbp; this
0x18003b33e  call    ?EnableSsl@FTP_DATA_CHANNEL@@QEAAJXZ; FTP_DATA_CHANNEL::EnableSsl(void)
0x18003b343  test    eax, eax
0x18003b345  jns     loc_18003B3ED
0x18003b34b  cmp     [rbx+490h], r15d
0x18003b352  jnz     short loc_18003B35A
0x18003b354  mov     [rbx+490h], eax
0x18003b35a  cmp     eax, 80092004h
0x18003b35f  jnz     short loc_18003B36F
0x18003b361  mov     eax, 2Ch ; ','
0x18003b366  lea     rdx, aSslCertificate_0; "SSL certificate was not found."
0x18003b36d  jmp     short loc_18003B3BA
0x18003b36f  cmp     eax, 8009030Eh
0x18003b374  jnz     short loc_18003B384
0x18003b376  mov     eax, 2Dh ; '-'
0x18003b37b  lea     rdx, aPrivateKeyWasN; "Private key was not found for the speci"...
0x18003b382  jmp     short loc_18003B3BA
0x18003b384  cmp     eax, 80070057h
0x18003b389  jnz     short loc_18003B399
0x18003b38b  mov     eax, 1Fh
0x18003b390  lea     rdx, aSslCertificate; "SSL certificate was not configured."
0x18003b397  jmp     short loc_18003B3BA
0x18003b399  cmp     eax, 800705B6h
0x18003b39e  jnz     short loc_18003B3AE
0x18003b3a0  mov     eax, 2Eh ; '.'
0x18003b3a5  lea     rdx, aSslCertificate_1; "SSL certificate hash has invalid length"...
0x18003b3ac  jmp     short loc_18003B3BA
0x18003b3ae  mov     eax, 20h ; ' '
0x18003b3b3  lea     rdx, aSslInitializat; "SSL initialization failed."
0x18003b3ba  cmp     [rbx+448h], r15d
0x18003b3c1  jnz     loc_18003B528
0x18003b3c7  mov     [rbx+448h], eax
0x18003b3cd  lea     rcx, [rbx+458h]
0x18003b3d4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003b3da  mov     rax, [rbx+478h]
0x18003b3e1  mov     [rbx+450h], rax
0x18003b3e8  jmp     loc_18003B528
0x18003b3ed  mov     rcx, [rbx+420h]
0x18003b3f4  add     rcx, 1608h
0x18003b3fb  mov     rdx, [rbx+0A0h]
0x18003b402  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18003b408  test    eax, eax
0x18003b40a  jns     loc_18003B53B
0x18003b410  cmp     [rbx+490h], r15d
0x18003b417  jnz     short loc_18003B41F
0x18003b419  mov     [rbx+490h], eax
0x18003b41f  lea     r8, aFailedToSetupS; "Failed to setup secure session."
0x18003b426  lea     rdx, a431; "431"
0x18003b42d  jmp     loc_18003B238
0x18003b432  cmp     [rbx+490h], r15d
0x18003b439  jnz     short loc_18003B445
0x18003b43b  mov     dword ptr [rbx+490h], 80070005h
0x18003b445  cmp     [rbx+448h], r15d
0x18003b44c  jnz     short loc_18003B47A
0x18003b44e  mov     dword ptr [rbx+448h], 18h
0x18003b458  lea     rcx, [rbx+458h]
0x18003b45f  lea     rdx, aSslPolicyRequi_3; "SSL policy requires SSL for data channe"...
0x18003b466  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003b46c  mov     rax, [rbx+478h]
0x18003b473  mov     [rbx+450h], rax
0x18003b47a  lea     r8, aRequestedProtL; "Requested PROT level not supported by m"...
0x18003b481  lea     rdx, a536; "536"
0x18003b488  jmp     loc_18003B276
0x18003b48d  cmp     [rsi+74h], edi
0x18003b490  jnz     short loc_18003B4ED
0x18003b492  cmp     [rbx+490h], r15d
0x18003b499  jnz     short loc_18003B4A5
0x18003b49b  mov     dword ptr [rbx+490h], 80070005h
0x18003b4a5  cmp     [rbx+448h], r15d
0x18003b4ac  jnz     short loc_18003B4DA
0x18003b4ae  mov     dword ptr [rbx+448h], 18h
0x18003b4b8  lea     rcx, [rbx+458h]
0x18003b4bf  lea     rdx, aSslPolicyRequi_3; "SSL policy requires SSL for data channe"...
0x18003b4c6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003b4cc  mov     rax, [rbx+478h]
0x18003b4d3  mov     [rbx+450h], rax
0x18003b4da  lea     r8, aPolicyRequires_1; "Policy requires SSL."
0x18003b4e1  lea     rdx, a534; "534"
0x18003b4e8  jmp     loc_18003B276
0x18003b4ed  mov     [rbp+34h], r15d
0x18003b4f1  lea     rcx, [rbp+70h]; this
0x18003b4f5  call    ?DisableAndCleanupSslSession@SSL_STREAM_CONTEXT@@QEAAXXZ; SSL_STREAM_CONTEXT::DisableAndCleanupSslSession(void)
0x18003b4fa  mov     rcx, [rbx+420h]
0x18003b501  add     rcx, 1608h
0x18003b508  mov     rdx, [rbx+0A0h]
0x18003b50f  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18003b515  test    eax, eax
0x18003b517  jns     short loc_18003B53B
0x18003b519  cmp     [rbx+490h], r15d
0x18003b520  jnz     short loc_18003B528
0x18003b522  mov     [rbx+490h], eax
0x18003b528  lea     r8, aFailedToSetupS; "Failed to setup secure session."
0x18003b52f  lea     rdx, a431; "431"
0x18003b536  jmp     loc_18003B276
0x18003b53b  mov     r9, [rbx+30h]
0x18003b53f  lea     r8, aSCommandSucces; "%s command successful."
0x18003b546  lea     rdx, a200; "200"
0x18003b54d  mov     rcx, rbx; this
0x18003b550  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x18003b555  or      ebx, 0FFFFFFFFh
0x18003b558  lock xadd [rsi], ebx
0x18003b55c  dec     ebx
0x18003b55e  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003b565  test    rcx, rcx
0x18003b568  jz      short loc_18003B575
0x18003b56a  mov     r8, rsi
0x18003b56d  mov     edx, ebx
0x18003b56f  call    cs:__imp_WriteRefTraceLog
0x18003b575  test    ebx, ebx
0x18003b577  jnz     short loc_18003B598
0x18003b579  test    rsi, rsi
0x18003b57c  jz      short loc_18003B598
0x18003b57e  mov     rcx, rsi; this
0x18003b581  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003b586  nop
0x18003b587  mov     rdx, rsi
0x18003b58a  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003b591  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003b597  nop
0x18003b598  mov     [r14], edi
0x18003b59b  add     rsp, 28h
0x18003b59f  pop     r15
0x18003b5a1  pop     r14
0x18003b5a3  pop     rdi
0x18003b5a4  pop     rsi
0x18003b5a5  pop     rbp
0x18003b5a6  pop     rbx
0x18003b5a7  retn
```
