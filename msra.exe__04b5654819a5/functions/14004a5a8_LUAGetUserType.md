# LUAGetUserType

- ea: `0x14004a5a8`
- end: `0x14004a6c0`
- name: `LUAGetUserType`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14004a784`

## callees

- `0x14004a5a8`
- `0x14004a6c8`

## import_xrefs

- `ntdll!NtClose` at `0x14004a6a4`
- `ntdll!NtClose` at `0x14004a6a4`
- `ntdll!NtQueryInformationToken` at `0x14004a675`
- `ntdll!NtQueryInformationToken` at `0x14004a675`
- `ntdll!NtOpenProcessToken` at `0x14004a605`
- `ntdll!NtOpenProcessToken` at `0x14004a605`
- `ntdll!NtOpenThreadToken` at `0x14004a5e6`
- `ntdll!NtOpenThreadToken` at `0x14004a5e6`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(__int64 a1, int *a2)
{
  NTSTATUS v3; // ebx
  void *v4; // rsi
  int v5; // ecx
  int TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  int TokenInformation_4; // [rsp+54h] [rbp+24h]
  ULONG ReturnLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  TokenInformation_4 = HIDWORD(a1);
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( v3 == -1073741700 )
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v3 >= 0 )
  {
    v4 = TokenHandle;
    v3 = LUAIsElevatedToken(TokenHandle);
    if ( v3 >= 0 )
    {
      *a2 = TokenInformation ? 0 : 2 - (ReturnLength != 0);
      TokenInformation = 0;
      ReturnLength = 4;
      v3 = NtQueryInformationToken(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength);
      if ( v3 >= 0 )
      {
        if ( TokenInformation )
        {
          v5 = *a2;
          if ( (unsigned int)(*a2 - 16) > 2 )
            v5 += 16;
          *a2 = v5;
        }
      }
    }
    if ( v4 )
      NtClose(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14004a5a8  mov     [rsp-18h+arg_8], rbx
0x14004a5ad  mov     [rsp-18h+TokenInformation], rcx
0x14004a5b2  push    rbp
0x14004a5b3  push    rsi
0x14004a5b4  push    rdi
0x14004a5b5  mov     rbp, rsp
0x14004a5b8  sub     rsp, 30h
0x14004a5bc  xor     r8d, r8d; OpenAsSelf
0x14004a5bf  mov     [rbp+TokenHandle], 0
0x14004a5c7  mov     rdi, rdx
0x14004a5ca  mov     dword ptr [rbp+TokenInformation], 0
0x14004a5d1  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14004a5d5  mov     [rbp+arg_10], 0
0x14004a5dc  lea     esi, [r8+8]
0x14004a5e0  mov     edx, esi; DesiredAccess
0x14004a5e2  lea     rcx, [r8-2]; ThreadHandle
0x14004a5e6  call    cs:__imp_NtOpenThreadToken
0x14004a5ed  nop     dword ptr [rax+rax+00h]
0x14004a5f2  mov     ebx, eax
0x14004a5f4  cmp     eax, 0C000007Ch
0x14004a5f9  jnz     short loc_14004A613
0x14004a5fb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14004a5ff  mov     edx, esi; DesiredAccess
0x14004a601  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14004a605  call    cs:__imp_NtOpenProcessToken
0x14004a60c  nop     dword ptr [rax+rax+00h]
0x14004a611  mov     ebx, eax
0x14004a613  test    ebx, ebx
0x14004a615  js      loc_14004A6B0
0x14004a61b  mov     rsi, [rbp+TokenHandle]
0x14004a61f  lea     r8, [rbp+arg_10]
0x14004a623  mov     rcx, rsi; TokenHandle
0x14004a626  lea     rdx, [rbp+TokenInformation]
0x14004a62a  call    LUAIsElevatedToken
0x14004a62f  mov     ebx, eax
0x14004a631  test    eax, eax
0x14004a633  js      short loc_14004A69C
0x14004a635  cmp     dword ptr [rbp+TokenInformation], 0
0x14004a639  jz      short loc_14004A643
0x14004a63b  mov     dword ptr [rdi], 0
0x14004a641  jmp     short loc_14004A64F
0x14004a643  mov     eax, [rbp+arg_10]
0x14004a646  neg     eax
0x14004a648  sbb     ecx, ecx
0x14004a64a  add     ecx, 2
0x14004a64d  mov     [rdi], ecx
0x14004a64f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14004a653  lea     rax, [rbp+arg_10]
0x14004a657  mov     r9d, 4; TokenInformationLength
0x14004a65d  mov     dword ptr [rbp+TokenInformation], 0
0x14004a664  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14004a668  mov     [rbp+arg_10], r9d
0x14004a66c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14004a671  lea     edx, [r9+16h]; TokenInformationClass
0x14004a675  call    cs:__imp_NtQueryInformationToken
0x14004a67c  nop     dword ptr [rax+rax+00h]
0x14004a681  mov     ebx, eax
0x14004a683  test    eax, eax
0x14004a685  js      short loc_14004A69C
0x14004a687  cmp     dword ptr [rbp+TokenInformation], 0
0x14004a68b  jz      short loc_14004A69C
0x14004a68d  mov     ecx, [rdi]
0x14004a68f  lea     eax, [rcx-10h]
0x14004a692  cmp     eax, 2
0x14004a695  jbe     short loc_14004A69A
0x14004a697  add     ecx, 10h
0x14004a69a  mov     [rdi], ecx
0x14004a69c  test    rsi, rsi
0x14004a69f  jz      short loc_14004A6B0
0x14004a6a1  mov     rcx, rsi; Handle
0x14004a6a4  call    cs:__imp_NtClose
0x14004a6ab  nop     dword ptr [rax+rax+00h]
0x14004a6b0  mov     eax, ebx
0x14004a6b2  mov     rbx, [rsp+30h+arg_8]
0x14004a6b7  add     rsp, 30h
0x14004a6bb  pop     rdi
0x14004a6bc  pop     rsi
0x14004a6bd  pop     rbp
0x14004a6be  retn
```
