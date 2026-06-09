# DhcpAlloc

- ea: `0x180001f90`
- end: `0x180001fcc`
- name: `DhcpAlloc`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001490`
- `0x180001bd0`
- `0x1800042d4`
- `0x180005a20`
- `0x180006300`
- `0x180007200`
- `0x1800075d0`
- `0x180008700`
- `0x180009060`
- `0x180009584`
- `0x18000a950`
- `0x18000dd30`
- `0x18000df6c`
- `0x18000e1e0`
- `0x18000e784`
- `0x18000e8b0`
- `0x18000f528`
- `0x18000f7d4`
- `0x18000faac`

## callees

- `0x180001f90`
- `0x18001088c`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!HeapAlloc` at `0x180001fb7`

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
0x180001f90  sub     rsp, 28h
0x180001f94  mov     eax, 0FFFFFFFFh
0x180001f99  cmp     rcx, rax
0x180001f9c  jnb     short loc_180001FC3
0x180001f9e  mov     rax, gs:60h
0x180001fa7  mov     r8, rcx
0x180001faa  mov     edx, 8
0x180001faf  mov     rcx, [rax+30h]
0x180001fb3  add     rsp, 28h
0x180001fb7  jmp     cs:__imp_HeapAlloc
0x180001fbe  add     rsp, 28h
0x180001fc2  retn
0x180001fc3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180001fc8  xor     eax, eax
0x180001fca  jmp     short loc_180001FBE
```
