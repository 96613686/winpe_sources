# GetSidFromToken(void *)

- ea: `0x1800b096c`
- end: `0x1800b0a26`
- name: `?GetSidFromToken@@YAPEAXPEAX@Z`
- size: `186`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b0770`

## callees

- `0x1800b096c`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800b09a4`
- `KERNELBASE!LocalAlloc` at `0x1800b09e3`
- `KERNELBASE!LocalAlloc` at `0x1800b09a4`
- `KERNELBASE!LocalAlloc` at `0x1800b09e3`
- `ntdll!RtlCopySid` at `0x1800b09f9`
- `ntdll!RtlCopySid` at `0x1800b09f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0a0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0a14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0a0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b0a14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b0993`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b09c9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b0993`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b09c9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b09d6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b09d6`

## pseudocode

```c
void *__fastcall GetSidFromToken(HANDLE TokenHandle)
{
  void *v1; // rsi
  PSID *v3; // rbx
  ULONG LengthSid; // ebp
  HLOCAL v5; // rax
  void *v6; // rdi
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v3 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v3 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
      {
        LengthSid = GetLengthSid(*v3);
        v5 = LocalAlloc(0x40u, LengthSid);
        v6 = v5;
        if ( v5 )
        {
          if ( RtlCopySid(LengthSid, v5, *v3) )
            LocalFree(v6);
          else
            v1 = v6;
        }
      }
      LocalFree(v3);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800b096c  push    rbx
0x1800b096e  push    rbp
0x1800b096f  push    rsi
0x1800b0970  push    rdi
0x1800b0971  sub     rsp, 38h
0x1800b0975  xor     esi, esi
0x1800b0977  lea     rax, [rsp+58h+TokenInformationLength]
0x1800b097c  xor     r9d, r9d; TokenInformationLength
0x1800b097f  mov     [rsp+58h+TokenInformationLength], esi
0x1800b0983  xor     r8d, r8d; TokenInformation
0x1800b0986  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800b098b  mov     rdi, rcx
0x1800b098e  lea     ebp, [rsi+1]
0x1800b0991  mov     edx, ebp; TokenInformationClass
0x1800b0993  call    cs:__imp_GetTokenInformation
0x1800b0999  test    eax, eax
0x1800b099b  jnz     short loc_1800B0A1A
0x1800b099d  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x1800b09a1  lea     ecx, [rsi+40h]; uFlags
0x1800b09a4  call    cs:__imp_LocalAlloc
0x1800b09aa  mov     rbx, rax
0x1800b09ad  test    rax, rax
0x1800b09b0  jz      short loc_1800B0A1A
0x1800b09b2  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800b09b7  lea     rax, [rsp+58h+TokenInformationLength]
0x1800b09bc  mov     r8, rbx; TokenInformation
0x1800b09bf  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800b09c4  mov     edx, ebp; TokenInformationClass
0x1800b09c6  mov     rcx, rdi; TokenHandle
0x1800b09c9  call    cs:__imp_GetTokenInformation
0x1800b09cf  test    eax, eax
0x1800b09d1  jz      short loc_1800B0A11
0x1800b09d3  mov     rcx, [rbx]; pSid
0x1800b09d6  call    cs:__imp_GetLengthSid
0x1800b09dc  mov     edx, eax; uBytes
0x1800b09de  lea     ecx, [rsi+40h]; uFlags
0x1800b09e1  mov     ebp, eax
0x1800b09e3  call    cs:__imp_LocalAlloc
0x1800b09e9  mov     rdi, rax
0x1800b09ec  test    rax, rax
0x1800b09ef  jz      short loc_1800B0A11
0x1800b09f1  mov     r8, [rbx]; SourceSid
0x1800b09f4  mov     rdx, rax; DestinationSid
0x1800b09f7  mov     ecx, ebp; DestinationSidLength
0x1800b09f9  call    cs:__imp_RtlCopySid
0x1800b09ff  test    eax, eax
0x1800b0a01  jnz     short loc_1800B0A08
0x1800b0a03  mov     rsi, rdi
0x1800b0a06  jmp     short loc_1800B0A11
0x1800b0a08  mov     rcx, rdi; hMem
0x1800b0a0b  call    cs:__imp_LocalFree
0x1800b0a11  mov     rcx, rbx; hMem
0x1800b0a14  call    cs:__imp_LocalFree
0x1800b0a1a  mov     rax, rsi
0x1800b0a1d  add     rsp, 38h
0x1800b0a21  pop     rdi
0x1800b0a22  pop     rsi
0x1800b0a23  pop     rbp
0x1800b0a24  pop     rbx
0x1800b0a25  retn
```
