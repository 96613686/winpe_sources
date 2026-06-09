# LUAIsUserUACAdminEx

- ea: `0x14001cf8c`
- end: `0x14001d053`
- name: `LUAIsUserUACAdminEx`
- size: `199`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000cfdc`

## callees

- `0x140010ca4`
- `0x14001cdbc`
- `0x14001ce60`
- `0x14001ce9c`
- `0x14001cf8c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d032`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001d032`

## pseudocode

```c
__int64 __fastcall LUAIsUserUACAdminEx(HANDLE TokenHandle, _DWORD *a2)
{
  int v5; // esi
  int v6; // eax
  void *v7; // rcx
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenInformation; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    return 3221225474LL;
  ReturnLength = 0;
  LODWORD(TokenInformation) = 0;
  v5 = LUAIsElevatedToken(TokenHandle);
  if ( v5 >= 0 )
  {
    if ( ReturnLength )
    {
      *a2 = _LUAIsTokenAdmin(TokenHandle);
    }
    else
    {
      TokenInformation = 0;
      ReturnLength = 8;
      if ( GetTokenInformation_0(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength) )
      {
        if ( TokenInformation )
        {
          v6 = _LUAIsTokenAdmin(TokenInformation);
          v7 = TokenInformation;
          *a2 = v6;
          CloseHandle(v7);
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001cf8c  mov     [rsp+arg_0], rbx
0x14001cf91  mov     [rsp+arg_18], rsi
0x14001cf96  push    rdi
0x14001cf97  sub     rsp, 30h
0x14001cf9b  mov     rbx, rdx
0x14001cf9e  mov     dword ptr [rdx], 0
0x14001cfa4  mov     rdi, rcx
0x14001cfa7  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x14001cfac  test    eax, eax
0x14001cfae  jnz     short loc_14001CFBA
0x14001cfb0  mov     eax, 0C0000002h
0x14001cfb5  jmp     loc_14001D043
0x14001cfba  lea     r8, [rsp+38h+TokenInformation]
0x14001cfbf  mov     [rsp+38h+arg_8], 0
0x14001cfc7  lea     rdx, [rsp+38h+arg_8]
0x14001cfcc  mov     dword ptr [rsp+38h+TokenInformation], 0
0x14001cfd4  mov     rcx, rdi; TokenHandle
0x14001cfd7  call    LUAIsElevatedToken
0x14001cfdc  mov     esi, eax
0x14001cfde  test    eax, eax
0x14001cfe0  js      short loc_14001D041
0x14001cfe2  cmp     [rsp+38h+arg_8], 0
0x14001cfe7  mov     rcx, rdi; void *
0x14001cfea  jnz     short loc_14001D03A
0x14001cfec  mov     r9d, 8; TokenInformationLength
0x14001cff2  mov     [rsp+38h+TokenInformation], 0
0x14001cffb  lea     rax, [rsp+38h+arg_8]
0x14001d000  mov     [rsp+38h+arg_8], r9d
0x14001d005  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x14001d00a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14001d00f  lea     edx, [r9+0Bh]; TokenInformationClass
0x14001d013  call    GetTokenInformation_0
0x14001d018  test    eax, eax
0x14001d01a  jz      short loc_14001D041
0x14001d01c  mov     rcx, [rsp+38h+TokenInformation]; void *
0x14001d021  test    rcx, rcx
0x14001d024  jz      short loc_14001D041
0x14001d026  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x14001d02b  mov     rcx, [rsp+38h+TokenInformation]; hObject
0x14001d030  mov     [rbx], eax
0x14001d032  call    cs:__imp_CloseHandle
0x14001d038  jmp     short loc_14001D041
0x14001d03a  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x14001d03f  mov     [rbx], eax
0x14001d041  mov     eax, esi
0x14001d043  mov     rbx, [rsp+38h+arg_0]
0x14001d048  mov     rsi, [rsp+38h+arg_18]
0x14001d04d  add     rsp, 30h
0x14001d051  pop     rdi
0x14001d052  retn
```
