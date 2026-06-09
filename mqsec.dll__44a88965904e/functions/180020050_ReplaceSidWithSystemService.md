# ReplaceSidWithSystemService

- ea: `0x180020050`
- end: `0x180020366`
- name: `ReplaceSidWithSystemService`
- size: `790`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR pSecurityDescriptor@<rcx>, PSECURITY_DESCRIPTOR@<rdx>, __int64, WINBOOL bDaclPresent)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001f5c0`

## callees

- `0x1800049ac`
- `0x1800136f0`
- `0x18001722c`
- `0x180020050`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180020310`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180020310`
- `ADVAPI32!AddAccessDeniedAceEx` at `0x180020265`
- `ADVAPI32!AddAccessDeniedAceEx` at `0x180020265`
- `ADVAPI32!AddAccessAllowedAce` at `0x180020216`
- `ADVAPI32!AddAccessAllowedAce` at `0x180020216`
- `ADVAPI32!EqualSid` at `0x1800201e6`
- `ADVAPI32!EqualSid` at `0x1800201e6`
- `ADVAPI32!GetAce` at `0x1800201cc`
- `ADVAPI32!GetAce` at `0x1800201cc`
- `ADVAPI32!InitializeAcl` at `0x18002016a`
- `ADVAPI32!InitializeAcl` at `0x18002016a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180020093`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180020093`
- `KERNEL32!GetLastError` at `0x18002009d`
- `KERNEL32!GetLastError` at `0x180020174`
- `KERNEL32!GetLastError` at `0x180020220`
- `KERNEL32!GetLastError` at `0x18002027a`
- `KERNEL32!GetLastError` at `0x1800202cc`
- `KERNEL32!GetLastError` at `0x18002031a`
- `KERNEL32!GetLastError` at `0x18002009d`
- `KERNEL32!GetLastError` at `0x180020174`
- `KERNEL32!GetLastError` at `0x180020220`
- `KERNEL32!GetLastError` at `0x18002027a`
- `KERNEL32!GetLastError` at `0x1800202cc`
- `KERNEL32!GetLastError` at `0x18002031a`

## pseudocode

```c
__int64 __fastcall ReplaceSidWithSystemService(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        PSECURITY_DESCRIPTOR a2,
        void *a3,
        char *a4,
        PACL *a5,
        int *bDaclPresent)
{
  int *v6; // r14
  int v7; // edi
  DWORD LastError; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  DWORD AclSize; // ebx
  struct _ACL *v15; // rax
  struct _ACL *v16; // rcx
  DWORD v17; // ebx
  DWORD AceCount; // r15d
  char *pSid; // rax
  DWORD v20; // eax
  WINBOOL bDaclDefaulted; // [rsp+30h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-20h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-18h] BYREF

  v6 = bDaclPresent;
  v7 = 0;
  LODWORD(bDaclPresent) = 0;
  bDaclDefaulted = 0;
  *v6 = 0;
  pDacl = 0;
  if ( !GetSecurityDescriptorDacl(a2, (LPBOOL)&bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v12 = 10;
LABEL_5:
      WPP_SF_d(v11[32], v12, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, LastError);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  if ( !pDacl || !(_DWORD)bDaclPresent )
    return 0;
  if ( pDacl->AclRevision == 2 )
  {
    AclSize = pDacl->AclSize;
    v15 = (struct _ACL *)MmAllocate(pDacl->AclSize);
    *a5 = v15;
    if ( InitializeAcl(v15, AclSize, 2u) )
    {
      v16 = pDacl;
      v17 = 0;
      AceCount = pDacl->AceCount;
      while ( v17 < AceCount )
      {
        pAce = 0;
        if ( !GetAce(v16, v17, &pAce) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          {
            v20 = GetLastError();
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 32),
              13,
              &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids,
              v17,
              v20);
          }
          return 3222146058LL;
        }
        if ( EqualSid((char *)pAce + 8, a3) )
        {
          pSid = a4;
          v7 = 1;
        }
        else
        {
          pSid = (char *)pAce + 8;
        }
        if ( *(_BYTE *)pAce )
        {
          if ( !AddAccessDeniedAceEx(*a5, 2u, 0, *((_DWORD *)pAce + 1), pSid) )
          {
            LastError = GetLastError();
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
            {
              v12 = 15;
              goto LABEL_5;
            }
            goto LABEL_6;
          }
        }
        else if ( !AddAccessAllowedAce(*a5, 2u, *((_DWORD *)pAce + 1), pSid) )
        {
          LastError = GetLastError();
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          {
            v12 = 14;
            goto LABEL_5;
          }
          goto LABEL_6;
        }
        v16 = pDacl;
        ++v17;
      }
      if ( !v7 || SetSecurityDescriptorDacl(pSecurityDescriptor, 1, *a5, 0) )
      {
        *v6 = v7;
        return 0;
      }
      LastError = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v12 = 16;
        goto LABEL_5;
      }
      goto LABEL_6;
    }
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v12 = 12;
      goto LABEL_5;
    }
LABEL_6:
    if ( (int)LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 32),
      11,
      &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids,
      pDacl->AclRevision);
  return 3222146088LL;
}

```

