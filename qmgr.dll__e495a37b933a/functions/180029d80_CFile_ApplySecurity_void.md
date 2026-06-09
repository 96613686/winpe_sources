# CFile::ApplySecurity(void)

- ea: `0x180029d80`
- end: `0x18002a0e0`
- name: `?ApplySecurity@CFile@@QEAAJXZ`
- size: `864`
- prototype: `__int64 __fastcall(CFile *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180029a84`

## callees

- `0x180029d80`
- `0x18002a660`
- `0x18002ac74`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a1114`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f91`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a060`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a060`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180029df7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180029df7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180029e67`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180029e67`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180029eaf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180029eaf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180029f0b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180029f0b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180029f87`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180029f87`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFile::ApplySecurity(CFile *this)
{
  void *v2; // rcx
  unsigned int v3; // esi
  DWORD LastError; // ebx
  EVENT_LOG *v5; // rcx
  __int64 v6; // rdx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  unsigned int v11; // edi
  void *v12; // rcx
  int v13; // eax
  int v14; // edx
  unsigned int v15; // r14d
  int v16; // eax
  WINBOOL bGroupDefaulted; // [rsp+40h] [rbp-30h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+44h] [rbp-2Ch] BYREF
  WINBOOL bSaclDefaulted; // [rsp+48h] [rbp-28h] BYREF
  DWORD dwRevision; // [rsp+4Ch] [rbp-24h] BYREF
  PACL pSacl; // [rsp+50h] [rbp-20h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-18h] BYREF
  PSID pGroup; // [rsp+60h] [rbp-10h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-8h] BYREF
  WORD pControl; // [rsp+B0h] [rbp+40h] BYREF
  WINBOOL bDaclPresent; // [rsp+B8h] [rbp+48h] BYREF
  WINBOOL bSaclPresent; // [rsp+C0h] [rbp+50h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+C8h] [rbp+58h] BYREF

  if ( !*((_QWORD *)this + 38) )
  {
LABEL_56:
    *((_BYTE *)this + 256) = 1;
    CFile::TriggerSerialization(this, 1);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
      *((_QWORD *)this + 2) + 12LL);
  v2 = (void *)*((_QWORD *)this + 38);
  v3 = 0;
  pOwner = 0;
  bOwnerDefaulted = 0;
  if ( !GetSecurityDescriptorOwner(v2, &pOwner, &bOwnerDefaulted) )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 47;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids, LastError);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  v8 = (void *)*((_QWORD *)this + 38);
  pGroup = 0;
  bGroupDefaulted = 0;
  if ( !GetSecurityDescriptorGroup(v8, &pGroup, &bGroupDefaulted) )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 48;
      goto LABEL_9;
    }
LABEL_10:
    if ( (int)LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
  v9 = (void *)*((_QWORD *)this + 38);
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(v9, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 49;
      goto LABEL_9;
    }
    goto LABEL_10;
  }
  if ( !bDaclPresent )
    pDacl = 0;
  v10 = (void *)*((_QWORD *)this + 38);
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !GetSecurityDescriptorSacl(v10, &bSaclPresent, &pSacl, &bSaclDefaulted) )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = 50;
      goto LABEL_9;
    }
    goto LABEL_10;
  }
  if ( !bSaclPresent )
    pSacl = 0;
  v11 = bOwnerDefaulted == 0;
  if ( !bGroupDefaulted )
    v11 |= 2u;
  if ( !bDaclDefaulted )
    v11 |= 4u;
  if ( !bSaclDefaulted )
    v11 |= 8u;
  if ( (v11 & 0xC) != 0 )
  {
    v12 = (void *)*((_QWORD *)this + 38);
    pControl = 0;
    dwRevision = 0;
    if ( !GetSecurityDescriptorControl(v12, &pControl, &dwRevision) )
    {
      LastError = GetLastError();
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v6 = 51;
        goto LABEL_9;
      }
      goto LABEL_10;
    }
    if ( _bittest16((const signed __int16 *)&pControl, 0xDu) )
    {
      v13 = -1073741824;
      v14 = 1610612736;
    }
    else
    {
      v13 = -1879048192;
      v14 = 805306368;
    }
    if ( (pControl & 0x1000) == 0 )
      v13 = v14;
    v11 |= v13;
  }
  v15 = 0;
  while ( v3 < 0xA )
  {
    v16 = BITSSetNamedSecurityInfo(
            (LPWSTR)(*((_QWORD *)this + 2) + 12LL),
            (enum _SE_OBJECT_TYPE)pDacl,
            v11,
            pOwner,
            pGroup,
            pDacl,
            pSacl);
    v15 = v16;
    if ( v16 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids);
      goto LABEL_56;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
        (unsigned int)v16);
    Sleep(0x32u);
    ++v3;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids);
  return v15;
}

