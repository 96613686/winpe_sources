# LUAIsElevatedToken

- ea: `0x18000250c`
- end: `0x1800025bf`
- name: `LUAIsElevatedToken`
- size: `179`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800018c0`

## callees

- `0x18000250c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180002559`
- `ntdll!NtQueryInformationToken` at `0x180002599`
- `ntdll!NtQueryInformationToken` at `0x180002559`
- `ntdll!NtQueryInformationToken` at `0x180002599`

## pseudocode

```c
NTSTATUS __fastcall LUAIsElevatedToken(HANDLE TokenHandle, _DWORD *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  int TokenInformation; // [rsp+58h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp+18h] BYREF
  int v9; // [rsp+68h] [rbp+20h] BYREF

  ReturnLength = 0;
  v9 = 0;
  TokenInformation = 1;
  *a3 = 1;
  *a2 = 0;
  result = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( result >= 0 )
  {
    if ( TokenInformation == 2
      || TokenInformation == 1
      && (*a3 = 0, result = NtQueryInformationToken(TokenHandle, TokenElevation, &v9, 4u, &ReturnLength), result >= 0)
      && v9 )
    {
      *a2 = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000250c  mov     rax, rsp
0x18000250f  push    rbx
0x180002510  push    rsi
0x180002511  push    rdi
0x180002512  sub     rsp, 30h
0x180002516  mov     r9d, 4; TokenInformationLength
0x18000251c  mov     dword ptr [rax+18h], 0
0x180002523  mov     dword ptr [rax+20h], 0
0x18000252a  mov     rdi, r8
0x18000252d  mov     dword ptr [rax+10h], 1
0x180002534  lea     rax, [rax+18h]
0x180002538  mov     rbx, rdx
0x18000253b  mov     dword ptr [r8], 1
0x180002542  mov     dword ptr [rdx], 0
0x180002548  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18000254d  lea     edx, [r9+0Eh]; TokenInformationClass
0x180002551  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180002556  mov     rsi, rcx
0x180002559  call    cs:__imp_NtQueryInformationToken
0x180002560  nop     dword ptr [rax+rax+00h]
0x180002565  test    eax, eax
0x180002567  js      short loc_1800025B6
0x180002569  cmp     [rsp+48h+TokenInformation], 2
0x18000256e  jz      short loc_1800025B0
0x180002570  cmp     [rsp+48h+TokenInformation], 1
0x180002575  jnz     short loc_1800025B6
0x180002577  mov     r9d, 4; TokenInformationLength
0x18000257d  mov     dword ptr [rdi], 0
0x180002583  lea     rax, [rsp+48h+arg_10]
0x180002588  mov     rcx, rsi; TokenHandle
0x18000258b  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x180002590  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180002595  lea     edx, [r9+10h]; TokenInformationClass
0x180002599  call    cs:__imp_NtQueryInformationToken
0x1800025a0  nop     dword ptr [rax+rax+00h]
0x1800025a5  test    eax, eax
0x1800025a7  js      short loc_1800025B6
0x1800025a9  cmp     [rsp+48h+arg_18], 0
0x1800025ae  jz      short loc_1800025B6
0x1800025b0  mov     dword ptr [rbx], 1
0x1800025b6  add     rsp, 30h
0x1800025ba  pop     rdi
0x1800025bb  pop     rsi
0x1800025bc  pop     rbx
0x1800025bd  retn
```
