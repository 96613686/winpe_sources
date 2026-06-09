# PlaiCreateHostSecurityDescriptor(void *,_ACL *,void * *,void * *)

- ea: `0x18009aef4`
- end: `0x18009b71c`
- name: `?PlaiCreateHostSecurityDescriptor@@YAJPEAXPEAU_ACL@@PEAPEAX2@Z`
- size: `2088`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, PACL pDacl, void **, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180105940`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18002b3a0`
- `0x18009aef4`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b2a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b48e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b2a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b3da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b48e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b6f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b6f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009af4d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009af4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009af3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009af3c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18009b1f2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18009b1f2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18009b32f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18009b32f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18009b3cc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18009b3cc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009b071`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009b152`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009b071`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009b152`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009b46b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18009b46b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009b292`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009b292`

## string_xrefs

- `0x18009aff1`: `PlaiCreateHostSecurityDescriptor`
- `0x18009b5ae`: `PlaiCreateHostSecurityDescriptor`
- `0x18009b695`: `PlaiCreateHostSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall PlaiCreateHostSecurityDescriptor(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        PACL pDacl,
        void **a3,
        void **a4)
{
  PSID *v4; // r14
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  void ***v12; // r9
  void ***v13; // rax
  PSID *v14; // r15
  DWORD v15; // eax
  int v16; // eax
  __int64 v17; // rax
  DWORD v18; // eax
  int v19; // eax
  __int64 v20; // rax
  DWORD v21; // eax
  int v22; // eax
  __int64 v23; // rax
  DWORD v24; // eax
  int v25; // eax
  __int64 v26; // rax
  DWORD v27; // eax
  int v28; // eax
  __int64 v29; // rax
  DWORD v30; // eax
  int v31; // eax
  __int64 v32; // rax
  DWORD v33; // eax
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  void **v40; // [rsp+70h] [rbp-90h] BYREF
  void **v41; // [rsp+78h] [rbp-88h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp-80h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v44[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v45[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v46[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v47[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v48[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v49[64]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v50[64]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v51[64]; // [rsp+410h] [rbp+310h] BYREF
  unsigned __int16 v52[64]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v53[64]; // [rsp+510h] [rbp+410h] BYREF

  v4 = 0;
  v41 = a4;
  TokenInformationLength = 0;
  TokenHandle = 0;
  v40 = a3;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    v9 = PlaiHResultFromWin32(LastError);
    v10 = v9;
    if ( v9 < 0 )
    {
      LODWORD(v40) = 0;
      LODWORD(v41) = v9;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_92;
      }
      PlaiWhoAmI(v44, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v44[v11] );
      v12 = &v41;
      v13 = &v40;
      goto LABEL_91;
    }
  }
  TokenInformationLength = 128;
  v14 = 0;
  do
  {
    if ( v14 )
      PlaiFree(v14, 1);
    v14 = (PSID *)PlaiAlloc(TokenInformationLength, 1, 0, byte_180147320, ReturnLength);
    if ( !v14 )
    {
      v10 = -2147024882;
      LODWORD(v40) = -2147024882;
      LODWORD(v41) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_92;
      }
      PlaiWhoAmI(v53, 0x4000000000000800uLL);
      v37 = -1;
      do
        ++v37;
      while ( v53[v37] );
      v12 = &v40;
      v13 = &v41;
LABEL_91:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v12, 4, byte_180147320, 1, v13, 4);
      goto LABEL_92;
    }
    if ( GetTokenInformation(TokenHandle, TokenOwner, v14, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_22;
    v15 = GetLastError();
    v16 = PlaiHResultFromWin32(v15);
    v10 = v16;
  }
  while ( v16 == -2147024774 );
  if ( v16 < 0 )
  {
    LODWORD(v40) = v16;
    LODWORD(v41) = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v45, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v45[v17] );
      goto LABEL_82;
    }
    goto LABEL_83;
  }
LABEL_22:
  TokenInformationLength = 128;
  while ( 2 )
  {
    if ( v4 )
      PlaiFree(v4, 1);
    v4 = (PSID *)PlaiAlloc(TokenInformationLength, 1, 0, byte_180147320, ReturnLength);
    if ( !v4 )
    {
      v10 = -2147024882;
      LODWORD(v41) = 0;
      LODWORD(v40) = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_83;
      }
      PlaiWhoAmI(v52, 0x4000000000000800uLL);
      v36 = -1;
      do
        ++v36;
      while ( v52[v36] );
      goto LABEL_82;
    }
    if ( GetTokenInformation(TokenHandle, TokenPrimaryGroup, v4, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_35;
    v18 = GetLastError();
    v19 = PlaiHResultFromWin32(v18);
    v10 = v19;
    if ( v19 == -2147024774 )
      continue;
    break;
  }
  if ( v19 >= 0 )
  {
LABEL_35:
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      v21 = GetLastError();
      v22 = PlaiHResultFromWin32(v21);
      v10 = v22;
      if ( v22 < 0 )
      {
        LODWORD(v40) = v22;
        LODWORD(v41) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_83;
        }
        PlaiWhoAmI(v47, 0x4000000000000800uLL);
        v23 = -1;
        do
          ++v23;
        while ( v47[v23] );
        goto LABEL_82;
      }
    }
    if ( !InitializeAcl(pDacl, 8u, 2u) )
    {
      v24 = GetLastError();
      v25 = PlaiHResultFromWin32(v24);
      v10 = v25;
      if ( v25 < 0 )
      {
        LODWORD(v40) = v25;
        LODWORD(v41) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_83;
        }
        PlaiWhoAmI(v48, 0x4000000000000800uLL);
        v26 = -1;
        do
          ++v26;
        while ( v48[v26] );
        goto LABEL_82;
      }
    }
    if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, *v14, 0) )
    {
      v27 = GetLastError();
      v28 = PlaiHResultFromWin32(v27);
      v10 = v28;
      if ( v28 < 0 )
      {
        LODWORD(v40) = v28;
        LODWORD(v41) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_83;
        }
        PlaiWhoAmI(v49, 0x4000000000000800uLL);
        v29 = -1;
        do
          ++v29;
        while ( v49[v29] );
        goto LABEL_82;
      }
    }
    if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, *v4, 0) )
    {
      v30 = GetLastError();
      v31 = PlaiHResultFromWin32(v30);
      v10 = v31;
      if ( v31 < 0 )
      {
        LODWORD(v40) = v31;
        LODWORD(v41) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_83;
        }
        PlaiWhoAmI(v50, 0x4000000000000800uLL);
        v32 = -1;
        do
          ++v32;
        while ( v50[v32] );
        goto LABEL_82;
      }
    }
    if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
    {
      v10 = 0;
LABEL_69:
      *v41 = v4;
      *v40 = v14;
      goto LABEL_92;
    }
    v33 = GetLastError();
    v34 = PlaiHResultFromWin32(v33);
    v10 = v34;
    if ( v34 >= 0 )
      goto LABEL_69;
    LODWORD(v41) = 0;
    LODWORD(v40) = v34;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_83;
    }
    PlaiWhoAmI(v51, 0x4000000000000800uLL);
    v35 = -1;
    do
      ++v35;
    while ( v51[v35] );
LABEL_82:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v40, 4, byte_180147320, 1, &v41, 4);
    goto LABEL_83;
  }
  LODWORD(v40) = v19;
  LODWORD(v41) = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v46, 0x4000000000000800uLL);
    v20 = -1;
    do
      ++v20;
    while ( v46[v20] );
    goto LABEL_82;
  }
LABEL_83:
  PlaiFree(v14, 1);
  if ( v4 )
    PlaiFree(v4, 1);
LABEL_92:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v10;
}

```

