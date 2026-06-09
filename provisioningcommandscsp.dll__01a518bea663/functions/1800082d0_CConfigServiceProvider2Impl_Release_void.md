# CConfigServiceProvider2Impl::Release(void)

- ea: `0x1800082d0`
- end: `0x1800082ff`
- name: `?Release@CConfigServiceProvider2Impl@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800062d0`

## callees

- `0x1800082d0`
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
0x1800082d0  push    rbx
0x1800082d2  sub     rsp, 20h
0x1800082d6  or      ebx, 0FFFFFFFFh
0x1800082d9  lock xadd [rcx+28h], ebx
0x1800082de  sub     ebx, 1
0x1800082e1  jnz     short loc_1800082F7
0x1800082e3  test    rcx, rcx
0x1800082e6  jz      short loc_1800082F7
0x1800082e8  mov     rdx, [rcx]
0x1800082eb  mov     rax, [rdx+28h]
0x1800082ef  lea     edx, [rbx+1]
0x1800082f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f7  mov     eax, ebx
0x1800082f9  add     rsp, 20h
0x1800082fd  pop     rbx
0x1800082fe  retn
```
