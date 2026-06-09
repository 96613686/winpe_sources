# HrGetClientInformation(ulong *,uint *,int *)

- ea: `0x180026a10`
- end: `0x180026b3f`
- name: `?HrGetClientInformation@@YAJPEAKPEAIPEAH@Z`
- size: `303`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, int *)`
- caller_count: `11`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800268f8`
- `0x1800842a0`
- `0x1800843d0`
- `0x1800a6ed0`
- `0x1800bf1b0`
- `0x1800c04f0`
- `0x1800c0720`
- `0x1800c09f0`
- `0x1800c48e0`
- `0x1800c4e00`
- `0x1800c5e90`

## callees

- `0x180026a10`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ae9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180026aa5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180026aa5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180026a34`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180026a34`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026a7c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026b25`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026a7c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026b25`
- `IPHLPAPI!GetSessionCompartmentId` at `0x180026a96`
- `IPHLPAPI!GetSessionCompartmentId` at `0x180026a96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrGetClientInformation(unsigned int *a1, unsigned int *a2, int *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ecx
  ULONG v8; // ecx
  unsigned int v9; // ebx
  signed int LastError; // eax
  signed int v12; // eax
  unsigned int TokenInformation; // [rsp+30h] [rbp-28h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-24h] BYREF

  v6 = CoImpersonateClient();
  v7 = 0;
  if ( v6 != -2147417833 )
    v7 = v6;
  if ( v7 )
    return v7;
  ReturnLength = 0;
  if ( a1 || a2 )
  {
    TokenInformation = 0;
    if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_11;
    }
    v8 = TokenInformation;
    if ( a1 )
      *a1 = TokenInformation;
    if ( a2 )
      *a2 = GetSessionCompartmentId(v8);
  }
  v9 = 0;
LABEL_11:
  if ( a3 )
  {
    TokenInformation = 0;
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      *a3 = TokenInformation != 0;
    }
    else
    {
      v12 = GetLastError();
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
    }
  }
  CoRevertToSelf();
  return v9;
}

```

## disassembly

```asm
0x180026a10  mov     [rsp+arg_18], rbx
0x180026a15  push    rbp
0x180026a16  push    rsi
0x180026a17  push    rdi
0x180026a18  sub     rsp, 40h
0x180026a1c  mov     rax, cs:__security_cookie
0x180026a23  xor     rax, rsp
0x180026a26  mov     [rsp+58h+var_20], rax
0x180026a2b  mov     rsi, r8
0x180026a2e  mov     rdi, rdx
0x180026a31  mov     rbx, rcx
0x180026a34  call    cs:__imp_CoImpersonateClient
0x180026a3a  xor     ebp, ebp
0x180026a3c  cmp     eax, 80010117h
0x180026a41  mov     ecx, ebp
0x180026a43  cmovnz  ecx, eax
0x180026a46  test    ecx, ecx
0x180026a48  jnz     loc_180026AE5
0x180026a4e  mov     [rsp+58h+var_24], ebp
0x180026a52  test    rbx, rbx
0x180026a55  jz      short loc_180026AC7
0x180026a57  lea     rax, [rsp+58h+var_24]
0x180026a5c  mov     [rsp+58h+TokenInformation], ebp
0x180026a60  mov     r9d, 4; TokenInformationLength
0x180026a66  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180026a6b  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180026a70  mov     edx, 0Ch; TokenInformationClass
0x180026a75  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180026a7c  call    cs:__imp_GetTokenInformation
0x180026a82  test    eax, eax
0x180026a84  jz      short loc_180026ACE
0x180026a86  mov     ecx, [rsp+58h+TokenInformation]; SessionId
0x180026a8a  test    rbx, rbx
0x180026a8d  jz      short loc_180026A91
0x180026a8f  mov     [rbx], ecx
0x180026a91  test    rdi, rdi
0x180026a94  jz      short loc_180026A9E
0x180026a96  call    cs:__imp_GetSessionCompartmentId
0x180026a9c  mov     [rdi], eax
0x180026a9e  mov     ebx, ebp
0x180026aa0  test    rsi, rsi
0x180026aa3  jnz     short loc_180026B00
0x180026aa5  call    cs:__imp_CoRevertToSelf
0x180026aab  mov     eax, ebx
0x180026aad  mov     rcx, [rsp+58h+var_20]
0x180026ab2  xor     rcx, rsp; StackCookie
0x180026ab5  call    __security_check_cookie
0x180026aba  mov     rbx, [rsp+58h+arg_18]
0x180026abf  add     rsp, 40h
0x180026ac3  pop     rdi
0x180026ac4  pop     rsi
0x180026ac5  pop     rbp
0x180026ac6  retn
0x180026ac7  test    rdi, rdi
0x180026aca  jnz     short loc_180026A57
0x180026acc  jmp     short loc_180026A9E
0x180026ace  call    cs:__imp_GetLastError
0x180026ad4  mov     ebx, eax
0x180026ad6  test    eax, eax
0x180026ad8  jle     short loc_180026AA0
0x180026ada  movzx   ebx, ax
0x180026add  or      ebx, 80070000h
0x180026ae3  jmp     short loc_180026AA0
0x180026ae5  mov     eax, ecx
0x180026ae7  jmp     short loc_180026AAD
0x180026ae9  call    cs:__imp_GetLastError
0x180026aef  mov     ebx, eax
0x180026af1  test    eax, eax
0x180026af3  jle     short loc_180026AA5
0x180026af5  movzx   ebx, ax
0x180026af8  or      ebx, 80070000h
0x180026afe  jmp     short loc_180026AA5
0x180026b00  lea     rax, [rsp+58h+var_24]
0x180026b05  mov     [rsp+58h+TokenInformation], ebp
0x180026b09  mov     r9d, 4; TokenInformationLength
0x180026b0f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180026b14  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180026b19  mov     edx, 1Dh; TokenInformationClass
0x180026b1e  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180026b25  call    cs:__imp_GetTokenInformation
0x180026b2b  test    eax, eax
0x180026b2d  jz      short loc_180026AE9
0x180026b2f  mov     ecx, ebp
0x180026b31  cmp     [rsp+58h+TokenInformation], ecx
0x180026b35  setnz   cl
0x180026b38  mov     [rsi], ecx
0x180026b3a  jmp     loc_180026AA5
```
