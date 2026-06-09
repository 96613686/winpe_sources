# GetWindowsAccountDomainSid

- ea: `0x1800b8980`
- end: `0x1800b8ac5`
- name: `GetWindowsAccountDomainSid`
- size: `325`
- prototype: `BOOL __stdcall(PSID pSid, PSID pDomainSid, DWORD *cbDomainSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800b8770`

## callees

- `0x18004b9d0`
- `0x1800b8980`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x1800b8a59`
- `ntdll!RtlInitializeSid` at `0x1800b8a59`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8a12`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8a70`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8a84`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8a12`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8a70`
- `ntdll!RtlSubAuthoritySid` at `0x1800b8a84`
- `ntdll!RtlLengthRequiredSid` at `0x1800b8a28`
- `ntdll!RtlLengthRequiredSid` at `0x1800b8a28`
- `ntdll!RtlSetLastWin32Error` at `0x1800b89ee`
- `ntdll!RtlSetLastWin32Error` at `0x1800b89ee`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b89d8`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800b89d8`
- `ntdll!RtlValidSid` at `0x1800b8992`
- `ntdll!RtlValidSid` at `0x1800b8992`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800b89ae`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800b8a44`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800b89ae`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800b8a44`

## pseudocode

```c
BOOL __stdcall GetWindowsAccountDomainSid(PSID pSid, PSID pDomainSid, DWORD *cbDomainSid)
{
  PSID_IDENTIFIER_AUTHORITY v6; // rax
  int v7; // ecx
  ULONG v8; // ecx
  ULONG v10; // eax
  DWORD v11; // ecx
  struct _SID_IDENTIFIER_AUTHORITY *v12; // rax
  NTSTATUS v13; // eax
  ULONG i; // esi
  PULONG v15; // rbx
  PULONG v16; // rax

  if ( !RtlValidSid(pSid) )
  {
    v8 = 1337;
    goto LABEL_8;
  }
  if ( !cbDomainSid )
    goto LABEL_10;
  v6 = RtlIdentifierAuthoritySid(pSid);
  v7 = *(_DWORD *)v6->Value;
  if ( !*(_DWORD *)v6->Value )
    v7 = *(unsigned __int16 *)&v6->Value[4] - 1280;
  if ( v7 || *RtlSubAuthorityCountSid(pSid) <= 3u || *RtlSubAuthoritySid(pSid, 0) != 21 )
  {
    v8 = 1257;
LABEL_8:
    RtlSetLastWin32Error(v8);
    return 0;
  }
  v10 = RtlLengthRequiredSid(4u);
  v11 = *cbDomainSid;
  *cbDomainSid = v10;
  if ( v11 < v10 )
  {
    v8 = 122;
    goto LABEL_8;
  }
  if ( !pDomainSid )
  {
LABEL_10:
    v8 = 87;
    goto LABEL_8;
  }
  v12 = RtlIdentifierAuthoritySid(pSid);
  v13 = RtlInitializeSid(pDomainSid, v12, 4u);
  if ( v13 < 0 )
  {
    BaseSetLastNTError((unsigned int)v13);
    return 0;
  }
  for ( i = 0; i < 4; ++i )
  {
    v15 = RtlSubAuthoritySid(pSid, i);
    v16 = RtlSubAuthoritySid(pDomainSid, i);
    *v16 = *v15;
  }
  return 1;
}

```

## disassembly

