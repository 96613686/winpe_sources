# CConfigServiceProvider2Impl::Release(void)

- ea: `0x180008690`
- end: `0x1800086c0`
- name: `?Release@CConfigServiceProvider2Impl@@UEAAKXZ`
- size: `48`
- prototype: `unsigned int __fastcall(CConfigServiceProvider2Impl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800065d0`

## callees

- `0x180008690`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::Release(CConfigServiceProvider2Impl *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 10);
  if ( !v1 && this )
    (*(void (__fastcall **)(CConfigServiceProvider2Impl *, __int64))(*(_QWORD *)this + 40LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180008690  push    rbx
0x180008692  sub     rsp, 20h
0x180008696  or      ebx, 0FFFFFFFFh
0x180008699  lock xadd [rcx+28h], ebx
0x18000869e  sub     ebx, 1
0x1800086a1  jnz     short loc_1800086B7
0x1800086a3  test    rcx, rcx
0x1800086a6  jz      short loc_1800086B7
0x1800086a8  mov     rdx, [rcx]
0x1800086ab  mov     rax, [rdx+28h]
0x1800086af  lea     edx, [rbx+1]
0x1800086b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086b7  mov     eax, ebx
0x1800086b9  add     rsp, 20h
0x1800086bd  pop     rbx
0x1800086be  retn
```
