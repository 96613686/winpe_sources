# Performance::RtlCompression::CRtlCompressBuffer::operator()(ushort,void const *,ulong,void *,ulong,ulong,ulong *,void *)

- ea: `0x18001ee04`
- end: `0x18001ee67`
- name: `??RCRtlCompressBuffer@RtlCompression@Performance@@QEBAJGPEBXKPEAXKKPEAK1@Z`
- size: `99`
- prototype: `__int64 __fastcall(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, int, int, __int64, __int64), __int64, __int64, unsigned int, __int64, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f888`
- `0x18002032c`

## callees

- `0x18001ee04`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall Performance::RtlCompression::CRtlCompressBuffer::operator()(
        __int64 (__fastcall **a1)(__int64, __int64, _QWORD, __int64, int, int, __int64, __int64),
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7,
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
0x18001ee04  sub     rsp, 58h
0x18001ee08  mov     rax, [rcx]
0x18001ee0b  mov     r10d, r9d
0x18001ee0e  mov     r11, r8
0x18001ee11  test    rax, rax
0x18001ee14  jz      short loc_18001EE5D
0x18001ee16  mov     rdx, [rsp+58h+arg_40]
0x18001ee1e  mov     ecx, 102h
0x18001ee23  mov     r9, [rsp+58h+arg_20]
0x18001ee2b  mov     r8d, r10d
0x18001ee2e  mov     [rsp+58h+var_20], rdx
0x18001ee33  mov     rdx, [rsp+58h+arg_38]
0x18001ee3b  mov     [rsp+58h+var_28], rdx
0x18001ee40  mov     edx, [rsp+58h+arg_28]
0x18001ee47  mov     [rsp+58h+var_30], 1000h
0x18001ee4f  mov     [rsp+58h+var_38], edx
0x18001ee53  mov     rdx, r11
0x18001ee56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee5b  jmp     short loc_18001EE62
0x18001ee5d  mov     eax, 0C0000002h
0x18001ee62  add     rsp, 58h
0x18001ee66  retn
```
