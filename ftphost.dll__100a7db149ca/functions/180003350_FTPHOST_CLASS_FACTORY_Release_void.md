# FTPHOST_CLASS_FACTORY::Release(void)

- ea: `0x180003350`
- end: `0x180003386`
- name: `?Release@FTPHOST_CLASS_FACTORY@@UEAAKXZ`
- size: `54`
- prototype: `unsigned int __fastcall(FTPHOST_CLASS_FACTORY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003350`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall FTPHOST_CLASS_FACTORY::Release(FTPHOST_CLASS_FACTORY *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 3);
  if ( !v1 && this )
    (*(void (__fastcall **)(FTPHOST_CLASS_FACTORY *, __int64))(*(_QWORD *)this + 40LL))(this, 1);
  _InterlockedDecrement(&g_dwRefCount);
  return v1;
}

```

## disassembly

```asm
0x180003350  push    rbx
0x180003352  sub     rsp, 20h
0x180003356  or      ebx, 0FFFFFFFFh
0x180003359  lock xadd [rcx+0Ch], ebx
0x18000335e  sub     ebx, 1
0x180003361  jnz     short loc_180003377
0x180003363  test    rcx, rcx
0x180003366  jz      short loc_180003377
0x180003368  mov     rdx, [rcx]
0x18000336b  mov     rax, [rdx+28h]
0x18000336f  lea     edx, [rbx+1]
0x180003372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003377  lock dec cs:?g_dwRefCount@@3JC; long volatile g_dwRefCount
0x18000337e  mov     eax, ebx
0x180003380  add     rsp, 20h
0x180003384  pop     rbx
0x180003385  retn
```
