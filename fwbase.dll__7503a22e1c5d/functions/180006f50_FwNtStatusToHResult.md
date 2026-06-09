# FwNtStatusToHResult

- ea: `0x180006f50`
- end: `0x180006fc1`
- name: `FwNtStatusToHResult`
- size: `113`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800048c0`
- `0x1800050c0`
- `0x180006d60`
- `0x180007040`
- `0x180013140`
- `0x180017c20`

## callees

- `0x180006f50`
- `0x18002f38c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180006f6f`
- `ntdll!RtlNtStatusToDosError` at `0x180006f6f`

## string_xrefs

- `0x180006f98`: `mpssvc.dll`
- `0x180006fab`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwNtStatusToHResult(NTSTATUS a1)
{
  unsigned int v1; // ebx
  signed int v4; // eax

  v1 = 0;
  if ( a1 >= 0 )
    return v1;
  v4 = RtlNtStatusToDosError(a1);
  v1 = v4;
  if ( v4 )
  {
    if ( v4 != 317 )
    {
      if ( v4 > 0 )
        v1 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_7;
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", (unsigned int)a1, 0);
  }
  v1 = a1 | 0x10000000;
LABEL_7:
  if ( ((a1 ^ v1) & 0x80000000) != 0 )
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v1, (unsigned int)a1);
  return v1;
}

```

## disassembly

```asm
0x180006f50  mov     [rsp+arg_0], rbx
0x180006f55  push    rdi
0x180006f56  sub     rsp, 20h
0x180006f5a  xor     ebx, ebx
0x180006f5c  mov     edi, ecx
0x180006f5e  test    ecx, ecx
0x180006f60  js      short loc_180006F6F
0x180006f62  mov     eax, ebx
0x180006f64  mov     rbx, [rsp+28h+arg_0]
0x180006f69  add     rsp, 20h
0x180006f6d  pop     rdi
0x180006f6e  retn
0x180006f6f  call    cs:__imp_RtlNtStatusToDosError
0x180006f75  mov     ebx, eax
0x180006f77  test    eax, eax
0x180006f79  jz      short loc_180006FA8
0x180006f7b  cmp     eax, 13Dh
0x180006f80  jz      short loc_180006FB9
0x180006f82  test    eax, eax
0x180006f84  jle     short loc_180006F8F
0x180006f86  movzx   ebx, ax
0x180006f89  or      ebx, 80070000h
0x180006f8f  mov     edx, ebx
0x180006f91  xor     edx, edi
0x180006f93  jns     short loc_180006F62
0x180006f95  mov     r8d, edi; __annotation("Debug", "TelemetryAssert", "!!(SUCCEEDED(hr)) == !!(NT_SUCCESS(ntStatus))", "Sanity check failure")
0x180006f98  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x180006f9f  mov     edx, ebx
0x180006fa1  call    MicrosoftTelemetryAssertTriggeredArgs
0x180006fa6  jmp     short loc_180006F62
0x180006fa8  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "dwError != ERROR_SUCCESS", "Failure status")
0x180006fab  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x180006fb2  mov     edx, edi
0x180006fb4  call    MicrosoftTelemetryAssertTriggeredArgs
0x180006fb9  mov     ebx, edi
0x180006fbb  bts     ebx, 1Ch
0x180006fbf  jmp     short loc_180006F8F
```
