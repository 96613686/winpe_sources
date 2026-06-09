# IsSameUser(char *,char *)

- ea: `0x18004a8f4`
- end: `0x18004a90e`
- name: `?IsSameUser@@YAHPEAD0@Z`
- size: `26`
- prototype: `__int64 __fastcall(char *, char *)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004890`
- `0x1800057e0`
- `0x180005988`
- `0x18002ac34`
- `0x18002adc8`

## callees

- `0x18004a8f4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004a904`

## pseudocode

```c
BOOL __fastcall IsSameUser(PSID *a1, PSID *a2)
{
  return a1 && a2 && EqualSid(*a1, *a2);
}

```

## disassembly

```asm
0x18004a8f4  test    rcx, rcx
0x18004a8f7  jz      short loc_18004A90B
0x18004a8f9  test    rdx, rdx
0x18004a8fc  jz      short loc_18004A90B
0x18004a8fe  mov     rdx, [rdx]
0x18004a901  mov     rcx, [rcx]
0x18004a904  jmp     cs:__imp_EqualSid
0x18004a90b  xor     eax, eax
0x18004a90d  retn
```
