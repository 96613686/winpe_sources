# CWinTaskClassFactoryT<CpnppolicyHandler,1>::Release(void)

- ea: `0x180003030`
- end: `0x18000305f`
- name: `?Release@?$CWinTaskClassFactoryT@VCpnppolicyHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180003030`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CpnppolicyHandler,1>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
  return v1;
}

```

## disassembly

```asm
0x180003030  push    rbx
0x180003032  sub     rsp, 20h
0x180003036  or      ebx, 0FFFFFFFFh
0x180003039  lock xadd [rcx+8], ebx
0x18000303e  sub     ebx, 1
0x180003041  jnz     short loc_180003057
0x180003043  test    rcx, rcx
0x180003046  jz      short loc_180003057
0x180003048  mov     rdx, [rcx]
0x18000304b  mov     rax, [rdx+28h]
0x18000304f  lea     edx, [rbx+1]
0x180003052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003057  mov     eax, ebx
0x180003059  add     rsp, 20h
0x18000305d  pop     rbx
0x18000305e  retn
```
