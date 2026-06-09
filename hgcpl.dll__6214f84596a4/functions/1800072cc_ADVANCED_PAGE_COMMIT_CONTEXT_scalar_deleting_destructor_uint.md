# ADVANCED_PAGE_COMMIT_CONTEXT::`scalar deleting destructor'(uint)

- ea: `0x1800072cc`
- end: `0x1800072eb`
- name: `??_GADVANCED_PAGE_COMMIT_CONTEXT@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(ADVANCED_PAGE_COMMIT_CONTEXT *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009de8`
- `0x18000a9c0`

## callees

- `0x180005904`
- `0x18000bd88`

## pseudocode

```c
ADVANCED_PAGE_COMMIT_CONTEXT *__fastcall ADVANCED_PAGE_COMMIT_CONTEXT::`scalar deleting destructor'(
        ADVANCED_PAGE_COMMIT_CONTEXT *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800072cc  push    rbx
0x1800072ce  sub     rsp, 20h
0x1800072d2  mov     rbx, rcx
0x1800072d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800072da  mov     rcx, rbx; lpMem
0x1800072dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072e2  mov     rax, rbx
0x1800072e5  add     rsp, 20h
0x1800072e9  pop     rbx
0x1800072ea  retn
```
