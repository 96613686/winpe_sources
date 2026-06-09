# PrivateSetThreadPreferredUILanguages(ulong,ushort const *,ulong *)

- ea: `0x18002c0d0`
- end: `0x18002c0fe`
- name: `?PrivateSetThreadPreferredUILanguages@@YAHKPEBGPEAK@Z`
- size: `46`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002ad38`

## callees

- `0x18002c0d0`

## import_xrefs

- `ntdll!RtlSetThreadPreferredUILanguages` at `0x18002c0d6`
- `ntdll!RtlSetThreadPreferredUILanguages` at `0x18002c0d6`
- `ntdll!RtlNtStatusToDosError` at `0x18002c0e9`
- `ntdll!RtlNtStatusToDosError` at `0x18002c0e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c0f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c0f1`

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
0x18002c0d0  sub     rsp, 28h
0x18002c0d4  xor     ecx, ecx
0x18002c0d6  call    cs:__imp_RtlSetThreadPreferredUILanguages
0x18002c0dc  test    eax, eax
0x18002c0de  js      short loc_18002C0E7
0x18002c0e0  mov     eax, 1
0x18002c0e5  jmp     short loc_18002C0F9
0x18002c0e7  mov     ecx, eax; Status
0x18002c0e9  call    cs:__imp_RtlNtStatusToDosError
0x18002c0ef  mov     ecx, eax; dwErrCode
0x18002c0f1  call    cs:__imp_SetLastError
0x18002c0f7  xor     eax, eax
0x18002c0f9  add     rsp, 28h
0x18002c0fd  retn
```
