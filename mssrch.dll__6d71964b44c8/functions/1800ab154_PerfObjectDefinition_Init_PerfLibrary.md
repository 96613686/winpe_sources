# PerfObjectDefinition::Init(PerfLibrary *)

- ea: `0x1800ab154`
- end: `0x1800ab768`
- name: `?Init@PerfObjectDefinition@@AEAAHPEAVPerfLibrary@@@Z`
- size: `1556`
- prototype: `__int64 __fastcall(wchar_t *this, struct PerfLibrary *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180149770`

## callees

- `0x1800269b0`
- `0x1800ab154`
- `0x1800ab770`
- `0x1800ac8b4`
- `0x1800ac938`
- `0x1800ac99c`
- `0x1800ad2a0`
- `0x1800ad360`
- `0x1800d6f20`
- `0x18010110c`
- `0x180102570`
- `0x1801244c0`
- `0x1801249b0`
- `0x180124d00`
- `0x18012540e`
- `0x1801496e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab4e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab4e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab4f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab56e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab4f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab56e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800ab48f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800ab48f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800ab555`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800ab555`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ab288`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ab302`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ab288`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ab302`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ab266`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ab2d7`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ab266`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ab2d7`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ab249`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ab2ba`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ab249`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ab2ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall PerfObjectDefinition::Init(wchar_t *this, struct PerfLibrary *a2)
{
  unsigned int v3; // r8d
  unsigned int v4; // r12d
  __int64 v5; // r9
  int i; // edx
  int v7; // r13d
  unsigned int v8; // r13d
  void *v9; // rsi
  unsigned __int64 SidLengthRequired; // rcx
  void *v11; // rbx
  DWORD v12; // edi
  void *v13; // rdi
  unsigned __int64 v14; // rcx
  void *v15; // rbx
  __int64 v16; // r8
  __int64 v17; // r12
  DWORD v18; // edi
  __int64 v19; // r8
  void *v20; // rbx
  int v21; // edx
  int v22; // r9d
  DWORD dwMaximumSizeLow; // r13d
  int v25; // edi
  HANDLE v26; // rax
  DWORD LastError; // eax
  void *v28; // rcx
  void *v29; // rax
  unsigned int *v30; // rcx
  struct PerfLibrary *v31; // r11
  unsigned int j; // r10d
  int v33; // r10d
  int v34; // [rsp+30h] [rbp-178h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-170h] BYREF
  void *v36; // [rsp+40h] [rbp-168h] BYREF
  void *v37; // [rsp+48h] [rbp-160h] BYREF
  void *v38; // [rsp+50h] [rbp-158h] BYREF
  void *Block; // [rsp+58h] [rbp-150h] BYREF
  struct PerfLibrary *v40; // [rsp+60h] [rbp-148h]
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+68h] [rbp-140h] BYREF
  _BYTE pSecurityDescriptor[80]; // [rsp+80h] [rbp-128h] BYREF
  const int *v43; // [rsp+D0h] [rbp-D8h] BYREF
  LPCWSTR lpName; // [rsp+D8h] [rbp-D0h]
  __int64 v45; // [rsp+E0h] [rbp-C8h]
  __int16 v46; // [rsp+E8h] [rbp-C0h] BYREF

  v40 = a2;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  v3 = *((_DWORD *)this + 138);
  v4 = 40 * v3 + 64;
  v35 = v4;
  *((_DWORD *)this + 139) = 40 * v3 + 72;
  *((_DWORD *)this + 140) = 8;
  v5 = 0;
  for ( i = 8; (unsigned int)v5 < v3; v5 = (unsigned int)(v5 + 1) )
  {
    i += 8 * (((unsigned __int64)*(unsigned int *)(*(_QWORD *)&this[4 * v5 + 20] + 28LL) + 7) >> 3);
    *((_DWORD *)this + 140) = i;
  }
  v7 = *((_DWORD *)this + 9);
  if ( v7 == -1 )
  {
    v8 = i + v4;
  }
  else
  {
    *((_DWORD *)this + 141) = i + 92;
    v8 = v4 + (i + 92) * v7;
  }
  Block = 0;
  SecUtil::CACL::Reset((SecUtil::CACL *)&Block);
  SecUtil::CSecurityDescriptor::CSecurityDescriptor(pSecurityDescriptor);
  SecUtil::CSecurityDescriptor::InitializeFromThread(pSecurityDescriptor);
  v9 = 0;
  v38 = 0;
  v36 = 0;
  SidLengthRequired = GetSidLengthRequired(1u);
  v11 = operator new[](SidLengthRequired);
  if ( InitializeSid(v11, (PSID_IDENTIFIER_AUTHORITY)SecUtil::CSID_NetworkServiceAccount::s_sia.SubAuthority, 1u) )
  {
    v12 = SecUtil::CSID_SystemAccount::s_rgSubAuth;
    *GetSidSubAuthority(v11, 0) = v12;
    v36 = 0;
    v9 = v11;
    v38 = v11;
    TPointer<unsigned char>::~TPointer<unsigned char>(&v36);
  }
  else
  {
    operator delete(v11);
  }
  v13 = 0;
  v36 = 0;
  v37 = 0;
  v14 = GetSidLengthRequired(2u);
  v15 = operator new[](v14);
  if ( InitializeSid(v15, (PSID_IDENTIFIER_AUTHORITY)SecUtil::CSID_EveryoneAccount::s_sia.SubAuthority, 2u) )
  {
    v17 = 0;
    do
    {
      v18 = *(&SecUtil::CSID_AdministratorsGroup::s_rgSubAuth + v17);
      *GetSidSubAuthority(v15, v17) = v18;
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 < 2 );
    v13 = v15;
    v37 = 0;
    v36 = v15;
    TPointer<unsigned char>::~TPointer<unsigned char>(&v37);
    v4 = v35;
  }
  else
  {
    operator delete(v15);
  }
  LOBYTE(v34) = 0;
  v37 = v9;
  SecUtil::CACL::AddAccessXXXAces(&Block, 1, v16, &v37, &v35, &v34, v34, -1072693248, v36);
  LOBYTE(v34) = 0;
  v35 = -1072693248;
  v37 = v13;
  ((void (__fastcall *)(void **, __int64, __int64, void **, unsigned int *, int *))SecUtil::CACL::AddAccessXXXAces)(
    &Block,
    1,
    v19,
    &v37,
    &v35,
    &v34);
  v20 = Block;
  SecUtil::CSecurityDescriptor::SetDacl(
    (SecUtil::CSecurityDescriptor *)pSecurityDescriptor,
    v21,
    (struct _ACL *)Block,
    v22);
  FileMappingAttributes.nLength = 24;
  FileMappingAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  FileMappingAttributes.bInheritHandle = 0;
  lpName = (LPCWSTR)&v46;
  v45 = 65;
  v46 = 0;
  v43 = &CCICommonPathString::`vftable';
  if ( (int)PerfNameToObjectName(this, (CLMString *)&v43) >= 0 )
  {
    dwMaximumSizeLow = v8 + 8;
    v25 = -1;
    v26 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, dwMaximumSizeLow, lpName);
    *((_QWORD *)this + 71) = v26;
    if ( v26 )
    {
      LastError = GetLastError();
      v28 = (void *)*((_QWORD *)this + 71);
      if ( LastError == 183 )
      {
        CloseHandle(v28);
        *((_QWORD *)this + 71) = 0;
        TLMString<64,64,32767>::~TLMString<64,64,32767>(&v43);
        SecUtil::CSID::~CSID((SecUtil::CSID *)&v36);
        SecUtil::CSID::~CSID((SecUtil::CSID *)&v38);
        SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pSecurityDescriptor);
        operator delete(v20);
        return 0;
      }
      else
      {
        v29 = MapViewOfFile(v28, 2u, 0, 0, 0);
        *((_QWORD *)this + 72) = v29;
        if ( v29 )
        {
          memset_0(v29, 0, dwMaximumSizeLow);
          v30 = (unsigned int *)*((_QWORD *)this + 72);
          *((_QWORD *)this + 73) = v30;
          *((_QWORD *)this + 74) = v30 + 16;
          *((_QWORD *)this + 75) = (char *)v30 + *((unsigned int *)this + 139);
          *v30 = v4;
          *(_DWORD *)(*((_QWORD *)this + 73) + 4LL) = v4;
          *(_DWORD *)(*((_QWORD *)this + 73) + 8LL) = 64;
          v31 = v40;
          *(_DWORD *)(*((_QWORD *)this + 73) + 12LL) = *((_DWORD *)this + 8) + *((_DWORD *)v40 + 51);
          *(_DWORD *)(*((_QWORD *)this + 73) + 16LL) = 0;
          *(_DWORD *)(*((_QWORD *)this + 73) + 20LL) = *((_DWORD *)this + 8) + *((_DWORD *)v31 + 50);
          *(_DWORD *)(*((_QWORD *)this + 73) + 24LL) = 0;
          *(_DWORD *)(*((_QWORD *)this + 73) + 28LL) = 100;
          *(_DWORD *)(*((_QWORD *)this + 73) + 32LL) = *((_DWORD *)this + 138);
          *(_DWORD *)(*((_QWORD *)this + 73) + 44LL) = -1;
          *(_DWORD *)(*((_QWORD *)this + 73) + 36LL) = 0;
          if ( *((_DWORD *)this + 9) != -1 )
            v25 = 0;
          *(_DWORD *)(*((_QWORD *)this + 73) + 40LL) = v25;
          v35 = 8;
          for ( j = 0; j < *((_DWORD *)this + 138); j = v33 + 1 )
            PerfCounterDefinition::Init(
              *(PerfCounterDefinition **)&this[4 * j + 20],
              v31,
              (struct _PERF_COUNTER_DEFINITION *)(*((_QWORD *)this + 74) + 40LL * j),
              &v35);
          *(_DWORD *)(v4 + *((_QWORD *)this + 72)) = *((_DWORD *)this + 140);
          *(_DWORD *)(v4 + *((_QWORD *)this + 72) + 4LL) = *((_DWORD *)this + 9);
          TLMString<64,64,32767>::~TLMString<64,64,32767>(&v43);
          SecUtil::CSID::~CSID((SecUtil::CSID *)&v36);
          SecUtil::CSID::~CSID((SecUtil::CSID *)&v38);
          SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pSecurityDescriptor);
          operator delete(v20);
          return 1;
        }
        else
        {
          CloseHandle(*((HANDLE *)this + 71));
          TLMString<64,64,32767>::~TLMString<64,64,32767>(&v43);
          SecUtil::CSID::~CSID((SecUtil::CSID *)&v36);
          SecUtil::CSID::~CSID((SecUtil::CSID *)&v38);
          SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pSecurityDescriptor);
          operator delete(v20);
          return 0;
        }
      }
    }
    else
    {
      TLMString<64,64,32767>::~TLMString<64,64,32767>(&v43);
      SecUtil::CSID::~CSID((SecUtil::CSID *)&v36);
      SecUtil::CSID::~CSID((SecUtil::CSID *)&v38);
      SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pSecurityDescriptor);
      operator delete(v20);
      return 0;
    }
  }
  else
  {
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v43);
    if ( v13 )
      operator delete(v13);
    if ( v9 )
      operator delete(v9);
    SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)pSecurityDescriptor);
    operator delete(v20);
    return 0;
  }
}

```

