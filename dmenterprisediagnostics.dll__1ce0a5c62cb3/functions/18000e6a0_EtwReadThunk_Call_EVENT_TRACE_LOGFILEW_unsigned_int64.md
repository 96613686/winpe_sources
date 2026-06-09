# EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)

- ea: `0x18000e6a0`
- end: `0x18000e6b9`
- name: `?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z`
- size: `25`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *, unsigned __int64)`
- caller_count: `256`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d6a0`
- `0x18000d6b0`
- `0x18000d6c0`
- `0x18000d6d0`
- `0x18000d6e0`
- `0x18000d6f0`
- `0x18000d700`
- `0x18000d710`
- `0x18000d720`
- `0x18000d730`
- `0x18000d740`
- `0x18000d750`
- `0x18000d760`
- `0x18000d770`
- `0x18000d780`
- `0x18000d790`
- `0x18000d7a0`
- `0x18000d7b0`
- `0x18000d7c0`
- `0x18000d7d0`
- `0x18000d7e0`
- `0x18000d7f0`
- `0x18000d800`
- `0x18000d810`
- `0x18000d820`
- `0x18000d830`
- `0x18000d840`
- `0x18000d850`
- `0x18000d860`
- `0x18000d870`
- `0x18000d880`
- `0x18000d890`
- `0x18000d8a0`
- `0x18000d8b0`
- `0x18000d8c0`
- `0x18000d8d0`
- `0x18000d8e0`
- `0x18000d8f0`
- `0x18000d900`
- `0x18000d910`
- `0x18000d920`
- `0x18000d930`
- `0x18000d940`
- `0x18000d950`
- `0x18000d960`
- `0x18000d970`
- `0x18000d980`
- `0x18000d990`
- `0x18000d9a0`
- `0x18000d9b0`

## callees

- `0x180026010`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_Call(struct _EVENT_TRACE_LOGFILEW *a1, __int64 a2)
{
  return ((__int64 (__fastcall *)(struct _EVENT_TRACE_LOGFILEW *, _UNKNOWN *****************))(&off_180032008)[3 * a2 + 1])(
           a1,
           (&off_180032008)[3 * a2]);
}

```

## disassembly

```asm
0x18000e6a0  lea     rax, [rdx+rdx*2]
0x18000e6a4  lea     r8, off_180032008
0x18000e6ab  mov     rdx, [r8+rax*8]
0x18000e6af  mov     rax, [r8+rax*8+8]
0x18000e6b4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
