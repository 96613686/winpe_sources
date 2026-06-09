# FatCheckSystemSecurityAccess

- ea: `0x140026864`
- end: `0x1400268b9`
- name: `FatCheckSystemSecurityAccess`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400268c0`
- `0x14002adec`
- `0x14002b790`

## callees

- `0x140026864`

## import_xrefs

- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14002688f`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x14002688f`

## pseudocode

```c
__int64 __fastcall FatCheckSystemSecurityAccess(__int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 184LL) + 8LL) + 8LL);
  if ( (*(_DWORD *)(v1 + 16) & 0x1000000) != 0 )
  {
    if ( !SeSinglePrivilegeCheck(FatSecurityPrivilege, 1) )
      return 3221225506LL;
    *(_DWORD *)(v1 + 16) &= ~0x1000000u;
    *(_DWORD *)(v1 + 20) |= 0x1000000u;
  }
  return 0;
}

```

## disassembly

```asm
0x140026864  push    rbx
0x140026866  sub     rsp, 20h
0x14002686a  mov     rax, [rcx+28h]
0x14002686e  mov     rcx, [rax+0B8h]
0x140026875  mov     rax, [rcx+8]
0x140026879  mov     rbx, [rax+8]
0x14002687d  test    dword ptr [rbx+10h], 1000000h
0x140026884  jz      short loc_1400268B0
0x140026886  mov     rcx, qword ptr cs:FatSecurityPrivilege.LowPart; PrivilegeValue
0x14002688d  mov     dl, 1; PreviousMode
0x14002688f  call    cs:__imp_SeSinglePrivilegeCheck
0x140026896  nop     dword ptr [rax+rax+00h]
0x14002689b  test    al, al
0x14002689d  jnz     short loc_1400268A6
0x14002689f  mov     eax, 0C0000022h
0x1400268a4  jmp     short loc_1400268B2
0x1400268a6  btr     dword ptr [rbx+10h], 18h
0x1400268ab  bts     dword ptr [rbx+14h], 18h
0x1400268b0  xor     eax, eax
0x1400268b2  add     rsp, 20h
0x1400268b6  pop     rbx
0x1400268b7  retn
```
