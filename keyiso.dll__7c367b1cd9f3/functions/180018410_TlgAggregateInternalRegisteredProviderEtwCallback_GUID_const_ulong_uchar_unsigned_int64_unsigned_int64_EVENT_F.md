# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180018410`
- end: `0x180018482`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180017f88`
- `0x180018310`
- `0x180018410`
- `0x180019010`

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
0x180018410  mov     [rsp+arg_0], rbx
0x180018415  push    rdi
0x180018416  sub     rsp, 40h
0x18001841a  mov     rbx, [rsp+48h+arg_30]
0x180018422  mov     r11b, r8b
0x180018425  mov     edi, edx
0x180018427  mov     rax, [rbx+138h]
0x18001842e  test    rax, rax
0x180018431  jz      short loc_18001845B
0x180018433  mov     r10, [rbx+140h]
0x18001843a  mov     r8, [rsp+48h+arg_20]
0x18001843f  mov     [rsp+48h+var_18], r10
0x180018444  mov     r10, [rsp+48h+arg_28]
0x180018449  mov     [rsp+48h+var_20], r10
0x18001844e  mov     [rsp+48h+var_28], r8
0x180018453  mov     r8b, r11b
0x180018456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001845b  cmp     edi, 1
0x18001845e  jnz     short loc_18001846A
0x180018460  mov     rcx, rbx
0x180018463  call    LookUpTableFlushComplete
0x180018468  jmp     short loc_180018477
0x18001846a  cmp     edi, 2
0x18001846d  jnz     short loc_180018477
0x18001846f  mov     rcx, rbx
0x180018472  call    LookUpTableFlushPartial
0x180018477  mov     rbx, [rsp+48h+arg_0]
0x18001847c  add     rsp, 40h
0x180018480  pop     rdi
0x180018481  retn
```
