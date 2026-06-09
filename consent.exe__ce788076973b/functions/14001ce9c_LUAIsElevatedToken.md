# LUAIsElevatedToken

- ea: `0x14001ce9c`
- end: `0x14001cf42`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001cf8c`

## callees

- `0x14001ce9c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x14001cee9`
- `ntdll!NtQueryInformationToken` at `0x14001cf23`
- `ntdll!NtQueryInformationToken` at `0x14001cee9`
- `ntdll!NtQueryInformationToken` at `0x14001cf23`

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
0x14001ce9c  mov     rax, rsp
0x14001ce9f  push    rbx
0x14001cea0  push    rsi
0x14001cea1  push    rdi
0x14001cea2  sub     rsp, 30h
0x14001cea6  mov     r9d, 4; TokenInformationLength
0x14001ceac  mov     dword ptr [rax+18h], 0
0x14001ceb3  mov     dword ptr [rax+20h], 0
0x14001ceba  mov     rdi, r8
0x14001cebd  mov     dword ptr [rax+10h], 1
0x14001cec4  lea     rax, [rax+18h]
0x14001cec8  mov     rbx, rdx
0x14001cecb  mov     dword ptr [r8], 1
0x14001ced2  mov     dword ptr [rdx], 0
0x14001ced8  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14001cedd  lea     edx, [r9+0Eh]; TokenInformationClass
0x14001cee1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14001cee6  mov     rsi, rcx
0x14001cee9  call    cs:__imp_NtQueryInformationToken
0x14001ceef  test    eax, eax
0x14001cef1  js      short loc_14001CF3A
0x14001cef3  cmp     [rsp+48h+TokenInformation], 2
0x14001cef8  jz      short loc_14001CF34
0x14001cefa  cmp     [rsp+48h+TokenInformation], 1
0x14001ceff  jnz     short loc_14001CF3A
0x14001cf01  mov     r9d, 4; TokenInformationLength
0x14001cf07  mov     dword ptr [rdi], 0
0x14001cf0d  lea     rax, [rsp+48h+arg_10]
0x14001cf12  mov     rcx, rsi; TokenHandle
0x14001cf15  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x14001cf1a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14001cf1f  lea     edx, [r9+10h]; TokenInformationClass
0x14001cf23  call    cs:__imp_NtQueryInformationToken
0x14001cf29  test    eax, eax
0x14001cf2b  js      short loc_14001CF3A
0x14001cf2d  cmp     [rsp+48h+arg_18], 0
0x14001cf32  jz      short loc_14001CF3A
0x14001cf34  mov     dword ptr [rbx], 1
0x14001cf3a  add     rsp, 30h
0x14001cf3e  pop     rdi
0x14001cf3f  pop     rsi
0x14001cf40  pop     rbx
0x14001cf41  retn
```
