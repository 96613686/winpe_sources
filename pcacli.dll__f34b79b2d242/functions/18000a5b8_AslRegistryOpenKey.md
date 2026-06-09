# AslRegistryOpenKey

- ea: `0x18000a5b8`
- end: `0x18000a62d`
- name: `AslRegistryOpenKey`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005620`
- `0x18000adf8`

## callees

- `0x180007738`
- `0x18000a5b8`
- `0x18000a634`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18000a5d9`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000a5d9`

## string_xrefs

- `0x18000a5e5`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x18000a5f6`: `AslRegistryOpenKey`

## pseudocode

```c
__int64 __fastcall AslRegistryOpenKey(void **a1, const WCHAR *a2, ACCESS_MASK a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = 0;
  inited = RtlInitUnicodeStringEx(&v8, a2);
  v6 = inited;
  if ( inited >= 0 )
    return (unsigned int)AslRegistryOpenKey_UStr(a1, &v8, a3);
  else
    AslLogCallPrintf(1, "AslRegistryOpenKey", 904, "AslRegistryOpenKey passed bad Path [%x]", inited);
  return v6;
}

```

## disassembly

```asm
0x18000a5b8  mov     rax, rsp
0x18000a5bb  mov     [rax+8], rbx
0x18000a5bf  mov     [rax+10h], rsi
0x18000a5c3  push    rdi
0x18000a5c4  sub     rsp, 40h
0x18000a5c8  mov     rsi, rcx
0x18000a5cb  xorps   xmm0, xmm0
0x18000a5ce  lea     rcx, [rax-18h]; DestinationString
0x18000a5d2  mov     edi, r8d
0x18000a5d5  movups  xmmword ptr [rax-18h], xmm0
0x18000a5d9  call    cs:__imp_RtlInitUnicodeStringEx
0x18000a5df  mov     ebx, eax
0x18000a5e1  test    eax, eax
0x18000a5e3  jns     short loc_18000A609
0x18000a5e5  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x18000a5ec  mov     [rsp+48h+var_28], eax
0x18000a5f0  mov     r8d, 388h
0x18000a5f6  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x18000a5fd  mov     ecx, 1
0x18000a602  call    AslLogCallPrintf
0x18000a607  jmp     short loc_18000A61B
0x18000a609  mov     r8d, edi
0x18000a60c  lea     rdx, [rsp+48h+var_18]
0x18000a611  mov     rcx, rsi
0x18000a614  call    AslRegistryOpenKey_UStr
0x18000a619  mov     ebx, eax
0x18000a61b  mov     rsi, [rsp+48h+arg_8]
0x18000a620  mov     eax, ebx
0x18000a622  mov     rbx, [rsp+48h+arg_0]
0x18000a627  add     rsp, 40h
0x18000a62b  pop     rdi
0x18000a62c  retn
```
