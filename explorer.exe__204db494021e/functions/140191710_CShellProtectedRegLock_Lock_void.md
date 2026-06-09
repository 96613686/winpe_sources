# CShellProtectedRegLock::Lock(void)

- ea: `0x140191710`
- end: `0x140191947`
- name: `?Lock@CShellProtectedRegLock@@QEAAXXZ`
- size: `567`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14019b85c`

## callees

- `0x140085c1c`
- `0x14010e160`
- `0x14010ed78`
- `0x140191710`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140191915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140191915`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1401917cb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1401917cb`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140191861`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1401918b6`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140191861`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1401918b6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140191752`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140191752`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14019181e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14019181e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140191781`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1401917af`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140191781`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1401917af`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140191890`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140191890`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x140191906`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x140191906`

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
    if ( !EqualSid(&qword_140201CB8, **(PSID **)this) )
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
0x140191710  mov     [rsp-28h+arg_8], rbx
0x140191715  mov     [rsp-28h+arg_10], rsi
0x14019171a  push    rbp
0x14019171b  push    rdi
0x14019171c  push    r13
0x14019171e  push    r14
0x140191720  push    r15
0x140191722  mov     rbp, rsp
0x140191725  sub     rsp, 70h
0x140191729  mov     rax, cs:__security_cookie
0x140191730  xor     rax, rsp
0x140191733  mov     [rbp+var_10], rax
0x140191737  cmp     qword ptr [rcx+10h], 0
0x14019173c  mov     rdi, rcx
0x14019173f  jz      loc_140191921
0x140191745  mov     rdx, [rcx]
0x140191748  lea     rcx, qword_140201CB8; pSid1
0x14019174f  mov     rdx, [rdx]; pSid2
0x140191752  call    cs:__imp_EqualSid
0x140191759  nop     dword ptr [rax+rax+00h]
0x14019175e  test    eax, eax
0x140191760  jnz     loc_140191921
0x140191766  mov     rcx, [rdi+10h]; pAcl
0x14019176a  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x14019176e  xor     eax, eax
0x140191770  mov     [rbp+pAclInformation], rax
0x140191774  mov     [rbp+var_18], eax
0x140191777  lea     esi, [rax+2]
0x14019177a  mov     r9d, esi; dwAclInformationClass
0x14019177d  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140191781  call    cs:__imp_GetAclInformation
0x140191788  nop     dword ptr [rax+rax+00h]
0x14019178d  test    eax, eax
0x14019178f  jz      loc_140191921
0x140191795  mov     rcx, [rdi+10h]; pAcl
0x140191799  lea     r9d, [rsi-1]; dwAclInformationClass
0x14019179d  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x1401917a0  lea     r8d, [rsi+2]; nAclInformationLength
0x1401917a4  lea     rdx, [rbp+dwAclRevision]; pAclInformation
0x1401917a8  mov     [rbp+dwAclRevision], 0
0x1401917af  call    cs:__imp_GetAclInformation
0x1401917b6  nop     dword ptr [rax+rax+00h]
0x1401917bb  mov     rcx, [rdi]
0x1401917be  mov     r15d, esi
0x1401917c1  test    eax, eax
0x1401917c3  cmovnz  r15d, [rbp+dwAclRevision]
0x1401917c8  mov     rcx, [rcx]; pSid
0x1401917cb  call    cs:__imp_GetLengthSid
0x1401917d2  nop     dword ptr [rax+rax+00h]
0x1401917d7  mov     r13d, eax
0x1401917da  mov     eax, 0FFFFh
0x1401917df  lea     esi, [r13+8]
0x1401917e3  cmp     esi, eax
0x1401917e5  ja      loc_140191921
0x1401917eb  add     ebx, esi
0x1401917ed  cmp     ebx, eax
0x1401917ef  ja      loc_140191921
0x1401917f5  lea     r8d, [rbx+rsi]; unsigned __int64
0x1401917f9  mov     [rbp+pAcl], 0
0x140191801  lea     r9, [rbp+pAcl]; void **
0x140191805  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x14019180a  test    eax, eax
0x14019180c  js      loc_140191921
0x140191812  mov     r14, [rbp+pAcl]
0x140191816  mov     r8d, r15d; dwAclRevision
0x140191819  mov     rcx, r14; pAcl
0x14019181c  mov     edx, ebx; nAclLength
0x14019181e  call    cs:__imp_InitializeAcl
0x140191825  nop     dword ptr [rax+rax+00h]
0x14019182a  add     rbx, r14
0x14019182d  mov     r8d, r13d; Size
0x140191830  mov     byte ptr [rbx], 1
0x140191833  lea     rcx, [rbx+8]; void *
0x140191837  mov     [rbx+2], si
0x14019183b  mov     dword ptr [rbx+4], 2
0x140191842  mov     rdx, [rdi]
0x140191845  mov     rdx, [rdx]; Src
0x140191848  call    memcpy_0
0x14019184d  or      r13d, 0FFFFFFFFh
0x140191851  mov     [rsp+70h+nAceListLength], esi; nAceListLength
0x140191855  mov     r8d, r13d; dwStartingAceIndex
0x140191858  mov     r9, rbx; pAceList
0x14019185b  mov     edx, r15d; dwAceRevision
0x14019185e  mov     rcx, r14; pAcl
0x140191861  call    cs:__imp_AddAce
0x140191868  nop     dword ptr [rax+rax+00h]
0x14019186d  test    eax, eax
0x14019186f  jz      loc_140191912
0x140191875  xor     esi, esi
0x140191877  xor     ebx, ebx
0x140191879  cmp     dword ptr [rbp+pAclInformation], ebx
0x14019187c  jbe     short loc_1401918DE
0x14019187e  mov     rcx, [rdi+10h]; pAcl
0x140191882  lea     r8, [rbp+pAcl]; pAce
0x140191886  mov     edx, ebx; dwAceIndex
0x140191888  mov     [rbp+pAcl], 0
0x140191890  call    cs:__imp_GetAce
0x140191897  nop     dword ptr [rax+rax+00h]
0x14019189c  test    eax, eax
0x14019189e  jz      short loc_1401918CE
0x1401918a0  mov     r9, [rbp+pAcl]; pAceList
0x1401918a4  mov     r8d, r13d; dwStartingAceIndex
0x1401918a7  mov     edx, r15d; dwAceRevision
0x1401918aa  mov     rcx, r14; pAcl
0x1401918ad  movzx   eax, word ptr [r9+2]
0x1401918b2  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x1401918b6  call    cs:__imp_AddAce
0x1401918bd  nop     dword ptr [rax+rax+00h]
0x1401918c2  test    eax, eax
0x1401918c4  mov     eax, 1
0x1401918c9  cmovz   esi, eax
0x1401918cc  jmp     short loc_1401918D3
0x1401918ce  mov     eax, 1
0x1401918d3  add     ebx, eax
0x1401918d5  cmp     ebx, dword ptr [rbp+pAclInformation]
0x1401918d8  jb      short loc_14019187E
0x1401918da  test    esi, esi
0x1401918dc  jnz     short loc_140191912
0x1401918de  mov     rcx, [rdi+8]; handle
0x1401918e2  xor     r9d, r9d; psidOwner
0x1401918e5  mov     [rsp+70h+pSacl], 0; pSacl
0x1401918ee  mov     r8d, 20000004h; SecurityInfo
0x1401918f4  mov     [rsp+70h+pDacl], r14; pDacl
0x1401918f9  mov     qword ptr [rsp+70h+nAceListLength], 0; psidGroup
0x140191902  lea     edx, [r9+4]; ObjectType
0x140191906  call    cs:__imp_SetSecurityInfo
0x14019190d  nop     dword ptr [rax+rax+00h]
0x140191912  mov     rcx, r14; hMem
0x140191915  call    cs:__imp_LocalFree
0x14019191c  nop     dword ptr [rax+rax+00h]
0x140191921  mov     rcx, [rbp+var_10]
0x140191925  xor     rcx, rsp; StackCookie
0x140191928  call    __security_check_cookie
0x14019192d  lea     r11, [rsp+70h+var_s0]
0x140191932  mov     rbx, [r11+38h]
0x140191936  mov     rsi, [r11+40h]
0x14019193a  mov     rsp, r11
0x14019193d  pop     r15
0x14019193f  pop     r14
0x140191941  pop     r13
0x140191943  pop     rdi
0x140191944  pop     rbp
0x140191945  retn
```
