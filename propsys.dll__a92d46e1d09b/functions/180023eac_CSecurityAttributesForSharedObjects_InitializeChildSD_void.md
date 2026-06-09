# CSecurityAttributesForSharedObjects::_InitializeChildSD(void)

- ea: `0x180023eac`
- end: `0x180024231`
- name: `?_InitializeChildSD@CSecurityAttributesForSharedObjects@@AEAAJXZ`
- size: `901`
- prototype: `__int64 __fastcall(CSecurityAttributesForSharedObjects *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022070`
- `0x180022348`

## callees

- `0x180023eac`
- `0x180024418`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002400e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002415f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002400e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002415f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800241d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023fc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180023fc0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023fd2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023fd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024071`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024071`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023edd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024023`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024086`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023edd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024023`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024086`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024126`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024197`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024126`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024197`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800241ea`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180023efc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180023efc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023fa6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023fb1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180024062`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023fa6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023fb1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180024062`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180024143`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180024143`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023ffb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002404e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023ffb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002404e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800240a4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800240a4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800240c9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800240f2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180024110`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800240c9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800240f2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180024110`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023f44`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023f44`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023f89`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180023f89`

## pseudocode

```c
__int64 __fastcall CSecurityAttributesForSharedObjects::_InitializeChildSD(CSecurityAttributesForSharedObjects *this)
{
  HLOCAL v2; // rax
  signed int Error; // esi
  PSID *v5; // r13
  PSID v6; // r12
  PSID *v7; // r15
  PSID v8; // rdi
  DWORD LengthSid; // ebx
  DWORD v10; // edi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  struct _ACL *v13; // rax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  DWORD ReturnLength; // [rsp+60h] [rbp-9h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-1h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+7h] BYREF

  v2 = LocalAlloc(0, 0x28u);
  *((_QWORD *)this + 2) = v2;
  if ( v2 )
  {
    if ( InitializeSecurityDescriptor(v2, 1u) || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      *(_DWORD *)pIdentifierAuthority.Value = 0;
      *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, (PSID *)this + 7)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        v5 = (PSID *)((char *)this + 64);
        if ( ConvertStringSidToSidW(
               L"S-1-15-3-1024-1502825166-1963708345-2616377461-2562897074-4192028372-3968301570-1997628692-1435953622",
               (PSID *)this + 8) )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
            return (unsigned int)Error;
        }
        v6 = 0;
        v7 = 0;
        v8 = *v5;
        LengthSid = GetLengthSid(*((PSID *)this + 7));
        TokenHandle = 0;
        v10 = LengthSid + GetLengthSid(v8) + 24;
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        {
          ReturnLength = 0;
          if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength) )
          {
            Error = -2147418113;
          }
          else
          {
            LastError = GetLastError();
            if ( LastError == 122 )
            {
              v7 = (PSID *)LocalAlloc(0x40u, ReturnLength);
              if ( v7 )
              {
                if ( GetTokenInformation(TokenHandle, TokenUser, v7, ReturnLength, &ReturnLength) )
                {
                  v6 = *v7;
                  v10 += GetLengthSid(*v7) + 8;
                }
                else
                {
                  v15 = GetLastError();
                  Error = v15;
                  if ( v15 > 0 )
                    Error = (unsigned __int16)v15 | 0x80070000;
                  LocalFree(v7);
                  v7 = 0;
                }
              }
              else
              {
                Error = -2147024882;
              }
            }
            else if ( LastError > 0 )
            {
              Error = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              Error = LastError;
            }
          }
          CloseHandle(TokenHandle);
        }
        else
        {
          v14 = GetLastError();
          Error = v14;
          if ( v14 > 0 )
            Error = (unsigned __int16)v14 | 0x80070000;
        }
        if ( Error >= 0 )
        {
          v13 = (struct _ACL *)LocalAlloc(0x40u, v10);
          *((_QWORD *)this + 3) = v13;
          if ( v13 )
          {
            if ( !InitializeAcl(v13, v10, 2u)
              || v6 && !AddAccessAllowedAce(*((PACL *)this + 3), 2u, 0x101F0000u, v6)
              || (*(_BYTE *)this & 2) != 0
              && (!AddAccessAllowedAce(*((PACL *)this + 3), 2u, 0x80020000, *((PSID *)this + 7))
               || !AddAccessAllowedAce(*((PACL *)this + 3), 2u, 0x80020000, *v5)) )
            {
              v16 = GetLastError();
              Error = v16;
              if ( v16 > 0 )
                Error = (unsigned __int16)v16 | 0x80070000;
              LocalFree(*((HLOCAL *)this + 3));
              *((_QWORD *)this + 3) = 0;
            }
          }
          else
          {
            Error = -2147024882;
          }
        }
        if ( v7 )
          LocalFree(v7);
        if ( Error >= 0 )
        {
          if ( SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 2), 1, *((PACL *)this + 3), 0) )
            return 0;
          else
            return (unsigned int)ResultFromKnownLastError();
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180023eac  push    rbp
0x180023eae  push    rbx
0x180023eaf  push    rsi
0x180023eb0  push    rdi
0x180023eb1  push    r12
0x180023eb3  push    r13
0x180023eb5  push    r14
0x180023eb7  push    r15
0x180023eb9  lea     rbp, [rsp-1Fh]
0x180023ebe  sub     rsp, 88h
0x180023ec5  mov     rax, cs:__security_cookie
0x180023ecc  xor     rax, rsp
0x180023ecf  mov     [rbp+57h+var_48], rax
0x180023ed3  mov     r14, rcx
0x180023ed6  mov     edx, 28h ; '('; uBytes
0x180023edb  xor     ecx, ecx; uFlags
0x180023edd  call    cs:__imp_LocalAlloc
0x180023ee3  xor     edi, edi
0x180023ee5  mov     [r14+10h], rax
0x180023ee9  test    rax, rax
0x180023eec  jz      loc_1800241FD
0x180023ef2  lea     r15d, [rdi+1]
0x180023ef6  mov     rcx, rax; pSecurityDescriptor
0x180023ef9  mov     edx, r15d; dwRevision
0x180023efc  call    cs:__imp_InitializeSecurityDescriptor
0x180023f02  test    eax, eax
0x180023f04  jz      loc_180024207
0x180023f0a  mov     r8d, 2; nSubAuthority0
0x180023f10  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x180023f13  lea     rbx, [r14+38h]
0x180023f17  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 0F00h
0x180023f1d  mov     [rsp+0C0h+pSid], rbx; pSid
0x180023f22  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180023f26  mov     [rsp+0C0h+nSubAuthority7], edi; nSubAuthority7
0x180023f2a  mov     r9d, r15d; nSubAuthority1
0x180023f2d  mov     [rsp+0C0h+nSubAuthority6], edi; nSubAuthority6
0x180023f31  mov     dl, r8b; nSubAuthorityCount
0x180023f34  mov     [rsp+0C0h+nSubAuthority5], edi; nSubAuthority5
0x180023f38  mov     [rsp+0C0h+nSubAuthority4], edi; nSubAuthority4
0x180023f3c  mov     [rsp+0C0h+nSubAuthority3], edi; nSubAuthority3
0x180023f40  mov     [rsp+0C0h+nSubAuthority2], edi; nSubAuthority2
0x180023f44  call    cs:__imp_AllocateAndInitializeSid
0x180023f4a  test    eax, eax
0x180023f4c  jnz     short loc_180023F7B
0x180023f4e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180023f53  mov     esi, eax
0x180023f55  test    eax, eax
0x180023f57  jns     short loc_180023F7B
0x180023f59  mov     eax, esi
0x180023f5b  mov     rcx, [rbp+57h+var_48]
0x180023f5f  xor     rcx, rsp; StackCookie
0x180023f62  call    __security_check_cookie
0x180023f67  add     rsp, 88h
0x180023f6e  pop     r15
0x180023f70  pop     r14
0x180023f72  pop     r13
0x180023f74  pop     r12
0x180023f76  pop     rdi
0x180023f77  pop     rsi
0x180023f78  pop     rbx
0x180023f79  pop     rbp
0x180023f7a  retn
0x180023f7b  lea     r13, [r14+40h]
0x180023f7f  mov     rdx, r13; Sid
0x180023f82  lea     rcx, StringSid; "S-1-15-3-1024-1502825166-1963708345-261"...
0x180023f89  call    cs:__imp_ConvertStringSidToSidW
0x180023f8f  test    eax, eax
0x180023f91  jz      loc_1800241A5
0x180023f97  mov     esi, edi
0x180023f99  mov     rcx, [rbx]; pSid
0x180023f9c  mov     r12, rdi
0x180023f9f  mov     r15, rdi
0x180023fa2  mov     rdi, [r13+0]
0x180023fa6  call    cs:__imp_GetLengthSid
0x180023fac  mov     rcx, rdi; pSid
0x180023faf  mov     ebx, eax
0x180023fb1  call    cs:__imp_GetLengthSid
0x180023fb7  mov     [rbp+57h+TokenHandle], r15
0x180023fbb  lea     edi, [rax+18h]
0x180023fbe  add     edi, ebx
0x180023fc0  call    cs:__imp_GetCurrentProcess
0x180023fc6  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180023fca  mov     edx, 8; DesiredAccess
0x180023fcf  mov     rcx, rax; ProcessHandle
0x180023fd2  call    cs:__imp_OpenProcessToken
0x180023fd8  test    eax, eax
0x180023fda  jz      loc_18002415F
0x180023fe0  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180023fe4  lea     rax, [rbp+57h+ReturnLength]
0x180023fe8  xor     r9d, r9d; TokenInformationLength
0x180023feb  mov     [rbp+57h+ReturnLength], r12d
0x180023fef  xor     r8d, r8d; TokenInformation
0x180023ff2  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; ReturnLength
0x180023ff7  lea     edx, [r9+1]; TokenInformationClass
0x180023ffb  call    cs:__imp_GetTokenInformation
0x180024001  mov     ebx, 80070000h
0x180024006  test    eax, eax
0x180024008  jnz     loc_18002417E
0x18002400e  call    cs:__imp_GetLastError
0x180024014  cmp     eax, 7Ah ; 'z'
0x180024017  jnz     loc_1800241C0
0x18002401d  mov     edx, [rbp+57h+ReturnLength]; uBytes
0x180024020  lea     ecx, [rax-3Ah]; uFlags
0x180024023  call    cs:__imp_LocalAlloc
0x180024029  mov     r15, rax
0x18002402c  test    rax, rax
0x18002402f  jz      loc_18002421B
0x180024035  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x180024039  lea     rax, [rbp+57h+ReturnLength]
0x18002403d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180024041  mov     r8, r15; TokenInformation
0x180024044  mov     edx, 1; TokenInformationClass
0x180024049  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; ReturnLength
0x18002404e  call    cs:__imp_GetTokenInformation
0x180024054  test    eax, eax
0x180024056  jz      loc_180024188
0x18002405c  mov     r12, [r15]
0x18002405f  mov     rcx, r12; pSid
0x180024062  call    cs:__imp_GetLengthSid
0x180024068  add     edi, 8
0x18002406b  add     edi, eax
0x18002406d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180024071  call    cs:__imp_CloseHandle
0x180024077  test    esi, esi
0x180024079  js      loc_18002411E
0x18002407f  mov     edx, edi; uBytes
0x180024081  mov     ecx, 40h ; '@'; uFlags
0x180024086  call    cs:__imp_LocalAlloc
0x18002408c  mov     [r14+18h], rax
0x180024090  test    rax, rax
0x180024093  jz      loc_180024158
0x180024099  mov     r8d, 2; dwAclRevision
0x18002409f  mov     edx, edi; nAclLength
0x1800240a1  mov     rcx, rax; pAcl
0x1800240a4  call    cs:__imp_InitializeAcl
0x1800240aa  test    eax, eax
0x1800240ac  jz      loc_1800241D5
0x1800240b2  test    r12, r12
0x1800240b5  jz      short loc_1800240D7
0x1800240b7  mov     rcx, [r14+18h]; pAcl
0x1800240bb  mov     r9, r12; pSid
0x1800240be  mov     edx, 2; dwAceRevision
0x1800240c3  mov     r8d, 101F0000h; AccessMask
0x1800240c9  call    cs:__imp_AddAccessAllowedAce
0x1800240cf  test    eax, eax
0x1800240d1  jz      loc_1800241D5
0x1800240d7  test    byte ptr [r14], 2
0x1800240db  jz      short loc_18002411E
0x1800240dd  mov     r9, [r14+38h]; pSid
0x1800240e1  mov     edi, 80020000h
0x1800240e6  mov     rcx, [r14+18h]; pAcl
0x1800240ea  mov     r8d, edi; AccessMask
0x1800240ed  mov     edx, 2; dwAceRevision
0x1800240f2  call    cs:__imp_AddAccessAllowedAce
0x1800240f8  test    eax, eax
0x1800240fa  jz      loc_1800241D5
0x180024100  mov     r9, [r13+0]; pSid
0x180024104  mov     r8d, edi; AccessMask
0x180024107  mov     rcx, [r14+18h]; pAcl
0x18002410b  mov     edx, 2; dwAceRevision
0x180024110  call    cs:__imp_AddAccessAllowedAce
0x180024116  test    eax, eax
0x180024118  jz      loc_1800241D5
0x18002411e  test    r15, r15
0x180024121  jz      short loc_18002412C
0x180024123  mov     rcx, r15; hMem
0x180024126  call    cs:__imp_LocalFree
0x18002412c  test    esi, esi
0x18002412e  js      loc_180023F59
0x180024134  mov     r8, [r14+18h]; pDacl
0x180024138  xor     r9d, r9d; bDaclDefaulted
0x18002413b  mov     rcx, [r14+10h]; pSecurityDescriptor
0x18002413f  lea     edx, [r9+1]; bDaclPresent
0x180024143  call    cs:__imp_SetSecurityDescriptorDacl
0x180024149  test    eax, eax
0x18002414b  jz      loc_180024225
0x180024151  xor     esi, esi
0x180024153  jmp     loc_180023F59
0x180024158  mov     esi, 8007000Eh
0x18002415d  jmp     short loc_18002411E
0x18002415f  call    cs:__imp_GetLastError
0x180024165  mov     esi, eax
0x180024167  mov     ebx, 80070000h
0x18002416c  test    eax, eax
0x18002416e  jle     loc_180024077
0x180024174  movzx   esi, ax
0x180024177  or      esi, ebx
0x180024179  jmp     loc_180024077
0x18002417e  mov     esi, 8000FFFFh
0x180024183  jmp     loc_18002406D
0x180024188  call    cs:__imp_GetLastError
0x18002418e  mov     esi, eax
0x180024190  test    eax, eax
0x180024192  jg      short loc_1800241B9
0x180024194  mov     rcx, r15; hMem
0x180024197  call    cs:__imp_LocalFree
0x18002419d  xor     r15d, r15d
0x1800241a0  jmp     loc_18002406D
0x1800241a5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800241aa  mov     esi, eax
0x1800241ac  test    eax, eax
0x1800241ae  jns     loc_180023F99
0x1800241b4  jmp     loc_180023F59
0x1800241b9  movzx   esi, ax
0x1800241bc  or      esi, ebx
0x1800241be  jmp     short loc_180024194
0x1800241c0  test    eax, eax
0x1800241c2  jg      short loc_1800241CB
0x1800241c4  mov     esi, eax
0x1800241c6  jmp     loc_18002406D
0x1800241cb  movzx   esi, ax
0x1800241ce  or      esi, ebx
0x1800241d0  jmp     loc_18002406D
0x1800241d5  call    cs:__imp_GetLastError
0x1800241db  mov     esi, eax
0x1800241dd  test    eax, eax
0x1800241df  jle     short loc_1800241E6
0x1800241e1  movzx   esi, ax
0x1800241e4  or      esi, ebx
0x1800241e6  mov     rcx, [r14+18h]; hMem
0x1800241ea  call    cs:__imp_LocalFree
0x1800241f0  mov     qword ptr [r14+18h], 0
0x1800241f8  jmp     loc_18002411E
0x1800241fd  mov     esi, 8007000Eh
0x180024202  jmp     loc_180023F59
0x180024207  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002420c  mov     esi, eax
0x18002420e  test    eax, eax
0x180024210  js      loc_180023F59
0x180024216  jmp     loc_180023F0A
0x18002421b  mov     esi, 8007000Eh
0x180024220  jmp     loc_18002406D
0x180024225  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002422a  mov     esi, eax
0x18002422c  jmp     loc_180023F59
```
