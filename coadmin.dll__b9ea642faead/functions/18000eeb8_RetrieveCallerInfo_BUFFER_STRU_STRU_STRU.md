# RetrieveCallerInfo(BUFFER *,STRU *,STRU *,STRU *)

- ea: `0x18000eeb8`
- end: `0x18000f304`
- name: `?RetrieveCallerInfo@@YAJPEAVBUFFER@@PEAVSTRU@@11@Z`
- size: `1100`
- prototype: `__int64 __fastcall(struct BUFFER *, struct STRU *, struct STRU *, struct STRU *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000238c`

## callees

- `0x18000b624`
- `0x18000e978`
- `0x18000eeb8`
- `0x18000fb06`
- `0x18000fb1e`
- `0x18000fb50`

## import_xrefs

- `ADVAPI32!LookupAccountSidW` at `0x18000f1fd`
- `ADVAPI32!LookupAccountSidW` at `0x18000f262`
- `ADVAPI32!LookupAccountSidW` at `0x18000f1fd`
- `ADVAPI32!LookupAccountSidW` at `0x18000f262`
- `ADVAPI32!GetLengthSid` at `0x18000f0bd`
- `ADVAPI32!GetLengthSid` at `0x18000f0d9`
- `ADVAPI32!GetLengthSid` at `0x18000f0bd`
- `ADVAPI32!GetLengthSid` at `0x18000f0d9`
- `ADVAPI32!GetTokenInformation` at `0x18000f05d`
- `ADVAPI32!GetTokenInformation` at `0x18000f0a8`
- `ADVAPI32!GetTokenInformation` at `0x18000f10a`
- `ADVAPI32!GetTokenInformation` at `0x18000f05d`
- `ADVAPI32!GetTokenInformation` at `0x18000f0a8`
- `ADVAPI32!GetTokenInformation` at `0x18000f10a`
- `ADVAPI32!OpenProcessToken` at `0x18000f000`
- `ADVAPI32!OpenProcessToken` at `0x18000f000`
- `KERNEL32!GetCurrentProcess` at `0x18000efed`
- `KERNEL32!GetCurrentProcess` at `0x18000efed`
- `KERNEL32!CloseHandle` at `0x18000f2a9`
- `KERNEL32!CloseHandle` at `0x18000f2a9`
- `KERNEL32!GetLastError` at `0x18000f00a`
- `KERNEL32!GetLastError` at `0x18000f01e`
- `KERNEL32!GetLastError` at `0x18000f067`
- `KERNEL32!GetLastError` at `0x18000f00a`
- `KERNEL32!GetLastError` at `0x18000f01e`
- `KERNEL32!GetLastError` at `0x18000f067`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000f2db`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000f2db`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f07b`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f0c8`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f211`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f229`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f07b`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f0c8`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f211`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f229`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f169`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f1b0`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f169`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f1b0`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f2bd`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f2c7`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f2d1`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f2bd`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f2c7`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f2d1`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000ef37`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000ef37`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f122`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f277`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f28a`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f122`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f277`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f28a`
- `IisRTL!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000f14f`
- `IisRTL!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000f196`
- `IisRTL!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000f14f`
- `IisRTL!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000f196`

## pseudocode

