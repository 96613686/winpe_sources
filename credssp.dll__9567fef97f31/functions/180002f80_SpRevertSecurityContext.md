# SpRevertSecurityContext

- ea: `0x180002f80`
- end: `0x180002f9a`
- name: `SpRevertSecurityContext`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002f80`

## import_xrefs

- `SspiCli!RevertSecurityContext` at `0x180002f93`

## pseudocode

```c
SECURITY_STATUS __fastcall SpRevertSecurityContext(__int64 a1)
{
  if ( a1 )
    return RevertSecurityContext((PCtxtHandle)(*(_QWORD *)(a1 + 8) + 16LL));
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180002f80  test    rcx, rcx
0x180002f83  jnz     short loc_180002F8B
0x180002f85  mov     eax, 80090301h
0x180002f8a  retn
0x180002f8b  mov     rcx, [rcx+8]
0x180002f8f  add     rcx, 10h
0x180002f93  jmp     cs:__imp_RevertSecurityContext
```
