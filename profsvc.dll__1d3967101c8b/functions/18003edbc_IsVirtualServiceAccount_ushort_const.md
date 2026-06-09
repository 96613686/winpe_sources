# IsVirtualServiceAccount(ushort const *)

- ea: `0x18003edbc`
- end: `0x18003ee32`
- name: `?IsVirtualServiceAccount@@YAHPEBG@Z`
- size: `118`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002f4fc`

## callees

- `0x18003ecf8`
- `0x18003edbc`
- `0x18003f19c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ee24`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003edd3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003edd3`

## pseudocode

```c
__int64 __fastcall IsVirtualServiceAccount(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
    v2 = IsVirtualServiceAccount(Sid);
  else
    v2 = StringIsPrefixed(a1, L"S-1-5-80") || StringIsPrefixed(a1, L"S-1-5-99");
  if ( Sid )
    LocalFree(Sid);
  return v2;
}

```

## disassembly

```asm
0x18003edbc  push    rbx
0x18003edbe  sub     rsp, 20h
0x18003edc2  lea     rdx, [rsp+28h+Sid]; Sid
0x18003edc7  mov     [rsp+28h+Sid], 0
0x18003edd0  mov     rbx, rcx
0x18003edd3  call    cs:__imp_ConvertStringSidToSidW
0x18003edd9  test    eax, eax
0x18003eddb  jz      short loc_18003EDEB
0x18003eddd  mov     rcx, [rsp+28h+Sid]; Sid
0x18003ede2  call    ?IsVirtualServiceAccount@@YAHPEAX@Z; IsVirtualServiceAccount(void *)
0x18003ede7  mov     ebx, eax
0x18003ede9  jmp     short loc_18003EE1A
0x18003edeb  lea     rdx, aS1580; "S-1-5-80"
0x18003edf2  mov     rcx, rbx; unsigned __int16 *
0x18003edf5  call    ?StringIsPrefixed@@YAHPEBG0@Z; StringIsPrefixed(ushort const *,ushort const *)
0x18003edfa  test    eax, eax
0x18003edfc  jnz     short loc_18003EE15
0x18003edfe  lea     rdx, aS1599; "S-1-5-99"
0x18003ee05  mov     rcx, rbx; unsigned __int16 *
0x18003ee08  call    ?StringIsPrefixed@@YAHPEBG0@Z; StringIsPrefixed(ushort const *,ushort const *)
0x18003ee0d  test    eax, eax
0x18003ee0f  jnz     short loc_18003EE15
0x18003ee11  xor     ebx, ebx
0x18003ee13  jmp     short loc_18003EE1A
0x18003ee15  mov     ebx, 1
0x18003ee1a  mov     rcx, [rsp+28h+Sid]; hMem
0x18003ee1f  test    rcx, rcx
0x18003ee22  jz      short loc_18003EE2A
0x18003ee24  call    cs:__imp_LocalFree
0x18003ee2a  mov     eax, ebx
0x18003ee2c  add     rsp, 20h
0x18003ee30  pop     rbx
0x18003ee31  retn
```
