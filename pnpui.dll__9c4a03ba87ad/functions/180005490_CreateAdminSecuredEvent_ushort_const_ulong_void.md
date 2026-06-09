# CreateAdminSecuredEvent(ushort const *,ulong,void * *)

- ea: `0x180005490`
- end: `0x1800056ee`
- name: `?CreateAdminSecuredEvent@@YAKPEBGKPEAPEAX@Z`
- size: `606`
- prototype: `__int64 __fastcall(LPCWSTR lpName, __int64, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007080`

## callees

- `0x180005490`
- `0x18000cd10`

## import_xrefs

- `msvcrt!malloc` at `0x18000559b`
- `msvcrt!malloc` at `0x18000559b`
- `msvcrt!free` at `0x1800056c3`
- `msvcrt!free` at `0x1800056c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000552e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000567d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000552e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000567d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180005524`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180005574`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180005524`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180005574`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800056a6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800056b5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800056a6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800056b5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180005620`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180005620`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800055bc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800055bc`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800055e3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180005609`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800055e3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180005609`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005582`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000558e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005582`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000558e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000563c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000563c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000566b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000566b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000568f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000568f`

## pseudocode

```c
__int64 __fastcall CreateAdminSecuredEvent(LPCWSTR lpName, __int64 a2, void **a3)
{
  struct _ACL *v5; // rdi
  DWORD LastError; // ebx
  DWORD LengthSid; // ebx
  DWORD v8; // ebx
  struct _ACL *v9; // rax
  HANDLE v10; // rsi
  PSID pSid; // [rsp+60h] [rbp-29h] BYREF
  PSID v13; // [rsp+68h] [rbp-21h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+70h] [rbp-19h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+1Fh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *a3 = 0;
  v16 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v5 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  pSid = 0;
  v13 = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v13) )
  {
    goto LABEL_2;
  }
  LengthSid = GetLengthSid(pSid);
  v8 = GetLengthSid(v13) + 24 + LengthSid;
  v9 = (struct _ACL *)malloc(v8);
  v5 = v9;
  if ( !v9 )
  {
    LastError = 8;
    goto LABEL_15;
  }
  if ( !InitializeAcl(v9, v8, 2u)
    || !AddAccessAllowedAceEx(v5, 2u, 0, 0x1F0003u, pSid)
    || !AddAccessAllowedAceEx(v5, 2u, 0, 2u, v13)
    || !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v5, 0)
    || (EventAttributes.nLength = 24,
        EventAttributes.bInheritHandle = 0,
        EventAttributes.lpSecurityDescriptor = pSecurityDescriptor,
        (v10 = CreateEventW(&EventAttributes, 1, 0, lpName)) == 0) )
  {
LABEL_2:
    LastError = GetLastError();
    goto LABEL_15;
  }
  LastError = 183;
  if ( GetLastError() == 183 )
  {
    CloseHandle(v10);
  }
  else
  {
    LastError = 0;
    *a3 = v10;
  }
LABEL_15:
  if ( pSid )
    FreeSid(pSid);
  if ( v13 )
    FreeSid(v13);
  if ( v5 )
    free(v5);
  return LastError;
}

