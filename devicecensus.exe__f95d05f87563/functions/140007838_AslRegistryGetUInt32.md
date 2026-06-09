# AslRegistryGetUInt32

- ea: `0x140007838`
- end: `0x1400078b4`
- name: `AslRegistryGetUInt32`
- size: `124`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140005918`

## callees

- `0x140007074`
- `0x140007838`
- `0x1400078bc`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140007860`
- `ntdll!RtlInitUnicodeStringEx` at `0x140007860`

## string_xrefs

- `0x14000787d`: `AslRegistryGetUInt32`

## pseudocode

```c
__int64 __fastcall AslRegistryGetUInt32(__int64 a1, __int64 a2)
{
  NTSTATUS inited; // eax
  unsigned int v5; // ebx
  struct _UNICODE_STRING v7; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  inited = RtlInitUnicodeStringEx(&v7, L"LogFlags");
  v5 = inited;
  if ( inited >= 0 )
    return (unsigned int)AslRegistryGetUInt32_UStr(a1, a2, &v7);
  else
    AslLogCallPrintf(1, "AslRegistryGetUInt32", 1148, "RtlInitUnicodeStringEx failed [%x]", inited);
  return v5;
}

```

## disassembly

```asm
0x140007838  mov     rax, rsp
0x14000783b  mov     [rax+8], rbx
0x14000783f  mov     [rax+10h], rsi
0x140007843  push    rdi
0x140007844  sub     rsp, 40h
0x140007848  mov     rdi, rdx
0x14000784b  mov     rsi, rcx
0x14000784e  xorps   xmm0, xmm0
0x140007851  lea     rdx, aLogflags; "LogFlags"
0x140007858  lea     rcx, [rax-18h]; DestinationString
0x14000785c  movups  xmmword ptr [rax-18h], xmm0
0x140007860  call    cs:__imp_RtlInitUnicodeStringEx
0x140007866  mov     ebx, eax
0x140007868  test    eax, eax
0x14000786a  jns     short loc_140007890
0x14000786c  lea     r9, aRtlinitunicode; "RtlInitUnicodeStringEx failed [%x]"
0x140007873  mov     [rsp+48h+var_28], eax
0x140007877  mov     r8d, 47Ch
0x14000787d  lea     rdx, aAslregistryget_2; "AslRegistryGetUInt32"
0x140007884  mov     ecx, 1
0x140007889  call    AslLogCallPrintf
0x14000788e  jmp     short loc_1400078A2
0x140007890  lea     r8, [rsp+48h+var_18]
0x140007895  mov     rdx, rdi
0x140007898  mov     rcx, rsi
0x14000789b  call    AslRegistryGetUInt32_UStr
0x1400078a0  mov     ebx, eax
0x1400078a2  mov     rsi, [rsp+48h+arg_8]
0x1400078a7  mov     eax, ebx
0x1400078a9  mov     rbx, [rsp+48h+arg_0]
0x1400078ae  add     rsp, 40h
0x1400078b2  pop     rdi
0x1400078b3  retn
```
