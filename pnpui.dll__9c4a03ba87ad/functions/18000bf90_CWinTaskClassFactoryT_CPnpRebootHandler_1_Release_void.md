# CWinTaskClassFactoryT<CPnpRebootHandler,1>::Release(void)

- ea: `0x18000bf90`
- end: `0x18000bfbf`
- name: `?Release@?$CWinTaskClassFactoryT@VCPnpRebootHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000bf90`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CPnpRebootHandler,1>::Release(volatile signed __int32 *a1)
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
0x18000bf90  push    rbx
0x18000bf92  sub     rsp, 20h
0x18000bf96  or      ebx, 0FFFFFFFFh
0x18000bf99  lock xadd [rcx+8], ebx
0x18000bf9e  sub     ebx, 1
0x18000bfa1  jnz     short loc_18000BFB7
0x18000bfa3  test    rcx, rcx
0x18000bfa6  jz      short loc_18000BFB7
0x18000bfa8  mov     rdx, [rcx]
0x18000bfab  mov     rax, [rdx+28h]
0x18000bfaf  lea     edx, [rbx+1]
0x18000bfb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb7  mov     eax, ebx
0x18000bfb9  add     rsp, 20h
0x18000bfbd  pop     rbx
0x18000bfbe  retn
```
