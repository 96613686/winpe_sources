# CreateSecurityDescriptorForCom(BUFFER *,ulong *,ulong,int,int)

- ea: `0x18002bc00`
- end: `0x18002be45`
- name: `?CreateSecurityDescriptorForCom@@YAJPEAVBUFFER@@PEAKKHH@Z`
- size: `581`
- prototype: `__int64 __fastcall(struct BUFFER *, unsigned int *, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800173a0`

## callees

- `0x180001210`
- `0x180001250`
- `0x18002bc00`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002bce1`
- `KERNEL32!GetLastError` at `0x18002bdad`
- `KERNEL32!GetLastError` at `0x18002bce1`
- `KERNEL32!GetLastError` at `0x18002bdad`
- `ADVAPI32!GetLengthSid` at `0x18002bcbb`
- `ADVAPI32!GetLengthSid` at `0x18002bcc7`
- `ADVAPI32!GetLengthSid` at `0x18002bcbb`
- `ADVAPI32!GetLengthSid` at `0x18002bcc7`
- `ADVAPI32!InitializeAcl` at `0x18002bcf8`
- `ADVAPI32!InitializeAcl` at `0x18002bcf8`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bd11`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bd2a`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bd11`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bd2a`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18002bda3`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18002bde1`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18002bda3`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18002bde1`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18002bd6a`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18002bd6a`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002bd83`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002bd83`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002bd55`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002bd55`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002bd3d`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002bd3d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002be1a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002be1a`
- `iisutil!FreeWellKnownSid` at `0x18002be02`
- `iisutil!FreeWellKnownSid` at `0x18002be02`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18002bc82`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18002bcab`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18002bc82`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18002bcab`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002bdc4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002bdc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateSecurityDescriptorForCom(struct BUFFER *a1, unsigned int *a2, DWORD a3)
{
  struct _ACL *v6; // rdi
  __int64 v7; // rcx
  _BYTE *v8; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  bool v11; // cc
  DWORD LengthSid; // ebx
  DWORD v13; // ebx
  struct _ACL *v14; // rax
  DWORD dwBufferLength; // [rsp+20h] [rbp-51h] BYREF
  PSID pOwner; // [rsp+28h] [rbp-49h] BYREF
  PSID pSid; // [rsp+30h] [rbp-41h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v20; // [rsp+58h] [rbp-19h]
  _QWORD v21[5]; // [rsp+60h] [rbp-11h] BYREF
  int v22; // [rsp+88h] [rbp+17h]
  __int16 v23; // [rsp+8Ch] [rbp+1Bh]

  v6 = 0;
  v21[0] = 0;
  v21[4] = v21;
  v22 = 32;
  v23 = 256;
  dwBufferLength = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v20 = 0;
  v7 = 40;
  v8 = pSecurityDescriptor;
  do
  {
    *v8++ = 0;
    --v7;
  }
  while ( v7 );
  pOwner = 0;
  pSid = 0;
  LastError = AllocateAndCreateWellKnownSid(WinLocalSystemSid, &pOwner);
  v10 = LastError;
  v11 = LastError <= 0;
  if ( !LastError )
  {
    LastError = AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &pSid);
    v10 = LastError;
    v11 = LastError <= 0;
    if ( !LastError )
    {
      LengthSid = GetLengthSid(pSid);
      v13 = GetLengthSid(pOwner) + 32 + LengthSid;
      v14 = (struct _ACL *)operator new(v13);
      v6 = v14;
      if ( v14
        && InitializeAcl(v14, v13, 2u)
        && AddAccessAllowedAce(v6, 2u, a3, pOwner)
        && AddAccessAllowedAce(v6, 2u, a3, pSid)
        && InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
        && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v6, 0)
        && SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
        && SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0) )
      {
        dwBufferLength = *((_DWORD *)a1 + 10);
        if ( MakeSelfRelativeSD(pSecurityDescriptor, *((PSECURITY_DESCRIPTOR *)a1 + 4), &dwBufferLength) )
        {
LABEL_22:
          v10 = 0;
          *a2 = dwBufferLength;
          goto LABEL_23;
        }
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError != 122 )
          goto LABEL_9;
        if ( !BUFFER::Resize(a1, dwBufferLength) )
        {
          v10 = -2147024882;
          goto LABEL_23;
        }
        if ( MakeSelfRelativeSD(pSecurityDescriptor, *((PSECURITY_DESCRIPTOR *)a1 + 4), &dwBufferLength) )
          goto LABEL_22;
      }
      LastError = GetLastError();
      v10 = LastError;
LABEL_9:
      v11 = LastError <= 0;
    }
  }
  if ( !v11 )
    v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_23:
  if ( pOwner )
    FreeWellKnownSid(&pOwner);
  if ( v6 )
    operator delete(v6);
  BUFFER::~BUFFER((BUFFER *)v21);
  return v10;
}

```

