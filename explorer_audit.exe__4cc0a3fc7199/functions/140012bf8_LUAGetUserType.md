# LUAGetUserType

- ea: `0x140012bf8`
- end: `0x140012d2a`
- name: `LUAGetUserType`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140012af4`
- `0x14008b158`

## callees

- `0x140012bf8`
- `0x14008d418`

## import_xrefs

- `ntdll!NtClose` at `0x140012d15`
- `ntdll!NtClose` at `0x140012d15`
- `ntdll!NtOpenProcessToken` at `0x140012c48`
- `ntdll!NtOpenProcessToken` at `0x140012c48`
- `ntdll!NtQueryInformationToken` at `0x140012c8b`
- `ntdll!NtQueryInformationToken` at `0x140012cbd`
- `ntdll!NtQueryInformationToken` at `0x140012c8b`
- `ntdll!NtQueryInformationToken` at `0x140012cbd`
- `ntdll!NtOpenThreadToken` at `0x140012c2f`
- `ntdll!NtOpenThreadToken` at `0x140012c2f`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(__int64 a1, int *a2)
{
  NTSTATUS v3; // ebx
  void *v4; // rsi
  int v5; // ecx
  int v7; // [rsp+30h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-8h] BYREF
  __int64 TokenInformation; // [rsp+60h] [rbp+20h] BYREF
  ULONG ReturnLength; // [rsp+70h] [rbp+30h] BYREF
  int v11; // [rsp+78h] [rbp+38h] BYREF

  TokenInformation = a1;
  TokenHandle = 0;
  v7 = 0;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( v3 == -1073741700 )
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v3 >= 0 )
  {
    v4 = TokenHandle;
    ReturnLength = 0;
    v11 = 0;
    LODWORD(TokenInformation) = 1;
    v3 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
    if ( v3 >= 0 )
    {
      if ( (_DWORD)TokenInformation == 2 )
        goto LABEL_11;
      if ( (_DWORD)TokenInformation != 1 )
      {
        *a2 = 1;
        goto LABEL_12;
      }
      v3 = NtQueryInformationToken(v4, TokenElevation, &v11, 4u, &ReturnLength);
      if ( v3 >= 0 )
      {
        if ( !v11 )
        {
          *a2 = 2;
LABEL_12:
          v3 = LUAIsUIAToken(TokenHandle, &v7);
          if ( v3 >= 0 && v7 )
          {
            v5 = *a2;
            if ( (unsigned int)(*a2 - 16) > 2 )
              v5 += 16;
            *a2 = v5;
          }
          goto LABEL_17;
        }
LABEL_11:
        *a2 = 0;
        goto LABEL_12;
      }
    }
LABEL_17:
    if ( v4 )
      NtClose(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140012bf8  mov     [rsp-18h+arg_8], rbx
0x140012bfd  mov     [rsp-18h+TokenInformation], rcx
0x140012c02  push    rbp
0x140012c03  push    rsi
0x140012c04  push    rdi
0x140012c05  mov     rbp, rsp
0x140012c08  sub     rsp, 40h
0x140012c0c  xor     r8d, r8d; OpenAsSelf
0x140012c0f  mov     [rbp+TokenHandle], 0
0x140012c17  mov     rdi, rdx
0x140012c1a  mov     [rbp+var_10], 0
0x140012c21  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140012c25  lea     esi, [r8+8]
0x140012c29  mov     edx, esi; DesiredAccess
0x140012c2b  lea     rcx, [r8-2]; ThreadHandle
0x140012c2f  call    cs:__imp_NtOpenThreadToken
0x140012c35  mov     ebx, eax
0x140012c37  cmp     eax, 0C000007Ch
0x140012c3c  jnz     short loc_140012C50
0x140012c3e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140012c42  mov     edx, esi; DesiredAccess
0x140012c44  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140012c48  call    cs:__imp_NtOpenProcessToken
0x140012c4e  mov     ebx, eax
0x140012c50  test    ebx, ebx
0x140012c52  js      loc_140012D1B
0x140012c58  mov     rsi, [rbp+TokenHandle]
0x140012c5c  lea     rax, [rbp+arg_10]
0x140012c60  mov     r9d, 4; TokenInformationLength
0x140012c66  mov     [rbp+arg_10], 0
0x140012c6d  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140012c71  mov     [rbp+arg_18], 0
0x140012c78  mov     rcx, rsi; TokenHandle
0x140012c7b  mov     dword ptr [rbp+TokenInformation], 1
0x140012c82  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140012c87  lea     edx, [r9+0Eh]; TokenInformationClass
0x140012c8b  call    cs:__imp_NtQueryInformationToken
0x140012c91  mov     ebx, eax
0x140012c93  test    eax, eax
0x140012c95  js      short loc_140012D0D
0x140012c97  cmp     dword ptr [rbp+TokenInformation], 2
0x140012c9b  jz      short loc_140012CDF
0x140012c9d  cmp     dword ptr [rbp+TokenInformation], 1
0x140012ca1  jnz     short loc_140012CD7
0x140012ca3  mov     r9d, 4; TokenInformationLength
0x140012ca9  lea     rax, [rbp+arg_10]
0x140012cad  lea     r8, [rbp+arg_18]; TokenInformation
0x140012cb1  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140012cb6  mov     rcx, rsi; TokenHandle
0x140012cb9  lea     edx, [r9+10h]; TokenInformationClass
0x140012cbd  call    cs:__imp_NtQueryInformationToken
0x140012cc3  mov     ebx, eax
0x140012cc5  test    eax, eax
0x140012cc7  js      short loc_140012D0D
0x140012cc9  cmp     [rbp+arg_18], 0
0x140012ccd  jnz     short loc_140012CDF
0x140012ccf  mov     dword ptr [rdi], 2
0x140012cd5  jmp     short loc_140012CE5
0x140012cd7  mov     dword ptr [rdi], 1
0x140012cdd  jmp     short loc_140012CE5
0x140012cdf  mov     dword ptr [rdi], 0
0x140012ce5  mov     rcx, [rbp+TokenHandle]
0x140012ce9  lea     rdx, [rbp+var_10]
0x140012ced  call    LUAIsUIAToken
0x140012cf2  mov     ebx, eax
0x140012cf4  test    eax, eax
0x140012cf6  js      short loc_140012D0D
0x140012cf8  cmp     [rbp+var_10], 0
0x140012cfc  jz      short loc_140012D0D
0x140012cfe  mov     ecx, [rdi]
0x140012d00  lea     eax, [rcx-10h]
0x140012d03  cmp     eax, 2
0x140012d06  jbe     short loc_140012D0B
0x140012d08  add     ecx, 10h
0x140012d0b  mov     [rdi], ecx
0x140012d0d  test    rsi, rsi
0x140012d10  jz      short loc_140012D1B
0x140012d12  mov     rcx, rsi; Handle
0x140012d15  call    cs:__imp_NtClose
0x140012d1b  mov     eax, ebx
0x140012d1d  mov     rbx, [rsp+40h+arg_8]
0x140012d22  add     rsp, 40h
0x140012d26  pop     rdi
0x140012d27  pop     rsi
0x140012d28  pop     rbp
0x140012d29  retn
```
