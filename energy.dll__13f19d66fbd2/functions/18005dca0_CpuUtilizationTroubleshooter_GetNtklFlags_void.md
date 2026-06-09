# CpuUtilizationTroubleshooter::GetNtklFlags(void)

- ea: `0x18005dca0`
- end: `0x18005dccf`
- name: `?GetNtklFlags@CpuUtilizationTroubleshooter@@UEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CpuUtilizationTroubleshooter *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18005dcb7`
- `ntdll!RtlAdjustPrivilege` at `0x18005dcb7`

## pseudocode

```c
__int64 __fastcall CpuUtilizationTroubleshooter::GetNtklFlags(CpuUtilizationTroubleshooter *this)
{
  unsigned __int8 OldValue; // [rsp+38h] [rbp+10h] BYREF

  OldValue = 0;
  return ((RtlAdjustPrivilege(0xBu, 1u, 0, &OldValue) >> 31) & 0xFEFFFFF9) + 16777223;
}

```

## disassembly

```asm
0x18005dca0  sub     rsp, 28h
0x18005dca4  xor     r8d, r8d; ForThread
0x18005dca7  mov     [rsp+28h+OldValue], 0
0x18005dcac  lea     r9, [rsp+28h+OldValue]; OldValue
0x18005dcb1  mov     dl, 1; NewValue
0x18005dcb3  lea     ecx, [r8+0Bh]; Privilege
0x18005dcb7  call    cs:__imp_RtlAdjustPrivilege
0x18005dcbd  sar     eax, 1Fh
0x18005dcc0  and     eax, 0FEFFFFF9h
0x18005dcc5  add     eax, 1000007h
0x18005dcca  add     rsp, 28h
0x18005dcce  retn
```
