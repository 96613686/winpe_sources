# PrivateSetThreadPreferredUILanguages(ulong,ushort const *,ulong *)

- ea: `0x18002e0f0`
- end: `0x18002e131`
- name: `?PrivateSetThreadPreferredUILanguages@@YAHKPEBGPEAK@Z`
- size: `65`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002cc58`

## callees

- `0x18002e0f0`

## import_xrefs

- `ntdll!RtlSetThreadPreferredUILanguages` at `0x18002e0f6`
- `ntdll!RtlSetThreadPreferredUILanguages` at `0x18002e0f6`
- `ntdll!RtlNtStatusToDosError` at `0x18002e10f`
- `ntdll!RtlNtStatusToDosError` at `0x18002e10f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e11d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e11d`

## pseudocode

```c
__int64 __fastcall PrivateSetThreadPreferredUILanguages(__int64 a1, const unsigned __int16 *a2, unsigned int *a3)
{
  NTSTATUS v3; // eax
  DWORD v5; // eax

  v3 = RtlSetThreadPreferredUILanguages(0, a2, a3);
  if ( v3 >= 0 )
    return 1;
  v5 = RtlNtStatusToDosError(v3);
  SetLastError(v5);
  return 0;
}

```

## disassembly

```asm
0x18002e0f0  sub     rsp, 28h
0x18002e0f4  xor     ecx, ecx
0x18002e0f6  call    cs:__imp_RtlSetThreadPreferredUILanguages
0x18002e0fd  nop     dword ptr [rax+rax+00h]
0x18002e102  test    eax, eax
0x18002e104  js      short loc_18002E10D
0x18002e106  mov     eax, 1
0x18002e10b  jmp     short loc_18002E12B
0x18002e10d  mov     ecx, eax; Status
0x18002e10f  call    cs:__imp_RtlNtStatusToDosError
0x18002e116  nop     dword ptr [rax+rax+00h]
0x18002e11b  mov     ecx, eax; dwErrCode
0x18002e11d  call    cs:__imp_SetLastError
0x18002e124  nop     dword ptr [rax+rax+00h]
0x18002e129  xor     eax, eax
0x18002e12b  add     rsp, 28h
0x18002e12f  retn
```
