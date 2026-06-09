# QueueHandleDescriptor::~QueueHandleDescriptor(void)

- ea: `0x140003ad0`
- end: `0x140003ae8`
- name: `??1QueueHandleDescriptor@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(QueueHandleDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003b20`

## callees

- `0x140003ad0`
- `0x140003af0`

## pseudocode

```c
void __fastcall QueueHandleDescriptor::~QueueHandleDescriptor(QueueHandleDescriptor *this)
{
  DriverSecurityContext *v1; // rcx

  v1 = (DriverSecurityContext *)*((_QWORD *)this + 1);
  if ( v1 )
    DriverSecurityContext::`scalar deleting destructor'(v1);
}

```

## disassembly

```asm
0x140003ad0  sub     rsp, 28h
0x140003ad4  mov     rcx, [rcx+8]; this
0x140003ad8  test    rcx, rcx
0x140003adb  jz      short loc_140003AE2
0x140003add  call    ??_GDriverSecurityContext@@QEAAPEAXI@Z; DriverSecurityContext::`scalar deleting destructor'(uint)
0x140003ae2  add     rsp, 28h
0x140003ae6  retn
```
