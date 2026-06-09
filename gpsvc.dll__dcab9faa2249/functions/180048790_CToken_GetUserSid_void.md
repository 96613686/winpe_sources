# CToken::GetUserSid(void * *)

- ea: `0x180048790`
- end: `0x1800488c3`
- name: `?GetUserSid@CToken@@UEBAKPEAPEAX@Z`
- size: `307`
- prototype: `unsigned int __fastcall(CToken *__hidden this, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180048770`
- `0x180066684`

## callees

- `0x180048790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800487da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004889f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800487da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004889f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800487f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048842`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800487f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048842`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048869`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800488b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048869`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800488b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800487d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180048824`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800487d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180048824`
- `ntdll!RtlCopySid` at `0x18004885a`
- `ntdll!RtlCopySid` at `0x18004885a`
- `ntdll!RtlLengthSid` at `0x180048831`
- `ntdll!RtlLengthSid` at `0x180048831`

## pseudocode

```c
DWORD __fastcall CToken::GetUserSid(CToken *this, void **a2)
{
  void *v4; // rcx
  DWORD result; // eax
  PSID *v6; // rsi
  HLOCAL v7; // rax
  int LastError; // ebx
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  v4 = (void *)*((_QWORD *)this + 1);
  TokenInformationLength = 0;
  if ( !v4 )
    return 0;
  if ( GetTokenInformation(v4, TokenUser, 0, 0, &TokenInformationLength) || (result = GetLastError(), result == 122) )
  {
    v6 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v6 )
    {
      if ( GetTokenInformation(*((HANDLE *)this + 1), TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
      {
        TokenInformationLength = RtlLengthSid(*v6);
        v7 = LocalAlloc(0x40u, TokenInformationLength);
        *a2 = v7;
        if ( v7 )
        {
          LastError = RtlCopySid(TokenInformationLength, v7, *v6);
          if ( LastError < 0 )
          {
            LastError = 266;
            LocalFree(*a2);
            *a2 = 0;
          }
        }
        else
        {
          LastError = 14;
        }
      }
      else
      {
        LastError = GetLastError();
      }
      LocalFree(v6);
      return LastError;
    }
    else
    {
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180048790  mov     [rsp+arg_10], rbx
0x180048795  mov     [rsp+arg_18], rbp
0x18004879a  push    rdi
0x18004879b  sub     rsp, 30h
0x18004879f  xor     ebp, ebp
0x1800487a1  mov     rbx, rcx
0x1800487a4  mov     [rdx], rbp
0x1800487a7  mov     rdi, rdx
0x1800487aa  mov     rcx, [rcx+8]; TokenHandle
0x1800487ae  mov     [rsp+38h+TokenInformationLength], ebp
0x1800487b2  test    rcx, rcx
0x1800487b5  jz      loc_180048886
0x1800487bb  lea     rax, [rsp+38h+TokenInformationLength]
0x1800487c0  xor     r9d, r9d; TokenInformationLength
0x1800487c3  xor     r8d, r8d; TokenInformation
0x1800487c6  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800487cb  mov     edx, 1; TokenInformationClass
0x1800487d0  call    cs:__imp_GetTokenInformation
0x1800487d6  test    eax, eax
0x1800487d8  jnz     short loc_1800487E9
0x1800487da  call    cs:__imp_GetLastError
0x1800487e0  cmp     eax, 7Ah ; 'z'
0x1800487e3  jnz     loc_180048876
0x1800487e9  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x1800487ed  mov     ecx, 40h ; '@'; uFlags
0x1800487f2  mov     [rsp+38h+arg_8], rsi
0x1800487f7  call    cs:__imp_LocalAlloc
0x1800487fd  mov     rsi, rax
0x180048800  test    rax, rax
0x180048803  jz      loc_180048898
0x180048809  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18004880e  lea     rax, [rsp+38h+TokenInformationLength]
0x180048813  mov     rcx, [rbx+8]; TokenHandle
0x180048817  mov     r8, rsi; TokenInformation
0x18004881a  mov     edx, 1; TokenInformationClass
0x18004881f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180048824  call    cs:__imp_GetTokenInformation
0x18004882a  test    eax, eax
0x18004882c  jz      short loc_18004889F
0x18004882e  mov     rcx, [rsi]; Sid
0x180048831  call    cs:__imp_RtlLengthSid
0x180048837  mov     edx, eax; uBytes
0x180048839  mov     ecx, 40h ; '@'; uFlags
0x18004883e  mov     [rsp+38h+TokenInformationLength], edx
0x180048842  call    cs:__imp_LocalAlloc
0x180048848  mov     [rdi], rax
0x18004884b  test    rax, rax
0x18004884e  jz      short loc_1800488A9
0x180048850  mov     r8, [rsi]; SourceSid
0x180048853  mov     rdx, rax; DestinationSid
0x180048856  mov     ecx, [rsp+38h+TokenInformationLength]; DestinationSidLength
0x18004885a  call    cs:__imp_RtlCopySid
0x180048860  mov     ebx, eax
0x180048862  test    eax, eax
0x180048864  js      short loc_1800488B0
0x180048866  mov     rcx, rsi; hMem
0x180048869  call    cs:__imp_LocalFree
0x18004886f  mov     eax, ebx
0x180048871  mov     rsi, [rsp+38h+arg_8]
0x180048876  mov     rbx, [rsp+38h+arg_10]
0x18004887b  mov     rbp, [rsp+38h+arg_18]
0x180048880  add     rsp, 30h
0x180048884  pop     rdi
0x180048885  retn
0x180048886  mov     rbx, [rsp+38h+arg_10]
0x18004888b  mov     eax, ebp
0x18004888d  mov     rbp, [rsp+38h+arg_18]
0x180048892  add     rsp, 30h
0x180048896  pop     rdi
0x180048897  retn
0x180048898  mov     eax, 0Eh
0x18004889d  jmp     short loc_180048871
0x18004889f  call    cs:__imp_GetLastError
0x1800488a5  mov     ebx, eax
0x1800488a7  jmp     short loc_180048866
0x1800488a9  mov     ebx, 0Eh
0x1800488ae  jmp     short loc_180048866
0x1800488b0  mov     rcx, [rdi]; hMem
0x1800488b3  mov     ebx, 10Ah
0x1800488b8  call    cs:__imp_LocalFree
0x1800488be  mov     [rdi], rbp
0x1800488c1  jmp     short loc_180048866
```
