# IsParameterSidEqualsUserSidOnToken

- ea: `0x180017578`
- end: `0x1800175ce`
- name: `IsParameterSidEqualsUserSidOnToken`
- size: `86`
- prototype: `__int64 __fastcall(PSID pSid2, LPCWSTR StringSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008954`

## callees

- `0x180017578`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800175bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800175bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017597`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017597`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800175a9`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800175a9`

## pseudocode

```c
__int64 __fastcall IsParameterSidEqualsUserSidOnToken(PSID pSid2, LPCWSTR StringSid)
{
  unsigned int v3; // ebx
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(StringSid, &Sid) )
    v3 = EqualSid(Sid, pSid2);
  if ( Sid )
    LocalFree(Sid);
  return v3;
}

```

## disassembly

```asm
0x180017578  mov     [rsp+arg_0], rbx
0x18001757d  push    rdi
0x18001757e  sub     rsp, 20h
0x180017582  mov     rax, rdx
0x180017585  mov     rdi, rcx
0x180017588  xor     ebx, ebx
0x18001758a  lea     rdx, [rsp+28h+Sid]; Sid
0x18001758f  mov     rcx, rax; StringSid
0x180017592  mov     [rsp+28h+Sid], rbx
0x180017597  call    cs:__imp_ConvertStringSidToSidW
0x18001759d  test    eax, eax
0x18001759f  jz      short loc_1800175B1
0x1800175a1  mov     rcx, [rsp+28h+Sid]; pSid1
0x1800175a6  mov     rdx, rdi; pSid2
0x1800175a9  call    cs:__imp_EqualSid
0x1800175af  mov     ebx, eax
0x1800175b1  mov     rcx, [rsp+28h+Sid]; hMem
0x1800175b6  test    rcx, rcx
0x1800175b9  jz      short loc_1800175C1
0x1800175bb  call    cs:__imp_LocalFree
0x1800175c1  mov     eax, ebx
0x1800175c3  mov     rbx, [rsp+28h+arg_0]
0x1800175c8  add     rsp, 20h
0x1800175cc  pop     rdi
0x1800175cd  retn
```
