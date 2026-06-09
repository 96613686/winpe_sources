# CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::Release(void)

- ea: `0x180002a70`
- end: `0x180002a9f`
- name: `?Release@?$CWinTaskClassFactoryT@VCEdpNotificationTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002a70`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CEdpNotificationTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x180002a70  push    rbx
0x180002a72  sub     rsp, 20h
0x180002a76  or      ebx, 0FFFFFFFFh
0x180002a79  lock xadd [rcx+8], ebx
0x180002a7e  sub     ebx, 1
0x180002a81  jnz     short loc_180002A97
0x180002a83  test    rcx, rcx
0x180002a86  jz      short loc_180002A97
0x180002a88  mov     rdx, [rcx]
0x180002a8b  mov     rax, [rdx+28h]
0x180002a8f  lea     edx, [rbx+1]
0x180002a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a97  mov     eax, ebx
0x180002a99  add     rsp, 20h
0x180002a9d  pop     rbx
0x180002a9e  retn
```
