# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x1800019a0`
- end: `0x180001a16`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `118`
- prototype: `void __fastcall(const struct _GUID *, __int64, unsigned __int8, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800019a0`
- `0x180001a20`
- `0x18000af64`
- `0x18000c010`

## pseudocode

```c
void __fastcall TlgAggregateInternalRegisteredProviderEtwCallback(
        const struct _GUID *a1,
        __int64 a2,
        unsigned __int8 a3,
        __int64 a4,
        unsigned __int64 a5,
        struct _EVENT_FILTER_DESCRIPTOR *a6,
        _QWORD *a7)
{
  int v7; // edi
  void (__fastcall *v8)(const struct _GUID *, __int64, _QWORD); // rax

  v7 = a2;
  v8 = (void (__fastcall *)(const struct _GUID *, __int64, _QWORD))a7[39];
  if ( v8 )
    v8(a1, a2, a3);
  if ( v7 == 1 )
  {
    LookUpTableFlushComplete(a7);
  }
  else if ( v7 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x1800019a0  mov     [rsp+arg_0], rbx
0x1800019a5  push    rdi
0x1800019a6  sub     rsp, 40h
0x1800019aa  mov     rbx, [rsp+48h+arg_30]
0x1800019b2  movzx   r11d, r8b
0x1800019b6  mov     edi, edx
0x1800019b8  mov     rax, [rbx+138h]
0x1800019bf  test    rax, rax
0x1800019c2  jnz     short loc_1800019DC
0x1800019c4  cmp     edi, 1
0x1800019c7  jnz     short loc_180001A07
0x1800019c9  mov     rcx, rbx
0x1800019cc  call    LookUpTableFlushComplete
0x1800019d1  mov     rbx, [rsp+48h+arg_0]
0x1800019d6  add     rsp, 40h
0x1800019da  pop     rdi
0x1800019db  retn
0x1800019dc  mov     r10, [rbx+140h]
0x1800019e3  mov     r8, [rsp+48h+arg_20]
0x1800019e8  mov     [rsp+48h+var_18], r10
0x1800019ed  mov     r10, [rsp+48h+arg_28]
0x1800019f2  mov     [rsp+48h+var_20], r10
0x1800019f7  mov     [rsp+48h+var_28], r8
0x1800019fc  movzx   r8d, r11b
0x180001a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a05  jmp     short loc_1800019C4
0x180001a07  cmp     edi, 2
0x180001a0a  jnz     short loc_1800019D1
0x180001a0c  mov     rcx, rbx
0x180001a0f  call    LookUpTableFlushPartial
0x180001a14  jmp     short loc_1800019D1
```
