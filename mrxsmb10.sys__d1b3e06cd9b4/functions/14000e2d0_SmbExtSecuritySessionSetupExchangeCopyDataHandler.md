# SmbExtSecuritySessionSetupExchangeCopyDataHandler

- ea: `0x14000e2d0`
- end: `0x14000e312`
- name: `SmbExtSecuritySessionSetupExchangeCopyDataHandler`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000e0d8`
- `0x14000e2d0`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14000e2f6`
- `ntoskrnl!DbgPrint` at `0x14000e2f6`

## string_xrefs

- `0x14000e2ef`: `Mapping Incomplete Server Response to Invalid Response\n`

## pseudocode

```c
__int64 __fastcall SmbExtSecuritySessionSetupExchangeCopyDataHandler(__int64 a1, __int64 a2, unsigned int a3)
{
  if ( (unsigned int)ParseExtSecuritySessionSetupResponse(a1, a3, a3, *(_QWORD *)(a1 + 376)) == -1073741802 )
  {
    DbgPrint("Mapping Incomplete Server Response to Invalid Response\n");
    *(_DWORD *)(a1 + 48) = -1073741629;
  }
  return 0;
}

```

## disassembly

```asm
0x14000e2d0  push    rbx
0x14000e2d2  sub     rsp, 20h
0x14000e2d6  mov     r9, [rcx+178h]
0x14000e2dd  mov     edx, r8d
0x14000e2e0  mov     rbx, rcx
0x14000e2e3  call    ParseExtSecuritySessionSetupResponse
0x14000e2e8  cmp     eax, 0C0000016h
0x14000e2ed  jnz     short loc_14000E309
0x14000e2ef  lea     rcx, aMappingIncompl; "Mapping Incomplete Server Response to I"...
0x14000e2f6  call    cs:__imp_DbgPrint
0x14000e2fd  nop     dword ptr [rax+rax+00h]
0x14000e302  mov     dword ptr [rbx+30h], 0C00000C3h
0x14000e309  xor     eax, eax
0x14000e30b  add     rsp, 20h
0x14000e30f  pop     rbx
0x14000e310  retn
```
