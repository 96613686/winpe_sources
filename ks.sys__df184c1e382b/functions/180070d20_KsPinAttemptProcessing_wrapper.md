# KsPinAttemptProcessing_wrapper

- ea: `0x180070d20`
- end: `0x180070d7b`
- name: `KsPinAttemptProcessing_wrapper`
- size: `91`
- prototype: `void __fastcall(PKSPIN Pin, BOOLEAN)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180005f40`
- `0x180019cb0`
- `0x180070d20`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180070d39`
- `ntoskrnl!KeGetCurrentIrql` at `0x180070d39`

## string_xrefs

- `0x180070d50`: `KsPinAttemptProcessing should only be called at IRQL <= DISPATCH_LEVEL.`

## pseudocode

```c
void __fastcall KsPinAttemptProcessing_wrapper(PKSPIN Pin, BOOLEAN a2)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() > 2u )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsPinAttemptProcessing should only be called at IRQL <= DISPATCH_LEVEL.",
      528393);
  KsPinAttemptProcessing(Pin, a2);
}

```

## disassembly

```asm
0x180070d20  mov     [rsp+arg_0], rbx
0x180070d25  push    rdi
0x180070d26  sub     rsp, 20h
0x180070d2a  mov     eax, cs:KsXdvExtLevel
0x180070d30  mov     bl, dl
0x180070d32  mov     rdi, rcx
0x180070d35  test    al, 8
0x180070d37  jz      short loc_180070D65
0x180070d39  call    cs:__imp_KeGetCurrentIrql
0x180070d40  nop     dword ptr [rax+rax+00h]
0x180070d45  cmp     al, 2
0x180070d47  jbe     short loc_180070D65
0x180070d49  mov     rax, cs:KsVerifierUtilTable
0x180070d50  lea     rcx, aKspinattemptpr; "KsPinAttemptProcessing should only be c"...
0x180070d57  mov     edx, 81009h
0x180070d5c  mov     rax, [rax+60h]
0x180070d60  call    _guard_dispatch_icall
0x180070d65  mov     dl, bl; Asynchronous
0x180070d67  mov     rcx, rdi; Pin
0x180070d6a  call    KsPinAttemptProcessing
0x180070d6f  mov     rbx, [rsp+28h+arg_0]
0x180070d74  add     rsp, 20h
0x180070d78  pop     rdi
0x180070d79  retn
```