```

## disassembly

```asm
0x180005490  mov     [rsp-8+arg_8], rbx
0x180005495  push    rbp
0x180005496  push    rsi
0x180005497  push    rdi
0x180005498  push    r14
0x18000549a  push    r15
0x18000549c  lea     rbp, [rsp-37h]
0x1800054a1  sub     rsp, 0C0h
0x1800054a8  mov     rax, cs:__security_cookie
0x1800054af  xor     rax, rsp
0x1800054b2  mov     [rbp+57h+var_28], rax
0x1800054b6  xor     r15d, r15d
0x1800054b9  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800054bf  xor     eax, eax
0x1800054c1  mov     [r8], r15
0x1800054c4  xorps   xmm0, xmm0
0x1800054c7  mov     [rbp+57h+var_38], rax
0x1800054cb  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], rax
0x1800054cf  mov     r14, r8
0x1800054d2  lea     rax, [rbp+57h+var_80]
0x1800054d6  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x1800054da  mov     [rsp+0E0h+pSid], rax; pSid
0x1800054df  lea     r8d, [r15+12h]; nSubAuthority0
0x1800054e3  mov     [rsp+0E0h+nSubAuthority7], r15d; nSubAuthority7
0x1800054e8  mov     rsi, rcx
0x1800054eb  mov     [rsp+0E0h+nSubAuthority6], r15d; nSubAuthority6
0x1800054f0  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800054f4  mov     [rsp+0E0h+nSubAuthority5], r15d; nSubAuthority5
0x1800054f9  xor     r9d, r9d; nSubAuthority1
0x1800054fc  mov     [rsp+0E0h+nSubAuthority4], r15d; nSubAuthority4
0x180005501  mov     dl, 1; nSubAuthorityCount
0x180005503  mov     [rsp+0E0h+nSubAuthority3], r15d; nSubAuthority3
0x180005508  mov     edi, r15d
0x18000550b  mov     [rsp+0E0h+nSubAuthority2], r15d; nSubAuthority2
0x180005510  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180005514  mov     [rbp+57h+var_80], r15
0x180005518  movups  [rbp+57h+var_48], xmm0
0x18000551c  mov     [rbp+57h+var_78], r15
0x180005520  movups  xmmword ptr [rbp+57h+EventAttributes.nLength], xmm0
0x180005524  call    cs:__imp_AllocateAndInitializeSid
0x18000552a  test    eax, eax
0x18000552c  jnz     short loc_18000553B
0x18000552e  call    cs:__imp_GetLastError
0x180005534  mov     ebx, eax
0x180005536  jmp     loc_18000569D
0x18000553b  lea     rax, [rbp+57h+var_78]
0x18000553f  mov     r9d, 220h; nSubAuthority1
0x180005545  mov     [rsp+0E0h+pSid], rax; pSid
0x18000554a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000554e  mov     [rsp+0E0h+nSubAuthority7], r15d; nSubAuthority7
0x180005553  mov     r8d, 20h ; ' '; nSubAuthority0
0x180005559  mov     [rsp+0E0h+nSubAuthority6], r15d; nSubAuthority6
0x18000555e  mov     dl, 2; nSubAuthorityCount
0x180005560  mov     [rsp+0E0h+nSubAuthority5], r15d; nSubAuthority5
0x180005565  mov     [rsp+0E0h+nSubAuthority4], r15d; nSubAuthority4
0x18000556a  mov     [rsp+0E0h+nSubAuthority3], r15d; nSubAuthority3
0x18000556f  mov     [rsp+0E0h+nSubAuthority2], r15d; nSubAuthority2
0x180005574  call    cs:__imp_AllocateAndInitializeSid
0x18000557a  test    eax, eax
0x18000557c  jz      short loc_18000552E
0x18000557e  mov     rcx, [rbp+57h+var_80]; pSid
0x180005582  call    cs:__imp_GetLengthSid
0x180005588  mov     rcx, [rbp+57h+var_78]; pSid
0x18000558c  mov     ebx, eax
0x18000558e  call    cs:__imp_GetLengthSid
0x180005594  add     eax, 18h
0x180005597  add     ebx, eax
0x180005599  mov     ecx, ebx; Size
0x18000559b  call    cs:__imp_malloc
0x1800055a1  mov     rdi, rax
0x1800055a4  test    rax, rax
0x1800055a7  jnz     short loc_1800055B1
0x1800055a9  lea     ebx, [rax+8]
0x1800055ac  jmp     loc_18000569D
0x1800055b1  mov     r8d, 2; dwAclRevision
0x1800055b7  mov     edx, ebx; nAclLength
0x1800055b9  mov     rcx, rdi; pAcl
0x1800055bc  call    cs:__imp_InitializeAcl
0x1800055c2  test    eax, eax
0x1800055c4  jz      loc_18000552E
0x1800055ca  mov     rax, [rbp+57h+var_80]
0x1800055ce  xor     r8d, r8d; AceFlags
0x1800055d1  mov     r9d, 1F0003h; AccessMask
0x1800055d7  mov     qword ptr [rsp+0E0h+nSubAuthority2], rax; pSid
0x1800055dc  mov     rcx, rdi; pAcl
0x1800055df  lea     edx, [r8+2]; dwAceRevision
0x1800055e3  call    cs:__imp_AddAccessAllowedAceEx
0x1800055e9  test    eax, eax
0x1800055eb  jz      loc_18000552E
0x1800055f1  mov     rax, [rbp+57h+var_78]
0x1800055f5  mov     r9d, 2; AccessMask
0x1800055fb  mov     edx, r9d; dwAceRevision
0x1800055fe  mov     qword ptr [rsp+0E0h+nSubAuthority2], rax; pSid
0x180005603  xor     r8d, r8d; AceFlags
0x180005606  mov     rcx, rdi; pAcl
0x180005609  call    cs:__imp_AddAccessAllowedAceEx
0x18000560f  test    eax, eax
0x180005611  jz      loc_18000552E
0x180005617  mov     edx, 1; dwRevision
0x18000561c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180005620  call    cs:__imp_InitializeSecurityDescriptor
0x180005626  test    eax, eax
0x180005628  jz      loc_18000552E
0x18000562e  xor     r9d, r9d; bDaclDefaulted
0x180005631  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180005635  mov     r8, rdi; pDacl
0x180005638  lea     edx, [r9+1]; bDaclPresent
0x18000563c  call    cs:__imp_SetSecurityDescriptorDacl
0x180005642  test    eax, eax
0x180005644  jz      loc_18000552E
0x18000564a  xor     r8d, r8d; bInitialState
0x18000564d  mov     [rbp+57h+EventAttributes.nLength], 18h
0x180005654  lea     rax, [rbp+57h+pSecurityDescriptor]
0x180005658  mov     [rbp+57h+EventAttributes.bInheritHandle], r15d
0x18000565c  mov     r9, rsi; lpName
0x18000565f  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x180005663  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x180005667  lea     edx, [r8+1]; bManualReset
0x18000566b  call    cs:__imp_CreateEventW
0x180005671  mov     rsi, rax
0x180005674  test    rax, rax
0x180005677  jz      loc_18000552E
0x18000567d  call    cs:__imp_GetLastError
0x180005683  mov     ebx, 0B7h
0x180005688  cmp     eax, ebx
0x18000568a  jnz     short loc_180005697
0x18000568c  mov     rcx, rsi; hObject
0x18000568f  call    cs:__imp_CloseHandle
0x180005695  jmp     short loc_18000569D
0x180005697  mov     ebx, r15d
0x18000569a  mov     [r14], rsi
0x18000569d  mov     rcx, [rbp+57h+var_80]; pSid
0x1800056a1  test    rcx, rcx
0x1800056a4  jz      short loc_1800056AC
0x1800056a6  call    cs:__imp_FreeSid
0x1800056ac  mov     rcx, [rbp+57h+var_78]; pSid
0x1800056b0  test    rcx, rcx
0x1800056b3  jz      short loc_1800056BB
0x1800056b5  call    cs:__imp_FreeSid
0x1800056bb  test    rdi, rdi
0x1800056be  jz      short loc_1800056C9
0x1800056c0  mov     rcx, rdi; Block
0x1800056c3  call    cs:__imp_free
0x1800056c9  mov     eax, ebx
0x1800056cb  mov     rcx, [rbp+57h+var_28]
0x1800056cf  xor     rcx, rsp; StackCookie
0x1800056d2  call    __security_check_cookie
0x1800056d7  mov     rbx, [rsp+0E0h+arg_8]
0x1800056df  add     rsp, 0C0h
0x1800056e6  pop     r15
0x1800056e8  pop     r14
0x1800056ea  pop     rdi
0x1800056eb  pop     rsi
0x1800056ec  pop     rbp
0x1800056ed  retn
```
