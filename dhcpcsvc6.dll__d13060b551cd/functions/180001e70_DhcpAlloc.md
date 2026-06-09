# DhcpAlloc

- ea: `0x180001e70`
- end: `0x180001eaa`
- name: `DhcpAlloc`
- size: `58`
- prototype: `LPVOID __fastcall(SIZE_T)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800016f0`
- `0x180004e10`
- `0x180005270`
- `0x180005640`
- `0x180005b30`
- `0x180005ec0`
- `0x1800062f0`

## callees

- `0x180001e70`
- `0x1800035a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001e97`

## pseudocode

```c
LPVOID __fastcall DhcpAlloc(SIZE_T a1)
{
  if ( a1 < 0xFFFFFFFF )
    return HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, a1);
  MicrosoftTelemetryAssertTriggeredNoArgs();
  return 0;
}

```

## disassembly

```asm
0x180001e70  sub     rsp, 28h
0x180001e74  mov     eax, 0FFFFFFFFh
0x180001e79  cmp     rcx, rax
0x180001e7c  jnb     short loc_180001E9E
0x180001e7e  mov     rax, gs:60h
0x180001e87  mov     r8, rcx
0x180001e8a  mov     edx, 8
0x180001e8f  mov     rcx, [rax+30h]
0x180001e93  add     rsp, 28h
0x180001e97  jmp     cs:__imp_HeapAlloc
0x180001e9e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001ea3  xor     eax, eax
0x180001ea5  add     rsp, 28h
0x180001ea9  retn
```
