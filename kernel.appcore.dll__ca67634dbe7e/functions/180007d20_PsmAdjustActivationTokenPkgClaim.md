# PsmAdjustActivationTokenPkgClaim

- ea: `0x180007d20`
- end: `0x180007e4f`
- name: `PsmAdjustActivationTokenPkgClaim`
- size: `303`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007d20`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x180007e10`
- `ntdll!RtlAcquirePrivilege` at `0x180007e10`
- `ntdll!RtlQueryPackageClaims` at `0x180007da1`
- `ntdll!RtlQueryPackageClaims` at `0x180007da1`
- `ntdll!RtlInitUnicodeString` at `0x180007ddf`
- `ntdll!RtlInitUnicodeString` at `0x180007ddf`
- `ntdll!NtSetInformationToken` at `0x180007e28`
- `ntdll!NtSetInformationToken` at `0x180007e28`
- `ntdll!RtlReleasePrivilege` at `0x180007e34`
- `ntdll!RtlReleasePrivilege` at `0x180007e34`

## pseudocode

```c
NTSTATUS __fastcall PsmAdjustActivationTokenPkgClaim(HANDLE TokenHandle, int a2)
{
  NTSTATUS result; // eax
  NTSTATUS v5; // ebx
  PVOID ReturnedState; // [rsp+40h] [rbp-9h] BYREF
  __int128 v7; // [rsp+48h] [rbp-1h] BYREF
  __int128 TokenInformation; // [rsp+58h] [rbp+Fh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+1Fh] BYREF
  __int128 v10; // [rsp+78h] [rbp+2Fh]
  __int64 *v11; // [rsp+88h] [rbp+3Fh]
  int v12; // [rsp+B8h] [rbp+6Fh] BYREF
  ULONG Privilege; // [rsp+C0h] [rbp+77h] BYREF
  __int64 v14; // [rsp+C8h] [rbp+7Fh] BYREF

  Privilege = 7;
  v11 = 0;
  v12 = 0;
  v14 = 0;
  ReturnedState = 0;
  DestinationString = 0;
  v10 = 0;
  v7 = 0;
  TokenInformation = 0;
  if ( (a2 & 0xFFFBF3F9) != 0 )
    return -1073741811;
  result = RtlQueryPackageClaims(TokenHandle, 0, 0, 0, 0, 0, &v14, 0, (_DWORD)ReturnedState, v7);
  if ( result >= 0 )
  {
    LODWORD(v14) = a2 | v14;
    *(_QWORD *)&v10 = 2;
    DWORD2(v10) = 1;
    v11 = &v14;
    v12 = 4;
    RtlInitUnicodeString(&DestinationString, L"WIN://PKG");
    *(_QWORD *)&v7 = 0x100000001LL;
    *((_QWORD *)&v7 + 1) = &DestinationString;
    *(_QWORD *)&TokenInformation = &v7;
    *((_QWORD *)&TokenInformation + 1) = &v12;
    result = RtlAcquirePrivilege(&Privilege, 1u, 2u, &ReturnedState);
    if ( result >= 0 )
    {
      v5 = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
      RtlReleasePrivilege(ReturnedState);
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007d20  mov     [rsp-8+arg_0], rbx
0x180007d25  push    rbp
0x180007d26  push    rsi
0x180007d27  push    rdi
0x180007d28  lea     rbp, [rsp-47h]
0x180007d2d  sub     rsp, 90h
0x180007d34  xor     eax, eax
0x180007d36  mov     [rbp+57h+Privilege], 7
0x180007d3d  mov     [rbp+57h+var_18], rax
0x180007d41  xorps   xmm0, xmm0
0x180007d44  mov     [rbp+57h+arg_8], eax
0x180007d47  xorps   xmm1, xmm1
0x180007d4a  mov     [rbp+57h+arg_18], rax
0x180007d4e  mov     edi, edx
0x180007d50  mov     [rbp+57h+ReturnedState], rax
0x180007d54  mov     rbx, rcx
0x180007d57  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180007d5b  movups  [rbp+57h+var_28], xmm0
0x180007d5f  movups  [rbp+57h+var_58], xmm0
0x180007d63  movups  [rbp+57h+TokenInformation], xmm1
0x180007d67  test    edx, 0FFFBF3F9h
0x180007d6d  jz      short loc_180007D79
0x180007d6f  mov     eax, 0C000000Dh
0x180007d74  jmp     loc_180007E3C
0x180007d79  mov     [rsp+0A0h+var_68], rax
0x180007d7e  xor     r9d, r9d
0x180007d81  lea     rax, [rbp+57h+arg_18]
0x180007d85  xor     r8d, r8d
0x180007d88  mov     [rsp+0A0h+var_70], rax
0x180007d8d  xor     edx, edx
0x180007d8f  mov     [rsp+0A0h+var_78], 0
0x180007d98  mov     [rsp+0A0h+var_80], 0
0x180007da1  call    cs:__imp_RtlQueryPackageClaims
0x180007da7  test    eax, eax
0x180007da9  js      loc_180007E3C
0x180007daf  or      dword ptr [rbp+57h+arg_18], edi
0x180007db2  lea     rax, [rbp+57h+arg_18]
0x180007db6  mov     esi, 1
0x180007dbb  mov     qword ptr [rbp+57h+var_28], 2
0x180007dc3  lea     rdx, SourceString; "WIN://PKG"
0x180007dca  mov     dword ptr [rbp+57h+var_28+8], esi
0x180007dcd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180007dd1  mov     [rbp+57h+var_18], rax
0x180007dd5  mov     [rbp+57h+arg_8], 4
0x180007ddc  lea     edi, [rsi+1]
0x180007ddf  call    cs:__imp_RtlInitUnicodeString
0x180007de5  lea     rax, [rbp+57h+DestinationString]
0x180007de9  mov     dword ptr [rbp+57h+var_58], esi
0x180007dec  mov     qword ptr [rbp+57h+var_58+8], rax
0x180007df0  lea     r9, [rbp+57h+ReturnedState]; ReturnedState
0x180007df4  lea     rax, [rbp+57h+var_58]
0x180007df8  mov     dword ptr [rbp+57h+var_58+4], esi
0x180007dfb  mov     qword ptr [rbp+57h+TokenInformation], rax
0x180007dff  lea     rcx, [rbp+57h+Privilege]; Privilege
0x180007e03  lea     rax, [rbp+57h+arg_8]
0x180007e07  mov     r8d, edi; Flags
0x180007e0a  mov     edx, esi; NumPriv
0x180007e0c  mov     qword ptr [rbp+57h+TokenInformation+8], rax
0x180007e10  call    cs:__imp_RtlAcquirePrivilege
0x180007e16  test    eax, eax
0x180007e18  js      short loc_180007E3C
0x180007e1a  lea     r9d, [rsi+0Fh]; TokenInformationLength
0x180007e1e  mov     rcx, rbx; TokenHandle
0x180007e21  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180007e25  lea     edx, [rsi+26h]; TokenInformationClass
0x180007e28  call    cs:__imp_NtSetInformationToken
0x180007e2e  mov     rcx, [rbp+57h+ReturnedState]; ReturnedState
0x180007e32  mov     ebx, eax
0x180007e34  call    cs:__imp_RtlReleasePrivilege
0x180007e3a  mov     eax, ebx
0x180007e3c  mov     rbx, [rsp+0A0h+arg_0]
0x180007e44  add     rsp, 90h
0x180007e4b  pop     rdi
0x180007e4c  pop     rsi
0x180007e4d  pop     rbp
0x180007e4e  retn
```
