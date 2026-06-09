# EqualDomainSid

- ea: `0x1800b8770`
- end: `0x1800b896b`
- name: `EqualDomainSid`
- size: `507`
- prototype: `BOOL __stdcall(PSID pSid1, PSID pSid2, BOOL *pfEqual)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800b8770`
- `0x1800b8980`
- `0x1800b8ad0`
- `0x1800b8e10`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x1800b888e`
- `ntdll!RtlSubAuthoritySid` at `0x1800b891a`
- `ntdll!RtlSubAuthoritySid` at `0x1800b888e`
- `ntdll!RtlSubAuthoritySid` at `0x1800b891a`
- `ntdll!RtlSetLastWin32Error` at `0x1800b893a`
- `ntdll!RtlSetLastWin32Error` at `0x1800b893a`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b8874`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b8904`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b8874`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b8904`
- `ntdll!RtlValidSid` at `0x1800b879b`
- `ntdll!RtlValidSid` at `0x1800b87b2`
- `ntdll!RtlValidSid` at `0x1800b879b`
- `ntdll!RtlValidSid` at `0x1800b87b2`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800b8846`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800b88da`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800b8846`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800b88da`

## pseudocode

```c
BOOL __stdcall EqualDomainSid(PSID pSid1, PSID pSid2, BOOL *pfEqual)
{
  _BYTE *v6; // rdi
  PSID_IDENTIFIER_AUTHORITY v7; // rax
  int v8; // ecx
  _BYTE *v9; // rdx
  PSID_IDENTIFIER_AUTHORITY v11; // rax
  int v12; // ecx
  ULONG v13; // ecx
  DWORD cbSid[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pDomainSid[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[80]; // [rsp+D0h] [rbp-30h] BYREF

  if ( !RtlValidSid(pSid1) || !RtlValidSid(pSid2) )
  {
    v13 = 1337;
LABEL_23:
    RtlSetLastWin32Error(v13);
    return 0;
  }
  if ( !pfEqual )
  {
    v13 = 87;
    goto LABEL_23;
  }
  if ( *(_BYTE *)pSid1 != *(_BYTE *)pSid2 )
  {
    v13 = 1306;
    goto LABEL_23;
  }
  cbSid[0] = 68;
  if ( CreateWellKnownSid(WinBuiltinDomainSid, 0, pSid, cbSid) )
  {
    cbSid[0] = 68;
    if ( GetWindowsAccountDomainSid(pSid1, pDomainSid, cbSid) )
    {
      v6 = pDomainSid;
    }
    else
    {
      v11 = RtlIdentifierAuthoritySid(pSid1);
      v12 = *(_DWORD *)v11->Value;
      if ( !*(_DWORD *)v11->Value )
        v12 = *(unsigned __int16 *)&v11->Value[4] - 1280;
      if ( v12 || !*RtlSubAuthorityCountSid(pSid1) || *RtlSubAuthoritySid(pSid1, 0) != 32 )
      {
LABEL_25:
        v13 = 1258;
        goto LABEL_23;
      }
      v6 = pSid;
    }
    cbSid[0] = 68;
    if ( GetWindowsAccountDomainSid(pSid2, v17, cbSid) )
    {
      v9 = v17;
      goto LABEL_15;
    }
    v7 = RtlIdentifierAuthoritySid(pSid2);
    v8 = *(_DWORD *)v7->Value;
    if ( !*(_DWORD *)v7->Value )
      v8 = *(unsigned __int16 *)&v7->Value[4] - 1280;
    if ( !v8 && *RtlSubAuthorityCountSid(pSid2) && *RtlSubAuthoritySid(pSid2, 0) == 32 )
    {
      v9 = pSid;
LABEL_15:
      *pfEqual = EqualSid(v6, v9);
      return 1;
    }
    goto LABEL_25;
  }
  return 0;
}

```

## disassembly

```asm
0x1800b8770  mov     [rsp-8+arg_18], rbx
0x1800b8775  push    rbp
0x1800b8776  push    rsi
0x1800b8777  push    rdi
0x1800b8778  lea     rbp, [rsp-30h]
0x1800b877d  sub     rsp, 130h
0x1800b8784  mov     rax, cs:__security_cookie
0x1800b878b  xor     rax, rsp
0x1800b878e  mov     [rbp+40h+var_20], rax
0x1800b8792  mov     rsi, r8
0x1800b8795  mov     rbx, rdx
0x1800b8798  mov     rdi, rcx
0x1800b879b  call    cs:__imp_RtlValidSid
0x1800b87a2  nop     dword ptr [rax+rax+00h]
0x1800b87a7  test    al, al
0x1800b87a9  jz      loc_1800B8935
0x1800b87af  mov     rcx, rbx; Sid
0x1800b87b2  call    cs:__imp_RtlValidSid
0x1800b87b9  nop     dword ptr [rax+rax+00h]
0x1800b87be  test    al, al
0x1800b87c0  jz      loc_1800B8935
0x1800b87c6  test    rsi, rsi
0x1800b87c9  jz      loc_1800B895D
0x1800b87cf  mov     al, [rbx]
0x1800b87d1  cmp     [rdi], al
0x1800b87d3  jnz     loc_1800B8964
0x1800b87d9  xor     edx, edx; DomainSid
0x1800b87db  mov     [rsp+140h+cbSid], 44h ; 'D'
0x1800b87e3  lea     r9, [rsp+140h+cbSid]; cbSid
0x1800b87e8  lea     r8, [rsp+140h+pSid]; pSid
0x1800b87ed  lea     ecx, [rdx+19h]; WellKnownSidType
0x1800b87f0  call    CreateWellKnownSid
0x1800b87f5  test    eax, eax
0x1800b87f7  jz      loc_1800B8946
0x1800b87fd  lea     r8, [rsp+140h+cbSid]; cbDomainSid
0x1800b8802  mov     [rsp+140h+cbSid], 44h ; 'D'
0x1800b880a  lea     rdx, [rbp+40h+pDomainSid]; pDomainSid
0x1800b880e  mov     rcx, rdi; pSid
0x1800b8811  call    GetWindowsAccountDomainSid
0x1800b8816  test    eax, eax
0x1800b8818  jz      loc_1800B88D7
0x1800b881e  lea     rdi, [rbp+40h+pDomainSid]
0x1800b8822  lea     r8, [rsp+140h+cbSid]; cbDomainSid
0x1800b8827  mov     [rsp+140h+cbSid], 44h ; 'D'
0x1800b882f  lea     rdx, [rbp+40h+var_70]; pDomainSid
0x1800b8833  mov     rcx, rbx; pSid
0x1800b8836  call    GetWindowsAccountDomainSid
0x1800b883b  test    eax, eax
0x1800b883d  jnz     loc_1800B8954
0x1800b8843  mov     rcx, rbx; Sid
0x1800b8846  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800b884d  nop     dword ptr [rax+rax+00h]
0x1800b8852  mov     ecx, [rax]
0x1800b8854  sub     ecx, cs:dword_1801A5150
0x1800b885a  jnz     short loc_1800B8869
0x1800b885c  movzx   ecx, word ptr [rax+4]
0x1800b8860  movzx   eax, cs:word_1801A5154
0x1800b8867  sub     ecx, eax
0x1800b8869  test    ecx, ecx
0x1800b886b  jnz     loc_1800B894D
0x1800b8871  mov     rcx, rbx; Sid
0x1800b8874  call    cs:__imp_RtlSubAuthorityCountSid
0x1800b887b  nop     dword ptr [rax+rax+00h]
0x1800b8880  cmp     byte ptr [rax], 0
0x1800b8883  jbe     loc_1800B894D
0x1800b8889  xor     edx, edx; SubAuthority
0x1800b888b  mov     rcx, rbx; Sid
0x1800b888e  call    cs:__imp_RtlSubAuthoritySid
0x1800b8895  nop     dword ptr [rax+rax+00h]
0x1800b889a  cmp     dword ptr [rax], 20h ; ' '
0x1800b889d  jnz     loc_1800B894D
0x1800b88a3  lea     rdx, [rsp+140h+pSid]; pSid2
0x1800b88a8  mov     rcx, rdi; pSid1
0x1800b88ab  call    EqualSid
0x1800b88b0  mov     [rsi], eax
0x1800b88b2  mov     eax, 1
0x1800b88b7  mov     rcx, [rbp+40h+var_20]
0x1800b88bb  xor     rcx, rsp; StackCookie
0x1800b88be  call    __security_check_cookie
0x1800b88c3  mov     rbx, [rsp+140h+arg_18]
0x1800b88cb  add     rsp, 130h
0x1800b88d2  pop     rdi
0x1800b88d3  pop     rsi
0x1800b88d4  pop     rbp
0x1800b88d5  retn
0x1800b88d7  mov     rcx, rdi; Sid
0x1800b88da  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800b88e1  nop     dword ptr [rax+rax+00h]
0x1800b88e6  mov     ecx, [rax]
0x1800b88e8  sub     ecx, cs:dword_1801A5150
0x1800b88ee  jnz     short loc_1800B88FD
0x1800b88f0  movzx   ecx, word ptr [rax+4]
0x1800b88f4  movzx   eax, cs:word_1801A5154
0x1800b88fb  sub     ecx, eax
0x1800b88fd  test    ecx, ecx
0x1800b88ff  jnz     short loc_1800B894D
0x1800b8901  mov     rcx, rdi; Sid
0x1800b8904  call    cs:__imp_RtlSubAuthorityCountSid
0x1800b890b  nop     dword ptr [rax+rax+00h]
0x1800b8910  cmp     byte ptr [rax], 0
0x1800b8913  jbe     short loc_1800B894D
0x1800b8915  xor     edx, edx; SubAuthority
0x1800b8917  mov     rcx, rdi; Sid
0x1800b891a  call    cs:__imp_RtlSubAuthoritySid
0x1800b8921  nop     dword ptr [rax+rax+00h]
0x1800b8926  cmp     dword ptr [rax], 20h ; ' '
0x1800b8929  jnz     short loc_1800B894D
0x1800b892b  lea     rdi, [rsp+140h+pSid]
0x1800b8930  jmp     loc_1800B8822
0x1800b8935  mov     ecx, 539h; LastError
0x1800b893a  call    cs:__imp_RtlSetLastWin32Error
0x1800b8941  nop     dword ptr [rax+rax+00h]
0x1800b8946  xor     eax, eax
0x1800b8948  jmp     loc_1800B88B7
0x1800b894d  mov     ecx, 4EAh
0x1800b8952  jmp     short loc_1800B893A
0x1800b8954  lea     rdx, [rbp+40h+var_70]
0x1800b8958  jmp     loc_1800B88A8
0x1800b895d  mov     ecx, 57h ; 'W'
0x1800b8962  jmp     short loc_1800B893A
0x1800b8964  mov     ecx, 51Ah
0x1800b8969  jmp     short loc_1800B893A
```
