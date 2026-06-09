# IsAppContainer(void)

- ea: `0x180046968`
- end: `0x1800469fe`
- name: `?IsAppContainer@@YAHXZ`
- size: `150`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180044ea0`
- `0x180045d0c`

## callees

- `0x180046968`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x1800469a3`
- `ntdll!NtOpenThreadToken` at `0x1800469a3`
- `ntdll!NtClose` at `0x1800469de`
- `ntdll!NtClose` at `0x1800469de`
- `ntdll!NtOpenProcessToken` at `0x1800469f6`
- `ntdll!NtOpenProcessToken` at `0x1800469f6`
- `ntdll!NtQueryInformationToken` at `0x1800469d3`
- `ntdll!NtQueryInformationToken` at `0x1800469d3`

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
0x180046968  sub     rsp, 38h
0x18004696c  mov     [rsp+38h+TokenHandle], 0
0x180046975  mov     edx, 8; DesiredAccess
0x18004697a  mov     [rsp+38h+TokenInformation], 0
0x180046982  mov     rax, gs:30h
0x18004698b  cmp     dword ptr [rax+179Ch], 0
0x180046992  jz      short loc_1800469ED
0x180046994  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180046999  mov     r8b, 1; OpenAsSelf
0x18004699c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800469a3  call    cs:__imp_NtOpenThreadToken
0x1800469a9  test    eax, eax
0x1800469ab  js      short loc_1800469E4
0x1800469ad  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800469b2  lea     rax, [rsp+38h+arg_8]
0x1800469b7  mov     r9d, 4; TokenInformationLength
0x1800469bd  mov     [rsp+38h+arg_8], 0
0x1800469c5  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800469ca  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800469cf  lea     edx, [r9+19h]; TokenInformationClass
0x1800469d3  call    cs:__imp_NtQueryInformationToken
0x1800469d9  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x1800469de  call    cs:__imp_NtClose
0x1800469e4  mov     eax, [rsp+38h+TokenInformation]
0x1800469e8  add     rsp, 38h
0x1800469ec  retn
0x1800469ed  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800469f2  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800469f6  call    cs:__imp_NtOpenProcessToken
0x1800469fc  jmp     short loc_1800469A9
```
