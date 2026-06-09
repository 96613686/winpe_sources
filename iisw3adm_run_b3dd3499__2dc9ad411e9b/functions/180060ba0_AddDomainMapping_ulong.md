# AddDomainMapping(ulong *)

- ea: `0x180060ba0`
- end: `0x180060cb8`
- name: `?AddDomainMapping@@YAJPEAK@Z`
- size: `280`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005388`

## callees

- `0x180060ba0`
- `0x180061060`

## import_xrefs

- `ntdll!RtlInitializeSid` at `0x180060c46`
- `ntdll!RtlInitializeSid` at `0x180060c46`
- `ntdll!RtlLengthRequiredSid` at `0x180060be6`
- `ntdll!RtlLengthRequiredSid` at `0x180060be6`
- `ntdll!RtlInitUnicodeString` at `0x180060c68`
- `ntdll!RtlInitUnicodeString` at `0x180060c79`
- `ntdll!RtlInitUnicodeString` at `0x180060c68`
- `ntdll!RtlInitUnicodeString` at `0x180060c79`
- `ntdll!RtlSubAuthoritySid` at `0x180060c51`
- `ntdll!RtlSubAuthoritySid` at `0x180060c51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060bf0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180060bf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060c1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060c1d`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x180060c8d`
- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x180060c8d`

## pseudocode

```c
__int64 __fastcall AddDomainMapping(unsigned int *a1)
{
  ULONG v2; // eax
  HLOCAL v3; // rax
  void *v4; // rdi
  unsigned int v5; // ebx
  unsigned int *v6; // rcx
  int v8; // eax
  unsigned int *v9; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString[3]; // [rsp+28h] [rbp-50h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+58h] [rbp-20h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  memset(DestinationString, 0, sizeof(DestinationString));
  v9 = 0;
  v2 = RtlLengthRequiredSid(6u);
  v3 = LocalAlloc(0, v2);
  v4 = v3;
  if ( !v3 )
  {
    v5 = -2147024882;
LABEL_3:
    v6 = v9;
    goto LABEL_4;
  }
  v5 = 0;
  RtlInitializeSid(v3, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v4, 0) = 82;
  RtlInitUnicodeString(&DestinationString[1], &SourceString);
  RtlInitUnicodeString(DestinationString, L"IIS APPPOOL");
  *(_QWORD *)&DestinationString[2].Length = v4;
  v8 = LsaManageSidNameMapping(0, DestinationString, &v9);
  if ( v8 >= 0 )
    goto LABEL_3;
  v6 = v9;
  if ( !v9 || *v9 != 2 )
    v5 = v8 | 0x10000000;
LABEL_4:
  if ( a1 && v6 )
    *a1 = *v6;
  if ( v4 )
    LocalFree(v4);
  return v5;
}

```

## disassembly

```asm
0x180060ba0  push    rbp
0x180060ba2  push    rbx
0x180060ba3  push    rsi
0x180060ba4  push    rdi
0x180060ba5  mov     rbp, rsp
0x180060ba8  sub     rsp, 78h
0x180060bac  mov     rax, cs:__security_cookie
0x180060bb3  xor     rax, rsp
0x180060bb6  mov     [rbp+var_18], rax
0x180060bba  xor     eax, eax
0x180060bbc  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x180060bc3  xorps   xmm0, xmm0
0x180060bc6  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180060bcc  mov     rsi, rcx
0x180060bcf  mov     word ptr [rbp+DestinationString], ax
0x180060bd3  movups  xmmword ptr [rbp+var_3E], xmm0
0x180060bd7  lea     ecx, [rax+6]; SubAuthorityCount
0x180060bda  mov     [rbp+var_58], rax
0x180060bde  movups  xmmword ptr [rbp+DestinationString+2], xmm0
0x180060be2  movups  xmmword ptr [rbp+var_3E+0Eh], xmm0
0x180060be6  call    cs:__imp_RtlLengthRequiredSid
0x180060bec  mov     edx, eax; uBytes
0x180060bee  xor     ecx, ecx; uFlags
0x180060bf0  call    cs:__imp_LocalAlloc
0x180060bf6  mov     rdi, rax
0x180060bf9  test    rax, rax
0x180060bfc  jnz     short loc_180060C3A
0x180060bfe  mov     ebx, 8007000Eh
0x180060c03  mov     rcx, [rbp+var_58]
0x180060c07  test    rsi, rsi
0x180060c0a  jz      short loc_180060C15
0x180060c0c  test    rcx, rcx
0x180060c0f  jz      short loc_180060C15
0x180060c11  mov     ecx, [rcx]
0x180060c13  mov     [rsi], ecx
0x180060c15  test    rdi, rdi
0x180060c18  jz      short loc_180060C23
0x180060c1a  mov     rcx, rdi; hMem
0x180060c1d  call    cs:__imp_LocalFree
0x180060c23  mov     eax, ebx
0x180060c25  mov     rcx, [rbp+var_18]
0x180060c29  xor     rcx, rsp; StackCookie
0x180060c2c  call    __security_check_cookie
0x180060c31  add     rsp, 78h
0x180060c35  pop     rdi
0x180060c36  pop     rsi
0x180060c37  pop     rbx
0x180060c38  pop     rbp
0x180060c39  retn
0x180060c3a  mov     r8b, 1; SubAuthorityCount
0x180060c3d  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180060c41  mov     rcx, rdi; Sid
0x180060c44  xor     ebx, ebx
0x180060c46  call    cs:__imp_RtlInitializeSid
0x180060c4c  xor     edx, edx; SubAuthority
0x180060c4e  mov     rcx, rdi; Sid
0x180060c51  call    cs:__imp_RtlSubAuthoritySid
0x180060c57  lea     rdx, SourceString; SourceString
0x180060c5e  lea     rcx, [rbp+DestinationString+10h]; DestinationString
0x180060c62  mov     dword ptr [rax], 52h ; 'R'
0x180060c68  call    cs:__imp_RtlInitUnicodeString
0x180060c6e  lea     rdx, aIisApppool; "IIS APPPOOL"
0x180060c75  lea     rcx, [rbp+DestinationString]; DestinationString
0x180060c79  call    cs:__imp_RtlInitUnicodeString
0x180060c7f  lea     r8, [rbp+var_58]
0x180060c83  mov     qword ptr [rbp+var_3E+0Eh], rdi
0x180060c87  lea     rdx, [rbp+DestinationString]
0x180060c8b  xor     ecx, ecx
0x180060c8d  call    cs:__imp_LsaManageSidNameMapping
0x180060c93  test    eax, eax
0x180060c95  jns     loc_180060C03
0x180060c9b  mov     rcx, [rbp+var_58]
0x180060c9f  test    rcx, rcx
0x180060ca2  jz      short loc_180060CAD
0x180060ca4  cmp     dword ptr [rcx], 2
0x180060ca7  jz      loc_180060C07
0x180060cad  mov     ebx, eax
0x180060caf  bts     ebx, 1Ch
0x180060cb3  jmp     loc_180060C07
```