## disassembly

```asm
0x18002bc00  mov     [rsp-8+arg_18], rbx
0x18002bc05  push    rbp
0x18002bc06  push    rsi
0x18002bc07  push    rdi
0x18002bc08  push    r14
0x18002bc0a  push    r15
0x18002bc0c  lea     rbp, [rsp-2Fh]
0x18002bc11  sub     rsp, 0A0h
0x18002bc18  mov     rax, cs:__security_cookie
0x18002bc1f  xor     rax, rsp
0x18002bc22  mov     [rbp+4Fh+var_30], rax
0x18002bc26  mov     r14d, r8d
0x18002bc29  mov     r15, rdx
0x18002bc2c  mov     rsi, rcx
0x18002bc2f  xor     edi, edi
0x18002bc31  mov     [rbp+4Fh+var_60], rdi
0x18002bc35  lea     rax, [rbp+4Fh+var_60]
0x18002bc39  mov     [rbp+4Fh+var_40], rax
0x18002bc3d  mov     [rbp+4Fh+var_38], 20h ; ' '
0x18002bc44  mov     [rbp+4Fh+var_34], 100h
0x18002bc4a  mov     [rbp+4Fh+dwBufferLength], edi
0x18002bc4d  xorps   xmm0, xmm0
0x18002bc50  xor     eax, eax
0x18002bc52  movups  [rbp+4Fh+pSecurityDescriptor], xmm0
0x18002bc56  movups  [rbp+4Fh+var_78], xmm0
0x18002bc5a  mov     [rbp+4Fh+var_68], rax
0x18002bc5e  lea     ecx, [rdi+28h]
0x18002bc61  lea     rax, [rbp+4Fh+pSecurityDescriptor]
0x18002bc65  mov     byte ptr [rax], 0
0x18002bc68  inc     rax
0x18002bc6b  sub     rcx, 1
0x18002bc6f  jnz     short loc_18002BC65
0x18002bc71  mov     [rbp+4Fh+pOwner], rcx
0x18002bc75  mov     [rbp+4Fh+pSid], rcx
0x18002bc79  lea     rdx, [rbp+4Fh+pOwner]
0x18002bc7d  mov     ecx, 16h
0x18002bc82  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002bc88  mov     ebx, eax
0x18002bc8a  test    eax, eax
0x18002bc8c  jz      short loc_18002BCA2
0x18002bc8e  jle     loc_18002BDF7
0x18002bc94  movzx   ebx, ax
0x18002bc97  or      ebx, 80070000h
0x18002bc9d  jmp     loc_18002BDF7
0x18002bca2  lea     rdx, [rbp+4Fh+pSid]
0x18002bca6  mov     ecx, 1Ah
0x18002bcab  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002bcb1  mov     ebx, eax
0x18002bcb3  test    eax, eax
0x18002bcb5  jnz     short loc_18002BC8E
0x18002bcb7  mov     rcx, [rbp+4Fh+pSid]; pSid
0x18002bcbb  call    cs:__imp_GetLengthSid
0x18002bcc1  mov     ebx, eax
0x18002bcc3  mov     rcx, [rbp+4Fh+pOwner]; pSid
0x18002bcc7  call    cs:__imp_GetLengthSid
0x18002bccd  add     eax, 20h ; ' '
0x18002bcd0  add     ebx, eax
0x18002bcd2  mov     ecx, ebx; Size
0x18002bcd4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bcd9  mov     rdi, rax
0x18002bcdc  test    rax, rax
0x18002bcdf  jnz     short loc_18002BCED
0x18002bce1  call    cs:__imp_GetLastError
0x18002bce7  mov     ebx, eax
0x18002bce9  test    eax, eax
0x18002bceb  jmp     short loc_18002BC8E
0x18002bced  mov     r8d, 2; dwAclRevision
0x18002bcf3  mov     edx, ebx; nAclLength
0x18002bcf5  mov     rcx, rdi; pAcl
0x18002bcf8  call    cs:__imp_InitializeAcl
0x18002bcfe  test    eax, eax
0x18002bd00  jz      short loc_18002BCE1
0x18002bd02  mov     r9, [rbp+4Fh+pOwner]; pSid
0x18002bd06  mov     r8d, r14d; AccessMask
0x18002bd09  mov     edx, 2; dwAceRevision
0x18002bd0e  mov     rcx, rdi; pAcl
0x18002bd11  call    cs:__imp_AddAccessAllowedAce
0x18002bd17  test    eax, eax
0x18002bd19  jz      short loc_18002BCE1
0x18002bd1b  mov     r9, [rbp+4Fh+pSid]; pSid
0x18002bd1f  mov     r8d, r14d; AccessMask
0x18002bd22  mov     edx, 2; dwAceRevision
0x18002bd27  mov     rcx, rdi; pAcl
0x18002bd2a  call    cs:__imp_AddAccessAllowedAce
0x18002bd30  test    eax, eax
0x18002bd32  jz      short loc_18002BCE1
0x18002bd34  mov     edx, 1; dwRevision
0x18002bd39  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x18002bd3d  call    cs:__imp_InitializeSecurityDescriptor
0x18002bd43  test    eax, eax
0x18002bd45  jz      short loc_18002BCE1
0x18002bd47  xor     r9d, r9d; bDaclDefaulted
0x18002bd4a  mov     r8, rdi; pDacl
0x18002bd4d  lea     edx, [r9+1]; bDaclPresent
0x18002bd51  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x18002bd55  call    cs:__imp_SetSecurityDescriptorDacl
0x18002bd5b  test    eax, eax
0x18002bd5d  jz      short loc_18002BCE1
0x18002bd5f  xor     r8d, r8d; bOwnerDefaulted
0x18002bd62  mov     rdx, [rbp+4Fh+pOwner]; pOwner
0x18002bd66  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x18002bd6a  call    cs:__imp_SetSecurityDescriptorOwner
0x18002bd70  test    eax, eax
0x18002bd72  jz      loc_18002BCE1
0x18002bd78  xor     r8d, r8d; bGroupDefaulted
0x18002bd7b  mov     rdx, [rbp+4Fh+pOwner]; pGroup
0x18002bd7f  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x18002bd83  call    cs:__imp_SetSecurityDescriptorGroup
0x18002bd89  test    eax, eax
0x18002bd8b  jz      loc_18002BCE1
0x18002bd91  mov     eax, [rsi+28h]
0x18002bd94  mov     [rbp+4Fh+dwBufferLength], eax
0x18002bd97  lea     r8, [rbp+4Fh+dwBufferLength]; lpdwBufferLength
0x18002bd9b  mov     rdx, [rsi+20h]; pSelfRelativeSecurityDescriptor
0x18002bd9f  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18002bda3  call    cs:__imp_MakeSelfRelativeSD
0x18002bda9  test    eax, eax
0x18002bdab  jnz     short loc_18002BDEF
0x18002bdad  call    cs:__imp_GetLastError
0x18002bdb3  mov     ebx, eax
0x18002bdb5  cmp     eax, 7Ah ; 'z'
0x18002bdb8  jnz     loc_18002BCE9
0x18002bdbe  mov     edx, [rbp+4Fh+dwBufferLength]
0x18002bdc1  mov     rcx, rsi
0x18002bdc4  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18002bdca  test    al, al
0x18002bdcc  jnz     short loc_18002BDD5
0x18002bdce  mov     ebx, 8007000Eh
0x18002bdd3  jmp     short loc_18002BDF7
0x18002bdd5  lea     r8, [rbp+4Fh+dwBufferLength]; lpdwBufferLength
0x18002bdd9  mov     rdx, [rsi+20h]; pSelfRelativeSecurityDescriptor
0x18002bddd  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18002bde1  call    cs:__imp_MakeSelfRelativeSD
0x18002bde7  test    eax, eax
0x18002bde9  jz      loc_18002BCE1
0x18002bdef  xor     ebx, ebx
0x18002bdf1  mov     eax, [rbp+4Fh+dwBufferLength]
0x18002bdf4  mov     [r15], eax
0x18002bdf7  cmp     [rbp+4Fh+pOwner], 0
0x18002bdfc  jz      short loc_18002BE08
0x18002bdfe  lea     rcx, [rbp+4Fh+pOwner]
0x18002be02  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x18002be08  test    rdi, rdi
0x18002be0b  jz      short loc_18002BE16
0x18002be0d  mov     rcx, rdi; Block
0x18002be10  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002be15  nop
0x18002be16  lea     rcx, [rbp+4Fh+var_60]
0x18002be1a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002be20  mov     eax, ebx
0x18002be22  mov     rcx, [rbp+4Fh+var_30]
0x18002be26  xor     rcx, rsp; StackCookie
0x18002be29  call    __security_check_cookie
0x18002be2e  mov     rbx, [rsp+0C0h+arg_18]
0x18002be36  add     rsp, 0A0h
0x18002be3d  pop     r15
0x18002be3f  pop     r14
0x18002be41  pop     rdi
0x18002be42  pop     rsi
0x18002be43  pop     rbp
0x18002be44  retn
```
