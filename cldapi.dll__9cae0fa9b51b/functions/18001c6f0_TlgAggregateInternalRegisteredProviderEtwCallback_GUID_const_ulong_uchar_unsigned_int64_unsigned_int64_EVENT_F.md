# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18001c6f0`
- end: `0x18001c763`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `115`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18001c1fc`
- `0x18001c5e0`
- `0x18001c6f0`
- `0x18001e010`

## pseudocode

```c
void __fastcall TlgAggregateInternalRegisteredProviderEtwCallback(
        const struct _GUID *a1,
        __int64 a2,
        char a3,
        int a4,
        unsigned __int64 a5,
        struct _EVENT_FILTER_DESCRIPTOR *a6,
        const __m128i *a7)
{
  int v8; // edi
  void (__fastcall *v9)(const struct _GUID *, __int64, unsigned __int64); // rax

  v8 = a2;
  v9 = (void (__fastcall *)(const struct _GUID *, __int64, unsigned __int64))a7[19].m128i_i64[1];
  if ( v9 )
  {
    LOBYTE(a5) = a3;
    v9(a1, a2, a5);
  }
  if ( v8 == 1 )
  {
    LookUpTableFlushComplete(a7, a2, a3, a4);
  }
  else if ( v8 == 2 )
  {
    LookUpTableFlushPartial(a7);
  }
}

```

## disassembly

```asm
0x18001c6f0  mov     [rsp+arg_0], rbx
0x18001c6f5  push    rdi
0x18001c6f6  sub     rsp, 40h
0x18001c6fa  mov     rbx, [rsp+48h+arg_30]
0x18001c702  mov     r11b, r8b
0x18001c705  mov     edi, edx
0x18001c707  mov     rax, [rbx+138h]
0x18001c70e  test    rax, rax
0x18001c711  jz      short loc_18001C73B
0x18001c713  mov     r10, [rbx+140h]
0x18001c71a  mov     r8, [rsp+48h+arg_20]
0x18001c71f  mov     [rsp+48h+var_18], r10
0x18001c724  mov     r10, [rsp+48h+arg_28]
0x18001c729  mov     [rsp+48h+var_20], r10
0x18001c72e  mov     [rsp+48h+var_28], r8
0x18001c733  mov     r8b, r11b
0x18001c736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c73b  cmp     edi, 1
0x18001c73e  jnz     short loc_18001C74A
0x18001c740  mov     rcx, rbx
0x18001c743  call    LookUpTableFlushComplete
0x18001c748  jmp     short loc_18001C757
0x18001c74a  cmp     edi, 2
0x18001c74d  jnz     short loc_18001C757
0x18001c74f  mov     rcx, rbx
0x18001c752  call    LookUpTableFlushPartial
0x18001c757  mov     rbx, [rsp+48h+arg_0]
0x18001c75c  add     rsp, 40h
0x18001c760  pop     rdi
0x18001c761  retn
```
