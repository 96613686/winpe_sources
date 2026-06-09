# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18003d060`
- end: `0x18003d0d3`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `115`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180027c80`
- `0x18003cb80`
- `0x18003cef8`
- `0x18003d060`

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
  v9 = (void (__fastcall *)(const struct _GUID *, __int64, unsigned __int64))a7[41];
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
0x18003d060  mov     [rsp+arg_0], rbx
0x18003d065  push    rdi
0x18003d066  sub     rsp, 40h
0x18003d06a  mov     rbx, [rsp+48h+arg_30]
0x18003d072  mov     r11b, r8b
0x18003d075  mov     edi, edx
0x18003d077  mov     rax, [rbx+148h]
0x18003d07e  test    rax, rax
0x18003d081  jz      short loc_18003D0AB
0x18003d083  mov     r10, [rbx+150h]
0x18003d08a  mov     r8, [rsp+48h+arg_20]
0x18003d08f  mov     [rsp+48h+var_18], r10
0x18003d094  mov     r10, [rsp+48h+arg_28]
0x18003d099  mov     [rsp+48h+var_20], r10
0x18003d09e  mov     [rsp+48h+var_28], r8
0x18003d0a3  mov     r8b, r11b
0x18003d0a6  call    _guard_dispatch_icall
0x18003d0ab  cmp     edi, 1
0x18003d0ae  jnz     short loc_18003D0BA
0x18003d0b0  mov     rcx, rbx
0x18003d0b3  call    LookUpTableFlushComplete
0x18003d0b8  jmp     short loc_18003D0C7
0x18003d0ba  cmp     edi, 2
0x18003d0bd  jnz     short loc_18003D0C7
0x18003d0bf  mov     rcx, rbx
0x18003d0c2  call    LookUpTableFlushPartial
0x18003d0c7  mov     rbx, [rsp+48h+arg_0]
0x18003d0cc  add     rsp, 40h
0x18003d0d0  pop     rdi
0x18003d0d1  retn
```
