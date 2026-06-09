# SetStorageSecurityDescriptor(void)

- ea: `0x180025ffc`
- end: `0x180026203`
- name: `?SetStorageSecurityDescriptor@@YAJXZ`
- size: `519`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001fa58`

## callees

- `0x18001ebb0`
- `0x180025ffc`

## import_xrefs

- `ADVAPI32!LsaClose` at `0x1800261f0`
- `ADVAPI32!LsaClose` at `0x1800261f0`
- `ADVAPI32!LsaFreeMemory` at `0x1800261e1`
- `ADVAPI32!LsaFreeMemory` at `0x1800261e1`
- `ADVAPI32!CopySid` at `0x1800261c0`
- `ADVAPI32!CopySid` at `0x1800261c0`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1800261a2`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x1800261a2`
- `ADVAPI32!LsaOpenPolicy` at `0x180026180`
- `ADVAPI32!LsaOpenPolicy` at `0x180026180`
- `ADVAPI32!CreateWellKnownSid` at `0x18002607a`
- `ADVAPI32!CreateWellKnownSid` at `0x18002609b`
- `ADVAPI32!CreateWellKnownSid` at `0x18002607a`
- `ADVAPI32!CreateWellKnownSid` at `0x18002609b`
- `ADVAPI32!InitializeAcl` at `0x1800260b7`
- `ADVAPI32!InitializeAcl` at `0x1800260b7`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002613f`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002613f`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180026120`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180026120`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180026162`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180026162`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002603b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002603b`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800260da`
- `ADVAPI32!AddAccessAllowedAce` at `0x180026101`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800260da`
- `ADVAPI32!AddAccessAllowedAce` at `0x180026101`
- `KERNEL32!GetLastError` at `0x180026045`
- `KERNEL32!GetLastError` at `0x180026045`

## pseudocode

```c
__int64 SetStorageSecurityDescriptor(void)
{
  unsigned int v0; // ebx
  signed int LastError; // eax
  NTSTATUS v2; // eax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  DWORD cbSid; // [rsp+60h] [rbp+10h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp+18h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp+20h] BYREF

  v0 = 0;
  cbSid = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  Buffer = 0;
  if ( g_fsdStorageInitialized )
    return v0;
  if ( !InitializeSecurityDescriptor(qword_180048AE8, 1u) )
    goto LABEL_3;
  cbSid = 68;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, qword_180048C60, &cbSid) )
    goto LABEL_3;
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, qword_180048C10, &cbSid)
    || !InitializeAcl(&pDacl, 0xA8u, 2u)
    || !AddAccessAllowedAce(&pDacl, 2u, 0x1F01FFu, qword_180048C60)
    || !AddAccessAllowedAce(&pDacl, 2u, 0x1F01FFu, qword_180048C10)
    || !SetSecurityDescriptorOwner(qword_180048AE8, qword_180048C10, 0)
    || !SetSecurityDescriptorGroup(qword_180048AE8, qword_180048C10, 0)
    || !SetSecurityDescriptorDacl(qword_180048AE8, 1, &pDacl, 0) )
  {
    goto LABEL_3;
  }
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v2 >= 0 )
  {
    v2 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
    if ( v2 >= 0 )
    {
      if ( CopySid(0x44u, qword_180048BC0, *((PSID *)Buffer + 2)) )
      {
        g_fsdStorageInitialized = 1;
        goto LABEL_18;
      }
LABEL_3:
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_18;
    }
  }
  v0 = HRESULT_FROM_NTSTATUS(v2);
LABEL_18:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v0;
}

```

## disassembly

