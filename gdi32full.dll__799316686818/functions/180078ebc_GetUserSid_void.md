# GetUserSid(void *)

- ea: `0x180078ebc`
- end: `0x180078fb7`
- name: `?GetUserSid@@YAPEAXPEAX@Z`
- size: `251`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180069474`

## callees

- `0x180078ebc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078ed9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078f5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078ed9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180078f5f`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180078f1f`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180078f1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078f82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078f8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078f9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078f82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078f8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180078f9f`
- `ntdll!NtQueryInformationToken` at `0x180078f07`
- `ntdll!NtQueryInformationToken` at `0x180078f44`
- `ntdll!NtQueryInformationToken` at `0x180078f07`
- `ntdll!NtQueryInformationToken` at `0x180078f44`
- `ntdll!RtlLengthSid` at `0x180078f51`
- `ntdll!RtlLengthSid` at `0x180078f51`
- `ntdll!RtlCopySid` at `0x180078f77`
- `ntdll!RtlCopySid` at `0x180078f77`

## pseudocode

```c
void *__fastcall GetUserSid(HANDLE TokenHandle)
{
  PSID *v2; // rdi
  NTSTATUS v3; // eax
  PSID *v4; // rax
  HLOCAL v5; // rax
  void *v6; // rsi
  NTSTATUS v7; // ebx
  ULONG TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = 200;
  v2 = (PSID *)LocalAlloc(0, 0xC8u);
  if ( !v2 )
    return 0;
  v3 = NtQueryInformationToken(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength);
  if ( v3 == -1073741789 )
  {
    v4 = (PSID *)LocalReAlloc(v2, TokenInformationLength, 2u);
    if ( !v4 )
    {
LABEL_10:
      LocalFree(v2);
      return 0;
    }
    v2 = v4;
    v3 = NtQueryInformationToken(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength);
  }
  if ( v3 < 0 )
    goto LABEL_10;
  TokenInformationLength = RtlLengthSid(*v2);
  v5 = LocalAlloc(0, TokenInformationLength);
  v6 = v5;
  if ( !v5 )
    goto LABEL_10;
  v7 = RtlCopySid(TokenInformationLength, v5, *v2);
  LocalFree(v2);
  if ( v7 < 0 )
  {
    LocalFree(v6);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180078ebc  mov     [rsp+arg_0], rbx
0x180078ec1  mov     [rsp+arg_10], rsi
0x180078ec6  push    rdi
0x180078ec7  sub     rsp, 30h
0x180078ecb  mov     rbx, rcx
0x180078ece  mov     edx, 0C8h; uBytes
0x180078ed3  xor     ecx, ecx; uFlags
0x180078ed5  mov     [rsp+38h+TokenInformationLength], edx
0x180078ed9  call    cs:__imp_LocalAlloc
0x180078edf  mov     rdi, rax
0x180078ee2  test    rax, rax
0x180078ee5  jz      loc_180078FA5
0x180078eeb  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180078ef0  lea     rax, [rsp+38h+TokenInformationLength]
0x180078ef5  mov     esi, 1
0x180078efa  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180078eff  mov     edx, esi; TokenInformationClass
0x180078f01  mov     r8, rdi; TokenInformation
0x180078f04  mov     rcx, rbx; TokenHandle
0x180078f07  call    cs:__imp_NtQueryInformationToken
0x180078f0d  cmp     eax, 0C0000023h
0x180078f12  jnz     short loc_180078F4A
0x180078f14  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180078f18  lea     r8d, [rsi+1]; uFlags
0x180078f1c  mov     rcx, rdi; hMem
0x180078f1f  call    cs:__imp_LocalReAlloc
0x180078f25  test    rax, rax
0x180078f28  jz      short loc_180078F9C
0x180078f2a  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180078f2f  lea     rcx, [rsp+38h+TokenInformationLength]
0x180078f34  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180078f39  mov     r8, rax; TokenInformation
0x180078f3c  mov     rcx, rbx; TokenHandle
0x180078f3f  mov     edx, esi; TokenInformationClass
0x180078f41  mov     rdi, rax
0x180078f44  call    cs:__imp_NtQueryInformationToken
0x180078f4a  test    eax, eax
0x180078f4c  js      short loc_180078F9C
0x180078f4e  mov     rcx, [rdi]; Sid
0x180078f51  call    cs:__imp_RtlLengthSid
0x180078f57  mov     edx, eax; uBytes
0x180078f59  xor     ecx, ecx; uFlags
0x180078f5b  mov     [rsp+38h+TokenInformationLength], edx
0x180078f5f  call    cs:__imp_LocalAlloc
0x180078f65  mov     rsi, rax
0x180078f68  test    rax, rax
0x180078f6b  jz      short loc_180078F9C
0x180078f6d  mov     r8, [rdi]; SourceSid
0x180078f70  mov     rdx, rax; DestinationSid
0x180078f73  mov     ecx, [rsp+38h+TokenInformationLength]; DestinationSidLength
0x180078f77  call    cs:__imp_RtlCopySid
0x180078f7d  mov     rcx, rdi; hMem
0x180078f80  mov     ebx, eax
0x180078f82  call    cs:__imp_LocalFree
0x180078f88  test    ebx, ebx
0x180078f8a  jns     short loc_180078F97
0x180078f8c  mov     rcx, rsi; hMem
0x180078f8f  call    cs:__imp_LocalFree
0x180078f95  xor     esi, esi
0x180078f97  mov     rax, rsi
0x180078f9a  jmp     short loc_180078FA7
0x180078f9c  mov     rcx, rdi; hMem
0x180078f9f  call    cs:__imp_LocalFree
0x180078fa5  xor     eax, eax
0x180078fa7  mov     rbx, [rsp+38h+arg_0]
0x180078fac  mov     rsi, [rsp+38h+arg_10]
0x180078fb1  add     rsp, 30h
0x180078fb5  pop     rdi
0x180078fb6  retn
```