## disassembly

```asm
0x1800ab154  mov     [rsp+arg_10], rbx
0x1800ab159  push    rsi
0x1800ab15a  push    rdi
0x1800ab15b  push    r12
0x1800ab15d  push    r13
0x1800ab15f  push    r14
0x1800ab161  sub     rsp, 180h
0x1800ab168  mov     rax, cs:__security_cookie
0x1800ab16f  xor     rax, rsp
0x1800ab172  mov     [rsp+1A8h+var_38], rax
0x1800ab17a  mov     [rsp+1A8h+var_148], rdx
0x1800ab17f  mov     r14, rcx
0x1800ab182  xorps   xmm0, xmm0
0x1800ab185  xor     eax, eax
0x1800ab187  movups  xmmword ptr [rsp+1A8h+FileMappingAttributes.nLength], xmm0
0x1800ab18c  mov     qword ptr [rsp+1A8h+FileMappingAttributes.bInheritHandle], rax
0x1800ab191  mov     r8d, [rcx+228h]
0x1800ab198  lea     eax, [r8+r8*4]
0x1800ab19c  lea     r12d, ds:40h[rax*8]
0x1800ab1a4  mov     [rsp+1A8h+var_170], r12d
0x1800ab1a9  lea     eax, [r12+8]
0x1800ab1ae  mov     [rcx+22Ch], eax
0x1800ab1b4  mov     eax, 8
0x1800ab1b9  mov     [rcx+230h], eax
0x1800ab1bf  xor     r9d, r9d
0x1800ab1c2  mov     edx, eax
0x1800ab1c4  test    r8d, r8d
0x1800ab1c7  jz      short loc_1800AB1EB
0x1800ab1c9  mov     rcx, [r14+r9*8+28h]
0x1800ab1ce  mov     eax, [rcx+1Ch]
0x1800ab1d1  add     rax, 7
0x1800ab1d5  shr     rax, 3
0x1800ab1d9  lea     edx, [rdx+rax*8]
0x1800ab1dc  mov     [r14+230h], edx
0x1800ab1e3  inc     r9d
0x1800ab1e6  cmp     r9d, r8d
0x1800ab1e9  jb      short loc_1800AB1C9
0x1800ab1eb  mov     r13d, [r14+24h]
0x1800ab1ef  cmp     r13d, 0FFFFFFFFh
0x1800ab1f3  jz      short loc_1800AB208
0x1800ab1f5  lea     eax, [rdx+5Ch]
0x1800ab1f8  mov     [r14+234h], eax
0x1800ab1ff  imul    r13d, eax
0x1800ab203  add     r13d, r12d
0x1800ab206  jmp     short loc_1800AB20C
0x1800ab208  lea     r13d, [rdx+r12]
0x1800ab20c  mov     [rsp+1A8h+Block], 0
0x1800ab215  lea     rcx, [rsp+1A8h+Block]; this
0x1800ab21a  call    ?Reset@CACL@SecUtil@@QEAAXXZ; SecUtil::CACL::Reset(void)
0x1800ab21f  nop
0x1800ab220  lea     rcx, [rsp+1A8h+pSecurityDescriptor]; pSecurityDescriptor
0x1800ab228  call    ??0CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::CSecurityDescriptor(void)
0x1800ab22d  nop
0x1800ab22e  lea     rcx, [rsp+1A8h+pSecurityDescriptor]; pSecurityDescriptor
0x1800ab236  call    ?InitializeFromThread@CSecurityDescriptor@SecUtil@@QEAAXXZ; SecUtil::CSecurityDescriptor::InitializeFromThread(void)
0x1800ab23b  xor     esi, esi
0x1800ab23d  mov     [rsp+1A8h+var_158], rsi
0x1800ab242  mov     [rsp+1A8h+var_168], rsi
0x1800ab247  mov     cl, 1; nSubAuthorityCount
0x1800ab249  call    cs:__imp_GetSidLengthRequired
0x1800ab24f  mov     ecx, eax; unsigned __int64
0x1800ab251  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ab256  mov     rbx, rax
0x1800ab259  mov     r8b, 1; nSubAuthorityCount
0x1800ab25c  lea     rdx, ?s_sia@CSID_NetworkServiceAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority; pIdentifierAuthority
0x1800ab263  mov     rcx, rax; Sid
0x1800ab266  call    cs:__imp_InitializeSid
0x1800ab26c  test    eax, eax
0x1800ab26e  jnz     short loc_1800AB27D
0x1800ab270  lea     edx, [rsi+1]
0x1800ab273  mov     rcx, rbx; Block
0x1800ab276  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab27b  jmp     short loc_1800AB2AC
0x1800ab27d  mov     edi, cs:?s_rgSubAuth@CSID_SystemAccount@SecUtil@@0PAKA; ulong near * SecUtil::CSID_SystemAccount::s_rgSubAuth
0x1800ab283  xor     edx, edx; nSubAuthority
0x1800ab285  mov     rcx, rbx; pSid
0x1800ab288  call    cs:__imp_GetSidSubAuthority
0x1800ab28e  mov     [rax], edi
0x1800ab290  mov     [rsp+1A8h+var_168], 0
0x1800ab299  mov     rsi, rbx
0x1800ab29c  mov     [rsp+1A8h+var_158], rbx
0x1800ab2a1  lea     rcx, [rsp+1A8h+var_168]
0x1800ab2a6  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800ab2ab  nop
0x1800ab2ac  xor     edi, edi
0x1800ab2ae  mov     [rsp+1A8h+var_168], rdi
0x1800ab2b3  mov     [rsp+1A8h+var_160], rdi
0x1800ab2b8  mov     cl, 2; nSubAuthorityCount
0x1800ab2ba  call    cs:__imp_GetSidLengthRequired
0x1800ab2c0  mov     ecx, eax; unsigned __int64
0x1800ab2c2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ab2c7  mov     rbx, rax
0x1800ab2ca  mov     r8b, 2; nSubAuthorityCount
0x1800ab2cd  lea     rdx, ?s_sia@CSID_EveryoneAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority; pIdentifierAuthority
0x1800ab2d4  mov     rcx, rax; Sid
0x1800ab2d7  call    cs:__imp_InitializeSid
0x1800ab2dd  test    eax, eax
0x1800ab2df  jnz     short loc_1800AB2EE
0x1800ab2e1  lea     edx, [rdi+1]
0x1800ab2e4  mov     rcx, rbx; Block
0x1800ab2e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab2ec  jmp     short loc_1800AB333
0x1800ab2ee  xor     r12d, r12d
0x1800ab2f1  lea     rdi, ?s_rgSubAuth@CSID_AdministratorsGroup@SecUtil@@0PAKA; ulong near * SecUtil::CSID_AdministratorsGroup::s_rgSubAuth
0x1800ab2f8  mov     edi, [rdi+r12*4]
0x1800ab2fc  mov     edx, r12d; nSubAuthority
0x1800ab2ff  mov     rcx, rbx; pSid
0x1800ab302  call    cs:__imp_GetSidSubAuthority
0x1800ab308  mov     [rax], edi
0x1800ab30a  inc     r12d
0x1800ab30d  cmp     r12d, 2
0x1800ab311  jb      short loc_1800AB2F1
0x1800ab313  mov     rdi, rbx
0x1800ab316  mov     [rsp+1A8h+var_160], 0
0x1800ab31f  mov     [rsp+1A8h+var_168], rbx
0x1800ab324  lea     rcx, [rsp+1A8h+var_160]
0x1800ab329  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800ab32e  mov     r12d, [rsp+1A8h+var_170]
0x1800ab333  mov     byte ptr [rsp+1A8h+var_178], 0
0x1800ab338  mov     ebx, 0C0100000h
0x1800ab33d  mov     [rsp+1A8h+var_170], ebx
0x1800ab341  mov     [rsp+1A8h+var_160], rsi
0x1800ab346  lea     rax, [rsp+1A8h+var_178]
0x1800ab34b  mov     [rsp+1A8h+lpName], rax
0x1800ab350  lea     rax, [rsp+1A8h+var_170]
0x1800ab355  mov     qword ptr [rsp+1A8h+dwMaximumSizeLow], rax
0x1800ab35a  lea     r9, [rsp+1A8h+var_160]
0x1800ab35f  mov     edx, 1
0x1800ab364  lea     rcx, [rsp+1A8h+Block]
0x1800ab369  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x1800ab36e  mov     byte ptr [rsp+1A8h+var_178], 0
0x1800ab373  mov     [rsp+1A8h+var_170], ebx
0x1800ab377  mov     [rsp+1A8h+var_160], rdi
0x1800ab37c  lea     rax, [rsp+1A8h+var_178]
0x1800ab381  mov     [rsp+1A8h+lpName], rax
0x1800ab386  lea     rax, [rsp+1A8h+var_170]
0x1800ab38b  mov     qword ptr [rsp+1A8h+dwMaximumSizeLow], rax
0x1800ab390  lea     r9, [rsp+1A8h+var_160]
0x1800ab395  mov     edx, 1
0x1800ab39a  lea     rcx, [rsp+1A8h+Block]
0x1800ab39f  call    ?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z; SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)
0x1800ab3a4  mov     rbx, [rsp+1A8h+Block]
0x1800ab3a9  mov     r8, rbx; struct _ACL *
0x1800ab3ac  lea     rcx, [rsp+1A8h+pSecurityDescriptor]; this
0x1800ab3b4  call    ?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z; SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)
0x1800ab3b9  mov     [rsp+1A8h+FileMappingAttributes.nLength], 18h
0x1800ab3c1  lea     rax, [rsp+1A8h+pSecurityDescriptor]
0x1800ab3c9  mov     [rsp+1A8h+FileMappingAttributes.lpSecurityDescriptor], rax
0x1800ab3ce  mov     [rsp+1A8h+FileMappingAttributes.bInheritHandle], 0
0x1800ab3d6  lea     rax, [rsp+1A8h+var_C0]
0x1800ab3de  mov     [rsp+1A8h+var_D0], rax
0x1800ab3e6  mov     [rsp+1A8h+var_C8], 41h ; 'A'
0x1800ab3f2  xor     eax, eax
0x1800ab3f4  mov     [rsp+1A8h+var_C0], ax
0x1800ab3fc  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1800ab403  mov     [rsp+1A8h+var_D8], rax
0x1800ab40b  lea     rdx, [rsp+1A8h+var_D8]; this
0x1800ab413  mov     rcx, r14; wchar_t *
0x1800ab416  call    ?PerfNameToObjectName@@YAJPEB_WAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; PerfNameToObjectName(wchar_t const *,TLMString<64,64,32767> &)
0x1800ab41b  test    eax, eax
0x1800ab41d  jns     short loc_1800AB466
0x1800ab41f  lea     rcx, [rsp+1A8h+var_D8]
0x1800ab427  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800ab42c  nop
0x1800ab42d  test    rdi, rdi
0x1800ab430  jz      short loc_1800AB43B
0x1800ab432  mov     rcx, rdi; Block
0x1800ab435  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab43a  nop
0x1800ab43b  test    rsi, rsi
0x1800ab43e  jz      short loc_1800AB449
0x1800ab440  mov     rcx, rsi; Block
0x1800ab443  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab448  nop
0x1800ab449  lea     rcx, [rsp+1A8h+pSecurityDescriptor]; this
0x1800ab451  call    ??1CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::~CSecurityDescriptor(void)
0x1800ab456  nop
0x1800ab457  mov     rcx, rbx; Block
0x1800ab45a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab45f  xor     eax, eax
0x1800ab461  jmp     loc_1800AB73F
0x1800ab466  add     r13d, 8
0x1800ab46a  mov     rax, [rsp+1A8h+var_D0]
0x1800ab472  mov     [rsp+1A8h+lpName], rax; lpName
0x1800ab477  mov     [rsp+1A8h+dwMaximumSizeLow], r13d; dwMaximumSizeLow
0x1800ab47c  xor     r9d, r9d; dwMaximumSizeHigh
0x1800ab47f  lea     r8d, [r9+4]; flProtect
0x1800ab483  lea     rdx, [rsp+1A8h+FileMappingAttributes]; lpFileMappingAttributes
0x1800ab488  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800ab48c  mov     rcx, rdi; hFile
0x1800ab48f  call    cs:__imp_CreateFileMappingW
0x1800ab495  mov     [r14+238h], rax
0x1800ab49c  xor     esi, esi
0x1800ab49e  test    rax, rax
0x1800ab4a1  jnz     short loc_1800AB4E4
0x1800ab4a3  lea     rcx, [rsp+1A8h+var_D8]
0x1800ab4ab  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800ab4b0  nop
0x1800ab4b1  lea     rcx, [rsp+1A8h+var_168]; this
0x1800ab4b6  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x1800ab4bb  nop
0x1800ab4bc  lea     rcx, [rsp+1A8h+var_158]; this
0x1800ab4c1  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x1800ab4c6  nop
0x1800ab4c7  lea     rcx, [rsp+1A8h+pSecurityDescriptor]; this
0x1800ab4cf  call    ??1CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::~CSecurityDescriptor(void)
0x1800ab4d4  nop
0x1800ab4d5  mov     rcx, rbx; Block
0x1800ab4d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab4dd  xor     eax, eax
0x1800ab4df  jmp     loc_1800AB73F
0x1800ab4e4  call    cs:__imp_GetLastError
0x1800ab4ea  mov     rcx, [r14+238h]; hFileMappingObject
0x1800ab4f1  cmp     eax, 0B7h
0x1800ab4f6  jnz     short loc_1800AB546
0x1800ab4f8  call    cs:__imp_CloseHandle
0x1800ab4fe  mov     [r14+238h], rsi
0x1800ab505  lea     rcx, [rsp+1A8h+var_D8]
0x1800ab50d  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800ab512  nop
0x1800ab513  lea     rcx, [rsp+1A8h+var_168]; this
0x1800ab518  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x1800ab51d  nop
0x1800ab51e  lea     rcx, [rsp+1A8h+var_158]; this
0x1800ab523  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x1800ab528  nop
0x1800ab529  lea     rcx, [rsp+1A8h+pSecurityDescriptor]; this
0x1800ab531  call    ??1CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::~CSecurityDescriptor(void)
0x1800ab536  nop
0x1800ab537  mov     rcx, rbx; Block
0x1800ab53a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab53f  xor     eax, eax
0x1800ab541  jmp     loc_1800AB73F
0x1800ab546  mov     qword ptr [rsp+1A8h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x1800ab54b  xor     r9d, r9d; dwFileOffsetLow
0x1800ab54e  xor     r8d, r8d; dwFileOffsetHigh
0x1800ab551  lea     edx, [r9+2]; dwDesiredAccess
0x1800ab555  call    cs:__imp_MapViewOfFile
0x1800ab55b  mov     [r14+240h], rax
0x1800ab562  test    rax, rax
0x1800ab565  jnz     short loc_1800AB5B6
0x1800ab567  mov     rcx, [r14+238h]; hObject
0x1800ab56e  call    cs:__imp_CloseHandle
0x1800ab574  nop
0x1800ab575  lea     rcx, [rsp+1A8h+var_D8]
0x1800ab57d  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800ab582  nop
0x1800ab583  lea     rcx, [rsp+1A8h+var_168]; this
0x1800ab588  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x1800ab58d  nop
0x1800ab58e  lea     rcx, [rsp+1A8h+var_158]; this
0x1800ab593  call    ??1CSID@SecUtil@@QEAA@XZ; SecUtil::CSID::~CSID(void)
0x1800ab598  nop
0x1800ab599  lea     rcx, [rsp+1A8h+pSecurityDescriptor]; this
0x1800ab5a1  call    ??1CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::~CSecurityDescriptor(void)
0x1800ab5a6  nop
0x1800ab5a7  mov     rcx, rbx; Block
0x1800ab5aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ab5af  xor     eax, eax
0x1800ab5b1  jmp     loc_1800AB73F
0x1800ab5b6  mov     r8d, r13d; Size
0x1800ab5b9  xor     edx, edx; Val
0x1800ab5bb  mov     rcx, rax; void *
0x1800ab5be  call    memset_0
0x1800ab5c3  mov     rcx, [r14+240h]
0x1800ab5ca  mov     [r14+248h], rcx
0x1800ab5d1  lea     rax, [rcx+40h]
0x1800ab5d5  mov     [r14+250h], rax
0x1800ab5dc  mov     eax, [r14+22Ch]
0x1800ab5e3  add     rax, rcx
0x1800ab5e6  mov     [r14+258h], rax
0x1800ab5ed  mov     [rcx], r12d
0x1800ab5f0  mov     rax, [r14+248h]
0x1800ab5f7  mov     [rax+4], r12d
0x1800ab5fb  mov     rax, [r14+248h]
0x1800ab602  mov     dword ptr [rax+8], 40h ; '@'
0x1800ab609  mov     r11, [rsp+1A8h+var_148]
0x1800ab60e  mov     ecx, [r11+0CCh]
0x1800ab615  add     ecx, [r14+20h]
0x1800ab619  mov     rax, [r14+248h]
0x1800ab620  mov     [rax+0Ch], ecx
0x1800ab623  mov     rax, [r14+248h]
0x1800ab62a  mov     [rax+10h], esi
0x1800ab62d  mov     ecx, [r11+0C8h]
0x1800ab634  add     ecx, [r14+20h]
0x1800ab638  mov     rax, [r14+248h]
0x1800ab63f  mov     [rax+14h], ecx
0x1800ab642  mov     rax, [r14+248h]
0x1800ab649  mov     [rax+18h], esi
0x1800ab64c  mov     rax, [r14+248h]
0x1800ab653  mov     dword ptr [rax+1Ch], 64h ; 'd'
0x1800ab65a  mov     rcx, [r14+248h]
0x1800ab661  mov     eax, [r14+228h]
0x1800ab668  mov     [rcx+20h], eax
0x1800ab66b  mov     rax, [r14+248h]
0x1800ab672  or      ecx, 0FFFFFFFFh
0x1800ab675  mov     [rax+2Ch], ecx
0x1800ab678  mov     rax, [r14+248h]
0x1800ab67f  mov     [rax+24h], esi
0x1800ab682  mov     rax, [r14+248h]
  ... truncated ...
```
