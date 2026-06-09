# BuildPrintObjectProtection

- ea: `0x1800239a0`
- end: `0x180023ba2`
- name: `BuildPrintObjectProtection`
- size: `514`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PSID pOwner, PSID pGroup, DWORD dwBufferLength, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800973b8`
- `0x180097b48`
- `0x180097f10`
- `0x180098628`
- `0x18009daec`

## callees

- `0x1800239a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x180023b7d`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x180023b7d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800239f4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800239f4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180023af9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180023af9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023b8a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023b8a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180023b38`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180023b38`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180023abe`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180023abe`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180023b60`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180023b60`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180023a41`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180023a41`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180023aa5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180023aa5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023a33`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023a33`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023a6d`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180023a6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023a18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023a18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023a51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023a51`
- `SPOOLSS!DllFreeSplMem` at `0x180023a80`
- `SPOOLSS!DllFreeSplMem` at `0x180023a80`
- `SPOOLSS!DllAllocSplMem` at `0x180023adc`
- `SPOOLSS!DllAllocSplMem` at `0x180023adc`

## pseudocode

```c
__int64 __fastcall BuildPrintObjectProtection(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PSID pOwner,
        PSID pGroup,
        DWORD dwBufferLength,
        _QWORD *a9)
{
  unsigned int v9; // r14d
  void *v11; // rdi
  struct _ACL *v12; // rbx
  unsigned int SelfRelativeSD; // r12d
  BOOL v14; // eax
  _QWORD *v15; // r15
  HLOCAL v16; // rax
  DWORD v18; // esi
  struct _ACL *v19; // rax
  __int64 v20; // rsi
  void *v21; // r9
  DWORD v22; // r8d
  BOOL Ace; // eax
  char v24; // cl
  DWORD LengthSid; // eax
  LPVOID pAce; // [rsp+20h] [rbp-38h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v28; // [rsp+48h] [rbp-10h]

  v28 = 0;
  v9 = a2;
  pAce = 0;
  dwBufferLength = 0;
  v11 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v12 = 0;
  SelfRelativeSD = 0;
  v14 = InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
  v15 = a9;
  if ( v14
    && SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
    && SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, 0) )
  {
    v18 = 8;
    if ( v9 )
    {
      do
      {
        LengthSid = GetLengthSid(*(PSID *)(a3 + 8LL * (_QWORD)v12));
        v12 = (struct _ACL *)(unsigned int)((_DWORD)v12 + 1);
        v18 += LengthSid + 8;
      }
      while ( (unsigned int)v12 < v9 );
    }
    v19 = (struct _ACL *)DllAllocSplMem(v18);
    v12 = v19;
    if ( v19 )
    {
      if ( InitializeAcl(v19, v18, 2u) )
      {
        v20 = 0;
        while ( (unsigned int)v20 < v9 )
        {
          v21 = *(void **)(a3 + 8 * v20);
          v22 = *(_DWORD *)(a4 + 4 * v20);
          if ( *(_BYTE *)(v20 + a1) )
            Ace = AddAccessDeniedAce(v12, 2u, v22, v21);
          else
            Ace = AddAccessAllowedAce(v12, 2u, v22, v21);
          if ( Ace && *(_BYTE *)(v20 + a5) && (Ace = GetAce(v12, v20, &pAce)) )
          {
            v24 = *(_BYTE *)(v20 + a5);
            v20 = (unsigned int)(v20 + 1);
            v9 = a2;
            *((_BYTE *)pAce + 1) = v24;
          }
          else
          {
            v9 = a2;
            v20 = (unsigned int)(v20 + 1);
            if ( !Ace )
              goto LABEL_9;
          }
        }
        if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v12, 0) )
        {
          dwBufferLength = GetSecurityDescriptorLength(pSecurityDescriptor);
          v16 = LocalAlloc(0, dwBufferLength);
          v11 = v16;
          if ( v16 )
          {
            SelfRelativeSD = MakeSelfRelativeSD(pSecurityDescriptor, v16, &dwBufferLength);
            if ( SelfRelativeSD )
            {
LABEL_9:
              *v15 = v11;
              goto LABEL_10;
            }
          }
        }
      }
    }
  }
  *v15 = 0;
  if ( v11 )
    LocalFree(v11);
  if ( v12 )
