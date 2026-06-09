# CMSMQQueueInfo::GetIsWorldReadable(int *)

- ea: `0x18001d410`
- end: `0x18001d673`
- name: `?GetIsWorldReadable@CMSMQQueueInfo@@IEAAJPEAH@Z`
- size: `611`
- prototype: `__int64 __fastcall(CMSMQQueueInfo *__hidden this, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001e4a0`
- `0x18001e520`

## callees

- `0x18000173c`
- `0x18000178c`
- `0x18001d410`
- `0x18001e10c`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d51c`
- `KERNEL32!GetLastError` at `0x18001d51c`
- `ADVAPI32!GetAclInformation` at `0x18001d567`
- `ADVAPI32!GetAclInformation` at `0x18001d567`
- `ADVAPI32!GetAce` at `0x18001d5b9`
- `ADVAPI32!GetAce` at `0x18001d5b9`
- `ADVAPI32!EqualSid` at `0x18001d5d5`
- `ADVAPI32!EqualSid` at `0x18001d5d5`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18001d512`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18001d512`
- `mqsec!MQSec_GetWorldSid` at `0x18001d57c`
- `mqsec!MQSec_GetWorldSid` at `0x18001d57c`
- `mqrt!MQGetQueueSecurity` at `0x18001d49c`
- `mqrt!MQGetQueueSecurity` at `0x18001d4ea`
- `mqrt!MQGetQueueSecurity` at `0x18001d49c`
- `mqrt!MQGetQueueSecurity` at `0x18001d4ea`

## pseudocode

```c
__int64 __fastcall CMSMQQueueInfo::GetIsWorldReadable(LPCWSTR *this, int *a2)
{
  BOOL v2; // r12d
  void *v3; // rsi
  int *v4; // r13
  int updated; // ebx
  HRESULT v7; // eax
  _BYTE *v8; // rcx
  int v9; // r14d
  DWORD i; // r15d
  _DWORD *v11; // r13
  int v12; // eax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-D0h] BYREF
  BOOL bDaclPresent; // [rsp+34h] [rbp-CCh] BYREF
  int v16; // [rsp+38h] [rbp-C8h]
  DWORD lpnLengthNeeded; // [rsp+3Ch] [rbp-C4h] BYREF
  BOOL bDaclDefaulted; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-B8h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-B0h] BYREF
  int *v21; // [rsp+58h] [rbp-A8h]
  PSID pSid2; // [rsp+60h] [rbp-A0h]
  __int64 pAclInformation; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+70h] [rbp-90h]
  _BYTE pSecurityDescriptor[256]; // [rsp+80h] [rbp-80h] BYREF

  v2 = 0;
  v21 = a2;
  v3 = 0;
  nLengthNeeded = 0;
  lpnLengthNeeded = 0;
  v4 = a2;
  bDaclPresent = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  updated = CMSMQQueueInfo::UpdateFormatName((CMSMQQueueInfo *)this);
  if ( updated < 0 )
    goto LABEL_31;
  v7 = MQGetQueueSecurity(this[20], 4u, pSecurityDescriptor, 0x100u, &nLengthNeeded);
  updated = v7;
  if ( v7 >= 0 )
  {
    v8 = pSecurityDescriptor;
  }
  else
  {
    if ( v7 != -1072824285 )
      goto LABEL_31;
    v3 = operator new(nLengthNeeded);
    if ( !v3 )
    {
      updated = -2147024882;
      goto LABEL_31;
    }
    updated = MQGetQueueSecurity(this[20], 4u, v3, nLengthNeeded, &lpnLengthNeeded);
    if ( updated < 0 )
      goto LABEL_31;
    v8 = v3;
  }
  if ( GetSecurityDescriptorDacl(v8, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    if ( bDaclPresent && pDacl )
    {
      pAclInformation = 0;
      v24 = 0;
      if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
        goto LABEL_10;
      v9 = 0;
      v16 = 131115;
      pSid2 = MQSec_GetWorldSid();
      for ( i = 0; i < (unsigned int)pAclInformation && !v2; ++i )
      {
        pAce = 0;
        if ( !GetAce(pDacl, i, &pAce) )
          goto LABEL_10;
        v11 = pAce;
        if ( EqualSid((char *)pAce + 8, pSid2) )
        {
          if ( *(_BYTE *)v11 )
          {
            if ( *(_BYTE *)v11 == 1 )
            {
              v2 = (v11[1] & 0x2002B) != 0;
              v12 = 0;
              if ( (v11[1] & 0x2002B) == 0 )
                v12 = v9;
              v9 = v12;
            }
          }
          else
          {
            v16 &= ~v11[1];
            if ( !v16 )
            {
              v9 = 1;
              v2 = 1;
            }
          }
        }
      }
      v4 = v21;
    }
    else
    {
      v9 = 1;
    }
    *v4 = v9;
    goto LABEL_31;
  }
LABEL_10:
  updated = GetLastError();
  if ( updated >= 0 )
    updated = -2147467259;
LABEL_31:
  operator delete(v3);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001d410  mov     [rsp-8+arg_10], rbx
0x18001d415  push    rbp
0x18001d416  push    rsi
0x18001d417  push    rdi
0x18001d418  push    r12
0x18001d41a  push    r13
0x18001d41c  push    r14
0x18001d41e  push    r15
0x18001d420  lea     rbp, [rsp-90h]
0x18001d428  sub     rsp, 190h
0x18001d42f  mov     rax, cs:__security_cookie
0x18001d436  xor     rax, rsp
0x18001d439  mov     [rbp+0C0h+var_40], rax
0x18001d440  xor     r12d, r12d
0x18001d443  mov     [rsp+1C0h+var_168], rdx
0x18001d448  mov     esi, r12d
0x18001d44b  mov     [rsp+1C0h+nLengthNeeded], r12d
0x18001d450  mov     [rsp+1C0h+var_184], r12d
0x18001d455  mov     r13, rdx
0x18001d458  mov     [rsp+1C0h+bDaclPresent], r12d
0x18001d45d  mov     rdi, rcx
0x18001d460  mov     [rsp+1C0h+pDacl], r12
0x18001d465  mov     [rsp+1C0h+bDaclDefaulted], r12d
0x18001d46a  call    ?UpdateFormatName@CMSMQQueueInfo@@IEAAJXZ; CMSMQQueueInfo::UpdateFormatName(void)
0x18001d46f  mov     ebx, eax
0x18001d471  test    eax, eax
0x18001d473  js      loc_18001D63F
0x18001d479  mov     rcx, [rdi+0A0h]; lpwcsFormatName
0x18001d480  lea     rax, [rsp+1C0h+nLengthNeeded]
0x18001d485  lea     r14d, [r12+4]
0x18001d48a  mov     [rsp+1C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001d48f  mov     edx, r14d; RequestedInformation
0x18001d492  lea     r8, [rbp+0C0h+pSecurityDescriptor]; pSecurityDescriptor
0x18001d496  mov     r9d, 100h; nLength
0x18001d49c  call    cs:__imp_MQGetQueueSecurity
0x18001d4a2  mov     ebx, eax
0x18001d4a4  test    eax, eax
0x18001d4a6  jns     short loc_18001D4FF
0x18001d4a8  cmp     eax, 0C00E0023h
0x18001d4ad  jnz     loc_18001D63F
0x18001d4b3  mov     ecx, [rsp+1C0h+nLengthNeeded]; Size
0x18001d4b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d4bc  mov     rsi, rax
0x18001d4bf  test    rax, rax
0x18001d4c2  jnz     short loc_18001D4CE
0x18001d4c4  mov     ebx, 8007000Eh
0x18001d4c9  jmp     loc_18001D63F
0x18001d4ce  mov     r9d, [rsp+1C0h+nLengthNeeded]; nLength
0x18001d4d3  lea     rax, [rsp+1C0h+var_184]
0x18001d4d8  mov     rcx, [rdi+0A0h]; lpwcsFormatName
0x18001d4df  mov     r8, rsi; pSecurityDescriptor
0x18001d4e2  mov     edx, r14d; RequestedInformation
0x18001d4e5  mov     [rsp+1C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001d4ea  call    cs:__imp_MQGetQueueSecurity
0x18001d4f0  mov     ebx, eax
0x18001d4f2  test    eax, eax
0x18001d4f4  js      loc_18001D63F
0x18001d4fa  mov     rcx, rsi
0x18001d4fd  jmp     short loc_18001D503
0x18001d4ff  lea     rcx, [rbp+0C0h+pSecurityDescriptor]; pSecurityDescriptor
0x18001d503  lea     r9, [rsp+1C0h+bDaclDefaulted]; lpbDaclDefaulted
0x18001d508  lea     r8, [rsp+1C0h+pDacl]; pDacl
0x18001d50d  lea     rdx, [rsp+1C0h+bDaclPresent]; lpbDaclPresent
0x18001d512  call    cs:__imp_GetSecurityDescriptorDacl
0x18001d518  test    eax, eax
0x18001d51a  jnz     short loc_18001D536
0x18001d51c  call    cs:__imp_GetLastError
0x18001d522  mov     ebx, eax
0x18001d524  test    eax, eax
0x18001d526  js      loc_18001D63F
0x18001d52c  mov     ebx, 80004005h
0x18001d531  jmp     loc_18001D63F
0x18001d536  cmp     [rsp+1C0h+bDaclPresent], r12d
0x18001d53b  jz      loc_18001D62E
0x18001d541  mov     rcx, [rsp+1C0h+pDacl]; pAcl
0x18001d546  test    rcx, rcx
0x18001d549  jz      loc_18001D62E
0x18001d54f  xor     eax, eax
0x18001d551  lea     rdx, [rsp+1C0h+pAclInformation]; pAclInformation
0x18001d556  mov     [rsp+1C0h+pAclInformation], rax
0x18001d55b  mov     [rsp+1C0h+var_150], eax
0x18001d55f  lea     r9d, [rax+2]; dwAclInformationClass
0x18001d563  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18001d567  call    cs:__imp_GetAclInformation
0x18001d56d  test    eax, eax
0x18001d56f  jz      short loc_18001D51C
0x18001d571  mov     r14d, r12d
0x18001d574  mov     [rsp+1C0h+var_188], 2002Bh
0x18001d57c  call    cs:__imp_?MQSec_GetWorldSid@@YAPEAXXZ; MQSec_GetWorldSid(void)
0x18001d582  mov     [rsp+1C0h+pSid2], rax
0x18001d587  mov     r15d, r12d
0x18001d58a  mov     edi, 1
0x18001d58f  cmp     r15d, dword ptr [rsp+1C0h+pAclInformation]
0x18001d594  jnb     loc_18001D636
0x18001d59a  test    r12d, r12d
0x18001d59d  jnz     loc_18001D636
0x18001d5a3  mov     rcx, [rsp+1C0h+pDacl]; pAcl
0x18001d5a8  lea     r8, [rsp+1C0h+pAce]; pAce
0x18001d5ad  mov     edx, r15d; dwAceIndex
0x18001d5b0  mov     [rsp+1C0h+pAce], 0
0x18001d5b9  call    cs:__imp_GetAce
0x18001d5bf  test    eax, eax
0x18001d5c1  jz      loc_18001D51C
0x18001d5c7  mov     r13, [rsp+1C0h+pAce]
0x18001d5cc  mov     rdx, [rsp+1C0h+pSid2]; pSid2
0x18001d5d1  lea     rcx, [r13+8]; pSid1
0x18001d5d5  call    cs:__imp_EqualSid
0x18001d5db  test    eax, eax
0x18001d5dd  jz      short loc_18001D626
0x18001d5df  movzx   ecx, byte ptr [r13+0]
0x18001d5e4  test    ecx, ecx
0x18001d5e6  jz      short loc_18001D60B
0x18001d5e8  cmp     ecx, edi
0x18001d5ea  jnz     short loc_18001D626
0x18001d5ec  test    dword ptr [r13+4], 2002Bh
0x18001d5f4  cmovnz  r12d, edi
0x18001d5f8  xor     eax, eax
0x18001d5fa  test    dword ptr [r13+4], 2002Bh
0x18001d602  cmovz   eax, r14d
0x18001d606  mov     r14d, eax
0x18001d609  jmp     short loc_18001D626
0x18001d60b  mov     eax, [r13+4]
0x18001d60f  mov     r13d, [rsp+1C0h+var_188]
0x18001d614  not     eax
0x18001d616  and     r13d, eax
0x18001d619  mov     [rsp+1C0h+var_188], r13d
0x18001d61e  jnz     short loc_18001D626
0x18001d620  mov     r14d, edi
0x18001d623  mov     r12d, edi
0x18001d626  add     r15d, edi
0x18001d629  jmp     loc_18001D58F
0x18001d62e  mov     r14d, 1
0x18001d634  jmp     short loc_18001D63B
0x18001d636  mov     r13, [rsp+1C0h+var_168]
0x18001d63b  mov     [r13+0], r14d
0x18001d63f  mov     rcx, rsi; Block
0x18001d642  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d647  mov     eax, ebx
0x18001d649  mov     rcx, [rbp+0C0h+var_40]
0x18001d650  xor     rcx, rsp; StackCookie
0x18001d653  call    __security_check_cookie
0x18001d658  mov     rbx, [rsp+1C0h+arg_10]
0x18001d660  add     rsp, 190h
0x18001d667  pop     r15
0x18001d669  pop     r14
0x18001d66b  pop     r13
0x18001d66d  pop     r12
0x18001d66f  pop     rdi
0x18001d670  pop     rsi
0x18001d671  pop     rbp
0x18001d672  retn
```
