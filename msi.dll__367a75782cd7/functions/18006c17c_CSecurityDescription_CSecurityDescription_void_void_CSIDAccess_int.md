# CSecurityDescription::CSecurityDescription(void *,void *,CSIDAccess *,int)

- ea: `0x18006c17c`
- end: `0x18006c369`
- name: `??0CSecurityDescription@@QEAA@PEAX0PEAUCSIDAccess@@H@Z`
- size: `493`
- prototype: `CSecurityDescription *__fastcall(CSecurityDescription *this, void *, void *, PSID *, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006bd18`
- `0x18006cc60`
- `0x180147e4c`
- `0x1801dda2c`
- `0x18020614c`

## callees

- `0x18006c17c`
- `0x1800a242c`
- `0x180144e34`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x18006c21e`
- `ADVAPI32!InitializeAcl` at `0x18006c21e`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18006c321`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18006c321`
- `ADVAPI32!GetLengthSid` at `0x18006c1d1`
- `ADVAPI32!GetLengthSid` at `0x18006c1d1`
- `ADVAPI32!AddAccessAllowedAce` at `0x18006c250`
- `ADVAPI32!AddAccessAllowedAce` at `0x18006c250`
- `ADVAPI32!GetAce` at `0x18006c273`
- `ADVAPI32!GetAce` at `0x18006c273`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18006c2aa`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18006c2aa`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18006c2c5`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18006c2c5`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18006c2da`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18006c2da`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18006c2ed`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18006c2ed`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18006c317`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18006c317`
- `KERNEL32!GlobalAlloc` at `0x18006c2fb`
- `KERNEL32!GlobalAlloc` at `0x18006c2fb`
- `KERNEL32!GlobalFree` at `0x18006c33a`
- `KERNEL32!GlobalFree` at `0x18006c33a`

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
0x18006c17c  mov     [rsp-8+arg_10], rbx
0x18006c181  push    rbp
0x18006c182  push    rsi
0x18006c183  push    rdi
0x18006c184  push    r12
0x18006c186  push    r15
0x18006c188  lea     rbp, [rsp-180h]
0x18006c190  sub     rsp, 280h
0x18006c197  mov     rax, cs:__security_cookie
0x18006c19e  xor     rax, rsp
0x18006c1a1  mov     [rbp+1A0h+var_30], rax
0x18006c1a8  mov     r15, r9
0x18006c1ab  mov     r12, rdx
0x18006c1ae  mov     rdi, rcx
0x18006c1b1  call    ?Initialize@CSecurityDescription@@IEAAXXZ; CSecurityDescription::Initialize(void)
0x18006c1b6  xor     esi, esi
0x18006c1b8  mov     byte ptr [rdi+19h], 0
0x18006c1bc  mov     ebx, 8
0x18006c1c1  cmp     [rbp+1A0h+arg_20], esi
0x18006c1c7  jle     short loc_18006C1E6
0x18006c1c9  lea     rcx, [rsi+rsi*2]
0x18006c1cd  mov     rcx, [r15+rcx*8]; pSid
0x18006c1d1  call    cs:__imp_GetLengthSid
0x18006c1d7  add     ebx, 8
0x18006c1da  inc     esi
0x18006c1dc  add     ebx, eax
0x18006c1de  cmp     esi, [rbp+1A0h+arg_20]
0x18006c1e4  jl      short loc_18006C1C9
0x18006c1e6  mov     esi, 200h
0x18006c1eb  lea     rcx, [rsp+2A0h+var_230]
0x18006c1f0  mov     [rsp+2A0h+var_238], esi
0x18006c1f4  mov     [rsp+2A0h+pAcl], rcx
0x18006c1f9  cmp     ebx, esi
0x18006c1fb  jle     short loc_18006C216
0x18006c1fd  mov     edx, ebx
0x18006c1ff  lea     rcx, [rsp+2A0h+pAcl]
0x18006c204  call    ?SetSize@?$CAPITempBuffer@D$0CAA@@@QEAA_NH_N@Z; CAPITempBuffer<char,512>::SetSize(int,bool)
0x18006c209  test    al, al
0x18006c20b  jz      loc_18006C32F
0x18006c211  mov     rcx, [rsp+2A0h+pAcl]; pAcl
0x18006c216  mov     r8d, 2; dwAclRevision
0x18006c21c  mov     edx, ebx; nAclLength
0x18006c21e  call    cs:__imp_InitializeAcl
0x18006c224  test    eax, eax
0x18006c226  jz      loc_18006C32F
0x18006c22c  xor     ebx, ebx
0x18006c22e  cmp     ebx, [rbp+1A0h+arg_20]
0x18006c234  jge     short loc_18006C28E
0x18006c236  mov     rcx, [rsp+2A0h+pAcl]; pAcl
0x18006c23b  mov     edx, 2; dwAceRevision
0x18006c240  movsxd  rax, ebx
0x18006c243  lea     r8, [rax+rax*2]
0x18006c247  mov     r9, [r15+r8*8]; pSid
0x18006c24b  mov     r8d, [r15+r8*8+10h]; AccessMask
0x18006c250  call    cs:__imp_AddAccessAllowedAce
0x18006c256  test    eax, eax
0x18006c258  jz      loc_18006C32F
0x18006c25e  mov     rcx, [rsp+2A0h+pAcl]; pAcl
0x18006c263  lea     r8, [rsp+2A0h+pAce]; pAce
0x18006c268  mov     edx, ebx; dwAceIndex
0x18006c26a  mov     [rsp+2A0h+pAce], 0
0x18006c273  call    cs:__imp_GetAce
0x18006c279  test    eax, eax
0x18006c27b  jz      loc_18006C32F
0x18006c281  mov     rax, [rsp+2A0h+pAce]
0x18006c286  inc     ebx
0x18006c288  mov     byte ptr [rax+1], 3
0x18006c28c  jmp     short loc_18006C22E
0x18006c28e  xor     eax, eax
0x18006c290  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18006c295  xorps   xmm0, xmm0
0x18006c298  mov     [rsp+2A0h+var_250], rax
0x18006c29d  movups  [rsp+2A0h+pSecurityDescriptor], xmm0
0x18006c2a2  lea     edx, [rax+1]; dwRevision
0x18006c2a5  movups  [rsp+2A0h+var_260], xmm0
0x18006c2aa  call    cs:__imp_InitializeSecurityDescriptor
0x18006c2b0  test    eax, eax
0x18006c2b2  jz      short loc_18006C32F
0x18006c2b4  mov     r8, [rsp+2A0h+pAcl]; pDacl
0x18006c2b9  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18006c2be  xor     r9d, r9d; bDaclDefaulted
0x18006c2c1  lea     edx, [r9+1]; bDaclPresent
0x18006c2c5  call    cs:__imp_SetSecurityDescriptorDacl
0x18006c2cb  test    eax, eax
0x18006c2cd  jz      short loc_18006C32F
0x18006c2cf  xor     r8d, r8d; bOwnerDefaulted
0x18006c2d2  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18006c2d7  mov     rdx, r12; pOwner
0x18006c2da  call    cs:__imp_SetSecurityDescriptorOwner
0x18006c2e0  test    eax, eax
0x18006c2e2  jz      short loc_18006C32F
0x18006c2e4  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pSecurityDescriptor
0x18006c2e9  mov     byte ptr [rdi+19h], 0
0x18006c2ed  call    cs:__imp_GetSecurityDescriptorLength
0x18006c2f3  mov     edx, eax; dwBytes
0x18006c2f5  xor     ecx, ecx; uFlags
0x18006c2f7  mov     [rsp+2A0h+dwBufferLength], edx
0x18006c2fb  call    cs:__imp_GlobalAlloc
0x18006c301  mov     [rdi+8], rax
0x18006c305  test    rax, rax
0x18006c308  jz      short loc_18006C32F
0x18006c30a  lea     r8, [rsp+2A0h+dwBufferLength]; lpdwBufferLength
0x18006c30f  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18006c312  lea     rcx, [rsp+2A0h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18006c317  call    cs:__imp_MakeSelfRelativeSD
0x18006c31d  mov     rcx, [rdi+8]; pSecurityDescriptor
0x18006c321  call    cs:__imp_IsValidSecurityDescriptor
0x18006c327  test    eax, eax
0x18006c329  setnz   al
0x18006c32c  mov     [rdi+19h], al
0x18006c32f  cmp     [rsp+2A0h+var_238], esi
0x18006c333  jle     short loc_18006C340
0x18006c335  mov     rcx, [rsp+2A0h+pAcl]; hMem
0x18006c33a  call    cs:__imp_GlobalFree
0x18006c340  mov     rax, rdi
0x18006c343  mov     rcx, [rbp+1A0h+var_30]
0x18006c34a  xor     rcx, rsp; StackCookie
0x18006c34d  call    __security_check_cookie
0x18006c352  mov     rbx, [rsp+2A0h+arg_10]
0x18006c35a  add     rsp, 280h
0x18006c361  pop     r15
0x18006c363  pop     r12
0x18006c365  pop     rdi
0x18006c366  pop     rsi
0x18006c367  pop     rbp
0x18006c368  retn
```
