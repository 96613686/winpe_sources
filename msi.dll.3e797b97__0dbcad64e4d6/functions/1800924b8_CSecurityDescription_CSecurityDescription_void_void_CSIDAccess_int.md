# CSecurityDescription::CSecurityDescription(void *,void *,CSIDAccess *,int)

- ea: `0x1800924b8`
- end: `0x1800926f2`
- name: `??0CSecurityDescription@@QEAA@PEAX0PEAUCSIDAccess@@H@Z`
- size: `570`
- prototype: `CSecurityDescription *(CSecurityDescription *__hidden this, void *, void *, struct CSIDAccess *, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800811d8`
- `0x180092930`
- `0x18014d394`
- `0x1801e6908`
- `0x18020f4c4`

## callees

- `0x1800924b8`
- `0x1800aa6f8`
- `0x180149e8c`
- `0x180265240`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x180092560`
- `ADVAPI32!InitializeAcl` at `0x180092560`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18009269d`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18009269d`
- `ADVAPI32!GetLengthSid` at `0x18009250d`
- `ADVAPI32!GetLengthSid` at `0x18009250d`
- `ADVAPI32!AddAccessAllowedAce` at `0x180092598`
- `ADVAPI32!AddAccessAllowedAce` at `0x180092598`
- `ADVAPI32!GetAce` at `0x1800925c1`
- `ADVAPI32!GetAce` at `0x1800925c1`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800925fe`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800925fe`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180092623`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180092623`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18009263e`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18009263e`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180092657`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180092657`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18009268d`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18009268d`
- `KERNEL32!GlobalAlloc` at `0x18009266b`
- `KERNEL32!GlobalAlloc` at `0x18009266b`
- `KERNEL32!GlobalFree` at `0x1800926bc`
- `KERNEL32!GlobalFree` at `0x1800926bc`

## pseudocode

```c
CSecurityDescription *__fastcall CSecurityDescription::CSecurityDescription(
        CSecurityDescription *this,
        void *a2,
        void *a3,
        PSID *a4,
        int a5)
{
  __int64 v8; // rsi
  signed int i; // ebx
  DWORD LengthSid; // eax
  struct _ACL *v11; // rcx
  signed int j; // ebx
  HGLOBAL v13; // rax
  DWORD dwBufferLength; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pAce; // [rsp+28h] [rbp-D8h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  PACL pAcl; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+68h] [rbp-98h]
  _BYTE v21[512]; // [rsp+70h] [rbp-90h] BYREF

  CSecurityDescription::Initialize(this);
  v8 = 0;
  *((_BYTE *)this + 25) = 0;
  for ( i = 8; (int)v8 < a5; i += LengthSid + 8 )
  {
    LengthSid = GetLengthSid(a4[3 * v8]);
    v8 = (unsigned int)(v8 + 1);
  }
  v11 = (struct _ACL *)v21;
  v20 = 512;
  pAcl = (PACL)v21;
  if ( i > 512 )
  {
    if ( !(unsigned __int8)CAPITempBuffer<char,512>::SetSize(&pAcl, (unsigned int)i) )
      goto LABEL_17;
    v11 = pAcl;
  }
  if ( InitializeAcl(v11, i, 2u) )
  {
    for ( j = 0; j < a5; ++j )
    {
      if ( !AddAccessAllowedAce(pAcl, 2u, (DWORD)a4[3 * j + 2], a4[3 * j]) )
        goto LABEL_17;
      pAce = 0;
      if ( !GetAce(pAcl, j, &pAce) )
        goto LABEL_17;
      *((_BYTE *)pAce + 1) = 3;
    }
    v18 = 0;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pAcl, 0) )
      {
        if ( SetSecurityDescriptorOwner(pSecurityDescriptor, a2, 0) )
        {
          *((_BYTE *)this + 25) = 0;
          dwBufferLength = GetSecurityDescriptorLength(pSecurityDescriptor);
          v13 = GlobalAlloc(0, dwBufferLength);
          *((_QWORD *)this + 1) = v13;
          if ( v13 )
          {
            MakeSelfRelativeSD(pSecurityDescriptor, v13, &dwBufferLength);
            *((_BYTE *)this + 25) = IsValidSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)this + 1));
          }
        }
      }
    }
  }