```asm
0x1800b8980  push    rbx
0x1800b8982  push    rbp
0x1800b8983  push    rsi
0x1800b8984  push    rdi
0x1800b8985  sub     rsp, 28h
0x1800b8989  mov     rbx, r8
0x1800b898c  mov     rbp, rdx
0x1800b898f  mov     rdi, rcx
0x1800b8992  call    cs:__imp_RtlValidSid
0x1800b8999  nop     dword ptr [rax+rax+00h]
0x1800b899e  test    al, al
0x1800b89a0  jz      loc_1800B8AA5
0x1800b89a6  test    rbx, rbx
0x1800b89a9  jz      short loc_1800B8A06
0x1800b89ab  mov     rcx, rdi; Sid
0x1800b89ae  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800b89b5  nop     dword ptr [rax+rax+00h]
0x1800b89ba  mov     ecx, [rax]
0x1800b89bc  sub     ecx, cs:dword_1801A5150
0x1800b89c2  jnz     short loc_1800B89D1
0x1800b89c4  movzx   ecx, word ptr [rax+4]
0x1800b89c8  movzx   eax, cs:word_1801A5154
0x1800b89cf  sub     ecx, eax
0x1800b89d1  test    ecx, ecx
0x1800b89d3  jnz     short loc_1800B89E9
0x1800b89d5  mov     rcx, rdi; Sid
0x1800b89d8  call    cs:__imp_RtlSubAuthorityCountSid
0x1800b89df  nop     dword ptr [rax+rax+00h]
0x1800b89e4  cmp     byte ptr [rax], 3
0x1800b89e7  ja      short loc_1800B8A0D
0x1800b89e9  mov     ecx, 4E9h; LastError
0x1800b89ee  call    cs:__imp_RtlSetLastWin32Error
0x1800b89f5  nop     dword ptr [rax+rax+00h]
0x1800b89fa  xor     eax, eax
0x1800b89fc  add     rsp, 28h
0x1800b8a00  pop     rdi
0x1800b8a01  pop     rsi
0x1800b8a02  pop     rbp
0x1800b8a03  pop     rbx
0x1800b8a04  retn
0x1800b8a06  mov     ecx, 57h ; 'W'
0x1800b8a0b  jmp     short loc_1800B89EE
0x1800b8a0d  xor     edx, edx; SubAuthority
0x1800b8a0f  mov     rcx, rdi; Sid
0x1800b8a12  call    cs:__imp_RtlSubAuthoritySid
0x1800b8a19  nop     dword ptr [rax+rax+00h]
0x1800b8a1e  cmp     dword ptr [rax], 15h
0x1800b8a21  jnz     short loc_1800B89E9
0x1800b8a23  mov     ecx, 4; SubAuthorityCount
0x1800b8a28  call    cs:__imp_RtlLengthRequiredSid
0x1800b8a2f  nop     dword ptr [rax+rax+00h]
0x1800b8a34  mov     ecx, [rbx]
0x1800b8a36  mov     [rbx], eax
0x1800b8a38  cmp     ecx, eax
0x1800b8a3a  jb      short loc_1800B8AAF
0x1800b8a3c  test    rbp, rbp
0x1800b8a3f  jz      short loc_1800B8A06
0x1800b8a41  mov     rcx, rdi; Sid
0x1800b8a44  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800b8a4b  nop     dword ptr [rax+rax+00h]
0x1800b8a50  mov     r8b, 4; SubAuthorityCount
0x1800b8a53  mov     rcx, rbp; Sid
0x1800b8a56  mov     rdx, rax; IdentifierAuthority
0x1800b8a59  call    cs:__imp_RtlInitializeSid
0x1800b8a60  nop     dword ptr [rax+rax+00h]
0x1800b8a65  test    eax, eax
0x1800b8a67  js      short loc_1800B8AB9
0x1800b8a69  xor     esi, esi
0x1800b8a6b  mov     edx, esi; SubAuthority
0x1800b8a6d  mov     rcx, rdi; Sid
0x1800b8a70  call    cs:__imp_RtlSubAuthoritySid
0x1800b8a77  nop     dword ptr [rax+rax+00h]
0x1800b8a7c  mov     edx, esi; SubAuthority
0x1800b8a7e  mov     rcx, rbp; Sid
0x1800b8a81  mov     rbx, rax
0x1800b8a84  call    cs:__imp_RtlSubAuthoritySid
0x1800b8a8b  nop     dword ptr [rax+rax+00h]
0x1800b8a90  mov     ecx, [rbx]
0x1800b8a92  inc     esi
0x1800b8a94  mov     [rax], ecx
0x1800b8a96  cmp     esi, 4
0x1800b8a99  jb      short loc_1800B8A6B
0x1800b8a9b  mov     eax, 1
0x1800b8aa0  jmp     loc_1800B89FC
0x1800b8aa5  mov     ecx, 539h
0x1800b8aaa  jmp     loc_1800B89EE
0x1800b8aaf  mov     ecx, 7Ah ; 'z'
0x1800b8ab4  jmp     loc_1800B89EE
0x1800b8ab9  mov     ecx, eax
0x1800b8abb  call    BaseSetLastNTError
0x1800b8ac0  jmp     loc_1800B89FA
```
