# CreateWellKnownSid

- ea: `0x1800b8ad0`
- end: `0x1800b8e09`
- name: `CreateWellKnownSid`
- size: `825`
- prototype: `BOOL __stdcall(WELL_KNOWN_SID_TYPE WellKnownSidType, PSID DomainSid, PSID pSid, DWORD *cbSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800b7f9c`
- `0x1800b8770`

## callees

- `0x18004b9d0`
- `0x1800b8ad0`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800b8b73`
- `ntdll!RtlInitializeSid` at `0x1800b8b73`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8bc4`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8c5d`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8c91`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8cad`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8cc9`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8cee`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8d10`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8df2`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8bc4`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8c5d`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8c91`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8cad`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8cc9`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8cee`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8d10`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8df2`
- `ntdll!RtlLengthRequiredSid` at `0x1800b8b28`
- `ntdll!RtlLengthRequiredSid` at `0x1800b8b28`
- `ntdll!RtlSetLastWin32Error` at `0x1800b8c11`
- `ntdll!RtlSetLastWin32Error` at `0x1800b8c79`
- `ntdll!RtlSetLastWin32Error` at `0x1800b8c11`
- `ntdll!RtlSetLastWin32Error` at `0x1800b8c79`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b8c45`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b8da3`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b8c45`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b8da3`
- `ntdll!RtlValidSid` at `0x1800b8bf8`
- `ntdll!RtlValidSid` at `0x1800b8bf8`
- `ntdll!RtlCopySid` at `0x1800b8c32`
- `ntdll!RtlCopySid` at `0x1800b8c32`

## pseudocode

```c
BOOL __stdcall CreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, PSID DomainSid, PSID pSid, DWORD *cbSid)
{
  ULONG v8; // r14d
  UCHAR v9; // di
  unsigned int v10; // ebp
  ULONG v11; // eax
  DWORD v12; // ecx
  NTSTATUS v13; // eax
  PUCHAR v15; // rax
  PULONG v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  unsigned int v19; // eax
  UCHAR v20; // di
  __int64 v21; // r9

  if ( DomainSid && !RtlValidSid(DomainSid) || !cbSid || WellKnownSidType == WinLogonIdsSid )
    goto LABEL_21;
  v8 = 0;
  if ( WellKnownSidType == WinUserModeDriversSid )
  {
    v9 = 6;
    v10 = 4;
    goto LABEL_6;
  }
  v10 = 0;
LABEL_50:
  v19 = 0;
  v21 = 3LL * v10;
  while ( 1 )
  {
    if ( v19 >= LODWORD(qword_1801A5100[v21]) )
    {
      if ( ++v10 < 0xD )
        goto LABEL_50;
      if ( WellKnownSidType != WinNtAuthoritySid )
        goto LABEL_21;
      v10 = 4;
LABEL_38:
      v9 = 0;
      goto LABEL_6;
    }
    v17 = v19;
    v18 = (&off_1801A50F8)[v21];
    if ( WellKnownSidType == HIDWORD(v18[v17]) )
      break;
    ++v19;
  }
  v8 = v18[v17];
  if ( v10 != 8 )
  {
    if ( v10 == 7 )
    {
LABEL_42:
      v9 = 2;
      goto LABEL_6;
    }
    if ( v10 != 6 )
    {
      v9 = 0;
      switch ( v10 )
      {
        case 0u:
        case 1u:
        case 2u:
        case 3u:
        case 4u:
          goto LABEL_40;
        case 5u:
        case 0xAu:
        case 0xBu:
          goto LABEL_42;
        case 9u:
          v9 = (WellKnownSidType == WinThisOrganizationCertificateSid) + 1;
          break;
        case 0xCu:
          goto LABEL_48;
        default:
          goto LABEL_6;
      }
      goto LABEL_6;
    }
    if ( DomainSid )
    {
      v20 = *RtlSubAuthorityCountSid(DomainSid);
      if ( v20 != 15 )
      {
        v9 = v20 + 1;
        goto LABEL_6;
      }
    }
    goto LABEL_21;
  }
LABEL_40:
  if ( WellKnownSidType == WinNtAuthoritySid )
    goto LABEL_38;
  if ( WellKnownSidType == WinThisOrganizationCertificateSid )
    goto LABEL_42;
LABEL_48:
  v9 = 1;
LABEL_6:
  v11 = RtlLengthRequiredSid(v9);
  v12 = *cbSid;
  *cbSid = v11;
  if ( v12 < v11 )
  {
    RtlSetLastWin32Error(0x7Au);
    return 0;
  }
  if ( !pSid )
  {
LABEL_21:
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  if ( v10 != 12 )
  {
    if ( v10 != 6 )
    {
      switch ( v10 )
      {
        case 0u:
        case 1u:
        case 2u:
        case 3u:
        case 4u:
        case 5u:
        case 7u:
        case 8u:
        case 9u:
        case 0xAu:
        case 0xBu:
          goto LABEL_9;
        default:
          goto LABEL_16;
      }
    }
    v13 = RtlCopySid(v11, pSid, DomainSid);
    if ( v13 >= 0 )
    {
      v15 = RtlSubAuthorityCountSid(pSid);
      ++*v15;
      goto LABEL_16;
    }
    goto LABEL_19;
  }
LABEL_9:
  v13 = RtlInitializeSid(pSid, (PSID_IDENTIFIER_AUTHORITY)&KnownAuthoritiesAndDomains[3 * v10], v9);
  if ( v13 < 0 )
  {
LABEL_19:
    BaseSetLastNTError((unsigned int)v13);
    return 0;
  }
  switch ( v10 )
  {
    case 5u:
      *RtlSubAuthoritySid(pSid, 0) = 32;
      break;
    case 7u:
      *RtlSubAuthoritySid(pSid, 0) = 64;
      break;
    case 9u:
      *RtlSubAuthoritySid(pSid, 0) = 65;
      break;
    case 0xAu:
      *RtlSubAuthoritySid(pSid, 0) = 2;
      break;
    case 0xBu:
      *RtlSubAuthoritySid(pSid, 0) = 3;
      break;
    default:
      if ( WellKnownSidType == WinUserModeDriversSid && v10 == 4 )
      {
        *RtlSubAuthoritySid(pSid, 0) = 84;
        v16 = RtlSubAuthoritySid(pSid, 1u);
        memset_0(v16, 0, 4LL * v9 - 4);
      }
      break;
  }
LABEL_16:
  if ( v9 )
    *RtlSubAuthoritySid(pSid, (unsigned int)v9 - 1) = v8;
  return 1;
}

```

## disassembly

```asm
0x1800b8ad0  push    rbx
0x1800b8ad2  push    rbp
0x1800b8ad3  push    rsi
0x1800b8ad4  push    rdi
0x1800b8ad5  push    r12
0x1800b8ad7  push    r13
0x1800b8ad9  push    r14
0x1800b8adb  push    r15
0x1800b8add  sub     rsp, 28h
0x1800b8ae1  mov     r15, r9
0x1800b8ae4  mov     r12, r8
0x1800b8ae7  mov     r13, rdx
0x1800b8aea  mov     ebx, ecx
0x1800b8aec  test    rdx, rdx
0x1800b8aef  jnz     loc_1800B8BF5
0x1800b8af5  test    r15, r15
0x1800b8af8  jz      loc_1800B8C0C
0x1800b8afe  cmp     ebx, 15h
0x1800b8b01  jz      loc_1800B8C0C
0x1800b8b07  xor     r14d, r14d
0x1800b8b0a  lea     r10, __ImageBase
0x1800b8b11  cmp     ebx, 62h ; 'b'
0x1800b8b14  jnz     loc_1800B8DCC
0x1800b8b1a  mov     dil, 6
0x1800b8b1d  mov     ebp, 4
0x1800b8b22  movzx   esi, dil; jumptable 000000018019FD3F default case, cases 6-8
0x1800b8b26  mov     ecx, esi; SubAuthorityCount
0x1800b8b28  call    cs:__imp_RtlLengthRequiredSid
0x1800b8b2f  nop     dword ptr [rax+rax+00h]
0x1800b8b34  mov     ecx, [r15]
0x1800b8b37  mov     [r15], eax
0x1800b8b3a  cmp     ecx, eax
0x1800b8b3c  jb      loc_1800B8C74
0x1800b8b42  test    r12, r12
0x1800b8b45  jz      loc_1800B8C0C
0x1800b8b4b  cmp     ebp, 0Ch
0x1800b8b4e  jnz     loc_1800B8C21
0x1800b8b54  lea     rdx, __ImageBase
0x1800b8b5b  mov     eax, ebp; jumptable 000000018019FD6E cases 0-5,7-11
0x1800b8b5d  movzx   r8d, dil; SubAuthorityCount
0x1800b8b61  lea     rcx, [rax+rax*2]
0x1800b8b65  lea     rdx, [rdx+rcx*8]
0x1800b8b69  mov     rcx, r12; Sid
0x1800b8b6c  lea     rdx, [rdx+1A50F0h]; IdentifierAuthority
0x1800b8b73  call    cs:__imp_RtlInitializeSid
0x1800b8b7a  nop     dword ptr [rax+rax+00h]
0x1800b8b7f  test    eax, eax
0x1800b8b81  js      short loc_1800B8BEA
0x1800b8b83  cmp     ebp, 5
0x1800b8b86  jz      loc_1800B8C58
0x1800b8b8c  cmp     ebp, 7
0x1800b8b8f  jz      loc_1800B8DED
0x1800b8b95  cmp     ebp, 9
0x1800b8b98  jz      loc_1800B8CC4
0x1800b8b9e  cmp     ebp, 0Ah
0x1800b8ba1  jz      loc_1800B8C8C
0x1800b8ba7  cmp     ebp, 0Bh
0x1800b8baa  jz      loc_1800B8CA8
0x1800b8bb0  cmp     ebx, 62h ; 'b'
0x1800b8bb3  jz      loc_1800B8CE0
0x1800b8bb9  test    dil, dil; jumptable 000000018019FD6E default case, case 6
0x1800b8bbc  jz      short loc_1800B8BD3
0x1800b8bbe  lea     edx, [rsi-1]; SubAuthority
0x1800b8bc1  mov     rcx, r12; Sid
0x1800b8bc4  call    cs:__imp_RtlSubAuthoritySid
0x1800b8bcb  nop     dword ptr [rax+rax+00h]
0x1800b8bd0  mov     [rax], r14d
0x1800b8bd3  mov     eax, 1
0x1800b8bd8  add     rsp, 28h
0x1800b8bdc  pop     r15
0x1800b8bde  pop     r14
0x1800b8be0  pop     r13
0x1800b8be2  pop     r12
0x1800b8be4  pop     rdi
0x1800b8be5  pop     rsi
0x1800b8be6  pop     rbp
0x1800b8be7  pop     rbx
0x1800b8be8  retn
0x1800b8bea  mov     ecx, eax
0x1800b8bec  call    BaseSetLastNTError
0x1800b8bf1  xor     eax, eax
0x1800b8bf3  jmp     short loc_1800B8BD8
0x1800b8bf5  mov     rcx, r13; Sid
0x1800b8bf8  call    cs:__imp_RtlValidSid
0x1800b8bff  nop     dword ptr [rax+rax+00h]
0x1800b8c04  test    al, al
0x1800b8c06  jnz     loc_1800B8AF5
0x1800b8c0c  mov     ecx, 57h ; 'W'; LastError
0x1800b8c11  call    cs:__imp_RtlSetLastWin32Error
0x1800b8c18  nop     dword ptr [rax+rax+00h]
0x1800b8c1d  xor     eax, eax
0x1800b8c1f  jmp     short loc_1800B8BD8
0x1800b8c21  cmp     ebp, 6
0x1800b8c24  jnz     loc_18019FD54
0x1800b8c2a  mov     r8, r13; SourceSid
0x1800b8c2d  mov     rdx, r12; DestinationSid
0x1800b8c30  mov     ecx, eax; DestinationSidLength
0x1800b8c32  call    cs:__imp_RtlCopySid
0x1800b8c39  nop     dword ptr [rax+rax+00h]
0x1800b8c3e  test    eax, eax
0x1800b8c40  js      short loc_1800B8BEA
0x1800b8c42  mov     rcx, r12; Sid
0x1800b8c45  call    cs:__imp_RtlSubAuthorityCountSid
0x1800b8c4c  nop     dword ptr [rax+rax+00h]
0x1800b8c51  inc     byte ptr [rax]
0x1800b8c53  jmp     def_18019FD6E; jumptable 000000018019FD6E default case, case 6
0x1800b8c58  xor     edx, edx; SubAuthority
0x1800b8c5a  mov     rcx, r12; Sid
0x1800b8c5d  call    cs:__imp_RtlSubAuthoritySid
0x1800b8c64  nop     dword ptr [rax+rax+00h]
0x1800b8c69  mov     dword ptr [rax], 20h ; ' '
0x1800b8c6f  jmp     def_18019FD6E; jumptable 000000018019FD6E default case, case 6
0x1800b8c74  mov     ecx, 7Ah ; 'z'; LastError
0x1800b8c79  call    cs:__imp_RtlSetLastWin32Error
0x1800b8c80  nop     dword ptr [rax+rax+00h]
0x1800b8c85  xor     eax, eax
0x1800b8c87  jmp     loc_1800B8BD8
0x1800b8c8c  xor     edx, edx; SubAuthority
0x1800b8c8e  mov     rcx, r12; Sid
0x1800b8c91  call    cs:__imp_RtlSubAuthoritySid
0x1800b8c98  nop     dword ptr [rax+rax+00h]
0x1800b8c9d  mov     dword ptr [rax], 2
0x1800b8ca3  jmp     def_18019FD6E; jumptable 000000018019FD6E default case, case 6
0x1800b8ca8  xor     edx, edx; SubAuthority
0x1800b8caa  mov     rcx, r12; Sid
0x1800b8cad  call    cs:__imp_RtlSubAuthoritySid
0x1800b8cb4  nop     dword ptr [rax+rax+00h]
0x1800b8cb9  mov     dword ptr [rax], 3
0x1800b8cbf  jmp     def_18019FD6E; jumptable 000000018019FD6E default case, case 6
0x1800b8cc4  xor     edx, edx; SubAuthority
0x1800b8cc6  mov     rcx, r12; Sid
0x1800b8cc9  call    cs:__imp_RtlSubAuthoritySid
0x1800b8cd0  nop     dword ptr [rax+rax+00h]
0x1800b8cd5  mov     dword ptr [rax], 41h ; 'A'
0x1800b8cdb  jmp     def_18019FD6E; jumptable 000000018019FD6E default case, case 6
0x1800b8ce0  cmp     ebp, 4
0x1800b8ce3  jnz     def_18019FD6E; jumptable 000000018019FD6E default case, case 6
0x1800b8ce9  xor     edx, edx; SubAuthority
0x1800b8ceb  mov     rcx, r12; Sid
0x1800b8cee  call    cs:__imp_RtlSubAuthoritySid
0x1800b8cf5  nop     dword ptr [rax+rax+00h]
0x1800b8cfa  mov     edx, 1; SubAuthority
0x1800b8cff  lea     rbx, ds:0FFFFFFFFFFFFFFFCh[rsi*4]
0x1800b8d07  mov     rcx, r12; Sid
0x1800b8d0a  mov     dword ptr [rax], 54h ; 'T'
0x1800b8d10  call    cs:__imp_RtlSubAuthoritySid
0x1800b8d17  nop     dword ptr [rax+rax+00h]
0x1800b8d1c  mov     r8, rbx; Size
0x1800b8d1f  xor     edx, edx; Val
0x1800b8d21  mov     rcx, rax; void *
0x1800b8d24  call    memset_0
0x1800b8d29  jmp     def_18019FD6E; jumptable 000000018019FD6E default case, case 6
0x1800b8d30  cmp     eax, r8d
0x1800b8d33  jnb     short loc_1800B8D51
0x1800b8d35  mov     ecx, eax
0x1800b8d37  lea     rdx, ds:0[rcx*8]
0x1800b8d3f  mov     rcx, [r9+r10+1A50F8h]
0x1800b8d47  cmp     ebx, [rdx+rcx+4]
0x1800b8d4b  jz      short loc_1800B8D6E
0x1800b8d4d  inc     eax
0x1800b8d4f  jmp     short loc_1800B8D30
0x1800b8d51  inc     ebp
0x1800b8d53  cmp     ebp, 0Dh
0x1800b8d56  jb      short loc_1800B8DCF
0x1800b8d58  cmp     ebx, 7
0x1800b8d5b  jnz     loc_1800B8C0C
0x1800b8d61  mov     ebp, 4
0x1800b8d66  xor     dil, dil
0x1800b8d69  jmp     def_18019FD3F; jumptable 000000018019FD3F default case, cases 6-8
0x1800b8d6e  mov     r14d, [rdx+rcx]
0x1800b8d72  cmp     ebp, 8
0x1800b8d75  jnz     short loc_1800B8D89
0x1800b8d77  cmp     ebx, 7; jumptable 000000018019FD3F cases 0-4
0x1800b8d7a  jz      short loc_1800B8D66
0x1800b8d7c  cmp     ebx, 52h ; 'R'
0x1800b8d7f  jnz     short loc_1800B8DC4; jumptable 000000018019FD3F case 12
0x1800b8d81  mov     dil, 2; jumptable 000000018019FD3F cases 5,10,11
0x1800b8d84  jmp     def_18019FD3F; jumptable 000000018019FD3F default case, cases 6-8
0x1800b8d89  cmp     ebp, 7
0x1800b8d8c  jz      short loc_1800B8D81; jumptable 000000018019FD3F cases 5,10,11
0x1800b8d8e  cmp     ebp, 6
0x1800b8d91  jnz     loc_18019FD28
0x1800b8d97  test    r13, r13
0x1800b8d9a  jz      loc_1800B8C0C
0x1800b8da0  mov     rcx, r13; Sid
0x1800b8da3  call    cs:__imp_RtlSubAuthorityCountSid
0x1800b8daa  nop     dword ptr [rax+rax+00h]
0x1800b8daf  movzx   edi, byte ptr [rax]
0x1800b8db2  cmp     dil, 0Fh
0x1800b8db6  jz      loc_1800B8C0C
0x1800b8dbc  inc     dil
0x1800b8dbf  jmp     def_18019FD3F; jumptable 000000018019FD3F default case, cases 6-8
0x1800b8dc4  mov     dil, 1; jumptable 000000018019FD3F case 12
0x1800b8dc7  jmp     def_18019FD3F; jumptable 000000018019FD3F default case, cases 6-8
0x1800b8dcc  mov     ebp, r14d
0x1800b8dcf  mov     ecx, ebp
0x1800b8dd1  mov     eax, r14d
0x1800b8dd4  lea     rdx, [rcx+rcx*2]
0x1800b8dd8  lea     r9, ds:0[rdx*8]
0x1800b8de0  mov     r8d, [r9+r10+1A5100h]
0x1800b8de8  jmp     loc_1800B8D30
0x1800b8ded  xor     edx, edx; SubAuthority
0x1800b8def  mov     rcx, r12; Sid
0x1800b8df2  call    cs:__imp_RtlSubAuthoritySid
0x1800b8df9  nop     dword ptr [rax+rax+00h]
0x1800b8dfe  mov     dword ptr [rax], 40h ; '@'
0x1800b8e04  jmp     def_18019FD6E; jumptable 000000018019FD6E default case, case 6
0x18019fd28  xor     dil, dil
0x18019fd2b  cmp     ebp, 0Ch; switch 13 cases
0x18019fd2e  ja      def_18019FD3F; jumptable 000000018019FD3F default case, cases 6-8
0x18019fd34  mov     eax, ds:(jpt_18019FD3F - 180000000h)[r10+rbp*4]
0x18019fd3c  add     rax, r10
0x18019fd3f  jmp     rax; switch jump
0x18019fd45  cmp     ebx, 52h ; 'R'; jumptable 000000018019FD3F case 9
0x18019fd48  setz    dil
0x18019fd4c  inc     dil
0x18019fd4f  jmp     def_18019FD3F; jumptable 000000018019FD3F default case, cases 6-8
0x18019fd54  cmp     ebp, 0Bh; switch 12 cases
0x18019fd57  ja      def_18019FD6E; jumptable 000000018019FD6E default case, case 6
0x18019fd5d  lea     rdx, __ImageBase
0x18019fd64  mov     eax, ds:(jpt_18019FD6E - 180000000h)[rdx+rbp*4]
0x18019fd6b  add     rax, rdx
0x18019fd6e  jmp     rax; switch jump
```
