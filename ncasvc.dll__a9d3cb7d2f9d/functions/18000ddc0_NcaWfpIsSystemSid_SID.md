# NcaWfpIsSystemSid(_SID *)

- ea: `0x18000ddc0`
- end: `0x18000de45`
- name: `?NcaWfpIsSystemSid@@YAHPEAU_SID@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(struct _SID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000de50`

## callees

- `0x18000ddc0`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000ddfb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18000ddfb`

## pseudocode

```c
__int64 __fastcall NcaWfpIsSystemSid(struct _SID *a1)
{
  unsigned int v1; // edi
  int Source2; // [rsp+20h] [rbp-18h] BYREF
  __int16 v5; // [rsp+24h] [rbp-14h]

  v1 = 0;
  v5 = 1280;
  Source2 = 0;
  if ( a1
    && RtlCompareMemory(&a1->IdentifierAuthority, &Source2, 6u) == 6
    && a1->SubAuthorityCount == 1
    && (a1->SubAuthority[0] == 18 || a1->SubAuthority[0] - 19 <= 1) )
  {
    return 1;
  }
  return v1;
}

```

## disassembly

```asm
0x18000ddc0  mov     [rsp+arg_8], rbx
0x18000ddc5  push    rdi
0x18000ddc6  sub     rsp, 30h
0x18000ddca  mov     rax, cs:__security_cookie
0x18000ddd1  xor     rax, rsp
0x18000ddd4  mov     [rsp+38h+var_10], rax
0x18000ddd9  xor     edi, edi
0x18000dddb  mov     [rsp+38h+var_14], 500h
0x18000dde2  mov     [rsp+38h+Source2], edi
0x18000dde6  mov     rbx, rcx
0x18000dde9  test    rcx, rcx
0x18000ddec  jz      short loc_18000DE2A
0x18000ddee  add     rcx, 2; Source1
0x18000ddf2  lea     r8d, [rdi+6]; Length
0x18000ddf6  lea     rdx, [rsp+38h+Source2]; Source2
0x18000ddfb  call    cs:__imp_RtlCompareMemory
0x18000de02  nop     dword ptr [rax+rax+00h]
0x18000de07  cmp     rax, 6
0x18000de0b  jnz     short loc_18000DE2A
0x18000de0d  cmp     byte ptr [rbx+1], 1
0x18000de11  jnz     short loc_18000DE2A
0x18000de13  mov     ecx, [rbx+8]
0x18000de16  sub     ecx, 12h
0x18000de19  jz      short loc_18000DE25
0x18000de1b  sub     ecx, 1
0x18000de1e  jz      short loc_18000DE25
0x18000de20  cmp     ecx, 1
0x18000de23  jnz     short loc_18000DE2A
0x18000de25  mov     edi, 1
0x18000de2a  mov     eax, edi
0x18000de2c  mov     rcx, [rsp+38h+var_10]
0x18000de31  xor     rcx, rsp; StackCookie
0x18000de34  call    __security_check_cookie
0x18000de39  mov     rbx, [rsp+38h+arg_8]
0x18000de3e  add     rsp, 30h
0x18000de42  pop     rdi
0x18000de43  retn
```
