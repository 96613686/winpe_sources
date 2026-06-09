# Microsoft::HostGuardian::Client::HgServicePlugin::`vector deleting destructor'(uint)

- ea: `0x180014070`
- end: `0x1800140a4`
- name: `??_EHgServicePlugin@Client@HostGuardian@Microsoft@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::HostGuardian::Client::HgServicePlugin *__fastcall(Microsoft::HostGuardian::Client::HgServicePlugin *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180013ffc`
- `0x180014070`

## pseudocode

```c
Microsoft::HostGuardian::Client::HgServicePlugin *__fastcall Microsoft::HostGuardian::Client::HgServicePlugin::`vector deleting destructor'(
        Microsoft::HostGuardian::Client::HgServicePlugin *this,
        char a2)
{
  Microsoft::HostGuardian::Client::HgServicePlugin::~HgServicePlugin(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180014070  mov     [rsp+arg_0], rbx
0x180014075  push    rdi
0x180014076  sub     rsp, 20h
0x18001407a  mov     ebx, edx
0x18001407c  mov     rdi, rcx
0x18001407f  call    ??1HgServicePlugin@Client@HostGuardian@Microsoft@@UEAA@XZ; Microsoft::HostGuardian::Client::HgServicePlugin::~HgServicePlugin(void)
0x180014084  test    bl, 1
0x180014087  jz      short loc_180014096
0x180014089  mov     edx, 88h
0x18001408e  mov     rcx, rdi; Block
0x180014091  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014096  mov     rbx, [rsp+28h+arg_0]
0x18001409b  mov     rax, rdi
0x18001409e  add     rsp, 20h
0x1800140a2  pop     rdi
0x1800140a3  retn
```
