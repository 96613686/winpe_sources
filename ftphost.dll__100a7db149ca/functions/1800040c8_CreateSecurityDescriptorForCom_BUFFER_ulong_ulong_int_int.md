# CreateSecurityDescriptorForCom(BUFFER *,ulong *,ulong,int,int)

- ea: `0x1800040c8`
- end: `0x1800042f2`
- name: `?CreateSecurityDescriptorForCom@@YAJPEAVBUFFER@@PEAKKHH@Z`
- size: `554`
- prototype: `__int64 __fastcall(struct BUFFER *, unsigned int *, DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180001bb0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003f28`
- `0x1800040c8`
- `0x180004420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800041a8`
- `KERNEL32!GetLastError` at `0x180004258`
- `KERNEL32!GetLastError` at `0x1800041a8`
- `KERNEL32!GetLastError` at `0x180004258`
- `KERNEL32!GlobalFree` at `0x1800042ae`
- `KERNEL32!GlobalFree` at `0x1800042ae`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000424e`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000428c`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000424e`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000428c`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18000422d`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18000422d`
- `ADVAPI32!GetLengthSid` at `0x180004182`
- `ADVAPI32!GetLengthSid` at `0x18000418e`
- `ADVAPI32!GetLengthSid` at `0x180004182`
- `ADVAPI32!GetLengthSid` at `0x18000418e`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180004218`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180004218`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180004203`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180004203`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800041eb`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800041eb`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800041d8`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800041d8`
- `ADVAPI32!InitializeAcl` at `0x1800041bf`
- `ADVAPI32!InitializeAcl` at `0x1800041bf`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000426f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000426f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800042c6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800042c6`

## pseudocode

```c
__int64 __fastcall CreateSecurityDescriptorForCom(struct BUFFER *a1, unsigned int *a2, DWORD a3)
{
  ACL *v6; // rsi
  __int64 v7; // rcx
  _BYTE *v8; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  bool v11; // cc
  DWORD LengthSid; // ebx
  DWORD v13; // ebx
  ACL *v14; // rax
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
      v14 = (ACL *)operator new(v13);
      v6 = v14;
      if ( v14
        && InitializeAcl(v14, v13, 2u)
        && AddAccessAllowedAce(v6, 2u, a3, pOwner)
        && InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
        && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v6, 0)
        && SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
        && SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0) )
      {
        dwBufferLength = *((_DWORD *)a1 + 10);
        if ( MakeSelfRelativeSD(pSecurityDescriptor, *((PSECURITY_DESCRIPTOR *)a1 + 4), &dwBufferLength) )
        {
LABEL_21:
          v10 = 0;
          *a2 = dwBufferLength;
          goto LABEL_22;
        }
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError != 122 )
          goto LABEL_9;
        if ( !BUFFER::Resize(a1, dwBufferLength) )
        {
          v10 = -2147024882;
          goto LABEL_22;
        }
        if ( MakeSelfRelativeSD(pSecurityDescriptor, *((PSECURITY_DESCRIPTOR *)a1 + 4), &dwBufferLength) )
          goto LABEL_21;
      }
      LastError = GetLastError();
      v10 = LastError;
LABEL_9:
      v11 = LastError <= 0;
    }
  }
  if ( !v11 )
    v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_22:
  if ( pOwner )
    GlobalFree(pOwner);
  if ( v6 )
    operator delete(v6);
  BUFFER::~BUFFER((BUFFER *)v21);
  return v10;
}