## disassembly

```asm
0x18009aef4  push    rbp
0x18009aef6  push    rbx
0x18009aef7  push    rsi
0x18009aef8  push    rdi
0x18009aef9  push    r12
0x18009aefb  push    r13
0x18009aefd  push    r14
0x18009aeff  push    r15
0x18009af01  lea     rbp, [rsp-4A8h]
0x18009af09  sub     rsp, 5A8h
0x18009af10  mov     rax, cs:__security_cookie
0x18009af17  xor     rax, rsp
0x18009af1a  mov     [rbp+4E0h+var_50], rax
0x18009af21  xor     r14d, r14d
0x18009af24  mov     [rsp+5E0h+var_568], r9
0x18009af29  mov     [rbp+4E0h+TokenInformationLength], r14d
0x18009af2d  mov     r13, rdx
0x18009af30  mov     [rbp+4E0h+TokenHandle], r14
0x18009af34  mov     rsi, rcx
0x18009af37  mov     [rsp+5E0h+var_570], r8
0x18009af3c  call    cs:__imp_GetCurrentProcess
0x18009af42  mov     rcx, rax; ProcessHandle
0x18009af45  lea     r8, [rbp+4E0h+TokenHandle]; TokenHandle
0x18009af49  lea     edx, [r14+8]; DesiredAccess
0x18009af4d  call    cs:__imp_OpenProcessToken
0x18009af53  test    eax, eax
0x18009af55  jnz     loc_18009B015
0x18009af5b  call    cs:__imp_GetLastError
0x18009af61  mov     ecx, eax; unsigned int
0x18009af63  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18009af68  mov     ebx, eax
0x18009af6a  test    eax, eax
0x18009af6c  jns     loc_18009B015
0x18009af72  cmp     dword ptr cs:xmmword_180169738, r14d
0x18009af79  mov     dword ptr [rsp+5E0h+var_570], r14d
0x18009af7e  mov     dword ptr [rsp+5E0h+var_568], eax
0x18009af82  jz      loc_18009B6E8
0x18009af88  mov     rdx, 4000000000000800h; unsigned __int64
0x18009af92  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009af99  jz      loc_18009B6E8
0x18009af9f  mov     rax, cs:qword_180169748
0x18009afa6  and     rax, rdx
0x18009afa9  cmp     cs:qword_180169748, rax
0x18009afb0  jnz     loc_18009B6E8
0x18009afb6  lea     rcx, [rbp+4E0h+var_550]; unsigned __int16 *
0x18009afba  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009afbf  lea     rcx, [rbp+4E0h+var_550]
0x18009afc3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009afc7  inc     rax
0x18009afca  cmp     [rcx+rax*2], r14w
0x18009afcf  jnz     short loc_18009AFC7
0x18009afd1  lea     ecx, [rax+rax]
0x18009afd4  mov     r12d, 4
0x18009afda  lea     rax, [rbp+4E0h+var_550]
0x18009afde  add     rcx, 2
0x18009afe2  mov     [rsp+5E0h+var_580], rcx
0x18009afe7  lea     r9, [rsp+5E0h+var_568]
0x18009afec  mov     [rsp+5E0h+var_588], rax
0x18009aff1  lea     rax, aPlaicreatehost; "PlaiCreateHostSecurityDescriptor"
0x18009aff8  mov     [rsp+5E0h+var_590], 21h ; '!'
0x18009b001  lea     edi, [r12-3]
0x18009b006  mov     [rsp+5E0h+var_598], rax
0x18009b00b  lea     rax, [rsp+5E0h+var_570]
0x18009b010  jmp     loc_18009B6AF
0x18009b015  mov     edi, 1
0x18009b01a  mov     [rbp+4E0h+TokenInformationLength], 80h
0x18009b021  mov     r15, r14
0x18009b024  lea     r12d, [rdi+3]
0x18009b028  lea     rbx, byte_180147320
0x18009b02f  test    r15, r15
0x18009b032  jz      short loc_18009B03E
0x18009b034  mov     edx, edi; int
0x18009b036  mov     rcx, r15; lpMem
0x18009b039  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18009b03e  mov     ecx, [rbp+4E0h+TokenInformationLength]; dwBytes
0x18009b041  mov     r9, rbx; char *
0x18009b044  xor     r8d, r8d; int
0x18009b047  mov     edx, edi; int
0x18009b049  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18009b04e  mov     r15, rax
0x18009b051  test    rax, rax
0x18009b054  jz      loc_18009B60C
0x18009b05a  mov     r9d, [rbp+4E0h+TokenInformationLength]; TokenInformationLength
0x18009b05e  lea     rax, [rbp+4E0h+TokenInformationLength]
0x18009b062  mov     rcx, [rbp+4E0h+TokenHandle]; TokenHandle
0x18009b066  mov     r8, r15; TokenInformation
0x18009b069  mov     edx, r12d; TokenInformationClass
0x18009b06c  mov     [rsp+5E0h+ReturnLength], rax; int
0x18009b071  call    cs:__imp_GetTokenInformation
0x18009b077  test    eax, eax
0x18009b079  jnz     loc_18009B103
0x18009b07f  call    cs:__imp_GetLastError
0x18009b085  mov     ecx, eax; unsigned int
0x18009b087  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18009b08c  mov     ebx, eax
0x18009b08e  cmp     eax, 8007007Ah
0x18009b093  jz      short loc_18009B028
0x18009b095  test    eax, eax
0x18009b097  jns     short loc_18009B103
0x18009b099  xor     esi, esi
0x18009b09b  mov     dword ptr [rsp+5E0h+var_570], eax
0x18009b09f  cmp     dword ptr cs:xmmword_180169738, esi
0x18009b0a5  mov     dword ptr [rsp+5E0h+var_568], esi
0x18009b0a9  jz      loc_18009B5EA
0x18009b0af  mov     rdx, 4000000000000800h; unsigned __int64
0x18009b0b9  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009b0c0  jz      loc_18009B5EA
0x18009b0c6  mov     rax, cs:qword_180169748
0x18009b0cd  and     rax, rdx
0x18009b0d0  cmp     cs:qword_180169748, rax
0x18009b0d7  jnz     loc_18009B5EA
0x18009b0dd  lea     rcx, [rbp+4E0h+var_4D0]; unsigned __int16 *
0x18009b0e1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009b0e6  lea     rcx, [rbp+4E0h+var_4D0]
0x18009b0ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009b0ee  inc     rax
0x18009b0f1  cmp     [rcx+rax*2], si
0x18009b0f5  jnz     short loc_18009B0EE
0x18009b0f7  lea     ecx, [rax+rax]
0x18009b0fa  lea     rax, [rbp+4E0h+var_4D0]
0x18009b0fe  jmp     loc_18009B584
0x18009b103  mov     [rbp+4E0h+TokenInformationLength], 80h
0x18009b10a  test    r14, r14
0x18009b10d  jz      short loc_18009B119
0x18009b10f  mov     edx, edi; int
0x18009b111  mov     rcx, r14; lpMem
0x18009b114  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18009b119  mov     ecx, [rbp+4E0h+TokenInformationLength]; dwBytes
0x18009b11c  lea     r9, byte_180147320; char *
0x18009b123  xor     r8d, r8d; int
0x18009b126  mov     edx, edi; int
0x18009b128  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18009b12d  mov     r14, rax
0x18009b130  test    rax, rax
0x18009b133  jz      loc_18009B50F
0x18009b139  mov     r9d, [rbp+4E0h+TokenInformationLength]; TokenInformationLength
0x18009b13d  lea     rax, [rbp+4E0h+TokenInformationLength]
0x18009b141  mov     rcx, [rbp+4E0h+TokenHandle]; TokenHandle
0x18009b145  mov     r8, r14; TokenInformation
0x18009b148  mov     edx, 5; TokenInformationClass
0x18009b14d  mov     [rsp+5E0h+ReturnLength], rax; ReturnLength
0x18009b152  call    cs:__imp_GetTokenInformation
0x18009b158  test    eax, eax
0x18009b15a  jnz     loc_18009B1ED
0x18009b160  call    cs:__imp_GetLastError
0x18009b166  mov     ecx, eax; unsigned int
0x18009b168  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18009b16d  mov     ebx, eax
0x18009b16f  cmp     eax, 8007007Ah
0x18009b174  jz      short loc_18009B10A
0x18009b176  test    eax, eax
0x18009b178  jns     short loc_18009B1ED
0x18009b17a  xor     esi, esi
0x18009b17c  mov     dword ptr [rsp+5E0h+var_570], eax
0x18009b180  cmp     dword ptr cs:xmmword_180169738, esi
0x18009b186  mov     dword ptr [rsp+5E0h+var_568], esi
0x18009b18a  jz      loc_18009B5EA
0x18009b190  mov     rdx, 4000000000000800h; unsigned __int64
0x18009b19a  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009b1a1  jz      loc_18009B5EA
0x18009b1a7  mov     rax, cs:qword_180169748
0x18009b1ae  and     rax, rdx
0x18009b1b1  cmp     cs:qword_180169748, rax
0x18009b1b8  jnz     loc_18009B5EA
0x18009b1be  lea     rcx, [rbp+4E0h+var_450]; unsigned __int16 *
0x18009b1c5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009b1ca  lea     rcx, [rbp+4E0h+var_450]
0x18009b1d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009b1d5  inc     rax
0x18009b1d8  cmp     [rcx+rax*2], si
0x18009b1dc  jnz     short loc_18009B1D5
0x18009b1de  lea     ecx, [rax+rax]
0x18009b1e1  lea     rax, [rbp+4E0h+var_450]
0x18009b1e8  jmp     loc_18009B584
0x18009b1ed  mov     edx, edi; dwRevision
0x18009b1ef  mov     rcx, rsi; pSecurityDescriptor
0x18009b1f2  call    cs:__imp_InitializeSecurityDescriptor
0x18009b1f8  test    eax, eax
0x18009b1fa  jnz     loc_18009B286
0x18009b200  call    cs:__imp_GetLastError
0x18009b206  mov     ecx, eax; unsigned int
0x18009b208  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18009b20d  mov     ebx, eax
0x18009b20f  test    eax, eax
0x18009b211  jns     short loc_18009B286
0x18009b213  xor     esi, esi
0x18009b215  mov     dword ptr [rsp+5E0h+var_570], eax
0x18009b219  cmp     dword ptr cs:xmmword_180169738, esi
0x18009b21f  mov     dword ptr [rsp+5E0h+var_568], esi
0x18009b223  jz      loc_18009B5EA
0x18009b229  mov     rdx, 4000000000000800h; unsigned __int64
0x18009b233  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009b23a  jz      loc_18009B5EA
0x18009b240  mov     rax, cs:qword_180169748
0x18009b247  and     rax, rdx
0x18009b24a  cmp     cs:qword_180169748, rax
0x18009b251  jnz     loc_18009B5EA
0x18009b257  lea     rcx, [rbp+4E0h+var_3D0]; unsigned __int16 *
0x18009b25e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009b263  lea     rcx, [rbp+4E0h+var_3D0]
0x18009b26a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009b26e  inc     rax
0x18009b271  cmp     [rcx+rax*2], si
0x18009b275  jnz     short loc_18009B26E
0x18009b277  lea     ecx, [rax+rax]
0x18009b27a  lea     rax, [rbp+4E0h+var_3D0]
0x18009b281  jmp     loc_18009B584
0x18009b286  mov     edx, 8; nAclLength
0x18009b28b  mov     rcx, r13; pAcl
0x18009b28e  lea     r8d, [rdx-6]; dwAclRevision
0x18009b292  call    cs:__imp_InitializeAcl
0x18009b298  test    eax, eax
0x18009b29a  jnz     loc_18009B326
0x18009b2a0  call    cs:__imp_GetLastError
0x18009b2a6  mov     ecx, eax; unsigned int
0x18009b2a8  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18009b2ad  mov     ebx, eax
0x18009b2af  test    eax, eax
0x18009b2b1  jns     short loc_18009B326
0x18009b2b3  xor     esi, esi
0x18009b2b5  mov     dword ptr [rsp+5E0h+var_570], eax
0x18009b2b9  cmp     dword ptr cs:xmmword_180169738, esi
0x18009b2bf  mov     dword ptr [rsp+5E0h+var_568], esi
0x18009b2c3  jz      loc_18009B5EA
0x18009b2c9  mov     rdx, 4000000000000800h; unsigned __int64
0x18009b2d3  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009b2da  jz      loc_18009B5EA
0x18009b2e0  mov     rax, cs:qword_180169748
0x18009b2e7  and     rax, rdx
0x18009b2ea  cmp     cs:qword_180169748, rax
0x18009b2f1  jnz     loc_18009B5EA
0x18009b2f7  lea     rcx, [rbp+4E0h+var_350]; unsigned __int16 *
0x18009b2fe  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009b303  lea     rcx, [rbp+4E0h+var_350]
0x18009b30a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009b30e  inc     rax
0x18009b311  cmp     [rcx+rax*2], si
0x18009b315  jnz     short loc_18009B30E
0x18009b317  lea     ecx, [rax+rax]
0x18009b31a  lea     rax, [rbp+4E0h+var_350]
0x18009b321  jmp     loc_18009B584
0x18009b326  mov     rdx, [r15]; pOwner
0x18009b329  xor     r8d, r8d; bOwnerDefaulted
0x18009b32c  mov     rcx, rsi; pSecurityDescriptor
0x18009b32f  call    cs:__imp_SetSecurityDescriptorOwner
0x18009b335  test    eax, eax
0x18009b337  jnz     loc_18009B3C3
0x18009b33d  call    cs:__imp_GetLastError
0x18009b343  mov     ecx, eax; unsigned int
0x18009b345  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18009b34a  mov     ebx, eax
0x18009b34c  test    eax, eax
0x18009b34e  jns     short loc_18009B3C3
0x18009b350  xor     esi, esi
0x18009b352  mov     dword ptr [rsp+5E0h+var_570], eax
0x18009b356  cmp     dword ptr cs:xmmword_180169738, esi
0x18009b35c  mov     dword ptr [rsp+5E0h+var_568], esi
0x18009b360  jz      loc_18009B5EA
0x18009b366  mov     rdx, 4000000000000800h; unsigned __int64
0x18009b370  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009b377  jz      loc_18009B5EA
0x18009b37d  mov     rax, cs:qword_180169748
0x18009b384  and     rax, rdx
0x18009b387  cmp     cs:qword_180169748, rax
0x18009b38e  jnz     loc_18009B5EA
0x18009b394  lea     rcx, [rbp+4E0h+var_2D0]; unsigned __int16 *
0x18009b39b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009b3a0  lea     rcx, [rbp+4E0h+var_2D0]
0x18009b3a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009b3ab  inc     rax
0x18009b3ae  cmp     [rcx+rax*2], si
0x18009b3b2  jnz     short loc_18009B3AB
0x18009b3b4  lea     ecx, [rax+rax]
0x18009b3b7  lea     rax, [rbp+4E0h+var_2D0]
0x18009b3be  jmp     loc_18009B584
0x18009b3c3  mov     rdx, [r14]; pGroup
0x18009b3c6  xor     r8d, r8d; bGroupDefaulted
0x18009b3c9  mov     rcx, rsi; pSecurityDescriptor
0x18009b3cc  call    cs:__imp_SetSecurityDescriptorGroup
0x18009b3d2  test    eax, eax
0x18009b3d4  jnz     loc_18009B460
0x18009b3da  call    cs:__imp_GetLastError
0x18009b3e0  mov     ecx, eax; unsigned int
0x18009b3e2  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18009b3e7  mov     ebx, eax
0x18009b3e9  test    eax, eax
0x18009b3eb  jns     short loc_18009B460
0x18009b3ed  xor     esi, esi
0x18009b3ef  mov     dword ptr [rsp+5E0h+var_570], eax
0x18009b3f3  cmp     dword ptr cs:xmmword_180169738, esi
0x18009b3f9  mov     dword ptr [rsp+5E0h+var_568], esi
0x18009b3fd  jz      loc_18009B5EA
0x18009b403  mov     rdx, 4000000000000800h; unsigned __int64
0x18009b40d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009b414  jz      loc_18009B5EA
0x18009b41a  mov     rax, cs:qword_180169748
0x18009b421  and     rax, rdx
0x18009b424  cmp     cs:qword_180169748, rax
0x18009b42b  jnz     loc_18009B5EA
0x18009b431  lea     rcx, [rbp+4E0h+var_250]; unsigned __int16 *
  ... truncated ...
```
