# KsPinRegisterIrpCompletionCallback_wrapper

- ea: `0x1800712b0`
- end: `0x18007130d`
- name: `KsPinRegisterIrpCompletionCallback_wrapper`
- size: `93`
- prototype: `__int64 __fastcall(PKSPIN Pin, PFNKSPINIRPCOMPLETION IrpCompletion)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180019c60`
- `0x1800424d0`
- `0x1800712b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800712ca`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800712ca`

## string_xrefs

- `0x1800712e1`: `KsPinRegisterIrpCompletionCallback should only be called at IRQL == PASSIVE_LEVEL.`

## pseudocode

```c
void __fastcall KsPinRegisterIrpCompletionCallback_wrapper(PKSPIN Pin, PFNKSPINIRPCOMPLETION IrpCompletion)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsPinRegisterIrpCompletionCallback should only be called at IRQL == PASSIVE_LEVEL.",
      528393);
  KsPinRegisterIrpCompletionCallback(Pin, IrpCompletion);
}

```

## disassembly

```asm
0x1800712b0  mov     [rsp+arg_0], rbx
0x1800712b5  push    rdi
0x1800712b6  sub     rsp, 20h
0x1800712ba  mov     eax, cs:KsXdvExtLevel
0x1800712c0  mov     rbx, rdx
0x1800712c3  mov     rdi, rcx
0x1800712c6  test    al, 8
0x1800712c8  jz      short loc_1800712F6
0x1800712ca  call    cs:__imp_KeGetCurrentIrql
0x1800712d1  nop     dword ptr [rax+rax+00h]
0x1800712d6  test    al, al
0x1800712d8  jz      short loc_1800712F6
0x1800712da  mov     rax, cs:KsVerifierUtilTable
0x1800712e1  lea     rcx, aKspinregisteri; "KsPinRegisterIrpCompletionCallback shou"...
0x1800712e8  mov     edx, 81009h
0x1800712ed  mov     rax, [rax+60h]
0x1800712f1  call    _guard_dispatch_icall
0x1800712f6  mov     rdx, rbx; IrpCompletion
0x1800712f9  mov     rcx, rdi; Pin
0x1800712fc  call    KsPinRegisterIrpCompletionCallback
0x180071301  mov     rbx, [rsp+28h+arg_0]
0x180071306  add     rsp, 20h
0x18007130a  pop     rdi
0x18007130b  retn
```
