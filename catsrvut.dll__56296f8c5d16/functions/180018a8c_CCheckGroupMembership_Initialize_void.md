# CCheckGroupMembership::Initialize(void)

- ea: `0x180018a8c`
- end: `0x180018d3f`
- name: `?Initialize@CCheckGroupMembership@@CAJXZ`
- size: `691`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001e864`

## callees

- `0x180018a8c`
- `0x1800191ac`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018b05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018c88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018b05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018b1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018caa`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180018af0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180018af0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018ca0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018ca0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018c51`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018c51`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018c7c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018c7c`
- `samcli!NetLocalGroupGetMembers` at `0x180018c05`
- `samcli!NetLocalGroupGetMembers` at `0x180018c05`
- `netutils!NetApiBufferFree` at `0x180018cea`
- `netutils!NetApiBufferFree` at `0x180018d14`
- `netutils!NetApiBufferFree` at `0x180018cea`
- `netutils!NetApiBufferFree` at `0x180018d14`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018b9b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180018b9b`

## pseudocode

```c
__int64 CCheckGroupMembership::Initialize(void)
{
  unsigned int v0; // ebx
  int v1; // edi
  void *v2; // rsi
  int j; // r14d
  __int64 v4; // rcx
  signed int v5; // eax
  int v6; // r14d
  signed int LastError; // eax
  DWORD Members; // eax
  LPBYTE v9; // r12
  signed int v10; // eax
  __int64 i; // rdi
  signed int v12; // eax
  DWORD LengthSid; // r13d
  void *v14; // rax
  void *v15; // r15
  __int64 v16; // rcx
  signed int v17; // eax
  LPBYTE v18; // rcx
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  DWORD totalentries[2]; // [rsp+60h] [rbp-A0h] BYREF
  void *v26; // [rsp+68h] [rbp-98h] BYREF
  WCHAR ReferencedDomainName[24]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF

  v0 = 0;
  bufptr = 0;
  v1 = 0;
  while ( 2 )
  {
    if ( v1 >= 1 )
    {
      v6 = 0;
      while ( 1 )
      {
        cchName = 257;
        cchReferencedDomainName = 16;
        peUse = 0;
        if ( !LookupAccountSidLocalW(
                *((PSID *)CCheckGroupMembership::sm_apSid + v6),
                Name,
                &cchName,
                ReferencedDomainName,
                &cchReferencedDomainName,
                &peUse) )
        {
          LastError = GetLastError();
          v0 = LastError;
          if ( LastError > 0 )
            v0 = (unsigned __int16)LastError | 0x80070000;
          if ( v0 )
            break;
        }
        cbSid = 0;
        totalentries[0] = 0;
        Members = NetLocalGroupGetMembers(0, Name, 1u, &bufptr, 0xFFFFFFFF, &cbSid, totalentries, 0);
        v9 = bufptr;
        if ( Members )
        {
          v10 = GetLastError();
          v0 = v10;
          if ( v10 > 0 )
            v0 = (unsigned __int16)v10 | 0x80070000;
          if ( v0 )
            break;
        }
        for ( i = 0; (unsigned int)i < cbSid; i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)&v9[24 * i + 8] == 2 )
          {
            if ( !IsValidSid(*(PSID *)&v9[24 * i]) )
            {
              v12 = GetLastError();
              v0 = v12;
              if ( v12 > 0 )
                v0 = (unsigned __int16)v12 | 0x80070000;
              if ( v0 )
                goto LABEL_40;
            }
            LengthSid = GetLengthSid(*(PSID *)&v9[24 * i]);
            v14 = CoTaskMemAlloc(LengthSid + 1);
            v15 = v14;
            if ( !v14 )
            {
LABEL_39:
              v0 = -2147024882;
              goto LABEL_40;
            }
            if ( !CopySid(LengthSid, v14, *(PSID *)&v9[24 * i]) )
            {
              v17 = GetLastError();
              v0 = v17;
              if ( v17 > 0 )
                v0 = (unsigned __int16)v17 | 0x80070000;
              if ( v0 )
                goto LABEL_40;
            }
            v26 = v15;
            Array<unsigned char *>::append(v16, &v26);
          }
        }
        v18 = bufptr;
        if ( bufptr )
        {
          NetApiBufferFree(bufptr);
          v18 = 0;
          bufptr = 0;
        }
        if ( ++v6 >= 1 )
          goto LABEL_41;
      }
    }
    else
    {
      v2 = 0;
      cbSid = 0;
      for ( j = 1; ; j = 0 )
      {
        if ( CreateWellKnownSid((WELL_KNOWN_SID_TYPE)dword_180062974[v1], 0, v2, &cbSid) )
          goto LABEL_11;
        if ( !j )
          break;
        v2 = CoTaskMemAlloc(cbSid + 1);
        if ( !v2 )
          goto LABEL_39;
      }
      v5 = GetLastError();
      v0 = v5;
      if ( v5 > 0 )
        v0 = (unsigned __int16)v5 | 0x80070000;
      if ( !v0 )
      {
LABEL_11:
        *(_QWORD *)totalentries = v2;
        Array<unsigned char *>::append(v4, totalentries);
        ++v1;
        continue;
      }
    }
    break;
  }
LABEL_40:
  v18 = bufptr;
LABEL_41:
  if ( v18 )
    NetApiBufferFree(v18);
  return v0;
}

```

