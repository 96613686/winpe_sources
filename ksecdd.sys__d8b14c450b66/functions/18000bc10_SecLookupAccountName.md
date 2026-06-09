# SecLookupAccountName

- ea: `0x18000bc10`
- end: `0x18000bc57`
- name: `SecLookupAccountName`
- size: `71`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING Name, PULONG SidSize, PSID Sid, PSID_NAME_USE NameUse, PULONG DomainSize, PUNICODE_STRING ReferencedDomain)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18000bc10`
- `0x18002092c`

## pseudocode

```c
NTSTATUS __stdcall SecLookupAccountName(
        PUNICODE_STRING Name,
        PULONG SidSize,
        PSID Sid,
        PSID_NAME_USE NameUse,
        PULONG DomainSize,
        PUNICODE_STRING ReferencedDomain)
{
  UNICODE_STRING *v7; // rdx
  __int128 v9; // [rsp+30h] [rbp-18h] BYREF

  v7 = (UNICODE_STRING *)&v9;
  v9 = 0;
  if ( ReferencedDomain && ReferencedDomain->MaximumLength )
    v7 = ReferencedDomain;
  return SecpLookupAccountName(&Name->Length, v7, DomainSize, SidSize, Sid, NameUse);
}

```

## disassembly

```asm
0x18000bc10  sub     rsp, 48h
0x18000bc14  mov     rax, [rsp+48h+ReferencedDomain]
0x18000bc19  xor     r11d, r11d
0x18000bc1c  xorps   xmm0, xmm0
0x18000bc1f  mov     r10, rdx
0x18000bc22  lea     rdx, [rsp+48h+var_18]
0x18000bc27  movups  [rsp+48h+var_18], xmm0
0x18000bc2c  test    rax, rax
0x18000bc2f  jz      short loc_18000BC3A
0x18000bc31  cmp     [rax+2], r11w
0x18000bc36  cmova   rdx, rax
0x18000bc3a  mov     [rsp+48h+var_20], r9
0x18000bc3f  mov     r9, r10
0x18000bc42  mov     [rsp+48h+var_28], r8
0x18000bc47  mov     r8, [rsp+48h+DomainSize]
0x18000bc4c  call    SecpLookupAccountName
0x18000bc51  add     rsp, 48h
0x18000bc55  retn
```
