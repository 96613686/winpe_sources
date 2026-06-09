# ServiceManager::~ServiceManager(void)

- ea: `0x18000e188`
- end: `0x18000e1b2`
- name: `??1ServiceManager@@UEAA@XZ`
- size: `42`
- prototype: `void __fastcall(ServiceManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000aa48`
- `0x18000e1c0`

## callees

- `0x18000d534`
- `0x18000e5d0`

## pseudocode

```c
void __fastcall ServiceManager::~ServiceManager(ServiceManager *this)
{
  const char *v2; // rdx
  __int64 v3; // r8
  const char *v4; // r9

  *(_QWORD *)this = &ServiceManager::`vftable';
  ObjectHandle::~ObjectHandle((ServiceManager *)((char *)this + 88));
  CriticalSection::~CriticalSection((ServiceManager *)((char *)this + 8), v2, v3, v4);
}

```

## disassembly

```asm
0x18000e188  push    rbx
0x18000e18a  sub     rsp, 20h
0x18000e18e  lea     rax, ??_7ServiceManager@@6B@; const ServiceManager::`vftable'
0x18000e195  mov     rbx, rcx
0x18000e198  mov     [rcx], rax
0x18000e19b  add     rcx, 58h ; 'X'; this
0x18000e19f  call    ??1ObjectHandle@@UEAA@XZ; ObjectHandle::~ObjectHandle(void)
0x18000e1a4  lea     rcx, [rbx+8]; this
0x18000e1a8  add     rsp, 20h
0x18000e1ac  pop     rbx
0x18000e1ad  jmp     ??1CriticalSection@@UEAA@XZ; CriticalSection::~CriticalSection(void)
```
