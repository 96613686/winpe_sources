# FwReportErrorAsNtStatus

- ea: `0x180017c20`
- end: `0x180017c92`
- name: `FwReportErrorAsNtStatus`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004100`
- `0x1800205fc`

## callees

- `0x180006f50`
- `0x180017c20`
- `0x18002158c`
- `0x18002f38c`

## string_xrefs

- `0x180017c40`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwReportErrorAsNtStatus(int a1, __int64 a2, int a3)
{
  if ( a3 >= 0 )
    MicrosoftTelemetryAssertTriggeredArgs((__int64)"mpssvc.dll", a3, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_ssD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, a3);
  return FwNtStatusToHResult(a3);
}

```

## disassembly

```asm
0x180017c20  mov     [rsp+arg_0], rbx
0x180017c25  mov     [rsp+arg_8], rsi
0x180017c2a  push    rdi
0x180017c2b  sub     rsp, 30h
0x180017c2f  mov     ebx, r8d
0x180017c32  mov     rdi, rdx
0x180017c35  mov     rsi, rcx
0x180017c38  test    r8d, r8d
0x180017c3b  js      short loc_180017C4E
0x180017c3d  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "!NT_SUCCESS(ntStatus)", "Function failure")
0x180017c40  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x180017c47  mov     edx, ebx
0x180017c49  call    MicrosoftTelemetryAssertTriggeredArgs
0x180017c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c55  lea     rax, WPP_GLOBAL_Control
0x180017c5c  cmp     rcx, rax
0x180017c5f  jz      short loc_180017C7C
0x180017c61  test    byte ptr [rcx+1Ch], 1
0x180017c65  jz      short loc_180017C7C
0x180017c67  mov     rcx, [rcx+10h]
0x180017c6b  mov     r9, rsi
0x180017c6e  mov     [rsp+38h+var_10], ebx
0x180017c72  mov     [rsp+38h+var_18], rdi
0x180017c77  call    WPP_SF_ssD
0x180017c7c  mov     ecx, ebx
0x180017c7e  mov     rbx, [rsp+38h+arg_0]
0x180017c83  mov     rsi, [rsp+38h+arg_8]
0x180017c88  add     rsp, 30h
0x180017c8c  pop     rdi
0x180017c8d  jmp     FwNtStatusToHResult
```
