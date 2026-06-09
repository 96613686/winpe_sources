# CWinTaskClassFactoryT<CmCleanupWim,1>::Release(void)

- ea: `0x1800055a0`
- end: `0x1800055cf`
- name: `?Release@?$CWinTaskClassFactoryT@VCmCleanupWim@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800055a0`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CmCleanupWim,1>::Release(volatile signed __int32 *a1)
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
0x1800055a0  push    rbx
0x1800055a2  sub     rsp, 20h
0x1800055a6  or      ebx, 0FFFFFFFFh
0x1800055a9  lock xadd [rcx+8], ebx
0x1800055ae  sub     ebx, 1
0x1800055b1  jnz     short loc_1800055C7
0x1800055b3  test    rcx, rcx
0x1800055b6  jz      short loc_1800055C7
0x1800055b8  mov     rdx, [rcx]
0x1800055bb  mov     rax, [rdx+28h]
0x1800055bf  lea     edx, [rbx+1]
0x1800055c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055c7  mov     eax, ebx
0x1800055c9  add     rsp, 20h
0x1800055cd  pop     rbx
0x1800055ce  retn
```
