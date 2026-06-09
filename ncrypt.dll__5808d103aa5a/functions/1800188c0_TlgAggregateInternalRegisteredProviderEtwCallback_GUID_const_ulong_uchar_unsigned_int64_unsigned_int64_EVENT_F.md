# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x1800188c0`
- end: `0x180018932`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800188c0`
- `0x180018a08`
- `0x180018db4`
- `0x180020010`

## pseudocode

```c
void __fastcall TlgAggregateInternalRegisteredProviderEtwCallback(
        const struct _GUID *a1,
        __int64 a2,
        char a3,
        __int64 a4,
        unsigned __int64 a5,
        struct _EVENT_FILTER_DESCRIPTOR *a6,
        _QWORD *a7)
{
  int v8; // edi
  void (__fastcall *v9)(const struct _GUID *, __int64, unsigned __int64); // rax

  v8 = a2;
  v9 = (void (__fastcall *)(const struct _GUID *, __int64, unsigned __int64))a7[39];
  if ( v9 )
  {
    LOBYTE(a5) = a3;
    v9(a1, a2, a5);
  }
  if ( v8 == 1 )
  {
    LookUpTableFlushComplete((__int64)a7);
  }
  else if ( v8 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x1800188c0  mov     [rsp+arg_0], rbx
0x1800188c5  push    rdi
0x1800188c6  sub     rsp, 40h
0x1800188ca  mov     rbx, [rsp+48h+arg_30]
0x1800188d2  mov     r11b, r8b
0x1800188d5  mov     edi, edx
0x1800188d7  mov     rax, [rbx+138h]
0x1800188de  test    rax, rax
0x1800188e1  jz      short loc_18001890B
0x1800188e3  mov     r10, [rbx+140h]
0x1800188ea  mov     r8, [rsp+48h+arg_20]
0x1800188ef  mov     [rsp+48h+var_18], r10
0x1800188f4  mov     r10, [rsp+48h+arg_28]
0x1800188f9  mov     [rsp+48h+var_20], r10
0x1800188fe  mov     [rsp+48h+var_28], r8
0x180018903  mov     r8b, r11b
0x180018906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001890b  cmp     edi, 1
0x18001890e  jnz     short loc_18001891A
0x180018910  mov     rcx, rbx
0x180018913  call    LookUpTableFlushComplete
0x180018918  jmp     short loc_180018927
0x18001891a  cmp     edi, 2
0x18001891d  jnz     short loc_180018927
0x18001891f  mov     rcx, rbx
0x180018922  call    LookUpTableFlushPartial
0x180018927  mov     rbx, [rsp+48h+arg_0]
0x18001892c  add     rsp, 40h
0x180018930  pop     rdi
0x180018931  retn
```
