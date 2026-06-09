# CCountedObject::Release(void)

- ea: `0x180004dc4`
- end: `0x180004deb`
- name: `?Release@CCountedObject@@QEAAXXZ`
- size: `39`
- prototype: `void __fastcall(CCountedObject *__hidden this)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180005bf4`
- `0x180005c40`
- `0x180005ee0`
- `0x180005fe8`
- `0x180007ac8`
- `0x180007c2c`
- `0x180007d0c`
- `0x180007e64`
- `0x180008558`
- `0x180008cb0`
- `0x180008eec`
- `0x1800094b8`
- `0x180009580`
- `0x18000a7f0`

## callees

- `0x180004670`
- `0x180004dc4`
- `0x18000c010`

## pseudocode

```c
void __fastcall CCountedObject::Release(CCountedObject *this)
{
  void (__fastcall ***v1)(_QWORD, __int64); // rcx

  if ( !(unsigned int)CCountedObject::InternalRelease(this) )
  {
    if ( v1 )
      (**v1)(v1, 1);
  }
}

```

## disassembly

```asm
0x180004dc4  sub     rsp, 28h
0x180004dc8  call    ?InternalRelease@CCountedObject@@IEAAJXZ; CCountedObject::InternalRelease(void)
0x180004dcd  test    eax, eax
0x180004dcf  jnz     short loc_180004DE6
0x180004dd1  test    rcx, rcx
0x180004dd4  jz      short loc_180004DE6
0x180004dd6  mov     rax, [rcx]
0x180004dd9  mov     edx, 1
0x180004dde  mov     rax, [rax]
0x180004de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de6  add     rsp, 28h
0x180004dea  retn
```