```

## disassembly

```asm
0x180029d80  push    rbp
0x180029d82  push    rbx
0x180029d83  push    rsi
0x180029d84  push    rdi
0x180029d85  push    r12
0x180029d87  push    r14
0x180029d89  push    r15
0x180029d8b  mov     rbp, rsp
0x180029d8e  sub     rsp, 70h
0x180029d92  cmp     qword ptr [rcx+130h], 0
0x180029d9a  mov     rbx, rcx
0x180029d9d  mov     r15d, 1
0x180029da3  jz      loc_18002A091
0x180029da9  mov     rcx, cs:WPP_GLOBAL_Control
0x180029db0  lea     r12, WPP_GLOBAL_Control
0x180029db7  cmp     rcx, r12
0x180029dba  jz      short loc_180029DDF
0x180029dbc  test    [rcx+1Ch], r15b
0x180029dc0  jz      short loc_180029DDF
0x180029dc2  mov     r9, [rbx+10h]
0x180029dc6  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x180029dcd  mov     rcx, [rcx+10h]
0x180029dd1  add     r9, 0Ch
0x180029dd5  mov     edx, 2Eh ; '.'
0x180029dda  call    WPP_SF_S
0x180029ddf  mov     rcx, [rbx+130h]; pSecurityDescriptor
0x180029de6  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x180029dea  xor     esi, esi
0x180029dec  lea     rdx, [rbp+pOwner]; pOwner
0x180029df0  mov     [rbp+pOwner], rsi
0x180029df4  mov     [rbp+bOwnerDefaulted], esi
0x180029df7  call    cs:__imp_GetSecurityDescriptorOwner
0x180029dfd  test    eax, eax
0x180029dff  jnz     short loc_180029E51
0x180029e01  call    cs:__imp_GetLastError
0x180029e07  mov     ebx, eax
0x180029e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e10  cmp     rcx, r12
0x180029e13  jz      short loc_180029E33
0x180029e15  test    byte ptr [rcx+1Ch], 4
0x180029e19  jz      short loc_180029E33
0x180029e1b  mov     edx, 2Fh ; '/'
0x180029e20  mov     rcx, [rcx+10h]
0x180029e24  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x180029e2b  mov     r9d, ebx
0x180029e2e  call    WPP_SF_d
0x180029e33  test    ebx, ebx
0x180029e35  jle     short loc_180029E40
0x180029e37  movzx   ebx, bx
0x180029e3a  or      ebx, 80070000h
0x180029e40  mov     eax, ebx
0x180029e42  add     rsp, 70h
0x180029e46  pop     r15
0x180029e48  pop     r14
0x180029e4a  pop     r12
0x180029e4c  pop     rdi
0x180029e4d  pop     rsi
0x180029e4e  pop     rbx
0x180029e4f  pop     rbp
0x180029e50  retn
0x180029e51  mov     rcx, [rbx+130h]; pSecurityDescriptor
0x180029e58  lea     r8, [rbp+bGroupDefaulted]; lpbGroupDefaulted
0x180029e5c  lea     rdx, [rbp+pGroup]; pGroup
0x180029e60  mov     [rbp+pGroup], rsi
0x180029e64  mov     [rbp+bGroupDefaulted], esi
0x180029e67  call    cs:__imp_GetSecurityDescriptorGroup
0x180029e6d  test    eax, eax
0x180029e6f  jnz     short loc_180029E92
0x180029e71  call    cs:__imp_GetLastError
0x180029e77  mov     ebx, eax
0x180029e79  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e80  cmp     rcx, r12
0x180029e83  jz      short loc_180029E33
0x180029e85  test    byte ptr [rcx+1Ch], 4
0x180029e89  jz      short loc_180029E33
0x180029e8b  mov     edx, 30h ; '0'
0x180029e90  jmp     short loc_180029E20
0x180029e92  mov     rcx, [rbx+130h]; pSecurityDescriptor
0x180029e99  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180029e9d  lea     r8, [rbp+pDacl]; pDacl
0x180029ea1  mov     [rbp+pDacl], rsi
0x180029ea5  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180029ea9  mov     [rbp+bDaclPresent], esi
0x180029eac  mov     [rbp+bDaclDefaulted], esi
0x180029eaf  call    cs:__imp_GetSecurityDescriptorDacl
0x180029eb5  test    eax, eax
0x180029eb7  jnz     short loc_180029EE5
0x180029eb9  call    cs:__imp_GetLastError
0x180029ebf  mov     ebx, eax
0x180029ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ec8  cmp     rcx, r12
0x180029ecb  jz      loc_180029E33
0x180029ed1  test    byte ptr [rcx+1Ch], 4
0x180029ed5  jz      loc_180029E33
0x180029edb  mov     edx, 31h ; '1'
0x180029ee0  jmp     loc_180029E20
0x180029ee5  cmp     [rbp+bDaclPresent], esi
0x180029ee8  jnz     short loc_180029EEE
0x180029eea  mov     [rbp+pDacl], rsi
0x180029eee  mov     rcx, [rbx+130h]; pSecurityDescriptor
0x180029ef5  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x180029ef9  lea     r8, [rbp+pSacl]; pSacl
0x180029efd  mov     [rbp+pSacl], rsi
0x180029f01  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x180029f05  mov     [rbp+bSaclPresent], esi
0x180029f08  mov     [rbp+bSaclDefaulted], esi
0x180029f0b  call    cs:__imp_GetSecurityDescriptorSacl
0x180029f11  test    eax, eax
0x180029f13  jnz     short loc_180029F41
0x180029f15  call    cs:__imp_GetLastError
0x180029f1b  mov     ebx, eax
0x180029f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f24  cmp     rcx, r12
0x180029f27  jz      loc_180029E33
0x180029f2d  test    byte ptr [rcx+1Ch], 4
0x180029f31  jz      loc_180029E33
0x180029f37  mov     edx, 32h ; '2'
0x180029f3c  jmp     loc_180029E20
0x180029f41  cmp     [rbp+bSaclPresent], esi
0x180029f44  jnz     short loc_180029F4A
0x180029f46  mov     [rbp+pSacl], rsi
0x180029f4a  cmp     [rbp+bOwnerDefaulted], esi
0x180029f4d  mov     edi, esi
0x180029f4f  cmovz   edi, r15d
0x180029f53  cmp     [rbp+bGroupDefaulted], esi
0x180029f56  jnz     short loc_180029F5B
0x180029f58  or      edi, 2
0x180029f5b  cmp     [rbp+bDaclDefaulted], esi
0x180029f5e  jnz     short loc_180029F63
0x180029f60  or      edi, 4
0x180029f63  cmp     [rbp+bSaclDefaulted], esi
0x180029f66  jnz     short loc_180029F6B
0x180029f68  or      edi, 8
0x180029f6b  test    dil, 0Ch
0x180029f6f  jz      short loc_180029FEF
0x180029f71  mov     rcx, [rbx+130h]; pSecurityDescriptor
0x180029f78  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180029f7c  lea     rdx, [rbp+pControl]; pControl
0x180029f80  mov     [rbp+pControl], si
0x180029f84  mov     [rbp+dwRevision], esi
0x180029f87  call    cs:__imp_GetSecurityDescriptorControl
0x180029f8d  test    eax, eax
0x180029f8f  jnz     short loc_180029FBD
0x180029f91  call    cs:__imp_GetLastError
0x180029f97  mov     ebx, eax
0x180029f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180029fa0  cmp     rcx, r12
0x180029fa3  jz      loc_180029E33
0x180029fa9  test    byte ptr [rcx+1Ch], 4
0x180029fad  jz      loc_180029E33
0x180029fb3  mov     edx, 33h ; '3'
0x180029fb8  jmp     loc_180029E20
0x180029fbd  movzx   ecx, [rbp+pControl]
0x180029fc1  mov     edx, 1000h
0x180029fc6  and     cx, dx
0x180029fc9  bt      [rbp+pControl], 0Dh
0x180029fcf  jnb     short loc_180029FDD
0x180029fd1  mov     eax, 0C0000000h
0x180029fd6  mov     edx, 60000000h
0x180029fdb  jmp     short loc_180029FE7
0x180029fdd  mov     eax, 90000000h
0x180029fe2  mov     edx, 30000000h
0x180029fe7  test    cx, cx
0x180029fea  cmovz   eax, edx
0x180029fed  or      edi, eax
0x180029fef  mov     r14d, esi
0x180029ff2  cmp     esi, 0Ah
0x180029ff5  jnb     loc_18002A0B4
0x180029ffb  mov     r8, [rbp+pGroup]
0x180029fff  mov     rax, [rbp+pSacl]
0x18002a003  mov     rdx, [rbp+pDacl]; enum _SE_OBJECT_TYPE
0x18002a007  mov     rcx, [rbx+10h]
0x18002a00b  mov     r9, [rbp+pOwner]; void *
0x18002a00f  add     rcx, 0Ch; pObjectName
0x18002a013  mov     [rsp+70h+var_40], rax; struct _ACL *
0x18002a018  mov     [rsp+70h+var_48], rdx; struct _ACL *
0x18002a01d  mov     [rsp+70h+var_50], r8; void *
0x18002a022  mov     r8d, edi; unsigned int
0x18002a025  call    ?BITSSetNamedSecurityInfo@@YAJPEAGW4_SE_OBJECT_TYPE@@KPEAX2PEAU_ACL@@3@Z; BITSSetNamedSecurityInfo(ushort *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)
0x18002a02a  mov     r14d, eax
0x18002a02d  test    eax, eax
0x18002a02f  jns     short loc_18002A06A
0x18002a031  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a038  cmp     rcx, r12
0x18002a03b  jz      short loc_18002A05B
0x18002a03d  test    byte ptr [rcx+1Ch], 4
0x18002a041  jz      short loc_18002A05B
0x18002a043  mov     rcx, [rcx+10h]
0x18002a047  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002a04e  mov     edx, 35h ; '5'
0x18002a053  mov     r9d, eax
0x18002a056  call    WPP_SF_d
0x18002a05b  mov     ecx, 32h ; '2'; dwMilliseconds
0x18002a060  call    cs:__imp_Sleep
0x18002a066  inc     esi
0x18002a068  jmp     short loc_180029FF2
0x18002a06a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a071  cmp     rcx, r12
0x18002a074  jz      short loc_18002A091
0x18002a076  test    [rcx+1Ch], r15b
0x18002a07a  jz      short loc_18002A091
0x18002a07c  mov     rcx, [rcx+10h]
0x18002a080  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002a087  mov     edx, 34h ; '4'
0x18002a08c  call    WPP_SF_
0x18002a091  mov     edx, r15d
0x18002a094  mov     [rbx+100h], r15b
0x18002a09b  mov     rcx, rbx
0x18002a09e  call    ?TriggerSerialization@CFile@@QEAAJW4SerializationBehavior@1@@Z; CFile::TriggerSerialization(CFile::SerializationBehavior)
0x18002a0a3  xor     eax, eax
0x18002a0a5  add     rsp, 70h
0x18002a0a9  pop     r15
0x18002a0ab  pop     r14
0x18002a0ad  pop     r12
0x18002a0af  pop     rdi
0x18002a0b0  pop     rsi
0x18002a0b1  pop     rbx
0x18002a0b2  pop     rbp
0x18002a0b3  retn
0x18002a0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0bb  cmp     rcx, r12
0x18002a0be  jz      short loc_18002A0DB
0x18002a0c0  test    [rcx+1Ch], r15b
0x18002a0c4  jz      short loc_18002A0DB
0x18002a0c6  mov     rcx, [rcx+10h]
0x18002a0ca  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x18002a0d1  mov     edx, 36h ; '6'
0x18002a0d6  call    WPP_SF_
0x18002a0db  mov     eax, r14d
0x18002a0de  jmp     short loc_18002A0A5
```
