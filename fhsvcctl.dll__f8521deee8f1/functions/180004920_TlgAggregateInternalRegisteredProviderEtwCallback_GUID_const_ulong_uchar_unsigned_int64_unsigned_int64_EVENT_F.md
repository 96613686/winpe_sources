# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180004920`
- end: `0x180004992`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000444c`
- `0x180004830`
- `0x180004920`
- `0x180006010`

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
    LookUpTableFlushComplete(a7);
  }
  else if ( v8 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x180004920  mov     [rsp+arg_0], rbx
0x180004925  push    rdi
0x180004926  sub     rsp, 40h
0x18000492a  mov     rbx, [rsp+48h+arg_30]
0x180004932  mov     r11b, r8b
0x180004935  mov     edi, edx
0x180004937  mov     rax, [rbx+138h]
0x18000493e  test    rax, rax
0x180004941  jz      short loc_18000496B
0x180004943  mov     r10, [rbx+140h]
0x18000494a  mov     r8, [rsp+48h+arg_20]
0x18000494f  mov     [rsp+48h+var_18], r10
0x180004954  mov     r10, [rsp+48h+arg_28]
0x180004959  mov     [rsp+48h+var_20], r10
0x18000495e  mov     [rsp+48h+var_28], r8
0x180004963  mov     r8b, r11b
0x180004966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000496b  cmp     edi, 1
0x18000496e  jnz     short loc_18000497A
0x180004970  mov     rcx, rbx
0x180004973  call    LookUpTableFlushComplete
0x180004978  jmp     short loc_180004987
0x18000497a  cmp     edi, 2
0x18000497d  jnz     short loc_180004987
0x18000497f  mov     rcx, rbx
0x180004982  call    LookUpTableFlushPartial
0x180004987  mov     rbx, [rsp+48h+arg_0]
0x18000498c  add     rsp, 40h
0x180004990  pop     rdi
0x180004991  retn
```
