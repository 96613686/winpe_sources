# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18002c548`
- end: `0x18002c586`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `62`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002c828`

## callees

- `0x18001da6c`
- `0x18002c548`
- `0x18003104a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c554`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c554`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(void *a1, __int64 a2, SIZE_T a3, void **a4)
{
  void *v5; // rax
  size_t v6; // rax

  v5 = CoTaskMemAlloc(a3);
  *a4 = v5;
  if ( !v5 )
    return 2147942414LL;
  v6 = CTCoAllocPolicy::_CoTaskMemSize(v5);
  memset_0(*a4, 0, v6);
  return 0;
}

```

## disassembly

```asm
0x18002c548  push    rbx
0x18002c54a  sub     rsp, 20h
0x18002c54e  mov     rcx, r8; cb
0x18002c551  mov     rbx, r9
0x18002c554  call    cs:__imp_CoTaskMemAlloc
0x18002c55a  mov     [rbx], rax
0x18002c55d  test    rax, rax
0x18002c560  jz      short loc_18002C57B
0x18002c562  mov     rcx, rax; void *
0x18002c565  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18002c56a  mov     rcx, [rbx]; void *
0x18002c56d  mov     r8, rax; Size
0x18002c570  xor     edx, edx; Val
0x18002c572  call    memset_0
0x18002c577  xor     eax, eax
0x18002c579  jmp     short loc_18002C580
0x18002c57b  mov     eax, 8007000Eh
0x18002c580  add     rsp, 20h
0x18002c584  pop     rbx
0x18002c585  retn
```
