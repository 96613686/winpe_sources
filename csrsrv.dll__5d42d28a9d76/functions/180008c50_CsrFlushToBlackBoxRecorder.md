# CsrFlushToBlackBoxRecorder

- ea: `0x180008c50`
- end: `0x180008c9d`
- name: `CsrFlushToBlackBoxRecorder`
- size: `77`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001540`
- `0x180008f00`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x180008c8b`
- `ntdll!NtPowerInformation` at `0x180008c8b`

## pseudocode

```c
NTSTATUS CsrFlushToBlackBoxRecorder()
{
  _QWORD v1[5]; // [rsp+30h] [rbp-28h] BYREF

  v1[3] = 22;
  v1[2] = 0;
  v1[0] = CsrpBlackboxBuffer;
  v1[1] = 3272;
  return NtPowerInformation(TraceApplicationPowerMessage|0x40, v1, 0x20u, 0, 0);
}

```

## disassembly

```asm
0x180008c50  mov     r11, rsp
0x180008c53  sub     rsp, 58h
0x180008c57  xor     ecx, ecx
0x180008c59  mov     qword ptr [r11-10h], 16h
0x180008c61  xor     r9d, r9d; OutputBuffer
0x180008c64  mov     [r11-18h], rcx
0x180008c68  lea     rax, CsrpBlackboxBuffer
0x180008c6f  mov     [rsp+58h+OutputBufferLength], ecx; OutputBufferLength
0x180008c73  lea     rdx, [r11-28h]; InputBuffer
0x180008c77  mov     [r11-28h], rax
0x180008c7b  lea     r8d, [rcx+20h]; InputBufferLength
0x180008c7f  mov     qword ptr [r11-20h], 0CC8h
0x180008c87  lea     ecx, [r9+5Eh]; InformationLevel
0x180008c8b  call    cs:__imp_NtPowerInformation
0x180008c92  nop     dword ptr [rax+rax+00h]
0x180008c97  add     rsp, 58h
0x180008c9b  retn
```
