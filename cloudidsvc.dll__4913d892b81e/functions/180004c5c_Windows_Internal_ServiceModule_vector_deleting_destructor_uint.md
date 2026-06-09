# Windows::Internal::ServiceModule::`vector deleting destructor'(uint)

- ea: `0x180004c5c`
- end: `0x180004c90`
- name: `??_EServiceModule@Internal@Windows@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Windows::Internal::ServiceModule *__fastcall(Windows::Internal::ServiceModule *this, __int64, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180004a00`

## callees

- `0x180001a74`
- `0x180004678`
- `0x180004c5c`

## pseudocode

```c
Windows::Internal::ServiceModule *__fastcall Windows::Internal::ServiceModule::`vector deleting destructor'(
        Windows::Internal::ServiceModule *this,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  char v4; // bl

  v4 = a2;
  Windows::Internal::ServiceModule::~ServiceModule(this, a2, a3, a4);
  if ( (v4 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004c5c  mov     [rsp+arg_0], rbx
0x180004c61  push    rdi
0x180004c62  sub     rsp, 20h
0x180004c66  mov     ebx, edx
0x180004c68  mov     rdi, rcx
0x180004c6b  call    ??1ServiceModule@Internal@Windows@@UEAA@XZ; Windows::Internal::ServiceModule::~ServiceModule(void)
0x180004c70  test    bl, 1
0x180004c73  jz      short loc_180004C82
0x180004c75  mov     edx, 38h ; '8'; unsigned __int64
0x180004c7a  mov     rcx, rdi; void *
0x180004c7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004c82  mov     rbx, [rsp+28h+arg_0]
0x180004c87  mov     rax, rdi
0x180004c8a  add     rsp, 20h
0x180004c8e  pop     rdi
0x180004c8f  retn
```
