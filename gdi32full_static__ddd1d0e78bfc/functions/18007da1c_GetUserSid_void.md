# GetUserSid(void *)

- ea: `0x18007da1c`
- end: `0x18007db58`
- name: `?GetUserSid@@YAPEAXPEAX@Z`
- size: `316`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006d76c`

## callees

- `0x18007da1c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007da39`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007dae1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007da39`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007dae1`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18007da8b`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18007da8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007db10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007db23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007db39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007db10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007db23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007db39`
- `ntdll!NtQueryInformationToken` at `0x18007da6d`
- `ntdll!NtQueryInformationToken` at `0x18007daba`
- `ntdll!NtQueryInformationToken` at `0x18007da6d`
- `ntdll!NtQueryInformationToken` at `0x18007daba`
- `ntdll!RtlLengthSid` at `0x18007dacd`
- `ntdll!RtlLengthSid` at `0x18007dacd`
- `ntdll!RtlCopySid` at `0x18007daff`
- `ntdll!RtlCopySid` at `0x18007daff`

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
0x18007da1c  mov     [rsp+arg_0], rbx
0x18007da21  mov     [rsp+arg_10], rsi
0x18007da26  push    rdi
0x18007da27  sub     rsp, 30h
0x18007da2b  mov     rbx, rcx
0x18007da2e  mov     edx, 0C8h; uBytes
0x18007da33  xor     ecx, ecx; uFlags
0x18007da35  mov     [rsp+38h+TokenInformationLength], edx
0x18007da39  call    cs:__imp_LocalAlloc
0x18007da40  nop     dword ptr [rax+rax+00h]
0x18007da45  mov     rdi, rax
0x18007da48  test    rax, rax
0x18007da4b  jz      loc_18007DB45
0x18007da51  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18007da56  lea     rax, [rsp+38h+TokenInformationLength]
0x18007da5b  mov     esi, 1
0x18007da60  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18007da65  mov     edx, esi; TokenInformationClass
0x18007da67  mov     r8, rdi; TokenInformation
0x18007da6a  mov     rcx, rbx; TokenHandle
0x18007da6d  call    cs:__imp_NtQueryInformationToken
0x18007da74  nop     dword ptr [rax+rax+00h]
0x18007da79  cmp     eax, 0C0000023h
0x18007da7e  jnz     short loc_18007DAC6
0x18007da80  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x18007da84  lea     r8d, [rsi+1]; uFlags
0x18007da88  mov     rcx, rdi; hMem
0x18007da8b  call    cs:__imp_LocalReAlloc
0x18007da92  nop     dword ptr [rax+rax+00h]
0x18007da97  test    rax, rax
0x18007da9a  jz      loc_18007DB36
0x18007daa0  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18007daa5  lea     rcx, [rsp+38h+TokenInformationLength]
0x18007daaa  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x18007daaf  mov     r8, rax; TokenInformation
0x18007dab2  mov     rcx, rbx; TokenHandle
0x18007dab5  mov     edx, esi; TokenInformationClass
0x18007dab7  mov     rdi, rax
0x18007daba  call    cs:__imp_NtQueryInformationToken
0x18007dac1  nop     dword ptr [rax+rax+00h]
0x18007dac6  test    eax, eax
0x18007dac8  js      short loc_18007DB36
0x18007daca  mov     rcx, [rdi]; Sid
0x18007dacd  call    cs:__imp_RtlLengthSid
0x18007dad4  nop     dword ptr [rax+rax+00h]
0x18007dad9  mov     edx, eax; uBytes
0x18007dadb  xor     ecx, ecx; uFlags
0x18007dadd  mov     [rsp+38h+TokenInformationLength], edx
0x18007dae1  call    cs:__imp_LocalAlloc
0x18007dae8  nop     dword ptr [rax+rax+00h]
0x18007daed  mov     rsi, rax
0x18007daf0  test    rax, rax
0x18007daf3  jz      short loc_18007DB36
0x18007daf5  mov     r8, [rdi]; SourceSid
0x18007daf8  mov     rdx, rax; DestinationSid
0x18007dafb  mov     ecx, [rsp+38h+TokenInformationLength]; DestinationSidLength
0x18007daff  call    cs:__imp_RtlCopySid
0x18007db06  nop     dword ptr [rax+rax+00h]
0x18007db0b  mov     rcx, rdi; hMem
0x18007db0e  mov     ebx, eax
0x18007db10  call    cs:__imp_LocalFree
0x18007db17  nop     dword ptr [rax+rax+00h]
0x18007db1c  test    ebx, ebx
0x18007db1e  jns     short loc_18007DB31
0x18007db20  mov     rcx, rsi; hMem
0x18007db23  call    cs:__imp_LocalFree
0x18007db2a  nop     dword ptr [rax+rax+00h]
0x18007db2f  xor     esi, esi
0x18007db31  mov     rax, rsi
0x18007db34  jmp     short loc_18007DB47
0x18007db36  mov     rcx, rdi; hMem
0x18007db39  call    cs:__imp_LocalFree
0x18007db40  nop     dword ptr [rax+rax+00h]
0x18007db45  xor     eax, eax
0x18007db47  mov     rbx, [rsp+38h+arg_0]
0x18007db4c  mov     rsi, [rsp+38h+arg_10]
0x18007db51  add     rsp, 30h
0x18007db55  pop     rdi
0x18007db56  retn
```
