# LUAGetUserType

- ea: `0x140020dfc`
- end: `0x140020f4d`
- name: `LUAGetUserType`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140020cdc`
- `0x140090720`

## callees

- `0x140020dfc`
- `0x140092ac4`

## import_xrefs

- `ntdll!NtClose` at `0x140020f31`
- `ntdll!NtClose` at `0x140020f31`
- `ntdll!NtOpenProcessToken` at `0x140020e52`
- `ntdll!NtOpenProcessToken` at `0x140020e52`
- `ntdll!NtQueryInformationToken` at `0x140020e9b`
- `ntdll!NtQueryInformationToken` at `0x140020ed3`
- `ntdll!NtQueryInformationToken` at `0x140020e9b`
- `ntdll!NtQueryInformationToken` at `0x140020ed3`
- `ntdll!NtOpenThreadToken` at `0x140020e33`
- `ntdll!NtOpenThreadToken` at `0x140020e33`

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
0x140020dfc  mov     [rsp-18h+arg_8], rbx
0x140020e01  mov     [rsp-18h+TokenInformation], rcx
0x140020e06  push    rbp
0x140020e07  push    rsi
0x140020e08  push    rdi
0x140020e09  mov     rbp, rsp
0x140020e0c  sub     rsp, 40h
0x140020e10  xor     r8d, r8d; OpenAsSelf
0x140020e13  mov     [rbp+TokenHandle], 0
0x140020e1b  mov     rdi, rdx
0x140020e1e  mov     [rbp+var_10], 0
0x140020e25  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140020e29  lea     esi, [r8+8]
0x140020e2d  mov     edx, esi; DesiredAccess
0x140020e2f  lea     rcx, [r8-2]; ThreadHandle
0x140020e33  call    cs:__imp_NtOpenThreadToken
0x140020e3a  nop     dword ptr [rax+rax+00h]
0x140020e3f  mov     ebx, eax
0x140020e41  cmp     eax, 0C000007Ch
0x140020e46  jnz     short loc_140020E60
0x140020e48  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140020e4c  mov     edx, esi; DesiredAccess
0x140020e4e  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140020e52  call    cs:__imp_NtOpenProcessToken
0x140020e59  nop     dword ptr [rax+rax+00h]
0x140020e5e  mov     ebx, eax
0x140020e60  test    ebx, ebx
0x140020e62  js      loc_140020F3D
0x140020e68  mov     rsi, [rbp+TokenHandle]
0x140020e6c  lea     rax, [rbp+arg_10]
0x140020e70  mov     r9d, 4; TokenInformationLength
0x140020e76  mov     [rbp+arg_10], 0
0x140020e7d  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140020e81  mov     [rbp+arg_18], 0
0x140020e88  mov     rcx, rsi; TokenHandle
0x140020e8b  mov     dword ptr [rbp+TokenInformation], 1
0x140020e92  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140020e97  lea     edx, [r9+0Eh]; TokenInformationClass
0x140020e9b  call    cs:__imp_NtQueryInformationToken
0x140020ea2  nop     dword ptr [rax+rax+00h]
0x140020ea7  mov     ebx, eax
0x140020ea9  test    eax, eax
0x140020eab  js      short loc_140020F29
0x140020ead  cmp     dword ptr [rbp+TokenInformation], 2
0x140020eb1  jz      short loc_140020EFB
0x140020eb3  cmp     dword ptr [rbp+TokenInformation], 1
0x140020eb7  jnz     short loc_140020EF3
0x140020eb9  mov     r9d, 4; TokenInformationLength
0x140020ebf  lea     rax, [rbp+arg_10]
0x140020ec3  lea     r8, [rbp+arg_18]; TokenInformation
0x140020ec7  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140020ecc  mov     rcx, rsi; TokenHandle
0x140020ecf  lea     edx, [r9+10h]; TokenInformationClass
0x140020ed3  call    cs:__imp_NtQueryInformationToken
0x140020eda  nop     dword ptr [rax+rax+00h]
0x140020edf  mov     ebx, eax
0x140020ee1  test    eax, eax
0x140020ee3  js      short loc_140020F29
0x140020ee5  cmp     [rbp+arg_18], 0
0x140020ee9  jnz     short loc_140020EFB
0x140020eeb  mov     dword ptr [rdi], 2
0x140020ef1  jmp     short loc_140020F01
0x140020ef3  mov     dword ptr [rdi], 1
0x140020ef9  jmp     short loc_140020F01
0x140020efb  mov     dword ptr [rdi], 0
0x140020f01  mov     rcx, [rbp+TokenHandle]
0x140020f05  lea     rdx, [rbp+var_10]
0x140020f09  call    LUAIsUIAToken
0x140020f0e  mov     ebx, eax
0x140020f10  test    eax, eax
0x140020f12  js      short loc_140020F29
0x140020f14  cmp     [rbp+var_10], 0
0x140020f18  jz      short loc_140020F29
0x140020f1a  mov     ecx, [rdi]
0x140020f1c  lea     eax, [rcx-10h]
0x140020f1f  cmp     eax, 2
0x140020f22  jbe     short loc_140020F27
0x140020f24  add     ecx, 10h
0x140020f27  mov     [rdi], ecx
0x140020f29  test    rsi, rsi
0x140020f2c  jz      short loc_140020F3D
0x140020f2e  mov     rcx, rsi; Handle
0x140020f31  call    cs:__imp_NtClose
0x140020f38  nop     dword ptr [rax+rax+00h]
0x140020f3d  mov     eax, ebx
0x140020f3f  mov     rbx, [rsp+40h+arg_8]
0x140020f44  add     rsp, 40h
0x140020f48  pop     rdi
0x140020f49  pop     rsi
0x140020f4a  pop     rbp
0x140020f4b  retn
```
