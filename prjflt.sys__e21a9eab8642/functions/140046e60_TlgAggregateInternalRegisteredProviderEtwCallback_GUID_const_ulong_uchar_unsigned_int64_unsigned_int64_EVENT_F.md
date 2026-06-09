# TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x140046e60`
- end: `0x140046ed3`
- name: `?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `115`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000bb00`
- `0x1400468e0`
- `0x140046cc4`
- `0x140046e60`

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
  v9 = (void (__fastcall *)(const struct _GUID *, __int64, unsigned __int64))a7[20].m128i_i64[1];
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
0x140046e60  mov     [rsp+arg_0], rbx
0x140046e65  push    rdi
0x140046e66  sub     rsp, 40h
0x140046e6a  mov     rbx, [rsp+48h+arg_30]
0x140046e72  mov     r11b, r8b
0x140046e75  mov     edi, edx
0x140046e77  mov     rax, [rbx+148h]
0x140046e7e  test    rax, rax
0x140046e81  jz      short loc_140046EAB
0x140046e83  mov     r10, [rbx+150h]
0x140046e8a  mov     r8, [rsp+48h+arg_20]
0x140046e8f  mov     [rsp+48h+var_18], r10
0x140046e94  mov     r10, [rsp+48h+arg_28]
0x140046e99  mov     [rsp+48h+var_20], r10
0x140046e9e  mov     [rsp+48h+var_28], r8
0x140046ea3  mov     r8b, r11b
0x140046ea6  call    _guard_dispatch_icall
0x140046eab  cmp     edi, 1
0x140046eae  jnz     short loc_140046EBA
0x140046eb0  mov     rcx, rbx
0x140046eb3  call    LookUpTableFlushComplete
0x140046eb8  jmp     short loc_140046EC7
0x140046eba  cmp     edi, 2
0x140046ebd  jnz     short loc_140046EC7
0x140046ebf  mov     rcx, rbx
0x140046ec2  call    LookUpTableFlushPartial
0x140046ec7  mov     rbx, [rsp+48h+arg_0]
0x140046ecc  add     rsp, 40h
0x140046ed0  pop     rdi
0x140046ed1  retn
```
