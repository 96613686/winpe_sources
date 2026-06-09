# DfsAdjustPrivilege

- ea: `0x14005a934`
- end: `0x14005a976`
- name: `DfsAdjustPrivilege`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140018e88`

## callees

- `0x14005a934`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x14005a94d`
- `ntdll!RtlAdjustPrivilege` at `0x14005a94d`
- `ntdll!RtlNtStatusToDosError` at `0x14005a95f`
- `ntdll!RtlNtStatusToDosError` at `0x14005a95f`

## pseudocode

```c
__int64 __fastcall DfsAdjustPrivilege(ULONG a1)
{
  unsigned int v1; // ebx
  int v2; // eax
  unsigned __int8 OldValue; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  OldValue = 0;
  v2 = RtlAdjustPrivilege(a1, 1u, 0, &OldValue);
  if ( v2 < 0 )
    return RtlNtStatusToDosError(v2);
  return v1;
}

```

## disassembly

```asm
0x14005a934  mov     [rsp+OldValue], dl
0x14005a938  push    rbx
0x14005a939  sub     rsp, 20h
0x14005a93d  xor     ebx, ebx
0x14005a93f  lea     r9, [rsp+28h+OldValue]; OldValue
0x14005a944  xor     r8d, r8d; ForThread
0x14005a947  mov     [rsp+28h+OldValue], bl
0x14005a94b  mov     dl, 1; NewValue
0x14005a94d  call    cs:__imp_RtlAdjustPrivilege
0x14005a954  nop     dword ptr [rax+rax+00h]
0x14005a959  test    eax, eax
0x14005a95b  jns     short loc_14005A96D
0x14005a95d  mov     ecx, eax; Status
0x14005a95f  call    cs:__imp_RtlNtStatusToDosError
0x14005a966  nop     dword ptr [rax+rax+00h]
0x14005a96b  mov     ebx, eax
0x14005a96d  mov     eax, ebx
0x14005a96f  add     rsp, 20h
0x14005a973  pop     rbx
0x14005a974  retn
```
