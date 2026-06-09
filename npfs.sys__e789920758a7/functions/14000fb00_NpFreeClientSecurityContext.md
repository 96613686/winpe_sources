# NpFreeClientSecurityContext

- ea: `0x14000fb00`
- end: `0x14000fb39`
- name: `NpFreeClientSecurityContext`
- size: `57`
- prototype: `void __fastcall(char *P)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001520`
- `0x14000deb8`
- `0x14000e980`
- `0x14000efb0`
- `0x1400100bc`
- `0x14001070c`
- `0x140013e30`

## callees

- `0x14000fb00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fb2b`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000fb1a`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000fb1a`

## pseudocode

```c
void __fastcall NpFreeClientSecurityContext(char *P)
{
  if ( (unsigned __int64)(P - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    SeDeleteClientSecurity(P);
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14000fb00  push    rbx
0x14000fb02  sub     rsp, 20h
0x14000fb06  lea     rax, [rcx-1]
0x14000fb0a  mov     rbx, rcx
0x14000fb0d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000fb11  jbe     short loc_14000FB1A
0x14000fb13  add     rsp, 20h
0x14000fb17  pop     rbx
0x14000fb18  retn
0x14000fb1a  call    cs:__imp_SeDeleteClientSecurity
0x14000fb21  nop     dword ptr [rax+rax+00h]
0x14000fb26  xor     edx, edx; Tag
0x14000fb28  mov     rcx, rbx; P
0x14000fb2b  call    cs:__imp_ExFreePoolWithTag
0x14000fb32  nop     dword ptr [rax+rax+00h]
0x14000fb37  jmp     short loc_14000FB13
```
