# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18000f480`
- end: `0x18000f4f3`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `115`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000f480`
- `0x18000f4fc`
- `0x180030088`
- `0x180035010`

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
0x18000f480  mov     [rsp+arg_0], rbx
0x18000f485  push    rdi
0x18000f486  sub     rsp, 40h
0x18000f48a  mov     rbx, [rsp+48h+arg_30]
0x18000f492  mov     r11b, r8b
0x18000f495  mov     edi, edx
0x18000f497  mov     rax, [rbx+138h]
0x18000f49e  test    rax, rax
0x18000f4a1  jz      short loc_18000F4CB
0x18000f4a3  mov     r10, [rbx+140h]
0x18000f4aa  mov     r8, [rsp+48h+arg_20]
0x18000f4af  mov     [rsp+48h+var_18], r10
0x18000f4b4  mov     r10, [rsp+48h+arg_28]
0x18000f4b9  mov     [rsp+48h+var_20], r10
0x18000f4be  mov     [rsp+48h+var_28], r8
0x18000f4c3  mov     r8b, r11b
0x18000f4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4cb  cmp     edi, 1
0x18000f4ce  jnz     short loc_18000F4DA
0x18000f4d0  mov     rcx, rbx
0x18000f4d3  call    LookUpTableFlushComplete
0x18000f4d8  jmp     short loc_18000F4E7
0x18000f4da  cmp     edi, 2
0x18000f4dd  jnz     short loc_18000F4E7
0x18000f4df  mov     rcx, rbx
0x18000f4e2  call    LookUpTableFlushPartial
0x18000f4e7  mov     rbx, [rsp+48h+arg_0]
0x18000f4ec  add     rsp, 40h
0x18000f4f0  pop     rdi
0x18000f4f1  retn
```
