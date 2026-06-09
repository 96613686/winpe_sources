# SecNetIpTableAvlCleanup

- ea: `0x140009c14`
- end: `0x140009c58`
- name: `SecNetIpTableAvlCleanup`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140009f20`
- `0x1400400a0`

## callees

- `0x140009c14`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140009c26`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140009c26`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140009c41`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140009c41`

## pseudocode

```c
PVOID SecNetIpTableAvlCleanup()
{
  BOOLEAN i; // dl
  PVOID result; // rax

  for ( i = 1; ; i = 0 )
  {
    result = RtlEnumerateGenericTableAvl(&SecNetIpAddressTable, i);
    if ( !result )
      break;
    RtlDeleteElementGenericTableAvl(&SecNetIpAddressTable, result);
    --SecNetIpAddressTableElements;
  }
  return result;
}

```

## disassembly

```asm
0x140009c14  sub     rsp, 28h
0x140009c18  mov     dl, 1
0x140009c1a  jmp     short loc_140009C3A
0x140009c1c  mov     rdx, rax; Buffer
0x140009c1f  lea     rcx, SecNetIpAddressTable; Table
0x140009c26  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140009c2d  nop     dword ptr [rax+rax+00h]
0x140009c32  dec     cs:SecNetIpAddressTableElements
0x140009c38  xor     edx, edx; Restart
0x140009c3a  lea     rcx, SecNetIpAddressTable; Table
0x140009c41  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140009c48  nop     dword ptr [rax+rax+00h]
0x140009c4d  test    rax, rax
0x140009c50  jnz     short loc_140009C1C
0x140009c52  add     rsp, 28h
0x140009c56  retn
```
