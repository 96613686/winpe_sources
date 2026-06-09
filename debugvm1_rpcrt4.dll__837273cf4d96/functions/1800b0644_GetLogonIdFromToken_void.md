# GetLogonIdFromToken(void *)

- ea: `0x1800b0644`
- end: `0x1800b06d8`
- name: `?GetLogonIdFromToken@@YA_JPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800b0770`

## callees

- `0x1800b0644`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800b067e`
- `KERNELBASE!LocalAlloc` at `0x1800b067e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b06bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b06bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b066e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b06a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b066e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b06a4`

## pseudocode

```c
__int64 __fastcall GetLogonIdFromToken(HANDLE TokenHandle)
{
  __int64 v1; // rbx
  unsigned int *v3; // rdi
  SIZE_T uBytes; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  LODWORD(uBytes) = 0;
  if ( !GetTokenInformation(TokenHandle, TokenStatistics, 0, 0, (PDWORD)&uBytes) )
  {
    v3 = (unsigned int *)LocalAlloc(0, (unsigned int)uBytes);
    if ( v3 )
    {
      if ( GetTokenInformation(TokenHandle, TokenStatistics, v3, uBytes, (PDWORD)&uBytes) )
        v1 = v3[2] + ((__int64)(int)v3[3] << 32);
      LocalFree(v3);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800b0644  mov     rax, rsp
0x1800b0647  mov     [rax+8], rbx
0x1800b064b  mov     [rax+18h], rsi
0x1800b064f  push    rdi
0x1800b0650  sub     rsp, 30h
0x1800b0654  xor     ebx, ebx
0x1800b0656  xor     r9d, r9d; TokenInformationLength
0x1800b0659  mov     [rax+10h], ebx
0x1800b065c  lea     rax, [rax+10h]
0x1800b0660  xor     r8d, r8d; TokenInformation
0x1800b0663  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800b0668  mov     rsi, rcx
0x1800b066b  lea     edx, [rbx+0Ah]; TokenInformationClass
0x1800b066e  call    cs:__imp_GetTokenInformation
0x1800b0674  test    eax, eax
0x1800b0676  jnz     short loc_1800B06C5
0x1800b0678  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x1800b067c  xor     ecx, ecx; uFlags
0x1800b067e  call    cs:__imp_LocalAlloc
0x1800b0684  mov     rdi, rax
0x1800b0687  test    rax, rax
0x1800b068a  jz      short loc_1800B06C5
0x1800b068c  mov     r9d, dword ptr [rsp+38h+uBytes]; TokenInformationLength
0x1800b0691  lea     rax, [rsp+38h+uBytes]
0x1800b0696  mov     r8, rdi; TokenInformation
0x1800b0699  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800b069e  lea     edx, [rbx+0Ah]; TokenInformationClass
0x1800b06a1  mov     rcx, rsi; TokenHandle
0x1800b06a4  call    cs:__imp_GetTokenInformation
0x1800b06aa  test    eax, eax
0x1800b06ac  jz      short loc_1800B06BC
0x1800b06ae  movsxd  rbx, dword ptr [rdi+0Ch]
0x1800b06b2  mov     ecx, [rdi+8]
0x1800b06b5  shl     rbx, 20h
0x1800b06b9  add     rbx, rcx
0x1800b06bc  mov     rcx, rdi; hMem
0x1800b06bf  call    cs:__imp_LocalFree
0x1800b06c5  mov     rsi, [rsp+38h+arg_10]
0x1800b06ca  mov     rax, rbx
0x1800b06cd  mov     rbx, [rsp+38h+arg_0]
0x1800b06d2  add     rsp, 30h
0x1800b06d6  pop     rdi
0x1800b06d7  retn
```
