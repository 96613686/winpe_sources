# DllMain$catch$3

- ea: `0x18002046e`
- end: `0x1800204ad`
- name: `DllMain$catch$3`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000dd0c`
- `0x18001019c`
- `0x18002046e`

## pseudocode

```c
__int64 __fastcall DllMain_catch_3(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edx

  WppCleanupUm(a1, a2, a3);
  if ( g_pMSMQErrorLoggingTrace )
  {
    CMSMQTrace::`scalar deleting destructor'(g_pMSMQErrorLoggingTrace, v3);
    g_pMSMQErrorLoggingTrace = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002046e  mov     [rsp+arg_8], rdx
0x180020473  push    rbp
0x180020474  sub     rsp, 20h
0x180020478  mov     rbp, rdx
0x18002047b  call    WppCleanupUm
0x180020480  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; this
0x180020487  test    rcx, rcx
0x18002048a  jz      short loc_18002049C
0x18002048c  call    ??_GCMSMQTrace@@QEAAPEAXI@Z; CMSMQTrace::`scalar deleting destructor'(uint)
0x180020491  mov     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002049c  mov     rax, 0
0x1800204a6  add     rsp, 20h
0x1800204aa  pop     rbp
0x1800204ab  retn
```
