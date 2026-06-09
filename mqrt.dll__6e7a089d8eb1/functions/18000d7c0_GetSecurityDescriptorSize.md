# GetSecurityDescriptorSize

- ea: `0x18000d7c0`
- end: `0x18000d7e0`
- name: `GetSecurityDescriptorSize`
- size: `32`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d7e8`
- `0x18000d8b4`
- `0x18000d9c8`

## callees

- `0x18000d7c0`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorLength` at `0x18000d7ce`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18000d7ce`

## pseudocode

```c
DWORD __fastcall GetSecurityDescriptorSize(void *a1, DWORD *a2)
{
  DWORD result; // eax

  if ( a1 )
    result = GetSecurityDescriptorLength(a1);
  else
    result = 0;
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x18000d7c0  push    rbx
0x18000d7c2  sub     rsp, 20h
0x18000d7c6  mov     rbx, rdx
0x18000d7c9  test    rcx, rcx
0x18000d7cc  jz      short loc_18000D7D6
0x18000d7ce  call    cs:__imp_GetSecurityDescriptorLength
0x18000d7d4  jmp     short loc_18000D7D8
0x18000d7d6  xor     eax, eax
0x18000d7d8  mov     [rbx], eax
0x18000d7da  add     rsp, 20h
0x18000d7de  pop     rbx
0x18000d7df  retn
```
