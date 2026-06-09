# Dfdll::CBuffer<uint>::InternalCopyFrom(void const *,uint,uint)

- ea: `0x180003150`
- end: `0x180003166`
- name: `?InternalCopyFrom@?$CBuffer@I@Dfdll@@MEAAJPEBXII@Z`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CBuffer<unsigned int>::InternalCopyFrom(__int64 a1)
{
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 104LL))(a1);
}

```

## disassembly

```asm
0x180003150  sub     rsp, 38h
0x180003154  mov     rax, [rcx]
0x180003157  mov     rax, [rax+68h]
0x18000315b  call    cs:__guard_dispatch_icall_fptr
0x180003161  add     rsp, 38h
0x180003165  retn
```
