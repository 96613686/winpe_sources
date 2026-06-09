# ServiceManager::`scalar deleting destructor'(uint)

- ea: `0x18000e1c0`
- end: `0x18000e1f4`
- name: `??_GServiceManager@@UEAAPEAXI@Z`
- size: `52`
- prototype: `ServiceManager *__fastcall(ServiceManager *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002330`
- `0x18000e188`
- `0x18000e1c0`

## pseudocode

```c
ServiceManager *__fastcall ServiceManager::`scalar deleting destructor'(ServiceManager *this, char a2)
{
  ServiceManager::~ServiceManager(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e1c0  mov     [rsp+arg_0], rbx
0x18000e1c5  push    rdi
0x18000e1c6  sub     rsp, 20h
0x18000e1ca  mov     ebx, edx
0x18000e1cc  mov     rdi, rcx
0x18000e1cf  call    ??1ServiceManager@@UEAA@XZ; ServiceManager::~ServiceManager(void)
0x18000e1d4  test    bl, 1
0x18000e1d7  jz      short loc_18000E1E6
0x18000e1d9  mov     edx, 90h; unsigned __int64
0x18000e1de  mov     rcx, rdi; void *
0x18000e1e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e1e6  mov     rbx, [rsp+28h+arg_0]
0x18000e1eb  mov     rax, rdi
0x18000e1ee  add     rsp, 20h
0x18000e1f2  pop     rdi
0x18000e1f3  retn
```
