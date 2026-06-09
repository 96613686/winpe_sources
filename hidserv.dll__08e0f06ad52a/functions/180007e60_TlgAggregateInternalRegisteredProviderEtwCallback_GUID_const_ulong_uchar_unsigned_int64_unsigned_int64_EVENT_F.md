# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x180007e60`
- end: `0x180007ed2`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `114`
- prototype: `void __fastcall(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007988`
- `0x180007d6c`
- `0x180007e60`
- `0x180009010`

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
0x180007e60  mov     [rsp+arg_0], rbx
0x180007e65  push    rdi
0x180007e66  sub     rsp, 40h
0x180007e6a  mov     rbx, [rsp+48h+arg_30]
0x180007e72  mov     r11b, r8b
0x180007e75  mov     edi, edx
0x180007e77  mov     rax, [rbx+138h]
0x180007e7e  test    rax, rax
0x180007e81  jz      short loc_180007EAB
0x180007e83  mov     r10, [rbx+140h]
0x180007e8a  mov     r8, [rsp+48h+arg_20]
0x180007e8f  mov     [rsp+48h+var_18], r10
0x180007e94  mov     r10, [rsp+48h+arg_28]
0x180007e99  mov     [rsp+48h+var_20], r10
0x180007e9e  mov     [rsp+48h+var_28], r8
0x180007ea3  mov     r8b, r11b
0x180007ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eab  cmp     edi, 1
0x180007eae  jnz     short loc_180007EBA
0x180007eb0  mov     rcx, rbx
0x180007eb3  call    LookUpTableFlushComplete
0x180007eb8  jmp     short loc_180007EC7
0x180007eba  cmp     edi, 2
0x180007ebd  jnz     short loc_180007EC7
0x180007ebf  mov     rcx, rbx
0x180007ec2  call    LookUpTableFlushPartial
0x180007ec7  mov     rbx, [rsp+48h+arg_0]
0x180007ecc  add     rsp, 40h
0x180007ed0  pop     rdi
0x180007ed1  retn
```
