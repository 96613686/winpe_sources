# KsFilterFactoryGetSymbolicLink_wrapper

- ea: `0x18006ff80`
- end: `0x18006ffce`
- name: `KsFilterFactoryGetSymbolicLink_wrapper`
- size: `78`
- prototype: `__int64 __fastcall(PKSFILTERFACTORY FilterFactory)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x180019c60`
- `0x1800658e0`
- `0x18006ff80`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006ff93`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006ff93`

## string_xrefs

- `0x18006ffaa`: `KsFilterFactoryGetSymbolicLink should only be called at IRQL == PASSIVE_LEVEL.`

## pseudocode

```c
PUNICODE_STRING __fastcall KsFilterFactoryGetSymbolicLink_wrapper(PKSFILTERFACTORY FilterFactory)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsFilterFactoryGetSymbolicLink should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  return KsFilterFactoryGetSymbolicLink(FilterFactory);
}

```

## disassembly

```asm
0x18006ff80  push    rbx
0x18006ff82  sub     rsp, 20h
0x18006ff86  mov     eax, cs:KsXdvExtLevel
0x18006ff8c  mov     rbx, rcx
0x18006ff8f  test    al, 8
0x18006ff91  jz      short loc_18006FFBF
0x18006ff93  call    cs:__imp_KeGetCurrentIrql
0x18006ff9a  nop     dword ptr [rax+rax+00h]
0x18006ff9f  test    al, al
0x18006ffa1  jz      short loc_18006FFBF
0x18006ffa3  mov     rax, cs:KsVerifierUtilTable
0x18006ffaa  lea     rcx, aKsfilterfactor_1; "KsFilterFactoryGetSymbolicLink should o"...
0x18006ffb1  mov     edx, 81009h
0x18006ffb6  mov     rax, [rax+60h]
0x18006ffba  call    _guard_dispatch_icall
0x18006ffbf  mov     rcx, rbx; FilterFactory
0x18006ffc2  call    KsFilterFactoryGetSymbolicLink
0x18006ffc7  add     rsp, 20h
0x18006ffcb  pop     rbx
0x18006ffcc  retn
```
