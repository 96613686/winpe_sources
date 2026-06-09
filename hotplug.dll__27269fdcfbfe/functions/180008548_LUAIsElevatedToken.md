# LUAIsElevatedToken

- ea: `0x180008548`
- end: `0x1800085ee`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008440`

## callees

- `0x180008548`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180008595`
- `ntdll!NtQueryInformationToken` at `0x1800085cf`
- `ntdll!NtQueryInformationToken` at `0x180008595`
- `ntdll!NtQueryInformationToken` at `0x1800085cf`

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
0x180008548  mov     rax, rsp
0x18000854b  push    rbx
0x18000854c  push    rsi
0x18000854d  push    rdi
0x18000854e  sub     rsp, 30h
0x180008552  mov     r9d, 4; TokenInformationLength
0x180008558  mov     dword ptr [rax+18h], 0
0x18000855f  mov     dword ptr [rax+20h], 0
0x180008566  mov     rdi, r8
0x180008569  mov     dword ptr [rax+10h], 1
0x180008570  lea     rax, [rax+18h]
0x180008574  mov     rbx, rdx
0x180008577  mov     dword ptr [r8], 1
0x18000857e  mov     dword ptr [rdx], 0
0x180008584  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180008589  lea     edx, [r9+0Eh]; TokenInformationClass
0x18000858d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180008592  mov     rsi, rcx
0x180008595  call    cs:__imp_NtQueryInformationToken
0x18000859b  test    eax, eax
0x18000859d  js      short loc_1800085E6
0x18000859f  cmp     [rsp+48h+TokenInformation], 2
0x1800085a4  jz      short loc_1800085E0
0x1800085a6  cmp     [rsp+48h+TokenInformation], 1
0x1800085ab  jnz     short loc_1800085E6
0x1800085ad  mov     r9d, 4; TokenInformationLength
0x1800085b3  mov     dword ptr [rdi], 0
0x1800085b9  lea     rax, [rsp+48h+arg_10]
0x1800085be  mov     rcx, rsi; TokenHandle
0x1800085c1  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x1800085c6  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800085cb  lea     edx, [r9+10h]; TokenInformationClass
0x1800085cf  call    cs:__imp_NtQueryInformationToken
0x1800085d5  test    eax, eax
0x1800085d7  js      short loc_1800085E6
0x1800085d9  cmp     [rsp+48h+arg_18], 0
0x1800085de  jz      short loc_1800085E6
0x1800085e0  mov     dword ptr [rbx], 1
0x1800085e6  add     rsp, 30h
0x1800085ea  pop     rdi
0x1800085eb  pop     rsi
0x1800085ec  pop     rbx
0x1800085ed  retn
```
