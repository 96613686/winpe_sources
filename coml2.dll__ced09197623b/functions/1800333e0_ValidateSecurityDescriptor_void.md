# ValidateSecurityDescriptor(void *)

- ea: `0x1800333e0`
- end: `0x180033403`
- name: `?ValidateSecurityDescriptor@@YAJPEAX@Z`
- size: `35`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033280`
- `0x180039ef0`

## callees

- `0x1800333e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800333e9`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800333e9`

## pseudocode

```c
__int64 __fastcall ValidateSecurityDescriptor(void *a1)
{
  if ( a1 )
    return !IsValidSecurityDescriptor(a1) ? 0x80030057 : 0;
  else
    return 0;
}

```

## disassembly

```asm
0x1800333e0  sub     rsp, 28h
0x1800333e4  test    rcx, rcx
0x1800333e7  jz      short loc_1800333FC
0x1800333e9  call    cs:__imp_IsValidSecurityDescriptor
0x1800333ef  neg     eax
0x1800333f1  sbb     eax, eax
0x1800333f3  not     eax
0x1800333f5  and     eax, 80030057h
0x1800333fa  jmp     short loc_1800333FE
0x1800333fc  xor     eax, eax
0x1800333fe  add     rsp, 28h
0x180033402  retn
```
