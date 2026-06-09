# OLE32::F_CoCreateInstance

- ea: `0x140009040`
- end: `0x1400090a2`
- name: `OLE32::F_CoCreateInstance`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140008e98`
- `0x140009040`
- `0x14000a010`

## string_xrefs

- `0x140009059`: `CoCreateInstance`

## pseudocode

```c
__int64 __fastcall OLE32::F_CoCreateInstance(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  if ( Bind_OLE32("CoCreateInstance", &OLE32::CoCreateInstance) )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64, __int64))OLE32::CoCreateInstance)(
             a1,
             a2,
             a3,
             a4,
             a5);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x140009040  push    rbx
0x140009042  push    rbp
0x140009043  push    rsi
0x140009044  push    rdi
0x140009045  sub     rsp, 38h
0x140009049  mov     rsi, rdx
0x14000904c  mov     rbp, rcx
0x14000904f  lea     rdx, ?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; __int64 (**)(void)
0x140009056  mov     rbx, r9
0x140009059  lea     rcx, aCocreateinstan; "CoCreateInstance"
0x140009060  mov     edi, r8d
0x140009063  call    ?Bind_OLE32@@YAP6A_JXZPEBDPEAP6A_JXZ@Z; Bind_OLE32(char const *,__int64 (**)(void))
0x140009068  test    rax, rax
0x14000906b  jz      short loc_140009094
0x14000906d  mov     r9, [rsp+58h+arg_20]
0x140009075  mov     r8d, edi
0x140009078  mov     rax, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x14000907f  mov     rdx, rsi
0x140009082  mov     [rsp+58h+var_38], r9
0x140009087  mov     rcx, rbp
0x14000908a  mov     r9, rbx
0x14000908d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009092  jmp     short loc_140009099
0x140009094  mov     eax, 80004005h
0x140009099  add     rsp, 38h
0x14000909d  pop     rdi
0x14000909e  pop     rsi
0x14000909f  pop     rbp
0x1400090a0  pop     rbx
0x1400090a1  retn
```