## disassembly

```asm
0x180020050  mov     [rsp-40h+pSid2], r8
0x180020055  push    rbp
0x180020056  push    rbx
0x180020057  push    rsi
0x180020058  push    rdi
0x180020059  push    r12
0x18002005b  push    r13
0x18002005d  push    r14
0x18002005f  push    r15
0x180020061  mov     rbp, rsp
0x180020064  sub     rsp, 58h
0x180020068  mov     r14, [rbp+bDaclPresent]
0x18002006c  lea     r8, [rbp+pDacl]; pDacl
0x180020070  xor     edi, edi
0x180020072  mov     rax, rdx
0x180020075  mov     r12, r9
0x180020078  mov     dword ptr [rbp+bDaclPresent], edi
0x18002007b  mov     r13, rcx
0x18002007e  mov     [rbp+bDaclDefaulted], edi
0x180020081  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180020085  mov     [r14], edi
0x180020088  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18002008c  mov     [rbp+pDacl], rdi
0x180020090  mov     rcx, rax; pSecurityDescriptor
0x180020093  call    cs:__imp_GetSecurityDescriptorDacl
0x180020099  test    eax, eax
0x18002009b  jnz     short loc_1800200EE
0x18002009d  call    cs:__imp_GetLastError
0x1800200a3  mov     ebx, eax
0x1800200a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200ac  lea     rax, WPP_GLOBAL_Control
0x1800200b3  cmp     rcx, rax
0x1800200b6  jz      short loc_1800200DA
0x1800200b8  test    byte ptr [rcx+10Ch], 1
0x1800200bf  jz      short loc_1800200DA
0x1800200c1  lea     edx, [rdi+0Ah]
0x1800200c4  mov     rcx, [rcx+100h]
0x1800200cb  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x1800200d2  mov     r9d, ebx
0x1800200d5  call    WPP_SF_d
0x1800200da  test    ebx, ebx
0x1800200dc  jle     short loc_1800200E7
0x1800200de  movzx   ebx, bx
0x1800200e1  or      ebx, 80070000h
0x1800200e7  mov     eax, ebx
0x1800200e9  jmp     loc_180020355
0x1800200ee  mov     rax, [rbp+pDacl]
0x1800200f2  test    rax, rax
0x1800200f5  jz      loc_180020353
0x1800200fb  cmp     dword ptr [rbp+bDaclPresent], edi
0x1800200fe  jz      loc_180020353
0x180020104  movzx   edx, byte ptr [rax]
0x180020107  cmp     dl, 2
0x18002010a  jz      short loc_18002014D
0x18002010c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020113  lea     rax, WPP_GLOBAL_Control
0x18002011a  cmp     rcx, rax
0x18002011d  jz      short loc_180020143
0x18002011f  test    byte ptr [rcx+10Ch], 1
0x180020126  jz      short loc_180020143
0x180020128  mov     rcx, [rcx+100h]
0x18002012f  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x180020136  mov     r9d, edx
0x180020139  mov     edx, 0Bh
0x18002013e  call    WPP_SF_d
0x180020143  mov     eax, 0C00E0C28h
0x180020148  jmp     loc_180020355
0x18002014d  movzx   ebx, word ptr [rax+2]
0x180020151  mov     ecx, ebx; unsigned __int64
0x180020153  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180020158  mov     rsi, [rbp+arg_20]
0x18002015c  mov     edx, ebx; nAclLength
0x18002015e  mov     r8d, 2; dwAclRevision
0x180020164  mov     rcx, rax; pAcl
0x180020167  mov     [rsi], rax
0x18002016a  call    cs:__imp_InitializeAcl
0x180020170  test    eax, eax
0x180020172  jnz     short loc_1800201AA
0x180020174  call    cs:__imp_GetLastError
0x18002017a  mov     ebx, eax
0x18002017c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020183  lea     rax, WPP_GLOBAL_Control
0x18002018a  cmp     rcx, rax
0x18002018d  jz      loc_1800200DA
0x180020193  test    byte ptr [rcx+10Ch], 1
0x18002019a  jz      loc_1800200DA
0x1800201a0  mov     edx, 0Ch
0x1800201a5  jmp     loc_1800200C4
0x1800201aa  mov     rcx, [rbp+pDacl]; pAcl
0x1800201ae  xor     ebx, ebx
0x1800201b0  movzx   r15d, word ptr [rcx+4]
0x1800201b5  cmp     ebx, r15d
0x1800201b8  jnb     loc_1800202FF
0x1800201be  lea     r8, [rbp+pAce]; pAce
0x1800201c2  mov     [rbp+pAce], 0
0x1800201ca  mov     edx, ebx; dwAceIndex
0x1800201cc  call    cs:__imp_GetAce
0x1800201d2  test    eax, eax
0x1800201d4  jz      loc_1800202B0
0x1800201da  mov     rcx, [rbp+pAce]
0x1800201de  mov     rdx, [rbp+pSid2]; pSid2
0x1800201e2  add     rcx, 8; pSid1
0x1800201e6  call    cs:__imp_EqualSid
0x1800201ec  mov     rcx, [rbp+pAce]
0x1800201f0  test    eax, eax
0x1800201f2  jz      short loc_1800201FE
0x1800201f4  mov     rax, r12
0x1800201f7  mov     edi, 1
0x1800201fc  jmp     short loc_180020202
0x1800201fe  lea     rax, [rcx+8]
0x180020202  cmp     byte ptr [rcx], 0
0x180020205  mov     edx, 2; dwAceRevision
0x18002020a  jnz     short loc_180020256
0x18002020c  mov     r8d, [rcx+4]; AccessMask
0x180020210  mov     r9, rax; pSid
0x180020213  mov     rcx, [rsi]; pAcl
0x180020216  call    cs:__imp_AddAccessAllowedAce
0x18002021c  test    eax, eax
0x18002021e  jnz     short loc_18002026F
0x180020220  call    cs:__imp_GetLastError
0x180020226  mov     ebx, eax
0x180020228  mov     rcx, cs:WPP_GLOBAL_Control
0x18002022f  lea     rax, WPP_GLOBAL_Control
0x180020236  cmp     rcx, rax
0x180020239  jz      loc_1800200DA
0x18002023f  test    byte ptr [rcx+10Ch], 1
0x180020246  jz      loc_1800200DA
0x18002024c  mov     edx, 0Eh
0x180020251  jmp     loc_1800200C4
0x180020256  mov     r9d, [rcx+4]; AccessMask
0x18002025a  xor     r8d, r8d; AceFlags
0x18002025d  mov     rcx, [rsi]; pAcl
0x180020260  mov     [rsp+58h+pSid], rax; pSid
0x180020265  call    cs:__imp_AddAccessDeniedAceEx
0x18002026b  test    eax, eax
0x18002026d  jz      short loc_18002027A
0x18002026f  mov     rcx, [rbp+pDacl]
0x180020273  inc     ebx
0x180020275  jmp     loc_1800201B5
0x18002027a  call    cs:__imp_GetLastError
0x180020280  mov     ebx, eax
0x180020282  mov     rcx, cs:WPP_GLOBAL_Control
0x180020289  lea     rax, WPP_GLOBAL_Control
0x180020290  cmp     rcx, rax
0x180020293  jz      loc_1800200DA
0x180020299  test    byte ptr [rcx+10Ch], 1
0x1800202a0  jz      loc_1800200DA
0x1800202a6  mov     edx, 0Fh
0x1800202ab  jmp     loc_1800200C4
0x1800202b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202b7  lea     rax, WPP_GLOBAL_Control
0x1800202be  cmp     rcx, rax
0x1800202c1  jz      short loc_1800202F8
0x1800202c3  test    byte ptr [rcx+10Ch], 1
0x1800202ca  jz      short loc_1800202F8
0x1800202cc  call    cs:__imp_GetLastError
0x1800202d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202d9  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x1800202e0  mov     edx, 0Dh
0x1800202e5  mov     dword ptr [rsp+58h+pSid], eax
0x1800202e9  mov     r9d, ebx
0x1800202ec  mov     rcx, [rcx+100h]
0x1800202f3  call    WPP_SF_dd
0x1800202f8  mov     eax, 0C00E0C0Ah
0x1800202fd  jmp     short loc_180020355
0x1800202ff  test    edi, edi
0x180020301  jz      short loc_180020350
0x180020303  mov     r8, [rsi]; pDacl
0x180020306  xor     r9d, r9d; bDaclDefaulted
0x180020309  mov     rcx, r13; pSecurityDescriptor
0x18002030c  lea     edx, [r9+1]; bDaclPresent
0x180020310  call    cs:__imp_SetSecurityDescriptorDacl
0x180020316  test    eax, eax
0x180020318  jnz     short loc_180020350
0x18002031a  call    cs:__imp_GetLastError
0x180020320  mov     ebx, eax
0x180020322  mov     rcx, cs:WPP_GLOBAL_Control
0x180020329  lea     rax, WPP_GLOBAL_Control
0x180020330  cmp     rcx, rax
0x180020333  jz      loc_1800200DA
0x180020339  test    byte ptr [rcx+10Ch], 1
0x180020340  jz      loc_1800200DA
0x180020346  mov     edx, 10h
0x18002034b  jmp     loc_1800200C4
0x180020350  mov     [r14], edi
0x180020353  xor     eax, eax
0x180020355  add     rsp, 58h
0x180020359  pop     r15
0x18002035b  pop     r14
0x18002035d  pop     r13
0x18002035f  pop     r12
0x180020361  pop     rdi
0x180020362  pop     rsi
0x180020363  pop     rbx
0x180020364  pop     rbp
0x180020365  retn
```