```

## disassembly

```asm
0x1800040c8  mov     [rsp-8+arg_18], rbx
0x1800040cd  push    rbp
0x1800040ce  push    rsi
0x1800040cf  push    r12
0x1800040d1  push    r14
0x1800040d3  push    r15
0x1800040d5  lea     rbp, [rsp-2Fh]
0x1800040da  sub     rsp, 0A0h
0x1800040e1  mov     rax, cs:__security_cookie
0x1800040e8  xor     rax, rsp
0x1800040eb  mov     [rbp+4Fh+var_30], rax
0x1800040ef  mov     r15d, r8d
0x1800040f2  mov     r12, rdx
0x1800040f5  mov     r14, rcx
0x1800040f8  xor     esi, esi
0x1800040fa  mov     [rbp+4Fh+var_60], rsi
0x1800040fe  lea     rax, [rbp+4Fh+var_60]
0x180004102  mov     [rbp+4Fh+var_40], rax
0x180004106  mov     [rbp+4Fh+var_38], 20h ; ' '
0x18000410d  mov     [rbp+4Fh+var_34], 100h
0x180004113  mov     [rbp+4Fh+dwBufferLength], esi
0x180004116  xorps   xmm0, xmm0
0x180004119  xor     eax, eax
0x18000411b  movups  [rbp+4Fh+pSecurityDescriptor], xmm0
0x18000411f  movups  [rbp+4Fh+var_78], xmm0
0x180004123  mov     [rbp+4Fh+var_68], rax
0x180004127  lea     ecx, [rsi+28h]
0x18000412a  lea     rax, [rbp+4Fh+pSecurityDescriptor]
0x18000412e  mov     byte ptr [rax], 0
0x180004131  inc     rax
0x180004134  sub     rcx, 1
0x180004138  jnz     short loc_18000412E
0x18000413a  mov     [rbp+4Fh+pOwner], rcx
0x18000413e  mov     [rbp+4Fh+pSid], rcx
0x180004142  lea     rdx, [rbp+4Fh+pOwner]; void **
0x180004146  mov     ecx, 16h; WellKnownSidType
0x18000414b  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180004150  mov     ebx, eax
0x180004152  test    eax, eax
0x180004154  jz      short loc_18000416A
0x180004156  jle     loc_1800042A3
0x18000415c  movzx   ebx, ax
0x18000415f  or      ebx, 80070000h
0x180004165  jmp     loc_1800042A3
0x18000416a  lea     rdx, [rbp+4Fh+pSid]; void **
0x18000416e  mov     ecx, 1Ah; WellKnownSidType
0x180004173  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180004178  mov     ebx, eax
0x18000417a  test    eax, eax
0x18000417c  jnz     short loc_180004156
0x18000417e  mov     rcx, [rbp+4Fh+pSid]; pSid
0x180004182  call    cs:__imp_GetLengthSid
0x180004188  mov     ebx, eax
0x18000418a  mov     rcx, [rbp+4Fh+pOwner]; pSid
0x18000418e  call    cs:__imp_GetLengthSid
0x180004194  add     eax, 20h ; ' '
0x180004197  add     ebx, eax
0x180004199  mov     ecx, ebx; Size
0x18000419b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800041a0  mov     rsi, rax
0x1800041a3  test    rax, rax
0x1800041a6  jnz     short loc_1800041B4
0x1800041a8  call    cs:__imp_GetLastError
0x1800041ae  mov     ebx, eax
0x1800041b0  test    eax, eax
0x1800041b2  jmp     short loc_180004156
0x1800041b4  mov     r8d, 2; dwAclRevision
0x1800041ba  mov     edx, ebx; nAclLength
0x1800041bc  mov     rcx, rsi; pAcl
0x1800041bf  call    cs:__imp_InitializeAcl
0x1800041c5  test    eax, eax
0x1800041c7  jz      short loc_1800041A8
0x1800041c9  mov     r9, [rbp+4Fh+pOwner]; pSid
0x1800041cd  mov     r8d, r15d; AccessMask
0x1800041d0  mov     edx, 2; dwAceRevision
0x1800041d5  mov     rcx, rsi; pAcl
0x1800041d8  call    cs:__imp_AddAccessAllowedAce
0x1800041de  test    eax, eax
0x1800041e0  jz      short loc_1800041A8
0x1800041e2  mov     edx, 1; dwRevision
0x1800041e7  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x1800041eb  call    cs:__imp_InitializeSecurityDescriptor
0x1800041f1  test    eax, eax
0x1800041f3  jz      short loc_1800041A8
0x1800041f5  xor     r9d, r9d; bDaclDefaulted
0x1800041f8  mov     r8, rsi; pDacl
0x1800041fb  lea     edx, [r9+1]; bDaclPresent
0x1800041ff  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x180004203  call    cs:__imp_SetSecurityDescriptorDacl
0x180004209  test    eax, eax
0x18000420b  jz      short loc_1800041A8
0x18000420d  xor     r8d, r8d; bOwnerDefaulted
0x180004210  mov     rdx, [rbp+4Fh+pOwner]; pOwner
0x180004214  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x180004218  call    cs:__imp_SetSecurityDescriptorOwner
0x18000421e  test    eax, eax
0x180004220  jz      short loc_1800041A8
0x180004222  xor     r8d, r8d; bGroupDefaulted
0x180004225  mov     rdx, [rbp+4Fh+pOwner]; pGroup
0x180004229  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pSecurityDescriptor
0x18000422d  call    cs:__imp_SetSecurityDescriptorGroup
0x180004233  test    eax, eax
0x180004235  jz      loc_1800041A8
0x18000423b  mov     eax, [r14+28h]
0x18000423f  mov     [rbp+4Fh+dwBufferLength], eax
0x180004242  lea     r8, [rbp+4Fh+dwBufferLength]; lpdwBufferLength
0x180004246  mov     rdx, [r14+20h]; pSelfRelativeSecurityDescriptor
0x18000424a  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18000424e  call    cs:__imp_MakeSelfRelativeSD
0x180004254  test    eax, eax
0x180004256  jnz     short loc_18000429A
0x180004258  call    cs:__imp_GetLastError
0x18000425e  mov     ebx, eax
0x180004260  cmp     eax, 7Ah ; 'z'
0x180004263  jnz     loc_1800041B0
0x180004269  mov     edx, [rbp+4Fh+dwBufferLength]
0x18000426c  mov     rcx, r14
0x18000426f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180004275  test    al, al
0x180004277  jnz     short loc_180004280
0x180004279  mov     ebx, 8007000Eh
0x18000427e  jmp     short loc_1800042A3
0x180004280  lea     r8, [rbp+4Fh+dwBufferLength]; lpdwBufferLength
0x180004284  mov     rdx, [r14+20h]; pSelfRelativeSecurityDescriptor
0x180004288  lea     rcx, [rbp+4Fh+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18000428c  call    cs:__imp_MakeSelfRelativeSD
0x180004292  test    eax, eax
0x180004294  jz      loc_1800041A8
0x18000429a  xor     ebx, ebx
0x18000429c  mov     eax, [rbp+4Fh+dwBufferLength]
0x18000429f  mov     [r12], eax
0x1800042a3  cmp     [rbp+4Fh+pOwner], 0
0x1800042a8  jz      short loc_1800042B4
0x1800042aa  mov     rcx, [rbp+4Fh+pOwner]; hMem
0x1800042ae  call    cs:__imp_GlobalFree
0x1800042b4  test    rsi, rsi
0x1800042b7  jz      short loc_1800042C2
0x1800042b9  mov     rcx, rsi; Block
0x1800042bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042c1  nop
0x1800042c2  lea     rcx, [rbp+4Fh+var_60]
0x1800042c6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800042cc  mov     eax, ebx
0x1800042ce  mov     rcx, [rbp+4Fh+var_30]
0x1800042d2  xor     rcx, rsp; StackCookie
0x1800042d5  call    __security_check_cookie
0x1800042da  mov     rbx, [rsp+0C0h+arg_18]
0x1800042e2  add     rsp, 0A0h
0x1800042e9  pop     r15
0x1800042eb  pop     r14
0x1800042ed  pop     r12
0x1800042ef  pop     rsi
0x1800042f0  pop     rbp
0x1800042f1  retn
```
