# CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::Release(void)

- ea: `0x18001dfe0`
- end: `0x18001e010`
- name: `?Release@?$CWinTaskClassFactoryT@VCMemoryDiagnosticHandler@@$00@@UEAAKXZ`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18001dfe0`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMemoryDiagnosticHandler,1>::Release(volatile signed __int32 *a1)
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
0x18001dfe0  push    rbx
0x18001dfe2  sub     rsp, 20h
0x18001dfe6  or      ebx, 0FFFFFFFFh
0x18001dfe9  lock xadd [rcx+8], ebx
0x18001dfee  sub     ebx, 1
0x18001dff1  jnz     short loc_18001E007
0x18001dff3  test    rcx, rcx
0x18001dff6  jz      short loc_18001E007
0x18001dff8  mov     rdx, [rcx]
0x18001dffb  mov     rax, [rdx+28h]
0x18001dfff  lea     edx, [rbx+1]
0x18001e002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e007  mov     eax, ebx
0x18001e009  add     rsp, 20h
0x18001e00d  pop     rbx
0x18001e00e  retn
```
