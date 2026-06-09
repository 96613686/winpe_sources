# KsFilterFactoryUpdateCacheData_wrapper

- ea: `0x180070050`
- end: `0x1800700ad`
- name: `KsFilterFactoryUpdateCacheData_wrapper`
- size: `93`
- prototype: `__int64 __fastcall(PKSFILTERFACTORY FilterFactory, KSFILTER_DESCRIPTOR *FilterDescriptor)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180019c60`
- `0x180057cf0`
- `0x180070050`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18007006a`
- `ntoskrnl!KeGetCurrentIrql` at `0x18007006a`

## string_xrefs

- `0x180070081`: `KsFilterFactoryUpdateCacheData should only be called at IRQL <= APC_LEVEL.`

## pseudocode

```c
NTSTATUS __fastcall KsFilterFactoryUpdateCacheData_wrapper(
        PKSFILTERFACTORY FilterFactory,
        KSFILTER_DESCRIPTOR *FilterDescriptor)
{
  if ( (KsXdvExtLevel & 8) != 0 && KeGetCurrentIrql() > 1u )
    (*(void (__fastcall **)(const char *, __int64))(KsVerifierUtilTable + 96))(
      "KsFilterFactoryUpdateCacheData should only be called at IRQL <= APC_LEVEL.",
      528393);
  return KsFilterFactoryUpdateCacheData(FilterFactory, FilterDescriptor);
}

```

## disassembly

```asm
0x180070050  mov     [rsp+arg_0], rbx
0x180070055  push    rdi
0x180070056  sub     rsp, 20h
0x18007005a  mov     eax, cs:KsXdvExtLevel
0x180070060  mov     rbx, rdx
0x180070063  mov     rdi, rcx
0x180070066  test    al, 8
0x180070068  jz      short loc_180070096
0x18007006a  call    cs:__imp_KeGetCurrentIrql
0x180070071  nop     dword ptr [rax+rax+00h]
0x180070076  cmp     al, 1
0x180070078  jbe     short loc_180070096
0x18007007a  mov     rax, cs:KsVerifierUtilTable
0x180070081  lea     rcx, aKsfilterfactor; "KsFilterFactoryUpdateCacheData should o"...
0x180070088  mov     edx, 81009h
0x18007008d  mov     rax, [rax+60h]
0x180070091  call    _guard_dispatch_icall
0x180070096  mov     rdx, rbx; FilterDescriptor
0x180070099  mov     rcx, rdi; FilterFactory
0x18007009c  call    KsFilterFactoryUpdateCacheData
0x1800700a1  mov     rbx, [rsp+28h+arg_0]
0x1800700a6  add     rsp, 20h
0x1800700aa  pop     rdi
0x1800700ab  retn
```
