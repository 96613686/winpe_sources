# CConfigServiceProvider2Impl::Release(void)

- ea: `0x18000aa60`
- end: `0x18000aa90`
- name: `?Release@CConfigServiceProvider2Impl@@UEAAKXZ`
- size: `48`
- prototype: `unsigned int __fastcall(CConfigServiceProvider2Impl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800067e0`

## callees

- `0x18000aa60`
- `0x180038010`

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
0x18000aa60  push    rbx
0x18000aa62  sub     rsp, 20h
0x18000aa66  or      ebx, 0FFFFFFFFh
0x18000aa69  lock xadd [rcx+28h], ebx
0x18000aa6e  sub     ebx, 1
0x18000aa71  jnz     short loc_18000AA87
0x18000aa73  test    rcx, rcx
0x18000aa76  jz      short loc_18000AA87
0x18000aa78  mov     rdx, [rcx]
0x18000aa7b  mov     rax, [rdx+28h]
0x18000aa7f  lea     edx, [rbx+1]
0x18000aa82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa87  mov     eax, ebx
0x18000aa89  add     rsp, 20h
0x18000aa8d  pop     rbx
0x18000aa8e  retn
```
