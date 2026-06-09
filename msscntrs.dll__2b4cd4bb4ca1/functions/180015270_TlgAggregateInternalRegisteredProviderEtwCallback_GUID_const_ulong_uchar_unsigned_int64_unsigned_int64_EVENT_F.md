# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180015270`
- end: `0x1800152e2`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180014d9c`
- `0x180015180`
- `0x180015270`
- `0x180018010`

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
0x180015270  mov     [rsp+arg_0], rbx
0x180015275  push    rdi
0x180015276  sub     rsp, 40h
0x18001527a  mov     rbx, [rsp+48h+arg_30]
0x180015282  mov     r11b, r8b
0x180015285  mov     edi, edx
0x180015287  mov     rax, [rbx+138h]
0x18001528e  test    rax, rax
0x180015291  jz      short loc_1800152BB
0x180015293  mov     r10, [rbx+140h]
0x18001529a  mov     r8, [rsp+48h+arg_20]
0x18001529f  mov     [rsp+48h+var_18], r10
0x1800152a4  mov     r10, [rsp+48h+arg_28]
0x1800152a9  mov     [rsp+48h+var_20], r10
0x1800152ae  mov     [rsp+48h+var_28], r8
0x1800152b3  mov     r8b, r11b
0x1800152b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152bb  cmp     edi, 1
0x1800152be  jnz     short loc_1800152CA
0x1800152c0  mov     rcx, rbx
0x1800152c3  call    LookUpTableFlushComplete
0x1800152c8  jmp     short loc_1800152D7
0x1800152ca  cmp     edi, 2
0x1800152cd  jnz     short loc_1800152D7
0x1800152cf  mov     rcx, rbx
0x1800152d2  call    LookUpTableFlushPartial
0x1800152d7  mov     rbx, [rsp+48h+arg_0]
0x1800152dc  add     rsp, 40h
0x1800152e0  pop     rdi
0x1800152e1  retn
```