## disassembly

```asm
0x180018a8c  push    rbp
0x180018a8e  push    rbx
0x180018a8f  push    rsi
0x180018a90  push    rdi
0x180018a91  push    r12
0x180018a93  push    r13
0x180018a95  push    r14
0x180018a97  push    r15
0x180018a99  lea     rbp, [rsp-1C8h]
0x180018aa1  sub     rsp, 2C8h
0x180018aa8  mov     rax, cs:__security_cookie
0x180018aaf  xor     rax, rsp
0x180018ab2  mov     [rbp+200h+var_50], rax
0x180018ab9  xor     ebx, ebx
0x180018abb  mov     [rsp+300h+bufptr], rbx
0x180018ac0  xor     edi, edi
0x180018ac2  lea     r13d, [rbx+1]
0x180018ac6  cmp     edi, r13d
0x180018ac9  jge     loc_180018B50
0x180018acf  xor     esi, esi
0x180018ad1  movsxd  r15, edi
0x180018ad4  mov     [rsp+300h+cbSid], esi
0x180018ad8  lea     r12, dword_180062974
0x180018adf  mov     r14d, r13d
0x180018ae2  mov     ecx, [r12+r15*4]; WellKnownSidType
0x180018ae6  lea     r9, [rsp+300h+cbSid]; cbSid
0x180018aeb  mov     r8, rsi; pSid
0x180018aee  xor     edx, edx; DomainSid
0x180018af0  call    cs:__imp_CreateWellKnownSid
0x180018af6  test    eax, eax
0x180018af8  jnz     short loc_180018B39
0x180018afa  test    r14d, r14d
0x180018afd  jz      short loc_180018B1C
0x180018aff  mov     ecx, [rsp+300h+cbSid]
0x180018b03  inc     ecx; cb
0x180018b05  call    cs:__imp_CoTaskMemAlloc
0x180018b0b  mov     rsi, rax
0x180018b0e  test    rax, rax
0x180018b11  jz      loc_180018D05
0x180018b17  xor     r14d, r14d
0x180018b1a  jmp     short loc_180018AE2
0x180018b1c  call    cs:__imp_GetLastError
0x180018b22  mov     ebx, eax
0x180018b24  test    eax, eax
0x180018b26  jle     short loc_180018B31
0x180018b28  movzx   ebx, ax
0x180018b2b  or      ebx, 80070000h
0x180018b31  test    ebx, ebx
0x180018b33  jnz     loc_180018D0A
0x180018b39  lea     rdx, [rsp+300h+var_2A0]
0x180018b3e  mov     qword ptr [rsp+300h+var_2A0], rsi
0x180018b43  call    ?append@?$Array@PEAE@@QEAAXAEBQEAE@Z; Array<uchar *>::append(uchar * const &)
0x180018b48  add     edi, r13d
0x180018b4b  jmp     loc_180018AC6
0x180018b50  xor     r14d, r14d
0x180018b53  lea     rcx, [rsp+300h+var_2B0]
0x180018b58  movsxd  rax, r14d
0x180018b5b  mov     [rsp+300h+peUse], rcx; peUse
0x180018b60  lea     r9, [rsp+300h+ReferencedDomainName]; ReferencedDomainName
0x180018b65  lea     rcx, [rsp+300h+var_2AC]
0x180018b6a  mov     [rsp+300h+cchName], 101h
0x180018b72  mov     [rsp+300h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180018b77  lea     r8, [rsp+300h+cchName]; cchName
0x180018b7c  mov     rcx, cs:?sm_apSid@CCheckGroupMembership@@0V?$Array@PEAE@@A; Array<uchar *> CCheckGroupMembership::sm_apSid
0x180018b83  lea     rdx, [rbp+200h+Name]; Name
0x180018b87  mov     [rsp+300h+var_2AC], 10h
0x180018b8f  mov     [rsp+300h+var_2B0], 0
0x180018b97  mov     rcx, [rcx+rax*8]; Sid
0x180018b9b  call    cs:__imp_LookupAccountSidLocalW
0x180018ba1  test    eax, eax
0x180018ba3  jnz     short loc_180018BC2
0x180018ba5  call    cs:__imp_GetLastError
0x180018bab  mov     ebx, eax
0x180018bad  test    eax, eax
0x180018baf  jle     short loc_180018BBA
0x180018bb1  movzx   ebx, ax
0x180018bb4  or      ebx, 80070000h
0x180018bba  test    ebx, ebx
0x180018bbc  jnz     loc_180018D0A
0x180018bc2  mov     [rsp+300h+resumehandle], 0; resumehandle
0x180018bcb  lea     rax, [rsp+300h+var_2A0]
0x180018bd0  mov     [rsp+300h+totalentries], rax; totalentries
0x180018bd5  lea     r9, [rsp+300h+bufptr]; bufptr
0x180018bda  lea     rax, [rsp+300h+cbSid]
0x180018bdf  mov     [rsp+300h+cbSid], 0
0x180018be7  mov     [rsp+300h+peUse], rax; entriesread
0x180018bec  lea     rdx, [rbp+200h+Name]; localgroupname
0x180018bf0  mov     r8d, r13d; level
0x180018bf3  mov     dword ptr [rsp+300h+cchReferencedDomainName], 0FFFFFFFFh; prefmaxlen
0x180018bfb  xor     ecx, ecx; servername
0x180018bfd  mov     [rsp+300h+var_2A0], 0
0x180018c05  call    cs:__imp_NetLocalGroupGetMembers
0x180018c0b  mov     r12, [rsp+300h+bufptr]
0x180018c10  test    eax, eax
0x180018c12  jz      short loc_180018C31
0x180018c14  call    cs:__imp_GetLastError
0x180018c1a  mov     ebx, eax
0x180018c1c  test    eax, eax
0x180018c1e  jle     short loc_180018C29
0x180018c20  movzx   ebx, ax
0x180018c23  or      ebx, 80070000h
0x180018c29  test    ebx, ebx
0x180018c2b  jnz     loc_180018D0A
0x180018c31  xor     edi, edi
0x180018c33  cmp     edi, [rsp+300h+cbSid]
0x180018c37  jnb     loc_180018CE0
0x180018c3d  lea     rsi, [rdi+rdi*2]
0x180018c41  cmp     dword ptr [r12+rsi*8+8], 2
0x180018c47  jnz     loc_180018CD8
0x180018c4d  mov     rcx, [r12+rsi*8]; pSid
0x180018c51  call    cs:__imp_IsValidSid
0x180018c57  test    eax, eax
0x180018c59  jnz     short loc_180018C78
0x180018c5b  call    cs:__imp_GetLastError
0x180018c61  mov     ebx, eax
0x180018c63  test    eax, eax
0x180018c65  jle     short loc_180018C70
0x180018c67  movzx   ebx, ax
0x180018c6a  or      ebx, 80070000h
0x180018c70  test    ebx, ebx
0x180018c72  jnz     loc_180018D0A
0x180018c78  mov     rcx, [r12+rsi*8]; pSid
0x180018c7c  call    cs:__imp_GetLengthSid
0x180018c82  mov     r13d, eax
0x180018c85  lea     ecx, [rax+1]; cb
0x180018c88  call    cs:__imp_CoTaskMemAlloc
0x180018c8e  mov     r15, rax
0x180018c91  test    rax, rax
0x180018c94  jz      short loc_180018D05
0x180018c96  mov     r8, [r12+rsi*8]; pSourceSid
0x180018c9a  mov     rdx, rax; pDestinationSid
0x180018c9d  mov     ecx, r13d; nDestinationSidLength
0x180018ca0  call    cs:__imp_CopySid
0x180018ca6  test    eax, eax
0x180018ca8  jnz     short loc_180018CC3
0x180018caa  call    cs:__imp_GetLastError
0x180018cb0  mov     ebx, eax
0x180018cb2  test    eax, eax
0x180018cb4  jle     short loc_180018CBF
0x180018cb6  movzx   ebx, ax
0x180018cb9  or      ebx, 80070000h
0x180018cbf  test    ebx, ebx
0x180018cc1  jnz     short loc_180018D0A
0x180018cc3  lea     rdx, [rsp+300h+var_298]
0x180018cc8  mov     [rsp+300h+var_298], r15
0x180018ccd  call    ?append@?$Array@PEAE@@QEAAXAEBQEAE@Z; Array<uchar *>::append(uchar * const &)
0x180018cd2  mov     r13d, 1
0x180018cd8  add     edi, r13d
0x180018cdb  jmp     loc_180018C33
0x180018ce0  mov     rcx, [rsp+300h+bufptr]; Buffer
0x180018ce5  test    rcx, rcx
0x180018ce8  jz      short loc_180018CF7
0x180018cea  call    cs:__imp_NetApiBufferFree
0x180018cf0  xor     ecx, ecx
0x180018cf2  mov     [rsp+300h+bufptr], rcx
0x180018cf7  add     r14d, r13d
0x180018cfa  cmp     r14d, r13d
0x180018cfd  jl      loc_180018B53
0x180018d03  jmp     short loc_180018D0F
0x180018d05  mov     ebx, 8007000Eh
0x180018d0a  mov     rcx, [rsp+300h+bufptr]; Buffer
0x180018d0f  test    rcx, rcx
0x180018d12  jz      short loc_180018D1A
0x180018d14  call    cs:__imp_NetApiBufferFree
0x180018d1a  mov     eax, ebx
0x180018d1c  mov     rcx, [rbp+200h+var_50]
0x180018d23  xor     rcx, rsp; StackCookie
0x180018d26  call    __security_check_cookie
0x180018d2b  add     rsp, 2C8h
0x180018d32  pop     r15
0x180018d34  pop     r14
0x180018d36  pop     r13
0x180018d38  pop     r12
0x180018d3a  pop     rdi
0x180018d3b  pop     rsi
0x180018d3c  pop     rbx
0x180018d3d  pop     rbp
0x180018d3e  retn
```