LABEL_17:
  if ( v20 > 512 )
    GlobalFree(pAcl);
  return this;
}

```

## disassembly

```asm
0x1800924b8  mov     [rsp-8+arg_10], rbx
0x1800924bd  push    rbp
0x1800924be  push    rsi
0x1800924bf  push    rdi
0x1800924c0  push    r12
0x1800924c2  push    r15
0x1800924c4  lea     rbp, [rsp-180h]
0x1800924cc  sub     rsp, 280h
0x1800924d3  mov     rax, cs:__security_cookie
0x1800924da  xor     rax, rsp
0x1800924dd  mov     [rbp+1A0h+var_30], rax
0x1800924e4  mov     r15, r9
0x1800924e7  mov     r12, rdx
0x1800924ea  mov     rdi, rcx
0x1800924ed  call    ?Initialize@CSecurityDescription@@IEAAXXZ; CSecurityDescription::Initialize(void)
0x1800924f2  xor     esi, esi
0x1800924f4  mov     byte ptr [rdi+19h], 0
0x1800924f8  mov     ebx, 8
0x1800924fd  cmp     [rbp+1A0h+arg_20], esi
0x180092503  jle     short loc_180092528
0x180092505  lea     rcx, [rsi+rsi*2]
0x180092509  mov     rcx, [r15+rcx*8]; pSid
0x18009250d  call    cs:__imp_GetLengthSid
0x180092514  nop     dword ptr [rax+rax+00h]
0x180092519  add     ebx, 8
0x18009251c  inc     esi
0x18009251e  add     ebx, eax
0x180092520  cmp     esi, [rbp+1A0h+arg_20]
0x180092526  jl      short loc_180092505
0x180092528  mov     esi, 200h
0x18009252d  lea     rcx, [rsp+2A0h+var_230]
0x180092532  mov     [rsp+2A0h+var_238], esi
0x180092536  mov     [rsp+2A0h+pAcl], rcx
0x18009253b  cmp     ebx, esi
0x18009253d  jle     short loc_180092558
0x18009253f  mov     edx, ebx
0x180092541  lea     rcx, [rsp+2A0h+pAcl]
0x180092546  call    ?SetSize@?$CAPITempBuffer@D$0CAA@@@QEAA_NH_N@Z; CAPITempBuffer<char,512>::SetSize(int,bool)
0x18009254b  test    al, al
0x18009254d  jz      loc_1800926B1
0x180092553  mov     rcx, [rsp+2A0h+pAcl]; pAcl
0x180092558  mov     r8d, 2; dwAclRevision
0x18009255e  mov     edx, ebx; nAclLength
0x180092560  call    cs:__imp_InitializeAcl
0x180092567  nop     dword ptr [rax+rax+00h]
0x18009256c  test    eax, eax
0x18009256e  jz      loc_1800926B1
0x180092574  xor     ebx, ebx
0x180092576  cmp     ebx, [rbp+1A0h+arg_20]
0x18009257c  jge     short loc_1800925E2
0x18009257e  mov     rcx, [rsp+2A0h+pAcl]; pAcl
0x180092583  mov     edx, 2; dwAceRevision
0x180092588  movsxd  rax, ebx
0x18009258b  lea     r8, [rax+rax*2]
0x18009258f  mov     r9, [r15+r8*8]; pSid
0x180092593  mov     r8d, [r15+r8*8+10h]; AccessMask
0x180092598  call    cs:__imp_AddAccessAllowedAce
0x18009259f  nop     dword ptr [rax+rax+00h]
0x1800925a4  test    eax, eax
0x1800925a6  jz      loc_1800926B1
0x1800925ac  mov     rcx, [rsp+2A0h+pAcl]; pAcl
0x1800925b1  lea     r8, [rsp+2A0h+pAce]; pAce
0x1800925b6  mov     edx, ebx; dwAceIndex
0x1800925b8  mov     [rsp+2A0h+pAce], 0
0x1800925c1  call    cs:__imp_GetAce
0x1800925c8  nop     dword ptr [rax+rax+00h]
0x1800925cd  test    eax, eax
0x1800925cf  jz      loc_1800926B1
0x1800925d5  mov     rax, [rsp+2A0h+pAce]
0x1800925da  inc     ebx
0x1800925dc  mov     byte ptr [rax+1], 3
0x1800925e0  jmp     short loc_180092576
0x1800925e2  xor     eax, eax
0x1800925e4  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800925e9  xorps   xmm0, xmm0
0x1800925ec  mov     [rsp+2A0h+var_250], rax
0x1800925f1  movups  [rsp+2A0h+pSecurityDescriptor], xmm0
0x1800925f6  lea     edx, [rax+1]; dwRevision
0x1800925f9  movups  [rsp+2A0h+var_260], xmm0
0x1800925fe  call    cs:__imp_InitializeSecurityDescriptor
0x180092605  nop     dword ptr [rax+rax+00h]
0x18009260a  test    eax, eax
0x18009260c  jz      loc_1800926B1
0x180092612  mov     r8, [rsp+2A0h+pAcl]; pDacl
0x180092617  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18009261c  xor     r9d, r9d; bDaclDefaulted
0x18009261f  lea     edx, [r9+1]; bDaclPresent
0x180092623  call    cs:__imp_SetSecurityDescriptorDacl
0x18009262a  nop     dword ptr [rax+rax+00h]
0x18009262f  test    eax, eax
0x180092631  jz      short loc_1800926B1
0x180092633  xor     r8d, r8d; bOwnerDefaulted
0x180092636  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18009263b  mov     rdx, r12; pOwner
0x18009263e  call    cs:__imp_SetSecurityDescriptorOwner
0x180092645  nop     dword ptr [rax+rax+00h]
0x18009264a  test    eax, eax
0x18009264c  jz      short loc_1800926B1
0x18009264e  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180092653  mov     byte ptr [rdi+19h], 0
0x180092657  call    cs:__imp_GetSecurityDescriptorLength
0x18009265e  nop     dword ptr [rax+rax+00h]
0x180092663  mov     edx, eax; dwBytes
0x180092665  xor     ecx, ecx; uFlags
0x180092667  mov     [rsp+2A0h+dwBufferLength], edx
0x18009266b  call    cs:__imp_GlobalAlloc
0x180092672  nop     dword ptr [rax+rax+00h]
0x180092677  mov     [rdi+8], rax
0x18009267b  test    rax, rax
0x18009267e  jz      short loc_1800926B1
0x180092680  lea     r8, [rsp+2A0h+dwBufferLength]; lpdwBufferLength
0x180092685  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x180092688  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18009268d  call    cs:__imp_MakeSelfRelativeSD
0x180092694  nop     dword ptr [rax+rax+00h]
0x180092699  mov     rcx, [rdi+8]; pSecurityDescriptor
0x18009269d  call    cs:__imp_IsValidSecurityDescriptor
0x1800926a4  nop     dword ptr [rax+rax+00h]
0x1800926a9  test    eax, eax
0x1800926ab  setnz   al
0x1800926ae  mov     [rdi+19h], al
0x1800926b1  cmp     [rsp+2A0h+var_238], esi
0x1800926b5  jle     short loc_1800926C8
0x1800926b7  mov     rcx, [rsp+2A0h+pAcl]; hMem
0x1800926bc  call    cs:__imp_GlobalFree
0x1800926c3  nop     dword ptr [rax+rax+00h]
0x1800926c8  mov     rax, rdi
0x1800926cb  mov     rcx, [rbp+1A0h+var_30]
0x1800926d2  xor     rcx, rsp; StackCookie
0x1800926d5  call    __security_check_cookie
0x1800926da  mov     rbx, [rsp+2A0h+arg_10]
0x1800926e2  add     rsp, 280h
0x1800926e9  pop     r15
0x1800926eb  pop     r12
0x1800926ed  pop     rdi
0x1800926ee  pop     rsi
0x1800926ef  pop     rbp
0x1800926f0  retn
```