LABEL_10:
    DllFreeSplMem(v12);
  return SelfRelativeSD;
}

```

## disassembly

```asm
0x1800239a0  mov     rax, rsp
0x1800239a3  mov     [rax+20h], r9
0x1800239a7  mov     [rax+18h], r8
0x1800239ab  mov     [rax+10h], edx
0x1800239ae  mov     [rax+8], rcx
0x1800239b2  push    rbp
0x1800239b3  push    rbx
0x1800239b4  push    rsi
0x1800239b5  push    rdi
0x1800239b6  push    r12
0x1800239b8  push    r13
0x1800239ba  push    r14
0x1800239bc  push    r15
0x1800239be  mov     rbp, rsp
0x1800239c1  sub     rsp, 58h
0x1800239c5  xor     eax, eax
0x1800239c7  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800239cb  xorps   xmm0, xmm0
0x1800239ce  mov     [rbp+var_10], rax
0x1800239d2  mov     r14d, edx
0x1800239d5  mov     [rbp+pAce], rax
0x1800239d9  mov     r13, r8
0x1800239dc  mov     [rbp+dwBufferLength], eax
0x1800239e2  lea     edx, [rax+1]; dwRevision
0x1800239e5  xor     edi, edi
0x1800239e7  movups  [rbp+pSecurityDescriptor], xmm0
0x1800239eb  xor     ebx, ebx
0x1800239ed  xor     r12d, r12d
0x1800239f0  movups  [rbp+var_20], xmm0
0x1800239f4  call    cs:__imp_InitializeSecurityDescriptor
0x1800239fa  mov     r15, [rbp+arg_40]
0x180023a01  test    eax, eax
0x180023a03  jnz     loc_180023A9A
0x180023a09  mov     qword ptr [r15], 0
0x180023a10  test    rdi, rdi
0x180023a13  jz      short loc_180023A1E
0x180023a15  mov     rcx, rdi; hMem
0x180023a18  call    cs:__imp_LocalFree
0x180023a1e  test    rbx, rbx
0x180023a21  jnz     short loc_180023A7D
0x180023a23  jmp     short loc_180023A86
0x180023a25  xor     r9d, r9d; bDaclDefaulted
0x180023a28  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180023a2c  mov     r8, rbx; pDacl
0x180023a2f  lea     edx, [r9+1]; bDaclPresent
0x180023a33  call    cs:__imp_SetSecurityDescriptorDacl
0x180023a39  test    eax, eax
0x180023a3b  jz      short loc_180023A09
0x180023a3d  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180023a41  call    cs:__imp_GetSecurityDescriptorLength
0x180023a47  mov     edx, eax; uBytes
0x180023a49  xor     ecx, ecx; uFlags
0x180023a4b  mov     [rbp+dwBufferLength], edx
0x180023a51  call    cs:__imp_LocalAlloc
0x180023a57  mov     rdi, rax
0x180023a5a  test    rax, rax
0x180023a5d  jz      short loc_180023A09
0x180023a5f  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180023a66  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180023a69  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180023a6d  call    cs:__imp_MakeSelfRelativeSD
0x180023a73  mov     r12d, eax
0x180023a76  test    eax, eax
0x180023a78  jz      short loc_180023A09
0x180023a7a  mov     [r15], rdi
0x180023a7d  mov     rcx, rbx
0x180023a80  call    cs:__imp_DllFreeSplMem
0x180023a86  mov     eax, r12d
0x180023a89  add     rsp, 58h
0x180023a8d  pop     r15
0x180023a8f  pop     r14
0x180023a91  pop     r13
0x180023a93  pop     r12
0x180023a95  pop     rdi
0x180023a96  pop     rsi
0x180023a97  pop     rbx
0x180023a98  pop     rbp
0x180023a99  retn
0x180023a9a  mov     rdx, [rbp+pOwner]; pOwner
0x180023a9e  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180023aa2  xor     r8d, r8d; bOwnerDefaulted
0x180023aa5  call    cs:__imp_SetSecurityDescriptorOwner
0x180023aab  test    eax, eax
0x180023aad  jz      loc_180023A09
0x180023ab3  mov     rdx, [rbp+pGroup]; pGroup
0x180023ab7  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180023abb  xor     r8d, r8d; bGroupDefaulted
0x180023abe  call    cs:__imp_SetSecurityDescriptorGroup
0x180023ac4  test    eax, eax
0x180023ac6  jz      loc_180023A09
0x180023acc  mov     esi, 8
0x180023ad1  test    r14d, r14d
0x180023ad4  jnz     loc_180023B85
0x180023ada  mov     ecx, esi
0x180023adc  call    cs:__imp_DllAllocSplMem
0x180023ae2  mov     rbx, rax
0x180023ae5  test    rax, rax
0x180023ae8  jz      loc_180023A09
0x180023aee  mov     r8d, 2; dwAclRevision
0x180023af4  mov     edx, esi; nAclLength
0x180023af6  mov     rcx, rax; pAcl
0x180023af9  call    cs:__imp_InitializeAcl
0x180023aff  test    eax, eax
0x180023b01  jz      loc_180023A09
0x180023b07  mov     r13, [rbp+arg_20]
0x180023b0b  xor     esi, esi
0x180023b0d  cmp     esi, r14d
0x180023b10  jnb     loc_180023A25
0x180023b16  mov     rax, [rbp+arg_10]
0x180023b1a  mov     edx, 2; dwAceRevision
0x180023b1f  mov     rcx, rbx; pAcl
0x180023b22  mov     r9, [rax+rsi*8]; pSid
0x180023b26  mov     rax, [rbp+arg_18]
0x180023b2a  mov     r8d, [rax+rsi*4]; AccessMask
0x180023b2e  mov     rax, [rbp+arg_0]
0x180023b32  cmp     [rsi+rax], dil
0x180023b36  jnz     short loc_180023B7D
0x180023b38  call    cs:__imp_AddAccessAllowedAce
0x180023b3e  test    eax, eax
0x180023b40  jz      short loc_180023B48
0x180023b42  cmp     [rsi+r13], dil
0x180023b46  jnz     short loc_180023B57
0x180023b48  mov     r14d, [rbp+arg_8]
0x180023b4c  inc     esi
0x180023b4e  test    eax, eax
0x180023b50  jnz     short loc_180023B0D
0x180023b52  jmp     loc_180023A7A
0x180023b57  lea     r8, [rbp+pAce]; pAce
0x180023b5b  mov     edx, esi; dwAceIndex
0x180023b5d  mov     rcx, rbx; pAcl
0x180023b60  call    cs:__imp_GetAce
0x180023b66  test    eax, eax
0x180023b68  jz      short loc_180023B48
0x180023b6a  mov     cl, [rsi+r13]
0x180023b6e  inc     esi
0x180023b70  mov     rax, [rbp+pAce]
0x180023b74  mov     r14d, [rbp+arg_8]
0x180023b78  mov     [rax+1], cl
0x180023b7b  jmp     short loc_180023B0D
0x180023b7d  call    cs:__imp_AddAccessDeniedAce
0x180023b83  jmp     short loc_180023B3E
0x180023b85  mov     rcx, [r13+rbx*8+0]; pSid
0x180023b8a  call    cs:__imp_GetLengthSid
0x180023b90  add     esi, 8
0x180023b93  inc     ebx
0x180023b95  add     esi, eax
0x180023b97  cmp     ebx, r14d
0x180023b9a  jnb     loc_180023ADA
0x180023ba0  jmp     short loc_180023B85
```
