# Performance::RtlCompression::CRtlCompressBuffer::operator()(ushort,void const *,ulong,void *,ulong,ulong,ulong *,void *)

- ea: `0x18001f9e8`
- end: `0x18001fa4c`
- name: `??RCRtlCompressBuffer@RtlCompression@Performance@@QEBAJGPEBXKPEAXKKPEAK1@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020508`
- `0x18002101c`

## callees

- `0x18001f9e8`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Performance::RtlCompression::CRtlCompressBuffer::operator()(
        __int64 (__fastcall **a1)(__int64, __int64, _QWORD, __int64, int, int, __int64, __int64),
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  if ( *a1 )
    return (*a1)(258, a3, a4, a5, a6, 4096, a8, a9);
  else
    return 3221225474LL;
}

```

## disassembly

```asm
0x18001f9e8  sub     rsp, 58h
0x18001f9ec  mov     rax, [rcx]
0x18001f9ef  mov     r10d, r9d
0x18001f9f2  mov     r11, r8
0x18001f9f5  test    rax, rax
0x18001f9f8  jz      short loc_18001FA41
0x18001f9fa  mov     rdx, [rsp+58h+arg_40]
0x18001fa02  mov     ecx, 102h
0x18001fa07  mov     r9, [rsp+58h+arg_20]
0x18001fa0f  mov     r8d, r10d
0x18001fa12  mov     [rsp+58h+var_20], rdx
0x18001fa17  mov     rdx, [rsp+58h+arg_38]
0x18001fa1f  mov     [rsp+58h+var_28], rdx
0x18001fa24  mov     edx, [rsp+58h+arg_28]
0x18001fa2b  mov     [rsp+58h+var_30], 1000h
0x18001fa33  mov     [rsp+58h+var_38], edx
0x18001fa37  mov     rdx, r11
0x18001fa3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa3f  jmp     short loc_18001FA46
0x18001fa41  mov     eax, 0C0000002h
0x18001fa46  add     rsp, 58h
0x18001fa4a  retn
```
