# DsRolepEnablePrivilege

- ea: `0x18000ace0`
- end: `0x18000ad25`
- name: `DsRolepEnablePrivilege`
- size: `69`
- prototype: `__int64 __fastcall(ULONG Privilege)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000b1c8`

## callees

- `0x18000ace0`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18000acfb`
- `ntdll!RtlAdjustPrivilege` at `0x18000ad14`
- `ntdll!RtlAdjustPrivilege` at `0x18000acfb`
- `ntdll!RtlAdjustPrivilege` at `0x18000ad14`

## pseudocode

```c
NTSTATUS __fastcall DsRolepEnablePrivilege(ULONG Privilege, BOOLEAN a2)
{
  NTSTATUS result; // eax
  unsigned __int8 OldValue; // [rsp+40h] [rbp+18h] BYREF

  OldValue = 0;
  result = RtlAdjustPrivilege(Privilege, a2, 1u, &OldValue);
  if ( result == -1073741700 )
    return RtlAdjustPrivilege(Privilege, a2, 0, &OldValue);
  return result;
}

```

## disassembly

```asm
0x18000ace0  mov     [rsp+arg_0], rbx
0x18000ace5  push    rdi
0x18000ace6  sub     rsp, 20h
0x18000acea  lea     r9, [rsp+28h+OldValue]; OldValue
0x18000acef  mov     [rsp+28h+OldValue], 0
0x18000acf4  mov     r8b, 1; ForThread
0x18000acf7  mov     ebx, edx
0x18000acf9  mov     edi, ecx
0x18000acfb  call    cs:__imp_RtlAdjustPrivilege
0x18000ad01  cmp     eax, 0C000007Ch
0x18000ad06  jnz     short loc_18000AD1A
0x18000ad08  lea     r9, [rsp+28h+OldValue]; OldValue
0x18000ad0d  xor     r8d, r8d; ForThread
0x18000ad10  mov     dl, bl; NewValue
0x18000ad12  mov     ecx, edi; Privilege
0x18000ad14  call    cs:__imp_RtlAdjustPrivilege
0x18000ad1a  mov     rbx, [rsp+28h+arg_0]
0x18000ad1f  add     rsp, 20h
0x18000ad23  pop     rdi
0x18000ad24  retn
```
