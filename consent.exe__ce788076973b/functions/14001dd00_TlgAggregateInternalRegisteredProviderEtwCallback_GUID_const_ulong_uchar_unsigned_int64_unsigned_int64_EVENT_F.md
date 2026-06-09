# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x14001dd00`
- end: `0x14001dd72`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14001d8c0`
- `0x14001dc38`
- `0x14001dd00`
- `0x14001f010`

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
0x14001dd00  mov     [rsp+arg_0], rbx
0x14001dd05  push    rdi
0x14001dd06  sub     rsp, 40h
0x14001dd0a  mov     rbx, [rsp+48h+arg_30]
0x14001dd12  mov     r11b, r8b
0x14001dd15  mov     edi, edx
0x14001dd17  mov     rax, [rbx+138h]
0x14001dd1e  test    rax, rax
0x14001dd21  jz      short loc_14001DD4B
0x14001dd23  mov     r10, [rbx+140h]
0x14001dd2a  mov     r8, [rsp+48h+arg_20]
0x14001dd2f  mov     [rsp+48h+var_18], r10
0x14001dd34  mov     r10, [rsp+48h+arg_28]
0x14001dd39  mov     [rsp+48h+var_20], r10
0x14001dd3e  mov     [rsp+48h+var_28], r8
0x14001dd43  mov     r8b, r11b
0x14001dd46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dd4b  cmp     edi, 1
0x14001dd4e  jnz     short loc_14001DD5A
0x14001dd50  mov     rcx, rbx
0x14001dd53  call    LookUpTableFlushComplete
0x14001dd58  jmp     short loc_14001DD67
0x14001dd5a  cmp     edi, 2
0x14001dd5d  jnz     short loc_14001DD67
0x14001dd5f  mov     rcx, rbx
0x14001dd62  call    LookUpTableFlushPartial
0x14001dd67  mov     rbx, [rsp+48h+arg_0]
0x14001dd6c  add     rsp, 40h
0x14001dd70  pop     rdi
0x14001dd71  retn
```
