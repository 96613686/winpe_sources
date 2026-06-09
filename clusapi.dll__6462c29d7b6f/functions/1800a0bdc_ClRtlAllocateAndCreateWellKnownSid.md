# ClRtlAllocateAndCreateWellKnownSid

- ea: `0x1800a0bdc`
- end: `0x1800a0c65`
- name: `ClRtlAllocateAndCreateWellKnownSid`
- size: `137`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800795d0`
- `0x1800a1d98`

## callees

- `0x1800a0bdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0c49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0c5d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0c2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0c2a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a0bfa`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a0c3f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a0bfa`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a0c3f`

## pseudocode

```c
__int64 __fastcall ClRtlAllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, _QWORD *a2)
{
  HLOCAL v3; // rdi
  DWORD LastError; // ebx
  DWORD cbSid; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  cbSid = 0;
  if ( CreateWellKnownSid(WellKnownSidType, 0, 0, &cbSid) )
  {
    LastError = 50;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      LastError = 0;
      v3 = LocalAlloc(0, cbSid);
      if ( CreateWellKnownSid(WellKnownSidType, 0, v3, &cbSid) )
        goto LABEL_3;
      LastError = GetLastError();
    }
    if ( LastError && v3 )
    {
      LocalFree(v3);
      return LastError;
    }
  }
LABEL_3:
  *a2 = v3;
  return LastError;
}

```

## disassembly

```asm
0x1800a0bdc  push    rbx
0x1800a0bde  push    rbp
0x1800a0bdf  push    rsi
0x1800a0be0  push    rdi
0x1800a0be1  sub     rsp, 28h
0x1800a0be5  mov     rsi, rdx
0x1800a0be8  lea     r9, [rsp+48h+cbSid]; cbSid
0x1800a0bed  xor     edi, edi
0x1800a0bef  xor     edx, edx; DomainSid
0x1800a0bf1  xor     r8d, r8d; pSid
0x1800a0bf4  mov     [rsp+48h+cbSid], edi
0x1800a0bf8  mov     ebp, ecx
0x1800a0bfa  call    cs:__imp_CreateWellKnownSid
0x1800a0c00  test    eax, eax
0x1800a0c02  jz      short loc_1800A0C15
0x1800a0c04  lea     ebx, [rdi+32h]
0x1800a0c07  mov     [rsi], rdi
0x1800a0c0a  mov     eax, ebx
0x1800a0c0c  add     rsp, 28h
0x1800a0c10  pop     rdi
0x1800a0c11  pop     rsi
0x1800a0c12  pop     rbp
0x1800a0c13  pop     rbx
0x1800a0c14  retn
0x1800a0c15  call    cs:__imp_GetLastError
0x1800a0c1b  mov     ebx, eax
0x1800a0c1d  cmp     eax, 7Ah ; 'z'
0x1800a0c20  jnz     short loc_1800A0C51
0x1800a0c22  mov     edx, [rsp+48h+cbSid]; uBytes
0x1800a0c26  xor     ecx, ecx; uFlags
0x1800a0c28  xor     ebx, ebx
0x1800a0c2a  call    cs:__imp_LocalAlloc
0x1800a0c30  lea     r9, [rsp+48h+cbSid]; cbSid
0x1800a0c35  xor     edx, edx; DomainSid
0x1800a0c37  mov     r8, rax; pSid
0x1800a0c3a  mov     ecx, ebp; WellKnownSidType
0x1800a0c3c  mov     rdi, rax
0x1800a0c3f  call    cs:__imp_CreateWellKnownSid
0x1800a0c45  test    eax, eax
0x1800a0c47  jnz     short loc_1800A0C07
0x1800a0c49  call    cs:__imp_GetLastError
0x1800a0c4f  mov     ebx, eax
0x1800a0c51  test    ebx, ebx
0x1800a0c53  jz      short loc_1800A0C07
0x1800a0c55  test    rdi, rdi
0x1800a0c58  jz      short loc_1800A0C07
0x1800a0c5a  mov     rcx, rdi; hMem
0x1800a0c5d  call    cs:__imp_LocalFree
0x1800a0c63  jmp     short loc_1800A0C0A
```
