# AslRegistryGetUInt32

- ea: `0x18000eb0c`
- end: `0x18000eb88`
- name: `AslRegistryGetUInt32`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800170fc`

## callees

- `0x18000e240`
- `0x18000eb0c`
- `0x18000eb90`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18000eb34`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000eb34`

## string_xrefs

- `0x18000eb51`: `AslRegistryGetUInt32`

## pseudocode

```c
__int64 __fastcall AslRegistryGetUInt32(_DWORD *a1, void *a2)
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
0x18000eb0c  mov     rax, rsp
0x18000eb0f  mov     [rax+8], rbx
0x18000eb13  mov     [rax+10h], rsi
0x18000eb17  push    rdi
0x18000eb18  sub     rsp, 40h
0x18000eb1c  mov     rdi, rdx
0x18000eb1f  mov     rsi, rcx
0x18000eb22  xorps   xmm0, xmm0
0x18000eb25  lea     rdx, aLogflags; "LogFlags"
0x18000eb2c  lea     rcx, [rax-18h]; DestinationString
0x18000eb30  movups  xmmword ptr [rax-18h], xmm0
0x18000eb34  call    cs:__imp_RtlInitUnicodeStringEx
0x18000eb3a  mov     ebx, eax
0x18000eb3c  test    eax, eax
0x18000eb3e  jns     short loc_18000EB64
0x18000eb40  lea     r9, aRtlinitunicode; "RtlInitUnicodeStringEx failed [%x]"
0x18000eb47  mov     [rsp+48h+var_28], eax
0x18000eb4b  mov     r8d, 47Ch
0x18000eb51  lea     rdx, aAslregistryget_2; "AslRegistryGetUInt32"
0x18000eb58  mov     ecx, 1
0x18000eb5d  call    AslLogCallPrintf
0x18000eb62  jmp     short loc_18000EB76
0x18000eb64  lea     r8, [rsp+48h+var_18]
0x18000eb69  mov     rdx, rdi
0x18000eb6c  mov     rcx, rsi
0x18000eb6f  call    AslRegistryGetUInt32_UStr
0x18000eb74  mov     ebx, eax
0x18000eb76  mov     rsi, [rsp+48h+arg_8]
0x18000eb7b  mov     eax, ebx
0x18000eb7d  mov     rbx, [rsp+48h+arg_0]
0x18000eb82  add     rsp, 40h
0x18000eb86  pop     rdi
0x18000eb87  retn
```
