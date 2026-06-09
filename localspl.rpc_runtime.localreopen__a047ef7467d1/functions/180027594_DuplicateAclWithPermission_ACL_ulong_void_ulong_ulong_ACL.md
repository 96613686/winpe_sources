# DuplicateAclWithPermission(_ACL *,ulong,void * *,ulong,ulong,_ACL * *)

- ea: `0x180027594`
- end: `0x180027771`
- name: `?DuplicateAclWithPermission@@YAKPEAU_ACL@@KPEAPEAXKKPEAPEAU1@@Z`
- size: `477`
- prototype: `unsigned int __usercall@<eax>(PACL pAcl@<rcx>, unsigned int@<edx>, void **@<r8>, unsigned int@<r9d>, unsigned int, struct _ACL **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180098ccc`

## callees

- `0x180011ed0`
- `0x180027594`
- `0x180046650`
- `0x180046a20`
- `0x180046aa0`
- `0x180047330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800275f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002771f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800275f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002771f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180027642`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180027642`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800276b5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800276df`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800276b5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800276df`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002760c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002760c`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180027704`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180027704`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800275eb`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800275eb`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180027670`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180027670`

## pseudocode

```c
DWORD __fastcall DuplicateAclWithPermission(
        PACL pAcl,
        DWORD a2,
        void **a3,
        unsigned int a4,
        DWORD AccessMask,
        struct _ACL **a6)
{
  __int64 i; // rbx
  DWORD LengthSid; // eax
  struct _ACL *v12; // rdi
  char v13; // r14
  DWORD j; // esi
  unsigned __int16 *v15; // r9
  __int64 k; // rbx
  DWORD LastError; // ebx
  unsigned __int64 v18; // rdx
  LPVOID pAce; // [rsp+30h] [rbp-40h] BYREF
  struct _ACL *v20; // [rsp+38h] [rbp-38h] BYREF
  PACL pAcla; // [rsp+40h] [rbp-30h]
  struct _ACL **v22; // [rsp+48h] [rbp-28h]
  __int64 pAclInformation; // [rsp+50h] [rbp-20h] BYREF
  int v24; // [rsp+58h] [rbp-18h]

  pAcla = pAcl;
  v22 = a6;
  pAclInformation = 0;
  v24 = 0;
  if ( !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
    return GetLastError();
  for ( i = 0; (unsigned int)i < a4; a2 += 2 * LengthSid + 24 )
  {
    LengthSid = GetLengthSid(a3[i]);
    i = (unsigned int)(i + 1);
  }
  v20 = (struct _ACL *)operator new[](a2);
  v12 = v20;
  memset_0(v20, 0, a2);
  if ( !InitializeAcl(v20, a2, 2u) )
  {
LABEL_21:
    LastError = GetLastError();
    operator delete(v12, v18);
    return LastError;
  }
  v13 = 0;
  for ( j = 0; j < (unsigned int)pAclInformation; ++j )
  {
    pAce = 0;
    if ( !GetAce(pAcla, j, &pAce) )
      goto LABEL_21;
    if ( v13 )
      goto LABEL_17;
    v15 = (unsigned __int16 *)pAce;
    if ( *(_BYTE *)pAce != 6 && *(_BYTE *)pAce != 1 )
    {
      v13 = 1;
      for ( k = 0; (unsigned int)k < a4; k = (unsigned int)(k + 1) )
      {
        if ( !AddAccessAllowedAceEx(v12, 2u, 0, AccessMask, a3[k])
          || !AddAccessAllowedAceEx(v12, 2u, 9u, 0xF0030u, a3[k]) )
        {
          goto LABEL_20;
        }
      }
LABEL_17:
      v15 = (unsigned __int16 *)pAce;
    }
    if ( !AddAce(v12, 2u, 0xFFFFFFFF, v15, v15[1]) )
    {
LABEL_20:
      LastError = GetLastError();
      goto LABEL_23;
    }
  }
  LastError = 0;
  v20 = 0;
  *v22 = v12;
LABEL_23:
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&v20);
  return LastError;
}

```

## disassembly

