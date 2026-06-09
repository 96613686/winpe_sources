# KsFilterAttemptProcessing_wrapper

- ea: `0x18006fe10`
- end: `0x18006fe6b`
- name: `KsFilterAttemptProcessing_wrapper`
- size: `91`
- prototype: `__int64 __fastcall(PKSFILTER Filter)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800051b0`
- `0x180019c60`
- `0x18006fe10`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18006fe29`
- `ntoskrnl!KeGetCurrentIrql` at `0x18006fe29`

## string_xrefs

- `0x18006fe40`: `KsFilterAttemptProcessing should only be called at IRQL <= DISPATCH_LEVEL.`

## pseudocode

```c
void __fastcall KsFilterAttemptProcessing_wrapper(PKSFILTER Filter, BOOLEAN a2)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() > 2u )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsFilterAttemptProcessing should only be called at IRQL <= DISPATCH_LEVEL.",
      528393);
  KsFilterAttemptProcessing(Filter, a2);
}

```

## disassembly

```asm
0x18006fe10  mov     [rsp+arg_0], rbx
0x18006fe15  push    rdi
0x18006fe16  sub     rsp, 20h
0x18006fe1a  mov     eax, cs:KsXdvExtLevel
0x18006fe20  mov     bl, dl
0x18006fe22  mov     rdi, rcx
0x18006fe25  test    al, 8
0x18006fe27  jz      short loc_18006FE55
0x18006fe29  call    cs:__imp_KeGetCurrentIrql
0x18006fe30  nop     dword ptr [rax+rax+00h]
0x18006fe35  cmp     al, 2
0x18006fe37  jbe     short loc_18006FE55
0x18006fe39  mov     rax, cs:KsVerifierUtilTable
0x18006fe40  lea     rcx, aKsfilterattemp; "KsFilterAttemptProcessing should only b"...
0x18006fe47  mov     edx, 81009h
0x18006fe4c  mov     rax, [rax+60h]
0x18006fe50  call    _guard_dispatch_icall
0x18006fe55  mov     dl, bl; Asynchronous
0x18006fe57  mov     rcx, rdi; Filter
0x18006fe5a  call    KsFilterAttemptProcessing
0x18006fe5f  mov     rbx, [rsp+28h+arg_0]
0x18006fe64  add     rsp, 20h
0x18006fe68  pop     rdi
0x18006fe69  retn
```
