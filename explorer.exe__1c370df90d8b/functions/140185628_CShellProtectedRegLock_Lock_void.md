# CShellProtectedRegLock::Lock(void)

- ea: `0x140185628`
- end: `0x140185822`
- name: `?Lock@CShellProtectedRegLock@@QEAAXXZ`
- size: `506`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14018f028`

## callees

- `0x14007ff8c`
- `0x1401040e0`
- `0x140104cc8`
- `0x140185628`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401857f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401857f7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1401856d1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1401856d1`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140185693`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1401856bb`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140185693`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1401856bb`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140185784`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140185784`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14018566a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14018566a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14018571e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14018571e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14018575b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1401857a4`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14018575b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1401857a4`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1401857ee`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1401857ee`

## pseudocode

```c
void __fastcall CShellProtectedRegLock::Lock(CShellProtectedRegLock *this)
{
  struct _ACL *v2; // rcx
  struct _ACL *v3; // rcx
  int v4; // ebx
  DWORD v5; // r15d
  unsigned int v6; // edx
  void *v7; // rcx
  DWORD LengthSid; // r13d
  DWORD nAceListLength; // esi
  __int64 v10; // rbx
  struct _ACL *pDacl; // r14
  _WORD *v12; // rbx
  int v13; // esi
  DWORD v14; // ebx
  struct _ACL *v15; // rcx
  DWORD dwAclRevision; // [rsp+40h] [rbp-30h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+58h] [rbp-18h]

  if ( *((_QWORD *)this + 2) )
  {
    if ( !EqualSid(qword_140205E98, **(PSID **)this) )
    {
      v2 = (struct _ACL *)*((_QWORD *)this + 2);
      pAclInformation = 0;
      v19 = 0;
      if ( GetAclInformation(v2, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        v3 = (struct _ACL *)*((_QWORD *)this + 2);
        v4 = HIDWORD(pAclInformation);
        dwAclRevision = 0;
        v5 = 2;
        if ( GetAclInformation(v3, &dwAclRevision, 4u, AclRevisionInformation) )
          v5 = dwAclRevision;
        LengthSid = GetLengthSid(**(PSID **)this);
        nAceListLength = LengthSid + 8;
        if ( LengthSid + 8 <= 0xFFFF )
        {
          v10 = nAceListLength + v4;
          if ( (unsigned int)v10 <= 0xFFFF )
          {
            pAcl = 0;
            if ( CTLocalAllocPolicy::Alloc(v7, v6, (unsigned int)v10 + nAceListLength, (void **)&pAcl) >= 0 )
            {
              pDacl = pAcl;
              InitializeAcl(pAcl, v10, v5);
              v12 = (_WORD *)((char *)pDacl + v10);
              *(_BYTE *)v12 = 1;
              v12[1] = LengthSid + 8;
              *((_DWORD *)v12 + 1) = 2;
              memcpy_0(v12 + 4, **(const void ***)this, LengthSid);
              if ( AddAce(pDacl, v5, 0xFFFFFFFF, v12, nAceListLength) )
              {
                v13 = 0;
                v14 = 0;
                if ( !(_DWORD)pAclInformation )
                  goto LABEL_16;
                do
                {
                  v15 = (struct _ACL *)*((_QWORD *)this + 2);
                  pAcl = 0;
                  if ( GetAce(v15, v14, (LPVOID *)&pAcl) )
                  {
                    if ( !AddAce(pDacl, v5, 0xFFFFFFFF, pAcl, pAcl->AclSize) )
                      v13 = 1;
                  }
                  ++v14;
                }
                while ( v14 < (unsigned int)pAclInformation );
                if ( !v13 )
LABEL_16:
                  SetSecurityInfo(*((HANDLE *)this + 1), SE_REGISTRY_KEY, 0x20000004u, 0, 0, pDacl, 0);
              }
              LocalFree(pDacl);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140185628  mov     [rsp-28h+arg_8], rbx
0x14018562d  mov     [rsp-28h+arg_10], rsi
0x140185632  push    rbp
0x140185633  push    rdi
0x140185634  push    r13
0x140185636  push    r14
0x140185638  push    r15
0x14018563a  mov     rbp, rsp
0x14018563d  sub     rsp, 70h
0x140185641  mov     rax, cs:__security_cookie
0x140185648  xor     rax, rsp
0x14018564b  mov     [rbp+var_10], rax
0x14018564f  cmp     qword ptr [rcx+10h], 0
0x140185654  mov     rdi, rcx
0x140185657  jz      loc_1401857FD
0x14018565d  mov     rdx, [rcx]
0x140185660  lea     rcx, qword_140205E98; pSid1
0x140185667  mov     rdx, [rdx]; pSid2
0x14018566a  call    cs:__imp_EqualSid
0x140185670  test    eax, eax
0x140185672  jnz     loc_1401857FD
0x140185678  mov     rcx, [rdi+10h]; pAcl
0x14018567c  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x140185680  xor     eax, eax
0x140185682  mov     [rbp+pAclInformation], rax
0x140185686  mov     [rbp+var_18], eax
0x140185689  lea     esi, [rax+2]
0x14018568c  mov     r9d, esi; dwAclInformationClass
0x14018568f  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140185693  call    cs:__imp_GetAclInformation
0x140185699  test    eax, eax
0x14018569b  jz      loc_1401857FD
0x1401856a1  mov     rcx, [rdi+10h]; pAcl
0x1401856a5  lea     r9d, [rsi-1]; dwAclInformationClass
0x1401856a9  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x1401856ac  lea     r8d, [rsi+2]; nAclInformationLength
0x1401856b0  lea     rdx, [rbp+dwAclRevision]; pAclInformation
0x1401856b4  mov     [rbp+dwAclRevision], 0
0x1401856bb  call    cs:__imp_GetAclInformation
0x1401856c1  mov     rcx, [rdi]
0x1401856c4  mov     r15d, esi
0x1401856c7  test    eax, eax
0x1401856c9  cmovnz  r15d, [rbp+dwAclRevision]
0x1401856ce  mov     rcx, [rcx]; pSid
0x1401856d1  call    cs:__imp_GetLengthSid
0x1401856d7  mov     r13d, eax
0x1401856da  mov     eax, 0FFFFh
0x1401856df  lea     esi, [r13+8]
0x1401856e3  cmp     esi, eax
0x1401856e5  ja      loc_1401857FD
0x1401856eb  add     ebx, esi
0x1401856ed  cmp     ebx, eax
0x1401856ef  ja      loc_1401857FD
0x1401856f5  lea     r8d, [rbx+rsi]; unsigned __int64
0x1401856f9  mov     [rbp+pAcl], 0
0x140185701  lea     r9, [rbp+pAcl]; void **
0x140185705  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x14018570a  test    eax, eax
0x14018570c  js      loc_1401857FD
0x140185712  mov     r14, [rbp+pAcl]
0x140185716  mov     r8d, r15d; dwAclRevision
0x140185719  mov     rcx, r14; pAcl
0x14018571c  mov     edx, ebx; nAclLength
0x14018571e  call    cs:__imp_InitializeAcl
0x140185724  add     rbx, r14
0x140185727  mov     r8d, r13d; Size
0x14018572a  mov     byte ptr [rbx], 1
0x14018572d  lea     rcx, [rbx+8]; void *
0x140185731  mov     [rbx+2], si
0x140185735  mov     dword ptr [rbx+4], 2
0x14018573c  mov     rdx, [rdi]
0x14018573f  mov     rdx, [rdx]; Src
0x140185742  call    memcpy_0
0x140185747  or      r13d, 0FFFFFFFFh
0x14018574b  mov     [rsp+70h+nAceListLength], esi; nAceListLength
0x14018574f  mov     r8d, r13d; dwStartingAceIndex
0x140185752  mov     r9, rbx; pAceList
0x140185755  mov     edx, r15d; dwAceRevision
0x140185758  mov     rcx, r14; pAcl
0x14018575b  call    cs:__imp_AddAce
0x140185761  test    eax, eax
0x140185763  jz      loc_1401857F4
0x140185769  xor     esi, esi
0x14018576b  xor     ebx, ebx
0x14018576d  cmp     dword ptr [rbp+pAclInformation], ebx
0x140185770  jbe     short loc_1401857C6
0x140185772  mov     rcx, [rdi+10h]; pAcl
0x140185776  lea     r8, [rbp+pAcl]; pAce
0x14018577a  mov     edx, ebx; dwAceIndex
0x14018577c  mov     [rbp+pAcl], 0
0x140185784  call    cs:__imp_GetAce
0x14018578a  test    eax, eax
0x14018578c  jz      short loc_1401857B6
0x14018578e  mov     r9, [rbp+pAcl]; pAceList
0x140185792  mov     r8d, r13d; dwStartingAceIndex
0x140185795  mov     edx, r15d; dwAceRevision
0x140185798  mov     rcx, r14; pAcl
0x14018579b  movzx   eax, word ptr [r9+2]
0x1401857a0  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x1401857a4  call    cs:__imp_AddAce
0x1401857aa  test    eax, eax
0x1401857ac  mov     eax, 1
0x1401857b1  cmovz   esi, eax
0x1401857b4  jmp     short loc_1401857BB
0x1401857b6  mov     eax, 1
0x1401857bb  add     ebx, eax
0x1401857bd  cmp     ebx, dword ptr [rbp+pAclInformation]
0x1401857c0  jb      short loc_140185772
0x1401857c2  test    esi, esi
0x1401857c4  jnz     short loc_1401857F4
0x1401857c6  mov     rcx, [rdi+8]; handle
0x1401857ca  xor     r9d, r9d; psidOwner
0x1401857cd  mov     [rsp+70h+pSacl], 0; pSacl
0x1401857d6  mov     r8d, 20000004h; SecurityInfo
0x1401857dc  mov     [rsp+70h+pDacl], r14; pDacl
0x1401857e1  mov     qword ptr [rsp+70h+nAceListLength], 0; psidGroup
0x1401857ea  lea     edx, [r9+4]; ObjectType
0x1401857ee  call    cs:__imp_SetSecurityInfo
0x1401857f4  mov     rcx, r14; hMem
0x1401857f7  call    cs:__imp_LocalFree
0x1401857fd  mov     rcx, [rbp+var_10]
0x140185801  xor     rcx, rsp; StackCookie
0x140185804  call    __security_check_cookie
0x140185809  lea     r11, [rsp+70h+var_s0]
0x14018580e  mov     rbx, [r11+38h]
0x140185812  mov     rsi, [r11+40h]
0x140185816  mov     rsp, r11
0x140185819  pop     r15
0x14018581b  pop     r14
0x14018581d  pop     r13
0x14018581f  pop     rdi
0x140185820  pop     rbp
0x140185821  retn
```
