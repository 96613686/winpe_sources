# SampMakeNewSelfRelativeSecurityDescriptor

- ea: `0x1803e67e4`
- end: `0x1803e691d`
- name: `SampMakeNewSelfRelativeSecurityDescriptor`
- size: `313`
- prototype: `__int64 __fastcall(PSID pOwner, PSID pGroup, PACL pDacl, PACL pSacl, LPDWORD lpdwBufferLength, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1803db8bc`
- `0x1803dc0a8`
- `0x1803e3d84`
- `0x1803e63d0`
- `0x1803e6580`

## callees

- `0x1803e67e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1803e688b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1803e688b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1803e68a9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1803e68a9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1803e682f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1803e682f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1803e6853`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1803e6853`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1803e686d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1803e686d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1803e68b8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1803e68b8`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1803e68ea`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1803e68ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803e68c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1803e68c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803e6901`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803e6901`

## pseudocode

```c
__int64 __fastcall SampMakeNewSelfRelativeSecurityDescriptor(
        PSID pOwner,
        PSID pGroup,
        PACL pDacl,
        PACL pSacl,
        LPDWORD lpdwBufferLength,
        HLOCAL *a6)
{
  unsigned int v10; // ebx
  DWORD SecurityDescriptorLength; // eax
  HLOCAL v12; // rax
  _OWORD pSecurityDescriptor[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v15; // [rsp+40h] [rbp-48h]

  v15 = 0;
  *lpdwBufferLength = 0;
  *a6 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    && (!pOwner || SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0))
    && (!pGroup || SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, 0))
    && (!pDacl || SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0))
    && (!pSacl || SetSecurityDescriptorSacl(pSecurityDescriptor, 1, pSacl, 0)) )
  {
    SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
    *lpdwBufferLength = SecurityDescriptorLength;
    v12 = LocalAlloc(0x40u, SecurityDescriptorLength);
    *a6 = v12;
    if ( v12 )
    {
      v10 = 0;
      if ( !MakeSelfRelativeSD(pSecurityDescriptor, v12, lpdwBufferLength) )
      {
        v10 = -1073741823;
        if ( *a6 )
        {
          LocalFree(*a6);
          *a6 = 0;
        }
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741823;
  }
  return v10;
}

```

## disassembly

```asm
0x1803e67e4  push    rbx
0x1803e67e6  push    rbp
0x1803e67e7  push    rsi
0x1803e67e8  push    rdi
0x1803e67e9  push    r14
0x1803e67eb  push    r15
0x1803e67ed  sub     rsp, 58h
0x1803e67f1  mov     r15, [rsp+88h+lpdwBufferLength]
0x1803e67f9  xor     eax, eax
0x1803e67fb  mov     rdi, [rsp+88h+arg_28]
0x1803e6803  xorps   xmm0, xmm0
0x1803e6806  mov     rsi, rdx
0x1803e6809  mov     [rsp+88h+var_48], rax
0x1803e680e  mov     rbx, rcx
0x1803e6811  mov     r14, r9
0x1803e6814  mov     [r15], eax
0x1803e6817  lea     edx, [rax+1]; dwRevision
0x1803e681a  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e681f  mov     [rdi], rax
0x1803e6822  mov     rbp, r8
0x1803e6825  movups  [rsp+88h+pSecurityDescriptor], xmm0
0x1803e682a  movups  [rsp+88h+var_58], xmm0
0x1803e682f  call    cs:__imp_InitializeSecurityDescriptor
0x1803e6835  test    eax, eax
0x1803e6837  jnz     short loc_1803E6843
0x1803e6839  mov     ebx, 0C0000001h
0x1803e683e  jmp     loc_1803E690E
0x1803e6843  test    rbx, rbx
0x1803e6846  jz      short loc_1803E685D
0x1803e6848  xor     r8d, r8d; bOwnerDefaulted
0x1803e684b  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e6850  mov     rdx, rbx; pOwner
0x1803e6853  call    cs:__imp_SetSecurityDescriptorOwner
0x1803e6859  test    eax, eax
0x1803e685b  jz      short loc_1803E6839
0x1803e685d  test    rsi, rsi
0x1803e6860  jz      short loc_1803E6877
0x1803e6862  xor     r8d, r8d; bGroupDefaulted
0x1803e6865  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e686a  mov     rdx, rsi; pGroup
0x1803e686d  call    cs:__imp_SetSecurityDescriptorGroup
0x1803e6873  test    eax, eax
0x1803e6875  jz      short loc_1803E6839
0x1803e6877  test    rbp, rbp
0x1803e687a  jz      short loc_1803E6895
0x1803e687c  xor     r9d, r9d; bDaclDefaulted
0x1803e687f  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e6884  mov     r8, rbp; pDacl
0x1803e6887  lea     edx, [r9+1]; bDaclPresent
0x1803e688b  call    cs:__imp_SetSecurityDescriptorDacl
0x1803e6891  test    eax, eax
0x1803e6893  jz      short loc_1803E6839
0x1803e6895  test    r14, r14
0x1803e6898  jz      short loc_1803E68B3
0x1803e689a  xor     r9d, r9d; bSaclDefaulted
0x1803e689d  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e68a2  mov     r8, r14; pSacl
0x1803e68a5  lea     edx, [r9+1]; bSaclPresent
0x1803e68a9  call    cs:__imp_SetSecurityDescriptorSacl
0x1803e68af  test    eax, eax
0x1803e68b1  jz      short loc_1803E6839
0x1803e68b3  lea     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1803e68b8  call    cs:__imp_GetSecurityDescriptorLength
0x1803e68be  mov     edx, eax; uBytes
0x1803e68c0  mov     ecx, 40h ; '@'; uFlags
0x1803e68c5  mov     [r15], edx
0x1803e68c8  call    cs:__imp_LocalAlloc
0x1803e68ce  mov     [rdi], rax
0x1803e68d1  test    rax, rax
0x1803e68d4  jnz     short loc_1803E68DD
0x1803e68d6  mov     ebx, 0C000009Ah
0x1803e68db  jmp     short loc_1803E690E
0x1803e68dd  mov     r8, r15; lpdwBufferLength
0x1803e68e0  lea     rcx, [rsp+88h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1803e68e5  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1803e68e8  xor     ebx, ebx
0x1803e68ea  call    cs:__imp_MakeSelfRelativeSD
0x1803e68f0  test    eax, eax
0x1803e68f2  jnz     short loc_1803E690E
0x1803e68f4  mov     rcx, [rdi]; hMem
0x1803e68f7  mov     ebx, 0C0000001h
0x1803e68fc  test    rcx, rcx
0x1803e68ff  jz      short loc_1803E690E
0x1803e6901  call    cs:__imp_LocalFree
0x1803e6907  mov     qword ptr [rdi], 0
0x1803e690e  mov     eax, ebx
0x1803e6910  add     rsp, 58h
0x1803e6914  pop     r15
0x1803e6916  pop     r14
0x1803e6918  pop     rdi
0x1803e6919  pop     rsi
0x1803e691a  pop     rbp
0x1803e691b  pop     rbx
0x1803e691c  retn
```
