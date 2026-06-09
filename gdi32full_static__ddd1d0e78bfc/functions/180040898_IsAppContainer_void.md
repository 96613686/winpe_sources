# IsAppContainer(void)

- ea: `0x180040898`
- end: `0x180040947`
- name: `?IsAppContainer@@YAHXZ`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003ec70`
- `0x18003fb74`

## callees

- `0x180040898`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x1800408d3`
- `ntdll!NtOpenThreadToken` at `0x1800408d3`
- `ntdll!NtClose` at `0x18004091a`
- `ntdll!NtClose` at `0x18004091a`
- `ntdll!NtOpenProcessToken` at `0x180040939`
- `ntdll!NtOpenProcessToken` at `0x180040939`
- `ntdll!NtQueryInformationToken` at `0x180040909`
- `ntdll!NtQueryInformationToken` at `0x180040909`

## pseudocode

```c
__int64 IsAppContainer(void)
{
  NTSTATUS v0; // eax
  unsigned int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  if ( NtCurrentTeb()->IsImpersonating )
    v0 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  else
    v0 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v0 >= 0 )
  {
    ReturnLength = 0;
    NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
    NtClose(TokenHandle);
  }
  return TokenInformation;
}

```

## disassembly

```asm
0x180040898  sub     rsp, 38h
0x18004089c  mov     [rsp+38h+TokenHandle], 0
0x1800408a5  mov     edx, 8; DesiredAccess
0x1800408aa  mov     [rsp+38h+TokenInformation], 0
0x1800408b2  mov     rax, gs:30h
0x1800408bb  cmp     dword ptr [rax+179Ch], 0
0x1800408c2  jz      short loc_180040930
0x1800408c4  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800408c9  mov     r8b, 1; OpenAsSelf
0x1800408cc  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800408d3  call    cs:__imp_NtOpenThreadToken
0x1800408da  nop     dword ptr [rax+rax+00h]
0x1800408df  test    eax, eax
0x1800408e1  js      short loc_180040926
0x1800408e3  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800408e8  lea     rax, [rsp+38h+arg_8]
0x1800408ed  mov     r9d, 4; TokenInformationLength
0x1800408f3  mov     [rsp+38h+arg_8], 0
0x1800408fb  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180040900  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180040905  lea     edx, [r9+19h]; TokenInformationClass
0x180040909  call    cs:__imp_NtQueryInformationToken
0x180040910  nop     dword ptr [rax+rax+00h]
0x180040915  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x18004091a  call    cs:__imp_NtClose
0x180040921  nop     dword ptr [rax+rax+00h]
0x180040926  mov     eax, [rsp+38h+TokenInformation]
0x18004092a  add     rsp, 38h
0x18004092e  retn
0x180040930  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180040935  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180040939  call    cs:__imp_NtOpenProcessToken
0x180040940  nop     dword ptr [rax+rax+00h]
0x180040945  jmp     short loc_1800408DF
```
