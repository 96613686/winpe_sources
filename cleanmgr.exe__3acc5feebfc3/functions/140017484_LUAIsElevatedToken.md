# LUAIsElevatedToken

- ea: `0x140017484`
- end: `0x14001752a`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001737c`

## callees

- `0x140017484`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1400174d1`
- `ntdll!NtQueryInformationToken` at `0x14001750b`
- `ntdll!NtQueryInformationToken` at `0x1400174d1`
- `ntdll!NtQueryInformationToken` at `0x14001750b`

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
0x140017484  mov     rax, rsp
0x140017487  push    rbx
0x140017488  push    rsi
0x140017489  push    rdi
0x14001748a  sub     rsp, 30h
0x14001748e  mov     r9d, 4; TokenInformationLength
0x140017494  mov     dword ptr [rax+18h], 0
0x14001749b  mov     dword ptr [rax+20h], 0
0x1400174a2  mov     rdi, r8
0x1400174a5  mov     dword ptr [rax+10h], 1
0x1400174ac  lea     rax, [rax+18h]
0x1400174b0  mov     rbx, rdx
0x1400174b3  mov     dword ptr [r8], 1
0x1400174ba  mov     dword ptr [rdx], 0
0x1400174c0  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1400174c5  lea     edx, [r9+0Eh]; TokenInformationClass
0x1400174c9  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1400174ce  mov     rsi, rcx
0x1400174d1  call    cs:__imp_NtQueryInformationToken
0x1400174d7  test    eax, eax
0x1400174d9  js      short loc_140017522
0x1400174db  cmp     [rsp+48h+TokenInformation], 2
0x1400174e0  jz      short loc_14001751C
0x1400174e2  cmp     [rsp+48h+TokenInformation], 1
0x1400174e7  jnz     short loc_140017522
0x1400174e9  mov     r9d, 4; TokenInformationLength
0x1400174ef  mov     dword ptr [rdi], 0
0x1400174f5  lea     rax, [rsp+48h+arg_10]
0x1400174fa  mov     rcx, rsi; TokenHandle
0x1400174fd  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x140017502  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140017507  lea     edx, [r9+10h]; TokenInformationClass
0x14001750b  call    cs:__imp_NtQueryInformationToken
0x140017511  test    eax, eax
0x140017513  js      short loc_140017522
0x140017515  cmp     [rsp+48h+arg_18], 0
0x14001751a  jz      short loc_140017522
0x14001751c  mov     dword ptr [rbx], 1
0x140017522  add     rsp, 30h
0x140017526  pop     rdi
0x140017527  pop     rsi
0x140017528  pop     rbx
0x140017529  retn
```
