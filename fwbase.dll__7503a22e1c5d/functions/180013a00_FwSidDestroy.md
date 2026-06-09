# FwSidDestroy

- ea: `0x180013a00`
- end: `0x180013a0d`
- name: `FwSidDestroy`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180013a00`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180013a06`

## pseudocode

```c
PVOID __fastcall FwSidDestroy(void *a1)
{
  PVOID result; // rax

  if ( a1 )
    return FreeSid(a1);
  return result;
}

```

## disassembly

```asm
0x180013a00  test    rcx, rcx
0x180013a03  jnz     short loc_180013A06
0x180013a05  retn
0x180013a06  jmp     cs:__imp_FreeSid
```