```c
__int64 __fastcall RetrieveCallerInfo(struct BUFFER *a1, struct STRU *a2, struct STRU *a3, struct STRU *a4)
{
  int ThreadToken; // eax
  signed int v9; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  PSID *v12; // rsi
  DWORD LengthSid; // eax
  void *v14; // rbx
  DWORD v15; // eax
  DWORD ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID TokenInformation; // [rsp+80h] [rbp-80h]
  DWORD TokenInformationLength; // [rsp+88h] [rbp-78h]
  __int16 v25; // [rsp+8Ch] [rbp-74h]
  _BYTE v26[32]; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+B0h] [rbp-50h]
  unsigned int v28; // [rsp+B8h] [rbp-48h]
  __int16 v29; // [rsp+BCh] [rbp-44h]
  _BYTE v30[32]; // [rsp+C0h] [rbp-40h] BYREF
  LPWSTR Name; // [rsp+E0h] [rbp-20h]
  unsigned int v32; // [rsp+E8h] [rbp-18h]
  __int16 v33; // [rsp+ECh] [rbp-14h]
  int v34; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v35[4]; // [rsp+F4h] [rbp-Ch]
  __int128 v36; // [rsp+104h] [rbp+4h]
  __int128 v37; // [rsp+114h] [rbp+14h]
  int v38; // [rsp+124h] [rbp+24h]
  _BYTE v39[56]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v40[64]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v41[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v42[64]; // [rsp+1E0h] [rbp+E0h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  cchName = 0;
  v38 = 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  cchReferencedDomainName = 0;
  v37 = 0;
  peUse = SidTypeUnknown;
  v34 = 0;
  STRU::STRU((STRU *)v39);
  memset_0(v40, 0, sizeof(v40));
  v32 = 64;
  Name = (LPWSTR)v40;
  v33 = 256;
  memset_0(v41, 0, sizeof(v41));
  v28 = 64;
  ReferencedDomainName = (LPWSTR)v41;
  v29 = 256;
  memset_0(v42, 0, sizeof(v42));
  TokenInformationLength = 64;
  TokenInformation = v42;
  v25 = 256;
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    v9 = -2147024809;
    goto LABEL_35;
  }
  ThreadToken = GetThreadToken(&TokenHandle);
  v9 = ThreadToken;
  if ( TokenHandle || ThreadToken != -2147417833 )
  {
    if ( ThreadToken < 0 )
      goto LABEL_35;
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
      goto LABEL_8;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &ReturnLength) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_8;
    if ( !BUFFER::Resize((BUFFER *)v22, ReturnLength) )
    {
LABEL_16:
      v9 = -2147024882;
      goto LABEL_35;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &ReturnLength) )
      goto LABEL_8;
  }
  v12 = (PSID *)TokenInformation;
  LengthSid = GetLengthSid(*(PSID *)TokenInformation);
  if ( !BUFFER::Resize(a1, LengthSid) )
    goto LABEL_16;
  v14 = (void *)*((_QWORD *)a1 + 4);
  v15 = GetLengthSid(*v12);
  memcpy_0(v14, *v12, v15);
  if ( !GetTokenInformation(TokenHandle, TokenStatistics, &v34, 0x38u, &ReturnLength) )
    goto LABEL_8;
  v9 = STRU::Copy(a4, L"(");
  if ( v9 < 0 )
    goto LABEL_35;
  v9 = DisplayAsHex(v35[2], (struct STRU *)v39);
  if ( v9 < 0 )
    goto LABEL_35;
  v9 = STRU::Append(a4, (const struct STRU *)v39);
  if ( v9 < 0 )
    goto LABEL_35;
  v9 = STRU::Append(a4, L",");
  if ( v9 < 0 )
    goto LABEL_35;
  v9 = DisplayAsHex(v35[1], (struct STRU *)v39);
  if ( v9 < 0 )
    goto LABEL_35;
  v9 = STRU::Append(a4, (const struct STRU *)v39);
  if ( v9 < 0 )
    goto LABEL_35;
  v9 = STRU::Append(a4, L")");
  if ( v9 < 0 )
    goto LABEL_35;
  cchName = v32 >> 1;
  cchReferencedDomainName = v28 >> 1;
  if ( !LookupAccountSidW(0, *v12, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    if ( !BUFFER::Resize((BUFFER *)v30, 2 * cchName) || !BUFFER::Resize((BUFFER *)v26, 2 * cchReferencedDomainName) )
      goto LABEL_16;
    if ( !LookupAccountSidW(0, *v12, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    {
LABEL_8:
      if ( GetLastError() )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v9 = -2147467259;
      }
      goto LABEL_35;
    }
  }
  v9 = STRU::Copy(a3, ReferencedDomainName);
  if ( v9 >= 0 )
  {
    v9 = STRU::Copy(a2, Name);
    if ( v9 >= 0 )
      v9 = 0;
  }
LABEL_35:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v22);
  BUFFER::~BUFFER((BUFFER *)v26);
  BUFFER::~BUFFER((BUFFER *)v30);
  STRU::~STRU((STRU *)v39);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000eeb8  push    rbp
0x18000eeba  push    rbx
0x18000eebb  push    rsi
0x18000eebc  push    rdi
0x18000eebd  push    r12
0x18000eebf  push    r14
0x18000eec1  push    r15
0x18000eec3  lea     rbp, [rsp-130h]
0x18000eecb  sub     rsp, 230h
0x18000eed2  mov     rax, cs:__security_cookie
0x18000eed9  xor     rax, rsp
0x18000eedc  mov     [rbp+160h+var_40], rax
0x18000eee3  xorps   xmm0, xmm0
0x18000eee6  mov     [rsp+260h+TokenHandle], 0
0x18000eeef  mov     r14, rcx
0x18000eef2  mov     [rsp+260h+var_220], 0
0x18000eefa  xor     eax, eax
0x18000eefc  mov     [rsp+260h+cchName], 0
0x18000ef04  lea     rcx, [rbp+160h+var_138]
0x18000ef08  mov     [rbp+160h+var_13C], eax
0x18000ef0b  movups  xmmword ptr [rbp+160h+var_16C], xmm0
0x18000ef0f  mov     rdi, r9
0x18000ef12  mov     r12, r8
0x18000ef15  movups  [rbp+160h+var_15C], xmm0
0x18000ef19  mov     r15, rdx
0x18000ef1c  mov     [rsp+260h+var_21C], 0
0x18000ef24  movups  [rbp+160h+var_14C], xmm0
0x18000ef28  mov     [rsp+260h+var_208], 8
0x18000ef30  mov     [rbp+160h+var_170], 0
0x18000ef37  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000ef3d  mov     ebx, 40h ; '@'
0x18000ef42  lea     rcx, [rbp+160h+var_100]; void *
0x18000ef46  mov     r8d, ebx; Size
0x18000ef49  xor     edx, edx; Val
0x18000ef4b  call    memset_0
0x18000ef50  lea     rax, [rbp+160h+var_100]
0x18000ef54  mov     [rbp+160h+var_178], ebx
0x18000ef57  mov     r8d, ebx; Size
0x18000ef5a  mov     [rbp+160h+Name], rax
0x18000ef5e  xor     edx, edx; Val
0x18000ef60  mov     [rbp+160h+var_174], 100h
0x18000ef66  lea     rcx, [rbp+160h+var_C0]; void *
0x18000ef6d  lea     esi, [rbx-3Fh]
0x18000ef70  call    memset_0
0x18000ef75  lea     rax, [rbp+160h+var_C0]
0x18000ef7c  mov     [rbp+160h+var_1A8], ebx
0x18000ef7f  mov     r8d, ebx; Size
0x18000ef82  mov     [rbp+160h+ReferencedDomainName], rax
0x18000ef86  xor     edx, edx; Val
0x18000ef88  mov     [rbp+160h+var_1A4], 100h
0x18000ef8e  lea     rcx, [rbp+160h+var_80]; void *
0x18000ef95  call    memset_0
0x18000ef9a  mov     [rbp+160h+TokenInformationLength], ebx
0x18000ef9d  lea     rax, [rbp+160h+var_80]
0x18000efa4  mov     [rbp+160h+TokenInformation], rax
0x18000efa8  mov     [rbp+160h+var_1D4], 100h
0x18000efae  test    r14, r14
0x18000efb1  jz      loc_18000F29A
0x18000efb7  test    r15, r15
0x18000efba  jz      loc_18000F29A
0x18000efc0  test    r12, r12
0x18000efc3  jz      loc_18000F29A
0x18000efc9  test    rdi, rdi
0x18000efcc  jz      loc_18000F29A
0x18000efd2  lea     rcx, [rsp+260h+TokenHandle]; TokenHandle
0x18000efd7  call    ?GetThreadToken@@YAJPEAPEAX@Z; GetThreadToken(void * *)
0x18000efdc  cmp     [rsp+260h+TokenHandle], 0
0x18000efe2  mov     ebx, eax
0x18000efe4  jnz     short loc_18000F03C
0x18000efe6  cmp     eax, 80010117h
0x18000efeb  jnz     short loc_18000F03C
0x18000efed  call    cs:__imp_GetCurrentProcess
0x18000eff3  lea     r8, [rsp+260h+TokenHandle]; TokenHandle
0x18000eff8  mov     edx, 20008h; DesiredAccess
0x18000effd  mov     rcx, rax; ProcessHandle
0x18000f000  call    cs:__imp_OpenProcessToken
0x18000f006  test    eax, eax
0x18000f008  jnz     short loc_18000F044
0x18000f00a  call    cs:__imp_GetLastError
0x18000f010  test    eax, eax
0x18000f012  jnz     short loc_18000F01E
0x18000f014  mov     ebx, 80004005h
0x18000f019  jmp     loc_18000F29F
0x18000f01e  call    cs:__imp_GetLastError
0x18000f024  mov     ebx, eax
0x18000f026  test    eax, eax
0x18000f028  jle     loc_18000F29F
0x18000f02e  movzx   ebx, ax
0x18000f031  or      ebx, 80070000h
0x18000f037  jmp     loc_18000F29F
0x18000f03c  test    eax, eax
0x18000f03e  js      loc_18000F29F
0x18000f044  mov     r9d, [rbp+160h+TokenInformationLength]; TokenInformationLength
0x18000f048  lea     rax, [rsp+260h+var_220]
0x18000f04d  mov     r8, [rbp+160h+TokenInformation]; TokenInformation
0x18000f051  mov     edx, esi; TokenInformationClass
0x18000f053  mov     rcx, [rsp+260h+TokenHandle]; TokenHandle
0x18000f058  mov     [rsp+260h+ReturnLength], rax; ReturnLength
0x18000f05d  call    cs:__imp_GetTokenInformation
0x18000f063  test    eax, eax
0x18000f065  jnz     short loc_18000F0B6
0x18000f067  call    cs:__imp_GetLastError
0x18000f06d  cmp     eax, 7Ah ; 'z'
0x18000f070  jnz     short loc_18000F00A
0x18000f072  mov     edx, [rsp+260h+var_220]
0x18000f076  lea     rcx, [rsp+260h+var_200]
0x18000f07b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000f081  test    al, al
0x18000f083  jnz     short loc_18000F08F
0x18000f085  mov     ebx, 8007000Eh
0x18000f08a  jmp     loc_18000F29F
0x18000f08f  mov     r9d, [rbp+160h+TokenInformationLength]; TokenInformationLength
0x18000f093  lea     rax, [rsp+260h+var_220]
0x18000f098  mov     r8, [rbp+160h+TokenInformation]; TokenInformation
0x18000f09c  mov     edx, esi; TokenInformationClass
0x18000f09e  mov     rcx, [rsp+260h+TokenHandle]; TokenHandle
0x18000f0a3  mov     [rsp+260h+ReturnLength], rax; ReturnLength
0x18000f0a8  call    cs:__imp_GetTokenInformation
0x18000f0ae  test    eax, eax
0x18000f0b0  jz      loc_18000F00A
0x18000f0b6  mov     rsi, [rbp+160h+TokenInformation]
0x18000f0ba  mov     rcx, [rsi]; pSid
0x18000f0bd  call    cs:__imp_GetLengthSid
0x18000f0c3  mov     edx, eax
0x18000f0c5  mov     rcx, r14
0x18000f0c8  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000f0ce  test    al, al
0x18000f0d0  jz      short loc_18000F085
0x18000f0d2  mov     rcx, [rsi]; pSid
0x18000f0d5  mov     rbx, [r14+20h]
0x18000f0d9  call    cs:__imp_GetLengthSid
0x18000f0df  mov     rdx, [rsi]; Src
0x18000f0e2  mov     rcx, rbx; void *
0x18000f0e5  mov     r8d, eax; Size
0x18000f0e8  call    memcpy_0
0x18000f0ed  mov     rcx, [rsp+260h+TokenHandle]; TokenHandle
0x18000f0f2  lea     rax, [rsp+260h+var_220]
0x18000f0f7  mov     r9d, 38h ; '8'; TokenInformationLength
0x18000f0fd  mov     [rsp+260h+ReturnLength], rax; ReturnLength
0x18000f102  lea     r8, [rbp+160h+var_170]; TokenInformation
0x18000f106  lea     edx, [r9-2Eh]; TokenInformationClass
0x18000f10a  call    cs:__imp_GetTokenInformation
0x18000f110  test    eax, eax
0x18000f112  jz      loc_18000F00A
0x18000f118  lea     rdx, asc_18001318C; "("
0x18000f11f  mov     rcx, rdi
0x18000f122  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f128  mov     ebx, eax
0x18000f12a  test    eax, eax
0x18000f12c  js      loc_18000F29F
0x18000f132  mov     ecx, [rbp+160h+var_16C+8]; unsigned int
0x18000f135  lea     rdx, [rbp+160h+var_138]; struct STRU *
0x18000f139  call    ?DisplayAsHex@@YAJKPEAVSTRU@@@Z; DisplayAsHex(ulong,STRU *)
0x18000f13e  mov     ebx, eax
0x18000f140  test    eax, eax
0x18000f142  js      loc_18000F29F
0x18000f148  lea     rdx, [rbp+160h+var_138]
0x18000f14c  mov     rcx, rdi
0x18000f14f  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18000f155  mov     ebx, eax
0x18000f157  test    eax, eax
0x18000f159  js      loc_18000F29F
0x18000f15f  lea     rdx, asc_180013190; ","
0x18000f166  mov     rcx, rdi
0x18000f169  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000f16f  mov     ebx, eax
0x18000f171  test    eax, eax
0x18000f173  js      loc_18000F29F
0x18000f179  mov     ecx, [rbp+160h+var_16C+4]; unsigned int
0x18000f17c  lea     rdx, [rbp+160h+var_138]; struct STRU *
0x18000f180  call    ?DisplayAsHex@@YAJKPEAVSTRU@@@Z; DisplayAsHex(ulong,STRU *)
0x18000f185  mov     ebx, eax
0x18000f187  test    eax, eax
0x18000f189  js      loc_18000F29F
0x18000f18f  lea     rdx, [rbp+160h+var_138]
0x18000f193  mov     rcx, rdi
0x18000f196  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18000f19c  mov     ebx, eax
0x18000f19e  test    eax, eax
0x18000f1a0  js      loc_18000F29F
0x18000f1a6  lea     rdx, asc_180013194; ")"
0x18000f1ad  mov     rcx, rdi
0x18000f1b0  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000f1b6  mov     ebx, eax
0x18000f1b8  test    eax, eax
0x18000f1ba  js      loc_18000F29F
0x18000f1c0  mov     eax, [rbp+160h+var_178]
0x18000f1c3  lea     rcx, [rsp+260h+var_208]
0x18000f1c8  mov     r8, [rbp+160h+Name]; Name
0x18000f1cc  lea     r9, [rsp+260h+cchName]; cchName
0x18000f1d1  shr     eax, 1
0x18000f1d3  mov     [rsp+260h+cchName], eax
0x18000f1d7  mov     eax, [rbp+160h+var_1A8]
0x18000f1da  mov     [rsp+260h+peUse], rcx; peUse
0x18000f1df  lea     rcx, [rsp+260h+var_21C]
0x18000f1e4  shr     eax, 1
0x18000f1e6  mov     [rsp+260h+var_21C], eax
0x18000f1ea  mov     rax, [rbp+160h+ReferencedDomainName]
0x18000f1ee  mov     rdx, [rsi]; Sid
0x18000f1f1  mov     [rsp+260h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18000f1f6  xor     ecx, ecx; lpSystemName
0x18000f1f8  mov     [rsp+260h+ReturnLength], rax; ReferencedDomainName
0x18000f1fd  call    cs:__imp_LookupAccountSidW
0x18000f203  test    eax, eax
0x18000f205  jnz     short loc_18000F270
0x18000f207  mov     edx, [rsp+260h+cchName]
0x18000f20b  lea     rcx, [rbp+160h+var_1A0]
0x18000f20f  add     edx, edx
0x18000f211  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000f217  test    al, al
0x18000f219  jz      loc_18000F085
0x18000f21f  mov     edx, [rsp+260h+var_21C]
0x18000f223  lea     rcx, [rbp+160h+var_1D0]
0x18000f227  add     edx, edx
0x18000f229  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000f22f  test    al, al
0x18000f231  jz      loc_18000F085
0x18000f237  mov     rax, [rbp+160h+ReferencedDomainName]
0x18000f23b  lea     rcx, [rsp+260h+var_208]
0x18000f240  mov     r8, [rbp+160h+Name]; Name
0x18000f244  lea     r9, [rsp+260h+cchName]; cchName
0x18000f249  mov     rdx, [rsi]; Sid
0x18000f24c  mov     [rsp+260h+peUse], rcx; peUse
0x18000f251  lea     rcx, [rsp+260h+var_21C]
0x18000f256  mov     [rsp+260h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18000f25b  xor     ecx, ecx; lpSystemName
0x18000f25d  mov     [rsp+260h+ReturnLength], rax; ReferencedDomainName
0x18000f262  call    cs:__imp_LookupAccountSidW
0x18000f268  test    eax, eax
0x18000f26a  jz      loc_18000F00A
0x18000f270  mov     rdx, [rbp+160h+ReferencedDomainName]
0x18000f274  mov     rcx, r12
0x18000f277  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f27d  mov     ebx, eax
0x18000f27f  test    eax, eax
0x18000f281  js      short loc_18000F29F
0x18000f283  mov     rdx, [rbp+160h+Name]
0x18000f287  mov     rcx, r15
0x18000f28a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f290  mov     ebx, eax
0x18000f292  test    eax, eax
0x18000f294  js      short loc_18000F29F
0x18000f296  xor     ebx, ebx
0x18000f298  jmp     short loc_18000F29F
0x18000f29a  mov     ebx, 80070057h
0x18000f29f  mov     rcx, [rsp+260h+TokenHandle]; hObject
0x18000f2a4  test    rcx, rcx
0x18000f2a7  jz      short loc_18000F2B8
0x18000f2a9  call    cs:__imp_CloseHandle
0x18000f2af  mov     [rsp+260h+TokenHandle], 0
0x18000f2b8  lea     rcx, [rsp+260h+var_200]
0x18000f2bd  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000f2c3  lea     rcx, [rbp+160h+var_1D0]
0x18000f2c7  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000f2cd  lea     rcx, [rbp+160h+var_1A0]
0x18000f2d1  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000f2d7  lea     rcx, [rbp+160h+var_138]
0x18000f2db  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f2e1  mov     eax, ebx
0x18000f2e3  mov     rcx, [rbp+160h+var_40]
0x18000f2ea  xor     rcx, rsp; StackCookie
0x18000f2ed  call    __security_check_cookie
0x18000f2f2  add     rsp, 230h
0x18000f2f9  pop     r15
0x18000f2fb  pop     r14
0x18000f2fd  pop     r12
0x18000f2ff  pop     rdi
0x18000f300  pop     rsi
0x18000f301  pop     rbx
0x18000f302  pop     rbp
0x18000f303  retn
```
