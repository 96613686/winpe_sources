# CWinTaskClassFactoryT<CReAgentTaskHandler,1>::Release(void)

- ea: `0x180001c30`
- end: `0x180001c60`
- name: `?Release@?$CWinTaskClassFactoryT@VCReAgentTaskHandler@@$00@@UEAAKXZ`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001c30`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CReAgentTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x180001c30  push    rbx
0x180001c32  sub     rsp, 20h
0x180001c36  or      ebx, 0FFFFFFFFh
0x180001c39  lock xadd [rcx+8], ebx
0x180001c3e  sub     ebx, 1
0x180001c41  jnz     short loc_180001C57
0x180001c43  test    rcx, rcx
0x180001c46  jz      short loc_180001C57
0x180001c48  mov     rdx, [rcx]
0x180001c4b  mov     rax, [rdx+28h]
0x180001c4f  lea     edx, [rbx+1]
0x180001c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c57  mov     eax, ebx
0x180001c59  add     rsp, 20h
0x180001c5d  pop     rbx
0x180001c5e  retn
```
