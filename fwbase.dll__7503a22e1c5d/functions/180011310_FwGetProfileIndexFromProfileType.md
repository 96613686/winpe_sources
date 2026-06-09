# FwGetProfileIndexFromProfileType

- ea: `0x180011310`
- end: `0x180011370`
- name: `FwGetProfileIndexFromProfileType`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011310`
- `0x18002f38c`

## string_xrefs

- `0x180011360`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwGetProfileIndexFromProfileType(int a1)
{
  switch ( a1 )
  {
    case 1:
      return 0;
    case 0x7FFFFFFF:
      return (unsigned int)(a1 == 0x7FFFFFFF) + 2;
    case 2:
      return 1;
  }
  if ( a1 != 4 )
  {
    MicrosoftTelemetryAssertTriggeredArgs((__int64)"mpssvc.dll", a1, 0);
    return (unsigned int)(a1 == 0x7FFFFFFF) + 2;
  }
  return 2;
}

```

## disassembly

```asm
0x180011310  push    rbx
0x180011312  sub     rsp, 20h
0x180011316  mov     ebx, ecx
0x180011318  cmp     ecx, 1
0x18001131b  jz      short loc_180011349
0x18001131d  cmp     ecx, 7FFFFFFFh
0x180011323  jnz     short loc_180011339
0x180011325  xor     eax, eax
0x180011327  cmp     ebx, 7FFFFFFFh
0x18001132d  setz    al
0x180011330  add     eax, 2
0x180011333  add     rsp, 20h
0x180011337  pop     rbx
0x180011338  retn
0x180011339  cmp     ebx, 2
0x18001133c  jnz     short loc_18001134D
0x18001133e  mov     eax, 1
0x180011343  add     rsp, 20h
0x180011347  pop     rbx
0x180011348  retn
0x180011349  xor     eax, eax
0x18001134b  jmp     short loc_180011333
0x18001134d  cmp     ebx, 4
0x180011350  jnz     short loc_18001135D
0x180011352  mov     eax, 2
0x180011357  add     rsp, 20h
0x18001135b  pop     rbx
0x18001135c  retn
0x18001135d  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "(Profile == FW_PROFILE_TYPE_DOMAIN) || (Profile == FW_PROFILE_TYPE_PRIVATE) || (Profile == FW_PROFILE_TYPE_PUBLIC || Profile == FW_PROFILE_TYPE_ALL)", "Invalid profile type")
0x180011360  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x180011367  mov     edx, ebx
0x180011369  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001136e  jmp     short loc_180011325
```
