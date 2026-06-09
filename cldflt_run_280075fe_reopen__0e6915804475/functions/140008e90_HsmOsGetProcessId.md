# HsmOsGetProcessId

- ea: `0x140008e90`
- end: `0x140008ebd`
- name: `HsmOsGetProcessId`
- size: `45`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140008d4c`
- `0x14003fc70`
- `0x140040090`
- `0x140049778`
- `0x140076810`
- `0x14007a0d4`
- `0x1400829e0`

## callees

- `0x140008e90`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140008ea6`
- `ntoskrnl!PsGetProcessId` at `0x140008ea6`

## pseudocode

```c
HANDLE __fastcall HsmOsGetProcessId(__int64 a1)
{
  __int64 v1; // rax

  if ( a1 && (v1 = *(_QWORD *)(a1 + 8)) != 0 )
    return (HANDLE)*(unsigned int *)(v1 + 24);
  else
    return PsGetProcessId(*(PEPROCESS *)(a1 + 16));
}

```

## disassembly

```asm
0x140008e90  sub     rsp, 28h
0x140008e94  test    rcx, rcx
0x140008e97  jz      short loc_140008EA2
0x140008e99  mov     rax, [rcx+8]
0x140008e9d  test    rax, rax
0x140008ea0  jnz     short loc_140008EB8
0x140008ea2  mov     rcx, [rcx+10h]; Process
0x140008ea6  call    cs:__imp_PsGetProcessId
0x140008ead  nop     dword ptr [rax+rax+00h]
0x140008eb2  add     rsp, 28h
0x140008eb6  retn
0x140008eb8  mov     eax, [rax+18h]
0x140008ebb  jmp     short loc_140008EB2
```