```asm
0x180025ffc  mov     [rsp-8+arg_18], rbx
0x180026001  push    rbp
0x180026002  mov     rbp, rsp
0x180026005  sub     rsp, 50h
0x180026009  xor     ebx, ebx
0x18002600b  xorps   xmm0, xmm0
0x18002600e  cmp     cs:?g_fsdStorageInitialized@@3HA, ebx; int g_fsdStorageInitialized
0x180026014  mov     [rbp+cbSid], ebx
0x180026017  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002601b  mov     [rbp+PolicyHandle], rbx
0x18002601f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180026023  mov     [rbp+Buffer], rbx
0x180026027  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002602b  jnz     loc_1800261F6
0x180026031  lea     edx, [rbx+1]; dwRevision
0x180026034  lea     rcx, qword_180048AE8; pSecurityDescriptor
0x18002603b  call    cs:__imp_InitializeSecurityDescriptor
0x180026041  test    eax, eax
0x180026043  jnz     short loc_180026063
0x180026045  call    cs:__imp_GetLastError
0x18002604b  mov     ebx, eax
0x18002604d  test    eax, eax
0x18002604f  jle     loc_1800261D8
0x180026055  movzx   ebx, ax
0x180026058  or      ebx, 80070000h
0x18002605e  jmp     loc_1800261D8
0x180026063  xor     edx, edx; DomainSid
0x180026065  mov     [rbp+cbSid], 44h ; 'D'
0x18002606c  lea     r9, [rbp+cbSid]; cbSid
0x180026070  lea     r8, qword_180048C60; pSid
0x180026077  lea     ecx, [rdx+16h]; WellKnownSidType
0x18002607a  call    cs:__imp_CreateWellKnownSid
0x180026080  test    eax, eax
0x180026082  jz      short loc_180026045
0x180026084  xor     edx, edx; DomainSid
0x180026086  mov     [rbp+cbSid], 44h ; 'D'
0x18002608d  lea     r9, [rbp+cbSid]; cbSid
0x180026091  lea     r8, qword_180048C10; pSid
0x180026098  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002609b  call    cs:__imp_CreateWellKnownSid
0x1800260a1  test    eax, eax
0x1800260a3  jz      short loc_180026045
0x1800260a5  mov     edx, 0A8h; nAclLength
0x1800260aa  lea     rcx, pDacl; pAcl
0x1800260b1  mov     r8d, 2; dwAclRevision
0x1800260b7  call    cs:__imp_InitializeAcl
0x1800260bd  test    eax, eax
0x1800260bf  jz      short loc_180026045
0x1800260c1  lea     r9, qword_180048C60; pSid
0x1800260c8  mov     edx, 2; dwAceRevision
0x1800260cd  mov     r8d, 1F01FFh; AccessMask
0x1800260d3  lea     rcx, pDacl; pAcl
0x1800260da  call    cs:__imp_AddAccessAllowedAce
0x1800260e0  test    eax, eax
0x1800260e2  jz      loc_180026045
0x1800260e8  lea     r9, qword_180048C10; pSid
0x1800260ef  mov     edx, 2; dwAceRevision
0x1800260f4  mov     r8d, 1F01FFh; AccessMask
0x1800260fa  lea     rcx, pDacl; pAcl
0x180026101  call    cs:__imp_AddAccessAllowedAce
0x180026107  test    eax, eax
0x180026109  jz      loc_180026045
0x18002610f  xor     r8d, r8d; bOwnerDefaulted
0x180026112  lea     rdx, qword_180048C10; pOwner
0x180026119  lea     rcx, qword_180048AE8; pSecurityDescriptor
0x180026120  call    cs:__imp_SetSecurityDescriptorOwner
0x180026126  test    eax, eax
0x180026128  jz      loc_180026045
0x18002612e  xor     r8d, r8d; bGroupDefaulted
0x180026131  lea     rdx, qword_180048C10; pGroup
0x180026138  lea     rcx, qword_180048AE8; pSecurityDescriptor
0x18002613f  call    cs:__imp_SetSecurityDescriptorGroup
0x180026145  test    eax, eax
0x180026147  jz      loc_180026045
0x18002614d  xor     r9d, r9d; bDaclDefaulted
0x180026150  lea     r8, pDacl; pDacl
0x180026157  lea     rcx, qword_180048AE8; pSecurityDescriptor
0x18002615e  lea     edx, [r9+1]; bDaclPresent
0x180026162  call    cs:__imp_SetSecurityDescriptorDacl
0x180026168  test    eax, eax
0x18002616a  jz      loc_180026045
0x180026170  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180026174  mov     r8d, 1; DesiredAccess
0x18002617a  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002617e  xor     ecx, ecx; SystemName
0x180026180  call    cs:__imp_LsaOpenPolicy
0x180026186  test    eax, eax
0x180026188  jns     short loc_180026195
0x18002618a  mov     ecx, eax; int
0x18002618c  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x180026191  mov     ebx, eax
0x180026193  jmp     short loc_1800261D8
0x180026195  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180026199  lea     r8, [rbp+Buffer]; Buffer
0x18002619d  mov     edx, 5; InformationClass
0x1800261a2  call    cs:__imp_LsaQueryInformationPolicy
0x1800261a8  test    eax, eax
0x1800261aa  js      short loc_18002618A
0x1800261ac  mov     r8, [rbp+Buffer]
0x1800261b0  lea     rdx, qword_180048BC0; pDestinationSid
0x1800261b7  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800261bc  mov     r8, [r8+10h]; pSourceSid
0x1800261c0  call    cs:__imp_CopySid
0x1800261c6  test    eax, eax
0x1800261c8  jz      loc_180026045
0x1800261ce  mov     cs:?g_fsdStorageInitialized@@3HA, 1; int g_fsdStorageInitialized
0x1800261d8  mov     rcx, [rbp+Buffer]; Buffer
0x1800261dc  test    rcx, rcx
0x1800261df  jz      short loc_1800261E7
0x1800261e1  call    cs:__imp_LsaFreeMemory
0x1800261e7  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x1800261eb  test    rcx, rcx
0x1800261ee  jz      short loc_1800261F6
0x1800261f0  call    cs:__imp_LsaClose
0x1800261f6  mov     eax, ebx
0x1800261f8  mov     rbx, [rsp+50h+arg_18]
0x1800261fd  add     rsp, 50h
0x180026201  pop     rbp
0x180026202  retn
```
