# AmiUtilitySetPrivilege(ulong,uchar)

- ea: `0x140018c3c`
- end: `0x140018c92`
- name: `?AmiUtilitySetPrivilege@@YAKKE@Z`
- size: `86`
- prototype: `unsigned int __fastcall(unsigned int, unsigned __int8)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140010df0`
- `0x140019930`
- `0x140019fa0`

## callees

- `0x1400151b0`
- `0x140018c3c`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x140018c55`
- `ntdll!RtlAdjustPrivilege` at `0x140018c55`
- `ntdll!RtlNtStatusToDosError` at `0x140018c61`
- `ntdll!RtlNtStatusToDosError` at `0x140018c61`

## string_xrefs

- `0x140018c6d`: `Failed to give privilege [%d]`
- `0x140018c74`: `AmiUtilitySetPrivilege`

## pseudocode

```c
__int64 __fastcall AmiUtilitySetPrivilege(ULONG a1)
{
  ULONG v1; // ebx
  int v2; // eax
  unsigned __int8 OldValue; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  OldValue = 0;
  v2 = RtlAdjustPrivilege(a1, 1u, 0, &OldValue);
  if ( v2 < 0 )
  {
    v1 = RtlNtStatusToDosError(v2);
    AslLogCallPrintf(2, "AmiUtilitySetPrivilege", 61, "Failed to give privilege [%d]", v1);
  }
  return v1;
}

```

## disassembly

```asm
0x140018c3c  mov     [rsp+OldValue], dl
0x140018c40  push    rbx
0x140018c41  sub     rsp, 30h
0x140018c45  xor     ebx, ebx
0x140018c47  lea     r9, [rsp+38h+OldValue]; OldValue
0x140018c4c  xor     r8d, r8d; ForThread
0x140018c4f  mov     [rsp+38h+OldValue], bl
0x140018c53  mov     dl, 1; NewValue
0x140018c55  call    cs:__imp_RtlAdjustPrivilege
0x140018c5b  test    eax, eax
0x140018c5d  jns     short loc_140018C8A
0x140018c5f  mov     ecx, eax; Status
0x140018c61  call    cs:__imp_RtlNtStatusToDosError
0x140018c67  mov     r8d, 3Dh ; '='
0x140018c6d  lea     r9, aFailedToGivePr; "Failed to give privilege [%d]"
0x140018c74  lea     rdx, aAmiutilitysetp_1; "AmiUtilitySetPrivilege"
0x140018c7b  mov     [rsp+38h+var_18], eax
0x140018c7f  mov     ebx, eax
0x140018c81  lea     ecx, [r8-3Bh]
0x140018c85  call    AslLogCallPrintf
0x140018c8a  mov     eax, ebx
0x140018c8c  add     rsp, 30h
0x140018c90  pop     rbx
0x140018c91  retn
```