```asm
0x180027594  mov     [rsp-38h+arg_18], rbx
0x180027599  push    rbp
0x18002759a  push    rsi
0x18002759b  push    rdi
0x18002759c  push    r12
0x18002759e  push    r13
0x1800275a0  push    r14
0x1800275a2  push    r15
0x1800275a4  mov     rbp, rsp
0x1800275a7  sub     rsp, 70h
0x1800275ab  mov     rax, cs:__security_cookie
0x1800275b2  xor     rax, rsp
0x1800275b5  mov     [rbp+var_10], rax
0x1800275b9  mov     r12, [rbp+arg_28]
0x1800275bd  mov     rax, rcx
0x1800275c0  mov     [rbp+pAcl], rcx
0x1800275c4  mov     r13, r8
0x1800275c7  xor     ecx, ecx
0x1800275c9  mov     [rbp+var_28], r12
0x1800275cd  mov     r15d, r9d
0x1800275d0  mov     [rbp+pAclInformation], rcx
0x1800275d4  mov     esi, edx
0x1800275d6  mov     [rbp+var_18], ecx
0x1800275d9  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x1800275dd  lea     r12d, [rcx+2]
0x1800275e1  lea     r8d, [rcx+0Ch]; nAclInformationLength
0x1800275e5  mov     r9d, r12d; dwAclInformationClass
0x1800275e8  mov     rcx, rax; pAcl
0x1800275eb  call    cs:__imp_GetAclInformation
0x1800275f1  test    eax, eax
0x1800275f3  jnz     short loc_180027600
0x1800275f5  call    cs:__imp_GetLastError
0x1800275fb  jmp     loc_18002774D
0x180027600  xor     ebx, ebx
0x180027602  test    r15d, r15d
0x180027605  jz      short loc_18002761F
0x180027607  mov     rcx, [r13+rbx*8+0]; pSid
0x18002760c  call    cs:__imp_GetLengthSid
0x180027612  inc     ebx
0x180027614  lea     esi, [rsi+rax*2]
0x180027617  add     esi, 18h
0x18002761a  cmp     ebx, r15d
0x18002761d  jb      short loc_180027607
0x18002761f  mov     ecx, esi; unsigned __int64
0x180027621  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027626  mov     r8d, esi; Size
0x180027629  xor     edx, edx; Val
0x18002762b  mov     rcx, rax; void *
0x18002762e  mov     [rbp+var_38], rax
0x180027632  mov     rdi, rax
0x180027635  call    memset_0
0x18002763a  mov     r8d, r12d; dwAclRevision
0x18002763d  mov     edx, esi; nAclLength
0x18002763f  mov     rcx, rdi; pAcl
0x180027642  call    cs:__imp_InitializeAcl
0x180027648  test    eax, eax
0x18002764a  jz      loc_18002771F
0x180027650  xor     r14b, r14b
0x180027653  xor     esi, esi
0x180027655  cmp     esi, dword ptr [rbp+pAclInformation]
0x180027658  jnb     loc_180027731
0x18002765e  mov     rcx, [rbp+pAcl]; pAcl
0x180027662  lea     r8, [rbp+pAce]; pAce
0x180027666  mov     edx, esi; dwAceIndex
0x180027668  mov     [rbp+pAce], 0
0x180027670  call    cs:__imp_GetAce
0x180027676  test    eax, eax
0x180027678  jz      loc_18002771F
0x18002767e  test    r14b, r14b
0x180027681  jnz     short loc_1800276ED
0x180027683  mov     r9, [rbp+pAce]
0x180027687  cmp     byte ptr [r9], 6
0x18002768b  jz      short loc_1800276F1
0x18002768d  cmp     byte ptr [r9], 1
0x180027691  jz      short loc_1800276F1
0x180027693  mov     r14b, 1
0x180027696  xor     ebx, ebx
0x180027698  cmp     ebx, r15d
0x18002769b  jnb     short loc_1800276ED
0x18002769d  mov     rax, [r13+rbx*8+0]
0x1800276a2  xor     r8d, r8d; AceFlags
0x1800276a5  mov     r9d, [rbp+AccessMask]; AccessMask
0x1800276a9  mov     rcx, rdi; pAcl
0x1800276ac  mov     [rsp+70h+pSid], rax; pSid
0x1800276b1  lea     edx, [r8+2]; dwAceRevision
0x1800276b5  call    cs:__imp_AddAccessAllowedAceEx
0x1800276bb  test    eax, eax
0x1800276bd  jz      short loc_180027715
0x1800276bf  mov     rax, [r13+rbx*8+0]
0x1800276c4  mov     r8d, 9; AceFlags
0x1800276ca  mov     r9d, 0F0030h; AccessMask
0x1800276d0  mov     [rsp+70h+pSid], rax; pSid
0x1800276d5  mov     rcx, rdi; pAcl
0x1800276d8  lea     r12d, [r8-7]
0x1800276dc  mov     edx, r12d; dwAceRevision
0x1800276df  call    cs:__imp_AddAccessAllowedAceEx
0x1800276e5  test    eax, eax
0x1800276e7  jz      short loc_180027715
0x1800276e9  inc     ebx
0x1800276eb  jmp     short loc_180027698
0x1800276ed  mov     r9, [rbp+pAce]; pAceList
0x1800276f1  movzx   eax, word ptr [r9+2]
0x1800276f6  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800276fa  mov     edx, r12d; dwAceRevision
0x1800276fd  mov     dword ptr [rsp+70h+pSid], eax; nAceListLength
0x180027701  mov     rcx, rdi; pAcl
0x180027704  call    cs:__imp_AddAce
0x18002770a  test    eax, eax
0x18002770c  jz      short loc_180027715
0x18002770e  inc     esi
0x180027710  jmp     loc_180027655
0x180027715  call    cs:__imp_GetLastError
0x18002771b  mov     ebx, eax
0x18002771d  jmp     short loc_180027742
0x18002771f  call    cs:__imp_GetLastError
0x180027725  mov     rcx, rdi; void *
0x180027728  mov     ebx, eax
0x18002772a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002772f  jmp     short loc_18002774B
0x180027731  mov     rax, [rbp+var_28]
0x180027735  xor     ebx, ebx
0x180027737  mov     [rbp+var_38], 0
0x18002773f  mov     [rax], rdi
0x180027742  lea     rcx, [rbp+var_38]
0x180027746  call    ?Reset@?$TGenericSP@GV?$TAutoPtrArray@G@NCoreLibrary@@PEAG$0A@PEBG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort,NCoreLibrary::TAutoPtrArray<ushort>,ushort *,0,ushort const *>::Reset(void)
0x18002774b  mov     eax, ebx
0x18002774d  mov     rcx, [rbp+var_10]
0x180027751  xor     rcx, rsp; StackCookie
0x180027754  call    __security_check_cookie
0x180027759  mov     rbx, [rsp+70h+arg_18]
0x180027761  add     rsp, 70h
0x180027765  pop     r15
0x180027767  pop     r14
0x180027769  pop     r13
0x18002776b  pop     r12
0x18002776d  pop     rdi
0x18002776e  pop     rsi
0x18002776f  pop     rbp
0x180027770  retn
```
